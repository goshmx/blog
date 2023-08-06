---
layout: post
title: Flutter rounded corners
---

### Esquinas redondeadas en Flutter en imagen

Para redondear las esquinas de una imagen en Flutter, se puede usar el widget `ClipRRect` que recibe como hijo un `Image.network` y como parámetro `borderRadius` recibe un `BorderRadius.circular(20)`.

```dart
ClipRRect(
    borderRadius: BorderRadius.circular(8.0),
    child: Image.network(
        subject['images']['large'],
        height: 150.0,
        width: 100.0,
    ),
)
```

Tambien se pueden hacer con el Widget `CircleAvatar`.

```dart
//Usando CircleAvatar
CircleAvatar(
    radius: 50.0,
    backgroundImage: NetworkImage(
        subject['images']['large'],
    ),
)

//Usando ClipRRect
ClipOval(
  child: SizedBox.fromSize(
    size: Size.fromRadius(48), // Image radius
    child: Image.network('imageUrl', fit: BoxFit.cover),
  ),
)

//Usando border 
CircleAvatar(
  radius: 56,
  backgroundColor: Colors.red,
  child: Padding(
    padding: const EdgeInsets.all(8), // Border radius
    child: ClipOval(child: Image.network('imageUrl')),
  ),
)

Container(
  padding: EdgeInsets.all(8), // Border width
  decoration: BoxDecoration(color: Colors.red, shape: BoxShape.circle),
  child: ClipOval(
    child: SizedBox.fromSize(
      size: Size.fromRadius(48), // Image radius
      child: Image.network('imageUrl', fit: BoxFit.cover),
    ),
  ),
)
```

#### Esquinas redondeadas.

```dart
ClipRRect(
  borderRadius: BorderRadius.circular(20), // Image border
  child: SizedBox.fromSize(
    size: Size.fromRadius(48), // Image radius
    child: Image.network('imageUrl', fit: BoxFit.cover),
  ),
)

//Con border
final borderRadius = BorderRadius.circular(20); // Image border

Container(
  padding: EdgeInsets.all(8), // Border width
  decoration: BoxDecoration(color: Colors.red, borderRadius: borderRadius),
  child: ClipRRect(
    borderRadius: borderRadius,
    child: SizedBox.fromSize(
      size: Size.fromRadius(48), // Image radius
      child: Image.network('imageUrl', fit: BoxFit.cover),
    ),
  ),
)
```

