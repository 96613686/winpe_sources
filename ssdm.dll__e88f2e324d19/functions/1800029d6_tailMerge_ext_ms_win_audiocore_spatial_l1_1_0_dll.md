# __tailMerge_ext_ms_win_audiocore_spatial_l1_1_0_dll

- ea: `0x1800029d6`
- end: `0x180002a4f`
- name: `__tailMerge_ext_ms_win_audiocore_spatial_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002a55`
- `0x180002a67`

## callees

- `0x1800029d6`
- `0x18000e820`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_audiocore_spatial_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_audiocore_spatial_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800029d6  mov     [rsp+arg_0], rcx
0x1800029db  mov     [rsp+arg_8], rdx
0x1800029e0  mov     [rsp+arg_10], r8
0x1800029e5  mov     [rsp+arg_18], r9
0x1800029ea  sub     rsp, 68h
0x1800029ee  movdqa  [rsp+68h+var_48], xmm0
0x1800029f4  movdqa  [rsp+68h+var_38], xmm1
0x1800029fa  movdqa  [rsp+68h+var_28], xmm2
0x180002a00  movdqa  [rsp+68h+var_18], xmm3
0x180002a06  mov     rdx, rax
0x180002a09  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_audiocore_spatial_l1_1_0_dll
0x180002a10  call    __delayLoadHelper2
0x180002a15  movdqa  xmm0, [rsp+68h+var_48]
0x180002a1b  movdqa  xmm1, [rsp+68h+var_38]
0x180002a21  movdqa  xmm2, [rsp+68h+var_28]
0x180002a27  movdqa  xmm3, [rsp+68h+var_18]
0x180002a2d  mov     rcx, [rsp+68h+arg_0]
0x180002a32  mov     rdx, [rsp+68h+arg_8]
0x180002a37  mov     r8, [rsp+68h+arg_10]
0x180002a3f  mov     r9, [rsp+68h+arg_18]
0x180002a47  add     rsp, 68h
0x180002a4b  jmp     short $+2
0x180002a4d  jmp     rax
```
