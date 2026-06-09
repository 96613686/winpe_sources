# __tailMerge_ext_ms_win_ntuser_gui_l1_1_0_dll

- ea: `0x18000d501`
- end: `0x18000d57a`
- name: `__tailMerge_ext_ms_win_ntuser_gui_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000d580`

## callees

- `0x180009370`
- `0x18000d501`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_ntuser_gui_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_gui_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000d501  mov     [rsp+arg_0], rcx
0x18000d506  mov     [rsp+arg_8], rdx
0x18000d50b  mov     [rsp+arg_10], r8
0x18000d510  mov     [rsp+arg_18], r9
0x18000d515  sub     rsp, 68h
0x18000d519  movdqa  [rsp+68h+var_48], xmm0
0x18000d51f  movdqa  [rsp+68h+var_38], xmm1
0x18000d525  movdqa  [rsp+68h+var_28], xmm2
0x18000d52b  movdqa  [rsp+68h+var_18], xmm3
0x18000d531  mov     rdx, rax
0x18000d534  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_gui_l1_1_0_dll
0x18000d53b  call    __delayLoadHelper2
0x18000d540  movdqa  xmm0, [rsp+68h+var_48]
0x18000d546  movdqa  xmm1, [rsp+68h+var_38]
0x18000d54c  movdqa  xmm2, [rsp+68h+var_28]
0x18000d552  movdqa  xmm3, [rsp+68h+var_18]
0x18000d558  mov     rcx, [rsp+68h+arg_0]
0x18000d55d  mov     rdx, [rsp+68h+arg_8]
0x18000d562  mov     r8, [rsp+68h+arg_10]
0x18000d56a  mov     r9, [rsp+68h+arg_18]
0x18000d572  add     rsp, 68h
0x18000d576  jmp     short $+2
0x18000d578  jmp     rax
```
