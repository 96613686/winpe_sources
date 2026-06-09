# __tailMerge_api_ms_win_core_localization_l1_2_0_dll

- ea: `0x14001a736`
- end: `0x14001a7af`
- name: `__tailMerge_api_ms_win_core_localization_l1_2_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14001a7b5`

## callees

- `0x14001a736`
- `0x14001a890`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_core_localization_l1_2_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_localization_l1_2_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x14001a736  mov     [rsp+arg_0], rcx
0x14001a73b  mov     [rsp+arg_8], rdx
0x14001a740  mov     [rsp+arg_10], r8
0x14001a745  mov     [rsp+arg_18], r9
0x14001a74a  sub     rsp, 68h
0x14001a74e  movdqa  [rsp+68h+var_48], xmm0
0x14001a754  movdqa  [rsp+68h+var_38], xmm1
0x14001a75a  movdqa  [rsp+68h+var_28], xmm2
0x14001a760  movdqa  [rsp+68h+var_18], xmm3
0x14001a766  mov     rdx, rax
0x14001a769  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_localization_l1_2_0_dll
0x14001a770  call    __delayLoadHelper2
0x14001a775  movdqa  xmm0, [rsp+68h+var_48]
0x14001a77b  movdqa  xmm1, [rsp+68h+var_38]
0x14001a781  movdqa  xmm2, [rsp+68h+var_28]
0x14001a787  movdqa  xmm3, [rsp+68h+var_18]
0x14001a78d  mov     rcx, [rsp+68h+arg_0]
0x14001a792  mov     rdx, [rsp+68h+arg_8]
0x14001a797  mov     r8, [rsp+68h+arg_10]
0x14001a79f  mov     r9, [rsp+68h+arg_18]
0x14001a7a7  add     rsp, 68h
0x14001a7ab  jmp     short $+2
0x14001a7ad  jmp     rax
```
