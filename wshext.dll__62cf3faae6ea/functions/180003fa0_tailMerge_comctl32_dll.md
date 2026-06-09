# __tailMerge_comctl32_dll

- ea: `0x180003fa0`
- end: `0x180004019`
- name: `__tailMerge_comctl32_dll`
- size: `121`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000401f`
- `0x180004031`
- `0x18000431b`
- `0x18000432d`

## callees

- `0x180002eb0`
- `0x180003fa0`

## pseudocode

```c
__int64 __fastcall _tailMerge_comctl32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_comctl32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180003fa0  mov     [rsp+arg_0], rcx
0x180003fa5  mov     [rsp+arg_8], rdx
0x180003faa  mov     [rsp+arg_10], r8
0x180003faf  mov     [rsp+arg_18], r9
0x180003fb4  sub     rsp, 68h
0x180003fb8  movdqa  [rsp+68h+var_48], xmm0
0x180003fbe  movdqa  [rsp+68h+var_38], xmm1
0x180003fc4  movdqa  [rsp+68h+var_28], xmm2
0x180003fca  movdqa  [rsp+68h+var_18], xmm3
0x180003fd0  mov     rdx, rax
0x180003fd3  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_comctl32_dll
0x180003fda  call    __delayLoadHelper2
0x180003fdf  movdqa  xmm0, [rsp+68h+var_48]
0x180003fe5  movdqa  xmm1, [rsp+68h+var_38]
0x180003feb  movdqa  xmm2, [rsp+68h+var_28]
0x180003ff1  movdqa  xmm3, [rsp+68h+var_18]
0x180003ff7  mov     rcx, [rsp+68h+arg_0]
0x180003ffc  mov     rdx, [rsp+68h+arg_8]
0x180004001  mov     r8, [rsp+68h+arg_10]
0x180004009  mov     r9, [rsp+68h+arg_18]
0x180004011  add     rsp, 68h
0x180004015  jmp     short $+2
0x180004017  jmp     rax
```
