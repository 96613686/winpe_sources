# __tailMerge_ext_ms_win_rtcore_ntuser_cursor_l1_1_0_dll

- ea: `0x1400027e9`
- end: `0x140002862`
- name: `__tailMerge_ext_ms_win_rtcore_ntuser_cursor_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140002868`

## callees

- `0x1400027e9`
- `0x14000b0a0`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_rtcore_ntuser_cursor_l1_1_0_dll(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_rtcore_ntuser_cursor_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1400027e9  mov     [rsp+arg_0], rcx
0x1400027ee  mov     [rsp+arg_8], rdx
0x1400027f3  mov     [rsp+arg_10], r8
0x1400027f8  mov     [rsp+arg_18], r9
0x1400027fd  sub     rsp, 68h
0x140002801  movdqa  [rsp+68h+var_48], xmm0
0x140002807  movdqa  [rsp+68h+var_38], xmm1
0x14000280d  movdqa  [rsp+68h+var_28], xmm2
0x140002813  movdqa  [rsp+68h+var_18], xmm3
0x140002819  mov     rdx, rax
0x14000281c  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_rtcore_ntuser_cursor_l1_1_0_dll
0x140002823  call    __delayLoadHelper2
0x140002828  movdqa  xmm0, [rsp+68h+var_48]
0x14000282e  movdqa  xmm1, [rsp+68h+var_38]
0x140002834  movdqa  xmm2, [rsp+68h+var_28]
0x14000283a  movdqa  xmm3, [rsp+68h+var_18]
0x140002840  mov     rcx, [rsp+68h+arg_0]
0x140002845  mov     rdx, [rsp+68h+arg_8]
0x14000284a  mov     r8, [rsp+68h+arg_10]
0x140002852  mov     r9, [rsp+68h+arg_18]
0x14000285a  add     rsp, 68h
0x14000285e  jmp     short $+2
0x140002860  jmp     rax
```
