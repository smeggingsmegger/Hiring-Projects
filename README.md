IWS Software Engineering Project
================================


Getting Started
---------------

 - Fork this repo on Github.
 
 - Please label each commit with the problem that it solves. (See more info below.)

 - Please have one commit per problem. (Use rebase if needed.)

 - We highly reccommend running all this from a \*nix terminal.
   If you don't have one currently set up, you can create an Ubuntu instance using [VirtualBox](https://www.virtualbox.org/wiki/Downloads).

 - Install the requirements for the project. They're all found in requirements.txt. You'll probably
   want to use [pip](https://pypi.python.org/pypi/pip) for this.

 - Use python2.7

 - We're just using a sqlite3 db for this project. Run ```build_or_refresh_db()``` to populate it with the initial data. You might want to take a look at this data and the models before you get started. For example, you can use [DB Browser for SQLite](http://sqlitebrowser.org/) graphically view the db, but feel free to use whatever.

 - A little bit about the files and dirs in this project:
   - runserver.py will start the Flask server
   - shell.py is a terminal with all the accounting instances already imported
   - accounting.models contains the SQLAlchemy database models
   - accounting.views is the view for the Flask server
   - accounting.tools contains the PolicyAccounting class
   - accounting.tests contains the unit tests for PolicyAccounting

 - Questions?
   Feel free to ask! 
   Send an email to amanda@britecore.com


Requirements
------------
- Flask 0.9
- SQLAlchemy 0.7.9
- Flask-SQLAlchemy 0.16
- python-dateutil 1.5
- nose 1.1.2


Helpful Links
-------------
* [Flask SQLAlchemy Plugin](http://pythonhosted.org/Flask-SQLAlchemy/)
* [SQLite Firefox Plugin](https://addons.mozilla.org/en-US/firefox/addon/sqlite-manager/)
* [SQLAlchemy Declarative Base](http://docs.sqlalchemy.org/en/rel_0_8/orm/extensions/declarative.html)
* [A List of Responsive Frameworks for HTML](http://komelin.com/en/5tips/5-most-popular-html5-responsive-frameworks)
* [Testing Flask](http://flask.pocoo.org/docs/testing/)
* [jQuery API](http://api.jquery.com/)
* [pip](https://pypi.python.org/pypi/pip)
* [flake8 (pep8 & syntax analyzer)](https://flake8.readthedocs.org/)
* [JS Hint](http://www.jshint.com/)

And some good things to know about writing Python:

* [PEP-8, a Style guide for Python](http://www.python.org/dev/peps/pep-0008/)
* [pudb, a full-screen, console-base, visual debugger for Python](https://pypi.python.org/pypi/pudb)
* [ipython, an enhanced interface to the Python interpreter](http://ipython.org/)


The Problems
------------
(remember to put which problem(s) you're working on in your commit message!)

**NOTE: Populate your database. Run the following function in the shell: ```build_or_refresh_db()``` Any time you think that your db is getting messed up, you can run this again to start from fresh.**

 1. Policy Three (effective 1/1/2015) is on a monthly billing schedule,
    the developers haven't gotten around to implementing monthly invoices,
    so please go ahead and implement that function without modifying the data
    so that Policy Three can have some invoices.

 2. Now that you've written monthly invoices, you should probably write a unit test for it.
    Use Python's built-in [unittest](https://docs.python.org/2/library/unittest.html) framework for this. We suggest running
    your tests with nosetests.

 3. Oh no, one of the test suites is completely failing! Figure out what caused this and fix it. Assume that it's a bug in the code and not in the test. 

 4. Geez, whoever wrote PolicyAccounting sure didn't like making comments. Would you add
    some comments to the code and functions? You could even add some logging if you'd like.

 5. Mary Sue Client is having problems creating a new policy. Will you help her?
    The info is below:

        - Policy Number: 'Policy Four'
        - Effective: 2/1/2015
        - Billing Schedule: 'Two-Pay'
        - Named Insured: 'Ryan Bucket'
        - Agent: 'John Doe'
        - Annual Premium: $500

 6. The agent Bob Smith called Mary Sue Client furious because his insured, John Doe, couldn't
    pay off Policy One! Please help her out!

 7. Did you notice that an invoice's cancel date is two weeks after the due date? For these two
    weeks, the policy's status is cancellation pending due to non-pay, but the system doesn't
    account for this in any way. If a policy is in cancellation pending due to non_pay, only an
    agent should be able to make a payment on it. There is a code stub for
    evaluate_cancellation_pending_due_to_non_pay get you started.

 8. You know what'd be great? Being able to change the billing schedule in the middle of a policy.
    For example, Policy Two is on quarterly and the insured (Anna White) has already paid off the
    first invoice. Making a payment for $400 was kind of a stretch for her, so in the future she'd
    like to have monthly invoices. Please mark those old quarterly invoices as deleted and switch
    her to monthly.

 9. Mary Sue Client doesn't like the way that cancelling a policy works. It doesn't do
    anything other than print to the screen! She thinks that maybe the Policy's status
    should change, and maybe even store the date that it canceled. It might also be nice to
    be able to store a description about why the policy cancelled. Well, really maybe she'd
    also like to be able to cancel policies for other reasons, like underwriting. Decide how
    to expand the cancellation logic and test it.

 10. Mary Sue Client doesn't really like using the shell when she wants to
     look at policies and their invoices. Will you build her a view where she
     could look at it online? She wants to be able to enter a policy number
     and a date and be able to see the account balance and invoices (even the paid ones).
     There's already a Flask server, but if there's something that you'd rather use
     go ahead. Also, she wouldn't mind looking at a pretty display, but she'd rather
     it be more functional than pretty. If you can think of anything else that
     Mary Sue Client might find useful on the interface, feel free to add it.

 Bonus: If there's anything else bothering you about the code, go ahead and feel free to
 change it. Be sure to put "Bonus" in the commit message please. :)
 
 
Finished?
---------

When you're done with the above problems, please submit your changes in the form of a pull request back to the IWS repo. For the pull request's description, go ahead and write a quick summary of the changes that you made, any major problems that you encountered, and any other comments that you'd like to add. 
