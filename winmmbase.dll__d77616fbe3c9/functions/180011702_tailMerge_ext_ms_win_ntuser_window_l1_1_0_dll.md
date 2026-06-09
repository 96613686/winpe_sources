# __tailMerge_ext_ms_win_ntuser_window_l1_1_0_dll

- ea: `0x180011702`
- end: `0x18001177b`
- name: `__tailMerge_ext_ms_win_ntuser_window_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180011781`
- `0x180011793`
- `0x1800117a5`
- `0x18001180c`

## callees

- `0x18000f240`
- `0x180011702`

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
0x180011702  mov     [rsp+arg_0], rcx
0x180011707  mov     [rsp+arg_8], rdx
0x18001170c  mov     [rsp+arg_10], r8
0x180011711  mov     [rsp+arg_18], r9
0x180011716  sub     rsp, 68h
0x18001171a  movdqa  [rsp+68h+var_48], xmm0
0x180011720  movdqa  [rsp+68h+var_38], xmm1
0x180011726  movdqa  [rsp+68h+var_28], xmm2
0x18001172c  movdqa  [rsp+68h+var_18], xmm3
0x180011732  mov     rdx, rax
0x180011735  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_window_l1_1_0_dll
0x18001173c  call    __delayLoadHelper2
0x180011741  movdqa  xmm0, [rsp+68h+var_48]
0x180011747  movdqa  xmm1, [rsp+68h+var_38]
0x18001174d  movdqa  xmm2, [rsp+68h+var_28]
0x180011753  movdqa  xmm3, [rsp+68h+var_18]
0x180011759  mov     rcx, [rsp+68h+arg_0]
0x18001175e  mov     rdx, [rsp+68h+arg_8]
0x180011763  mov     r8, [rsp+68h+arg_10]
0x18001176b  mov     r9, [rsp+68h+arg_18]
0x180011773  add     rsp, 68h
0x180011777  jmp     short $+2
0x180011779  jmp     rax
```
