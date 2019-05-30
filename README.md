# VideoConverter
Video file conversion library based on <a href="https://android.googlesource.com/platform/cts/+/jb-mr2-release/tests/tests/media/src/android/media/cts/ExtractDecodeEditEncodeMuxTest.java">ExtractDecodeEditEncodeMuxTest.java</a> CTS test

## Installation
VideoConverter is installed by adding the following dependency to your build.gradle file:
dependencies {
    implementation 'com.dstukalov:videoconverter:1.0'
}

## Usage
    mConverter = new VideoConverter(input, output);
    mConverter.setTimeRange(timeFrom, timeTo);
    mConverter.setFrameSize(dstWidth, dstHeight);
    mConverter.setVideoBitrate(2000000);
    mConverter.setAudioBitrate(128000);
    mConverter.setStreamable(true);

    mConverter.setListener(percent -> {
        publishProgress(percent);
        return isCancelled();
    });

    mConverter.convert();
