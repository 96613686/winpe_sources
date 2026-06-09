# __tailMerge_api_ms_win_security_lsalookup_l2_1_0_dll

- ea: `0x18000c803`
- end: `0x18000c87c`
- name: `__tailMerge_api_ms_win_security_lsalookup_l2_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000c882`

## callees

- `0x18000b110`
- `0x18000c803`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_security_lsalookup_l2_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_lsalookup_l2_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000c803  mov     [rsp+arg_0], rcx
0x18000c808  mov     [rsp+arg_8], rdx
0x18000c80d  mov     [rsp+arg_10], r8
0x18000c812  mov     [rsp+arg_18], r9
0x18000c817  sub     rsp, 68h
0x18000c81b  movdqa  [rsp+68h+var_48], xmm0
0x18000c821  movdqa  [rsp+68h+var_38], xmm1
0x18000c827  movdqa  [rsp+68h+var_28], xmm2
0x18000c82d  movdqa  [rsp+68h+var_18], xmm3
0x18000c833  mov     rdx, rax
0x18000c836  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_lsalookup_l2_1_0_dll
0x18000c83d  call    __delayLoadHelper2
0x18000c842  movdqa  xmm0, [rsp+68h+var_48]
0x18000c848  movdqa  xmm1, [rsp+68h+var_38]
0x18000c84e  movdqa  xmm2, [rsp+68h+var_28]
0x18000c854  movdqa  xmm3, [rsp+68h+var_18]
0x18000c85a  mov     rcx, [rsp+68h+arg_0]
0x18000c85f  mov     rdx, [rsp+68h+arg_8]
0x18000c864  mov     r8, [rsp+68h+arg_10]
0x18000c86c  mov     r9, [rsp+68h+arg_18]
0x18000c874  add     rsp, 68h
0x18000c878  jmp     short $+2
0x18000c87a  jmp     rax
```
