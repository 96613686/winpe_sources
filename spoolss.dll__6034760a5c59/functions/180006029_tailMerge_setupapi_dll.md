# __tailMerge_setupapi_dll

- ea: `0x180006029`
- end: `0x1800060a2`
- name: `__tailMerge_setupapi_dll`
- size: `121`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x1800060a8`
- `0x1800060ba`
- `0x1800060cc`
- `0x1800060de`
- `0x1800060f0`

## callees

- `0x180006029`
- `0x180014d80`

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
0x180006029  mov     [rsp+arg_0], rcx
0x18000602e  mov     [rsp+arg_8], rdx
0x180006033  mov     [rsp+arg_10], r8
0x180006038  mov     [rsp+arg_18], r9
0x18000603d  sub     rsp, 68h
0x180006041  movdqa  [rsp+68h+var_48], xmm0
0x180006047  movdqa  [rsp+68h+var_38], xmm1
0x18000604d  movdqa  [rsp+68h+var_28], xmm2
0x180006053  movdqa  [rsp+68h+var_18], xmm3
0x180006059  mov     rdx, rax
0x18000605c  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_setupapi_dll
0x180006063  call    __delayLoadHelper2
0x180006068  movdqa  xmm0, [rsp+68h+var_48]
0x18000606e  movdqa  xmm1, [rsp+68h+var_38]
0x180006074  movdqa  xmm2, [rsp+68h+var_28]
0x18000607a  movdqa  xmm3, [rsp+68h+var_18]
0x180006080  mov     rcx, [rsp+68h+arg_0]
0x180006085  mov     rdx, [rsp+68h+arg_8]
0x18000608a  mov     r8, [rsp+68h+arg_10]
0x180006092  mov     r9, [rsp+68h+arg_18]
0x18000609a  add     rsp, 68h
0x18000609e  jmp     short $+2
0x1800060a0  jmp     rax
```
