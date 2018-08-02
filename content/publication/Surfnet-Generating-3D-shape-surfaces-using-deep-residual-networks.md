+++
title = "Surfnet Generating 3D Shape Surfaces Using Deep Residual Networks"
date = 2017-07-25T11:24:27+05:30
draft = false

# Authors. Comma separated list, e.g. `["Bob Smith", "David Jones"]`.
authors = ["Ayan Sinha","Asim Unmesh","Qixing Huang","Karthik Ramani"]

# Publication type.
# Legend:
# 0 = Uncategorized
# 1 = Conference paper
# 2 = Journal article
# 3 = Manuscript
# 4 = Report
# 5 = Book
# 6 = Book section
publication_types = ["1"]

# Publication name and optional abbreviated version.
publication = "Surfnet Generating 3D Shape Surfaces Using Deep Residual Networks"
publication_short = "CVPR 2017, Honolulu, Hawaii"

# Abstract and optional shortened version.
abstract = "3D shape models are naturally parameterized using vertices and faces, i.e, composed on polygons forming a surface. However, current 3D learning paradigms for predictive and generative tasks using convolutional neural networks focus on a voxelized representation of the object. Lifting convolution operators from the traditional 2D to 3D results in high computational overhead with little additional benefit as most of the geometry information is contained on the surface boundary. Here we study the problem of directly generating the 3D shape surface of rigid and non-rigid shapes using deep convolutional neural networks. We develop a procedure to create consistent `geometry images' representing the 3D shape surface of a category of shapes. We then use this consistent representation for category-specific shape generation from a parametric representation or an image by developing novel extensions of deep residual networks for the task of 3D surface generation. Our experiments indicate that our network learns a meaningful representation of shape surfaces allowing it to interpolate between shape orientations and poses, invent new shape surfaces, reconstruct 3D shape surfaces from previously unseen images, and rectify noisy correspondence between 3D shapes belonging to the same class."
abstract_short = "3D shape models are naturally parameterized using vertices and faces, i.e, composed on polygons forming a surface. However, current 3D learning paradigms for predictive and generative tasks using convolutional neural networks focus on a voxelized representation of the object. Lifting convolution operators from the traditional 2D to 3D results in high computational overhead with little additional benefit as most of the geometry information is contained on the surface boundary. Here we study the problem of directly generating the 3D shape surface of rigid and non-rigid shapes using deep convolutional neural networks."

# Featured image thumbnail (optional)
image_preview = "surfnet.jpg"

# Is this a selected publication? (true/false)
selected = true

# Projects (optional).
#   Associate this publication with one or more of your projects.
#   Simply enter your project's filename without extension.
#   E.g. `projects = ["deep-learning"]` references `content/project/deep-learning.md`.
#   Otherwise, set `projects = []`.
projects = []

# Tags (optional).
#   Set `tags = []` for no tags, or use the form `tags = ["A Tag", "Another Tag"]` for one or more tags.
tags = []

# Links (optional).
url_pdf = "http://openaccess.thecvf.com/content_cvpr_2017/papers/Sinha_SurfNet_Generating_3D_CVPR_2017_paper.pdf"
url_preprint = ""
url_code = ""
url_dataset = ""
url_project = ""
url_slides = ""
url_video = ""
url_poster = ""
url_source = ""
# Custom links (optional).
#   Uncomment line below to enable. For multiple links, use the form `[{...}, {...}, {...}]`.
# url_custom = [{name = "Custom Link", url = "http://example.org"}]

# Does this page contain LaTeX math? (true/false)
math = false

# Does this page require source code highlighting? (true/false)
highlight = true

# Featured image
# Place your image in the `static/img/` folder and reference its filename below, e.g. `image = "example.jpg"`.
[header]
image = "surfnet.jpg"
#<img src="static/img/surfnet.jpg" width="100" height="100" />
caption = ""

+++
