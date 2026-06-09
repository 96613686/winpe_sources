# __tailMerge_sspicli_dll

- ea: `0x180003b90`
- end: `0x180003c09`
- name: `__tailMerge_sspicli_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `8`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003c0f`
- `0x180003c21`
- `0x180003c33`
- `0x180003c45`
- `0x180003d7f`
- `0x180003d91`
- `0x180003dec`
- `0x180003dfe`

## callees

- `0x180003580`
- `0x180003b90`

## pseudocode

```c
__int64 __fastcall _tailMerge_sspicli_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_sspicli_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180003b90  mov     [rsp+arg_0], rcx
0x180003b95  mov     [rsp+arg_8], rdx
0x180003b9a  mov     [rsp+arg_10], r8
0x180003b9f  mov     [rsp+arg_18], r9
0x180003ba4  sub     rsp, 68h
0x180003ba8  movdqa  [rsp+68h+var_48], xmm0
0x180003bae  movdqa  [rsp+68h+var_38], xmm1
0x180003bb4  movdqa  [rsp+68h+var_28], xmm2
0x180003bba  movdqa  [rsp+68h+var_18], xmm3
0x180003bc0  mov     rdx, rax
0x180003bc3  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_sspicli_dll
0x180003bca  call    __delayLoadHelper2
0x180003bcf  movdqa  xmm0, [rsp+68h+var_48]
0x180003bd5  movdqa  xmm1, [rsp+68h+var_38]
0x180003bdb  movdqa  xmm2, [rsp+68h+var_28]
0x180003be1  movdqa  xmm3, [rsp+68h+var_18]
0x180003be7  mov     rcx, [rsp+68h+arg_0]
0x180003bec  mov     rdx, [rsp+68h+arg_8]
0x180003bf1  mov     r8, [rsp+68h+arg_10]
0x180003bf9  mov     r9, [rsp+68h+arg_18]
0x180003c01  add     rsp, 68h
0x180003c05  jmp     short $+2
0x180003c07  jmp     rax
```
