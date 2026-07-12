# Contributing to Schroedinger Sync

Thanks for your interest. This project is small, security-sensitive, and
**dual-licensed** — which makes the contribution rules a little stricter than a
typical repo. Please read this before opening a pull request.

## 1. You must sign the CLA (non-negotiable)

Every external contribution requires agreement to the
[Contributor License Agreement](CLA.md). **Pull requests without an agreed CLA
will not be merged — no exceptions.**

Why: the project is offered publicly under the **AGPLv3** *and* reserved for a
separate **commercial licence** for organisations that want to embed it in
closed-source products. Dual licensing only works if one party can relicense
*all* the code. A single un-agreed contribution would splinter that right and
break the commercial path permanently. The CLA keeps it consolidated. See
[CLA.md → "Why this exists"](CLA.md#why-this-exists).

How to sign: follow [CLA.md → "How to sign"](CLA.md#how-to-sign). In short —
add to each commit:

```
Signed-off-by: Your Name <your.email@example.com>
CLA-1.0: I agree to the terms of CLA.md
```

and state in the PR description that you have read and agree to the CLA.

## 2. Security invariants are enforced in code, not prose

This tool decrypts a DPAPI-protected credential store. Its safety rests on
invariants that are tested in `security_test.go` (see [SECURITY.md](SECURITY.md)):
claude.ai-only network egress, the hardcoded headless flag, credential redaction,
and the non-importable-package check.

- **Do not** weaken, bypass, or delete a security test to make a change pass.
- **Do not** add network egress to any host other than claude.ai.
- A change that touches auth, the cookie store, CDP, or egress will get extra
  scrutiny and must keep every security invariant green.

## 3. Development

```
go build -trimpath -ldflags "-s -w" -o schroedinger-sync.exe .   # build
go test -v ./...                                                  # all tests must pass
```

- Windows / x64 only (the tool is inherently Windows-DPAPI-bound).
- Match the surrounding Go style; keep functions focused and the diff minimal.
- New behaviour needs a test. Security-relevant behaviour needs a security test.
- Keep commits scoped and messages conventional (`feat:`, `fix:`, `docs:`,
  `test:`, `refactor:`, `chore:`).

## 4. Before you open a PR

- [ ] `go test -v ./...` is green (including security invariants).
- [ ] CLA agreed (sign-off + CLA line on every commit, statement in PR).
- [ ] The change is Windows-only-safe and adds no non-claude.ai egress.
- [ ] Docs/CHANGELOG updated if behaviour changed.

## 5. Reporting security issues

Do **not** open a public issue for a vulnerability. Follow the private disclosure
process in [SECURITY.md](SECURITY.md).
