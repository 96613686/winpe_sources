# __tailMerge_browcli_dll

- ea: `0x1800078ea`
- end: `0x180007963`
- name: `__tailMerge_browcli_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180007969`

## callees

- `0x180004ab0`
- `0x1800078ea`

## pseudocode

```c
__int64 __fastcall _tailMerge_browcli_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_browcli_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800078ea  mov     [rsp+arg_0], rcx
0x1800078ef  mov     [rsp+arg_8], rdx
0x1800078f4  mov     [rsp+arg_10], r8
0x1800078f9  mov     [rsp+arg_18], r9
0x1800078fe  sub     rsp, 68h
0x180007902  movdqa  [rsp+68h+var_48], xmm0
0x180007908  movdqa  [rsp+68h+var_38], xmm1
0x18000790e  movdqa  [rsp+68h+var_28], xmm2
0x180007914  movdqa  [rsp+68h+var_18], xmm3
0x18000791a  mov     rdx, rax
0x18000791d  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_browcli_dll
0x180007924  call    __delayLoadHelper2
0x180007929  movdqa  xmm0, [rsp+68h+var_48]
0x18000792f  movdqa  xmm1, [rsp+68h+var_38]
0x180007935  movdqa  xmm2, [rsp+68h+var_28]
0x18000793b  movdqa  xmm3, [rsp+68h+var_18]
0x180007941  mov     rcx, [rsp+68h+arg_0]
0x180007946  mov     rdx, [rsp+68h+arg_8]
0x18000794b  mov     r8, [rsp+68h+arg_10]
0x180007953  mov     r9, [rsp+68h+arg_18]
0x18000795b  add     rsp, 68h
0x18000795f  jmp     short $+2
0x180007961  jmp     rax
```
