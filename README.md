
# Intelligent Vehicle Accident Analysis System API #
The Intelligent Vehicle Accident Analysis System API or IVAA API provides an **artificial intelligence** service to estimate the damaged part of vehicle after the accident is occurred from images.

## Train model ##
```
POST http://ivaa.space:64563/projects
```
* POST argument
```
{
  'model': 'model.config',
  'train': 'train.config',
  'label': 'class.txt',
  'file': 'photo.png'
}
```
* POST response
```
{
  'message': 'successful',
  'model-id': 'model-.....',
  'project-id': 'project-.....'
}
```


## Test model ##
```
POST http://ivaa.space:64563/api
```
* POST argument
```
{
  'file': 'photo.png',
  'model-id': 'model-.....',
  'project-id': 'project-......'
}
```
* POST response
```
{
  'boxes': [
  {
    'score': '', #accuracy
    'type': '', #damaged part
    'x0': '', #x-axis position at top-left
    'x1': '', #x-axis position at bottom-right
    'y0': '', #y-axis position at top-left
    'y1': '', #y-axis position at bottom-right
  }
  ],
  'download_duration': '...', #time to download
  'processing_duration' '...', #time to process
}
```
