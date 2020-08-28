# Simple Image Based Search Engine

## Overview
- Simple image-based image search engine using Keras + Flask. You can launch the search engine just by running two python scripts.
- `offline.py`: This script extracts a deep-feature from each database image. Each feature is a 4096D fc6 activation from a VGG16 model with ImageNet pre-trained weights.
- `server.py`: This script runs a web-server. You can send your query image to the server via a Flask web-interface. The server finds similar images to the query by a simple linear scan.
- GPUs are not required.

## Usage
```bash
git clone https://github.com/Pooja-Lokesh/Image_based_search_engine
cd Image_based_search_engine
pip install -r requirements.txt

# Put your image files (*.jpg) on static/img

python offline.py
# Then fc6 features are extracted and saved on static/feature
# Note that it takes time for the first time because Keras downloads the VGG weights.

python server.py
# Now you can do the search via http://127.0.0.1:5000/
```

