# Feature_CLAT_Preview2_RandomLocalAddress__private_IsEnabledDeviceUsageNoInline

- ea: `0x14000e390`
- end: `0x14000e3c5`
- name: `Feature_CLAT_Preview2_RandomLocalAddress__private_IsEnabledDeviceUsageNoInline`
- size: `53`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x14000ed90`
- `0x140016d4c`
- `0x1400177b8`
- `0x14001e4fc`
- `0x14001e58c`
- `0x14003476c`
- `0x140034cc0`
- `0x140034d80`

## callees

- `0x14000e390`
- `0x14000e3cc`

## pseudocode

```c
__int64 __fastcall Feature_CLAT_Preview2_RandomLocalAddress__private_IsEnabledDeviceUsageNoInline()
{
  if ( (Feature_CLAT_Preview2_RandomLocalAddress__private_featureState & 0x10) != 0 )
    return Feature_CLAT_Preview2_RandomLocalAddress__private_featureState & 1;
  else
    return Feature_CLAT_Preview2_RandomLocalAddress__private_IsEnabledFallback(
             (unsigned int)Feature_CLAT_Preview2_RandomLocalAddress__private_featureState,
             3);
}

```

## disassembly

```asm
0x14000e390  sub     rsp, 28h
0x14000e394  mov     eax, cs:Feature_CLAT_Preview2_RandomLocalAddress__private_featureState
0x14000e39a  mov     [rsp+28h+arg_0], 0
0x14000e3a3  mov     dword ptr [rsp+28h+arg_0], eax
0x14000e3a7  test    al, 10h
0x14000e3a9  jz      short loc_14000E3B0
0x14000e3ab  and     eax, 1
0x14000e3ae  jmp     short loc_14000E3BF
0x14000e3b0  mov     rcx, [rsp+28h+arg_0]
0x14000e3b5  mov     edx, 3
0x14000e3ba  call    Feature_CLAT_Preview2_RandomLocalAddress__private_IsEnabledFallback
0x14000e3bf  add     rsp, 28h
0x14000e3c3  retn
```
