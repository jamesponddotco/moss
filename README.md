# Moss, the Go expert

> **Note**: The use of GPTs requires a [ChatGPT Plus subscription](https://openai.com/chatgpt).

**[Moss](https://chat.openai.com/g/g-PAHVE3a64-moss-the-go-expert)** is a [custom version of ChatGPT](https://openai.com/blog/introducing-gpts) that acts as a senior, inquisitive, and clever Go pair programmer. It's fed with [several megabytes of Go knowledge](data/), is updated every Tuesday, and should be quite useful to Go programmers of all levels.

**[Add Moss to your GPT list](https://chat.openai.com/g/g-PAHVE3a64-moss-the-go-expert)**.

## Knowledge

ChatGPT has a knowledge cut off date of April 2023, which means a lot of information that came after that isn't available to it, such as usage of the [log/slog](https://pkg.go.dev/log/slog) module. To work around that limitation, **[Moss](https://chat.openai.com/g/g-PAHVE3a64-moss-the-go-expert)** is fed with several articles, books, documentation, and other tidbits of information from around the web.

[Send a patch](https://lists.sr.ht/~jamesponddotco/moss-devel) if you want something included in its knowledge base.

Custom GPTs have a limit of 10 uploaded files, so we concatenate every category into its own file, having a total of 5 files only. There is no information on size limit right now.

### Articles & Pages

- [A few bytes here, a few there, pretty soon you’re talking real memory](https://dave.cheney.net/2021/01/05/a-few-bytes-here-a-few-there-pretty-soon-youre-talking-real-memory)
- [Better HTTP server routing in Go 1.22](https://eli.thegreenplace.net/2023/better-http-server-routing-in-go-122/)
- [Bitmasks for nicer APIs](https://www.arp242.net/bitmask)
- [Clear is better than clever](https://dave.cheney.net/2019/07/09/clear-is-better-than-clever)
- [Code coverage for Go integration tests](https://go.dev/blog/integration-test-coverage)
- [CodeReviewComments](https://github.com/golang/go/wiki/CodeReviewComments)
- [CodeReviewConcurrency](https://github.com/golang/go/wiki/CodeReviewConcurrency)
- [CommonMistakes](https://github.com/golang/go/wiki/CommonMistakes)
- [Common pitfalls in Go benchmarking](https://eli.thegreenplace.net/2023/common-pitfalls-in-go-benchmarking/)
- [Constant Time](https://dave.cheney.net/2019/06/10/constant-time)
- [Coverage profiling support for integration tests](https://go.dev/testing/coverage/)
- [Deconstructing Type Parameters](https://go.dev/blog/deconstructing-type-parameters)
- [Don’t force allocations on the callers of your API](https://dave.cheney.net/2019/09/05/dont-force-allocations-on-the-callers-of-your-api)
- [Effective Go](https://go.dev/doc/effective_go)
- [Everything You Always Wanted to Know About Type Inference - And a Little Bit More](https://go.dev/blog/type-inference)
- [Forward Compatibility and Toolchain Management in Go 1.21](https://go.dev/blog/toolchain)
- [Go 1.21 is released!](https://go.dev/blog/go1.21)
- [Go Proverbs](https://go-proverbs.github.io/)
- [Go testing style guide](https://www.arp242.net/go-testing-style)
- [Inlining optimisations in Go](https://dave.cheney.net/2020/04/25/inlining-optimisations-in-go)
- [Logging in Go A Comparison of the Top 8 Libraries](https://betterstack.com/community/guides/logging/best-golang-logging-libraries/)
- [Logging in Go with Slog The Ultimate Guide](https://betterstack.com/community/guides/logging/logging-in-go/)
- [Perfectly Reproducible, Verified Go Toolchains](https://go.dev/blog/rebuild)
- [Prefer table driven tests](https://dave.cheney.net/2019/05/07/prefer-table-driven-tests)
- [Profile-guided optimization in Go 1.21](https://go.dev/blog/pgo)
- [Profile-guided optimization](https://go.dev/doc/pgo)
- [Retrieval Augmented Generation in Go](https://eli.thegreenplace.net/2023/retrieval-augmented-generation-in-go/)
- [Structured Logging with slog](https://go.dev/blog/slog)
- [The Go Programming Language Specification](https://go.dev/ref/spec)
- [The Zen of Go](https://dave.cheney.net/2020/02/23/the-zen-of-go)
- [Use internal packages to reduce your public API surface](https://dave.cheney.net/2019/10/06/use-internal-packages-to-reduce-your-public-api-surface)

### Books

- [100 Go Mistakes](https://100go.co/)
- [Go Perfbook](https://github.com/dgryski/go-perfbook/blob/master/performance.md)

### Module documentation

- [errors](https://pkg.go.dev/errors)
- [log/slog](https://pkg.go.dev/log/slog)
- [testing/slogtest](https://pkg.go.dev/testing/slogtest)


### Style guides

- [Google's style guide](https://google.github.io/styleguide/go/)
- [Uber's style guide](https://github.com/uber-go/guide)

### Workshops

- [High Performance Go Workshop](https://dave.cheney.net/high-performance-go-workshop/dotgo-paris.html)
- [Practical Go Real world advice for writing maintainable Go programs](https://dave.cheney.net/practical-go/presentations/gophercon-singapore-2019.html)

## Prompt

**[Moss](https://chat.openai.com/g/g-PAHVE3a64-moss-the-go-expert)** is a custom version of ChatGPT, and as such, it has a custom prompt tailored to a Go programmers' needs.

```
You're Moss, an expert Go developer that is the user's senior, inquisitive, and clever pair programmer. Getting correct responses is very important to the user's career, as they're under a lot of stress.

Coding process:
1. Show concise step-by-step reasoning.
2. Prioritize tasks/steps you'll address in each response.
3. Finish one file before the next.
4. If needed, interrupt yourself and ask to continue.

When providing advice, reviewing, or writing code, adhere to the following guidelines:

- Follow the Uber Go style guide.
- Use the latest version of Go.
- Follow Go best practices for writing idiomatic code.
- Follow DRY principles.
- Do not use deprecated modules and functions.
- Properly handle errors.
- Include structured logging with log/slog where appropriate.
- Include all the code, do not skip details or methods for brevity.
- Don't apologize for errors, fix them.
- Include comments in the code. Comments should tell the reader why we implemented the code that way, not what the code does.
- Do not include TODO comments; write the code instead.
- Comments MUST describe purpose, not effect.

Bias towards the most efficient solution, with security and performance as a priority.

When writing tests adhere to the guidelines above, but add the guidelines below:

- Make the test a black-box test, unless asked otherwise.
- Name the test package with a _test suffix.
- Do not use third-party packages such as stretchr/testify.
- Always use methods like t.Parallel, t.Cleanup, t.Setenv, and t.TempDir.
- If using t.Setenv, do not use t.Parallel.
- Use tt := tt to capture range variable.
- Never compare error vlaues directly; use errors.Is() instead.

Write concise answers and speak in a casual, unapologetic, and assertive tone. Minimize any other prose. Respond in Markdown.
```

[Send a patch](https://lists.sr.ht/~jamesponddotco/moss-devel) if you want to improve the above prompt.

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for details.

## Resources

The following resources are available:

- [Support and general discussions](https://lists.sr.ht/~jamesponddotco/moss-discuss).
- [Patches and development related questions](https://lists.sr.ht/~jamesponddotco/moss-devel).
- [Instructions on how to prepare patches](https://git-send-email.io/).
- [Feature requests and suggestions](https://todo.sr.ht/~jamesponddotco/moss).

---

This repository is released under the [CC0 license](LICENSE.md).
