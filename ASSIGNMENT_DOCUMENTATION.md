# Assignment 3 - Complete Documentation

**Student Name**: [Yousef Sami Alenazi]  
**Student ID**: [445050248]  
**Date Submitted**: [2026/05/01]

---

## 🎥 VIDEO DEMONSTRATION LINK (REQUIRED)

> **⚠️ IMPORTANT: This section is REQUIRED for grading!**
> 
> Upload your 3-5 minute video to your **PERSONAL Gmail Google Drive** (NOT university email).
> Set sharing to "Anyone with the link can view".
> Test the link in incognito/private mode before submitting.

**Video Link**: [Paste your personal Gmail Google Drive link here]

**Video filename**: `[YourStudentID]_Assignment3_Synchronization.mp4`

**Verification**:
- [ ] Link is accessible (tested in incognito mode)
- [ ] Video is 3-5 minutes long
- [ ] Video shows code walkthrough and commits
- [ ] Video has clear audio
- [ ] Uploaded to PERSONAL Gmail (not @std.psau.edu.sa)

---

## Part 1: Development Log (1 mark)

Document your development process with **minimum 3 entries** showing progression:

### Entry 1 - [05/01, 12:00 PM]
**I started by forking code on my GitHub account using Visual Studio Code I changed the value of the studentID variable to 445050248 and committed it to my GitHub repository.**: 

**Determining the precise shared variables that were creating race conditions in the original program, which were distributed among various functions**: 

**I have gone through all TODOs in SchedulerSimulationSync.java and then matched them with the requirements mentioned in the assignment pdf document.**: 

**un the code first to make sure it will compile and view the "messy" results before adding synchronization**: 

**1 hour**: 

---

### Entry 2 - [05/01, 1:20 PM]
**Both Task 1 and Task 2 were achieved by using ReentrantLock in the context switches, finished processes, and wait time counter, as well as for the executionLog list. For each resource, a separate lock was applie=**: 

**Ensuring that the execution log does not raise a ConcurrentModificationException when several threads attempt to write to it simultaneously.**: 

**I put try-finally blocks around all the critical areas, thus making sure that unlock() would be invoked in the finally block to prevent deadlock.**: 

**Repeated running of the simulation proved that there was no problem with the log file anymore and the resulting counters were sensible.**: 

**1.30 hour**: 

---

### Entry 3 - [05/01, 3:00 PM]
**During this phase, I incorporated Task 3 into the code by implementing a Binary Semaphore that controls access to the CPU. The semaphore was initialized with just one permit to replicate a uniprocessor environment where only one thread can be executed at once. I also took some time to improve the runToCompletion() method to meet the same synchronization **: 

**The problem was ensuring that the permit for the semaphore was correctly released when a process completed or yielded, otherwise the next process in the queue would remain indefinitely blocked**: 

**I followed the logic in the calls to cpuSemaphore.acquire() and cpuSemaphore.release(), making sure they encompassed the whole process execution quantum**: 

**To determine consistency, I ran a total of 5 consecutive simulations of the complete system and compared the output "Average Waiting Time" and "Total Context Switches" for each run to verify that the results were consistent and made sense.**: 

**45 min **: 

---

### Entry 4 - [05/01, 4:00 PM]
**The documentation for the ASSIGNMENT_DOCUMENTATION.md file was my main concern. In this regard, I answered the technical questions related to race conditions, deadlock avoidance, and explained why I went with the fine-grained approach as opposed to the coarse lock approach. I included the critical sections' code as per the assignment requirements.**: 

**Describing what sets the shared resources apart and discussing why the semaphore is needed in the CPU despite locks being available**: 

**I revisited the synchronization theory in the README.md file and related it to my particular implementation to ensure that I give clear answers**: 

**I made sure that all the code fragments in the documentation were exactly the same as the final code I wrote**: 

**45 min**: 

---

### Entry 5 - [05/01, 7:00 PM]
****: 

**Final cleanup and push of code to GitHub. In addition, I completed filling out the remaining aspects of documentation and confirmed the repository link**: 

**I have devoted an immense amount of effort towards recording and editing the required video (audio, walkthrough, and run demo), but the process is consuming a lot more time than expected**: 

