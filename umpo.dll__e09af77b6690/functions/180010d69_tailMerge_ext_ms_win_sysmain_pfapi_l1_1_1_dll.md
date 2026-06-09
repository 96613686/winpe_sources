# __tailMerge_ext_ms_win_sysmain_pfapi_l1_1_1_dll

- ea: `0x180010d69`
- end: `0x180010de2`
- name: `__tailMerge_ext_ms_win_sysmain_pfapi_l1_1_1_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180010de8`
- `0x180010dfa`
- `0x180010e0c`

## callees

- `0x180010d69`
- `0x180018770`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_sysmain_pfapi_l1_1_1_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_sysmain_pfapi_l1_1_1_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180010d69  mov     [rsp+arg_0], rcx
0x180010d6e  mov     [rsp+arg_8], rdx
0x180010d73  mov     [rsp+arg_10], r8
0x180010d78  mov     [rsp+arg_18], r9
0x180010d7d  sub     rsp, 68h
0x180010d81  movdqa  [rsp+68h+var_48], xmm0
0x180010d87  movdqa  [rsp+68h+var_38], xmm1
0x180010d8d  movdqa  [rsp+68h+var_28], xmm2
0x180010d93  movdqa  [rsp+68h+var_18], xmm3
0x180010d99  mov     rdx, rax
0x180010d9c  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_sysmain_pfapi_l1_1_1_dll
0x180010da3  call    __delayLoadHelper2
0x180010da8  movdqa  xmm0, [rsp+68h+var_48]
0x180010dae  movdqa  xmm1, [rsp+68h+var_38]
0x180010db4  movdqa  xmm2, [rsp+68h+var_28]
0x180010dba  movdqa  xmm3, [rsp+68h+var_18]
0x180010dc0  mov     rcx, [rsp+68h+arg_0]
0x180010dc5  mov     rdx, [rsp+68h+arg_8]
0x180010dca  mov     r8, [rsp+68h+arg_10]
0x180010dd2  mov     r9, [rsp+68h+arg_18]
0x180010dda  add     rsp, 68h
0x180010dde  jmp     short $+2
0x180010de0  jmp     rax
```
