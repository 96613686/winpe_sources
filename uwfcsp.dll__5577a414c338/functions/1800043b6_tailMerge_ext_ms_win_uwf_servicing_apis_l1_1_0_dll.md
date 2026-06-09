# __tailMerge_ext_ms_win_uwf_servicing_apis_l1_1_0_dll

- ea: `0x1800043b6`
- end: `0x18000442f`
- name: `__tailMerge_ext_ms_win_uwf_servicing_apis_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x180004435`
- `0x180004447`

## callees

- `0x1800043b6`
- `0x18001a190`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_uwf_servicing_apis_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_uwf_servicing_apis_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800043b6  mov     [rsp+arg_0], rcx
0x1800043bb  mov     [rsp+arg_8], rdx
0x1800043c0  mov     [rsp+arg_10], r8
0x1800043c5  mov     [rsp+arg_18], r9
0x1800043ca  sub     rsp, 68h
0x1800043ce  movdqa  [rsp+68h+var_48], xmm0
0x1800043d4  movdqa  [rsp+68h+var_38], xmm1
0x1800043da  movdqa  [rsp+68h+var_28], xmm2
0x1800043e0  movdqa  [rsp+68h+var_18], xmm3
0x1800043e6  mov     rdx, rax
0x1800043e9  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_uwf_servicing_apis_l1_1_0_dll
0x1800043f0  call    __delayLoadHelper2
0x1800043f5  movdqa  xmm0, [rsp+68h+var_48]
0x1800043fb  movdqa  xmm1, [rsp+68h+var_38]
0x180004401  movdqa  xmm2, [rsp+68h+var_28]
0x180004407  movdqa  xmm3, [rsp+68h+var_18]
0x18000440d  mov     rcx, [rsp+68h+arg_0]
0x180004412  mov     rdx, [rsp+68h+arg_8]
0x180004417  mov     r8, [rsp+68h+arg_10]
0x18000441f  mov     r9, [rsp+68h+arg_18]
0x180004427  add     rsp, 68h
0x18000442b  jmp     short $+2
0x18000442d  jmp     rax
```
