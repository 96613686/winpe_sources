# __tailMerge_api_ms_win_security_provider_l1_1_0_dll

- ea: `0x180007eab`
- end: `0x180007f24`
- name: `__tailMerge_api_ms_win_security_provider_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180007f2a`
- `0x180007f3c`

## callees

- `0x1800063c0`
- `0x180007eab`

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
0x180007eab  mov     [rsp+arg_0], rcx
0x180007eb0  mov     [rsp+arg_8], rdx
0x180007eb5  mov     [rsp+arg_10], r8
0x180007eba  mov     [rsp+arg_18], r9
0x180007ebf  sub     rsp, 68h
0x180007ec3  movdqa  [rsp+68h+var_48], xmm0
0x180007ec9  movdqa  [rsp+68h+var_38], xmm1
0x180007ecf  movdqa  [rsp+68h+var_28], xmm2
0x180007ed5  movdqa  [rsp+68h+var_18], xmm3
0x180007edb  mov     rdx, rax
0x180007ede  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_provider_l1_1_0_dll
0x180007ee5  call    __delayLoadHelper2
0x180007eea  movdqa  xmm0, [rsp+68h+var_48]
0x180007ef0  movdqa  xmm1, [rsp+68h+var_38]
0x180007ef6  movdqa  xmm2, [rsp+68h+var_28]
0x180007efc  movdqa  xmm3, [rsp+68h+var_18]
0x180007f02  mov     rcx, [rsp+68h+arg_0]
0x180007f07  mov     rdx, [rsp+68h+arg_8]
0x180007f0c  mov     r8, [rsp+68h+arg_10]
0x180007f14  mov     r9, [rsp+68h+arg_18]
0x180007f1c  add     rsp, 68h
0x180007f20  jmp     short $+2
0x180007f22  jmp     rax
```
