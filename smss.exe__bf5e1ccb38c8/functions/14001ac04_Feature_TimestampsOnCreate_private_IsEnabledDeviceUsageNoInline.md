# Feature_TimestampsOnCreate__private_IsEnabledDeviceUsageNoInline

- ea: `0x14001ac04`
- end: `0x14001ac2e`
- name: `Feature_TimestampsOnCreate__private_IsEnabledDeviceUsageNoInline`
- size: `42`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14001a3fc`

## callees

- `0x14001ac04`
- `0x14001ac34`

## pseudocode

```c
__int64 Feature_TimestampsOnCreate__private_IsEnabledDeviceUsageNoInline()
{
  if ( (Feature_TimestampsOnCreate__private_featureState & 0x10) != 0 )
    return Feature_TimestampsOnCreate__private_featureState & 1;
  else
    return Feature_TimestampsOnCreate__private_IsEnabledFallback(
             (unsigned int)Feature_TimestampsOnCreate__private_featureState,
             3);
}

```

## disassembly

```asm
0x14001ac04  mov     eax, cs:Feature_TimestampsOnCreate__private_featureState
0x14001ac0a  mov     [rsp+arg_0], 0
0x14001ac13  mov     dword ptr [rsp+arg_0], eax
0x14001ac17  test    al, 10h
0x14001ac19  jz      short loc_14001AC1F
0x14001ac1b  and     eax, 1
0x14001ac1e  retn
0x14001ac1f  mov     rcx, [rsp+arg_0]
0x14001ac24  mov     edx, 3
0x14001ac29  jmp     Feature_TimestampsOnCreate__private_IsEnabledFallback
```
