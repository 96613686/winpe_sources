# __tailMerge_ext_ms_win_rtcore_ntuser_window_ext_l1_1_0_dll

- ea: `0x1800034e9`
- end: `0x180003562`
- name: `__tailMerge_ext_ms_win_rtcore_ntuser_window_ext_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `18`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003568`
- `0x18000357a`
- `0x18000358c`
- `0x18000359e`
- `0x1800035b0`
- `0x1800035c2`
- `0x1800035d4`
- `0x1800035e6`
- `0x1800035f8`
- `0x18000360a`
- `0x18000361c`
- `0x18000362e`
- `0x180003640`
- `0x180003652`
- `0x180003664`
- `0x180003676`
- `0x180003688`
- `0x18000369a`

## callees

- `0x1800034e9`
- `0x18001a930`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_rtcore_ntuser_window_ext_l1_1_0_dll(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_rtcore_ntuser_window_ext_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800034e9  mov     [rsp+arg_0], rcx
0x1800034ee  mov     [rsp+arg_8], rdx
0x1800034f3  mov     [rsp+arg_10], r8
0x1800034f8  mov     [rsp+arg_18], r9
0x1800034fd  sub     rsp, 68h
0x180003501  movdqa  [rsp+68h+var_48], xmm0
0x180003507  movdqa  [rsp+68h+var_38], xmm1
0x18000350d  movdqa  [rsp+68h+var_28], xmm2
0x180003513  movdqa  [rsp+68h+var_18], xmm3
0x180003519  mov     rdx, rax
0x18000351c  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_rtcore_ntuser_window_ext_l1_1_0_dll
0x180003523  call    __delayLoadHelper2
0x180003528  movdqa  xmm0, [rsp+68h+var_48]
0x18000352e  movdqa  xmm1, [rsp+68h+var_38]
0x180003534  movdqa  xmm2, [rsp+68h+var_28]
0x18000353a  movdqa  xmm3, [rsp+68h+var_18]
0x180003540  mov     rcx, [rsp+68h+arg_0]
0x180003545  mov     rdx, [rsp+68h+arg_8]
0x18000354a  mov     r8, [rsp+68h+arg_10]
0x180003552  mov     r9, [rsp+68h+arg_18]
0x18000355a  add     rsp, 68h
0x18000355e  jmp     short $+2
0x180003560  jmp     rax
```
