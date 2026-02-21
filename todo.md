# Todo list for website:

## Non-Website things to do list
* [ ] org capture templates
* [ ] change org directory to /.emacs.d/org with below code
* [ ] Figure out capture template details
* [ ] Make each item prompt for the Key sequence, whether its a tree or not, and
* [ ] Make mode-specific one
* [ ] What does which-key read from a function to get the mouseover text? Put that somewhere in the capture thingy.
* [ ] Try the capture template again, but think about how it will function instead of just relying on the AI for it. Maybe that will make the AI usable.
    * [ ] Also try to use a new branch ahead of time this time.
    * [ ] And look at an Org file to see how it really looks without the fancy formatting, since thats whats going to be written.
* [ ] Figure out the deal with autocomplete with tab
* [ ] Get rid of trailing red markers
* [ ] tab-switch keybinding that isn't `C-x t`

* [ ] Those blasted trailing space Red boxes are back. Is emacs so determined to hate me T_T

?Is the binding mode-specific? (y/n/u)
 
* All modes
* Unknown
* X Mode
* Y Mode

```elisp
(with-eval-after-load 'org
  (setq org-directory "~/path/to/your/org/files/"))
```
and to make agenda work too:
```elisp
(setq org-agenda-files '("~/path/to/your/org/files/"))
;; Or include subdirectories
(setq org-agenda-files '("~/path/to/your/org/files/" "~/path/to/your/org/files/subdir/"))

```

## Things to do:

  * [ ] Get markdown live preview working in emacs
      * [x] Update Macports
      * [x] Install pandoc
      * [ ] Install/enable markdown, GFMD, Kramdown in pandoc
      * [x] Get pandoc hooked into emacs
  * [x] Add website link to README
  * [ ] Look into modifying theme to fix checkbox rendering
  * [x] Make Git Notes Page
  * [ ] remove H7 from front page. (and make README.md not open somewhere else)
  * [x] fix stupid trailing space red bars in emacts >_>
    * [x] Make that urgent
  * [x] Make website header redirect to home page
  * [ ] Make the Sidebar scroll


## Pages to make:

  * [x] Todo List
  * [ ] Syntax examples for Markdown
  * [ ] GitUp Notes
  * [ ] Syntax examples for Github Flavored Markdown
  * [ ] Syntax examples for Kramdown
  * [ ] AI-Jail (in top bar) (maybe)
  * [ ] HTML-Only (in top bar)

### Todo export:
* Look into cron jobs for stuff like running macports update that has to compile/install but i'll never do unless I'm doing something using macports already.


```java
public class Runner {
    public static void main(String[] args) {
        System.out.println("Hello, World!");
    }
}
```


## Notes

`,` and `M-RET` and `SPC m` all act as the entry command for the major mode command tree. Notably, only M-RET works in `--INSERT MODE--`.

### Emacs Markdown Editing


#### All Modes

##### `M-RET | SPC m | ,` Shortcut Tree
* `RET` Makes new checkbox out of the current line (modes: normal, insert)

* `M-RET` makes a new item in a list in insert mode (if cursor at end of line, makes one before, if at start, makes one after. if in middle, slices line into 2 entries.
    * Note: only works at EOL if in `--INSERT MODE--`
* `l i` does the same thing
* `c r` makes a preview window of the formatted markdown.



##### Normal Mode


##### Insert Mode

Markdown M-ret shortcuts
![Markdown M-ret shortcuts](images/markdown-M-RET.png)

