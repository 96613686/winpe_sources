# __tailMerge_ext_ms_win_ntuser_gui_l1_1_0_dll

- ea: `0x180002440`
- end: `0x1800024b9`
- name: `__tailMerge_ext_ms_win_ntuser_gui_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800024bf`
- `0x1800024d1`

## callees

- `0x180002440`
- `0x180016ac0`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_ntuser_gui_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_gui_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002440  mov     [rsp+arg_0], rcx
0x180002445  mov     [rsp+arg_8], rdx
0x18000244a  mov     [rsp+arg_10], r8
0x18000244f  mov     [rsp+arg_18], r9
0x180002454  sub     rsp, 68h
0x180002458  movdqa  [rsp+68h+var_48], xmm0
0x18000245e  movdqa  [rsp+68h+var_38], xmm1
0x180002464  movdqa  [rsp+68h+var_28], xmm2
0x18000246a  movdqa  [rsp+68h+var_18], xmm3
0x180002470  mov     rdx, rax
0x180002473  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_gui_l1_1_0_dll
0x18000247a  call    __delayLoadHelper2
0x18000247f  movdqa  xmm0, [rsp+68h+var_48]
0x180002485  movdqa  xmm1, [rsp+68h+var_38]
0x18000248b  movdqa  xmm2, [rsp+68h+var_28]
0x180002491  movdqa  xmm3, [rsp+68h+var_18]
0x180002497  mov     rcx, [rsp+68h+arg_0]
0x18000249c  mov     rdx, [rsp+68h+arg_8]
0x1800024a1  mov     r8, [rsp+68h+arg_10]
0x1800024a9  mov     r9, [rsp+68h+arg_18]
0x1800024b1  add     rsp, 68h
0x1800024b5  jmp     short $+2
0x1800024b7  jmp     rax
```
