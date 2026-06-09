# __tailMerge_winhttp_dll

- ea: `0x1800034d0`
- end: `0x180003549`
- name: `__tailMerge_winhttp_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000354f`

## callees

- `0x180001850`
- `0x1800034d0`

## pseudocode

```c
__int64 __fastcall _tailMerge_winhttp_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_winhttp_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800034d0  mov     [rsp+arg_0], rcx
0x1800034d5  mov     [rsp+arg_8], rdx
0x1800034da  mov     [rsp+arg_10], r8
0x1800034df  mov     [rsp+arg_18], r9
0x1800034e4  sub     rsp, 68h
0x1800034e8  movdqa  [rsp+68h+var_48], xmm0
0x1800034ee  movdqa  [rsp+68h+var_38], xmm1
0x1800034f4  movdqa  [rsp+68h+var_28], xmm2
0x1800034fa  movdqa  [rsp+68h+var_18], xmm3
0x180003500  mov     rdx, rax
0x180003503  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_winhttp_dll
0x18000350a  call    __delayLoadHelper2
0x18000350f  movdqa  xmm0, [rsp+68h+var_48]
0x180003515  movdqa  xmm1, [rsp+68h+var_38]
0x18000351b  movdqa  xmm2, [rsp+68h+var_28]
0x180003521  movdqa  xmm3, [rsp+68h+var_18]
0x180003527  mov     rcx, [rsp+68h+arg_0]
0x18000352c  mov     rdx, [rsp+68h+arg_8]
0x180003531  mov     r8, [rsp+68h+arg_10]
0x180003539  mov     r9, [rsp+68h+arg_18]
0x180003541  add     rsp, 68h
0x180003545  jmp     short $+2
0x180003547  jmp     rax
```
