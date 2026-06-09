# __tailMerge_api_ms_win_service_management_l1_1_0_dll

- ea: `0x180003384`
- end: `0x1800033fd`
- name: `__tailMerge_api_ms_win_service_management_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x180003403`
- `0x180003415`
- `0x1800034a0`
- `0x1800034b2`

## callees

- `0x180001850`
- `0x180003384`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_service_management_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_service_management_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180003384  mov     [rsp+arg_0], rcx
0x180003389  mov     [rsp+arg_8], rdx
0x18000338e  mov     [rsp+arg_10], r8
0x180003393  mov     [rsp+arg_18], r9
0x180003398  sub     rsp, 68h
0x18000339c  movdqa  [rsp+68h+var_48], xmm0
0x1800033a2  movdqa  [rsp+68h+var_38], xmm1
0x1800033a8  movdqa  [rsp+68h+var_28], xmm2
0x1800033ae  movdqa  [rsp+68h+var_18], xmm3
0x1800033b4  mov     rdx, rax
0x1800033b7  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_service_management_l1_1_0_dll
0x1800033be  call    __delayLoadHelper2
0x1800033c3  movdqa  xmm0, [rsp+68h+var_48]
0x1800033c9  movdqa  xmm1, [rsp+68h+var_38]
0x1800033cf  movdqa  xmm2, [rsp+68h+var_28]
0x1800033d5  movdqa  xmm3, [rsp+68h+var_18]
0x1800033db  mov     rcx, [rsp+68h+arg_0]
0x1800033e0  mov     rdx, [rsp+68h+arg_8]
0x1800033e5  mov     r8, [rsp+68h+arg_10]
0x1800033ed  mov     r9, [rsp+68h+arg_18]
0x1800033f5  add     rsp, 68h
0x1800033f9  jmp     short $+2
0x1800033fb  jmp     rax
```
