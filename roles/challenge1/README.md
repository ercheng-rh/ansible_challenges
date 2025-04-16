# ansible_challenges

## challenge 1

1) Write a playbook to install Nginx and ensure that it is running on port 7510. When accessing the web page on a server it should tell you the time of day eg. 'Morning', 'Afternoon', 'Evening' (1700-2400) on the first line of the page, under that it should provide the hostname, IP address, and what environment it is on.

eg.

```console
[Production]
servera.example.com

[Development]
serverb.example.com

[Test]
serverc.example.com
```

2) There is a file called test.html in /var/www/html which needs to be accessible from the web. In that file there are multiple typos of the word TeSt that should be test. Everything else in the file should remain the same.

3) Ensure each user(s) from a list called users exists on the system setting the username to the username value, along with adding them to a group (same with UID) only if provided, and generate a password if a password isn't already set for each user that has alpha numeric and special characters in it. This password should be saved in a file /root/.USERNAME.password with the permissions 700.

eg.

```yaml
users:
  - first: Bob
    last: Builder
    username: bbuilder
    group: dev
    uid: 1230
```

4) Add a GitHub action to run ansible-lint in a file called `ansible-lint.yml` that utilizes an official ansible-lint action. This action should read an ansible-lint configuration file that ensures that any ansible-lint run CI or CLI that runs the production rule sets, ignores any github configuration files, ignores yaml line length checks, and enforces the yamllint rules of document starting with `---` ending with `...`, only allows for "true" or "false" not other boolean options.