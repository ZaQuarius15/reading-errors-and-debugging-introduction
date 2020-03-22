![Debugging Icon](https://curriculum-content.s3.amazonaws.com/module-1/practice-debugging/Image_113_Code%20Debugging.png)

# Debugging

> The terms "bug" and "debugging" are popularly
> attributed to Admiral Grace Hopper in the 1940s.
> While she was working on a Mark II computer at
> Harvard University, her associates discovered a
> moth stuck in a relay and thereby impeding operation,
> whereupon she remarked that they were "debugging"
> the system. - Wikipedia

Debugging is the process of finding and fixing problems
in our code. The keyword being _process_ - part of the journey
of learning how to program is learning how to deal with
obstacles like errors in your code.

"Debugging" is the process a mechanic does when you bring your
car in. "When I start it, it sounds fine. But when I hit the
brakes I hear squee-squee-squee." "Debugging" is the process
a repair person does when your washing machine does something
"strange."

Both cars and washing machines are complex machines with many interacting parts.
But if your car won't start you might "isolate" the battery and hook it up to a
battery tester. If the battery tester shows the battery is good, then you know
that the problem is somewhere else; if the battery is dead, then you have
_verified_ that the battery is the problem with your car.

That process is known as _debugging_ when applied to computers or
_troubleshooting_ when applied to pretty much everything else. At the risk of
sounding mystical, debugging is a skill shared by all makers: guitarists to
brewers, to chefs, to programmers. From Neal Stephenson's _Cryptonomicon_:

> Randy counts four men in addition to Amy and the pilot...  All of them are
> fiddling around with engines or diving gear in a way Randy recognizes,
> through many cultural and technological barriers, as debugging.

In this section, we're going to take a look at some common debugging strategies
to help you as you advance through this course. As you progress, you will need
to develop and rely on debugging techniques to help you through some of the
toughest concepts and labs. In this lesson, we will briefly introduce some of
the concepts we'll cover in this section.

## Debugging and Programming

To quote Brian Kernighan (who invented the C programming language and the
Unix operating system; so, someone who made a bug or two):

> The most effective debugging tool is still careful thought, coupled with
> judiciously placed print statements.

We might not have battery testers, but we _can_ put `puts` and `print`s and `p`
throughout our code. This gives us some insight into the flow of the code. At this
point, we can print out the contents of variables or leave a message to
ourselves in the console output like:

```ruby
puts "please, i want to go home, please print this out!"
```

Place in a method, a statement like this will give us a signal whenever that
method is called.

```rb
def multiply(num1, num2)
  puts "multiply got called with #{num1} and #{num2}"
  num1 * num2
end
```

If we loaded this into IRB and called it, we will see the output printed before
the return value from the method:

```sh
2.6.1 :006 > multiply(2, 4)
multiply got called with 2 and 4
 => 8
```

Now, not only can we confirm the method was called, we are getting some info
about the arguments.

In complex applications, this can be very handy - a method might only be called
as part of a larger process. Using print statements like `puts`, we can confirm
code runs in the way we expect and that variables are assigned the values we
think they are.

## "Stop the World" Debuggers

One disadvantage of using print statements is that they aren't interactive. We
only see the output of our code as it runs.

Sometimes, it is helpful to use a tool referred to as a "stop the world"
debugger. These debugger tools will stop the execution of code in a program and
let us step into it and interact. Very similar to IRB, while the program is
stopeed, we get access to variables and methods and can use them. After we quit
the debugger, the program will continue execution.

Ruby's main "stop the world" debuggers are called Pry and Byebug. We'll be
exploring Pry a few lessons.

## Reading Errors

There is no way around it - a critical part of debugging is reading output when
something goes wrong. Ruby is wonderful for this - errors in Ruby often tell you
exactly where something went wrong and will do their best to tell you what
happened. This information can be used to rapidly _isolate_ a problem. If Ruby
is saying, something went wrong on line 9, we might start debugging by placing a
`puts` on line 8 and confirming that everything is working the way we _think it
is_.

Errors can be tricky. Sometimes they produce so much output, it is easy to glaze
over them and feel overwhelmed. Actively taking some time to become comfortable
reading errors will have an exceptional return on investment while you're
learning the basics of programming - you're going to see _a lot_ of them, so the
more you know about them, the faster you can interpret them and fix your bugs.

We will take a look at how to read errors and learn about a few of the most
common ones.

## Reading Tests

We use tests in our course to confirm you are able to apply the concepts you are
learning, but tests are often used in professional applications to ensure
features work as intended, even if the application gets updated.

We've briefly talked about tests and how they are structured in a previous lab.
Tests provide an additional layer of feedback. Maybe your code is _error_ free,
but still doesn't do exactly what it is supposed to do. Similar to errors, tests
will provide information about what was expected in code and what actually
happened.

Also like errors, tests can produce a lot of output and be difficult to read at
times. Sometimes a test will just reflect an error that occurred. We will take
a more in-depth look at reading tests and some strategies for solving them.

## Conclusion

Ultimately, each engineer finds a pattern of debugging they prefer. Many
students find Pry to be very helpful while they're first learning, which is why
we want to teach this to you early.

We hope, though, that you will try to develop a broad approach to debugging
during this course and not just rely on a single tool. Programmers are usually
hired during a "whiteboard" interview where they have to handle complexity,
correct code, and achieving a goal by writing with a pen on a whiteboard. If you
can't structure code in digestible chunks, or to debug it by reading code, you
will not pass the interview. We speak from bitter experience here.

Reading errors and tests and verifying assumptions with print statements are
fantastic ways to develop a better sense of how code works. When these don't
work, we have tools like Pry to dig in further.