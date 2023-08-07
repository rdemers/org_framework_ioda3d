# IODA - Architecture principes

For Ralf Westphal, common architecture patterns like Layered Architecture, Hexagonal Architecture, and Clean Architecture all look very similar when performing the following 2 actions: defining areas of responsibility and putting functional dependencies in order. For him, these models give a very rough idea of ​​the structure of an application, essentially describing software as a deep hierarchy of functional or behavioral dependencies.

Looking for another way to describe architectures, Westphal defined an architectural style, IODA architecture, built around three formal responsibilities, ranging from orthogonal to behavioral:

* **Operation:** element of logic or behavioral change on the data, but without knowledge of any other operation and not authorized to call upon it.

* **Data:** data structure, possibly including services working on the data to ensure consistency, but without adding any other form of logic.

* **Integration:** uses operations and other integrations to put everything together creating behavior, but do not contain logic.

* **APIs** and frameworks are the fourth part through which operations interact with the environment.

The following figure presents a functional view of this architecture.

![alt text](./asserts/ioda.png "IODA Architecture")

In this model, operations depend only on data, while integrations depend on operations and other integrations. Westphal hereby claims to have removed all functional dependencies, what remains are simply what he calls formal or empty dependencies. He also claims that since operations cannot call on other operations, extracting logic from new operational methods involves creating integrations to keep things together and thus implementing small methods, less than 10-20 lines of code, in an application.

An important aspect that Westphal mentions is that an IODA structure can appear on several levels. What is an operation for one level of abstraction may itself be a complete IODA structure when zoomed in.

## IODA|3D Framework for flutter

IODA|3D implements the code according to these architectural principles.

## Links and references

* [IODA Architecture (pdf presentation)](./asserts/ioda.pdf).

* [Introducing the IODA Architecture](https://www.infoq.com/fr/news/2015/06/ioda-architecture/).

* [Introducing the IODA Architecture (french local version)](./asserts/french/Présentation%20de%20l’Architecture%20IODA.html).
