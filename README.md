FOGMJPEGImageView
=================

FOGMJPEGImageView is a UIImageView subclass dedicated to displaying a MJPEG from a remote feed.

A typical use case for FOGMJPEGImageView would be displaying a live webcam feed.

Installation
============

Copy the contents of the FOGMJPEGImageView directory into your project:

- FOGJPEGImageMarker.h
- FOGJPEGImageMarker.m
- FOGMJPEGDataReader.h
- FOGMJPEGDataReader.m
- FOGMJPEGImageView.h
- FOGMJPEGImageView.m
- FOGMJPEGImageViewDelegate.h

Usage
=====

With an instantiated FOGMJPEGImageView simply call `startWithURL:` passing the URL of the MJPEG feed you wish to display

```objective-c
FOGMJPEGImageView *mjpegImageView;
...
[mjpegImageView startWithURL:[NSURL URLWithString:@"http://192.168.0.1/mjpg/video.mjpg?camera=1"]];
```

You may halt the MJPEG feed by calling `stop`.

```objective-c
[mjpegImageView stop];
```

If you want to get informed about certain event you can make your class conform to the FOGMJPEGImageViewDelegate
```objective-c
@interface MyClass () <FOGMJPEGImageViewDelegate>
```

Set your class as the delegate of the FOGMJPEGImageView
```objective-c
    mjpegImageView.delegate = self;
```

And implement some or all of the given delegate methods from the protocol
```objective-c
- (void)FOGMJPEGImageViewDidReceiveImage:(FOGMJPEGImageView *)mjpegImageView
{
    // Handle success.
}

- (void)FOGMJPEGImageView:(FOGMJPEGImageView *)mjpegImageView loadingImgaeDidFailWithError:(NSError *)error
{
    // Handle error.
}

```

Maintainers
=======

FOGMJPEGImageView is mainted by [Richard C McGuire](https://github.com/vfog) ([@vf0g](https://twitter.com/vf0g))

License
=======

FOGMJPEGImageView is available under the MIT license. See the LICENSE file for more info.
