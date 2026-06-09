# __tailMerge_api_ms_win_security_lsalookup_l1_1_0_dll

- ea: `0x180018c5d`
- end: `0x180018cd6`
- name: `__tailMerge_api_ms_win_security_lsalookup_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180018cdc`
- `0x180018cee`
- `0x180018d00`
- `0x180018d12`

## callees

- `0x180018c5d`
- `0x180021f30`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_security_lsalookup_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_lsalookup_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180018c5d  mov     [rsp+arg_0], rcx
0x180018c62  mov     [rsp+arg_8], rdx
0x180018c67  mov     [rsp+arg_10], r8
0x180018c6c  mov     [rsp+arg_18], r9
0x180018c71  sub     rsp, 68h
0x180018c75  movdqa  [rsp+68h+var_48], xmm0
0x180018c7b  movdqa  [rsp+68h+var_38], xmm1
0x180018c81  movdqa  [rsp+68h+var_28], xmm2
0x180018c87  movdqa  [rsp+68h+var_18], xmm3
0x180018c8d  mov     rdx, rax
0x180018c90  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_lsalookup_l1_1_0_dll
0x180018c97  call    __delayLoadHelper2
0x180018c9c  movdqa  xmm0, [rsp+68h+var_48]
0x180018ca2  movdqa  xmm1, [rsp+68h+var_38]
0x180018ca8  movdqa  xmm2, [rsp+68h+var_28]
0x180018cae  movdqa  xmm3, [rsp+68h+var_18]
0x180018cb4  mov     rcx, [rsp+68h+arg_0]
0x180018cb9  mov     rdx, [rsp+68h+arg_8]
0x180018cbe  mov     r8, [rsp+68h+arg_10]
0x180018cc6  mov     r9, [rsp+68h+arg_18]
0x180018cce  add     rsp, 68h
0x180018cd2  jmp     short $+2
0x180018cd4  jmp     rax
```
