Saku - a clone of P2P anonymous BBS shinGETsu
=============================================

Authors
-------
* (main) Satoshi Fukutomi <fuktommy@shingetsu.info>
* sbwhitecap
* (apollo) replaceable anonymous.
* (2ch interface) kkka
* (thumbnail patch) A shinGETsu user.
* (imghdr patch) A shinGETsu user.
* (js extensions) shinGETsu users.

Contributors
------------
* (run\_cgi) **Python Software Foundation**.
* (Jinja2) the **Jinja Team**.
* (MarkupSafe) **Armin Ronacher** and the contributors.
* (jQuery) the **jQuery Foundation**.
* (Twitter Bootstrap) **Twitter, Inc**.
* (jQuery Lazy) **Daniel 'Eisbehr' Kern**
* (Spoiler Alert) **Joshua Hull**, **Jared Volpe**, and **Dwayne Charrington**

Website and etymology
---------------------
* http://www.shingetsu.info/

*SAKU* stands for "**S**hingetsu **A**nother **K**een **U**tility."
Both the word *saku* and *shingetsu* mean the new moon in Japanese.

Agreements before going in
--------------------------
Agree the following terms and you can join shinGETsu network.

* Describe your own licence, if any, in every article you submit.
  Otherwise, **ALL** your articles are treated as open, public and/or free:
  anyone can use, modify and/or redistribute them.
* Do not use the network for any illegal purpose.
* Do not use the network at the cost of others.

Description
-----------
* Saku is a P2P anonymous BBS works on Python.
* We've confirmed that Saku works on CPython 3.2 on GNU/Linux.
    Saku may not work on Mac OS 9 or any older version.
* The features of shinGETsu include:
    * *2ch.net*-style interface
    * *Wiki*-style hyperlinks
    * *IRC*-style cache function
    * Uploader

Requirements
------------
* [Python](https://www.python.org/) (ver. 3.2 or later)
* [Jinja2](http://jinja.pocoo.org/docs/dev/) (ver. 2.6) if you install Saku using ``setup.py``
* [markupsafe](http://www.pocoo.org/projects/markupsafe/) (ver. 0.19 or later) if you install Saku
* [Pillow](https://pypi.python.org/pypi/Pillow/3.0.0) or [PIL](http://www.pythonware.com/products/pil/) (Python Imaging Library), if required
* [Supervisor](http://supervisord.org/), if needed

Usage (without installation)
----------------------------
1. Open port ``8000/tcp``.
2. Edit ``(your extract path)/file/saku.ini``.
3. Start with

        % python ./saku.py -v
4. Browse ``http://localhost:8000/``.
5. Stop with ``Ctrl-c``.

Usage (with installation)
-------------------------
1. Install **[Jinja2](http://jinja.pocoo.org/)**.
2. Open port ``8000/tcp``.
3. Compile and install.

        $ make
        # su
        # make install
   You can use ``PREFIX`` option for ``make``, or run ``setup.py`` directly.
   If your system does not read modules in ``/usr/bin/local``, do:

        # ln -s /usr/local/lib/python3.2/site-packages/shingetsu \
                /usr/lib/python3.2/site-packages

4. Configuration files are installed into ``/usr/local/share/doc/saku/sample``.
   You should install them into the directories in effect by doing:

        # cp init.sample /usr/local/etc/init.d/saku
        # cp saku.ini /usr/local/etc/saku/saku.ini
        
   or something like these.

   If you use **Supervisor**, install ``supervisor.sample`` instead of ``init.sample``.

   The paths of config files are set in ``saku.ini``,
   which are located in ``/usr/local/etc/saku`` by default.
   ``saku.ini`` are loaded from the following paths and the last one is searched first.

        * ``/usr/local/etc/saku/saku.ini``
        * ``/etc/saku/saku.ini``
        * ``~/.saku/saku.ini``

5. Setup users and directories referring to the config files.
6. Start with

        # /usr/local/etc/init.d/saku start

7. Browse ``http://localhost:8000/``.
8. Stop with

        # /usr/local/etc/init.d/saku stop

9. As a user, run ``/usr/local/bin/saku``.

How to install all required packages on Debian GNU/linux 7.4
------------------------------------------------------------
1. ``sudo aptitude install python3 python3-jinja2 python3-pip``
2. ``sudo aptitude install libjpeg-dev libopenjpeg-dev libtiff-dev libwebp-dev``
3. ``sudo pip-3.2 install Pillow``

Acknowledgements
----------------
* The overall design is made referring to **Vojta** and **Winny**.
* I learned how to handle file names from [YukiWiki](http://www.hyuki.com/yukiwiki/),
  written by *Hiroshi Yuki*.
* Module ``apollo.py`` was made referring to ``apollo.c``,
  written by a *replaceable anonymous*.
* Popup JavaScript was made referring to [Kindan-no Tubo](http://tubo.80.kg/) by *Zero corp*.
* The XSLT scripts were coded reffering to [Landscape](http://sonic64.com/2005-03-16.html).
