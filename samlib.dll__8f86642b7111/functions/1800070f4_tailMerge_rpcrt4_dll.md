# __tailMerge_rpcrt4_dll

- ea: `0x1800070f4`
- end: `0x18000716d`
- name: `__tailMerge_rpcrt4_dll`
- size: `121`
- prototype: ``
- caller_count: `14`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180007173`
- `0x180007185`
- `0x1800071f1`
- `0x180007203`
- `0x180007215`
- `0x180007227`
- `0x180007239`
- `0x18000724b`
- `0x1800072e8`
- `0x1800072fa`
- `0x18000730c`
- `0x18000731e`
- `0x180007330`
- `0x1800073cd`

## callees

- `0x1800054c0`
- `0x1800070f4`

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
0x1800070f4  mov     [rsp+arg_0], rcx
0x1800070f9  mov     [rsp+arg_8], rdx
0x1800070fe  mov     [rsp+arg_10], r8
0x180007103  mov     [rsp+arg_18], r9
0x180007108  sub     rsp, 68h
0x18000710c  movdqa  [rsp+68h+var_48], xmm0
0x180007112  movdqa  [rsp+68h+var_38], xmm1
0x180007118  movdqa  [rsp+68h+var_28], xmm2
0x18000711e  movdqa  [rsp+68h+var_18], xmm3
0x180007124  mov     rdx, rax
0x180007127  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_rpcrt4_dll
0x18000712e  call    __delayLoadHelper2
0x180007133  movdqa  xmm0, [rsp+68h+var_48]
0x180007139  movdqa  xmm1, [rsp+68h+var_38]
0x18000713f  movdqa  xmm2, [rsp+68h+var_28]
0x180007145  movdqa  xmm3, [rsp+68h+var_18]
0x18000714b  mov     rcx, [rsp+68h+arg_0]
0x180007150  mov     rdx, [rsp+68h+arg_8]
0x180007155  mov     r8, [rsp+68h+arg_10]
0x18000715d  mov     r9, [rsp+68h+arg_18]
0x180007165  add     rsp, 68h
0x180007169  jmp     short $+2
0x18000716b  jmp     rax
```
