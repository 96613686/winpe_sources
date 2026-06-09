# __tailMerge_ext_ms_win_security_slc_l1_1_0_dll

- ea: `0x180010b61`
- end: `0x180010bda`
- name: `__tailMerge_ext_ms_win_security_slc_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180010be0`

## callees

- `0x180010b61`
- `0x180018770`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_security_slc_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_security_slc_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180010b61  mov     [rsp+arg_0], rcx
0x180010b66  mov     [rsp+arg_8], rdx
0x180010b6b  mov     [rsp+arg_10], r8
0x180010b70  mov     [rsp+arg_18], r9
0x180010b75  sub     rsp, 68h
0x180010b79  movdqa  [rsp+68h+var_48], xmm0
0x180010b7f  movdqa  [rsp+68h+var_38], xmm1
0x180010b85  movdqa  [rsp+68h+var_28], xmm2
0x180010b8b  movdqa  [rsp+68h+var_18], xmm3
0x180010b91  mov     rdx, rax
0x180010b94  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_security_slc_l1_1_0_dll
0x180010b9b  call    __delayLoadHelper2
0x180010ba0  movdqa  xmm0, [rsp+68h+var_48]
0x180010ba6  movdqa  xmm1, [rsp+68h+var_38]
0x180010bac  movdqa  xmm2, [rsp+68h+var_28]
0x180010bb2  movdqa  xmm3, [rsp+68h+var_18]
0x180010bb8  mov     rcx, [rsp+68h+arg_0]
0x180010bbd  mov     rdx, [rsp+68h+arg_8]
0x180010bc2  mov     r8, [rsp+68h+arg_10]
0x180010bca  mov     r9, [rsp+68h+arg_18]
0x180010bd2  add     rsp, 68h
0x180010bd6  jmp     short $+2
0x180010bd8  jmp     rax
```
