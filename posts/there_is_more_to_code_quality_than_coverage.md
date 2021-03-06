#There is more to code quality than coverage

As developers we always strive to write the best code possible. And while we test for it, coverage doesn’t always tell the full story of the quality of your code output.

Firstly, what is coverage? Within a coding context coverage refers to the number of lines of code covered by tests. Once calculated code coverage is a way of seeing how much of your source code is covered by tests. So the higher your code coverage the better tested your source code is, and less likely to suffer from any bugs or regressions during its life time.

Previously we’ve shown you our [complete deployment pipeline](https://www.madetech.com/news/continuous-delivery-with-jenkins). In this article I am going to talk about the tooling we currently use during the first step of our deployment pipeline - the build step - to keep our code at a consistently high standard.

The majority of our code quality testing happens before any unit, or feature tests are run. The exception being to this being security testing. The reason being that this static code analysis takes a lot less time to run than an entire test suite does, so you don’t want to waste a build slave running "bad code”.

The areas we focus in on can be broadly separated into three areas; Complexity, Style, and Security.

###Complexity?
More specifically the complexity of Assignments, Branches and Conditionals (ABC) within a method. This metric can quickly identify potential “code smell” and overly complex methods. ABC metrics are not language specific, but the way you calculate them does vary between each language to allow for syntax differences. Broadly speaking though the ABC metric is calculated in a similar fashion.

The ABC metric of method (or function) is calculated by evaluating the number of variable assignments, calls to other methods or classes, and number of conditionals within said method. Our build will fail if any method exceeds the industry standard score of 15. More in-depth explanation of the ABC metric can be found in this [article](http://www.softwarerenovation.com/ABCMetric.pdf)

###Style
Language style guides aren’t anything new, but the enforcement of a consistent code style within the team aids readability, and understanding. We run style analysis on both our Ruby and SCSS files, and fail the build for anything deemed a serious violation. For example, missing spaces around a brace will fail the build, while an unnecessary double quote will just get you a warning.

###Security
Writing secure code has to be a top priority, so identifying any potential vulnerabilities in your codebase as early as possible is a must. Some of the common vulnerabilities you should be looking for are:
- Remote code execution
- Cross site scripting
- SQL injection
- String formating

We run our security analysis after feature and unit testing to guard against these common pitfalls, the thinking being that this [build] could reach production. In addition to this security analysis, you could run any number of security scans on your application once it is deployed out.

###Self-Discipline
All the previous areas I have discussed are easily automated, but there is an important human aspect to writing good code. Without self-disipline everything else could be in vein. It is down to the individual to write clean, and readable code. But this responsibility to be disciplined also rests on the team too.

As a team you should be spending time looking at each others commits, to keep yourselves honest. When you find an area of code that could be tidier, consider pair-programming with the author of the code.

##Testing

To test for complexity, style, and security we use [at time of writing] the following gems:

- **Tailor** - Style analysis tool for Ruby, that like its peers is configurable based on the [Ruby community style guide](https://github.com/bbatsov/ruby-style-guide).
- **Cane** - Code analysis tool for Ruby that enforces the ABC metric, and some basic styles like line length, trailing whitespace, and new line at the end of a file.
- **SCSS-Lint** - Style analysis for SCSS, which like Tailor can be configured to your SCSS
- **Brakeman** - A vulnerability scanner for Ruby on Rails that will find security issues. The vulnerabilities it identifies are shown [here](http://brakemanscanner.org/docs/warning_types/) which is quite comprehensive.

Because all of these gems come bundled with Rake tasks, we can easily switch them out if we find a better gem for the job. This enables our code analysis to evolve from project to project.

###Looking forward

A code analysis tool that I’d like to implement is Rubocop. Rubocop would effectively replace Tailor and Cane in our current set up as it provides an ABC metric, and style analysis. It can even rectify some issues automatically for you, which would be great, because there is nothing more annoying than a failed build because of a missing new line!

####Links
- Tailor - https://github.com/turboladen/tailor
- Cane - https://github.com/square/cane
- SCSS-Lint - https://github.com/brigade/scss-lint
- Brakeman - http://brakemanscanner.org/
- Rubocop - https://github.com/bbatsov/rubocop
