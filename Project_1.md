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


## do you think implementing a face mask detector could add value to a social distancing detector?
While integrating mask detection is interesting for statistics, I don't think it will help to determine infections. Yes, 
it's less likely you'll infect someone if you're wearing a mask. But it isn't a 100% guarantee. It would however be helpful
to look at how many people are obeying the mask wearing guidelines as well as social distancing guidelines. 

As for this mask detection and social distance detector combination, no it isn't helpful. My integration is rough. It can't
detect masks at a meaningful distance and may only be able to detect one at a time. I'm not sure if it is supposed to or not,
or if I broke that functionality if it is. I could make it do that, but it would be a challenge. A further goal for the future.

## Video output for Social Distancing Detector:
[Walk.avi](https://rmclanton.github.io/DS310_public/walk.avi)

## Video output for Social Distancing Detector combined with Mask Detector
## Mask detection and social distancing video output:

I had to take this video myself as I couldn't find any that would test both at the same time. 
The original code for mask detection doesn't have outputting a file implemented as far as I'm aware, so this video serves
as both my example for mask detection and mask detection and social distance integration.

## How I combined the two:
I had to do three things to combine these files. First I moved all of the dependencies for the mask detector into the
directory with SDD (Social Distancing Detector). Then I made sure they were working off the same frame, using SDD's 
implementation, as it supports taking in videos as input. I removed Mask Detector's runtime loop and put its code 
inside of SDD's. Mask Detector only drew its detection frames and predictions live, so I made it store them the same
 way SDD did. Then I moved the write to frame function from SDD to the end, to draw both of their outputs.

