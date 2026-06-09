# __tailMerge_advapi32_dll

- ea: `0x18000221f`
- end: `0x180002298`
- name: `__tailMerge_advapi32_dll`
- size: `121`
- prototype: ``
- caller_count: `10`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000229e`
- `0x1800022b0`
- `0x1800022c2`
- `0x1800022d4`
- `0x1800022e6`
- `0x1800022f8`
- `0x18000230a`
- `0x18000231c`
- `0x18000232e`
- `0x180002340`

## callees

- `0x18000221f`
- `0x18001be40`

## pseudocode

```c
__int64 __fastcall _tailMerge_advapi32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_advapi32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000221f  mov     [rsp+arg_0], rcx
0x180002224  mov     [rsp+arg_8], rdx
0x180002229  mov     [rsp+arg_10], r8
0x18000222e  mov     [rsp+arg_18], r9
0x180002233  sub     rsp, 68h
0x180002237  movdqa  [rsp+68h+var_48], xmm0
0x18000223d  movdqa  [rsp+68h+var_38], xmm1
0x180002243  movdqa  [rsp+68h+var_28], xmm2
0x180002249  movdqa  [rsp+68h+var_18], xmm3
0x18000224f  mov     rdx, rax
0x180002252  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_advapi32_dll
0x180002259  call    __delayLoadHelper2
0x18000225e  movdqa  xmm0, [rsp+68h+var_48]
0x180002264  movdqa  xmm1, [rsp+68h+var_38]
0x18000226a  movdqa  xmm2, [rsp+68h+var_28]
0x180002270  movdqa  xmm3, [rsp+68h+var_18]
0x180002276  mov     rcx, [rsp+68h+arg_0]
0x18000227b  mov     rdx, [rsp+68h+arg_8]
0x180002280  mov     r8, [rsp+68h+arg_10]
0x180002288  mov     r9, [rsp+68h+arg_18]
0x180002290  add     rsp, 68h
0x180002294  jmp     short $+2
0x180002296  jmp     rax
```
