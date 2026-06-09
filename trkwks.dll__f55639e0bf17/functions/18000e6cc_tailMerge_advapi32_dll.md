# __tailMerge_advapi32_dll

- ea: `0x18000e6cc`
- end: `0x18000e745`
- name: `__tailMerge_advapi32_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000e74b`
- `0x18000e75d`
- `0x18000e76f`

## callees

- `0x18000e6cc`
- `0x180010e60`

## pseudocode

```c
__int64 __fastcall _tailMerge_advapi32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_advapi32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000e6cc  mov     [rsp+arg_0], rcx
0x18000e6d1  mov     [rsp+arg_8], rdx
0x18000e6d6  mov     [rsp+arg_10], r8
0x18000e6db  mov     [rsp+arg_18], r9
0x18000e6e0  sub     rsp, 68h
0x18000e6e4  movdqa  [rsp+68h+var_48], xmm0
0x18000e6ea  movdqa  [rsp+68h+var_38], xmm1
0x18000e6f0  movdqa  [rsp+68h+var_28], xmm2
0x18000e6f6  movdqa  [rsp+68h+var_18], xmm3
0x18000e6fc  mov     rdx, rax
0x18000e6ff  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_advapi32_dll
0x18000e706  call    __delayLoadHelper2
0x18000e70b  movdqa  xmm0, [rsp+68h+var_48]
0x18000e711  movdqa  xmm1, [rsp+68h+var_38]
0x18000e717  movdqa  xmm2, [rsp+68h+var_28]
0x18000e71d  movdqa  xmm3, [rsp+68h+var_18]
0x18000e723  mov     rcx, [rsp+68h+arg_0]
0x18000e728  mov     rdx, [rsp+68h+arg_8]
0x18000e72d  mov     r8, [rsp+68h+arg_10]
0x18000e735  mov     r9, [rsp+68h+arg_18]
0x18000e73d  add     rsp, 68h
0x18000e741  jmp     short $+2
0x18000e743  jmp     rax
```
