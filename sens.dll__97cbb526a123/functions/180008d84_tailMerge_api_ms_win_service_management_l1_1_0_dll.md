# __tailMerge_api_ms_win_service_management_l1_1_0_dll

- ea: `0x180008d84`
- end: `0x180008dfd`
- name: `__tailMerge_api_ms_win_service_management_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x180008e03`
- `0x180008fec`
- `0x180008ffe`

## callees

- `0x180006a50`
- `0x180008d84`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_service_management_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_service_management_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180008d84  mov     [rsp+arg_0], rcx
0x180008d89  mov     [rsp+arg_8], rdx
0x180008d8e  mov     [rsp+arg_10], r8
0x180008d93  mov     [rsp+arg_18], r9
0x180008d98  sub     rsp, 68h
0x180008d9c  movdqa  [rsp+68h+var_48], xmm0
0x180008da2  movdqa  [rsp+68h+var_38], xmm1
0x180008da8  movdqa  [rsp+68h+var_28], xmm2
0x180008dae  movdqa  [rsp+68h+var_18], xmm3
0x180008db4  mov     rdx, rax
0x180008db7  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_service_management_l1_1_0_dll
0x180008dbe  call    __delayLoadHelper2
0x180008dc3  movdqa  xmm0, [rsp+68h+var_48]
0x180008dc9  movdqa  xmm1, [rsp+68h+var_38]
0x180008dcf  movdqa  xmm2, [rsp+68h+var_28]
0x180008dd5  movdqa  xmm3, [rsp+68h+var_18]
0x180008ddb  mov     rcx, [rsp+68h+arg_0]
0x180008de0  mov     rdx, [rsp+68h+arg_8]
0x180008de5  mov     r8, [rsp+68h+arg_10]
0x180008ded  mov     r9, [rsp+68h+arg_18]
0x180008df5  add     rsp, 68h
0x180008df9  jmp     short $+2
0x180008dfb  jmp     rax
```
