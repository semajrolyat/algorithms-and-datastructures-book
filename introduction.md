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


