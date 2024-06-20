# Subfuzz

is a simple and efficient tool designed to generate potential subdomains by replacing a `FUZZ` placeholder in a given domain pattern with words from a specified wordlist. This is particularly useful for security testing and discovering hidden subdomains.

## Features

- **Flexible Pattern Replacement**: Replace `FUZZ` in your domain pattern with words from a wordlist.
- **Easy to Use**: Command-line interface for quick and straightforward use.
- **High Efficiency**: Generates subdomains quickly compared to traditional fuzzers.

## Installation

To get started with Subfuzz, you need to have Python 3 installed on your system. Follow these steps to install and run Subfuzz:

`git clone https://github.com/Vulnpire/subfuzz && cd subfuzz && chmod +x subfuzz && mv subfuzz /usr/bin/subfuzz`

## Usage

To use Subfuzz, you need to provide a domain pattern with the FUZZ placeholder and a wordlist file. The script will replace FUZZ with each word from the wordlist and print the generated subdomains.

## Arguments

    <domain_pattern>: The domain pattern containing FUZZ (e.g., subdomainFUZZ.domain.tld).
    -w, --wordlist: Path to the wordlist file containing words to replace FUZZ.

## Example

Suppose you have a wordlist wordlist.txt with the following content:


```
nl wordlist.txt
  1  test
  2  example
  3  demo
```

Running the command:

`subfuzz subdomain-FUZZ.example.com -w wordlist.txt`

Will produce the following output:

```
subdomain-test.example.com
subdomain-example.example.com
subdomain-demo.example.com
```

## Efficiency and Integration with Other Tools

Subfuzz is designed to be significantly faster than traditional fuzzers that test subdomain patterns against DNS resolvers directly. By quickly generating a comprehensive list of potential subdomains, you can pass this list to a DNS resolution tool like `dnsx` for validation and further processing.
