# __tailMerge_ole32_dll

- ea: `0x1800060fc`
- end: `0x180006175`
- name: `__tailMerge_ole32_dll`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000617b`
- `0x18000618d`
- `0x18000619f`

## callees

- `0x1800060fc`
- `0x180014d80`

## pseudocode

```c
__int64 __fastcall _tailMerge_ole32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ole32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800060fc  mov     [rsp+arg_0], rcx
0x180006101  mov     [rsp+arg_8], rdx
0x180006106  mov     [rsp+arg_10], r8
0x18000610b  mov     [rsp+arg_18], r9
0x180006110  sub     rsp, 68h
0x180006114  movdqa  [rsp+68h+var_48], xmm0
0x18000611a  movdqa  [rsp+68h+var_38], xmm1
0x180006120  movdqa  [rsp+68h+var_28], xmm2
0x180006126  movdqa  [rsp+68h+var_18], xmm3
0x18000612c  mov     rdx, rax
0x18000612f  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ole32_dll
0x180006136  call    __delayLoadHelper2
0x18000613b  movdqa  xmm0, [rsp+68h+var_48]
0x180006141  movdqa  xmm1, [rsp+68h+var_38]
0x180006147  movdqa  xmm2, [rsp+68h+var_28]
0x18000614d  movdqa  xmm3, [rsp+68h+var_18]
0x180006153  mov     rcx, [rsp+68h+arg_0]
0x180006158  mov     rdx, [rsp+68h+arg_8]
0x18000615d  mov     r8, [rsp+68h+arg_10]
0x180006165  mov     r9, [rsp+68h+arg_18]
0x18000616d  add     rsp, 68h
0x180006171  jmp     short $+2
0x180006173  jmp     rax
```
