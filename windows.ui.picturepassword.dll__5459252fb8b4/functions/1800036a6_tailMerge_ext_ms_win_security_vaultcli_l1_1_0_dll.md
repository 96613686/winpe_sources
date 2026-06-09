# __tailMerge_ext_ms_win_security_vaultcli_l1_1_0_dll

- ea: `0x1800036a6`
- end: `0x18000371f`
- name: `__tailMerge_ext_ms_win_security_vaultcli_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003725`
- `0x180003737`
- `0x180003749`
- `0x18000375b`
- `0x18000376d`
- `0x18000377f`
- `0x180003791`
- `0x1800037a3`

## callees

- `0x1800036a6`
- `0x18001a930`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_security_vaultcli_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_security_vaultcli_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800036a6  mov     [rsp+arg_0], rcx
0x1800036ab  mov     [rsp+arg_8], rdx
0x1800036b0  mov     [rsp+arg_10], r8
0x1800036b5  mov     [rsp+arg_18], r9
0x1800036ba  sub     rsp, 68h
0x1800036be  movdqa  [rsp+68h+var_48], xmm0
0x1800036c4  movdqa  [rsp+68h+var_38], xmm1
0x1800036ca  movdqa  [rsp+68h+var_28], xmm2
0x1800036d0  movdqa  [rsp+68h+var_18], xmm3
0x1800036d6  mov     rdx, rax
0x1800036d9  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_security_vaultcli_l1_1_0_dll
0x1800036e0  call    __delayLoadHelper2
0x1800036e5  movdqa  xmm0, [rsp+68h+var_48]
0x1800036eb  movdqa  xmm1, [rsp+68h+var_38]
0x1800036f1  movdqa  xmm2, [rsp+68h+var_28]
0x1800036f7  movdqa  xmm3, [rsp+68h+var_18]
0x1800036fd  mov     rcx, [rsp+68h+arg_0]
0x180003702  mov     rdx, [rsp+68h+arg_8]
0x180003707  mov     r8, [rsp+68h+arg_10]
0x18000370f  mov     r9, [rsp+68h+arg_18]
0x180003717  add     rsp, 68h
0x18000371b  jmp     short $+2
0x18000371d  jmp     rax
```
