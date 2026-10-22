# Web Security Notes

## 1. What is Web Security?
Web security means protecting websites, web applications, servers, and user data from attacks.

## 2. Path Traversal

**What it is:** A vulnerability that allows an attacker to access files outside the intended directory.

**How it happens:** An application uses user input to construct a file path without properly restricting which files can be accessed.

**Example payload in an authorized lab:**
```text
../../../etc/passwd
```

**Possible impact:**
- Unauthorized file access
- Exposure of sensitive configuration files
- Disclosure of credentials stored in files

**How to identify it:**
1. Observe requests that load or download files.
2. Identify parameters such as `filename` or `file`.
3. Test controlled traversal variations in an authorized lab.
4. Check whether the response exposes an unintended file.

**Mitigation:**
- Use an allowlist of permitted files.
- Resolve paths to canonical absolute paths.
- Verify that the resolved path remains inside the permitted directory.
- Restrict application file permissions.

## 3. SQL Injection (SQLi)

**What it is:** A vulnerability where untrusted input changes the structure of a database query.

**Example of an unsafe query:**
```sql
SELECT * FROM users WHERE username = 'USER_INPUT';
```

If input is concatenated directly into SQL, an attacker may alter the query.

**Possible impact:**
- Unauthorized access to records
- Authentication bypass
- Modification or deletion of data
- Exposure of sensitive information

**How to identify it:**
1. Find input fields and URL parameters that may reach database queries.
2. Test harmless input variations in a controlled lab.
3. Observe database errors and unexpected response changes.
4. Confirm findings using authorized testing methods.

**Mitigation:**
- Use parameterized queries or prepared statements.
- Avoid constructing SQL queries through string concatenation.
- Apply least-privilege database permissions.
- Handle errors without exposing database details.

## 4. Cross-Site Scripting (XSS)

**What it is:** A vulnerability that allows attacker-controlled JavaScript to execute in another user's browser under the website's origin.

**Types:**
- Reflected XSS: input is returned in an immediate response.
- Stored XSS: malicious input is saved and later displayed.
- DOM-based XSS: unsafe client-side JavaScript causes execution.

**Possible impact:**
- Actions performed as the victim
- Exposure of accessible page data
- Phishing or interface manipulation
- Abuse of a user's authenticated session

**How to identify it:**
1. Identify places where user input appears in a page.
2. Test in an authorized lab with harmless proof-of-execution input.
3. Determine whether the input is interpreted as code or displayed as text.

**Mitigation:**
- Apply context-appropriate output encoding.
- Sanitize HTML when rich HTML is required.
- Avoid unsafe DOM sinks.
- Use Content Security Policy as an additional layer of defense.

## 5. Authentication Security

**What it is:** Authentication verifies a user's identity.

**Common weaknesses:**
- Weak or reused passwords
- Missing rate limits
- Poor password-reset controls
- Multi-factor authentication not enabled
- Username enumeration
- Insecure session management

**How to test in an authorized lab:**
1. Review login and password-reset behavior.
2. Check rate limiting and error messages.
3. Examine session-cookie security attributes.
4. Verify that logout invalidates the session.

**Mitigation:**
- Use strong password hashing, such as Argon2id.
- Implement rate limiting and multi-factor authentication.
- Use secure session cookies.
- Rotate or invalidate sessions when appropriate.

## 6. Web Security Testing Workflow

1. Map the application's pages and input points.
2. Inspect HTTP requests and responses.
3. Identify potential attack surfaces.
4. Test suspected vulnerabilities safely.
5. Record evidence and security impact.
6. Recommend remediation.
7. Retest after fixes.

## Learning Resources
- OWASP Top 10: https://owasp.org/www-project-top-ten/
- PortSwigger Web Security Academy: https://portswigger.net/web-security

## Key Takeaway
Understand how each vulnerability works, how to reproduce it safely, what impact it causes, and how developers can prevent it.
