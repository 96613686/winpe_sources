# __tailMerge_api_ms_win_service_winsvc_l1_1_0_dll

- ea: `0x140005a0a`
- end: `0x140005a83`
- name: `__tailMerge_api_ms_win_service_winsvc_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x140005a89`

## callees

- `0x140002100`
- `0x140005a0a`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_service_winsvc_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_service_winsvc_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x140005a0a  mov     [rsp+arg_0], rcx
0x140005a0f  mov     [rsp+arg_8], rdx
0x140005a14  mov     [rsp+arg_10], r8
0x140005a19  mov     [rsp+arg_18], r9
0x140005a1e  sub     rsp, 68h
0x140005a22  movdqa  [rsp+68h+var_48], xmm0
0x140005a28  movdqa  [rsp+68h+var_38], xmm1
0x140005a2e  movdqa  [rsp+68h+var_28], xmm2
0x140005a34  movdqa  [rsp+68h+var_18], xmm3
0x140005a3a  mov     rdx, rax
0x140005a3d  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_service_winsvc_l1_1_0_dll
0x140005a44  call    __delayLoadHelper2
0x140005a49  movdqa  xmm0, [rsp+68h+var_48]
0x140005a4f  movdqa  xmm1, [rsp+68h+var_38]
0x140005a55  movdqa  xmm2, [rsp+68h+var_28]
0x140005a5b  movdqa  xmm3, [rsp+68h+var_18]
0x140005a61  mov     rcx, [rsp+68h+arg_0]
0x140005a66  mov     rdx, [rsp+68h+arg_8]
0x140005a6b  mov     r8, [rsp+68h+arg_10]
0x140005a73  mov     r9, [rsp+68h+arg_18]
0x140005a7b  add     rsp, 68h
0x140005a7f  jmp     short $+2
0x140005a81  jmp     rax
```
