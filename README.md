## To compile the programs
   
  - run `build.sh`
  - `make`
    
     After the make, an extracted OCaml file (voter_state_transition.ml) will be available in the same directory.
## Dependencies
  - [`Rocq Prover 9.0.0`](https://rocq-prover.org/)
  - [`OCaml`](https://ocaml.org/)

## Files and their description

  * `config.v`       : The configurable parameters are defined in this file.
  * `voter_state.v`  : Contains all the definitions of the data structures used in this project
                      along with some functions and lemmas used to define those data structures.
  
  * `voter_state_transition.v` : This is the main file, in which the transition function of the system is defined.
    - The function `voter_state_transition` compute the new voter state from the old voter state and the currenct cycle measurments.
    - The last few lines of this file contains commands for extracting to an OCaml executable file with appropriate values of the configurable parameters. 
  * `library_using_list.v` : Contains some basic commonly used functions and lemmas.
  * `gen_lemmas.v`    : Contains some generic lemmas on lists which are independent of data structures defined for this project
  * `combine.v`       : Contains some lemmas on a combined list of two lists.
  * `find_faulty.v`   : Contains the functions used to find the miscomparing or maybe_miscomparing units and lemmas 
                       on miscomparison properties (including soundness and completness properties)
  * `build_updated_u_data_lst.v` :
                        Contains functions to update the u_data_lst in the voter_state according to the unit output values of the current cycle.
                       It updates the unit signal, risky_count, miscomparison status, isolatiion status etc.
                       It also contains the lemmas to prove properties which are related to the unit_data and u_data_lst
  * `invalidate.v`     : Contains functions to create invalid and un_id voter_states
  * `prime_switch.v`   : Contains function to create voter_state while switching the prime unit  
  * `properties.txt`   : This file lists the main properties we proved and tells where these properties are proved. 
                        Some of the properties are part of the data structure itself, some others are part of the voter_state_transition function with 
                        the name voter_state_transition_prop. And remaining are proved as separate lemmas.
  * `_CoqProject`      : This file tells which files need to be compiled on make
  
  
