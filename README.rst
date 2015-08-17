======
README
======

This template is based on the proposal files of `OpenDreamKit
<https://github.com/OpenDreamKit/OpenDreamKit>`_, using `LaTeX-proposal
<https://github.com/KWARC/LaTeX-proposal/>`_.

It is set for the FET-Open program and has been cleared of any personal and/or
project-specific references.
The git history has been deleted to avoid carrying about 100MB of
project-specific data.

What you need to do
===================

As a participant:
-----------------

#.  Create a file CVs/<First>.<Last>.tex, starting from CVs/template.tex

#.  Read the `description <http://ec.europa.eu/research/participants/portal/desktop/en/opportunities/h2020/calls/h2020-fetopen-2014-2015-ria.html>`_ of the call.

#.  Read the whole proposal.pdf file. Fix typos directly. Look for
    WRITE HERE comments with your initials, and implement them.
    Comment on the mailing list for other suggestions.


As leader of a workpackage
--------------------------

Edit the file WorkPackages/<WorkPackageName>.tex.

See WorkPackages/template.tex for further instructions.

As leader of a participating institution:
-----------------------------------------

#. Send to PAR1P1 the PIC for your institution:

   http://ec.europa.eu/research/participants/portal/desktop/en/organisations/

#. Create a file Participants/<Institution>.tex, starting from Participants/template.tex

#. Check that the file is included in participants.tex, section Members of the Consortium

#. Double check the file participants.tex


Compiling the proposal
======================

Compiling the proposal
----------------------

Use the Makefile

    make -B draft

or

    make -B final

And you will get a draft.pdf resp. final.pdf file. You can also just
compile the proposal by hand as a usual LaTeX file:

    pdflatex proposal.tex

LaTeX syntax
------------

Tasks::

   \begin{task}[id=portability,title=Portability]
     ...
   \end{task}

You can use the \localtaskref{portability} inside the same work package
to reference this task or \taskref{management}{portability} outside
(assuming that the task is in a \begin{workpackage}[id=management]
There are macros \localtasktref and \tasktref that also add the title.

Deliverables::

   \begin{wpdeliv}[due=48,id=final-mgt-rep,dissem=R,nature=PU]
        {Project Final Report}
        The final report will a summary of all things in the project
   \end{wpdeliv}

There is a title (in the {}) and - optionally - a text (a couple of
lines) that further describes the deliverable. The nature of the
deliverable should be specified using one of the following codes::

    R = Report, P = Prototype, D = Demonstrator, O = Other

The dissemination level should be specified using one of the following
codes::

    PU = Public
    PP = Restricted to other programme participants (including the Commission Services).
    RE = Restricted to a group specified by the consortium (including the Commission Services).
    CO = Confidential, only for members of the consortium (including the Commission Services).

Bibliography
------------

If you need to add a bibTeX data base foo.bib, please commit it, and
add a line \addbibresource{foo.bib} near the other ones at the top of
proposal.tex. We are using biblatex.sty because it is more versatile.
