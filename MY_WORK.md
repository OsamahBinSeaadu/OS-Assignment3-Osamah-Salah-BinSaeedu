# 📝 MY_WORK: Student Information, Development Log, Reflection & Answers

> This is the **only file** your instructor reads to grade Parts 3 and 4 (documentation and video). Everything you write here must be **in your own words**.

---

## 🛑 STOP: Read This Before You Do Anything Else

> ### 1️⃣ Read the whole `README.md` first
> The `README.md` in this repository contains the full instructions: how this assignment continues Assignment 1, the Chapter 5 recap, class descriptions, feature specifications, question prompts and the video script. **If you skip it, you will lose marks.**
>
> ### 2️⃣ Understand the full code before answering any question
> Open `SchedulerSimulationSync.java` and read it **from top to bottom**. You must be able to explain what `SharedStats`, `ReadyQueue`, `CpuWorker`, `RaceWindow.pause()`, `ReentrantLock` and `Semaphore` do **before** you write a single answer in Parts B and C. **Run the original starter first** (it is intentionally broken) and **save its output**: you need it for Question 1 of Part C.
>
> ### 3️⃣ Use only the code of this repository
> Work **only** on `SchedulerSimulationSync.java` from this repository. Do **not** copy or paste code from your previous assignments.
>
> ### 4️⃣ Commit many times, not once
> A single commit, or all commits made in the last hour, costs you **-0.5 mark**. See the [Commit Rules](#-commit-rules-mandatory) below.

**How to use this file:**
1. Fill in your **Student Information** (below) right now.
2. Follow the steps in the **Work Roadmap** in order.
3. Update the **Development Log** *every time* you work on the assignment, not at the end.
4. Do not delete any section header. Replace the `[...]` placeholders with your own text.

---

## 👤 Student Information

> ⚠️ **WARNING:** Fill this in first. Your name and ID must match the student ID you set in `SchedulerSimulationSync.java` (line 304) and the one you say in your video.

| Field | Your Answer |
|-------|-------------|
| **Full Name** | Osamah Salah Bin Saeedu |
| **Student ID** | 445052781 |
| **University Email** | 445052781@std.psau.edu.sa |
| **GitHub Username** | OsamahBinSeaadu|
| **Repository Link** | https://github.com/OsamahBinSeaadu/OS-Assignment3-Osamah-Salah-BinSaeedu.git |
 
---

## 🎥 Video Link

**Video Link**: [Paste your video link here]

> ⚠️ **WARNING:** The video must be **publicly accessible** ("Anyone with the link can view") on **Google Drive**, **YouTube (Unlisted or Public)** or any other cloud file-sharing system. A private, restricted or broken link counts as a **missing video (-1 mark)**.
>
> 💡 **TIP:** Open the link in a **private/incognito window** before you submit. If it asks you to log in or request access, it is not public.
>
> 📌 **NOTE:** The link goes in **this file only** (`MY_WORK.md`), **not** in `README.md`. Name your video file `StudentID_Assignment3_Demo.mp4`. It must last **2 to 3 minutes**.

---

## 🗺️ Work Roadmap (follow in this order)

| Step | What to do | Where | Marks |
|:----:|------------|-------|:-----:|
| 0 | Read `README.md`, read the full code, **run the original starter and save its output** (it fails on purpose) | Your IDE | – |
| 1 | Fork, rename, keep the repo **PUBLIC**, set your student ID (line 304), **commit** | GitHub + code | Part 1 (1) |
| 2 | Feature 1: Mutex lock on the ready queue, **commit** | Code | Part 2 (0.25) |
| 3 | Feature 2: Mutex lock(s) on the shared statistics, **commit** | Code | Part 2 (0.25) |
| 4 | Feature 3: Counting semaphore instead of busy waiting, **commit** | Code | Part 2 (0.5) |
| 5 | Development Log (5+ entries, different dates) | This file, Part A | Part 3 (0.5) |
| 6 | Reflection (4 questions) | This file, Part B | Part 3 (0.5) |
| 7 | Technical Answers (4 questions) | This file, Part C | Part 3 (0.5) |
| 8 | Record the video, upload it, paste the link above | Video + this file | Part 4 (1.5) |
| 9 | Final check, then submit the repo link on Blackboard | Blackboard | – |

> 💡 **TIP:** Tick each step off as you go. Do not leave the log, the reflection or the video for the last day.

---

## 🔁 Commit Rules (MANDATORY)

> ### ⚠️ MANY COMMITS ARE REQUIRED. A single bulk commit is penalized (-0.5 mark).

**Minimum: 4 meaningful commits. Aim for 7 or more.**

| # | Commit | Example message |
|:-:|--------|-----------------|
| 1 | Student ID set | `Set my student ID: 441234567` |
| 2 | Feature 1: Ready queue lock | `Feature 1: Protected the ready queue with a ReentrantLock` |
| 3 | Feature 2: Statistics locks | `Feature 2: Added locks to the shared statistics counters` |
| 4 | Feature 3: Semaphore | `Feature 3: Replaced busy waiting with a counting semaphore` |
| 5 | Development log entries | `Docs: Added development log entries 1-3` |
| 6 | Reflection and answers | `Docs: Completed reflection and technical answers` |
| 7 | Video link | `Docs: Added demo video link` |

**Rules:**
- ✅ **One commit per feature.** Do not put all three features in one commit.
- ✅ **Commit after each work session**, and after each part of this file.
- ✅ **Spread your commits over different dates.** Not all in one day.
- ❌ **Do not make all commits in the last hour** before the deadline (November 14, 2026).
- ❌ **No vague messages** like `done`, `update` or `final version`.

> 💡 **TIP:** Your commit history is checked and you **show it in your video** (at least 4 commits visible). Your development log dates should match your commit dates.
>
> 💡 **TIP:** **Use VS Code** (see *Recommended Development Environment* in `README.md` for the full setup). Sign in to GitHub in VS Code, then commit from the Source Control panel (Ctrl+Shift+G) → stage → write a message → Commit → Sync/Push. You can edit and commit this file the same way. **Pushing** matters: commits that are not pushed to GitHub are invisible to the instructor.

---

# Part A: Development Log (0.5 mark)

> ⚠️ **WARNING:** Minimum **5 entries**, spread over **different dates**. Five entries written on the same day, or written all at once at the end, will lose marks and look like a copy. Entry dates should be **between the start of the assignment and the deadline (November 14, 2026)**.
>
> 💡 **TIP:** Write an entry at the **end of each work session**, while you still remember what happened. It takes 5 minutes.
>
> 💡 **TIP:** Be specific. "Worked on the code" is a weak entry. "Added a `ReentrantLock queueLock` to `ReadyQueue` and wrapped the body of `poll()` in `lock()` / `try` / `finally { unlock() }`" is a strong one.
>
> 📌 **NOTE:** Each entry needs: date and time, what you did, details, challenges, solution, and time spent. Real challenges are fine (and expected). Do not invent fake ones.

## Example Entry (do not copy it, write your own)

### Entry 1 - [November 2, 2026, 4:30 PM]
**What I did**: Forked the repository, set my student ID, and ran the original starter

**Details**:
- Forked the starter repository and renamed it
- Changed student ID on line 304 to my actual ID (441234567)
- Ran the original program: 4 CPUs started, three of them picked `P1`, then `IllegalThreadStateException` and the watchdog stopped the program
- Saved the output in a text file for Question 1
- Committed and pushed: `Set my student ID: 441234567`

**Challenges**: I did not understand why the same process was picked by three CPUs

**Solution**: Read `ReadyQueue.poll()` again and found the `RaceWindow.pause()` between reading the head and removing it

**Time spent**: 45 minutes

---

## Your Development Log

### Entry 1 - [November 13, 2026, 7:00 PM]
**What I did**:Forked the repository, set my student ID and ran the original starter

**Details**:
- Forked `makopt/OS-Assignment3-Starter-481`, renamed it to `OS-Assignment3-Osama-BinSaeedo` and checked that it is public
- Changed line 304 to `int studentID = 445052781;`
- My parameters: 11 processes, time quantum 4000 ms, 2 CPUs
- Ran the original starter: CPU-2 and CPU-1 both picked `P1`, then `IllegalThreadStateException` on CPU-1, `P2` was never executed and the watchdog stopped the program after 40 s
- Saved the starter output for Question 1
- Committed and pushed: `Set my student ID: 445052781`

**Challenges**:I had no problem with the code at this step, but at first I did not understand the link between the exception, the watchdog and the wrong counters: everything failed at the same time, so I did not know which problem came first.

**Solution**: I used the table in the README ("What you see in the console / What it means"). It showed me that two CPUs picking `P1` and a lost process are caused by the missing ready queue lock (Feature 1), so I started with that.

**Time spent**:[30 minutes]

---

### Entry 2 - [November 13, 2026, 7:30 PM]
**What I did**:Feature 1: protected the ready queue with a ReentrantLock

**Details**:
- Added `import java.util.concurrent.locks.ReentrantLock;`
- Declared `private final ReentrantLock queueLock` in `ReadyQueue`
- Wrapped the bodies of `add()`, `poll()`, `processOf()` and `snapshot()` in `queueLock.lock()` / `try` / `finally { queueLock.unlock(); }`
- Ran the program 5 times: no more exception and no lost process, but context switches were 23 instead of 27 and total service time 75639 instead of 83639 (this is Feature 2)
- Committed and pushed: `Feature 1: Protected the ready queue with a ReentrantLock`

**Challenges**: I was not sure if the lock is really released in `poll()`, because the `return` statements are inside the `try` block and the method leaves before reaching the end of the code.

**Solution**: The README tip says the `finally` block still runs after the `return`, and the slides describe the exit section that must always release permission. So I kept `unlock()` only in `finally` and did not call it before the `return`.


**Time spent**: 45 minutes

---

### Entry 3 - [November 13, 2026, 8:30 PM]
**What I did**:Feature 2: protected the three shared statistics with one lock per variable

**Details**:
- Declared `contextSwitchLock`, `completedLock` and `serviceTimeLock` in `SharedStats`
- Protected the three update methods and the three getters with lock / try / finally
- Ran the program 5 times: the first three verification lines were always ✔ (27, 11, 83639); only `Busy-waiting polls` was still 1 to 3
- Committed and pushed: `Feature 2: Added locks to the shared statistics counters`

**Challenges**:This was the hardest part for me. I did not know if I should use one lock for the three counters or one lock for each counter, and I had to justify my choice. One lock looked simpler and safer, so at first I did not see why three locks would be better.


**Solution**:I re-read the critical-section part of the slides and the hint in the README that the three variables are independent. I checked the code: no method changes two counters together. So a thread adding service time does not need to wait for a thread counting a context switch. I chose one lock per variable to reduce waiting, and I accepted the cost of having more locks to manage.

**Time spent**: 1 Hours

---

### Entry 4 - [November 13, 2026, 9:30 PM]
**What I did**:Feature 3: replaced busy waiting with a counting semaphore

**Details**:
- Added `import java.util.concurrent.Semaphore;` and declared `final Semaphore readyCount = new Semaphore(0)` in `ReadyQueue`
- Called `readyCount.release()` at the end of `add()`, after releasing `queueLock`
- In `CpuWorker.run()`: replaced the polling code by `readyCount.acquire()` and added the shutdown: the CPU that sees completed == total calls `release(SharedStats.totalCPUs)`, and a CPU that wakes up when everything is completed stops
- Ran the program 6 times: all four lines ✔, `Busy-waiting polls = 0`, the program ends by itself in about 9 s
- Committed and pushed: `Feature 3: Replaced busy waiting with a counting semaphore`

**Challenges**: Choosing the initial value of the semaphore and understanding the end of the program: if the CPUs sleep in `acquire()`, who wakes them up when there are no more processes?

**Solution**: The slides define the semaphore value as the number of available resources, and the queue is empty at the start, so the value is 0 (the README common mistakes also warn that 1 is wrong). For the end, I followed the README: the CPU that sees the last process complete calls `release(totalCPUs)`, and a CPU that wakes up when everything is completed stops instead of polling.


**Time spent**:1 Hours

---

### Entry 5 - [November 13, 2026, 11:00 PM]
**What I did**:Documentation: wrote the reflection and the technical answers in MY_WORK.md

**Details**:
- Pasted the verification block of the starter and of my final version in Question 1
- Answered the four technical questions and the four reflection questions
- Committed and pushed: `Docs: Completed reflection and technical answers`

**Challenges**: Explaining the starter failure with my own numbers. The starter mismatch (25 instead of 27) was not a lost update on the counter but the lost process `P2`, so I had to separate the two problems.

**Solution**:I used the output of the version with only Feature 1 (23 instead of 27, 75639 instead of 83639) to explain the lost update on `contextSwitchCount`, and the starter output to explain the lost process.

**Time spent**:1 Hours

---

### Entry 6 - [Optional - November 14, 2026, 1:20 AM]
**What I did**:Recorded the video and added the link

**Details**:- Recorded the demo in VS Code (repository, 3 features, execution, concept, commit history)
- Uploaded `445052781_Assignment3_Demo.mp4`, set it to "Anyone with the link", tested it in incognito
- Committed and pushed: `Docs: Added demo video link`


**Challenges**:Keeping the video between 2 and 3 minutes while showing everything required (repository, 3 features, execution, one concept, commits).

**Solution**:I prepared the order of what to show, did a test recording, and shortened my explanation of the code so the verification block stays visible a few seconds.

**Time spent**: 20 minutes

---

## Development Log Summary

> 💡 **TIP:** Fill this in **last**, after all entries are written.

**Total time spent on assignment**: [6 hours]

**Most challenging part**:Choosing the lock granularity for the statistics (one lock for the three counters or one lock per counter) and being able to justify it.

**Most interesting learning**: Seeing two CPUs pick the same process `P1` in my own output, and that a simple `count++` can lose updates because it is three steps and not one.

**What I would do differently next time**: Start earlier and spread my work over more days, and write each log entry right after the session instead of later.


---

# Part B: Reflection (0.5 mark)

> 🛑 **STOP:** Do **not** start this part until you have read the `README.md`, read the **entire** `SchedulerSimulationSync.java`, run it, and finished the three features.
>
> ⚠️ **WARNING:** Each answer must be **5 to 7 sentences**, in **your own words**. Copied or AI-generated answers without understanding get **0 marks for the whole assignment**. You may be asked to explain them in person.
>
> 💡 **TIP:** Mention concrete things you actually did: a method you wrote, an error you hit, a line of output you saw. Generic answers score low.
>
> 💡 **TIP:** Draft your answer in a few bullet points first, then turn them into sentences.

## Question 1: What did you learn about synchronization?

> 💡 **TIP:** Talk about race conditions (read-modify-write), critical sections, mutual exclusion with `ReentrantLock` and `try/finally`, the role of a counting semaphore, and what surprised you when the starter failed.

**Your Answer:** *(5-7 sentences)*

I learned that a race condition happens when several threads change the same shared data and the result depends on the order of their steps. Before this assignment I thought `count++` was one operation, but it is a read, an addition and a write, and a thread can be stopped between them. In my starter output I saw CPU-1 and CPU-2 both pick `P1`, and `P2` was lost without running, so the problem is not only theory. I learned that the code that touches shared data is a critical section, and that a `ReentrantLock` gives mutual exclusion on it. I also understood why `unlock()` must always be in `finally`: if an exception happens, the lock is still released. Finally, I learned that a counting semaphore can count the processes in the queue and make a CPU sleep instead of checking the queue again and again.

## Question 2: What was the most challenging part of this assignment?

> 💡 **TIP:** Pick **one** specific challenge (understanding why the starter failed, choosing the lock granularity, the initial value of the semaphore, the shutdown of the CPUs, Git, the video) and say *why* it was hard.

**Your Answer:** *(5-7 sentences)*

The most challenging part for me was Feature 2, choosing the lock granularity for the three statistics. The code was not difficult to write, but I had to decide between one lock for the three counters or one lock per counter, and justify it in this file and in the video. One lock looked simpler and safer, so at first I did not understand why I would need three. I also worried that more locks could create more problems, like a deadlock. It was hard because both solutions give correct results in the verification block, so the output alone could not tell me which one is better. I had to think about how the threads actually use the counters, not only about whether the program works.

## Question 3: How did you overcome the challenges you faced?

> 💡 **TIP:** Describe your method: reading the slides and the documentation, adding `System.out.println` to debug, running the program many times, re-reading the README, testing after each small change, asking for help.

**Your Answer:** *(5-7 sentences)*

I went back to the Chapter 5 slides, especially the critical-section problem and the mutex lock part. Then I re-read the README, which says that the three variables are independent. I checked the code of `SharedStats` and saw that no method changes two counters at the same time. So if they share one lock, a thread adding service time waits for a thread counting a context switch for no reason, and with `RaceWindow.pause()` inside each update this waiting is even longer. Three locks keep each counter safe and let the threads work in parallel when they update different counters. About the deadlock worry, I understood it only happens if a thread holds two locks and waits for another, and my methods never take two locks at the same time.

## Question 4: Where can synchronization concepts be applied in real-world applications?

> 💡 **TIP:** Use real applications you know (banking and money transfers, ticket or seat booking, a shared counter on a website, a print queue, a database) and connect each one to what you built here (shared data, critical section, lock or semaphore).

**Your Answer:** *(5-7 sentences)*

A good example from my life is course registration at the university: when registration opens, many students try to take the last seat in the same section at the same moment. Without a critical section, two students could both see one seat free and both get registered, exactly like two CPUs picking `P1` in my starter. Booking an appointment, a seat or a ticket in an app is the same problem, so the check and the booking must be done together under a lock, like `poll()` in my `ReadyQueue`. In banking, two withdrawals on the same balance at the same time can lose an update, like `contextSwitchCount` lost increments in my run. In all these cases the shared data needs mutual exclusion. A counting semaphore can also be used when a system has a fixed number of resources, like a limited number of seats or service windows.

### Optional: What would you like to learn more about?

I would like to learn more about deadlocks (detection and prevention) and how real operating systems and databases handle many readers and writers at the same time.

### Optional: How confident do you feel about synchronization concepts now?

Intermediate. I understand race conditions, mutex locks with `try/finally` and the counting semaphore well. I need more practice with fairness, starvation and the classical problems like dining philosophers.

### Optional: Feedback on the assignment

The assignment was helpful because the verification block shows clearly if the synchronization is correct, and `RaceWindow` makes the bugs appear in every run instead of randomly.
---

# Part C: Technical Answers (0.5 mark)

> 🛑 **STOP:** You cannot answer these questions without understanding the code. Re-read `SchedulerSimulationSync.java` and **run it** first. Your answers must reference **your own code and your own output** (your student ID makes your output and your expected values unique).
>
> ⚠️ **WARNING:** Each answer must be **3 to 5 sentences**, with specific examples from your code or output. Use correct terms: race condition, critical section, mutual exclusion, mutex lock, semaphore, busy waiting, deadlock, producer, consumer.
>
> 💡 **TIP:** Keep the output of the **original starter** and the output of your **final version** in text files or screenshots, so you can copy real snippets for Question 1.

## Question 1: Race Condition in Your Own Output

**Question**: Run the **original starter** (before any fix) and paste the **verification block** of that run. Which value was wrong (expected vs observed)? Explain **step by step**, with two named threads/CPUs, how **one lost update** happens on one of the shared variables (read, `RaceWindow.pause()`, write). Why can the same bug happen on a real machine even without `RaceWindow`, and why is it hard to detect?

> ⚠️ **WARNING:** The snippet must come from **your own run** (with your student ID), not from a classmate or from this README.
>
> 💡 **TIP:** Use a small timeline: *CPU-1 reads `contextSwitchCount` = 12 → CPU-2 reads 12 → CPU-1 writes 13 → CPU-2 writes 13 → one increment is lost.* If your starter run crashed before printing numbers, run it several times (or paste the exception and the watchdog message and explain it).

**Your Answer:** *(3-5 sentences)*

In the run of the original starter with my ID (11 processes, quantum 4000 ms, 2 CPUs), all four lines were wrong: context switches 25 instead of 27 (-2), completed processes 10 instead of 11 (-1), total service time 77686 instead of 83639 (-5953 ms) and 1208 busy-waiting polls. The output shows why: `[CPU-2] picks P1` and `[CPU-1] picks P1` appear one after the other, because both CPUs read the same head during the `RaceWindow.pause()` of `poll()`, and each one then removed an element, so `P2` (burst 5953 ms = 2 quanta) was removed without ever being executed and CPU-1 crashed with `IllegalThreadStateException` when it started P1's thread a second time. After Feature 1 the counters still lost updates (context switches 23 instead of 27 and service time 75639 instead of 83639, exactly two quanta of 4000 ms lost), which is the lost update explained below. On a real machine the same thing can happen without `RaceWindow`, because the OS can preempt a thread (or two cores can run in parallel) between the read and the write of `count++`, which are separate instructions. It is hard to detect because this window is only a few nanoseconds wide, so the bug appears rarely, randomly, and may disappear when we add prints or use a debugger.

Verification block of the **original starter**:
```
  ┌─ [CPU-2] picks P1 │ Ready queue: [P2 → P3 → P4 → P5 → P6 → P7 → P8 → P9 → P10 → P11]
  ┌─ [CPU-1] picks P1 │ Ready queue: [P3 → P4 → P5 → P6 → P7 → P8 → P9 → P10 → P11]
Exception in thread "CPU-1" java.lang.IllegalThreadStateException
...
⛔ WATCHDOG: the simulation did not finish (40 s). A process was lost, or a CPU is blocked forever, or the 'completed' counter lost an update.

═══ VERIFICATION (expected values are computed from YOUR seed) ═══
  Context switches (quanta executed)     expected 27       observed 25       ✘ MISMATCH
  Completed processes                    expected 11       observed 10       ✘ MISMATCH
  Total service time (ms)                expected 83639    observed 77686    ✘ MISMATCH
  Busy-waiting polls (must be 0)         expected 0        observed 1208     ✘ MISMATCH
  ✘ At least one check failed (see the ✘ lines above): a race condition or busy waiting is still present.
```

Verification block of **my final version**:
```
═══ VERIFICATION (expected values are computed from YOUR seed) ═══
  Context switches (quanta executed)     expected 27       observed 27       ✔
  Completed processes                    expected 11       observed 11       ✔
  Total service time (ms)                expected 83639    observed 83639    ✔
  Busy-waiting polls (must be 0)         expected 0        observed 0        ✔
  ✔ All shared values are consistent.```

**Explanation of the timeline:**
Lost update on `contextSwitchCount` (version with Feature 1 only, where I observed 23 instead of 27). Suppose the counter is 12 and the processes running on CPU-1 and CPU-2 both start a quantum:
1. CPU-1 (its process thread) executes `int tmp = contextSwitchCount;` and reads **12**.
2. CPU-1 calls `RaceWindow.pause()` and is "preempted" for 1 ms.
3. CPU-2 executes `int tmp = contextSwitchCount;` and also reads **12** (CPU-1 has not written yet).
4. CPU-1 wakes up and writes `contextSwitchCount = 12 + 1` → **13**.
5. CPU-2 writes `contextSwitchCount = 12 + 1` → **13**.

Two quanta started but the counter only went from 12 to 13: the last write wins and one increment is lost. With `contextSwitchLock`, step 3 cannot happen: CPU-2 blocks on `lock()` until CPU-1 has written 13, then reads 13 and writes 14.

## Question 2: Critical Sections and Lock Granularity

**Question**: List the **critical sections** you protected (variables and methods) and the lock(s) you used. **Lock granularity:** did you use **one lock** for the three statistics or **one lock per variable**? Why, and what is the trade-off? Why is the **ready queue** protected by a **different** lock than the statistics? Explain how your solution provides **mutual exclusion**, and discuss **progress** and **bounded waiting** (a default `ReentrantLock` is not fair: what does that imply?).

> 💡 **TIP:** The three counters are independent: does updating `contextSwitchCount` need to block an update of `totalServiceTime`? Also think about what could go wrong (deadlock, or long waiting) if the queue lock and the statistics lock were the **same** lock and a thread held it while doing something slow.

**Your Answer:** *(3-5 sentences)*

I protected two groups of critical sections. The ready queue (`list` + `map`) is protected by one lock, `queueLock`, in the four methods `add()`, `poll()`, `processOf()` and `snapshot()`, because the list and the map always change together and form one shared object. For the statistics I chose **one lock per variable** (`contextSwitchLock`, `completedLock`, `serviceTimeLock`): the three counters are independent (no method updates two of them at the same time), so a thread that adds service time should not wait for a thread that counts a context switch. The trade-off is more lock objects to manage (and a possible deadlock if one day a method needed two of them in different orders), against less contention and more parallelism; one global lock would be simpler but would make all threads wait for each other, even with `RaceWindow.pause()` inside. The queue has a different lock than the statistics because they are unrelated data: if they shared one lock, a CPU doing `poll()` (with its 1 ms pause) would block every process thread that only wants to update a counter. Mutual exclusion is guaranteed because every read and write of a shared variable is between `lock()` and `unlock()` of the same lock, and `unlock()` is always in `finally`, so a lock is never kept forever (progress). A default `ReentrantLock` is **not fair**: a thread that just released the lock can take it again before a waiting thread, so bounded waiting is not strictly guaranteed in theory (possible starvation); in this program the critical sections are very short, so in practice every thread gets the lock quickly, and `new ReentrantLock(true)` would give FIFO fairness at a performance cost.

| Critical section (variable / method) | Lock used | Why it needs protection |
|---|---|---|
| `ReadyQueue.add()` (`list`, `map`) | `queueLock` | Two CPUs re-enqueueing at the same time modify the `LinkedList` and `HashMap`, which are not thread-safe |
| `ReadyQueue.poll()` (`list`) | `queueLock` | Read of the head + `removeFirst()` must be one step, otherwise two CPUs pick the same process and another one is lost (P1 / P2 in my starter run) |
| `ReadyQueue.processOf()` (`map`) | `queueLock` | Reading the map while another CPU puts a new entry is unsafe |
| `ReadyQueue.snapshot()` (`list`, `map`) | `queueLock` | Iterating while another CPU modifies the list throws `ConcurrentModificationException` (seen in one of my starter runs) |
| `incrementContextSwitch()` / `getContextSwitchCount()` | `contextSwitchLock` | Read-modify-write of `contextSwitchCount` loses increments (23 instead of 27 after Feature 1) |
| `incrementCompletedProcess()` / `getCompletedProcessCount()` | `completedLock` | A lost update would make the CPUs wait for a count that never reaches 11 (watchdog) |
| `addServiceTime()` / `getTotalServiceTime()` | `serviceTimeLock` | Lost additions (75639 instead of 83639 after Feature 1); a `long` read is not even guaranteed atomic |

## Question 3: Busy Waiting vs Semaphore

**Question**: Describe the **busy waiting** of the starter and its cost (give the `Busy-waiting polls` number from your **starter** run). What does the **value of your semaphore** represent? What is its **initial value** and why? What is its value right after the `numProcesses` initial `add()` calls? Why does the last CPU call `release(totalCPUs)` at the end, and what would happen if it did not?

> 💡 **TIP:** Think about what a CPU does when the queue is empty in the starter, and what a CPU does in your final version (is it running, ready or blocked?). Also check what happens to a CPU blocked in `acquire()` when no process will ever be added again.

**Your Answer:** *(3-5 sentences)*

In the starter, a CPU that finds the queue empty increments `busyWaitPolls`, sleeps 20 ms and checks the queue again, in a loop that only stops when `completedProcessCount == totalProcesses`. This is busy waiting: the CPU thread stays in the running/ready state and keeps checking a condition instead of doing useful work; in my starter run it polled the empty queue **1208** times (CPU-2 kept polling because the lost process P2 never completed), and even after Features 1 and 2 it still polled 1 to 3 times at the end. My semaphore `readyCount` represents **the number of processes currently waiting in the ready queue**: `add()` calls `release()` (signal) after inserting a process, and a CPU calls `acquire()` (wait) before `poll()`, so it is **blocked** (sleeping, no CPU used) when the value is 0. Its initial value is **0** because the queue is empty when the `ReadyQueue` is created; with a wrong value like 1 a CPU could pass `acquire()` and `poll()` an empty queue. Right after the 11 initial `add()` calls of `main` its value is **11** (one permit per process of my run). At the end no process will ever be added again, so the CPUs blocked in `acquire()` would sleep forever (a deadlock-like situation stopped by the watchdog); that is why the CPU that observes `completed == totalProcesses` calls `release(totalCPUs)` (here 2 permits): each CPU wakes up, sees that everything is completed, and terminates, so my program ends by itself in about 9 seconds.

## Question 4: Classical Problems and Deadlock

**Question**: The CPUs and the ready queue look like a classical synchronization problem of Chapter 5. **Name it**, and say who plays the **producer** and the **consumer** roles (careful: here the CPUs also re-enqueue processes). If the ready queue were **bounded** (capacity `K`), name the **three semaphores** you would need and their **initial values**. Describe a **deadlock scenario** that appears if a thread acquired the **mutex before** waiting on the semaphore (or if two locks were acquired in different orders), and say **which of the four necessary conditions** you would break to prevent it.

> 💡 **TIP:** Recall the bounded-buffer solution of the slides (`empty`, `full`, `mutex`) and the order of `wait()` calls in the producer and the consumer. For the deadlock, think about a producer that holds the mutex while waiting for a free slot that only a consumer (who needs the mutex) can create.

**Your Answer:** *(3-5 sentences)*

**Classical problem and roles**:
It is the **producer-consumer (bounded-buffer) problem**, with an unbounded buffer: the ready queue is the shared buffer and `readyCount` plays the role of the `full` semaphore of the slides. The `main` thread is a producer (it adds the 11 initial processes), and the CPUs (`CpuWorker`) are consumers because they take processes with `acquire()` + `poll()`; but the CPUs are **also producers**, because a process that is not finished after its quantum is put back with `add()`, which calls `release()`.

**Semaphores for a bounded queue (name and initial value)**:
- `mutex` = **1** (binary semaphore, mutual exclusion on the queue; it would replace `queueLock`)
- `full` = **0** (number of processes in the queue; this is my `readyCount`)
- `empty` = **K** (number of free slots; `add()` would call `wait(empty)` before inserting and `poll()` would call `signal(empty)` after removing)

**Deadlock scenario and prevention**:
Suppose the queue is full (`empty` = 0) and a CPU wants to re-enqueue its process: if it calls `wait(mutex)` first and **then** `wait(empty)`, it blocks on `empty` while **holding** the mutex. Another CPU that wants to `poll()` (the only action that could free a slot and `signal(empty)`) blocks on `wait(mutex)`, so each one waits for the other forever: deadlock (in my unbounded version, the same would happen if a CPU called `readyCount.acquire()` while holding `queueLock`). The four necessary conditions are mutual exclusion, hold and wait, no preemption and circular wait; I would break **hold and wait** by always waiting on the counting semaphore **before** taking the mutex (`wait(empty)` then `wait(mutex)`, like the slides), and never holding a lock while blocking. That is exactly what my code does: `acquire()` in `CpuWorker` is called without `queueLock`, and `release()` in `add()` is called after `unlock()`. For two locks taken in different orders, I would break **circular wait** by imposing one global order (always the same lock first), like the resource-hierarchy solution of the dining philosophers.

## Summary

**Key concepts I understood through these questions:**
1. A race condition is a read-modify-write that is interrupted: the last write wins and an update is lost
2. A mutex lock (`ReentrantLock` with `try/finally`) gives mutual exclusion on a critical section, readers included
3. A counting semaphore initialized to 0 lets consumers block instead of busy waiting, and needs a shutdown signal at the end

**Concepts I need to study more:**
1. Fairness and starvation with non-fair locks (bounded waiting)
2. Deadlock prevention and the four necessary conditions in more detail

---

# ✅ Final Checklist (complete before submitting)

> ⚠️ **WARNING:** Go through every line. Blackboard does not accept submissions after the deadline, which is **November 14, 2026**.

**Repository**
- [ ] Repository is **PUBLIC** (Settings → Danger Zone → Visibility)
- [ ] Repository is renamed to `OS-Assignment3-YourFirstName-YourLastName`
- [ ] GitHub account uses the university email (`@std.psau.edu.sa`)

**Code**
- [ ] Student ID is set in `SchedulerSimulationSync.java` (line 304)
- [ ] My code is based **only** on the starter of this repository (nothing copied from previous assignments)
- [ ] Code compiles and runs with no errors, and terminates by itself (no `⛔ WATCHDOG`)
- [ ] Feature 1 (ready queue lock), Feature 2 (statistics locks) and Feature 3 (semaphore, no busy waiting) all work
- [ ] **The four verification lines are ✔ in 5 consecutive runs**
- [ ] Every lock is released in a `finally` block
- [ ] `RaceWindow`, `Config`, the verification block and the watchdog are **unchanged**
- [ ] Each feature has clear comments

**Commits**
- [ ] **At least 4 meaningful commits, ideally 7 or more**
- [ ] **One commit per feature**
- [ ] Commits are spread over **different dates** (not all in the last hour)
- [ ] Everything is **pushed** to GitHub

**This file (`MY_WORK.md`)**
- [ ] Full name and student ID filled in at the top
- [ ] Development log has **5+ entries** on different dates
- [ ] Reflection: 4 questions, 5-7 sentences each
- [ ] Technical answers: 4 questions, 3-5 sentences each, with examples from **your** output (starter output **and** final output pasted in Question 1)
- [ ] No `[...]` placeholders left
- [ ] No section headers deleted

**Video**
- [ ] 2-3 minutes long, named `StudentID_Assignment3_Demo.mp4`
- [ ] Shows your name, ID, repository, 3 features (and your lock granularity choice), IDE execution with the verification block, one synchronization concept, and commit history
- [ ] Link is **public** (tested in an incognito window) and pasted in the **Video Link** section above

**Blackboard**
- [ ] Submit **only** the link to your public GitHub repository

> 🎯 **Good luck!** Start early, commit regularly, and make sure you can explain every line you submit.
