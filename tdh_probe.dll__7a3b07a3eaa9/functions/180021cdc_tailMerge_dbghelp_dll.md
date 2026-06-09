# __tailMerge_dbghelp_dll

- ea: `0x180021cdc`
- end: `0x180021d55`
- name: `__tailMerge_dbghelp_dll`
- size: `121`
- prototype: ``
- caller_count: `12`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180021d5b`
- `0x180021d6d`
- `0x180021d7f`
- `0x180021d91`
- `0x180021da3`
- `0x180021db5`
- `0x180021dc7`
- `0x180021dd9`
- `0x180021deb`
- `0x180021dfd`
- `0x180021e0f`
- `0x180021e21`

## callees

- `0x180021cdc`
- `0x180049e40`

## pseudocode

```c
__int64 __fastcall _tailMerge_dbghelp_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_dbghelp_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180021cdc  mov     [rsp+arg_0], rcx
0x180021ce1  mov     [rsp+arg_8], rdx
0x180021ce6  mov     [rsp+arg_10], r8
0x180021ceb  mov     [rsp+arg_18], r9
0x180021cf0  sub     rsp, 68h
0x180021cf4  movdqa  [rsp+68h+var_48], xmm0
0x180021cfa  movdqa  [rsp+68h+var_38], xmm1
0x180021d00  movdqa  [rsp+68h+var_28], xmm2
0x180021d06  movdqa  [rsp+68h+var_18], xmm3
0x180021d0c  mov     rdx, rax
0x180021d0f  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_dbghelp_dll
0x180021d16  call    __delayLoadHelper2
0x180021d1b  movdqa  xmm0, [rsp+68h+var_48]
0x180021d21  movdqa  xmm1, [rsp+68h+var_38]
0x180021d27  movdqa  xmm2, [rsp+68h+var_28]
0x180021d2d  movdqa  xmm3, [rsp+68h+var_18]
0x180021d33  mov     rcx, [rsp+68h+arg_0]
0x180021d38  mov     rdx, [rsp+68h+arg_8]
0x180021d3d  mov     r8, [rsp+68h+arg_10]
0x180021d45  mov     r9, [rsp+68h+arg_18]
0x180021d4d  add     rsp, 68h
0x180021d51  jmp     short $+2
0x180021d53  jmp     rax
```
