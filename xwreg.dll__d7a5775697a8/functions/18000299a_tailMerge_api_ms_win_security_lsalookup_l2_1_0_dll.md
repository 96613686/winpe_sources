# __tailMerge_api_ms_win_security_lsalookup_l2_1_0_dll

- ea: `0x18000299a`
- end: `0x180002a13`
- name: `__tailMerge_api_ms_win_security_lsalookup_l2_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002a19`

## callees

- `0x18000299a`
- `0x18000da70`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_security_lsalookup_l2_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_lsalookup_l2_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000299a  mov     [rsp+arg_0], rcx
0x18000299f  mov     [rsp+arg_8], rdx
0x1800029a4  mov     [rsp+arg_10], r8
0x1800029a9  mov     [rsp+arg_18], r9
0x1800029ae  sub     rsp, 68h
0x1800029b2  movdqa  [rsp+68h+var_48], xmm0
0x1800029b8  movdqa  [rsp+68h+var_38], xmm1
0x1800029be  movdqa  [rsp+68h+var_28], xmm2
0x1800029c4  movdqa  [rsp+68h+var_18], xmm3
0x1800029ca  mov     rdx, rax
0x1800029cd  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_lsalookup_l2_1_0_dll
0x1800029d4  call    __delayLoadHelper2
0x1800029d9  movdqa  xmm0, [rsp+68h+var_48]
0x1800029df  movdqa  xmm1, [rsp+68h+var_38]
0x1800029e5  movdqa  xmm2, [rsp+68h+var_28]
0x1800029eb  movdqa  xmm3, [rsp+68h+var_18]
0x1800029f1  mov     rcx, [rsp+68h+arg_0]
0x1800029f6  mov     rdx, [rsp+68h+arg_8]
0x1800029fb  mov     r8, [rsp+68h+arg_10]
0x180002a03  mov     r9, [rsp+68h+arg_18]
0x180002a0b  add     rsp, 68h
0x180002a0f  jmp     short $+2
0x180002a11  jmp     rax
```
