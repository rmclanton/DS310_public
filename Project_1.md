## Was your social distance detector effective at detecting potential violations?
While it was good at identifying people and when they got near each other, I have several issues with its performance
and implementation. The social distance detector would occasionally pick up things such as posts as people, causing 
violations to be detected between a human and an inanimate object. Also, at a 90 degree angle from the horizontal, people
could be hidden behind each other and detected as one person, instead of two within six feet of each other. The biggest 
issue with the methodology of this is that people from the same unit within six feet of each other are considered to be 
violating social distancing. A woman and her two year old child in a stroller were picked up as violating social distancing.

## Do you think this approach would be effective for estimating new infections in real time? How would you implement such an approach in response to the COVID-19 pandemic we are currently experiencing?
Not at all. In order for this approach to be accurate for every group that went within six feet of each other, one would
need to infect the other. Which means it assumes half the people in frame at any given point have COVID19, which isn't the case.
It would only work if it could detect who is sick, or follow a specific person known to be a carrier and detect who they 
might have infected.

## What limitations or improvements might you include in order to improve your proposed design?
I'd only use this program from a camera with a downwards view. It needs to be able to clearly distinguish people. A difficult
improvement would be to give it thermal imaging. If thermal imaging could be implemented to accurate within a few degrees,
it could detect feverish people and then only count possible infections when those people break social distancing protocol.

## Video output:
[Walk.avi](https://rmclanton.github.io/DS310_public/walk.avi)


While integrating mask detection is interesting for statistics, I don't think it will help to determine infections. Yes, 
it's less likely you'll infect someone if you're wearing a mask. But it isn't a 100% guarantee.