# __tailMerge_oleaut32_dll

- ea: `0x140008be3`
- end: `0x140008c5c`
- name: `__tailMerge_oleaut32_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140008c62`
- `0x140008c74`

## callees

- `0x140006020`
- `0x140008be3`

## pseudocode

```c
__int64 __fastcall _tailMerge_oleaut32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_oleaut32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x140008be3  mov     [rsp+arg_0], rcx
0x140008be8  mov     [rsp+arg_8], rdx
0x140008bed  mov     [rsp+arg_10], r8
0x140008bf2  mov     [rsp+arg_18], r9
0x140008bf7  sub     rsp, 68h
0x140008bfb  movdqa  [rsp+68h+var_48], xmm0
0x140008c01  movdqa  [rsp+68h+var_38], xmm1
0x140008c07  movdqa  [rsp+68h+var_28], xmm2
0x140008c0d  movdqa  [rsp+68h+var_18], xmm3
0x140008c13  mov     rdx, rax
0x140008c16  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_oleaut32_dll
0x140008c1d  call    __delayLoadHelper2
0x140008c22  movdqa  xmm0, [rsp+68h+var_48]
0x140008c28  movdqa  xmm1, [rsp+68h+var_38]
0x140008c2e  movdqa  xmm2, [rsp+68h+var_28]
0x140008c34  movdqa  xmm3, [rsp+68h+var_18]
0x140008c3a  mov     rcx, [rsp+68h+arg_0]
0x140008c3f  mov     rdx, [rsp+68h+arg_8]
0x140008c44  mov     r8, [rsp+68h+arg_10]
0x140008c4c  mov     r9, [rsp+68h+arg_18]
0x140008c54  add     rsp, 68h
0x140008c58  jmp     short $+2
0x140008c5a  jmp     rax
```
