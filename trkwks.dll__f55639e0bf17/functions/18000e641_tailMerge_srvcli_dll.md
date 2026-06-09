# __tailMerge_srvcli_dll

- ea: `0x18000e641`
- end: `0x18000e6ba`
- name: `__tailMerge_srvcli_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000e6c0`

## callees

- `0x18000e641`
- `0x180010e60`

## pseudocode

```c
__int64 __fastcall _tailMerge_srvcli_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_srvcli_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000e641  mov     [rsp+arg_0], rcx
0x18000e646  mov     [rsp+arg_8], rdx
0x18000e64b  mov     [rsp+arg_10], r8
0x18000e650  mov     [rsp+arg_18], r9
0x18000e655  sub     rsp, 68h
0x18000e659  movdqa  [rsp+68h+var_48], xmm0
0x18000e65f  movdqa  [rsp+68h+var_38], xmm1
0x18000e665  movdqa  [rsp+68h+var_28], xmm2
0x18000e66b  movdqa  [rsp+68h+var_18], xmm3
0x18000e671  mov     rdx, rax
0x18000e674  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_srvcli_dll
0x18000e67b  call    __delayLoadHelper2
0x18000e680  movdqa  xmm0, [rsp+68h+var_48]
0x18000e686  movdqa  xmm1, [rsp+68h+var_38]
0x18000e68c  movdqa  xmm2, [rsp+68h+var_28]
0x18000e692  movdqa  xmm3, [rsp+68h+var_18]
0x18000e698  mov     rcx, [rsp+68h+arg_0]
0x18000e69d  mov     rdx, [rsp+68h+arg_8]
0x18000e6a2  mov     r8, [rsp+68h+arg_10]
0x18000e6aa  mov     r9, [rsp+68h+arg_18]
0x18000e6b2  add     rsp, 68h
0x18000e6b6  jmp     short $+2
0x18000e6b8  jmp     rax
```
