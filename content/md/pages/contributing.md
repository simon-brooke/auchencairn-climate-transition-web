{:author "Simon Brooke",
 :date "2025-07-16",
 :description
 "To contribute to Auchencairn Climate Transition's website, you will need the following:",
 :image
 {:path "/img/git-commit-example.png",
  :alt "An editor open onto a commit message",
  :width 1338,
  :height 746,
  :type "image/png"},
 :inferred-meta true,
 :tags [""],
 :title "Contributing to this website"}

To contribute to Auchencairn Climate Transition's website, you will need the following:

1. **Authority to do so.**
    We have not yet established how people will be authorised to contribute to the website. That is a decision which will probably be made by the Website/Branding group but which will need to be signed off by trustees. This page will be updated when that decision has been made.
2. **A secure shell key pair.**
    Your key pair can be generated as explained [here](https://git-scm.com/book/en/v2/Git-on-the-Server-Generating-Your-SSH-Public-Key). Your key pair should have a strong *and memorable* pass phrase, and you should keep the private key on your own machine only and never share it with anyone. You should never share the pass phrase with anyone.
3. **Access to the repository.**
    The repository is currently hosted on [GitHub, here](https://github.com/simon-brooke/auchencairn-climate-transition-web). However, it may be moved to [the Journeyman Forgejo instance](https://git.journeyman.cc/); again, this is a decision which needs to be taken and this page will be updated when it is.

    Wherever the repository is hosted, you will need an account on that server, and will need to share your public key with the administrator(s) of that server.
4. **Secure copy protocol access to `notary.journeyman.cc`.**
    The website is physically hosted on `notary.journeyman.cc`. This server accepts uploads only from authorised users with registered public keys and using the [secure copy protocol](https://en.wikipedia.org/wiki/Secure_copy_protocol).

-----

## Brief description of the process of adding to or editing the website

### Introduce yourself to Cryogen

The website is built using a framework called [Cryogen](http://cryogenweb.org/). You don't really need to know very much about it, because all the setup has already been done, but if you want to understand fully how it works [the documentation is here](http://cryogenweb.org/docs/home.html).

### Set up your computer to edit the website

#### Tools for interacting with the repository

When you are first authorised to contribute to the website, you should first clone the repository to your own computer. This is a standard [git clone](https://git-scm.com/docs/git-clone) operation.

You can use [git](https://git-scm.com/) from the command line, on Windows, Mac or Linux computers. It is free and open source.

For those not comfortable with using the command line there are many programs which provide graphical interfaces to git; we will probably recommend one. [GitKraken](https://www.gitkraken.com/) is good and is free to use for projects like this, but it is far from the only one and may not be the one we choose to support. 

#### Tools for editing pages

Pages of the website are written in a simple text format known as [Markdown](https://www.markdownguide.org/). You can write Markdown files with any text editor, but there are editors which provide a near 'What you see is what you get' editing experience.

We recommend

1. [Typora](https://typora.io/)

    Typora isn't free, it costs $14.99. But it's extremely clean and easy to use and does not get in your way.

2. [Zettlr](https://zettlr.com/)

    Zettlr is free and open source, and although not perfectly 'what you see is what you get', it's close. It too is clean and easy to use.

#### Tool for automating build

To build the website, you need [Leiningen](https://leiningen.org/). Leiningen is a specialist tool for automating the build of Clojure programs, and Cryogen is a Clojure program.

Again, you can download Leiningen for Windows, Mac or Linux computers, but you will have to use it from the command line.

Fortunately, there are only two commands you need to know.

1. `lein serve`

    `lein serve`, if executed in the directory `auchencairn-climate-transition-web` which is the root of the repository you checked out of `git`, will run a local copy of our website on your machine which will automatically update whenever you edit a file, so that you can see exactly how your changes will appear. 

    The local copy of our website will continue to run until you type `[Control]-C` in the command window in which you executed `lein serve`, or close that window.

2. `lein run`

    `lein run`, if executed in the directory `auchencairn-climate-transition-web` which is the root of the repository you checked out of `git`, will compile the whole of our website into the sub-directory `public` of that repository.

#### Tools for uploading to the website server

The website is (currently) hosted on `notary.journeyman.cc`. This server can only be accessed by [secure shell](https://en.wikipedia.org/wiki/Secure_Shell) and related tools; in particular, file upload can only be done using [secure copy protocol](https://en.wikipedia.org/wiki/Secure_copy_protocol). Notary *does not* accept log on, or connection, by password, but only by key pair (which is why you needed to generate your key pair).

For Windows machines, the most convenient graphical interface to secure copy protocol is [WinSCP](https://winscp.net/eng/index.php). For Macs there's no graphical client, you can only use `scp` from the command line. On Linux, the Gnome file browser works as a graphical client for SCP.

### Editing a page

>   **IMPORTANT**: before making any change to the site, you should ensure that your local copy of the repository is up to date with the copy on the git server. To do this you execute a `git pull` request. If you have a graphical git helper such as GitKraken, this is just a matter of opening the repository and selecting `pull` from the menu. Otherwise, you can open a command window, navigate to the `auchencairn-climate-transition-web` directory on your machine, and type `git pull`.

Pages within the website are divided into two categories: those called 'pages', which don't describe particular events or have any specific date but are permanent parts of the infrastructure of the site, like this one; and those called 'posts' which are dated pages such as minutes of meetings, press releases, or reports of events. It is intended that there should be few of the 'pages' and that they should be created only rarely, after discussion among the website/branding group; but they will occasionally have to be updated.

To edit a page, open the sub-directory `content/md/pages` of the directory `auchencairn-climate-transition-web` in your file browser, choose the file you want to edit, and open it in the Markdown editor you have chosen to use. Then just edit it and save it like any other file.

### Editing an existing post

Most of the pages of our website will be of the type called 'posts'. To edit an existing post, open the sub-directory `content/md/posts` of the directory `auchencairn-climate-transition-web` in your file browser, choose the file you want to edit, and open it in the Markdown editor you have chosen to use. Then just edit it and save it like any other file.

### Creating a new post

To create a new post, open your chosen Markdown editor, write the file, and then save it into the sub-directory `content/md/posts` of the directory `auchencairn-climate-transition-web`. Each post should start with a title, which should be formatted as 'Heading 1', indicated in Markdown by starting the line with a single initial hash (`#`) mark. You should use 'Heading 1' *only* for the title, but can use any other Markdown features you choose in the text of the post.

#### Naming post files

The name you choose for your post file has a fixed format which is important. You will see that post files have names like

```
2024-08-12-notice-of-AGM.md
```

That is:

1. the year of publication, as a four digit number, followed by a hyphen;
2. the month of publication, as a two digit number, followed by a hyphen;
3. the day of month of publication, as a two digit number, followed by a hyphen;
4. the title of the post, as upper and lower case letters and numbers only, with any spaces or punctuation replaced by hyphens;
5. the file-type suffix `.md`, to identify this as a Markdown file.

#### Editing metadata

When you run either `lein serve` to preview your edit of the website, or `lein run` to compile it, you will find that your file has been automatically changed by adding metadata to the beginning of it. This metadata will look something like this:

```clojure
{:author "Rowan O'Dowd",
 :date "2024-08-13",
 :description "ACT is a dynamic community organisation driven by many committed and enthusiastic people. This is a place to catch-up on all the great things that are happening and a space to share your news and projects with other members",
 :image
 {:path "/img/carrifran-visit.png",
  :alt
  "Minibus trip participants enjoy views of a Golden Eagle at Carrifran Wildwood. Photo: Barry O’Dowd",
  :width 1484,
  :height 445,
  :type "image/png"},
 :inferred-meta true,
 :tags ["Newsletters"],
 :title "August newsletter"}
```

You can edit this metadata, in your editor, just like any other text; but the format of this section is not Markdown but [Extensible Data Notation](https://github.com/edn-format/edn). 

You will also notice that the title you entered has been transferred into this metadata.

The things that you are likely to want to edit are the `:tags`. You may add as many tags as you like; you can find the tags that have already been used in the lower part of the left-hand navigation panel of any page of the website.

Any new word of phrase you add in `:tags` will become a new tag and will be added to the list shown in that left hand panel. We do not want too many different tags, because this makes them less useful in navigating the website; on the other hand, if you are writing about something we haven't written about on the website before but are likely to want to write about again, a well chosen tag will help group those posts.

### Adding pictures to your pages or posts

If the picture you want to use already exists publicly available on the web, you may link to it [as described here](https://www.markdownguide.org/basic-syntax/#images-1). This has the advantage that we don't have to store the image, but the disadvantage that if the site which currently serves the image deletes it, our page will show a broken link.

If the picture you want does not exist on the web, you should copy it into the `content/img` sub-directory within the `auchencairn-climate-transition-web` directory. You may then use it in your document by linking using the relative URL `/img/` followed by the file name.

Thus, if your picture is called `my-picture.png`, you would link to it in your Markdown file like this:

```markdown
![This is my picture](/img/my-picture.png)
```

You may use pictures in the following formats:

1. `gif`

    A raster (pixel) format for graphics with a limited range of flat colours. Now largely obsolete, but does have the merit that it can be used to create short animations.

2. `jpg` or `jpeg`

    A raster (pixel) format which is very efficient for graphics with a full range of colours and tones, such as photographs; less good for graphics with a limited range of flat colours. Because the compression algorithm is lossy, the picture the reader sees may not be exactly the same as the picture you originally took, but the changes are usually undetectable.

3. `png`

    A modern raster (pixel) format with non-lossy compression which works reasonably well for images of all sorts.

4. `svg`

    A vector format, typically for graphics, diagrams and techical drawings, has the great merit that images can be scaled up indefinitely without losing sharpness.

### Previewing your changes

To preview your changes, execute `lein serve`, as described above. Your web browser should open, showing a local copy of the website. If, reading your post or your edits back, you aren't pleased with what you have written, you can re-edit and save your file and your page or post will automatically recompiled, so that you can see the changes in your browser just by reloading.

**Note**, however, that, Cryogen will only recompile the pages that are changed, so that after editing one file, the rest of the local copy of the website may be missing. To fix this, interrupt the `lein serve` process by pressing `[Control]-C` in the command window in which you started it, and restart it by typing `lein serve` again.

## Publishing your changes

>   **IMPORTANT**: unless all changes you have made &mdash; that is, files you have added and changes you have made &mdash; have been committed to the repository and pushed to the git host, other people who edit the site will not have your changes, and consequently when they subsequently publish their changes, your changes may be lost. So you **MUST** commit and push before publishing. If you have a graphical git helper tool, it will prompt you to do this.

If you do not, other people editing the website will not have your changes, and so when they publish theirs, yours will be lost.

### Committing and pushing your changes

1. open a command window and navigate to the `auchencairn-climate-transition-web` directory;

2. type `git commit -a` (followed by `[Return]`);

3. whichever text editor you have selected as your default will open with a message like this:
    ![An editor open onto a commit message](/img/git-commit-example.png)

4. If any of the files you have added or edited are listed as `Untracked files`, you should exit the text editor immediately and, for each such file, enter a `git add` command like this one:

    ```shell
    git add content/md/pages/contributing.md
    ```

5. If there are no such files listed as untracked, or once you have added the untracked files and invoked `git commit` again, you should enter a brief description of the changes you have made as the first line of the file, save the file, and exit the text editor;

6. You should see a message something like this:

    ```
    [master 0733077] Added a page on how to edit the website
     3 files changed, 180 insertions(+), 2 deletions(-)
     create mode 100644 content/img/git-commit-example.png
     create mode 100644 content/md/pages/contributing.md
    ```

7. If this looks satisfactory, you should then invoke `git push`. You will be challenged for the pass-phrase of your secret key. Enter this. If you enter it correctly, your changes should be transmitted to the server.

8. You should see a message something like this:

    ```
    Enumerating objects: 17, done.
    Counting objects: 100% (17/17), done.
    Delta compression using up to 12 threads
    Compressing objects: 100% (10/10), done.
    Writing objects: 100% (10/10), 78.02 KiB | 26.01 MiB/s, done.
    Total 10 (delta 6), reused 0 (delta 0), pack-reused 0
    remote: Resolving deltas: 100% (6/6), completed with 6 local objects.
    To github.com:simon-brooke/auchencairn-climate-transition-web.git
       419a056..0733077  master -> master
    ```

### Compiling the website

Once you have successfully pushed your changes you should compile the website as follows: in a command window in which the current directory is `auchencairn-climate-transition-web`, invoke `lein run` (followed by `[Return]`). This should produce *a lot* of output, ending with something like this:

```shell
generating site map
generating main rss
generating filtered rss
        --> /cryogen.xml
"Elapsed time: 507.750415 msecs"
```

Congratulations, you have now compiled the website.

## Publishing your changes

> **IMPORTANT** if you have not been authorised to do this, and have not provided the server administrator(s) with a copy of your public key, you will not be able to do this.

On Notary, hosted websites are stored as sub-directories of the directory `/var/www/https/hosted-sites/`. Thus, to publish the website, once you have committed and pushed your changes to the git server, and have compiled the website (see above), you should invoke `scp` in a command window in which the current directory is `auchencairn-climate-transition-web`, as follows:

```shell
scp -r public/* your-name@notary.journeyman.cc:/var/www/https/hosted-sites/act.scot
```

You may be prompted for your private key pass-phrase; if you are, you should enter it.

Uploading will take a few seconds, during which `scp` will print a log of what it is doing, ending something like this:

```shell
index.html                              100%   11KB 190.7KB/s   00:00    
index.html                              100% 7770    92.0KB/s   00:00    
index.html                              100%   10KB 181.7KB/s   00:00    
index.html                              100%   14KB 241.6KB/s   00:00    
sitemap.xml                             100% 2625    47.2KB/s   00:00    
index.html                              100% 5868   104.1KB/s   00:00    
index.html                              100% 6437   111.3KB/s   00:00    
index.html                              100% 5574   103.9KB/s   00:00    
index.html                              100% 6230   110.8KB/s   00:00   
```

Congratulations! You have now published your changes to the website.

