# __tailMerge_bcrypt_dll

- ea: `0x180006704`
- end: `0x18000677d`
- name: `__tailMerge_bcrypt_dll`
- size: `121`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180006783`
- `0x180006795`
- `0x1800067a7`
- `0x1800067b9`
- `0x1800067cb`
- `0x1800067dd`
- `0x1800067ef`

## callees

- `0x180006704`
- `0x180016780`

## pseudocode

```c
__int64 __fastcall _tailMerge_bcrypt_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_bcrypt_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180006704  mov     [rsp+arg_0], rcx
0x180006709  mov     [rsp+arg_8], rdx
0x18000670e  mov     [rsp+arg_10], r8
0x180006713  mov     [rsp+arg_18], r9
0x180006718  sub     rsp, 68h
0x18000671c  movdqa  [rsp+68h+var_48], xmm0
0x180006722  movdqa  [rsp+68h+var_38], xmm1
0x180006728  movdqa  [rsp+68h+var_28], xmm2
0x18000672e  movdqa  [rsp+68h+var_18], xmm3
0x180006734  mov     rdx, rax
0x180006737  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_bcrypt_dll
0x18000673e  call    __delayLoadHelper2
0x180006743  movdqa  xmm0, [rsp+68h+var_48]
0x180006749  movdqa  xmm1, [rsp+68h+var_38]
0x18000674f  movdqa  xmm2, [rsp+68h+var_28]
0x180006755  movdqa  xmm3, [rsp+68h+var_18]
0x18000675b  mov     rcx, [rsp+68h+arg_0]
0x180006760  mov     rdx, [rsp+68h+arg_8]
0x180006765  mov     r8, [rsp+68h+arg_10]
0x18000676d  mov     r9, [rsp+68h+arg_18]
0x180006775  add     rsp, 68h
0x180006779  jmp     short $+2
0x18000677b  jmp     rax
```
