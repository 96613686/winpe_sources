# __tailMerge_ext_ms_win_profile_userenv_l1_1_0_dll

- ea: `0x18000ea62`
- end: `0x18000eadb`
- name: `__tailMerge_ext_ms_win_profile_userenv_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `20`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000eae1`
- `0x18000eb7e`
- `0x18000eba2`
- `0x18000ebb4`
- `0x18000ebd8`
- `0x18000ebea`
- `0x18000ebfc`
- `0x18000ec0e`
- `0x18000ec32`
- `0x18000ec44`
- `0x18000ec56`
- `0x18000ec68`
- `0x18000ec7a`
- `0x18000ec8c`
- `0x18000ec9e`
- `0x18000ecc2`
- `0x18000ecd4`
- `0x18000ed71`
- `0x18000ed83`
- `0x18000ed95`

## callees

- `0x180007910`
- `0x18000ea62`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_profile_userenv_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_profile_userenv_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000ea62  mov     [rsp+arg_0], rcx
0x18000ea67  mov     [rsp+arg_8], rdx
0x18000ea6c  mov     [rsp+arg_10], r8
0x18000ea71  mov     [rsp+arg_18], r9
0x18000ea76  sub     rsp, 68h
0x18000ea7a  movdqa  [rsp+68h+var_48], xmm0
0x18000ea80  movdqa  [rsp+68h+var_38], xmm1
0x18000ea86  movdqa  [rsp+68h+var_28], xmm2
0x18000ea8c  movdqa  [rsp+68h+var_18], xmm3
0x18000ea92  mov     rdx, rax
0x18000ea95  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_profile_userenv_l1_1_0_dll
0x18000ea9c  call    __delayLoadHelper2
0x18000eaa1  movdqa  xmm0, [rsp+68h+var_48]
0x18000eaa7  movdqa  xmm1, [rsp+68h+var_38]
0x18000eaad  movdqa  xmm2, [rsp+68h+var_28]
0x18000eab3  movdqa  xmm3, [rsp+68h+var_18]
0x18000eab9  mov     rcx, [rsp+68h+arg_0]
0x18000eabe  mov     rdx, [rsp+68h+arg_8]
0x18000eac3  mov     r8, [rsp+68h+arg_10]
0x18000eacb  mov     r9, [rsp+68h+arg_18]
0x18000ead3  add     rsp, 68h
0x18000ead7  jmp     short $+2
0x18000ead9  jmp     rax
```
