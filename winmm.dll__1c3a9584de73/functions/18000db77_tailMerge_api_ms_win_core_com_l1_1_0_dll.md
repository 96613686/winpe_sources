# __tailMerge_api_ms_win_core_com_l1_1_0_dll

- ea: `0x18000db77`
- end: `0x18000dbf0`
- name: `__tailMerge_api_ms_win_core_com_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000dbf6`
- `0x18000dc08`

## callees

- `0x180009370`
- `0x18000db77`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_core_com_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_com_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000db77  mov     [rsp+arg_0], rcx
0x18000db7c  mov     [rsp+arg_8], rdx
0x18000db81  mov     [rsp+arg_10], r8
0x18000db86  mov     [rsp+arg_18], r9
0x18000db8b  sub     rsp, 68h
0x18000db8f  movdqa  [rsp+68h+var_48], xmm0
0x18000db95  movdqa  [rsp+68h+var_38], xmm1
0x18000db9b  movdqa  [rsp+68h+var_28], xmm2
0x18000dba1  movdqa  [rsp+68h+var_18], xmm3
0x18000dba7  mov     rdx, rax
0x18000dbaa  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_com_l1_1_0_dll
0x18000dbb1  call    __delayLoadHelper2
0x18000dbb6  movdqa  xmm0, [rsp+68h+var_48]
0x18000dbbc  movdqa  xmm1, [rsp+68h+var_38]
0x18000dbc2  movdqa  xmm2, [rsp+68h+var_28]
0x18000dbc8  movdqa  xmm3, [rsp+68h+var_18]
0x18000dbce  mov     rcx, [rsp+68h+arg_0]
0x18000dbd3  mov     rdx, [rsp+68h+arg_8]
0x18000dbd8  mov     r8, [rsp+68h+arg_10]
0x18000dbe0  mov     r9, [rsp+68h+arg_18]
0x18000dbe8  add     rsp, 68h
0x18000dbec  jmp     short $+2
0x18000dbee  jmp     rax
```
