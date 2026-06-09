# __tailMerge_api_ms_win_service_core_l1_1_0_dll

- ea: `0x140005a95`
- end: `0x140005b0e`
- name: `__tailMerge_api_ms_win_service_core_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x140005b14`
- `0x140005c72`

## callees

- `0x140002100`
- `0x140005a95`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_service_core_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_service_core_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x140005a95  mov     [rsp+arg_0], rcx
0x140005a9a  mov     [rsp+arg_8], rdx
0x140005a9f  mov     [rsp+arg_10], r8
0x140005aa4  mov     [rsp+arg_18], r9
0x140005aa9  sub     rsp, 68h
0x140005aad  movdqa  [rsp+68h+var_48], xmm0
0x140005ab3  movdqa  [rsp+68h+var_38], xmm1
0x140005ab9  movdqa  [rsp+68h+var_28], xmm2
0x140005abf  movdqa  [rsp+68h+var_18], xmm3
0x140005ac5  mov     rdx, rax
0x140005ac8  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_service_core_l1_1_0_dll
0x140005acf  call    __delayLoadHelper2
0x140005ad4  movdqa  xmm0, [rsp+68h+var_48]
0x140005ada  movdqa  xmm1, [rsp+68h+var_38]
0x140005ae0  movdqa  xmm2, [rsp+68h+var_28]
0x140005ae6  movdqa  xmm3, [rsp+68h+var_18]
0x140005aec  mov     rcx, [rsp+68h+arg_0]
0x140005af1  mov     rdx, [rsp+68h+arg_8]
0x140005af6  mov     r8, [rsp+68h+arg_10]
0x140005afe  mov     r9, [rsp+68h+arg_18]
0x140005b06  add     rsp, 68h
0x140005b0a  jmp     short $+2
0x140005b0c  jmp     rax
```
