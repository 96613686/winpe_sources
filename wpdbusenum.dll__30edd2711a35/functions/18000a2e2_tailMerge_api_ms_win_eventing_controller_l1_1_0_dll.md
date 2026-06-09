# __tailMerge_api_ms_win_eventing_controller_l1_1_0_dll

- ea: `0x18000a2e2`
- end: `0x18000a35b`
- name: `__tailMerge_api_ms_win_eventing_controller_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000a361`

## callees

- `0x180006050`
- `0x18000a2e2`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_eventing_controller_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_eventing_controller_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000a2e2  mov     [rsp+arg_0], rcx
0x18000a2e7  mov     [rsp+arg_8], rdx
0x18000a2ec  mov     [rsp+arg_10], r8
0x18000a2f1  mov     [rsp+arg_18], r9
0x18000a2f6  sub     rsp, 68h
0x18000a2fa  movdqa  [rsp+68h+var_48], xmm0
0x18000a300  movdqa  [rsp+68h+var_38], xmm1
0x18000a306  movdqa  [rsp+68h+var_28], xmm2
0x18000a30c  movdqa  [rsp+68h+var_18], xmm3
0x18000a312  mov     rdx, rax
0x18000a315  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_eventing_controller_l1_1_0_dll
0x18000a31c  call    __delayLoadHelper2
0x18000a321  movdqa  xmm0, [rsp+68h+var_48]
0x18000a327  movdqa  xmm1, [rsp+68h+var_38]
0x18000a32d  movdqa  xmm2, [rsp+68h+var_28]
0x18000a333  movdqa  xmm3, [rsp+68h+var_18]
0x18000a339  mov     rcx, [rsp+68h+arg_0]
0x18000a33e  mov     rdx, [rsp+68h+arg_8]
0x18000a343  mov     r8, [rsp+68h+arg_10]
0x18000a34b  mov     r9, [rsp+68h+arg_18]
0x18000a353  add     rsp, 68h
0x18000a357  jmp     short $+2
0x18000a359  jmp     rax
```
