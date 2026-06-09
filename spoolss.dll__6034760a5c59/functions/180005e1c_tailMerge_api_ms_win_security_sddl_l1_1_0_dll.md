# __tailMerge_api_ms_win_security_sddl_l1_1_0_dll

- ea: `0x180005e1c`
- end: `0x180005e95`
- name: `__tailMerge_api_ms_win_security_sddl_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180005e9b`

## callees

- `0x180005e1c`
- `0x180014d80`

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
0x180005e1c  mov     [rsp+arg_0], rcx
0x180005e21  mov     [rsp+arg_8], rdx
0x180005e26  mov     [rsp+arg_10], r8
0x180005e2b  mov     [rsp+arg_18], r9
0x180005e30  sub     rsp, 68h
0x180005e34  movdqa  [rsp+68h+var_48], xmm0
0x180005e3a  movdqa  [rsp+68h+var_38], xmm1
0x180005e40  movdqa  [rsp+68h+var_28], xmm2
0x180005e46  movdqa  [rsp+68h+var_18], xmm3
0x180005e4c  mov     rdx, rax
0x180005e4f  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_sddl_l1_1_0_dll
0x180005e56  call    __delayLoadHelper2
0x180005e5b  movdqa  xmm0, [rsp+68h+var_48]
0x180005e61  movdqa  xmm1, [rsp+68h+var_38]
0x180005e67  movdqa  xmm2, [rsp+68h+var_28]
0x180005e6d  movdqa  xmm3, [rsp+68h+var_18]
0x180005e73  mov     rcx, [rsp+68h+arg_0]
0x180005e78  mov     rdx, [rsp+68h+arg_8]
0x180005e7d  mov     r8, [rsp+68h+arg_10]
0x180005e85  mov     r9, [rsp+68h+arg_18]
0x180005e8d  add     rsp, 68h
0x180005e91  jmp     short $+2
0x180005e93  jmp     rax
```
