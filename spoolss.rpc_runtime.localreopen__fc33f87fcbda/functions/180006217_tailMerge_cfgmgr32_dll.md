# __tailMerge_cfgmgr32_dll

- ea: `0x180006217`
- end: `0x180006290`
- name: `__tailMerge_cfgmgr32_dll`
- size: `121`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180006296`
- `0x1800062a8`
- `0x1800062ba`
- `0x1800062cc`
- `0x1800062de`
- `0x1800065ac`

## callees

- `0x180006217`
- `0x180016780`

## pseudocode

```c
__int64 __fastcall _tailMerge_cfgmgr32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_cfgmgr32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180006217  mov     [rsp+arg_0], rcx
0x18000621c  mov     [rsp+arg_8], rdx
0x180006221  mov     [rsp+arg_10], r8
0x180006226  mov     [rsp+arg_18], r9
0x18000622b  sub     rsp, 68h
0x18000622f  movdqa  [rsp+68h+var_48], xmm0
0x180006235  movdqa  [rsp+68h+var_38], xmm1
0x18000623b  movdqa  [rsp+68h+var_28], xmm2
0x180006241  movdqa  [rsp+68h+var_18], xmm3
0x180006247  mov     rdx, rax
0x18000624a  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_cfgmgr32_dll
0x180006251  call    __delayLoadHelper2
0x180006256  movdqa  xmm0, [rsp+68h+var_48]
0x18000625c  movdqa  xmm1, [rsp+68h+var_38]
0x180006262  movdqa  xmm2, [rsp+68h+var_28]
0x180006268  movdqa  xmm3, [rsp+68h+var_18]
0x18000626e  mov     rcx, [rsp+68h+arg_0]
0x180006273  mov     rdx, [rsp+68h+arg_8]
0x180006278  mov     r8, [rsp+68h+arg_10]
0x180006280  mov     r9, [rsp+68h+arg_18]
0x180006288  add     rsp, 68h
0x18000628c  jmp     short $+2
0x18000628e  jmp     rax
```
