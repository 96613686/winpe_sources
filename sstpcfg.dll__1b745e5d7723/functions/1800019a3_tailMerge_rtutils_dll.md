# __tailMerge_rtutils_dll

- ea: `0x1800019a3`
- end: `0x180001a1c`
- name: `__tailMerge_rtutils_dll`
- size: `121`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001a22`
- `0x180001a34`
- `0x180001a46`
- `0x180001a58`

## callees

- `0x1800019a3`
- `0x18000ad60`

## pseudocode

```c
__int64 __fastcall _tailMerge_rtutils_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_rtutils_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800019a3  mov     [rsp+arg_0], rcx
0x1800019a8  mov     [rsp+arg_8], rdx
0x1800019ad  mov     [rsp+arg_10], r8
0x1800019b2  mov     [rsp+arg_18], r9
0x1800019b7  sub     rsp, 68h
0x1800019bb  movdqa  [rsp+68h+var_48], xmm0
0x1800019c1  movdqa  [rsp+68h+var_38], xmm1
0x1800019c7  movdqa  [rsp+68h+var_28], xmm2
0x1800019cd  movdqa  [rsp+68h+var_18], xmm3
0x1800019d3  mov     rdx, rax
0x1800019d6  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_rtutils_dll
0x1800019dd  call    __delayLoadHelper2
0x1800019e2  movdqa  xmm0, [rsp+68h+var_48]
0x1800019e8  movdqa  xmm1, [rsp+68h+var_38]
0x1800019ee  movdqa  xmm2, [rsp+68h+var_28]
0x1800019f4  movdqa  xmm3, [rsp+68h+var_18]
0x1800019fa  mov     rcx, [rsp+68h+arg_0]
0x1800019ff  mov     rdx, [rsp+68h+arg_8]
0x180001a04  mov     r8, [rsp+68h+arg_10]
0x180001a0c  mov     r9, [rsp+68h+arg_18]
0x180001a14  add     rsp, 68h
0x180001a18  jmp     short $+2
0x180001a1a  jmp     rax
```
