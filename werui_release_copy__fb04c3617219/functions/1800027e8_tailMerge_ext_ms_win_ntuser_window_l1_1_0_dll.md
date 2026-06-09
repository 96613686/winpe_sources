# __tailMerge_ext_ms_win_ntuser_window_l1_1_0_dll

- ea: `0x1800027e8`
- end: `0x180002861`
- name: `__tailMerge_ext_ms_win_ntuser_window_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `13`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002867`
- `0x180002879`
- `0x18000288b`
- `0x18000289d`
- `0x1800028af`
- `0x18000294c`
- `0x18000295e`
- `0x180002982`
- `0x180002994`
- `0x1800029a6`
- `0x1800029b8`
- `0x180002abc`
- `0x180002ace`

## callees

- `0x1800027e8`
- `0x180016ac0`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_ntuser_window_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_window_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800027e8  mov     [rsp+arg_0], rcx
0x1800027ed  mov     [rsp+arg_8], rdx
0x1800027f2  mov     [rsp+arg_10], r8
0x1800027f7  mov     [rsp+arg_18], r9
0x1800027fc  sub     rsp, 68h
0x180002800  movdqa  [rsp+68h+var_48], xmm0
0x180002806  movdqa  [rsp+68h+var_38], xmm1
0x18000280c  movdqa  [rsp+68h+var_28], xmm2
0x180002812  movdqa  [rsp+68h+var_18], xmm3
0x180002818  mov     rdx, rax
0x18000281b  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_window_l1_1_0_dll
0x180002822  call    __delayLoadHelper2
0x180002827  movdqa  xmm0, [rsp+68h+var_48]
0x18000282d  movdqa  xmm1, [rsp+68h+var_38]
0x180002833  movdqa  xmm2, [rsp+68h+var_28]
0x180002839  movdqa  xmm3, [rsp+68h+var_18]
0x18000283f  mov     rcx, [rsp+68h+arg_0]
0x180002844  mov     rdx, [rsp+68h+arg_8]
0x180002849  mov     r8, [rsp+68h+arg_10]
0x180002851  mov     r9, [rsp+68h+arg_18]
0x180002859  add     rsp, 68h
0x18000285d  jmp     short $+2
0x18000285f  jmp     rax
```
