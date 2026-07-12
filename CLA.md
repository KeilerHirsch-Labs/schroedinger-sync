# Contributor License Agreement (Individual)

> **Not legal advice.** This document is adapted from the community-standard
> [Harmony Agreements](http://www.harmonyagreements.org/) HA-CLA-I template
> (individual contributor, "any licence" outbound option). It is provided so the
> project can offer the code under more than one licence (see [dual licensing](#why-this-exists)).
> Before it is relied on to sell or enforce a commercial licence, it should be
> reviewed by a qualified lawyer and bound to a real legal identity or entity
> (see [Open point](#open-point-legal-identity)).

This Contributor License Agreement ("Agreement") is between **You** (the individual
who submits a Contribution) and the **Project Maintainer** of *Schroedinger Sync*
(referred to as "We" / "Us" / "the Maintainer") — the sole copyright holder of the
project, publicly identified as **KeilerHirsch**.

By submitting a Contribution (a pull request, patch, or any other form of code,
documentation, or material) to this project, You agree to the terms below.

## 1. Definitions

- **"Contribution"** means any original work of authorship — including any
  modifications or additions to existing work — that You intentionally submit to
  the project for inclusion in, or documentation of, *Schroedinger Sync*.
- **"Submit"** means any form of communication sent to Us or our repositories
  (e.g. a pull request, a patch, an issue attachment), excluding communication
  clearly marked "Not a Contribution".

## 2. Copyright licence — and the right to relicense (the point of this CLA)

You retain ownership of the copyright in Your Contribution. Subject to that,
You grant to Us a **perpetual, worldwide, non-exclusive, royalty-free,
irrevocable** licence in Your Contribution to:

1. reproduce, prepare derivative works of, publicly display, publicly perform,
   and distribute Your Contribution and such derivative works; and
2. **sublicense and license Your Contribution — and derivative works of it —
   under any licence terms, including copyleft, permissive, commercial, and
   proprietary (closed-source) terms.**

Clause 2.2 is what allows the project to be **dual-licensed**: offered publicly
under the GNU AGPLv3, *and* offered to commercial users under a separate paid
commercial licence, without needing to track down and re-ask every past
contributor. Without this grant from every contributor, the project could not
lawfully be relicensed, and the commercial-licence path would be impossible.

## 3. Patent licence

You grant to Us and to recipients of software distributed by Us a perpetual,
worldwide, non-exclusive, royalty-free, irrevocable (except as stated in this
section) patent licence to make, have made, use, offer to sell, sell, import,
and otherwise transfer Your Contribution, where such licence applies only to
those patent claims licensable by You that are necessarily infringed by Your
Contribution alone or by combination of Your Contribution with the project.

If any entity institutes patent litigation against You or any other entity
alleging that Your Contribution, or the project to which You contributed,
constitutes direct or contributory patent infringement, then any patent licences
granted to that entity under this Agreement for that Contribution terminate as of
the date such litigation is filed.

## 4. Your representations

You represent that:

- You are legally entitled to grant the above licences.
- Each of Your Contributions is Your original creation.
- If Your employer has rights to intellectual property You create, You have
  either received permission to make the Contribution on behalf of that employer,
  or Your employer has waived such rights for Your Contribution.
- Your Contribution does not, to Your knowledge, violate any third party's
  copyrights, patents, trademarks, or other intellectual-property rights.

## 5. No obligation; disclaimer

We are not obligated to use Your Contribution. Your Contribution is provided
"AS IS", without warranty of any kind, express or implied, to the extent
permitted by applicable law. You are not expected to provide support for Your
Contribution, except to the extent You desire to do so.

## Why this exists

*Schroedinger Sync* decrypts a DPAPI-protected credential store — the trust bar
is high, so the source stays open under the **AGPLv3** for everyone to read and
run for free. At the same time, the project reserves the ability to offer a
**separate commercial licence** to organisations that want to embed or
redistribute the code inside a closed-source or SaaS product (something the
AGPLv3's network-copyleft otherwise forbids without releasing their own source).

Dual licensing only works if a single party holds the rights to relicense
**all** of the code. That is why every external contribution requires this CLA:
it keeps the relicensing right consolidated, so the commercial path stays open
and cannot be splintered by a single un-agreed contribution.

## How to sign

Until an automated CLA bot is configured, sign by asserting the
Developer-Certificate-of-Origin-style line in **every commit** of Your pull
request, and by stating in the pull-request description:

> I have read and agree to the Contributor License Agreement (CLA.md).

Add to each commit message:

```
Signed-off-by: Your Name <your.email@example.com>
CLA-1.0: I agree to the terms of CLA.md
```

Pull requests without an agreed CLA will not be merged. See
[CONTRIBUTING.md](CONTRIBUTING.md).

## Open point (legal identity)

For enforceability of an actual *commercial* licence sale, the "Maintainer" party
above must eventually be a real legal person or entity, not only the public
pseudonym *KeilerHirsch*. Binding this CLA to that identity/entity — and the
public trademark filing — are deliberately deferred steps (they expose real-world
identity) and should be done with legal counsel before the first commercial
licence is sold. The CLA text itself is valid to start collecting agreement now;
only the commercial-sale enforcement depends on that later binding.
