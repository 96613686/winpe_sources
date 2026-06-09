# __tailMerge_api_ms_win_security_audit_l1_1_1_dll

- ea: `0x18000ad04`
- end: `0x18000ad7d`
- name: `__tailMerge_api_ms_win_security_audit_l1_1_1_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000ad83`

## callees

- `0x180006050`
- `0x18000ad04`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_security_audit_l1_1_1_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_audit_l1_1_1_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000ad04  mov     [rsp+arg_0], rcx
0x18000ad09  mov     [rsp+arg_8], rdx
0x18000ad0e  mov     [rsp+arg_10], r8
0x18000ad13  mov     [rsp+arg_18], r9
0x18000ad18  sub     rsp, 68h
0x18000ad1c  movdqa  [rsp+68h+var_48], xmm0
0x18000ad22  movdqa  [rsp+68h+var_38], xmm1
0x18000ad28  movdqa  [rsp+68h+var_28], xmm2
0x18000ad2e  movdqa  [rsp+68h+var_18], xmm3
0x18000ad34  mov     rdx, rax
0x18000ad37  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_audit_l1_1_1_dll
0x18000ad3e  call    __delayLoadHelper2
0x18000ad43  movdqa  xmm0, [rsp+68h+var_48]
0x18000ad49  movdqa  xmm1, [rsp+68h+var_38]
0x18000ad4f  movdqa  xmm2, [rsp+68h+var_28]
0x18000ad55  movdqa  xmm3, [rsp+68h+var_18]
0x18000ad5b  mov     rcx, [rsp+68h+arg_0]
0x18000ad60  mov     rdx, [rsp+68h+arg_8]
0x18000ad65  mov     r8, [rsp+68h+arg_10]
0x18000ad6d  mov     r9, [rsp+68h+arg_18]
0x18000ad75  add     rsp, 68h
0x18000ad79  jmp     short $+2
0x18000ad7b  jmp     rax
```
