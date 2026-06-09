# __tailMerge_ext_ms_win_ntuser_windowclass_l1_1_0_dll

- ea: `0x18000d811`
- end: `0x18000d88a`
- name: `__tailMerge_ext_ms_win_ntuser_windowclass_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000d890`
- `0x18000d8a2`
- `0x18000d8b4`

## callees

- `0x180009370`
- `0x18000d811`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_ntuser_windowclass_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_windowclass_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000d811  mov     [rsp+arg_0], rcx
0x18000d816  mov     [rsp+arg_8], rdx
0x18000d81b  mov     [rsp+arg_10], r8
0x18000d820  mov     [rsp+arg_18], r9
0x18000d825  sub     rsp, 68h
0x18000d829  movdqa  [rsp+68h+var_48], xmm0
0x18000d82f  movdqa  [rsp+68h+var_38], xmm1
0x18000d835  movdqa  [rsp+68h+var_28], xmm2
0x18000d83b  movdqa  [rsp+68h+var_18], xmm3
0x18000d841  mov     rdx, rax
0x18000d844  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_windowclass_l1_1_0_dll
0x18000d84b  call    __delayLoadHelper2
0x18000d850  movdqa  xmm0, [rsp+68h+var_48]
0x18000d856  movdqa  xmm1, [rsp+68h+var_38]
0x18000d85c  movdqa  xmm2, [rsp+68h+var_28]
0x18000d862  movdqa  xmm3, [rsp+68h+var_18]
0x18000d868  mov     rcx, [rsp+68h+arg_0]
0x18000d86d  mov     rdx, [rsp+68h+arg_8]
0x18000d872  mov     r8, [rsp+68h+arg_10]
0x18000d87a  mov     r9, [rsp+68h+arg_18]
0x18000d882  add     rsp, 68h
0x18000d886  jmp     short $+2
0x18000d888  jmp     rax
```
