# Introduction 

The main goal of this repository is to produce a standard format documenting who 
represents you in local, state, and federal government. This information is currently 
dispersed among different sites. Here, we aggregate this information into a set format 
using directories and flat json files as a start. The idea is that these files and 
directories will be injested by other systems for more dynamic functionality.

## Hierarchy 

In general, the top hierarchy will represent the country, such as `us`. Data for the 
country level will contain federal representatives that are voted into office. Next up,
provincial directories, which contain representatives at the provincial/state level. Using 
`us` as an example, you would have directories for `states` with: `ak`, `tn`, etc. Each of these
will list out the state-level representatives for state legislature, and state-level
senators. Congressional representatives aren't listed under each state, as not all congressional 
districts fall within a single state. For this, we include two other categories: `judiciary` and 
`congressional`. The former is for the intrastate federal judicial districts (1-9). The latter 
is for categorizing the congressional districts (in `us`, there are 435 of these, with some crossing 
state borders).

At this point, we should have coverage for elected federal- and state-level government representatives.
The common key for all of these is ZIP+4 in `us`. This may hold for other countries, but probably
varies in many ways yet to be discovered.

### TODO

- Local government

This doesn't yet account for local government (county, city, and lower-level city government positions).
The challenge is that there's no clean overlap for districts and counties. But since counties definitely
lie within states, we can nest them under a `counties/` directory.

- Perhaps to simplify, everything should be annotated based on how they overlap the fixed boundaries.

If we can draw a map showing the boundaries of the country, states, and counties, and cities, we can
overlap the intra-state and intra-county districts.

## Control points

For each mappable district, there will be a `coords` key that contains all the control points to
draw the area. For instance if you look up `us/states/tn/data.json`, you can expect to have this key, 
that can be coverted into lat/long positions on a globe.
