# __tailMerge_ext_ms_win_core_winsrv_min_l1_1_0_dll

- ea: `0x1800014da`
- end: `0x180001553`
- name: `__tailMerge_ext_ms_win_core_winsrv_min_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001559`

## callees

- `0x180001010`
- `0x1800014da`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_core_winsrv_min_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_core_winsrv_min_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800014da  mov     [rsp+arg_0], rcx
0x1800014df  mov     [rsp+arg_8], rdx
0x1800014e4  mov     [rsp+arg_10], r8
0x1800014e9  mov     [rsp+arg_18], r9
0x1800014ee  sub     rsp, 68h
0x1800014f2  movdqa  [rsp+68h+var_48], xmm0
0x1800014f8  movdqa  [rsp+68h+var_38], xmm1
0x1800014fe  movdqa  [rsp+68h+var_28], xmm2
0x180001504  movdqa  [rsp+68h+var_18], xmm3
0x18000150a  mov     rdx, rax
0x18000150d  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_core_winsrv_min_l1_1_0_dll
0x180001514  call    __delayLoadHelper2
0x180001519  movdqa  xmm0, [rsp+68h+var_48]
0x18000151f  movdqa  xmm1, [rsp+68h+var_38]
0x180001525  movdqa  xmm2, [rsp+68h+var_28]
0x18000152b  movdqa  xmm3, [rsp+68h+var_18]
0x180001531  mov     rcx, [rsp+68h+arg_0]
0x180001536  mov     rdx, [rsp+68h+arg_8]
0x18000153b  mov     r8, [rsp+68h+arg_10]
0x180001543  mov     r9, [rsp+68h+arg_18]
0x18000154b  add     rsp, 68h
0x18000154f  jmp     short $+2
0x180001551  jmp     rax
```
