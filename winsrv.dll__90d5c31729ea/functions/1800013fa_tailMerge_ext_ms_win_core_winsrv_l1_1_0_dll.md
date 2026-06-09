# __tailMerge_ext_ms_win_core_winsrv_l1_1_0_dll

- ea: `0x1800013fa`
- end: `0x180001473`
- name: `__tailMerge_ext_ms_win_core_winsrv_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001479`

## callees

- `0x180001010`
- `0x1800013fa`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_core_winsrv_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_core_winsrv_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800013fa  mov     [rsp+arg_0], rcx
0x1800013ff  mov     [rsp+arg_8], rdx
0x180001404  mov     [rsp+arg_10], r8
0x180001409  mov     [rsp+arg_18], r9
0x18000140e  sub     rsp, 68h
0x180001412  movdqa  [rsp+68h+var_48], xmm0
0x180001418  movdqa  [rsp+68h+var_38], xmm1
0x18000141e  movdqa  [rsp+68h+var_28], xmm2
0x180001424  movdqa  [rsp+68h+var_18], xmm3
0x18000142a  mov     rdx, rax
0x18000142d  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_core_winsrv_l1_1_0_dll
0x180001434  call    __delayLoadHelper2
0x180001439  movdqa  xmm0, [rsp+68h+var_48]
0x18000143f  movdqa  xmm1, [rsp+68h+var_38]
0x180001445  movdqa  xmm2, [rsp+68h+var_28]
0x18000144b  movdqa  xmm3, [rsp+68h+var_18]
0x180001451  mov     rcx, [rsp+68h+arg_0]
0x180001456  mov     rdx, [rsp+68h+arg_8]
0x18000145b  mov     r8, [rsp+68h+arg_10]
0x180001463  mov     r9, [rsp+68h+arg_18]
0x18000146b  add     rsp, 68h
0x18000146f  jmp     short $+2
0x180001471  jmp     rax
```
