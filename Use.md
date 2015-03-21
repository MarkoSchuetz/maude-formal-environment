

## Executing Maude++ and Loading the MFE ##

Assuming that `maude` is Maude++'s executable and that `mfe.maude` is MFE's main Maude file, both in your path, the MFE can be executed with the following command:

```
$maude mfe.maude
                    \||||||||||||||||||/
                 --- Welcome to Maude ---
                     /||||||||||||||||||\
            With CETA extensions
            Maude-ceta 2.6 built: Nov 2 2011 12:54:56
	    Copyright 1997-2011 SRI International
                 Thu Jul 12 10:51:01 2012

	    Full Maude 2.6.1d July 7th 2012

The Maude Formal Environment 1.0
    Inductive Theorem Prover - July 20th 2010
    Sufficient Completeness Checker 2a - August 2010
    Church-Rosser Checker 3m - July 7th 2012
    Coherence Checker 3l - November 24th 2010
    Maude Termination Tool 1.5i - July 7th 2012

Maude>
```

## MFE Commands ##

The MFE extends Full Maude, and therefore all the functionality of Full Maude including its commands and facilities for loading modules, theories, and views, etc., is available in the MFE.

The MFE also provides the following commands:

  * `(select tool <tool-name> .)` sets the tool `<tool-name>` as active tool

  * `(MFE help .)` shows information on the commands available in the MFE

  * `(show global state .)` shows the state of the environment

If the input (between parentheses) cannot be parsed cannot be parsed by the MFE, then it is submitted to the currently active tool. In this way, the interaction with each tool in the environment remains almost as it was before the integration.

The user is referred to the help command or the tool documentation for further information on the tools already available in the MFE.

## Generic Tool Commands ##

We suggest the implementation of the following commands upon the integration of a new tool in the MFE, in addition to the tool's own list of commands:

  * `(<tool-name> help .)` shows information on the commands available in the tool.

  * `(show state .)` shows the state of the tool.

For instance, these commands are available for all tools currently available in the MFE.

## Specific Tool Commands ##

### ITP ###

Commands available in the ITP:

  * `(ITP help .)` shows the commands available for the ITP

**Goal commands**:

  * `(a-inst <name> with <subs> .)` instantiates a labeled universally quantified formula with a substitution
  * `(auto .)` applies the auto strategy
  * `(cnj .)` splits a conjunction into two subgoals
  * `(cns .)` performs universal quantifier elimination
  * `(cov on <pattern> .)` applies cover set induction by assuming the module has no equational attributes in the operators
  * `(cov* on <pattern> .)` applies cover set induction and then the auto strategy by assuming the module has no equational attributes in the operators
  * `(cov-split on <pattern> split <split-patterns> .)` applies cover set induction with split patterns by assuming the module has no equational attributes in the operators
  * `(cov-split* on <pattern> split <split-patterns> .)` applies cover set induction with split patterns and then the auto strategy by assuming the module has no equational attributes in the operators
  * `(cov using <names> on <pattern> .)` applies cover set induction with alternative constructors by assuming the module has no equational attributes in the operators
  * `(cov* using <names> on <pattern> .)` applies cover set induction with alternative constructors and then the auto strategy by assuming the module has no equational attributes in the operators
  * `(cov-split using <names> on <pattern> split <split-patterns> .)` applies cover set induction with alternative constructors and split patterns by assuming the module has no equational attributes in the operators
  * `(cov-split* using <names> on <pattern> split <split-patterns> .)` applies cover set induction with alternative constructors and split patterns and then the auto command by assuming the module has no equational attributes in the operators
  * `(ctor-def <name> : A{<x>:<s>} (E{<y1>} <t1>=<x> & <cond1>)...(E{<yn>} <tn>=<x> & <condn>) .)` adds an alternative constructor declaration
  * `(ctor-term-split <var> .)` performs constructor splitting
  * `(def-equiv <p> on <var> .)` defines an equivalence relation on a commutative symbol of a sort
  * `(disable <rule-name> .)` disables an equation for rewriting
  * `(e-inst with <sub> .)` performs existential instantiation
  * `(enable <rule-name> .)` enables an equation for rewriting
  * `(equiv-propagate .)` propagates facts implied by transitivity of an equivalence relation
  * `(eq-split on <pattern> .)` instantiates universally quantified variables to better match the left hand side of the equations
  * `(eq-split* on <pattern> .)` instantiates universally quantified variables to better match the left hand side of the equations and then the auto strategy
  * `(goal <label> : <mod-name> |- <formula> .)` introduces a goal
  * `(imp .)` adds the hypothesis as equations of the module
  * `(ind on <var> .)` inducts structurally on a variable
  * `(ind* on <var> .)` inducts structurally on a variable and then applies the auto strategy
  * `(lem <name> : <formula> .)` introduces a lemma
  * `(red <term> .)` reduces a term
  * `(sel <goal-name> .)` selects a goal
  * `(set-default-constructor <name> .)`
  * `(show-all <name> .)` shows all goals in a proof
  * `(show-hyps <name> .)` shows hypothesis in a proof
  * `(show-rules with <name> .)` shows rules with a name
  * `(split on <bool-formula> .)` splits on a Boolean formula