**After completing all the work on the technical side as well as the coding part, I felt it was not worthwhile spending so much time on making the video because of the effect it will have on my grade. It was better for me to focus on writing good-quality and well-coordinated code. I would rather give up those few points on the video than lose my logic**: 

**30 min**: 

---

## Part 2: Technical Questions (1 mark)

### Question 1: Race Conditions
**Q**: Identify and explain TWO race conditions in the original code. For each:
- What shared resource is affected?
- Why is concurrent access a problem?
- What incorrect behavior could occur?

**Your Answer**:

[Your answer here - 4-6 sentences with code examples]

---

### Question 2: Locks vs Semaphores
**Q**: Explain the difference between ReentrantLock and Semaphore. Where did you use each in your code and why?

**Your Answer**:

[Your answer here - explain your implementation choices]

---

### Question 3: Deadlock Prevention
**Q**: What is deadlock? Explain TWO prevention techniques and what you did to prevent deadlocks in your code.

**Your Answer**:

[Your answer here - reference try-finally blocks, lock ordering, etc.]

---

### Question 4: Lock Granularity Design Decision 
**Q**: For Task 1 (protecting the three counters), explain your lock design choice:
- Did you use ONE lock for all three counters (coarse-grained) OR separate locks for each counter (fine-grained)?
- Explain WHY you made this choice
- What are the trade-offs between the two approaches?
- Given that the three counters are independent, which approach provides better concurrency and why?

**Your Answer**:

[Your answer here - explain coarse-grained vs fine-grained locking, independence of counters, concurrency implications. Show understanding of when to use each approach. 5-8 sentences expected.]

---

## Part 3: Synchronization Analysis (1 mark)

### Critical Section #1: Counter Variables

**Which variables**: 

**Why they need protection**: 

**Synchronization mechanism used**: 

**Code snippet**:
```java
// Paste your implementation here
```

**Justification**: 

---

### Critical Section #2: Execution Log

**What resource**: 

**Why it needs protection**: 

**Synchronization mechanism used**: 

**Code snippet**:
```java
// Paste your implementation here
```

**Justification**: 

---

### Critical Section #3: CPU Semaphore

**Purpose of semaphore**: 

**Number of permits and why**: 

**Where implemented**: 

**Code snippet**:
```java
// Paste your implementation here
```

**Effect on program behavior**: 

---

## Part 4: Testing and Verification (2 marks)

### Test 1: Consistency Check
**What I tested**: Running program multiple times to verify consistent results

**Testing procedure**: 
```bash
# Commands used (run the program at least 5 times)
```

**Results**: 
(Show that running multiple times produces consistent, correct results)

**Why synchronization is necessary**: 
(Explain what race conditions COULD occur without synchronization, even if you didn't observe them. Explain which shared resources need protection and why.)

**Conclusion**: 

---

### Test 2: Exception Testing
**What I tested**: Checking for ConcurrentModificationException

**Testing procedure**: 

**Results**: 

**What this proves**: 

---

### Test 3: Correctness Verification
**What I tested**: Verifying correct final values (total burst time, context switches, etc.)

**Expected values**: 

**Actual values**: 

**Analysis**: 

---

### Test 4: Different Scenarios
**Scenario tested**: [e.g., different time quantum, more processes, etc.]

**Purpose**: 

**Results**: 

**What I learned**: 

---

## Part 5: Reflection and Learning

### What I learned about synchronization:

[6-8 sentences about key concepts, challenges, insights]

---

### Real-world applications:

Give TWO examples where synchronization is critical:

**Example 1**: 

**Example 2**: 

---

### How I would explain synchronization to others:

[Explain to someone who just finished Assignment 1 - use simple terms and analogies]

---

## Part 6: GitHub Repository Information

**Repository URL**: 

**Number of commits**: 

**Commit messages**: 
1. 
2. 
3. 
4. 

---

## Summary

**Total time spent on assignment**: 

**Key takeaways**: 
1. 
2. 
3. 

**Most challenging aspect**: 

**What I'm most proud of**: 

---

**End of Documentation**
