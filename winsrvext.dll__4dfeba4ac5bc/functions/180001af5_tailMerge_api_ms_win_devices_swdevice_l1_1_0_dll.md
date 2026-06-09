# __tailMerge_api_ms_win_devices_swdevice_l1_1_0_dll

- ea: `0x180001af5`
- end: `0x180001b6e`
- name: `__tailMerge_api_ms_win_devices_swdevice_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001b74`
- `0x180001b86`

## callees

- `0x180001af5`
- `0x180012d30`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_devices_swdevice_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_devices_swdevice_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180001af5  mov     [rsp+arg_0], rcx
0x180001afa  mov     [rsp+arg_8], rdx
0x180001aff  mov     [rsp+arg_10], r8
0x180001b04  mov     [rsp+arg_18], r9
0x180001b09  sub     rsp, 68h
0x180001b0d  movdqa  [rsp+68h+var_48], xmm0
0x180001b13  movdqa  [rsp+68h+var_38], xmm1
0x180001b19  movdqa  [rsp+68h+var_28], xmm2
0x180001b1f  movdqa  [rsp+68h+var_18], xmm3
0x180001b25  mov     rdx, rax
0x180001b28  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_devices_swdevice_l1_1_0_dll
0x180001b2f  call    __delayLoadHelper2
0x180001b34  movdqa  xmm0, [rsp+68h+var_48]
0x180001b3a  movdqa  xmm1, [rsp+68h+var_38]
0x180001b40  movdqa  xmm2, [rsp+68h+var_28]
0x180001b46  movdqa  xmm3, [rsp+68h+var_18]
0x180001b4c  mov     rcx, [rsp+68h+arg_0]
0x180001b51  mov     rdx, [rsp+68h+arg_8]
0x180001b56  mov     r8, [rsp+68h+arg_10]
0x180001b5e  mov     r9, [rsp+68h+arg_18]
0x180001b66  add     rsp, 68h
0x180001b6a  jmp     short $+2
0x180001b6c  jmp     rax
```
