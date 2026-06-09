# __tailMerge_api_ms_win_core_com_l1_1_0_dll

- ea: `0x18000194b`
- end: `0x1800019c4`
- name: `__tailMerge_api_ms_win_core_com_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800019ca`
- `0x1800019dc`
- `0x1800019ee`
- `0x180001a00`

## callees

- `0x18000194b`
- `0x1800035c0`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_core_com_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_com_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000194b  mov     [rsp+arg_0], rcx
0x180001950  mov     [rsp+arg_8], rdx
0x180001955  mov     [rsp+arg_10], r8
0x18000195a  mov     [rsp+arg_18], r9
0x18000195f  sub     rsp, 68h
0x180001963  movdqa  [rsp+68h+var_48], xmm0
0x180001969  movdqa  [rsp+68h+var_38], xmm1
0x18000196f  movdqa  [rsp+68h+var_28], xmm2
0x180001975  movdqa  [rsp+68h+var_18], xmm3
0x18000197b  mov     rdx, rax
0x18000197e  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_com_l1_1_0_dll
0x180001985  call    __delayLoadHelper2
0x18000198a  movdqa  xmm0, [rsp+68h+var_48]
0x180001990  movdqa  xmm1, [rsp+68h+var_38]
0x180001996  movdqa  xmm2, [rsp+68h+var_28]
0x18000199c  movdqa  xmm3, [rsp+68h+var_18]
0x1800019a2  mov     rcx, [rsp+68h+arg_0]
0x1800019a7  mov     rdx, [rsp+68h+arg_8]
0x1800019ac  mov     r8, [rsp+68h+arg_10]
0x1800019b4  mov     r9, [rsp+68h+arg_18]
0x1800019bc  add     rsp, 68h
0x1800019c0  jmp     short $+2
0x1800019c2  jmp     rax
```
