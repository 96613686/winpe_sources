# __tailMerge_oleaut32_dll

- ea: `0x18000234c`
- end: `0x1800023c5`
- name: `__tailMerge_oleaut32_dll`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800023cb`
- `0x1800023dd`
- `0x1800023ef`

## callees

- `0x18000234c`
- `0x18001be40`

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
0x18000234c  mov     [rsp+arg_0], rcx
0x180002351  mov     [rsp+arg_8], rdx
0x180002356  mov     [rsp+arg_10], r8
0x18000235b  mov     [rsp+arg_18], r9
0x180002360  sub     rsp, 68h
0x180002364  movdqa  [rsp+68h+var_48], xmm0
0x18000236a  movdqa  [rsp+68h+var_38], xmm1
0x180002370  movdqa  [rsp+68h+var_28], xmm2
0x180002376  movdqa  [rsp+68h+var_18], xmm3
0x18000237c  mov     rdx, rax
0x18000237f  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_oleaut32_dll
0x180002386  call    __delayLoadHelper2
0x18000238b  movdqa  xmm0, [rsp+68h+var_48]
0x180002391  movdqa  xmm1, [rsp+68h+var_38]
0x180002397  movdqa  xmm2, [rsp+68h+var_28]
0x18000239d  movdqa  xmm3, [rsp+68h+var_18]
0x1800023a3  mov     rcx, [rsp+68h+arg_0]
0x1800023a8  mov     rdx, [rsp+68h+arg_8]
0x1800023ad  mov     r8, [rsp+68h+arg_10]
0x1800023b5  mov     r9, [rsp+68h+arg_18]
0x1800023bd  add     rsp, 68h
0x1800023c1  jmp     short $+2
0x1800023c3  jmp     rax
```
