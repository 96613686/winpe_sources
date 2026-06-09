# __tailMerge_ext_ms_win_ntuser_window_l1_1_2_dll

- ea: `0x18000d96a`
- end: `0x18000d9e3`
- name: `__tailMerge_ext_ms_win_ntuser_window_l1_1_2_dll`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000d9e9`
- `0x18000d9fb`

## callees

- `0x180009370`
- `0x18000d96a`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_ntuser_window_l1_1_2_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_window_l1_1_2_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000d96a  mov     [rsp+arg_0], rcx
0x18000d96f  mov     [rsp+arg_8], rdx
0x18000d974  mov     [rsp+arg_10], r8
0x18000d979  mov     [rsp+arg_18], r9
0x18000d97e  sub     rsp, 68h
0x18000d982  movdqa  [rsp+68h+var_48], xmm0
0x18000d988  movdqa  [rsp+68h+var_38], xmm1
0x18000d98e  movdqa  [rsp+68h+var_28], xmm2
0x18000d994  movdqa  [rsp+68h+var_18], xmm3
0x18000d99a  mov     rdx, rax
0x18000d99d  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_window_l1_1_2_dll
0x18000d9a4  call    __delayLoadHelper2
0x18000d9a9  movdqa  xmm0, [rsp+68h+var_48]
0x18000d9af  movdqa  xmm1, [rsp+68h+var_38]
0x18000d9b5  movdqa  xmm2, [rsp+68h+var_28]
0x18000d9bb  movdqa  xmm3, [rsp+68h+var_18]
0x18000d9c1  mov     rcx, [rsp+68h+arg_0]
0x18000d9c6  mov     rdx, [rsp+68h+arg_8]
0x18000d9cb  mov     r8, [rsp+68h+arg_10]
0x18000d9d3  mov     r9, [rsp+68h+arg_18]
0x18000d9db  add     rsp, 68h
0x18000d9df  jmp     short $+2
0x18000d9e1  jmp     rax
```
