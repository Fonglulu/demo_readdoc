Point-to-point Communication 
----------------------------

The point-to-point communication is the most original form of communication in MPI. It's when process A wants to send a message to process B. So what is a message?

.. admonition:: Definition

    In MPI, a **message** is **message data** + **message envelope**.
    
.. admonition:: Definition

    The **message data** is made of three components: (address, count, datatype).
    **address**: the beginning address of the data buffer.
    **count**: the number of successive entries of the type specified by datatype.
    **datatype**: the MPI datatype of the data.


.. admonition:: Definition

    The **message envelope** is made of four components: (source, destination, tag, communicator).
    **source**: the rank of the sending MPI process.
    **destination**: the rank of the receiving MPI process.
    **tag**: a message identifier.
    **communicator**: the communicator over which the message is sent.


.. admonition:: Remark

    #. The **datatype** is a predefined name to specify machine-independent data elements. The basic datatypes are `MPI_INT`, `MPI_DOUBLE`(in C); MPI_INTEGER, MPI_REAL (in Fortran).
    MPI always provides derived datatypes which are user-defined mix of basic datatypes.
    The rational for MPI datatype is to support communications between machines with different memory representations.
    #. The **tag** is a message identifier that allows the receiver to distinguish between different messages from the same source.
    #. The **communicator** specifies a 'communication universe'. Messages are always received within the 'communication universe' they were sent, and messages sent in different 'communication universe' do not interfere. For example, `MPI_COMM_WORLD` is a specifies the communication within all processes available at initialization time.


In our model problem, we need to send the nodal values of the second bottom row to the neighouring processor's top boundary row; as shown in the figure below:

.. image:: ../../figures/Submesh.png

Processor A updates its row $R_i$ to processor B's row $R_i$. This can be done by `MPI_Send`

.. code-block:: c 

    MPI_Send(submesh[1], mesh_size, MPI_DOUBLE, lower, lowertag, MPI_COMM_WORLD);

In this line of code, the data buffer starts at `submesh[1]`, the number of elements is `mesh_size`, the datatype is `MPI_DOUBLE`, the destination is `lower`, the tag is `lowertag`, and the communicator is `MPI_COMM_WORLD`.