# __tailMerge_cryptsp_dll

- ea: `0x18000c56c`
- end: `0x18000c5e5`
- name: `__tailMerge_cryptsp_dll`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000c5eb`
- `0x18000c5fd`

## callees

- `0x180009770`
- `0x18000c56c`

## pseudocode

```c
__int64 __fastcall _tailMerge_cryptsp_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_cryptsp_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000c56c  mov     [rsp+arg_0], rcx
0x18000c571  mov     [rsp+arg_8], rdx
0x18000c576  mov     [rsp+arg_10], r8
0x18000c57b  mov     [rsp+arg_18], r9
0x18000c580  sub     rsp, 68h
0x18000c584  movdqa  [rsp+68h+var_48], xmm0
0x18000c58a  movdqa  [rsp+68h+var_38], xmm1
0x18000c590  movdqa  [rsp+68h+var_28], xmm2
0x18000c596  movdqa  [rsp+68h+var_18], xmm3
0x18000c59c  mov     rdx, rax
0x18000c59f  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_cryptsp_dll
0x18000c5a6  call    __delayLoadHelper2
0x18000c5ab  movdqa  xmm0, [rsp+68h+var_48]
0x18000c5b1  movdqa  xmm1, [rsp+68h+var_38]
0x18000c5b7  movdqa  xmm2, [rsp+68h+var_28]
0x18000c5bd  movdqa  xmm3, [rsp+68h+var_18]
0x18000c5c3  mov     rcx, [rsp+68h+arg_0]
0x18000c5c8  mov     rdx, [rsp+68h+arg_8]
0x18000c5cd  mov     r8, [rsp+68h+arg_10]
0x18000c5d5  mov     r9, [rsp+68h+arg_18]
0x18000c5dd  add     rsp, 68h
0x18000c5e1  jmp     short $+2
0x18000c5e3  jmp     rax
```
