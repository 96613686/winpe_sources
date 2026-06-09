# __tailMerge_netutils_dll

- ea: `0x180002761`
- end: `0x1800027da`
- name: `__tailMerge_netutils_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800027e0`

## callees

- `0x180002761`
- `0x18001d240`

## pseudocode

```c
__int64 __fastcall _tailMerge_netutils_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_netutils_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002761  mov     [rsp+arg_0], rcx
0x180002766  mov     [rsp+arg_8], rdx
0x18000276b  mov     [rsp+arg_10], r8
0x180002770  mov     [rsp+arg_18], r9
0x180002775  sub     rsp, 68h
0x180002779  movdqa  [rsp+68h+var_48], xmm0
0x18000277f  movdqa  [rsp+68h+var_38], xmm1
0x180002785  movdqa  [rsp+68h+var_28], xmm2
0x18000278b  movdqa  [rsp+68h+var_18], xmm3
0x180002791  mov     rdx, rax
0x180002794  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_netutils_dll
0x18000279b  call    __delayLoadHelper2
0x1800027a0  movdqa  xmm0, [rsp+68h+var_48]
0x1800027a6  movdqa  xmm1, [rsp+68h+var_38]
0x1800027ac  movdqa  xmm2, [rsp+68h+var_28]
0x1800027b2  movdqa  xmm3, [rsp+68h+var_18]
0x1800027b8  mov     rcx, [rsp+68h+arg_0]
0x1800027bd  mov     rdx, [rsp+68h+arg_8]
0x1800027c2  mov     r8, [rsp+68h+arg_10]
0x1800027ca  mov     r9, [rsp+68h+arg_18]
0x1800027d2  add     rsp, 68h
0x1800027d6  jmp     short $+2
0x1800027d8  jmp     rax
```
