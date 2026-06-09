# Microsoft.Internal.PInvoke.Extensions::AsFeatureConfigurationType

- ea: `0xac0`
- end: `0xacc`
- name: `Microsoft.Internal.PInvoke.Extensions::AsFeatureConfigurationType`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0xa80`
- `0xac0`

## pseudocode

```c

```

## disassembly

```asm
0xac0  ldarg.0
0xac1  call     bool Microsoft.Internal.PInvoke.Extensions::RequiresSessionChange(valuetype FEATURE_CHANGE_TIME changeTime)
0xac6  brfalse.s loc_ACA
0xac8  ldc.i4.0
0xac9  ret
0xaca  ldc.i4.1
0xacb  ret
```
