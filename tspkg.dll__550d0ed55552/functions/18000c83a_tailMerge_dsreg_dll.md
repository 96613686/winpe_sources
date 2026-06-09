# __tailMerge_dsreg_dll

- ea: `0x18000c83a`
- end: `0x18000c8b3`
- name: `__tailMerge_dsreg_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000c8b9`

## callees

- `0x180009770`
- `0x18000c83a`

## pseudocode

```c
__int64 __fastcall _tailMerge_dsreg_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_dsreg_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000c83a  mov     [rsp+arg_0], rcx
0x18000c83f  mov     [rsp+arg_8], rdx
0x18000c844  mov     [rsp+arg_10], r8
0x18000c849  mov     [rsp+arg_18], r9
0x18000c84e  sub     rsp, 68h
0x18000c852  movdqa  [rsp+68h+var_48], xmm0
0x18000c858  movdqa  [rsp+68h+var_38], xmm1
0x18000c85e  movdqa  [rsp+68h+var_28], xmm2
0x18000c864  movdqa  [rsp+68h+var_18], xmm3
0x18000c86a  mov     rdx, rax
0x18000c86d  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_dsreg_dll
0x18000c874  call    __delayLoadHelper2
0x18000c879  movdqa  xmm0, [rsp+68h+var_48]
0x18000c87f  movdqa  xmm1, [rsp+68h+var_38]
0x18000c885  movdqa  xmm2, [rsp+68h+var_28]
0x18000c88b  movdqa  xmm3, [rsp+68h+var_18]
0x18000c891  mov     rcx, [rsp+68h+arg_0]
0x18000c896  mov     rdx, [rsp+68h+arg_8]
0x18000c89b  mov     r8, [rsp+68h+arg_10]
0x18000c8a3  mov     r9, [rsp+68h+arg_18]
0x18000c8ab  add     rsp, 68h
0x18000c8af  jmp     short $+2
0x18000c8b1  jmp     rax
```
