# Automate-the-Creation-of-an-API-Wrapper-package-by-Scraping-its-Online-Documentation

The details of the codeset and plots are included in the attached Adobe Acrobat reader (.pdf) file in this repository. 
You need to download the same to view the contents. There are referrals to other contents in BLUE colour also to follow.

A Brief Introcduction
=======================

One thing I don’t like about
building API wrapper is that it’s very repetitive: you have to copy and
paste things over and over again, for each endpoint of the API.
Arguments, documentation…

But here’s a fun idea, how about scraping the help page of the API to
generate the whole thing?

General idea
=============

So the global skeleton I need is the one for a .R file for a function,
with {roxygen2} skeleton, and as much of the function as possible.
Then, I need the arguments to the function, which are the available
parameters of the API call.

If they are required by the API, I’ll leave them without a default
value. If they are not, I’ll pass them NULL as a default parameter.
Then, I’ll create a list with these params, remove the NULL with an
internal fun, and turn them to JSON. Then I’ll be building the
{httr} call.

One thing I know upfront is that I won’t be able to generate the whole
thing, but let’s try to do as much as I can!
