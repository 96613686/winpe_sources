# __tailMerge_ext_ms_win_rtcore_ntuser_sysparams_l1_1_0_dll

- ea: `0x18000dada`
- end: `0x18000db53`
- name: `__tailMerge_ext_ms_win_rtcore_ntuser_sysparams_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000db59`
- `0x18000db6b`

## callees

- `0x180009370`
- `0x18000dada`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_rtcore_ntuser_sysparams_l1_1_0_dll(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_rtcore_ntuser_sysparams_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000dada  mov     [rsp+arg_0], rcx
0x18000dadf  mov     [rsp+arg_8], rdx
0x18000dae4  mov     [rsp+arg_10], r8
0x18000dae9  mov     [rsp+arg_18], r9
0x18000daee  sub     rsp, 68h
0x18000daf2  movdqa  [rsp+68h+var_48], xmm0
0x18000daf8  movdqa  [rsp+68h+var_38], xmm1
0x18000dafe  movdqa  [rsp+68h+var_28], xmm2
0x18000db04  movdqa  [rsp+68h+var_18], xmm3
0x18000db0a  mov     rdx, rax
0x18000db0d  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_rtcore_ntuser_sysparams_l1_1_0_dll
0x18000db14  call    __delayLoadHelper2
0x18000db19  movdqa  xmm0, [rsp+68h+var_48]
0x18000db1f  movdqa  xmm1, [rsp+68h+var_38]
0x18000db25  movdqa  xmm2, [rsp+68h+var_28]
0x18000db2b  movdqa  xmm3, [rsp+68h+var_18]
0x18000db31  mov     rcx, [rsp+68h+arg_0]
0x18000db36  mov     rdx, [rsp+68h+arg_8]
0x18000db3b  mov     r8, [rsp+68h+arg_10]
0x18000db43  mov     r9, [rsp+68h+arg_18]
0x18000db4b  add     rsp, 68h
0x18000db4f  jmp     short $+2
0x18000db51  jmp     rax
```
