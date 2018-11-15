## 2.1.3
  Update podspec and README for Cocoapods.
  Cleaner version of logic proposed by @saltyskip.
  adding possibility of tab bar or nav bar
  make tab bar controller

## 2.1.4
  Silence warning.
  Update README for Cocoapods.
  Update podspec.
  Fix for multiple gestures causing crashes when presenting or dismissing menu. SideMenuTransition is due for a refactoring of logic to simplify that I don’t have time for now.
  Update to Launch Screen.
  Say “SideMenu” instead of “Example” in demo project.
  
## 2.1.5
  Update README for Cocoapods.
  Update pod spec.
  Refactoring.
  Second fix for multiple gestures actuating and causing problem.
  
#### 2.1.x总结 i.更新各种使用说明 ii.解决手势问题 iii.精简优化代码

## 2.2.0
  Remove unused variable.
  Update README for Cocoapods.
  Update podspec.
  Updated README.
  Update comment.
  Additional debug warnings to help troubleshoot common problems.
  Refactoring.
  Tighter logic for responding to only a single gesture to avoid conflicts.
  New properties for further customizing non-interactive menu animations.
  Some refactoring and added in .subMenu to the list of behaviors.
  Documentation - added note about .replace hiding the back button.
  deprecation function simplification for .replace and .popifpossible
  updated readme and fixed indentation issues
  Enum changed / new "hide back button" behaviors
  updated documentation (disables back button)
  Default for "PreserveViewOnPush" is now to always disable the back button.
  When I thought I included the animation in the last commit, I did it in my own test project lol 00ps. Animation default now included as well as disable nav back button.
  removed menuTab option and set default action to always hide SideMenu when transitioning to new view. Refactored menuPreserveViewOnPush to match syntax and efficiency
  implemented changed to menuPreserveViewOnPush filter, now instead matching syntax with type(of: )
  last indentation fix
  
#### 2.2.x总结 i.更新说明ii.提升代码效率&逻辑iii.修改了一些ui上的不足

## 2.3.0
  Updated README and podspec.
  Fix for tapView to not be sized to main screen which may be transformed and therefor hard to touch.
  Support for in-call status bar height change.
  Refactoring.
  Updated demo project to show various SideMenu events.
  Logic simplification.
  Removal of no longer needed logic.
  Updated comments and minor refactor.
  Fix for keyboard animations being confused during SideMenu display.
  Updated documentation.
  Fix deprecation warnings in swift 3.1

## 2.3.1
  Updated pod spec and README for Cocoapods.
  Updated project settings.
  Reverting old logic that kept the layout correct when presenting a sub-screen.
  Subtle tweak if a larger transform is used on the main view controller when menu is presented (edge case).
  Fix for disabling gestures. Gestures were being added multiple times preventing all of them from being disabled when the menuEnableSwipeGestures was used.

## 2.3.2
  README edit.
  Updated podspec and README for cocoa pods.

Updated README for Github.

## 2.3.3
  Updated podspec and README.
  Added menuDismissOnPush property.
  Fix for single menu setups losing ability to swipe menu if wrong side is swiped.

## 2.3.4
  Updated README and podspec.
  Added comment.
  Changed menuAnimationCompleteGestureDuration default.
  Changing individual menu width properties in favor of a property on UISideMenuNavigationController.
  Refactor.
  Formatting.
  Support for UISplitViewControllers when pushing view controllers.
  These methods will never be called as they are handled by the topViewController.
  Neglected to use menuDismissOnPush switch in code.
  Fixes to maintain iOS 11 animation smoothness.
  Refactor.
  Changed MainViewController's scrollview to align to the topLayoutGuide.
  Add missing designated initialiser to UITableViewVibrantCell
  Set right menu width equal half of left menu width in example
  Add supporting of different left and right menu width
  
#### 2.3.x总结 i.优化了对屏幕尺寸的自适应ii.优化了动画效果iii.更新了说明


## 3.0.0
  Updated podspec.
  Additional Swift4 support updates.
  Fix for Swift 4 and version 2.3.4

## 3.0.1
  Updated podspec.
  Fixed hack to more specific logic.

## 3.0.2
  Updated podspec and README for cocoapods.
  Corrected logic for default menu width.
  
#### 3.0.x总结 i.升级以支持swift4ii.更新了说明
  
## 3.1
  Updated README for Cocoapods.
  Updated podspec.
  Update README.md
  Updated README.
  Fix for non-animated dismissal of menu causing a black screen.
  Renamed class and refactored how blurring works in UITableViewVibrantCell.
  Major project update to support multiple SideMenuManager instances beyond the primary instance, if necessary.
  Added isHidden property.
  Support for delegate methods on SideMenu appearing/disappearing.
  Refactor.
  Refactoring.
  Fix for menuDismissOnPush as it was incorrectly applied.
  Fix for regression on enums to objective-C.

## 3.1.1
  Updated podspec.
  Update README for Cocoapods.
  README correction.
  Better logic for managing UISideMenuNavigationController properties across interface builder and programmatic instantiations.

## 3.1.2
  Updated podspec.
  Updated README.
  Allow for specifying the sideMenuDelegate, otherwise it discovers it automatically.
  Last commit was incorrect -- but this commit fixes it and includes a work-around for more experience devs who may still want to use default initializer as well as silence some newbie warnings.
  Override of navigation controller default init to prevent new developers from seeing black menus.
  It should be possible now to have the menu slide out even if pushing the new view is not animated itself (animating both can look a bit weird when relying on 'animated' only)

## 3.1.3
  Update README for cocoapods.
  Updated podspec.
  Updated README.

## 3.1.4
  Update README for Cocoapods.
  Updated podspec.
  Fixed SideMenu.UISideMenuNavigationController crash on init(nibName:bundle:)

## 3.1.5
  Updated README requirements.
  Updated README for Cocoapods.
  Exposed defaultManager for Objective-C support.
  Updated podspec.
  Additional changes for objective-C support in UISideMenuNavigationController
  fix objc inference in swift 4

## 3.1.7
  Refactor.
  Refactor.
  Updated example storyboard.
  Upped minimum deployment target.
  Refactor.
  optimize check
  add nil check
  Fixed func hideMenuStart() to avoid problems when mainViewController is released at hideMenuComplete() func
  
#### 3.1.x总结 i.升级以支持swift4 ii.更新了说明 iii.支持objective-Civ.修改函数的bug

## 4.0.0
  Updated README and podspec.
  minor change to be compliant with swift 4.1
  
#### 4.0.x总结 i.升级以支持swift4.1 ii.更新了说明

## 5.0.0
  feat: update swift version for all sub-projects (example,  pod, etc) to 4.2
  feat: update pod swift version to 4.2
  feat: update support for swift 4.2 (source and example)

## 5.0.1
  Updated podspec.
  Update README for Cocoapods.
  Fixes to fully upgrade to Swift 4.2 as it appears to have been incomplete.
  
## 5.0.2
  Refactor
  fix: makes dismissWhenInBackground to be computed property of SideMenuManager
  Adds mainViewController.view to originalSuperview only if dismissWhenInBackground is true
  Prevents fadeout transition if 'dismissWhenInBackground' is set to false
  Adds ability to toggle automatic dismissal of the menu when app goes to the background
  
#### 5.0.x总结 i.升级以支持swift4.2 ii.更新了说明 iii.完善了一些效果的函数
