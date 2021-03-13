+++
title="on obsidian.md"
date=2020-11-15
+++

Obsidian didn't work for me.  I gave it a drive for about a month or so, attempting to slightly modify my workflow to fit it, but ultimately, I'm going to move back to a slightly modified version of my existing note-taking routine:  VSCode.

When I first checked out Obsidian, I thought, "sweet, this will help me be more organized without having to really change what I'm doing."  Starting up with Obsidian is just as easy as opening the folder full of markdown files that I'm already using.  So, really, other than reading documentation, all I had to do was download it and get started.

But this doesn't actually leverage what Obsidian can do for you.  I attempted to reorganize the way that I took notes to some degree, breaking off more projects and landing zones from my daily notes document into their own space.  It didn't really work, though; I ended up with a sort of half-baked zettelkasten that felt all over the place.  The last thing I'd want is for the tool that helps me organize my thoughts to feel unorganized.

So, to me, Obsidian felt like it tried to do too many things at once, and not very well.  It's not an "IDE"; there are plugins, but they just don't really match what I get out of writing plain markdown in VSCode.  For example, I just opened on of my markdown files that I'd written in Obsidian in VSCode, and immediately saw all of the trailing whitespace that I'd just left hanging around highlighted in bright red.  And, of course, the code snippets I'd embedded in the first file I'd opened had syntax highlighting in them, unlike in Obsidian!

Also, I just didn't really feel like I needed Yet Another Electron Application open to take notes.  Switching between writing notes and writing code should not be distracting — doing so with VSCode is, in my mind, seamless.  Switching between Obsidian and VSCode still always required a context switch for me.

The other benefits I thought Obsidian could have brought to the table just didn't work out for me, either.  Obsidian has a unified aesthetic, and seen from far away, it is quite pretty.  But that got stale for me pretty fast, and I found myself again preferring my hyper-personalized VSCode setup.  I found the places where Obsidian took over and formatted your markdown for you just not worth it — I guess I just prefer headers to be boldly highlighted, but not actually bigger when I'm writing documents.  At the end of the day, I just found my VSCode theme more delightful to look at.  I [even tried theming Obsidian](https://github.com/tjwds/obsidian-minimal-iceburg), but it still just couldn't hold up.

There are very many valid complaints to be made about Microsoft, but VSCode is licensed under MIT.  Microsoft seems to have found shepherding this editor that I really, really like profitable, but maybe a lot of that is because they're big name players that can afford to give the project the attention it deserves.  Obsidian is closed-source, and though the way they seek to gain a profit off the editor isn't creepy yet, I could see it easily growing that way.

## Concrete UI complaints

So:  that was a lot of abstract complaints, but there were quite a few day-to-day UI quirks about Obsidian that made me quit it.  Some of these are just an artifact of my having gained muscle memory for one editor and then attempting to switch to another, but others, I think, are valid complaints, and even those that are _clearly_ a me problem could be resolved by letting things be a little more configurable.

### I just don't get the way that changing between files works

I could not wrap my head around pressing ⌘O to bring up the file switcher, but this is probably because Obsidian's "action" command pallet shortcut is ⌘P, which is subtly different from VSCode, where the command pallet is in "file" mode on ⌘P and "action" mode with ⌘⇧P (or, my preferred ⌘P then typing `>`).  I know that this is mostly a me problem, but this seems like a pretty hard break from the way any other editor does things.

### New files

I kept pressing ⌘N to create a new file and ⌘V to dump my clipboard buffer in one single action, because this is muscle memory for me at this point, but if you do this in Obsidian, you'll end up with your paste buffer as the file name, and you can't just ⌘A to select and delete your mistake, because you can't ⌘A within the title.

### Folders

Folder support in Obsidian is not great.  You can either have all new files be created at the top level, or be put into the same directory as the file you just had open (?!).  This means that I was just constantly losing files, turning to my terminal to try to find where the heck the file actually went.  VSCode's file browser does this pretty great thing where it'll focus the file location in the file explorer when you focus on a file in your editor; it seems to me the Obsidian _must_ get this feature in order for me to be able to actually use it.  Trying to find a file among many, many folders all containing many, many files was infinitely frustrating.

### VSCode's just better about workspaces and opening files

I am constantly reaching for the terminal command `open .`.  As far as I know, you can't do that with Obsidian; nor is it really designed for opening arbitrary files to edit outside of the context of a project.

I have a lot of workspace-specific configurations in VSCode, like the extension Peacock, which allows me to say, mark an editor as the bright blue "this is the active repository" editor so that I can very easily distinguish it from a reference repository I have open.  Yeah, I have multiple checkouts of a few projects, I know, I know.

### Editing often feels clunky

Writing just didn't feel like a pleasant experience to me with Obsidian.  I honestly don't have a lot of concrete data to point to _why_, it just didn't feel good!

The only actual issue I can remember is the frustrating ambiguity as to what an asterisk is about to do in markdown.  I make a lot of unordered lists when organizing projects, notes, or just writing about things — this article, for example, was written in my typical writing style of having a big ol' unordered list at the bottom that I slowly turned into paragraphs.

Wrapping something in asterisks in markdown creates emphasis, though, so Obsidian will add another asterisk _after_ your current cursor location when you type one.  But, if your line starts with an asterisk and you press enter, Obsidian will create a new line for you that starts with an asterisk.

Maybe this is the behavior that other people want, but it often broke my flow as I was writing.

### Panes and tabs

I also just found the pane model frustrating.  Obsidian (as far as I know) doesn't support tabs, which means in order to open another file, it must be in another pane, or it'll close the editor you had open in order to open the new file.  To keep a file open, you can pin it, and then opening a new file will create a new split pane, which is kind of nice, but again, I just prefer the way that VSCode does it.

### Organization

I'd prefer if Obsidian didn't keep around empty files with the title "Untitled" — I would often find myself opening and then closing a new file, so at the end of the day, I'd have at least one completely empty "Untitled.md" file to delete from my notes.

### Other thoughts

* VSCode and git go hand-in-hand, and I like using git to back up and see how my notes have changed over time.  VSCode makes unstaged changes very visible, whereas Obsidian doesn't!
