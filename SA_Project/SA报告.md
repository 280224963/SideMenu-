SlideMenu 
========== 

![temporary_logo](https://github.com/280224963/SideMenu-/blob/master/picture/temporary_logo.png)
-------------

## Abstract

(待完成


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

#### 1.What is the SlideMenu
SlideMenu is an open source implementation of a sliding menu animation effect posted on Github. 
Developing an ios application often involves designing side menus. SideMenu is a simple and versatile side menu control written in Swift. 
There are numerous Slide Menu control available on the Internet, this one is more likely be included in apple application. 
SideMenu is practically a frame that helps to switch from one scene to another scene by touching a button or sliding left or right.
After importing the SideMenu package, developers don't need to write a lot of custom code, just a simple interface call, you can achieve a vivid animation sliding effect. 
The SlideMenu is based on Swift 4.2 and uses Xcode 10 and needs to run on iOS 10 or higher.

#### 2.History

![history](https://github.com/280224963/SideMenu-/blob/master/picture/history.png)

#### 3.Preview Samples
| Slide Out | Slide In | Dissolve | Slide In + Out |
| --- | --- | --- | --- |
| ![](https://raw.githubusercontent.com/jonkykong/SideMenu/master/etc/SlideOut.gif) | ![](https://raw.githubusercontent.com/jonkykong/SideMenu/master/etc/SlideIn.gif) | ![](https://raw.githubusercontent.com/jonkykong/SideMenu/master/etc/Dissolve.gif) | ![](https://raw.githubusercontent.com/jonkykong/SideMenu/master/etc/InOut.gif) |

## StakeHolders
We will describe a number of different types of stakeholders exist as defined by Rozanski & Woods [1] and relate our views of the classes in relation to the SlideMenu project. 
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
 
 Table 1: Stakeholders of the SlideMenu project
 
 Contributor | Commits | LOC++ | LOC-- | Active during 
 ----|----|----|----|----
 Jon Kent | 339 | 12,402 | 7,004 | 2015-present
 Aron Geczy Gates | 13 | 208 | 130 | 2016-2017
 Soheil | 5 | 3,503 | 4,841 | 2016
 ... | | | |
 
 Table2:Most active contributors in terms of number of commits

The stakeholders are visualized in Table1 and Table 2, their respective power and interest in the SlideMenu project are shown in Figure 1.

![power_interest](https://github.com/280224963/SideMenu-/blob/master/picture/power_interest_pic.png)

Figure 1: Power-Interest grid for the stakeholders of SlideMenu

In the stakeholder analysis, many different actors with different roles, power and interest have been analyzed and visualized in Figure 1. Since SlideMenu is a personal developed control unit,The main stakeholder of SlideMenu is the developer Jon Kent who has the most power and interest in the platform. Since SlideMenu is built upon Swift and Xcode, these programming languages can be seen as more powerful actors than other suppliers, having very little interest. The developers, testers and maintainers can be placed in the middle of the spectrum, all with some power and interest.


## Context view

Context View gives a bief explanation about the system. Usually, a context view describes the relationships, dependencies, and the interactions between the system and its environment. This view is relevant for the system's architecture and defines
the boundaries of the system and how it interacts with external entities across these boundaries. Besides, it will also show you on which system the app runs on.



![context_view](https://github.com/280224963/SideMenu-/blob/master/picture/context_view.png)

Figure 2: context view of SlideMenu

From the above figure, we can easily know about the eviroment.
SideMenu is mainly developed by Jon Kent and Sohei.B.Marvasti. 
This is licensed by MIT, so if you want to know something more about this you can go MIT to learn.
It is implemented by Swift. So if you want use SideMenu in your own app you have to run it on IOS X and above.
Xcode also needs to be 9. It use Cocospods and Carthage to help manage the dependency library. You can use git to learn the source code and chat with the developer. And it is mainly developed for personal users. It can be a good choice if you want SideMenu in your small app. This can also be a good learning resource for students

## Use case view
![use_case](https://github.com/280224963/SideMenu-/blob/master/picture/use_case1.png)

![use_case](https://github.com/280224963/SideMenu-/blob/master/picture/use_case2.png)

Figure 3: use case view of SlideMenu

## Logic view

Logical view is mainly the abstract structure of the whole system. It pays attention to the function of the system which is provided to the end user. It does not involve specific compilation, output or deployment. It is usually expressed in UML by class diagram, interaction diagram and sequence diagram. Figure 5.1 shows the class diagram of this program. There are four main class in this program and an important protocol named UISideMenuNavigationControllerDelegate which is used To receive notifications when a menu is displayed from a view controller which is adhered to the UISideMenuNavigationControllerDelegate protocol: and send the notifications to UISideMenuNavigationController to give feedback.  
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

...

## Evolution Perspective
The evolution perspective deals with concerns related to evolution during the lifetime of a system, it focuses on identifying the ability to be flexible in the face of inevitable change. As discussed by Rozanski and Woods, a flexible system should be able to deal with all possible types of changes that it may experience during its lifetime [1]. Therefore, the changes throughout the lifetime of the project are analyzed, and the mechanisms in place to provide flexibility are discussed. Although only few change occur in the SlideMenu, this is still closely relevant to it.

Thought out the years, SlideMenu has evolved a lot. At this moment SlideMenu has 28 releases, which started with release 2.0.7 in December 2015 and the latest release 5.0.3 in November 2018. However the real first a few release can't be found on the Github repository
anymore. This is probably because it was an alpha version and can not be put into use well. In order to understand the changes in the various releases, the release notes have been analyzed. These were found on the SlideMenu release page on Github.

SlideMenu updates their current version number according to the semantic versioning convention. SlideMenu releases can be categorized into two main categories: major updates that symbolize a new backwards compatibility baseline, and new versions containing novel features and bug fixes.

The first type has occurred five times in the history of SlideMenu. The latter on the other hand, has an average frequency between 2-3 weeks.

![ep_release](https://github.com/280224963/SideMenu-/blob/master/picture/ep_release.png)

Figure4: gives an overview of SlideMenu and mentions the changes with the largest magnitude of change.


#### Gesture:
As a mobile app control, gesture support is crucial. Jon Kent's initial changes focused on improving the support and optimization of various gestures and fixing some bugs that were not noticeable.

#### Ui: 
Although SlideMenu is only about the implementation of the effect, the specific ui design is defined by the user, but Jon Kent still allows for more optimized screen adaptation and some black border problems, making the use of SlideMenu easier.

#### Animation: 
Animation: This part of the optimization is mainly implemented by other developers on github in 2017. Most of the time, the original animation effect is still used. In the optimization, the developer fixed some logic bugs in the animation call, achieving smoother, higher quality animations.

#### Language: 
SlideMenu is written in the swift language, and this part of the maintenance is basic maintenance. Whenever there is a new version of swift release developer upgrade to accommodate the new version of the swift language. Later upgrade also support for calling SlideMenu with Objective-C.

#### Use experience improvement：
Jon kent has put a lot of effort into making the use of SlideMenu easier and more convenient, `SideMenuManager.default` serves as the primary instance as most projects will only need one menu across all screens. User can show a different SideMenu, such as from a modal view controller presented from a previous SideMenu, just by doing the following:
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

From the figure, the project certification is B. It analyses the project through 3 aspects. They are issues, complex Files and Duplicated code. Issues means the comparison of the number of the issues with the industry average. It gets 90% at this part. In this piece, SideMenu has basically reached the industrial level. Complex Files means a file is over 20. The percentage is about 13%.
From this data, we can easily know that only a little files are complex. Most of them is simple. Similarly, the project is also a simple project. Duplicated code means a file has at least 1 clone. 26% ， in my opinion， is a little high. The code is reused much. In some way, this phenomenon is not good for a project.

#### 4.Issues Breakdown
![result_2](https://github.com/280224963/SideMenu-/blob/master/picture/result1.png)

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

(待完成
## Reference

1. Nick Rozanski and Eoin Woods. Software Systems Architecture: Working with Stakeholders using Viewpoints and Perspectives. Addison-Wesley, 2012.

2.https://github.com/jonkykong/SideMenu/releases SlideMenu release page.(2018).
