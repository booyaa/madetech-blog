# Remote Pairing

## Outline

- The problem
  - How we do pairing on-site
- The current solution
  - Screen sharing
    - Gui - Slack or Google Meets)
      - Pros: Can see what the driver is doing.
      - Cons: Having to swap screens or use the other person's editor if you're swapping pairs.
    - Terminal - tmux
      - Pros: Highly responsive
      - Cons: Not friendly to non-Vim or emacs users
- The new alternatives:
  - Floobits
    - Pros: 
      - supports a lot of editors (atom, sublime text, intellj, vim and emacs)
      - terminal support
    - Cons: requires storing of "shared" workspaces
    - Trivia: code roulette
  - Teletype
    - Pros: 
    - Cons: atom only
  - Visual Studio's Live Share
    - Pros: debugging
    - Cons: 
      - Visual Studio Code and Pro only.
      - Reliant on language support extension to implement features i.e. RLS extension doesn't work. Where as typescript does (demo video implies this, but should also test).
  - Summary
    - There's no clear winner, but floobit has the advantage of supporting so many editors and terminal support. Ideally we should adopt something similar to Language Support Protocol, a common protocol that allows us to share editor changes and allow the editor to implement.

### The problem

 at Madetech we try to spend at least 50% pairing with colleagues. We have dedicated pairing workstations. Where there are two screens one for the driver and one for the navigator.


## Further Reading

- Read Richard's excellent https://www.madetech.com/blog/the-best-and-worst-times-to-pair-program
- Read the book: https://www.madetech.com/resources/ebook/building_high_performance_agile_teams
- https://teletype.atom.io/
- https://floobits.com/