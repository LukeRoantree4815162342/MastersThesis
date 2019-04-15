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

### Chapter 3: TDSE Implementation
> Introduce FFD and Krylov Subspace Propagator approaches
>
> Analytic / Exact Solutions:
>> Cases where analytic solutions are possible / why some are difficult/impossible
>>
>> Some approaches to approximating solutions (pertubation theory?)
>>
>> Full derivation for field-free case, and why it's a good check for numerical methods
>
> Numerical Approximations by Propagating TISE sols;
>> Allows investigation of analytically difficult / unsolvable problems - motivation
>>
>> Can use similar methods to our TISE approach, but propagating through time not space 
>>
>> We need to re-calculate the Hamiltonian at every timestep as it changes with time
>
> FD Propagator;
>> Uses same method for generating FD coefficients as TISE sol
>>
>> Note: can't use any Backwards terms in FD scheme as we don't have knowledge of next steps (unlike in space)
>>
>> To start, we need to know how the wavefunction changes for the first few timesteps without using FD method
>> - use analytic solution for Field-Free propagation, explain implications of this
>
> Krylov Subspace Propagator;
>> Explain how subspace is built (this one in particular, assume knowledge of in general)
>>
>> How next state is calculated via projection
>>
>> Why there is no need for Field-Free propagation at the start
>
> Comparison between propagators;
>> Efficiency - [big/small] systems, for [long/short] times,
>> 
>> Accuracy - [big/small] systems, for [long/short] times
>> comparing to analytic solutions for Field-Free case
>
> Parallelisation of FD propagator;
>> Splitting up the Hamiltonian & analogue to considering seperate regions of space
>>
>> pseudocode / diagram to describe process
>>
>> implications at region boundaries
>>
>> boundary implications on accuracy over time and over level of parallelism
>>
>> methods of limitting this effect - overlapping boundaries, sharing datapoints between regions & efficiency implications for this
>>
>> Definition of weak & strong scaling
>>
>> comparisons (weak & strong scaling)

### Chapter 4: Investigation of Interesting Potentials
> DC drift;
>> definition (math), qualitative explanation, physical interpretation
>>
>> results @ different time steps
>> 
>> impacts of varying field strength
>
> Laser Pulse;
>> definition (math), qualitative explanation, physical interpretation
>>
>> results @ different time steps
>> 
>> impacts of varying field strength
>>
>> impacts of varying packet width

### Chapter 5: RMT
> Overview of R-Matrix origins, work being done, goals/capabilities of RMT, qualitative explanation of operation
>
> Currently available options for parallelised time-propagation, differences, main bottlenecks
>
> My work on parallelised finite difference time-propagation capabilities; why it should avoid some bottlenecks, what I've done so far, what is left to do
>
> Results so far, sanity checks, comparisons (if at a stage where possible)

### Summary & Conclusions
