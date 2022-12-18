# Code review process

> A code review (also referred to as peer code review) is a process where one or two developers analyze a teammate’s code, identifying bugs, logic errors, and overlooked edge cases.

## Main improvement goals

- **Readability** - Are there any redudant comments/LOCs? Does it need some comments? Are variables/function names descriptive enough?
- **Security** - Does the code expose system to a cyber attack? Does the code contains relevant/secure/up-to-date libraries?
- **Test coverage** - Is there a need to test the code / test more cases?
- **Architecture** - Does the code follow the best practices (encapsulation/modularization)? Does the code follow our guidelines?
- **Reusability** - Does the code use reusable components, functions and services?

## Specific steps to follow

- Every Pull Request should be reviewed by at least two people.

  - It is highly recommended to get at least one review from a more senior member of the team.

- Every Pull Request should be reviewed in 1 working day from when it was opened.

  - PR opened in the morning: reviewed by the end of the working day.
  - PR opened in the afternoon: reviewed by lunch of the next working day.
  - Author is responsible for this - you should ask a team member if you see your PR has no reviews in a reasonable time (see above).

- Don't review more than 200-400 lines of code (LOC) at a time.

  - Most bugs are found in the first 200 lines.
  - See [study done by CISCO](https://static1.smartbear.co/support/media/resources/cc/book/code-review-cisco-case-study.pdf).

- Don't review for more than 60 minutes at a time.

  - ![](https://i.imgur.com/eyhMRYo.png)

- Do explain the changes you made.

  - Each PR should contain description telling which files to look at first and defending the reason behind each modification.

- Focus on coding standards, not personal preference.

  - More often than not, **perfectionism is the enemy** of good code - refrain from being too nitpicky about trivial concerns (such as declaring variables in a certain order).

- Ask open ended questions.
  - This can set the stage for **discussion, knowledge sharing, and mentorship**.
  - **Even the most seasoned developers** can learn from a beginner in the field.
