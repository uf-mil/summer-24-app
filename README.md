# Summer 2024 Application for the Software Team of the Machine Intelligence Laboratory

Hello! Thanks for checking our lab, we appreciate your interest in
applying to work with us. To gauge the skills of our software members,
we ask all incoming applicants to complete a short coding challenge to
assess their skills at programming. This helps us ensure that all our
members have a baseline requisite of experience.

## Challenge
You are going to develop an inventory management system for
managing robotics parts and inventory. Most robotics are composed of
hundreds or thousands of parts, which will eventually break, get lost,
or need backups. Therefore, you'll demonstrate your coding proficiency
by developing an inventory management system for MIL.

Managing parts and inventory is a significant challenge
at MIL, especially for our electrical and mechanical teams. We have
thousands of parts in our lab and realizing that we are out of a certain
component right when we need it can be a disastrous situation!

## Terminology

-   **Part**: An individual, unique item that can be used to support a
    robotic system. If two items they have the exact same
    characteristics, they are the same "part." For example, a "3ft Black
    HDMI cable" is a part.

-   **SKU**: "Stock Keeping Unit". Each SKU is associated with a
    specific, unique "part". An equivalent SKU indicates an equivalent
    part. Typically, a SKU is a integer, but there is no necessary
    requirement for the datatype of the SKU.

## Specification

-   The number of parts your inventory management system could be tested
    with is 1 \< parts \< 1,000,000.

-   There is no required public API/interface for your program, to
    provide you creative and design flexibility. You can design a public
    C++ API, a REST API, a Python API, a serial interface, etc. To
    convey what you have implemented you must document your API.

## Part Characteristics

Each part is associated with a "class" of parts (resistors, solders,
etc.). The class determines the necessary properties of the part.

Each part should have a "Last Updated Date" property (date with time)
representing the most recent time that some quantity of that part was
added to the inventory. Each property of a part must be of the necessary
type, or your API should error out.

-   **Resistor**

    -   Resistance (ohms, integer-type)

    -   Tolerance (number, integer-type)

-   **Solder**

    -   Type (enumerator of `lead`, `lead-free`, `rosin-core`,
        `acid-core`)

    -   Length (ft, decimal-type)

-   **Wire**

    -   Gauge (in, decimal-type)

    -   Length (ft, decimal-type)

-   **Display Cable**

    -   Type (enumerator of `hdmi`, `vga`, `displayport`, `micro-hdmi`)

    -   Length (ft, decimal-type)

    -   Color (hex code)

-   **Ethernet Cables**

    -   Alpha Type (enumerator of `male`, `female`)

    -   Beta Type (enumerator of `male`, `female`)

    -   Speed (enumerator of `10mbps`, `100mbps`, `1gbps`, `10gbps`)

    -   Length (ft, decimal-type)

## Necessary Methods

-   **Add Part**

    -   *Parameters:* All necessary characteristics to describe the
        part.

-   **Add Inventory**

    -   *Parameters*: SKU, quantity

    -   Adds a certain quantity of SKU to the available inventory. Note
        that this will need to update the "Last Updated Date" property
        of the part.

-   **Get Quantity**

    -   *Parameters:* SKU

    -   Returns the quantity of the SKU.

-   **Get Inventory**

    -   *Parameters:* None

    -   Returns all parts and their quantity in the lab.

-   **Get Part**

    -   *Parameters*: SKU

    -   Returns the characteristics of the part belonging to the SKU

-   **Search**

    -   *Parameters:* Class, and relevant characteristics

    -   Allows a user to search through the parts inventory for a
        necessary part based on the necessary characteristics. Returns a
        list of all parts that have at least one of the searched-by
        characteristics.

-   **Delete Part**

    -   *Parameters:* SKU

    -   Completely removes a part with the designated SKU

## Errors
Your interface should be resilient to common errors. A
list of every possible error would be too exhaustive for this document,
but some initial ones you might want to consider include:

-   What happens if a user tries to add a negative quantity of an item?

-   What happens if a user tries to get the quantity of a non-existent
    SKU?

-   What happens if a user fails to provide all necessary
    characteristics to accurately describe a part?

-   What happens if a user tries to add a new part with the exact same
    characteristics of another part?

Do not assume intended behavior if one of these situations occur \--
throw an error instead. How you implement the error handling of your
program will vary based on your program type, but it should contain a
human-readable message with a description of what went wrong.

## Testing
Part of working on a robot is ensuring that it meets set
standards for reliability and robustness. Therefore, you will need to
develop some tests for your API. How you go about testing your API is up
to you, and of course, it will depend on the interface that you choose.

However, alongside reviewing your code, we will be testing your API via
the documentation you provide, so **we highly encourage** adding some
tests to ensure that your program will work well under a variety of
conditions.

## Optional Features
If you're interested in implementing optional features in
your interface, here are some ideas of components you could add:

1.  **Authentication** -- Requiring users to authenticate before using
    the API. This would allow you to store an additional field on each
    Part with *who* last updated the part.

2.  **Analytics** -- Ability to create graphs highlighting which parts
    are most used, and which parts commonly fall out of stock.

3.  **Webhooks/Event Notifications** -- Notifying users about updates to
    parts could be helpful for notifying users of important information
    (ex, a part going out of stock) before it happens.

## Authentication
Authentication for your API is not required. It can be
implemented if you would like.

## Submission
You will submit your code through a Git repository, via
GitHub. Please create a new repository under your account, **set it to
private**, and then add the following users:
[cbrxyz](https://github.com/cbrxyz) (Cameron Brown),
[andrew-aj](https://github.com/andrew-aj) (Andrew Knee), and
[DaniParr](https://github.com/DaniParr) (Daniel Parra) so we can review
your work.

Furthermore, remember to complete the full application at
<https://mil.ufl.edu/apply>.

## Documentation
Because of the flexibility in how you can design your
API, you must document how we can go about using it. There are no exact
design requirements, but we would like you to include the following
somewhere in your documentation:

1.  How each method can be called via your API.

2.  Some brief examples of using your API and the expected response.

3.  The overall design of your API, why you chose to implement with a
    certain interface over another one.

## Assessment
Your submission will be assessed primarily based on your
ability to:

1.  Develop a complete API that implements all the requirements (listed
    above)

2.  Develop a comprehensible, clear solution that can be understood by
    us when we review your work

3.  Test and validate your API by showing its capability to withstand
    errors and misuse

4.  Document and write about the capabilities of your interface

## Questions/Comments/Concerns?
Feel free to reach out to us anytime. Our emails can be
found here:

1.  Cameron Brown, <cbrown14@ufl.edu>

2.  Andrew Knee, <andrew.knee@ufl.edu>

3.  Daniel Parra, <dparra1@ufl.edu>

If you have questions about your application, feel free to reach out to
us via email. If you would like to join our Discord, please email one of
us for the invitation link.

We look forward to seeing all your submissions!

_\- Cameron, Andrew, Daniel, and everyone at MIL_
