# Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline

- ea: `0x140013738`
- end: `0x140013762`
- name: `Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline`
- size: `42`
- prototype: `__int64()`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x140013938`
- `0x14001415c`
- `0x140015e14`
- `0x140016070`
- `0x1400176a4`
- `0x140017730`
- `0x140017be4`

## callees

- `0x140013738`
- `0x140013768`

## pseudocode

```c
__int64 Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline()
{
  if ( (Feature_SdbValidateRootTagsOnOpen__private_featureState & 0x10) != 0 )
    return Feature_SdbValidateRootTagsOnOpen__private_featureState & 1;
  else
    return Feature_SdbValidateRootTagsOnOpen__private_IsEnabledFallback(
             (unsigned int)Feature_SdbValidateRootTagsOnOpen__private_featureState,
             3);
}

```

## disassembly

```asm
0x140013738  mov     eax, cs:Feature_SdbValidateRootTagsOnOpen__private_featureState
0x14001373e  mov     [rsp+arg_0], 0
0x140013747  mov     dword ptr [rsp+arg_0], eax
0x14001374b  test    al, 10h
0x14001374d  jz      short loc_140013753
0x14001374f  and     eax, 1
0x140013752  retn
0x140013753  mov     rcx, [rsp+arg_0]
0x140013758  mov     edx, 3
0x14001375d  jmp     Feature_SdbValidateRootTagsOnOpen__private_IsEnabledFallback
```
