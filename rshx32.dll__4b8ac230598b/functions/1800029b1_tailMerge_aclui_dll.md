# __tailMerge_aclui_dll

- ea: `0x1800029b1`
- end: `0x180002a2a`
- name: `__tailMerge_aclui_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180002a30`
- `0x180002a42`
- `0x180002a54`

## callees

- `0x1800029b1`
- `0x18001d240`

## pseudocode

```c
__int64 __fastcall _tailMerge_aclui_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_aclui_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800029b1  mov     [rsp+arg_0], rcx
0x1800029b6  mov     [rsp+arg_8], rdx
0x1800029bb  mov     [rsp+arg_10], r8
0x1800029c0  mov     [rsp+arg_18], r9
0x1800029c5  sub     rsp, 68h
0x1800029c9  movdqa  [rsp+68h+var_48], xmm0
0x1800029cf  movdqa  [rsp+68h+var_38], xmm1
0x1800029d5  movdqa  [rsp+68h+var_28], xmm2
0x1800029db  movdqa  [rsp+68h+var_18], xmm3
0x1800029e1  mov     rdx, rax
0x1800029e4  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_aclui_dll
0x1800029eb  call    __delayLoadHelper2
0x1800029f0  movdqa  xmm0, [rsp+68h+var_48]
0x1800029f6  movdqa  xmm1, [rsp+68h+var_38]
0x1800029fc  movdqa  xmm2, [rsp+68h+var_28]
0x180002a02  movdqa  xmm3, [rsp+68h+var_18]
0x180002a08  mov     rcx, [rsp+68h+arg_0]
0x180002a0d  mov     rdx, [rsp+68h+arg_8]
0x180002a12  mov     r8, [rsp+68h+arg_10]
0x180002a1a  mov     r9, [rsp+68h+arg_18]
0x180002a22  add     rsp, 68h
0x180002a26  jmp     short $+2
0x180002a28  jmp     rax
```
