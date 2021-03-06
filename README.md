## TLV

[![GoDoc](https://godoc.org/github.com/Akagi201/tlv?status.svg)](https://godoc.org/github.com/Akagi201/tlv)

[TLV](https://en.wikipedia.org/wiki/Type-length-value) is the representative of type-length-value.

It might be found in a binary file format or a network protocol.

This is a fork from [github.com/Akagi201/tlv](https://github.com/Akagi201/tlv). Just some minor changes:

- Set TLV Lenght to just 1 byte (uint8)
- Introduced GetThemAll(), to get a slice with all TLVs found

## Brief

One TLV Object:

```
 1 Byte   1 Byte   $Length Bytes
+-------+---------+-------------+
| Type  | Length  |    Value    |
+-------+---------+-------------+
```

Serial TLV Objects:

```
 1 Byte   1 Byte   $Length Bytes 1 Byte   1 Byte   $Length Bytes
+-------+---------+-------------+-------+---------+-------------+
| Type  | Length  |    Value    | Type  | Length  |    Value    | ...
+-------+---------+-------------+-------+---------+-------------+
```

Embedded TLV Objects:

```
 1 Byte   1 Byte           $Length Bytes
                   1 Byte   1 Byte   $Length Bytes
+-------+---------+-------+---------+-------------+
| Type  | Length  | Type  | Length  |    Value    |
+-------+---------+-------+---------+-------------+
```
