# __tailMerge_ext_ms_win_session_winsta_l1_1_0_dll

- ea: `0x180007f9e`
- end: `0x180008017`
- name: `__tailMerge_ext_ms_win_session_winsta_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000801d`
- `0x18000802f`
- `0x180008041`

## callees

- `0x1800063c0`
- `0x180007f9e`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_session_winsta_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_session_winsta_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180007f9e  mov     [rsp+arg_0], rcx
0x180007fa3  mov     [rsp+arg_8], rdx
0x180007fa8  mov     [rsp+arg_10], r8
0x180007fad  mov     [rsp+arg_18], r9
0x180007fb2  sub     rsp, 68h
0x180007fb6  movdqa  [rsp+68h+var_48], xmm0
0x180007fbc  movdqa  [rsp+68h+var_38], xmm1
0x180007fc2  movdqa  [rsp+68h+var_28], xmm2
0x180007fc8  movdqa  [rsp+68h+var_18], xmm3
0x180007fce  mov     rdx, rax
0x180007fd1  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_session_winsta_l1_1_0_dll
0x180007fd8  call    __delayLoadHelper2
0x180007fdd  movdqa  xmm0, [rsp+68h+var_48]
0x180007fe3  movdqa  xmm1, [rsp+68h+var_38]
0x180007fe9  movdqa  xmm2, [rsp+68h+var_28]
0x180007fef  movdqa  xmm3, [rsp+68h+var_18]
0x180007ff5  mov     rcx, [rsp+68h+arg_0]
0x180007ffa  mov     rdx, [rsp+68h+arg_8]
0x180007fff  mov     r8, [rsp+68h+arg_10]
0x180008007  mov     r9, [rsp+68h+arg_18]
0x18000800f  add     rsp, 68h
0x180008013  jmp     short $+2
0x180008015  jmp     rax
```
