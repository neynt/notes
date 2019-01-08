## How to: prepare for a Google engineering interview

[Link](https://www.youtube.com/watch?v=ko-KkSmp-Lk)

- Data structures and algorithms: Hash tables, stacks, arrays, space and time
  complexity
- Whiteboard coding
- System design
- Object oriented programming
- Language: Typically C++ or Java, Python and C also used.
- Know Dijkstra's and A star -- may help
- Unit testing, coming up with test cases, integration, security tests
- Know NP complete problems, recognize them
- Tree construction, manipulation
- Discrete math: Counting, probability
- Recursion
- Operating systems: OSes, threads, concurrency, semaphores, mutexes, locks,
  resources, context switching, scheduling
- System design: Feature sets, interfaces, class hierarchies, distributed
  systems, design under constraints
- Internet: Routers, DNS, load balancers, firewalls, search

- Keep talking during the interview.
- Ask clarifying questions. Time or space complexity requirements?
- Keep thinking.

- Practice writing code physically.

## Example coding/engineering interview

[Link](https://www.youtube.com/watch?v=XKu_SEDAykw)

- Set of numbers; Find pair of numbers with a desired sum.
- Ask for clarification. How are the numbers stored? Are they integers?
- Constantly think out loud.
- Think through before writing code.
- Simplest solution: Nested loop. O(n²).
- Better solution: Binary search. O(n log n).
- Best solution: Two-ended scan. O(n).
- Note solution of degenerate cases
- Test your code in real time. Think about edge cases.

## Google University Tech Coaching meeting

- Any talk about previous projects, resume etc. is just an informal chat.
- The important part of the interview is the technical bit.
- Of 45 minute interview, 35 minutes should be about the technical question.
- Don't worry about number of questions.
- Write actual code. Not pseudocode. Use your strongest language.

- Assessment axes are:
  - Algo and data structures
  - Analytical skills
  - Sound design (make things testable)
  - Communication (explain yourself)
    - State your assumptions

- The right answer is nice but not necessary
  - (Actually: The right answer is necessary but not enough)

- Interview flow:
  - 1. Question is asked.
  - 2. Clarify question, state assumptions, collect additional constraints.
  - 3. Outline plan of attack.
  - 4. Implement. While implementing, propose alternative solutions.
  - +: Test everything so that you catch your own bugs.

- Sample interview question: "Determine whether a circular array of relative
  indicies is composed of a single, complete cycle."
  - Clarifying the problem: Define "relative index", "circular".
  - Relative indices can be negative.
  - They had a kickass solution with no constant additional space, no input
    modification, and linear time.

- With solution in mind, verify it on some cases BEFORE coding.
- Use short variable names because whiteboard.
- Clean up the code after the first pass.
  - (double space code the first time around)
  - Ask if interviewer has questions before refining.

- Sample interview question 2: "Imagine that there is a large bucket of marbles
  of various colors. Describe an algorithm for drawing a marble from a bucket
  at random."
  - Clarify representation of marbles / marble frequency.
  - Clarify with/without replacement (!!!)
  - All of these affect the solution.

- SEA/KIRK are mostly Google Cloud. Also Hangouts, Chrome, Android.

- System design questions don't typically show up for new grads. Recruiter will
  know. 3+ years experience: System design is a thing.
