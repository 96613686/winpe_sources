# __tailMerge_ext_ms_win_ntuser_window_l1_1_0_dll

- ea: `0x18000da07`
- end: `0x18000da80`
- name: `__tailMerge_ext_ms_win_ntuser_window_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000da86`
- `0x18000da98`
- `0x18000daaa`
- `0x18000dabc`
- `0x18000dace`

## callees

- `0x180009370`
- `0x18000da07`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_ntuser_window_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_window_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000da07  mov     [rsp+arg_0], rcx
0x18000da0c  mov     [rsp+arg_8], rdx
0x18000da11  mov     [rsp+arg_10], r8
0x18000da16  mov     [rsp+arg_18], r9
0x18000da1b  sub     rsp, 68h
0x18000da1f  movdqa  [rsp+68h+var_48], xmm0
0x18000da25  movdqa  [rsp+68h+var_38], xmm1
0x18000da2b  movdqa  [rsp+68h+var_28], xmm2
0x18000da31  movdqa  [rsp+68h+var_18], xmm3
0x18000da37  mov     rdx, rax
0x18000da3a  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_window_l1_1_0_dll
0x18000da41  call    __delayLoadHelper2
0x18000da46  movdqa  xmm0, [rsp+68h+var_48]
0x18000da4c  movdqa  xmm1, [rsp+68h+var_38]
0x18000da52  movdqa  xmm2, [rsp+68h+var_28]
0x18000da58  movdqa  xmm3, [rsp+68h+var_18]
0x18000da5e  mov     rcx, [rsp+68h+arg_0]
0x18000da63  mov     rdx, [rsp+68h+arg_8]
0x18000da68  mov     r8, [rsp+68h+arg_10]
0x18000da70  mov     r9, [rsp+68h+arg_18]
0x18000da78  add     rsp, 68h
0x18000da7c  jmp     short $+2
0x18000da7e  jmp     rax
```
