# __tailMerge_api_ms_win_devices_query_l1_1_0_dll

- ea: `0x1800062ea`
- end: `0x180006363`
- name: `__tailMerge_api_ms_win_devices_query_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180006369`
- `0x18000637b`
- `0x18000638d`

## callees

- `0x1800062ea`
- `0x180016780`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_devices_query_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_devices_query_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800062ea  mov     [rsp+arg_0], rcx
0x1800062ef  mov     [rsp+arg_8], rdx
0x1800062f4  mov     [rsp+arg_10], r8
0x1800062f9  mov     [rsp+arg_18], r9
0x1800062fe  sub     rsp, 68h
0x180006302  movdqa  [rsp+68h+var_48], xmm0
0x180006308  movdqa  [rsp+68h+var_38], xmm1
0x18000630e  movdqa  [rsp+68h+var_28], xmm2
0x180006314  movdqa  [rsp+68h+var_18], xmm3
0x18000631a  mov     rdx, rax
0x18000631d  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_devices_query_l1_1_0_dll
0x180006324  call    __delayLoadHelper2
0x180006329  movdqa  xmm0, [rsp+68h+var_48]
0x18000632f  movdqa  xmm1, [rsp+68h+var_38]
0x180006335  movdqa  xmm2, [rsp+68h+var_28]
0x18000633b  movdqa  xmm3, [rsp+68h+var_18]
0x180006341  mov     rcx, [rsp+68h+arg_0]
0x180006346  mov     rdx, [rsp+68h+arg_8]
0x18000634b  mov     r8, [rsp+68h+arg_10]
0x180006353  mov     r9, [rsp+68h+arg_18]
0x18000635b  add     rsp, 68h
0x18000635f  jmp     short $+2
0x180006361  jmp     rax
```
