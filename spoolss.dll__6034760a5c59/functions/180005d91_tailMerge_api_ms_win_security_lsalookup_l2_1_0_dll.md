# __tailMerge_api_ms_win_security_lsalookup_l2_1_0_dll

- ea: `0x180005d91`
- end: `0x180005e0a`
- name: `__tailMerge_api_ms_win_security_lsalookup_l2_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180005e10`

## callees

- `0x180005d91`
- `0x180014d80`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_security_lsalookup_l2_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_lsalookup_l2_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180005d91  mov     [rsp+arg_0], rcx
0x180005d96  mov     [rsp+arg_8], rdx
0x180005d9b  mov     [rsp+arg_10], r8
0x180005da0  mov     [rsp+arg_18], r9
0x180005da5  sub     rsp, 68h
0x180005da9  movdqa  [rsp+68h+var_48], xmm0
0x180005daf  movdqa  [rsp+68h+var_38], xmm1
0x180005db5  movdqa  [rsp+68h+var_28], xmm2
0x180005dbb  movdqa  [rsp+68h+var_18], xmm3
0x180005dc1  mov     rdx, rax
0x180005dc4  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_lsalookup_l2_1_0_dll
0x180005dcb  call    __delayLoadHelper2
0x180005dd0  movdqa  xmm0, [rsp+68h+var_48]
0x180005dd6  movdqa  xmm1, [rsp+68h+var_38]
0x180005ddc  movdqa  xmm2, [rsp+68h+var_28]
0x180005de2  movdqa  xmm3, [rsp+68h+var_18]
0x180005de8  mov     rcx, [rsp+68h+arg_0]
0x180005ded  mov     rdx, [rsp+68h+arg_8]
0x180005df2  mov     r8, [rsp+68h+arg_10]
0x180005dfa  mov     r9, [rsp+68h+arg_18]
0x180005e02  add     rsp, 68h
0x180005e06  jmp     short $+2
0x180005e08  jmp     rax
```
