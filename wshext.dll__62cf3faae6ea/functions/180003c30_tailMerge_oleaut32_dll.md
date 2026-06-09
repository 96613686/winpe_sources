# __tailMerge_oleaut32_dll

- ea: `0x180003c30`
- end: `0x180003ca9`
- name: `__tailMerge_oleaut32_dll`
- size: `121`
- prototype: ``
- caller_count: `11`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003caf`
- `0x180003cc1`
- `0x180003cd3`
- `0x180003ce5`
- `0x180003cf7`
- `0x180003d09`
- `0x180003d1b`
- `0x180003d2d`
- `0x180003d3f`
- `0x18000433f`
- `0x180004351`

## callees

- `0x180002eb0`
- `0x180003c30`

## pseudocode

```c
__int64 __fastcall _tailMerge_oleaut32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_oleaut32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180003c30  mov     [rsp+arg_0], rcx
0x180003c35  mov     [rsp+arg_8], rdx
0x180003c3a  mov     [rsp+arg_10], r8
0x180003c3f  mov     [rsp+arg_18], r9
0x180003c44  sub     rsp, 68h
0x180003c48  movdqa  [rsp+68h+var_48], xmm0
0x180003c4e  movdqa  [rsp+68h+var_38], xmm1
0x180003c54  movdqa  [rsp+68h+var_28], xmm2
0x180003c5a  movdqa  [rsp+68h+var_18], xmm3
0x180003c60  mov     rdx, rax
0x180003c63  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_oleaut32_dll
0x180003c6a  call    __delayLoadHelper2
0x180003c6f  movdqa  xmm0, [rsp+68h+var_48]
0x180003c75  movdqa  xmm1, [rsp+68h+var_38]
0x180003c7b  movdqa  xmm2, [rsp+68h+var_28]
0x180003c81  movdqa  xmm3, [rsp+68h+var_18]
0x180003c87  mov     rcx, [rsp+68h+arg_0]
0x180003c8c  mov     rdx, [rsp+68h+arg_8]
0x180003c91  mov     r8, [rsp+68h+arg_10]
0x180003c99  mov     r9, [rsp+68h+arg_18]
0x180003ca1  add     rsp, 68h
0x180003ca5  jmp     short $+2
0x180003ca7  jmp     rax
```
