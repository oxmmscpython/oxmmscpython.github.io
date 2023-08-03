.. _assessment:

Assessment
==========

For those taking this course for credit in Oxford, an assessment is required.
This will take the form of a report, since that is how MMSC special
topics are assessed.


.. proof:exercise::

    Develop a Python package that implements an algorithm or algorithms
    for solving a clearly-specified class of mathematical problems.

    The project should involve a substantial amount of novel
    programming. You should use existing open-source libraries where
    appropriate, but the libraries used should not address the main
    purpose of your program. For example, if you were implementing
    Krylov methods for solving linear systems, your code should use the
    scipy sparse matrix classes (since you need these for efficiency),
    but should not use the scipy implementations of Krylov methods.

    The code should exhibit the principles of good programming described
    in the course. The code should be well-structured, well-documented,
    and tested thoroughly.

    The University's guidance on plagiarism applies both to the code and
    the report: in particular, the code should not incorporate samples
    available on the internet without due acknowledgement.

    The report should be of about 10--20 pages in length. It should
    motivate and describe the class of mathematical problems your code
    aims to solve, briefly describe the algorithms that attempt to solve
    them, and discuss the Python code written for the project. The
    report should persuade the reader that the code is implemented
    correctly, is well-tested, and is reasonably efficient. Continuing
    the example of Krylov methods, if the code employed dense matrix
    formats to represent sparse matrices, it would be orders of
    magnitude slower, and hence would not be reasonably efficient. For
    demonstrating correctness, consider a code for solving differential
    equations. The code should employ the method of manufactured
    solutions to construct a test case for which an analytical solution
    is known, so that the order of convergence achieved by the code (in
    some norm) matches that expected theoretically.

    A typical report will include selected code snippets, to demonstrate
    how the code is used, and to illustrate the main ideas in how it is
    structured, implemented, and tested. The report should not typically
    include the entire code. You will submit a .zip archive of your code
    alongside the report, so that the assessors can execute and evaluate
    it.

    Please ensure that the code submitted in the .zip installs cleanly
    in a clean virtual environment with `pip install -e .`, which should
    also install any dependencies necessary to run the tests and examples.
    Please do not include Jupyter notebooks; examples should be presented
    in documented .py files alone.

    Many students develop ideas for their Python projects from their MSc
    dissertations. If you can develop code that will be useful for your
    MSc research, this is valued and encouraged. However, due regard
    should be paid to the University's guidance on plagiarism, and in
    particular on self-plagiarism; you should not submit the same work
    for credit twice. A typical pattern might be that you will implement
    Algorithm A from the literature in your Python in Scientific
    Computing report, while in your MSc research you will develop
    extensions and modifications of Algorithm A to Algorithms B and C.
    Your MSc dissertation would then clearly state that the
    implementation of Algorithm A was submitted for credit for Python in
    Scientific Computing (and cite your PiSC report), while the
    extensions to Algorithms B and C was conducted as part of your
    dissertation research.

    Rather than develop code from scratch, it is also possible and
    encouraged to make contributions to existing open source codes (e.g.
    by means of pull requests on github). In this case, your report
    should clearly describe the capabilities of the software before your
    contribution, as well the new features in your contribution. Your
    contribution should implement substantial new features or
    algorithms, rather than merely fix bugs.

    The report will be assessed primarily on the beauty, elegance, and
    correctness of the code. Other factors under consideration will
    include the mathematical interest of the class of problems solved,
    and the application of the code to interesting problems.

    For any questions, please contact `the course lecturer
    <mailto:patrick.farrell@maths.ox.ac.uk>`_.

Tips
----

Some tips:

- When citing results in the literature, please cite specific theorems. For example, to cite a proof that a particular problem is well-posed, or that we should expect a given convergence rate in a given norm, you might write `\\cite[Theorem 8.4]{StandardReference}`.

- When describing the algorithms you are implementing, a good report will offer mathematical commentary: this algorithm computes approximations that are expected to converge at this rate, or this algorithm has this computational complexity, or this algorithm will fail in these circumstances.

- If your code uses matrices, think carefully about whether they are sparse or dense, and use appropriate data structures (e.g. `scipy.sparse`).

- If your code repeatedly solves linear systems with a matrix factorisation, compute the matrix factorisation only once (e.g. `scipy.linalg.lu_factor`, `scipy.sparse.linalg.splu`).

- The best type of test for code that solves differential equations is to check the order of convergence of the approximation to a known exact solution. The error should be calculated in a norm for which the expected order of convergence is known theoretically. If you don't know an exact solution, make one with the method of manufactured solutions.

- The tests should run automatically without any intervention (such as to close plots). Your code should almost certainly depend on pytest.

- Spell check your report before submission (e.g. with `aspell --mode=tex check report.tex` in the terminal).

- Make a clean venv before submission. Check that you can install the package in this venv, and that all tests and examples run without errors or warnings.

