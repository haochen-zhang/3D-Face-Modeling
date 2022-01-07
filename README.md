# 3D-Face-Modeling
A vanilla 3D face modeling on pose-invariant and multi-lightning image data

### Table of Contents
- Background
- Install
- Usage
- Contributing

## Background

The project tries to restore surface normal and albedo information based on pose-invariant and multi-lightning image data, then use them to rebuild the 3d face model.

![face_08](https://user-images.githubusercontent.com/70677169/148566969-eb773475-a514-4dcc-9a32-46f9b157868c.png)

<p align="center">Test Data</p>

![image](https://user-images.githubusercontent.com/70677169/148576189-44e35113-ec89-483e-9365-03f165977c68.png)

<p align="center">Recovered Surface</p>

## Install

This project is implemented with Google Colab. Please download all the files and upload them into your own Google Drive project folder and then open it.

## Usage

First, load images

``` sh
# load images as intensity matrix at each pixel
imstack = []
for i in range(1, 8):
  imstack.append((cv2.imread(Images path, cv2.IMREAD_GRAYSCALE)).flatten())
imstack = np.vstack(imstack)
```

Second, define data light

```sh
# load light source vector S
S = pickle.load(open('./data/sources.pickle', 'rb'))['S']
```

## Contributing
The project's recover surface function is credited to Todd Zickler, CS283, Harvard University.
