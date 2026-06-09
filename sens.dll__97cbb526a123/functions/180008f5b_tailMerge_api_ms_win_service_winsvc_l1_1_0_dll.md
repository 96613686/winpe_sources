# __tailMerge_api_ms_win_service_winsvc_l1_1_0_dll

- ea: `0x180008f5b`
- end: `0x180008fd4`
- name: `__tailMerge_api_ms_win_service_winsvc_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x180008fda`

## callees

- `0x180006a50`
- `0x180008f5b`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_service_winsvc_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_service_winsvc_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180008f5b  mov     [rsp+arg_0], rcx
0x180008f60  mov     [rsp+arg_8], rdx
0x180008f65  mov     [rsp+arg_10], r8
0x180008f6a  mov     [rsp+arg_18], r9
0x180008f6f  sub     rsp, 68h
0x180008f73  movdqa  [rsp+68h+var_48], xmm0
0x180008f79  movdqa  [rsp+68h+var_38], xmm1
0x180008f7f  movdqa  [rsp+68h+var_28], xmm2
0x180008f85  movdqa  [rsp+68h+var_18], xmm3
0x180008f8b  mov     rdx, rax
0x180008f8e  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_service_winsvc_l1_1_0_dll
0x180008f95  call    __delayLoadHelper2
0x180008f9a  movdqa  xmm0, [rsp+68h+var_48]
0x180008fa0  movdqa  xmm1, [rsp+68h+var_38]
0x180008fa6  movdqa  xmm2, [rsp+68h+var_28]
0x180008fac  movdqa  xmm3, [rsp+68h+var_18]
0x180008fb2  mov     rcx, [rsp+68h+arg_0]
0x180008fb7  mov     rdx, [rsp+68h+arg_8]
0x180008fbc  mov     r8, [rsp+68h+arg_10]
0x180008fc4  mov     r9, [rsp+68h+arg_18]
0x180008fcc  add     rsp, 68h
0x180008fd0  jmp     short $+2
0x180008fd2  jmp     rax
```
