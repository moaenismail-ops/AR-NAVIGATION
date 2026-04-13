CSEway – Indoor Navigation Based on Visual Landmark Detection and AR

CSEway is an indoor navigation project for the Engineering building, designed to help students and visitors navigate in an environment where GPS is unreliable.
The system uses visual landmark detection from signs and location labels (such as room names and points of interest) to identify the user’s location and guide them to a destination.

The project started as an image-based MVP, where the user uploads or captures an image of a sign, the system runs OCR, detects the current location,
and later verifies arrival using another image while providing visual feedback (including an annotated arrow when detection succeeds). After this pipeline became stable,
we migrated the same core logic into an AR-based application.

At the current stage, the system operates as a scenario-focused AR MVP (specific routes / predefined destinations), combining camera input, text detection, and matching against known landmarks. 
The application is developed in Kotlin, while reusing the detection logic originally validated in the image-based MVP.

Technically, the system performs OCR on text from the environment, normalizes OCR outputs (to handle noise and common OCR errors), and uses robust matching to detect the start point,
intermediate checkpoints, and destination. The same mechanism is used both for localization and for arrival verification.

At this stage, the project demonstrates a working proof of concept: visual localization, navigation guidance for a defined scenario, and destination verification.
The next step is to expand the landmark set and support more general routes across the building.

For best demo results, it is recommended to use clear images with good lighting so signs are visible and readable. This repository includes the project logic, 
application components, and demo materials
This repository documents our progress on an indoor navigation project based on visual landmarks. Since GPS is unreliable indoors,
we use the device camera to detect signage (room labels and key landmarks) with OCR and robust text matching, and then use these detections as anchors for guidance and arrival verification.

We first built an image-based prototype to validate the core pipeline: capture or upload an image, extract text with OCR,
normalize and match it against a predefined landmark set using confidence and fuzzy similarity, and verify arrival by detecting the destination sign again. After this worked reliably,
we migrated the same detection logic into an AR-style flow with a live camera experience. The current implementation is an Android (Kotlin) prototype focused on a small, controlled demo scenario with predefined landmarks, demonstrating end-to-end behavior from detection to destination confirmation.
