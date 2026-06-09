# __tailMerge_api_ms_win_security_sddl_l1_1_0_dll

- ea: `0x18000cd8a`
- end: `0x18000ce03`
- name: `__tailMerge_api_ms_win_security_sddl_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000ce09`
- `0x18000ce1b`

## callees

- `0x180008bd0`
- `0x18000cd8a`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_security_sddl_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_sddl_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000cd8a  mov     [rsp+arg_0], rcx
0x18000cd8f  mov     [rsp+arg_8], rdx
0x18000cd94  mov     [rsp+arg_10], r8
0x18000cd99  mov     [rsp+arg_18], r9
0x18000cd9e  sub     rsp, 68h
0x18000cda2  movdqa  [rsp+68h+var_48], xmm0
0x18000cda8  movdqa  [rsp+68h+var_38], xmm1
0x18000cdae  movdqa  [rsp+68h+var_28], xmm2
0x18000cdb4  movdqa  [rsp+68h+var_18], xmm3
0x18000cdba  mov     rdx, rax
0x18000cdbd  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_sddl_l1_1_0_dll
0x18000cdc4  call    __delayLoadHelper2
0x18000cdc9  movdqa  xmm0, [rsp+68h+var_48]
0x18000cdcf  movdqa  xmm1, [rsp+68h+var_38]
0x18000cdd5  movdqa  xmm2, [rsp+68h+var_28]
0x18000cddb  movdqa  xmm3, [rsp+68h+var_18]
0x18000cde1  mov     rcx, [rsp+68h+arg_0]
0x18000cde6  mov     rdx, [rsp+68h+arg_8]
0x18000cdeb  mov     r8, [rsp+68h+arg_10]
0x18000cdf3  mov     r9, [rsp+68h+arg_18]
0x18000cdfb  add     rsp, 68h
0x18000cdff  jmp     short $+2
0x18000ce01  jmp     rax
```
