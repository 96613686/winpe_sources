# Feature_TPMDriverMemoryTISWriteFix__private_IsEnabledDeviceUsageNoInline

- ea: `0x1400193c8`
- end: `0x1400193fd`
- name: `Feature_TPMDriverMemoryTISWriteFix__private_IsEnabledDeviceUsageNoInline`
- size: `53`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x140001a30`
- `0x14000ff70`
- `0x140018978`
- `0x140018a30`
- `0x140018fc8`

## callees

- `0x1400193c8`
- `0x140019404`

## pseudocode

```c
__int64 Feature_TPMDriverMemoryTISWriteFix__private_IsEnabledDeviceUsageNoInline()
{
  if ( (Feature_TPMDriverMemoryTISWriteFix__private_featureState & 0x10) != 0 )
    return Feature_TPMDriverMemoryTISWriteFix__private_featureState & 1;
  else
    return Feature_TPMDriverMemoryTISWriteFix__private_IsEnabledFallback(
             (unsigned int)Feature_TPMDriverMemoryTISWriteFix__private_featureState,
             3);
}

```

## disassembly

```asm
0x1400193c8  sub     rsp, 28h
0x1400193cc  mov     eax, cs:Feature_TPMDriverMemoryTISWriteFix__private_featureState
0x1400193d2  mov     [rsp+28h+arg_0], 0
0x1400193db  mov     dword ptr [rsp+28h+arg_0], eax
0x1400193df  test    al, 10h
0x1400193e1  jz      short loc_1400193E8
0x1400193e3  and     eax, 1
0x1400193e6  jmp     short loc_1400193F7
0x1400193e8  mov     rcx, [rsp+28h+arg_0]
0x1400193ed  mov     edx, 3
0x1400193f2  call    Feature_TPMDriverMemoryTISWriteFix__private_IsEnabledFallback
0x1400193f7  add     rsp, 28h
0x1400193fb  retn
```
