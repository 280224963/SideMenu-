SideMenu 
========== 

![logo](https://github.com/280224963/SideMenu-/blob/master/picture/logo.png)
-------------

## Abstract

Side menu is an important part in many programs. It provides directions to all functions of a software or webpage. Different styles of side menu can fit in different kinds of situations. And the design of a side menu should meet the requirements of users. This program is about a simple and versatile side menu control written in Swift which can be implemented in storyboard without a single line of code. This passage talks about the stakeholders, design view and other software architecture information of this side menu.


## Table of contents
- [Introduction](#introduction)
- [Stakeholders](#stakeholders)
- [Context view](#context-view)
- [Use case view](#use-case-view)
- [Logic view](#logic-view)
- [Development view](#development-view)
- [Evolution perspective](#evolution-perspective)
- [Technical Debt](#Technical-Debt)
- [Conclusion](#conclusion)
- [Reference](#reference)

## Introduction

#### 1.What is the SideMenu
SideMenu is an open source implementation of a sliding menu animation effect posted on Github. 
Developing an ios application often involves designing side menus. SideMenu is a simple and versatile side menu control written in Swift. 
There are numerous Side Menu control available on the Internet, this one is more likely be included in apple application. 
SideMenu is practically a frame that helps to switch from one scene to another scene by touching a button or sliding left or right.
After importing the SideMenu package, developers don't need to write a lot of custom code, just a simple interface call, you can achieve a vivid animation sliding effect. 
The SideMenu is based on Swift 4.2 and uses Xcode 10 and needs to run on iOS 10 or higher.

#### 2.History

![history](https://github.com/280224963/SideMenu-/blob/master/picture/history.png)

Figure 1.1: history of SideMenu.

#### 3.Preview Samples
| Slide Out | Slide In | Dissolve | Slide In + Out |
| --- | --- | --- | --- |
| ![](https://raw.githubusercontent.com/jonkykong/SideMenu/master/etc/SlideOut.gif) | ![](https://raw.githubusercontent.com/jonkykong/SideMenu/master/etc/SlideIn.gif) | ![](https://raw.githubusercontent.com/jonkykong/SideMenu/master/etc/Dissolve.gif) | ![](https://raw.githubusercontent.com/jonkykong/SideMenu/master/etc/InOut.gif) |

## StakeHolders
We will describe a number of different types of stakeholders exist as defined by Rozanski & Woods [1] and relate our views of the classes in relation to the SideMenu project. 
- Developers: Jon kent
- Test and integration staff: Jon kent and Github.
- Users：ios application developers
> The major user of SlideMenu is individual developers. Their concrete names are hard to find.
- Ultimate user: app users
  
    
      
 Stakeholders | Description
 ----|----
 Developer | Jon kent
 Test and integration staff | Jon kent and github
 User	| ios application developers
 Ultimate user |	app users
 competitors |	-
 
 Table 2.1: Stakeholders of the SideMenu project
 
 Contributor | Commits | LOC++ | LOC-- | Active during 
 ----|----|----|----|----
 Jon Kent | 339 | 12,402 | 7,004 | 2015-present
 Aron Geczy Gates | 13 | 208 | 130 | 2016-2017
 Soheil | 5 | 3,503 | 4,841 | 2016
 ... | | | |
 
 Table 2.2:Most active contributors in terms of number of commits

The stakeholders are visualized in Table1 and Table 2, their respective power and interest in the SideMenu project are shown in Figure 2.1.

![power_interest](https://github.com/280224963/SideMenu-/blob/master/picture/power_interest_pic.png)

Figure 2.1: Power-Interest grid for the stakeholders of SideMenu

In the stakeholder analysis, many different actors with different roles, power and interest have been analyzed and visualized in Figure 1. Since SideMenu is a personal developed control unit,The main stakeholder of SlideMenu is the developer Jon Kent who has the most power and interest in the platform. Since SideMenu is built upon Swift and Xcode, these programming languages can be seen as more powerful actors than other suppliers, having very little interest. The developers, testers and maintainers can be placed in the middle of the spectrum, all with some power and interest.


## Context view

Context View gives a bief explanation about the system. Usually, a context view describes the relationships, dependencies, and the interactions between the system and its environment. This view is relevant for the system's architecture and defines
the boundaries of the system and how it interacts with external entities across these boundaries. Besides, it will also show you on which system the app runs on.



![context_view](https://github.com/280224963/SideMenu-/blob/master/picture/context_view.png)

Figure 3.1: context view of SlideMenu

From the above figure, we can easily know about the eviroment.
SideMenu is mainly developed by Jon Kent and Sohei.B.Marvasti. 
This is licensed by MIT, so if you want to know something more about this you can go MIT to learn.
It is implemented by Swift. So if you want use SideMenu in your own app you have to run it on IOS X and above.
Xcode also needs to be 9. It use Cocospods and Carthage to help manage the dependency library. You can use git to learn the source code and chat with the developer. And it is mainly developed for personal users. It can be a good choice if you want SideMenu in your small app. This can also be a good learning resource for students

## Use case view

Use case diagrams showed below describe the system functions understood by the participants. The main elements are the use cases and participants. They help the development team understand the system's functional requirements in a visual way. And this program--SideMenu can be implemented in storyboard without a single line of code. First of all, if the app developer wants to use this side menu, the step is extremely simple. He will only need to install CocoaPods and Carthage and do some other easy options by creating a Navigation Controller for a side menu. The figure 4.1 showed below tells what an app developer can do. He can create views as he want. You first have to create a Root View Controller for the Navigation Controller (shown as a UITableViewController) and then you can set up any Triggered Segues you want in that view controller. Very importantly, add an UIButton or UIBarButton to a view controller that you want to display the menu from.

![use_case](https://github.com/280224963/SideMenu-/blob/master/picture/use_case1.png)

Figure 4.1 use case view of SlideMenu

As you can see from the figure 4.2, the SideMenuManager is the most important class in this program. Once the user press the corresponding button, the exactly view will be showed. For example, if the user want to slide in a new view, a viewController will be created and the sidemenuManager will do the corresponding respond to the viewController. The user can make a view presents and he can also make a view dismiss, so as long as the button is code for a function, the view controller connected to it will follow the procedure and make a view do the things it should do.

![use_case](https://github.com/280224963/SideMenu-/blob/master/picture/use_case2.png)

Figure 4.2: use case view of SlideMenu

## Logic view

Logical view is mainly the abstract structure of the whole system. It pays attention to the function of the system which is provided to the end user. It does not involve specific compilation, output or deployment. It is usually expressed in UML by class diagram, interaction diagram and sequence diagram. Figure 5.1 shows the class diagram of this program.
There are four main class in this program and an important protocol named UISideMenuNavigationControllerDelegate which is used To receive notifications when a menu is displayed from a view controller which is adhered to the UISideMenuNavigationControllerDelegate protocol: and send the notifications to UISideMenuNavigationController to give feedback.  
The SideMenuManager class is the class of an instance of sidemenu which defines the many attributes of a sidemenu, for example, the menuWidth, the present mode which has four modes—slide in, slide out, slideInOut and dissolve in, the six modes in push style which are defaultBehavior, popWhenPossible, preserve, preserveAndHideBackButton, replace and submenu.
UISideMenuNavigationController supports four customizations and properties: 

1.A SideMenuManager instance associated with this menu. Default is `SideMenuManager.default`.  This property cannot be changed after the menu has loaded.

2.Width of the menu when presented on screen, showing the existing view controller in the remaining space. Default is zero. When zero, `sideMenuManager.menuWidth` is used. This property cannot be changed while the isHidden property is false.

3.Whether the menu appears on the right or left side of the screen. Right is the default. This property cannot be changed after the menu has loaded.

4.Indicates if the menu is anywhere in the view hierarchy, even if covered by another view controller.  
![use_case](https://github.com/280224963/SideMenu-/blob/master/picture/logical_1.png)

Figure 5.1 class diagram

And the sequence diagram shows how this sidemenu works with the app. The user open the app while UISideMenuNavigationController create the menu, and there are several kinds of action, for example, slide in, slide out, dissolve, slide in+out which will be caught by UISideMenuNavigationControllerDelegate and finish the move. When the user press a button, the ControllerDelegate would receive the notification and make the corresponding response. For example, if the user slide in a menu then the function sideMenuWillAppear which will be followed by a appearance of a new menu and before that a hint: "SideMenu Appearing! (animated: \(animated))" will be showed somewhere. It works like that. And if setting the sideMenuDelegate property on UISideMenuNavigationController is optional. If your view controller adheres to the protocol then the methods will be called automatically.
![use_case](https://github.com/280224963/SideMenu-/blob/master/picture/logical_2.png)

Figure 5.2 sequence diagram


## Development view
### 6.1 Design Discipline
Sidemenu is an open-source Swift library. It is so small but useful when you need a sidemenu in your IOS project. It can be use without complex codes, which makes it easier to use, and you don’t need to study it for a long time. In addition, as it is an open-source library, we can change the effects easily.
#### Composition
Sidemenu is a small library that the key codes is the swift files in Pld/Classes. That makes it easy to read, and you can even change it by yourself just by reading a few codes, and it is important that it will not cause the errors in your project.
#### Stability
You can follow the README.md to install and use by code-less storyboard or customize in SideMenuManager, UISideMenuNavigationController and UISideMenuNavigationControllerDelegate. If you follow the guide, it will not cause any instability.
#### Interoperability
Anyone can install easily just to use cocoapods and carthage, and any IOS projects can use them by following the README.md, because of that it is just a small tool and it is flexible, so the interoperability is obvious.
#### Modifiable
The codes about the effects, the actions is modifiable, so you can customize what you want by modifying the codes
Developer Experience
It provides the developers with a simple way to add the sidemenu in their projects, and even without studying the source codes a lot.
#### Implementation
You have the way to implement it that it is a Code-less Storyboard Implementation. Set the Custom Class of the Navigation Controller to be UISideMenuNavigationController in the Identity Inspector. Set the Module to SideMenu (ignore this step if you've manually added SideMenu to your project). Create a Root View Controller for the Navigation Controller (shown as a UITableViewController below). Set up any Triggered Segues you want in that view controller. Then changing where to appear. In addition, you can DIY your own ways to modify it.
#### Optimized for Tooling
In order to make the points of interaction with the library highly visible, some commonly used APIs have verbose names, such as UISideMenuNavigation-Controller, UISideMenuNavigationControllerDelegate. That makes it easier to use the classes and the functions. More important, it is easier to search, and distinguish them so that the developer will not mix them up.


### 6.2 Source Code Structure
The figure shows the structure of the SideMenu:
![Code](https://github.com/280224963/SideMenu-/blob/master/picture/Code.png)

### Functionality
Main functions are designed in the Pod/classes and where you can change the effects is in the folder.
In SideMenuManager, you can customize the effects. Just type SideMenuManager.default.menu... and code completion will show you everything you can customize (for Objective-C, use SideMenuManager.defaultManager.menu...). Defaults values are shown below for reference.
In UISideMenuNavigationController, it supports the following customizations and properties: SideMenuManager instance associated with this menu. Width of the menu when presented on screen, showing the existing view controller in the remaining space. Whether the menu appears on the right or left side of the screen. Right is the default. Indicates if the menu is anywhere in the view hierarchy.
In UISideMenuNavigationControllerDelegate, To receive notifications when a menu is displayed from a view controller, have it adhere to the UISideMenuNavigationControllerDelegate protocol.
Example and ExampleTest folders are designed to show the sample effects.
Pods are something get from CocoaPods.
ect are the pictures to show the library.

### 6.3 Design Patterns
This section discusses some of the design patterns used in SideMenu.

#### Singleton Pattern
The singleton pattern that you can use the SideMenu, and only one object. So that makes it easier to use the SideMenu.

#### Least Knowledge Principle(Law Of Demeter)
That means the SideMenu object just affect itself, like the activity to show, the effects, ect. And you can change it needless to consider about others.

#### Extensibility
The SideMenu is easily to change, you can customize it by modifying the classes like UISideMenuNavigationController, SideMenuManager, UISideMenuNavigation-ControllerDelegate, etc.

#### Easy to understand
The premise of its reliability and modifiable ability is the comprehensibility of software. It is not only a clear and readable document, but also requires a simple and clear structure of the software itself. This largely depends on the designer's insight and creativity, as well as the thoroughness of the design object, of course, it also depends on the appropriate use of design tools and methods.

#### Single Responsibility Principle
The Single Responsibility Principle states that a class should only have a single responsibility. In SideMenu, SideMenuManager is designed just for the style of the menu, UISideMenu-NavigationController is for some global attributions. UISideMenuNavigation-ControllerDelegate is for the call-back about some events.

#### Open/Closed Principle
The Open/Closed Principle states that software entities should be open for extension, but
closed for modification. In SideMenu, we can use the SideMenu without codes, and the interface is so clearly that it is open for extension, and it is no use to modify the core codes.

### 6.4 Module Structure
![Module](https://github.com/280224963/SideMenu-/blob/master/picture/Module.png)

Figure 6.1: Module Structure of SlideMenu
...

## Evolution Perspective
The evolution perspective deals with concerns related to evolution during the lifetime of a system, it focuses on identifying the ability to be flexible in the face of inevitable change. As discussed by Rozanski and Woods, a flexible system should be able to deal with all possible types of changes that it may experience during its lifetime [1]. Therefore, the changes throughout the lifetime of the project are analyzed, and the mechanisms in place to provide flexibility are discussed. Although only few change occur in the SlideMenu, this is still closely relevant to it.

Thought out the years, SideMenu has evolved a lot. At this moment SideMenu has 28 releases, which started with release 2.0.7 in December 2015 and the latest release 5.0.3 in November 2018. However the real first a few release can't be found on the Github repository
anymore. This is probably because it was an alpha version and can not be put into use well. In order to understand the changes in the various releases, the release notes have been analyzed. These were found on the SlideMenu release page on Github.

SideMenu updates their current version number according to the semantic versioning convention. SlideMenu releases can be categorized into two main categories: major updates that symbolize a new backwards compatibility baseline, and new versions containing novel features and bug fixes.

The first type has occurred five times in the history of SlideMenu. The latter on the other hand, has an average frequency between 2-3 weeks.

![ep_release](https://github.com/280224963/SideMenu-/blob/master/picture/ep_release.png)

Figure 7.1: gives an overview of SideMenu and mentions the changes with the largest magnitude of change.


#### Gesture:
As a mobile app control, gesture support is crucial. Jon Kent's initial changes focused on improving the support and optimization of various gestures and fixing some bugs that were not noticeable.

#### Ui: 
Although SideMenu is only about the implementation of the effect, the specific ui design is defined by the user, but Jon Kent still allows for more optimized screen adaptation and some black border problems, making the use of SlideMenu easier.

#### Animation: 
This part of the optimization is mainly implemented by other developers on github in 2017. Most of the time, the original animation effect is still used. In the optimization, the developer fixed some logic bugs in the animation call, achieving smoother, higher quality animations.

#### Language: 
SideMenu is written in the swift language, and this part of the maintenance is basic maintenance. Whenever there is a new version of swift release developer upgrade to accommodate the new version of the swift language. Later upgrade also support for calling SlideMenu with Objective-C.

#### Use experience improvement：
Jon kent has put a lot of effort into making the use of SideMenu easier and more convenient, `SideMenuManager.default` serves as the primary instance as most projects will only need one menu across all screens. User can show a different SideMenu, such as from a modal view controller presented from a previous SideMenu, just by doing the following:
1. Declare a variable containing the custom `SideMenuManager` instance. If one wants it to define it globally and configure it in his app delegate if menus will be used on multiple screens.
``` swift
let customSideMenuManager = SideMenuManager()
```
2. Setup and display menus with custom instance the same as one would with the  `SideMenuManager.default` instance.
3. If using Storyboards, subclass the instance of `UISideMenuNavigationController` and set its `sideMenuManager` property to the custom instance. This must be done before `viewDidLoad` is called:
``` swift
class MySideMenuNavigationController: UISideMenuNavigationController {

    let customSideMenuManager = SideMenuManager()

    override func awakeFromNib() {
        super.awakeFromNib()

        sideMenuManager = customSideMenuManager
    }

}
```
Alternatively, users can set  `sideMenuManager` from the view controller that segues to their UISideMenuNavigationController:
``` swift
override func prepare(for segue: UIStoryboardSegue, sender: Any?) {
    if let sideMenuNavigationController = segue.destination as? UISideMenuNavigationController {
        sideMenuNavigationController.sideMenuManager = customSideMenuManager
    }
}
```

Nowadays, the most recent stable release version of SlideMenu (as of 11-6-2018) is version 5.0.7, and as a personal developer, it seems that Jon Kent hasn’t planned for the next version if no major bugs are found.


## Technical Debt

#### 1.Definition
Technical debt is a well-known concept that was introduced in 1992 by Ward Cunningham (founder of the wiki), who talked about this topic in a recent video. Since then, this topic has been discussed and studied countless times in blogs and articles. Martin Fowler gives a point of view through metaphor:

In this metaphor, we set up a technical debt through a temporary emergency, which is similar to economic debt. Just like economic debt, technical debt is also subject to interest. It exists in our future development. Because we choose temporary emergency measures, at some point, we will pay some form of extra cost. We can choose to continue to pay interest, or we can choose to repay the principal and reconcile the principal to get a better design. Although it paid off the principal on the spot, it allowed us to reduce interest payments in the future.

#### 2.Tools
We use Codacy to analyse the code.Codacy contains almost all the features you need. Such as free installation, support for multiple languages, only focus on new issues in the submitted version, enterprise-level security, notifications when new issues are discovered, security and performance checks, configuration files for all projects, cloud or presets Version, code coverage, thousands of rules, analysis of different branches, flexible customization, code repetition rate, agitator/complexity, neglecting irrelevant issues, keeping analysis results concise, estimating time to fix problems, project statistics, in GH/ Automatically annotate PR on BB/GL, document each issue, manage user roles and permissions, and set goals to help fix technical debt.

#### 3.Analysis
Use Codacy, we get the following figure. The result is shown below:

![result_1](https://github.com/280224963/SideMenu-/blob/master/picture/result2.png)

Figure 8.1: Result from Codacy

From the figure, the project certification is B. It analyses the project through 3 aspects. They are issues, complex Files and Duplicated code. Issues means the comparison of the number of the issues with the industry average. It gets 90% at this part. In this piece, SideMenu has basically reached the industrial level. Complex Files means a file is over 20. The percentage is about 13%.
From this data, we can easily know that only a little files are complex. Most of them is simple. Similarly, the project is also a simple project. Duplicated code means a file has at least 1 clone. 26% ， in my opinion， is a little high. The code is reused much. In some way, this phenomenon is not good for a project.

#### 4.Issues Breakdown
![result_2](https://github.com/280224963/SideMenu-/blob/master/picture/result1.png)

Figure 8.2: Result

In this aspect, the project is brokendown in 6 parts. 

###### Security
As the Internet penetrates into all walks of life, more and more application systems, websites, etc. are connected and accessed by humans through the Internet. How to ensure that the system and website will not cause security problems such as system crash and data leakage due to malicious attacks by hackers. The most fundamental means to solve this problem is to return to the code. Only the code written is safe and impeccable. Without any logic loopholes, all security issues can be eliminated. SideMenu's security catagory only gets 7. After all, SideMenu is only a framework. It does nothing with users's data or privacy. SideMenu also needs not to connect database. So in some way, security is not significant for SideMenu.

###### Error Prone
Using Error Prone to augment the compiler’s type analysis, you can catch more mistakes before they cost you time, or end up as bugs in production. Most of the issues have use error prone to avoid later error in usage. This guarantee less error to take place when user import SideMenu in their own project. This helps the project be stable.

###### Code Style
Although the code style is not as easy to fry as a technical circle, it is not as easy to stand as a programming language or editor, but there are always people who have a unified style to improve work efficiency. If code styles are different, it is not conducive to collaborative programming, the code is also chaotic. As for similar code style, this produce a certain constraint. Functional importance, code style and post-maintenance are also important. As we know, SideMenu can be seen as a private project, It is nearly implemented by one person. SideMenu's code style is not diverse.

###### Compatibility
Compatibility refers to the degree of coordination between hardware, software, or a combination of hardware and software. Since SideMenu is implemented in Swift. So unluckily, SideMenu is not for Antroid users. As for IOS user, this is a good choice. But at first, the iOS need to be X or above. You use Xcode to be the compiler and the version should be above 9. When all the requirements are satisfied, you can easily import SideMenu in your project. Obviously, SideMenu just as the figure shown, has good compatibility for IOS user who needs SideMenu.

###### Unused Code
Unused Code, we can regard as dead code. At first, when the result gives out, it shows like the SideMenu has lots of unused code. But when I click "show details", I found that Codacy think 'import' and dependency as unused code. Maybe that is the shortcome of the tools I use. Review the details except code mentioned above , unused code reduced 70%. In code quality, SideMeNu doen't have many unused code. In this aspect, its code quality is good. 

###### Performance
There are only 2 issues about performance. In my opinion, SideMenu is a private project, so it There will be no special personnel to maintain and update it, and as a sidebar menu, there will be no relevant security detection or protection. Compared to other industrial projects, the sidebar menu is very simple, its role is only limited to the sliding in and out of the scene, so it is not significant in terms of performance. But through the examples provided by the author, I have to admit that SideMenu is very convenient....

## Conclusion

Even though SideMenu is just a small frame, it still has a lot of things to learn with it. SideMenu is a widely used framework. Even all the apps now, have relation with the framework. And though the author just gives out a simple version. I think it has a long way to develop better.

In this chapter, we have analysed the architecture of SideMenu from different viewpoints and perspectives. We learn a lot from the progress. First, we know that SideMenu helps switch from one scene to another scene by sliding in or out. It has many versions. Though,there are not many differences from each version. We analyse the stakeholder, logic view , Technical Debt and so on. Only when we finished the analyse could we know that SideMenu is truly a good framework. It is simple but useful. There is one thing we have to admit that we didn't fully understand the architeture through months of learning. We still have to learn more about it.

It let us have a good command of Software Architecture. It is the precious experience we can't learn from the book. If possible, We hope that we can have more chances to analyse such frameworks or apps.
## Reference

1. Nick Rozanski and Eoin Woods. Software Systems Architecture: Working with Stakeholders using Viewpoints and Perspectives. Addison-Wesley, 2012.

2.https://github.com/jonkykong/SideMenu/releases SlideMenu release page.(2018).
