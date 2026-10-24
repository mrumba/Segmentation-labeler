# Image Segmentation Annotation Tool

A web-based image segmentation annotation tool that lets a user upload an image, draw and assign segments to different classes, and export the labeled data in **COCO JSON format** ready for training segmentation models.

---

## What I Built

- **Browser-based annotation canvas** — users can upload an image, create polygon or mask segments, and tag each segment with a class label.
- **Class manager** — multiple classes can be defined and color-coded, with each segment linked to its class ID.
- **Export pipeline** — converts in-browser annotations into standard COCO JSON (images, annotations, categories), so the output drops directly into downstream training pipelines.

---

## Techniques Used

- **Canvas-based interaction** (HTML5 Canvas / pointer events) for drawing and editing segment boundaries in real time.
- **Coordinate normalization** so annotations stay consistent regardless of display size, and map correctly back to original image dimensions on export.
- **COCO schema mapping** — converting polygon/mask data into COCO's `segmentation`, `bbox`, `area`, and `category_id` fields, including handling the RLE/mask representation.
- **Frontend state management** for tracking segments, classes, and undo/edit operations without losing data.

---

## Outcome

The tool produces annotation files that load directly into standard segmentation training workflows **without post-processing**. Building it gave me hands-on experience with the full annotation-to-training data pipeline — and it's directly relevant to this hackathon, since I plan to use **SAM 3.1** in my project. I understand both how segmentation outputs are structured and what a usable annotation interface needs to get clean training data.

---

## Status

Working prototype. Produces COCO JSON that loads directly into standard segmentation training workflows.

---

## Roadmap

- [ ] Mask (brush) annotation mode in addition to polygons
- [ ] Import existing COCO JSON for review and editing
- [ ] Keyboard shortcuts for faster annotation
- [ ] Multi-image batch export
