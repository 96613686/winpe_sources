# __tailMerge_ws2_32_dll

- ea: `0x180027515`
- end: `0x18002758e`
- name: `__tailMerge_ws2_32_dll`
- size: `121`
- prototype: ``
- caller_count: `24`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180027594`
- `0x1800275a6`
- `0x180027643`
- `0x1800276e0`
- `0x180027728`
- `0x1800277ca`
- `0x1800277dc`
- `0x1800277ee`
- `0x180027800`
- `0x180027812`
- `0x180027824`
- `0x180027836`
- `0x180027848`
- `0x18002785a`
- `0x18002786c`
- `0x18002787e`
- `0x180027890`
- `0x1800278b4`
- `0x1800278c6`
- `0x1800278d8`
- `0x1800278ea`
- `0x180027bf5`
- `0x180027c07`
- `0x180027c73`

## callees

- `0x180025f20`
- `0x180027515`

## pseudocode

```c
__int64 __fastcall _tailMerge_ws2_32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ws2_32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180027515  mov     [rsp+arg_0], rcx
0x18002751a  mov     [rsp+arg_8], rdx
0x18002751f  mov     [rsp+arg_10], r8
0x180027524  mov     [rsp+arg_18], r9
0x180027529  sub     rsp, 68h
0x18002752d  movdqa  [rsp+68h+var_48], xmm0
0x180027533  movdqa  [rsp+68h+var_38], xmm1
0x180027539  movdqa  [rsp+68h+var_28], xmm2
0x18002753f  movdqa  [rsp+68h+var_18], xmm3
0x180027545  mov     rdx, rax
0x180027548  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ws2_32_dll
0x18002754f  call    __delayLoadHelper2
0x180027554  movdqa  xmm0, [rsp+68h+var_48]
0x18002755a  movdqa  xmm1, [rsp+68h+var_38]
0x180027560  movdqa  xmm2, [rsp+68h+var_28]
0x180027566  movdqa  xmm3, [rsp+68h+var_18]
0x18002756c  mov     rcx, [rsp+68h+arg_0]
0x180027571  mov     rdx, [rsp+68h+arg_8]
0x180027576  mov     r8, [rsp+68h+arg_10]
0x18002757e  mov     r9, [rsp+68h+arg_18]
0x180027586  add     rsp, 68h
0x18002758a  jmp     short $+2
0x18002758c  jmp     rax
```
