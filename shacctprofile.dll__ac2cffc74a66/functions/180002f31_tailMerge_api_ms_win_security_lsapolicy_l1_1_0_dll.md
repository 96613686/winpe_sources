# __tailMerge_api_ms_win_security_lsapolicy_l1_1_0_dll

- ea: `0x180002f31`
- end: `0x180002faa`
- name: `__tailMerge_api_ms_win_security_lsapolicy_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180002fb0`
- `0x180002fc2`
- `0x180002fd4`
- `0x180002fe6`
- `0x1800030b9`

## callees

- `0x180002f31`
- `0x1800095f0`

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
0x180002f31  mov     [rsp+arg_0], rcx
0x180002f36  mov     [rsp+arg_8], rdx
0x180002f3b  mov     [rsp+arg_10], r8
0x180002f40  mov     [rsp+arg_18], r9
0x180002f45  sub     rsp, 68h
0x180002f49  movdqa  [rsp+68h+var_48], xmm0
0x180002f4f  movdqa  [rsp+68h+var_38], xmm1
0x180002f55  movdqa  [rsp+68h+var_28], xmm2
0x180002f5b  movdqa  [rsp+68h+var_18], xmm3
0x180002f61  mov     rdx, rax
0x180002f64  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_lsapolicy_l1_1_0_dll
0x180002f6b  call    __delayLoadHelper2
0x180002f70  movdqa  xmm0, [rsp+68h+var_48]
0x180002f76  movdqa  xmm1, [rsp+68h+var_38]
0x180002f7c  movdqa  xmm2, [rsp+68h+var_28]
0x180002f82  movdqa  xmm3, [rsp+68h+var_18]
0x180002f88  mov     rcx, [rsp+68h+arg_0]
0x180002f8d  mov     rdx, [rsp+68h+arg_8]
0x180002f92  mov     r8, [rsp+68h+arg_10]
0x180002f9a  mov     r9, [rsp+68h+arg_18]
0x180002fa2  add     rsp, 68h
0x180002fa6  jmp     short $+2
0x180002fa8  jmp     rax
```
