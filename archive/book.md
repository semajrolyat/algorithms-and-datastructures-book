 # Algorithms and Data Structures

George Washington University

James Taylor

Fall 2025

# Notes

- Amortized time complexity - figure out the correct time to introduce amortized time complexity with respect to the doubling space algorithm for arrays.
-  Detail the quicksort naive partition algorithm
-  

# Introduction

Data structures is traditionally the second required course in any computer science curriculum and it has been taught in a variety of languages over the years, but what is this class about?

Programming is a skill that may be one of the most accessible skills in modern society. The Internet after all was invented by programmers who have been using it since its inception to publish, promote, share, market and sell their skills and products. Good programmers do not necessarily need modeling, communication, or analytical skills to successfully program; however, in the modern programming labor market, it can be difficult to compete for jobs without these skills. In the field, there is a common core of terminology, well researched algorithms, and standard approaches, knowledge of which are mandatory for even entry-level developers. A majority of the class will focus on developing analytical, communication, and design skills based on established industry standards. On top of this, we will also come to understand how to apply science to the development process which will grant the trained computer scientist significant advantages over the feral, self-trained programmer.

 Beyond the technobabble, communication skills, and standard models, computer science is primarily about applying scientific principles to software programming and development. This means that we need to learn the scientific method and how to apply it to software development. The scientific method is a simple set of steps that give post-enlightenment society a means to conduct research and analysis of phenomena including phenomena entirely derived from reasoning.  The scientific method may require some small adaptation for a specific problem, but in general it follows the prescription: 

1. Observe phenomena and ask questions about observations
2. Formulate hypotheses and models to explain phenomena and questions
3. Predict using formulated models and experiment to test if hypotheses/models hold 
4. Analyze results. Reflect on and critique any and all hypotheses, models, and outcomes in the face of the evidence presented by the results.
5. Revise hypotheses and models if analysis contradicts predictions and repeat the process

The skills necessary to be an effective scientist are imagination and creativity, reasoning and analysis, communication, and practical understanding and skillful use of our instruments. We will use a variety of techniques to develop student capabilities in each of these skill-sets in the context of computer software.

For computer science, we also need to learn the common knowledge of the discipline. This includes learning how to measure a program's efficiency, how to structure data for optimal efficiency, what affects efficiency, and how to design and structure data so that programs operate according to design expectations and application requirements.

We have Java and other sophisticated languages, so why would it be necessary for a computer scientist to learn how to build fundamental data structures? A specialist can become quite successful by refining their skillset, but a specialist typically begins with a broad general understanding and then apprentices in a field to learn a specialty.  A programmer that can only write one language and relies on the existence of provided libraries does not develop a broad general understanding and has limited ability to adapt to changing technology. Considering that the story of software is constantly evolving technology and the introduction of new languages at least every five years, it is not a viable professional plan to expect to focus on one language for the next 40 years.  Additionally, a programmer with any ambition will want to make contributions to the state of the art, *i.e.* working at the edge of technology, so there will not necessarily be existing technology for a given project and the programmer may be responsible for implementing even the most fundamental structures to make the project feasible and successful.  Sometimes, a project’s success is entirely dependent on the need to choose the right data structure early in development, so a programmer needs to understand data structures intimately and to reason out which structure is the best choice in order to be a successful developer. 

Consider the role of draftsman. 

![Image of a draftsman at a drafting table drawing engineering diagrams](assets/draftsman)

Drafting required extensive training and skills; however, it is a narrow skill set that was completely displaced by image design tools like Photoshop, and CAD systems like AutoCAD and Solidworks becoming widely available. During WW2, tens of thousands of draftsmen supported the war effort designing all the components necessary to produce war materials, and the draftsman role was a prized and respected engineering job and drafting was considered a necessary engineering skill through the 1980’s.[^1]

[^1]: Somewhat ironically drafting classes were steadily replaced with typing classes throughout the 1980's and these typing classes were later replaced with computer classes as academics adapted to the evolving demands of the labor market.  Some students may be in this class today as a direct result of the rise and fall of the drafting skill which may seem a little prescient when studying programming in the time of AI.

![Image of a drafting shop with rows of drafting tables](assets/draftingshop.png)

With the development of drafting and art design software in the 1980's, the drafting profession was effectively eliminated from the labor market as a job in itself and the skill-set is now only one among many skills needed for specific professions like architects and CNC operators.  The lesson here is that engineers must be wary of developing too narrow a skill-set because an extremely narrow specialty can be entirely eliminated from the labor market due to technological advancement.  While programming is a specialty, programmers need to be flexible enough to adapt to new technologies and languages as changes affect the programming labor market especially in the burgeoning age of AI.  Consider that you are making a substantial investment for this education with the expectation that your college fees are amortized over a 40+ year career.  This course will focus on developing language independent skills that will help the modern programmer survive specialized changes to the labor market in order to make a programmer more adaptable in the face of technical pressure to subsume the programming job.  

Computers are also still surprisingly slow for this day and age especially from a lay user perspective. This is probably a somewhat confusing claim because we have reached a moment in technical capability where generative AI is feasible; however, the technology and skills required to create efficient software is extremely complex and in some cases unintuitive.  While computers are much faster than they used to be, there are still problems that are unsolvable on existing computers if the problem is improperly approached.  A poor choice in data structure can even make programs run extremely slow or fail to resolve a solvable problem even on modern hardware.

To facilitate understanding of the engineering of software, we will NOT use any built-in data structures of Java. Instead, we will design all of our data structures from scratch. To this end, students are NOT allowed to use any existing java utility classes for any assignment unless explicitly endorsed.  Instead students will write their own versions of standard data structures as Java classes which will ensure students understand how to write industry standard data structures for applications where libraries are not available or feasible or understand the cost of choosing one data structure over another for a specific application.

This class is not really about learning to leverage Java. We will learn more about Java in order to become better at Java, better at object oriented programming, and better at programming in general, but the lessons are much more generalizable and apply to many different programming languages.  Java is just a medium we will use to learn and really has no special significance.  Java is one language among many and while it is good for some applications, it is completely inappropriate for many other applications.  An experienced programmer is prepared to work in any language, even those that don’t exist yet.

At a deeper level, this course is about learning what the true cost of using a specific algorithm or a specific data structure is. As an aspiring scientist, your immediate question should be what is meant by “cost”? In terms of this course we will define cost in terms of both time and space, but now you should ask what is meant by “time” and what is meant by “space”?  Throughout this course, we will learn both how to quantify the amount of space used by a data structure or an operation and how to quantify the amount of computation time needed to complete an operation.  We will use a variety of terms such as efficiency or complexity to communicate these concepts, but fortunately, these approaches will be simple, robust, and useful. 

Fortunately, memory has grown according to Moore’s Law for the last 60 years, so memory is abundant and cheap in the modern computer, so there is less emphasis on the cost in terms of space today than there was twenty or more years ago. As a result, we may deemphasize space as a cost or even assume an understanding of it later in the course; however, space utilization can still be very important especially in terms of systems that may have extremely limited memory capacity such as a wearable application so cost in terms of memory is still relevant and cannot be ignored.

Conversely, computation time still remains incredibly important and will remain so until we have quantum computers.  Even with our significant advancement in computing power, there are problems that cannot be solved on modern computers, and in fact it is trivially easy to write a program that cannot be solved in a reasonable amount of time.  One of the most important lessons in this class will be that the organization of code determines the time efficiency of a program and simple structural changes to a program can change the program from unsolvable to solvable in terms of real time processing. 

This class is also about learning how to predict using science. In fact, prediction is the superpower of science which has facilitated all of the tools of our modern society: we predict the capacity of bridges and so they are engineered to support thousands of cars per day and do not generally fall down, we predict airflow over a wing and lift capacity so we are able to move tens of thousands of passengers via jet airplane everyday with minimal accidents (mostly attributed to poor maintenance or operator error), etc.  Given these principles and their powers, we want to use the scientific method to help us anticipate how long it will take for our program to run, how much space is required, and how reliable it may be.  To do so, we will learn to analyze our problems and communicate our ideas using abstract models and symbolic languages. 

This brings us to the most abused word in programming, abused in the sense that you will hear it used in almost every programming conversation but its definition will always remain a bit elusive. That word is "abstract", so what does it mean?  Abstract can mean an idea, the essence of, or a representation of.  These are reasonable definitions but they themselves are very abstract and only start to scratch the surface.

For example, a blueprint is an abstraction of a building. The blueprint represents the plan but it is not the building itself. In a subdivision. Many houses may share the same blueprint, but they may differ in the specifics of their construction. In other words, they are the same in their ideas, but they may have specific differences in their implementations. 

![common-blueprint-houses](/home/jrt/gwu-new/course/cs1112/assets/common-blueprint-houses.png)This will become a critical distinction throughout the material for this course. A `class` acts as a blueprint, but we generate objects from that blueprint. This is the same as the difference between classifying a model such as the idea of a house (the class) and creating a new instance of that house (creating a new house object). 

Our ultimate goal with the course is to design software without incurring the cost of implementing it. Ultimately, design is a separate step from implementation and we want to break these phases up into clear and independent steps. We also want to predict and quantify the costs of each of the steps appropriately so that we can anticipate the cost of development long before we and our stakeholders commit to the investment required to deliver a solution.

## Algorithm

What is an algorithm?  You might have already encountered the term "method" which is quite common in Java or the more general term "function" which is widely used regardless of programming language.  Both of these terms try to capture the idea of a "sequence of operations associated with a specific set of data" and are generally descriptive of object completing a sequence of operations.  However, these terms are built on rather simple concepts extended from a long history of terminology that is derived from basic mathematical ideals and practical concepts.  In a programming career, one will hear the terms algorithm, operation, subroutine, procedure, function, and method all used interchangeably.  While these terms may be used interchangeably according to specific contexts, they may be used more generally and interchangeably throughout a career in computer science.

Regardless of the specific term, the idea of an algorithm or function represents a process that requires a set of inputs, a sequence of steps, and a set of return values.  Keep in mind that an algorithm <u>always</u> takes input and produces output even if it is the null set.  This concept is most similar to the idea of a recipe in the real world where an algorithm, like a recipe, must prescribe the ingredients (inputs), the product produced (outputs), and the steps (the ordered process) necessary to successfully complete the task.  Even feral programmers are used to this idea because it does represent the basic elements required for the definition of a function (or method).  A really complex program can be considered an algorithm as it takes input whether through files or device inputs, executes a process, and produces output through devices, files, or even a simple return value from `main`.  In short, a program is an algorithm composed of algorithms.

## Data Structure

While the concept of a data structure does include an array; an array is actually too simple to comprehensively act as a data structure in most languages.  In fact, an array is so fundamentally associated with basic system design that an array does not really offer any significant structure without some coherent plan and a system of rules applied to it and as such an array by itself is rarely sufficient enough to be a complete data structure at least as far in terms of a modern data structure.

The modern data structure of a class is an outgrowth of the C structures defined using the `struct` keyword.  

```C
struct Box {
    int width;
    int height;
}
```

The role of the C-struct was to compose the state data of a number of unique but related variables into a single structure so that a programmer could create a new instance of structure in one step and pass a single reference to that structure as a parameter instead of using a contrived and necessarily complex naming convention to associate together related variables and managing the complexity of passing multiple associated variables to a function.  As in the above example, the `Box` is composed of `width` and `height` properties; however, the `struct` is incapable of encapsulating methods associated with the `Box` idea, so any 'methods' have to implemented as basic functions.  This leads to organizational issues in sufficiently complex software.  A better solution would be to allow data structures to encapsulate both properties and methods associated with that structure.  This concept became a part of the fundamental basis for Object Oriented Programming (OOP) by extending the C-structure to contain and group together both associated functions (methods) and associated data into the `class` container.  

```Java
class Box {
    // data
    int width;
    int height;
    
    // methods
    int area();
    int perimeter();
    void draw();
}
```

In the most modern context of object oriented languages, when we refer to a data structure, we are generally referring to one or more classes that work in conjunction to maintain data according to a specific applied concept such as a graph, tree, list, etc.  The same concepts can be applied in more fundamental languages using `structs` or their equivalents and a set of functions or even at the most primitive level  using only a set of associated variables and functions.

Data structures allow us to apply concepts and rules to structure and manage data such that we can expect specific behaviors and performance from interactions with that data.  In this course, we will discuss a variety of data structures including a more refined array, an alternative to the array called a linked list, structures maintained by a strict policy such as stacks and queues, hierarchical structures like trees, associative structures like hash tables composed of combinations of more basic data structures, and the general structure of a graph.

# 1 - Fundamentals

## Pseudocode

<!-- Write a thorough intro to pseudo code to motivate its use -->

Good pseudocode is algorithmic, not language specific, simple, and easily human readable.

### Algorithmic

An algorithm is like a recipe. Defining an algorithm should prescribe the ingredients (inputs), the results (outputs), and the steps (the stepwise, ordered process) necessary to successfully complete the task.  Algorithmic development is not simply implementing the process but it is also clearly documenting the algorithm including documenting any and all inputs and any and all outputs.

Pseudocode should be organized as a stepwise sequence and not as a paragraph.  Pseudocode is used for organization and logical analysis at the beginning of algorithmic development, but it also can act as key documentation of the implementation as it allows a stakeholder to understand the process without needing to read syntactically detailed code.  In other words, the pseudocode that a programmer may write to initially understand and organize the logic of a process can become the documentation embedded in the code which can be critical for future debugging or further development.  In this regard, writing pseudocode that is too symbolic and too close to the programming language becomes redundant and does not add any information to the code.  Consider the following example where pseudocode is written using Java comments...

```
// for i = 0 to n-1
for(int i = 0; i < n; i++) {
    // print A[i]
    print( A[i] ); 
}
```

The above pseudocode meets general pseudocode criteria, but it is redundant and does not really add any information.  It is actually more distracting than useful because it provides no new information and any stakeholder still has to infer the intent of the code.  Consider this alternative:

 ```
// iterate over all elements in A
for(int i = 0; i < n; i++) {
    // print each element to the console
    print( A[i] ); 
}
 ```

In this example, the pseudocode provides additional context and does not require someone to interpret the code to understand what the process is doing.  If we omit the implementation it would leave the following... 

```
// iterate over all elements in A
    // print each element to the console
```

The above is probably an artifact of the first algorithmic developmental step where the developer reasoned out the process in human terms.  The added code was simply a translation step into the implementation language from the pseudocode. 

We can perform time complexity analysis on pseudocode before investing the time to write syntactically correct and debugged in depth code which means we can assess whether it is a correct approach before spending costly, limited resources on an implementation.

### Not Language Specific

As suggested, good pseudocode is not required to conform to any language’s specific syntax.  Good quality pseudocode should be easily translatable to any language but there is no single or formal definition of pseudocode.  Programmers need to develop their own pseudocoding skill and also the flexibility to read other programmers pseudocode.  Good pseudocode should be both simple and easily human readable.

Code in a specific language must adhere to syntactic and allocation rules and can become deeply symbolic and dependent on evolving steps.  Pseudocode frees a programmer from focusing on language specific rules and lets a programmer focus on the process and quickly sketch it out without the need to debug language specific details.  A programmer should work out the logic of an algorithm first and then focus on translating it into a specific language.   This allows a programmer to first debug the logic in the abstract language so the programmer may know it is algorithmically correct.  Once a working model is proposed, the programmer can then focus on translating it according to the specific syntactic nuances of a the implementation language. 

### Simple

By keeping pseudocode simple, it can omit trivial details that are just not necessary to communicate the idea.  For example, it is a common pattern to use a for loop with an index that increments the index each pass through the loop to complete some repetitive task.  Unless there is something very special about the incrementing of the index, it is not necessary describe incrementing the index.  In fact, pseudocode for a loop might completely abstract away the specifics of the for loop and focus on the overall task.  Just as in the example above:

```pseudocode
// iterate over all elements in A
```

suggests a loop without prescribing the implementation.  A language may not even have a `for` keyword, so using more generalized language might be more easily translatable.  In the example, there are no indices and no for loop, yet the idea of looping is fully described.

There are some associated costs like, the creation of space in memory in an implementation, but these details often distract from and are superfluous to the algorithmic analysis. Yes allocating space is costly in terms of both time and space, but it is generally linear time at worst and most algorithms are linear time at best, so including pseudocode about allocation, unless it is the central feature of the algorithm, is distracting and mostly irrelevant to the more important exercise of sketching out the logical steps involved with an algorithm. Memory allocation is also usually closely associated with language specific features.  For this reason, most memory management will not be mentioned in the pseudocode sketch of an algorithm unless it is a critical feature of the algorithm.

### Easily Human Readable

We write pseudocode for stakeholders not for the computer.   In other words, we write pseudocode for people and not for automated systems.  

One of the purposes of AI systems is to bring computing closer to human communication and reasoning, so we would prefer to provide more human oriented prompts or sketches to the computer.  In this regard it would benefit the novice programmer to learn how to more clearly communicate the ideas and structure of a process in the necessary logical order to generate code faster through these systems than to focus on writing perfect syntax in the first programming pass.

Reading code is non-productive time, or in other words, no one gets paid to read code.   Over the lifetime of the program, someone will likely have to read through code you write, most likely you.  Debugging is costly in terms of time and money. We do not want to break working code. Changes are costly.  If pseudocode is written before implementation it can be used as comments for development and it can create a scaffold for code design that allows the programmer to fill in the blanks.  It is considered good practice to sketch out the process as pseudocode comments first and then write the actual code in between each pseudocode step.  This also has the added benefit that it leaves clear explanations that summarize segments of code so that debugging is safer and easier.

## Activity Times

Java is a compiled language. In other words, there are three activity times for development involving a compiled language:

1. Design Time
2. Compile Time
3. Run Time

### Design Time

Design time encompasses all the activities around writing code. Design time is the time involved with writing code. Students often wrongfully associate actions with design time. The central issue revolves around that nothing really happens during design time and students associated design time with actions like allocating memory; however, one key is that allocation can only happen during execution,

### Compile Time

Compile time encompasses all the activities around compiling code. This activity is mostly out of the hands of the programmer as this is the step where a rather sophisticated program interprets the code produced during design time. This is a translation step by very definition as the compiler is translating the steps defined by a high level language into the more primitive instructions necessary to fulfill the high level design. One of the mistakes of a novice programmer is to imagine that small structural changes at the design level affect the overall system generated by the compiler. The fact of the matter is that the compiler makes decisions about the code provided to the compiler that are difficult to anticipate and therefore small, deeply debated changes at design time can have no impact on the code produced by the compiler. Optimizing design time code such that the code produced by the compiler requires extensive understanding of the compiler. For the most part, the novice programmer hallucinates that changes to the code will produce any marketable improvement in the program actually produced. In other words, without extensive knowledge of the compiler, modest code restructuring will likely have no impact on the run time efficiency of a program.

### Run Time

Run-time encompasses all activities around running code. Students again hallucinate a number of activities at design time that are actually performed at run time. For example, a variable is never allocated until a program actually runs. Students tend to deeply associate allocation of a variable with design time activities when in fact allocation is a run time operation. In other words, there is no memory available and therefore no memory can be allocated at design time; 

however, at run time, we cannot actually execute unless memory is available. 

## State

The term **state** captures the idea of the values of a system at a specific point in time.  What can we generally say about `x` and `i` in the following example:

```java
x = 0;
for( int i = 0; i < 10; i++ ) { 
    x = x + i;
}
```

Variables are a programming tool because a program must change values throughout its execution.  The term variable literally means it has the capacity to change over time, so it is important for a programmer to consider the state of a variable with respect to a specific point of time and to rarely assume the state of a variable at any point in time.

We can loosely associate vertical position in adjacent regions of the program with time.  Unless there are some control elements that change the flow of execution, lines in the same function will be processed from top to bottom.  For this reason, line numbers become a loose proxy for time, but it is again important to be clear about the the control elements around a specific line number.  If a specific line is inside a loop, a programmer needs to not only consider the line number but also the iteration of the loop.

Generally, with each line executed, there is some change to at least one value in the overall system.  As the program proceeds through lines, it is “evolving”. In other words the value of variables are changing with respect to time.  We not only use the term state to describe the snapshot of a variable at a specific line but also the snapshot of an entire system with respect to a specific point in time.  For example:

```java
x = 0;
for( int i = 0; i < 10; i++ ) {
	x = x + i;
}
```

We may concern ourselves with the state of `i` or with the state of `x` as independent variables, or we may concern ourselves with the state of the entire system including both `i` and `x` as a snapshot of the entire system at any specific point in time.  In other words, state may refer to the “status” of a single variable, of an object, or of an entire system, but it implicitly means that we are capturing this information at a specific point in time as it will change with further evolution of the system

When debugging, we have to be very familiar with and careful of assessing the state of the system. A bug arises because the system enters an unanticipated state that the system was not designed for. When discussing state, it is important to specify both the scope of what is being assessed, variable, function, object, system, and the time at which it is being measured.

We may **trace** a system.  Tracing means to track the evolution of a system by hand to identify where the state is invalid.

<!-- add a sample trace -->

## Java Types

Java is a **strongly typed language** which means that all variables have to be declared before they can be used. Every Java variable **declaration** has two required components: `<type>` and `<label>` in other words a Java variable declaration follows the form: 

`<type> <label>;`

For example, each of the following are examples of a Java declaration:

```java
boolean success;
int i;
float x;
int[] A;
String msg;
```

In each of the above examples, a `<label>` is declared with a specific `<type>`. In Java, and any strongly typed language like C, the label cannot appear before the declaration, so the declaration must always be made “above” the usage of any symbol using the declared label. Considering that programs are generally processed from top to bottom, before means that any variable must be declared at a line above the symbol’s usage in any expression. In other words, the symbol’s type needs to be clearly specified before it is used in any way. 

The purpose of a declaration is to notify a language’s compiler of usage and syntactical rules for a specific variable. This is a feature and while it may sometimes be in the way for a language like Java, it is one of the purposes of using Java. Consider that in Python, variables do not need to be declared and so illegal operations may only be discovered at the time of execution. For a strongly typed language, some operations can be validated at the compile time simply because of type declaration. The reasoning here is that one signifier of correct logic is following consistent syntactical rules, and if syntactical rules do not exist or are loosely enforced, then there is a higher likelihood of errors in the program. In other words, one of the services a strongly typed language can perform is to indicate errors that arise due to a program violating syntactic rules. These types of errors can be detected before run time during compile time.. 

### Meta-type

In Java, the `<type>` declared must be one of the available and legally defined types. All types can be broadly classified as belonging to one of two meta-types.

A **primitive type** represents the basic data built into a programming language. There are eight Java primitive types each of which is defined by a specific Java keyword and commonly color coded in modern IDE’s to easily identify them. The Java primitives are byte, short, int, long, float, double, boolean, and char. All other types including arrays and types defined through classes are non-primitive and are represented as a **reference type**. Variables are either primitive or non-primitive. If a variable is declared with one of the eight primitive types, it must be primitive, and if a variable is not one of the eight primitive types, it must be non-primitive and therefore a reference type. 

Primitives:

```java
boolean success;
int i;
float x;
```

Non-primitives are everything else:

````java
int[] A;
String msg;
MyCustomClassType o;
````

We make a distinction between primitives and non-primitives because primitives are simple, fixed size, single values in memory while non-primitives are containers that may hold sets of values. Since primitives are fixed in size, they are stored in a single location in memory, and since non-primitives may be composed of multiple values, they need a range of memory to store them. Because each of these two metatypes have such different memory requirements and behaviors, they are treated very differently in code.

The value stored in a non-primitive is really a memory address. This address references where the container exists in memory which means the value stored in memory for all non-primitive types is interpreted as a location. Since there is an indirect relationship between the variable value and the container for non-primitive types, we may describe non-primitive variables as “reference types”, *i.e.* they refer to the location of their data, or “pointers”, *i.e.* they point to the location of their data. Because a reference type has two pieces: the variable and the object it refers/points to, both pieces have to be managed. 

Consider the following declaration and what it instructs the compiler to do.

```java
int[] A;
```

A programmer will typically describe the above as declaring an integer array; however, this is not technically correct. The declaration actually instructs the compiler to set aside a pointer A that is allowed to point to an integer array and it does not actually instruct the compiler to create an array. Creating the array requires an additional step and the use of the new keyword.

```java
A = new int[5];
```

This second step is what makes the request to the compiler to allocate an array with space for 5 integers. Whenever working with non-primitives, we must be mindful that creating the reference is a separate step from creating the object and that it is legal for a reference to refer to nothing which we call `null`. Primitive types always must contain a legal value, so they do not point and they can never be nothing.

### Initialization

Another concern for variables is establishing initial state.  Optionally, a Java variable declaration may assign a specified `<initial value>` to the variable overriding assignment of the default value or a programmer may allow Java to assign a default value for `<initial value>` if one is not specified by the programmer.  The `<initial value>` must be a value that conforms to the declared type. A Java declaration that assigns an initial value follows the form:

```java
<type> <label> = <initial value>;
```

The following are examples of appropriate values for each of the associated types `<initial value>`:

```java
boolean success = false;
int i = 0;
float x = 1.0;
String msg = “”;
```

All data in memory is a number whether it is a `byte`, `boolean`, `char`, or even non-primitive type.  The variable type instructs Java how to interpret the underlying numeric representation in memory.  

A `boolean` is interpreted as either `true` or `false`.  If the numeric value stored in the `boolean` variable's memory location is location zero, the `boolean` variable is interpreted to have the value of `false`.   If the numeric value stored in the `boolean`  variable's memory location is non-zero, the `boolean` variable is interpreted to have the value of `true`.

Numeric types have specific formats but generally a zero representation in these formats is interpreted as a zero numeric value.

Non-primitives are really addresses of locations in memory, so a zero value is interpreted as referencing the zero address in memory.  The zero address has a special role on a computer and it is generally illegal for any program to access the zero address.  As such the zero address has a special meaning of representing nothing and the special keyword of `null` to identify it and suggest it is nothing.  

If no initialization is provided with a Java declaration, Java automatically assigns the variable a default value of zero to memory and the type determines how that value is interpreted.

```java
boolean success; 	// zero boolean is interpreted as false
int i;      		// zero int is interpreted as 0
float x;     		// zero float is interpreted as 0.0
String msg;   		// zero non-primitive is interpreted as null
```

The above is equivalent to:

```java
boolean success = false;
int i = 0;
float x = 0.0;
String msg = null;
```

Non-primitive reference types are either assigned a `null` pointer, *i.e.* they don’t point to a legal address yet, assigned to point to a newly constructed object as signaled with the `new` keyword, or assigned to point to an already existing object through another variable.

## Proof By Exhaustion

There are a variety of strategies we can use to find an answer but one approach is to simply try every possibility.  In other words, this strategy attempts to prove a hypothesis by exhausting all possibilities and it is known as “proof by exhaustion” or a “brute force approach”.

Consider search for a moment.  If our search strategy is to simply check everywhere, we are using a brute force approach.  However, if our strategy is to order the set and then compare the middle value with our search value allowing us to eliminate either the first half or the second half from subsequent comparison, we are using another more refined strategy, specifically we call this strategy “divide and conquer”.  

Brute force is the most costly approach we might use other than some random approach.  People naturally learn this in their lives and create their own strategies to minimize search. For example, it is a common strategy to avoid searching for our keys if we put them in the same location every day.

## Exponentials and Logarithms

At some point in your mathematical education you learned exponentials (powers) and their relationship to logarithms.   We will find that both of these mathematical functions will be useful from an analytical standpoint, so it is important to refresh our understanding of them as we begin this course.  One bit of reassurance is that we will exclusively focus on exponentials and logarithms in base 2 for this course.

### Base 2 Exponential

A base 2 exponential is expressed by the following formula:

$y =2^x$

Since this is a base 2 exponential, every time $x$ increases by 1. the output doubles the result of the preceding value of $x$.  For example, if $x=2$ the result $y=4$ but if $x=3$ then $y=8$.  The result $y$ of the second case is exactly double the result of the first case but with only an increase in $1$ for the value of $x$.  This doubling is the consequence of the the choice of base and since the base equals $2$ every increase in the exponent by $1$ doubles the previous result.  Functions that involve a similar rate of change are typically referred to as having "exponential" growth.

If my investment grows exponentially year over year, I will grow quite wealthy in a short period of time.  We can think of the initial equation as asking the question how much larger will be my investment after 5 years, $x = 5$, if it doubles year over year and the answer will be 32.  In other words, if I invested \$100 in year zero, my investment should be worth \$3200 after 5 years.  Exponentials can be powerful functions in terms of growth.

| $2^{0} = 1$   |                  |
| ------------- | ---------------- |
| $2^{1} = 2$   | $2^{9} = 512$    |
| $2^{2} = 4$   | $2^{10} = 1024$  |
| $2^{3} = 8$   | $2^{11} = 2048$  |
| $2^{4} = 16$  | $2^{12} = 4096$  |
| $2^{5} = 32$  | $2^{13} = 8192$  |
| $2^{6} = 64$  | $2^{14} = 16384$ |
| $2^{7} = 128$ | $2^{15} = 32768$ |
| $2^{8} = 256$ | $2^{16} = 65536$ |

### Base 2 Logarithm

Logarithms are the “inverse exponential” and represent decay rather than growth.  To understand the relationship of logarithms with the exponential recall the initial exponential equation:

$y =2^x$

We can take the logarithm of both sides of this equation:

$\log_{2}y =\log_{2}2^x$

We take the base 2 logarithm of both sides because the exponential base is 2.  Our goal is solve for $x$ which means we need to eliminate the base on the right side of the equation.  By taking the base 2 logarithm of the right side, the base of 2 in the exponent is cancelled.   In other words, the equation becomes the following:

$\log_{2}y = x$

Let's slightly rearrange the terms by swapping the terms on either side of the equal sign:

$x = \log_{2}y$

What types of questions does this equation answer?  The original question addressed the question of "if my money doubles every year, how much money will I have in $x$ years". This new question is capable of addressing the question of "if my money doubles every year, how many years will it take for me to earn $y$".  Similarly it can answer how many times can I divide this set in half until I have one element left.

| $\log_{2} 1 = 0$   |                       |
| ------------------ | --------------------- |
| $\log_{2} 2 = 1$   | $\log_{2} 512 = 9$    |
| $\log_{2} 4 = 2$   | $\log_{2} 1024 = 10$  |
| $\log_{2} 8 = 3$   | $\log_{2} 2048 = 11$  |
| $\log_{2} 16 = 4$  | $\log_{2} 4096 = 12$  |
| $\log_{2} 32 = 5$  | $\log_{2} 8192 = 13$  |
| $\log_{2} 64 = 6$  | $\log_{2} 16384 = 14$ |
| $\log_{2} 128 = 7$ | $\log_{2} 32768 = 15$ |
| $\log_{2} 256 = 8$ | $\log_{2} 65536 = 16$ |

## Review

1. What is an algorithm?

2. Compute the powers of two from $2^0$ to $2^8$.

3. Explain why the base 2 logarithm predicts the maximum number of times a discrete set can be repeatedly subdivided in half.

4. With diminishing rainfall over the years, water reservoirs are stressed throughout the country. Imagine a scenario where half the preceding years rainfall is collected each year. If the local reservoir collected 50 feet of water this year, in how many years will the collection be less than 1 foot of water? Model your answer with a mathematical equation. *Hint : approximate numbers are good enough.*

5. You are given a 416 card deck (eight 52 card decks) of playing cards for blackjack. You divide the deck precisely in half resulting in two decks of 208 cards. You repeat this process again on each of the generated decks which results in you having four decks of 104 cards. Model this process with a simple mathematical expression and use that model to predict the maximum number of times you can repeat this process before ending up with decks consisting of either 1 or zero cards. 

6. You are given a deck of 26 cards each with a different letter of the English alphabet on it. You divide the deck in half resulting in two decks of 13 cards each. You repeat this process resulting in four decks containing either 6 or 7 cards. If you continue to repeat this process, eventually you will end when you have a number of decks consisting of either 0 or 1 cards.

   a. Model this problem with a diagram that illustrates the number of times this process is repeated. One step in the process is considered subdividing all of the available decks into smaller decks.

   b. Model this problem with a simple mathematical formula.

7. You have found a crypto coin that is projected to double in value year over year for the next seven years. If the coin is currently worth \$0.20, the projection predicts it to be worth \$0.40 next year and \$0.80 the year after that, and so forth. Model the expected growth for this coin through seven years using either a diagram or mathematical formula.

8. Java is a strongly typed language, what does this mean?

9. What two minimum pieces of information are required for every Java variable declaration? 

10. Give an example of a Java variable declaration.

11. What is the default value assigned by Java to every variable if an initial value is not explicitly provided?

12. Explain how Java handles assigning default values to variables if an initial value is not explicitly specified?

13. A memory location contains the value 100. If the value at that location is interpreted as a boolean, what value will be produced? 

14. A memory location contains the value 0. If the value at that location is interpreted as a non-primitive, what value will be produced? 

15. All Java types belong to one of two meta-types. What are the two “meta-types”?

16. The Java `int` type belongs to which “meta-type”?

17. Given the following Java variable declaration:    `int[] x;`

    a. What type is being declared?

    b. What meta-type does the above type belong to?

18. What meta-type does the Java String type belong to?

19. Give two examples of a primitive type.

20. Give two examples of a non-primitive or reference type.

21. All non-primitive variables contain the same kind of data. How is the value stored in a non-primitive type interpreted?

22. What is meant by the term state?

23. What is the relationship between the status of a variable or system with respect to time?

24. Explain what is meant by “the state of the program at line 5”?

25. What is the relationship between time and the values of variables in a program?

26. What does it mean to say that a program evolves through its execution?

27. Assuming an infinite universe, why would it be impossible to prove that life does NOT exist elsewhere in the universe?

28. What does it mean to use a “proof by exhaustion” or “brute force” strategy?

29. Recall our simple computer that can only store, add , negate, and conditionally loop.

    a. Why does the number of operations remain constant for the subtract function?

    b. Why does the number of operations in the multiply function vary with the size of the parameters?

## Vocabulary

algorithm

pseudo-code

activity time

design time

compile time

run time

declaration

state

trace

type

meta-type

primitive type

reference type

brute force

# 2 - Memory, Arrays and Strings

Computers have a variety of technology to retain data.  Some of this technology is used to store data when the computer is on while other technology is used to store data when the computer is off.  We generally use the term **memory** to refer to short term Random Access Memory (RAM) which is used to store data for running programs and the term **storage** to refer to long term data storage such as Hard Disk Drive (HDD) or Solid State Drive (SSD) which is used to store data long term.  Memory supports all of the variables and data in a Java program and it is managed by the programmer and compiler through the Java language and Java virtual machine.  To access storage, requires specific system calls to the operating system to make requests to read or write data between memory and a file in storage.  For this course, we will entirely focus on memory and while storage will be addressed in future classes.

<img src="/home/jrt/gwu-new/course/cs1112/assets/poboxes.png" style="zoom:50%;" />

Memory is like a set of mail boxes servicing a building where every location in the building has an address, *i.e.* a room or apartment number.  When a variable is declared in Java, that variable acts as a label to alias a memory address so you the programmer do not need to know or to refer to data by its memory address and instead can refer to it by its label.  For a variable of primitive type, the variable stores the value associated with the variable using **direct access** where the memory address aliased by the variable name holds the associated value.  For reference types, the variable instead stores an address, *i.e.* the address of the referenced object , which requires a form of **indirect access** where the stored address must first be accessed in one step before a value stored in that object is looked up in a second step.  Since references refer to another address we call them **pointers** because they point to the location in memory where the object or container resides.

## Program Memory Organization

![](/home/jrt/gwu-new/course/cs1112/assets/memory.png)

Computer programs use two blocks of memory to support their operation: the **code block** and the **data block**.  Recall, a program is composed of two separate elements: the immutable (read only) code that is executed to run the program, and the mutable (changeable) state data that represents all of the values making up the program at a specific point in execution.  The code is stored in the code block and it is not generally possible to change the code during the program's execution.  The state data, including all variables and objects associated with the program, is stored separately in the data block.

![](/home/jrt/gwu-new/course/cs1112/assets/memory-datasegment.png)

In Java, the data block is separated into three segments: the **global segment**, the **stack segment**, and the **heap segment**.  The scope of a variable depends on which segment the variable exists in and the segment in which a variable lives depends on where (and with what keywords) the variable is declared in the code.  

Memory must be explicitly given to a program, and in Java, requests for more memory are built into and managed by the language, compiler, and Java virtual machine.  Available, free memory is managed by the operating system and Java makes requests for new memory on behalf of a running Java program according to a prescribed "memory model".  When new memory is assigned to a program it is called **memory allocation**. 

Given a little experience with Java programming, these memory concepts may seem alien because Java intentionally hides these details from the programmer to simplify the language.  Regardless, memory allocation is fundamental to two different Java syntactical elements, *i.e.* declaring a variable or creating a new instance of an object using the `new` keyword.

### Memory Allocation

Memory is allocated by the operating system in response to request by a running program.  In other words, memory is not allocated until run-time while declaring variables is done at design-time.  One of the roles of the compiler is to write allocation rules for every variable declared at compile time.  At specific phases during program execution, Java reads the allocation rules for a region of code and handles the allocation request either by using blocks of memory allocated at program start or by passing it through to the operating system for more memory. 

In general, memory is either allocated as a **static memory allocation** or as a **dynamic memory allocation**.  In this context of memory allocations, the term *static* means "unchanging" and the term *dynamic* means "provided on demand".  In other words, a static memory allocation is an allocation made for the program that guarantees that memory allocation will be available for the duration of the program -- note that static does not mean that the value is unchanging but instead means that the allocation is unchanging.  In contrast, dynamic memory allocation provides a means for a program to ask for new memory at the moment it needs it.  A Java programmer does not have to think too much about these distinctions, but other languages may make the programmer more responsible for memory management and it may be important to discriminate between the two types of allocations.  In the following discussion we will plainly identify which variables are subject to these allocation rules.

Java also deallocates memory on behalf of the programmer according to specific deallocation rules so that the programmer does not have to focus on memory management.  Declared variables are deallocated when they go out of **scope**, while object are cleaned up by a special process called **garbage collection**.  Not all languages provide automatic garbage collection, *e.g.* C and C++, which means that in these languages the programmer is responsible for cleaning up heap memory allocations.

These allocation rules and the underlying organization of memory establish the concept of **variable scope**.

## Variable Scope

There are two aspects to a variable’s scope: **lifespan** and **visibility**.  

A variable's lifespan is the time between that variable's allocation and its deallocation.  A variable is only legally accessible if it has space in memory simply because a variable only exists between the time it is allocated and the time it is deallocated.  If there is no space in memory for the variable, the variable does not exist.  As such, all variables have a lifespan that dictates when it accessible.

A variable's visibility is the region of code in which that variable is accessible.  A variable is only visible as long as the variable exists and the scope of its accessibility is subject to the segment of memory in which it is allocated and is therefore dependent on where it is declared.

There are three variable scopes each of which is associate with a specific data segment: **global variables**, **local variables**, and **instance variables**.

- Global variable - allocated in the global data segment
- Local variable - allocated in the stack data segment
- Instance variable - allocated in the heap data segment

### Global Variables

Variables declared inside a class (outside a function) with the `static` keyword are **global variables**, *i.e.* have **global scope**.

```java
public class ExGlobal {  
    // a, b, c are all global variables  
    public static int a;  
    public static int b;  
    public static int c;   
    
    public static void main (String[] args) {    
        a = 5;
        b = 1;
        c = a + b;
    }
}
```

Global variables are stored in the  global segment of the data block.  All global variables are allocated when the program starts and are deallocated when the program exits and as such their lifespan is the entire run-time of the program.  Global variable are accessible anywhere in the program and therefore their visibility is everywhere in the program.

To differentiate global symbols from other symbols, it may be necessary to refer to them by their class name.  This is necessary if the global variables are declared in a separate class from the one being operated on.  The syntax in Java for accessing a global variable is  `<ClassName>.<label>`.

```java
public class GlobalVars {
    // d, e, f are all global variables  
    public static int d;  
    public static int e;  
    public static int f;   
}

public class ExGlobal2 {  
    
    public static void main (String[] args) {    
        GlobalVars.d = 7;
        GlobalVars.e = 8;
        GlobalVars.f = GlobalVars.d + GlobalVars.d;
    }
}
```

Global variables are generally dangerous to use especially in multiprocess applications and should be used for very limited purposes with additional guards used to protect access to them.  The reason for this is complex and will be explored in subsequent courses, but the basic problem is that two programs writing data to the same memory location at the same time can cause data to become ambiguous and corrupted in what is called a **data race** or a **race condition**.

The compiler writes rules for when global variables are allocated and deallocated, so a programmer does not need to generally manage memory for them; however, if a global variable is a reference type, it is necessary to separately consider when the object to which it refers is created.

The global variable being allocated at program start and deallocated at program end coincides with the allocation existing for the entire run time of the program.  This meets the definition of a static allocation above and is, in fact, why the Java global variable declaration uses the `static` keyword.  In Java, the `static` keyword is used to indicated a static memory allocation and therefore specifies a variable as a global variable.

### Local Variables

Variables declared inside a function are **local variables**, *i.e.* have **local scope**.

```java
public class ExLocal {  
    public static void main (String[] args) {    
        // i, j, k are all local variables    
        int i = 0;
        int j = 5;
        int k = 100;
    }
}
```

Local variables are stored in the data block’s stack segment.  Local variables are allocated when the function in which they are declared is called and are deallocated when that specific function call returns.  As such, a local variable is only available within the context of that function call, *i.e.* between the opening and closing brackets for the function, and only for that specific function call.   Recall that a function can be called many times and can even call itself which means each function call has its own variables even if this results in multiple versions of the same symbol being created.

All local variables use a dynamic allocation model where local variables are dynamically allocated on the stack when the function is called and those same variables are automatically deallocated when the function returns.  Local variables are accessible only inside the function after they are declared, but as a rule of thumb, the compiler allocates the local variable when the function is called.  For the sake of this class, assume that all local variables for a specific function are allocated when that function is called.

**Parameters**, *i.e.* input variables declared inside the parentheses of the function declaration, are variables declared in the function, so they are also local variables.  Parameters are unique variables, independent in terms of their memory location from the arguments that are passed to the function, so parameters are copies of the original values passed to the function.  This policy of copying arguments to parameters is known as **pass-by-value** and is the general policy applied to all function calls in Java and practically it means that changing a parameter in a function will not affect the value of the calling argument.  However, this only applies to direct access parameters as any referenced values can be changed inside a function and the change will be reflected outside that function.

The compiler writes rules for when local variables are allocated and deallocated, so a programmer does not need to manage memory for them.  In many ways, using the automated allocation and deallocation of local variables can greatly simplify memory management for a program and can ensure that key state data exists throughout the execution of a program.

```java
public class Rectangle {
    public int width;  
    public int height;  
}
```



```java
public class GlobalApproach {
    public static Rectangle rectangle;  
    
    public static void main (String[] args) {    
        rectangle = new Rectangle();
        ...
    }
}
```

In the `GlobalApproach` program, the global variable `rectangle` has the lifespan of the entire program, so it will be automatically cleaned up when the program exits; however, the global variable actually represents a weakness because we cannot easily limit its visibility to control when and where it can be accessed.

```java
public class StackApproach {  
    public static void main (String[] args) {    
        Rectangle rectangle = new Rectangle();
        ...
    }
}
```

In the `StackApproach` program, the local variable `rectangle` also has the lifespan of the entire program because it is declared and initialized to a legal object at the beginning of `main` and it is on the stack so it will be automatically cleaned up when `main` (the program) exits.  The visibility of `rectangle` in this program will be subject to explicitly passing the reference to `rectangle` as an argument.

<!-- Diagram would help -->

From a lifespan perspective, the `rectangle` variable has the same behaviors in both programs; however, the visibility in the `StackApproach` program is entirely different.  In the `GlobalApproach` program, a programmer cannot control access to the `rectangle` reference, so the object referenced can be accessed, modified, and even destroyed anywhere in the program.  In the `StackApproach` program, the `rectangle` reference must be passed to subsequent methods or objects to gain access to the referenced object; however, this will be done explicitly and within any rules created by the developers.

The `StackApproach` example represents a way to control and limit access to an object that is needed program-wide while also gaining similar memory management as a global variable.

### Instance Variables

Variables declared inside a class (outside a function) without the `static` keyword are **instance variables**, *i.e.* have **instance scope**, and are associated with (belong to) a specific instance of an object.

```java
public MyObject {
    // x, y, z are all instance variables  
    public int x;  
    public int y;  
    public int z;      
}

public class ExInstance {  
    
    public static void main (String[] args) {    
        // obj is a new instance of MyObject    
        // class. When obj is created, new     
        // instances of all instance variables    
        // declared in the class are created.    
        MyObject obj = new MyObject();
        obj.x = 0;
        obj.y = 2;
        obj.z = 50;
    }
}
```

Instance variables are stored in the data block's heap segment.  All instance variables declared in an object's class definition are allocated for an object when that object is newly created from a class and all instance variables for that object are available as long as there is a valid reference to that object.  A reference to an object can be a global variable, a local variable, or even an instance variable belonging to another object.

Instance variables are accessible through a valid reference to the object using the syntax `<reference-label>.<instance-label>`.  In the `ExInstance` example above, `obj` is declared as a reference type to objects of type `MyObject`.  While `obj` lives on the stack, it is a local variable declared in `main`, the object of type `MyObject` to which it refers lives on the heap.  To access the instance variables inside the object referred to by `obj`, the programmer must use the `obj` label as a prefix.  In other words, `obj.x` accesses the instance variable `x` stored inside the object referred to by the instance variable `obj`.  Instance variables can only be accessed outside the object using a valid reference to an object.

Instance variables do not exist until an object instance is explicitly created.  The `new` keyword asks Java to allocate a new instance of an object with the type that follows the `new` keyword.  All non-primitives must be allocated with the `new` keyword.  The `new` keyword causes the run-time environment to create the object on the heap.  All objects live on the heap.

All instance variables use a dynamic allocation model where instance variables are dynamically allocated on the heap when the object to which they belong -- the instance -- is constructed.  Instance variables are accessible inside the object and are available as long as the object exists.  An object exists until there are no more references to the object.  The Java system automatically deallocates an object if it no longer has any references to it using garbage collection.

```java
public MyObject {
    // x, y, z are all instance variables  
    public int x;  
    public int y;  
    public int z;      
}

public class ExInstance {  
    
    public static void main (String[] args) {
        MyObject obj2;
        ...    
        obj2 = new MyObject();
        obj2.x = 0;
        obj2.y = 2;
        obj2.z = 50;
    }
}
```

Remember that the reference to the object and the object are two separate things stored independent of one another in memory.  The above example hopes to illustrate that the declaration of `obj2` does not require or even guarantee that there is an object associated with it.  It is legal for a reference to point to nothing or `null`.  Creation of the object is an explicit step that requires usage of the `new` keyword.

### Garbage Collector

If an object on the heap has no references, then it cannot be accessed anywhere in the program and the object needs to be deleted.  Programming languages may use several strategies as to how to resolve deallocation of heap memory.

Some languages put the burden of deallocating and releasing heap memory back to the system on the programmer.  For example, C requires programmers to free the last reference to an object before the reference is set to null (or the program exits).  If the programmer does not free all heap memory, then the memory can stay allocated even after a program exits.  This phenomena is called a memory leak and explains why some programs can hoard resources from the operating system and other programs even if the program exits which can only be resolved by a reboot.

Java as well as many other high level languages provide a process that prowls around the heap looking for objects that are inaccessible.  Rather than forcing the programmer to manage heap memory, this process takes on the role of deallocating heap memory if an object has no more references.  This process is called the garbage collector which performs garbage collection on the heap.  Note that garbage collection is only performed on the heap as the stack and global segments allocate and deallocate using different rules.

The garbage collector comes at a cost.  It runs about every millisecond and steals some processing time away from the processes that you are actively running.  If there is a significant amount of deallocation work, the garbage collector will interrupt progress of any process while it cleans up the heap.  This can be a problem with real-time applications that must meet deadlines such as control software for planes or robots.  In the case of these applications, it may be better to choose a language that forces the programmer to control deallocations because the programmer also controls when deallocations occur and there is not an uncontrollable process that may interrupt scheduled events.

##                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 Arrays

An array is a set of memory intended to hold a set of elements all with the same type.  Java uses special syntax for arrays however Java arrays are still classes.  Therefore, Java arrays have properties and methods accessible by the dot operator and Java array declarations are also non-primitive references.  

```java
1  public class ArrayEx {
2    
3      public void main(String[] args) {
4          int[] A;        // A is declared as a reference type that will refer 
5                          // to an array of ints
6          ...
7          A = new int[5]; // the new keyword requests creation of an array of ints
8                          // with 5 elements.  Up until this point, A referred to
9                          // null (nothing).  After line 7, A will refer to the
10                         // array allocated by line 7
11      }
12 }
```



![](/home/jrt/gwu-new/course/cs1112/assets/ch2-basicarray.png)

As a result, the array is an entirely separate entity from the variable declared in code.  A programmer must consider the scope of both the array reference pointer and the array object independently.  These two entities may live in entirely different memory locations, where the location of the array reference is subject to where its variable is declared and the array itself always lives on the heap because it is an object.  

An object may have multiple references to it, so while the pointer initially assigned the reference to a new object may be cleaned up, one or more additional pointers to the object may have been established between object creation and initial pointer deletion which means the object itself will not be cleaned up until all references to the object go out of scope.

```java
1  public class MultiPointerEx {
2      public static int[] B;
3    
4      public void main(String[] args) {
5          foo();
6          ...
7      }
8    
9      public void foo() {
10         int[] A;        // A is local to foo.
11         ...
12         A = new int[5]; //  A holds initial reference to array
13         ...
14         B = A;          // B is a global var.  B copies the reference to A
15         ...
16         // A and B have different scopes.  A is cleaned up upon return from foo.
17         // B is global and will persist even after foo.  As a result, the array
18         // will persist even after A goes out of scope here because there is at 
19         // least one reference to it beyond A in this case via B.
20     }
21 }
```

The `MultiPointerEx` example demonstrates copying a pointer.  Regardless of the type that is referenced, all reference types contain only a memory addresses.  In other words, the line `B = A;` copies the address stored in `A` into `B`.  It does NOT copy the data stored in the object into a new object.  In the `MultiPointerEx` there is only one object, but inside `foo()`, there are temporarily two references to that object.  At the end of `foo()` the global variable `B` continues to refer to and anchor the object in heap memory even after variable `A` is deallocated because the `foo()` returns and all of its local variable go out of scope.

<img src="/home/jrt/gwu-new/course/cs1112/assets/ch2-multiptrex-programs start.png" style="zoom:50%;" />

In the `MultiPointerEx` example above, `B` is declared as global variable, so it is allocated in the global area when the program starts.  However, it is not assigned to an object so by the rules of Java as a reference type it is initially assigned to point to nothing.

<img src="/home/jrt/gwu-new/course/cs1112/assets/ch2-multiptrex-foo call.png" style="zoom:50%;" />

When the method `foo()` is called, the local variable `A` is allocated on the stack; however, like variable `B`, variable `A` has not been assigned an initial value, so it too is assigned to initially point to nothing.

<img src="/home/jrt/gwu-new/course/cs1112/assets/ch2-multiptrex-array allocd.png" style="zoom:50%;" />

At line 12, variable `A` is assigned to point to (a reference to) the newly allocated array of integers with 5 elements.  As the array is a container type/object, it is allocated on the heap because all objects live on the heap.

<img src="/home/jrt/gwu-new/course/cs1112/assets/ch2-multiptrex-ptr copy.png" style="zoom:50%;" />

At line 14, `B` is assigned the same reference value stored in `A`.  Note that this does not copy the array, it only copies the reference to the array.  As a result, both `A` and `B` point to the same array.

Copying a pointer does not create new objects. Instead it copies the address of the object.  This means that a programmer must explicitly develop a means to copy objects if copying objects is the programmer's intent.  In contrast, copying a primitive is simple and straightforward using the assignment operator.  Copying a pointer may be called a shallow copy and copying a primitive value may be called a deep copy.

## Shallow Copy and Deep Copy

We use the simple terms **shallow copy** and **deep copy** to communicate what is copied.  The term shallow copy tries to communicate a superficial or surface level copy of information and the term deep copy tries to communicate a comprehensive or deep level copy of information.

The following `PointerCopy` example demonstrates a shallow copy where two references refer to the same object in memory.  Since both references refer to the same data, a change to either pointer is visible to both.

```java
1  import java.util.*;
2  
3  public class PointerCopy {
4  
5      public static void main (String[] argv)
6      {
7          int[] A = {1, 2, 3};
8          System.out.println ("A: " + Arrays.toString(A));
9  
10         // Declare a new array variable.
11         int[] B;
12 
13         // Pointer copy!
14         B = A;
15 
16         // A modification of B affects A
17         B[1] = 5;
18         System.out.println ("A: " + Arrays.toString(A));
19     }
20 }

```



<img src="/home/jrt/gwu-new/course/cs1112/assets/refcopy.png"  />

The following `ValueCopy` example demonstrates a deep copy where both references point to independent arrays of the same size.  The data is copied from one array to the other and while the second array contains duplicate information, it is independent of the other array after the copy operation is completed.  Since the references are refer to different memory locations, a change to either one does not affect the other.

```java
1  import java.util.*;
2  
3  public class ValueCopy {
4      public static void main (String[] argv)
5      {
6          int[] A = {1, 2, 3};
7          System.out.println ("A: " + Arrays.toString(A));
8  
9          int[] B;
10 
11         // First make the space - getting the length from A.
12         B = new int [A.length];
13 
14         // Copy each entry.
15         for (int i=0; i < A.length; i++) {
16             B[i] = A[i];
17         }
18 
19         // Modification of B does not affect A.
20         B[1] = 5;
21         System.out.println ("A: " + Arrays.toString(A));
22     }
23 }
```



![](/home/jrt/gwu-new/course/cs1112/assets/valuecopy.png)



## Strings

The term **string** is used in computing to describe a sequence of characters.  Java provides a `String` class to encapsulate all properties and methods associated with strings into a single class.  While the Java `String` class appears quite complex at least with respect to [having about a hundred methods associated with it](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html), the data in the class is simply just an array of `char` values.  In other words, the `String` class is just a wrapper for a  `char[]` property and any associated string operations.

#### ASCII

The American Standard Code for Information Interchange (ASCII) is a convention for character encoding first established in the 1960's.  ASCII defines the association between character data and the numeric values that represent them.  Recall that all data in memory is just a number, so the role of ASCII is to provide a translation layer between the numeric representations of `char` data in memory to the symbolic letters used in English.

For example, the decimal value of 65 is interpreted and translated as the English character symbol 'A' if it is typed as character data.  Similarly, the decimal value of 66 translates to the character symbol 'B' and so forth.

![](/home/jrt/gwu-new/course/cs1112/assets/asciitable.png)

If the string "HELLO" is stored as a Java `String` in memory, what is really stored is an array of `char` data with the values 72, 69, 76, 76, 79 where 72 is 'H', 69 is 'E', 76 is 'L', 76 is 'L', and 79 is 'O' according to the ASCII standard.

![](/home/jrt/gwu-new/course/cs1112/assets/ascii-hello.png)



Each block of uppercase and lowercase letters are in alphabetical order.  Additionally the difference between 'A' and 'a' is exactly 32 ($2^5$), so to convert from uppercase to lowercase is just addition and to convert from lowercase to uppercase is just subtraction.

| ![](/home/jrt/gwu-new/course/cs1112/assets/asciitable-uppercase.png) | ![](/home/jrt/gwu-new/course/cs1112/assets/asciitable-lowercase.png) |
| :----------------------------------------------------------: | :----------------------------------------------------------: |
|             Uppercase Letters 'A' (65)- 'Z' (90)             |            Lowercase Letters 'a' (97)- 'z' (122)             |

Similarly all numeric characters are also grouped together and in order beginning with 48 is '0' through 57 is '9'.

![](/home/jrt/gwu-new/course/cs1112/assets/asciitable-numerics.png)

It is important to understand that if numeric information has a `char[]` or `String` type, it is really represented as an array of characters in ASCII format and these values will require a translation step to convert them into numeric types compatible for math.

| ![](/home/jrt/gwu-new/course/cs1112/assets/ascii-65535.png) | ![](/home/jrt/gwu-new/course/cs1112/assets/ascii-20052.png) |
| ----------------------------------------------------------- | ----------------------------------------------------------- |

The first column (0-31) in the ASCII table contains 'control codes' which are generally unprintable or whitespace characters that are easy to overlook but can play crucial roles in documents.  

For example, the character 9 is the 'TAB' character which represents the whitespace Tab character associated with the Tab key on the keyboard.  Note that 'TAB' is distinct from character 32 which represents the 'SPACE' character which represents the whitespace Space character associated with the Space key on the keyboard.  These characters are distinct and are treated different due to the historical roles they played on typewriter keyboards.

![](/home/jrt/gwu-new/course/cs1112/assets/asciitable-commands.png)

Understanding typewriters and teletype systems can offer some interesting perspective on the ASCII model and the artifacts programmers must deal with even today.  For example, the end of line on a typewriter was a mechanical operation involving multiple individual actions.  When the end of line was reached:

1. The operator would return the carriage to its left most position by striking the carriage handle.  This is known as carriage return.
2. Upon carriage return, the drum, around which the paper was half looped, would feed to the next line.  This is known as line feed.

| ![](/home/jrt/gwu-new/course/cs1112/assets/1132px-MEK_II-371.jpeg) |
| ------------------------------------------------------------ |
| [By GodeNehler - Own work, CC BY-SA 4.0](https://commons.wikimedia.org/w/index.php?curid=75088136) |

Memorialized in ASCII are the carriage return (CR) as decimal value 13 and line feed (LF) as decimal value 10.  Since programmers are not constrained by the mechanics of a typewriter, different platform developers did not feel the need to fully model the typewriter's operation to represent end of line.  This resulted an interesting and fundamental difference in file data on Windows, Mac, and Linux when it comes to interpretation of the end of line (EOL) character, *i.e.* `\n`.  On Windows, EOL is represented as the sequence of carriage return followed by linefeed, so on Windows CRLF is embedded in text when an EOL is translated to `char` data.  On Mac systems before the OSX version was adopted, the EOL character embedded CR only.  On Linux systems and Mac OSX systems, the EOL character is LF only.

### Pangram

Word games are common in languages and one game asks a simple question of whether or not a phrase contains all symbols from a language.  This is known as a *pangram* derived from *pan* meaning all and *gram* meaning symbols.  The most common example of an English pangram is “The quick brown fox jumps over the lazy dog” which raises the question of how can we determine whether or not a phrase is a pangram.

The brute force pangram checking algorithm is the obvious one that most people adopt when posed the problem of a pangram.  It generally follows the approach:



```pseudocode
# alphabet : the alphabet to for all letters of
# phrase : the phrase to check to see if it is a pangram
# returns : true if phrase contains all letters in alphabet, otherwise, false
ispangram-bf(alphabet, phrase):

    1. Beginning with the alphabet letter 'A' up to 'Z'
       1.1 For each letter in the phrase
           1.1.1 If the alpha letter equals the phrase letter
               1.1.1.1 Found the alpha letter
               1.1.1.2 Can go to next alpha letter
       1.2 If alpha not found
           1.2.1 The phrase is not a pangram
           1.2.2 Stop return false
    2. 'A' - 'Z' must have been found to get here, so must be a pangram return true
```



While we are dealing with a rather narrow problem that will not generally be inefficient for a language like English with only 26 letters, we might want to use a similar strategy in other symbolic languages.  Consider if we want to play this same game with traditional Chinese which has well over 10,000 unique symbols.  Maybe instead the question becomes, "are all symbols in the language used in this document".  While the English pangram can use brute force because of the small amount of symbols in the language, the same algorithm becomes much slower in another application.  Can we write a more efficient algorithm for this process?

First consider, the claim that the brute force approach to pangram is slow.  Why is it slow and how can it be improved?  The inefficiency exists because the process starts over at the beginning of the phrase for each symbol.  In essence, the outer loop structures the question as look at every letter in phrase for 'A', then do the same for 'B', etc.  This means that in the worst case, it takes two entire passes through the phrase in the inner loop to determine that both 'A' and 'B' exist in the phrase.  For the entire alphabet, it would take 26 passes.  For English, again this is not so slow but for a language like traditional Chinese this process is considerably slower.  Is it possible to do this in only one pass through the phrase?  

It is possible if we reconsider the fundamental question we ask.  Instead of repeatedly asking each letter in the phrase whether that letter is an 'A' and then doing the same with each subsequent alphabet character, why not ask each letter in the phrase "what letter are you" and then track the answers somehow.  Perhaps we can use an array to represent the count of each letter we find in the phrase.  Consider the following alternative algorithm



```pseudocode
# alphabet : the alphabet to for all letters of
# phrase : the phrase to check to see if it is a pangram
# returns : true if phrase contains all letters in alphabet, otherwise, false
ispangram-opt(alphabet, phrase):

    1. Create an array of len(alphabet) integers indexed 0 to len(alphabet) - 1 
       with initial values of 0
       
    2. For each letter in the phrase
       2.1 positon = letter - alphabet[0]
       2.2 array[position] = array[position] + 1
       
    3. For each value in array
       3.1 if value is 0
           3.2 phrase is not a pangram, return false
    
    4. phrase is a pangram, return true
```

`ispangram-opt` loops through the phrase once.  It's weakness is it does loop through the alphabet once as well which is actually unnecessary with a slight optimization.  This approach is faster than the brute force technique initially proposed because it eliminates a significant number of operations contributed by using a nested loop structure.

There is one open question that arises from the `ispangram-opt` pseudocode above , specifically about how to compute `positon = letter - alphabet[0]` in a strongly typed language like Java.  Consider that `letter` and `alphabet[0]` are characters yet `position` is an integer, so the question is how to overcome Java's protection against performing math on a non-math type like a `char` and the answer lies in type casting.

### Casting Types

Recall that Java is a strongly typed language which means that all variables must be assigned a type which is done through variable declaration.  In fact, all values in Java have a type, this includes all literals.  A literal is a "hardcoded", constant value.  

For example, the symbols `0`, `1.0`, `false`,  `"Hello"`, and `null` are all literals and they all carry with them implicit types.  `0` or any counting number is generally interpreted to be an `int` type, `1.0` or any number containing a decimal is generally interpreted to be a `float` type, `false` and `true` are generally interpreted to be of `boolean` type, anything bounded by a double quotes, *e.g.* `"Hello"`, is generally interpreted as a `String` literal, and the `null` value is interpreted to be a reference type.

There are a variety of reasons to cast types and we can cast primitive values and reference types.  Later in the course we will see reference types change depending on their declarations and the relationships with other types.  Primitives might be cast because we have a`char` type but we need to cast it to an `int` to perform a math operation on the data or we might cast an `int` to a `char` after performing some transformation on the data and we need to use the value in string operations.  There are other cases to cast as well, but they are beyond the context of this discussion.
```java
String phrase =“the quick brown fox jumps over the lazy dog”;
char[] carr = phrase.toCharArray();
char ch = carr[0];  // ch is a copy of the first character in phrase
int ascii = (int) ch; // ascii is the integer code of ch
```

Recall that all values in memory are just numbers and the type acts as a filter that determines how the values are presented to the user.  In the above example, the `ascii` variable contains a copy of the value stored in `ch`; however, the `int` type associated with the `ascii` variable .

Suppose we want to find the position of a character in the alphabet.  The position of a letter in the alphabet is basically the distance of that letter from the letter 'a'.  In ASCII, the alphabet is logically ordered and every character has a numeric value, so it is just a matter of expressing to Java that your intent really is to perform math on letters even if it is a non-standard thing to do.

```java
char ch = carr[0];  // ch is a copy of the first character in phrase
int ascii = (int) ch; // ascii is the integer code of ch
int pos = ascii - (int)'a';
```

In the above example, type casting is used to clarify two things: that the conversion of `ch` from character type to `int` type is intentional and to cast the value of `a` into a type compatible with the subtraction operation and that this statement is intentional.

## Review

1. What is stored in the program block and what is stored in the data block?

2. The data block is divided into three segments. What are these three segments?

3. Define variable scope.

4. What are the three scoping levels associated with Java?

5. What is the lifespan of a variable and how does variable lifespan relate to variable scope?

6. What is the visibility of a variable and how does variable visibility relate to variable scope?

7. What is the lifespan and visibility of a global variable?

8. What is the lifespan and visibility of a local variable?

9. What is the lifespan and visibility of an instance variable?

10. How does the scope of a variable relate to the memory allocation of that variable?

11. How does the declaration of a variable relate to its scope?

12. Given the following code snippet, explain what is copied on line 2?

    ```Java
    int[] A = new int[10];
    int[] B = A;
    ```

13. What is an array?

14. What is a String?

15. What is ASCII?

16. What does it mean to cast from one type to another?

17. Why is it possible to cast from one type to another?

18. How do you cast from a character type to an integer type in Java? In other words, what is the syntax and give an example.

19. How do you cast from an integer type to a character type in Java? What is the syntax and give an example.

20. Explain what is meant by the term “deep copy”.

21. Explain what is meant by the term “shallow copy”.

22. Contrast the idea of a deep copy with a shallow copy.

23. Give an example in Java of a shallow copy.

24. Give an example in Java of a deep copy.

25. When a primitive value is copied, is that a deep copy or a shallow copy?

26. When a reference value is copied, is that a deep copy or a shallow copy?

27. If a deep copy of an array is made and a change is made to the copied array, how is the original array affected? Why?

28. If a shallow copy of an array is made and a change is made to the copied array, how is the original array affected? Why?

29. Illustrate the memory allocation Java would make for the following statement. Assume the statement appears inside a function. 

    ```Java
    int[][][] p = new int[4][3][2];
    ```

30. Illustrate the memory allocation Java would make for the following statement. Assume the statement appears inside a function. 

    ```Java
    int[][] q = new int[4][3];
    ```


## Vocabulary

memory

storage

primary memory

secondary memory



# 3 - Efficiency

## Counting Operations

The typical modern processor operates at 4 gigahertz (GHz).   The prefix "giga" means billion ($10^{9}$) and a hertz is an inverse second ($1/s$ or $s^{-1}$) which makes it a measure of time used to describe something in terms of the number of actions or operations per second.  In other words, a 4GHz processor operates at 4 billion ($4 \cdot 10^9$) basic operations per second.  4GHz may seem extremely fast and with the historical improvement of computer speeds according to Moore's Law, it may appear that if we wait a few years processing speeds will only get faster.

### Moore’s Law

In the 1960’s Gordon Moore, a founder of Intel, predicted based upon the historical rate of improvement of transistors in that era that the number of transistors in new computers would double roughly every two years [Moore 1965].

| ![973px-Moore's_Law_Transistor_Count_1970-2020](/home/jrt/gwu-new/course/cs1112/assets/973px-Moore's_Law_Transistor_Count_1970-2020.png) |
| :----------------------------------------------------------: |
| [By Max Roser, Hannah Ritchie](https://ourworldindata.org/uploads/2020/11/Transistor-Count-over-time.png), [CC BY 4.0](https://commons.wikimedia.org/w/index.php?curid=98219918) |

Moore's prediction held true due to the refinement of photolithography processes over decades and the resultant miniaturization of transistors that this process allowed; however, the lower bound for the scale of transistors using this processes has likely been surpassed already (around 2013) and the continued doubling of processor speeds within the same timescales is unlikely.  This did not mean the end of improvements in processing speed because instead of doubling transistors chip developers began doubling the number of "cores" (roughly equivalent to a processor) allowing for multiple processes to run simultaneously.  Doubling cores began in the early 2000s and processors with 24 to 32 cores are currently available to consumers.  Unfortunately, a conventional single process program must be entirely re-engineered for multicore architectures in order to take advantage of the resources of a multicore system.  As a result, we cannot simple count on hardware improvements to improve the efficiency of our applications.

## Efficiency

What is the meaning of efficiency?  It involves assessment of the utilization of a resource by a system where more efficient means less of the resource is used and it requires an objective metric and a way to measure the resource with respect to that metric.  Improving or optimizing attempts to increase the efficiency of a system.

In terms of computing, we are managing two basic resources: time and space.  Time in this context means computational time or the amount of processing time necessary for a program or algorithm to complete its computation and space in this context means the amount of memory used by a program.

To estimate efficiency, computer scientists build mathematical models of algorithms and their informed understanding of the system to model both the utilization of memory for a program and the amount of time necessary for the program to fully execute.  A mathematical function can abstractly and generally describe the efficiency of an algorithm which means a precise mathematical function is not necessary.  In other words, computer scientists classify an algorithm's performance based on the largest mathematical term that approximates its efficiency.

### Efficiency in Space

Space in this context means primary memory or RAM.  In general, every variable you allocate must exist somewhere in primary memory during the run-time of a program.  Efficiency in terms of space means how much memory an algorithm requires to execute.  Fortunately, the amount of primary memory available in personal computers has grown according to Moore's Law over the last 50 years, so the modern computer has massive amounts of memory compared to its counterpart in the late 1970's.

The size of primary memory in modern systems today is more than 16,000x times larger than it was in the late 1970’s.  In 1995 the cost of 1MB of memory was \$50; today 16GB of memory can be bought for about $50, and 16 GB is about 16,000x larger than 1MB.

With so much memory available, developers often overlook space efficiency especially in terms of applications running on personal computers; however, there are still a significant number of platforms where space efficiency is non-trivial and these are typically platforms with very small form factors.  Worrying about space has had a lower emphasis in modern computing, but we need to still need consider memory needs especially in emerging computing domains like wearables.

Throughout this course, we will look at the memory organization associated with Java code which will give us a view into the space costs of a program and we will realize a metric that we can use to generalize the amount of space used by a program; however, this will be a diminished focus in this class compared to efficiency in terms of time.

This material will generally summarize space complexity anticipating that the reader will further investigate analysis on their own and will occasionally discuss space complexity at depth for clarity.  Courses primarily focus on time complexity because there is no easy remedy for computational cost while the principles of space complexity are very easy to infer from time complexity, so our focus is typically on the more important one (time) with the assumption that students will ultimately recognize the other one (space).

### Efficiency in Time

Moore’s law held in terms of processing time until mid 2000’s but processors have not generally grown much beyond 4GHz since around 2004 and the processor speeds are unlikely to improve more than 2-4x beyond what we have today without a significant breakthrough in physics.  What are the physical limits on processing speed and why are processor speeds unlikely to continue to grow according to Moore's Law?

A wire can only be so small to reliably carry a signal.  The wires in a processor are on the order of nanometers and it is difficult to make them any smaller while still being reliable.  Reducing the scale of wires has increased the number of wires we can pack into the same area of a processor.  As the number of wires increases, so too does the power requirement for the system increases and with an increase in the amount of power comes a corresponding increase in waste heat.  Heat, specifically getting rid of it, is harder to manage as the size of wires gets smaller and more components are crammed onto the same size area in a processor.  There is a difficult balance between wire size, power needs, and waste heat that bounds the minimum size of a conventional processor; however, a significant advance in physics or materials might allow for more miniaturization and corresponding processor speed increases, but these advances are not on the immediate horizon.  However, it is one of the reasons industry continues to research semiconductors.

If processors have not been getting faster, how have computers been getting better since the 2000s. In other words, what was the big architectural change in processors that occurred in the 2000’s.

#### Multi-Core Processors

The first dual-core processor was released in 2001 [IBM Power4].  The underlying principal is that two or more processing units can be packaged into a single processor allowing for two processes to compute in parallel.  There is a distinction to be made here between multiple processor and multiple compute units which endures today and that is that a multi-core processors processing units are not independent processors.  Two independent processors in a computer is called a multi-processor system while a system with a single processor but with multiple computing units inside the processor is called a multi-core system.  The distinction is important because a multiple processor system can run multiple, completely independent programs (the number is dependent on the number of processors) simultaneously while a multi-core system allows multiple sub-processes belonging to the same program to be run simultaneously.  From an outside the application perspective, the multi-core system still acts like a single processor running a single program, but from an inside the application perspective, a program may be broken into different sub-processes that perform different roles.  To further make a distinction in the nomenclature between multi-process and multi-core systems we call the sub-processes in a multi-core system threads instead of processes to indicate that they are not fully independent processes.

This advancement allowed chip manufactures to continue to claim that they were doubling processing speed according to Moore's Law even without substantially increasing the processing speed of the processing unit by doubling the number of cores in a processor roughly every two years.  It is not uncommon to buy a processor with 8 to 16 cores today in the average laptop and some very high-end desktops are already shipping with 32 cores.  However, the multi-core processing model does not actually double processing speeds unless a program is specifically designed and well constructed for a multi-core environment.  The software designed in an introductory level computer science class is not designed for a multi-core system, so these programs are effectively capped to run at speeds associated with a computer designed in 2000.

#### The Graphics Revolution

The insights of parallel processing also resulted in a massive redevelopment of computer graphics technology.  Computer graphics had required more and more specialized processing to produce the computer graphics of the late 1990's and early 2000's; however, specialization was also limiting the future of computer graphics.  Computer graphics cards of this era were highly engineered and optimized to perform a very specific sequence of subtasks in order to perform one specific task, generating computer graphics.  This was an incredibly specific process necessary to sustain the growth of the still somewhat narrow computer graphics card market.  NVIDIA dominated the computer graphics market by the end of the 1990's and began to look at other products in the market to continue its growth via gaming support.

In the late 1990's and early 2000's, other computational capabilities were being recognized in the market, such as improving the physics of computer simulations.  Companies went so far as to produce expansion cards and libraries to calculate physics for games or other simulations [NovodeX AG] and NVIDIA acquired much of this intellectual property because it was a natural extension of their market.  NVIDIA faced an important decision as a result of these acquisitions: it could continue to build and maintain an extremely specialized, expensive, and limited graphics pipeline or it could reinvent the process by generalizing graphics as a computational linear algebra equation and designing a card on this new concept.

In 2009, NVIDIA released a completely new technology for computer graphics processing using massive parallel processing, i.e. NVIDIA’s CUDA model, to improve performance.  This processing model uses hundreds of very specialized processing units to compute the mathematics underlying computer graphics.  What NVIDIA recognized is, in the general sense, that computer graphics is essentially a set of linear algebra or mathematical equations.  The physics for more realistic physical behaviors is also a similar set of equations.  This means that NVIDIA simplified the process of graphics by creating cards that are very efficient at calculating large sets of equations simultaneously and added the capability of supporting physics simply by generalizing the cards.

NVIDIA introduced CUDA in 2009 and it took about a half a decade to refine the tools to expand accessibility beyond game developers and scientists; however, other applications quickly emerged where similar large mathematical problems are at the heart of the problem, namely crypto-mining and artificial intelligence.

Computer science has been studying and developing AI theory for more than seventy years but the computational needs far exceeded the computational capacity of systems before CUDA entered the market.  Developers have only recently been able to actually apply the theory of AI and take advantage of all of the years of research and development into the algorithms now that there is sufficient hardware to support it, hence the AI boom of the early 2020's.

Regardless of these computational advancements, we continue to be more concerned about the amount of time it takes for a program to execute. Why?  Because it is trivial to write a program that cannot be solved even on a modern computer if the algorithm is naively designed and the input is sufficiently large.  We can't always solve a complex problem by just waiting around for the technology to improve, we do have to plan and design our models in such a way that they are computationally solvable on current technology or we have to shelve that model until it is computationally feasible.

In light of this important objective, we need a measured way to evaluate efficiency objectively so that we can make decisions guided by reasoned, scientific principles and not by hunches and guesswork.

## How to measure efficiency?

At first consideration, it may seem reasonable to measure the run time of an application as a measure of the application's computational efficiency; however, run-time measurements have very limited use and have significant, hidden built-in cost.  Consider the following run-time data measured in seconds gathered from a variety of different platforms with applications using different data structures:

| **Operation**            | **2006 Mac-OSX** | **SUN Server Unix** | **2005 Win-XP** |
| ------------------------ | ---------------- | ------------------- | --------------- |
| **Insert (linked list)** | 3.412            | 2.969               | 3.562           |
| **Insert (array list)**  | 3.39             | 1.136               | 1.406           |
| **Search (linked list)** | 0.626            | 4.675               | 0.687           |
| **Search (array list)**  | 0.629            | 4.177               | 0.469           |
| **Get (linked list)**    | 0.432            | 3.479               | 0.719           |
| **Get (array list)**     | 0.0              | 0.002               | 0.0             |

http://www2.seas.gwu.edu/~jrt/cs1112/modules/module7/module7.html

While the above may initially seem reasonable consider that it tells us nothing about how these algorithms will perform given different data set, and without the data used for these tests, the tests themselves lose all context.  In other words, it does not address potential variations in performance subject to variations in the size of the input, so there is no predictive capacity with regard to input in these measurements.  It would be better if the analysis abstracts away the data so that the analysis can be performed without specific data yet takes into account the impact of data on the algorithm's performance.

The cost of measuring these algorithms is also significant and difficult to capture.  Consider that these algorithms could not be evaluated until they were completely implemented meaning that the analysis, design, implementation, testing, and debugging time for each algorithm has already been absorbed before it was possible to measure their performance.  As a results, the developmental investment is at least double (two data structures are being compared) yet we may only use one of the data structures in the final product.  Even if we need both data structures, we could not make any predictions about performance before completing the development, so all other development depending on these data structures must be on hold until this phase of development is complete.  A much more cost effective approach would allow measurement of the efficiency of these algorithms before any implementation begins.

### Computational Efficiency

Variations in computational performance exist because there are a significant differences at many levels in the computational model surrounding the average application.  It is quite rare for two computers to contain the same hardware and hardware manufactures optimize different aspects of their products, so performance will naturally vary when the same application is run on two different hardware configurations.  On top of the hardware, there are significant differences in operating systems (OS) design and implementation, such that even if the same hardware is used for two different OS's, performance will naturally vary when the same application is run on two different operating systems.  These same differences between language implementations also exist which contributing additional variation.  Additionally, the number and nature of programs running on a machine at a given time also affect the run-time of a program.  The run-time measurement of program is affected by a large number of outside variables that are difficult to capture, so while while run-time has some level of objectivity, the variables contributing performance differences are hard to control for and are difficult to isolate as contributing factors.

Remember that we want to measure the efficiency before even implementing the algorithm.  In other words, we want to use the power of prediction, the key capability of science, via well tested models to approximate the computational efficiency of an algorithm before investing implementation, testing, and debugging resources and time into the development cycle.  We need to know at concept time whether our algorithm is efficient enough or whether we need to investigate alternative algorithms.  In other words, is there a model that can estimate the computation efficiency of an algorithm without using real-time measures?  Additionally, a good model will abstract away hardware, operating system, and language specifics and will focus instead on the central property that really determines the performance of an algorithm, namely the size of the input?  In other words, is there an abstract but objective measure that allows us to predict and compare the efficiency of algorithms based on the size of the input?

### A Simple Computer

We can design a simple computer that only directly supports a few specific mathematical operations yet is still capable of performing a wide variety of math.  For example, if our simple computer supports four basic operations, `store`, `add`, `negate`, and `loop`, it can perform addition, subtraction, multiply, division, exponentials, and a host of other mathematical operations.

| The primitive computer has four basic operations:            |
| ------------------------------------------------------------ |
| 1. Store/Assign an integer value to a named location in memory, ex. `X = 0`, is expressed using the binary `=` operator where the variable on the left of the operator is assigned the value of the expression on the right of the operator. |
| 2. Add two integer operands is expressed using the binary `+` operator, ex. `A + B`. Given two operands, `A` and `B`, the add operation `+` returns the sum of the two operands. |
| 3. Negate one integer operand, `A`. That is, given `A`, the negate operation returns `-A` and is expressed using the unary `-` operator.  If the input `A` is positive the result will be negative and if the input `A` is negative the result will be positive. |
| 4. Loop using a basic conditional check. The condition is checked at the top of the loop. If the condition is true when the top of the loop is reached, the process will repeat the contents of the loop. If the condition is false when the top of the loop is reached, the process will skip the contents of the loop. The syntax necessary is roughly equivalent to the Java `while` loop syntax. |

From this set of simple operations, we can define a subtraction operation, `sub(A,B)`, because subtraction is a form of addition, `A + (-B)`.  We can also define a multiplication operation, `mul(A,B)`, because multiplication is repeated addition, `A+A+...+A` where the number of `A`'s added is equal to `B`.  From these basic concepts and mathematical axioms, we can build a rather capable computer; however, it raises the question of how efficient will each operation be.

Consider the following definitions:

```pseudocode
add(A,B):
    return A + B
    
sub(A,B):
    return A + (-B)

mul(A,B):
    result = 0
    i = 0
    while i < B
        result = result + 1
        i = i + 1
    return result
```

Is it possible to quantify the efficiency of `add(A,B)` in terms of the number of operations with respect to the size of the input.  In other words, does the number of operations in`add(A,B)` vary in any way given inputs of `add(1,2)` and `add(100,100)`.  The answer is no because in both cases, only a single line is operated on regardless of the size of the input values.

Conversely, consider whether or not `mul(A,B)` is more or less efficient than `sub(A,B)`?  While`sub(A,B)` consistently requires two operations on the primitive computer regardless of any outside variables, `mul(A,B)` is not so straightforward.  In fact, the efficiency of `mul(A,B)`, at least in terms of the algorithm presented above, varies with respect to the size of `B`, and in general, it varies with the size of the operation's input.  The follow-up question is how much does  `sub(A,B)` and`mul(A,B)` vary with respect to the size of the input so that we can compare these two algorithms.

Subtract never varies in the number of operations.  In fact, subtract only required two operations any time it is called; therefore the number of operations never vary with respect to the size of the input.  As a result, `sub(A,B)` can be described as having a constant number of operations.

In contrast, multiply is dependent on the size of the input values.  Why, because multiply involves iteration, in this form via a loop.  While the number of operations in the multiply loop is constant, the number of times the loop operates depends on the input.  For example, if `A=10` and `B=10`, the loop would iterate 10 times because it is dependent on the size of `B` based on the implementation above.  However, if `A=1000` and `B=1000`, the loop would iterate 1000 times because it is again dependent on the size of `B`.  The most important observation here is both that the number operations varies with the size of the input and the mathematical relationship that describes the relationship. 

In terms of the example, the relationship is linear between the size of the input and the number of operations.  For other algorithms, this relationship may be defined by another mathematical function.  Given an appropriate, comprehensive analysis, we do not even need to run the program to measure this, and in fact we can measure this efficiency from a diagram or pseudo-code.  Most importantly, a programmer can predict the performance of an algorithm before implementing it.

## Complexity Analysis

Our goal is to define a measure for **Algorithmic Complexity** and a basis for **Complexity Analysis**.  We can use the same measure to quantify an algorithm's performance in terms of its processing time, *i.e.* **Time Complexity**, and memory usage, *i.e.* **Space Complexity**.  In other words, we will need an objective measure for "how much the computation time of a program scales with respect to the size of the input," and it  also is a way to measure "how much our program's memory needs scale with input".  Note that our measure, critically, is always defined in terms of how many elements exist within the input set.

This metric is predictive, generalized, simple, and universal which allows us to compare the complexity of any two algorithms and make reasoned arguments based on the objective, clear relationships we can infer from the mathematical nature of quantitative analysis.  Additionally, as a predictive measure, we can now predict the efficiency of an algorithm from a rough outline of the operations which means we do not need to invest development time before we can determine whether a candidate algorithm is a good fit for our program requirements.  The metric is generalized, so we can compare the efficiency of two algorithms regardless of the architecture, operating system, language, or other applications that they may compete with or on.  Because our measure is sufficiently generalized, we can compare completely unrelated algorithms.  The simple, abstract measure ensures an algorithm's complexity is reduced to a single, easily communicable, easily interpretable measure such that any computer scientist will understand the same model which makes it universal, meaningful, and useful.  It is also quantitative which allows us to clearly differentiate and rank algorithmic performance. 

For every time complexity analysis, it is necessary to <u>always</u> address three components:

1. Must always define variables used in the analysis
2. Must make a claim/hypothesis in terms of Big O
3. Must defend that hypothesis with an analysis

In other words, an analysis is incomplete and generally meaningless without defining variables, defining a hypothesis, and defending the hypothesis.  Most students feel most comfortable with the above order and argument structure; however, a reasonable alternative is:

1. Define variables used in the analysis
2. Perform analysis
3. Summarize as Big O

What is meant by defining variables?  We will generally always express complexity analysis in terms of $n$ and we generically define $n$ to be “$n$ where $n$ is the size of the input”.  But what does this mean?

In many cases we are dealing with only a set of size $n$ like an array, so $n$ is an abstraction representing the number of elements in the array.  You may define $n$ to be “$n$ where $n$ is the size of the array” or “$n$ where $n$ is the number of elements in the set”, but the generic definition always works.  Some algorithms may have multiple or alternate inputs that are functions of $n$ which affect the time complexity and we will generally try to reduce these cases down to be in terms of $n$ to eliminate all other variables.  Ultimately, you will define $n$ as a set that encompasses all inputs, but it is reasonable for now to narrowly consider it as the largest variable input set like an array that is passed in or the tree to be operated on.

There is no single correct answer here on how to perform an analysis and we will spend much of the course using a variety of approaches ranging from raw math to diagrammatic approaches to pseudo-code in order to perform analysis.  The key takeaway is that this is an absolutely necessary step in both student and program development and it is the primary skill we are developing in this course.  Without performing analysis and supporting your argument you have not fulfilled the programming task.  This course is designed to force regular exercise on time complexity and this skill set will be assessed on virtually every meaningful evaluation.

### Big O

While analyses may take on a variety of approaches and forms, efficiency claims are reduced to a single measure, Big O Notation.  Big O Notation follows the form – O(<function in terms of n>). For example, these are all valid Big O arguments:

|                          |                                                              |                                                              |
| ------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| Polynomial (P) Time      | $O(c)$ or $O(1)$<br />$O(\log_{2}n)$<br />$O(n)$<br />$O(n\log_{2}n)$<br />$O(n^{2})$<br />$O(n^{3})$<br />$O(n^{4})$ | Constant Time<br />Logarithmic Time<br />Linear Time<br />Log-linear Time<br />Quadratic Time<br />Cubic Time<br />Quartic Time |
| Non-Polynomial (NP) Time | $O(2^{n})$<br />$O(n!)$                                      | Exponential Time<br />Factorial Time                         |

Of course there are more. Any mathematical function can be expressed in Big O notation, but there are some that are more common than others. Regardless, there are also some important, common features for Big O notation.

Big O allows us to drop all term coefficients. For example if we were to estimate a function with the following function $f(n) = an^{2}$ we would drop the coefficient $a$ and generalize the function in Big O as $O(n^{2})$. The reason behind dropping coefficients is that it can be difficult to accurately calculate coefficients from code and for large inputs the variable term itself dominates the equation.  In other words, for really large numbers of $n$, the difference between $f(n) = 2n$ and $g(n) = 3n$ is much less relevant than the difference between how the order of the largest variable term, such as comparing $f(n)$ with respect to $h(n) = n^2$, would affect overall efficiency.  On the scale of large numbers $f(n)$ and $g(n)$ take essentially the same amount of time while $h(n)$ will take considerably longer.

Big O also focuses only on the largest term and allows smaller terms to be dropped. For example if we were to estimate a function with the following function $f(n) = n^3+n^2+n$, we would drop both the $n^2$ and $n$ terms and generalize the function in Big O as $O(n^3)$. We do this because the growth of the function will be dominated by the largest term and the smaller terms have a relatively negligible effect on the growth of the function for large inputs.

There are other forms of similar analyses such as Big Omega and Big Theta, but it is most important to introduce Big O to students in this course.

For a small input, most polynomial algorithms will solve in a reasonable amount of time, however, non-polynomial algorithms with even modest sized inputs may not solve.  The following plots are limited in the scale that can be shown, but they endeavor to give an idea of the differences between algorithms of different Big O classifications.  Remember that in terms of efficiency, having a small y-value is better or more efficient.  This translates to any line below another line is a more efficient algorithm.

The first plot below illustrates the performance of functions for small inputs.  Note that the quartic $O(n^4)$ algorithm is "above" or "to the left" of the exponential $O(2^n)$ on this plot; however, once they cross at around $n=15$, the quartic algorithm will always be below the exponential over the rest of the domain.  This same characteristic will arise for all polynomials cubic $n^3$ or greater.  For example, the cubic and exponential cross with the purple line $O(n^3)$ crossing the pink line $O(2^n)$ and a rapid divergence after crossing.  However, this plot is far from comprehensive and may be a bit misleading because the scale of $x$ is relatively small.

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXd61NhcdlXN5Gq-CHPA5F_lmDdHDxBMpmCsSTfdlo0O8rqgI9z9uYZcFSm6sIyHMyXWZ3Scu2k-HYhGWm4hOPrsY5BM_i-pFGzB1BqAvtYuOLThkvT-mdv2cBc4uyQ87TsA9N2LHA?key=Dtv4rTA9pOEP4S9I_P3BlnzE)

The second plot attempts to illustrate the functions for what may be considered an extremely small set of 10000 elements.  Note that it is difficult to discern much other than logarithmic is extremely efficient while everything "above" $O(n^2)$ is hard to interpret.

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfD_1_IAOqf7CX61Axaf0z-bO4HhPXh69HzEffEx_Ct118ljEiRXPrHTig-T1mNRyD41Ny1UnMPxWvx86vPXcxuRBKgkkRqQDUkBwWmo_HUVkblpc1hyIK7dUEeqZ_-BGclsiiHLw?key=Dtv4rTA9pOEP4S9I_P3BlnzE)

This third plot addresses the weaknesses of the second plot by using a logarithmic y-axis.  Note that the growth of y-axis is not constant but each step is an order of magnitude greater which compresses the data in the upward $y$ scale and allows for extremely large numbers to be represented.  One artifact of this is that all of the polynomial functions have a pronounced turn on the plot and appear to flatten which could falsely be interpreted as an asymptotic behavior.  What is evident from the plot is that the non-polynomials even for very small values of $n$ are unsolvable because they are "off the chart" and that there is a clear hierarchy of polynomials indicating which algorithms will perform better than others according to their Big O classification.  

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdkJTP9OPO2PAtNXKS10vanznfwTW4VEOUwo-jCgeXAUQmS3ZdK4Y0VyONngxHBelrwarxmhE9eGwZx5g-JS8_PX41iJZAjHF9rUVYizJG5xzknX1jOgEJwzbjiFXL99scDYYNg?key=Dtv4rTA9pOEP4S9I_P3BlnzE)

Big O will be the most important concept of this course and it will be a recurring theme as a result.  It will feature prominently in every discussion involving algorithms. 

### Other Complexity Analyses

The field of algorithm quantitative analysis has more measures beyond just Big O.  Two similar measures are Big Theta, $\Theta$, and Bit Omega, $\Omega$, which are expressed in the same ways as Big O using similar analytical techniques but with different analytical envelopes.  Big O is strictly limited to a general worst-case envelope that every function shares which is what makes it applicable to all algorithms while these others are applicable to more specialized cases such as Big Theta only operating on algorithms where the best-case and worst-case match.  In other words, these measures can be more nuanced and actually give better estimates of the performance for specific classifications of algorithms.

Above, we declared that the material will focus more on time complexity at the cost of some discussion of space complexity for the sake of teaching the most relevant material, and so here we too will narrow our focus on time complexity to Big O in the remainder of the materials for the same reasons.  We memorialize these alternative measures here to make the student aware that there are other more sophisticated measures of algorithmic time complexity, but in this course, we will perform algorithm time complexity analysis exclusively using Big O evaluations and will leave further definition, instruction, and discussion of these complexity analyses to the domain of a discrete structures or a strictly focused algorithm course.  

We do encourage students to further explore Big Theta and Big Omega analysis, but they will remain beyond the scope of this course as we will wish to focus on one single metric so that there is no confusion among students at this level and because Big O analysis is generally all the industry demands.  We wish to encourage students to explore Big Theta and Big Omega more as having these skills can distinguish you from the rest of the labor market or better equip you for analytical/optimization work in programming, but this will be the extent of addressing the metrics in this material for the aforementioned reasons.

## Review

1. What variables affect the execution time of a program?
2. Why do we use algorithmic time complexity to measure a program’s efficiency rather than execution time?
3. What are the benefits of using an abstract measure like algorithmic time complexity over a rigidly specific measure like execution time?
4. Why can we ignore coefficients and smaller terms in an algorithmic time complexity analysis?
5. What is Big O notation?
6. Why does the growth rate of Big O meaningfully capture the efficiency of a program over its entire input?
7. Why do we generalize time complexity analysis to an evaluation in terms of “$n$ where $n$ is the size of the input”?
8. Why does time complexity analysis capture information about arbitrarily large data sets that cannot be captured by measurement of execution time?
9. Why does time complexity analysis allow us to measure efficiency of pseudo-code?
10. How is algorithmic time complexity a predictive measurement? 
11. Why is any real-time measure a reactive measurement? 
12. Why is it much more efficient in the design space to use algorithmic time complexity rather than real-time measurement?
13. Why would a real-time measurement be almost useless if the size of the input was significantly changed.
14. Why are the efficiencies generally grouped into polynomial (P) time and non-polynomial (NP) time?
15. In the plots, an input of $n=10000$ is claimed to be small.  What would be considered large?  Justify.
16. The chapter suggest that the same approaches can be used for space complexity.  Why is space complexity of diminished concern for the average application?  What types of applications would require optimization of space complexity and why?

<!-- Memory is ignored in the Simple Computer Example. -->

# 4 - Recursion

In programming we are typically operating on sets. In order to support more effective coding we typically rely on structures that allow us to repeat a number of operations on each element of a set so that we can write compact and easily adaptable code. This follows from the reasoning that if we are operating on a set, we are likely performing the same operations on each member of the set, so the code is highly redundant and might be modeled in a way that allows a small sequence of code to be repeated however many times there are elements in the set. In an introductory programming class, we introduce the `for` loop control element for this purpose and we reuse it extensively; however, this is not the only means of repeating code. In this class, we will generally refer to repeating a set of code as **iteration** and the design model of using a `for` loop as the basis of repeating in an algorithm as an **iterative** design, technique, or approach.

An alternative approach for the design of an algorithm is to repeat code by calling a function repeatedly. This requires close attention to the design of the function as a poor design with an unreachable return may result in the function calling itself until the system runs out of memory which would result in a program crash at best and a system crash at worse. In this class, we will exclusively refer to repeating a set of code using a function as **recursion** and the design model of using a function as the basis of repeating in an algorithm as a **recursive** design, technique, or approach.

Let’s discuss recursion in terms of some basic mathematical functions such as power, factorial, and the Fibonacci sequence.

### Power

Power is a common alternative name for an exponential operation.  For the sake of this discussion, assume power is defined for zero and positive exponents only.  In other words, the power function defined in this section is discrete and computes exponentials for only non-negative integer exponents and non-zero bases.

Define power as $f(a, b)$ where $a$ is the base and $b$ is the exponent. Power is often expressed using the notation $f(a, b) = a^{b}$; however, this notation masks that the power operation is really defined as a repeated multiplication per Definitions 1 and 2.

**Definition 1** : 
$$
f(a, b) = 1 × a_{1} × \cdots × a_{b}
$$
**Definition 2** *(As a piecewise formula)* : 
$$
f(a,b)=
\begin{cases} 
      1 & b = 0 \\
      a \cdot f(a,b-1) & b > 0 
   \end{cases}
$$
We may use different symbols to make the operation more descriptive, *e.g.* `power(base, exp)`, rather than using the symbolic representation of math, but doing so does not change the definition. Regardless of how the power operation is represented, it is a function with two parameters where the base is typically the first parameter and the exponent is typically the second parameter. For simplicity, we are defining power as discrete, *i.e.* non-negative, integer exponents and integer, non-zero bases. While limited, it is an incredibly useful version of power because we often need exponentials in the integer domain.

#### Power Iteratively

Let’s implement using an iterative approach, *i.e.* using Definition 1. What does an implementation look like?

```pseudocode
power(b, e) → integer >= 1 where b and e are integers and b is >= 1 and e >= 0 :
	
	result = 1

	for i = 1 to e : 
		result = result * b

	return result		
```

Consider the efficiency of the iterative power implementation.  The number of operations is dependent on the number of times the loop iterates.  The number of loop iterations is determined by the exponent input `e`.  The mathematical relationship between the number of loop iterations and `e` is linear.  In other words, if  `e` increases by one, the number of overall operations increases according to a linear relationship.  `b` is a constant in this analysis and can be generally dismissed with respect to its affect on time complexity.  Therefore the overall time complexity is $O(n)$ or linear time complexity.

#### Power Recursively

By Definition 2, the piecewise mathematical expression defines a clear model for how to implement this recursively:
$$
f(a,b)=\begin{cases}       
	1 & b = 0 \\      
	a \cdot f(a,b-1) & b > 0    
\end{cases}
$$
The two independent pieces or cases of the piecewise formula need to be implemented.  The first case represents a fundamental basis of the problem.  In the case of power, this is the axiom that for all natural number bases, a zero exponent produces a result of 1, i.e. $a^{0}=1$ for all $a$ in the domain of natural numbers.  This may also be called a "base case".

```pseudocode
power(b, e) → integer >= 1 where b and e are integers and b is >= 1 and e >= 0 :
	if( e == 0 ) :
		return 1

	return b * power(b, e - 1);
```

Consider the efficiency of the recursive power implementation.  Every time that `power` is called, `power` subtracts 1 from `e`.  Assuming `e` is positive (a fundamental design assumption), `e` takes one step closer to the base case.  The total number of calls to `power` is determined by the initial value of the exponent $e_i$ on the first external call to `power` which will result in $i$ internal calls to `power`.  This means there is a linear relationship between the input `e` and the total number of calls to `power`.  Again, the base `b` is effectively constant and does not affect the time complexity, so it is ignored.  The linear relationship between the size of input `e` and the number time `power` calls itself means that this implementation is $O(n)$ and has linear time complexity.

### Recursive Design

All recursive functions must include two control cases

1. Base Case
2. Recursive Case

The base case represents an immutable fundamental solution to one of the smallest versions of this problem.

The recursive case represents reducing the problem into constituent problems, part of which is a self-similar subproblem, *i.e.* it has different, smaller parameters and is closer to a base case but it is fundamentally structured as the same type of problem. We generally control a recursive algorithm by parameter reduction when making a recursive function call which leads subsequent recursive function calls towards a base case.

By viewing recursive problems as composed of self-similar subproblems, we can properly structure our algorithms in a reductive manner. In other words, we typically want our design to count down towards base cases designed around when one or more parameters approach or reach zero. Good recursive designs generally approach zero or one because it is hard to miss and clearly associates base cases with the smallest indivisible subproblem. When a recursive method is structured to count up to a target number, it requires additional parameters and every parameter increases the memory usage of the recursive function.

Recall that all local variables use stack memory and all parameters are local variables, so adding an additional parameter increases the amount of memory required to support this function. There is a finite amount of memory in a computer, so increasing the number of local variables decreases the number of times a recursive function can be called compared to a function with less local variables. Since memory is finite, the stack, which provides memory for local variables, will eventually run out of space if functions are repeatedly called without returning. Running out of memory is typically called a Stack Overflow exception and leads to a crash of the program. In modern systems, there is so much stack memory, it is difficult to run out of memory unless your recursive method is improperly structured and cannot return properly or if the input size is exceptionally large.

## Factorial

Assume factorial is defined for positive integers only. In other words, factorial is a discrete function for positive inputs only.  The definition involves repeated multiplication as indicated in Definitions 3 and 4.

**Definition 3** : 
$$
f(x) = 1 × 2 × \cdots × (x-1) × x
$$
**Definition 4** *(As a piecewise formula)* : 
$$
f(x)=
\begin{cases} 
      1 & x = 1 \\
      x \cdot f(x-1) & x > 1 
   \end{cases}
$$

#### 

Factorial is often expressed symbolically using the notation $f(x) = x!$; however, this notation is problematic in programming languages as it is odd and unique syntax for an operator to follow an operand in most programming languages.  Instead factorial is generally only accessible via a function with a typical declaration being`int factorial( int x )`.

#### Factorial Iteratively

The iterative implementation of factorial follows the model prescribed by Definition 3.

```pseudocode
factorial(x) → integer > 0 where x is an integer and x is > 0 :
	fx = 1

	for i = 2 to x  
		fx = fx ∙ i 

	return fx
```

Just as with the `power` iterative implementation, the number of operations for the `factorial` function scales with the loop and the number of operations is dependent upon the input `x`.  The relationship between the number of loop iterations and the input `x` is linear which means that this iterative factorial implementation is $O(n)$ or linear time complexity.    

#### Factorial Recursively

By Definition 4, the piecewise model for factorial suggests the recursive implementation of `factorial` the same way Definition 2 suggests the recursive implementation of `power`.
$$
f(x)=
\begin{cases} 
      1 & x = 1 \\
      x \cdot f(x-1) & x > 1 
   \end{cases}
$$
Again, factorial has a single base case defining the basis of the factorial definition and the ultimate exit condition for the operation.  Because the piecewise mathematical definition of factorial is structurally similar to the piecewise mathematical definition of power, the implementation of both is almost identical with the exception of literals and operators. 

```pseudocode
factorial(x) → integer > 0 where x is an integer and x is > 0 :
	if x = 1 : 
		return 1

	return x ∙ factorial(x-1)
```

For the same reasons we conclude that the efficiency of recursive `power` is $O(n)$, we generally estimate the `factorial` to have linear time complexity.  Just as in `power`, every time that `factorial` is called, `factorial` subtracts 1 from `x` and `x` takes one step closer to converging on the base case.

## Fibonacci Sequence

The Fibonacci sequence is defined by the series 0, 1, 1, 2, 3, 5, 8, 13, 21, 34, 55, 89, 144, …

In other words the $i$-th Fibonacci Number is the number in the $i$-th position of the Fibonacci Sequence. By definition, the Fibonacci Sequence is only defined for non-negative integers,  begins with $f(0)=0$ and $f(1)=1$, and subsequent Fibonacci Numbers are defined as the sum of the two preceding Fibonacci Numbers. Here is the Fibonacci sequence with corresponding indices:

| *x*    | 0    | 1    | 2    | 3    | 4    | 5    | 6    | 7    | 8    | 9    | 10   | 11   | 12   | ...  |
| ------ | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- |
| *f(x)* | 0    | 1    | 1    | 2    | 3    | 5    | 8    | 13   | 21   | 34   | 55   | 89   | 144  | ...  |

**Definition 5** *(As a piecewise formula)* : 
$$
f(x)=
\begin{cases} 
      0 & x = 0 \\
      1 & x = 1 \\
      f(x-1) + f(x-2) & x > 1 
   \end{cases}
$$

#### Fibonacci Iteratively

While we do not have a simple, clean mathematical formula representing the iterative form for computing a Fibonacci Number, we can implement it using a loop:

```pseudocode
fibonacci(x) → integer >= 0 where x is an integer and x is >= 0 :
	fx-2 = 0
	fx-1 = 1
	fx = fx-2

	for i = 1 to x:
		fx = fx-1 + fx-2 
		fx-2 = fx-1    
		fx-1 = fx

	return fx
```

Comparing the above implementation with iterative power or factorial, iterative Fibonacci involves at least 5 variables and appears to generally be a more complex implementation; but, how does this affect its time complexity.  If we were trying to compute an accurate measure of efficiency, we might quantify the above implementation as $4n + 4$.  The constant term captures the first three statements and the `return` statement while the coefficient captures the top of the `for` loop and all of the statements in the loop itself.  Keep in mind that this is an estimate in itself as there are aspects of this code that will be hidden by any compiler hence why we use an estimation methodology that is elastic and does not pretend to be too accurate.  If we ignore coefficients and constants, we conclude that the efficiency of the implementation is linear time complexity and has a Big O of $O(n)$.   

#### Fibonacci Recursively

Definition 5 prescribes the recursive model for Fibonacci: 
$$
f(x)=
\begin{cases} 
      0 & x = 0 \\
      1 & x = 1 \\
      f(x-1) + f(x-2) & x > 1 
   \end{cases}
$$
This definition is so far unique as it prescribes two base cases and a more complex recursive case when compared with Definition 2 for power or Definition 4 for factorial; however, the implementation is still rather simple.

```		pseudocode
fibonacci(x) → integer >= 0 where x is an integer and x is >= 0 :
	if x = 0 : 
		return 0
    if x = 1 : 
		return 1

	return fibonacci(x-1) + fibonacci(x-2)
```

Again, consider the efficiency of Fibonacci.  While most of the design elements are familiar, a novel question about how to estimate the efficiency of the recursive case needs to be considered.  

If the recursive case is reached in Fibonacci, how many function calls result? The answer is two. This means for each call to recursive Fibonacci, the algorithm potentially generates two additional recursive calls. A diagram may help illustrate the grown of function calls in recursive Fibonacci:

| The initial call to recursive Fibonacci with say an input of 5, will require that it solves two smaller Fibonacci problems, *i.e.* $f(4)$ and $f(3)$. Given this pattern, for each call we expect two additional calls. | ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfJ4Sw3LSwrGTOaCkW2uYOhkQvSqMXcoGxv0uf_l11KsNiW8mVKQV5kxBbCbtqQH-5itkt0d41OLcu7N-FdjBV8k-VzKQD2-KtxGrc36n5b5-x9SXGJPKhUyfzSvFzwNLrYM1bqkRNFixEFZr5C6BE?key=51ZvvWJZT0VLJN68FZq3eOhR) |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| Recursive Fibonacci will actually start to solve itself by repeatedly calling down until it has solved the left most $f(2)$ subproblem in an effort to solve the left most $f(3)$ subproblem in an effort to solve the left hand $f(4)$ subproblem. Once it has solved the left hand $f(2)$ subproblem, it can very easily solve the left hand $f(3)$ subproblem because the solution involves the just solved $f(2)$ solution and a base case $f(1)$ solution. After the left most $f(3)$ subproblem is solved, Fibonacci will solve the left most $f(4)$ subproblem. | ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfOs6RIIH5Whpv0u0T6VYqnGkc3611JtRhoqXsfJbZJNx2ctnzvjE0Oc0Hm5p_jqdo8tK4RpuE60Gy9KMT5Zl7mElJKsM762zcph2nxDIEbuxb2ZKpVaFeGc3Dcl3yRT-hefCGsz8rL-ZGTNHiiUS0?key=51ZvvWJZT0VLJN68FZq3eOhR) |
| To complete computing $f(4)$ after solving the $f(3)$ calculation, *i.e.* the left most subtree, recursive Fibonacci then needs to solve the $f(2)$ problem again. | ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXe2cNmYML5kRFe6w2YETsblbP5plbkf1ZToklbKHvcm-sLSDNDiI7GlXBSmro3G5haFKaQOZVLSVwwjzjsiJ7c58XD2MXQIEUjYGXKF9U-oIZG6DTO_9jZlbkEHm2X2_qtk-F5BUcsFTkSkGtG4tSc?key=51ZvvWJZT0VLJN68FZq3eOhR) |
| After solving the entire $f(4)$ subproblem, *i.e.* the entire left subtree, recursive Fibonacci must solve the entire $f(3)$ subproblem, *i.e.* the entire right subtree, again. | ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcC7U3q4ytQN9yvog03RbdU8vQ9ax2wWTBS0f7FajzrNSTqgLlzsPA2q3-RnHezxBv2tMs8nj-MMq-Eqz3e8MrJCYmTIUI31Ob5OYdclLbV-DRTfKZ---G_yDO-ZcO23P0Zc5Tw06WIMxfR1Yv_tQM?key=51ZvvWJZT0VLJN68FZq3eOhR) |

Early in the course, we discovered that the number of nodes in a structure like this is at most $2^{n}$ where $n$ is the number of nodes or the size of the input under certain conditions that we will discuss later when we focus specifically on trees. It does not matter that some of the subtrees are incomplete. Imagine the growth of the tree, *i.e.* the number of additional nodes that would be appended, if we added one more level above to solve $f(6)$. The size of the tree would effectively double. In other words, recursive Fibonacci has exponential time complexity or it is classified as $O(2^{n})$.  This time complexity is also evident from the perspective offered by the impllementation

```pseudocode
fibonacci(x) → integer >= 0 where x is an integer and x is >= 0 :
	if x = 0 : 
		return 0
    if x = 1 : 
		return 1

	return fibonacci(x-1) + fibonacci(x-2)
```

Note that one call to the function generally produces two calls, so the initial call to Fibonacci results in two more calls.  However, these two calls in turn produce four calls which produce eight calls and so forth.  So what is the relationship between the size of the input $n$ (`x` in the pseudocode) and the number of calls.  Consider the sequence of calls described :
$$
1+2+4+8+...
$$
What is the formula that describes the number of calls:
$$
2^{0} + 2^{1} + 2^{2} + 2^{3} + ...
$$
While the formula does not precisely model the number of calls, it is a reasonable approximation for the number of calls.  If we assume a full tree is generated, the formula becomes:
$$
2^{0} + 2^{1} + 2^{2} + 2^{3} + ... + 2^{n-1} + 2^{n}
$$
This sum is equal to:
$$
2^{n+1}-1
$$
Since we are performing an efficiency analysis, we can drop constants in the equation and summarize this as $O(2^{n})$ or exponential time complexity.

## Towers of Hanoi

Towers of Hanoi is based on a legend involving Buddhist monks moving large, circular stone discs from one peg to another.  The problem is to move a stack of discs from one peg to another by moving only a single disc at a time.  

|         |                   One Disc Towers of Hanoi                   |
| :-----: | :----------------------------------------------------------: |
| initial | <img src="/home/jrt/gwu-new/course/cs1112/assets/toh-1disc-initiala.png" style="zoom:50%;" /> |
| move 1  | <img src="/home/jrt/gwu-new/course/cs1112/assets/toh-1disc-move1.png" style="zoom:50%;" /> |

The single disc problem is trivial and requires only a single move to complete the puzzle.

Each disc must have a different diameter than all other discs, and for a multiple disc problem, no disc that is larger than another disc can be stacked on top of a smaller disc by rule.  Therefore, to move the two discs to another post and restack them in the original order, it takes three moves.

|         |                   Two Disc Towers of Hanoi                   |
| :-----: | :----------------------------------------------------------: |
| initial | <img src="/home/jrt/gwu-new/course/cs1112/assets/toh-2disc-initial.png" style="zoom:50%;" /> |
| move 1  | <img src="/home/jrt/gwu-new/course/cs1112/assets/toh-2disc-move1.png" style="zoom:50%;" /> |
| move 2  | <img src="/home/jrt/gwu-new/course/cs1112/assets/toh-2disc-move2.png" style="zoom:50%;" /> |
| move 3  | <img src="/home/jrt/gwu-new/course/cs1112/assets/toh-2disc-move3.png" style="zoom:50%;" /> |

The three disc tower increases the complexity of movement.

|         |                  Three Disc Towers of Hanoi                  |
| :-----: | :----------------------------------------------------------: |
| initial | <img src="/home/jrt/gwu-new/course/cs1112/assets/toh-3disc-initial.png" style="zoom:50%;" /> |
| move 1  | <img src="/home/jrt/gwu-new/course/cs1112/assets/toh-3disc-move1.png" style="zoom:50%;" /> |
| move 2  | <img src="/home/jrt/gwu-new/course/cs1112/assets/toh-3disc-move2.png" style="zoom:50%;" /> |
| move 3  | <img src="/home/jrt/gwu-new/course/cs1112/assets/toh-3disc-move3.png" style="zoom:50%;" /> |
| move 4  | <img src="/home/jrt/gwu-new/course/cs1112/assets/toh-3disc-move4.png" style="zoom:50%;" /> |
| move 5  | <img src="/home/jrt/gwu-new/course/cs1112/assets/toh-3disc-move5.png" style="zoom:50%;" /> |
| move 6  | <img src="/home/jrt/gwu-new/course/cs1112/assets/toh-3disc-move6.png" style="zoom:50%;" /> |
| move 7  | <img src="/home/jrt/gwu-new/course/cs1112/assets/toh-3disc-move7.png" style="zoom:50%;" /> |

However, a key insight is that the three-disc Towers of Hanoi is unstacking a two-disc tower, moving one disc, restacking a two-disc tower.  In other words, the solution for the three-disc tower requires solving a two-disc tower twice which suggests that we can approach this problem using recursion.

### Algorithmic Time Complexity

How many moves are necessary to solve Towers of Hanoi for four discs or the general $n$-disc problem?

<img src="/home/jrt/gwu-new/course/cs1112/assets/toh-4disc-initial.png" style="zoom:50%;" />

Each single action, a discrete move, is always the same, *i.e.* move a single disc.  For a stack of discs, we are just repeating the move single disc action a number of times and to find the time complexity it is just a matter of estimating how many move disc actions are necessary to solve for a tower of $n$-discs where the number of discs, $n$, is the "size of the input".  

Further, consider that the three disc problem must solve the two disc problem twice.  Once the two discs above the third disc are stacked elsewhere, moving the bottom-most disc of the current problem is just a single move, but then the two disc problem must be solved again to replace the discs above on top of the bottom-most disc.

|                                         |                                                              |
| :-------------------------------------: | :----------------------------------------------------------: |
|    solve 2 disc tower to free $d_3$     | <img src="/home/jrt/gwu-new/course/cs1112/assets/toh-3disc-2disc1.png" style="zoom:50%;" /> |
|               move $d_3$                | <img src="/home/jrt/gwu-new/course/cs1112/assets/toh-3disc-move4.png" style="zoom:50%;" /> |
| solve 2 disc tower to complete solution | <img src="/home/jrt/gwu-new/course/cs1112/assets/toh-3disc-2disc2.png" style="zoom:50%;" /> |

Therefore the solution to the current problem of $n$-discs is just a 1 disc problem in between solving the $n$-1 disc problem twice.  The $n$-1 disc problem is just solving a 1 disc problem in between solving the $n$-2 disc problem twice, and so forth.  Based upon our understanding of recursion, this is clearly a problem that can be decomposed into self-similar subproblems with a base case of moving a single disc.

To estimate time complexity, we can refer back to what we learned from recursive Fibonacci where a call to Fibonacci resulted in two additional calls to Fibonacci which produced a tree that we agreed had approximately an exponential number of elements with respect to the size of the input.  We see this same pattern here in Towers of Hanoi as every time we add a disc, it results in having to solve two smaller $n-1$ Towers of Hanoi problems which in turn results in solving four smaller $n-2$ Towers of Hanoi problems and so forth.  We can summarize this with the piecewise recursive equation:
$$
f(d)=\begin{cases}
    1 & d = 1 \\
    f(d-1) + 1 + f(d-1) & d > 1
  \end{cases}
$$
We can also determine the total of moves from an inductive approach.  Given the following pattern:

1 disc $\rarr$ 1 move

2 disc $\rarr$ 1+1+1 = 3 moves

3 disc $\rarr$ 3 + 1 + 3 = 7 moves

Based on the progression, the 4-th element will be:

4 disc $\rarr$ 7 + 1 + 7 moves

But what is the $i$-th?

The insight comes from understanding that the right side of the equation is related to the left by powers of 2.  In other words:

$i$ disc =  $2^{i-1}-1 + 1 + 2^{i-1}-1$ moves

$i$ disc =  $2 \cdot 2^{i-1}-1 + 1-1$ moves

$i$ disc =  $2^{i}-1$ moves

In other words, the efficiency of Towers of Hanoi is $O(2^{n})$ where $n$ is the number of discs.



## Manhattan Problem

The Manhattan problem asks the question of “how many paths of shortest length” exist between two points on a grid. Distance on a grid is measured by the Manhattan distance which is constrained because travel can only occur on the grid lines themselves. While the shortest path between two points in Cartesian space is a straight line, the shortest path on the grid is the number of blocks that must be traversed in order to reach the destination.

<img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXddodH46U7hxkfhCE4cY8GgWd2CgwSDZqTuDkg1cwMvqHuh8QSR4kxRrXnKkHG3LWeHfiW9wfGDRffUNW3WtVmtIMSYWXjDLiAoaz04jMo7JbCljOkK7KgTJCBoNSmYiib7mLw3FZIJgfBhrQwfz3k?key=51ZvvWJZT0VLJN68FZq3eOhR" alt="img" style="zoom:50%;" />

In the above example, there are 5 blocks between 55th and 50th and there are 3 blocks between Park and 2nd and as a result the shortest path is a total of 8 blocks (5+3). However, this is only part of the problem because the actual question we are investigating is how many paths of length 8 exist between 55th and Park and 50th and 2nd. Additionally, we want to generalize our approach to be able to answer this question on an arbitrary grid, and while we could perform some brute force iterative approach, we really want to see if there is a simple and error proof way of answering this question.

### Graphical Analysis

The simplest grid is a single block:

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXciozxdf9g2sdyGdP_byOnO04h-Yar7LQlgKbD5hdVr50BLn_0gRV-949EwLoiIbCNcSOuei2fQgKO7Txw1ZMtilSXlFCU6ZnBZ4U3WKBr510l5_ZpeQ2KWHaHuguo4MINeBBJ7K9OFkJK1WkLzOW0?key=51ZvvWJZT0VLJN68FZq3eOhR)

All other versions of this problem are just more extensions of this problem. If we can develop a generalized algorithm to solve this version of the problem, we can solve any version of this problem.

From a human perception and reasoning standpoint, we are inclined to quickly conclude that there are two paths from the starting position in the top-left corner to the goal in the bottom-right corner.

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXd07aOvw6xCLGvFkmVVJO3IH_4QBrGcozr5qLGd7aXtcBUwCzzku_jU2Kdq2z5344kgYCdrZ2TNmRt6AxgZdRbMjjtloJ346f2Q-VHx_ltvhtqjwYgOD7Vndj1jvqEICQmEZzraTPIfmOctA93DfG8?key=51ZvvWJZT0VLJN68FZq3eOhR)

However, this overlooks how this problem can be broken down further into relevant constituents. There are really three different steps to individually consider:

| If the starting position for a path is on the bottom edge, there is only one path to the goal | If the starting position for a path is on the right edge, there is only one path to the goal | If the starting position for a path is at an intersection there are multiple paths to the goal. Each path leads to a self-similar subproblem |
| :----------------------------------------------------------: | :----------------------------------------------------------: | :----------------------------------------------------------: |
| ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXds1xuk3ICjiC8nVXYN025V9OEQhWEj3NvNtX0N2dETyEuTgO5XzA_wpI7zxmUSkTtlpTyT_Q79S7SPbbagRi2HMF6UVqp_6MneHORnR6uQ7h_p6crQpB3erMciC3Vhl0MhYGsEBCC96ifxS0BrtQ0?key=51ZvvWJZT0VLJN68FZq3eOhR) | ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXef7hnHvmkeSff3z8VDYcFwDkKgDNHvZ5PB7XcXJ50jZU0F1cd5tGRDaGOUzrpt6tl8ytwOWZD6Ssva84i4hwtzgTZmkDkTE2lxYUWrGYc8259w5c6PKGEYvMTIyeb9Q5zBSFJiGBVyNRgz1VUbglE?key=51ZvvWJZT0VLJN68FZq3eOhR) | ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcft4IEglGTGyq5PFP5rd1GCtEopLxtyQi853zPxx6Oi7ckkVf3vZZ9mD0RqItMAuqymF75iBu4B-0kebS-LLcCCyf5TiW4xxOshgTOcbEn74O9UFAt5xOMhdIAfLrXvi53fXCJI6JpV0cuqIc8uw?key=51ZvvWJZT0VLJN68FZq3eOhR) |
|                          Base Case                           |                          Base Case                           |                        Recursive Case                        |

When at an intersection, the recursive case leads to another position on the grid which may be another intersection or it may be a base case. A base case is characterized as having no choices because any direction other than moving along that edge to the goal violates shortest path, so the base cases are any position on the grid along either the bottom or right edge of this presented grid.

As argued, all more complex grids are simply extensions of the basic grid.

| ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXckzFISlWBHxSdM6N2iEyATKUomr4KQbe82jtPBPo2wzwwvpvX_Ve_M3OUf0qBL83SmEMvwVZEc6m9F2Tu6Hk_D4p5quJhdiQbA3TUH1ms65yC0skDDrRtVLM22I4X_PlEes6y4Y47M5j1qEceVfBw?key=51ZvvWJZT0VLJN68FZq3eOhR) | ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXf62lz6X5imC4a214Y7heWhE7NZnE2wBy_6LO9OxGWp_zsLJFdmHsjNlGprg_N7dUHk6fVLy2VMVUsULk6WFarhBZD3Eg3wdLRyzxZxMwTwq3oMLk3c3RtOn0C8fuIZpv1hIj8khoADFR6qAW74JsM?key=51ZvvWJZT0VLJN68FZq3eOhR) |
| :----------------------------------------------------------: | :----------------------------------------------------------: |
|                 The Two Block Problem Setup                  |       There Are Three Paths From The Start To The Goal       |

For the above example, moving down from the starting position arrives at the base case along the bottom edge which means there is only one path from the starting position when following the downward direction, and moving right from the starting position arrives at an intersection which means there is more than one path emerging from this intersection because this is self-similar, *i.e.* we are still computing the number of shortest paths from this intersection in a grid, and a sub-problem, *i.e.* we are computing a smaller grid from this intersection. If the middle intersection is reached, this is the 1 block problem discussed above.

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfpgEE3UltuqwO7soQD6-h3UvGdC98Lzm3W5Q-ZoP77SmX_FBPDn2xGERAub_33LghcF_JeHYdYsv-VXaUTYigrEdYUcm0kb--uLqrgNmBTr1n-u_xGfBEcpBgkr4GKg8C3sTXraSCxWlkUrvhOpg?key=51ZvvWJZT0VLJN68FZq3eOhR)

Is there symmetry in this problem? In other words, does the above solution inform us of other similar problems? The answer is yes, as all versions of the 2x1 problem have the same number of paths..

| ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXd5-Vk3h1hvOmrydEIKRXlr_rS4Oa8u3ewe5H95-QjJFKo3dP8QdTP3WD72bGDbNOwR9qOPZrnttcP9zvmjE9DaXyO11pNOMQK-jgjPrtNn_ho5vDPQzm-PCzcxwhdhivqj_0O1z8uho8nkuI3cvQ?key=51ZvvWJZT0VLJN68FZq3eOhR) | ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXem9lzOnsKEijQoQIRB51iUMu0DQXnRpQT7bRL_WTuBTRyFNycmBwpBO3OqOv8yY3Rm6RTXLimTVi5qoOFt-C46NY71OFT0LQN97tSsyVlbP4kVFgQHOhB6gaNUtIJi29ntZJBC3NsYqX7JUvpdBXg?key=51ZvvWJZT0VLJN68FZq3eOhR) |
| :----------------------------------------------------------: | :----------------------------------------------------------: |
|           The Alternative Two Block Problem Setup            |    There Are Also Three Paths From The Start To The Goal     |

Does this symmetry further inform us? Yes, because the 2x2 problem decomposes into the 2x1 and 1x2 problems:

| ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdzQFP95S90dA1-HUJHFFQ20y8CBdkmEO7QUrLpi3oFZUyBEOreyFEjKZka7ECQiN3970gFBwcMRKOT0mJ754qKXx_kWmL0p4g0qa9UGASY7NruX0NVSjz9Otr6weSEeCpS9k2GtMMWMB2fHBEjSFY?key=51ZvvWJZT0VLJN68FZq3eOhR) | ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXf9fXgbMhqTsZgvOzJddWCvyuoutKKreXQqdTX4vVlkGGSDr_VK7MZzntS9l1PRyqjqtkanYLpHoapnBRkT1BjI2Oe6KB_1XFwBnmPF9hPWYK9CiF8ywcCDO_vth21DJYzXFVhyCYP34r8853EqTXI?key=51ZvvWJZT0VLJN68FZq3eOhR) |
| :----------------------------------------------------------: | :----------------------------------------------------------: |
| In The 2x2 Grid, Moving Down Leads To The 2x1 Grid Which Has 3 Paths | In The 2x2 Grid, Moving Right Leads To The 1x2 Grid Which Has 3 Paths |

*There are a total of 6 paths in the 2x2 grid. This problem is really the sum of the number of paths in the 2x1 grid and the number of paths in the 1x2 grid. From this observation, we see that the count of all paths can be solved by solving the adjacent subproblems.*

All of the above simply reinforces that this is problem can be solved using a recursive implementation.

### Recursive Implementation

Based on our analysis of the one block problem, we can identify all of the elements involved in a recursive solution to the Manhattan problem:

| ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXds1xuk3ICjiC8nVXYN025V9OEQhWEj3NvNtX0N2dETyEuTgO5XzA_wpI7zxmUSkTtlpTyT_Q79S7SPbbagRi2HMF6UVqp_6MneHORnR6uQ7h_p6crQpB3erMciC3Vhl0MhYGsEBCC96ifxS0BrtQ0?key=51ZvvWJZT0VLJN68FZq3eOhR) | ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXef7hnHvmkeSff3z8VDYcFwDkKgDNHvZ5PB7XcXJ50jZU0F1cd5tGRDaGOUzrpt6tl8ytwOWZD6Ssva84i4hwtzgTZmkDkTE2lxYUWrGYc8259w5c6PKGEYvMTIyeb9Q5zBSFJiGBVyNRgz1VUbglE?key=51ZvvWJZT0VLJN68FZq3eOhR) | ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcft4IEglGTGyq5PFP5rd1GCtEopLxtyQi853zPxx6Oi7ckkVf3vZZ9mD0RqItMAuqymF75iBu4B-0kebS-LLcCCyf5TiW4xxOshgTOcbEn74O9UFAt5xOMhdIAfLrXvi53fXCJI6JpV0cuqIc8uw?key=51ZvvWJZT0VLJN68FZq3eOhR) |
| :----------------------------------------------------------: | :----------------------------------------------------------: | :----------------------------------------------------------: |
|                  First base casetailor mage                  |                       Second base case                       |                        Recursive Case                        |

The first base case occurs whenever we reach the bottom row of the grid regardless of which column we are in because there is only one path that may be followed of shortest distance once on the bottom row.  Similarly, the second base case occurs whenever and wherever we reach the rightmost column because there is only one path of shortest distance at that point to the goal.

The recursive case occurs whenever we reach an "intersection" which is any "interior intersection" that is not along the bottommost row or rightmost column.  When an intersection is reached, there always exists two directions that lead to one or more shortest paths extending from that intersection.  In the basic one block problem, each of these directions lead to base cases meaning that from the two possible directions there are two and only paths total.

These observations are enough to implement a simple recursive Manhattan algorithm:

```		pseudocode
manhattan(row, col) → paths from this row and col :
	if row = 0  :
		return 1
    if col = 0  :
    	return 1
    	
    count = manhattan( row - 1, col )
    count += manhattan( row, col - 1 )
    return count 
```

### Algorithmic Time Complexity

To determine the algorithmic time complexity, revisit recursive Fibonacci.  The recursive implementation of Manhattan shares similar characteristics to recursive Fibonacci. Recall that recursive Fibonacci has the following pseudocode:

```pseudocode
fibonacci(x) → integer >= 0 where x is an integer and x is >= 0 :
	if x = 0 : 
		return 0
	if x = 1 : 
		return 1
		
    return fibonacci(x-1) + fibonacci(x-2)
```

So how does the above relate to the time complexity of Manhattan? From our pseudo code of Manhattan, we see the same pattern of two recursive calls to itself for each call to a recursive case. This suggests that Manhattan is at best the same efficiency as recursive Fibonacci and we determined that recursive Fibonacci is exponential or $O(2^{n})$.

We could restructure Manhattan slightly and see how closely it resembles Fibonacci

```pseudocode
manhattan(row, col) → paths from this row and col :
	if row = 0  :
		return 1
    if col = 0  :
    	return 1

	return manhattan( row - 1, col ) + manhattan( row, col - 1 )
```

Why did we use a more “back of the envelope” way to estimate the efficiency of Manhattan? Should we have tried to find an analytic mathematical solution that gives us a more accurate estimate? Manhattan actually belongs to a class of combinatorial problems which are similar to but have worse time complexity than exponentials, so while we classified Manhattan a little generously, the reality is that our estimate is good enough because both classes of problems are essentially unsolvable given sufficiently high input.

## Permutations

A permutation problem involves making a number of choices and the order in which choices are made matters.

Imagine a stage with 3 seats (a, b, c) and two speakers (1, 2). What are all the permutations of how the seating can be arranged for the two speakers:

|      |                                                              |                                                              |
| ---- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| 1    | Speaker 1 could sit in seat **a** which means that speaker 2 must sit in either seat **b** or **c**. Suppose that speaker sits in seat **b**. This represents one permutation. | ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdFzxtNg3n_F2khVsiXPCgeAqdTa-7-KDDW2bgJEEjT0nFFud_1LtRGD8Q17RY7nTksq0QqYpybThVYzYEh0FpJQFSFZQ8usv3KJ0zAzK9rf8BVnfdO2yRx-OGHJqnIX-La0MT0HUvcQRqkhCYuXOI?key=51ZvvWJZT0VLJN68FZq3eOhR) |
| 2    | As already suggested, speaker 2 could have instead sat in seat **c** resulting in a second permutation. | ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfSmq2zCv14cBxygaw1xvq6SKamotW0m3q4snzu0itRoXZuKfH06Tqc46u69uwWmiA2atrVUgcI7rYjML6ENAKTEaoS0APkJWKRAaNi1ivcXnlHUV8iczWZrVUGqT5gnBiPxA4Da9gbvJH3Uk7mGw?key=51ZvvWJZT0VLJN68FZq3eOhR) |
| 3    | Alternatively speaker 1 could sit in seat **b** which means that speaker 2 must sit in either seat **a** or **c**. Suppose that speaker 2 sits in seat **a** resulting in a third permutation. | ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcIujVtBrfmmnJwcRvEJLYEtff-PSkLI_Kfo6mVWolHso6fIuOEbIkrJ-qHp_xkgM1kH0tOUoh2dZ_hhEzQ3kyvl9SuZ9rZxSdhXSOwnESdtZBHzn0cOhbDe-E-EsAzJqTk1IbFl-6jpsU3nsqK4SM?key=51ZvvWJZT0VLJN68FZq3eOhR) |
| 4    | Or speaker speaker 2 sits in seat **c** resulting in a fourth permutation. | ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdnuF9707PG9SfOy1SZvJ3mfTZKRs1yIr2W9OVJ8IWcVKs6eY5Cp0FWmZshQXJSCqEQ_A6i6WWQMaQY1_LsKLP9gZw4bD9A1Fj8U5ZZnCi6gakkShTK9aLZbdrJWqGLHFJSjNtwHcmasDWl_FtANk8?key=51ZvvWJZT0VLJN68FZq3eOhR) |
| 5    | Or speaker 1 sits in seat **c** which forces speaker 2 to sit in either seat **a** or **b**. If speaker 2 sits in seat a, this produces the fifth permutation | ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcExBeWfteJQnjz7mw-kpn4KD7TLe07JhLpWd2ZaxkLCDKa5olvjdW_RharSmlew8uwDEBRDqpn6MFEsA2b3snsCodf1cw1KySVKkFt7c1GpDUacWDWuIcVlLcKCxVma3oP0-EKrDtiXhtj5cPbd3s?key=51ZvvWJZT0VLJN68FZq3eOhR) |
| 6    | If speaker 2 instead sits in seat **b**, this produces the sixth permutation | ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcE_sj0-52Yx_yaNhokq38O7Bsh49Va4rhgM_q0rs58fsh08iPcKx8t_Ngk6w2tE66E5XireFkiWYxOHFNfgHQO1QfL_FjgBt6wPzaws6Hn2isYqJD5Awi9X00Zyn-EooEen3LNpQS6Wc6z8O5SmFE?key=51ZvvWJZT0VLJN68FZq3eOhR) |

### Analysis

While the illustrative example is useful, it becomes cumbersome as the problem grows in size. Is there a mathematical formula that generalizes this idea? Where $n$ represents the total number of elements to choose from and $k$ represents the total choices made among the elements, the following formula predicts the number of permutations:

$P(n,k)=\frac{n!}{(n-k)!}$

Let’s apply this formula to the seating problem where $n$ is the number of seats, 3, and $k$ is the number of speakers, 2:

$P(3,2)=\frac{3!}{(3-2)!}$

$P(3,2)=\frac{3!}{1!}$

$P(3,2)=\frac{3·2·1}{1}$

$P(3,2)=\frac{6}{1}$

$P(3,2)=6$

This formula does indeed predict the permutations. Without drawing out all the examples, what does it predict the number of permutations for 5 seats and 2 speakers to be?

$P(5,2)=\frac{5!}{(5-2)!}$

$P(5,2)=\frac{5!}{3!}$

$P(5,2)=\frac{5·4·3·2·1}{3·2·1}$

$P(5,2)=5·4$

$P(5,2)=20$

In short, this answer predicts that there are 20 different arrangements of speakers and chairs when there are 5 chairs and 2 speakers.

While this is a novel idea, what is the purpose of illustrating this problem? Note what mathematical operation is used in the analytical solution provided. This shows that the relationship between the size of the input $n$ and the number of potential arrangements (the output) is a factorial relationship. In other words, permutation problems by their very nature are $O(n!)$ and are incredibly inefficient problems in terms of time complexity to solve. If the difference between $n$ and $k$ is sufficiently large, such as $n=100$ and $k = 5$, then the time complexity of a permutation problem is more defined by the factorial operation. If the difference between $n$ and $k$ is small, such as $n=100$ and $k = 99$, then the time complexity is closer to $n$.

### Combinations

Permutations belong to the more general class of combinatorial problems. Combinatorial problems involve choices and the general combination problem does not consider the order of choices while permutation problems do. For example choosing six for one die role does not limit the choices for another die roll (a combination problem) but choosing six for this die role does limit the remaining choices for this die role assuming exclusivity (a permutation problem). The general equation for a combinatorial is also factorial and is defined by the equation:

$C(n,k)=\frac{n!}{k!(n-k)!}$

Unfortunately, most of the really interesting problems in modern society are choice problems and so are defined by combinations or permutations.

Manhattan above is actually a combinatoric problem even though our rough estimation predicts it to be exponential.  Calculating the number of paths using an analytical equation is difficult for those who have not focused on combinatorics, but it is quite easy to implement an algorithm to solve the equation; however, regardless of our mathematical background, as programmers we still need to practical ways to address the question of much time will the algorithm take to solve the problem.

## Exploration Problems

An exploration problem is one that cannot be solved without some flexibility to undo a decision. For example, if we were not able to undo a decision when exploring a maze, we would quickly become trapped in the maze. It is the ability to retrace our steps that allows us to escape a maze whether it is solvable or not.

A recursive algorithm that has a well defined solution and does NOT require exploration is called **tail recursive**.   It is called this because these algorithms typically end with a recursive call at the end of their definitions.

We call the algorithmic strategy of retracing steps and undoing decisions **backtracking**.  Backtracking can be applied to a variety of problems, but in general, we need to apply backtracking to problems where we do not know whether there is a solution or not. These such problems need to be robust to failure as they may have many different failure states and few if any paths to success.

Backtracking algorithms are often more easily expressed through recursive implementations because recursion is naturally built upon the memory Stack.  The primary challenge to writing a backtracking algorithm is to manage start restoration when it is necessary to undo a decision.  If using a loop and a table, it can be difficult to accurately compute earlier state.  Because recursion stores the history of previous unresolved function calls and associated parameters on the memory Stack, there is generally a natural snapshot of earlier state readily available in memory.  One key feature of the stack data structure, which we will study in depth in Chapter 9, is that it is ideally suited for maintaining a history of information, so because we are using a stack to manage memory, there is a mechanism built into Java memory management tailor made for backtracking through recursion.

### Maze

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXevsKTlb2MrF8wja7cS9pUcZOTUjFcmaTwgZyu0xeH50qGubM-foycFtQQ-TORpi96hq-bUs26HeIF_vPzcHNz1VPz1RoSjzoZx3y2d9XULCLpZH4J_b4S_TXSTWOkgZlUos8e4-Gk3clN8x6YrqiQ?key=51ZvvWJZT0VLJN68FZq3eOhR)

First consider that solving the maze from inside limits the information available and the top down map we have here is not generally information we have when exploring. Instead, we have to put ourselves inside the maze to have the proper perspective about our inherent limitations.

To explore a maze successfully we need to be flexible but robust. There are mazes with no solution and there are mazes where we can wander in circles and that may have multiple solutions. For this problem we are only concerned with finding a single solution and not all solutions.

| ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfUpG18-pu2wSZygFplHWyNMtXZA489chHHa8Hh38N4VTHWzZK-VpeXZRoUeTlQhIwz7lUJ5dQ94qSfPU_od4X5FK8Lu9BZK4GcNDd7BaFbroH5MBWrD9HkizH6jnMFzw4-0MFVyRx4udf9meN4nu4?key=51ZvvWJZT0VLJN68FZq3eOhR) | ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXeSf-pLBPsTxkvsrZhoFjLqIeOlg3GNap3KsxGnBRribhuU1o3yBvq704i7y3cL5lbnWa7O0rG1HuxHNcte1baiFviLb8PM2KkzQVXFJhzu_UaEkO_mOWntlo6zE-WzUq4Q27f0KoreYToZus1bEEo?key=51ZvvWJZT0VLJN68FZq3eOhR) |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| A maze with no solution                                      | A maze with multiple solutions and an infinite cycle         |

We will assume we are dealing with a maze composed of square cells oriented to a grid describable by the cardinal directions.  Each cell can be entered or exited along a direction of travel if there is no wall in that direction.  We call a cell with *more* than two directions of travel an "intersection", a cell with only two directions of travel a "hallway", and a cell with only one direction of travel a "dead-end".

A maze has a starting point called an "entrance" and a goal called an "exit" and to traverse a maze is to find a path consisting of one or more cells with contiguous directions of travel that link start to goal.

At intersections there are multiple choices about the directions one may go and represent points in the maze where a decision must be made. However, only on direction can be explored at a time, so it may be necessary to return to an intersection later if exploration of another direction of travel fails.

Hallways do not represent choices. A hallway connects to an intersection, a dead end, the goal, or the starting point.

Dead-ends represent local failures in an exploration but reaching a dead end does not suggest the problem is unsolvable, it simply suggests that the sequence of choices made results in a local failure but it says nothing about other sequences of choices.

If the goal is ever reached, a path through the maze has been found and traversal has succeeded.  If the start is ever arrived at again after traversal is started, assuming all decisions have been explored, then the maze has no solution and cannot be traversed.

To consistently navigate and avoid retracing already made decisions, potential paths at intersections should be explored in a clockwise order and breadcrumbs can be used to indicate that a location has already been visited.

Due to the extreme variations among mazes and problems like circularity, it might be very difficult to successfully write an iterative algorithm that solves the maze. Can we use a recursive strategy instead?

Consider that at each intersection, each path ahead is simply a smaller maze, so a maze is composed of self-similar subproblems which means that intersections represent recursive cases.  Base cases occur whenever a dead-end, goal, or starting point is visited.

A dead-end is just a local failure, so the response is to backtrack to the most recent intersection (decision) and explore the next unexplored path. If all paths at this intersection have been explored, the response is to backtrack further to earlier intersections until an unexplored direction of travel is found.  If backtracking leads all the way back to the starting point, there is no solution because all decisions have been explored.  If the goal is reached instead of a dead-end, there exists a path from start to goal and this path is recorded in the current list of successful decisions used to get to the goal.

### Backtracking

Backtracking is the power to undo decisions and typically involves a stack to retain the history of decisions.  This history is naturally stored in reverse order as the bottom of the stack represents the first decision and the top of the stack represents the most recent decision.  The memory Stack is a stack so it naturally supports backtracking and since the Stack manages memory for recursion anyway, *i.e.* the stack records state for each function call and all local variables are stored on the stack, backtracking is generally accessible and very natural for recursive implementations.  We will talk more about stack data structures in a few weeks.

Backtracking is a useful strategy for solving “exploration problems”.   An exploration problem is one where we are not sure if there is a solution to begin with and to determine if there is a solution it requires an exploration of the solution space.  Examples of exploration problems are a maze, hill climbing problems like evolutionary problems, and n-queens.
## N-Queens

In chess, the queen has complete movement and is the most powerful piece on the chess board. It can attack in any direction, vertical, horizontal, and along either diagonal, so any piece that ends its movement along one of these axes is threatened by the queen and may be captured on the queen’s next movement.

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXeMGNmU3_OQI_T0JG525-bPgl4A2GSY3CFYADtgAEeu-Zgwsss9NVJpJBB_Ei1pizWNya1x9s0cOA_HVlYHdqQEQO3R8sM42xy9gS5H5jvLld63r_wCibkmPsdqnTkB_g7kjD_3Hh26iNnwxWR1oiI?key=51ZvvWJZT0VLJN68FZq3eOhR)

- We saw that N-queens is a backtracking problem as well
- We may call it “trial and error”, but we used a very structured strategy

|                                                              |                                                              |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| has1. Place a queen in the first column, first row           | <img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXcILvyQkh3P77gsTvofiFt7sHlDkZjdJVYw160mB7THDOroeW2lYYjqiQoPLCy9wnqKUFKH77p5UWDBlMpOOB_9hQbRozAAdVrVz8dXDvdebVoqjgqaSFBunSej_ek8SKFnNOXtAnhsu2FySqA0kQ?key=51ZvvWJZT0VLJN68FZq3eOhR" alt="img" style="zoom:800%;" /> |
| 2. Try to place a queen in the second column. We first try to place the queen in the first row but it is threatened by the queen in the first column. We then try to place the queen in the second row but it is also threatened by the queen in the first column. We then try to place the queen in the second column, third row and succeed because this position is not threatened by preexisting queens on the board. | <img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXd9h_B18FRaoxJ4gklUyOMKKIu1c-aN61hneBVaqD645-grSPZ-nBepT-N5qqfbRy2HPqu6HzOD0GyWizRHOgED5Tdgy4aJ1DDaOdKc85IqRgwdUhliCn_ZyZ7WRqCRAsN87cQ8Iz3kxH5tPjbSjyY?key=51ZvvWJZT0VLJN68FZq3eOhR" alt="img" style="zoom:200%;" /> |
| 3. We cannot place a queen in the third column because all positions in the column are threatened by the placement of queens in the first and second columns. This represents a failure in the process, but it does not mean it is unsolvable. Our next step is to remove the most recent queen’s placement (placed in the second column, third row) restoring the previous board state, and try to place it elsewhere if possible. | ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcILvyQkh3P77gsTvofiFt7sHlDkZjdJVYw160mB7THDOroeW2lYYjqiQoPLCy9wnqKUFKH77p5UWDBlMpOOB_9hQbRozAAdVrVz8dXDvdebVoqjgqaSFBunSej_ek8SKFnNOXtAnhsu2FySqA0kQ?key=51ZvvWJZT0VLJN68FZq3eOhR) |
| 4. Since the previous attempt was the second column, third row, we continue on to the fourth row and try that position. The second column, fourth row is unthreatened, so we replace the queen there and continue the process. | ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfqo8QCTXyiAr3JLwMq8HftISVb_ruiCWliWJL0jxYW8dBV-rDlvCa3EIPB5OrlcNovKZaQK6FxMsfJ2lCywT1qssOf3pNazSco0v0Pog0IXK3Oy0nZd9MRWg0HztiAgwVZ_aL5hGMqTHcNOkDWIlQ?key=51ZvvWJZT0VLJN68FZq3eOhR) |
| 5. Attempt to place in the third column first by testing the third column first row which we find under threat and not a legal position. We then find the third column, second row to be not under threat, so we place the queen there. However, scanning the fourth column shows that all positions are under threat, so placement in the third column, second row does not lead to a solution. Subsequent placements in the third column are all illegal, so there is no solution for placing the queen in the second column, fourth position. Because this is the last row in the second column, it means that our initial placement of the queen in the first column, first row has no solutions, and we must replace the queen in the first column. | ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdCW5jkgewYE0iH74Ic95QFa3kTjsRqh6zmc7gA8DAWpmEKLGtiWKzowF4HOICU4Dsg40GopabWGLOEOMGJyZ8yYNd_fQngZ0SKcfHQ1suL0EGwLnd7i_LzcjxjevM10z9dsaiFhUfVoOiejMD-Gt0?key=51ZvvWJZT0VLJN68FZq3eOhR) |
| 6. We have undone each column and replaced the first queen in the first column, second row. | ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdS7Z5hyp-6sfYmb7x1QjmOJk2AbAwl7-76-vlOqVRnE7qsroC_FZQzytmuHm71hE40sUQWtEr2mIz7zmneEOj-2QoEJFCcrC8h8D_SQvNJiSHIHz4BHCRwZrj6MekphFNyn54xqU3KJO9wITeQyUs?key=51ZvvWJZT0VLJN68FZq3eOhR) |
| 7. We try all positions in the second column beginning with the first row and find positions up to the last position is under threat from the queen in the first column, second row. Because the last positon is legal, we place the queen in the second, column, fourth row. | ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdddg3ZDmT4t7VtYS-Iq_2lA7DgYt8TIH71C0rJNL6DZS1BxONMwvznxtcbM-rXOMVBODahydkrCumtgGSkIIou6t9e5zUS4QEcv8nKy_x-WHmg11E-2980u7CcfwXiVzsul5j0H4A1j2JG3BtECck?key=51ZvvWJZT0VLJN68FZq3eOhR) |
| 8. We start at the top of the third column and scan top to bottom for a legal position to place the queen. We find that the third column, first row is unthreatened, so we place a queen there and continue on to try to place in the fourth column. | ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfWxkgIS6JCM9-l16GVwe9Om10F-njfHKipVj9oSf9D4e2uszLRg3D3BpO1_26g0_WjFfmkYcSAWu7DMOzc1sQoETGlwWk5SuSaOQ7yNHyg_J859th8mSjEr0VeCoq-xZvlJ_nQB1jaCoIGGi5oPH8?key=51ZvvWJZT0VLJN68FZq3eOhR) |
| 9. We start at the top of the fourth column and scan top to bottom for a legal position to place the last queen. We find that the fourth column, third row is unthreatened, so we place a queen there. Because we have placed our last queen, we have found a solution and the process is both successful and complete. | ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdDWIXCMCJyssU8V08PEFDVmvgYYmFhTsxuHeNqfdOHmJLkwBhr0J99uhz5UIXKJhaGF6EHlgctpovBvSD4e08acInIDxpo7CMtUS0-2ttG-0E2D6cgtBDeQJGPbgJ4QDNqBIPvLld-VcSgchh8gw?key=51ZvvWJZT0VLJN68FZq3eOhR) |

### Recursive Implementation

```pseudocode
nqueens(n, c) → n = the number of queens to assign, c = the column to start with : boolean indicating if solved
	if n == 0 : 
		return true
	if c == 0 : 
		return false

 	for each row r : 
		if [r,c] is not threatened(r,c) : 
			place queen n at [r,c]
			found = nqueens( n-1, c-1 )
			if found : 
				return true
	return false
```

### Algorithmic Time Complexity

The obvious aspect is that for each recursive call, the algorithm proceeds through each row and attempts to place a queen; however, the time complexity is seriously affected by the efficiency of more opaque aspects of the algorithm.  

One opaque aspect is that there is some magic operation `threatened(r,c)` which returns a boolean that summarizes whether the cell in question is legal for a queen's placement.  While a lookup of this information in a table could be as fast as $O(c)$ the efficiency of the update whenever a queen is placed or removed is unclear and could be as much as $O(n^2)$ itself.

Regardless of the efficiency of ```threatened``` the overall efficiency of the placement and removal process is not straightforward.  It is not simply a loop inside a loop as that would only be possible if we never removed a queen; however, this is a robust process intended to backtrack whenever a queen is placed in an unsolvable position.  Each call to `nqueens` represents iterating over every row in a given column and it is possible to backtrack from every previous column configuration when a failure is detected.  As a result, in the worst case, `nqueens` has the potential to try every permutation of queen placement on the board plus the additional cost of updating the `threatened` data structure on attempting to place a queen and removing a queen.  

Because `nqueens` is a form of permutation problem, then this must be operating in on the order of factorial time and can be estimated with a time complexity of $O(n!)$ where $n$ is the size of the input equal to both the number of queens and the number of rows and columns on the board.  While for 4 queens this still seems like a trivial problem, consider how complex it would be to solve this for $n=100$ or $n=1000$.

## Review

1. What is recursion?
2. Is the piecewise definition of power recursive, and if so, why?
3. Is it possible to do express everything recursively? 
4. What are the behaviors and characteristics of an iterative design?
5. What are the behaviors and characteristics of an recursive design?
6. What types of problems are good candidates for recursive implementations?  Why?
7. What is meant by “a problem that can be reduced into self-similar subproblems”?
8. Why are reductive problems good candidates?
9. What are the two cases necessary to implement a recursive design and what are their characteristics?
10. How do we structure recursive implementations with regard to these cases? Why?
11. How do we control recursion? *Note: A base case alone does nothing, so it alone cannot control recursion.*
12. Why do we try to model base cases at or around zero ,one, or null cases?
13. Analyze the time complexity of iterative power.
14. Analyze the time complexity of recursive power.
15. Analyze the time complexity of iterative factorial.
16. Analyze the time complexity of recursive factorual.
17. Analyze the time complexity of iterative fibonacci.
18. Analyze the time complexity of recursive fibonacci.
19. Why is the stack so important to recursive algorithms? What is it handling for us?
20. What happens if recursion is uncontrolled?
21. Given the previous question, why is there a finite number of recursive calls that can be made and why?
22. What is the relationship between the number of variables (and parameters) in a recursive function and the upper limit on the number of recursive calls?
23. Give an example of a permutation
24. Formally define permutations in the context of available options, numbers of choices, and order of choices. *An illustrative example would be enough.*
25. If permutations are modeled by the formula $P(n, k) = \frac{n!}{(n-k)!}$ and combinations are modeled by the formula $C(n, k) = \frac{n!}{(n-k)! k!}$, what is the general algorithmic efficiency in terms of Big O of any algorithm that attempts to solve a permutation or combination problem by brute force? Why?
26. What is the “Manhattan Distance”?
27. Define the “Manhattan Problem” in terms of Manhattan Distance.
28. What are the constraints on the Manhattan Problem?
29. Illustrate the base cases for the Manhattan Problem.
30. Illustrate the recursive case for the Manhattan Problem.
31. Write pseudo code that solves the Manhattan Problem.
32. Estimate the growth of the problem with respect to the number of operations for the Manhattan Problem from the pseudo code.
33. What does it mean to backtrack?
34. Why is recursion a natural approach for backtracking problems?
35. Why might an iterative approach be difficult to implement for a backtracking problem?
36. What is an “exploration problem”? 
37. Why are exploration problems good candidates for backtracking problems
38. Describe the Maze problem.
39. What is the “self-similar subproblem” in a maze?
40. Why is a Maze an exploration problem?
41. Describe backtracking in a Maze.
42. Describe the N-Queens problem.
43. What is the “self-similar subproblem” in N-Queens?
44. Why is the N-Queens problem an exploration problem?
45. Describe backtracking in the N-Queens example.
46. Analyze the time complexity of N-Queens
47. Describe the Towers of Hanoi problem.
48. Does Towers of Hanoi involve backtracking? Justify your answer.
49. What is an application of Towers of Hanoi? Justify your answer.
50. Analyze the time complexity of Towers of Hanoi
51. Contrast “tail recursion” with “backtracking” recursion.
52. Why is it more “expensive” and more prone to error to count up to a target value for a base case rather than to center that base case around one, zero, or null? What is it more expensive in terms of and why does this expense further limit recursion?
53. If iterative approaches are almost always less expensive in terms of memory than recursive approaches, why use recursive approaches at all?

# 5 - Search

The term **set** with no adjectives does not generally imply order. In essence, a set or specifically an **unordered set** is just a pool of data with no structure. If a set has some structure and therefore some order imposed on it, it is typically referred to as an **ordered set** or by other terms that suggest the nature of the ordering imposed. For example, an **array** suggests a set that has positional order. There are a variety of ways to order and structure a set which we will explore further in the coming weeks. Many of these specific structures will be given names that will describe the nature of their ordering, structuring, and the rules by which they allow interactions and by which they behave.

**Search** is the process of locating an element within a set ordered or otherwise. It is often a two part question: 

1. **existential** *-* “Does the value exist in the input set?”
2. **accessible** - “If it exists, retrieve its value or retrieve a reference to it” or “give access to it”

The accessible question is moot if the existential question fails, so the existential question is both the most basic and most important question to focus on when performing search on a set of data. Our analysis of search will assume the worst case scenario which is a failure to succeed with the existential question. In other words, when we perform a time complexity analysis, our analysis will assume search does not find the element in the set given the strategy and ordering used.

> **Worst Case Analysis**: Worst case does not mean that we intentionally design a poorly performing data structure. Worst case analysis is not analysis of a faulty design, it is an analysis of a data structure under its worst data conditions. This is a reflection on the fact that programmers control design but users generally control the data. Programmers have a variety of choices when designing data structures and it is the programmer’s responsibility is to make good decisions on that design to ensure the best performance under expected data conditions.  Worse case analysis should be performed on that design, not on an arbitrary, poor design that is incapable of meeting the necessary application requirements

Search is one of the most common computational operations that programmers take for granted. We should be concerned with the time complexity hidden behind a method like `.find(value)` if it is at the heart of one of our own processes and a search operation can come in many names: `search`, `find`, `contains`, `get`, or even list operators like braces, `[i]`, or parentheses, `(j)`. It is important to remember that the time complexity of any method we use scales the time complexity of our own algorithm and this becomes a multiplicative term to the time complexity of our algorithm.  For implementations that must be efficient, we need to anticipate any implicit costs and minimize the use of any especially costly, redundant function calls.

## Search Algorithms

Search requires a search set $A$, a search value $e$, and determines whether or not $e$ is a member of $A$.  Let `search(A, e)` be the general form for a search function where the first parameter, $A$, is the search set and the second parameter, $e$, is the search value.

For example, let set $A$, contain 73,51,41,85,32,63,24,42,87,71

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfwvveQYrCV3yx5_8iXYf6_DD52nRjUXHyjmIpk756ybGtW8uVRof9W3JrS8bfDh-vuBHVd0ztclZsNTzgFzKbpDzZNssy8IxRoxl2xsqlRyIyK_ksQSswxn4dKwRrOYJUK1hcU4Q?key=c-HjLrei7-1addUWRhuwjm6S)

Let element $e=41$ and let $e’=93$, `search(A, e)` would at the least return `true` because $41$ is a member of set $A$ while `search(A, e')` would at the least return `false` because $93$ is not a member of set $A$.

## Random Sampling Search

One search strategy is to randomly sample an element from the set and compare that element to the search value. Random sampling is like drawing tiles from an opaque bag where you may not peek inside the bag in any way. There are a number of issues with this brute force strategy particularly if we are required to return selected tiles to the bag as this will likely result in an infinite process.

How is an infinite process possible here?  Simple, assume the element is not in the set. If there is no tracking of previously sampled elements as there is when we return the tile to the bag, there is no way to determine whether or not all elements have been sampled from the set. Without the ability to know when all the elements have been sampled, it is not possible to know when to end the process and therefore the efficiency is $O(\infty)$.

To ensure the process exits in a predictable amount of time, the process could instead divide the set into two subsets: the unsampled search set $A$, and the previously sampled set $B$.   The unsampled search set represents tiles still in the bag and the sampled set represents tiles that we do not return to the bag once we have removed them.

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdoOtQFVzhVEUmrD-JXO_iP2g3-YjhOB7W8ZAzHijcgoJU45oFR4y9ObiUFZi6bwoDUbPNIyijh6Zih2iW2QgF_Y7_nD9qUR0DL6oAD_OFYU_aEhSt3ufcgNNSimWuM8BbE43kX_Q?key=c-HjLrei7-1addUWRhuwjm6S)

Sampling for search is only performed on the unsampled set and when an element is sampled, it is moved from the unsampled set to the sampled set thus decreasing the unsampled set by one with each sampling.

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXd2ZMkwaURVBwN0bX4Itrvx503UzyieF_uRVjw7imvHl61lDAylsFddJz701AEOGdplYpXjZREhxQ1vPns5VY_NxyEy-mkRMJltkeI3B_KxiPGDsNRidutVcwtbisy5okJjBgQGAg?key=c-HjLrei7-1addUWRhuwjm6S)

This process guarantees that all elements in the set will be sampled and compared, that no element will be sampled and compared more than once, and that the process will exit in a predictable amount of time.

### Mathematical Analysis

Recall that the worst case for search using this two set random sampling approach is that the tile does not exist in the original unsampled search set $A$, a set containing $n$ elements.  If an element can only be sampled once, it must be removed from set $A$ and placed into set $B$ when it is sampled; therefore, one new element is guaranteed to be sampled with each comparison.  The maximum number of comparisons will be $n$ because it will take $n$ total samples (comparisons) to determine that the search element does not exist in the original search set $A$.  
$$
f(A_{n}) = \underbrace{1 + 1 + \cdots + 1}_{n}
$$
This leads to a Big O analysis of $O(n)$ and a linear time complexity for random sampling in the worst case where already sampled elements are removed from the search set

## Linear (Iterative) Search

Random search is inefficient and generally requires more work to implement than linear search in computing.  Why?  When using an array to represent a set, we are imposing a structural order on the set even if we are not imposing any additional order such as a lexicographic order.  The structural order arises naturally because the array is ordered by position which we generally call the array index.  It takes more work to treat the data as an abstract pool of data in a computer, so by default the iterative strategy is more natural and immediately accessible if data is stored in an array.  Because linear search is exhaustive in the same way our two-set random sampling strategy was exhaustive, *i.e.* neither can determine if an element does not exist in the set unless every element in the set is sampled, linear search is also a brute force strategy.  Because linear search is an [iterated function](https://en.wikipedia.org/wiki/Iterated_function) or, more programmatically, it is implemented with a loop that iterates using the same operations repeatedly over all of the input data, it is also called iterative search.

Given an array of data $A$, containing $n$ elements, with no additional order other than the natural positional order imposed by the array structure:

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfDoQAihOyucQB24IQl9yB7nVqAB1DPx7KXSuYVKZogllmyJ3cW-kutpDii_j3Kfatmhy-Ya_C4E2kLwTp77jz0X8ch89zVRPLUAb9A-Qgrvqhndw0Twb81xV5wgxbqCswTka4H4Q?key=c-HjLrei7-1addUWRhuwjm6S)

Iterative search operates by scanning the array from left-to-right. At each index, the algorithm compares the array element at that index $a_{i}$ with the search element $e$.  If the array element matches the search element, $a_{i}=e$, then the search element $e$ exists in the set $A$, and the search was successful.  If the process reaches the end of the array without ever finding the condition $a_{i}=e$, the search is a failure and $e$ must not exist in the array $A$. 

### Mathematical Analysis

The worst case for search is that the element being searched for does not exist in the set. For a brute-force, iterative search, to confirm that a value does not exist in the set, it requires comparing the element in question to every value in the set. The mathematics is pretty simple:

Given an array $A$ as input, $n$ is defined as the number of elements in the array or simply as the size of $A$.  As in random sampling with sample removal, linear search samples a single element each step and in the worst case it must sample all elements to confirm an element does not exist.
$$
f(A_{n}) = \underbrace{1 + 1 + \cdots + 1}_{n}
$$
Therefore, the algorithmic time complexity of linear search is $O(n)$.

As mentioned above, we generally base our analysis of the worst case, but let’s consider other cases to better understand why worst case analysis is used.

#### Best Case

For the best case, the time complexity would be constant time, $O(1)$, because the best case is predicated on the assumption that we would always find our element in one comparison; however, what is the likelihood of the best case? 

The apparent probability that the best case arises in linear search is $\frac{1}{n}$ which gets less and less likely as the size of $n$ increases.  Consider that if $n$ is sufficiently large, the likelihood of the best case arising approaches $0$, so the best case is highly improbable if not impossible for large data sets.

Further, consider that the best case approximation above assumes that the search value exists in the search set; however, this assumption cannot always hold and may be exceedingly rare in real data.  Given a near infinite number of candidate elements and a fixed sized search set, there are far more elements NOT in the search set than those that exist in the search set which means that the probability of any given value being in the search set again approaches zero unless the domain of the universal set is relatively small.  This means that the best case is extremely biased and virtually impossible so it is a poor representation of the efficiency of the algorithm under normal conditions.

#### Average Case

For the average case, the time complexity would be some average of all searches within the search set.  Analyzing this might require we make some assumption like assuming that the search value must exist in the search set.  If this assumption holds, then sometimes the search value is in the first place we look, sometimes it is in the second place we look, sometimes it is in the last place we look.  If we assume a uniform probability distribution of these searches, then the likelihood of the search value being in any given position is $\frac{1}{n}$ and the number of operations to locate an element is equal to its position in the array. In other words, the average number of operations is:
$$
\frac{1 + 2 + ... + (n-2) + (n-1) + n}{n}
$$

We simplify the equation to:
$$
\frac{\cancel{1} + \cancel{2} + ... + (n\cancel{-2}) + (n\cancel{-1}) + n}{n}
$$

Which results in the elimination of half the terms leaving the equation:
$$
\frac{\overbrace{n + \cdots + n}^{\frac{n}{2}}}{n}
$$
Repeated addition of the same term is the definition of multiplication, so the above further simplifies to:
$$
\frac{n}{2} \cdot \frac{n}{n}
$$
Which then reduces to:
$$
\frac{n}{2}
$$
In other words, the time complexity is $O(n)$, so we do get a definitive average case time complexity analysis; however, it turns out to be the same as our worst case analysis and computing it requires both additional work and a more detailed mathematical analysis.  On top of this, our average case above does not even take into consideration the more realistic data scenario that the value we are searching for does not exist in the search set as argued above.  So the average case is at best $\frac{n}{2}$ and at worst $n$ but is most likely worse than $\frac{n}{2}$ and likely trends towards $n$ given realistic data.  It is also difficult to precisely know what it should be, it is hard to compute, and it is trending towards the worst case anyway.

### Pseudocode

**Iterative Search (Existential):**

```pseudocode
search(A, e) → search set A, search value e : boolean, true if e found in A else false
	for v in A : 
		if v == e : 
			return true

	return false	
```



**Iterative Search (Accessible):**

```pseudocode
search(A, e) → search set A, search value e : index of the value in A if found else -1
	for i = 1 to n | n is size of A : 
		if A[i] == e : 
			return i

	return -1
```



## Binary Search

Binary search is an alternate search strategy that uses a **divide and conquer** approach. Divide and conquer relies on structured data and allows us to discard data that fails to meet general criteria which means we do not need to exhaustively search every element in order to know whether or not the search element exists in the search set. 

Consider this example:

We need to find S in the English alphabet.  Because of the properties of the alphabet, we know that M is the middle letter of the alphabet.  From these same properties, we know that S follows M.  We can divide the alphabet in half centered around M, *i.e.* into the sets A-L, M, and N-Z, and compare S to M.  Since S is not M and we know that S follows M, S cannot exist in the set A-L, and we can discard A-L entirely in any subsequent search involving S.  We repeat this process on the remaining set N-Z, and so forth.  If we reach the point where we are left searching only one subset of only one letter, the existential question becomes trivial, *i.e.* is the search value is either equal to that letter or it is not, and this can be determined in one step.

The key to binary search is that the data needs to be in a **lexicographic order** or in other words if the data is an array it needs to be structured by some known order such that it is “in order”.  It is the relationship between the position of an element in the ordered set and the relationship of elements to one another based on the lexicographic order that allows fast searching using binary search. 

In the example above, the lexicographic order is the alphabetical order and from this we know that A is before B, C, etc., that Z is after Y, X, etc., and that M is after L but before N, etc.  We also know that the middle position is 26/2 or the 13th letter, M. If we are searching for a search value that precedes M, there is no need to search in the region following M if the data is in alphabetical order which means we can completely ignore any elements following M if the search element precedes M.

### Mathematical Analysis

Again, the worst case for search is that the element being searched for does not exist in the set.  Because binary search samples only a few elements in its process, it is more efficient than iterative search; however,  it is also less intuitive as to how to arrive at our estimate.

At each step, we divide the remaining search set in half.  In other words for the initial search set of size $n$, we divide the set into two equal sized sets of size $\frac{n}{2}$ and discard one of these subsets.  This requires only a single operation because we take advantage of the efficiency offered by sampling any index in an array in constant time.  For the remaining subset of size $\frac{n}{2}$, we divide it into two equal sized sets of size $\frac{n}{4}$ and again discard one of these subsets using one operation.  We continue to repeat this subdividing and discard process until we reach a subset of size 1.  The progressive size of subsets that results is:
$$
n, \frac{n}{2}, \frac{n}{4}, \frac{n}{8}, \cdots , 4 , 2, 1
$$
The number of operations is simply a question of how many terms are in the above description.  So we need to answer what function predicts the decay of $n$ to $1$ if the decay rate is $\frac{1}{2}$ of the size of the remaining subset at each step. The answer is:
$$
\underbrace{n, \frac{n}{2}, \frac{n}{4}, \frac{n}{8}, \cdots , 4 , 2, 1}_{\log_{2}n}
$$
In other words, the number of terms defines the efficiency and the efficiency of binary search in the worst case is:
$$
O(\log_{2}n)
$$

Consider an ordered search set with 10 elements containing the following values: 24, 32, 41, 42, 51, 63, 71, 73, 85, 87.  If we search for a search value of 45 in the search set using binary search, the process is illustrated below. 

![](/home/jrt/gwu/course/cs1112/assets/search-binary.png)

The grayed out boxes represent values that are eliminated from further consideration in the search set at each step.  The dashed circle represents the middle element of the remaining search set at each step and the single value compared to the search value at each step. As a result, this process requires a total of four comparisons to confirm that the search value 45 does not exist in the search set.  At this point we would need to determine the relationship between the number of elements in the search set, $n$ and the number of circles.  This relationship was predicted and modeled by our mathematical analysis above, but the general relationship, considering that this is a discrete problem and $2^3 < n < 2^4$ where 4 is the number of comparisons, then the efficiency is logarithmic or $O(\log_{2}n)$.

Here is another way to look at it.  Binary search repeatedly reduces the search space with initial size $n$ by half until the search problem is simply comparing whether or not one remaining element is the search value.  

If $k$ represents the number of times the search space is reduced in size by $\frac{1}{2}$:
$$
\underbrace{\frac{1}{2} \times \frac{1}{2} \times \cdots \times \frac{1}{2} }_{k}
$$
Simplified as:
$$
\frac{n}{2^{k}}
$$
We are trying to solve the above equation for when there is one remaining element in the search set because any remaining operations are constant time for a set of size 1.  We can now formulate the problem:  
$$
\frac{n}{2^{k}} = 1
$$
Recall that we are asking "how many reductions" which is what $k$ represents, so our goal is to solve for $k$ to find out how many times this process needs to be repeated until it reaches the end:
$$
n = 2^{k}
$$

$$
2^{k} = n
$$

Cancel the base to isolate $k$ and answer our question:
$$
\log_{2}2^k =\log_{2}n
$$

$$
k =\log_{2}n
$$

So, in the worst case where the search value does not exist in the initial ordered search set, it takes at most $\log_2{n}$ reductions until the search set is reduced to a set of one element leaving us only one question as to whether or not that one element is the search value.  Therefore the time complexity of binary search where $n$ is number of elements in the array is:
$$
O(\log_{2}n)
$$
Because this is the maximum number of comparisons necessary to determine whether or not an element exists within an ordered array when we use this binary search algorithm.

### Pseudocode

**Binary Search (Existential):**

```pseudocode
search(A, v, l, r) → ordered set A, search value v, search region [l,r] 
				   : true if v is found in A, else false
	if l > r : 
		return false

	mid = (l+r) / 2

	if A[mid] == v : 
		return true
	if A[mid] > v : 
		return search(A, v, l, mid-1)
	if A[mid] < v : 
		return search(A, v, mid+1, r)
```



**Binary Search (Accessible):**

```pseudocode
search(A, v, l, r) → ordered set A, search value v, search region [l,r] 
				   : non-negative index of v if v in A else -1
	if l > r : 
		return -1

    mid = (l+r) / 2

	if A[mid] == v : 
		return mid
	if A[mid] > v : 
		return search(A, v, l, mid-1)
	if A[mid] < v : 
		return search(A, v, mid+1, r)
```

## Generic Functions

The above algorithms are generically defined in pseudocode which is intentionally used to avoid the constraints of type imposed by Java.  This raises the question of whether we can similarly define algorithms and data structures in Java such that type is not strictly defined in the implementation.  In other words, can we define a search algorithm such that type is another parameter instead of a fixed requirement and the answer is yes by using generics.  There are both generic functions and generic classes but we will focus on generic functions here.

A generic function accepts a type as a parameter.  Typically we use the `T` symbol to indicate a generic type (we can use other symbols, but by convention we typically start with `T`).  Syntactically, the angled braces along with an inscribed `T`, *i.e.* `<T>`, before the return type signals to the compiler that the function is a generic function.  For example, the following function `genericFun` is an example of a generic function:

```java
	public static <T> void genericFun( T x ) {
		System.out.println( x );
	}
```

The `<T>` preceding the `void` signals that `genericFun` is a generic function.  The `T` in the parameter list preceding the variable `v` holds the place of the type of `x`.   The generic type must be a reference type in Java passed to `genericFun` at compile time.  It is important to note that a generic type can only work on reference types in Java, so primitive types cannot be directly used with generics.  This might seem like a serious oversight; however, Java provides "wrapper" classes for each primitive type, *e.g.* `class Integer` for `int`, `class Float` for `float`, `class Character` for `char`, `class Boolean` for `boolean`, etc.   For example, using `genericFun` just requires calling the method with a value represented with a reference type:

```java
class GenericFunEx {

	public static void main( String[] args ) {
		genericFun( Integer.valueOf(5) );
        genericFun( Boolean.valueOf(false) );
		genericFun( new String("Hello") );
	}

	public static <T> void genericFun( T x ) {
		System.out.println( x );
	}
}
```

The above program outputs the following:

```console
5
false
Hello
```

A generic type is known at compile time, enabling the compiler to perform syntax and type checking throughout compilation to enforce type safety.

Now reconsider the Iterative Existential search again, this time in Java using a generic function:

```java
class GenericSearchIterativeEx {

	public static void main( String[] args ) {
        
        // generate an array of integers
        Integer[] arrInt = new Integer[5];
        for( int i = 0; i < arrInt.length; i++ ) {
            arrInt[i] = Integer.valueOf(i);
        }

        // use the generic searchIt function to search 
        // for specific integers in the integer array
		System.out.println( searchIt( arrInt, Integer.valueOf(4)) );
		System.out.println( searchIt( arrInt, Integer.valueOf(6)) );
        
        // generate an array of floats
        Float[] arrFloat = new Float[5];
        for( int i = 0; i < arrFloat.length; i++ ) {
            arrFloat[i] = Float.valueOf(i);
        }

        // use the same generic searchIt function to search 
        // for specific floats in the float array
		System.out.println( searchIt( arrFloat, Float.valueOf(4)) );
		System.out.println( searchIt( arrFloat, Float.valueOf(6)) );
	}

    public static <T extends Comparable<T>> boolean searchIt( T [] A, T v) {
        // iterate over all elements from beginning to end
        for( int i = 0; i < A.length; i++ ) {
            // use the comparison method implemented by any Comparable type
            // to compare whether the search value v is equal to the current element
            if( v.compareTo( A[i] ) == 0 ) {
                // if they are equal, the search value is found
                return true;
            } 
        }
        // if the process gets here, the search value was never found in the 
        // entire array
        return false;
    }
}
```

There may be some details that are not immediately obvious without further understanding of inheritance or other high level concepts and this is also not the only way to solve this problem; however, the above does address the question and allows us to write and maintain one function that implements this algorithm.  We could do the same for binary search or an other algorithm using generic functions to allow any type of object to be supported with a single implementation.  Similar principles allow us to implement generic data structures that ensure we can write one class to support any type of object. 

## Review

1. Why are we so concerned with the efficiency of search? Why can the efficiency of search act as a multiplier to the efficiency of virtually all other algorithms we develop or use?  Give an example.
2. What is the existential question in terms of set membership and why does it define worst case analysis of search?
3. Why is worst case analysis used?  Why not use best or average cases to analyze efficiency instead?
4. Summarize the strategy for Iterative Search
5. Summarize the strategy for Binary Search
6. What are the requirements for Iterative Search
7. What are the requirements for Binary Search
8. Define Pseudo-code for Iterative Search
9. Define Pseudo-code for Binary Search
10. Analyze the efficiency for Iterative Search
11. Analyze the efficiency for Binary Search

# 6 - Sort

Sorting means to structure the elements in a set with a specific order according to a sorting criteria which we may refer to as an ordered set. Data in arrays has a natural **positional order** corresponding to index due to the nature of the arrays; however, we often want to impose an additional order that allows and even utilizes the cross-referencing of positional order with a very specific order that facilitates more efficient searching beyond brute force iteration.  

> Positional Order: Computers really cannot model the abstract set without some effort due to the structuring imposed by memory.  Arrays are just contiguous segments of memory and are offset indexed from $0$ to $n-1$ based on the starting address of the array. This means that a positional order is always imposed on any data inserted into an array.  Whether further ordering is imposed is optional, but the positional order is an implicit feature in all arrays and can be useful feature.  In fact, we leveraged the relationship between positional ordering and lexicographic ordering in binary search to be able to reduce search efficiency from $O(n)$ for data with positional order only using linear search to $O(\log_{2}n)$ for data with both positional order and lexical order using binary search

Numerical data can be ordered from smallest value to largest value in **numerical order**. However, numerical order is not enough to fully specify the ordering of data in the set because data can be structured in **ascending order** or **descending order**. It therefore becomes very important to completely specify the criteria used to order data, *e.g.* ascending numerical order or descending numerical order. 

Data composed of symbolic sets like strings may be sorted using a **lexicographic**, **lexical, or dictionary order**, *i.e.* ordering based on sequences of symbols like the alphabet. Likewise, lexicographic order can be ascending or descending; however, alphabetical order probably suggests ascending order without further specification while an odd ordering like reverse alphabetical order would be expected to be explicitly specified.

Complex data structures like objects can be ordered as well, but the sorting criteria used will depend greatly on the nature of the data stored in the object and this sorting criteria may even be variable over the lifespan of the object. Consider that student data could be ordered by name or by student id or by a combination of the two. Why a combination of the two? Consider that names are not unique so to generate a highly consistent sort structure, the name is the primary order element but if two students have the same name their records are further sorted in a secondary order by student id. We might generally refer to the ordering of objects as a **composite order** or **custom order**.

Complex data structures raise a number of questions about the implementation including how to implement simple comparison operations like less than, greater than, and equal to that are necessary to determine order.

In this section, we will explore different strategies for sorting that have been formalized into algorithms over the last century and we will analyze their efficiencies in a number of different ways. However, before we dive into different sort strategies, we first have to understand that sorting is built on one of the most basic yet fundamental algorithms for ordered sets, swap.

## Swap

To swap is to exchange two elements. Given the interface `swap(A,B)`, the intent of executing the swap algorithm is to exchange the value stored in `A` with the value stored in `B` such that when the algorithm completes the new value in `A` is the value that was originally stored in `B` and the new value in `B` is the value that was originally stored in `A` before the swap was initiated. For example, suppose `A=1` and `B=5` and `swap` is performed on `(A,B)`, the result will be `A=5` and `B=1`.

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXedBEr0_y55V6kACMi0X6YOKnpnShXfDQ1vQqAGY3jxv9flVkT_2qG--p5FAj4efjuPdKl5p6s3hDAY9DC0B7nbN4FKC5ksd_DUR-hHNvbsVpEL3qtgghJmdFaFcW8pjTkTsbK1?key=KEi1pMKVOxS1gZVpUrUYW_Ab)

Conceptually this should be a straightforward algorithm; however, there are a number of problems that may arise when implementing it in a specific language. There are at least two problems if we tried to directly implement the above process in Java.

### Nuances of swap in Java

Consider the following swap operation implemented in Java:

```java
int A = 1;
int B = 5;

// swap(A,B)
A = B;
B = A;

// end of swap
```

Why does the above code fail to correctly perform the swap operation?

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXelf1odTSz45QPUdV37JTilFiL1VtX8caiND-z4GAo03a8Qo92qkHegJaA65X42Gdv1VhV0JkwxwY4EeixFjDDt0-Tkp5bDU_mZqI84dQRWEYEV89UEvDpIGcFB2pT-1FIU1IWL?key=KEi1pMKVOxS1gZVpUrUYW_Ab)

The problem is that the original value of A will be overwritten and effectively destroyed by the `A=B` statement. The original information in `A` is lost in the process, so when the `B=A` statement is reached, no net change occurs because `B` is being overwritten with its original value. How can we resolve this issue so that swap is carried out successfully? Consider the following adjustment to the implementation:

```java
int A = 1;
int B = 5;
int temp;

// swap(A,B)
temp = A;
A = B;
B = temp;

// end of swap
```

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXegzr6GwCPNhJFVMe9T7dvWIAVnX9TNEP41yk7XTvfer8-hYMjOZ5FpEi8XX_A3vVNjK6DVMOibCRxQqJGAPmug63wYEEfd0iH8jnav4P51yqpiZ03HZ2Th-wQxNtsylgltfrmt?key=KEi1pMKVOxS1gZVpUrUYW_Ab)

The introduction of the temporary variable `temp` resolves the issue as now the original value of `A` is preserved in `temp` and even though `A` is overwritten in the `A=B` step, the original value of `A` is available in `temp` which is why it is assigned to `B` in the step before returning from `swap`.

The second issue with `swap` is a consequence of the relationship between local variables and the stack. When a function is called, the input arguments are copied to the function’s parameters which is a form of protection called **pass-by-value**. In other words, the Java policy for passing arguments to functions is to pass-by-value which means that manipulation of the variable inside the function results in manipulation of a copy of the argument. 

Whether or not changes to data in the function is reflected after returning from the function will depend on the metatype of the parameter. If the parameter is a primitive type, the parameter is always deep copied in Java when the function was called, so any changes to that parameter inside the function will be completely discarded when the function returns. If the parameter is a reference type, a shallow copy was made when the function was called, so any changes to the reference itself are discarded when the function returns but any changes to the parameter's referenced object are permanently changed. Consider the following example:

```java
void swap(int x, int y) {
    int temp = x;
    x = y;
    y = temp;
}
```

Because `x` and `y` are input parameters, `x` and `y` are also local variables allocated on the stack. When the end of the function is reached, the stack frame containing these instances of `x` and `y` are forever removed from the stack and are lost. Stack memory for a given function only lasts until the function returns, so the results of this function are transient and lost at function return.

Alternatively, consider the following Java implementation:

```java
void swap(int[] A, int i, int j) {
    int temp = A[i];
    A[i] = A[j];
    A[j] = temp;
}
```

Input parameters `i` and `j` represent the indices of the elements in array `A` that are to be swapped. Assuming that `i` and `j` are within the legal bounds of `A` and `A` is a legal reference, the implementation will swap the value in the `i`-th position with the value in the `j`-th position of `A`. This change will be a permanent change because `A` is a reference to an object on the heap where the exchange is actually carried out. Heap memory does not delete an object until there are no references remaining to that object and the calling region of code must pass in a reference to an integer array, so the change will be accessible in the calling region of code.

## Stability

*Not covered at this time and not a topic for quizzes. This note is to introduce this idea in future course content and to flesh out this section. For CS majors, you are encouraged to look up sort algorithm stability for a comprehensive understanding.*

A simple summary of stability is to maintain order among like elements. If there are two 10’s in a set, the first 10 should remain the first 10 even after sorting. A stable sorting algorithm guarantees that this order is preserved while an unstable algorithm does not. 

## Sorting in Place

When sorting, we are really moving data from an unsorted set into a newly sorted set. If performing sort on an array, this might lead us to introduce an additional array and copy data between the unsorted array and the newly sorted array. For reasons hinted at in the discussion of pass-by-value (beyond simple considerations of space efficiency), it is often not practical to use a new array and sorting needs to instead be done as efficiently as possible in the original array. Sorting the original array is called **sorting in-place**. Sorting in-place alters the original data but this is often fine because replicating the same data twice is redundant. if two copies are necessary, the original array can still be deep copied and the copy can be sorted in-place. To identify the two sets during the sorting processes, this text will use terminology and graphics to discriminate between the sorted and unsorted sets in one array.

## Selection Sort

Selection Sort is arguably the most straightforward and natural strategy people typically use to sort data. It is based on the process of locating the smallest value (assuming the sort is ascending) and placing that value in the smallest position. The process is then repeated on the remaining elements which results in the second smallest element placed in the second smallest position. There are two critical flaws with this process: it is not possible to determine whether or not an element is the smallest element until it has been compared to every other element and only one element can objectively be known to be sorted with each pass through the data.

Given an array with the following data:

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXe8b0CJU7cE3QxJf3_-qDkpLz_f5o4twXl728P5SfJiGuoz9pEi4OmreWAuIl8ZjbImWuiAgDPdn8GkSS4S718EmLbQHwdh4s16PqtdGLBlE3JgV4_WMkXGy4qe31UJW4ApuLCp5w?key=KEi1pMKVOxS1gZVpUrUYW_Ab)

This initial array represents a completely unsorted set on which we wish to perform Selection Sort. Suppose this array is to be sorted in ascending numerical order.

Selection Sort makes an initial selection of the first value in the first position. Independently, the selected value is tracked by position in the array and the position that is being selected for is also tracked.

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXeW7INCukDtWJfc8eBtCaaNwaQxgzcyI3B6eC-5dXejwtdWzS6R4tGjunmWS1pS8oI7t4mX9tTDwpHswXn25yHOLQx0NiXO9SEy4jTYwSsloDPyGVk8Hd0VMYhfykgVOltSZDMrSg?key=KEi1pMKVOxS1gZVpUrUYW_Ab)

In the initial pass, selection sort scans (iterates) through all values and compares the next candidate value with the selected value. If the candidate value is less than (this specific comparison is used because sorting into ascending order) the selected value, the candidate value becomes the new selected value and the position of the new selected value is stored for future comparisons and a potential swap once the pass is completed. 

In the example, the first comparison asks if 51 is less than 32 as 32 sits in the first position of the remaining unsorted set:

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXeweBkrSRHj6p3LsflU32yjV0Q1Pwv4T1i-f_Fj90Lou6aS-1D6qHjFBUF3MQULkfAf4ptJw2bWSGpzII2dZYVOfJPSKuufh8KefWDkCGwW7Hg-xj_LXfJtpjtGHtThMItiWlkS4A?key=KEi1pMKVOxS1gZVpUrUYW_Ab)

Because 32 is less than 51, 51 cannot be the smallest element in the unsorted set and so 32 replaces 51 as the current selection. Specifically, the selection algorithm starts tracking index 1 as the location of the smallest element.  Any swap will be performed only once all elements in the unsorted set have been compared.  The goal of the pass is to select the smallest element among the unsorted set and a separate step after the pass will swap the value into its correct position. 

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcw9IPt8fnsNAya8nQYaw64ebO43tODOYTGnDUiQ5GOGCS5Osr3NAiLMQGSRVG8x8LVvkHNiGATKjPwMx2XAs2JgPSZT5tyM1iWtk-TuGRSLOYJ6Vq_fdMCAHC4Yl9Elpc4kk7dCA?key=KEi1pMKVOxS1gZVpUrUYW_Ab)

Selection Sort will continue its initial pass by comparing the new current selected value with the next candidate. In this case the next candidate is 73 which is not less than the current selected value of 32, so 73 is ignored.

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXeVAz3Q2s17iakKaOqXWY1Nyxh5s4bBvqE-nux_Yo62gJ34yymEUkD7vf8Zg84cpS24G33r76y4rwNKKWtl1eavngdC2DXxAC5JkfJpYO1nswvVthFu-U7zhmkiXUJv8w1T-Rtnbw?key=KEi1pMKVOxS1gZVpUrUYW_Ab)

Selection Sort continues to compare candidate values including comparing 63 with the current selected value of 32, and because 63 is not less than the current selected value, 63 is ignored.

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdbEGNpBJ-bNlNorXI9BjO2gg5Bib1ViWi7w6GFNuUyszteSEyiCzLNBY39v8Hzf98QKVkIgkCgkix9s5qvIq1KUMkjNd0-ZgpOFWKsfNkEQ5SH-e8eeZdBNw4L9nRRqrg6EhzXPg?key=KEi1pMKVOxS1gZVpUrUYW_Ab)

Selection Sort compares all remaining values to the current selected value but does not find a replacement until it reaches the last value in the array. 24 is compared to 32.

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXeZWEkSHN2I1ecKuvmONkI8zsEZnNARtey4tuOWVO1Rsr2Aid5slm80Cl6g3utAwutkMMrtUr3p5GuHsU-paheBnUff1A0YgkUSVrkHUpqx2TSQFzGb4vZBn5AgTMr_-lXZiX6WTw?key=KEi1pMKVOxS1gZVpUrUYW_Ab)

Because 24 is less than 32, 24 becomes the current selected value.

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcsUYqqPbaOBdru5SGzb-yJCfxxIsOAyBkmAWblmEqdZ4EW7uQAk85RmRUBqc8Q-LpE-Yjj6tnFcEJ2IsCPPLC6XN-Wf9lNYm2cNci2yy2rd8qVqHpMzfnlV953a9TPy4aYcSz3aw?key=KEi1pMKVOxS1gZVpUrUYW_Ab)

Because Selection Sort has reached the end of the set, there are no further comparisons to be made and the minimum value in the unsorted set must be the current selected value. The current selected value is only now swapped with the selected position.

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfwyKFuBrjnene3nqL02o2xDr46cZT11urlzoB4s90FRNHu_D3Ddu9wmF30CSO6RPJ72PFwqHrks5ZBnV1FpBgXCV441NKL1bDqApji1KMiKripbKFCtZLBCDh1Bz4QuBlfFVsVDg?key=KEi1pMKVOxS1gZVpUrUYW_Ab)

Once the swap is completed, the smallest value is guaranteed to be in the first position of the array. We can imagine a dividing line between the 1st and 2nd position where elements to the left of the division belong to a sorted subset and elements to the right of the division belong to the remaining unsorted subset.

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcvgeTy8nQuIeZfqqdQjaH92vVx25r9I0ggfWLxKCm_RsqCXo3ROeOsjwmLpeJ2G_aeCY4O_5dUoe9e2X5qBZtDVbi5zUZqH1uS28TkU_vFwjFMZiYCrF4GzHaGgBNn6uMv2YOG-w?key=KEi1pMKVOxS1gZVpUrUYW_Ab)

With each pass, Selection Sort is selecting the i-th smallest element of the overall set, but more simply, Selection Sort is selecting the smallest element of the unsorted set which should suggest that there is a recursive approach to this problem. In other words, the unsorted set is being reduced in size by one element with each pass and eventually the unsorted set will become a set of size zero.

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXd4LXIXxra8EHUmVNsYP96PvFT9NEnTFSCvc1s9qJqmHqPNDOIIDWHCQQFAHDZGxMtquJdxw0L4OOMgxNxmqH-EUq3T3Qf1mmBrD_WXWaDg0H5o8Mfs005M5mVeGbA4CIRD81TbKQ?key=KEi1pMKVOxS1gZVpUrUYW_Ab)

Selection sort makes multiple passes through the set. The general result of a single pass through the data is that one element is placed into sorted order, the unsorted set shrinks by one element each pass, and the sorted set grows by one element. This pattern can be visualized in the following way where the gray box represents the sort position, solid outlined boxes represent members of the unsorted set, and dashed outlined boxes represent members of the sorted set. The general result is consistent up until the last pass where two elements are sorted which occurs because selecting and sorting one element of a two element set puts all elements in order.

  

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXc2qiCbxG-irl7ptqGglwLxcHvRN0sINWVuKp4cwmCGtivZpAqQhT94yozhsL2pxs4Nq82BWXUVP3TjFL5DT00vFOirYmsSXMC_qzB2cfoICUapEnarDvwqYTDCLsR8em0eiubp7Q?key=KEi1pMKVOxS1gZVpUrUYW_Ab)

The above diagram can be generalized into the following diagram so that we can do an inductive step in the mathematical analysis.

| ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXf-2CB0dM1zponk_QPCWKJJX83UviKp47fcMyzVrUcwRAW5B5QH-pd2HELlmBl1tny2l88fbJJbNDTtkJ5KEvoj22YBpEeroVl078BNJTB4J6LQ3NOKqJOfzMUb-zN4kqyN6yLxsw?key=KEi1pMKVOxS1gZVpUrUYW_Ab) |
| :----------------------------------------------------------: |

To the right is illustrated the number of comparisons performed in a pass. On the first pass, n-1 comparisons are needed to put the smallest element into its sorted position, on the second pass, n-2 comparisons are needed to put the second smallest element into its sorted position, on the second to last pass, two comparisons are needed to put the third largest element into its sorted position, and on the last pass, one comparison is needed to put the second largest and the largest elements into their sorted positions. From this model we can perform a formal mathematical analysis.

### Mathematical Analysis

Where $n$ is the size of the input.  If we sum the values along the right side, we get the following expression that represents the total number of comparisons for Selection Sort:

$$
(n-1)+(n-2)+(n-3)+\cdots+3+2+1
$$
We know that there are a total of n-1 terms in this equation from the diagram above: 
$$
\underbrace{(n-1)+(n-2)+(n-3)+\cdots+3+2+1}_{n-1}
$$
Assuming that $n$ is an odd number, $n-1$ is an even number and the number of constants on the right of the expression equals the number of terms on the left of the expression:
$$
\underbrace{(n\cancel{-1})+(n\cancel{-2})+(n\cancel{-3})+\cdots+\cancel{3}+\cancel{2}+\cancel{1}}_{n-1}
$$
Assuming the $n$ is an odd number is a just a convenience for us to reason this out.  Since this is a Big O analysis we will be dropping coefficients and smaller terms, so it does not really matter whether $n$ is odd or even other than to simplify our math model during the analysis.

Since cancellation has eliminated all constants, half of the terms in the expression are eliminated and the equation is reduced to a summation involving elements with only a value of $n$: 
$$
\underbrace{n+n+\cdots+n}_{\frac{n-1}{2}}
$$
By the definition of multiplication, we can simplify the above expression into the following: 

$$
n\cdot\frac{n-1}{2}
$$
Distributing $n$ gives us the following equation:

$$
\frac{1}{2}n^{2}-\frac{1}{2}n
$$


Since we are performing time complexity analysis, we can drop all coefficients and lesser terms to arrive at a big O estimation of $O(n^{2})$.

The formal mathematical analysis is involved and requires a solid mathematical foundation to reach a correct conclusion. This might lead us to a search for another, easier way to analyze the data in the abstract without relying on extensive mathematical skills.

### Graphical Analysis

One of the features of Big O is that it is an estimated and abstract form of analysis and it is not necessary to compute coefficients and constants for most general programming. The same analysis can be performed by looking at the dimensionality of the process which does not require the same depth of mathematical expertise.

Where $n$ is the size of the input, the earlier diagram of can be generalized as Selection Sort performs approximately $n$ passes (iterations) through the data and for each pass it performs approximately $n$ comparisons among $n$ elements. In other words, it performs $n$ iterations and operates on $n$ elements per iteration. From this we can estimate that it has a Big O of $O(n^{2})$,

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdPSTn1z4L3uOO53pps0icDDWQvPRItF5tOK3QYOVffQsVPe-9yQvOpazYPGvO-P-vMbgT5i9BOielNfDHNFvqyXCwLTAiQSxmKBcemdarV_wyeeOxrQhdB4Zg7yk0TxR5R4l-hww?key=KEi1pMKVOxS1gZVpUrUYW_Ab)

The above techniques may be useful, but algorithms are expressed in code, whether pseudocode or in a specific language. This suggests the need to develop the same analytic tools only more code centric. 

### Pseudocode Analysis

The pseudo code for Selection Sort can be expressed as the following:

```pseudocode
Input : E is the input set and is considered unordered
Output : E is sorted in place, so E implicitly returns as the ordered set selectionsort(E):
	for i = 1 to length(E):	
		selected = i	
		for j = i+1 to length(E):		
			if E[j] < E[selected]:			
				selected = j	
        swap(E[i], E[selected])
```

This raises the question of how Big O efficiency can be estimated from the code above.  The answer is deceptively simple for Selection Sort, but this simplicity should never be assumed without careful consideration of an algorithm.

Where $n$ is the size of the input, $n$ is equal to `length(E)`.  The maximum bound of the outer loop would result in $n$ iterations and the maximum bound of the inner loop would result in n iterations. In other words, for a single iteration of the outer loop, the inner loop iterates on the order of $n$ times and therefore for an approximate total of $n$ iterations of the outer loop the innermost block of code is repeated approximately $n \cdot n$  times.  This indicates that the algorithm is $O(n^{2})$ in the worst case. 

Selection Sort could be described as a brute force algorithm that uses a grand strategy of finding the smallest value in the unsorted set and putting it in the largest sorted position of the sorted set.  This strategy comes at the price of an $O(n^{2})$ in the worst case algorithm.  Can Selection Sort ever do better than $O(n^{2})$?

### Best Case & Average Case

As it turns out, there are no possible optimizations or data configurations that allow Selection Sort to ever perform better than $O(n^{2})$.  In other words, Selection Sort’s best case and average case equal its worst case and it performs as an $O(n^{2})$ algorithm under all conditions.  This is a weakness of its strategy as it can never know if it has selected the best candidate in any pass until it has performed comparisons with all other elements remaining in the unsorted set. 

Are there algorithms that do not suffer from this limitation? It would be beneficial to have a sorting algorithm that even though it might be $O(n^{2})$ in the worst case can perform better in the average or best case. 

### Stability

Selection sort is an unstable sorting algorithm

TODO: Illustrate

## Bubble Sort

Bubble Sort like Selection Sort is a brute force sorting algorithm; however, Bubble Sort builds its strategy on a simple, localized technique involving neighbor comparison. In short, Bubble Sort iterates through the array, compares each pair of neighboring elements, and exchanges them if they are out of order. If this process is repeated frequently enough on all the data, the data will eventually reach a sorted state.

Given an array with the following data:

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXe8b0CJU7cE3QxJf3_-qDkpLz_f5o4twXl728P5SfJiGuoz9pEi4OmreWAuIl8ZjbImWuiAgDPdn8GkSS4S718EmLbQHwdh4s16PqtdGLBlE3JgV4_WMkXGy4qe31UJW4ApuLCp5w?key=KEi1pMKVOxS1gZVpUrUYW_Ab)

This initial array again represents a completely unsorted set on which we wish to perform Bubble Sort and again suppose this array is to be sorted in ascending numerical order.

Bubble Sort starts at the beginning of an array and compares the first two neighboring elements, *i.e.* elements at indices 0 and 1.

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcLdQlwKQuYnUFA956zZRexFZHH0K17d9lw6Nmf4yP-vkFTnE5do4Yfd4BCLklbuHubRMM-Ud0wz4SbYyLw6a2ETaR3KG7ttbGGT-F9vcSwKE2lRJy2kqT3Up4HBZxAUlgKArYOIA?key=KEi1pMKVOxS1gZVpUrUYW_Ab)

In the case of the first pair of neighbors, 51 is greater than 32, so this pair is out of order and this pair of neighbors need to swap positions to locally order the two which will increase the overall order of the set.

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXffbU25PjV3aoGTMTs9u4j2V4u5j-wVHr3Xhid2DbbNqW4FlT7Qe1_vuhfF0wXaKzugXR4GXB5hYQLVCwUZQ5JaPM0uMnrgecBvHfyZ6WBMFLoV5otFEger_Z6w61m5Omg8uf1gXQ?key=KEi1pMKVOxS1gZVpUrUYW_Ab)

After the first pair of neighbors are compared and if necessary swapped, the second pair of neighbors is compared. The second pair is composed of the following element (the element that landed on the right side at the end of the comparison and potential swap) from the previous comparison and the element to its right, *i.e.* elements at indices 1 and 2.

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdGPLGyCGoXioPLOn-MN0rkIJc2KyR_yvWwT1bhHDatoj8MNkso_ukx7Z56fI7KTkeOphdiuMZexQ--YiVG0jI_FrdrlpaalMDIt2M3Cf0pu3ntY0MCdhlKyPsktvRQos1Gh9tvmw?key=KEi1pMKVOxS1gZVpUrUYW_Ab)

The second pair of neighboring elements is already in order.

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXewj16ELsqp-Ky4_8gIo6SZtluA1ah4ngdcL2sG9fAmZQJT1-MRfC7RsfPlHL4xq8r6kHWtiABSspitntBEGMncZ5dgBnL1HpOJFhLhKx7du-3eSnrYmmO_UoxEB9QyEgVAqVsw?key=KEi1pMKVOxS1gZVpUrUYW_Ab)

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdBeplynk2TCH2ipoVQ0Odq3Nj5QSywjWOPoTkT3XFyMIVRo4RzDUFXw1hg6jCuWPGctB7XIyY0MLe0O15phB4Q7fPdb-sgKwBkN4F_a5VK9MkhSKz_SvCtfqDpUgoNZhQXZm0nBw?key=KEi1pMKVOxS1gZVpUrUYW_Ab)

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcSJVZOBYm0SwYgdrwQHWxWaHLvMzvY-0IFRUaPMCVdU7IumR_wrPY9PmvoufCdZbUy_J5gxT21aIMppkIm55wbN-90PYfSS1aTMBVOKwo_N5BoaWaMsbzlZ7IQeTURm6LaMFaFoA?key=KEi1pMKVOxS1gZVpUrUYW_Ab)

At the end of the first pass the array has the following order.

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXc4ciOunxf-OsQ6uxEJNmYPrxgud1wEtdw0Ane3q8DVY3lGETyvr6Ow3IQzZmukQnSmVSoLTyEuuCwsYf45Xv9bAAEt8ol_wVxwSQRdWqADi1CFg-9S-_h-Ps2xQqb5pF3sgNkYzw?key=KEi1pMKVOxS1gZVpUrUYW_Ab)

Note that the largest number has landed in the rightmost spot and at the completion of each subsequent pass at least one element, *i.e.* the largest remaining element in the unsorted set, is sorted into the sorted set. The block diagram for Bubble Sort tells an almost identical story to that of Selection Sort except that the diagram for Bubble Sort is the mirror of that for Selection Sort.

| ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcMod_UaJhwzPpiKvVgrMAqUREiCzALLe8x7PCDbxqWLvlwtw_WFC6w86NQH2ejOlFEzpd9QGBDrfjvoLVdEFLYKgyDYaaQu5aRKMHNPonwKJHyk1dJ8Oj_-aZpMqDyeLTZs95bdA?key=KEi1pMKVOxS1gZVpUrUYW_Ab) | ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXc2qiCbxG-irl7ptqGglwLxcHvRN0sINWVuKp4cwmCGtivZpAqQhT94yozhsL2pxs4Nq82BWXUVP3TjFL5DT00vFOirYmsSXMC_qzB2cfoICUapEnarDvwqYTDCLsR8em0eiubp7Q?key=KEi1pMKVOxS1gZVpUrUYW_Ab) |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| Block diagram illustrating Bubble Sort in the worst case.    | Block diagram illustrating Selection Sort in the worst case. |

For this illustration and implementation of Bubble Sort, one sorted set element is guaranteed to be sorted each pass and the sorted set aggregates to the right side of the array while the unsorted set is reduced from the left side of the array. As before, the gray element illustrates the position of the element that is guaranteed to be sorted at the end of each pass.

Bubble Sort is built on the idea that increasing the local order of a pair of elements increases the order of the overall set and if this process is repeated enough times, the entire set will become ordered. The overall efficiency depends on what is “enough times”. The block diagram illustrates that in the worst case Bubble Sort has the same efficiency as Selection Sort.

### Mathematical Analysis

As the block diagram above suggests, the mathematical worst case proof for Bubble sort is identical to the proof for Selection Sort. Refer to the section on Selection Sort for a detailed analysis.

### Graphical Analysis

The similarities between Bubble Sort and Selection Sort block diagrams suggests the same inductive technique is used to estimate the efficiency of Bubble Sort in a dimensional analysis. The generalized diagram for Bubble Sort is also a reflection of the Selection Sort diagram.

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcFP0njd5Joq3DtN8aKSa_-eLgYGswzDcjeB1U1sxbwxvLMf1O06iXIVzmCVxFKKl-f6iTtqlNgLdT8-QTO6cWUxE9GkJx6EVPBBP-aTNzegWSLjN1oCPDYXi4_XdMd2FZfu_vVjg?key=KEi1pMKVOxS1gZVpUrUYW_Ab)

From this we can estimate that Bubble Sort is Big O of $O(n^{2})$ where $n$ is the size of the input.

### Pseudocode Analysis

The pseudo code for Bubble Sort can be expressed as the following:

```pseudocode
Input : E is the input set and is considered unsorted
Output : E is sorted in place, so E implicitly returns as the sorted set
n: the size of E
ei: the ith element of e
ei+1: the neighboring element to the right of e 
bubblesort(E):
	for i = 0 to n-1:
		for j = 0 to n-i:		
			if ej > ej+1:			
				swap(ej+1, ej)
```

As in Selection Sort, the maximum bound of the outer loop would result in $n$ iterations and the maximum bound of the inner loop would result in $n$ iterations which indicates that the algorithm is $O(n^{2})$ in the worst case where $n$ is the size of the input. 

Bubble Sort could also be described as a brute force algorithm that uses a relative, neighbor comparison strategy to produce a sorted set. This strategy comes at the price of an $O(n^{2})$ in the worst case algorithm and also raises the question of whether or not Bubble Sort is $O(n^{2})$ in the best and average cases.

### Best Case & Average Case

While Bubble Sort has the same efficiency in the worst case as Selection Sort, there may be an objectively supportable argument that Bubble Sort is a better algorithm than Selection Sort depending on Bubble Sort’s performance in the best or average cases. The original algorithm proposed above struggles with the same deficiency that existed in Selection Sort, *i.e.* there is no way to exit early; however, not all inputs are the same. 

Consider how long Selection Sort will take on an ordered set:

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXeLm72pwCnK4eV_6zZmmIQ9_YW2kUoiGqV3pzqOvqgo3eEb9UKDoqoLQnFUhXOm8gdPHplRbkkcpXl0d_8Tct1cS7avaJVK0dYH1wRkGT3KCeBLL8a8Oa8DzX8UbEQSaohiRPDCCg?key=KEi1pMKVOxS1gZVpUrUYW_Ab)

With Selection Sort, there is no way to determine if the set is already ordered, much less a way to exit the process in an operation in the middle of the process results in an ordered set.  Selection Sort is designed to put the $i$-th best element in the $i$-th position and the $i$-th best can only be operated on when all proceeding positions have been validated through selection.  Selection Sort is a more holistic approach in terms of ordering the entire array and is a distinct contrast from the more relative, neighborly approach of Bubble Sort.  Since these approaches are so different, it raises the question of whether or not it is possible to alter Bubble Sort in a way that allows Bubble Sort to exit the process early if the set is ordered.  

Consider this question, what is indicated in Bubble Sort if it completes a pass and a swap is never performed?

Remember that if a pair of neighbors are out of order, Bubble Sort swaps them when it encounters them during a pass.  If we complete an entire Bubble Sort pass through the data and no swap is made, the data must already be in order.  Any subsequent passes through the data will not alter the order of the data, so they are wasted operations.  Armed with this information, let's improve the initial Bubble Sort algorithm to detect when a swap is not made during a pass and exit the algorithm at that point.

```pseudocode
Input : E is the input set and is considered unsorted
Output : E is sorted in place, so E implicitly returns as the sorted set
n: the size of E
ei: the ith element of e
ei+1: the neighboring element to the right of e 
bubblesort(E):
	for i = 0 to n-1:
		swapped = false             // set swapped flag to false at start of pass
        for j = 0 to n-i:		
            if ei > ei+1:			
                swap(ei+1, ei)			
                swapped = true      // flip swapped flag to true if swap is performed
        if not swapped:             // after completing pass, check if swap NOT performed
        	done                    // if no swap, then data is in order, get out
```

In the revised approach to Bubble Sort, a boolean “flag”, swapped, is used to determine if a swap is performed during a pass. The flag is set to false at the beginning of a pass and if a swap is performed during the pass, the flag is switched to true to indicate that a swap was performed during this current pass.  It does not matter how many swaps are performed, it only matters if at least one swap is performed.  If no swap is performed during a complete pass through the data, no further swaps will be performed in any subsequent passes and the data must be in order.  If the data is in order, there is no need to continue the process.

### Stability

Bubble sort is a stable sorting algorithm

TODO: Illustrate

## Insertion Sort

Insertion Sort uses a similar neighbor comparison strategy as Bubble Sort, but it makes use of an observation about the sorted set to minimize the number of unnecessary comparisons and swaps that may occur in Bubble Sort. 

Bubble Sort and Insertion Sort are similar, but there is an important and subtle difference in their design principle. In a single pass, Bubble Sort guarantees the extreme-most unsorted element propagates to the end of the sorted set where it joins the sorted set in its correct position. In a single pass, Insertion Sort guarantees that the current element is inserted into the sorted set at its correct sorted position relative to the other elements in the sorted set. In other words, Insertion Sort finds the correct position for the next element in the sorted set with respect to the elements in the sorted set while Bubble Sort sorts the i-th smallest or largest element into its absolute position in the sorted set. In this respect, while Bubble Sort uses the neighbor swapping strategy the overall behavior is more similar to Selection Sort than it is to Insertion Sort.

Given an array with the following data:

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXe8b0CJU7cE3QxJf3_-qDkpLz_f5o4twXl728P5SfJiGuoz9pEi4OmreWAuIl8ZjbImWuiAgDPdn8GkSS4S718EmLbQHwdh4s16PqtdGLBlE3JgV4_WMkXGy4qe31UJW4ApuLCp5w?key=KEi1pMKVOxS1gZVpUrUYW_Ab)

For Insertion Sort, it is difficult to discern what is going on from the initial few passes, so the following examples start at sorting the element at index 4 into its correct position in the sorted set. At the beginning of this pass the array has the following state:

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXc7l3rwcXRxbvPocNgdMBwKPkbj0FAqoTQkr_5Ha_c5LEqGq0MQmOqfcYeWFr5BPRsYVxEwUUI6S6t69C55fGFGbfLceDBxhy3VHgtGxlyalVNUmow10ZGvt_MnUIcxevsAPxoC?key=KEi1pMKVOxS1gZVpUrUYW_Ab)

The sort element, as indicated by the dashed circle, with the value 42 is compared with the element to its left, *i.e.* the rightmost (largest) element in the sorted set here at the first comparison, 72.

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdt6n-Y3Qbpp-1DFifwZnArt28qC4LAGSw5LIIEiOhCDqfoF9LK6zn-2WfBuuGIDh4QcMfZtop_UIqbsVf4s5hX3VNuV7qlxQAcPWyYQeZBCV1mGUW6AD9TSu9e4fLvbhr2dLyt?key=KEi1pMKVOxS1gZVpUrUYW_Ab)

If the sort element is less than the element to its left, the two values are swapped and the process repeats as is the case for this example, *i.e.* 73 > 42 so they are out of order and must be swapped. 

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdoWGenfymlWp8AH0ygJiXc9HqvSPFpEUeihaozncR5TA23aRk1OQqVdRzzWlGV5_y2q43-zv9bJqB4OuXWFU8-BiNa7m_iNiNLmdSNoSZmyHIw66c6CHS2hEZrbHIwS1JCZrbJ?key=KEi1pMKVOxS1gZVpUrUYW_Ab)

The process repeats itself where the sort element is compared to the next neighboring element to its left.

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcOwKKs8VjWGNU69xnMxyNkxHWlDaKjoptmK1paoY6bbKCT6wDeeD7Ovqftr2yf_UscQ4ZZFGbPXX5v6NJ3F1hzjfg032saA4l6OcnJq_rv2ArwYSW6-s13Bchs0WbKNMV1wQGN5w?key=KEi1pMKVOxS1gZVpUrUYW_Ab)

Again, if 42 is less than the neighboring element, they are swapped.

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXf1V0NqiKrlvFyGn08uT5kJqf7FugjzpyV3VRubBagZWVzKyNnG-wRkCU9UOVbMUAgln3BUOq0tG_euJT7xU9YJ7AvG-s-Lalpn4vRmru6vDKVQ6lOasTuYmZ1Ioj4DxZOIPZ3U6w?key=KEi1pMKVOxS1gZVpUrUYW_Ab)

This process is repeated as long as 42 is less than subsequent neighboring elements. 

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXeAwPF5dvYBWMAMawaYy9MnEiZUYQPIMwidPyyQih_mNIBJueLwpx42bok9nVogZ_pejHv6gujznaDO4Y-2fn8hVCVLEaJLMz3rIJaL_r16Iuwqse3eXdxzEXSxSDi3xhgMR0sT?key=KEi1pMKVOxS1gZVpUrUYW_Ab)

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdNPNmVDR1xI1xHAvwN9Bvo7oedDR-G1YNWwJEpV1nbO32OyrZPPT3EW77aq1uBVSCxdqEH8h46smCdIt6O_Kgb6qdqtNqSqRnWmfOb8PnoFbY6XsFbBU5qLAFtCZiVgmRGRIUgbA?key=KEi1pMKVOxS1gZVpUrUYW_Ab)



The process ends if the next neighboring element to its left is not less than the sort element. Since this propagation occurs within the ordered set, we are assured that if the next neighboring element to the left is not less than the sort element, then all elements to the left of the sort element are not less than the sort element and the sort element has reached its sorted position.

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcHNdSEjvHemHQno9ynXLXV6v1fog_G6afU9KQeUy3eiMe_lurhX61-8wuiECKRrDEwRn2h3d_Xg86JGYAYc-82mJ5pxg_w1OV8vmrIRN3wvje_SV9jwhTh7Wzo9F7TtPz0pcW5qQ?key=KEi1pMKVOxS1gZVpUrUYW_Ab)

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcH-ir9zRecFFqA6CLrSwLb8PpLXdmsJr_OJIGqJIb7S-urZYhCJCKmQbdgincwEb7eNcSznuCwyAjlksrM3131d4k4FDfQuYfuUjX7_K1_xchQ2xLuMIhsaoJ6jOE1hj2x8eKEmg?key=KEi1pMKVOxS1gZVpUrUYW_Ab)

At the end of the pass for the $i$-th element, it is guaranteed to be in the correct sorted position within those elements that have joined the sorted set and the unsorted set is reduced by one element. Insertion Sort is ready to perform the same process on the next unsorted element.

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXe6yttfUGynNEXN14Wg9A4przfsAYbGPxVqzi5-pvLvsUppOq1LMiJUyJHD4vchdO2QYy2bRo-Z3M6HXKbbPnTyoeenF2yORLHpD6vS9Nkj5Cb88RPA8wMr2rejC8O6t188dUeu?key=KEi1pMKVOxS1gZVpUrUYW_Ab)

### Graphical Analysis

The overall Insertion Sort process resembles the same set groupings that emerge from Selection Sort which suggests Insertion Sort has the same worst case performance as Selection Sort.

| ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXeCgN-P9R0V0X-mfCOy7M1jEUTs9DBW3z3bSnQWK8wjTYQFoWl0xz7FXJnc_JxPr-Zq0p2h5TBbXt2f_cMwEuniXdE-v4qFeFYQmSMGPpuMn8dLpFBX36PMDNA6rNyFjNDAV5I_?key=KEi1pMKVOxS1gZVpUrUYW_Ab) | ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXc2qiCbxG-irl7ptqGglwLxcHvRN0sINWVuKp4cwmCGtivZpAqQhT94yozhsL2pxs4Nq82BWXUVP3TjFL5DT00vFOirYmsSXMC_qzB2cfoICUapEnarDvwqYTDCLsR8em0eiubp7Q?key=KEi1pMKVOxS1gZVpUrUYW_Ab) |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| Block diagram illustrating Insertion Sort                    | Block diagram illustrating Selection Sort                    |

But consider when Insertion Sort produces its worst case performance. We found that Selection Sort’s best case and average case are the same as Selection Sort’s worst case, because due to its strategy, the process has no way to exit the process early and the same number of comparisons will be performed regardless of the ordering of the input data. In contrast, we found that Bubble Sort has an optimization that allows it to exit early if there are no swaps, and from this emerges a best case where if the input data is already ordered Bubble Sort will make only one pass which has $O(n)$ efficiency. 

This raises the question of whether Insertion Sort similarly has advantageous best and average cases. In fact, Insertion Sort only performs at its worst case if the input data is sorted in reverse order. Given a reverse order input, on each pass through the data, Insertion Sort must move the current sort element all the way to the beginning of the sorted set which results in the same number of total iterations as Selection Sort; however, Insertion Sort is actually worse than Selection Sort in this specific case because a comparison + swap for each iteration is more expensive than just a comparison.

### Pseudocode

```pseudocode
Input : E is the input set and is considered unsorted
Output : E is sorted in place, so E implicitly returns as the sorted set
n: the size of E
ej: the jth element of e
ej+1: the neighboring element to the left of e 
insertionsort(E):
	for i = 1 to n-1:
		for j = i to 1:		
			if ej-1 > ej:			
				swap(ei+1, ei)		
            else:			
            	break
```

### Best Case & Average Case

The worst case for Insertion Sort is established above, but to really understand that Insertion Sort was an advancement over both Selection Sort and Bubble sort, we must examine the best and average cases.

The best case for Bubble Sort was established above to be O(n), so if Insertion Sort needs to be equivalent, and it is. If the data is already sorted, then the outer loop will loop over all elements as normal, but only a single operation will be performed in the inner loop each pass as the inner loop will break on the first comparison which will result in a no swap. 

But what about the average case for Insertion Sort? We did not even explore Bubble Sort’s average case because it is extremely difficult to identify given randomized data and we generally assume it to tend to Bubble Sort’s worst case. For Insertion Sort to be an improvement on Bubble Sort, Insertion Sort’s average case needs to be better than Bubble Sort’s worst case, so let’s see if we can prove it.

To address the average case, we will assume that half the time we have to move an element from its initial position all the way to the left-most position in the sorted set and half the time we don’t have to move an element at all because it is already in its sorted position. This means all of the terms in the original proof are divided by two and we proceed through the proof as normal.
$$
\underbrace{\frac{1}{2}+\frac{2}{2}+\frac{3}{2}+\cdots+\frac{n-3}{2}+\frac{n-2}{2}+\frac{n-1}{2}}_{n-1}
$$

$$
\underbrace{\frac{1}{2}+\frac{2}{2}+\frac{3}{2}+\cdots+(\frac{n}{2}-\frac{3}{2})+(\frac{n}{2}-\frac{2}{2})+(\frac{n}{2}-\frac{1}{2})}_{n-1}
$$
As we did in the Selection Sort analysis, we assume that $n$ is an odd number and $n-1$ is an even number, so the number of constants on the right of the expression equals the number of terms on the left of the expression allowing us to cancel all of the constant terms:
$$
\underbrace{\cancel{\frac{1}{2}}+\cancel{\frac{2}{2}}+\cancel{\frac{3}{2}}+\cdots+(\frac{n}{2}\cancel{-\frac{3}{2}})+(\frac{n}{2}\cancel{-\frac{2}{2}})+(\frac{n}{2}-\cancel{-\frac{1}{2}})}_{n-1}
$$
Similarly, cancellation eliminated all constants, so half of the terms in the expression are eliminated and the equation is reduced to a summation involving elements with only a value of $\frac{n}{2}$: 
$$
\underbrace{\frac{n}{2} + \frac{n}{2} + \cdots + \frac{n}{2}}_{\frac{n-1}{2}}
$$
Again, using the definition of multiplication, we can simplify the above expression into the following: 

$$
\frac{n}{2}\cdot\frac{n-1}{2}
$$
Distributing $\frac{n}{2}$ gives us the following equation:

$$
\frac{1}{4}n^{2}-\frac{1}{4}n
$$

So, our average case time complexity for Selection Sort is $O(n^2)$ which is no different than our worst case time complexity.  

However recall the details of the math we used to derive the average case for both selection sort and insertion sort.

|                            |         Selection Sort          |         Insertion Sort          |
| -------------------------- | :-----------------------------: | :-----------------------------: |
| Avg Number of Comparisions | $\frac{1}{2}n^{2}-\frac{1}{2}n$ | $\frac{1}{4}n^{2}-\frac{1}{4}n$ |
| Avg Case Time Complexity   |            $O(n^2)$             |            $O(n^2)$             |

From the above selection sort generally has the same time complexity as insertion sort, but from a practical standpoint, the average number of comparisons for insertion sort is significantly less.  In other words, they will both grow quadratically with the size of the input, but objectively, insertion sort will almost always require less comparisons than selection sort.

| n    | Avg Selection Sort Comparisons | Avg Insertion Sort Comparisons |
| ---- | :----------------------------: | :----------------------------: |
| 10   |               45               |               23               |
| 100  |             4,550              |             2,475              |
| 1000 |            499,500             |            249,750             |

<!--This means that generally Insertion Sort is a marginally better choice than Selection Sort so it is easy to justify using either, *i.e.* Bubble Sort is easy to implement and Insertion Sort is marginally more efficient in the average case but performs the same in both the best and worst cases. -->

### Stability

Insertion sort is a stable sorting algorithm

TODO: Illustrate

## Quicksort

Quicksort operates in a way unlike all the other sorting algorithms we have so far studied. Instead of using a brute force strategy, it uses a divide and conquer strategy to sort the data in the input set.

Quicksort is built on the idea of a pivot which acts much like the pivot on which a see-saw balances. In a perfectly balanced see-saw, half the weight is distributed on one side which is counterbalanced by half the weight on the other side. 

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXecY7ZOpOAyaDCdbqg5kxRWnK4NAb-I9NpbNiSQR5j8E-XYC6gI1d0ipRNTBw9j2JlwHPRFltBqEoFmxe_Vw82unNKzTM2kefzub8jxbLRyXZGubIsyDiqUo91MDEkBJbjfSlPXWg?key=KEi1pMKVOxS1gZVpUrUYW_Ab)

For Quicksort, the first step is selecting a pivot, followed by moving any elements that are larger than the pivot to the right side of the array and moving any elements that are smaller than the pivot to the left side of the array, and finally swapping the pivot into the pivot’s correct location in the array. This process is then repeated on the subset to the right of the pivot and on the subset to the left of the pivot. The process concludes when the subsets are empty. 

Given an array with the following data:

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcbArxwSIFtL6S0RptI56i9SQEDFFWJnNQWOjrb5oAQhD4Iqv5R0d0ai3FWOfGd2UJG51nFapfm4sQo7WrdWWGmv1xG5EikmO4iDM1D9n9HZlmEwj2hHRwoEnE7W87YdQeXiEHzZw?key=KEi1pMKVOxS1gZVpUrUYW_Ab)

This example uses a naive pivot selection where the leftmost element is arbitrarily chosen as the pivot. In addition to tracking the pivot location, the pivot algorithm also tracks two indices: i indexes a loop through the set and j tracks the index that divides the left and right sets. 

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcRiV5LX80NaSswYxhEdg70NLhNKjqFX6g2lgSup3Kz1ngRGDgQuXMyguBCiZGL8tthvWQQIymo9RpF_7VeMVnMYPiJrD9AYi_OMzqFye7dgSYJGkxPsgtGZXYjJ7r-iQp2PPQlQg?key=KEi1pMKVOxS1gZVpUrUYW_Ab)

i begins at the index to the left of the pivot and j at the pivot index.

At each iteration of the loop, the i-th element is compared with the pivot element. If the i-th element is greater than the pivot element, j is moved to the left one position and the i-th and j-th element are swapped.

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcGzxUa-rotuwftg9RM32brlEV99hsgUJ_OWUilFRwVSOPJhq7edtKxVWB2ghLPwIXxUvdfFHIjtAgoR6b1GgYUyU9uk7_0e5ud4KoXCDpF4L0_kkt7AFUDEBRv4lQLiw4scjuF?key=KEi1pMKVOxS1gZVpUrUYW_Ab)

This presents a bit of an odd case in the example where the first element is swapped with itself, but this cost is marginal and eliminates any need for the algorithm to have additional branches.

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdDZO2J6bO2nxi9KkTAjaLq5IngcWhrYoYaLCFItHWRygJcLgmYE1uQCJCLqDY4c1PMhUR3KDLoEptW-b1AZKVKIzk8TV5ap6lucdm_3N2qa6LojTiF6y-Dn1CacUXplPaKmzOr?key=KEi1pMKVOxS1gZVpUrUYW_Ab)

The pivoting process proceeds and compares the next element with the pivot

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfy1m5Xk5Zpu-jGxa6-ja78IgXjAmTjRFiq6JguWuN6vAjtbJ2tveddZO9jssrP5unp9MBgxo7qKpIfShkz4JrJxez8YVTBg5gwODictR7k7LkNlQ60SVSXY6tM_UQzJy74Qomi1w?key=KEi1pMKVOxS1gZVpUrUYW_Ab)

In this case, the next element is less than the pivot, so no swap is performed.

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXco3FpmAX7kb5RZqSukPeDewjmLoAWsP7Wc5vmW_uRBKVEl59FRR6PGGPVAQAuxkQXDwuBNhlTZJcxJ8GmsWOP1t96IYGYlXMiY7b0E9HsyLybuTSpC2z5U2h783OAi8WaCh4vWwQ?key=KEi1pMKVOxS1gZVpUrUYW_Ab)

Because no swap was performed in the previous step, the two indices, i and j, will start to diverge and the left and right sets will be more apparent, *i.e.* elements between i and j are in the subset that is smaller than the pivot element and elements at j up to but excluding the pivot index are in the subset that is larger than the pivot element. The process repeats until the leftmost end of the array is reached. 

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcD6vFW1scUJPsAdcwI5-8ZMwng6epYTh6ypHHJOhuVU03c5YuTvhoMQagFDOmf34WohFWaqDwG4jmqlH5B7bl-5LRwAr2XqlaDn3s0roIYIAOsTEkTIBPVHwxSUsts9bUlAeVNCw?key=KEi1pMKVOxS1gZVpUrUYW_Ab)

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcYVLDWpR2qfNi8Bp-Bb5drb9qTPhXOifjg2mUoLcH5-qBKUV2kyyS1ClUWXezFkn8bJndMQ9FA5MnGLED9iF-iZS-F5PDXUl4kKQMz-1xNDgGJi--pbuE8JZ5UKgF6pYHrMnz6qg?key=KEi1pMKVOxS1gZVpUrUYW_Ab)

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcHZegpqWz_A9HMN0EdxOY2O8hH_ocQeARGcrPp5s9121Wp2JZKO1FatU23wr3pUwL_bqHAj1oFiCylJPn7ccGEi7tvTXoAiuk4gwcKqEzP9XT0FaHq9u0Fceg6BDiMM2v7pjxs?key=KEi1pMKVOxS1gZVpUrUYW_Ab)

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfGccgsJ8-K4kNQyZ2uqQUjJ6uEJBYmn8yRlrYPUqchO9pDQJJZPq0vxoPvxx4fFJwgaTNSs-oksmNUqBbQ4KEnsF1TsZKaPobH6AzrYWyWS5yezH8aG6NQK4dCVLTjPWQK9UWz_w?key=KEi1pMKVOxS1gZVpUrUYW_Ab)

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfmF_X1SoUZxgKmqYQvA78iL4ywOcyiDNxCe3rljDzL8sqMGowrsoWgJbMDEG-wx3XnPAjlI2BX31HQnf7fNvUB6mClVvLY0fyTt34Eq-EdOvz9U9Hwdi_zqyzoqIERyDSeah6Yjw?key=KEi1pMKVOxS1gZVpUrUYW_Ab)

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcdOp__XDrVHPtJqHVHEzqRyclYrFF0Kw2wr2zeHuMUudAByWHx6bN30p7A5lXuSKqIxibkoVymMmVJEAEp0xRjhJJnsSzona-lZ9PgpJwSUzh6cKNFR39HPl_7-4GUVBnCMsIqpA?key=KEi1pMKVOxS1gZVpUrUYW_Ab)

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdADtSy1HjFQHVmUw0MhPKsB9mkejPh4Icv3aSXo17QVV-kkuVQdI0w3oEDhIyEMhsrfgq0HU_hEagAa8vw6qXWkpzFwlORWpEl-hR3Jog8qsE2faFSGY7FfGyqm5ZIriKDOxSX_A?key=KEi1pMKVOxS1gZVpUrUYW_Ab)

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfRdTH8lyiJSchZvHIuiD1h22pRue9axBdMwOkzDW3UbNIcg6c3sQdJLZqzGPEB0is2b1DI3OPhJO5F13YOxtm4ZTVrmhacnTbygUv5_0rFpENzhwGylVcblceX0Nbe0nwQT0wMkQ?key=KEi1pMKVOxS1gZVpUrUYW_Ab)

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdeKy196qTbzXu56ZSHa6ivH9P4nuldprHucSAn956z8mBoJMoygERL-A1hShPvLn3qASNBX61kdSsmVsNcRR5SIm0qbSvRD5oJI50BAIITkCLAuctg9JLmNAx-n3leyLprHO_9mw?key=KEi1pMKVOxS1gZVpUrUYW_Ab)

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcl6ntr-n66588JjSeDeR3Hl34ybDN3fzyYm1Ijkc3GVd2mhXjZ7mbto2soR2wr0aXXMO9uyY2Zyk04VokxzX1BpDgSRwk_ZnElo9laBtwOmO5yThaJs6n64X7rNDKuo54LBHId?key=KEi1pMKVOxS1gZVpUrUYW_Ab)

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXc1Bjty1qcrhxv5wqyEs2oswTgyIYgSyF6y8Yn3wy8oGNYWm5dbWwMbzpX58e8u8dZnD4BVwjz99S02kQpcF4Z5RjKSeqZxxTLEVc3aTetL-TO0mwKv_jH8Jg0MdbGk-R-tcXRG?key=KEi1pMKVOxS1gZVpUrUYW_Ab)

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXegykynquMKEpXHJ3jnBrrp9Q7EKpSUdKuj9H5gvaTnxK4c3cmoXOtnvF_5AEXUXqAfqq4n2yIhWBHAlk69X0PfgxunEwX55K4571OcqFeRSnRdC7Y2uN5asFiYpXn223Z5HUOkQA?key=KEi1pMKVOxS1gZVpUrUYW_Ab)



When the last index is processed, the pivot element is swapped with the element at index j, i.e. the index of the leading element in the right subset, which puts the pivot element into its sorted position.

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXd42vZBJa8r7L_qmoYnymtNxVzR0JUAT1b_eC9Q2cuv9DxhAMiB6_mDENm5lra_273NMmXIUrx4ZoKdVrP3T2umdn3Q6EzMxZGe7j3i3wU6Jk08nezKKl1w9iMA1BjwvNVisNjwJQ?key=KEi1pMKVOxS1gZVpUrUYW_Ab)

All elements to the left of the pivot element are less than or equal to the pivot element and all elements to the right of the pivot element are greater than the pivot element. While the left and right subsets may not be sorted yet, the pivot is in its correct, sorted position within the overall set.

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXePLNLjh463y-Ch_KPxO5LHgfZM4I_HxYEPnRWdxPcS0xDRAmlP-j9DhdeL-Uq84_pTn-2Kl_l_fvnn_SFkJpNwS2YRpnKR3a64ucYzVfygCBcV1OtnJPtFOa7RMbbmTjaCVieX?key=KEi1pMKVOxS1gZVpUrUYW_Ab)

The process is then repeated on the left and right subsets.

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXe5lpldDRfbiMP2_vO4WgBSZvrh3Hgrwk-BdTUTaWF--bGgWb7nAgwH4uURGLV0jvroX0cOphpkMm9NLn2tYd86YuW6qoQA60G0QM7ft6adWSLSE4awLvqCCu8oe02HHoxCrY8aCQ?key=KEi1pMKVOxS1gZVpUrUYW_Ab)

This second pass will result in two elements being placed into their sorted positions with each subsequent pass resulting in twice the number of previous pivots being sorted into their correct location at the cost of a single pass through the data assuming that pivot selection is ideal for each subset. 

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXemn4U84Md6meMd9FEMTzL6ty7Rkw-OtGatVmD4XLXPYYdNXKPkhAOeWqlBzTRIcNXXSv-lZFq8kHlQgVoVhp1sS8rpnTI_YLOU6D_kHzujppADPUjm5vl-nbEdzXtqFuZkptsLQw?key=KEi1pMKVOxS1gZVpUrUYW_Ab)

### Mathematical Analysis

Let us assume that pivot selection is ideal, meaning that pivot selection always produces the median (middle-most) element in the set using a constant time algorithm. If pivot selection is optimal, then the mathematical analysis is as follows. 

At each pass, each subsets is divided in half until each subset consists of a single element.   

The first pass the algorithm processes the entire set performing $n$ comparisons:
$$
n
$$
The second pass the algorithm also processes the entire set performing a total of $n$ comparisons on two subsets; however, assuming the pivot selection perfectly bisects the set, then there are $\frac{n}{2}$ elements in two subsets:
$$
\underbrace{\frac{n}{2} + \frac{n}{2}}_{2}
$$
Each pass continues to bisect each subset producing twice as many subsets, but performing half as many comparisons on each subset.  For a given pass though the data, no more than $n$ comparisons are made:
$$
\underbrace{\frac{n}{4} + \frac{n}{4} + \frac{n}{4} + \frac{n}{4}}_{4}
$$
The process continues until the subsets contain only one element:
$$
\underbrace{1 + 1 + \cdots + 1}_{n}
$$
At which point, the open remaining question $x$ is how many times times was it possible to subdivide each subset until each subset contained only one element.
$$
\underbrace{(n) + (\frac{n}{2}+\frac{n}{2}) + (\frac{n}{4}+\frac{n}{4}+\frac{n}{4}+\frac{n}{4}) + \cdots + (\underbrace{1 + 1 + \cdots + 1}_{n})}_x
$$
Based on our earlier discussion of logarithms, the base 2 logarithm predicts the maximum number of times a set can be repeatedly divided in half.  In other words:
$$
x = \log_{2}n
$$
Giving us the following equation for the total number of comparisons:
$$
\underbrace{(n) + (\frac{n}{2}+\frac{n}{2}) + (\frac{n}{4}+\frac{n}{4}+\frac{n}{4}+\frac{n}{4}) + \cdots + (\underbrace{1 + 1 + \cdots + 1}_{n})}_{\log_{2}n}
$$
Simplifying each of the parenthetical subequations yields:
$$
\underbrace{n + n + \cdots + n}_{\log_{2}n}
$$
Again, applying the definition of multiplication simplifies to:
$$
n\log_{2}n
$$
In other words, given an ideal pivot selection algorithm, Quicksort’s efficiency is $O(n\log_{2}n)$ or loglinear time complexity.

### Graphical Analysis

Again, we can perform a dimensional analysis to clearly see the efficiency is $O(n\log_{2}n)$.

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXe-3WOrN8htLmSi1FWoX4vx2NDK2SBJaJ8NJumRv98PxorICOe1M09SqEbInmfMCF-3mzAP1iIKFanxOLDOyEua6vh3etoUOh8drW34MlYGdkaOAQhBD7tAaBIbQupWeHtVUa1zNg?key=KEi1pMKVOxS1gZVpUrUYW_Ab)

### Pseudocode Analysis

Since this is a recursive algorithm, analysis becomes more difficult and in this case, it is much easier to model the efficiency using one of the other techniques. The risk here is seeing two recursive calls per call to the function and assuming that the algorithm is exponential without recognizing that the size of the sets are diminishing by half each time.

```pseudocode
Input : E is the input set and is considered unsorted
Output : E is sorted in place, so E implicitly returns as the sorted set
left : the leftmost position in the unordered set
right : the leftmost position in the unordered set
p : the pivot position 
quicksort(E, left, right) :
	if left < right : sorted	
		p ← pivot(E) where E defined by E[left, right]	
		quicksort(E, right, p-1)	
		quicksort(E, p+1, left) 
		
pivot(E[left, right]) : E[left,pivot-1], E[pivot+1,right]
	if left = right : 
		no remaining set 
    pivot = right
    for ei in E[right, left] 	
    	if epivot < ei 	
    		pivot = pivot - 1
    		swap(ei, epivot)
    		
    swap(epivot, eright)
    return pivot
```

### Best Case, Average Case, and Worst Case

Pivot selection is critical to the overall efficiency of Quicksort. What we analyzed above is actually the best case for quicksort with naive pivot selection. Pivot selection can become more robust and guarantee average case efficiency at the least if we just sampled three elements from the array during pivot selection and chose the median. With naive pivot selection average case performance is actually somewhere between $O(n\log_{2}n)$ and $O(n^2)$ suggesting that it is really an $O(n^2)$ algorithm.  However, Quicksort will generally perform closer to its best case if data is sufficiently randomized, so whenever performing a Quicksort analysis, you must consider the nature of the data. 

| ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfjgATgvfB0d7HUOVLeijXwwSUkrzgpO1nfhrWHGowZKk5zkVQiI9KmIDBF58e-SR2sbRGJQ4_Y9ywulVC-zAqj-RGFscMyjFJ0qcz1meppnpGxR5EGDKgRs9uxeD0yrIfXOr_g?key=KEi1pMKVOxS1gZVpUrUYW_Ab) |
| ------------------------------------------------------------ |
| Average case emerges because data is not likely to be perfectly balanced. |

### Degenerate Case

The degenerate case represents a specific situation where the expected behavior of the algorithm simply breaks down and performs extraordinarily poorly. We could argue this case arose in Insertion Sort with the reverse order input, but we are intentionally and somewhat arbitrarily introducing this worst-most case and making it distinct from the worst case here in Quicksort because students at this level have a tendency to assume this degenerate case is common enough to immediately conclude and argue that Quicksort generally performs at $O(n^2)$ when it does not if the pivot selection algorithm is slightly improved. Quicksort only performs at this worst-most case when the data is in order and the incredibly naive pivot selection algorithm proposed here is used. If we make a marginal improvement to pivot selection, the degenerate case disappears even with ordered data and Quicksort’s worst case is somewhere between $O(n\log_{2}n)$ and $O(n^2)$ but closer to $O(n\log_{2}n)$ than to $O(n^2)$. 

| ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcc24aavAcRnKqPrIBsiHIiywF2G74De5xuk8J2fBkV3jcFrJ9aJDVIpesjttYtj2p9kIjkpxWestjrpZQFE1S8PeWaI30knpjLw9Caih4TNVEn6CdTLqeFghCCy3qqPGIDonqj2Q?key=KEi1pMKVOxS1gZVpUrUYW_Ab) |
| ------------------------------------------------------------ |
| The degenerate case emerges when the data is already sorted and naive pivot selection is used. In this case, all elements are on one side of the pivot with each pass of quicksort. This means the block diagram generated resembles selection sort because only one element is sorted with each pass. |

Cases that assume typical behavior will be described as having randomized input data and if the degenerate case is explicitly referenced, assume data is not random and has an order that triggers the worst-most case. 

### Stability

Quicksort is an unstable sorting algorithm.  Instability can occur when a value with duplicates is selected as a pivot.

TODO: Illustrate

## Visualization

https://www.cs.usfca.edu/~galles/visualization/ComparisonSort.html

## Other Sorts

With the high variability in performance and list of special cases to consider for Quicksort, it is no wonder that further research was conducted into sort algorithms after Quicksort was published. Since this is an introductory course in algorithms, we will end our required discussion here but it is not the end of the sorting story. Additional sorts listed below are mentioned to ensure the breadth of the topic is illustrated and to encourage further study.  

### Merge Sort

Quicksort orders data while breaking the array down into constituent subsets but an alternative strategy is to break down the array into individual elements and then reassemble it in sorted order as we build it back up. This build it back up strategy in sorted order is the concept behind Merge Sort.

Merge Sort has better worst case performance than Quicksort, in fact it is $O(n\log_{2}n)$ under all cases, and it is generally the best of the simple sorts to implement in terms of efficiency; however, it is difficult to visualize and understand its process for an introductory algorithms course. If you are interviewing for a programming position, it is important to familiarize yourself with this sort and to be prepared to implement it. 

<!-- Add a fully realized section on Merge Sort -->

## Review

1. What is the pass-by-value policy and how does it relate to arguments passed as parameters to functions?
2. Define the swap algorithm.
3. Why does pass-by-value cause a swap function that has primitive parameters to fail?  Where in memory would the swap occur?  Why does this lead to a failure in a swap function implementation?
4. Why can pass-by-value be bypassed by passing a reference to an object?  Where are objects stored in memory and why is this location not governed by pass-by-value?
5. Summarize the strategy for Selection Sort
6. Summarize the strategy for Bubble Sort
7. Summarize the strategy for Insertion Sort
8. Summarize the strategy for Quicksort
9. Diagram the behavior of Selection Sort
10. Diagram the behavior of Bubble Sort
11. Diagram the behavior of Insertion Sort
12. Diagram the behavior of Quicksort
13. Define Pseudo-code for Selection Sort
14. Define Pseudo-code for Bubble Sort
15. Define Pseudo-code for Insertion Sort
16. Justify why the worst case, average case, and best case efficiencies for Selection Sort are always the same.
17. Justify why the best case for Bubble Sort is linear time complexity while its worst case is quadratic time complexity
18. Justify why Insertion Sort’s average time complexity is better than Selection Sort’s average time complexity.
19. Analyze the efficiency for Selection Sort.
20. Analyze the efficiency for Bubble Sort.
21. Analyze the efficiency for Insertion Sort.
22. Analyze the efficiency of Quicksort assuming the input is sufficiently randomized in the worst case.
23. Analyze the efficiency of Quicksort assuming the input is ordered. In other words, analyze the degenerate worst case efficiency for Quicksort.
24. Why does pivot selection determine the efficiency of Quicksort? 
25. Given randomized input data, which sort algorithm among those we studied is the best choice?  Justify your answer.
26. Given ordered input data, which sort algorithm among those we studied is the best choice?  Justify your answer.
27. Given a system with extremely minimal memory and unordered data input of less than a million values, which sort is the best choice?  Justify your answer.
28. Given a system with extensive amounts of memory and unordered data input on the order of a trillions of values, which sort is the best choice?  Justify your answer. 
29. Why do we sort?

# 7 - Java Classes and Objects

Java is strictly an **Object Oriented Programming (OOP)** language.  The Object Oriented paradigm follows a few basic principles from which emerge powerful capabilities to extensively structure components and how they are composed together to build a modern application.  The fundamental structural element all OOP languages are built on is the class.

## Class

At its most basic a class is a container.  Programming language developers recognized a need to compose multiple variables together into a single structure to reduce the management and naming burden on early developers.  Consider a rectangle which is defined by two independent variables: width and height.  

In early languages a rectangle's width and height would need to be managed independently of one another even though they don't have any meaning without the other.  Operations on a rectangle would generally need all of the rectangle data in order to perform their roles correctly, *e.g.* a rectangle's area cannot be computed without both the width and height.  Functions intended to operate on rectangles would therefore require multiple parameters and more complex ideas and their associated functions might have tens or even hundreds of parameters.

Additionally if the labels `width` and `height` are chosen for a specific rectangle, they might not be available for reuse for other rectangles or even for use in completely different contexts.  This might pose a non-trivial naming problem where a program consisting of multiple rectangles might instead use labels like `rect1_width`, `rect1_height`, `rect2_width`,  and`rect2_height` to ensure data is easily distinguishable and readable to the programmer.  Again for complex ideas and associated functions, labels might become extremely long to make them distinguishable from one another.

```c
// C does not have classes. In C, labels tend to be more descriptive and longer,
// function parameter lists tend to be longer and more discrete, and variables need 
// much more consideration and management

float rect1_width = 1.0;
float rect1_height = 2.0;
float rect2_width = 5.0;
float rect2_height = 10.0;
float circle1_radius = 1.0;
float circle2_radius = 2.0;

float area_rectangle( float width, float height ) {...}
float perimeter_rectangle( float width, float height ) {...}
float area_circle( float radius ) {...}
float perimeter_circle( float radius ) {...}
```

We might try to resolve this by packing multiple values together into an array which might allow us to pass one parameter containing multiple values; however, few complex ideas have variables of a uniform type, and it is, at the very least, convoluted to put different types into a single array.  Additionally, it becomes difficult to keep track of which field, *i.e.* index, represents what in the array for a sufficiently complex idea.  However, as difficult as it might be to pack data into an array, this concept does form the basis of the idea of a "data structure" because a programming language can provide a purpose built type that packs different variables of various types into a single container.

Before the development of OOP languages, the C procedural language introduced a container type via the `struct` type that acts as a data structure; however, the `struct` type is only capable of composing data into the container and has no capacity to compose functions into the same container. 

```c
// C structs improved the ability to group and contain data
struct rectangle {
	float width;
	float height;
};

struct circle {
	float radius;
};

struct rect1;
struct rect2;
struct circle1;
struct circle2;

rect1.width = 1.0;
rect1.height = 2.0;
rect2.width = 5.0;
rect2.height = 10.0;
circle1.radius = 1.0;
circle2.radius = 2.0;

// But they do not facilitate close association of functions to their data
float area( struct rectangle* r ) {...}
float perimeter( struct rectangle* r ) {...}
float area( struct circle* c ) {...}
float perimeter( struct circle* c ) {...}
```

The `class` type introduced by OOP extends the data structure concept to allow both data and operations associated with the structure to be collected into a single container type.  We generally call an operation, *i.e.* a function, associated with a class a **method**, and we generally call a variable associated with a class a **property**, **field**, or **instance variable**.

The term `class` is short for *classification* which means to associate similar elements based on shared characteristics.  A class generally acts as both as a container and a blueprint.  From the class, we can create an instance of an object that has its own unique copies of the instance variables defined in the class blueprint. 

### Object Creation

To create a new instance of an object in Java, in the majority of cases, we must use the `new` keyword.

First consider the `Rectangle` class:

```java
class Rectangle {
    int width;
    int height;
}
```

The following `RectangleEx1` program creates a `Rectangle` instance which we generally call an object, hence the *object* term in *object oriented programming*:

```java
public class RectangleEx1 {
    public static void main (String[] args) {    
        Rectangle rect = new Rectangle();
        ...
    }
}
```

The above program combines the declaration with the allocation and construction of the object; however, these are distinct steps.  In fact, this simple statement contains considerable complexity as illustrated in the following diagram:

<img src="/home/jrt/gwu-new/course/cs1112/assets/object creation.png" style="zoom:80%;" />

The `RectangleEx2` program illustrates the declaration of the `rectangle` reference type as a separate step from allocation and construction of an associated `Rectangle` instance.  The `RectangleEx2` program is generally equivalent to the `RectangleEx1` program:

```java
public class RectangleEx2 {
    public static void main (String[] args) {    
        Rectangle rect;
        rect = new Rectangle();
        ...
    }
}
```

Recall that there are two distinct elements involved with reference types: the reference variable itself and object instance that it refers to.  `RectangleEx2` illustrates these two distinct elements.  The `Rectangle rect;` statement represents the declaration of a reference type that is allowed to point only to objects that have been generated from the `Rectangle` class blueprint.  We know from our discussion on default initialization of reference types that this statement is actually equivalent to `Rectangle rect = null;`.  The subsequent statement `rect = new Rectangle();` triggers the creation of a new `Rectangle` object on the heap, returns a reference to that newly created `Rectangle` object, and assigns the local `rect` variable on the stack a reference to the newly created `Rectangle` object.

<!-- Add stack and heap diagram -->

### Constructors

In Java, when creating an object from a class blueprint, the programmer must provide initial state for the object.  This may be done implicitly or explicitly, but initial state of the object is always determined by the constructor called at object creation.

A constructor is NOT a function.  While there are some syntactical similarities, a constructor is distinctly different from a method/function.  In terms of syntax, a constructor does not have a return type in its declaration, cannot return a value, and shares its name with the class name while a method must have a return type in its declaration, may return a value subject to its declared return type, and can NOT share its name with class name.  In terms of invocation, a constructor can only be invoked (called) when preceded by the `new` keyword during object creation while a method can be invoked anywhere the object is valid after the object has been created given a legal reference to the object.

Recall the `Rectangle` class proposed in the previous section:

```java
class Rectangle {
    int width;
    int height;
}
```

Note that this version of the class does not explicitly provide a constructor; however, a constructor must be called on object creation.  How could a `Rectangle rect = new Rectangle();` statement legal if there is no constructor defined by the `Rectangle` class?  Java provides a **default constructor** if the class developer does not explicitly defined a custom constructor.  In other words, the above class actually has the following implementation even though the class designer did not provide a constructor:

```java
class Rectangle {
    int width;
    int height;

    /* The default constructor would look like the following if it was explicitly defined
    Rectangle() {
        width = 0;
        height = 0;
    }
    But it is commented here to remind us that this code was not written by us */
}
```

The default constructor is a **no parameter constructor** or **parameterless constructor** meaning it takes no inputs hence why the parentheses are empty in the `Rectangle rect = new Rectangle();` default example.

*If the class developer implements a constructor, then the default constructor is not provided by Java*.  The intent of the default constructor is to allow rapid development of a class and it follows established design principles and assumptions associated with Java.  Recall that Java already assumes that if an initial value is not provided to a variable, a default value will be assigned.  Assigning a default constructor is just this same principle extended to the `class` structure.  However, default constructors can cause unintended side effects that produce anomalous or error producing behavior if class developers do not enforce logical requirements.

For example, consider the `Rectangle` class.  From a logical standpoint, should it be possible to create a `Rectangle` with a zero value for either `width` or `height`?  The answer is no because without a positive value for both dimensions, logically the shape is either a line, a point, nothing, or something that is ill defined, *e.g.* a `Rectangle` with one or more negative values.  This logical requirements should be enforced from the moment of `Rectangle` creation and not left up to the user to "fill in later".  Part of the class designer's job is to create rules based on logical requirements and use the syntactical features of the language to enforce these requirements so class users cannot work around them.  Working around the rules is a significant source of bugs and if a loophole or shortcut in the object's design is left available by a senior class developer, a junior developer or intern will inevitably exploit it which will inevitably lead to a future issue.

To enforce logical state consistency beginning at the very creation of an object, a class developer should ALWAYS provide an explicit constructor.  As stated above, the default constructor will not be provided by Java if if any explicit constructor is provided.  An explicit constructor can be parameterless or parameterized, *i.e.* a constructor that requires parameters.  A class may also have multiple constructors including a no parameter constructor alongside one or more parameterized constructors.

```java
class Rectangle {
    int width;
    int height;

    // Explicit parameterless constructor
    Rectangle() {
        width = 0;
        height = 0;
    }
    
    // Parameterized constructor
    Rectangle( int w, int h ) {
        width = w;
        height = h;
    }
}
```

However, as suggested above, the above version of the `Rectangle` class is not logically consistent.  The parameterless constructor is probably dangerous to include because it means `Rectangle` objects can be created with invalid initial state.  A more logically consistent version of the `Rectangle` class would be the following:

```java
class Rectangle {
    int width;
    int height;
   
    // Parameterized constructor
    Rectangle( int w, int h ) {
        width = w;
        height = h;
    }
}
```

This version of the `Rectangle` class eliminates the default constructor and forces class users to call the parameterized constructor.  In other words, a class user could no longer create a `Rectangle` instance using the `new Rectangle();` statement.  Instead, the class user MUST use the `Rectangle(int w, int h)` constructor to create a `Rectangle`  which forces any class user to provide both parameters to the `Rectangle` object when creating every `Rectangle` object.  In other words,  `new Rectangle(10,20);` would create a `Rectangle` with `width = 10` and `height = 20`.  Does this resolve all logical issues?  No as it would still be possible to create `Rectangle` instances with zero or negative dimensions (preventing this requires more understand of Java features and more work to implement); however, it does force the class user to provide initial values for required fields which in and of itself will generally reduce and prevent some logical issues related to usage of the `Rectangle` class.

### Access Modifiers

Access modifiers are keywords that allow a class designer to intentionally expose or hide class members, *i.e.* methods and instance variables, from class users.  There are three access modifiers defined for Java: `public`, `private`, and `protected`.  We will only concern ourselves with `public` and `private` access modifiers in this course. 

The `public` access modifier is intended to allow a class designer to intentionally expose and grant access to class members, whether instance variables or methods, by a class user. The lazy class developer declares everything with public access to begin with and worries about locking it down later. This is problematic because when a member is exposed, it is not protected and users will bind dependencies to these public members even if the class designer’s real intent was to protect these members. This exposes internal class members to outside manipulation and can result in unexpected and illegal states to arise within an instance. In general, it is bad design to start with everything as `public`, but it is a natural approach because we want convenience and quick development.

The `private` access modifier is intended to allow a class designer to intentionally hide and prevent access to a class member by a class user. The intentional, bug-conscious, safe class developer declares only a very limited set of methods to have public access and otherwise defines all instance variables and all other methods to be private (or protected if relevant) access. Class users should NEVER have direct access to class instance variables such that the internal state of a class should be well-maintained, controlled, and inaccessible to class users.  If internal state needs to be exposed to a class user, then the access needs to be well curated and safe.  Private access enables support for information hiding which will be discussed later.

<!-- Java's default policy is "package-private" -->

### Accessors and Mutators

Accessors are commonly referred to as “getters” and mutators are commonly referred to as “setters”. This is because they are typically expressed as `get` and `set` class methods. Specifically, these methods are created to explicitly control read and write rights for member instance variables.

An **accessor** is called such because it provides a read access interface for a specific instance variable and a **mutator** (to change) is called such because it provides a write access interface for a specific instance variable. Provided the instance variable is declared as `private`, if only an accessor is provided for an instance variable then the variable is read-only outside the class, if only a mutator is provided for an instance variable then the variable is write-only outside the class, and if both a mutator and an accessor are provided then the instance variable is both read and write outside the class. 

This approach gives the class developer the ability to control what is exposed to class users and to only expose prescribed behaviors for a class. It forces class users to use the explicitly designed interface, prevents class users from binding directly to class instance variables that should remain hidden inside the class, and helps ensure that the internal state of the class remains within the design parameters for the class. It also eliminates the burden on class users to have to know how a class works in order to use it properly.

For example, consider a `Circle` class that provides a way for users to get and or set the instance variables and offers the opportunity to enforce validation rules for any mutators provided.

```java
class Circle {  
    private float radius;   
    
    public float getRadius() {    
        return radius;  
    }  
    
    public float setRadius( float r ) {    
        radius = r;  
    }   
    ...
}
```

In the above example, the class developer has provided an accessor `getRadius` to allow a class user to read the value of the radius stored inside a `Circle` object. The class developer has also provided a mutator `setRadius` that allows the class user to change the value of the radius. Given sufficient additional rules for the `mutator`, specifically by introducing error throwing, the class designer could prevent a class user from setting the `radius` to 0 or a negative value.  If `radius` was declared as `public`, a class user could set the `radius` to zero or a negative value without any supervision or control by the class developer which would produce nonsensical (in this case) or even dangerous state for some classes.

A better implementation might be to not provide a mutator for `radius` at all so that the property cannot be changed after the object is created.

```java
class Circle {  
    private float radius;   
    
    public Circle(float r) {
        radius = r;
    }
    
    public float getRadius() {    
        return radius;  
    }  
    
    ...
}
```

By not providing a mutator, making the `radius` private, and providing a `radius` accessor, it encourages the class user to initialize the class correctly and prevents a class user from modifying the `radius` to an illegal value after the `Circle` object is created. 



<!--class Circle extends Shape {  
    private float radius;   
    public float getRadius() {    
        return radius;  
    }  
    public float setRadius( float r ) throws RuntimeException {    
        if ( r <= 0 ) {      
            throw new RuntimeException(“radius must be positive”);    
        }    
        radius = r;  
    }   
    ...
}-->

### `this` keyword

The `this` keyword is a convenience reference that allows class developers to clearly specify the context of a symbol that may be used in both local and instance level scopes. According to Java syntax, the same symbol can be declared as an instance variable and as a local variable in the same class and the two variables will be distinct and stored in two different locations in memory, *i.e.* the local variable will be on the stack and the instance variable will be on the heap.  This might lead to trying to find different names for variables depending on their scope to avoid collisions and confusion; however, if two variables share the same intent why should we arbitrarily name them something different just to address a scoping difference. For this reason the `this` keyword exists.

`this` acts as a reference to the current instance from within a class.  `this` allows a class developer to explicitly refer to an instance level variable from the local scope regardless of whether or not the symbol is declared in local scope.  Let’s look at the `Circle` example again to clarify.

```java
class Circle {  
    private float radius;
    
    public float setRadius( float radius ) {    
        radius = radius;  // what is the intent of this line?
                          // what does it actually do?
    }   
    ...
}
```

In the above example, the input parameter for the mutator is named `radius` which is the same symbol used for the instance variable `radius`. It is perfectly legal to name these two different variables this way; however, a problem arises with the statement `radius = radius;`.  It seems the class developer intends to assign the `radius` instance variable to the value provided by the `radius` input parameter (this is the only context for the example that makes sense); however, this intent is not properly communicated to Java and it will not work the way intended.  Instead, Java will interpret the intent of the code is to assign the input parameter to itself and therefore do nothing because that is what the syntax is describing.  Java first looks for the symbol in the local scope and if it cannot find it there it then looks in the instance scope, but because there is a `radius` symbol in both scopes, all `radius` labels inside `setRadius` are associated with the local variable.  We need some way to differentiate between and specify scope levels at the function level to clearly communicate intent, so how can we provide the intent and avoid renaming the local variable to some arbitrary, less meaningful symbol?

```java
class Circle implements Shape {  
    private float radius;   
    public float setRadius( float radius ) {    
        this.radius = radius;  
    }   
    ...
}
```

The `this` keyword communicates the intent clearly to Java. By using the self reference of `this` in the above example, Java interprets the statement to mean assign the `radius` instance variable the value of the local variable `radius`.

## Object Oriented Principles

There are three principles of **Object Oriented Programming (OOP)** : **Encapsulation, Inheritance, Polymorphism**. Since this is a course in data structures, we will naturally and explicitly focus on Encapsulation; however, we will only address Inheritance and Polymorphism around the edges and these topics will be considered in detail in a follow-up Software Engineering course.

#### Encapsulation

To encapsulate simple means to enclose something. Encapsulation in terms of OOP is to put associated data and methods into a class. For example, most logic needed to store and operate on string data is all encapsulated into the [Java String class](https://docs.oracle.com/en/java/javase/11/docs/api/java.base/java/lang/String.html). This class contains a character array, *i.e.* the string data, and a whole suite of methods for strings that almost fully encapsulate everything associated with strings into a single class.

Whenever you write a class, you are encapsulating related methods and data into that class, so encapsulation is the most fundamental development activity in OOP languages. It allows you to group all the associated operations and data into a single container.

So far, we have assumed that everything generally has public access but this is generally a dangerous assumption. Part of encapsulation is to discriminate if each individual instance variable and method you add to a class should be accessible to everyone or if it should be hidden inside the class. This idea is known as **information hiding** and it is a critical secondary principle that is provided by encapsulation.

##### Information Hiding

The principle of information hiding is that only the minimal information needed to use the class should be visible outside the class.  Users of a class, *i.e.* junior developers or third parties, do not need to know how a class works to use it, they only need to know how to interact with the class and how it behaves in response.  This is a form of "black boxing" that allows developers to discriminate between internal and external class data and to protect the internal state of a class from unintended manipulation by a class user. In order to support information hiding, Java provides the `public` and `private` access modifiers which allow for the developer to explicitly specify which variables should be exposed by the class interface.  The `protected` access modifier is just a specialized `private` access modifier that assists OOP inheritance. 

#### Inheritance

Inheritance develops relationships between classes based on shared traits. The most obvious example is that you inherit traits from your ancestors and any descendants you have will inherit traits from you and from your ancestral lineage. 

For a more abstract example consider that we have circles and rectangles. Circles and rectangles are obviously different, a circle has a radius while a rectangle has a width and height, but a more interesting and maybe more useful organizational question is what do they share in common which we can answer as both are shapes. So, what specifics about shapes are useful for any shape: all shapes have a perimeter derived from its dimensions, all shapes have an area derived from its dimensions, and maybe all shapes can be drawn. This raises the question of how we express all of the above in a set of class structures and whether these relationships can be modeled by the object definitions themselves.  There are several possible approaches, but OOP introduces the concept of inheritance to allow OOP languages to model the relationship of shared traits between class definitions and objects.

There are different forms of inheritance in Java and we will not go deeply into them here, but they do involve special keywords. For this form of inheritance we need to use the `interface` keyword to define a `Shape` type and the `implements` keyword for the `Circle` and `Rectangle` classes. We will discuss these keywords in more detail later with respect to Abstract Data Types.  The relationships between a generic `Shape` and specific `Circle` and `Rectangle` shapes is illustrated in the following Java code:

```java
interface Shape {  
    float area();  
    float perimeter();  
    void draw();
}

class Circle implements Shape {  
    float radius;   
    float area() { 
        return 3.1459 * radius * radius; 
    }  
    float perimeter() { 
        return 3.1459 * 2 * radius; 
    }  
    void draw() { ... }
}

class Rectangle implements Shape {  
    float width;   
    float height;  
    float area() { 
        return width * height; 
    )  
    float perimeter() { 
        return 2 * (width + height); 
    }  
    void draw() { ... }
}
```

There are many issues with the above code, but it conveys the general idea that a `Shape` defines certain ideas shared by all types of shapes and it is up to a specific shape to implement the specifics of that idea. We will revisit this example below and discuss it in more detail.

#### Polymorphism

The term polymorphism is the portmanteau of “poly” meaning “many” and “morph” meaning “forms”; therefore, polymorphism means “having many forms”.  Ironically, there are many types of polymorphism in programming and non-OOP languages may support some types of polymorphism without even offering a class structure; however, OOP languages specifically offer a form of polymorphism as an extension of inheritance.  

One non-OOP form of polymorphism is to have multiple functions with the same label. 

```java
class Greet {   
    static void hello() {    
        System.out.println(“Hello”);  
    }   
    static void hello( String name ) {    
        System.out.println(“Hello ” + name);  
    }
}
```

There are two methods with the same name. How is this possible? This is the common form of polymorphism involving functions. From a practical sense, we use the same symbol to represent two independent operations. Java accepts this because even though these two functions share the same label, the parameter list has a unique permutation of types which is used to discriminate between the same symbols. Java uses the function label and the ordered list of types to find the corresponding function.  As suggested above, this is not the only form of polymorphism and you will be introduced to a much more dynamic version once you master inheritance, but this is an important form of polymorphism to discover now as it will free you from trying to invent different symbols for functionally similar operations.

The OOP form of polymorphism is an extension of inheritance.  Recall the `Shape`, `Circle`, `Rectangle` example:

```java
interface Shape {  
    float area();  
    float perimeter();  
    void draw();
}

class Circle implements Shape {  
    float radius;   
    float area() { 
        return 3.1459 * radius * radius; 
    }  
    float perimeter() { 
        return 3.1459 * 2 * radius; 
    }  
    void draw() { ... }
}

class Rectangle implements Shape {  
    float width;   
    float height;  
    float area() { 
        return width * height; 
    )  
    float perimeter() { 
        return 2 * (width + height); 
    }  
    void draw() { ... }
}
```

The inheritance here defines that every `Circle` object is both a `Circle`  and a `Shape`.  Similarly, every `Rectangle` object is both a `Rectangle` and a `Shape`.  This means that it is legal for a Shape reference to point to a `Circle`, a `Rectangle`, or any other type that implements the `Shape` interface.  Which also means that we can store `Circle`, `Rectangle`, or any other `Shape` references in a data structure defined to hold `Shape` references.  If the implications of this are not entirely clear now, it will become more clear as we look at specific data structures.

## Abstraction

An **Abstract Data Type (ADT)** is a description of a data type that only prescribes in the most general sense “what it does” but does not specify “how it works”. In other words, an ADT only prescribes the interactions and the behaviors of that type and does not prescribe the implementation which should be generally hidden from class users. An **interaction** is an intentionally exposed interactive element of a system like the button on a device that performs some set of actions in response to user interaction, and a **behavior** describes how the system responds when a specific interaction is evoked. In programming terms, an interaction is a method including a description of the necessary inputs, and a behavior is a high-level generalization of what the method does including a description of any output the system produces in response. These descriptions are extremely abstract and intentionally ignore any specific implementation details about the process. 

Consider the following "media player interface":

<img src="/home/jrt/gwu-new/course/cs1112/assets/media player interface.png" alt="media player interface" style="zoom:50%;" />

While a media player user does not necessarily know how the media player works, certain operations have been exposed through buttons and associated icons.  For the above interface, we expect that the media player will begin playing whatever the selected media is when the middle button with the right facing triangle is pressed.  We recognize this operation as "play" due to its standard interface and as such we have certain expectations of what will happen in response to pressing the button.  A description of this interface would be "play" as the interaction and something as simple as "plays the current track" for its associated behavior.

Interfaces become recognizable standards and that systems including humans in society come to depend on.  For example, consider the standard interface for driving an automatic car.  This interface consists of a steering wheel that rotates clockwise and counter-clockwise, the right pedal, the accelerator, speeds up the car, and the left pedal, the brake, slows down the car.  When the car is moving forward, if the steering wheel is turned clockwise the car turns to its right, and if the steering wheel is turned counter-clockwise the car turns to its left.  Even if the same controls are used but their layout or behaviors were changed by car designers, it would have dangerous effects on the driver and people around the car where drivers would have to relearn the car interface for each car they drove.  For example, suppose that some cars turned left when the steering wheel was turned clockwise or some cars had the accelerator on the left.  It is because the car interface is standard that drivers can easily and safely drive unfamiliar cars.

The term **interface** is generally used to describe the interactive elements of a system specifically where two systems interact and exchange information.  The term interface, much like the term state, can be used to describe a single element or can be used to describe an entire system.  We can focus on a function's interface such as the **function signature** which includes the return type, label, and list of parameter types, we can focus on a class interface which includes the public methods and public instance variables, we can focus on an application's interface such as the inputs, outputs, buttons, windows, and other controls used to interact with an application, or we could use the term to focus on complex systems like a computer to describe all the interactive elements such as keyboard, monitor, mouse, etc and the connections joining other subsystems like USB, SATA, etc.

As illustrated by the abstract `Shape` definition, Java even uses `interface` as a keyword for an abstract class:

```java
interface Shape {  
    float area();         // computes (returns) the geometric area of the shape
    float perimeter();    // computes (returns) the geometric perimeter of the shape
    void draw(Window w);  // draws the shape to a graphical Window device
}
```

An abstract class is a class that only defines the interface for a type and does not provide any implementations.  In other words, it defines only how to interact with the type and how the type will respond to specific interactions.  It does not define the implementation meaning it does not define how the type will actually function to achieve the stated interface.  In the `Shape` `interface`  above there are only function declarations meaning that none of the functions provide implementation details.  As a result, a Java `inteface` cannot be created directly meaning that attempting to create an instance of an interface would be illegal, *e.g.* using this statement `Shape s = new Shape();` would lead to a compilation error.  Instead a class would have to "implement"  the `interface` as illustrated by the following `Circle` class and an instance of the Circle could be created:

```java
class Circle implements Shape {  
    float radius;   
    
    // computes (returns) the geometric area of the shape
    float area() {
        return 3.1459 * radius * radius; 
    }  
    
	// computes (returns) the geometric perimeter of the shape
	float perimeter() {
        return 3.1459 * 2 * radius; 
    }

	// draws the shape to a graphical Window device
    void draw(Window w) { ... }
}
```

Note that Java uses the `implements` keyword to establish the relationship between the `interface` definition and a class.  This is a contract where a class that `implements` the `interface` must define implementations for all methods in the associated `interface`.  In the `Circle` class, the class must provide implementations for `area()`, `perimeter()`, and `draw(Window)` because the class is declared as `implements Shape`.  As mentioned earlier, this is a form of inheritance and helps support polymorphism at the class level.

A natural question for this Java interface model is what are the benefits of developing these associations?  Consider the following example program:

```java
class ShapeAppEx {  
    
    void main( String[] args ) { 
        // create an array of abstract shapes
        Shape[] shapes = new Shapes[2];
        
        // create specific shapes and store references to them in the shape array
        shapes[0] = new Circle( 1.0 );
        shapes[1] = new Rectangle( 2.0, 4.0 );
        
        // pass the abstract array to a function that operates on them
        draw(shapes);
    }
    
    // iterates over all shapes and draw each one
    void draw( Shape[] shapes ) {
        Window w = System.getWindow();  // Note this is just a conceptual example
        
        for( int i = 0; i < shapes.length; i++ ) {
            Shape shape = shapes[i];
            shape.draw( w );
        }
    }
}
```

Recall that conceptually everything must be an object in an object oriented language which is why all code in Java must be contained within classes.  When a programmer defines a class, they are defining an object.  Java reflects this defining every class to inherit from an `Object` base class.  The `Object` class defines the default `toString()` method that is inherited by all objects which generally allows any custom type to be printed using `System.out.print(...)` or `System.out.println(...)`.   In other words, when you print any reference type, you are calling the `toString()` method associated with that type.  If there is no `toString()` method provided in the class definition, the default `Object.toString()`  method will be called.  

| `Circle c = new Circle(1.0);`<br />`System.out.println( c );` | $\rarr$ | `Circle c = new Circle(1.0);`<br />`System.out.println( c.toString() );` |
| ------------------------------------------------------------ | ------- | ------------------------------------------------------------ |

The class designer does not have to provide the `toString()` method for their class because it is already provided in the `Object` class; however, the default behavior of the `Object.toString()` method may not be useful for specialized classes.  The Java 8 documentation describes the `Object.toString()` implementation as:

> The `toString` method for class `Object` returns a string consisting of the name of the class of which the object is an instance, the at-sign character '`@`', and the unsigned hexadecimal representation of the hash code of the object. In other words, this method returns a string equal to the value of: 
>
> ```java
>  getClass().getName() + '@' + Integer.toHexString(hashCode()) 
> ```
>
> [Object.toString()   Java 8 documentation](https://docs.oracle.com/javase/8/docs/api/java/lang/Object.html#toString--)

In other words, the default `Object` class `toString()` method returns the name of the class and some additional information which is not generally useful to the average programmer.  Instead, a programmer might want instead the `toString()` method for their own class to return a string containing detailed state information about an object so that the programmer can peak inside the class and trace state data.  

For example, in a simple `Point` class, we could override the default `toString()` method: 

```java
class Point {
    private float x;
    private float y;

    Point(float x, float y) {
        this.x = x;
        this.y = y;
    }

	// overrides the inherited Object class method toString and returns 
	// information involving the instance variables of this circle
	public String toString() {
        return "Point(" + "x=" + x  + ",y=" + y + ")";
    }
}
```

From the above, we can create a simple program where we create a point, and then call the system print operation which in turn implicitly calls the `Point` class `toString()` method:

```java
class PointToStringEx {
    public static void main( String[] args ) {
        Point pt = new Point( 1.0f, 2.0f );
        System.out.println( "pt=" + pt );
    }
}
```

If we run the above, it should print the following to the console:

```
pt=Point(x=1.0,y=2.0)
```

In the `System.out.println( "pt=" + pt );` instruction, we are asking Java to build a string consisting of the `"pt="` prefix concatenated with whatever the output of `pt`'s class definition for its `toString()` method.  If we had not overridden the `Point` class `toString()` method by providing one in the `Point` class itself, it would have used the `Object` class `toString()` method instead which would have simply printed according to the Java 8 definition discussed above.  However, we did provide our own `Point` class `toString()` method which is defined to build a `String` defined as `"Point(" + "x=" + x  + ",y=" + y + ")"`  which contains detailed state information about this instance.  The `toString()` method can be customized to the programmer's and program's needs.

The inheritance used to define the relationship between the `Object` class and all other classes is slightly different from the inheritance defined by the `interface` and `implements` model illustrated above.  The details of these differences will be left for another class to explore, but it is important to understand that OOP allows programmers to define relationships between classes and to inherit entire methods or just the interfaces from another class.

<!-- Reference “wrappers” for primitive types: Integer, Float, Double, Etc.-->

### List ADT

The first step in the development of any class is to determine the set of interactions and their resultant behaviors for that class and to determine what these interactions are we have to first characterize the class itself. In other words, if we want to define a class that encapsulates the entire idea of a list, we have to first address the question of “what is a list”. 

A list is a generic tool we use to structure information in our daily lives. When we think of a list, we might think of a shopping list, a todo list, or a contact list. Evidently all of these things are lists because we call them that, but to classify (build a class) that captures the critical essence of all lists, we need to identify what all lists share in common. Let’s work with a very concrete example of a shopping list and use it to try to identify characteristics of a list.

Assuming we have a piece of paper and a pen handy, we have an empty list ready for use. Great, but it is mostly useless as an empty list so the first thing we usually do is add a new element to the list, so we need an interaction that allows us to add an element to the list. What is the associated behavior that add produces? Do we just write anywhere on the list? For practical reasons when the paper gets full, we might, but we generally do not start out that way and we only do that because of physical limitations, e.g. too little remaining space on the page, need to reorder the list but we wrote in pen, etc. No, add for a list is generally thought of as append, or in other words, we typically add a new element to the end of the list. So this suggests our first and possibly most important method shared by all lists:

```pseudocode
add( element )  # append element to the end of the list
```

Note that this is intentionally a pseudo code to avoid the specifics of Java right now. It allows us to avoid specific implementation considerations like types when sketching this out as a concept. We want the idea of the list to be as generic and language independent as possible to start out with and we will worry about how it works when we actually try to write it in a specific language (implement) like Java.

So when writing down a shopping list of items, I generally add items in the order I think of them without too much consideration for things like shopping order. For example, I might think of eggs, milk, bread, cereal so I will probably add things to my list in that order:

```pseudocode
add( eggs )
add( milk )
add( bread )
add( cereal )
```

Which generates the following list:

1. eggs
2. milk
3. bread
4. cereal

Note that lists implicitly have an order that emerges simply by writing down each element one after another.

At its minimum we expect a list to have certain positional characteristics, specifically, a list guarantees both the absolute positioning and relative positioning of elements with respect to the list and other elements in the list. In short, a list is a special kind of set where a linear order is imposed based upon position and when a linear order is imposed, positioning naturally emerges. **Absolute position** means that an element has a unique position within the set based upon a numerical index, *i.e.* first, second, last. **Relative position** means that an element has a position relative to other elements in the set, *i.e.* the first element precedes all other elements, the second element follows the first element but is before the remaining elements, the last element follows all other elements. If a set is structured by absolute position, then relative position naturally emerges, and if a set is structured by relative position, then absolute position naturally emerges. This brings us to another method for a list, accessing an element by positon:

```pseudocode
get( position )    # get element by absolute position in the list
```

However, just because we have the ability to use absolute position in all lists, only lists that are specifically optimized around absolute position will support efficient interactions using absolute position. In other words, arrays are better tools if your list needs to be accessed by absolute position because arrays support constant time access of any element in an array based list, but a list structured around relative positioning will not be as efficient as an array if absolute positioning access is used. So while get is a generic list interaction, whether it is wise to use it frequently will depend on whether the list implementation efficiently supports the interaction.

In addition to adding and retrieving elements from the list, we also typically need a way to remove elements from the list. In reality, we may need a variety of ways to remove elements from a list, *e.g.* remove by absolute position, remove by relative position, remove by some other identifier, however, let’s keep this simple to start out with and suggest that when we shop, we look at the top-most element of the list, go find it, and scratch it off (remove from) our list. Then, we can simply define remove as:

```pseudocode
remove( )    # remove the first element in the list if it exists
```

We also may need other basic information like how many elements are in our list. This tracks with basic questions we might ask about a list like “how long is my list”, but it is also very practical from an implementation standpoint because to support iteration using our defined get we probably need to know the length of the list. This leads to another interaction:

```pseudocode
size( )     # answers question of how many elements are in list
```

Finally, we might want to ask questions about whether or not something is in our shopping list. Like remove, we might have a variety of different forms of this question, but in the simplest terms, when looking at items in a store, we might simply need to answer the question of “is this item on my list”. Let’s generalize all possible search questions into a single method to start with:

```pseudocode
contains( element ) # answers question of whether element is in list
```

This gives us an overall generic interface for a list:

```pseudocode
add( element )  # append element to the end of the list
get( position )    # get element by absolute position in the list
remove( )    # remove the first element in the list if it exists
size( )     # answers question of how many elements are in list
contains( element ) # answers question of whether element is in list
```

Yes we may be omitting additional interactions that fully define a list, but as an example, we are really focusing on the essential operations necessary to support the abstract idea of list. By listing too much we also may start to drift into other ideas that are not necessarily list related which may confuse and crowd this simple idea with too many features. There is nothing preventing us from adding new interactions later as we discover them and classify them as list operations, but it is often a good design decision to keep things simple and to let complexity emerge later. 

For example, we might be tempted to add a variety of remove interactions to support all the different ways removal needs to be supported. But we can actually still support something like remove by absolute position if we just call remove i times. This would remove everything preceding the element to be removed, so we could use add for each element removed preceding the i-th element to ensure these elements are put back into the list. It may be inefficient and it may result in the list being reordered, but this approach still fulfills the general behavior of any remove( position ) interaction we might define.

### Interface 

We use the term **interface** to generally describe interactions and behaviors. An interface can be thought of as a location where two or more entities interact. Generally we want to provide prescribed interfaces that facilitate positive, specific, and protected actions between entities. We may use the term about a single method, as in the method interface is just another way to describe the **method signature**, *i.e.* the method label, return value, and list of input parameters. We may use the term about a class, as in the class interface is a way to describe all the methods defined for the class, or the public class interface, as in all the methods exposed to outside entities with the public access modifier that allow interaction with the class.

In Java there is also the interface keyword which meets all the above definitions but also has a very narrowly tailored definition. Recall the earlier definition of the Shape class:

```java
interface Shape {  
    float area();  
    float perimeter();  
    void draw();
}
```

This may seem odd, but it is a legal definition in Java and is in fact how we define ADTs in Java. Remember that an abstract data type defines “what it does” and not “how it works”. In other words, an ADT only defines the interface, *i.e.* the method declarations for that data structure, and does not prescribe the implementation, *i.e.* the actual method definitions. The implementations are left up to any classes that fulfill (implement), the interface which brings us to the rest of the example:

```java
class Circle implements Shape {  
    float radius;   
    float area() { 
        return 3.1459 * radius * radius; 
    }  
    float perimeter() { 
        return 3.1459 * 2 * radius; 
    }  
    void draw() { ... }
} 

class Rectangle implements Shape {  
    float length;  
    float width;   
    float area() { 
        return length * width; 
    }  
    float perimeter() { 
        return 2 * (length + width); 
    }  
    void draw() { ... }
}
```

The `Circle` and `Rectangle` classes use the implements keyword to declare to Java that these classes will fulfill the interface established by `Shape`. In order to be a `Shape`, a class must implement the Shape interface. Which probably raises the question of why would we do this and the answer is both inheritance and polymorphism.

According to the example, any `Circle` object is also a `Shape` and likewise any `Rectangle` object is also `Shape`. This provides a number of benefits:

- We design a list that holds generic `Shape` types instead of two different types of lists, *e.g.* `RectangleList` and `CircleList`.
- We can pass any `Circle` instance and any `Rectangle` instance as a `Shape` parameter without needing to know if it is a `Circle` or a `Rectangle`.
- If we find we are using the wrong implementation later, we can change out a type declaration without needing to rewrite everything because all entities use the same interface.

This last point is not a great example with shapes, but it is a good example when dealing with lists. Consider the following example:

```java
interface List {  
    void append( Object o );       // append an element to the end of the list
    Object get( int i );           // get a reference to list element by absolute position
    Object remove( int i );        // remove an element by absolute position
    int length();                  // get the length of the list
    boolean contains( Object o );  // determine if a specific element exists in the list
} 

class ArrayList implements List { ... } 
class LinkedList implements List { ... }
```

If both `ArrayList` and `LinkedList` classes fulfill the `List` interface without exposing additional methods or any of their instance variables, then the only way to interact with these entities is by using the `List` interface. This means you can change out one data structure for the other at a later time without worrying about breaking anything. 

For example, suppose we started development and chose an `ArrayList` for our implementation:

```java
class ListApp {
    public static void main( String args[] ) {
        ArrayList list = new ArrayList();    
        list.append( new Element(1) );    
        list.append( new Element(2) );    
        list.append( new Element(3) );    
        list.remove( 1 );        
        for( int i = 0; i < list.length(); i++ ) { 
            Object o = list.get( i );
            ...
        }
        ...  
    }
}
```

Suppose we discover months after release that the `ArrayList` was a poor choice and we really needed to use a `LinkedList`, if we did not share the same interface and did not adhere to it, we might need to make hundreds or thousands of changes to our code, which could result in months of debugging and potential disaster if we are not thorough in our reassessment of the system. However, if we used the abstract data type as a template and we stuck to it rigorously, all of those hours of redeveloping and debugging and the massive risk of bulk changes might be reduced to a small, single change:

```java
class ListApp {
    public static void main( String args[] ) {
        LinkedList list = new LinkedList();    
        list.append( new Element(1) );    
        list.append( new Element(2) );    
        list.append( new Element(3) );    
        list.remove( 1 );        
        for( int i = 0; i < list.length(); i++ ) { 
            Object o = list.get( i );
            ...
        }
        ...  
    }
}
```



### Layering

The purpose of the ADT is to intentionally create layers that hide the implementation away from users. Class users engage with the abstraction layer and if it is well defined they don’t need to know anything about how the class is supported to use it.

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXesZCpgc3W_1bmR3x9ZqbIdIIi16qahG48_Gt2Z0oEWFZV8ezBFpeTTXTC7CgXcMCs-x-RShnq-NuM-fipP7euO-Xs8Xnzxt1Ibv9dmXcvzuHdG0dWnrgHbUyQ-IQ0_cxfsTgc2lA?key=qlc-kZfti0Po1qPlKts6I4C5)

Users of the class only see the public interface and these are the only interactions available to them. As far as a class user is concerned a linked list is indistinguishable from an array list in terms of how to use it because they have the same external interface.  The details are intentionally hidden away within the classes so that class users cannot manipulate the internal state of an instance without validation.

We limit what is accessible to class users by using access modifiers to limit what users can interact with inside the class.  If the instance variables are hidden from class users by `private`  declarations and well reasoned and controlled accessors and mutators are the only means to access the internal state of the object, then class users can only interact with methods intentionally made `public` which prevents class users from binding to implementation specific variables, like the array backing an array list, and ensures that class users must use the prescribed interface.

It is not necessary to know how something works in order to use it if it has a well designed interface.  We can hide the implementation from users to protect the system and users from poor usage, like how the hood of a car keeps one from putting their hands inside a running engine.  A system that hides the implementation from the user is called a "black box".

### Black Boxing

A **black box** is a system that we don’t need to see inside a box in order to use it. By making an opaque “black” skin around the box and providing only specific ports and buttons on its surface, a designer protects internal components and provides the supported interfaces to the user. This limits how the box can be used and ensures the internal state inside the box remains consistent with any design assumptions. 

Any provided external interfaces, i.e. buttons like a power button, screen, keyboard, etc. or ports like USB or lightning connector, prescribe the legal and supported actions and features of a device. These interfaces represent the expected, supported, and sometimes legal ways a system is to be used.  

When you attempt to open up a physical device, you often encounter various tamper indicators, stickers or fasteners, designed to be destroyed if the device has been opened after sale.  These tamper indicators allow a manufacturer to determine if the box has been opened by a user. A manufacturer typically protects its liabilities through legal contracts, e.g. a warranty or end user agreement, that specifies the box never be opened and these tamper devices help ensure the manufacturer can detect tampering and contract violations. 

The skin of a black box plays an important role. It prevents users from interacting with the object in ill-advised or even dangerous ways. If your phone did not have a case around it and all the internal wiring was exposed, you could easily short out the battery or damage other components just by touching the phone in the wrong way. For this reason we also want to provide a skin for classes. We can skin a class, i.e. hide information, if we generally assume every instance variable and method is private to begin with and only set those methods that we explicitly approve for use by a class user to be `public`. It requires much more developmental work, but for large systems, it is imperative to limit and control access to internal class components so that the class performs as advertised and cannot be corrupted by user interference with internal state.

### Generic Classes (Templated Types)

Throughout the material of this course there is one question that constantly lurks in the shadows, how do we implement a data type that can support all types. So far, in each of our examples the class designer has specified a type for data stored in a class, but is there a way to design a class such that the class user defines the type stored in the class. Java is built on inheritance and we have the `Object` type as the base class at the top of the object hierarchy, so we might try to specify data generically as an `Object`. 

This is object reference polymorphism.  If every class inherits from the `Object` base class, then every type is both its specified type and `Object` type.  To create an object of specialized type, we have to declare it of that type and create it using the associated constructor; however, once the instance is created, we can cast its reference to any type that is in its inheritance hierarchy.

Our `List` interface would therefore define any methods that require the type of the data to be specified as base class `Object` types.  For example:

```java
interface List {  
    void append( Object o );  
    Object get( int i );  
    Object remove( int i );  
    int length();  
    boolean contains( Object o );
} 
```

On the implementation side, any classes that implement the List interface would fulfill the List interface using the base class `Object` type.

```java
class ArrayList implements List {  
    Object[] data;  
    int size;
    
    ArrayList( int size ) {
        data = new Object[size];
        this.size = size;
    }
    
    void add( Object o ) { ... }
    Object get( int i ) { ... }
    Object remove( int i ) { ... }  
    int length( ) { ... }  
    boolean contains( Object o ) { ... }
    ...
}
```

This would allow programs that interact with any `List` derived class to pass base class Object references to the list; however, it would require the class user to know what type each Object stored in the list is in order to cast it to its correct type when ready to use it.

```java
ArrayList list = new ArrayList(10);
// The Integer references can be implicitly downcast to Object types since the 
// Integer class inherits from the Object class
list.append( new Integer(1) );
list.append( new Integer(2) ); 
// get returns a reference to an Object type, so to use it as an Integer type
// the returned reference needs to be explicitly upcast to Integer.  It can
// get complicated even with only a single type in the List to cast appropriately
// every time we interact with the list.
int x = ((Integer) list.get(1)).intValue();
```

Instead of using the `Object` base class we could instead ask the class user to provide a type when they declare a `List` using generics similar to how we defined generic functions.  Instead, we will define a generic class:

```java
interface List<T> {  
    void append( T o );  
    T get( int i );  
    T remove( int i );  
    int length( );  
    boolean contains( T o );
} 
```

In the above interface, we are no longer explicitly specifying the type of the data stored in the list until the list is declared.  The implementation side uses similar syntax:

```java
class ArrayList< T > implements List<T> {  
    T[] data;  
    int size;   
    
    ArrayList( int size ) {
        data = new T[size];
        this.size = size;
    }
    
    T get( int i ) {
        if( i < 0 || i >= size) {
            return null;
        }
        for(int i = 0; i < size; i++) {
            return data[i];
        }
    }
    
    void append( T o ) { ... }
    T remove( int i ) { ... }
    int length( ) { ... }
    boolean contains( T o ) { ... }

    ...
} 
```



### Review

1. What is the role of a class?
2. When is a constructor called?
3. What does the `new` keyword do?
4. When is the `new` keyword used?
5. What always follows the `new` keyword?
6. What are the characteristics of a constructor?
7. What is the default constructor?
8. What happens to the default constructor when an explicit constructor is defined?
9. Why should you provide an explicit constructor?
10. Why does it make your class less safe when you rely on the default constructor?
11. What is a parameterless constructor?
12. What is a parameterized constructor?
13. What is an access modifier? 
14. Why should you generally make instance variables private?
15. What is a mutator? Is a mutator read-only or write-only?
16. What is an accessor? Is an accessor read-only or write-only?
17. How can you combine mutators and accessors to control read and write access to instance variables?
18. What does it mean for an instance variable to have the `public` keyword in its declaration?  What if it has the `private` keyword instead?
19. What is an object?
20. What is an instance?
21. What is the relationship between instance variables and an instance?
22. What does the `this` keyword represent?
23. How can this be used to change the scoping level of two variables with the same name but with different scopes, *i.e.* from local to instance?
24. What does the word abstract mean in the context of computer science?
25. Explain the concept of *encapsulation* in the context of OOP.
26. Explain the concept of *information hiding* in the context of programming.
27. Explain the concept of *inheritance* in the context of OOP.
28. Explain the concept of *polymorphism* in the context of OOP.
29. Why do we create abstraction layers?
30. What is meant by the term *interface*? What is meant by the terms *interactions* and *behaviors* with respect to an interface?
31. What does the Java keyword `interface` mean? What is its relationship to a class?
32. How does the Java interface relate to the `implements` keyword?
33. What does Abstract Data Type mean?
34. How is an abstract type typically expressed in Java?
35. What is the minimal List interface?
36. What are the characteristics of a list?
37. What do we mean by *absolute position*?
38. What do we mean by *relative position*?
39. What do we mean by “the list is an abstraction”?

# 8 - Linked Lists

A linked list is built on relative position much like standing in a line allows us to build a linked structure.  Consider that you can successfully stand in line without ever knowing or managing your absolute position in any way.  Instead you maintain your position in line simply by keeping track of who you are adjacent to.  This is the underlying idea of relative position, *i.e.* maintaining position with respect to references to neighboring elements.

## Singly Linked List

The term "singly" in singly linked list describes the number of references used to maintain relative position.  Based on the "standing in line" analogy, a singly linked version of this line would be each person only needs to keep track of who is standing behind them in order to maintain the integrity of the line.

The key to this structure is that each element must keep track of neighboring elements and we will need a structure that supports this reference based structural information.

### List Node

The list node is a very simple container that will encapsulate together a data element and in the most simple form a reference to the next element. Consider a line where you keep track of who is behind you to organize the list. You are a node and you are also tracking a reference to the “next” following element behind you.

<img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXfC4HNv_DRiTbRKkRJ9tRMfcpEIpJOG0dOdAgISLOZAg5z9KGAKGtXnylMewfRkaBArAgI1bj_Ftcdj7WeRDB4FIRZhHwXcwuAB3SIMA4jbFeIJWdCrMxUVvTIoDpV2K-ZjpoQX?key=-TPZkgWYQlZl8XvMrEGxfCGv" alt="img" style="zoom:67%;" />

Since Java is a strongly typed language, both of these elements must have associated types declared.  The following `class` is one possible way to express the above Node type.

```java
class Node {
    int data;  
    Node next;
}
```

In the above example, we are assigning the `data` field an `int` type.  This is primarily for illustrative purposes because it would be more practical to define a single Node type capable of holding a wider range of types of data.  To do so, we could make the type of the data field a reference to a generic Jav `Object`, but to use this effectively, we will need a better understanding of polymorphism in Java.

```java
class Node {  
    Object data;  
    Node next;
}
```

The real oddity for novice programmers is seeing an class contain a reference to an object of the same type. It is very normal for this type of referencing to occur. The disjoint in reasoning comes because a student is often still thinking of reference types as objects and not as reference types.  Back in our standing in line analogy, the node serves as us “tracking the next person” in line not as a “person within a person”.  In other words, it is not some recursive situation, *i.e.* a node object does not contain another node, but instead involves a reference, *i.e.* a node points to another node. 

Nodes can of course be more complex and we will see other data structures with similar nodes but more properties later in discussion.

As mentioned in the introduction to generic functions in the chapter 5 discussion, a data structure can be defined with generic types as well.  The details of this will be covered more in the chapter 8, but the `Node` structure could instead be defined as the following to allow for an explicit type for the `data` element at compile time while still supporting any type:

```java
class Node <T> {  
    T data;  
    Node<T> next;
}
```

The rest of this chapter will first focus on defining a linked list using an `int` primitive type. 

### Minimal Singly Linked List

Any linked list will be built out of nodes and at the very least a head pointer. The **head pointer** refers to the first element in the list and through the next pointer of the first element, *i.e.* pointed to by the head, subsequent elements are linked and accessible. The end of the list is indicated by the last node-in-the-list’s next pointing to null which indicates that nothing follows it.

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdQIC0w0ESO3NtfX4U6RfL1dRABUIhJFvGywua3uhHQbCkkhxGj6e3gViO3YQ822ldQGkPj_s8YOcjZaiGWlIrMNo-4kBMo_gtjIqjXPS7l46xDTDpVHxkbX6GSB_8nLby07ZMnLQ?key=-TPZkgWYQlZl8XvMrEGxfCGv)

Linked lists can have more complex construction, but the above design is remarkably capable of supporting all important list operations although some operations can be made more efficient by adding additional complexity to the linked list structure. We will slowly add additional features here, but it is important to understand that you only need to implement more features for wider ranges of linked list applications and in some systems, *e.g.* operating systems, you may encounter linked lists that are as simple as possible to minimize their space complexity.

#### Iterating Through a Linked List

> **Iterators** 
>
> An **iterator** is a pointer with the specific role to move through the data. It is a temporary pointer used to point to existing data so generally it will not be assigned to a new object. Instead it is assigned to point to an existing object, so it is a shallow copy of an existing reference.  For non-linear, complex data structures, indexing stops making sense and it is necessary to find an alternative means to move through a data structure rather than using a simple, indexed `for` loop. The iterator is an extremely flexible tool that facilitates traversal of any data structure and it is very important to learn what an iterator is, how it works, and how to use it. The linked list is the simplest structure to apply and learn this tool, so it is critical to adopt it now.  As a result, we will generally abandon the `for` loop construct for linked lists as it is primarily focused on indexed based approaches and we will instead adopt the `while` loop construct to iterate over linked lists.  If you continue to use the `for` loop here, it can lead to suboptimal, inefficient implementations, so you need to get comfortable with alternative iterative approaches that do not rely on conventional `for` loops.

We will use the variable name `it` when declaring an iterator. The label `it` is simple, easily recognizable, and distinct which evokes the idea of both iterator and the standard `i` used in indexing. A longer label, `iter`, may also be common in some organizations and conventions.

We can assign our iterator to the head to point to the first element.  Remember that we are using this specifically to look at existing elements, so we are rarely assigning the iterator to a new node instance.

```java
ListNode it = head;     // points to existing head, not a new node
```



![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXef1Y_lYfOtaZssjNj2xRq18gIGIKqf8NP2gjiQGpBZZKHzDvz9F0V9YraS6_bUT-TO0eFK2JMAqsGpFwitR4KUXbrZfueIx4Q4l7FHgQFvzf2B0PEKsSEc7rJ-Dh4yosSZylABDw?key=-TPZkgWYQlZl8XvMrEGxfCGv)

To advance through the list, we can assign the iterator to its own next pointer.

```java
ListNode it = head;
it = it.next;
```



![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdXTXauDi-7GLNVe_xgmXuofoU_RSa5mqLL31LWAkyRiO1ySnA9kGfhP-mBLy4MapJ91L3ur8c_iEX-31GExhOog1aoQNRKyAtSWif93-nr1caI6BKH8SQvBSOFLaI3zCoM-X4U?key=-TPZkgWYQlZl8XvMrEGxfCGv)

This is where relative positioning takes over for a linked list. We can access any element relative to the head pointer.

```java
head                	// first element
head.next           	// second element
head.next.next          // third element
head.next.next...next   // ith element
```

But of course this is clunky and hard to effectively use which is where the more generalized approach of the iterator comes in:

```java
ListNode it = head;     // first element
it = it.next;           // second element
it = it.next;           // third element
...                 	// repeat the pattern
it = it.next;           // ith element
```

This generalized model is the basis of our iterative approach.  In order to traverse the linked-list, we will move the iterator through the list until we reach the end of it by using the `it = it.next` statement.  For example, we can traverse the entirety of the list with this simple `while` loop:

```java
it = head;
while(it.next != null) {
    it = it.next;
}
```

There is a slight problem with the above `while` loop as it is difficult to do anything meaningful once the iterator goes beyond the tail of the list by reaching `null` but the solution is rather simple and only requires a slight adjustment to the condition the loop is based on.

#### Adding at the head

Recall the first operation we need to make a list usable is the ability to add to the linked list. Let’s start with the assumption that we generally add at the head of the linked list and that this linked list is empty. To add the first element, we would use the following.

```java
head = new Node(data);
```



![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfp9GlEecjypnYb5qJAaYJSvVsGU_VPtIrQkY7Zf45GGH1hArVUL4xwfSg86LFzqLHLaXmNBjPlNGsR7lP9lrxTYVukC6ay9tYwWoehDmmXljqVlagExSmQO3qetJq4nV_4F5bd9A?key=-TPZkgWYQlZl8XvMrEGxfCGv)

We can add further elements at the head with the following

```java
Node n = new Node(data);
n.next = head;
head = n;
```



| 1    | ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdPeTG1hTO_qM0Yv9uMlvMjjnWml2-3IE1L2KqN0MFsSKx02G3FdzBKnk4WpG3dyMgRAP4yKeUDQcT-BqPr4tUg6pP6N3QX3BtAsyKzrYKjuBgFG0PuwmKmWTQFBGsrsI9m_e1tRw?key=-TPZkgWYQlZl8XvMrEGxfCGv) |
| ---- | ------------------------------------------------------------ |
| 2    | ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXexXIewrLkDc6r6L3OrT4yJvmtLPNaVfuUPzZrp7QdlyLoDDxyq8xLEJGu_8jpiTUdHojQbwQ7fkspFRb85brFKmycvbHzAAAOAK6ADTFXnpWx4dZ5wj7O2zVnXLTBqkgTyMeaYRQ?key=-TPZkgWYQlZl8XvMrEGxfCGv) |
| 3    | ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdRZkvijW5mwlO32-aE6FtEvjbrChpBH4S5Ktc4LhHuucor0b59BjcmrW-DlZjt-UErdZs1QvnYnDQM07kFxs2qApmED_iDC-dy4RXkMb5qKsS4axxA2W2d-rJVaIP646ZWnn00iA?key=-TPZkgWYQlZl8XvMrEGxfCGv) |

Now consider the efficiency of inserting a element into the head and contrast this efficiency with inserting an element into the first position of an array,

Given a non-empty linked list, regardless of how long the linked list is, it takes only three statements to insert at the head location; therefore, the relationship between n where n is the size of the linked list and the number of operations for insert at the head is always constant time complexity. Given a non-empty array, the relationship between n where n is the size of the array and the number of operations for insert into the first position of the array is always linear time complexity because to insert at the first index we must always first shift every element to the right to make room in the first position of the array regardless of whether or not the array is full. So if faced with an application that requires high frequency insertion at the beginning of a list, the most efficient choice is the linked list over an array.

#### Removing at the head

Now that we have demonstrated that we can add at the head of a linked list, can we also remove at the head of the linked list. And in particular, since we have linear time complexity with insertion at the head, do we have the same performance with removal at the head.

First we need to ask what is necessary in the implementation to remove the head and it turns out that it is a rather simple single line of code.

```java
head = head.next;
```



| 0    | ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdQIC0w0ESO3NtfX4U6RfL1dRABUIhJFvGywua3uhHQbCkkhxGj6e3gViO3YQ822ldQGkPj_s8YOcjZaiGWlIrMNo-4kBMo_gtjIqjXPS7l46xDTDpVHxkbX6GSB_8nLby07ZMnLQ?key=-TPZkgWYQlZl8XvMrEGxfCGv) |
| ---- | ------------------------------------------------------------ |
| 1    | ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcje88ttJc2-KfJ5pfEPaPYNQdVfvePSxqPVMLfZxGg5-WmkIOmEkQuesWxphPAE718ZuTg73mVUjuZ0fh07R5CuM5C7MejJoRhaQpnIC0vTksuuCGooVAnVB_JK2j4CGiV6mFoUw?key=-TPZkgWYQlZl8XvMrEGxfCGv) |
| 2    | ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdm76F99HWu4FQOcw20jAmvsrKj748mHIbE8bDxGELn2o46mSgbQ2HW0L8EFUkSV9zlcIfX5hZ7RBOEhHmPDgqTlFFb0vYVByhWiSY-W-0pete7JmvcVo5zScTqDoqsYyrRGng8jA?key=-TPZkgWYQlZl8XvMrEGxfCGv) |

In the step 1 of the code, the head is advanced to the second element via `head.next` which means that there is no longer a reference to the first element in the list. Since there are no references to the first element, the Java garbage collector comes along and cleans up the now orphaned first element and what was the second element is now the head of the list.

> **Garbage Collection**
>
> Garbage collection is a feature of some languages but not all.  In C based languages there is no garbage collector and so this automatic cleanup of orphaned objects does not exist.  This means it is the developer’s responsibility to clean up memory manually in some languages and the linked list remove implementation in other languages may involve one or two more steps.  The concepts proposed here are universal to all languages, but you will need to study the language features of your development language of choice and adjust an implementation accordingly.  This is one of the reasons we use pseudo-code as a proto development language since it abstracts away language specific requirements.

If we needed to return the data in the first element in addition to removing it we can make a simple adjustment by adding an additional variable to retain the reference to the first element and return the data.

```java
ListNode it = head;
head = head.next;
return it.data;
```



| 0    | ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdQIC0w0ESO3NtfX4U6RfL1dRABUIhJFvGywua3uhHQbCkkhxGj6e3gViO3YQ822ldQGkPj_s8YOcjZaiGWlIrMNo-4kBMo_gtjIqjXPS7l46xDTDpVHxkbX6GSB_8nLby07ZMnLQ?key=-TPZkgWYQlZl8XvMrEGxfCGv) |
| ---- | ------------------------------------------------------------ |
| 1    | ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXef1Y_lYfOtaZssjNj2xRq18gIGIKqf8NP2gjiQGpBZZKHzDvz9F0V9YraS6_bUT-TO0eFK2JMAqsGpFwitR4KUXbrZfueIx4Q4l7FHgQFvzf2B0PEKsSEc7rJ-Dh4yosSZylABDw?key=-TPZkgWYQlZl8XvMrEGxfCGv) |
| 2    | ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXeZzHVrQCwJzuLsJrGWdiA9LoCB8xwRwBo169FlgNA6XAIgRArdeUltAa3zUnLNUTjBSNpTmgOu4qSv5pM-YriQQEqmARk0G3C3Z1tm_t1UI--gmlVoUZS-PLpwtBHclPi0cuRXSg?key=-TPZkgWYQlZl8XvMrEGxfCGv) |

Again consider the efficiency instead with regard to removing an element at the head and contrast this efficiency with removing an element from the first position of an array,

Given a non-empty linked list, regardless of how long the linked list is, it takes a constant number of statements to remove from the head location; therefore, the relationship between n where n is the size of the linked list and the number of operations for removal from the head is constant time complexity. Given a non-empty array, the relationship between n where n is the size of the array and the number of operations for removal from the first position of the array is always linear time complexity because to remove from the first index we must always shift every element to the left to keep array elements aligned to the first position of the array. So if faced with an application that requires high frequency removal from the beginning of a list, the most efficient choice is the linked list over an array.

#### Removing at the tail

Suppose we need to remove an element at the tail of the linked list, how would we go about this? We only have a head pointer in the structure we have so far designed, so in order to remove from the tail, we need to first find the tail, so what does it look like to find the tail and what is the efficiency?

Finding the tail will require that we iterate through the linked list until we find the last element.

| 1    | ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXef1Y_lYfOtaZssjNj2xRq18gIGIKqf8NP2gjiQGpBZZKHzDvz9F0V9YraS6_bUT-TO0eFK2JMAqsGpFwitR4KUXbrZfueIx4Q4l7FHgQFvzf2B0PEKsSEc7rJ-Dh4yosSZylABDw?key=-TPZkgWYQlZl8XvMrEGxfCGv) |
| ---- | ------------------------------------------------------------ |
| ith  | ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXeCQNoe8ADtqWT6yXJn4dqhAfyEbhejNwyIeWlPmHwqYTqLKOVvPHvj3v45I3HeX6mPGpck5DAbDH9A1k8UZGeKdMCc-5WYvMkCrQMGP-96a0j0IsvRsGh3MbTQLyeQCGdZL3-5pQ?key=-TPZkgWYQlZl8XvMrEGxfCGv) |
| nth  | ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfFXUwX87f4pLyddumAppFTYN4kd3v0nZz0OGXz48wCbyquvrUeYas9kzSF0_-UHEjtrAV1mNMFafF7fdw4Ajj7-_ljlQGn3JrFmuLmC9oYZnGoLVgK7QCS6gXOl4iSNvUgC7mjiA?key=-TPZkgWYQlZl8XvMrEGxfCGv) |

Our search condition is whether or not `it.next` is null. We use `it.next` as a part of the conditional logic because we are searching for the last element. If `it` is equal to `null` then we run past the end of the list and our iterator is now invalid.

*Remember, when iterating over a linked list use a* `while` *loop construct.*

Ah, but this poses a problem. The iterator has gone past the node element that contains the pointer we need to fix. Instead of stopping at the last node, we really needed to stop at the second to last node and set that node’s `next` pointer equal to `null`. While this is possible, it seems like we will be creating some unnecessarily complex code since we can always remove at the head in constant time.  What if we can add at the tail and remove from the head, that will give us all the useful combinations of operations: add and remove at the same end, add and remove at different ends.

#### Adding at the tail

We are presented with the same problem as removal at the tail of the linked list, first we have to find the tail. Once the tail of the list has been found, what does adding to the tail look like?

```java
it.next = new Node(data);
```

Note that finding the tail is the expensive part of adding at the tail and the code for actually adding at the tail once the tail is found is trivial.  Again, consider the efficiency of inserting a element at the tail of the linked list assuming we have to find the tail and contrast this efficiency with inserting an element into the last position of an array.  

Given a non-empty linked list, it takes $n$ operations to insert at the tail location where $n$ is the size of the linked list because we must iterate over the entire list in order to find the tail.  Insertion at the tail is constant time because it just requires allocation of a new node and assignment of a single pointer to the new node.

Assuming the array is full, we will have to allocate a new array with sufficient space to copy the original array into and to append the element to insert, then we will need to perform the copy and insertion.  Copying the array dominates this process as it requires $n$ operations where $n$ is the size of the array while allocation and insertion are at worst constant time, therefore the overall process to insert into a full array is linear time complexity.

The time complexity of both is rather dismal, but consider what would happen if we added a tail pointer to the linked list and maintained the tail pointer over all operations.

#### Inserting or indexing to any internal node

Inserting at the head, removing at the head, and adding at the tail are all constant time complexity operations for a singly linked-list with a head and a tail pointer, but consider the efficiency of other, more array inspired operations such as any indexed based operations like `get(int i)` or `add(element e, int i)`.  The array was efficient at these types of operations because its fundamental design supports constant time access by index to any element while the linked list does not have this capability.  Therefore, using a linked-list like an array is generally a poor choice because its efficiency in these operations will always be worse than what is possible using an array.  This does not mean that we should not support indexed based operations in a linked-list; however, we should be sparing in using this operations, especially avoiding writing an indexed based `for` loop around a linked-list as this becomes $O(n^2)$ for a single `for` loop, and if we need indexed based operations, we can always copy the list data into an array at the cost of a constant time copy.

Why is an indexed based `for` loop around a linked-list for a single `for` loop $O(n^2)$ time complexity?  Consider the following example:

```java
LinkedList list = new LinkedList();
...       									// append a lot of data to the list
for( int i=0; i < list.length(); i++ ) {
    Object o = list.get(i);					// there is considerable hidden cost here
    System.out.println( o );
}
```

Why is there considerable hidden cost on the line involving the `get(int i )` call, because, backing this call for a linked list would be a linear search performed with each iteration of the above `for` loop.  The above code combined with the implementation hidden behind the method call would actually look like the following:

```java
LinkedList list = new LinkedList();
...       									// append a lot of data to the list
for( int i=0; i < list.length(); i++ ) {
    Node it = list.head;
    for( int j=1; j < i; j++ ) {
        it = it.next;
    }
    Object o = it.data;
    System.out.println( o );
}
```

As you can see, the linked list `get(int i)` implementation requires a loop to back the operations.  Using a `get` call in this case results in a nested loop with both loops bounded by $n$ in the worst case; therefore, this is an $O(n^2)$ implementation even though we may have written this according the to first example above.  The inner loop's contribution to the overall time complexity is easy to overlook and this hidden cost can make the algorithm inefficient.  If we needed to use indexed based access, we should have chosen an array based data structure to begin with.

Note that the inner loop is designed as a`for` loop for this example because it maps well to indexed based problems, but most loop approaches inside the linked-list implementation would generally use `while` loops instead as suggested earlier.

Regardless of whether it is efficient or not, we can insert into the middle of the list by finding the node preceding the position at which we will perform the insertion or removal.  Assuming the iterator references the node in front of the position to insert:

```java 
Node n = new Node(data);
// assumes that it references the element before the positon to insert
n.next = it.next;
it.next = n;
```

Note that the order in which the pointers are updated is important.  Consider this alternative:

```java
Node n = new Node(data);
// assumes that it references the element before the positon to insert
it.next = n;
n.next = it.next;
```

In the alternative, the iterator's next pointer is overwritten by the `it.next = n` instruction; however, the following instruction, `n.next = it.next`, operates on `it.next`.  From the original example, we see that we first assign the new node's next element to the current element's (the iterator) next element before overwriting the iterator's next element in the second step.  By reversing these two instructions in the second example, `it.next` no longer points to the current element's original next element in the list after the first step, so the second step results in a cycle where `n.next` points back to `n` which will result in an infinite loop in the list because there will no longer be a tail element pointing to null.

We can still provide methods for a linked list that index to an internal node, whether the method is add, remove, or get, but it is important to recognize that regularly using any of these methods is dramatically and negatively affecting the data structure and the program's performance.  If the program must use indexed based approaches, the correct and optimal answer is to use an array because the array will perform in constant time for get and linear time for insert or remove for any element in the middle of the list.  However, if we are performing these same operations only at the end of the list, we should use a linked list because we can support all of these operations in constant time if the operations are exclusive to the end of the list.

Wait above, we showed that we have to first find the tail element which takes linear time before performing the constant time insertion at the tail, so how can we generally support constant time access at the tail?  The answer is to eliminate the search by maintaining a tail pointer at all times in the singly linked-list.

### Singly Linked List with a Tail Pointer

Adding a tail pointer solves the problem of finding the tail when we need to access the tail end of the list. It adds some additional overhead to each operation because we will need to check a variety of conditions to know whether or not a list is empty which may trigger operations specific to the head, operations specific to the tail, or even operations involving both pointers such as when the linked list contains one element, *i.e.* the head and tail refer to the same element, but all of this cost is constant time.

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXezkGeM7r8vf8WprMQZNCrNU3_moDrj2-0J1g6-zyB_2mObDZ6CZIVPfqIBDfpt6aFhIP9kPpCi7EzgzCiMbHxcqqd83O0Y8IpZ1jaJW4APAtVRiaF9jzdsgcF1NkqKc5P5akCKRQ?key=-TPZkgWYQlZl8XvMrEGxfCGv)

Adding the tail pointer does not affect adding and removal operations at the head, so we can still perform either operation at the head in constant time. It also does not resolve removal at the tail for a singly linked list as we would still need to find the second to last element in a costly iteration; however, it does solve the find problem for adding at the tail and reduces it from linear time to constant time insertion at the tail because the costly linear search is no longer required.

#### Adding at the tail

Recall adding at the tail once the tail was found was simply one line of code. Given a tail pointer, this code generally becomes:

```java
tail.next = new Node(data);
tail = tail.next;
```



| 0    | ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXezkGeM7r8vf8WprMQZNCrNU3_moDrj2-0J1g6-zyB_2mObDZ6CZIVPfqIBDfpt6aFhIP9kPpCi7EzgzCiMbHxcqqd83O0Y8IpZ1jaJW4APAtVRiaF9jzdsgcF1NkqKc5P5akCKRQ?key=-TPZkgWYQlZl8XvMrEGxfCGv) |
| ---- | ------------------------------------------------------------ |
| 1    | ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXeZJyE2MTvFprBNrhWRPNXoUY0zqFONlGqUQSejwBbiBd_aUYf1LWAaZmgYJTNQ-HM3Darfb1L3FzQFXQcHySfoRXuG4mCY696vPTUNm5vpCrsl1XvWrsSfZ0tnt7RZIywWvzd2NQ?key=-TPZkgWYQlZl8XvMrEGxfCGv) |
| 2    | ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcqa8p5LmPecbRLb_a9skQ0j1W0buyWMt4ZzULPgwBzC3WkWM8l0IHyeiMQJ8XCiGwGPKfZL3rMD3kIc-Egbeh1jVrHxFf8cKCLJWY_pS8baijrCCSuS39VLbu4AY_gi-Cg7yyJow?key=-TPZkgWYQlZl8XvMrEGxfCGv) |

This resolves our problem of needing to support the different combinations when interacting at the ends. When adding at one end and removing at the other, we add at the tail and remove from the head. When adding at one end and removing at the same end, we add and remove at the head. This gives us constant time complexity for all the different combinations of end interaction and we will be able to support data structures that may rely on characteristics where end interaction is high frequency.



## Doubly Linked List

We can continue to increase the complexity of the linked list structure. One change is to introduce a second link in every node such that each node can link to the node in front of it and to the node that follows it.  In other words, the term "doubly" in doubly linked list describes that two references are used to maintain relative position in the list, and in the "standing in line" analogy, a doubly linked version of the line would be each person keeps track of both who is standing behind them and who is standing in from of them to maintain the integrity of the line.  

While the doubly linked list is not necessary for interactions limited to either ends of the linked list, it does make it easier but not necessarily more efficient to remove elements in the middle of the linked list.  However, it does make bidirectional traversal much easier, *i.e.* the ability to go back, which can be a necessary feature for specific problems.

### Double Linked List Node (DLNode)

The doubly linked list node introduces a previous pointer or prev pointer to the node data structure. This previous pointer is linked to the node that precedes the node so that it is possible to move either forwards or backwards through the linked list.

<img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXdQDAe4jpY7iXyZ-_thgTBkwybtPA1dm7pz9WyoqfmpNJweZxJYAfQ9GYpViqwxbHwKnqTKQQPYkX6_nF0cW4p1gSp3pztkEz54Zvk3mDCHLDtl2hPRjkLSta0eBJ8Omwl37XRF?key=-TPZkgWYQlZl8XvMrEGxfCGv" alt="img" style="zoom:67%;" />

This can be useful in very specific circumstances, but the increase in complexity can lead to additional bugs, so not all linked lists need to be doubly linked in order to function.

### Minimal Doubly Linked List

Just as the minimal single linked list has only a head pointer, the minimal doubly linked list likewise only needs a head.

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcxBHf77tubZEo8LTJbRi95Zb2kwkZoO6XSrxpyrHpIDSeB07_2lGRYBHEHvC9zSXYJTDJVLH68Wj3Wu0N6eFUOeirRuc_6cmudkOkmZtu9-dPrccEj9uReTw37WRjxpEIUDdsLEA?key=-TPZkgWYQlZl8XvMrEGxfCGv)

The convention to determine if we have reached the tail “end” of a list, *i.e.* a node with a next of null, is also used to determine if we have reached the head “end” of the list except it involves the prev pointer.

#### Inserting or removing a node

The doubly linked list facilitates insertion or removal of a new node in the middle of the list.  The operation is still linear to locate the node; however, the implementation is fairly simple once we have identified the location to insert or remove.  

For insertion, we need to find either the preceding or following node.  Finding the preceding node is generally more standard.  Assuming the iterator `it` points to the node in front of the position to insert, then inserting a node into the middle of the list follows these operations:

```java
DLNode n = new DLNode(data);
// assuming it references the location before the position to insert
n.next = it.next;
n.prev = it;
n.next.prev = n;
n.prev.next = n;
```

Similarly, if it points to the node that we need to remove, we can remove that node with two operations:

```java
it.prev.next = it.next;
it.next.prev = it.prev;
```



## Circular Linked List

A circular linked list is created by simply linking the last element to the first element to create a cycle. A circular data structure can be incredibly useful because it is technically never ending unless it is empty. For processes that repeat indefinitely, a circular linked list may be the right way to ensure it continues to operate continuously.

<img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXeiEss0y6m_FrghumDxYfAPBqfbeKHYm4HLvOrRAhXQDLZy34M4RWYLwxZGQV4Qy4xzQSo0EItxxgzd72yUJHDi50ZrO_uCK1XiexyBhZWlBI0r9VImF87O5pJqziP_tlonWLYwXA?key=-TPZkgWYQlZl8XvMrEGxfCGv" alt="img" style="zoom:50%;" />

Since we can structure a linked list in a circular manner, it raises the question of whether or not we can do something similar with an array. In fact, we can and this special configuration of an array is called a ring.

### Review

1. What is the role of the head pointer in a linked-list?
2. Define the structure of a singly-linked linked-list node?
3. How is the end of a linked-list represented?
4. Analyze the algorithmic time complexity of append for a linked-list based List.
5. Analyze the algorithmic time complexity of remove for a linked-list based List.
6. Assuming the maintenance of a tail pointer, why is appending to the tail end of a singly-linked linked-list constant time complexity?
7. Assuming no tail pointer, why is appending to the tail end of a singly-linked linked-list linear time complexity?
8. Is it necessary to maintain both a head and a tail pointer for a linked-list to support all List interactions? Justify your answer.
9. Assess and demonstrate the feasibility of adding to the head of a singly-linked linked-list. If this operation is feasible, analyze the efficiency of adding to the head of a linked-list.
10. Assess and demonstrate the feasibility of removing from the head of a singly-linked linked-list. If this operation is feasible, analyze the efficiency of removing from the head of a linked-list. 
11. Assess and demonstrate the feasibility of adding to the tail of a singly-linked linked-list. If this operation is feasible, analyze the efficiency of adding to the tail of a linked-list.
12. Assess and demonstrate the feasibility of removing from the tail of a singly-linked linked-list. If this operation is feasible, analyze the efficiency of removing from the tail of a linked-list.
13. Define the structure of a doubly-linked linked-list node
14. What improvements does a doubly-linked linked-list node bring to a List implementation? Justify your answer.
15. What additional costs does a doubly-linked linked-list node bring to a List implementation? Justify your answer.
16. Contrast the time complexity of list operations in a linked list against list operations in an array based list.
17. Contrast the space complexity of list operations in a linked list against list operations in an array based list.
18. Justify why a `while` loop is recommended for iteration in a linked list instead of a for loop? 
19. What is an iterator?   
20. How does using an iterator for iteration differ from indexed based iteration?
21. Why should iterator based iteration be used for linked lists over index based iteration?



# 9 - Stacks and Queues

Abstract data types and a single abstraction layer are not the only level of abstraction we can introduce. We can add a variety of additional abstractions to divorce concepts from implementations including one or more policies to dictate specific behaviors for a data structure.

## Policy

The word **policy** comes from the Latin *politia* meaning “government” and we generally associate the word to mean “rule”. It shares the same root as “police”, as in rule enforcement, and “politics”, as in rule debate.

A policy in terms of programming is a rule that we will follow rigorously. The problem in programming is that rules are only as strong as the enforcement we create, and it can be easy to sidestep a rule if we do not use robust constraints to force adherence to rules by our programming team and client developers. For example, we can use information hiding to encapsulate and create abstraction layers that support enforcement simply by prohibiting access to the implementation and only allowing access through prescribed interfaces. A policy in programming can take many forms, but one way is to use an abstraction layer called a **policy layer** that not only prescribes the interface for a data type but also specifies the rules that the data type behaviors must always ensure.

As an example, we can specify simple add-remove policies that dictate the behaviors for list interactions. One such policy is that the oldest item added to the list must be the next item to be removed, a policy known in society as first-come-first-served or in the programming domain as **first-in-first-out (FIFO)**. An alternative policy is that the newest item added to the list be the next item to be removed, a policy known in the programming domain as **last-in-first-out (LIFO)**. We encounter these policies in daily life, *e.g.* FIFO is applied in every line you ever stand in and LIFO often emerges when unloading a box or an elevator.

These policies are so regularly encountered at the application level, that programmers have defined formal names and interfaces for lists that follow these two policies. A FIFO list is known as a **queue** and a LIFO list is known as a **stack**.

![layers-policy_stackandqueue](/home/jrt/gwu-new/course/cs1112/assets/layers-policy_stackandqueue.png)

In other words, a stack is a specialized list that has additional rules that may invalidate the general list interface to ensure the rules are consistently enforced. Similarly a queue is also a specialized list that also may invalidate the list interface for consistent enforcement. Because both are lists, both can be implemented using either an array or a linked-list; however, one implementation may be better suited than the other based on efficiency.

## Stack

A **stack** is a specialized list that operates under a last-in, first out (LIFO) insertion and removal policy and we intentionally use language that suggests vertical structuring. For example, we use terminology like top and bottom when referring to the “ends” of a stack and interactions occur exclusively at the top of the stack, *i.e.* a single end of a list. A stack is built on the metaphor of placing items on top of one another and items are typically added to the top of a stack, removed from the top of the stack, and when a stack is empty we have reached the bottom of the stack, so the data structure should conform to these ideas and terminologies.

Remember that abstract data types are really just ideas built on human conceived metaphors, so it is important to use language that conforms to these metaphors so everyone can understand any discussions that involve that data type. Inventing new language for well settled ideas will result in lack of clarity, misunderstanding, and ultimately bugged implementations. For example, novice students have a tendency to use terms like the front of a stack which omits the proper context and raises the question of whether the student means the top or the bottom of the stack.

### Stack Interface

The minimal stack interface consists of three interactions:

```pseudocode
void push( element ) : Takes an element as input, places that element on top of the stack, and returns nothing
    
element pop( void ) : Takes no input, removes the top element from the Stack and returns that element
    
boolean isEmpty( void ) : Takes no input, returns true if the Stack contains no elements; otherwise, returns false
```

A fourth interaction is also common for stacks but it is not a necessity for basic stacks:

```pseudocode
element peek( void ) : Takes no input, returns the top element from the stack without removing the element from the stack, *i.e.* the stack must remain unchanged.
```

> **Feature Creep, Trust, and Developmental Efficiency** 
>
> It may seem like that the stack interface is too simple because it does not include interactions like `remove(element)` or `get(index)`, and as a result you may be inclined to add more and more “features”, *i.e.* interactions, to the interface and there is no doubt that some features may be welcome additions; however, this can lead to “feature creep” and may start to blur the lines between different data structures and worse may allow class users to violate the policy that the data structure is supposed to enforce.  Before adding more features to a stack consider that a stack has very specific rules it MUST enforce, *i.e.* LIFO insertion and removal, so methods that may violate this policy should generally not be added to the stack interface. A stack with an additional `remove(element)` method is no longer a stack and is instead some form of hybrid data structure that supports both list and stack features and should not be extended much trust in policy enforcement on the part of the class user. Efficiency is determined at the implementation level but we are intentionally hiding the implementation. A feature like `get(index)` can be inefficient in a linked-list, so we don’t really want to expose it in the stack just to allow the stack to be used like a list. If system users want to use a stack like an array list, make them create an array list instead and give them interactions that allows conversion back and forth between array list and stack. It is impossible to write one data structure that does everything efficiently and when you try to do so it starts to do everything poorly, so create data structures that fulfill specific roles extremely well and force users to use the data structure correctly by controlling interactions with the data structure.

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdpUIZyda1Rc14TteqloxRFeeHJdDlCXH4UH43RwTIrBG-F8M62IJbmzMT1FrtcmsUwcjapjcEK-ipqMkGJLSrD2yYn8Luul69AMvv-TnuqpiP-oqMt_ojoXTbvPG5zyP94jKgmIw?key=3j7PrUznQLmvtkr4cdFHOW7i)

A stack is empty if the top of the stack is at the bottom and a stack may have a maximum capacity determined when the stack is initially created, especially if the stack uses an array-based implementation.

### Stack Applications

We have talked about one specific stack application throughout the semester and that is the memory stack. The stack in the memory model operates exactly like a stack: we push a new stack frame onto the stack every time we call a function, we pop the current stack frame (top) from the stack when a function returns. We call it “The Stack” because it is a stack.

In the real world, we see stack behaviors naturally emerge in situations like the loading and unloading of an nearly full elevator.  A new passenger squeezes into the elevator and stands at the front because there is no room to maneuver inside the elevator.  At the next stop, this new arrival must get off the elevator before anyone else can get off.  The full elevator is the correct example here because in a non-full elevator, humans will self reorganize inside the elevator car because they don't want to have to exit the elevator car before reaching their destination.

In a more general sense, stacks are incredibly useful in maintaining a history of data and facilitate going back to an earlier step in that history.  This is one way to implement the back button on your browser or the undo (Ctrl-Z) option in most applications.  In these applications, a stack can be used to record the last $x$ actions and you can step back any number of actions less than $x$ by popping the history stack. In a browser, it back and forward can be modeled using two stacks, one for back and one for forward, such that when back is activated, the topmost link on the back stack is popped and that link is then pushed onto the forward stack and vice versa when the forward button is activated.

## Queue

A **queue** is a specialized list that operates under a first-in, first out (FIFO) insertion and removal policy and we intentionally use language that suggests horizontal structuring. For example, we use terminology like front and back when referring to the “ends” of a queue and interactions occur at both ends of the queue, *i.e.* at both ends of the list. A queue is built on the metaphor of standing in line and people typically join the back of a line and leave when they reach the front of a line, so the data structure should conform to these ideas and terminologies.

### Queue Interface

The minimal stack interface consists of three interactions:

```pseudocode
void enqueue( element ) : Takes an element as input, places that element at the back of the Queue, and returns nothing

element dequeue( void ) : Takes no input, removes the front element from the Queue and returns that element

boolean isEmpty( void ) : Takes no input, returns true if the Queue contains no elements; otherwise, returns false
```

Similar to stacks, the peek interaction is also common for queues but it is not a necessity for basic queues:

```pseudocode
element peek( void ) : Takes no input, returns the front element from the queue without removing the element from the queue, *i.e.* the queue must remain unchanged.
```

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdLcvL9P6JDRzRR2jLd1EbA6dPtNUT4LLl8nIv5e5N1OqaOIFYjqR-5BN7ls-eG67U-kcdYGTMoC-qxzWeE_bI6435czHZPSS9EhaacZ4c6fOyg_8PjcJlWp1ytXy5OhSa8BVv2?key=3j7PrUznQLmvtkr4cdFHOW7i)

Most queues can be considered empty if the front of the queue is at the back and a queue may have a maximum capacity determined when the queue is initially created, especially if the queue uses an array-based implementation.

### Queue Applications

We encounter queues on a daily basis in society because we structure many interactions around waiting in line, so we will need a queue in an application whenever we need to model the idea of standing in line. At a high level, queues are used to model play-lists in audio and video streaming services, for waiting models like buying concert tickets on a virtual marketplace or waiting to be matched in video games, or for other applications.  

There are more sophisticated forms of queues where there are multiple lines where certain lines have specific priority.  For example, some airlines have "priority boarding" and they model this by assigning passengers priority groups and many airports have priority security where passengers who have been "prescreened" are allowed to us a security lane dedicated exclusively for qualified passengers.

## Implementation

Recall that the stack and queue are just lists with specific rules for adding and removing elements and the basic stack implementation only requires we support interactions at one end

## Stack Implementations

When interacting with a stack, we will interact with only one end of a list data structure, so we want to implement our interactions such that they use the underlying data structure in the most efficient manner. For example, adding and removing at the front of an array is always $O(n)$, but adding and removing at the back of an array can be $O(c)$ if there is space in the array. 

Remember that worst-case does not mean intentionally creating a bad design for data structure. Worst-case naturally emerges from usage in an application as a function of data in the data structure which can be difficult to detect and control. We intentionally design our algorithms and data structures, so we can make choices that may mitigate worst case scenarios.

### Linked List Based Stack

If we were to implement a stack using a linked list, what design elements are needed to support the fastest insertion and removal policies? Considering that a stack requires interactions at only one end and all linked-lists have a head, we should ask whether or not push and pop, *i.e.* add and remove, can be done in constant time at the linked-list head.

Recall that adding to the head involves the following code:

```java
Node n = new Node(data);
n.next = head;
head = n;
```

The number of lines to add to the head does not vary with the size of the list, so adding at the head can be done in constant time.

Recall that removing from the head involves the following code:

```java
ListNode it = head;
head = head.next;
return it.data;
```

The number of lines to remove from the head does not vary with the size of the list, so removing at the head can also be done in constant time.

Note that we are still retaining the head terminology introduced in linked lists for consistency, but we could easily instead call it top to conform to stack terminology. In other words, in a linked list implementation, the head acts as the top of the stack.

Since both add and remove can be implemented in our most basic singly linked list with a head pointer only in constant time, we can easily support push and pop with constant time operations using a linked list implementation. We can also test whether or not the stack is empty in constant time by a simple test of whether or not the head is null and we don’t really need to keep track of counts or other features to support the basic stack with a linked list.

This suggests that a linked list is an excellent data structure to support stacks in terms of time complexity. However, recall that each element in the basic linked list requires two pieces of information to maintain each element in the list: the data and the next pointer. It is worth considering whether the cost in terms of space is too expensive and an alternative implementation should be sought.

### Array Based Stack

If we were to implement a stack using an array, what design elements are needed to support the fastest insertion and removal policies? The challenge we face with an array based stack is that stacks grow and shrink dynamically while arrays are more static and for an array to grow and shrink, it requires relatively costly, *i.e.* $O(n)$, copying because we have to allocate a whole new array and copy data from the old array into the new array in order to “grow” the array. Is it possible to mitigate this weakness somewhat so that we do not need to copy arrays at all or at the very least copy with very low frequency.

Inserting and removing elements at the low order index of the array is going to result in $O(n)$ efficiency for insertion and removal. If we force insertion to occur strictly at the 0 index, we have to make space for the new element which would require us to shift all elements to the right assuming there is space in the array. If we force removal to occur strictly at the 0 index, we have to eliminate the space created when the element is removed which would require us to shift all elements to the left.

Suppose instead we have an array that has more space allocated than it currently uses and we insert and remove elements at the smallest available high order index (in a zero based indexed array, this is the index `n` which is the `n+1` position and element in an array since it is zero based), what is the efficiency of insert and remove? 

In this array, the n index is a legal position because the space is already allocated and because arrays support constant time access to any element in the array, we can assign the element to the `n+1` position in constant time.

```java
int[] A = new int[2 * n];  // allocate more space than needed
count = n;                 // array contains n elements
A[n] = value;              // inserting a new element in O(c)
count = count + 1;         // updating the number of elements
```

Similarly, in this array we can remove an element from the highest order position in constant time because we do not need to allocate a new array (just absorb the space into the array’s **free space**, *i.e.* the difference between the array’s **used space** and array’s **allocated space**) and copy when an element is removed. In fact, we don’t need to technically remove the element, we just need to reduce the count of elements.

 ```java
 count = count - 1;         // removes the last element
 ```

Based on this argument, assuming we have sufficient free space in an array, we can support constant time insertion and removal if we perform these operations at the highest order index in the array’s used space. This does raise several questions: how much space we should provide for an array that needs free space, what we should do when the array is full, and are there other ways to use arrays that will allow us to operate on both ends of the data without expensive shifting.

Trading Space Efficiency for Time Efficiency Memory is cheap and plentiful. While improvements in processor speeds has reached a number of physical limits that raise questions about future processor speeds in terms of Moore’s law, memory has consistently grown according to Moore’s Law which has resulted in extremely large amounts of memory for very low prices in all forms of electronics on the current market. Arrays have a very tight relationship between space and time performance especially if we only allocate just enough space for the array to hold existing data. However, if we allocate more space that we anticipate for an array, we can minimize the number of times we have to grow an array. When we grow an array, the naive approach is to allocate an array of only one additional element which we will immediately fill up forcing subsequent insertions into the array to grow again. This leads to $O(n)$ time complexity for all inserts (best case, average case, and worst case) and $O(n)$ space complexity overall for the array. Is there an alternative that can improve the efficiency? Consider that if we fill up an array of size $n$ and have to grow it in anticipation of further usage, it is a reasonable assumption that since we needed $n$ spaces to hold the existing data, we will need an additional $n$ spaces for future growth. In other words, when we grow an array, we double the size of the previous array in the new allocation. This suggests a simple policy that helps minimize the frequency of the growth. In terms of efficiency, this strategy is still $O(n)$ time complexity for insert in the worst case of the array being full and $O(n)$ space complexity overall for the array; however, the best case and average case time complexity fall to $O(c)$ and the frequency of the worst case is minimized to occur on a logarithmic time scale.

## Queue Implementations

A queue is similar to a stack but different enough that the implementation needed to support a queue will require additional features for the underlying data structures. Recall that interacting with a queue requires interactions at both ends of the list data structure, so again our implementations need to support the interactions such that they produce the most time efficient behaviors.

### Linked List Based Queue

A queue requires efficient insertion at one and efficient removal at the other end. This raises the question of whether or not a linked list can support constant time insertion at one end and constant time removal at the other end and what features of the linked-list are needed to support these behaviors. Consider the following questions:

- Can we insert and/or remove at the head in constant time?
- Can we insert and/or remove at the tail in constant time?
- Does the linked-list need a tail pointer?
- Does the linked-list need to be singly-linked or doubly-linked?
- What is the design that minimizes space efficiency?

In the discussion of linked-list based stacks, we demonstrated that any linked-list with a head pointer supports constant time insertion and removal at the head. 

##### Constant Time Insertion at Head

```java
Node n = new Node(data);
n.next = head;
head = n;
```

##### Constant Time Removal from Head

```java
ListNode it = head;
head = head.next;
return it.data;
```

We can insert at the tail once we locate it:

##### Insertion at Tail

```java
it.next = new Node(data);
```

But we can eliminate the cost of finding the tail if we include a tail pointer

##### Constant Time Insertion at Tail

```java
tail.next = new Node(data);
tail = tail.next;
```

However to remove from the tail, we need to find the element preceding the tail which requires an $O(n)$ iterative search through the linked-list if the linked list is singly linked. However, we could doubly-link the linked-list which would give us constant time access to the element preceding the tail.

##### Constant Time Removal at Tail for Doubly Linked-List

```java
tail = tail.prev;
tail.next = null;
```

But this does now require a doubly linked-list just to support an operation we don’t really need. Consider that the singly linked list with a head and tail meets all of our requirements, *i.e.* constant time insertion at one end (tail) and constant time removal at the other end (head). Using a doubly linke,d-list does not increase the space complexity but it does double the number of references per element unnecessarily for no additional benefit. In some applications, space is still a premium, *e.g.* operating systems and low-level device programming, so it is important to be able to support data structures with the minimum implementation that services all requirements with the best time complexity.

### Array Based Queue

On the surface, using an array for a data structure that requires data to be inserted or removed from the low order indices is inefficient if we take a conventional approach with an array where we shift data around. However, shifting data is not the only approach we could take. Instead we might shift around the indices demarcating the front and back of the queue. In other words, instead of moving the data around, move the pointers to the head and tail around. In the conventional approach, we assume the front of the queue is at index 0 and the back of the queue is at index `n-1`.

#### Ring

The **ring** data structure is a queue implemented with an array that uses multiple indices and simple but clever math for index incrementing. Let `R` reference an array that will be treated as a ring.

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcPxtSDLTdxBiqiz1Dyejd6j2E0jTY9HEwMcHxsXfuz3s7GhHM5HEtBGoJ1ELWLv4-nakNXQ6g4G-P6YPpIQPFvfaMNzxljhFW2qICmuLVd-62had-2hQT5T0MMV_JBKgvHldLUcg?key=3j7PrUznQLmvtkr4cdFHOW7i)

The challenge is how can we use a linear data structure in such a way that it behaves like a circular structure using very simple logic to ensure high reliability.

<img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXfR3V_PLxrZeFyIlzlww548bqPBpVS2jvHPDW1ZHuYToOzTrYHqW2lOAL2p-rm8muwIldAbNiHJsZVl6aRhirUB3IEOLix08yepyYS_QJrJTPlBKCdd3BLkG4dUvv4YtZOle61WRw?key=3j7PrUznQLmvtkr4cdFHOW7i" alt="img" style="zoom:75%;" />

As with any queue we will need data elements that track the head and tail of data in the ring; however, since this is an array, we can track the head and tail elements using integer values instead of using reference types. The effect is similar (and raises some interesting questions about what reference types really are) and allows integer math to be performed on the indices. Let `h` be the index of the head and `t` be the index of the tail.

```java
class Ring {  
    private int h;  
    private int t;  
    private int[] data;  
    private int count;   
    
    public Ring( int size ) {    
        data = new int[size];    
        h = 0;    
        t = 0;    
        count = 0;  
    }  
    ...
}
```

In Java, `h` and `t` would not be reference types and instead are strictly defined as `int` types.  However, they technically are acting as pointers, so we will use pointer representations in the following illustrations. This does make sense because a reference is a form of index as an address is just a memory index.

Given the code above, our ring is initialized as the following.

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdXLts0Rp2llrnJpgNMm_WTeFTx4pqs6VyI6XEwTLeNXYrWr0JRnFT51Cq1BtGUs04NXDsfNglhB79m54Fa4wsmDH5XNswBwI4JZZ9KH6ySNWK6HZuiGyGO7kWzx-UsbNH_FGWuKw?key=3j7PrUznQLmvtkr4cdFHOW7i)

When we enqueue an element to the ring, we insert it at the position `t` and then advance `t`.

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdZCozCRa0rnF4eYvortitydiMKAPlDA07sBSRmRuVid53MRpo018n5I4Dy0j4DJL1gYbVgkuSP4QbDXclRL40rT5D1Pk4K2JCAiWRg7EpQlBKDL-qx7Y19pstztrb_smsddPLkrA?key=3j7PrUznQLmvtkr4cdFHOW7i)

When we dequeue an element to the ring, we remove it from position `h` and then advance `h`.

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcRcsb541Srynnk9vQ0hioRvxFkBQTR_sDJcM02PH_XGY-aIaGigCv6FwyUDJkcLU_YMf81_YfJez3YOVBdVI-rD0VTwqkRagZ1EOHn6BjrowYZHfhprOqdaN_VAgwUCLyH5XWE7w?key=3j7PrUznQLmvtkr4cdFHOW7i)

If a ring is full, `h` and `t` are equal and the count is non-zero.

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfuPF3K30SQ3bIAZwv_hUUy-ybpU-LgRzL1dERnmbNwOlrwKmzemWPI9ClVbV0fbHl5fWKMlRYaDawUMCVNhNRAImD_lxZHmnm4UJ3AOxBseWaeLqGM9v0SFykTy2gtKFZRn3Bzjg?key=3j7PrUznQLmvtkr4cdFHOW7i)

If a ring is empty, `h` and `t` are equal and the count is zero.

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfoa8JfpeoDrXpjq8f4DcI1zA9fvpU6oz3HU6hUXdC9FlswIyJ21whnWEN7VblzWIYHeEqexfZSjIQppDuKuGIIQD68lD2UEHvh3ac5gjTiXTQvYroA4si9aUUsl0AzMOIb03vo8w?key=3j7PrUznQLmvtkr4cdFHOW7i)

If one of our indices contains the index of the last element in the array, how can we advance it? For example, `t` equals $n-1$ and advancing it by simply adding one will cause it to index beyond the legal boundary of the array

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdpnpJS_W_HB-LhQmDCsS8JXstfXfNVis4NZ879y0E00E_yDa3IlGk8e0t9WrPWjO_Y8zdEbDn8kvW1FpWzxX1gLZW-1iE8V7Tz_ltSqpi61fz3w_YDF4Kl8ElZXODA_mvDPvMKqg?key=3j7PrUznQLmvtkr4cdFHOW7i)

So how do we advance `t` (or `h`) in such a way that it contains the value of the beginning index of the array?

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdw9i1wiPDwpuGRQlmc7EBY0PPGLgf4CUQ8ou0SO69IziQ-YP9rnJr2XKimReMPKFf6iTu-g7lmUTcZRzeximb29HUei8AtsHrRH4xRNS7Igrfa8tQ47W6gEivkx-EKG4LZtymI7A?key=3j7PrUznQLmvtkr4cdFHOW7i)

The first inclination is to write conditional logic that tries to address this issue; however, this logic can become surprisingly complex if the data structure has more complex features like allowing multiple items to be enqueued simultaneously. Can we instead handle this mathematically and robustly such that we can completely eliminate any if statements? Yes, if we advance an index using the modulo operator (`%`).

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXf_JgXDzZafns_ulO5cdXdE1_Wn3jr3ucNiBYyV39zCU1uh04tFKDAaIa6ZErjJFRq04YKlzEusbtDS-OmZWmYNcrm0ZgOvxAA7KHbhlyfARIrvkMC7B_tJuc3KCtpL9QMdIzG-?key=3j7PrUznQLmvtkr4cdFHOW7i)

Recall that the modulo operator computes the remainder of integer division. 

The equation:

$i=(i+1) \mod n$

ensures that when adding to a value that should remain bounded in the range $[0, n-1]$, the value remains in the range. Consider the following:

| $0 \mod n = 0$<br />$1 \mod n = 1$<br />$2 \mod n = 2$<br />$\cdots$<br />$(n-2) \mod n = n-2$<br />$(n-1) \mod n = n-1$<br />$(n-0) \mod n = 0$<br />$(n+1) \mod n = 1$<br />$\cdots$<br />$(2n-1) \mod n = n-1$<br/>$(2n-0) \mod n = 0$<br/>$(2n+1) \mod n = 1$<br/>$\cdots$<br/>$(cn-1) \mod n = n-1$<br/>$(cn-0) \mod n = 0$<br/>$(cn+1) \mod n = 1$<br /> |
| ------------------------------------------------------------ |

In all cases, including the last few examples which demonstrate arbitrary values around the range boundary, the math just works out such that the result of the calculation is always within the range. In other words, the use of modulo allows creation of a simple math expression that automatically resets the calculation such that it can never violate the range and the index will never be out of bounds. This eliminates the need for any if statements and reduces the likelihood of introducing a bug in the indexing logic. It also conceptually wraps the indexing of an array into a circle, *i.e.* indexing goes around and around without limit on the number of cycles but still bounded in the legal range, and practically the array behaves like a circular data structure, hence the name ring.

<img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXfR3V_PLxrZeFyIlzlww548bqPBpVS2jvHPDW1ZHuYToOzTrYHqW2lOAL2p-rm8muwIldAbNiHJsZVl6aRhirUB3IEOLix08yepyYS_QJrJTPlBKCdd3BLkG4dUvv4YtZOle61WRw?key=3j7PrUznQLmvtkr4cdFHOW7i" alt="img" style="zoom:75%;" />

## Double-Ended Queue (Deque)

The **Deque** or **Double-Ended Queue** is a generalization of the queue into a data structure allowing for add and removal at both ends of the queue and therefore it is capable of acting both as a stack producing LIFO behavior and as a queue producing FIFO behavior.  Due to the increase in complexity and the hybrid nature of the structure, there is no standard interface for a deque so method labels should need to expand to clearly indicate the location of the add or the remove operation.  For example, an deque interface might include the following methods among others:

```pseudocode
addFront(element)
addBack(element)
element removeFront()
element removeBack()
```

With the added requirements, it is necessary to use a more complex implementation to support it, so a deque will generally be implemented using a doubly-linked list including both `head` and `tail` pointers so that it can support the requirements in constant time.   Because the deque must support efficient operation of both add and remove at both ends, an array is typically a poor choice for the implementation; however, if it is possible to fix the size of the structure at the beginning, a deque could be implemented using the same strategies used with the Ring to produce a constant time array-based deque.    

The deque is the more appropriate solution to the browser back button and browser forward button example because the back and forth behavior can be managed in the deque alone and eliminates any need for a second data structure.

## Review

1. Explain the First-In, First Out policy.
2. Explain the Last-In, First Out policy.
3. Define the standard minimum interface for a stack
4. Define the standard minimum interface for a queue
5. Define the insertion/removal policy for a stack.
6. Define the insertion/removal policy for a queue.
7. To have stack behavior emerge, how many ends of a list do you interact with?
8. To have queue behavior emerge, how many ends of a list do you interact with?
9. Describe the full implementation of a stack using an array.
10. Analyze the efficiency of stack operations when implemented using an array.
11. Describe the full implementation of a stack using a linked-list.
12. Analyze the efficiency of stack operations when implemented using a linked-list.
13. Describe the full implementation of a queue using an array.
14. Analyze the efficiency of queue operations when implemented using an array.
15. Describe the full implementation of a queue using a linked-list.
16. Analyze the efficiency of queue operations when implemented using a linked-list.
17. Give an example of stack behaviors in the real world.
18. Give an example of a software application where the stack is the best suited data structure.
19. Give an example of queue behaviors in the real world.
20. Give an example of a software application where the queue is the best suited data structure.

# 10 - Trees

All data structures can be expressed as graphs.  For example, we can also define a linked list as a graph because it is composed of vertices (nodes) and edges.  We can claim that all linked lists are directed graphs, whether singly linked or double linked, because the links themselves are naturally directed. Two nodes in a linked list are adjacent if there is a reference to one or the other linking them together. Additionally, the linking of nodes constructs a path that connects the head and the tail and this path connects all nodes of the linked-list to the head which is why we can access any element from the head of a linked-list. If a linked list is non-circular and singly-linked, it contains no cycles; however, if it is doubly-linked, there are many possible cycles in the linked list.

Trees are hierarchical data structures and all trees are graphs.  With a basic introduction to graph properties, we can develop a general tree definition:

> A Tree is an acyclic, directed graph where all nodes are connected to a single node called the root.

## Introductory Graph Properties

We will revisit graphs at the end of the course; however, it is useful to introduce some ideas now.

| <img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXdaNJSxVlJ3WccQ_iBPKGTBbt2wr3BCBxlTx2CZ0Wt1YmEnm0JkyMnMUrZwtQnudvcgLePokkGfZOnH7oXEah_yC_yEvOXnXHD_bpsiHATT8Iu5vZgLRQYcpBgy0wjuleKx6vLpAw?key=rlf7PWiT5fE8oCFeuqwVsRoJ" alt="img" style="zoom: 80%;" /> | <img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXfinLAXDAjgXQGx85GBmUzpxurWnePV4z7HoZle3V33YxpjGyGuX68mHGjrWe7NFAgofNyDjhDhqxktwU16bOItiDLeL-OlSsucPVELXooVU8On017pMmKb0M5BUoi5NqPGaaI3JQ?key=rlf7PWiT5fE8oCFeuqwVsRoJ" alt="img" style="zoom: 80%;" /> |
| :----------------------------------------------------------: | :----------------------------------------------------------: |
|                       **Basic Graph**                        |                      **Directed Graph**                      |

 A **graph** $G$ is defined by $G = (V,E)$ where $V$ is a set of vertices and $E$ is a set of edges.  An **edge** is a pair of vertices in the graph where edge $e_k$ is defined as $e_k=(v_1,v_2)$.  The graph may be **undirected** allowing for edges to be traversed in either direction, from $v_1$ to $v_2$ or from $v_2$ to $v_1$ allowing the vertex pair to be unordered.

In a **directed** graph,  edges have direction and edges can only be traversed along their direction, so the vertex pair may define the direction through its order, $e_k=(\overrightarrow{v_1,v_2})$, meaning that this edge only defines traversal from $v_1$ to $v_2$.  In most directed graph diagrams, direction may be explicitly illustrated by arrowheads that are interpreted as the terminating end of an edge but direction may also be implied using other conventions, *e.g.* a tree diagram uses a tiered structure to imply direction.  

Two vertices are **adjacent** or neighbors if there is an edge between them.  Two nodes are **connected** if there is a set of adjacent vertices, *i.e.* a **path**, such that it is possible to traverse from the first vertex to the second vertex through the graph.  For a directed graph, a directed path must follow any direction constraints.  A **cycle** exists if there is a path connecting a vertex to itself and a graph with no cycles is called **acyclic**.  Generally, the **distance** between vertices $v_i$ and $v_j$ is the number of edges in the path connecting $v_i$ and $v_j$ and the **shortest path** between $v_i$ and $v_j$ is the path with the minimum distance.

## Introduction to Trees

| ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcYz3LrpfSDmaHufkREmW6W4bmeP_m8hhw6QdgayROvxraVrQ-u1hRMVAzlPWv69LGqVplvuF-4z7lPacB6wGanE8-XQ7gham2n8615RG3afveLe-x_ETYL2fpp4fYUVAHtMcQ3?key=rlf7PWiT5fE8oCFeuqwVsRoJ) |
| :----------------------------------------------------------: |
|                    **Example of a tree**                     |

The vertices of a tree are frequently referred to as nodes and vertex and node terminology can be used interchangeably.

The **root** node of a tree is a singular node to which all other nodes in the tree are connected. In the example above, the root of the tree is node $B$.

A **branch** is an edge connection in a tree. In the example above, there are many branches joining nodes in the tree, but some examples of branches are the edges $(B,E)$, $(B,X)$, $(X,M)$, and $(Y,S)$.

A tree is naturally directed originating from the root.  In the edge convention syntax $(\overrightarrow{v_1,v_2})$ for directed graphs, direction is implied by the ordering of the vertices in the pair, so for the edge $(B,E)$, the edge originates at the first vertex specified, $B$, and terminates at the second node specified, $E$, therefore, the edge is directed from $B$ to $E$.

The direction of edges is also implied by the hierarchical vertical ordering of the tree.  Since edges are directed from the root down the tree, given the edge $(\overrightarrow{v_1,v_2})$, vertex $v_1$ is higher in the tree (closer to the root) and vertex $v_2$ is lower (further from the root) in the tree. Therefore the edge is directed from $v_1$ to $v_2$. 

A tree is technically a tree of trees. In other words, each node is the root of a subtree containing the nodes that are connected to and lie below that node. In the above example, $D$ is the root of a subtree containing nodes $D$, $R$, and $T$. This should suggest that many algorithms that operate on trees can be decomposed into self-similar subproblems and recursive algorithms are especially useful in trees.

A tree node is either an inner node or an outer node. An **inner node** is connected to at least one node further down the tree and may also be called a **branch node**. In the above example, nodes $B$, $X$, $M$, and $Y$ are inner nodes.  An **outer node** is not connected to any nodes further down the tree and is also called a **leaf node** or **terminal node**. In the above example, $R$, $C$, and $A$ are outer nodes.

If there is a directed path from node $n_1$ to node $n_2$, *i.e.* $n_1$ is closer to the root and $n_2$ exists within the subtree where $n_1$ is the root, then $n_1$ is an **ancestor** of $n_2$ and $n_2$ is a **descendant** of $n_1$, and two nodes are said to have a **parent-child relationship** if they are neighbors. In other words, $X$ is the parent node of $D$ and the child node of $B$.  We might also say $D$ is the **grandchild** of $B$ and $B$ is the **grandparent** of $D$.

| ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcrhXtvY2Zv9Xma3wOxHrG_6D8OMNyHNo23WCVKS8CoYBtbgkmNctfmDJ7quRuNQl2Mh0oNfffJI5QzVb1-Wc0o-yy4pKuc7uAxxSNJoLswuQzJenrXtn1M9ZX4iGUIbM_ppDlk?key=rlf7PWiT5fE8oCFeuqwVsRoJ) |
| ------------------------------------------------------------ |
| $X$ is the parent of $D$ because $D$ is both adjacent to $X$ and descends from $X$.   $X$ is also the child of $B$ because $X$ is both adjacent to $B$ and descends from $B$.  $D$ is the grandchild of $B$ because $D$ is the child of $X$ and $X$ is the child of $B$. Conversely, we can say $B$ is the grandparent of $D$ because $B$ is the parent of $X$ and $X$ is the parent of $D$. |

### Metrics

The **degree of a node** is the number of outgoing branches that originate from this node; therefore, an inner node has a degree greater than zero and an outer node has a degree of zero. The **degree of a tree** is the maximum degree of any node in the tree. In the above example, the degree of the tree is 2 because the maximum outgoing degree of any of the nodes in the tree is 2.

As defined for graphs, the **distance** between node $n_1$ and node $n_1$ is the number of edges between the two nodes in the path connecting the two nodes.  Because trees are acyclic by definition, all trees have only one connection between two nodes, so it is only possible for there to be one path between two nodes.  All tree nodes are connected to its root, so It is always possible to reach any node in the tree from the root.

The **depth of a node** or **level of a node** is the distance of a node from the root in terms of the number of edges between the root and that node. The root is the root and there are no edges between the root and itself, so the distance between the root and itself is 0 meaning that the root is at depth/level 0.  Any node that is a child of the root is at depth 1 or level 1, any node that is the grandchild of the root is at depth 2, and so forth.  The **depth of the tree** or **height of the tree** is the distance of the furthest leaf from the root and represents the longest path from the root to any leaf in the tree.

## Binary Tree and Binary Search Tree

A tree with degree of 2 is called a **binary tree**. A binary tree that contains inner nodes with only a degree of 2, *i.e.* it has no inner nodes with a degree of 1, is a **full binary tree**. If all outer nodes in a full tree only exist at the full depth of the tree, it is a **complete binary tree**.

| ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfjM-AatsxtuY4h90K_U4QaEzPSNmGW3KOUwCP_qGIlopBNc9cUnGySv0PZPddbkAExnMOneNnZxYDRduQMYxERrn8h6oXbBBU_bu8cc1RZkvUgsntxM4a0W88IXi-vMV7IOnEXZg?key=rlf7PWiT5fE8oCFeuqwVsRoJ) | ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXf4OaCx_ypK14TzabVLVwWxm9aNnDHRsU062mAZ7McyPW2ecre-qNXOdnMshhKGqbeQOogatuUcjon0M8bAfnZzqZAin1Sg4j0XOLqOCJV5tLUv3sI55tdCt38d_c6Zo5L89AOTSg?key=rlf7PWiT5fE8oCFeuqwVsRoJ) |
| :----------------------------------------------------------: | :----------------------------------------------------------: |
|                     **Full binary tree**                     |                   **Complete binary tree**                   |

A complete binary tree is a tree of **minimum height**, and with balancing, a full binary tree approaches its minimum height.  In a binary tree with minimum height, the longest path from root to any leaf is no longer than $\log_{2}n$. 

An **ordered** binary tree is structured in such a way that search in the tree results in a binary search.  If a binary tree is ordered and of minimum height, we call it a **Binary Search Tree (BST)**.  Note that not all ordered binary trees are binary search trees because a BST must also have minimum height.  Both the full binary tree and complete binary tree examples above are **unordered** so binary search cannot be performed on them and therefore they are not BST’s. A binary search tree has the property that in any subtree given the value of its root then all nodes in each subtree with values less than that subtree’s root value lie to the left of the root, otherwise, the value must lie to the right of the root node. However, there is no single ordering for a BST and there are many potential orderings for the same data.  Both of the following trees are ordered binary trees of minimal height, so both are BST’s. The left example 1 is full while the right example 2 is not full. 

| ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcN_Q_Qn-m73dCcTSNsz8olBNvPLdNvW8RN40c6gHCOlsJ6iNr6Ymrc9VknYomelT5OpmH6lCLQVgiHpO6-VEeB7sGh-8Gg6HBzqieYX33YTpHmXcOtNoXE4RiB1ts-COjyArsG?key=rlf7PWiT5fE8oCFeuqwVsRoJ) | ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXeM9KvSWXedbx6K0UqcjJYKFKrKfRtaRy6tt7Ek6xpdaZb6DSOz7sCgRmIfKYhGuox03U5ZeEkFWguTcFcUvfdqLuxpEGiR5653ydfqfyzlBpNbJkluSWMcpxrTbsk5-VCxCW0jbg?key=rlf7PWiT5fE8oCFeuqwVsRoJ) |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| **Ordered binary tree example 1**                            | **Ordered binary tree example 2**                            |

### Search Analysis

There is a close relationship between binary search in an ordered array and search in an ordered binary tree; however, there are sufficient differences that the efficiency analysis for each structure is unique.  The most important distinction is that binary search in an ordered array always results in the search of a binary tree of minimum height (we leave it to the reader to examine this further) and the search efficiency follows from this fact.  However, the efficiency of search in an ordered binary tree is subject to whether or not the tree's height is minimized which represents a significant variable in efficiency analysis and key factor in tree implementation.

For the sake of analysis, assume a complete, ordered tree meaning that the tree is of minimum height and search us guaranteed to follow a single path.  Our worst case analysis therefore seeks to quantify the length of the longest path from root to leaf in a complete, ordered tree.  In other words, what is the relationship between the length of the longest path and the number of elements in the complete, ordered binary tree.

For each level, $\ell$, of the complete binary tree, the number of elements in a given level, $n_{\ell}$ , is equal to the base 2 exponential of the level where the first level containing the root node is level 0.  In other words, the relationship between the level and the number of elements in a level for a complete binary tree is:
$$
n_{\ell} = 2^{\ell}
$$
This formula makes sense because the first level, $\ell=0$, contains only the root making $n_{0} = 2^{0} = 1$, the second level, $\ell=1$, contains the two children of the root in a complete binary tree making $n_{1} = 2^{1} = 2$, and each subsequent level doubles the number of elements from the previous level.

The depth of the tree, $d$, is equal to the maximum level and the total number of elements in the tree would therefore be the sum of the elements in all levels up to the depth of the tree:
$$
n = n_{0} + n_{1} + \cdots + n_{d}
$$
Therefore the total number elements in the complete binary tree is the summation:
$$
n=\sum_{\ell=0}^{d}2^{\ell}
$$
This summation establishes that for a complete tree of depth $d = 0$, the total number of elements in the tree is:
$$
n = n_{0} = 2^{0} = 1
$$
And for a complete tree of depth $d = 1$, the total number of elements in the tree is:
$$
n = n_{0} + n_{1} = 2^{0} + 2^{1} = 1 + 2 = 3
$$
And for a complete tree of depth $d = 2$, the total number of elements in the tree is:
$$
n = n_{0} + n_{1} + n_{2} = 2^{0} + 2^{1} + 2^{2} = 1 + 2 + 4 = 7
$$
Consider the relationship of the above summation and examples with the number of elements in the next level added beyond the current depth of a complete tree, *i.e.* $n_{d+1}$.  When a new level is introduced, the total number of elements in the next level is equal to:
$$
n_{d+1} = 2^{d+1}
$$
But what is the relationship between the number of elements in the new level with all the existing elements in the tree?  From above:
$$
n_{0} + n_{1} + n_{2} = 7
$$
and
$$
n_{2+1} = 2^{2+1} = 8
$$
therefore
$$
n_{0} + n_{1} + n_{2} = n_{2+1} - 1
$$
or expressed in terms of the total number of elements in the tree $n$:
$$
n= n_{d+1} - 1
$$
While this text only proves this relationship for a narrow specific example, it holds for all levels in a complete binary tree.  For example, $n_{0} = 1 = n_{0+1}-1 = 2-1$ and $n_{0} + n_{1} = 1+2 = n_{1+1}-1 = 4-1$.  We leave it to you to refer to the proof for the sum of a geometric series for a full proof on this relationship.

The above means that the relationship between the number of nodes $n$ in a complete binary tree and the depth $d$ is:
$$
n = 2^{d+1} - 1
$$
This formula is the answer to our question about the relationship between the longest path and the number elements; however, it does not answer the question about what is the length of the longest path directly.  To determine the length of the longest path, we need to determine what the depth $d$ would be for a complete binary tree in terms of the number of elements in the tree $n$, so we should probably rearrange the equation first:
$$
2^{d+1}+1 = n
$$
Since we are performing Big O analysis, we are estimating and can make some slight simplifications to reduce complexity in the equation:
$$
2^{d} \approx n
$$
We can then apply the logarithm to both sides to isolate and express in terms of $d$:
$$
\log_{2}(2^{d}) \approx \log_{2}n
$$
Which reduces to:
$$
d \approx \log_{2}n
$$
In other words, in a complete binary tree, no node is more than $\log_{2}n$ edges from the root where $n$ is the number of elements in the tree.  This means that to search an ordered, complete binary tree, *i.e.* a complete BST, it takes no more than $\log_{2}n$ comparisons to determine whether or not the element in question exists in the complete BST and search in a complete BST is therefore $O(\log_{2}n)$. 

| ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcp2Bz8lOXTlMicf797BVm_61kWzZpQdlGiF9joFsAXzAnMqgAuf7jBXCDOnVHPfmnmSHGKY-FxboPsDSuLvt6GWAfyjvFnerzBuNZA-9M-AsX_Wbo8ECA82apP3D-plt5BOaEBBg?key=rlf7PWiT5fE8oCFeuqwVsRoJ) |
| ------------------------------------------------------------ |
| For a complete binary tree, the total number of elements $n$ is related to the depth $d$ by $n=2^{d+1}-1$, the base 2 exponential, or alternatively via by $\log{2}n \approx d$, the base 2 logarithm. This means that the distance of the furthest leaf from the root is $log_{2}n$, and the longest path from the root to any node is no more than the depth of the tree, $\log{2}n$, as long as the tree is a complete binary tree. |

In a complete tree, the relationship between the number of elements and the longest path is $\log_{2}n$. Because of the ordering of a BST, a node can only exist on a single path through the tree as dictated by ordering relative to subtree root nodes.  This means that there is one and only one search path within a given tree for a specific element, and if that element is not in that path, then the element must not exist within the tree.  Therefore, we only need to perform a number of comparisons equal to the length of that path to determine if an element is not in the tree and the length of that path determines the efficiency of the search operation.  In other words, if the tree is of minimum height, then the longest path is of length $\log_{2}n$ which defines the number of comparisons necessary in a worst case search and therefore the worst-case time complexity for search within a complete BST is $O(\log_{2}n)$. This efficiency of search holds because the height of a complete binary tree is minimized by definition, but how does this change for binary search trees in general?

Whether or not a binary search tree performs search with logarithmic time complexity will depend on whether the binary search tree is **balanced**, which is a property specific to algorithms designed to maintain a binary search tree with minimal height. 

| <img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXdBvDjz7oumYkX7w82iw_0-HKUqUZuknssdrhQ7xs6E-hNuRzVNXl6H6CmVyqXpMTk1uz7EuHLewbmcWW30_DLOtj5Mzg4Mb8m2NNXrCmrY5t_1vdtdeC1tnH7JcYLkgiI_7FRi_A?key=rlf7PWiT5fE8oCFeuqwVsRoJ" alt="img" style="zoom: 50%;" /> |
| :----------------------------------------------------------: |
|                    **An unbalanced tree**                    |

An **unbalanced** tree is generally measured by the height difference between all left and right subtrees for every node in the tree.  Note that this is a recursive definition.  If this difference between heights in all left and right subtrees is greater than 1 then the tree is unbalanced and needs **rebalancing**.

| ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXc5O5vBOPRj2pF2eGntXJiTu_IO3FQa1VSxuBNJY4P_ziBoqzb_zkGECAHYAz00KHHky5_-l3EOVURVjdRS9raFi5KPGFVczFJ5dNcGMwynEFBxqp4FUM2KzHhcisoyvKE2qsjm?key=rlf7PWiT5fE8oCFeuqwVsRoJ) | ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdmKc8rbRqHbDLqr6hdrUdiuXTZO1zBOdnKlO-0anvWqzQfbRCMJa3NsI7Ulg9b88O6r2LARtfXYzF8fQdGd4tRiZV6D_py0dRqeHBXOmVS8DfcLudA5Q2uswQbBM9UmpVv8RBNgA?key=rlf7PWiT5fE8oCFeuqwVsRoJ) |
| ------------------------------------------------------------ | ------------------------------------------------------------ |

| The left and right subtrees of $E$ have a height difference of 1 so the subtree defined by $E$ as the root is considered balanced |
| ------------------------------------------------------------ |



| ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXebsOdwPpMOQAQaSBEVagoIHAzMJ6DtTCSZhl3ZaBIcAybeDibMH1l3It2A-JlWSZbHtoSP-Ffv-ywmJL-C7xYyrI_cDUZouv7HdF8nU9_K29LV7lyw72pS3ScGce77q9sPJqTX-w?key=rlf7PWiT5fE8oCFeuqwVsRoJ) | ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXek7Nk3kgi00lIlqhXRpZEMTSRqxEERupktftNcf0Jrrqne6UqOsl7dTq1ObaMvL3vnZQIQUYYoOt8HGiHfHMpKGHusSY0cAT3j_gDV4pR_YClFX2pTljm_H-d0hiNh0DAE-06d?key=rlf7PWiT5fE8oCFeuqwVsRoJ) |
| ------------------------------------------------------------ | ------------------------------------------------------------ |

| The left and right subtrees of $B$ have a height difference greater than 1 so the subtree defined by $B$ as the root is considered unbalanced |
| ------------------------------------------------------------ |

In binary search on an array, the tree that is generated is always ordered (assuming the data is ordered), always has minimum height, and is always balanced, so binary search in an array is always logarithmic time complexity.  However, there is no such guarantee that all trees have minimum height unless they are full. 

Balance is not a passive property as balance must be regularly maintained, potentially with each insertion into or deletion from a tree, so a key feature of all binary search tree algorithms is to **rebalance** (to rearrange the tree with time complexity less than or equal to the efficiency of search) a tree when necessary, to both maintain its order and minimize its height.  If a tree is balanced efficiently, the worst-case search efficiency consistently remains $O(\log_{2}n)$ for insert and search in a balanced binary search tree where $n$ is the number of nodes in the tree.

Let $x$ be the time complexity of rebalance.  If the time complexity to rebalance is less than the time complexity of search, $O(\log_{2}n)$, in the binary search tree then:

​	$O(\log_{2}n) + x = O(\log_{2}n)$ where $x \leq O(\log_{2}n)$,

And the overall efficiency of insert or search based operations is no more than $O(\log_2{n})$.  

If a binary search tree is not properly balanced, the efficiency of search can degenerate beyond the expected worst-case efficiency.  The unbalanced tree degenerates towards becoming a linked-list rather than remaining a binary tree, so the efficiency of search in a *degenerate BST* tends towards $O(n)$ in the worst case; however, a degenerate BST is only possible if rebalancing is not properly or regularly performed.  

The balanced property and the balancing algorithm are therefore key in maintaining optimal search efficiency in a binary search tree and the efficiency of the rebalancing algorithm will dominate the efficiency of any insertion operation in the tree.

| <img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXcyqP5t6x0QtxKCU-yzdSt30ak6sX3bv391nJzXOP6jw5FiiE3-fO3Knpf7B9GXLPhGGOQt0lYzeJSnvZI_l5sw-fhdre9D89Pr3dWLLtu5CD3fl0fngl9GQYpu3qbQfiZozul3pw?key=rlf7PWiT5fE8oCFeuqwVsRoJ" alt="img" style="zoom: 50%;" /> |
| :----------------------------------------------------------: |
|                    **A degenerate tree**                     |

## Binary Tree Implementation

Binary trees share structural elements with a linked list.  Both the linked list and the tree require an anchor, *i.e.* head versus root, to maintain access to the data structure in memory, use references to link together elements within each data structure, and use similar node data structures to maintain data and relationships in the data structure.

### Binary Tree Node

The binary tree node has the same structural elements as a doubly linked-list node, *i.e.* a data element and two pointers to nodes of the same class, but the concept of the structure is slightly different as signified by the unique labels used for the binary tree node.

| <img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXeLk5_2EP02v-APNqqyXmZrGYq_u4ioRiwwavLSNQYqcwjB2xTEiC0VZ_qUDFc0nXjJJSbhitcJKCSqu2hJgKif1-znk7N_tWWfrjHa5iWMxFNch_ZEeRem4RUX4yGTHIdLwqcUjg?key=rlf7PWiT5fE8oCFeuqwVsRoJ" alt="img" style="zoom: 150%;" /> |
| :----------------------------------------------------------: |
|                **Binary tree node structure**                |

```java
class BinaryTreeNode {  
    Object data;            // the data in this node  
    BinaryTreeNode left;    // node to left if it exists  
    BinaryTreeNode right;   // node to right if it exists
}
```

In a tree class we need minimally to track the root node and provide internal operations to maintain the integrity of the tree itself such as a balancing operation. For more sophisticated trees, more methods and more sophisticated node properties may be needed.

```java
class BinaryTree {  
    BinaryTreeNode root;                    // root of the tree
    
    void balance( BinaryTreeNode lroot );   // balance algorithm
    ...
}
```

### Traversal

When dealing with a linked list, we needed a methodology to traverse the list; however, for a linked-list, any traversal methodology is very straightforward and simply requires an iterative approach. For a tree, such an approach is not possible because for each node there are multiple paths that can be traversed and as a result we need to be considerate of the varied (breadth-first, depth-first, boundary, and diagonal) general traversal strategies that may be used to traverse a binary tree and each may be further structured by a specific order.

It is important to consider that **inspecting** a node is a separate operation from visiting node. We can visit a node and then visit one or more of its children before actually making any comparison of a value stored in the node itself. Given this consideration, the order we visit nodes and the point at which in the visiting process we inspect a node becomes very important. 

#### Depth-First Search (DFS)

A depth-first approach emphasizes descending the tree first before branching out and examining alternatives. However, this comes at the cost of potentially exploring an extremely deep tree before considering a more desirable decision adjacent to any initial choice. 

These depth-first traversals are known as **pre-order** **traversal**, **in-order traversal**, and **post-order traversal**. The prefix in these conventions describes when the local root is inspected with respect to the children, so pre-order means the root is inspected before its child nodes are inspected, in-order means the root is inspected between inspection of the two children, and post-order means the root is inspected after both children are inspected.

| ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdYh6p4kCV5i9fk8H7fAqXJNttf6deM8enE486mVJNNx3f1g71rTLFSlKjzj3v7bMfVqyDcZ-90ueuZldFhWuige2E_JgT3T96qfmBoptnaT8VbmzB0lP1TADkGIDCZpnITHHKSaA?key=rlf7PWiT5fE8oCFeuqwVsRoJ) | ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXeCCM6XYsHfXVl-2HVow2Q4_Nrd0VCJphz6ar7KG1nJDiEFmZkrLfXpb8TRM065dq8SP91PQ-ycA1-PlNUKe3SXfBDjAR3lLp2QV8UphKvQQUhB_AXOyqmEe06rD-EqMMf4cKZfow?key=rlf7PWiT5fE8oCFeuqwVsRoJ) | ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXd1P-96Vhijl4loVbCQwO1_eM8X7r8gbhGkoyXpA8QgN24fBXIIOYKShMBuqjY5JvUP-WoJ7F168OvERKlFx4uUFbVMfJdZ-8qhxirJiRAUP-61RccOtxi7yTaSK-sL5NUkARsnVA?key=rlf7PWiT5fE8oCFeuqwVsRoJ) |
| :----------------------------------------------------------: | :----------------------------------------------------------: | :----------------------------------------------------------: |
|                   **Pre-order traversal**                    |                    **In-order traversal**                    |                   **Post-order traversal**                   |

In the traversal diagrams above, the node labeled 1 is visited first, the node visited 2 is visited second, and the node labeled 3 is visited third; and this process is performed recursively for each node. By default, these traversals follow a left-to-right convention but a “reverse” convention of right-to-left, *i.e.* reverse pre-order, reverse in-order, and reverse post-order, can be specified and implemented. These multiple traversal approaches reflect the increased complexity of a tree over a linked-list; however, it leaves us to consider whether this complexity is a benefit or a burden. 

> **Inspection**
>
> In the following traversal discussion, we will use the term “inspect” or “inspection” to indicate when an action is performed on the local root. If we were reading data from the root or deleting the root, these actions would be performed at the time of inspection. We make this distinction because the action must be performed at a specific phase during the traversal if the order is to be preserved.

##### Pre-Order

Pre-order traversal means that the local root is inspected before any of its children are visited.

If we transcribe tree nodes into an array using pre-order traversal, the order of nodes in the array will reflect the construction order of the tree. In other words, we can flatten a tree into an array and then reconstruct the tree from the flattened array. This is useful because we often need to serialize, *i.e.* convert data into a sequence of symbols, for transmission, and by using pre-order traversal, we could serialize a tree, broadcast the tree as an array to another system, and reconstruct the tree on the other end of transimission.

The recursive pre-order traversal algorithm is as follows:

```pseudocode
Preorder(root) :  root -> left -> right  
	Inspect(root)  
	Preorder(root.left)  
	Preorder(root.right)
```

The following example illustrates pre-order traversal over the entire tree:

<img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXdWbeFmUTjgtbJZ3IZ1AIFfg6-5BczeFVnpfeSRqDCNBa2cjBDOxbhK_aQHlZg7uGuKfzPojeBL2E8dmixu76fCE9ol6Z7o7YJoAafUegYwcMl8THsurnqt3emLEh3hxCFjaWy22A?key=rlf7PWiT5fE8oCFeuqwVsRoJ" alt="img" style="zoom: 50%;" />

|      | **Step**  | **Actions**                      |
| ---- | --------- | -------------------------------- |
| 1    | Inspect B | Descend left to X                |
| 2    | Inspect X | Descend left to D                |
| 3    | Inspect D | Ascend to X. Descend right to M. |
| 4    | Inspect M | Ascend to B. Descend right to E. |
| 5    | Inspect E | Descend left to Y                |
| 6    | Inspect Y | Ascend to E. Descend right to A. |
| 7    | Inspect A |                                  |

##### In-Order

In-order traversal means that the local root is inspected in between visiting its children.

If we transcribe an ordered tree’s nodes into an array using in-order traversal, the array itself will be in order.  In other words, in-order traversal is capable of flattening an ordered tree into an ordered array.

The recursive in-order traversal algorithm is as follows:

```pseudocode
Inorder(root) :  left -> root -> right  
	Inorder(root.left)  
	Inspect(root)  
	Inorder(root.right)
```

The following example illustrates in-order traversal over the entire tree:

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdWbeFmUTjgtbJZ3IZ1AIFfg6-5BczeFVnpfeSRqDCNBa2cjBDOxbhK_aQHlZg7uGuKfzPojeBL2E8dmixu76fCE9ol6Z7o7YJoAafUegYwcMl8THsurnqt3emLEh3hxCFjaWy22A?key=rlf7PWiT5fE8oCFeuqwVsRoJ)

|      | **Step**  | **Actions**                            |
| ---- | --------- | -------------------------------------- |
|      |           | Descend left to X. Descend left to D.  |
| 1    | Inspect D | Ascend to X.                           |
| 2    | Inspect X | Descend to M.                          |
| 3    | Inspect M | Ascend to B.                           |
| 4    | Inspect B | Descend right to E. Descend left to Y. |
| 5    | Inspect Y | Ascend to E                            |
| 6    | Inspect E | Descend right to A.                    |
| 7    | Inspect A |                                        |

##### Post-Order

Post-order traversal means that the local root is inspected after all of its children are visited.

When we need to delete the contents of the tree, we need to start **pruning** at the leaves and work back up to the root of the tree in order to ensure full deletion of the tree. We also may use the same approach for pruning specific branches of the tree. To support this, we would need to inspect the children before inspecting their local root, and this is exactly what post-order traversal guarantees.

The recursive post-order traversal algorithm is as follows:

```pseudocode
Postorder(root) :  left -> right -> root  
	Postorder(root.left)  
	Postorder(root.right)  
	Inspect(root)
```

The following example illustrates post-order traversal over the entire tree:

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdWbeFmUTjgtbJZ3IZ1AIFfg6-5BczeFVnpfeSRqDCNBa2cjBDOxbhK_aQHlZg7uGuKfzPojeBL2E8dmixu76fCE9ol6Z7o7YJoAafUegYwcMl8THsurnqt3emLEh3hxCFjaWy22A?key=rlf7PWiT5fE8oCFeuqwVsRoJ)

|      | **Step**  | **Actions**                                        |
| ---- | --------- | -------------------------------------------------- |
|      |           | Descend left to X and D                            |
| 1    | Inspect D | Ascend to X. Descend right to M                    |
| 2    | Inspect M | Ascend to X                                        |
| 3    | Inspect X | Ascend to B. Descend right to E. Descend left to Y |
| 4    | Inspect Y | Ascend to E. Descend to right A                    |
| 5    | Inspect A | Ascend to E.                                       |
| 6    | Inspect E | Ascend to B.                                       |
| 7    | Inspect B |                                                    |

#### Breadth-First Search (BFS)

Rather than prioritizing iteration down the tree, **breadth-first search (BFS)** traversal prioritizes traversal at the current level, known also as **level-order traversal**, and it ensures that all elements at the current level are inspected before any descent down the tree is made. There are no direct relationships among elements at the same level which requires some other data structure to support BFS traversal. In general, a queue can aid in BFS where when a node is inspected, its children are enqueued for future inspection and inspection occurs based on the queueing order.

There is no simple recursive algorithm for level-order traversal as there are no links between elements in the same level; however, the algorithm is still quite simple.

```pseudocode
Levelorder(root) :    
	queue ← queue.empty()
	queue.enqueue(root)
	while not queue.isEmpty()
		node ← queue.dequeue()
		Inspect(node)
		if node.left ≠ null
			queue.enqueue(node.left)
        if node.right ≠ null
        	queue.enqueue(node.right)
```

Adapted from https://en.wikipedia.org/w/index.php?title=Tree_traversal#Breadth-first_search_2

The following example illustrates level-order traversal over the entire tree:

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdWbeFmUTjgtbJZ3IZ1AIFfg6-5BczeFVnpfeSRqDCNBa2cjBDOxbhK_aQHlZg7uGuKfzPojeBL2E8dmixu76fCE9ol6Z7o7YJoAafUegYwcMl8THsurnqt3emLEh3hxCFjaWy22A?key=rlf7PWiT5fE8oCFeuqwVsRoJ)

|      | **Step**             | **Actions**          |
| ---- | -------------------- | -------------------- |
| 1    | Inspect B            | Enqueue X, Enqueue E |
| 2    | Dequeue X, Inspect X | Enqueue D, Enqueue M |
| 3    | Dequeue E, Inspect E | Enqueue Y, Enqueue A |
| 4    | Dequeue D, Inspect D |                      |
| 5    | Dequeue M, Inspect M |                      |
| 6    | Dequeue Y, Inspect Y |                      |
| 7    | Dequeue A, Inspect A |                      |

BFS is used to traverse decision trees used in very simple heuristic based AIs.  

For example, a chess engine would not use a DFS approach because trees do not model cycles, so there are an infinite number of board positions.  As as result, DFS might be slow and would requires that we explore the entire tree for the “best” decision.  However. some decision trees are infinitely deep, *e.g.* Chess and Go, so DFS will never stop.

If planning time is bounded, often BFS will give a better outcome than DFS because it can sample a more varied number of distinct choices, and if a scoring metric is available, it can choose the highest scoring option.  BFS can look several layers deep in a relatively short time to find the best choice among available choices rather than exploring one option to its conclusion.  For really deep decision trees, a level order traversal will better support decision making over DFS.

### Binary Search Tree Implementations

There are multiple approaches to maintaining a balanced BST, but two established approaches are AVL and Red-Black Trees.

#### Adelson-Velsky and Landis (AVL) Tree (1962)

The Adelson-Velsky and Landis (AVL) approach defines a **balance factor**, *i.e* a binary tree is balanced if the absolute difference of heights of left and right subtrees at any node is no greater than 1. In other words, using a recursive descent through the tree, each and every left and right subtree must remain balanced for every subroot in the tree and this is measured by taking the difference between the heights of the left and right subtrees. 

Where $n$ as the number of nodes in the tree, recomputing the balance factor would be a relatively expensive $O(n)$ operation if it is necessary to recompute the balance factor for every node in the tree. However, it is not necessary to recompute the balance factor for every node if two observations are made.  First, the balance factor can be maintained as a property of each node and so we have access to the previously computed balance factor whenever we need to rebalance.  Second, the balance factor only needs to be recomputed in the subtrees along the path from root to the newly added (or removed) node as all other paths through the tree remain unchanged and will have the same balance factor as what is stored in their nodes.

The key observation to make rebalancing efficient for the AVL tree is that we do not need to rebalance the entire tree and instead, in the worst case, can rebalance along a single path through the tree to produce a new tree of minimum height. If we only have to rebalance along a single path and the original tree was of minimum height, then the efficiency of rebalance can be as fast as $O(\log_{2}n)$ where $n$ is the number of nodes in the tree because the height of the new binary tree is no greater than $\log_{2}n + 1$.  So how can we optimally rebalance local subtrees at $O(\log_{2}n)$ without rebalancing the entire tree at $O(n)$ and the answer is to use rotations.

##### Rotations

A rotation is like grabbing a node adjacent to the subtree’s root, promoting that adjacent node to be the new subtree’s root, and then rehanging the entire subtree from that node. Since we are working with references, we can simply reassign left and right elements of a node in constant time, so if we avoid traversing nodes and only need to perform a rotation to rebalance, then rebalancing a specific subtree can be carried out in constant time and if we reached the worst case of needing to rebalance the entire tree, we would need only to rotate at most $\log_{2}n$ subtrees.

The following discussion is a summarization of [Decker 1989]

There are two cases where rotations are necessary and each has two flavors; each is a mirror image of the other. 

We will assume that the imbalance was caused by the right subtree of a node $x$ being too high, either by an insertion to the right of $x$ or a deletion to the left of $x$. We denote the root of the right subtree of $x$ by $y$. The other case, where the imbalance was caused by the left subtree of node $x$ being too high, is dealt with by interchanging left and right in the subsequent discussion.

Case 1 : Suppose the right subtree of $y$ has height larger than that of the left subtree of $y$ caused by the deletion of a node from subtree $A$ or insertion into subtree $C$. A left rotation preserves the left-right order $A$, $x$, $B$, $y$, $C$ so the BST is preserved by left rotations, and the left rotation in this case restores the balance at node $x$. Restoring the balance at $x$ may change the height of the subtree rooted at $x$, so we may have to continue the balancing process at the parent of $x$, and so on up to the root of the AVL tree.

| ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdH-cD7NKry__jb22HgevETGXq7eS8CFgSHEpzL3lsJpQpRE-zmtwTtYNrIrVsjqaWDHe-OcK9mutlaPUJ1aMDamKoHVkflU5_R-vKwH-dK0eLDcBh6A5woX8yJ__tsVuXleiOquQ?key=rlf7PWiT5fE8oCFeuqwVsRoJ) | ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcu9-qxeRrXtZ3M3coXbCzCIClAWtSWA6ckl9oCAK4SuyNk9JK2kt6ujyt9Qv0_LAZUrHRlqrYthMBUJaUPWvxX1D2mylAFnQgZ7OgnRPFTQc97Sbemc2sslLq4BtHADpv1-PsC?key=rlf7PWiT5fE8oCFeuqwVsRoJ) | ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdw89dvlMb-8o3ajiN3DfdNZxLswNPaE74KUlYFsN2frnBtV2Pna_oI2DL1vbPsfPid0FSDORQnNEDdPjukynb2NJwJCiFdebizTdbB9HoulLI9_WVWpNr6OqHGM8P6UeETBkjJ5Q?key=rlf7PWiT5fE8oCFeuqwVsRoJ) |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| Rotating left by promoting y to be the root of the subtree originally defined by $x$ as the root. All elements of $B$ are greater than or equal to $x$ and less than $y$ | To rotate, we can reassign the references associated with the right child of $x$ and the left child of $y$. Since $y$ must be greater than or equal to $x$, $x$ also qualifies to be the left child of $y$ | By reassigning the left child of $y$ to be $x$ and simultaneously reassigning the right child of $x$ to be $B$ (formerly the left child of $y$), the subtree is rebalanced now with $y$ as the root of the subtree. |

Case 2 : Suppose that the imbalance at $x$ is caused by the left subtree of $y$ being too high. A simple rotation in this case is not sufficient to restore balance at $x$. Instead, we need to perform two rotations, beginning further down the tree. We expand subtree $B$ into its root and subtrees $B'$ and $B''$ to illustrate the first rotation on the right child of $x$ where the expanded subtree with root $z$ is rotated with its parent $y$. A second rotation is then performed at $z$ such that $x$ and the left child of $z$ are now balanced to the left of $z$, $y$ and the right child of $y$ are now balanced to the right of $z$, and $z$ is now the root of the overall subtree.

| ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfW6Gcidtc0C9qPp1Wt0xphkDzIKzsgukv57Jia8CEzxiR9mv9bVrToIb0z0Z-5sSyd-93bV9n85oreT3AfKg5jn4g3EzZC5YDCNs0t_2Tgb1fcTMd4OxSdIV1dosjTJLODp8b8rQ?key=rlf7PWiT5fE8oCFeuqwVsRoJ) | ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdHaljtf3PMpi1LNzb1WNMFiaCO8iUCgVEVDG_jjOEUwyaKT_LQzxNXLEQlNs80aBtlmBqqyrlyyhV8BITfNeuaQ8D0SHEV4IA7iRzdjL0OkNZwFnpyplkvvoTS0tyYba3tUnTG?key=rlf7PWiT5fE8oCFeuqwVsRoJ) | ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXeZ258RAO6ezgnfiGmUiytMYps4iagldUTWq12dRHIM5ERIRAviUFq6m9aIJGVYtTP1RlGf1gzuKJistQQLe_YdwJvwXuIPs-52My6JutM6hxks6nx9dLbfXR8vraSPsVdKwYIvBw?key=rlf7PWiT5fE8oCFeuqwVsRoJ) |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| Suppose the left subtree of $y$, $B$, is too high            | We expand subtree $B$ into its root $z$ and subtrees $B'$ and $B''$ | We break the edge $(y,z)$ and the edge $(z,B'')$             |

| ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXf3wNUTUZFAUxgPg0pQDzTnXJVMkEkwA5kSnYNo0O8gDT7X_pR5sNxhz1rWn4Tr4yX2jPHzf2rg4FiQPWLr04oNtGigD1FpiXLkqF943whw3QOmKvwzu_Rri_EfIAuMRh4AaEUD8A?key=rlf7PWiT5fE8oCFeuqwVsRoJ) | ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcKMtzLz3zB7hQ9naojCU0OEMZdsSudJK5kEiF3rq9nJS-eW9r_2pd4Kiy7dNhtZJhN9G9Fpg9DJWyiycT6azqs2ZyrO6mBpIiUIcGFjlmbkP2aLs8NER6-kxTi2Rplb_85s8kDzA?key=rlf7PWiT5fE8oCFeuqwVsRoJ) | ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXel4RWNqtyoAUBAxPqwZSglg4lfkd0__LR3N6voMkWUf3R02OJwMHt7_K5RPpflvNXX6vuKiwFDwBnkycKzbAXTjqxaplLul8xQ7bDnsDUZvXC2ZtL0ZCAzdSm4PquliKnV1QNb?key=rlf7PWiT5fE8oCFeuqwVsRoJ) |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| We can then hang $y$ from the right of $z$ and $B''$ from the left of $y$ | We can then break the edge $(x,z)$ and the edge $(z,B')$ to perform a left rotation on $z$ | With the left rotation on $z$ the overall subtree is rebalanced with $z$ newly promoted to the root of the subtree. Recall that $z$ began as the root node of the subtree $B$. |

#### Red-Black Tree (1978)

The Red-Black Tree is an extension  of the AVL tree concept and was invented by Guibas and Sedgewick where the primary benefit of Red-Black trees is their additional complexity helps reduce the frequency of rebalancing.  The Red-Black tree uses an additional property, "color",  to determine if balancing can stop before reaching the root.   In the Red-Black tree, every node has a color and color generally alternates at each level.  Further balancing is necessary if when ascending the tree during the balancing operation, two successive nodes have the same color.

Here is a high level summary of the Red-Black tree rules:

1. Every node is either red or black (or practically either black and not black).
2. Empty leaf nodes (NIL nodes) are added whenever a new terminal node is added. All empty leaf nodes are always colored black regardless of the color of the newly added terminal node.
3. A red node can never have a red child
4. Every path from a local root to any descendant NIL node goes through the same number of black nodes.
5. If a node $N$ has exactly one child, the child must be red, because if it were black, its NIL descendants would sit at a different black depth than $N$'s NIL child, violating requirement 4.

### Search in an Unordered Tree

Even if a tree is unordered, we may still search it but with a worst case search efficiency approaching a linear approach regardless of its structure. In other words, if a tree is unordered, we have to search every node before determining that the search value does not exist in the tree and our efficiency is no better than search in an unordered array.

### Binary Search Tree Abstraction

As suggested previously, trees can be represented using reference based binary tree structure or using an array. A binary search tree must remain balanced to ensure that it maintains its worst-case search efficiency of $O(\log_{2}n)$ and there are at least three candidate implementations to ensure a binary search tree is not degenerate.

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfRkGTmB5BlYkEtOTV54aag_i8CclrDM80OG5aUj3W4BLm7Mu9I6NBvHvE7JEzGVbvs7RyS2rPN-4gJw6fNUd340JMsq2wPwzo4eLTKl80HNSyd2lTm1iA6m8Fk6uKmYsl2Gvd8dQ?key=rlf7PWiT5fE8oCFeuqwVsRoJ)

In other words, a BST can be maintained using an ordered array, an AVL tree or a red-black tree; however, users of the BST do not need to know what data structure is supporting its underlying implementation if a binary search tree abstraction is provided. A typical BST interface might have the following methods:

```pseudocode
void insert( element ) : Takes an element as input, inserts that element into the binary search tree in order, returns nothing

boolean contains( element ) : Takes an element as input, searches the binary search tree to determine whether or not the element exists in the search tree, returns true if the element is in the tree otherwise returns false.
```

While the efficiency of search in the array implementation is $O(\log_{2}n)$ where $n$ is the size of the input, the reason not to use the array becomes clear with the $O(n)$ efficiency of insert. Since the array must remain ordered in order for the array to be a BST, we have to assume that we must shift $n$ elements in the worst-case to make room for the new element to insert regardless of whether there is spare space allocated. This is why there is extensive study of reference based structures that are capable of both insert and search in $O(\log_{2}n)$ worst-case time complexity.

## Review

1. Define the following terms in terms of the morphology of a tree: Node (inner/outer, terminal/branch, parent/child), Root, Branch (edge), Leaf
2. What does it mean for two nodes to be adjacent? What does it mean for two nodes to be connected? What is a path through the tree?
3. Define distance in a tree.
4. Define height or depth of a tree. What is a level in a tree?
5. Define the term degree with respect to a node, *i.e.* define “degree of a node”. Define the term degree with respect to a tree, *i.e.* define “degree of a tree”.
6. What is the difference between an outgoing and an incoming branch? How many incoming branches do nodes in a tree have? What is the maximum number of outgoing branches for a given node in a binary tree and what is the relationship to degree? Associate these arguments with the statement, “a tree is a directed graph”.
7. What is the meaning of ancestor and descendant and parent and child in a tree in terms of levels and connectedness? What are the relationships between parent and child nodes specifically with respect to adjacency and what are the relationships between ancestor and descendant specifically with respect to paths?
8. What is the significance of an ancestor’s position in the tree with respect to the root and any descendants.
9. What can generally be said about the ancestral relationship between the root and all nodes in the tree. Justify your answer.
10. Define what it means to be balanced in terms of all the tree’s subtrees with respect to the heights of those subtrees’ left and right subtrees. What is a rotation in a binary tree balancing algorithm?
11. How many nodes *n* are in a complete binary tree with depth *d*? Justify your answer.
12. What is the mathematical relationship between and the maximum number of nodes in a level ℓ for a binary tree? What is the mathematical relationship between the length of the path from root to any leaf in a complete binary tree with depth *d*?
13. A degenerate tree is exceedingly unbalanced. Explain what data structure the degenerate tree becomes like and why. Why would a tree become a degenerate tree?
14. Justify why a balanced tree performs insert and search operations in logarithmic time complexity with a worst case analysis based on the length of a path in the tree.
15. What is the relationship between the number of nodes in a balanced tree and its depth?
16. Why do we want to ensure that a binary tree remains balanced throughout its usage?
17. Insert sample data into an ordered binary tree and show the resulting tree.
18. Show tree traversal using preorder, postorder, and inorder traversal by recording the order in which nodes are visited given the traversal strategy.
19. Show tree traversal using level order traversal by recording the order in which nodes are visited
20. Which form of search is preorder traversal: depth first (DFS) or breadth first (BFS)? Justify your answer. It is depth first because…
21. Which form of search is inorder traversal: depth first (DFS) or breadth first (BFS)? Justify your answer. It is depth first because…
22. Which form of search is postorder traversal: depth first (DFS) or breadth first (BFS)? Justify your answer. It is depth first because…
23. Which form of search is level order traversal: depth first (DFS) or breadth first (BFS)? Justify your answer. It is breadth first because…
24. What is meant by depth first search (DFS) as opposed to breadth first search (BFS)? How do these two different search strategies emerge from the choice of traversal you implement?
25. What characteristics of a binary tree are required for a binary tree to be considered a binary search tree?
26. Why can we characterize the search efficiency of a BST as the length of the longest path through the tree? Why is the search efficiency not the length of all paths through the tree?
27. Given a balanced BST, what is the length of the longest path given *n* where *n* is the number of elements in the BST. Justify your answer.
28. Why is balance critical to maintaining a BST’s search efficiency? How does whether or not a BST is balanced affect the length of the longest path through the BST?

# 11 - Maps

A map in terms of formal math is described as a "surjective onto relationship", but what does this mean practically and where have we seen maps in the real world?  In fact, we rely on maps frequently, especially in an online world, and at university, one map is critically important to student life.

| ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXc7htPNdVsWkI4SZHyogihQC5jTOXoTy10-wYftiew0Zm3IxT950uclaysb1OtmmrwIPFtAR8TstMSXVEpPxjB9rM4hfKD_7_czELYPqVymK3y8x76Sw9-xGxBH3pxSDA8oyihZ4Q?key=1klISeGJgJOidd2MWfltZX0w) |
| :----------------------------------------------------------: |
|                     **Mapping X onto Y**                     |

A mathematical function is defined as $f : X → Y$ where $X$ is the set (domain) of all input values and $Y$ is the set (co-domain) of all associated output values. This can be interpreted as, $f$ maps the values in $X$ onto the values of $Y$ and we often use the notation $f(x)$ to clearly represent that $x$ is an input and $f(x)$ is the mapping.  In other words, a mathematical function is one form of map.  What are the key characteristics of a function that define it as a map?

Recall that a simple, graphical way to determine whether or not a plot is a function is that the plot must pass the vertical line test in order to be a function. The **vertical line test** is defined as “if a vertical line can be drawn anywhere on a graph such that the vertical line intersects the plot of a function at more than one point, then the plot can not be a function”.

| ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcGvv7FqRt-J5KIZPsY46Sbg41xa0Zle2Ce4P2-7MpmHli1dhxizo1ITRcd7w8u70CJ66pVtA5NIbBJqDJac1-wxOm4D8CM4EnOGr80BYRWNLJH8J4k7yCbBq_UYy8Ao3j3eGyHcA?key=1klISeGJgJOidd2MWfltZX0w) | ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXf1MURKHgdEI-h9AGr0YTGLzbEBe5dOGAKCa0Qm0005SXLin4EK31zCmOF3l8DOdbC5SXDAZJlK5MEvXqITjHC8cl-PN2Wl7CegBKu4k_7YgrswNeiMmIxDtiQQAf0b0tlZY0G98Q?key=1klISeGJgJOidd2MWfltZX0w) |
| :----------------------------------------------------------: | :----------------------------------------------------------: |
|               **Fails the Vertical Line Test**               |              **Passes the Vertical Line Test**               |

In the above example, the left plot is not a function because it is trivial to draw a vertical line that intersects the plot in multiple locations, and the right plot is a function (at least the portion that can be seen in the graph) because no matter where we draw vertical lines, every vertical line would only intersect the plot in a single location.  The vertical line test may be an easy tool to use with a plot; however, what does the vertical line test actually test and how can we determine whether or not an arbitrary set of input and output data meets the same requirements?

The vertical line test validates that for every *unique* value of $x$ there exists an associated value of $y$.  In other words, each value in the $X$ domain maps to one and only one value in the $Y$. Note that this is a one-way relationship and does not limit values in the $Y$ domain.  Two different $x$’s can map to the same $y$ value but two $y$ values cannot map to the same $x$ value.  A function is therefore only defined by the mapping of $X$ onto $Y$ using the vertical line test and there is no corresponding horizontal line test.  In terms of relationships, we can say there is a **one-to-one relationship** between $x$’s and $y$’s, *i.e.* for each $x$ there exists one and only one associated y value, and we can say there is a **one-to-many relationship** between $y$’s and $x$’s, *i.e.* for each y there may exists may associated $x$ values.

So where do we encounter maps beyond just mathematical functions?  Believe it or not, maps run the world and you rely on them with just about every interaction on the Internet.  One form of map is the email address you used to sign up for an account, another map is the underlying IP address assigned to your device’s Internet connection, and yet another map is your GWID or Social Security Number.  In each of these cases, your information is associated with a single, unique key that serves as an identifier for you.

| key  | value      |           |        |
| ---- | ---------- | --------- | ------ |
| gwid | first_name | last_name | gwmail |

<img src="/home/jrt/gwu-new/course/cs1112/assets/map_example_data.png" style="zoom:80%;" />

In a database, the key acts as a unique identifier for a specific set of data or record and it is a necessary feature for fast lookup of records and to minimize data duplicated.

## Key-Value Pair

In programming, we express and maintain map associations by storing **key-value pair (KVP)** data

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcA0_9H3KmiFWzSTW5GiON5MkP0wz9AvdaoAsO8z2kLbGgmttHMwtcxfa_VDh7OfAwHAzG16-aCuUvL7rAyaNPDcp6Ti1yucfJGAQSZ_ulvPyNS0DOs3VDemrIgbTZKQmdqj_gV?key=1klISeGJgJOidd2MWfltZX0w)

Regardless of the specifics of a particular implementation, any map must maintain the association of key to its value and it is typically managed by a structure we call the **Key-Value Pair** or **KVP** for short.  It can be simply represented as a tuple consisting of two elements (very common in python), an array of 2 elements, or in OOP languages as an explicit class with accessors and mutators that limit the ability to change keys after the object has been initialized.

In addition to being unique, the key is generally considered **immutable** meaning that it cannot be changed once it has been created.  From a practical development standpoint, this probably means that the key is a read-only field in the KVP structure while it is allowable to both read and write to the value field, so the key should have an accessor only in the KVP class interface while the value may have both an accessor and a mutator in the KVP class interface.

Note that as suggested above in the example student data, a value can be rather complex and can be composed of a number of properties all of which are changeable.

### Map ADT Interface

There are three basic operations needed in a map all of which must test for the existence of the key in the map and their behaviors are dependent on the outcome of this test.

```pesudocode
put( key, value ) : if the key exists in the map, put updates that key with the associated value; otherwise, put inserts the key-value pair into the map

value get( key ) : if the key exists in the map, get retrieves the associated value; otherwise, get returns a signifier that the key does not exist in the map

value delete( key ) : if the key exists in the map, delete removes the key and the associated value; otherwise, delete returns a signifier that key does not exist in the map
```

It is important to note that the above public interface is built on a number of common, basic operations hidden in the implementations including search, update, and insert.  Due to the uniqueness constraint for the keys that are used by maps, `put` must always search for the key first.  It is only after the search is complete that we know whether `put` is performing an update or an insert.  If the search fails to find the key in the map, then `put` performs an insert at the node where the search ended, and if search successfully finds the key, then `put` performs an update at the node where the search ended.  Similarly, in order to `get` or `delete`, a search needs to be performed first to locate the key in the map and if the search fails then these operations must fail gracefully, that is fail in such a way that does not cause the program to halt.

To **insert** into a map is to add the KVP into the structure in a way that maintains any constraints such as order or balance that is critical to maintaining the expected search efficiency of the structure.  To **update** a map is to change the associated value to a new value for an existing, specified key without otherwise altering the data structure.

### Implementations

As with any ADT, there are a variety of ways we can implement a map as long as the map maintains uniqueness of keys, the key-value association, fulfills the Map interface, and consistently maintains its search efficiency without degenerating.



![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdCzSmbwwH-UIEDQxJWH7ngIGL6XYqhmW3lzBGtY_Ctt75nUoqk1sc9yo5TS8IlY-jG7TTzl9B2an7_tOnkCKvzXEYJGAUtnScaPxg361QBUl35cLOpRQx0zJ29LcZG7L4bXN0y?key=1klISeGJgJOidd2MWfltZX0w)



Regardless of the implementation, since the key in the key-value pair is an alias for the input set of domain $X$, **any individual key must be unique in the set of all keys**, so whenever a key-value pair is inserted into a map, the map must always enforce the uniqueness of the key and there can never be allowed a duplicate of the key in the map. Therefore it is the primary responsibility of the map implementation to enforce uniqueness of the key for all operations associated with the map, and in particular for any write operations in the map, *i.e.* `put` and `delete`. This means that interactions must first search for the existence of the key as a part of their behaviors and their overall efficiency is subject to the efficiency of search within the data structure. Efficient search is therefore a top priority of any map implementation.

#### Associative Array

As with most ADTs, we can use an array to implement a map and in this context we will call this type of array an associative array or array map.  Consider a subset of the student data presented before.

![](/home/jrt/gwu/course/cs1112/assets/map-aa-example-unordered.png)

The data could be represented as a set of records ordered or otherwise using an array.  Consider the efficiency of `get`, `put`, and `delete` in the associative array.

If the array is unordered, then the efficiencies of `put`, `get`, and `delete` are all $O(n)$ because we have to first linear search for any map operation because we must first determine whether or not the key exists in the data structure before fulfilling the operation.    The efficiency of linear search in an unordered array is $O(n)$ where $n$ is the number of keys in the array, so a map using an unordered array will generally be an $O(n)$ data structure for all map operations.   For a proof of the efficiency of linear search in an array refer to *Chapter 5 - Search*. 

However, we could instead maintain the array as an ordered set ordered on the key, in this case the student identifier, allowing us to use binary search on the array instead of linear search.

![map-aa-example-ordered](/home/jrt/gwu/course/cs1112/assets/map-aa-example-ordered.png)

if the array remains ordered by the key, then the binary search worst case efficiency of $O(\log_{2}n)$ where $n$ is the number of keys in the array determines the overall efficiency of the data structure in terms of search.  Since `get(key)` is just a search, then the efficiency of `get(key)` will be $O(\log_{2}n)$ as long as the array is maintained in order on the key field.  For a proof of the efficiency of binary search in an array refer to *Chapter 5 - Search*.   

Recall that `put(key,value)` first searches the array for the existence of the key and if the key is found, the value is updated; otherwise, the key-value pair is inserted into the array.  Since the array is in order, we can use binary search to answer the existential question; however, our worst-case for this 'search and insert' operation actually emerges from maintaining order when inserting or removing an element and not from the search.  If the key does not exist, we must insert the key-value pair into an ordered array, so we would need to make space for the new element.  Regardless of whether or not spare empty space is preallocated in the array, we would still need to shift all elements over to insert the element into its correct ordered position.  If the element already exists in the array, then `put` will just update the value and the shift is not needed so the update is not a worst-case operation.  Therefore in the worst-case, `put` in the associative array is $O(n)$ where $n$ is the number of keys in the array. 

`delete(key)` also suffers from the same efficiency issue just in reverse.  Even though we don't perform an insert *per se*, the process for `delete` is effectively the same except for the final insertion step from worst case `put`, *i.e.* we first search and then we shift skipping the final insertion.   For `delete`, we need to shift elements back toward the low-order indices in order to fill the space left by the element we removed as we do not want to have gaps in the array.

Using an associative array is feasible, but for many operations other than `get` in an ordered array, the efficiency is generally no better than $O(n)$. This begs the question of whether or not there exists a data structure we can implement for maps that will give us consistently better efficiency than the associative array.

#### Binary Search Tree

One alternative might be to store the key-value pairs in a binary search tree and search in the keys, raising the question of whether or not the characteristics of a BST match well to a map.  A BST by its very definition is ordered, its search efficiency is $O(\log_{2}n)$ as long as it remains balanced, and it is possible to rebalance a tree in $O(\log_{2}n)$ time.  Given these characteristics, it suggests that most if not all operations of a map can be supported in $O(\log_{2}n)$ time complexity.

![](/home/jrt/gwu/course/cs1112/assets/map-bst-example.png)

The map interaction `get(key)` is simply a search on a key.  If a BST is ordered by keys, then the existential question for a key existing in the tree can be determined based on the efficiency of search in a BST and once the key is found, the value can be retrieved from the identified node in constant time. The efficiency of search in a BST is $O(\log_{2}n)$ where $n$ is the number of elements in the tree as long as it remains balanced.  For a proof of the efficiency of search in a BST refer to *Chapter 10 - Trees*. 

The map interaction `put(key, value)` involves first a search followed by either an update or insert.  As established with `get(key)` the efficiency of search in the BST is $O(\log_{2}n)$, so the question is what are the efficiencies of update and insert.  The process of searching the BST would result in locating either the node in which the key resides or the node to which the key should descend from on an insert.  Updating the associated value for a key-value pair should be no worse than constant time, so a `put` that results in update should be $O(\log_{2}n) + O(1)$ reducing to $O(\log_{2}n)$ in the worst case.  Inserting after already locating the parent node of the key to insert should also be no worse than constant time followed by a potential rebalance along the search path.  Recall that a failed search in a BST means that we end at a node that does not have a child in the expected direction where the key we are searching on should lie, so adding a new KVP at this position requires only allocating a new node, attaching that new node to the unassigned branch of the node reached during search making the insertion part of `put` a constant time operation.   If rebalancing is $O(\log_{2}n)$, a `put` that results in insert should be $O(\log_{2}n) + O(1) + O(\log_{2}n)$ or overall $O(\log_{2}n)$ in the worst case.  Therefore in a BST, the efficiency of `put` is $O(\log_{2}n)$ as long as it remains a properly implemented BST.

The map interaction `delete(key)` involves first a search followed by a rebalancing of the tree along the search path.  To efficiently delete, we can mark a node for deletion and then rebalance that node which will ideally cost no more to rebalance the subtrees associated with that node than the normal rebalancing operation.  If this methodology works, then `delete` is no worse than a search followed by a rebalancing operation which would again be $O(\log_{2}n) + O(1) + O(\log_{2}n)$ or $O(\log_{2}n)$ in the worst case.  Therefore in a properly implemented BST, the efficiency of `delete` is $O(\log_{2}n)$.

Clearly the BST is a better candidate in terms of efficiency than the associative array.  This does not mean we can’t use or should never consider the associative array.  There are some applications where efficiency may not be our top concern and the associative array may be functionally the easiest and most reliable choice; however, if efficiency is a high priority, then we should choose the BST over the associative array. But, is there something even more efficient than a BST?

## Review

1. The term “map” derives from mathematics. Explain symbolically the mapping of one domain onto another. What are the requirements for each domain?
2. Why is the map a one way relationship? What does it mean for values in domain X to have a one-to-one relationship with values in domain Y while values in domain Y have a many-to-one relationship with values in domain X?
3. What is the vertical line test with respect to the definition of a mathematical function and how does this relate to the idea of a map?
4. In computing, we map what to what? In other words, we typically develop a class to handle the mapping association. What is the typical definition for this class, *i.e.* what is a typical name for this class and what fields are defined for this class? In other words, what specific labels do we give to the abstract ideas of domains X and Y from our mathematical map definition?
5. What is the interface for a map, *i.e.* what are a map’s prescribed interactions and behaviors?
6. Why must keys be unique?
7. Why does the uniqueness of keys imply all map operations are search?
8. Describe the implementation of an associative array for a map. 
9. What is the efficiency of each map interface method for the associative array?
10. Should we insert new elements in order into the associative array or should we periodically sort the array? In other words, what would be the efficiency of inserting into an ordered array versus the efficiency of sorting?
11. Describe the implementation of a binary tree for a map, *i.e.* a treemap. 
12. What is the efficiency of each map interface method for the treemap?
13. What is the relationship between the number of levels and the number of elements in a balanced binary tree? How does this relate to the maximum number of steps in search of the binary tree?
14. What is the degenerate case for a tree map? Why might a degenerate case arise in a binary tree? What is the efficiency of the degenerate case? What data structure does the binary tree degenerate into in the degenerate case? Why?

# 12 - Hash Tables

A hash table is an array of structures as illustrated in Figure 12.1. The structures referenced by the array are typically linked-lists, but more sophisticated structures like trees could be used instead. The type of container each bucket references is an implementation detail left up to the hash table designer, so for the duration of this discussion, we will assume that a hash table is an array of linked lists.

| ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXecdQUH_m5MGfkvMhIwU_PZDxZ5gE2DZstCILXtN6mxdtHdgAhfgu9EA18vSUoXZUSyKyBGVLfeH25TU4YnMyJslUYpZZeb5NBzWm9QfXaDyAPgSxij6ifvLZ4r2kUF_Eb2bR8p?key=B8kUrrFvwreS7-aRV424UChK) |
| :----------------------------------------------------------: |
|  Figure 12.1 - Hash table $A$ is an array of linked lists.   |

We call each index of the array a **bucket** to convey the idea that each index is itself a container that can hold multiple items. The number of buckets will be quantified by the variable $m$, so the size of the array is $m$; however, the size of the array is an independent decision from the size of the input $n$. 

A developer controls the size of the array which is often static and determined at design time while users control the size of the input which is generally dynamic and determined at run-time.  The linked-lists allow the hash table to dynamically grow to accommodate users but changing the number of linked lists (the size of the array) at runtime would be extremely inefficient, so the number of buckets is generally fixed at design time by the developer.  It is rare to include logic that resizes the hash table programmatically during run-time because doing so effectively eliminates the possibility of having an insert efficiency better than linear. 

Hash tables therefore introduce two independent variables that will affect efficiency, $m$ and $n$, so we will need to consider and address both when performing any efficiency analysis on hash tables.  However, we still want to conclude our overall efficiency of hash tables in terms of $n$ exclusively, so that we can easily relate and compare the hash table to all other data structures and algorithms we have so far studied.  We will need to classify hash tables according to a few general relationships between $m$ and $n$ so that we can effectively generalize our claims in terms of $n$ in the final analysis.

To determine which linked list in the array a particular element should be associated with, we use a hash function.

## Hash Function

The hash function’s role is to map an **arbitrary size value** into a **fixed size value**. A hash function takes in a string of data as input and converts that input string into a single number that is bounded within a limited range of values. In the case of a hash table, the bounds are $[0,m-1]$ where $m$ represents the number of buckets or the size of the array.  If the range of outputs from the hash function is bounded $[0,m-1]$, then any output from the hash function would be a legal index for an array of size $n$.  If the hash function is limited to this output range, then the hash function should convert any arbitrary size string into a legal fixed size index for the array.

In other words, given an input string the hash function converts this input string into an index identifying a bucket (the array element). which acts as the identifier of the specific linked list in the array that should contain any data associated with that input string. A given string always maps to the same bucket, so there is one and only one bucket that a given key may be associated with.  Ideally, all buckets have sparse numbers of elements in them so looking in any bucket is a simple, constant time operation.

All values in computing are numeric, so all symbols in a computer are already mapped to numeric values anyway, *i.e.* ASCII, so performing some form of math on a string is trivial. Fixing an integer into a specific range is trivial using modulo, *i.e.* the remainder from integer division.  The number of buckets, $m$, is determined when the a rray is allocated, so $m$ is a fixed and known value at all times for the array.  It is also not necessary to be able to retrieve the original input from the hashed output -- we don't have to be able to retrieve the key for a given value -- so the hash function does not have to be reversible, but it must be **deterministic** meaning that there is no randomness in the hash function and the same input key must always map to the same output value.

So in terms of a hash table acting as a map (a hashmap), we can hash any key and find out which array index the key is associated with. The key always hashes to the same index as long as the size of the array stays the same, so the hash function consistently and <u>always</u> maps *any arbitrary key* to *one specific bucket* as long as the size of the array stays the same.

```pseudocode
int hash(HashTable H, String s)  
    for each ch in s:    
		sum += ascii(ch)  
    hashvalue = sum % H.buckets
    return hashvalue
```

A hash function is a very basic form of cryptography and researchers have developed a variety of hash functions; however, hash functions can be quite simple as long as they consistently generate the same output given a specific input.

### Requirements

An ideal hash function must be as fast as possible -- run in constant time -- since it will be used in every hash table operation to identify a key's associated bucket.  Being the case, this means that its efficiency is a factor in all other operations, so the efficiency of hashing could dominate all operations.  If hashing is constant time, then it will not be the dominant term in the efficiency equations for map operations and is effectively ignored.

An ideal hash function is also **unbiased**.  Bias means that a system has a tendency to prefer one thing over another. An unbiased hash function should produce a **uniform distribution** of outputs given any set of inputs where a uniform distribution means that every result has equal probability like a “fair coin” or a “fair die”.  A hash table's efficiency is dependent upon statistical probability where we would like the distribution of elements among buckets to be the average $\frac{n}{m}$, but this behavior only arises if the hash function is fair and there is a relatively equal probability for each bucket to be the result of a given hashing input.

### Probability

For a fair coin, the probability of heads to be 0.5 and the probability of tails to be 0.5.  

<img src="/home/jrt/gwu/course/cs1112/assets/coin-headsandtails.png" style="zoom:50%;" />

These probabilities are derived from the fact that there are two options and both are equally likely to occur, so the individual probabilities are all $\frac{1}{2}$.  For a fair six-sided die, the probability of any one specific number of the die being rolled would be $\frac{1}{6}$.

Probability says nothing about the outcome of a single coin flip or a single die roll and probability is incapable of predicting the outcome of the next trial.  Instead it is a measure of the aggregate total of many outcomes with respect to a significant number of trials.  In other words, it is perfectly within the bounds of probability to flip a coin repeatedly and get a sequence of heads or a sequence of tails; however, if the coin is flipped a sufficient number of times, *i.e.* hundreds of times, all of the sequences will cancel each other out eventually and the ratio of the number of heads outcomes to the total number of trials will converge towards the predicted probability of $\frac{1}{2}$.  

Unfortunately, what represents a "sufficient number" is ill defined and the answer is generally a lot more than you think you need.  In other words, statistics is more meaningful, accurate, and predictive over large sample sizes so the more flips you make the closer the answer will get to the true probability.

Suppose we flipped a fair coin ten times and the result was a streak of heads one after another.

<img src="/home/jrt/gwu/course/cs1112/assets/coin-allheads.png" style="zoom:50%;" />

This is an extremely rare event and seems to defy probability; however, this event is possible and is equally probable to flipping a coin ten times and getting the precise sequence of heads-tails-heads-tails-heads-tails-heads-tails-heads-tails.  

<img src="/home/jrt/gwu/course/cs1112/assets/coin-headstails-oneafteranother.png" style="zoom:50%;" />

We enter the realm of permutations when specific sequences are focused on, and as discussed earlier, this means that the number of sequences possible from flipping a coin multiple times is measured in terms of a factorial equation.  It also means that the probability of getting a specific sequence is very, very small because this is the only version out of hundreds, thousands, millions, etc. of permutations with that exact sequence.

The probability of a single flip is $\frac{1}{2}$ because there are only two options (heads or tails), both are equally likely (fair coin), and one of those outcomes must happen (cannot result in a "null" outcome like balancing on the edge of the coin).  However, the probability of a specific sequence of flips is the product of all the probabilities for each individual flip which as the length of the sequences increases makes it increasingly less likely to have two sequences of flips equal each other.  Each flip is its own independent sample so it is unbiased and unaffected by any previous states.  So while it is highly probable to get a heads followed by a heads it is much less probable to get heads, heads, heads, or any other longer specific sequence.

Over the span of all flips of a fair coin, regardless of the specific sequencing, the coin should trend towards an equal number of heads and tails.  Sometimes we can get a string of heads and it is even possible, if unlikely, to get ten heads in a row; however, if we flip the coin enough, the overall count of heads and tails will be approximately equal.

Most sequences of ten flips will be roughly equal in terms of the number of heads and tails

<img src="/home/jrt/gwu/course/cs1112/assets/coin-headstails-random.png" style="zoom:50%;" />

Some sequences may generate a large run of heads

<img src="/home/jrt/gwu/course/cs1112/assets/coin-headstails-headstreak.png" style="zoom:50%;" />

But for every run of heads, there will be a run of tails or small runs of tails roughly canceling it out

<img src="/home/jrt/gwu/course/cs1112/assets/coin-headstails-tailstreak.png" style="zoom:50%;" />

In the end, for a fair coin with enough flips, we will find that there is approximately the same number of heads and tails.  If a coin is flipped 1000 times, the outcome may be 506 heads to 494 tails or approximately a 50/50 ratio.  If we continue to flip, the results will continue to trend towards the 50/50 ratio even if the numbers are not precisely 50/50.  Probability is messy in terms of the specific details, but the overall statistics are consistent as long as the system is fair.

A good hash function should avoid the tendency to pick a subset of outputs over all other potential outputs and yields a probability of $\frac{1}{m}$ for any output index generated making the probability of any index generated both equal and fair given a randomly generated input key.  An unbiased hash function means that It is okay for two or more keys to hash to the same bucket as long as the probability of hashing to any bucket remains equal.  From a practical standpoint, this means that for a small number of inputs into a hash table (less than the number of buckets), there will be some buckets containing zero keys, most buckets containing one key, and a few buckets containing two or more keys.  While some buckets may contain two or more keys, this should be extremely rare if the number of inputs is small.  If one bucket contains a significant number of keys given a small number of inputs and a significant number of buckets, then it is probably indicating a biased hash function.

## Implementation

A hash table is generally defined as an array that uses a hashing function to determine which index an element is assigned. A hash table is also an implementation of the map ADT, so a hash table fulfills the map interface and is often called a hashmap for this reason.

```java
class HashMap {  
	private LinkedList[] table;     		// array of linkedlists   
	private int hash( String key ) {...}	// hash function   
	
	// public map interface  
	put( key, value ) {...}  
	value get( key ) {...}    
	value delete( key ) {...}
}
```

In each map function, the hash table first uses the hash function to hash the input key to find an integer representing the index of the bucket that the key-value pair must belong to. However, by definition of a map, the key must always remain unique within the hash table, so the bucket must be searched for the existence of the key in all operations. 

For example, `put` performs either an insert or an update operation by definition.  If the key exists in the bucket, then `put` performs an update, and if the key does not exist in the bucket, then `put` performs an insert.  This means the existential question determines the operation performed by `put` so search must be performed first. 

Hashing to a specific bucket is easy and fast, but searching a bucket will depend on how many elements are in the bucket.  If the bucket is not empty, we cannot know whether or not we are inserting into the bucket until we traverse the entire linked list contained in that bucket.  For this reason, it is mostly useless to have a tail associated with the hash table linked lists because we cannot blindly insert into a bucket and instead we must first traverse it and find the tail anyway.

Consider a concrete example of `put`. When the key-value [“Hello”, “World”] pair is put into the hash table, the key “Hello” is hashed, suppose the hash function returns the result of 2. The bucket at index 2 is searched for the key “Hello”. If the key is found, the existing value associated with the key-value pair in the bucket is updated to “World” and the operation is complete. If the key is not found which can only be known if the tail of the linked list in bucket 2 is reached, then a new key-value pair is appended to the end of the list in bucket 2.

Consider a concrete example of `put` involving a hash table containing keys representing first names with 26 buckets and the hash function returning the index associated with the alphabet position of the first character in the first name.  For example, the key "Andy" would hash to the first bucket because it begins with "A", the first letter in the alphabet and the key "Casey" would hash to the third bucket because it begins with "C", the third letter in the alphabet.

<img src="/home/jrt/gwu/course/cs1112/assets/hashtable-insert-setup.png" style="zoom:50%;" />

If we insert the key "Chris" and some associated value data into the above hash table, we would first hash the key to find "Chris" should belong to the linked list associated with index 2.

<img src="/home/jrt/gwu/course/cs1112/assets/hashtable-insert-hashtoll.png" style="zoom:50%;" />

We would then need to iterate over the linked list referenced by index 2 comparing each key in the linked list to the to the search key starting with the first element.

<img src="/home/jrt/gwu/course/cs1112/assets/hashtable-insert-start.png" style="zoom:50%;" />

We would end the search if the key was matched OR if we reached the end of the linked list.

<img src="/home/jrt/gwu/course/cs1112/assets/hashtable-insert-end.png" style="zoom:50%;" />

If the last element is compared and it does not contain the key that is being searched for, the key and associated data can be inserted as a node at the end of that linked list.

<img src="/home/jrt/gwu/course/cs1112/assets/hashtable-insert-insert.png" style="zoom:50%;" />

By adding the element to the end of the linked list designated by the hash function, the element is added to the overall hash table

<img src="/home/jrt/gwu/course/cs1112/assets/hashtable-insert-conclusion.png" style="zoom:50%;" />

Otherwise, if the key was found before the end of the list was reached, then `put` performs an update of the value at the element pointed to by the iterator.

## Time Complexity

Remember that there are two independent variables that must be considered when analyzing the efficiency of the hash table: $n$, the number of elements **in the entire hash table**, and $m$, the number of buckets in the hash table. 

While we must consider both variables at the beginning of the analysis, we want to eliminate $m$ through our analysis so that we can continue to compare the hash table to all other data structures and algorithms. In other words, the value of $m$ affects the efficiency a hash table so we cannot ignore $m$ in our analysis, but we need to find a way to eliminate $m$ in our conclusion so that we can establish a final Big O evaluation(s) involving only $n$.  We want to frame the final analysis in terms of $n$ because other algorithms and data structures do not have any correlation with $m$.  If we our final Big O analysis includes both $m$ and $n$, then hash tables cannot be easily and directly compared to other data structures.  We did this in the tree analysis as well when we introduced the height of the tree as an analytical variable and eliminated it in the analysis by established and expressing the mathematical relationship between height and $n$ in terms of $n$.1

Let us assume that the hash function is unbiased and consider the analysis of the hash table in terms of the ratio of number of elements in the hash table to the number of buckets, *i.e.* $\frac{n}{m}$. Structuring the ratio in this manner makes sense because a hash table always has at least one bucket, so the denominator is always a positive, non-zero number.  Additionally, if we can somehow eliminate $m$ through the analysis then $n$ already resembles other Big O analysis.

The ratio of $n$ and $m$ is of such significance, it is specially named as the **load factor** and is a measure of "how full" a hash table is.

We can classify the hash tables as belonging to one of two cases:

1. $n$ is significantly larger than $m$, *i.e.* $n >> m$
2. $n$ is approximately equal to (or smaller than) $m$, *i.e.* $n ≲ m$

##### Analysis of Case 1

Assuming an unbiased hash function, if $n$ is significantly larger than $m$, *i.e.* $n>>m$, the numerator of the ratio $\frac{n}{m}$ dominates the equation.  The size of each bucket on average is trending towards the overall number of elements in the entire table or the number of elements in each bucket is approximately $n$ elements.  In other words,  $m$ is constant and small so we can decompose the equation $\frac{n}{m}$ into the equation:
$$
\frac{1}{m} \cdot n
$$
With $\frac{1}{m}$ acting as a constant coefficient, we can drop constant coefficients in Big O analysis so the equation reduces to:
$$
n
$$
And as a result, every search is effectively like searching a linked list of size $n$ and therefore the overall efficiency of the hash table is $O(n)$. Since we must search in every map operation, the efficiency of `put`, `get`, and `delete` are all $O(n)$.

| ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcjDWzZbOEY4GvgcM0dpb8cq_gKEDGoyDdNG3Z4WLHeH8OP0m9h0P8JFiDvfoXTms1eutCKe_V8pFviELrBfey3MVd4ZqPz4XD52cBjXMAejsgpvEs6eofQ8CbTlgttjHG89UzUEw?key=B8kUrrFvwreS7-aRV424UChK) |
| ------------------------------------------------------------ |
| Figure 2 - A hash table that performs in linear time has significantly more data than buckets and therefore all the buckets are performing more like linked lists |

This case represents the scenario where a user has crammed a lot of data into the hash table and we the developer did not anticipate the hash table would be supporting this much data when we specified the size of the hash table initially.

##### Analysis of Case 2

Assuming an unbiased hash function, if $n$ is approximately equal to (or smaller than) $m$, 
$$
\lim_{n \rarr m} \frac{n}{m} = 1
$$
In other words, as the ratio $\frac{n}{m}$ approaches 1, $n$ and $m$ are approximately equal and $\frac{n}{m}\approx 1$.  Under these circumstances, it is reasonable to conclude that the efficiency of the hash table is $O(1)$ and constant time.  

In fact, for any $n$ where $n < m$, then $\frac{n}{m}<1$, and $O(1)$ continues to be a reasonable, straightforward conclusion. 

In this case assuming an unbiased hashing function, each bucket contains about 1 element. Some might contain two elements, some may contain zero, but from a statistical standpoint all buckets contain about the same number of elements and that number is small and approaches 1. In this case, buckets are mostly empty or contain only one or two elements each, and the efficiency of every search is effectively like searching an array using direct access because each bucket has an average size of 1 and the maximum number of elements per bucket approaches an average of 1.  Therefore the overall efficiency of the hash table is $O(1)$ for every map operation.

| ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXe3YrO3dOKiRm694uXm9nsT-99E4OeLHoH525s-Zn4Ahwv3j4bljMwt69oD89Z2iAKvTCuB7OevJ1yjrADSlQ_3tyTK8PZVLZQfhDwMc8K_hINpMLnlK-uiBSjxtvW73uBosibDnw?key=B8kUrrFvwreS7-aRV424UChK) |
| ------------------------------------------------------------ |
| Figure 3 - A hash table that performs in constant time has a near uniform distribution of elements among m buckets and each bucket has a small number of elements in it. |

This does raise the question of when does the efficiency tip from this case to the first case and that is a difficult answer and hence the reason the comparison for the first case is “$n$ is significantly larger than $m$”.

This second case represents the scenario where the developer has appropriately studied and modeled their data needs and has a reasonable understanding of the maximum amount of data that will need to be stored in the map. This does not mean that $m$ must be larger than $n$ to achieve constant time performance, but it does mean that the developer has a reasonable expectation of the upper bound on the number of elements that should be in each bucket.

##### Analysis of Degenerate Case(s)

Like a degenerate tree, we can have degenerate cases arise with a hash table. Degenerate cases are generally failures of the system and are not strictly due to insufficient design.

One such degenerate case that is out of the developers control can arise due to software being used for a long period of time without update. As software becomes more critical and trusted and more data become introduced into a problem space, users often start to exceed the original design specifications and performance can precipitously drop especially when the initial design assumed a maximum input size of $n$ and users are currently trying to use the same software on inputs of size $n^2$ or worse.

Another degenerate case that is under the developer’s control is the case of *bias in the hash function*. A biased hash function renders the statistical assumptions that we build our efficiency analysis on for a hash table moot. Our argument about hash table performance is built on the average number of elements per bucket being approximately $\frac{n}{m}$ which is linked to the requirement that the hash function must produce a uniform distribution of outputs. In other words, all outputs must have equal probability. However, if there is bias then one of the outputs is more likely than the others and the efficiency of the hash table is negatively affected.

If the hash function is biased, this can lead to one bucket being preferred over all others. This means that more keys hash to a single index and the linked list in that index grows significantly larger than all other indices. In this case, it is more likely that the hashing of any key will result in the access of the biased bucket and the number of elements in that bucket is trending towards n and therefore the required search for each map operation is now iterating over a linked list of size n rather a linked list of size nm. In other words, with a biased hash function, the hash table degenerates into performing like a linked list instead of a hash table and the efficiency of its operations are $O(n)$.

| ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXd_Ho0xmvINbOj-0paSlZyfFAJG1LuXUQmsF-FpWhzk3sfEFCrH9EAqocIPdJpZcW06OL8B152QDEWwDVtyv1khk2GkfkMbykqJqR_xMr9OiN6CfxQveJdpmgycaOUz8sv-NxXubQ?key=B8kUrrFvwreS7-aRV424UChK) |
| ------------------------------------------------------------ |
| Figure 4 - A biased hash function results in a degenerate hash table where one bucket is preferred over all others. |

## Alternative Decisions

Recall that the hash table is not our only choice for a map implementation.  While the associative array is a much poorer choice, the binary tree is a reasonable alternative to the hash map.

![ ](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdCzSmbwwH-UIEDQxJWH7ngIGL6XYqhmW3lzBGtY_Ctt75nUoqk1sc9yo5TS8IlY-jG7TTzl9B2an7_tOnkCKvzXEYJGAUtnScaPxg361QBUl35cLOpRQx0zJ29LcZG7L4bXN0y?key=1klISeGJgJOidd2MWfltZX0w)

Which leaves an open question as to when should you choose a hash tree over a hash map.

The hash map has unbeatable performance when $\frac{n}{m}\approx 1$, but this assumes that we have some understanding and control within the problem space.  $m$ is generally chosen by us developers at design time before the software is even shipped to software users and $n$ is generally decided by software users during run time rather than by us developers.  If we do not understand the potential scale of $n$ that users expect to use, it is difficult to select an appropriate $m$ to take advantage of the efficiency of a hash table.  It is also difficult to design a hash table capable of resizing itself to amortize the time complexity of insert like we did so with the doubling strategy when growing unordered arrays.

If we attempt to redefine $m$ at run-time, we have to rehash everything in the hash table tanking our hash table efficiency to $O(n)$.  For the array, we had everything to gain because insert was always $O(n)$ when the array was full so our performance was already at worst case.  The hash table is generally operating closer to $O(1)$ until we reach a somewhat ambiguous threshold were the performance starts to trend toward $O(n)$; however, if we implement an aggressive strategy to redefine $m$ then the hash table is guaranteed to operate at $O(n)$ with some frequency and is basically operating as an associative array.  If there are better candidates out there that consistently perform better than $O(n)$ such as a binary tree map that operates at $O(\log_{2}n)$, it raises the question of why design a complicated hash table that is no better than an associative array when there is a ready solution at hand that consistently performs more efficiently.  A more appropriate way to frame this question is, when should we switch from a hash map to a binary tree map for a map implementation.  It is critical to know your application's domain and its potential clients.  

| ![](/home/jrt/gwu/course/cs1112/assets/map-ht-plot.png) | ![](/home/jrt/gwu/course/cs1112/assets/map-bst-plot.png) |
| :-----------------------------------------------------: | :------------------------------------------------------: |
|                  Hash Table Efficiency                  |                      BST Efficiency                      |

If $n$ remains a complete unknown, it is difficult to predict an appropriate $m$ to take advantage of the hash map.  If $m$ is too small, the hash table will tend towards $O(n)$ efficiency for all operations because every operation depends on search and every linked list in the hash map contains some large proportion of $n$.  If $m$ is too large, the hash table is mostly empty and the space used is effectively wasted; however, it is still better to have a sparsely populated hash map servicing operations at $O(1)$ for high frequency searches than to choose too small an $m$.  When $n$ is an unknown, it is generally better to choose a binary tree map instead.  

Consider the implication of the following relation in terms of a hash map's load factor with respect to a binary search tree of minimum height:
$$
\frac{n}{m}= \log_{2}n
$$
The above equation marks the point at which a hash table performs the same as a binary search tree.  If a hash table's load factor exceeds the maximum depth of a balanced binary search tree, then the binary search tree is a more efficient data structure in terms of both search and insert.  The derivative of a linear equation is constant, so when a hash table begins to "fill up", the hash table becomes consistently less efficient.  Counter-intuitively, the derivative of the logarithm decreases as $n$ increases, so the binary search tree is extremely efficient when handling very large sets of data when compared to any linear data structures.  This leads to the argument that if $n$ is difficult to predict or unknowable, then it is better to chose a binary tree map over a hash map.  However, if an $m$ can be chosen with respect to $n$ to maintain the relationship
$$
\frac{n}{m} < \log_{2}n
$$
then a hash table would be the optimal solution.

| <img src="/home/jrt/gwu/course/cs1112/assets/map-ht-bst-decision.png" style="zoom:70%;" /> |
| :----------------------------------------------------------: |
| Once $\frac{n}{m}> \log_{2}n$, then the BST is a more efficient implementation of the map. |

It might be difficult to anticipate $\frac{n}{m}= \log_{2}n$ , so a general guideline for selecting a hash table over a binary tree is to consider whether or not the size of the data $n$ is bounded and can be anticipated.  In other words, if $n$ is predictable and of reasonable size, then it is possible to choose an $m$ such that the hash table can  provide constant time access; however, if $n$ is generally an unknown and expected to be large, then a binary search tree is a better alternative by default.

## Review

1. Describe the structure of a hash table.
2. What does the hashing function do in a hash table? How does the hashing function relate an arbitrary sized data representation to a fixed sized data representation? Practically, how does the hash function relate a key to a bucket?
3. What does bias mean in terms of the hashing function? If a hashing function is biased, what will the hash table generally look like?  How will the efficiency of the hash table be affected?
4. Why is the number of buckets an independent variable with respect to the number of elements?  Who controls the number of buckets and when is it chosen?  Who controls the number of elements and when is the size of the input known?
5. What is the relationship between the number of buckets and the number of elements?
6. Why do we express the relationship between the number of buckets $m$ and the number of elements $n$ as $\frac{n}{m}$ in our analysis? In other words, why do we use a ratio, why is $m$ in the denominator, and why is $n$ in the numerator?  What would swapping numerator and denominator make less sense?
7. Why do we condition our arguments with multiple cases in the hash table?  In other words, why do we *caveat* our analysis with ideas like “where $n$ is significantly larger than $m$” or “where $n$ and $m$ are approximately equal”?
8. Assuming an unbiased hash function, when $n$ is significantly larger than $m$, what data structure does our hash table resemble, what is its efficiency for all map operations in this hash table, and why is it performing this way?
9. Assuming an unbiased hash function, when $n$ is less than or approximately equal to $m$, what is its efficiency for all map operations and why is it performing this way?
10. What is the degenerate case for a hash table?  Why might a degenerate case arise in a hash table?  What is the efficiency of the degenerate case?  What data structure does the hash table degenerate into in the degenerate case and why does it resemble this data structure?
11. Describe the implementation of a hash table for a map, *i.e.* a hash-map.
12. What is the efficiency of each map interface method for the hash-map?
13. In optimal conditions, the hash table is the most efficient map implementation. What are these optimal conditions?
14. Under what circumstances would the binary tree be the better solution for a map implementation? Why?
15. Why is the associative array generally the worst choice among the three potential map implementations discussed?  Contrast the associative array’s average performance with respect to the worst case performance of both the tree-map and hash-map.

# 13 - Graphs

A **graph** $G$ is defined by $G = (V,E)$ where $V$ represents the set of vertices and $E$ represents the set of edges that compose $G$.  A **vertex** is a node (element) within the graph.  An **edge** connects (associates) two vertices in the graph such that $e_{ij}=(v_{i} ,v_{j})$ where $V ∋ v_{i} , v_{j}$ and $E ∋ e_{ij}$.  We encounter graphs everywhere in daily life; although, systems that can be organized as graphs may not always take a clear form as a graph.

| ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfelZfAGiSfhF0yRIabVUsgcJ-ktFy1Kmn4_xOkYGinGkjx53j817DzAgOfvLTweB2AJNklSHUE64IGaXdbKX1GqZQC6beNI-THUMWftI4Emsbb9wTfhq5CIhW7iPADqyqXqEsx?key=XYBq4a5_K7w37fYNYXAoaWFB) | ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfD2aDqLXRwGMhHBiZh1dc8OSOkkuiXdoAEzE8Gg31eQM4ptgDBU__85cXuSfWC0FafwikzrEz7Uz_NE76u4qiCCYKjh8-n63ufkCZW4-RMGDCAxmAtMD2GDCLOdNKnCs8XlLEKrw?key=XYBq4a5_K7w37fYNYXAoaWFB) |
| :----------------------------------------------------------: | :----------------------------------------------------------: |
|              **Washington DC Metro Subway Map**              |                    **Internet Topology**                     |

Two vertices are **adjacent** if they share an edge joining together and an edge may be **directed** or **undirected**.  A **directed graph** is a graph that contains directed edges while an **undirected graph** is a graph that does not contain any directed edges.

| <img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXem1v7NymblJH2nVGqjf6rtuMzeygLzUqYqeL77nd1r7dtPAbGT_neFR8IZ4IHmOd3G8O_xGlgZg4gXSMoTrfDi3Xg3IuFWuDn2c_0hFe3jyuINQ1Hot_v2NfP3mTAJBIUMKvpABA?key=XYBq4a5_K7w37fYNYXAoaWFB" alt="img" style="zoom:80%;" /> | <img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXc4xxvkUnrm8YdD_gXJnF_s1k_fgxf2oOV8pFipvwU7R_mxnpL5aF74m5VHCNp4piEek_RmnS7_39zRO20IBTJtdYQMe2jHihI42_Zm5oCGSjopKp6_iyRaPms3WD2hfL7EqDvipg?key=XYBq4a5_K7w37fYNYXAoaWFB" alt="img" style="zoom:80%;" /> |
| :----------------------------------------------------------: | :----------------------------------------------------------: |
|                          Undirected                          |                           Directed                           |

An **undirected edge** does not suggest or create any directional constraints.  An undirected edge is typically represented by just a line segment between two vertices and can be traversed in either direction along the edge’s axis.  In an undirected edge, the edge association $(v_{i} ,v_{j})$ is transitive or in other words, $e_{ij}=e_{ji}$, so there is no need to consider the order in the vertex pair and the vertices can appear in any order in the pair.

A **directed edge** points in a specified direction.  A directed edge is typically represented by an arrow that suggests transitions are only allowed in the direction in which the edge points.  The tail of the edge indicates the vertex at which the edge originates while the arrowhead indicates the vertex at which the edge terminates.  For the directed edge $e_{ij}=(v_{i} ,v_{j})$, the order of the vertices matters, so the first vertex in the pair, $v_{i}$, designates the originating vertex and the second vertex, $v_{j}$, designates the terminating vertex.  Note that this means that the edge association is not transitive for a directed graph so all directed edges must be explicitly defined.  Alternative syntax might include an overarrow pointing from origin to terminator, $e_{ij}=(\overrightarrow{v_{i},v{j}})$, to specify direction.

For vertices in a directed graph we differentiate **outgoing edges** and **incoming edges**.  Outgoing edges are defined by where the tails of any edges drawn with an arrow emerge from a vertex and incoming edges are defined by the node that is pointed to by the arrow head at the end of an edge.  In an undirected graph, all edge terminators define both incoming and outgoing 

The **degree** of a vertex is the measure of the number of edges connected to it.  Degree may be further defined for a directed graph where degree is subdivided into **indegree** and **outdegree**. The **indegree** is the number of incoming edges to the vertex and the **outdegree** is the number of outgoing edges from the vertex.  For an undirected graph where there is no discrimination between incoming and outgoing edges, so the indegree and outdegree are equal and is generally summarized simply as degree.  For a directed graph, indegree and outdegree are not necessarily equal and these metrics are maintained independent of one another.

Edges may have a value associated with them which is called the edge **weight** and a graph with weighted edges is a **weighted graph**. A weighted graph can be directed or undirected.

| <img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXdcoKZ7LmKeA9UrJvR2CF6Mds0MOkWacUXSasmUvee6StUf0APoySSJ8yNMuKobomelmdMk46PIsglP3_kJR9_Qn2KqHyWfAWFLMcvWPEpZVqfE03uZJtEmfvbhjOcDs6mNmPHdvQ?key=XYBq4a5_K7w37fYNYXAoaWFB" alt="img" style="zoom:80%;" /> | <img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXf6GRQ-MFNPz3MUs59v5sAfwvrDxpqmLWDoL813GyOKT-wk51bsd-88YMZh0di_qbX6iCWi-cqU4EeZn6rzCyGXgYhgQLAKsJIVSDOmz5vnE42Q3zLEkL8s5_-xAe4c3yGbC2sDlg?key=XYBq4a5_K7w37fYNYXAoaWFB" alt="img" style="zoom:80%;" /> |
| :----------------------------------------------------------: | :----------------------------------------------------------: |
|                   Undirected and Weighted                    |                    Directed and Weighted                     |

Weights represent a **cost metric** associated with the transition along that edge.  Weight is intentionally abstract as it may represent a variety of costs such as a measure of distance, time, money, energy to traverse along that edge.  For this reason weights may also be called costs.  In an unweighted graph, we can assume that all the weight of each edge is generally equal to 1, or in other words, the cost of traveling along any edge is equal.

Two vertices, $v_{i}$  and $v_{j}$, are **connected** if there exists a set of edges between them that enables transition from $v_{i}$ and $v_j$.  If $v_i$ and $v_{j}$ are connected, the set of vertices and edges that connect $v_i$ to $v_j$ form a **path** between the two edges.  For a directed graph, a directed path adhere to any direction constraints. 

A **cycle** is a configuration of edges and vertices that results in a path back to an originating vertex.  In other words a cycle exists if there exists a path from $v_{i}$ to $v_{i}$.  Cycles may be formed by a vertex with an outgoing edge that is also an ingoing edge to that vertex or by a sequence of vertices that begins and ends with the same vertex.  A graph with no cycles is **acyclic**.

| ![](/home/jrt/gwu/course/cs1112/assets/graphs/example-cycle.png) | ![](/home/jrt/gwu/course/cs1112/assets/graphs/general-cycle-path.png) |
| :----------------------------------------------------------: | :----------------------------------------------------------: |
|               A single vertex can form a cycle               |              Multiple vertices can form a cycle              |

If $v_{i}$ and $v_j$ are connected, **distance** is the **total cost** of the path from $v_{i}$ to $v_{j}$.  For an unweighted graph, the total cost is the number of edges in the path connecting $v_{i}$ and $v_{j}$.  For a weighted graph, the total cost is the sum of the weights of all edges in the path from $v_{i}$ to $v_{j}$.  The **shortest path** from $v_{i}$ to $v_{j}$ is the path with the lowest cost.

Graphs are everywhere and we can represent every data structure we have so far studied as a graph. For example, any linked list meets the definition of a graph:

- All linked-lists are composed of vertices and edges where vertices are linked list nodes and edges are the references between nodes.
- All linked-lists can be considered to be directed graphs, whether singly linked or double linked because references create direction.
- The linking of nodes in a linked-list constructs a path that links the head and the tail and all nodes in a linked-list are connected as a result.
- Further, if the linked list is non-circular and singly-linked, it contains no cycles and is acyclic, but circular linked-lists and doubly-linked lists are cyclic.

Furthermore, there are many problems we encountered in the class that can be expressed as a graph. For example, the maze we studied with backtracking can be reimagined as a graph:

- Each cell in the maze can be described by the number of walls it has.  A square cell has 0, 1, 2, or 3 walls.  Two cells are adjacent if there is no wall between them.
- Assume that the start and end locations are vertices.  If traversal begins at the start vertex and the end vertex is ever reached during graph exploration, there exists a path in the graph from start to end.
- A cell with 0, 1, or 3 walls represents a decision point, whether it is a choice among multiple available paths or a point at which backtracking is necessary.  Decision points are graph vertices.  
- A cell with only 2 walls can be thought of as a "hall" and only serves to connect decision points.  Generally once one travels along a hall, they continue on until they reach the next decision point.  Therefore, halls are graph edges.   A weight for each edge can be measured by the length of the hall in terms of the number of cells along that hall before a decision point is reached.
- A decision point with 3 walls is a "dead end" and has a degree equal to 1.  Backtracking is necessary to escape a dead-end.
- A decision point with 0 or 1 wall is an "intersection" and there are multiple potential paths that emerge from an intersection.

| ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcKw7eU-3Dtgfo2BTZuPULe6vumg2s26efPTc5zo4NUsg8AF-FmWTn6g5nZ1vHEjvklC9Hh2PIgBO5ExoxLoasrz0qH7bK5HEEyW5bDUyZ5aTEvvTRJsy52ME9gOvOl5z413ZWHDw?key=XYBq4a5_K7w37fYNYXAoaWFB) | ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfvx3hBC8EhyTOr_CqcqDvjF7l5jIMRY08iVASZ59C74k01Tc-FlAOwuXgFbReCPPikWGr_Cg25veZBjqk2tuNH7bsiv9vG4jLXnSLB8qGJX4TVSW7wghW38Zumi7iae44srLQ8ww?key=XYBq4a5_K7w37fYNYXAoaWFB) |
| :----------------------------------------------------------: | :----------------------------------------------------------: |
|                   *The geometry of a maze*                   |                     *A maze as a graph*                      |
| ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdjdH3AXGcjMFTWdi6P09jQ5q0ntLrSrIecHuN8_7VR3bLhVRTvcCSsYujc2ZGH_zWbgMC_KPnsIjM6LGhPWvSyfxQtHThJtzE9chTgce2fPQ_JclHEDo5WPtrXJu5SnjGr_ajFlQ?key=XYBq4a5_K7w37fYNYXAoaWFB) | ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXegJCe7Xi_dEwFRIqQc50-9z0ajUnohT9aPuUyYO_mjTfDaryZtnJTJcT6c-v4nhyvDdkdnOS3pQU2S8hlJNASflnor2VlCMKVlSSZ6k4dtaGWCA2a96FbfL1X3IXFyRgcW-f-f?key=XYBq4a5_K7w37fYNYXAoaWFB) |
|           *A maze demaring terminals and branches*           |                 *A maze as a weighted graph*                 |

| <img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXfL1fwABK04FLVYtBDqVWA00aFYlWW8ZSl3gGNKBD2Syt4Jf1dhRMY6FvOtlbRsw2QLR64KVWq6VWm77UHZdFYgBMvh-jpP-w357JzNf2AZRV-Lyj_cV-vaLCulYhHEwj2mN9upTg?key=XYBq4a5_K7w37fYNYXAoaWFB" alt="img" style="zoom:25%;" /> |
| :----------------------------------------------------------: |
| **A tree (therefore a graph) representing all the recursive calls to fibonacci given an input value of 5 when using a naive recursive implementation** |

### Implementation

The question of how to implement a graph poses the question “given a graph, how can we represent it?”

| ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcVVp-45IH7F0oNRsv7yM5fUvnEPCAG0qDiCaeZ1HWi0wl2L6cjwQJqgh64fukqGWwh2TkysrGCAkCqt8KzTQUxa9vuRBWdN0NGpJAW7Vf-WY8Pr0SLtxqOmvLScLRGUN1gLbpu?key=XYBq4a5_K7w37fYNYXAoaWFB) | ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdtTNC0Fr1_ITIWN6ooQXALHtbgFQbzvU_A_Ldz3idlLRDrDjZRDap9InHBewOr2His3buqHZhBqZ6aF1vmxw70Ud2wfOuM14dh85NIODnrXcNVlqnNvZPV1pf39t_1ysMzuf8_aQ?key=XYBq4a5_K7w37fYNYXAoaWFB) | ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcj2CgIKCeAOPTIULQZhUwlqLCBTOpchHe8-JqMzWDIfeh2RJE1T93PrG8TtmbE1O2HEncsRVQH2daqP0zY0mLzgtIrzyIF_FXlHSKEGdBfi1bHu2AyUcjIuaTYH9HGt_slm9ci?key=XYBq4a5_K7w37fYNYXAoaWFB) |
| :----------------------------------------------------------: | :----------------------------------------------------------: | :----------------------------------------------------------: |
|                         *Undirected*                         |                          *Directed*                          |                   *Directed and Weighted*                    |

Given OOP languages, our initial strategy might be to try to use an object oriented, referential approach using Vertex objects and Edge objects.  While this is a feasible structure that is capable of representing the graph, it is also difficult to perform efficient queries over the span of the graph as the edge data is not summarized in a succinct, efficient to query form.  

Given a purely OOP representational model, our graph has no single summary of adjacency that we can look up and instead we have to traverse the graph to answer a basic question such as whether or not two vertices are adjacent.  Recall that two vertices are adjacent if there is an edge connecting the two vertices.  If we have to search the graph to fulfill the most fundamental queries that we are needed for more complex operations, we inherit at the very least an $O(n)$ efficiency cost into the foundation of every graph query.

Graphs predate OOP, so we can lean on the basic and very efficient representations that facilitated graphs before OOP such as the adjacency matrix or adjacency list.  The adjacency matrix and adjacency list consolidate all of these adjacency relationships into a single data structure for easy access and fast query.

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXflHu88CtL3T0clBMtCbgxrMey_5SHnBG8zjVaXxvYARazyxondTbFcDyrzdWIoO195TcoT8oQdvZqZUhMm7Tw570X3bQpuQDVJe7iHPWurkMnxUlVY25bqxryXp77aOy2WKd-o?key=XYBq4a5_K7w37fYNYXAoaWFB)

#### Adjacency Matrix

An **adjacency matrix**, $M$, uses a two dimensional array to consolidate edge adjacency into a single table. The row and column indices map to one of the vertices in the graph and therefore the matrix is of size $n \times n$ where $n$ is the number of vertices.  To determine whether or not two vertices with mapped indices $i$ and $j$ are adjacent, $v_{i}$ can be queried against $v_{j}$ simply by looking up the value in $M(i,j)$.  For undirected graphs, the matrix is symmetrical and the property $M(i,j)=M(j,i)$ holds, but this is not the case for directed graphs.  In an unweighted graph, the value in the cell will be in the range $[0,1]$ which indicates whether or not the edge $(v_{i}, v_{j})$ exists where a $1$ indicates that $v_{i}$ and $v_{j}$ are adjacent and there exists an edge joining $v_{i}$ and $v_{j}$ while a $0$ indicates that $v_{i}$ and $v_{j}$ are not adjacent and there is no edge between $v_{i}$ and $v_{j}$.  For weighted graphs, the weight of the edge will be stored in the cell and the cell’s range is can be any numeric value produced by the cost function associated with the graph.

For example, suppose we have an undirected graph with 5 vertices, then the adjacency matrix will be $5\times5$ and there will be symmetry such that we can query either by row, column or column, row to determine adjacency.

| <img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXcVVp-45IH7F0oNRsv7yM5fUvnEPCAG0qDiCaeZ1HWi0wl2L6cjwQJqgh64fukqGWwh2TkysrGCAkCqt8KzTQUxa9vuRBWdN0NGpJAW7Vf-WY8Pr0SLtxqOmvLScLRGUN1gLbpu?key=XYBq4a5_K7w37fYNYXAoaWFB" alt="img" style="zoom:80%;" /> | ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXebeO1h9DlO45bn2fJdEckyuEyYKliFH3uYRWHZh8l9FX0RWrRd-a_DoWjcEOX79UJm5EX33cjb9SQzWqwaHLJWuEpbenuP5WTJzlRMyqQGaFpq-JwJ6CUCsx0xkKv1UVWTa8aR?key=XYBq4a5_K7w37fYNYXAoaWFB) |
| :----------------------------------------------------------: | :----------------------------------------------------------: |
|                         *Undirected*                         |                      *Adjacency Matrix*                      |

As suggested, the adjacency matrix in a directed graph is not symmetrical.  This means that $M(i,j) \neq M(j,i)$.  In this case, the adjacency matrix designer must clearly document whether row indices map to outgoing edges and column indices map to incoming edges or vice versa.

For example, given the following directed graph example, associated adjacency matrix, and the convention $M(i, j)$, there is an edge $(v_{0}, v_{2})$ because there is a $1$ in $M(0, 2)$ where $i$ represents as the row index for $M$ and $j$ represents the column index for $M$.  Whether or not two vertices are adjacent is therefore a constant time operation if we know both vertex indices.

| <img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXdtTNC0Fr1_ITIWN6ooQXALHtbgFQbzvU_A_Ldz3idlLRDrDjZRDap9InHBewOr2His3buqHZhBqZ6aF1vmxw70Ud2wfOuM14dh85NIODnrXcNVlqnNvZPV1pf39t_1ysMzuf8_aQ?key=XYBq4a5_K7w37fYNYXAoaWFB" alt="img" style="zoom:80%;" /> | ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfE7ojwCOrWbBBweU0goqrKE5W9o6qs4MK-AR2KVH6fPsz-S8_-_uyYn8fEOCxWGLW6gGXftlfn3fH2q76JC8Sbo0whWggD1TsrPBtrL3g-3d6TWO-BTJUOlkW-R_-1XP7F3lwjZA?key=XYBq4a5_K7w37fYNYXAoaWFB) |
| :----------------------------------------------------------: | :----------------------------------------------------------: |
|                          *Directed*                          |                      *Adjacency Matrix*                      |

Additionally, it takes linear time in the number of vertices to determine that there is one and only one incoming edge into $v_{2}$ because all the remaining cells in column $0$ equal $0$ and there is only a single $1$, in column $v_{2}$, on row $0$.  We can also quickly see that there are two outgoing edges from $v_{2}$ because row $2$ has two cells containing $1$ while all the rest of the cells on row $2$ contain $0$, indicating no edge. 

In order to maintain weights for weighted graphs, the weights for each edge can be stored in the cell instead of using the simple binary indicator.

| <img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXcj2CgIKCeAOPTIULQZhUwlqLCBTOpchHe8-JqMzWDIfeh2RJE1T93PrG8TtmbE1O2HEncsRVQH2daqP0zY0mLzgtIrzyIF_FXlHSKEGdBfi1bHu2AyUcjIuaTYH9HGt_slm9ci?key=XYBq4a5_K7w37fYNYXAoaWFB" alt="img" style="zoom:80%;" /> | ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXf4Z-0fPfkTcLv6Wa3ONfWujVrPGt19tsxgSt1LBSpUjnvz9rSz-bK3KpWbzhO3Sdt5APCmtQ8mlipONZQB2eNmxdx_fvYQby41M1m8Uor6MQWFg4FcpDvm_iCbNJewySCsQg1g0g?key=XYBq4a5_K7w37fYNYXAoaWFB) |
| :----------------------------------------------------------: | :----------------------------------------------------------: |
|                   *Directed and Weighted*                    |                      *Adjacency Matrix*                      |

An adjacency matrix provides for very fast lookup of edge data; however, it cannot resize efficiently.  To change the size of the adjacency matrix, it costs $O(n^2)$ where $n$ is the number vertices because we must copy a two dimensional array of size $n$.  In other words, the adjacency matrix supports fast lookup of adjacency information, but it is inefficient if the number of nodes in graph are changing.  This raises the question of whether or not there exists an alternative edge representation that is more efficient in terms of changing graph size, and the answer is to use an adjacency list.

#### Adjacency List

An **adjacency list**, $L$, uses an array of lists to consolidate edge adjacency into a single structure. In the adjacency list, the array index maps to the vertex identifier and therefore the array is of size $n$ where $n$ is the number of vertices.

For an undirected graph, every edge associated with a vertex will appear in the list mapped to that vertex. To determine whether or not two vertices with mapped identities $i$ and $j$ are adjacent, either $L(i)$ or $L(j)$ can be queried and the associated list searched for the other vertex.

| <img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXcVVp-45IH7F0oNRsv7yM5fUvnEPCAG0qDiCaeZ1HWi0wl2L6cjwQJqgh64fukqGWwh2TkysrGCAkCqt8KzTQUxa9vuRBWdN0NGpJAW7Vf-WY8Pr0SLtxqOmvLScLRGUN1gLbpu?key=XYBq4a5_K7w37fYNYXAoaWFB" alt="img" style="zoom:80%;" /> | ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXekYCP90B-32N9qrGkYarUqNiV6u24BJFM4lbwknSMS5m_7qM5tU5CxTdnpL5Ylae3fa6KhWaHM-301eXktddK9xD6VuoJXbK6gP0Xrohg2yluDb0kYbYmUY0joGDjRLpG8yxStaQ?key=XYBq4a5_K7w37fYNYXAoaWFB) |
| :----------------------------------------------------------: | :----------------------------------------------------------: |
|                         *Undirected*                         |                       *Adjacency List*                       |

For example, in the above figure, the vertices adjacent to vertex $4$ are $1$, $2$, and $3$ because all of these indices exist in $L(4)$. Alternatively, we can see that vertex $4$ is adjacent to only vertices $1$, $2$, and $3$ because $4$ appears in $L(1)$, $L(2)$, and $L(3)$ and no others.

For a directed graph, a minimal adjacency list can represent the directed edges by storing the terminal vertex identifiers in each vertex list.

| <img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXdtTNC0Fr1_ITIWN6ooQXALHtbgFQbzvU_A_Ldz3idlLRDrDjZRDap9InHBewOr2His3buqHZhBqZ6aF1vmxw70Ud2wfOuM14dh85NIODnrXcNVlqnNvZPV1pf39t_1ysMzuf8_aQ?key=XYBq4a5_K7w37fYNYXAoaWFB" alt="img" style="zoom:80%;" /> | ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXeuoolhTMHn-glitoAmPSFDC_200Oz8Nu-wClp9ksEPhmX9YhFsoUxnGHW2zTqP5BKJgliM9_Nj7ARsbSHgbnWaJuCwwBwahRh0Qi9mcBmefqiDfmkdK5LQSVhHeWPvN6lg_8tW?key=XYBq4a5_K7w37fYNYXAoaWFB) |
| :----------------------------------------------------------: | :----------------------------------------------------------: |
|                          *Directed*                          |                       *Adjacency List*                       |

For example, in the above figure, the vertices that terminate the outgoing edges from vertex $4$ are $1$ and $3$ because $1$ and $3$ are in $L(4)$.  The weakness of this approach is that it is difficult to determine which vertices lead to a specific vertex without searching all vertex lists; however, this could be resolved either by maintaining two adjacency lists, one representing incoming edges and the other representing outgoing edges, or by using a vertex structure in each node of the adjacency list with a property that discriminates between incoming and outgoing edges.

```java
class DirectedAdjacency {  
    int vertex_id;    // vertex index/identifier  
    boolean outgoing;  // if not outgoing, must be incoming
}
```

In order to maintain weights for weighted graphs, the vertex structure in each node of the adjacency list must include weights for each edge.

| <img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXcj2CgIKCeAOPTIULQZhUwlqLCBTOpchHe8-JqMzWDIfeh2RJE1T93PrG8TtmbE1O2HEncsRVQH2daqP0zY0mLzgtIrzyIF_FXlHSKEGdBfi1bHu2AyUcjIuaTYH9HGt_slm9ci?key=XYBq4a5_K7w37fYNYXAoaWFB" alt="img" style="zoom:80%;" /> | ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcx3nd35peK8mdsd757ZW-gfKPea0Bm725zbfGehotZfJphdcnxoOw9McYoOLvedT_I9DHcOgGr34_FBQrCf8k6AF4k6DMttwup0g5pHZnXnhPUiAOGpsxRZFCapPNSPvyc5xHb?key=XYBq4a5_K7w37fYNYXAoaWFB) |
| :----------------------------------------------------------: | :----------------------------------------------------------: |
|                   *Directed and Weighted*                    |                       *Adjacency List*                       |

```java
class WeightedAdjacency {  
    int vertex_id;    // vertex index/identifier  
    int weight;     // weight of the edge  
    ...         // other properties such as direction
}
```

An adjacency list is much more object oriented and may be a more comfortable representation for today’s programmers; however, adjacency queries are slower than the adjacency matrix since the matrix can service an adjacency query in constant time while the worst-case efficiency for an adjacency query in a adjacency list is linear time in the number of vertices because each list can have every vertex in it and search in a linked list is at best linear time complexity.  

The advantage of an adjacency list is that it can grow more efficiently than the adjacency matrix as insert for the adjacency list in the worst case is linear time in the number of vertices instead of the quadratic time for the adjacency matrix.  While linked lists can support fast append, there is likely a uniqueness constraint limiting the number of times a vertex can appear in a specific list to one, so a given list still needs to be searched for the existence of the edge before one can be inserted into a specific linked list.  

Overall, an adjacency list is a better choice if the graph is dynamically changing in terms of the number of vertices in the graph, but if a graph is well established and generally stable in the number of vertices, it is more efficient to use an adjacency matrix.

### Search

Like any other data structure, one of the key algorithms for a graph is search.  If search prioritizes exploring as far as possible and then backtracking when a dead end is reached, it represents a depth-first strategy.  Alternatively, if search instead prioritizes exploring all adjacent vertices before further exploration, it is a breadth-first strategy.  To prevent revisiting a vertex, search may require an additional “visited” property be maintained.

#### Visited

Unlike a tree, a graph does not have to be hierarchical and can be cyclic, so it is possible for a graph traversal to be caught in an infinite loop.  Adding a **visited property** to each vertex that indicates whether or not a vertex has already been visited will give the traversal process a means to determine whether or not it has explored a vertex already and a means to escape cyclic regions of a graph. This is the same idea as leaving breadcrumbs in a maze.

The visited property can be tracked using a property associated with each vertex object in a OOP modeled graph or using an array of boolean values if a more primitive graph structure is implemented.

| <img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXdXX6DsosCIpZSqRVaReqcFJEBiDLuFrZJRIFKQsmIRw_PwgnPUO7qa_o12ax0PLYv5-NmlwCgmFvFbIqwmtJJuKP-TKV0d0hrZ0OZv476y2TL4okWwRnNXcL2TnKt-WfPq535SRQ?key=XYBq4a5_K7w37fYNYXAoaWFB" alt="img" style="zoom: 70%;" /> | <img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXfJaUf4iBaTQiqsmMDpSyc4MXWmc5RUpe8zQsHQUn3RNjzl8RL61dJnS2ruKOJCZ2_pPR1_hIU57v8R1dF63QcDbfeUlAjufGs2RgIpCVSq2IbHL3VUXuRxDUDcOjvMBvZE0pXp?key=XYBq4a5_K7w37fYNYXAoaWFB" alt="img" style="zoom: 70%;" /> |
| :----------------------------------------------------------: | :----------------------------------------------------------: |
|      Start search at vertex 0 with vertex 2 as adjacent      | Mark 0 as visited, explore the adjacent vertex 2, and determine any adjacent vertices, *i.e.* vertices 1 and 4 |

Because there are a variety of choices at a given vertex, determining which node to visit next is subject to a search policy.  There are two general search policies as examined in trees: Depth-First Search and Breadth-First Search. 

#### Depth-First Search (DFS)

**Depth-First Search (DFS)** in graphs is the same model as Depth-First Traversal used in Trees. In Depth-First Search, the search algorithm prioritizes exploration of all of the paths from one adjacent vertex before exploring additional paths from the current vertex.

| <img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXe1YYWVZ2OTTDHI6A6uWTbIYIi1gPNuSKJspohjXsu4bYxqG9j5UaRnfPDrjr79NdRl8D0TwhsmuxlA1SGQ8aH49v57r_k_1U-6TVffIfswFyii56pn_0xJ8NulVBt5wAxZS30i?key=XYBq4a5_K7w37fYNYXAoaWFB" alt="img" style="zoom:70%;" /> | <img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXecU0u6FcYuD0k8Z1uZ40h0gITG2yqj4OvoHS3B5yxQAYaReLT2SjqCW9N8_-oFDehiXW6beEwpwP9cqbvekYzNvxYHduFJI-0Fyn50HoeF26ez-YN4M4yik6dP4_7tU9fQhNOH?key=XYBq4a5_K7w37fYNYXAoaWFB" alt="img" style="zoom:70%;" /> |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| For DFS, once vertex 2 is visited, either vertex 4 or vertex 1 will be explored next. Suppose vertex 4 is selected. At vertex 4, DFS again would choose one of the adjacent vertices and continue exploration there. | Suppose vertex 3 is selected. This will ultimately lead to vertex 1 being explored leading to a cycle back to vertex 0 (or dead-end); however, if the search value was not found, DFS would backtrack to explore unexplored adjacent vertices of vertex 3, then vertex 4, then vertex 2, and then vertex 0 |

#### Breadth-First Search (BFS)

**Breadth-First Search (BFS)** in graphs is also the same model as Breadth-First Search traversal used in Trees. In Breadth-First Search, the search algorithm will prioritize exploration of all vertices adjacent to the current vertex before making a decision on which vertex to visit next.

| <img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXdpRxQMGNeVUR-2aVsWi5D3PCI6t0ARM20-Nq3ARxfU3rSRKA6d_rgHpNbROws0VNGkd8U0hkx_b2WR5qcJHu_5F3eLtkFup61N9zhW6uWBOxVGdlItQehaIdtgneqUqzfUSw8P?key=XYBq4a5_K7w37fYNYXAoaWFB" alt="img" style="zoom:70%;" /> | <img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXezMDdX6iPIMBr1wDGxiTzlMXfIwK3G1jv0DaOQdrsno55As6y5QKhE0Aw8Bc--tQUyZlL5q-taw5YzljiI5oexYhHycg6_PxMDiFy5Cd7RJN942hmB7qQRllbBhm-5dwv1V-CuNg?key=XYBq4a5_K7w37fYNYXAoaWFB" alt="img" style="zoom:70%;" /> |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| For BFS, once vertex 2 is visited, both vertex 1 and vertex 4 will be explored next; however, it can only explore one at a time. Suppose vertex 1 is selected. | Continuing the scenario to the left, BFS will then explore vertex 4 after exploring vertex 1 because both vertex 1 and 4 are adjacent to vertex 2. |

### Shortest Path

A naive DFS or BFS will ultimately find a search value in the graph; however, the path taken to find the vertex does not necessarily reflect an optimal path especially when exploring a weighted graph. The optimal path is the path with the minimum total weight or shortest path through the graph which raises the question of how to compute this shortest path. 

In a tree, each vertex is connected to the root by only one path, but for a more generalized graph, the number of potential paths between vertices $v_{src}$ and $v_{dest}$ may be quantified by a permutation that is dependent on the number of vertices in the graph.  Recall from the earlier discussion of permutations, that this implies that the number of paths in a graph is generally approximated as a factorial making computation of all paths through the graph potentially computationally intensive. 

In other words, the naive approach of DFS or BFS is unlikely to produce an optimal path and a brute force approach has factorial time complexity in the worst case.

The shortest path problem is generally expressed as the following: given a graph $G(V,E)$ where $V$ is the set of vertices in $G$ and $E$ is the set of edges in $G$, compute the shortest path between vertices $v_{src}$ and $v_{dest}$ where $v_{src}$ and $v_{dest}$ are members of $V$ and the shortest path is the path with the minimal cost among all paths from $v_{src}$ to $v_{dest}$.

The Dutch computer scientist Edsger Dijkstra [1930-2002] defined an algorithm we know today as Dijkstra’s Algorithm that solves the shortest path problem for any graph.

#### Dijkstra’s Algorithm

![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcGF1K4WLOSTbFKd9Ud-jQ1xhHsdojJadslDWBjmvrUYlEvh2up3ig8PkKoo8oMvbku3RpH314V4yXAkXQjjHZ5kiRer7vkWNvps5uWme4KL9OHCaF5WH7r78ptrpeix7xv66Nm?key=XYBq4a5_K7w37fYNYXAoaWFB)

Dijkstra’s algorithm uses two arrays the same size as $V$ to compute distance and path association: $d(i)$ and $p(i)$.  $d(i)$ represents the minimum distance to the $i$-th vertex.  $p(i)$ represents the previous vertex in the shortest path leading to the $i$-th vertex. The distance, $d$, to a vertex is recomputed whenever a neighboring vertex is visited and entries of $d(i)$ and $p(i)$ are updated when $d<d(i)$.

Let $U$ represent the set of unvisited vertices. Marking a vertex as visited removes that vertex from the set $U$. When $U$ is empty, Dijkstra’s is complete and the path information can be reconstructed from $p(i)$.  In other words, the shortest path can be reconstructed by starting at the destination vertex and referring to its previous node in $p(i)$ which leads to that nodes previous node, etc. leading back to the initial node: 
$$
v_{dest} \rightarrow p(v_{dest}) \rightarrow p(p(v_{dest})) \rightarrow ... \rightarrow p(v_{src}) : p(v_{src}) =\emptyset
$$
If in the process of recreating this path a null, $\emptyset$, is encountered and it is not in the initial node’s index, there does not exist a path from $v_{src}$ to $v_{dest}$.

Let us assume function $w(i,j)$ returns the weight of the edge between $v_i$ and $v_j$

In high level terms, Dijkstra’s Algorithm uses the following steps:

1. Mark the distance to the source vertex, $v_{src}$, with a current distance of 0, $d(v_{src})=0$, and the rest with infinity, $d(i)=\infty$ : $i \neq v_{src}$.  Mark all node’s previous as null, $p(i)=\emptyset$.  Mark all nodes as unvisited, adding them to the set $U$.
2. Set the non-visited vertex with the smallest current distance as the current vertex $v_{i}$.
3. For each neighbor, $v_j$, of the current vertex in the set of neighbors, $N$: 

   3.1 Add the distance of the current vertex with the weight of the edge between the current vertex and the current neighbor, $d(i)+w(i,j)$. 

   3.2 If this distance is smaller than the current distance to the current neighbor, $d(j) > d(i)+w(i,j)$: 

   ​	3.2.1 Set the new current distance to the neighboring vertex $v_j$ equal to the sum of the distance to $v_i$ and the weight of the edge between $v_i$ and $v_j$, $d(j)=d(i)+w(i,j)$.

   ​	3.2.2 Update the previous vertex of the neighboring vertex to the current vertex, $p(j)=i$.
4. Mark the current vertex $v_i$ as visited removing $v_i$ from the set $U$.
5. Go to step 2 if there are any unvisited vertices.



| ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcGF1K4WLOSTbFKd9Ud-jQ1xhHsdojJadslDWBjmvrUYlEvh2up3ig8PkKoo8oMvbku3RpH314V4yXAkXQjjHZ5kiRer7vkWNvps5uWme4KL9OHCaF5WH7r78ptrpeix7xv66Nm?key=XYBq4a5_K7w37fYNYXAoaWFB) | $v_{src} = 0$<br />$v_{dest} = 5$<br/>$v_{i}=v_{src}$<br/>$U=\{0,1,2,3,4,5\}$<br/>$d(i) = [0,\infty,\infty,\infty,\infty,\infty]$<br/>$p(i) = [\emptyset,\emptyset,\emptyset,\emptyset,\emptyset,\emptyset]$<br /> |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfJ9UHszMTgo8nNsgSa6wuSInqLXSx4P0Hl_1BqGQQumAzjWzGHai_rq4WlWhxajzYLv1AwrIKwzdGxoo-Et5OLlWv8ZFOFkq-DTs-5O-vnxyugI3kS_Kpqo-5y4lfrdFywzz5ZJg?key=XYBq4a5_K7w37fYNYXAoaWFB) | $v_{src} = 0$<br />$v_{dest} = 5$<br/>$v_{i}=0$<br/>$N=\{1,2,3\}$<br/>$U=\{0,1,2,3,4,5\}$<br/>$d(i) = [0,8,12,3,\infty,\infty]$<br/>$p(i) = [\emptyset,0,0,0,\emptyset,\emptyset]$<br /> |
| ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcsx5WnE6SSvijK9xVkUVVP2wNY-ZQ5BJUzbbvC3oJlMy-Q5hTJ7BmN1i_tLpP4r_hr4qNqeHQZArXVPDeUYf_tTg_UEJlJVupJ7Z8mk_QZ9G5KMoB_ZaXWi2rusggB7H6-NAA06w?key=XYBq4a5_K7w37fYNYXAoaWFB) | $v_{src} = 0$<br />$v_{dest} = 5$<br/>$v_{i}=3$<br/>$N=\{0,2,5\}$<br/>$U=\{1,2,3,4,5\}$<br/>$d(i) = [0,8,7,3,\infty,31]$<br/>$p(i) = [\emptyset,0,3,0,\emptyset,3]$<br /> |
| ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcvKN0RFSAD_h4N2sEzjxJQLF5hC4SqG_hMpErnEFEdHrsQXkX_u8rDlz9j1wkiMm6BqG-evlTOYXLJL3NG63HeYX3FI0_889SxkPxe6rfvJkTm0SjEa9i2k5p3IICL3t-7_sBk?key=XYBq4a5_K7w37fYNYXAoaWFB) | $v_{src} = 0$<br />$v_{dest} = 5$<br/>$v_{i}=2$<br/>$N=\{0,1,3,4\}$<br/>$U=\{1,2,4,5\}$<br/>$d(i) = [0,8,7,3,17,31]$<br/>$p(i) = [\emptyset,0,3,0,2,3]$<br /> |
| ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXf4yPlG9IWz5-L_TAeBbm2hGOj8fWAvc0NgbSSaZ1SXBHCJnsfpnqa61_HtdqkU8tYd6D-AALaQTfONFaTywoT-zU283j0DPXIT57TxvRnmQxrEZQebnDuaNuU58rZZJ5O4ecZ0UQ?key=XYBq4a5_K7w37fYNYXAoaWFB) | $v_{src} = 0$<br />$v_{dest} = 5$<br/>$v_{i}=1$<br/>$N=\{0,2,4\}$<br/>$U=\{1,4,5\}$<br/>$d(i) = [0,8,7,3,16,31]$<br/>$p(i) = [\emptyset,0,3,0,1,3]$<br /> |
| ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXc5Tcwcf1eMZ-c7_HCZmhtkbkQEU2AdNjTeUl71Bwf-49tNxcAbGU2SyUMIR0v_BDa2gVZZ6HKgQB6gFooLgZVcjNIZoJcbz15txIG22UxPzK-cLGBJ8rJf1o7ztnequ2aiSPhDTg?key=XYBq4a5_K7w37fYNYXAoaWFB) | $v_{src} = 0$<br />$v_{dest} = 5$<br/>$v_{i}=4$<br/>$N=\{1,2,5\}$<br/>$U=\{4,5\}$<br/>$d(i) = [0,8,7,3,16,24]$<br/>$p(i) = [\emptyset,0,3,0,1,4]$<br /> |
| ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcNC0Rcq5ScppXvZHGNxJEqalB2DYp2zyf3SvtkN1Pit7F4tdDgK5-90kzjKdqSVUDFT0fLkRAgaDNPvOkHtXtXo2wIiSLtEk0zOUN_cDEHrLu5XxKGn2KMuOlWPNLhmQaZiDyeVA?key=XYBq4a5_K7w37fYNYXAoaWFB) | $v_{src} = 0$<br />$v_{dest} = 5$<br/>$v_{i}=5$<br/>$N=\{4,3\}$<br/>$U=\{5\}$<br/>$d(i) = [0,8,7,3,16,24]$<br/>$p(i) = [\emptyset,0,3,0,1,4]$<br /> |
| ![img](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfMzlqLUim0h3mhKGi9VVe6-iHp4puMSTkdWbP0QdvRfU0650erzv_H1_twoqUzk5RGz-kEo78i-ltk1RmtFXKLK4PhuYSoOAS_5on3RJKTGcB0VQcnzLSMEs0yxxCDsuMRdXPlCQ?key=XYBq4a5_K7w37fYNYXAoaWFB) | $v_{src} = 0$<br />$v_{dest} = 5$<br/>$U=\{\}$<br/>$d(i) = [0,8,7,3,16,24]$<br/>$p(i) = [\emptyset,0,3,0,1,4]$<br/>$shortestpath = v_{dest} → p(v_{dest}) → p(p(v_{dest}))→ ... → \emptyset$<br/>$shortestpath = 5 → 4 → 1 → 0 → \emptyset$<br /> |



# 14 - Advanced Topics

A common theme among previous topics is that we can often improve time complexity if we are able to trade more memory than is optimal for more computational efficiency.  The specifics of these strategies vary with the specifics of a data structure's or an algorithm's implementation, but some specific examples are doubling the size of an array when we increase its size to accommodate future appends and storing the answers to Fibonacci as each term is computed.  Here are some potential strategies to optimize time complexity. 

## Amortized Time Complexity

To *amortize* something is "to spread a cost over time" and is a basic principle of accounting.  It's root, *mort-*, is from the latin *mortis* meaning "death" and can be found in words like *mortuary* (processing and storage of the dead), *mortal* (between life and death), and *mortgage* (a lifetime contract).  While the root is more strictly associated with death, it can also more generally be interpreted as meaning lifetime so to amortize means to consider a cost over the lifetime of the object rather than solely to consider the cost at the time it is incurred.

This concept of amortization comes from making large capital investments.  For large investments like buildings and equipment, an initial cost may be extremely large; however, if the investment will not need further large investments over a long time, any annual maintenance costs are relatively small, and is functionally critical to a valuable system, then while the cost of the investment is sunk at a single time, the overall cost can be instead considered to be spread out over the lifetime of the investment up until it is replaced.  For example, a company may need a factory to generate its product and while the cost of the factory is a massive initial investment, it will "pay for itself" over time because the factory will continue to produce products for years and years without the need for another massive investment.  It will require additional maintenance and occasional significant repair as well as resource inputs but if the business plan is sound the factory may produce product over time that eventually will cover all total lifetime costs including initial investment, interests, and maintenance as well as producing profits.  Once again, we can look to this other discipline and set of concepts and leverage the same principle with our data structures to improve time complexity.

In our domain, an array can be a costly investment in terms of computation time if it is adhering to any policy that expects the array to dynamically grow.  We have to be very considerate about how we grow an array because every time the array needs to be increased in size, we incur an $O(n)$ cost.  We can think about the array in the same way as our factory above where the array is an investment with a large computational cost for increasing its size.  We have established that the most basic strategy to appending to a full array with a dynamic growth policy is the allocate a new array with one additional space of capacity at a cost of $O(?)$, copy all elements from the old array into the new array at $O(n)$, and assign the element at the largest index in the new array to the element to insert at $O(1)$ for a total of $O(n)$ assuming $O(?) < O(n)$.  This means that growing the array by one element each time is linear time complexity in its best, average, and worst cases.  While we cannot prevent the worst case from arising, if can we delay the allocation we might amortize that linear time complexity cost for the array allocation over multiple append calls enabling the program to make a number of calls to a constant time append with an highly infrequent call to a linear time append.  This seems like a winning idea, but there is an open question about how much space should we allocate.   

From a space perspective, we have a lot of memory in a modern system, so why not trade some of space for improved time efficiency.  However, we don't want to aggressively reserve space we are unlikely to need as we generally need to keep memory free and available for other usage so there is some balance we need to find between the frequency of the allocation and the size of the space reserved.  Given that, it is reasonable to assume that if a set is growing and we need to store $n$ elements, it is likely that we will need to store $n$ more elements as the process continues.  In other words, when appending a new element to the array requires increasing the size of the array, instead of allocating an array of size $n+1$, we allocate an array of size $2n$.  Allocating the new array will still cost $O(n)$ because we will need to traverse and copy $n$ elements from the source array; however, this will also buy at least $n$ further append operations at a cost of $O(1)$ before incurring another $O(n)$ allocation event.  This means that when using the doubling strategy to grow an array in response to an append operation, the array's worst case time complexity is linear, $O(n)$, but its amortized time complexity (time complexity over time) is constant time, $O(1)$ which is also its average time complexity.

## Dynamic Programming

Dynamic Programming is a programming technique where one or more solutions to a previous problem act as input to solve subsequent problems.  It is a self-referential technique and therefore naturally fits with recursive implementations.

The optimization behind dynamic programming is not a surprise.  Just as with other strategies, we are generally exchanging space (store previous solutions) for time (to compute the $n+1$ solution).  The key is to store any solutions after they are computed in a structure.  By storing the computed solutions in a structure with fast retrieval, the solutions become available as input into the algorithm and the data from our stored solutions can be used to improve the efficiency of computing the next solution by reusing the previously computed value instead of recomputing it.

Because it is built on both inductive principles and recursion, it can be difficult to initially conceive.  We will look back at two problems, Fibonacci Sequence and the Manhattan Problem, which can easily be converted into dynamic programming problems.  By using dynamic programming, we will reduce their time complexities from an intractable non-polynomial time to a very reasonable polynomial time.

### Fibonacci

From Chapter 4, recall the Fibonacci Sequence:
$$
f(x)=\begin{cases}       0 & x = 0 \\      1 & x = 1 \\      f(x-1) + f(x-2) & x > 1    \end{cases}
$$
We found that the above can be implemented using the following pseudocode: 

```pseudocode
fibonacci(x) → integer >= 0 where x is an integer and x is >= 0 :
	if x = 0 : 
		return 0
    if x = 1 : 
		return 1

	return fibonacci(x-1) + fibonacci(x-2)
```

However, this implementation has exponential $O(2^{n})$ time complexity and linear $O(n)$ space complexity.  The time complexity arises because we make two subsequent recursive calls to this function for every non-base case call to the function.  The space complexity arises because we generate a function call tree on the stack to solve the problem and the maximum depth of the tree is $n$ where $n$ is literally the input value we are calling $x$ in the examples above.

While we know there is an iterative approach, consider if we can leverage recursive principles to improve the algorithm without using recursion itself.  In other words, can the recursive function be rewritten so that it solves the problem without calling itself.  You might ask how is it then recursive if it does not call itself.  The twist is that we will sill use the recursive formula but we will store the solutions as we calculate them.  The conventional recursive algorithm uses $O(n)$ space anyway, so if our algorithm uses an array with equivalent space, it is no more resource demanding than the conventional algorithm.   

Consider the following implementation of Fibonacci:

```pseudocode
fibonacci(x) :
	int[] A = new int[x+1];
	A[0] = 0;
	A[1] = 1;
	for(int i = 2; i <= x; i++) {
		A[i] = A[i-1] + A[i-2]    // The dynamic programming step
	} 
	return A[x]
```

In this version, the solutions are stored in an array.  This array is initialized with the base case(s) and then the program iterates on the dynamic programming problem until the solution is calculated.  The solution is stored in the last element of the array and this element is returned.   

The arguments that the time complexity of this algorithm is no better than the original iterative technique and the original iterative technique uses constant space suggest that this algorithm has no place; however, if you needed to calculate an entire Fibonacci sequence up to $x$, this algorithm could do so with simple changes at no additional computational cost, so not only does this algorithm solve for a single Fibonacci number but it is also able to compute (and could return) the entire Fibonacci sequence up to the input value. 

### Manhattan

Recall the Manhattan Problem from Chapter 4:

<img src="/home/jrt/gwu/course/cs1112/assets/manhattan.png" style="zoom:30%;" />

We arrived at the following recursive implementation:

```pseudocode
manhattan(row, col) → paths from this row and col :
	if row = 0  :
		return 1
    if col = 0  :
    	return 1
    	
    count = manhattan( row - 1, col )
    count += manhattan( row, col - 1 )
    return count 
```

While we did not perform a rigorous time complexity analysis, we were able to approximate that it is at best exponential, $O(2^{n})$, because it has the same basic structure as the Fibonacci recursive implementation; however, this problem is actually worse than an exponential because it is a combinatoric,  proof of which is left for another course.  Regardless, the algorithm is intractable for large inputs in its current form, so can we apply dynamic programming to the problem and solve it more efficiently and the answer is yes.  

Like many optimization strategies, we will exchange a portion of free space for faster processing time.  In reality, the original Manhattan algorithm still used memory to hold intermediate calculations, however, it did so on stack so the spatial complexity was not immediately apparent.  This algorithm will still cost more in terms of memory than the original Manhattan algorithm, but this algorithm will use the space to leverage the recursive properties of the problem without having to use recursion itself and will run with a significantly more efficient time complexity than the algorithm above.   

We will use a multidimensional array to hold the intermediate solutions.  This array must have the same dimensionality as the grid above.  Note that there are four streets in the vertical dimension and there are six streets in the horizontal dimension.  The cells of the array will contain the calculated solution for the number of paths from the intersection the cell maps to on the grid.  In Java, conveniently every value in an integer array will initialize to zero, so the initial state of the array is benign and it is ready to work with once the array is allocated.

<img src="/home/jrt/gwu-new/course/cs1112/assets/manhattan_dp_setup.png" style="zoom:20%;" />

The base condition information needs to encoded into the array in the second step.  Here we assign any cell on the zero row or the zero column a value of 1.  This reflects that when the right edge is reached or the bottom edge is reached, there will be only one path to follow to the solution.  Note that we will ignore the value in cell [0,0] hence the reason it remains set to the value 0.

<img src="/home/jrt/gwu-new/course/cs1112/assets/manhattan_dp_basecases.png" style="zoom:20%;" />

Consider the implication of this code from the above implementation:

```java
	count = manhattan( row - 1, col )
    count += manhattan( row, col - 1 )
```

The code says the solution to $A[i,j]$  where $A$ is the multidimensional solution array is:

$A[i,j] = A[i-1,j]+A[i,j-1]$

or in other words, the solution to the current problem is equal to the sum of the solution to the problem from the same column/previous row and the solution to the problem from the same row/previous column.  

| <img src="/home/jrt/gwu-new/course/cs1112/assets/manhattan_dp_process.png" style="zoom:20%;" /> | <img src="/home/jrt/gwu-new/course/cs1112/assets/manhattan_dp_process2.png" style="zoom:20%;" /> |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| A[1,1] is equal to the sum of A[1,0] + A[0,1]                |                                                              |

Once the base cases have been computed, we can compute an entire column quickly by iterating over the column and summing according to the above formula.

<img src="/home/jrt/gwu-new/course/cs1112/assets/manhattan_dp_1st row.png" style="zoom:20%;" />

This allows us to create a nested loop that will iterate over every cell of the array and compute the solution.

<img src="/home/jrt/gwu-new/course/cs1112/assets/manhattan_dp_solution.png" style="zoom:20%;" />

Now our algorithm is capable of computing, retaining, and even returning the entire solution.  The recursive algorithm illustrated above was non-polynomial with at best an exponential time complexity.  This implementation is simply a nested `for` loop; however, we need to consider the dimensionality of the problem with respect to the input so that we summarize the efficiency correctly.

Because  a nested `for` loop is involved, it is tempting to just claim quadratic time complexity and call it a day; however, this would be incorrect.  The input measure can be reduced from two dimensions to one dimension if we realize that the size of the input is the number of intersections in the grid which has a clear, easily expressible relationship with the number of rows and the number of columns:

​	$intersections = width \times height$

Therefore our analysis variable is just $n$ where $n$ is the number of intersections, so the time complexity of the dynamic programming approach is linear.

```java
public class ManhattanDP {

    static int[][] A;

    public static void main(String[] argv) {
        int height = 5; 
        int width = 3;

        A = new int[height+1][width+1];

        // initialize base cases along edges
        for(int i = 1; i <= height; i++) {
            A[i][0] = 1;
        }
        for(int i = 1; i <= width; i++) {
            A[0][i] = 1;
        }

        // dynamic progrmming approach notes that the total number of
        // paths at any given intersection is the sum of the downward 
        // paths and the rightward paths
        for(int i = 1; i <= height; i++) {
            for(int j = 1; j <= width; j++) {
                A[i][j] = A[i-1][j] + A[i][j-1];
            }
        }

        String msg = "For a " + width + " x " + height + " manhattan grid,";
        msg += " there are " + A[height][width] + " shortest paths.";

        System.out.println(msg);
    }
}
```







## n-ary Tree

Point Cloud, Quadtree/Octree

## Priority Queue

Queue of queues or more accurately an array of queues.  Each queue has a **priority** property, typically an int in range of [0,MAX_PRIORITY].

# References

[Decker 1989] Rick Decker, "Data Structures", Prentice-Hall, 1989

[IBM Power4] https://www.ibm.com/history/power

[Moore 1965] - [Moore, Gordon E.](https://en.wikipedia.org/wiki/Gordon_Moore), ["Cramming more components onto integrated circuits"](http://cva.stanford.edu/classes/cs99s/papers/moore-crammingmorecomponents.pdf), 1965

[NovodeX AG] https://ethz.ch/en/industry/entrepreneurship/explore-startup-portraits-and-success-stories/exits/novodex.html







# Notes

\# of moves = $\sum \limits_{i=1}^N \frac{1}{2^{-i}} $