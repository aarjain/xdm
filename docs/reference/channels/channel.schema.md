
# Experience Channel Schema

```
https://ns.adobe.com/xdm/channels/channel
```

An experience channel is a way how digital experiences are consumed.

There are multiple experience channels, each with different constraints on how content is delivered and how customer interaction can be observed and data collected. Within a channel, experiences can be delivered to specific locations. The locations and types of locations that exist in a channel differ from channel to channel.


| Abstract | Extensible | Custom Properties | Additional Properties | Defined In |
|----------|------------|-------------------|-----------------------|------------|
| Can be instantiated | Yes | Forbidden | Permitted | [channels/channel.schema.json](channels/channel.schema.json) |

## Schema Hierarchy

* Experience Channel `https://ns.adobe.com/xdm/channels/channel`
  * [Extensibility base schema](../common/extensible.schema.md) `https://ns.adobe.com/xdm/common/extensible`

## Experience Channel Example
```json
{
  "@id": "https://ns.adobe.com/xdm/channels/facebook-feed",
  "@type": "https://ns.adobe.com/xdm/channel-types/social",
  "xdm:metrics": [
    "https://ns.adobe.com/xdm/data/metrics/web/page-views",
    "https://ns.adobe.com/xdm/data/metrics/web/link-clicks"
  ]
}
```

# Experience Channel Properties

| Property | Type | Required | Defined by |
|----------|------|----------|------------|
| [@id](#@id) | `string` | **Required** | Experience Channel (this schema) |
| [@type](#@type) | `string` | Optional | Experience Channel (this schema) |
| [xdm:contentTypes](#xdmcontentTypes) | `string[]` | Optional | Experience Channel (this schema) |
| [xdm:locationTypes](#xdmlocationTypes) | `string[]` | Optional | Experience Channel (this schema) |
| [xdm:metricTypes](#xdmmetricTypes) | `string[]` | Optional | Experience Channel (this schema) |
| [xdm:mode](#xdmmode) | `enum` | Optional | Experience Channel (this schema) |
| `*` | any | Additional | this schema *allows* additional properties |

## @id

The ID uniquely identifies the channel. Each specific experience channel defines a constant `@id`.

`@id`
* is **required**
* type: `string`
* defined in this schema

### @id Type


`string`
* format: `uri` – Uniformous Resource Identifier (according to [RFC3986](http://tools.ietf.org/html/rfc3986))






## @type

The `@type` property is used to provide a rough classification of channels with similar properties.

`@type`
* is optional
* type: `string`
* defined in this schema

### @type Type


`string`
* format: `uri` – Uniformous Resource Identifier (according to [RFC3986](http://tools.ietf.org/html/rfc3986))



### @type Known Values
| Value | Description |
|-------|-------------|
| `https://ns.adobe.com/xdm/channel-types/web` | The world wide web, including mobile web |
| `https://ns.adobe.com/xdm/channel-types/social` | Social media platforms |
| `https://ns.adobe.com/xdm/channel-types/mobile` | Mobile applications |
| `https://ns.adobe.com/xdm/channel-types/messaging` | Instant Messaging |
| `https://ns.adobe.com/xdm/channel-types/email` | E-Mail |
| `https://ns.adobe.com/xdm/channel-types/offline` | Non-Digital experience channels |




## xdm:contentTypes

The content types that this channel can deliver.

`xdm:contentTypes`
* is optional
* type: `string[]`

* defined in this schema

### xdm:contentTypes Type


Array type: `string[]`

All items must be of the type:
`string`
* format: `uri` – Uniformous Resource Identifier (according to [RFC3986](http://tools.ietf.org/html/rfc3986))


  
The `@type` of an XDM-defined content type that is supported by this channel.







## xdm:locationTypes

The types of locations (virtual places) that this channel consists of and can deliver content to.

`xdm:locationTypes`
* is optional
* type: `string[]`

* defined in this schema

### xdm:locationTypes Type


Array type: `string[]`

All items must be of the type:
`string`
* format: `uri` – Uniformous Resource Identifier (according to [RFC3986](http://tools.ietf.org/html/rfc3986))


  
The `@type` of an XDM-defined location (virtual place) that this channel can contain.







## xdm:metricTypes

The metrics that can be collected in this channel.

`xdm:metricTypes`
* is optional
* type: `string[]`

* defined in this schema

### xdm:metricTypes Type


Array type: `string[]`

All items must be of the type:
`string`
* format: `uri` – Uniformous Resource Identifier (according to [RFC3986](http://tools.ietf.org/html/rfc3986))


  
The `@type` of an XDM-defined metric that is supported by this channel.







## xdm:mode

How experiences are delivered in this channel.

`xdm:mode`
* is optional
* type: `enum`
* defined in this schema

The value of this property **must** be equal to one of the [known values below](#xdm:mode-known-values).

### xdm:mode Known Values
| Value | Description |
|-------|-------------|
| `push` | The publisher of an experience can initiate an experience by sending a message into the channel. Most `push` channels involve some form of subscription or opt-in. |
| `pull` | The consumer can initiate an experience by requesting a location in the channel. Most `pull` channels give publishers some control how the experience is then delivered. |
| `bidirectional` | Both `push` and `pull` interaction modes are supported by the channel. |



