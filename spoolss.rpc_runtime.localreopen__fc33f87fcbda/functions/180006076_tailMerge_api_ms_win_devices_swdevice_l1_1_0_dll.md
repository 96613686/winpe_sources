# __tailMerge_api_ms_win_devices_swdevice_l1_1_0_dll

- ea: `0x180006076`
- end: `0x1800060ef`
- name: `__tailMerge_api_ms_win_devices_swdevice_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800060f5`

## callees

- `0x180006076`
- `0x180016780`

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
0x180006076  mov     [rsp+arg_0], rcx
0x18000607b  mov     [rsp+arg_8], rdx
0x180006080  mov     [rsp+arg_10], r8
0x180006085  mov     [rsp+arg_18], r9
0x18000608a  sub     rsp, 68h
0x18000608e  movdqa  [rsp+68h+var_48], xmm0
0x180006094  movdqa  [rsp+68h+var_38], xmm1
0x18000609a  movdqa  [rsp+68h+var_28], xmm2
0x1800060a0  movdqa  [rsp+68h+var_18], xmm3
0x1800060a6  mov     rdx, rax
0x1800060a9  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_devices_swdevice_l1_1_0_dll
0x1800060b0  call    __delayLoadHelper2
0x1800060b5  movdqa  xmm0, [rsp+68h+var_48]
0x1800060bb  movdqa  xmm1, [rsp+68h+var_38]
0x1800060c1  movdqa  xmm2, [rsp+68h+var_28]
0x1800060c7  movdqa  xmm3, [rsp+68h+var_18]
0x1800060cd  mov     rcx, [rsp+68h+arg_0]
0x1800060d2  mov     rdx, [rsp+68h+arg_8]
0x1800060d7  mov     r8, [rsp+68h+arg_10]
0x1800060df  mov     r9, [rsp+68h+arg_18]
0x1800060e7  add     rsp, 68h
0x1800060eb  jmp     short $+2
0x1800060ed  jmp     rax
```
