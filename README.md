
# Intelligent Vehicle Accident Analysis System API #
The Intelligent Vehicle Accident Analysis System API or IVAA API provides an **artificial intelligence** service to estimate the damaged part of vehicle after the accident is occurred from images.

## Train model ##
```
POST http://ivaa.space:64563/projects
```
* POST argument
```
{
  'model': 'model.config', #model configuration file
  'train': 'train.config', #training model configuration file
  'label': 'class.txt', #train dataset class
  'file': 'photo.png' #train dataset
}
```
* POST response
```
{
  'message': 'successful', #status message
  'model-id': 'model-.....', #model identification number
  'project-id': 'project-.....' #project identification number
}
```


## Model usage ##
```
POST http://ivaa.space:64563/api
```
* POST argument
```
{
  'file': 'photo.png', #test dataset
  'model-id': 'model-.....', #model identification number
  'project-id': 'project-......' #project identification number
}
```
* POST response
```
{
  'boxes': [
  {
    'score': '...', #accuracy of each damaged part
    'type': '...', #damaged part
    'x0': '...', #x-axis position at top-left
    'x1': '...', #x-axis position at bottom-right
    'y0': '...', #y-axis position at top-left
    'y1': '...', #y-axis position at bottom-right
  }
  ],
  'download_duration': '...', #download duration
  'processing_duration' '...', #processing duration
}
```
