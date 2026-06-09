# __tailMerge_api_ms_win_security_lsalookup_l1_1_0_dll

- ea: `0x180001b92`
- end: `0x180001c0b`
- name: `__tailMerge_api_ms_win_security_lsalookup_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001c11`

## callees

- `0x180001b92`
- `0x180012d30`

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
0x180001b92  mov     [rsp+arg_0], rcx
0x180001b97  mov     [rsp+arg_8], rdx
0x180001b9c  mov     [rsp+arg_10], r8
0x180001ba1  mov     [rsp+arg_18], r9
0x180001ba6  sub     rsp, 68h
0x180001baa  movdqa  [rsp+68h+var_48], xmm0
0x180001bb0  movdqa  [rsp+68h+var_38], xmm1
0x180001bb6  movdqa  [rsp+68h+var_28], xmm2
0x180001bbc  movdqa  [rsp+68h+var_18], xmm3
0x180001bc2  mov     rdx, rax
0x180001bc5  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_lsalookup_l1_1_0_dll
0x180001bcc  call    __delayLoadHelper2
0x180001bd1  movdqa  xmm0, [rsp+68h+var_48]
0x180001bd7  movdqa  xmm1, [rsp+68h+var_38]
0x180001bdd  movdqa  xmm2, [rsp+68h+var_28]
0x180001be3  movdqa  xmm3, [rsp+68h+var_18]
0x180001be9  mov     rcx, [rsp+68h+arg_0]
0x180001bee  mov     rdx, [rsp+68h+arg_8]
0x180001bf3  mov     r8, [rsp+68h+arg_10]
0x180001bfb  mov     r9, [rsp+68h+arg_18]
0x180001c03  add     rsp, 68h
0x180001c07  jmp     short $+2
0x180001c09  jmp     rax
```
