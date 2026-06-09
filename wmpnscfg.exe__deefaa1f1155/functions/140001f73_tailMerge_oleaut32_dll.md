# __tailMerge_oleaut32_dll

- ea: `0x140001f73`
- end: `0x140001fec`
- name: `__tailMerge_oleaut32_dll`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140001ff2`
- `0x140002004`

## callees

- `0x140001f73`
- `0x140007430`

## pseudocode

```c
__int64 __fastcall _tailMerge_oleaut32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_oleaut32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x140001f73  mov     [rsp+arg_0], rcx
0x140001f78  mov     [rsp+arg_8], rdx
0x140001f7d  mov     [rsp+arg_10], r8
0x140001f82  mov     [rsp+arg_18], r9
0x140001f87  sub     rsp, 68h
0x140001f8b  movdqa  [rsp+68h+var_48], xmm0
0x140001f91  movdqa  [rsp+68h+var_38], xmm1
0x140001f97  movdqa  [rsp+68h+var_28], xmm2
0x140001f9d  movdqa  [rsp+68h+var_18], xmm3
0x140001fa3  mov     rdx, rax
0x140001fa6  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_oleaut32_dll
0x140001fad  call    __delayLoadHelper2
0x140001fb2  movdqa  xmm0, [rsp+68h+var_48]
0x140001fb8  movdqa  xmm1, [rsp+68h+var_38]
0x140001fbe  movdqa  xmm2, [rsp+68h+var_28]
0x140001fc4  movdqa  xmm3, [rsp+68h+var_18]
0x140001fca  mov     rcx, [rsp+68h+arg_0]
0x140001fcf  mov     rdx, [rsp+68h+arg_8]
0x140001fd4  mov     r8, [rsp+68h+arg_10]
0x140001fdc  mov     r9, [rsp+68h+arg_18]
0x140001fe4  add     rsp, 68h
0x140001fe8  jmp     short $+2
0x140001fea  jmp     rax
```
