# Three examples of clearer replies

[简体中文](examples.md)

These examples are written by hand to illustrate the writing style the prompt asks for.

## Explain a technical idea

**Question** — If negative feedback lowers an amplifier's gain, why does it make the gain more stable?

**Harder to read**

> Negative feedback trades excess open-loop gain for reduced closed-loop sensitivity to component parameters.

**Clearer**

> Adding negative feedback lowers the gain. It also makes the gain less sensitive to changes in the components. Suppose the circuit warms up and the amplifier's own gain increases. That would raise the output. But the circuit feeds some of that larger output back and subtracts it from the input. The amplifier now sees a smaller effective input, which offsets part of the increase.
>
> Let A be the amplifier's gain before feedback and β the fraction of the output fed back. Where this simple model applies, the gain with feedback is A/(1 + Aβ). If Aβ is much greater than 1, the result is close to 1/β. The feedback fraction then has more influence on the final gain than the amplifier's own gain does.

## Explain what a research result supports

**Question** — On the same data, my baseline scored 82.0% and the new method scored 82.8%. Can I say the new method is better?

**Harder to read**

> A single metric improvement is insufficient to establish method superiority. Verify across seeds and report statistical significance.

**Clearer**

> You can say that the new method scored 0.8 percentage points higher on this validation run. To find out whether the improvement holds across training runs or data splits, check how much the difference moves when you change those conditions.
>
> Start with the same data split, metric, and tuning budget for both methods. Train both with the same set of random seeds, and record the difference for each pair of runs. If one method consistently comes out ahead, you can report that pattern. If the lead changes hands, show the spread. If you used the validation set repeatedly to choose a method, use a held-out test set for the final check.

## Report a code change

**Scenario** — An earlier request sometimes finishes late and overwrites the results for the newest search.

**Harder to read**

> Improved concurrent request coordination and search state consistency. Tests passed.

**Clearer**

> The search box now shows results for the last thing you typed. If you search for “lamp” and then “lampshade,” the lampshade results stay on screen even if the lamp request comes back later.
>
> Each search gets a new request ID. When a response arrives, the page updates only if the response belongs to the latest request. To check the fix, make “lampshade” return first and confirm that the later “lamp” response leaves the results alone.
