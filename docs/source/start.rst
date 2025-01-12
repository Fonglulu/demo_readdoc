.. _getting-started:

Getting Started
-------

Currently, there are two supported MPI implementations on Gadi. Both are available by Environment Modules.

* OpenMPI
* Intel MPI

To load these models, use the following commands:

.. code-block:: bash

    module load openmpi/[version]
    module load intel-mpi/[version]
If you are using Intel MPI, you also need to load one of the Intel Compilers. There are two options:

* Intel Compiler (classic)
* Intel Compiler (LLVM-based)

To load the Intel Compiler (classic), use:

.. code-block:: bash

    module load intel-compiler/[version]

To load the Intel Compiler (LLVM-based), use:

.. code-block:: bash

    module load intel-compiler-llvm/[version]

Once you have loaded the appropriate modules, you can compile your MPI code using the appropriate compiler wrapper. For example, to compile a C code using OpenMPI, use: