# Feature_PackagedComElevationSupport__private_IsEnabledFallback

- ea: `0x18000661c`
- end: `0x180006628`
- name: `Feature_PackagedComElevationSupport__private_IsEnabledFallback`
- size: `12`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180006630`

## callees

- `0x18000b830`

## pseudocode

```c
__int64 __fastcall Feature_PackagedComElevationSupport__private_IsEnabledFallback(__int64 a1, __int64 a2)
{
  return wil_details_IsEnabledFallback(a1, a2, Feature_PackagedComElevationSupport__private_descriptor);
}

```

## disassembly

```asm
0x18000661c  lea     r8, Feature_PackagedComElevationSupport__private_descriptor
0x180006623  jmp     wil_details_IsEnabledFallback
```
