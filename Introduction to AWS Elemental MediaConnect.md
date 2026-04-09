# Introduction to AWS Elemental MediaConnect

## What is MediaConnect?

Using AWS Elemental MediaConnect, you can reliably and securely transport high-quality live video from a source to one or more destinations for encoding, packaging, and delivery.

Streaming major live events is one of the most challenging things to do in the video space. Reliability of the signal is of huge importance, as dead air or lagging streams are never acceptable. Major events also attract viewers on all sorts of devices and different bandwidths. Regular networks don’t have the reliability, speed, and low latency required.

That's where MediaConnect comes in. It gives you a secure and reliable way to transport live mezzanine-quality video into, within, and out of the AWS Cloud, providing a quality-of-service layer over standard IP transport, for uninterrupted live video connections globally.

To learn more, go to the [AWS Elemental MediaConnect User Guide](https://docs.aws.amazon.com/mediaconnect/latest/ug/what-is.html) (opens in a new tab).

## What are the benefits of MediaConnect?

MediaConnect is a cost-effective, fast-to-deploy solution compared to more traditional technologies such as cable, satellite, or managed fiber. Instead of long-term commitments, MediaConnect offers a pay-as-you-go transport alternative.

Additionally, MediaConnect securely transports video using end-to-end, industry-standard encryption and allow lists. It is fully integrated with the Secure Packager and Encoder Key Exchange (SPEKE) API. SPEKE defines the standard for communication between encryptors and packagers of media content and digital rights management (DRM) key providers.

## What is a flow?

A MediaConnect flow is a transport between a source and one or more destinations. When you create a flow, you specify the source, a name, and an Availability Zone. MediaConnect supports two types of flows:

### Transport stream flows
Transport stream flows transport compressed content that is muxed (audio, video, and ancillary data are combined) into a single stream. The quality is high enough to use as a source for creating final encodes that are delivered to consumer devices. You can add outputs to indicate where you want the content to be sent and how you want it transported.

### CDI flows
AWS Cloud Digital Interface (CDI) flows transport high-quality uncompressed or lightly compressed content into and out of the AWS Cloud. You can configure a CDI flow to use JPEG XS to transport lightly compressed content. The content is demuxed into separate media streams for audio, video, or ancillary data. Each CDI flow can use multiple media streams for the source and multiple media streams for each output. MediaConnect uses AWS CDI network technology to transport content that adheres to the SMPTE 2110, part 22 transport standard.

To learn more about flows, go to [Flows in AWS Elemental MediaConnect](https://docs.aws.amazon.com/mediaconnect/latest/ug/flows.html) (opens in a new tab).

![MediaConnect Flow Architecture](./images/mediaconnect-flow-architecture.png)

## What is an output?

After you create a flow, you can add outputs to indicate where you want your live video content to be sent and how you want it transported.

You can have one or more outputs such as another MediaConnect flow, an encoder receiver, or any publicly addressable IP address. To learn more, choose each numbered marker.

- **Output 1: Stream to MediaLive**  
  You can transport the live video to the AWS Elemental MediaLive encoder. MediaLive compresses the high-resolution, high-bitrate stream into lower resolution or bitrate versions suitable for streaming to internet-based viewers.
- **Output 2: Stream to a non-AWS encoder**  
  You can transport the live video stream to a third party on-premises encoder (outside of the AWS Cloud).
- **Output 3: Stream to a partner in another Region**  
  You can transport the live video stream to a different AWS account (partner) in a different AWS Region. The AWS account (partner) can then create their own outputs to distribute the live video stream.
- **Output 4: Stream to an affiliate in the same Region**  
  You can transport the live video stream to a different AWS account (affiliate) in the same AWS Region using entitlements. The AWS account (affiliate) can then create their own outputs to distribute the live video stream.

### Task 1: Creating a flow and adding an output
In this task, AnyCompany Broadcasting creates a flow to establish a live video transport. They also add an output to send the live video stream to a partner in a different AWS Region.

### Task 2: Granting an entitlement
In this task, the originator company grants an entitlement to send or share the live video stream with an affiliate in the same AWS Region. Entitlements are special types of outputs that are only available when both sender and receiver are located in the same AWS Region. It provides a more straightforward option to share and configure the transport.

### Task 3: Subscribing to shared content
In this task, the receiver of the entitlement subscribes to the live video stream by creating a new MediaConnect flow using the sender account's flow as the source.

## What is an entitlement?

You can grant an entitlement to share the content in your MediaConnect flow with another AWS account (subscriber account) in the same AWS Region.

When the subscriber account sets up a flow based on the entitlement, the service generates an output on your flow to represent the stream from your flow to the subscriber's flow. This output is counted as part of the 50 maximum outputs that you can have on your flow. The total bandwidth of all outputs should not exceed 400 Mbps.

The subscriber must set up their MediaConnect flow in the same AWS Region as the originator's flow. Also, entitlements can only be granted on transport stream flows. MediaConnect doesn't support entitlements on CDI flows. To learn more, go to [Entitlements in AWS Elemental MediaConnect](https://docs.aws.amazon.com/mediaconnect/latest/ug/entitlements.html) (opens in a new tab).

Explore the following diagram to learn more:

![Entitlement Example](./images/mediaconnect-entitlement-example.png)

In this example, the originator account is a broadcaster who has granted an entitlement of a live stream in AWS Region 1. The subscriber account (the affiliate) needs to create their own flow in the same AWS Region as the originator's flow. To distribute the content to markets in AWS Region 2, the subscriber needs to create a second flow in AWS Region 2 and create an output (Output 1) that connects the two flows.

### What are the benefits of entitlements?

The following are some of the benefits of entitlements:

- You can specify the percentage of the entitlement data transfer fee that you want the subscriber to be responsible for.
- You can grant, update, and revoke entitlements at any time, even on an active flow. If you want to stop streaming content to the subscriber’s flow on a temporary basis, you can disable the entitlement.
- You don’t need to know the subscriber’s IP address or port—all you need to set up the entitlement is the subscriber’s AWS account number.
- Entitlements do not require originators to understand a subscriber’s technology stack. The subscription is decoupled from the entitlement.
- The account boundary creates a clear demarcation of both operational and commercial responsibility. It clearly defines what resources belong to the originator and to the subscriber.
- Content can be secured with AWS Elemental SPEKE-compliant conditional access. SPEKE provides integration with digital rights management (DRM) solutions providers.

---

## How to subscribe to the shared content

To subscribe to the shared or entitled content, the subscriber account (affiliate) needs to create an entitled flow by choosing the **Entitled Source** option.

Before creating the entitled flow, the subscriber account needs to obtain the following information from the content originator:

- The entitlement Amazon Resource Name (ARN)
- The AWS Region that the originator created the flow in
- The encryption key and algorithm if the originator set up encryption on the entitlement
