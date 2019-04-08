## Plan:

---

### Title, Abstract, Motivations, similar

### Chapter 1: Overview & Intro
> Relevant background theory;
>> Schrodinger equation
>> 
>> soft-core potential vs. Coulomb potential
>> 
>> FD methods
>> 
>> Krylov Subspace methods (brief)
>> 
>> Parallelism (brief)
>
> Introduce the problem to solve, 
>
> Description of how theory introduced relates to the problem

### Chapter 2: TISE (all)
> CFD methods (as extension of FD methods from Ch1), including coefficient calculation?
>
> Initial / baseline TISE solution implementations 
>
> Results; comparison with expectation for 
  field-free and soft-core cases. (propagator & CFD) <-- update, 
  propagator doesn't work (never did?); instead FFD & BFD - good display of instability with FFD
>
> Optimisations;
>> Sparse storage - max model size improvement, impact on max accuracy, limitations
>> 
>> Eigensolver choice - desc. of differences, extra parameters, quirks of our problem, speed comparisons
>>
>> Boosted Optimiser Method - use cases, proofs of matrix properties, shift-inverse method, introduce basic algorithm, extend to recursive algorithm, table of speed comparisons
>>
>> Meta-Knowledge Optimiser Method - use cases, relation to BOM, description of one-off pseudo data generation & shape descriptions, (overview of ML?), table of speed comparisons, advantages over BOM, limitations w.r.t. BOM

### Chapter 3: TDSE (all)
> Introduce FFD and Krylov Subspace Propagator approaches
>
> Explain weak & strong scaling testing
>
> Analytic solution for field-free propagation
>
> Comparison between propagators;
>> Efficiency,
>> 
>> Accuracy 
>
> Simulation of different external potentials;
>> DC drift,
>>
>> laser pulse,
>>
>> Effects on wavefunction evolution (qualitative)
>
> Parallelisation of FFD propagator;
>> comparison on a laptop (weak & strong scaling)
>> 
>> comparison on a server cluster (weak & strong scaling)

### Chapter 4: RMT
> Overview of R-Matrix origins, work being done, goals/capabilities of RMT, qualitative explanation of operation
>
> Currently available options for parallelised time-propagation, differences, main bottlenecks
>
> My work on parallelised finite difference time-propagation capabilities; why it should avoid some bottlenecks, what I've done so far, what is left to do
>
> Results so far, sanity checks, comparisons (if at a stage where possible)

### Summary & Conclusions
