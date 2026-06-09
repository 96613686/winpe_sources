# __tailMerge_api_ms_win_mm_misc_l2_1_0_dll

- ea: `0x18001154f`
- end: `0x1800115c8`
- name: `__tailMerge_api_ms_win_mm_misc_l2_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800115ce`
- `0x1800115e0`

## callees

- `0x18000f240`
- `0x18001154f`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_mm_misc_l2_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_mm_misc_l2_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18001154f  mov     [rsp+arg_0], rcx
0x180011554  mov     [rsp+arg_8], rdx
0x180011559  mov     [rsp+arg_10], r8
0x18001155e  mov     [rsp+arg_18], r9
0x180011563  sub     rsp, 68h
0x180011567  movdqa  [rsp+68h+var_48], xmm0
0x18001156d  movdqa  [rsp+68h+var_38], xmm1
0x180011573  movdqa  [rsp+68h+var_28], xmm2
0x180011579  movdqa  [rsp+68h+var_18], xmm3
0x18001157f  mov     rdx, rax
0x180011582  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_mm_misc_l2_1_0_dll
0x180011589  call    __delayLoadHelper2
0x18001158e  movdqa  xmm0, [rsp+68h+var_48]
0x180011594  movdqa  xmm1, [rsp+68h+var_38]
0x18001159a  movdqa  xmm2, [rsp+68h+var_28]
0x1800115a0  movdqa  xmm3, [rsp+68h+var_18]
0x1800115a6  mov     rcx, [rsp+68h+arg_0]
0x1800115ab  mov     rdx, [rsp+68h+arg_8]
0x1800115b0  mov     r8, [rsp+68h+arg_10]
0x1800115b8  mov     r9, [rsp+68h+arg_18]
0x1800115c0  add     rsp, 68h
0x1800115c4  jmp     short $+2
0x1800115c6  jmp     rax
```
