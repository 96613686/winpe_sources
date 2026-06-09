# __tailMerge_cryptsp_dll

- ea: `0x1800074be`
- end: `0x180007537`
- name: `__tailMerge_cryptsp_dll`
- size: `121`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000753d`
- `0x18000754f`
- `0x180007561`
- `0x180007573`
- `0x180007585`
- `0x180007597`
- `0x1800075a9`

## callees

- `0x1800054c0`
- `0x1800074be`

## pseudocode

```c
__int64 __fastcall _tailMerge_cryptsp_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_cryptsp_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800074be  mov     [rsp+arg_0], rcx
0x1800074c3  mov     [rsp+arg_8], rdx
0x1800074c8  mov     [rsp+arg_10], r8
0x1800074cd  mov     [rsp+arg_18], r9
0x1800074d2  sub     rsp, 68h
0x1800074d6  movdqa  [rsp+68h+var_48], xmm0
0x1800074dc  movdqa  [rsp+68h+var_38], xmm1
0x1800074e2  movdqa  [rsp+68h+var_28], xmm2
0x1800074e8  movdqa  [rsp+68h+var_18], xmm3
0x1800074ee  mov     rdx, rax
0x1800074f1  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_cryptsp_dll
0x1800074f8  call    __delayLoadHelper2
0x1800074fd  movdqa  xmm0, [rsp+68h+var_48]
0x180007503  movdqa  xmm1, [rsp+68h+var_38]
0x180007509  movdqa  xmm2, [rsp+68h+var_28]
0x18000750f  movdqa  xmm3, [rsp+68h+var_18]
0x180007515  mov     rcx, [rsp+68h+arg_0]
0x18000751a  mov     rdx, [rsp+68h+arg_8]
0x18000751f  mov     r8, [rsp+68h+arg_10]
0x180007527  mov     r9, [rsp+68h+arg_18]
0x18000752f  add     rsp, 68h
0x180007533  jmp     short $+2
0x180007535  jmp     rax
```
