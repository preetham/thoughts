---
title: "Linked List (Part 1)"
date: 2021-04-25
slug: "linked-list-part-1"
description: "Linked List introduction and experiences"
keywords: ["thoughts", "blog", "computerscience", "developer", "linkedlist", "computers"]
draft: false
tags: ["comsci"]
math: false
toc: false
---

# Linked Lists (Part 1)
```
DISCLAIMER: Some of the concepts explained here might feel dumbed down, this is just my pathway of understanding. Please be mindful of it.
```
Linked Lists are a type of data structure that are connected via pointers. Any singly linked list contains nodes where each node consists of a data member and a pointer which points to the next node in the list. There is also a doubly linked list which is essentially a singly linked list with an extra pointer in each node which points to the previous node in the list.
Linked lists are advantageous over arrays as they don't require contiguous allocation of memory. The drawback here is that now access to nodes cannot be random, it cannot be performed in O(1) time.

Think of linked list as a train with each compartment representing a node, there might a two way passthrough in between the compartments (doubly linked list) or it can be a one way passthrough (singly linked list). Linked lists are usually the first foray of any ComSci student into struct/class based data structures, which can confuse some people (myself included). I initially didn't understand the concept of a node's member type being the node itself. For example:
```c
struct Node {
    int data;
    Node *next;
}
```
I somehow couldn't wrap around the concept of `next` being type `Node*`, later realising that it represents a connection to an element of type Node, which makes sense as linked list just comprises of multiple Nodes. This might be pretty trivial to most of you but the concept of pointers scared me during the initial days of programming, I didn't understand their significance or their purpose until I started programming in Golang couple of years ago. Somehow this time it clicked, I initially understood it as a way to not pass by value all the time in a program, large data had to be passed around inside a program I was working on and it made sense to just pass around the pointer and not burden the runtime to copy the entire data while passing to a different method.

As I am currently solving problems on Linked Lists again in preparation, I came across a problem I was asked 3 years ago in a interview: `Detect a cycle in a singly linked list`.

![Linked List with a cycle](/images/cycled-linked-list.png)

I hadn't really prepared for an interview at that point in time, just started applying around after approximately a year's work experience. A startup called me for an in person interview at a fancy co-working space inside a massive office complex. The interviewer was the company CTO, who quiet patiently tried to give multiple hints and push me towards the solution. I never came across such a problem before and I didn't get an intuition to use two different pointers for solving the problem (bear in mind I was not really a fan of pointers at the time). Although I couldn't solve the problem at all, he went through the solution and explained the concept of a fast pointer and a slow pointer. Just to give context, the solution goes like this: we take two pointers - one which traverses the list one node at a time (slow pointer), one which traverses the list two nodes at a time (fast pointer); since the fast pointer traverses the list quicker, if there is a cycle in the linked list it should meet up with the slow pointer at some point. If the slow pointer reaches the end of linked list (becomes `NULL` in C++), there is no cycle. It felt like a eureka moment to me, but I also wanted to ask some questions to seem a little smart in the interview (I genuinely didn't understand the reason also at the time) so I asked why he specifically took two as the distance traversed for the fast pointer and why not three. I was fixated on that quesiton for sometime, eventually giving up on the logic for it. Looking back it is kind of a dumb question as it doesn't matter what the pace of fast pointer is, as long as the slow pointer pace is one and the fast pointer pace is anything greater than one. This way any distance traversed by fast pointer is can be reached by slow pointer (any whole number is divisible by one).

Currently I am able to solve these two pointer based linked list problems, have a plan to complete linked list based problems this week. Stay tuned.