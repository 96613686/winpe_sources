# __tailMerge_ext_ms_win_devmgmt_policy_l1_1_0_dll

- ea: `0x1800034ff`
- end: `0x180003578`
- name: `__tailMerge_ext_ms_win_devmgmt_policy_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18000357e`

## callees

- `0x1800034ff`
- `0x18000fec0`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_devmgmt_policy_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_devmgmt_policy_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800034ff  mov     [rsp+arg_0], rcx
0x180003504  mov     [rsp+arg_8], rdx
0x180003509  mov     [rsp+arg_10], r8
0x18000350e  mov     [rsp+arg_18], r9
0x180003513  sub     rsp, 68h
0x180003517  movdqa  [rsp+68h+var_48], xmm0
0x18000351d  movdqa  [rsp+68h+var_38], xmm1
0x180003523  movdqa  [rsp+68h+var_28], xmm2
0x180003529  movdqa  [rsp+68h+var_18], xmm3
0x18000352f  mov     rdx, rax
0x180003532  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_devmgmt_policy_l1_1_0_dll
0x180003539  call    __delayLoadHelper2
0x18000353e  movdqa  xmm0, [rsp+68h+var_48]
0x180003544  movdqa  xmm1, [rsp+68h+var_38]
0x18000354a  movdqa  xmm2, [rsp+68h+var_28]
0x180003550  movdqa  xmm3, [rsp+68h+var_18]
0x180003556  mov     rcx, [rsp+68h+arg_0]
0x18000355b  mov     rdx, [rsp+68h+arg_8]
0x180003560  mov     r8, [rsp+68h+arg_10]
0x180003568  mov     r9, [rsp+68h+arg_18]
0x180003570  add     rsp, 68h
0x180003574  jmp     short $+2
0x180003576  jmp     rax
```
