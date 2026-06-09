# __tailMerge_ext_ms_win_profile_userenv_l1_1_2_dll

- ea: `0x18000eaed`
- end: `0x18000eb66`
- name: `__tailMerge_ext_ms_win_profile_userenv_l1_1_2_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000eb6c`
- `0x18000eb90`
- `0x18000ebc6`
- `0x18000ec20`
- `0x18000ecb0`

## callees

- `0x180007910`
- `0x18000eaed`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_profile_userenv_l1_1_2_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_profile_userenv_l1_1_2_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000eaed  mov     [rsp+arg_0], rcx
0x18000eaf2  mov     [rsp+arg_8], rdx
0x18000eaf7  mov     [rsp+arg_10], r8
0x18000eafc  mov     [rsp+arg_18], r9
0x18000eb01  sub     rsp, 68h
0x18000eb05  movdqa  [rsp+68h+var_48], xmm0
0x18000eb0b  movdqa  [rsp+68h+var_38], xmm1
0x18000eb11  movdqa  [rsp+68h+var_28], xmm2
0x18000eb17  movdqa  [rsp+68h+var_18], xmm3
0x18000eb1d  mov     rdx, rax
0x18000eb20  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_profile_userenv_l1_1_2_dll
0x18000eb27  call    __delayLoadHelper2
0x18000eb2c  movdqa  xmm0, [rsp+68h+var_48]
0x18000eb32  movdqa  xmm1, [rsp+68h+var_38]
0x18000eb38  movdqa  xmm2, [rsp+68h+var_28]
0x18000eb3e  movdqa  xmm3, [rsp+68h+var_18]
0x18000eb44  mov     rcx, [rsp+68h+arg_0]
0x18000eb49  mov     rdx, [rsp+68h+arg_8]
0x18000eb4e  mov     r8, [rsp+68h+arg_10]
0x18000eb56  mov     r9, [rsp+68h+arg_18]
0x18000eb5e  add     rsp, 68h
0x18000eb62  jmp     short $+2
0x18000eb64  jmp     rax
```
