# __tailMerge_api_ms_win_security_sddl_l1_1_0_dll

- ea: `0x180001a50`
- end: `0x180001ac9`
- name: `__tailMerge_api_ms_win_security_sddl_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001acf`

## callees

- `0x180001a50`
- `0x18002ce10`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_security_sddl_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_sddl_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180001a50  mov     [rsp+arg_0], rcx
0x180001a55  mov     [rsp+arg_8], rdx
0x180001a5a  mov     [rsp+arg_10], r8
0x180001a5f  mov     [rsp+arg_18], r9
0x180001a64  sub     rsp, 68h
0x180001a68  movdqa  [rsp+68h+var_48], xmm0
0x180001a6e  movdqa  [rsp+68h+var_38], xmm1
0x180001a74  movdqa  [rsp+68h+var_28], xmm2
0x180001a7a  movdqa  [rsp+68h+var_18], xmm3
0x180001a80  mov     rdx, rax
0x180001a83  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_sddl_l1_1_0_dll
0x180001a8a  call    __delayLoadHelper2
0x180001a8f  movdqa  xmm0, [rsp+68h+var_48]
0x180001a95  movdqa  xmm1, [rsp+68h+var_38]
0x180001a9b  movdqa  xmm2, [rsp+68h+var_28]
0x180001aa1  movdqa  xmm3, [rsp+68h+var_18]
0x180001aa7  mov     rcx, [rsp+68h+arg_0]
0x180001aac  mov     rdx, [rsp+68h+arg_8]
0x180001ab1  mov     r8, [rsp+68h+arg_10]
0x180001ab9  mov     r9, [rsp+68h+arg_18]
0x180001ac1  add     rsp, 68h
0x180001ac5  jmp     short $+2
0x180001ac7  jmp     rax
```
