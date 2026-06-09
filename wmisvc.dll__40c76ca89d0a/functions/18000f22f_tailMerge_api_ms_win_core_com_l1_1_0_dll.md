# __tailMerge_api_ms_win_core_com_l1_1_0_dll

- ea: `0x18000f22f`
- end: `0x18000f2a8`
- name: `__tailMerge_api_ms_win_core_com_l1_1_0_dll`
- size: `121`
- prototype: `__int64(void)`
- caller_count: `12`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000f2ae`
- `0x18000f2c0`
- `0x18000f2d2`
- `0x18000f2e4`
- `0x18000f2f6`
- `0x18000f308`
- `0x18000f31a`
- `0x18000f3db`
- `0x18000f54b`
- `0x18000f55d`
- `0x1800101fc`
- `0x18001020e`

## callees

- `0x18000a5e0`
- `0x18000f22f`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_core_com_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_com_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000f22f  mov     [rsp+arg_0], rcx
0x18000f234  mov     [rsp+arg_8], rdx
0x18000f239  mov     [rsp+arg_10], r8
0x18000f23e  mov     [rsp+arg_18], r9
0x18000f243  sub     rsp, 68h
0x18000f247  movdqa  [rsp+68h+var_48], xmm0
0x18000f24d  movdqa  [rsp+68h+var_38], xmm1
0x18000f253  movdqa  [rsp+68h+var_28], xmm2
0x18000f259  movdqa  [rsp+68h+var_18], xmm3
0x18000f25f  mov     rdx, rax
0x18000f262  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_com_l1_1_0_dll
0x18000f269  call    __delayLoadHelper2
0x18000f26e  movdqa  xmm0, [rsp+68h+var_48]
0x18000f274  movdqa  xmm1, [rsp+68h+var_38]
0x18000f27a  movdqa  xmm2, [rsp+68h+var_28]
0x18000f280  movdqa  xmm3, [rsp+68h+var_18]
0x18000f286  mov     rcx, [rsp+68h+arg_0]
0x18000f28b  mov     rdx, [rsp+68h+arg_8]
0x18000f290  mov     r8, [rsp+68h+arg_10]
0x18000f298  mov     r9, [rsp+68h+arg_18]
0x18000f2a0  add     rsp, 68h
0x18000f2a4  jmp     short $+2
0x18000f2a6  jmp     rax
```
