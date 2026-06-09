# TimeZoneSyncTask.Core.XmlDataTransform::ReadXmlAttributes

- ea: `0x126b0`
- end: `0x1270a`
- name: `TimeZoneSyncTask.Core.XmlDataTransform::ReadXmlAttributes`
- size: `90`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x120f0`
- `0x121c0`
- `0x123f0`
- `0x12530`

## callees

- `0x126b0`

## pseudocode

```c

```

## disassembly

```asm
0x126b0  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x126b5  stloc.0
0x126b6  ldarg.0
0x126b7  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToFirstAttribute()
0x126bc  brfalse.s loc_12708
0x126be  ldarg.1
0x126bf  ldarg.0
0x126c0  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0x126c5  call     T0x2B00003D
0x126ca  brfalse.s loc_12700
0x126cc  ldloc.0
0x126cd  ldarg.0
0x126ce  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0x126d3  ldarg.0
0x126d4  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Value()
0x126d9  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x126de  br.s     loc_12700
0x126e0  ldarg.1
0x126e1  ldarg.0
0x126e2  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0x126e7  call     T0x2B00003D
0x126ec  brfalse.s loc_12700
0x126ee  ldloc.0
0x126ef  ldarg.0
0x126f0  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0x126f5  ldarg.0
0x126f6  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Value()
0x126fb  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x12700  ldarg.0
0x12701  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToNextAttribute()
0x12706  brtrue.s loc_126E0
0x12708  ldloc.0
0x12709  ret
```
