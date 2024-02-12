# NSFW & SFW Image Classification

## Stack:
- [FastAPI](https://fastapi.tiangolo.com)
- [Python](https://www.python.org)

## Installation
- For ease of use it's recommended to use the provided [docker-compose.yml](https://github.com/tiltedcube/image_classification/blob/main/docker-compose.yml).
- Rename the `.env.example` file to `.env` and set the preferred values.

## Models
Any model designed for image classification should work.

##### Examples
- https://huggingface.co/Falconsai/nsfw_image_detection
- https://huggingface.co/nateraw/vit-age-classifier

## Usage

Interactive API documentation can be found at: http://localhost:8000/docs

### Image Classification
`POST` request to the `/api/image-classification/` endpoint, uploading an image located at file path.
```
curl -X POST \
    -H "Content-Type: multipart/form-data" \
    -F "file=@file.jpg" \
    http://localhost:8000/api/image-classification?model_name=Falconsai/nsfw_image_detection

```
Example returned json array for`Falconsai/Falconsai/nsfw_image_detection`:
```json
[
	{
		"label": "nsfw",
		"score": value
	},
	{
		"label": "normal",
		"score": value
	}
]
```
---

_Notice:_ _This project was initally created to be used in-house, as such the
development is first and foremost aligned with the internal requirements._