Overview of .NET implementations
================================

.NET Platform is, at its very core, a set of standards that can be implemented. There are 
various implementations, some coming from Microsoft, some coming from other companies and 
groups. This document will outline the current state of the .NET ecosystem and its various 
implementations, so you can get a good "lay of the land". 

.NET Framework
--------------

The .NET Framework is the premier implemetentation of the .NET Platform available for 
Windows server and client developers. It is a very powerful, very mature framework, with 
a huge class library (known as the **Base Class Library** or BCL for short) that supports 
a wide variety of applications and solutions on Windows. 

The additional stacks built on top the .NET Framework allow developers to build software 
from CLI tools to rich web applications. 

**Windows Forms** and **Windows Presentation Foundation** are two stacks that allow developers 
to build desktop applications for Windows operating system. The former is focused more on LOB 
apps, while the latter allows developers great control over the layout and provides opportunities
to create really stunning user interfaces.

**ASP.NET** is Microsoft's main web platform that runs on .NET Framework (among other things). 

.NET Core
---------
.NET Core is a cloud-optimized, cross-platform implementation of the .NET Platform. The roadmap 
currently in place covers support for three main operating systems, Linux, Windows and OS X. We 
expect the wider community to tackle porting to other operating systems as well; for instance, 
`FreeBSD port <https://github.com/dotnet/coreclr/blob/master/Documentation/building/freebsd-instructions.md>`_ 
is currently in progress. 

There are several reasons why .NET Core came to be. 

**Cross-platform support** is increasingly becoming a number one ask from the wider developer 
community. Simply put, new types of applications (such as mobile applications and modern web 
applications) have different requirements when it comes to the underlying platforms. Developers 
want to be able to pick and choose the platforms, especially on the cloud, for their solutions.

**Open source** is a natural extension to cross-platform support. In order to support as many 
platforms as possible, open source has so far proven as the best possible way to make sure 
that all of the various platforms out there are supported. 

**Better packaging story** of the entire runtime is also something that influenced the 
design of the runtime. We wanted to make sure that the entire runtime can be distributed 
as a set of pieces that developers can pick and choose from, rather than a single, 
monolithic platform. .NET Core is the first implementation of .NET Platform that will be 
distributed via `NuGet <http://www.nuget.org/>`_ package manager. 

**Better isolation and versioning** was one of the key influencers to create .NET Core. Today's 
trends in development practices lead to a very different set than what was available just 
a couple of years ago. Cloud services are posed to radically change the way developers build, 
test and run their solutions. Application containers like Docker are introducing new 
possibilities and opportunities when it comes to server (and services) consolidation. With 
this in mind, the .NET Core is targeting scenarios where the application, essentially, "takes" 
the runtime with it. This allows for per-app versioning scenario; the developer needs to worry 
only about the runtime (a set of packages, as seen in the previous paragraph) that her app 
is dependent on. 

With all of the above, the .NET Core represents a very generic, cross-platform and modern 
runtime that is capable of supporting multiple workloads, from cloud services, to desktop 
applications to CLI tools. 

.NET Native
-----------

.NET Native is not so much an "edition" of the .NET platform as it is a set of tools that 
allow developers to have different build outputs. The normal .NET compilation process takes 
the source code written in one of the .NET languages (such as C#, Visual Basic, F# etc.) and 
produces something called "Intermediate Language". IL is then picked up by the runtime, 
and Just-In-Time compiled at run-time to machine code. This is a very simplifed description, but 
it works for this scope; if you want to find out more, you can read through 
:doc:`<../concepts/managed-code>`. 

.NET Native is an additional step in this pipeline which takes the IL and compiles it 
**Ahead-of-Time** (AOT) to machine code, so that when the code is executed, there is 
only "native" code running. This means that the resulting binary is what the OS executes; 
there is no JIT-ing, no runtime compiling. This leads to better performance, as well as 
some security benefits. 

.NET Native is a key component in the new **Universal Windows Platform** (UWP) applications.

Supported operating systems
---------------------------

For .NET Framework and .NET Native, the only supported system at this time is Windows. For .NET Core, Windows, Linux and OS X are supported systems. 




