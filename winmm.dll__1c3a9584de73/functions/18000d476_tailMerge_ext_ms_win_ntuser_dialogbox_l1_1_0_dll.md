# __tailMerge_ext_ms_win_ntuser_dialogbox_l1_1_0_dll

- ea: `0x18000d476`
- end: `0x18000d4ef`
- name: `__tailMerge_ext_ms_win_ntuser_dialogbox_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000d4f5`

## callees

- `0x180009370`
- `0x18000d476`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_ntuser_dialogbox_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_dialogbox_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000d476  mov     [rsp+arg_0], rcx
0x18000d47b  mov     [rsp+arg_8], rdx
0x18000d480  mov     [rsp+arg_10], r8
0x18000d485  mov     [rsp+arg_18], r9
0x18000d48a  sub     rsp, 68h
0x18000d48e  movdqa  [rsp+68h+var_48], xmm0
0x18000d494  movdqa  [rsp+68h+var_38], xmm1
0x18000d49a  movdqa  [rsp+68h+var_28], xmm2
0x18000d4a0  movdqa  [rsp+68h+var_18], xmm3
0x18000d4a6  mov     rdx, rax
0x18000d4a9  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_dialogbox_l1_1_0_dll
0x18000d4b0  call    __delayLoadHelper2
0x18000d4b5  movdqa  xmm0, [rsp+68h+var_48]
0x18000d4bb  movdqa  xmm1, [rsp+68h+var_38]
0x18000d4c1  movdqa  xmm2, [rsp+68h+var_28]
0x18000d4c7  movdqa  xmm3, [rsp+68h+var_18]
0x18000d4cd  mov     rcx, [rsp+68h+arg_0]
0x18000d4d2  mov     rdx, [rsp+68h+arg_8]
0x18000d4d7  mov     r8, [rsp+68h+arg_10]
0x18000d4df  mov     r9, [rsp+68h+arg_18]
0x18000d4e7  add     rsp, 68h
0x18000d4eb  jmp     short $+2
0x18000d4ed  jmp     rax
```
