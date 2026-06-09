# __tailMerge_oleaut32_dll

- ea: `0x18000290f`
- end: `0x180002988`
- name: `__tailMerge_oleaut32_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000298e`

## callees

- `0x18000290f`
- `0x18000da70`

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
0x18000290f  mov     [rsp+arg_0], rcx
0x180002914  mov     [rsp+arg_8], rdx
0x180002919  mov     [rsp+arg_10], r8
0x18000291e  mov     [rsp+arg_18], r9
0x180002923  sub     rsp, 68h
0x180002927  movdqa  [rsp+68h+var_48], xmm0
0x18000292d  movdqa  [rsp+68h+var_38], xmm1
0x180002933  movdqa  [rsp+68h+var_28], xmm2
0x180002939  movdqa  [rsp+68h+var_18], xmm3
0x18000293f  mov     rdx, rax
0x180002942  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_oleaut32_dll
0x180002949  call    __delayLoadHelper2
0x18000294e  movdqa  xmm0, [rsp+68h+var_48]
0x180002954  movdqa  xmm1, [rsp+68h+var_38]
0x18000295a  movdqa  xmm2, [rsp+68h+var_28]
0x180002960  movdqa  xmm3, [rsp+68h+var_18]
0x180002966  mov     rcx, [rsp+68h+arg_0]
0x18000296b  mov     rdx, [rsp+68h+arg_8]
0x180002970  mov     r8, [rsp+68h+arg_10]
0x180002978  mov     r9, [rsp+68h+arg_18]
0x180002980  add     rsp, 68h
0x180002984  jmp     short $+2
0x180002986  jmp     rax
```
