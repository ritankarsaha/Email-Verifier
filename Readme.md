# Email Verifier

This is a simple command-line tool written in Go that verifies email domains for various DNS records. It checks for the presence of MX, SPF, and DMARC records for a given domain.

## Usage

1. Clone the repository:

    ```shell
    git clone https://github.com/ritankarsaha/Email-Verifier.git
    ```

2. Build the executable:

    ```shell
    go build
    ```

3. Run the program:

    ```shell
    ./email-verifier
    ```

    Alternatively:- 

    ```shell
    echo -e "example.com\nanotherdomain.com" | ./domain-checker
    OR
    echo -e "example.com\nanotherdomain.com" | go run main.go
    ```

4. Enter the domain names you want to verify, one per line. The program will output the results in CSV format.

## Example

```shell
$ ./email-verifier
example.com
example.org
```

Output:

```
domain,hasMX,hasSPF,sprRecord,hasDMARC,dmarcRecord
example.com, true, true, "v=spf1 include:_spf.example.com -all", true, "v=DMARC1; p=reject; rua=mailto:dmarc@example.com"
example.org, false, false, "", false, ""
```

## Dependencies

This program uses the `net` package from the Go standard library for DNS lookups.


## Error Handling

If there is an error reading from the input or performing DNS lookups, the program logs the error and continues processing the next domain.
echo -e "example.com\nanotherdomain.com" | ./domain-checker


## AUTHOR

  RITANKAR SAHA - ritankarsaha
