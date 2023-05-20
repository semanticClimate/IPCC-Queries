# Using the DPSIR Framework

The [Driver-Pressure-Statement-Impact-Response (DPSIR) framework](https://en.wikipedia.org/wiki/DPSIR) was defined by the European Environmental Agency (EEA) in 1999 to describe interactions between society and the environment [<cite>Q111716241</cite>]. The framework consists of five components: driver, pressure, state, impact, and response. Together, these form a cause-and-effect chain. When annotating the IPCC report, this framework can be used to create a more structured set of annotations.

## Components of the framework

### Drivers

In the DPSIR framework, <topic>driver</topic>s are human activities &mdash; such as farming, travelling, and fishing &mdash; that affect the environment. In this Wikibase, natural processes that affect the environment are also included as drivers. The Wikibase has the following drivers:

<sparql>drivers</sparql>

This gives:

<out>drivers</out>

### Pressures

The way that drivers affect the environment is expressed in <topic>pressure</topic>s. For example, one pressure that results from travel is the emission of greenhouse gases from combustion engines. The Wikibase has the following pressures:

<sparql>pressures</sparql>

This gives:

<out>pressures</out>

### States

The properties of the environment that pressures change are called <topic>state</topic>s. For example, the emission of CO₂ results in the changing of the state "atmospheric CO₂ concentration", and indirectly the state "surface temperature". The Wikibase has the following pressures:

<sparql>states</sparql>

This gives:

<out>states</out>

### Impacts

Changes in the state of different properties of the environment can then have <topic>impact</topic>s on human life and other aspects of the environment that we give intrinsic value. The Wikibase has the following impacts:

<sparql>impacts</sparql>

This gives:

<out>impacts</out>

### Responses

Finally, these impacts can trigger society and policy-makers to respond, either by mitigating the impact, counter-acting the change in state, eliminating the pressure, or fundamentally changing human activity. The Wikibase has the following responses:

<sparql>responses</sparql>

This gives:

<out>responses</out>

## DPSIR Chains

Together, these components form a chain of cause and effect. Within a statement in the IPCC report, such cause-and-effect relationships are mentioned. By annotating these statements with their different DPSIR components, the chain can be derived:

<sparql>dpsir</sparql>

This gives:

<out>dpsir</out>

## References

<references/>
