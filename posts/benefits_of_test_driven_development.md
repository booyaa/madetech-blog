# Benefits of Test Driven Development

Test Driven Development is the practice of writing a test for a piece of functionality that is required before writing any implementation code. This test should fail when first run. Then, you write the code to get it to pass. It doesn't have to be the most perfect code. Just so long as the test passes. Once it does, you can then safely refactor your code.

TDD is a discipline. You must try your best to not be tempted to write tests after you've written code. Pressure can come from clients or employers to delay or not bother with the writing the tests at all. Firstly they need to understand the benefits of tests, and then the additional benefits of TDD on top so you can secure that time to practice TDD correctly.

If your application has tests that weren't written before the code that implements them, then that means TDD wasn't followed. It does mean however that your project has test coverage, which is a good thing that has many benefits—definitely better than not having any tests—but practising TDD brings additional benefits on top of those. Often some articles on the internet claim to write about those additional benefits but instead seem to end up focusing on the benefits of tests in general. This post will try and focus strictly on the benefits of TDD.

You shouldn't assume either that TDD doesn't mix with BDD. The key is writing the tests before the code. When writing feature specs that define the behaviour of something, if you're writing those specifications before implementing them, you're TDD'ing too.

At Made, we use TDD when writing our feature specs. We use tools most commonly used for unit tests for our feature tests too, rather than things like Cucumber, which are often associated with BDD. Namely [RSpec](http://rspec.info/) with [Capybara helpers](https://github.com/jnicklas/capybara#using-capybara-with-rspec). You can still use [Cucumber](https://cucumber.io/) for example for feature specs, and TDD.

## Benefits

 * **Acceptance criteria:** When writing some new code, you usually have a list of features that are required, or acceptance criteria that needs to be met. You can use either of these as a means to know what you need to test and then you can rest assured once you've got that list in the form of test code, that you won't have missed any work.
 * **Focus:** You'll be more productive while coding. You're thinking about smaller chunks of functionality at a time. You write one failing test, and focus on that solely, to get it passing. You can then slowly build on a passing test incrementally rather than trying to tackle the bigger picture from the get-go, which will probably result in more bugs, and therefore a longer development time.
 * **Interfaces:** Because you're writing a test for a single piece of functionality, writing a test first means you think of the public interface that other code in your application has to integrate with. You don't think about the private methods or inner workings of what you're about to work on. From the tests perspective, you're only writing method calls to test the public methods. This means that code will read well and make more sense.
 * **Tidier code:** Continuing on from the point above, your tests are only interfacing with public methods, so you have a much better idea of what can be made private, meaning you don't accidentally expose methods that don't need to be. If you weren't TDD'ing, and you made a method as public, you'd then possibly have to support that in the future, meaning more work for you for a method that was only intended to be used internally in a class.
 * **Dependencies:** Will your new code have any dependencies? When writing your tests, you'll be able to mock these out without really worrying about what they are doing behind the scenes, which lets you focus on the logic within the class you're writing. Additional benefit is that the dependencies you mock would potentially be faster when running the tests, and not bring additonal dependencies to your test suite, in the form of filesystems, networks, databases etc.
 * **Safer refactoring:** Once you've got a test passing, it's then safe to refactor it, knowing that the test cases will have your back. If you're having to work with legacy code, or code that someone else has written, if no tests have been written, you can still practice TDD. You haven't got to have authored the original code in order for you to TDD. Rather than thinking you can only TDD code that you have written, think of it more as you can only TDD any code you are _about_ to write. So if you inherit someone elses untested code, before you start work, write a test that covers as much as you can. Then you can be in a better position to refactor, or add new functionality to that code feeling safer that you won't break anything.
 * **Pairing:** When teaming up with another developer, TDD can help ensure that both are on the same page when it comes to figuring out what they're working on. You both write tests that make it clear what the expectations of the code are. It also helps onboard people quicker who might be pairing with you, that aren't familiar with the code base, as expectations and assertions are clear. A variation on standard pairing practice—whereby you each take it in turns for a fixed amount of time before swapping around—is that one person can write the test and the other implements, and vice-versa.
 * **Fewer bugs:** TDD results in more tests, which can often result in longer test run times, however, with better code coverage, you save time down the line with bugs popping up that need time to figure out what's wrong and fix. Not to say that you might be able to think of all the things to test, but if a bug does come up, you can still write a test first before attempting to fix the problem, to be sure that the bug won't come up again. This also helps to work out what a bug actually is, as you always need reproducible steps.
 * **Increasing returns:** The cost to TDD is higher at first, when compared to not writing any tests. Though projects that don't have tests written first usually end up costing more as they don't have decent test code coverage, or any at all, so therefore are more susceptible to bugs and issues, which means more time is spent in the long run fixing those. More time equals more money, which makes the project more expensive overall. Not only does TDD save time on fixing bugs, but it also means that the cost to change functionallity is less too as you have tests as a safety net to ensure change doesn't break existing functionallity. 
 * **Living Documentation:** Tests can serve as documentation to a developer. If you're unsure of how a class or library works, go and have a read through the tests. With TDD, tests usually get written for different scenarios, one of which is probably how you want to use the class. So you can see the expected inputs a method requires and what you can expect as outcome, all based on the assertions made in the test.