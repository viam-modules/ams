# [`ams` module](https://github.com/viam-modules/ams)

This [ams module](https://app.viam.com/module/viam/ams) implements a ams [as5048 encoder](<LINK TO HARDWARE>), used for <DESCRIPTION> using the [`rdk:component:encoder` API](https://docs.viam.com/appendix/apis/components/encoder/).

> [!NOTE]
> Before configuring your encoder, you must [create a machine](https://docs.viam.com/cloud/machines/#add-a-new-machine).

## Configure your as5048 encoder

Navigate to the [**CONFIGURE** tab](https://docs.viam.com/configure/) of your [machine](https://docs.viam.com/fleet/machines/) in the [Viam app](https://app.viam.com/).
[Add encoder / ams:as5048 to your machine](https://docs.viam.com/configure/#components).

On the new component panel, copy and paste the following attribute template into your encoder's attributes field:

```json
{
  <ATTRIBUTES>
}
```

### Attributes

The following attributes are available for `viam:ams:as5048` encoders:

<EXAMPLE !!>
| Attribute | Type | Required? | Description |
| --------- | ---- | --------- | ----------  |
| `i2c_bus` | string | **Required** | The index of the I<sup>2</sup>C bus on the board that the encoder is wired to. |
| `i2c_address` | string | Optional | Default: `0x77`. The [I<sup>2</sup>C device address](https://learn.adafruit.com/i2c-addresses/overview) of the encoder. |

## Example configuration

### `viam:ams:as5048`
```json
  {
      "name": "<your-ams-as5048-encoder-name>",
      "model": "viam:ams:as5048",
      "type": "encoder",
      "namespace": "rdk",
      "attributes": {
      },
      "depends_on": []
  }
```

### Next Steps
- To test your encoder, expand the **TEST** section of its configuration pane or go to the [**CONTROL** tab](https://docs.viam.com/fleet/control/).
- To write code against your encoder, use one of the [available SDKs](https://docs.viam.com/sdks/).
- To view examples using a encoder component, explore [these tutorials](https://docs.viam.com/tutorials/).