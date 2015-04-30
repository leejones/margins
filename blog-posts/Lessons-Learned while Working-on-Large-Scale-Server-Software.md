# Reading notes from "Lessons Learned while Working on Large-Scale Server Software"

* source: http://ferd.ca/lessons-learned-while-working-on-large-scale-server-software.html?utm_medium=email&utm_source=webopsweekly
* author: Fred Hebert
* tags: distributed systems

## Lessons

### Plan for the worst

> Handle this worst case scenario and you've just figured out how to handle pretty much all errors in your system.

### The CAP Theorem is Real

### The Fallacies of Distributed Computing are real

> If you can avoid making parts of your system distributed, avoid it. It's leaving the comfort of your home to step into a rain of fire.

### Back-Pressure or Load-shedding: pick one.

> Sooner or later, your system will be overloaded. You have two options: do you stop people from inputting stuff in the system, or do you shed load.

### Debugging is a Science

### Postel's Law is Hard.

> Be conservative in what you send, be liberal in what you accept

### Don't trust the network.

### Et tu, System?

> A huge part of a system's success is tied to its operators. Without enough practice, they might just become the riskiest part of the system.

### Crash Early, Crash Often

> When you're not sure about how to handle an error, let it crash.

### Deploys Fix Bugs, Cause Failures

> The bigger the deploy, the scarier.

### Long Running Systems Have Their Own Bugs

### Be Ready for a Total Restart

> Be ready to restart the entire system from a blank slate, under load.

### There's more Global stuff than variables

> Refactoring of large systems, particularly legacy systems, is fraught with peril because there have been many such decisions, made by both smart and distracted people, that end up acting as invisible glue to large parts of everything you stand on. Refactoring can only truly begin once you've actually learned what a piece of code or some data structure did, the unique properties for which they were written or chosen. Anything else is setting yourself up for failure.

### It's all about people

> It also means that when building systems, you should not assume that operators will do things correctly. Expect failure from people. Try to think about tools you can give them to undo their mistakes, because they will happen sooner or later. Have some dread. Be understanding. Know things won't be perfect.
