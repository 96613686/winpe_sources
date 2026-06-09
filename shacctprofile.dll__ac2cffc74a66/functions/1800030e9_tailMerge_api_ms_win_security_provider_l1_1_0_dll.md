# __tailMerge_api_ms_win_security_provider_l1_1_0_dll

- ea: `0x1800030e9`
- end: `0x180003162`
- name: `__tailMerge_api_ms_win_security_provider_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003168`
- `0x18000317a`

## callees

- `0x1800030e9`
- `0x1800095f0`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_security_provider_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_provider_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800030e9  mov     [rsp+arg_0], rcx
0x1800030ee  mov     [rsp+arg_8], rdx
0x1800030f3  mov     [rsp+arg_10], r8
0x1800030f8  mov     [rsp+arg_18], r9
0x1800030fd  sub     rsp, 68h
0x180003101  movdqa  [rsp+68h+var_48], xmm0
0x180003107  movdqa  [rsp+68h+var_38], xmm1
0x18000310d  movdqa  [rsp+68h+var_28], xmm2
0x180003113  movdqa  [rsp+68h+var_18], xmm3
0x180003119  mov     rdx, rax
0x18000311c  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_provider_l1_1_0_dll
0x180003123  call    __delayLoadHelper2
0x180003128  movdqa  xmm0, [rsp+68h+var_48]
0x18000312e  movdqa  xmm1, [rsp+68h+var_38]
0x180003134  movdqa  xmm2, [rsp+68h+var_28]
0x18000313a  movdqa  xmm3, [rsp+68h+var_18]
0x180003140  mov     rcx, [rsp+68h+arg_0]
0x180003145  mov     rdx, [rsp+68h+arg_8]
0x18000314a  mov     r8, [rsp+68h+arg_10]
0x180003152  mov     r9, [rsp+68h+arg_18]
0x18000315a  add     rsp, 68h
0x18000315e  jmp     short $+2
0x180003160  jmp     rax
```
