# __tailMerge_ext_ms_win_session_usermgr_l1_1_0_dll

- ea: `0x180002fd0`
- end: `0x180003049`
- name: `__tailMerge_ext_ms_win_session_usermgr_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000304f`
- `0x180003061`
- `0x180003073`

## callees

- `0x180002fd0`
- `0x18001af90`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_session_usermgr_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_session_usermgr_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002fd0  mov     [rsp+arg_0], rcx
0x180002fd5  mov     [rsp+arg_8], rdx
0x180002fda  mov     [rsp+arg_10], r8
0x180002fdf  mov     [rsp+arg_18], r9
0x180002fe4  sub     rsp, 68h
0x180002fe8  movdqa  [rsp+68h+var_48], xmm0
0x180002fee  movdqa  [rsp+68h+var_38], xmm1
0x180002ff4  movdqa  [rsp+68h+var_28], xmm2
0x180002ffa  movdqa  [rsp+68h+var_18], xmm3
0x180003000  mov     rdx, rax
0x180003003  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_session_usermgr_l1_1_0_dll
0x18000300a  call    __delayLoadHelper2
0x18000300f  movdqa  xmm0, [rsp+68h+var_48]
0x180003015  movdqa  xmm1, [rsp+68h+var_38]
0x18000301b  movdqa  xmm2, [rsp+68h+var_28]
0x180003021  movdqa  xmm3, [rsp+68h+var_18]
0x180003027  mov     rcx, [rsp+68h+arg_0]
0x18000302c  mov     rdx, [rsp+68h+arg_8]
0x180003031  mov     r8, [rsp+68h+arg_10]
0x180003039  mov     r9, [rsp+68h+arg_18]
0x180003041  add     rsp, 68h
0x180003045  jmp     short $+2
0x180003047  jmp     rax
```
