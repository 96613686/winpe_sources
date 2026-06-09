# __tailMerge_api_ms_win_core_file_l2_1_0_dll

- ea: `0x180015029`
- end: `0x1800150a2`
- name: `__tailMerge_api_ms_win_core_file_l2_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800150a8`

## callees

- `0x180014c80`
- `0x180015029`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_core_file_l2_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  FARPROC *v4; // rax
  FARPROC Helper2; // rax

  Helper2 = _delayLoadHelper2((const ImgDelayDescr *)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_file_l2_1_0_dll, v4);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64))Helper2)(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180015029  mov     [rsp+arg_0], rcx
0x18001502e  mov     [rsp+arg_8], rdx
0x180015033  mov     [rsp+arg_10], r8
0x180015038  mov     [rsp+arg_18], r9
0x18001503d  sub     rsp, 68h
0x180015041  movdqa  [rsp+68h+var_48], xmm0
0x180015047  movdqa  [rsp+68h+var_38], xmm1
0x18001504d  movdqa  [rsp+68h+var_28], xmm2
0x180015053  movdqa  [rsp+68h+var_18], xmm3
0x180015059  mov     rdx, rax
0x18001505c  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_file_l2_1_0_dll
0x180015063  call    __delayLoadHelper2
0x180015068  movdqa  xmm0, [rsp+68h+var_48]
0x18001506e  movdqa  xmm1, [rsp+68h+var_38]
0x180015074  movdqa  xmm2, [rsp+68h+var_28]
0x18001507a  movdqa  xmm3, [rsp+68h+var_18]
0x180015080  mov     rcx, [rsp+68h+arg_0]
0x180015085  mov     rdx, [rsp+68h+arg_8]
0x18001508a  mov     r8, [rsp+68h+arg_10]
0x180015092  mov     r9, [rsp+68h+arg_18]
0x18001509a  add     rsp, 68h
0x18001509e  jmp     short $+2
0x1800150a0  jmp     rax
```
