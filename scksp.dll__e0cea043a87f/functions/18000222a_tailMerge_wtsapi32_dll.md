# __tailMerge_wtsapi32_dll

- ea: `0x18000222a`
- end: `0x1800022a3`
- name: `__tailMerge_wtsapi32_dll`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800022a9`
- `0x1800022bb`

## callees

- `0x18000222a`
- `0x18003c140`

## pseudocode

```c
__int64 __fastcall _tailMerge_wtsapi32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_wtsapi32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000222a  mov     [rsp+arg_0], rcx
0x18000222f  mov     [rsp+arg_8], rdx
0x180002234  mov     [rsp+arg_10], r8
0x180002239  mov     [rsp+arg_18], r9
0x18000223e  sub     rsp, 68h
0x180002242  movdqa  [rsp+68h+var_48], xmm0
0x180002248  movdqa  [rsp+68h+var_38], xmm1
0x18000224e  movdqa  [rsp+68h+var_28], xmm2
0x180002254  movdqa  [rsp+68h+var_18], xmm3
0x18000225a  mov     rdx, rax
0x18000225d  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_wtsapi32_dll
0x180002264  call    __delayLoadHelper2
0x180002269  movdqa  xmm0, [rsp+68h+var_48]
0x18000226f  movdqa  xmm1, [rsp+68h+var_38]
0x180002275  movdqa  xmm2, [rsp+68h+var_28]
0x18000227b  movdqa  xmm3, [rsp+68h+var_18]
0x180002281  mov     rcx, [rsp+68h+arg_0]
0x180002286  mov     rdx, [rsp+68h+arg_8]
0x18000228b  mov     r8, [rsp+68h+arg_10]
0x180002293  mov     r9, [rsp+68h+arg_18]
0x18000229b  add     rsp, 68h
0x18000229f  jmp     short $+2
0x1800022a1  jmp     rax
```
