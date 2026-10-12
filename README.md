# A web application for diagram reasoning

Tested with Edge 155.0.4283.45, and Rocq 9.2.


## Example of sort declarations

The JavaScript file that is loaded by default can be found [here](examples/default_sorts.js).

## Example: Proof that composition of monomorphisms compose

- Open app.html in a browser. 
- Open the drawing MonoComp. 
- Click on the button "Start Proof" in the panel on the right of the screen. This action automatically opens the list of "Applicable rules".
- Start by applying the rule AddMono on h. This solves the main goal (since it adds the mono tag on h), but opens a new subgoal, introducing two morphisms f and g that share the same composite with h. The Goal layer consists of the equality f and g: this is what we need to prove.
- Apply all the possible Comp rules. Thanks to the (checked) filter no-progress, the web app only displays the rules that add new stuff. For example, if the composite of f and m is already on the canvas, then it will not suggest the rule application that adds this composite.
- To make the drawing more readable, at any time you can edit the position or the bend attribute of any vertex or morphism by selecting it in the list of artefacts (on the left), and adjust its value in the Inspector panel, located below the (collapsible) list of applicable rules.
- Apply the remaining two associativity rules.
- In the list of artefacts, click on the button ⨝ next to the morphism fmn to merge it with u. The two morphisms are then merged into a single one called "fmn, u". Then do the same with gmn. Note that the web app checks that they are provably equal.
- Apply the rule UseMono to deduce fm = gm 
- Merge fm with gm
- Apply the rule UseMono to conclude that f = g. The proof is done: the window is opened with Rocq script that you can check.

The merging steps can be skipped if "Flexible match" is checked at the top of the panel Applicable Rules.

## Example: Pullback characterisation of monomorphisms

- Open app.html in a browser
- Delete all the drawings: click on the checkbox at the top of the drawing store to select all the drawings, and then click on Delete.
- Load the file `examples/pbkfrommono_monofrompbk.json`
- Complete the proofs of PbkFromMono and MonoFromPullback that provide a pullback characterisation of monomorphisms: a morphism f is mono if and only if the commutative square `id ; f = id ; f` is a pullback.


