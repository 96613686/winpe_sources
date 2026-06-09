# __tailMerge_api_ms_win_core_com_l1_1_0_dll

- ea: `0x140005764`
- end: `0x1400057dd`
- name: `__tailMerge_api_ms_win_core_com_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400057e3`
- `0x1400058a4`
- `0x1400058b6`
- `0x1400058c8`
- `0x1400058da`

## callees

- `0x140001ff0`
- `0x140005764`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_core_com_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_com_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x140005764  mov     [rsp+arg_0], rcx
0x140005769  mov     [rsp+arg_8], rdx
0x14000576e  mov     [rsp+arg_10], r8
0x140005773  mov     [rsp+arg_18], r9
0x140005778  sub     rsp, 68h
0x14000577c  movdqa  [rsp+68h+var_48], xmm0
0x140005782  movdqa  [rsp+68h+var_38], xmm1
0x140005788  movdqa  [rsp+68h+var_28], xmm2
0x14000578e  movdqa  [rsp+68h+var_18], xmm3
0x140005794  mov     rdx, rax
0x140005797  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_com_l1_1_0_dll
0x14000579e  call    __delayLoadHelper2
0x1400057a3  movdqa  xmm0, [rsp+68h+var_48]
0x1400057a9  movdqa  xmm1, [rsp+68h+var_38]
0x1400057af  movdqa  xmm2, [rsp+68h+var_28]
0x1400057b5  movdqa  xmm3, [rsp+68h+var_18]
0x1400057bb  mov     rcx, [rsp+68h+arg_0]
0x1400057c0  mov     rdx, [rsp+68h+arg_8]
0x1400057c5  mov     r8, [rsp+68h+arg_10]
0x1400057cd  mov     r9, [rsp+68h+arg_18]
0x1400057d5  add     rsp, 68h
0x1400057d9  jmp     short $+2
0x1400057db  jmp     rax
```
