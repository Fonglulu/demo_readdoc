Example: Monte-carlo Approximation of Pi
------------------

.. admonition:: Overview
    :class: Overview

    * **Tutorial:** 20 min

        **Objectives:**
            #. Learn how to use MPI to approximate Pi using the Monte Carlo method.

**Monte Carlo Method:** The Monte Carlo method is a statistical technique used to estimate the value of an unknown quantity using random sampling.
In this example, we generate :math:`N` random sampling points within a square, and count the number :math:`h` of samples that fall in the unit circle. Then the approximation of :math:`\pi` is given by: :math:`4h/N`.

.. image:: ../../figures/Monte-Carlo01.jpg