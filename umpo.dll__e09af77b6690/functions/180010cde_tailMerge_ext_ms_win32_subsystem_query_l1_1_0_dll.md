# __tailMerge_ext_ms_win32_subsystem_query_l1_1_0_dll

- ea: `0x180010cde`
- end: `0x180010d57`
- name: `__tailMerge_ext_ms_win32_subsystem_query_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180010d5d`

## callees

- `0x180010cde`
- `0x180018770`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win32_subsystem_query_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_ext_ms_win32_subsystem_query_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180010cde  mov     [rsp+arg_0], rcx
0x180010ce3  mov     [rsp+arg_8], rdx
0x180010ce8  mov     [rsp+arg_10], r8
0x180010ced  mov     [rsp+arg_18], r9
0x180010cf2  sub     rsp, 68h
0x180010cf6  movdqa  [rsp+68h+var_48], xmm0
0x180010cfc  movdqa  [rsp+68h+var_38], xmm1
0x180010d02  movdqa  [rsp+68h+var_28], xmm2
0x180010d08  movdqa  [rsp+68h+var_18], xmm3
0x180010d0e  mov     rdx, rax
0x180010d11  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win32_subsystem_query_l1_1_0_dll
0x180010d18  call    __delayLoadHelper2
0x180010d1d  movdqa  xmm0, [rsp+68h+var_48]
0x180010d23  movdqa  xmm1, [rsp+68h+var_38]
0x180010d29  movdqa  xmm2, [rsp+68h+var_28]
0x180010d2f  movdqa  xmm3, [rsp+68h+var_18]
0x180010d35  mov     rcx, [rsp+68h+arg_0]
0x180010d3a  mov     rdx, [rsp+68h+arg_8]
0x180010d3f  mov     r8, [rsp+68h+arg_10]
0x180010d47  mov     r9, [rsp+68h+arg_18]
0x180010d4f  add     rsp, 68h
0x180010d53  jmp     short $+2
0x180010d55  jmp     rax
```
