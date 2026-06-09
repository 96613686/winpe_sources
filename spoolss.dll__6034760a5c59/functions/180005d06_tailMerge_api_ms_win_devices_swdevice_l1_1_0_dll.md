# __tailMerge_api_ms_win_devices_swdevice_l1_1_0_dll

- ea: `0x180005d06`
- end: `0x180005d7f`
- name: `__tailMerge_api_ms_win_devices_swdevice_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180005d85`

## callees

- `0x180005d06`
- `0x180014d80`

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
0x180005d06  mov     [rsp+arg_0], rcx
0x180005d0b  mov     [rsp+arg_8], rdx
0x180005d10  mov     [rsp+arg_10], r8
0x180005d15  mov     [rsp+arg_18], r9
0x180005d1a  sub     rsp, 68h
0x180005d1e  movdqa  [rsp+68h+var_48], xmm0
0x180005d24  movdqa  [rsp+68h+var_38], xmm1
0x180005d2a  movdqa  [rsp+68h+var_28], xmm2
0x180005d30  movdqa  [rsp+68h+var_18], xmm3
0x180005d36  mov     rdx, rax
0x180005d39  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_devices_swdevice_l1_1_0_dll
0x180005d40  call    __delayLoadHelper2
0x180005d45  movdqa  xmm0, [rsp+68h+var_48]
0x180005d4b  movdqa  xmm1, [rsp+68h+var_38]
0x180005d51  movdqa  xmm2, [rsp+68h+var_28]
0x180005d57  movdqa  xmm3, [rsp+68h+var_18]
0x180005d5d  mov     rcx, [rsp+68h+arg_0]
0x180005d62  mov     rdx, [rsp+68h+arg_8]
0x180005d67  mov     r8, [rsp+68h+arg_10]
0x180005d6f  mov     r9, [rsp+68h+arg_18]
0x180005d77  add     rsp, 68h
0x180005d7b  jmp     short $+2
0x180005d7d  jmp     rax
```
