# __tailMerge_ext_ms_win_session_wtsapi32_l1_1_0_dll

- ea: `0x18000d573`
- end: `0x18000d5ec`
- name: `__tailMerge_ext_ms_win_session_wtsapi32_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000d5f2`
- `0x18000d604`
- `0x18000d616`

## callees

- `0x180008bd0`
- `0x18000d573`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_session_wtsapi32_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_session_wtsapi32_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000d573  mov     [rsp+arg_0], rcx
0x18000d578  mov     [rsp+arg_8], rdx
0x18000d57d  mov     [rsp+arg_10], r8
0x18000d582  mov     [rsp+arg_18], r9
0x18000d587  sub     rsp, 68h
0x18000d58b  movdqa  [rsp+68h+var_48], xmm0
0x18000d591  movdqa  [rsp+68h+var_38], xmm1
0x18000d597  movdqa  [rsp+68h+var_28], xmm2
0x18000d59d  movdqa  [rsp+68h+var_18], xmm3
0x18000d5a3  mov     rdx, rax
0x18000d5a6  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_session_wtsapi32_l1_1_0_dll
0x18000d5ad  call    __delayLoadHelper2
0x18000d5b2  movdqa  xmm0, [rsp+68h+var_48]
0x18000d5b8  movdqa  xmm1, [rsp+68h+var_38]
0x18000d5be  movdqa  xmm2, [rsp+68h+var_28]
0x18000d5c4  movdqa  xmm3, [rsp+68h+var_18]
0x18000d5ca  mov     rcx, [rsp+68h+arg_0]
0x18000d5cf  mov     rdx, [rsp+68h+arg_8]
0x18000d5d4  mov     r8, [rsp+68h+arg_10]
0x18000d5dc  mov     r9, [rsp+68h+arg_18]
0x18000d5e4  add     rsp, 68h
0x18000d5e8  jmp     short $+2
0x18000d5ea  jmp     rax
```
