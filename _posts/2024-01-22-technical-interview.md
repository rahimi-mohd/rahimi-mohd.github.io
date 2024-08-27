---
layout: post
author: rahimi
---

Hello world, one of my goals for this year is to get an IT job, the positions that I focus on are backend engineer and software tester (manual or automation). Since I'm already on my second year of my diploma, I tried to apply for some job which I think suits me and where I can get a real experiences from. Even though I really want to start working and learn hands on this year, I don't have high hope that I can land a job since I know the job market for IT this year has been unstable with all the layoff and stuff, but I want to try my luck and see what happen.

To my suprise, there's some companies who reach back and want to interview me. Unfortunately, I have to reject one interview (backend/embedded engineer), due to it being too far from my home and they didn't allowed work from home. Actually, I don't care about working from office, I just don't want to spend half of my day on the road commuting from home to office and back.

There's one more company for backend engineer internship approached and asked me to fill a Google Form regarding my details and tech stack. So I fill out the form and... I don't know maybe they're ok with my details and tech stack so they asked me to attend IQ test and technical test on wed, 17 Jan 2024. So this is my first technical interview experiences.

I have two and a half day to prepare for my first technical test, first thing that come to mind is LeetCode. I have never tried LeetCode before and I know I suck at problem solving, this is because I spend too much time on learning programming languages instead of learning programming and problem solving. I can solved two sum with two for loops but I know, this is not the optimum answer, then I study the solution which using map or dictionary. I realized now that I'm suck at problem solving and I need to study more. I don't know what to expect for my interview, I just hope that they didn't have this kind of questions.

During the interview, there's only one person and she didn't asked me too many question since this is not behavioral interview, so she just asked me to introduced myself and I can start if I'm ready. When I said I'm ready, she shared with me the IQ test questions and I have to share my screen to answer the questions, they were all subjective questions where you have to think about the answer and there's no hint. I guess I can answer most of them, even though I don't know how IQ test work and I don't even know if my answers are correct or not. What shock me the most is that I have to really write the answer for IQ test, I thought all IQ test use Multi Choice Question (MCQ) format but not this time I guess.

After IQ test, we go straight to technical test. So the questions are not too bad, it just..... I blank. I'm not sure how to describe the situation but I can't think straight and I kinda lost it. So I have a choice whether to write complete code in python or just write pseudocode, obviously this will affect the mark --since they are looking for python developer. The problem happened when I tried to write python code for question one but when I run it, it doesn't do what it's supposed to do, so I panicked and I think that's the reason why I can't answer most of the questions. When I checked back the questions after the interview, I started to laugh out loud and think "what the heck is wrong with me, how can I be so stupid ?"."

Here are the questions and how I solved it **after** the interview, I can't remember how I answer it during the interview because I give up writing the answer in python after it failed to run as intended for question one. I guess I got it all right using pseudocode but who know ? Maybe they will review it back with me later. 

**Notes** All the question have been changed to make it shorter, and the answer is not the answer I write during the interview, this is the answer I think of after the interview. **END**

### Question One

Given two list of names, return new list without duplicate values.
Example:
name_1 = ["ava", "olivia", "emma"]
name_2 = ["olivia", "sophia", "emma"]
unique_names(name_1, name_2)
should return ["emma", "olivia", "sophia"]

**My answer**

```
    def unique_names(l: list[str], ll: list[int]) -> list[int]:
        names = l + ll
        return list(set(names))
```
---

### Question Two:

Create a function find_roots to find the roots of the quadratic equation: ax**2 + bx + c = 0. You can find the formula for the roots of the quadratic equation <a href="https://en.wikipedia.org/wiki/Quadratic_equation">here.</a>

**My answer:**

```
    import math
    def find_roots(a: int, b: int, c: int) -> list[int]:
        d = math.sqrt(b**2 - 4 * a * c)
        root_1 = (-b + d) / (2 * a)
        root_2 = (-b - d) / (2 * a)
        return [root_1, root_2]
```
---

### Question Three:

Given a files with key value of k: text_file_name, v: name, return a map of k: name, v: list_of_text_file_name.

**My answer:**

```
    files = {
        "Input.txt" : "Randy",
        "Code.py" : "Stan",
        "Output.txt" : "Randy"
    }

    def group_by_owner(files: dict) -> dict:
        m = {}
        for k, v in files.item():
            if v not in m:
                m[v] = [k]
            else:
                m[v].append(k)
        
        return m
```
---

### Question Four:

Implement TextInput class that contains method add(text), which add given text to the current value. Method get_value(), which return the current value in string
Implement NumericInput class that inherit from TextInput, override the add method so that each non-numeric text is ignored.

**My answer**

```
    class TextInput:
        def __init__(self):
            self.value = ""
        def add(self, text):
            self.value = text    
        def get_value(self):
            return self.value
    class NumericInput(TextInput):
        def add(self, text):
        if text.isdigit():
            self.value += text
```
---

### Conclusion

I know, the questions were easy and it should really be a problem. I guess everybody have this *first-time-syndrome*, where they're easily panic and can't focus to think clearly. Other reason why I'm panic is because I have this expectation that they will give me LeetCode's style of question and that make me panic even before I see the questions.

So yeah, that's my first ever technical interview experiences, even though I don't have high expectation regarding the result, I'll be lying if I say that I don't want it to pass. Finally, there's alot to learn and to be improve in the future, let's try our best to get what we want and ...CYA!