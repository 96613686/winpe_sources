# __tailMerge_api_ms_win_security_sddl_l1_1_0_dll

- ea: `0x180008b68`
- end: `0x180008be1`
- name: `__tailMerge_api_ms_win_security_sddl_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180008be7`

## callees

- `0x180003970`
- `0x180008b68`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_security_sddl_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_sddl_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180008b68  mov     [rsp+arg_0], rcx
0x180008b6d  mov     [rsp+arg_8], rdx
0x180008b72  mov     [rsp+arg_10], r8
0x180008b77  mov     [rsp+arg_18], r9
0x180008b7c  sub     rsp, 68h
0x180008b80  movdqa  [rsp+68h+var_48], xmm0
0x180008b86  movdqa  [rsp+68h+var_38], xmm1
0x180008b8c  movdqa  [rsp+68h+var_28], xmm2
0x180008b92  movdqa  [rsp+68h+var_18], xmm3
0x180008b98  mov     rdx, rax
0x180008b9b  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_sddl_l1_1_0_dll
0x180008ba2  call    __delayLoadHelper2
0x180008ba7  movdqa  xmm0, [rsp+68h+var_48]
0x180008bad  movdqa  xmm1, [rsp+68h+var_38]
0x180008bb3  movdqa  xmm2, [rsp+68h+var_28]
0x180008bb9  movdqa  xmm3, [rsp+68h+var_18]
0x180008bbf  mov     rcx, [rsp+68h+arg_0]
0x180008bc4  mov     rdx, [rsp+68h+arg_8]
0x180008bc9  mov     r8, [rsp+68h+arg_10]
0x180008bd1  mov     r9, [rsp+68h+arg_18]
0x180008bd9  add     rsp, 68h
0x180008bdd  jmp     short $+2
0x180008bdf  jmp     rax
```
