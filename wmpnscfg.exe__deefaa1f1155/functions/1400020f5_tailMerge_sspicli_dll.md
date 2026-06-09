# __tailMerge_sspicli_dll

- ea: `0x1400020f5`
- end: `0x14000216e`
- name: `__tailMerge_sspicli_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140002174`

## callees

- `0x1400020f5`
- `0x140007430`

## pseudocode

```c
__int64 __fastcall _tailMerge_sspicli_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_sspicli_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1400020f5  mov     [rsp+arg_0], rcx
0x1400020fa  mov     [rsp+arg_8], rdx
0x1400020ff  mov     [rsp+arg_10], r8
0x140002104  mov     [rsp+arg_18], r9
0x140002109  sub     rsp, 68h
0x14000210d  movdqa  [rsp+68h+var_48], xmm0
0x140002113  movdqa  [rsp+68h+var_38], xmm1
0x140002119  movdqa  [rsp+68h+var_28], xmm2
0x14000211f  movdqa  [rsp+68h+var_18], xmm3
0x140002125  mov     rdx, rax
0x140002128  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_sspicli_dll
0x14000212f  call    __delayLoadHelper2
0x140002134  movdqa  xmm0, [rsp+68h+var_48]
0x14000213a  movdqa  xmm1, [rsp+68h+var_38]
0x140002140  movdqa  xmm2, [rsp+68h+var_28]
0x140002146  movdqa  xmm3, [rsp+68h+var_18]
0x14000214c  mov     rcx, [rsp+68h+arg_0]
0x140002151  mov     rdx, [rsp+68h+arg_8]
0x140002156  mov     r8, [rsp+68h+arg_10]
0x14000215e  mov     r9, [rsp+68h+arg_18]
0x140002166  add     rsp, 68h
0x14000216a  jmp     short $+2
0x14000216c  jmp     rax
```
