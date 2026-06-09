# __tailMerge_api_ms_win_security_credentials_l2_1_0_dll

- ea: `0x18000c4e1`
- end: `0x18000c55a`
- name: `__tailMerge_api_ms_win_security_credentials_l2_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000c560`

## callees

- `0x180009770`
- `0x18000c4e1`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_security_credentials_l2_1_0_dll(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_credentials_l2_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000c4e1  mov     [rsp+arg_0], rcx
0x18000c4e6  mov     [rsp+arg_8], rdx
0x18000c4eb  mov     [rsp+arg_10], r8
0x18000c4f0  mov     [rsp+arg_18], r9
0x18000c4f5  sub     rsp, 68h
0x18000c4f9  movdqa  [rsp+68h+var_48], xmm0
0x18000c4ff  movdqa  [rsp+68h+var_38], xmm1
0x18000c505  movdqa  [rsp+68h+var_28], xmm2
0x18000c50b  movdqa  [rsp+68h+var_18], xmm3
0x18000c511  mov     rdx, rax
0x18000c514  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_credentials_l2_1_0_dll
0x18000c51b  call    __delayLoadHelper2
0x18000c520  movdqa  xmm0, [rsp+68h+var_48]
0x18000c526  movdqa  xmm1, [rsp+68h+var_38]
0x18000c52c  movdqa  xmm2, [rsp+68h+var_28]
0x18000c532  movdqa  xmm3, [rsp+68h+var_18]
0x18000c538  mov     rcx, [rsp+68h+arg_0]
0x18000c53d  mov     rdx, [rsp+68h+arg_8]
0x18000c542  mov     r8, [rsp+68h+arg_10]
0x18000c54a  mov     r9, [rsp+68h+arg_18]
0x18000c552  add     rsp, 68h
0x18000c556  jmp     short $+2
0x18000c558  jmp     rax
```
