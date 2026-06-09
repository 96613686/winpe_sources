# __tailMerge_dnsapi_dll

- ea: `0x18001348a`
- end: `0x180013503`
- name: `__tailMerge_dnsapi_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180013509`

## callees

- `0x18001348a`
- `0x1800376a0`

## pseudocode

```c
__int64 __fastcall _tailMerge_dnsapi_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_dnsapi_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18001348a  mov     [rsp+arg_0], rcx
0x18001348f  mov     [rsp+arg_8], rdx
0x180013494  mov     [rsp+arg_10], r8
0x180013499  mov     [rsp+arg_18], r9
0x18001349e  sub     rsp, 68h
0x1800134a2  movdqa  [rsp+68h+var_48], xmm0
0x1800134a8  movdqa  [rsp+68h+var_38], xmm1
0x1800134ae  movdqa  [rsp+68h+var_28], xmm2
0x1800134b4  movdqa  [rsp+68h+var_18], xmm3
0x1800134ba  mov     rdx, rax
0x1800134bd  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_dnsapi_dll
0x1800134c4  call    __delayLoadHelper2
0x1800134c9  movdqa  xmm0, [rsp+68h+var_48]
0x1800134cf  movdqa  xmm1, [rsp+68h+var_38]
0x1800134d5  movdqa  xmm2, [rsp+68h+var_28]
0x1800134db  movdqa  xmm3, [rsp+68h+var_18]
0x1800134e1  mov     rcx, [rsp+68h+arg_0]
0x1800134e6  mov     rdx, [rsp+68h+arg_8]
0x1800134eb  mov     r8, [rsp+68h+arg_10]
0x1800134f3  mov     r9, [rsp+68h+arg_18]
0x1800134fb  add     rsp, 68h
0x1800134ff  jmp     short $+2
0x180013501  jmp     rax
```
