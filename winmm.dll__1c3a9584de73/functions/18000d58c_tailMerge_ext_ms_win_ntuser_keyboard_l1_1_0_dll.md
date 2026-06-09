# __tailMerge_ext_ms_win_ntuser_keyboard_l1_1_0_dll

- ea: `0x18000d58c`
- end: `0x18000d605`
- name: `__tailMerge_ext_ms_win_ntuser_keyboard_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000d60b`

## callees

- `0x180009370`
- `0x18000d58c`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_ntuser_keyboard_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_keyboard_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000d58c  mov     [rsp+arg_0], rcx
0x18000d591  mov     [rsp+arg_8], rdx
0x18000d596  mov     [rsp+arg_10], r8
0x18000d59b  mov     [rsp+arg_18], r9
0x18000d5a0  sub     rsp, 68h
0x18000d5a4  movdqa  [rsp+68h+var_48], xmm0
0x18000d5aa  movdqa  [rsp+68h+var_38], xmm1
0x18000d5b0  movdqa  [rsp+68h+var_28], xmm2
0x18000d5b6  movdqa  [rsp+68h+var_18], xmm3
0x18000d5bc  mov     rdx, rax
0x18000d5bf  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_keyboard_l1_1_0_dll
0x18000d5c6  call    __delayLoadHelper2
0x18000d5cb  movdqa  xmm0, [rsp+68h+var_48]
0x18000d5d1  movdqa  xmm1, [rsp+68h+var_38]
0x18000d5d7  movdqa  xmm2, [rsp+68h+var_28]
0x18000d5dd  movdqa  xmm3, [rsp+68h+var_18]
0x18000d5e3  mov     rcx, [rsp+68h+arg_0]
0x18000d5e8  mov     rdx, [rsp+68h+arg_8]
0x18000d5ed  mov     r8, [rsp+68h+arg_10]
0x18000d5f5  mov     r9, [rsp+68h+arg_18]
0x18000d5fd  add     rsp, 68h
0x18000d601  jmp     short $+2
0x18000d603  jmp     rax
```
