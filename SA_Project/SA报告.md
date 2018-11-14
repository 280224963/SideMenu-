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

![power_interest](https://github.com/280224963/SideMenu-/blob/master/picture/power_interest.png)

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

Figure 2: use case view of SlideMenu

## Logic view

...

## Development view

...

## Evolution Perspective


## Technical Debt

#### 1.Definition
Technical debt is a well-known concept that was introduced in 1992 by Ward Cunningham (founder of the wiki), who talked about this topic in a recent video. Since then, this topic has been discussed and studied countless times in blogs and articles. Martin Fowler gives a point of view through metaphor:

In this metaphor, we set up a technical debt through a temporary emergency, which is similar to economic debt. Just like economic debt, technical debt is also subject to interest. It exists in our future development. Because we choose temporary emergency measures, at some point, we will pay some form of extra cost. We can choose to continue to pay interest, or we can choose to repay the principal and reconcile the principal to get a better design. Although it paid off the principal on the spot, it allowed us to reduce interest payments in the future.


## Conclusion

(待完成
## Reference

1. Nick Rozanski and Eoin Woods. Software Systems Architecture: Working with Stakeholders using Viewpoints and Perspectives. Addison-Wesley, 2012.
