---
layout: post
author: rahimi
---

I'm on the journey to finish my diploma Final Year Project, I'll be building a Clinic Management System using Python Django on the Back-end, Html, Css and Bootstrap5 for the Front-end. In this blog, I want to explain about how we can can get data from primary key and fill a form using it using Class Based View (CBV).

The situation is, I want to implement a check in system, where I can check in patient who came to the clinic, and render the data on the webpage. The check in list will be easy, I just have to use to inherit/extends `ListView`. Example:

```

clinic/urls.py

...
app_name = "clinic"
urlpatterns = [
    path("checkin_list/", views.ListCheckInPageView.as_view(), name="checkin_list"),
]

```

```

clinic/views.py

class ListCheckInPageView(ListView):
    template_name = "clinic/checkin_list.html"
    queryset = CheckIn.objects.all().order_by("-check_in_time") # this will display the latest on top
    context_object_name = "checkin_list"

```

---

Now, this is easy right ? Well, kinda. The problem is when you want to check in patient based on their data. I have two situation where I want to check in patient 1) from the check in list, I want to implement a link/button to create new check in 2) from patient detail, I want to directly check in current patient and automatically get their data. Situation 1 should be easy to implement, example:

```

clinic/urls.py

... new code

path("checkin_list/checkin/" views.CheckInView.as_view(), name="checkin")

... end new code

```

```

clinic/views.py

... new code

class CheckInView(FormView):
    template_name = "clinic/checkin_patient.html"
    form_class = CheckInForm
    success_url = reverse_lazy("clinic:patient_list")

    def form_valid(self, form):
    form.save()
    return super().form_valid(form)

    ... end new code
```

---

To implement situation two, we will need new url, because we want an url that can handle argument which is patient primary key. 

```

clinic/urls.py

... new code

path("patient_list/<int:pk>/checkin/", views.CheckInView.as_view(), name="checkin_pk")

... end new code

```

Now, the problem is: should we create another view or use the same CheckInView with additional logic inside it ? Here's what I've learn to handle this problem. To handle the problem, we need a condition where if there is primary key, we will return it, or else we will not return anything. Something like this:

```

clinic/views.py

...

class CheckInView(FormView):
    ... new code

    def get_context_data(self, **kwargs):
        context = super().get_context_data(**kwargs)
        patient_pk = self.kwargs.get("pk")

        if patient_pk:
            patient = get_object_or_404(Patient, pk=patient_pk)
            context["patient"] = patient 

        return context
    

    def get_initial(self):
        initial = super().get_initial()
        patient_pk = self.kwargs.get("pk")

        if patient_pk:
            patient = get_object_or_404(Patient, pk=patient_pk)
            initial["patient"] = patient

        return initial

    ... end new code

```

What happen in the additional view logic is, we check if primary key available, and then return it. We also need to get initial to fill the form with the data, so we fill the form based on the primary key given. Let's say our url now is `patient_list/1/checkin/`, we'll use the data from patient with primary key = 1 to fill the form.

This logic actually can be use in many situation, what if you want to fill appointment list with the patient data ? Let's say you're the clinic staff, you open this patient detail page --say the name of the patient is Dave. Then you click add appointment, but the form need you to fill the patient data, by using the logic, you have to fill appointment description and date only, not fill it from scratch. 

...CYA!