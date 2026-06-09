# __tailMerge_ext_ms_win_uwf_servicing_apis_l1_1_0_dll

- ea: `0x180002b1a`
- end: `0x180002b93`
- name: `__tailMerge_ext_ms_win_uwf_servicing_apis_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x180002b99`

## callees

- `0x180002b1a`
- `0x18001af90`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_uwf_servicing_apis_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_uwf_servicing_apis_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002b1a  mov     [rsp+arg_0], rcx
0x180002b1f  mov     [rsp+arg_8], rdx
0x180002b24  mov     [rsp+arg_10], r8
0x180002b29  mov     [rsp+arg_18], r9
0x180002b2e  sub     rsp, 68h
0x180002b32  movdqa  [rsp+68h+var_48], xmm0
0x180002b38  movdqa  [rsp+68h+var_38], xmm1
0x180002b3e  movdqa  [rsp+68h+var_28], xmm2
0x180002b44  movdqa  [rsp+68h+var_18], xmm3
0x180002b4a  mov     rdx, rax
0x180002b4d  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_uwf_servicing_apis_l1_1_0_dll
0x180002b54  call    __delayLoadHelper2
0x180002b59  movdqa  xmm0, [rsp+68h+var_48]
0x180002b5f  movdqa  xmm1, [rsp+68h+var_38]
0x180002b65  movdqa  xmm2, [rsp+68h+var_28]
0x180002b6b  movdqa  xmm3, [rsp+68h+var_18]
0x180002b71  mov     rcx, [rsp+68h+arg_0]
0x180002b76  mov     rdx, [rsp+68h+arg_8]
0x180002b7b  mov     r8, [rsp+68h+arg_10]
0x180002b83  mov     r9, [rsp+68h+arg_18]
0x180002b8b  add     rsp, 68h
0x180002b8f  jmp     short $+2
0x180002b91  jmp     rax
```
