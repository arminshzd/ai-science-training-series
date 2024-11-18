#  Theory Homework
1. What are the key architectural features that make these systems suitable for AI workloads?
Special Hardware for fast tensor operations and large available memory for handeling large batch sizes and datasets.

2. Identify the primary differences between these AI accelerator systems in terms of their architecture and programming models.
    
    * Sambanova's RDU allows for handling of large data with terabytes of memory. 
    * Cerebra's WSE consists of processors with dedicated memory which operate independently, making Cerebra highly parallel and scalable.
    * Graphcore’s IPU consists of many interconnected processing tiles, each with its own core and local memory. The IPU operates in two phases—computation and communication—using Bulk Synchronous Parallelism.
    * Groq’s TSP architecture focuses inference tasks where low latency is critical.
    
3. Based on hands-on sessions, describe a typical workflow for refactoring an AI model to run on one of ALCF's AI testbeds (e.g., SambaNova or Cerebras). What tools or software stacks are typically used in this process?

Depending on the system chosen, some changes to the original code are required so that the model is compatible with the testbed's architecture. For example, for Sambanova, all `torch.Tesor`s should be converted to `SambaTensor` so that they are compatible with the oeprations on Sambanova

4. Give an example of a project that would benefit from AI accelerators and why?
Many applications that require large datasets and large models for training can benefit from AI testbeds. Examples include large language models with B scale parameters, as well as scientific models like AlphaFold that require large datasets and models.