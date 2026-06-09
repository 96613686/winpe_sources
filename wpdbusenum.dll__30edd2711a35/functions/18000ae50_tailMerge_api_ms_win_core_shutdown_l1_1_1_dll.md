# __tailMerge_api_ms_win_core_shutdown_l1_1_1_dll

- ea: `0x18000ae50`
- end: `0x18000aec9`
- name: `__tailMerge_api_ms_win_core_shutdown_l1_1_1_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000aecf`

## callees

- `0x180006050`
- `0x18000ae50`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_core_shutdown_l1_1_1_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_shutdown_l1_1_1_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000ae50  mov     [rsp+arg_0], rcx
0x18000ae55  mov     [rsp+arg_8], rdx
0x18000ae5a  mov     [rsp+arg_10], r8
0x18000ae5f  mov     [rsp+arg_18], r9
0x18000ae64  sub     rsp, 68h
0x18000ae68  movdqa  [rsp+68h+var_48], xmm0
0x18000ae6e  movdqa  [rsp+68h+var_38], xmm1
0x18000ae74  movdqa  [rsp+68h+var_28], xmm2
0x18000ae7a  movdqa  [rsp+68h+var_18], xmm3
0x18000ae80  mov     rdx, rax
0x18000ae83  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_shutdown_l1_1_1_dll
0x18000ae8a  call    __delayLoadHelper2
0x18000ae8f  movdqa  xmm0, [rsp+68h+var_48]
0x18000ae95  movdqa  xmm1, [rsp+68h+var_38]
0x18000ae9b  movdqa  xmm2, [rsp+68h+var_28]
0x18000aea1  movdqa  xmm3, [rsp+68h+var_18]
0x18000aea7  mov     rcx, [rsp+68h+arg_0]
0x18000aeac  mov     rdx, [rsp+68h+arg_8]
0x18000aeb1  mov     r8, [rsp+68h+arg_10]
0x18000aeb9  mov     r9, [rsp+68h+arg_18]
0x18000aec1  add     rsp, 68h
0x18000aec5  jmp     short $+2
0x18000aec7  jmp     rax
```
