# __tailMerge_ext_ms_win_shell_shell32_l1_2_0_dll

- ea: `0x180036c66`
- end: `0x180036cdf`
- name: `__tailMerge_ext_ms_win_shell_shell32_l1_2_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180036ce5`

## callees

- `0x180036c66`
- `0x180043490`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_shell_shell32_l1_2_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_shell_shell32_l1_2_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180036c66  mov     [rsp+arg_0], rcx
0x180036c6b  mov     [rsp+arg_8], rdx
0x180036c70  mov     [rsp+arg_10], r8
0x180036c75  mov     [rsp+arg_18], r9
0x180036c7a  sub     rsp, 68h
0x180036c7e  movdqa  [rsp+68h+var_48], xmm0
0x180036c84  movdqa  [rsp+68h+var_38], xmm1
0x180036c8a  movdqa  [rsp+68h+var_28], xmm2
0x180036c90  movdqa  [rsp+68h+var_18], xmm3
0x180036c96  mov     rdx, rax
0x180036c99  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_shell_shell32_l1_2_0_dll
0x180036ca0  call    __delayLoadHelper2
0x180036ca5  movdqa  xmm0, [rsp+68h+var_48]
0x180036cab  movdqa  xmm1, [rsp+68h+var_38]
0x180036cb1  movdqa  xmm2, [rsp+68h+var_28]
0x180036cb7  movdqa  xmm3, [rsp+68h+var_18]
0x180036cbd  mov     rcx, [rsp+68h+arg_0]
0x180036cc2  mov     rdx, [rsp+68h+arg_8]
0x180036cc7  mov     r8, [rsp+68h+arg_10]
0x180036ccf  mov     r9, [rsp+68h+arg_18]
0x180036cd7  add     rsp, 68h
0x180036cdb  jmp     short $+2
0x180036cdd  jmp     rax
```
