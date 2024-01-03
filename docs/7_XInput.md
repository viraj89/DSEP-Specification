# The XInput Schema

## Context
Beckn protocol defines a domain-agnostic specification that can be used to represent any customer- provider transaction by implementing a standard set of APIs and schema. Creating a transaction ideally involves the customer discovering products and services offered by various providers, selecting the desired products or services, obtaining the terms of service and payment, and then finally confirming the order. But sometimes,  the provider might require additional metadata in order to confirm a transaction. This requirement may be due to legal requirements imposed by the regulatory authorities, or business requirements to allow better serviceability. 

For example, a logistics service provider might require additional information from the logistics customer (like a restaurant) like the dimensions of the package, category of items (food, flammable, fragile etc), approximate weight of the package, the order Number etc, to confirm the order. All of this information needs to be transmitted to the person availing the logistics service. 

Similarly, a healthcare service might want the patient to provide information like, their medical history, a description of their symptoms, details of the insurance, etc, before confirming the order.  

The nature of additional information required could vary significantly across sectors. These fields could be varied and many, and adding them as protocol attributes would make the protocol bulky and cluttered. 


## Problem

We require an object that captures additional information (over and above what has been published in the catalog) from the customer regarding the item being ordered without extending the core transaction protocol.


## Solution

It is probably not such a good idea to transmit such required data fields as first class citizens of the transaction protocol, rather transmit them in some sort of a custom form object. This form could be a simple HTML form hosted on a url endpoint or transmitted as a whole as per standard form specifications like [XForms 2.0](https://www.w3.org/TR/xforms20/).

The detailed proposed design of this feature can be found [here.](https://github.com/beckn/protocol-specifications/blob/master/docs/BECKN-007-The-XInput-Schema.md) 

