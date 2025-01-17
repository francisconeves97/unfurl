Taken from: https://github.com/tomnomnom/hacks/blob/master/unfurl/README.mkd for ease of installation

# unfurl

Pull out bits of URLs provided on `stdin`

Install:

```
▶ go install github.com/francisconeves97/unfurl@latest
```

## Help

```
▶ unfurl -h
Format URLs provided on stdin

Usage:
  unfurl [OPTIONS] [MODE] [FORMATSTRING]

Options:
  -u, --unique   Only output unique values
  -v, --verbose  Verbose mode (output URL parse errors)

Modes:
  keys     Keys from the query string (one per line)
  values   Values from the query string (one per line)
  domains  The hostname (e.g. sub.example.com)
  paths    The request path (e.g. /users)
  format   Specify a custom format (see below)

Format Directives:
  %%  A literal percent character
  %s  The request scheme (e.g. https)
  %d  The domain (e.g. sub.example.com)
  %P  The port (e.g. 8080)
  %p  The path (e.g. /users)
  %q  The raw query string (e.g. a=1&b=2)
  %f  The page fragment (e.g. page-section)

Examples:
  cat urls.txt | unfurl keys
  cat urls.txt | unfurl format %s://%d%p?%q
```
