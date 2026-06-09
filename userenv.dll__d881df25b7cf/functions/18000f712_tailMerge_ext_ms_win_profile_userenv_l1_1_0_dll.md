# __tailMerge_ext_ms_win_profile_userenv_l1_1_0_dll

- ea: `0x18000f712`
- end: `0x18000f78b`
- name: `__tailMerge_ext_ms_win_profile_userenv_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `20`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000f791`
- `0x18000f82e`
- `0x18000f852`
- `0x18000f864`
- `0x18000f888`
- `0x18000f89a`
- `0x18000f8ac`
- `0x18000f8be`
- `0x18000f8e2`
- `0x18000f8f4`
- `0x18000f906`
- `0x18000f918`
- `0x18000f92a`
- `0x18000f93c`
- `0x18000f94e`
- `0x18000f972`
- `0x18000f984`
- `0x18000fa21`
- `0x18000fa33`
- `0x18000fa45`

## callees

- `0x1800089d0`
- `0x18000f712`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_profile_userenv_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_profile_userenv_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000f712  mov     [rsp+arg_0], rcx
0x18000f717  mov     [rsp+arg_8], rdx
0x18000f71c  mov     [rsp+arg_10], r8
0x18000f721  mov     [rsp+arg_18], r9
0x18000f726  sub     rsp, 68h
0x18000f72a  movdqa  [rsp+68h+var_48], xmm0
0x18000f730  movdqa  [rsp+68h+var_38], xmm1
0x18000f736  movdqa  [rsp+68h+var_28], xmm2
0x18000f73c  movdqa  [rsp+68h+var_18], xmm3
0x18000f742  mov     rdx, rax
0x18000f745  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_profile_userenv_l1_1_0_dll
0x18000f74c  call    __delayLoadHelper2
0x18000f751  movdqa  xmm0, [rsp+68h+var_48]
0x18000f757  movdqa  xmm1, [rsp+68h+var_38]
0x18000f75d  movdqa  xmm2, [rsp+68h+var_28]
0x18000f763  movdqa  xmm3, [rsp+68h+var_18]
0x18000f769  mov     rcx, [rsp+68h+arg_0]
0x18000f76e  mov     rdx, [rsp+68h+arg_8]
0x18000f773  mov     r8, [rsp+68h+arg_10]
0x18000f77b  mov     r9, [rsp+68h+arg_18]
0x18000f783  add     rsp, 68h
0x18000f787  jmp     short $+2
0x18000f789  jmp     rax
```
