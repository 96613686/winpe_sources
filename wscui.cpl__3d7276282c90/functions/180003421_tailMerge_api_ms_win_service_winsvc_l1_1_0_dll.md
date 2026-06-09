# __tailMerge_api_ms_win_service_winsvc_l1_1_0_dll

- ea: `0x180003421`
- end: `0x18000349a`
- name: `__tailMerge_api_ms_win_service_winsvc_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x1800034c4`

## callees

- `0x180001850`
- `0x180003421`

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
0x180003421  mov     [rsp+arg_0], rcx
0x180003426  mov     [rsp+arg_8], rdx
0x18000342b  mov     [rsp+arg_10], r8
0x180003430  mov     [rsp+arg_18], r9
0x180003435  sub     rsp, 68h
0x180003439  movdqa  [rsp+68h+var_48], xmm0
0x18000343f  movdqa  [rsp+68h+var_38], xmm1
0x180003445  movdqa  [rsp+68h+var_28], xmm2
0x18000344b  movdqa  [rsp+68h+var_18], xmm3
0x180003451  mov     rdx, rax
0x180003454  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_service_winsvc_l1_1_0_dll
0x18000345b  call    __delayLoadHelper2
0x180003460  movdqa  xmm0, [rsp+68h+var_48]
0x180003466  movdqa  xmm1, [rsp+68h+var_38]
0x18000346c  movdqa  xmm2, [rsp+68h+var_28]
0x180003472  movdqa  xmm3, [rsp+68h+var_18]
0x180003478  mov     rcx, [rsp+68h+arg_0]
0x18000347d  mov     rdx, [rsp+68h+arg_8]
0x180003482  mov     r8, [rsp+68h+arg_10]
0x18000348a  mov     r9, [rsp+68h+arg_18]
0x180003492  add     rsp, 68h
0x180003496  jmp     short $+2
0x180003498  jmp     rax
```
