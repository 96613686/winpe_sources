# __tailMerge_ext_ms_win_cng_rng_l1_1_1_dll

- ea: `0x180006120`
- end: `0x180006199`
- name: `__tailMerge_ext_ms_win_cng_rng_l1_1_1_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000619f`

## callees

- `0x180006120`
- `0x18000b940`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_cng_rng_l1_1_1_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_cng_rng_l1_1_1_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180006120  mov     [rsp+arg_0], rcx
0x180006125  mov     [rsp+arg_8], rdx
0x18000612a  mov     [rsp+arg_10], r8
0x18000612f  mov     [rsp+arg_18], r9
0x180006134  sub     rsp, 68h
0x180006138  movdqa  [rsp+68h+var_48], xmm0
0x18000613e  movdqa  [rsp+68h+var_38], xmm1
0x180006144  movdqa  [rsp+68h+var_28], xmm2
0x18000614a  movdqa  [rsp+68h+var_18], xmm3
0x180006150  mov     rdx, rax
0x180006153  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_cng_rng_l1_1_1_dll
0x18000615a  call    __delayLoadHelper2
0x18000615f  movdqa  xmm0, [rsp+68h+var_48]
0x180006165  movdqa  xmm1, [rsp+68h+var_38]
0x18000616b  movdqa  xmm2, [rsp+68h+var_28]
0x180006171  movdqa  xmm3, [rsp+68h+var_18]
0x180006177  mov     rcx, [rsp+68h+arg_0]
0x18000617c  mov     rdx, [rsp+68h+arg_8]
0x180006181  mov     r8, [rsp+68h+arg_10]
0x180006189  mov     r9, [rsp+68h+arg_18]
0x180006191  add     rsp, 68h
0x180006195  jmp     short $+2
0x180006197  jmp     rax
```
