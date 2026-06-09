# __tailMerge_api_ms_win_service_management_l1_1_0_dll

- ea: `0x18000f3e7`
- end: `0x18000f460`
- name: `__tailMerge_api_ms_win_service_management_l1_1_0_dll`
- size: `121`
- prototype: `__int64(void)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x18000f466`
- `0x18000f478`
- `0x18000f539`
- `0x18000f56f`

## callees

- `0x18000a5e0`
- `0x18000f3e7`

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
0x18000f3e7  mov     [rsp+arg_0], rcx
0x18000f3ec  mov     [rsp+arg_8], rdx
0x18000f3f1  mov     [rsp+arg_10], r8
0x18000f3f6  mov     [rsp+arg_18], r9
0x18000f3fb  sub     rsp, 68h
0x18000f3ff  movdqa  [rsp+68h+var_48], xmm0
0x18000f405  movdqa  [rsp+68h+var_38], xmm1
0x18000f40b  movdqa  [rsp+68h+var_28], xmm2
0x18000f411  movdqa  [rsp+68h+var_18], xmm3
0x18000f417  mov     rdx, rax
0x18000f41a  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_service_management_l1_1_0_dll
0x18000f421  call    __delayLoadHelper2
0x18000f426  movdqa  xmm0, [rsp+68h+var_48]
0x18000f42c  movdqa  xmm1, [rsp+68h+var_38]
0x18000f432  movdqa  xmm2, [rsp+68h+var_28]
0x18000f438  movdqa  xmm3, [rsp+68h+var_18]
0x18000f43e  mov     rcx, [rsp+68h+arg_0]
0x18000f443  mov     rdx, [rsp+68h+arg_8]
0x18000f448  mov     r8, [rsp+68h+arg_10]
0x18000f450  mov     r9, [rsp+68h+arg_18]
0x18000f458  add     rsp, 68h
0x18000f45c  jmp     short $+2
0x18000f45e  jmp     rax
```
