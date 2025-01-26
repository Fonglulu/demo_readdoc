MPI Semantics
---------------


.. admonition:: Overview
   :class: Overview

    * **Tutorial:** 20 min

        **Objectives:**
            #. Learn the semantics of MPI.

To help us understand and better use MPI, we get into the details of its semantics. Fair warning ahead, this is a bit of a dry topic and it does get tedious. You can skip this section if you just want pick up MPI functions and use them straightaway, but recommend you to go through this section to acquire a more in-depth understanding of MPI.



MPI Operations
----------------
First, we introduce the concept of MPI operations.

.. admonition:: Definition
    :class: hint

    An **MPI operation** is a sequence of steps performed by the MPI library to establish and enable data transfer and/or synchronishation. It consists of four stages: **initialisation**, **starting**, **completion**, and **freeing**. An MPI operation is implemented as a set of one or more MPI procedures. 


The main MPI opeartions are: ** Blocking Operations**, **Non-blocking Operations**, **Collective Operations**, and **Persistent Operations**. We will discuss each of these in detail in the upcoming sections.

.. note::
    An MPI operation describes the property of a class of data transfer mechanism but does not define a unique MPI procedure.

The four 



MPI Procedures
----------------
, we introduce the concept of MPI procedures.

.. admonition:: Definition
    :class: hint

    An **MPI procedure** describes functionalities and are specified using a language-independent notation. 