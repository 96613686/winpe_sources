# __tailMerge_ext_ms_win_ntuser_window_l1_1_3_dll

- ea: `0x18000275d`
- end: `0x1800027d6`
- name: `__tailMerge_ext_ms_win_ntuser_window_l1_1_3_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800027dc`

## callees

- `0x18000275d`
- `0x180016ac0`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_ntuser_window_l1_1_3_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_window_l1_1_3_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000275d  mov     [rsp+arg_0], rcx
0x180002762  mov     [rsp+arg_8], rdx
0x180002767  mov     [rsp+arg_10], r8
0x18000276c  mov     [rsp+arg_18], r9
0x180002771  sub     rsp, 68h
0x180002775  movdqa  [rsp+68h+var_48], xmm0
0x18000277b  movdqa  [rsp+68h+var_38], xmm1
0x180002781  movdqa  [rsp+68h+var_28], xmm2
0x180002787  movdqa  [rsp+68h+var_18], xmm3
0x18000278d  mov     rdx, rax
0x180002790  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_window_l1_1_3_dll
0x180002797  call    __delayLoadHelper2
0x18000279c  movdqa  xmm0, [rsp+68h+var_48]
0x1800027a2  movdqa  xmm1, [rsp+68h+var_38]
0x1800027a8  movdqa  xmm2, [rsp+68h+var_28]
0x1800027ae  movdqa  xmm3, [rsp+68h+var_18]
0x1800027b4  mov     rcx, [rsp+68h+arg_0]
0x1800027b9  mov     rdx, [rsp+68h+arg_8]
0x1800027be  mov     r8, [rsp+68h+arg_10]
0x1800027c6  mov     r9, [rsp+68h+arg_18]
0x1800027ce  add     rsp, 68h
0x1800027d2  jmp     short $+2
0x1800027d4  jmp     rax
```
