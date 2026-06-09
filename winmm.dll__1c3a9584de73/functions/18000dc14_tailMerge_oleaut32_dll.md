# __tailMerge_oleaut32_dll

- ea: `0x18000dc14`
- end: `0x18000dc8d`
- name: `__tailMerge_oleaut32_dll`
- size: `121`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000dc93`
- `0x18000dca5`
- `0x18000dcb7`
- `0x18000dcc9`
- `0x18000dcdb`

## callees

- `0x180009370`
- `0x18000dc14`

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
0x18000dc14  mov     [rsp+arg_0], rcx
0x18000dc19  mov     [rsp+arg_8], rdx
0x18000dc1e  mov     [rsp+arg_10], r8
0x18000dc23  mov     [rsp+arg_18], r9
0x18000dc28  sub     rsp, 68h
0x18000dc2c  movdqa  [rsp+68h+var_48], xmm0
0x18000dc32  movdqa  [rsp+68h+var_38], xmm1
0x18000dc38  movdqa  [rsp+68h+var_28], xmm2
0x18000dc3e  movdqa  [rsp+68h+var_18], xmm3
0x18000dc44  mov     rdx, rax
0x18000dc47  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_oleaut32_dll
0x18000dc4e  call    __delayLoadHelper2
0x18000dc53  movdqa  xmm0, [rsp+68h+var_48]
0x18000dc59  movdqa  xmm1, [rsp+68h+var_38]
0x18000dc5f  movdqa  xmm2, [rsp+68h+var_28]
0x18000dc65  movdqa  xmm3, [rsp+68h+var_18]
0x18000dc6b  mov     rcx, [rsp+68h+arg_0]
0x18000dc70  mov     rdx, [rsp+68h+arg_8]
0x18000dc75  mov     r8, [rsp+68h+arg_10]
0x18000dc7d  mov     r9, [rsp+68h+arg_18]
0x18000dc85  add     rsp, 68h
0x18000dc89  jmp     short $+2
0x18000dc8b  jmp     rax
```
