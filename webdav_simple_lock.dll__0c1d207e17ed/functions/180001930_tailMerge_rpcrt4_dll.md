# __tailMerge_rpcrt4_dll

- ea: `0x180001930`
- end: `0x1800019a9`
- name: `__tailMerge_rpcrt4_dll`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800019af`
- `0x1800019c1`
- `0x1800019d3`

## callees

- `0x180001930`
- `0x180003b30`

## pseudocode

```c
__int64 __fastcall _tailMerge_rpcrt4_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_rpcrt4_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180001930  mov     [rsp+arg_0], rcx
0x180001935  mov     [rsp+arg_8], rdx
0x18000193a  mov     [rsp+arg_10], r8
0x18000193f  mov     [rsp+arg_18], r9
0x180001944  sub     rsp, 68h
0x180001948  movdqa  [rsp+68h+var_48], xmm0
0x18000194e  movdqa  [rsp+68h+var_38], xmm1
0x180001954  movdqa  [rsp+68h+var_28], xmm2
0x18000195a  movdqa  [rsp+68h+var_18], xmm3
0x180001960  mov     rdx, rax
0x180001963  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_rpcrt4_dll
0x18000196a  call    __delayLoadHelper2
0x18000196f  movdqa  xmm0, [rsp+68h+var_48]
0x180001975  movdqa  xmm1, [rsp+68h+var_38]
0x18000197b  movdqa  xmm2, [rsp+68h+var_28]
0x180001981  movdqa  xmm3, [rsp+68h+var_18]
0x180001987  mov     rcx, [rsp+68h+arg_0]
0x18000198c  mov     rdx, [rsp+68h+arg_8]
0x180001991  mov     r8, [rsp+68h+arg_10]
0x180001999  mov     r9, [rsp+68h+arg_18]
0x1800019a1  add     rsp, 68h
0x1800019a5  jmp     short $+2
0x1800019a7  jmp     rax
```
