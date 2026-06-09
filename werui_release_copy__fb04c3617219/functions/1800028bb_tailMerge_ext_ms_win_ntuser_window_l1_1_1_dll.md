# __tailMerge_ext_ms_win_ntuser_window_l1_1_1_dll

- ea: `0x1800028bb`
- end: `0x180002934`
- name: `__tailMerge_ext_ms_win_ntuser_window_l1_1_1_dll`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000293a`
- `0x180002970`
- `0x180002a55`

## callees

- `0x1800028bb`
- `0x180016ac0`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_ntuser_window_l1_1_1_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_window_l1_1_1_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800028bb  mov     [rsp+arg_0], rcx
0x1800028c0  mov     [rsp+arg_8], rdx
0x1800028c5  mov     [rsp+arg_10], r8
0x1800028ca  mov     [rsp+arg_18], r9
0x1800028cf  sub     rsp, 68h
0x1800028d3  movdqa  [rsp+68h+var_48], xmm0
0x1800028d9  movdqa  [rsp+68h+var_38], xmm1
0x1800028df  movdqa  [rsp+68h+var_28], xmm2
0x1800028e5  movdqa  [rsp+68h+var_18], xmm3
0x1800028eb  mov     rdx, rax
0x1800028ee  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_window_l1_1_1_dll
0x1800028f5  call    __delayLoadHelper2
0x1800028fa  movdqa  xmm0, [rsp+68h+var_48]
0x180002900  movdqa  xmm1, [rsp+68h+var_38]
0x180002906  movdqa  xmm2, [rsp+68h+var_28]
0x18000290c  movdqa  xmm3, [rsp+68h+var_18]
0x180002912  mov     rcx, [rsp+68h+arg_0]
0x180002917  mov     rdx, [rsp+68h+arg_8]
0x18000291c  mov     r8, [rsp+68h+arg_10]
0x180002924  mov     r9, [rsp+68h+arg_18]
0x18000292c  add     rsp, 68h
0x180002930  jmp     short $+2
0x180002932  jmp     rax
```
