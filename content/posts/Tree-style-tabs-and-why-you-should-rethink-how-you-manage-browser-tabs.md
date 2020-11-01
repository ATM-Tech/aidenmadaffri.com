---
title: "Tree Style Tabs: And Why You Should Rethink How You Manage Browser Tabs"
date: 2020-10-01T00:00:00-05:00
draft: false
author:
    name: Aiden Madaffri
    image: /images/avatar.png
---

Browser tabs. Such a necessary tool in today&rsquo;s environment, yet we never think if the way we use them is as effective as possible. Normally we are subjected to having our tabs presented to us in an unorganized fashion. But what if I told you there was an option to have tabs follow the same structure as our brain processes them.

![Normal Tabs](/images/posts/TST/NormalTabs.png)

<a id="orge44b813"></a>

## What are Tree Style Tabs?

Tree Style Tabs are an alternative way to view and manage your tabs powered by browser extensions like Firefox&rsquo;s [Tree Style Tab](https://addons.mozilla.org/en-US/firefox/addon/tree-style-tab/) add-on. Instead of a flat structure, TST allows tabs to become &rsquo;children&rsquo; of others.

![TST Tabs](/images/posts/TST/TSTTabs.png)

This allows you to see which tabs came from other tabs. For example, in the picture above I could see a path of the tabs from both the feature and bug of the application I was working on. As compared to normal browser tabs (as demonstrated above), I can clearly see what tabs spawned from each other, not having to lose precious time to sort through them. In addition, I could middle-click on the close button for a parent tab and close its entire tree. This will allow me to easily clean up my browser tabs after I fix that bug.


<a id="org29aa126"></a>

## What kind of person should not use this style of tabs?

In my opinion, these tabs should be a better way of organization for nearly everyone. Unless you purely use your browser for entertainment, almost every task has some sort of structure involved. For example, when you do a google search, for any type of research, you can have a clear view of where all the subsequent tabs came from.


<a id="org3c687d1"></a>

## Availability

Unfortunately, tabs are a rather integral part of the browser, and most browsers do not include TST by default. Currently, [no](no) Chromium-based browsers like Google Chrome, Brave, Vivaldi, or Microsoft Edge support this feature. There are extensions for these browsers that claim to implement the technology, but in my testing, none of them provided a seamless, usable experience out of the box. While Firefox also doesn&rsquo;t support this feature out of the box, the [Tree Style Tab](https://addons.mozilla.org/en-US/firefox/addon/tree-style-tab/) add-on by GitHub user [piroor](https://github.com/piroor) gives a solid experience with this new tab style.


<a id="org6b6964a"></a>

## Configuration

Even after installing this add-on, you will find that the original horizontal tab bar is still present. Firefox, fortunately, allows you to configure custom CSS for the browser to get rid of it. Steps for changing this behavior are below


<a id="org390b1a9"></a>

#### Enable userchrome customization in about:config

1.  Navigate to `about:config`
2.  Accept the risks
3.  Search for `toolkit.legacyUserProfileCustomizations.stylesheets`
4.  Set the value to true


<a id="org74c0218"></a>

#### Navigate to your profile folder

1.  Navigate to `about:support`
2.  Under `Applications Basics` --> `Profile Directory` click `Open Directory`


<a id="orgeaf12e1"></a>

#### Create the folder and files

1.  Inside the folder you just opened, create a new folder called `chrome`
2.  Inside the `chrome` folder, create two new files: `userChrome.css` and `userContent.css`

It should be noted that in Windows, you must have file extensions visible to do this. This falls out of the scope of this tutorial


<a id="org42919b3"></a>

#### Populate CSS

Open `userChrome.css` and populate it with the following information.

    :root {
      --sidebar-width: 180px;
      --toolbar-height: -26px;
      --menubar-height: -60px;
      --toolmenubar-height: -85px; /* sum of previous two */
    }

    /* show bookmarks toolbar on new tab only */
    #main-window #PersonalToolbar {
      visibility: collapse !important;
      z-index: 1!important;
      position: relative!important;
      margin-left: var(--sidebar-width); /* shift toolbar to the right out of the way of the sidebar */
      margin-top: var(--toolbar-height) !important;
    }

    #main-window[title^="Mozilla Firefox"] #PersonalToolbar {
      visibility: visible !important;
      margin-top: -1px !important;
    }

    /* lock sidebar to height by doing the inverse margin of the toolbar element */
    #sidebar-box {
      z-index: 1000 !important;
      position: relative!important;
      margin-top: var(--menubar-height) !important;
      border-right: 1px solid #ccc;
    }

    #main-window[title^="Mozilla Firefox"] #sidebar-box {
      margin-top: var(--toolmenubar-height) !important;
    }

    /* lock sidebar to specified width */
    #sidebar-box, #sidebar-box #sidebar {
        min-width: var(--sidebar-width) !important;
        max-width: var(--sidebar-width) !important;
    }

    /* hide sidebar header for tree style tabs sidebar */
    #sidebar-box[sidebarcommand="treestyletab_piro_sakura_ne_jp-sidebar-action"] #sidebar-header {
      display: none;
    }

    /* Hide the title bar */
    #titlebar{ visibility: collapse; }

    /* hide normal horizontal tab bar */
    #TabsToolbar { visibility: collapse; }

    #sidebar { border-right: 1px solid #ccc; }

    toolbar#nav-bar {
      padding-top: 12px;
      padding-bottom: 7px;
      margin-left: var(--sidebar-width);
      padding-left: 7px;
    }

It should be noted that you may need to modify the variables in `:root` based on the resolution of your monitor.


<a id="org643dc45"></a>

#### Credit

I have adopted this configuration from [/u/infogulch](https://www.reddit.com/user/infogulch) on Reddit in his [post](https://www.reddit.com/r/FirefoxCSS/comments/bhtba7/minimal_tree_tabs/) where he details his setup. For more detailed configuration instructions and descriptions, you should head there.


<a id="org57d3b17"></a>

## Conclusion

Tree Style Tabs are a new technology I began to use that I now wonder how I lived without. For being such an essential tool, why should my browser tabs not provide me with as much organization as possible? I would highly recommend anyone who feels like their tabs could use more structured organization to try out TST. You might find that it changes how you use your browser.


