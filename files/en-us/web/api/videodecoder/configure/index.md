---
title: "VideoDecoder: configure() method"
short-title: configure()
slug: Web/API/VideoDecoder/configure
page-type: web-api-instance-method
browser-compat: api.VideoDecoder.configure
---

{{APIRef("WebCodecs API")}}{{SecureContext_Header}}{{AvailableInWorkers("window_and_dedicated")}}

The **`configure()`** method of the {{domxref("VideoDecoder")}} interface enqueues a control message to configure the video decoder for decoding chunks.

## Syntax

```js-nolint
configure(config)
```

### Parameters

- `config`
  - : An object containing the following members:
    - `codec`
      - : A string containing a [valid codec string](https://w3c.github.io/webcodecs/codec_registry.html#video-codec-registry). See ["codecs" parameter](/en-US/docs/Web/Media/Guides/Formats/codecs_parameter#codec_options_by_container) for details on codec string construction.
    - `description` {{optional_inline}}
      - : An {{jsxref("ArrayBuffer")}}, a {{jsxref("TypedArray")}}, or a {{jsxref("DataView")}} containing a sequence of codec specific bytes, commonly known as extradata.
    - `codedWidth` {{optional_inline}}
      - : An integer representing the width of the {{domxref("VideoFrame")}} in pixels, including any non-visible padding, before any ratio adjustments.
    - `codedHeight` {{optional_inline}}
      - : An integer representing the height of the {{domxref("VideoFrame")}} in pixels, including any non-visible padding, before any ratio adjustments.
    - `displayAspectWidth` {{optional_inline}}
      - : An integer representing the horizontal dimension of the {{domxref("VideoFrame")}} in pixels when displayed.
    - `displayAspectHeight` {{optional_inline}}
      - : An integer representing the vertical dimension of the {{domxref("VideoFrame")}} in pixels when displayed.
    - `colorSpace` {{optional_inline}}
      - : An object representing a {{domxref("VideoColorSpace")}}, containing the following members:
        - `primaries`
          - : A string representing the color {{glossary("gamut")}} of the video sample. One of:
            - `"bt709"`
            - `"bt470bg"`
            - `"smpte170m"`
        - `transfer`
          - : A string representing transfer characteristics. One of:
            - `"bt709"`
            - `"smpte170m"`
            - `"iec61966-2-1"`
        - `matrix`
          - : A string representing a matrix coefficient. One of:
            - `"rgb"`
            - `"bt709"`
            - `"bt470bg"`
            - `"smpte170m"`
    - `hardwareAcceleration` {{optional_inline}}
      - : A hint as to the hardware acceleration method to use. One of:
        - `"no-preference"`
        - `"prefer-hardware"`
        - `"prefer-software"`
    - `optimizeForLatency` {{optional_inline}}
      - : A boolean. If `true` this is a hint that the selected decoder should be optimized to minimize the number of {{domxref("EncodedVideoChunk")}} objects that have to be decoded before a {{domxref("VideoFrame")}} is output.
    - `flip` {{optional_inline}}
      - : A boolean. If `true`, horizontal mirroring is applied. Defaults to `false`.
    - `rotation` {{optional_inline}}
      - : An integer representing the rotation (0, 90, 180, or 270) in degrees clockwise. Defaults to `0`. Arbitrary numbers (including negatives) are rounded to the next quarter turn.

> [!NOTE]
> The registrations in the [WebCodecs Codec Registry](https://w3c.github.io/webcodecs/codec_registry.html#video-codec-registry) link to a specification detailing whether and how to populate the optional `description` member.

### Return value

None ({{jsxref("undefined")}}).

### Exceptions

- {{jsxref("TypeError")}}
  - : Thrown if the provided `config` is invalid.
- `InvalidStateError` {{domxref("DOMException")}}
  - : Thrown if the {{domxref("VideoDecoder.state","state")}} is `"closed"`.
- `NotSupportedError` {{domxref("DOMException")}}
  - : Thrown if the provided `config` is valid but the user agent cannot provide a codec that can decode this profile.

## Examples

The following example creates a new {{domxref("VideoDecoder")}} and configures it with the `"vp8"` codec, a `codedWidth` of 640 pixels and a `codedHeight` of 480 pixels.

```js
const init = {
  output: handleFrame,
  error(e) {
    console.log(e.message);
  },
};

const config = {
  codec: "vp8",
  codedWidth: 640,
  codedHeight: 480,
};

let decoder = new VideoDecoder(init);
decoder.configure(config);
```

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}
