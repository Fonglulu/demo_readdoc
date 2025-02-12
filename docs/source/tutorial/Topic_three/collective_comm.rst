Collective Communication 
----------------------------

We have seen a bundle of point to point communication in the previous section. 
Despite the various modes and behaviours of the communication, the basic idea is the same: a message is sent from one process to another.
In this section, we discuss collective communication, which involves multiple processes.
The collective communication can be further divided into: **All to All**, **One to All**, and **All to One** communication.

.. admonition:: Definition

    **All to All** All processes contribute to the result. All processes receive the result.

    **All to One** All processes contribute to the result. One process receives the result.

    **All to One** One process contributes to the result. All processes receive the result.


In our example, we need the collective communications for quantities such as the averaging the errors, or the max or min of the function values defined over the domain.


All to All Communication
=========================


**MPI_BCAST**
MPI_BCAST broadcasts a message from the process with rank "root" to all other processes of the communicator, as shown in the figure below.

.. image:: ../../figures/bcast.png

In this diagram, each row of the box represents data location in one process. Initially only the first process contain the data A0, after the MPI_BCAST call, all processes contain the data A0.

.. admonition:: Key MPI call
    :class: hint

    MPI_BCAST(buffer, count, datatype, root, comm)
        INOUT **buffer**: initial address of send buffer (choice)
        IN **count**: number of elements in send buffer (non-negative integer)
        IN **datatype**: data type of elements in send buffer (handle)
        IN **root**: rank of broadcast root (integer)
        IN **comm**: communicator (handle)
    C Binding:

    .. code-block:: c

        // broadcast a message from the process with rank "root" to all other processes of the communicator
        int MPI_Bcast(void *buffer, int count, MPI_Datatype datatype, int root, MPI_Comm comm)