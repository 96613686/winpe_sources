# __tailMerge_rpcrt4_dll

- ea: `0x180011239`
- end: `0x1800112b2`
- name: `__tailMerge_rpcrt4_dll`
- size: `121`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800112b8`
- `0x1800112ca`
- `0x1800112ee`
- `0x180011336`
- `0x180011482`
- `0x180011543`

## callees

- `0x18000f240`
- `0x180011239`

## pseudocode

```c
__int64 __fastcall _tailMerge_rpcrt4_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_rpcrt4_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180011239  mov     [rsp+arg_0], rcx
0x18001123e  mov     [rsp+arg_8], rdx
0x180011243  mov     [rsp+arg_10], r8
0x180011248  mov     [rsp+arg_18], r9
0x18001124d  sub     rsp, 68h
0x180011251  movdqa  [rsp+68h+var_48], xmm0
0x180011257  movdqa  [rsp+68h+var_38], xmm1
0x18001125d  movdqa  [rsp+68h+var_28], xmm2
0x180011263  movdqa  [rsp+68h+var_18], xmm3
0x180011269  mov     rdx, rax
0x18001126c  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_rpcrt4_dll
0x180011273  call    __delayLoadHelper2
0x180011278  movdqa  xmm0, [rsp+68h+var_48]
0x18001127e  movdqa  xmm1, [rsp+68h+var_38]
0x180011284  movdqa  xmm2, [rsp+68h+var_28]
0x18001128a  movdqa  xmm3, [rsp+68h+var_18]
0x180011290  mov     rcx, [rsp+68h+arg_0]
0x180011295  mov     rdx, [rsp+68h+arg_8]
0x18001129a  mov     r8, [rsp+68h+arg_10]
0x1800112a2  mov     r9, [rsp+68h+arg_18]
0x1800112aa  add     rsp, 68h
0x1800112ae  jmp     short $+2
0x1800112b0  jmp     rax
```
