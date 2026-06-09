# __tailMerge_ext_ms_win_ntuser_misc_l1_1_0_dll

- ea: `0x140008cc8`
- end: `0x140008d41`
- name: `__tailMerge_ext_ms_win_ntuser_misc_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140008d47`
- `0x140008d59`

## callees

- `0x140006020`
- `0x140008cc8`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_ntuser_misc_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_misc_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x140008cc8  mov     [rsp+arg_0], rcx
0x140008ccd  mov     [rsp+arg_8], rdx
0x140008cd2  mov     [rsp+arg_10], r8
0x140008cd7  mov     [rsp+arg_18], r9
0x140008cdc  sub     rsp, 68h
0x140008ce0  movdqa  [rsp+68h+var_48], xmm0
0x140008ce6  movdqa  [rsp+68h+var_38], xmm1
0x140008cec  movdqa  [rsp+68h+var_28], xmm2
0x140008cf2  movdqa  [rsp+68h+var_18], xmm3
0x140008cf8  mov     rdx, rax
0x140008cfb  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_misc_l1_1_0_dll
0x140008d02  call    __delayLoadHelper2
0x140008d07  movdqa  xmm0, [rsp+68h+var_48]
0x140008d0d  movdqa  xmm1, [rsp+68h+var_38]
0x140008d13  movdqa  xmm2, [rsp+68h+var_28]
0x140008d19  movdqa  xmm3, [rsp+68h+var_18]
0x140008d1f  mov     rcx, [rsp+68h+arg_0]
0x140008d24  mov     rdx, [rsp+68h+arg_8]
0x140008d29  mov     r8, [rsp+68h+arg_10]
0x140008d31  mov     r9, [rsp+68h+arg_18]
0x140008d39  add     rsp, 68h
0x140008d3d  jmp     short $+2
0x140008d3f  jmp     rax
```
