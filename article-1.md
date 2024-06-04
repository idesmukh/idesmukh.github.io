---
layout: home
title: List copying in Python
---

For those curious about Lists in Python, here are some interesting ideas I've come across while exploring alternative ways to copy lists. Link to code: https://github.com/ibaddesmukh/python-notes/blob/main/list-copy.ipynb

Using the assignment operator: When a list is copied using the assignment operator i.e. "a=b", the copied list only contains a reference to the memory address of the original list object. Therefore, changing the original list object, changes the output of printing the copied list as well.

Shallow copy using list slicing: If you do not want a change in the original list to be reflected in the copied list, a shallow copy of the original list can be created through list slicing using the "copy_list=orig_list[:]" statement. This creates a real copy of all the top-level elements of the original list and saves them in a list in a new memory address. Therefore, changing the top-level elements of the original list object does not change the output of printing the copied list. However, if the original list contains another list that is nested inside it, a change in an element of the nested list in the original list will be reflected as a change in an element of the nested list in the copied list. This is because the nested list in the copied list is only a reference to the memory address of the nested list in the original list. This is why it's called a "shallow copy".

Deep copying using copy.deepcopy() function: If you do not want a change in the nested list of the original list to be reflected in the copied list, a deep copy of the original list can be created using "copy_list = copy.deepcopy(orig_list)" statement. This function iterates through all elements in the original list, including all its nested lists, creates a real copy and saves it in a new memory address. This is why it's called a "deep copy".
