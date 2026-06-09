# __tailMerge_api_ms_win_security_lsalookup_l1_1_0_dll

- ea: `0x18000d4e8`
- end: `0x18000d561`
- name: `__tailMerge_api_ms_win_security_lsalookup_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000d567`

## callees

- `0x180008bd0`
- `0x18000d4e8`

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
0x18000d4e8  mov     [rsp+arg_0], rcx
0x18000d4ed  mov     [rsp+arg_8], rdx
0x18000d4f2  mov     [rsp+arg_10], r8
0x18000d4f7  mov     [rsp+arg_18], r9
0x18000d4fc  sub     rsp, 68h
0x18000d500  movdqa  [rsp+68h+var_48], xmm0
0x18000d506  movdqa  [rsp+68h+var_38], xmm1
0x18000d50c  movdqa  [rsp+68h+var_28], xmm2
0x18000d512  movdqa  [rsp+68h+var_18], xmm3
0x18000d518  mov     rdx, rax
0x18000d51b  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_lsalookup_l1_1_0_dll
0x18000d522  call    __delayLoadHelper2
0x18000d527  movdqa  xmm0, [rsp+68h+var_48]
0x18000d52d  movdqa  xmm1, [rsp+68h+var_38]
0x18000d533  movdqa  xmm2, [rsp+68h+var_28]
0x18000d539  movdqa  xmm3, [rsp+68h+var_18]
0x18000d53f  mov     rcx, [rsp+68h+arg_0]
0x18000d544  mov     rdx, [rsp+68h+arg_8]
0x18000d549  mov     r8, [rsp+68h+arg_10]
0x18000d551  mov     r9, [rsp+68h+arg_18]
0x18000d559  add     rsp, 68h
0x18000d55d  jmp     short $+2
0x18000d55f  jmp     rax
```
