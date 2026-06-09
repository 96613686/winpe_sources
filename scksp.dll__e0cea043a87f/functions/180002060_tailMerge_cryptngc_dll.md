# __tailMerge_cryptngc_dll

- ea: `0x180002060`
- end: `0x1800020d9`
- name: `__tailMerge_cryptngc_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800020df`

## callees

- `0x180002060`
- `0x18003c140`

## pseudocode

```c
__int64 __fastcall _tailMerge_cryptngc_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_cryptngc_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002060  mov     [rsp+arg_0], rcx
0x180002065  mov     [rsp+arg_8], rdx
0x18000206a  mov     [rsp+arg_10], r8
0x18000206f  mov     [rsp+arg_18], r9
0x180002074  sub     rsp, 68h
0x180002078  movdqa  [rsp+68h+var_48], xmm0
0x18000207e  movdqa  [rsp+68h+var_38], xmm1
0x180002084  movdqa  [rsp+68h+var_28], xmm2
0x18000208a  movdqa  [rsp+68h+var_18], xmm3
0x180002090  mov     rdx, rax
0x180002093  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_cryptngc_dll
0x18000209a  call    __delayLoadHelper2
0x18000209f  movdqa  xmm0, [rsp+68h+var_48]
0x1800020a5  movdqa  xmm1, [rsp+68h+var_38]
0x1800020ab  movdqa  xmm2, [rsp+68h+var_28]
0x1800020b1  movdqa  xmm3, [rsp+68h+var_18]
0x1800020b7  mov     rcx, [rsp+68h+arg_0]
0x1800020bc  mov     rdx, [rsp+68h+arg_8]
0x1800020c1  mov     r8, [rsp+68h+arg_10]
0x1800020c9  mov     r9, [rsp+68h+arg_18]
0x1800020d1  add     rsp, 68h
0x1800020d5  jmp     short $+2
0x1800020d7  jmp     rax
```
