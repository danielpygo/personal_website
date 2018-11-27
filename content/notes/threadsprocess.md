---
title: "Threads and Processes"
date: 2018-07-10
description: "Notes about differences between the two"
type: "notes"
draft: false
---
Process is an executing program

A process can consist of multiple threads

Threads are lightweight processes used to complete small tasks; processes used for heavier tasks.

## Advantages of Threads:
* Lightweight
* Can read and write to the same data structures and resources.

## Disadvantages of Threads:
* IPC is difficult and errors arise
* Synchronization and race conditions
* Requires careful attention; must use a lock to prevent other threads from running a certain critical section

## Advantages of Process
* Independent of each other (threads are interdepedent)

## Context Switching
* The process of storing an d restoring context of a program so that the exectuion can be resumed from the same point at another time. Memory caches have to be flushed and reloaded for the new process. Overhead in determining what process to execute next.
* Usually takes 3-5 microseconds
