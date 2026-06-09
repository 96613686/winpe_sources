# __tailMerge_ws2_32_dll

- ea: `0x180008e0f`
- end: `0x180008e88`
- name: `__tailMerge_ws2_32_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180008e8e`
- `0x180008ea0`
- `0x180008eb2`

## callees

- `0x180006a50`
- `0x180008e0f`

## pseudocode

```c
__int64 __fastcall _tailMerge_ws2_32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_ws2_32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180008e0f  mov     [rsp+arg_0], rcx
0x180008e14  mov     [rsp+arg_8], rdx
0x180008e19  mov     [rsp+arg_10], r8
0x180008e1e  mov     [rsp+arg_18], r9
0x180008e23  sub     rsp, 68h
0x180008e27  movdqa  [rsp+68h+var_48], xmm0
0x180008e2d  movdqa  [rsp+68h+var_38], xmm1
0x180008e33  movdqa  [rsp+68h+var_28], xmm2
0x180008e39  movdqa  [rsp+68h+var_18], xmm3
0x180008e3f  mov     rdx, rax
0x180008e42  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ws2_32_dll
0x180008e49  call    __delayLoadHelper2
0x180008e4e  movdqa  xmm0, [rsp+68h+var_48]
0x180008e54  movdqa  xmm1, [rsp+68h+var_38]
0x180008e5a  movdqa  xmm2, [rsp+68h+var_28]
0x180008e60  movdqa  xmm3, [rsp+68h+var_18]
0x180008e66  mov     rcx, [rsp+68h+arg_0]
0x180008e6b  mov     rdx, [rsp+68h+arg_8]
0x180008e70  mov     r8, [rsp+68h+arg_10]
0x180008e78  mov     r9, [rsp+68h+arg_18]
0x180008e80  add     rsp, 68h
0x180008e84  jmp     short $+2
0x180008e86  jmp     rax
```