**Proof commands**:

  * `(new-goal <label> : <mod-name> |- <formula> .)` adds a goal
  * `(sel-proof <proof-id> .)` selects a proof
  * `(ITP show state .)` shows the state of the ITP
  * `(ITP trust <goal-name> .)` trusts a goal

### SCC ###

Commands available in the SCC tool, for `<mod-name>` denoting the name of an equational theory `(Sigma, E U A)`:

  * `(SCC help .)` shows the commands available for the SCC
  * `(scc <mod-name> .)` checks the sufficient completeness and the freeness of constructors of the specified module
  * `(select <mod-name> .)`selects the module with the given name
  * `(submit .)` submits the sort-decreasingness assertion to the CRC and the termination assertion to the MTT for the selected module
  * `(trust .)` trusts the selected module to be suffiently complete and to have free equational constructors

### CRC ###

Commands available in the CRC:

  * `(CRC help .)` shows the commands available for the CRC
  * `(ccr .)/(check Church-Rosser .)` checks the Church-Rosser property of the current module
  * `(ccr <mod-name> .)/(check Church-Rosser <mod-name> .)` checks the Church-Rosser property of the specified module
  * `(show cps .)/(show critical pairs .)` shows the critical pairs for the last check Church-Rosser command.
  * `(show all cps .)/(show all critical pairs .)` shows the status of all critical pairs for the last check Church-Rosser command
  * `(show mas .)/(show membership assertions .)`shows the membership assertions of the last check Church-Rosser command
  * `(show all mas .)/(show all membership assertions .)` shows the status of all membership assertions of the last check Church-Rosser command
  * `(select <mod-name> .)` sets the specified module as the current module of the CRC

### ChC ###

Commands available in the ChC:

  * `(ChC help .)` shows the commands available for the ChC
  * `(cch .)/(check coherence .)` checks the coherence property of the default module
  * `(cch <mod-name> .)/(check coherence <mod-name> .)` checks the coherence property of the specified module
  * `(cgch .)(check ground coherence .)` checks the ground coherence property of the current module
  * `(cgch <mod-name> .)/(check ground coherence <mod-name> .)` checks the ground coherence property of the specified module
  * `(show cps .)/(show critical pairs .)` shows the critical pairs of the last check coherence or ground coherence command after rewritten
  * `(show all cps .)/(show all critical pairs .)` shows the critical pairs of the last check coherence or ground coherence command before rewritten
  * `(select <mod-name> .)` sets the specified module as the current module of the ChC

### MTT ###

Commands available in the MTT:


  * `(MTT help .)` shows the commands available for the MTT
  * `(ct .)/(check termination .)` checks the termination of the current module
  * `(ct <mod-name> .)/(check termination <mod-name> .)` checks the termination of the specified module.
  * `(ctf .)/(check termination functional part .)` checks the termination of the functional part of the current module
  * `(ctf <mod-name> .)/(check termination functional part <mod-name> .)` checks the termination of the functional part of the specified module
  * `(show state .)` shows the state of the MTT
  * `(show proof .)` shows the termination proof for the last check termination command
  * `(select proof <module> .)` sets the specified module as the current module of the MTT
  * `(select external tool <tool> .)` sets the specified external tool as the current backend tool of the MTT (the specified `<tool>` must be one of the tools in your `mfe.config` file).
  * `(show transformation graph .)` shows the transformations available as a graph (use semicolons to enter paths, e.g., `C;A;B`, `OS;T;B;O-L`, ...).
  * `(show current path .)` shows the current checking path
  * `(select path <path> .)` sets the path to be used in termination checks (use the show-transformation-graph command for the available transformations). By default, the path for termination checks is `C;U;B`.
  * `(trust .)` assumes that the current module has been proved terminating