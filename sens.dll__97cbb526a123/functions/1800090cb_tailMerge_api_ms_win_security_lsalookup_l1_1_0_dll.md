# __tailMerge_api_ms_win_security_lsalookup_l1_1_0_dll

- ea: `0x1800090cb`
- end: `0x180009144`
- name: `__tailMerge_api_ms_win_security_lsalookup_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000914a`

## callees

- `0x180006a50`
- `0x1800090cb`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_security_lsalookup_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_lsalookup_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800090cb  mov     [rsp+arg_0], rcx
0x1800090d0  mov     [rsp+arg_8], rdx
0x1800090d5  mov     [rsp+arg_10], r8
0x1800090da  mov     [rsp+arg_18], r9
0x1800090df  sub     rsp, 68h
0x1800090e3  movdqa  [rsp+68h+var_48], xmm0
0x1800090e9  movdqa  [rsp+68h+var_38], xmm1
0x1800090ef  movdqa  [rsp+68h+var_28], xmm2
0x1800090f5  movdqa  [rsp+68h+var_18], xmm3
0x1800090fb  mov     rdx, rax
0x1800090fe  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_lsalookup_l1_1_0_dll
0x180009105  call    __delayLoadHelper2
0x18000910a  movdqa  xmm0, [rsp+68h+var_48]
0x180009110  movdqa  xmm1, [rsp+68h+var_38]
0x180009116  movdqa  xmm2, [rsp+68h+var_28]
0x18000911c  movdqa  xmm3, [rsp+68h+var_18]
0x180009122  mov     rcx, [rsp+68h+arg_0]
0x180009127  mov     rdx, [rsp+68h+arg_8]
0x18000912c  mov     r8, [rsp+68h+arg_10]
0x180009134  mov     r9, [rsp+68h+arg_18]
0x18000913c  add     rsp, 68h
0x180009140  jmp     short $+2
0x180009142  jmp     rax
```
