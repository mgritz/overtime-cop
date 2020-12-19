# overtime-cop
Keep track of your daily work time.

*WIP: This tool is still under ongoing change and I am also open to suggestions.*

Do you also have the problem of getting so immersed with your (software) work that
you might loose sense of time and suddenly find yourself having done overtime?

Here comes a useful little helper that helps you around that.

```
overtime-cop --planned 7.5 --breaks 0.75`
```

very simply computes the time you are supposed to leave from work given that
you have to work 7h30min and clock off for 45min of lunch break.

It assumes that your day started when you last bootet your computer. You can
pass in any other time of arrival thorugh the `--arrived '2020-12-20 07:30'`.

If your company uses a Redmine task management system to log your hours there is
more: Pass your companies `--redmine-url` and your personal Redmine API `--key`
and it will look up the number of hours you have booked so far and tell you about
that as well.

See `overtime-cop --help` for other command line options.

Pro-Tip: Automate execution of this little script and include the output in your
Linux desktop environmet.

## Dependencies

It's written for python 3 and has some library dependencies:
- `uptime` for platform-independent way to get the system boot time. \\
  Get it via `pip3 install uptime`.
- `redminelib` if you want the redmine-features to work. \\
  Get from Debian packet sources with `sudo apt install python3-redminelib`.

## Ideas for the Future

Here are some ideas on how to improve this:
- Daemonization and popup notification for going home. \\
  This can be scripted for now using chron and notify-send or something.
- Persistent config file.
- Support for Redmine user-password access as well.
- Support for other task management systems that allow time tracking.
