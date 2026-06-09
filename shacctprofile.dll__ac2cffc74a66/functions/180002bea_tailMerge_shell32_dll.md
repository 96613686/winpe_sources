# __tailMerge_shell32_dll

- ea: `0x180002bea`
- end: `0x180002c63`
- name: `__tailMerge_shell32_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002c69`
- `0x180002c7b`
- `0x180002c8d`

## callees

- `0x180002bea`
- `0x1800095f0`

## pseudocode

```c
__int64 __fastcall _tailMerge_shell32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_shell32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002bea  mov     [rsp+arg_0], rcx
0x180002bef  mov     [rsp+arg_8], rdx
0x180002bf4  mov     [rsp+arg_10], r8
0x180002bf9  mov     [rsp+arg_18], r9
0x180002bfe  sub     rsp, 68h
0x180002c02  movdqa  [rsp+68h+var_48], xmm0
0x180002c08  movdqa  [rsp+68h+var_38], xmm1
0x180002c0e  movdqa  [rsp+68h+var_28], xmm2
0x180002c14  movdqa  [rsp+68h+var_18], xmm3
0x180002c1a  mov     rdx, rax
0x180002c1d  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_shell32_dll
0x180002c24  call    __delayLoadHelper2
0x180002c29  movdqa  xmm0, [rsp+68h+var_48]
0x180002c2f  movdqa  xmm1, [rsp+68h+var_38]
0x180002c35  movdqa  xmm2, [rsp+68h+var_28]
0x180002c3b  movdqa  xmm3, [rsp+68h+var_18]
0x180002c41  mov     rcx, [rsp+68h+arg_0]
0x180002c46  mov     rdx, [rsp+68h+arg_8]
0x180002c4b  mov     r8, [rsp+68h+arg_10]
0x180002c53  mov     r9, [rsp+68h+arg_18]
0x180002c5b  add     rsp, 68h
0x180002c5f  jmp     short $+2
0x180002c61  jmp     rax
```
