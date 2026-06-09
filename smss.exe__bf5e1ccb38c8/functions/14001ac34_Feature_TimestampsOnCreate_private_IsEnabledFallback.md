# Feature_TimestampsOnCreate__private_IsEnabledFallback

- ea: `0x14001ac34`
- end: `0x14001ac40`
- name: `Feature_TimestampsOnCreate__private_IsEnabledFallback`
- size: `12`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14001ac04`

## callees

- `0x1400176c0`

## pseudocode

```c
__int64 __fastcall Feature_TimestampsOnCreate__private_IsEnabledFallback(__int64 a1, __int64 a2)
{
  return wil_details_IsEnabledFallback(a1, a2, Feature_TimestampsOnCreate__private_descriptor);
}

```

## disassembly

```asm
0x14001ac34  lea     r8, Feature_TimestampsOnCreate__private_descriptor
0x14001ac3b  jmp     wil_details_IsEnabledFallback
```
