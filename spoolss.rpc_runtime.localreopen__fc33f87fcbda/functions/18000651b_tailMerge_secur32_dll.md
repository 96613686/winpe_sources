# __tailMerge_secur32_dll

- ea: `0x18000651b`
- end: `0x180006594`
- name: `__tailMerge_secur32_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000659a`

## callees

- `0x18000651b`
- `0x180016780`

## pseudocode

```c
__int64 __fastcall _tailMerge_secur32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_secur32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000651b  mov     [rsp+arg_0], rcx
0x180006520  mov     [rsp+arg_8], rdx
0x180006525  mov     [rsp+arg_10], r8
0x18000652a  mov     [rsp+arg_18], r9
0x18000652f  sub     rsp, 68h
0x180006533  movdqa  [rsp+68h+var_48], xmm0
0x180006539  movdqa  [rsp+68h+var_38], xmm1
0x18000653f  movdqa  [rsp+68h+var_28], xmm2
0x180006545  movdqa  [rsp+68h+var_18], xmm3
0x18000654b  mov     rdx, rax
0x18000654e  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_secur32_dll
0x180006555  call    __delayLoadHelper2
0x18000655a  movdqa  xmm0, [rsp+68h+var_48]
0x180006560  movdqa  xmm1, [rsp+68h+var_38]
0x180006566  movdqa  xmm2, [rsp+68h+var_28]
0x18000656c  movdqa  xmm3, [rsp+68h+var_18]
0x180006572  mov     rcx, [rsp+68h+arg_0]
0x180006577  mov     rdx, [rsp+68h+arg_8]
0x18000657c  mov     r8, [rsp+68h+arg_10]
0x180006584  mov     r9, [rsp+68h+arg_18]
0x18000658c  add     rsp, 68h
0x180006590  jmp     short $+2
0x180006592  jmp     rax
```
