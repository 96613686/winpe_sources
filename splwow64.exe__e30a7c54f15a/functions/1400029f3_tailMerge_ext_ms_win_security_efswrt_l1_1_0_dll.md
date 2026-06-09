# __tailMerge_ext_ms_win_security_efswrt_l1_1_0_dll

- ea: `0x1400029f3`
- end: `0x140002a6c`
- name: `__tailMerge_ext_ms_win_security_efswrt_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140002a72`
- `0x140002a84`
- `0x140002a96`

## callees

- `0x1400029f3`
- `0x140014f70`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_security_efswrt_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  FARPROC *v4; // rax
  FARPROC Helper2; // rax

  Helper2 = _delayLoadHelper2(
              (const ImgDelayDescr *)&_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_security_efswrt_l1_1_0_dll,
              v4);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64))Helper2)(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1400029f3  mov     [rsp+arg_0], rcx
0x1400029f8  mov     [rsp+arg_8], rdx
0x1400029fd  mov     [rsp+arg_10], r8
0x140002a02  mov     [rsp+arg_18], r9
0x140002a07  sub     rsp, 68h
0x140002a0b  movdqa  [rsp+68h+var_48], xmm0
0x140002a11  movdqa  [rsp+68h+var_38], xmm1
0x140002a17  movdqa  [rsp+68h+var_28], xmm2
0x140002a1d  movdqa  [rsp+68h+var_18], xmm3
0x140002a23  mov     rdx, rax
0x140002a26  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_security_efswrt_l1_1_0_dll
0x140002a2d  call    __delayLoadHelper2
0x140002a32  movdqa  xmm0, [rsp+68h+var_48]
0x140002a38  movdqa  xmm1, [rsp+68h+var_38]
0x140002a3e  movdqa  xmm2, [rsp+68h+var_28]
0x140002a44  movdqa  xmm3, [rsp+68h+var_18]
0x140002a4a  mov     rcx, [rsp+68h+arg_0]
0x140002a4f  mov     rdx, [rsp+68h+arg_8]
0x140002a54  mov     r8, [rsp+68h+arg_10]
0x140002a5c  mov     r9, [rsp+68h+arg_18]
0x140002a64  add     rsp, 68h
0x140002a68  jmp     short $+2
0x140002a6a  jmp     rax
```
