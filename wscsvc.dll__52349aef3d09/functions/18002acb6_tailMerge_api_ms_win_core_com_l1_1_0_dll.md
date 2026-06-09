# __tailMerge_api_ms_win_core_com_l1_1_0_dll

- ea: `0x18002acb6`
- end: `0x18002ad2f`
- name: `__tailMerge_api_ms_win_core_com_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002ad35`
- `0x18002ae6f`
- `0x18002ae81`
- `0x18002af30`
- `0x18002afdf`
- `0x18002b003`
- `0x18002b254`
- `0x18002b266`

## callees

- `0x180020640`
- `0x18002acb6`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_core_com_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_com_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18002acb6  mov     [rsp+arg_0], rcx
0x18002acbb  mov     [rsp+arg_8], rdx
0x18002acc0  mov     [rsp+arg_10], r8
0x18002acc5  mov     [rsp+arg_18], r9
0x18002acca  sub     rsp, 68h
0x18002acce  movdqa  [rsp+68h+var_48], xmm0
0x18002acd4  movdqa  [rsp+68h+var_38], xmm1
0x18002acda  movdqa  [rsp+68h+var_28], xmm2
0x18002ace0  movdqa  [rsp+68h+var_18], xmm3
0x18002ace6  mov     rdx, rax
0x18002ace9  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_com_l1_1_0_dll
0x18002acf0  call    __delayLoadHelper2
0x18002acf5  movdqa  xmm0, [rsp+68h+var_48]
0x18002acfb  movdqa  xmm1, [rsp+68h+var_38]
0x18002ad01  movdqa  xmm2, [rsp+68h+var_28]
0x18002ad07  movdqa  xmm3, [rsp+68h+var_18]
0x18002ad0d  mov     rcx, [rsp+68h+arg_0]
0x18002ad12  mov     rdx, [rsp+68h+arg_8]
0x18002ad17  mov     r8, [rsp+68h+arg_10]
0x18002ad1f  mov     r9, [rsp+68h+arg_18]
0x18002ad27  add     rsp, 68h
0x18002ad2b  jmp     short $+2
0x18002ad2d  jmp     rax
```
