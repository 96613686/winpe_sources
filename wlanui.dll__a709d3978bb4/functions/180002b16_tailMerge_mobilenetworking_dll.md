# __tailMerge_mobilenetworking_dll

- ea: `0x180002b16`
- end: `0x180002b8f`
- name: `__tailMerge_mobilenetworking_dll`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002b95`
- `0x180002ba7`
- `0x180002bb9`

## callees

- `0x180002b16`
- `0x18001be40`

## pseudocode

```c
__int64 __fastcall _tailMerge_mobilenetworking_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_mobilenetworking_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002b16  mov     [rsp+arg_0], rcx
0x180002b1b  mov     [rsp+arg_8], rdx
0x180002b20  mov     [rsp+arg_10], r8
0x180002b25  mov     [rsp+arg_18], r9
0x180002b2a  sub     rsp, 68h
0x180002b2e  movdqa  [rsp+68h+var_48], xmm0
0x180002b34  movdqa  [rsp+68h+var_38], xmm1
0x180002b3a  movdqa  [rsp+68h+var_28], xmm2
0x180002b40  movdqa  [rsp+68h+var_18], xmm3
0x180002b46  mov     rdx, rax
0x180002b49  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_mobilenetworking_dll
0x180002b50  call    __delayLoadHelper2
0x180002b55  movdqa  xmm0, [rsp+68h+var_48]
0x180002b5b  movdqa  xmm1, [rsp+68h+var_38]
0x180002b61  movdqa  xmm2, [rsp+68h+var_28]
0x180002b67  movdqa  xmm3, [rsp+68h+var_18]
0x180002b6d  mov     rcx, [rsp+68h+arg_0]
0x180002b72  mov     rdx, [rsp+68h+arg_8]
0x180002b77  mov     r8, [rsp+68h+arg_10]
0x180002b7f  mov     r9, [rsp+68h+arg_18]
0x180002b87  add     rsp, 68h
0x180002b8b  jmp     short $+2
0x180002b8d  jmp     rax
```
