# __tailMerge_api_ms_win_security_lsapolicy_l1_1_0_dll

- ea: `0x18001f739`
- end: `0x18001f7b2`
- name: `__tailMerge_api_ms_win_security_lsapolicy_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001f7b8`
- `0x18001f7ca`
- `0x18001f7ee`
- `0x18001f975`

## callees

- `0x18000c9b0`
- `0x18001f739`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_security_lsapolicy_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_lsapolicy_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18001f739  mov     [rsp+arg_0], rcx
0x18001f73e  mov     [rsp+arg_8], rdx
0x18001f743  mov     [rsp+arg_10], r8
0x18001f748  mov     [rsp+arg_18], r9
0x18001f74d  sub     rsp, 68h
0x18001f751  movdqa  [rsp+68h+var_48], xmm0
0x18001f757  movdqa  [rsp+68h+var_38], xmm1
0x18001f75d  movdqa  [rsp+68h+var_28], xmm2
0x18001f763  movdqa  [rsp+68h+var_18], xmm3
0x18001f769  mov     rdx, rax
0x18001f76c  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_lsapolicy_l1_1_0_dll
0x18001f773  call    __delayLoadHelper2
0x18001f778  movdqa  xmm0, [rsp+68h+var_48]
0x18001f77e  movdqa  xmm1, [rsp+68h+var_38]
0x18001f784  movdqa  xmm2, [rsp+68h+var_28]
0x18001f78a  movdqa  xmm3, [rsp+68h+var_18]
0x18001f790  mov     rcx, [rsp+68h+arg_0]
0x18001f795  mov     rdx, [rsp+68h+arg_8]
0x18001f79a  mov     r8, [rsp+68h+arg_10]
0x18001f7a2  mov     r9, [rsp+68h+arg_18]
0x18001f7aa  add     rsp, 68h
0x18001f7ae  jmp     short $+2
0x18001f7b0  jmp     rax
```
