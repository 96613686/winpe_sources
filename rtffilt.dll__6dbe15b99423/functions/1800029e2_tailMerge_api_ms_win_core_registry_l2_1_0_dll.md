# __tailMerge_api_ms_win_core_registry_l2_1_0_dll

- ea: `0x1800029e2`
- end: `0x180002a5b`
- name: `__tailMerge_api_ms_win_core_registry_l2_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180002a61`

## callees

- `0x1800029e2`
- `0x180019710`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_core_registry_l2_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_registry_l2_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800029e2  mov     [rsp+arg_0], rcx
0x1800029e7  mov     [rsp+arg_8], rdx
0x1800029ec  mov     [rsp+arg_10], r8
0x1800029f1  mov     [rsp+arg_18], r9
0x1800029f6  sub     rsp, 68h
0x1800029fa  movdqa  [rsp+68h+var_48], xmm0
0x180002a00  movdqa  [rsp+68h+var_38], xmm1
0x180002a06  movdqa  [rsp+68h+var_28], xmm2
0x180002a0c  movdqa  [rsp+68h+var_18], xmm3
0x180002a12  mov     rdx, rax
0x180002a15  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_registry_l2_1_0_dll
0x180002a1c  call    __delayLoadHelper2
0x180002a21  movdqa  xmm0, [rsp+68h+var_48]
0x180002a27  movdqa  xmm1, [rsp+68h+var_38]
0x180002a2d  movdqa  xmm2, [rsp+68h+var_28]
0x180002a33  movdqa  xmm3, [rsp+68h+var_18]
0x180002a39  mov     rcx, [rsp+68h+arg_0]
0x180002a3e  mov     rdx, [rsp+68h+arg_8]
0x180002a43  mov     r8, [rsp+68h+arg_10]
0x180002a4b  mov     r9, [rsp+68h+arg_18]
0x180002a53  add     rsp, 68h
0x180002a57  jmp     short $+2
0x180002a59  jmp     rax
```
