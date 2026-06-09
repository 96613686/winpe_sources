# __tailMerge_ext_ms_win_ntuser_windowclass_l1_1_0_dll

- ea: `0x180002ada`
- end: `0x180002b53`
- name: `__tailMerge_ext_ms_win_ntuser_windowclass_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002b59`
- `0x180002b6b`
- `0x180002b7d`
- `0x180002be4`
- `0x180002bf6`
- `0x180002c08`

## callees

- `0x180002ada`
- `0x180016ac0`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_ntuser_windowclass_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_windowclass_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002ada  mov     [rsp+arg_0], rcx
0x180002adf  mov     [rsp+arg_8], rdx
0x180002ae4  mov     [rsp+arg_10], r8
0x180002ae9  mov     [rsp+arg_18], r9
0x180002aee  sub     rsp, 68h
0x180002af2  movdqa  [rsp+68h+var_48], xmm0
0x180002af8  movdqa  [rsp+68h+var_38], xmm1
0x180002afe  movdqa  [rsp+68h+var_28], xmm2
0x180002b04  movdqa  [rsp+68h+var_18], xmm3
0x180002b0a  mov     rdx, rax
0x180002b0d  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_windowclass_l1_1_0_dll
0x180002b14  call    __delayLoadHelper2
0x180002b19  movdqa  xmm0, [rsp+68h+var_48]
0x180002b1f  movdqa  xmm1, [rsp+68h+var_38]
0x180002b25  movdqa  xmm2, [rsp+68h+var_28]
0x180002b2b  movdqa  xmm3, [rsp+68h+var_18]
0x180002b31  mov     rcx, [rsp+68h+arg_0]
0x180002b36  mov     rdx, [rsp+68h+arg_8]
0x180002b3b  mov     r8, [rsp+68h+arg_10]
0x180002b43  mov     r9, [rsp+68h+arg_18]
0x180002b4b  add     rsp, 68h
0x180002b4f  jmp     short $+2
0x180002b51  jmp     rax
```
