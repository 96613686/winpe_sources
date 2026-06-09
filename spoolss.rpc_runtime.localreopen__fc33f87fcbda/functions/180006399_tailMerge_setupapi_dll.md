# __tailMerge_setupapi_dll

- ea: `0x180006399`
- end: `0x180006412`
- name: `__tailMerge_setupapi_dll`
- size: `121`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x180006418`
- `0x18000642a`
- `0x18000643c`
- `0x18000644e`
- `0x180006460`

## callees

- `0x180006399`
- `0x180016780`

## pseudocode

```c
__int64 __fastcall _tailMerge_setupapi_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_setupapi_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180006399  mov     [rsp+arg_0], rcx
0x18000639e  mov     [rsp+arg_8], rdx
0x1800063a3  mov     [rsp+arg_10], r8
0x1800063a8  mov     [rsp+arg_18], r9
0x1800063ad  sub     rsp, 68h
0x1800063b1  movdqa  [rsp+68h+var_48], xmm0
0x1800063b7  movdqa  [rsp+68h+var_38], xmm1
0x1800063bd  movdqa  [rsp+68h+var_28], xmm2
0x1800063c3  movdqa  [rsp+68h+var_18], xmm3
0x1800063c9  mov     rdx, rax
0x1800063cc  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_setupapi_dll
0x1800063d3  call    __delayLoadHelper2
0x1800063d8  movdqa  xmm0, [rsp+68h+var_48]
0x1800063de  movdqa  xmm1, [rsp+68h+var_38]
0x1800063e4  movdqa  xmm2, [rsp+68h+var_28]
0x1800063ea  movdqa  xmm3, [rsp+68h+var_18]
0x1800063f0  mov     rcx, [rsp+68h+arg_0]
0x1800063f5  mov     rdx, [rsp+68h+arg_8]
0x1800063fa  mov     r8, [rsp+68h+arg_10]
0x180006402  mov     r9, [rsp+68h+arg_18]
0x18000640a  add     rsp, 68h
0x18000640e  jmp     short $+2
0x180006410  jmp     rax
```
