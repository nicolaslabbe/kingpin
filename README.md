#My Edit

-------

i used it in my swift project with a bridge to obj-c and i needed to store & to retrieve some properties from this custom annotation class

so i did add an NSMutableDictionary property to KPAnnotation class to store any additionnal info to this custom annotation class

this property is named "additionnalDatas"

HOW TO USE:

after creating a KPAnnotation (for example named myKPAnnotation) you can do:

```swift
myKPAnnotation.additionnalDatas = dico
```

dico is a NSMutableDictionary

example:

```swift
var dico: NSMutableDictionary = [
    "customProperty1": "a String",
    "customProperty2": "another String"
]
```

HOW IT CAN BE USED:

in a custom class that extend "MKMapViewDelegate", you can override mapView function like so:

```swift
func mapView(mapView: MKMapView!, viewForAnnotation annotation: MKAnnotation!) -> MKAnnotationView! {...}
```

then inside of this function you can test if

```swift
if annotation is KPAnnotation {...}
```

if it is, you can retrieve your custom data this way:

```swift
var myCustomProperty:String = (annotation as KPAnnotation).additionnalDatas["myCustomProperty"] as String
```

-------
