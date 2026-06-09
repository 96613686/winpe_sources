# __tailMerge_ole32_dll

- ea: `0x140002010`
- end: `0x140002089`
- name: `__tailMerge_ole32_dll`
- size: `121`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14000208f`
- `0x1400020a1`
- `0x1400020b3`
- `0x1400020c5`
- `0x1400020d7`
- `0x1400020e9`

## callees

- `0x140002010`
- `0x140007430`

## pseudocode

```c
__int64 __fastcall _tailMerge_ole32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ole32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x140002010  mov     [rsp+arg_0], rcx
0x140002015  mov     [rsp+arg_8], rdx
0x14000201a  mov     [rsp+arg_10], r8
0x14000201f  mov     [rsp+arg_18], r9
0x140002024  sub     rsp, 68h
0x140002028  movdqa  [rsp+68h+var_48], xmm0
0x14000202e  movdqa  [rsp+68h+var_38], xmm1
0x140002034  movdqa  [rsp+68h+var_28], xmm2
0x14000203a  movdqa  [rsp+68h+var_18], xmm3
0x140002040  mov     rdx, rax
0x140002043  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ole32_dll
0x14000204a  call    __delayLoadHelper2
0x14000204f  movdqa  xmm0, [rsp+68h+var_48]
0x140002055  movdqa  xmm1, [rsp+68h+var_38]
0x14000205b  movdqa  xmm2, [rsp+68h+var_28]
0x140002061  movdqa  xmm3, [rsp+68h+var_18]
0x140002067  mov     rcx, [rsp+68h+arg_0]
0x14000206c  mov     rdx, [rsp+68h+arg_8]
0x140002071  mov     r8, [rsp+68h+arg_10]
0x140002079  mov     r9, [rsp+68h+arg_18]
0x140002081  add     rsp, 68h
0x140002085  jmp     short $+2
0x140002087  jmp     rax
```
