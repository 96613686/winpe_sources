# __tailMerge_ext_ms_win_ntuser_window_l1_1_0_dll

- ea: `0x18000754c`
- end: `0x1800075c5`
- name: `__tailMerge_ext_ms_win_ntuser_window_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800075cb`
- `0x1800075dd`

## callees

- `0x180004ab0`
- `0x18000754c`

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
0x18000754c  mov     [rsp+arg_0], rcx
0x180007551  mov     [rsp+arg_8], rdx
0x180007556  mov     [rsp+arg_10], r8
0x18000755b  mov     [rsp+arg_18], r9
0x180007560  sub     rsp, 68h
0x180007564  movdqa  [rsp+68h+var_48], xmm0
0x18000756a  movdqa  [rsp+68h+var_38], xmm1
0x180007570  movdqa  [rsp+68h+var_28], xmm2
0x180007576  movdqa  [rsp+68h+var_18], xmm3
0x18000757c  mov     rdx, rax
0x18000757f  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_window_l1_1_0_dll
0x180007586  call    __delayLoadHelper2
0x18000758b  movdqa  xmm0, [rsp+68h+var_48]
0x180007591  movdqa  xmm1, [rsp+68h+var_38]
0x180007597  movdqa  xmm2, [rsp+68h+var_28]
0x18000759d  movdqa  xmm3, [rsp+68h+var_18]
0x1800075a3  mov     rcx, [rsp+68h+arg_0]
0x1800075a8  mov     rdx, [rsp+68h+arg_8]
0x1800075ad  mov     r8, [rsp+68h+arg_10]
0x1800075b5  mov     r9, [rsp+68h+arg_18]
0x1800075bd  add     rsp, 68h
0x1800075c1  jmp     short $+2
0x1800075c3  jmp     rax
```
