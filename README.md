# [`ams` module](https://github.com/viam-modules/ams)

This [ams module](https://app.viam.com/module/viam/ams) implements an ams [as5048 encoder](https://ams.com/en/as5048a), an absolute encoder that uses an I2C or SPI interface to connect, using the [`rdk:component:encoder` API](https://docs.viam.com/appendix/apis/components/encoder/).

> [!NOTE]
> Before configuring your encoder, you must [create a machine](https://docs.viam.com/cloud/machines/#add-a-new-machine).

Navigate to the [**CONFIGURE** tab](https://docs.viam.com/configure/) of your [machine](https://docs.viam.com/fleet/machines/) in the [Viam app](https://app.viam.com/).
[Add encoder / ams:as5048 to your machine](https://docs.viam.com/configure/#components).

## Configure your as5048 encoder

On the new component panel, copy and paste the following attribute template into your encoder's attributes field:

```json
{
  "connection_type": "i2c",
  "i2c_attributes": {
    "i2c_bus": "<your-i2c-bus-index-on-board>",
    "i2c_addr": <int>
  }
}
```

> [!IMPORTANT]
> Any [motor](https://docs.viam.com/components/motor/) using the `AMS-AS5048` encoder must have its `ticks_per_rotation` attribute configured as `1` because this encoder provides angular measurements directly.

### Attributes

The following attributes are available for `viam:ams:as5048` encoders:

| Attribute | Type | Required? | Description |
| --------- | ---- | --------- | ----------  |
| `connection_type` | string | **Required** | Use `"i2c"`. |
| `i2c_attributes` | object | **Required** | The attributes to configure the I2C connection: `i2c_bus` and `i2c_addr` |
| `i2c_bus` | object | **Required** | The index of the I2C bus on the [board](https://docs.viam.com/components/board/) wired to this encoder.  Example: `"1"` |
| `i2c_addr` | object | **Required** | The address of the bus. Example: `64` |

### Example configuration

```json
  {
    "connection_type": "i2c",
    "i2c_attributes": {
      "i2c_bus": "1",
      "i2c_addr": 64
    }
  }
```

### Next Steps

- To test your encoder, expand the **TEST** section of its configuration pane or go to the [**CONTROL** tab](https://docs.viam.com/fleet/control/).
- To write code against your encoder, use one of the [available SDKs](https://docs.viam.com/sdks/).
- To view examples using a encoder component, explore [these tutorials](https://docs.viam.com/tutorials/).
