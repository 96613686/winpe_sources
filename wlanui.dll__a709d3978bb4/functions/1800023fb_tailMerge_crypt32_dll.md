# __tailMerge_crypt32_dll

- ea: `0x1800023fb`
- end: `0x180002474`
- name: `__tailMerge_crypt32_dll`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000247a`
- `0x18000248c`

## callees

- `0x1800023fb`
- `0x18001be40`

## pseudocode

```c
__int64 __fastcall _tailMerge_crypt32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_crypt32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800023fb  mov     [rsp+arg_0], rcx
0x180002400  mov     [rsp+arg_8], rdx
0x180002405  mov     [rsp+arg_10], r8
0x18000240a  mov     [rsp+arg_18], r9
0x18000240f  sub     rsp, 68h
0x180002413  movdqa  [rsp+68h+var_48], xmm0
0x180002419  movdqa  [rsp+68h+var_38], xmm1
0x18000241f  movdqa  [rsp+68h+var_28], xmm2
0x180002425  movdqa  [rsp+68h+var_18], xmm3
0x18000242b  mov     rdx, rax
0x18000242e  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_crypt32_dll
0x180002435  call    __delayLoadHelper2
0x18000243a  movdqa  xmm0, [rsp+68h+var_48]
0x180002440  movdqa  xmm1, [rsp+68h+var_38]
0x180002446  movdqa  xmm2, [rsp+68h+var_28]
0x18000244c  movdqa  xmm3, [rsp+68h+var_18]
0x180002452  mov     rcx, [rsp+68h+arg_0]
0x180002457  mov     rdx, [rsp+68h+arg_8]
0x18000245c  mov     r8, [rsp+68h+arg_10]
0x180002464  mov     r9, [rsp+68h+arg_18]
0x18000246c  add     rsp, 68h
0x180002470  jmp     short $+2
0x180002472  jmp     rax
```
