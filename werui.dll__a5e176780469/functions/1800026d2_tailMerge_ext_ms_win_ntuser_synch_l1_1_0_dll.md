# __tailMerge_ext_ms_win_ntuser_synch_l1_1_0_dll

- ea: `0x1800026d2`
- end: `0x18000274b`
- name: `__tailMerge_ext_ms_win_ntuser_synch_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002751`

## callees

- `0x1800026d2`
- `0x180016ac0`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_ntuser_synch_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_synch_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800026d2  mov     [rsp+arg_0], rcx
0x1800026d7  mov     [rsp+arg_8], rdx
0x1800026dc  mov     [rsp+arg_10], r8
0x1800026e1  mov     [rsp+arg_18], r9
0x1800026e6  sub     rsp, 68h
0x1800026ea  movdqa  [rsp+68h+var_48], xmm0
0x1800026f0  movdqa  [rsp+68h+var_38], xmm1
0x1800026f6  movdqa  [rsp+68h+var_28], xmm2
0x1800026fc  movdqa  [rsp+68h+var_18], xmm3
0x180002702  mov     rdx, rax
0x180002705  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_synch_l1_1_0_dll
0x18000270c  call    __delayLoadHelper2
0x180002711  movdqa  xmm0, [rsp+68h+var_48]
0x180002717  movdqa  xmm1, [rsp+68h+var_38]
0x18000271d  movdqa  xmm2, [rsp+68h+var_28]
0x180002723  movdqa  xmm3, [rsp+68h+var_18]
0x180002729  mov     rcx, [rsp+68h+arg_0]
0x18000272e  mov     rdx, [rsp+68h+arg_8]
0x180002733  mov     r8, [rsp+68h+arg_10]
0x18000273b  mov     r9, [rsp+68h+arg_18]
0x180002743  add     rsp, 68h
0x180002747  jmp     short $+2
0x180002749  jmp     rax
```
