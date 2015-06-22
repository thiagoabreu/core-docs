Overview of different editions of .NET
======================================

With the advent of .NET Core and .NET Native, the layout of the .NET ecosystem has changed significantly. Where before there was a (somewhat) simple mapping between platforms and .NET Framework versions, today we have a lot of 

.NET Framework
--------------
The tried and true workhorse of the past 10+ years, the full .NET framework is still around, of course, and has been recently updated to version 4.6. There are many enhancements to the CLR (the runtime) and the BCL (the class library) that comes with this release for the consumers presented in the diagram above, such as the .NET Compiler Platform, new language innovations etc.

This edition of the .NET Framework is not cross-platform and you can run it only on Windows. Most of the consumers of this particular edition of the .NET Framework should be already know, if in name only. Windows Presentation Foundation or WPF is a framework for building desktop applications using specific technologies to make them compelling and rich. Windows Forms is already known as the bulwark of the LOB desktop applications from the early day of the .NET Framework. Of course, ASP.NET is Microsoft's main web stack, which is getting a major overhaul in the 5 release timeframe.

.NET Core
---------
.NET Core is a cloud-optimized, pay-as-you-go, cross-platform port of the .NET Framework. The roadmap currently in place covers support for three main operating systems, Linux, Windows and OS X. The community porters have made it work on FreeBSD as well. It is freely available on `GitHub <https://www.github.com/dotnet/coreclr>`_ and it is very easy to get for the supported systems and get going.

Today, development of modern services and applications is very different from what was available a couple of years ago. Cloud services, application containers with Docker, strong client-side requirements and much more all change the way in which a modern developer may get about doing their everyday tasks. Many of these new developments mean that the developer wants to have a fully packaged environment that can be deployed in isolation, without affecting anything else, not to mention a way to include only those things that the application in question actually needs. 

This is precisely why .NET Core came into the world. First, it is a completely componentized framework, meaning that everything is available as a package that you can opt-in. This includes the entire list of libraries that you would use in your application; you pull them in via packages and ship them as part of your application, and then update them as you see fit, without messing around with the centrally installated version. This makes it that much easier to deploy your apps in the cloud, Docker images or even hosting the runtime yourself if you're so inclined.

.NET Native
-----------
Before we can explain what .NET Native is all about, we need to first cover some (very basic) ground on how .NET runtime currently executes code. The way .NET framework normally works is by JIT-ing IL (Intermediate Language) code. This happens at runtime. For the new generation of mobile and tablet applications, however, there are many scenarios where this is not really optimal, and where the developer would like to get to the actual code that is being run, without all of the JIT-ing and other things.

Enter .NET Native. It is a toolchain which is focused on compiling the IL code into native code. It is also known as AOT, Ahead of Time compiler, to differentiate between it and the Just in Time compiler, or JIT.

Supported operating systems
---------------------------

The table below lists out the supported operating systems for each of the editions mentioned in this document.

.. note:: 
  Please note that "supported operating system" refers to those operating systems that are aligned with current .NET Platform project priorities and goals. You can see the project priorites on `GitHub <https://github.com/dotnet/coreclr/blob/master/Documentation/project-docs/project-priorities.md>`_.

+----------------+---------+-------+------+---------+
| Runtime        | Windows | Linux | OS X | Other   |
+================+=========+=======+======+=========+
| .NET Framework |    Y    |   N   |   N  |   N     |
+----------------+---------+-------+------+---------+
| .NET Core      |    Y    |   Y   |   Y  | FreeBSD |  
+----------------+---------+-------+------+---------+
| .NET Native    |    Y    |   N   |   N  |   N     |
+----------------+---------+-------+------+---------+



