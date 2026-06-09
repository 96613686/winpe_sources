# __tailMerge_cryptbase_dll

- ea: `0x180018bc0`
- end: `0x180018c39`
- name: `__tailMerge_cryptbase_dll`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180018c3f`
- `0x180018c51`

## callees

- `0x180018bc0`
- `0x180021f30`

## pseudocode

```c
__int64 __fastcall _tailMerge_cryptbase_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_cryptbase_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180018bc0  mov     [rsp+arg_0], rcx
0x180018bc5  mov     [rsp+arg_8], rdx
0x180018bca  mov     [rsp+arg_10], r8
0x180018bcf  mov     [rsp+arg_18], r9
0x180018bd4  sub     rsp, 68h
0x180018bd8  movdqa  [rsp+68h+var_48], xmm0
0x180018bde  movdqa  [rsp+68h+var_38], xmm1
0x180018be4  movdqa  [rsp+68h+var_28], xmm2
0x180018bea  movdqa  [rsp+68h+var_18], xmm3
0x180018bf0  mov     rdx, rax
0x180018bf3  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_cryptbase_dll
0x180018bfa  call    __delayLoadHelper2
0x180018bff  movdqa  xmm0, [rsp+68h+var_48]
0x180018c05  movdqa  xmm1, [rsp+68h+var_38]
0x180018c0b  movdqa  xmm2, [rsp+68h+var_28]
0x180018c11  movdqa  xmm3, [rsp+68h+var_18]
0x180018c17  mov     rcx, [rsp+68h+arg_0]
0x180018c1c  mov     rdx, [rsp+68h+arg_8]
0x180018c21  mov     r8, [rsp+68h+arg_10]
0x180018c29  mov     r9, [rsp+68h+arg_18]
0x180018c31  add     rsp, 68h
0x180018c35  jmp     short $+2
0x180018c37  jmp     rax
```
