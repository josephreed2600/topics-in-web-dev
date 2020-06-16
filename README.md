# <span id="Foreword">Foreword</span>

I would like to see these topics covered either in relevant existing courses or in a new course or series, maybe "Topics in Web Development", at Neumont College of Computer Science, targeted towards students in the BS in Web Design and Development degree program.

This repository will be used as a staging ground for curriculum items. Modules will be constructed in directories in the top level of the project tree. Modules will contain lesson plans, code examples, exercises, labs, and collections of resources.

# <span id="Semantics">Semantics</span>

This module discusses writing meaningful content.

  - What does "semantic" mean and why is it important?
  - Semantic HTML tags and where/how/why to use them
    - Use semantically meaningful markup even if it means more work styling; that’s what CSS is meant for. Browser defaults can change and vary anyways.
  - "Divitis" and cluttering the DOM with tags whose only purpose is styling
    - Good markup should usually not need to be changed to accommodate styling
    - A document should be usable and meaningful without styles
    - Importance of CSS Grid to avoiding markup antipatterns
  - Accessibility considerations
    - Where accessibility is important
      - Static content/information vs. web application
    - Implications of accessibility requirements on design choices
      - What is the purpose of this page? Why does the user want to use this page?
      - How can I organize the page to make it the most useful?
    - ARIA
    - Tools and resources for accessibility validation, guidelines, and information
      - [WAVE Web Accessibility Evaluation Tool][WAVE]
      - [Web Content Accessibility Guidelines (WCAG) Overview][WCAG]
    - Considerations for Adobe PDF documents
      - Availability of tools
        - [Adobe Acrobat Pro DC accessibility remediation tools][Acrobat]
        - [CommonLook PDF accessibility remediation tools][CommonLook]
        - [PDF Accessibility Checker, a free validator][PAC]
        - [Active project for the LaTeX accessibility package, for generating accessible PDFs][LaTeX]
      - Alternative formats, such as HTML
    - No validator can guarantee compliance with all requirements; many criteria require the analysis of a human
  - Semantics of HTTP response codes

# <span id="Performance">Performance</span>

This module discusses performance considerations for improving a site's speed and user experience.

  - How does the user perceive their experience? What are the most important contributing factors?
    - What can we do to anticipate the user's next move and prepare for it?
  - Performance benchmarks and how to test them
    - DCL, FCP, LCP, TTI, TBT, CLS, etc.
    - [Google PageSpeed Insights/Lighthouse][Lighthouse]
  - Modern technologies
    - Caching
      - Browser cache, `Cache-Control` header
      - Cache API/Service workers
      - Server-side caching and approaches
      - When should I store data on the client machine? What kinds of data should be stored?
    - HTTP/1.1/2/3
      - What does a request look like?
      - Headers that are and aren't useful
        - Compression: `Accept-Encoding` header
    - Reverse proxy
        - Cache
        - HTTPS
        - HTTP/2
        - Do these things belong in the application itself or in the reverse proxy?
    - HTTPS and its performance implications
  - Asset optimization
    - Image formats, compression, and support
    - Chaining critical requests
      - Deferring scripts
        - Modular scripts
    - Link tags
      - Media queries
      - `type="preload"` and `type="prefetch"`
        - Semantics vs. common applications
      - `disabled`
    - Impact of third-party scripts, styles, and frameworks
  - Design for mobile first

# <span id="CSS">CSS analysis</span>

This module discusses CSS through the lens of code quality.

  - Does (my) CSS create any major performance concerns? How can we know?
  - How can I write more efficient and maintainable CSS?
    - Precedence
    - Organization
    - Modularity
    - Antipatterns

# <span id="SEO">SEO</span>

This module discusses the importance of and techniques related to search engine optimization (SEO).

  - What is SEO and why does it matter?
  - Tools and resources for tracking, analyzing, and improving rankings
  - What is crawling?
    - Site map
    - robots.txt

# <span id="DevOps">DevOps: Exposing a site to the Internet</span>

This module discusses the process of turning a local web server into an Internet-accessible web site.

  - How do I register a domain name?
    - Example: [Freenom][Freenom] offers free domain names under five (uncommon) TLDs
  - DNS fundamentals
    - Record types
    - TTLs
    - Zones/authority
    - Syntax/how to read
    - Selecting a DNS provider
      - Example: [Hurricane Electric][dns.he.net], lots of services for free
  - Port forwarding on a home router
    - Configuring enterprise equipment is beyond the scope of this degree; see IS
  - Setting up a reverse proxy
    - Example: NGINX
  - Tools and resources for troubleshooting deployment issues
    - ping, dig, nslookup, whois, nmap

# <span id="Security">Security</span>

This module discusses various topics in securing connections and stored data.

  - SSL and TLS
    - History
    - Types of certificates: DV, OV, EV
    - What is a CA?
    - When is HTTPS necessary/advisable?
    - How does adding or removing HTTPS affect features?
      - Example: Geolocation API is only available in secure contexts
    - How can I get a certificate?
      - Example: [Let's Encrypt][letsencrypt], Certbot
  - Content Security Policy
    - What is XSS?
  - CORS
  - CSRF
  - Validation and sanitization of user input
    - Server-side vs. client-side
    - Asynchronous validation (related to [Performance](#Performance))
  - Protecting API keys and other sensitive technical data
  - Perspectives on password requirements
    - "At least one character from each of these categories"
    - "Correct horse battery staple"
  - Safe storage of PII (related to [Legal](#Legal))
    - Hashing and proper handling techniques for passwords
  - How to handle a data breach
    - If you're a site administrator for a small company, this may fall to you, or you may be asked to advise other teams
    - What to share with the public/media/employees, and when
      - Handling rumors
    - Patch the hole, but don't stop there
    - Hire a third party to investigate
    - Research laws related to the breached data
    - Have a comprehensive set of breach plans ready before collecting data

# <span id="Legal">Legal/regulatory compliance</span>

This module discusses legal considerations that affect web site implementation and administration.

  - Cookie notices
    - When do they apply?
      - What forms of local storage count?
      - What forms of stored data count?
      - What laws require them?
  - Major laws affecting web sites:
    - DMCA
    - GDPR
    - ADA 508

# <span id="Readings">Readings</span>

  - [Designed to Last][Designed to Last]: A manifesto describing ideals to bear in mind while writing content for the web, with the goal of improving robustness to time and change.

[WAVE]: https://wave.webaim.org/
[WCAG]: https://www.w3.org/WAI/standards-guidelines/wcag/
[Acrobat]: https://www.adobe.com/accessibility/products/acrobat/using-acrobat-pro-accessibility-checker.html
[CommonLook]: https://commonlook.com/accessibility-software/
[PAC]: https://www.access-for-all.ch/en/pdf-lab/pdf-accessibility-checker-pac.html
[LaTeX]: https://github.com/AndyClifton/accessibility
[Lighthouse]: https://developers.google.com/speed/pagespeed/insights/
[Freenom]: https://www.freenom.com/en/index.html?lang=en
[dns.he.net]: https://dns.he.net/
[letsencrypt]: https://letsencrypt.org/
[Designed to Last]: https://jeffhuang.com/designed_to_last/
