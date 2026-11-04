# Roadmap

This page is for maintainers. It is the product's rolling roadmap and the only place that records planned and
deferred work and its state. The user documentation describes what the product does today; nothing on this page is
available until its row says so.

## Status values

**Contract**

- `pending`: the item needs a reviewed design before work starts; the link names the current source.
- `ready`: the linked design holds a reviewed contract for the item.
- `not needed`: the Work cell states the change completely.
- `—`: delivered before this roadmap; the code and user documentation define the behaviour.

**Implementation**

- `planned`: none of the item is in the product.
- `partly implemented`: part of it is; the evidence names which part.
- `implemented`: the item is in the product.

## Maintaining the roadmap

- One row per planned item. IDs never change and are never reused; a split gets new IDs and the old one leaves the
  table. A need in another repository is written `<repository>:<ID>`.
- A row changes in the commit that changes its item: its scope, its needs, its contract or its implementation. Its
  evidence names in-repository witnesses (tests, documents, reports); a row never names the commit that changes it.
- An implemented row may leave the table once a release has shipped it and no row needs it; the repository's changelog
  or its dated history reports keep it.
- Status words live only on this page. Designs state requirements; the changelog or the dated history reports say what
  shipped.
  When this page and a design disagree on order or needs, this page wins; on behaviour, the design wins.
- The page records product facts, not how the work is run: an effort's plans, reviews and CI results stay in its own
  records.
- An item moves from Deferred to Planned on the maintainer's decision, and gets its ID then.

## Planned

Nothing is scheduled yet.

| ID | Work | Needs | Contract | Implementation | Evidence |
|---|---|---|---|---|---|

## Deferred

Not scheduled. One entry per item: what it is, and why it is not scheduled or what would make it worth doing.

- **Single-route TE sizing**: offer a separate link-sizing setting that sends each demand over one deterministically
  selected cheapest route, with a clear distinction from the current equal split across cheapest next hops; no current
  consumer needs that sizing model.
- **Expose advanced NetGraph scenario settings**: expose scenario units and routing-domain/WCMP-controller
  configuration, and document how failure states and simultaneous interaction pass through selected workflow
  definitions; add first-class settings only for a concrete generated-scenario use, since custom workflow fields already
  pass through.
- **Shared hardware validation**: decide whether to adopt NetGraph's explorer rules for node capacity, ports and optics
  in place of the local audits, explicitly resolving enabled-link behavior, zero limits, tolerances and exact optic
  coverage; this changes which generated scenarios pass, so it needs an agreed validation contract before
  implementation.
- **Cross-Python traffic-volume rounding**: make gravity and hose volume generation identical across supported Python
  versions only if last-bit differences begin to affect a consumer or reproducible artifacts; some builtin sums still
  vary by interpreter, but replacing them solely for byte identity would change existing volumes without a demonstrated
  downstream benefit.
- **Publishing trigger instructions**: document package publication from a published GitHub release and the manual Test
  PyPI path, matching `.github/workflows/publish.yml`; defer to the next release-instruction update.
