# __tailMerge_ext_ms_win_shell_shell32_l1_2_0_dll

- ea: `0x18000d622`
- end: `0x18000d69b`
- name: `__tailMerge_ext_ms_win_shell_shell32_l1_2_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000d6a1`

## callees

- `0x180008bd0`
- `0x18000d622`

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
0x18000d622  mov     [rsp+arg_0], rcx
0x18000d627  mov     [rsp+arg_8], rdx
0x18000d62c  mov     [rsp+arg_10], r8
0x18000d631  mov     [rsp+arg_18], r9
0x18000d636  sub     rsp, 68h
0x18000d63a  movdqa  [rsp+68h+var_48], xmm0
0x18000d640  movdqa  [rsp+68h+var_38], xmm1
0x18000d646  movdqa  [rsp+68h+var_28], xmm2
0x18000d64c  movdqa  [rsp+68h+var_18], xmm3
0x18000d652  mov     rdx, rax
0x18000d655  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_shell_shell32_l1_2_0_dll
0x18000d65c  call    __delayLoadHelper2
0x18000d661  movdqa  xmm0, [rsp+68h+var_48]
0x18000d667  movdqa  xmm1, [rsp+68h+var_38]
0x18000d66d  movdqa  xmm2, [rsp+68h+var_28]
0x18000d673  movdqa  xmm3, [rsp+68h+var_18]
0x18000d679  mov     rcx, [rsp+68h+arg_0]
0x18000d67e  mov     rdx, [rsp+68h+arg_8]
0x18000d683  mov     r8, [rsp+68h+arg_10]
0x18000d68b  mov     r9, [rsp+68h+arg_18]
0x18000d693  add     rsp, 68h
0x18000d697  jmp     short $+2
0x18000d699  jmp     rax
```
