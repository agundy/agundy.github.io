---
layout: post
title: Livable Code
tags:
  - Learning
  - Conferences
  - Programming
---

This was originally an entry in my Rails Conf note series but this talk
deserved it's own post. Sarah Mei give a really insightful talk with a unique
way to view software. I will attempt to summarize it here but I would recommend
listening to the talk when it comes out.

### Summary

Think of software as a creative and iterative process over a purely technical
endeavour. The talk began talking about 
[Conway's Law](http://melconway.com/Home/Conways_Law.html): _The structure of
the system a team or organization builds will match their communication
structure._ This means messiness in communication will translate into messiness
in the code base. Often software teams work as independent technical teams when they
creative teams. Programming can be creative and the systems we build rely on
communicating and novel solutions.

Software is regularly compared to architecture, but Sarah argues that this is
wrong. Architecture has three well defined stages:
1. Design
2. Construction
3. Maintenance

These three stages are handled by separate teams and require separate skills.
Software used to be built like that, but not any more. Now we have libraries and
frameworks that provide the structure. Instead we are living inside of these
buildings that are the technologies we choose. These technologies give us the
outline and walls with limitations and design choices we must live with or work
around. We now focus on making our code livable.

Inside our "home" of code we need to create value and solve problems.
Also the happiness that we feel depends on who we live in the code with.
Everyone has their own quirks and habits, but together you work and live
together. This living together in a house analogy was extended to hoarding and
messiness. When you let laziness seep in, little decisions and messes compound
until it's an episode of Hoarders. 

The answer to this isn't to through out the house and start again, the same
habits and behavior that made the mess will slowly creep in to the new system.
To prevent this mess approach coding with the livable code mindset rules:

1. **Don't make it worse.**
2. **Improvement over consistency:** but be sure to communicate the direction and
   goal.
3. **Inline everything:** do the easy things instead of saying you'll come back to
   it.
4. **Talk more about the code.**
  - Don't always ask for permission, but be upfront with what you are doing
  - Don't ask for forgiveness
  - Be open to feedback but don't always listen

Code gets messy if care is not regulary cleaned and organized. Blog post and
book sample code is comparable to staged homes. Those aren't livable, just like
the showrooms and photos of houses for sale hide the clutter and the things you
actually need in a home. This analogy really resonated when she pulled up a
photo of a bedroom on a house listing and picked apart how it wasn't livable.
No chargers on the end tables, no dresser, bed was on the floor to make the
room feel spacious, etc. This is staged, just like overly abstracted code.

Modern software development is building and using generic components that
together build a home, and we live there so keep it livable.

### Takeaways

- Think of code as a home, it needs to be livable, you should organize and
  clean but a little mess is okay.
- Value continous improvement over consistency and correctness.
- Rewriting code will not prevent the next codebase from getting messy, instead
  fix the process.

### Sources

- [Rails Conf Talk - PENDING](#)
- [Livable Code Twitter Moment](https://twitter.com/i/moments/843392359903649792)
