# __tailMerge_cryptbase_dll

- ea: `0x180006f72`
- end: `0x180006feb`
- name: `__tailMerge_cryptbase_dll`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180006ff1`
- `0x180007197`

## callees

- `0x1800054c0`
- `0x180006f72`

## pseudocode

```c
__int64 __fastcall _tailMerge_cryptbase_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_cryptbase_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180006f72  mov     [rsp+arg_0], rcx
0x180006f77  mov     [rsp+arg_8], rdx
0x180006f7c  mov     [rsp+arg_10], r8
0x180006f81  mov     [rsp+arg_18], r9
0x180006f86  sub     rsp, 68h
0x180006f8a  movdqa  [rsp+68h+var_48], xmm0
0x180006f90  movdqa  [rsp+68h+var_38], xmm1
0x180006f96  movdqa  [rsp+68h+var_28], xmm2
0x180006f9c  movdqa  [rsp+68h+var_18], xmm3
0x180006fa2  mov     rdx, rax
0x180006fa5  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_cryptbase_dll
0x180006fac  call    __delayLoadHelper2
0x180006fb1  movdqa  xmm0, [rsp+68h+var_48]
0x180006fb7  movdqa  xmm1, [rsp+68h+var_38]
0x180006fbd  movdqa  xmm2, [rsp+68h+var_28]
0x180006fc3  movdqa  xmm3, [rsp+68h+var_18]
0x180006fc9  mov     rcx, [rsp+68h+arg_0]
0x180006fce  mov     rdx, [rsp+68h+arg_8]
0x180006fd3  mov     r8, [rsp+68h+arg_10]
0x180006fdb  mov     r9, [rsp+68h+arg_18]
0x180006fe3  add     rsp, 68h
0x180006fe7  jmp     short $+2
0x180006fe9  jmp     rax
```
