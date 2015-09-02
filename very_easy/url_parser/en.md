URL are very common strings with a simple syntax:
scheme://[username:password@]domain[:port]/path?query_string#fragment_id
This task (which has nothing to do with URL encoding or URL decoding) is to parse a well-formed URL to retrieve the relevant information scheme, domain, path,...
According to the standards, the characters [!*'();:@&=+$,/?%#[]] only need to be percent-encoded in case of possible confusion. So warn the splits and regular expressions. Note also that, the path, query and fragment are case sensitive, even if the scheme and domain are not.
The way the returned information is provided (set of variables, array, structured, record, object,...) is language dependent and left to the programer, but the code should be clear enough to reuse.
Extra credit is given for clear errors diagnostic.

Here is the official standard: https://tools.ietf.org/html/rfc3986,
and here a simpler BNF http://www.w3.org/Addressing/URL/5_URI_BNF.html.

Test cases
According to T. Berners-Lee

    foo://example.com:8042/over/there?name=ferret#nose should parse into:
    scheme = foo
    domain = example.com
    port = :8042
    path = over/there
    query = name=ferret
    fragment = nose
    urn:example:animal:ferret:nose should parse into:
    scheme = urn
    path = example:animal:ferret:nose
    
other must parse include:

    jdbc:mysql://test_user:ouupppssss@localhost:3306/sakila?profileSQL=true
    ftp://ftp.is.co.za/rfc/rfc1808.txt
    http://www.ietf.org/rfc/rfc2396.txt#header1
    ldap://[2001:db8::7]/c=GB?objectClass=one&objectClass=two
    mailto:John.Doe@example.com
    news:comp.infosystems.www.servers.unix
    tel:+1-816-555-1212
    telnet://192.0.2.16:80/
    urn:oasis:names:specification:docbook:dtd:xml:4.1.2