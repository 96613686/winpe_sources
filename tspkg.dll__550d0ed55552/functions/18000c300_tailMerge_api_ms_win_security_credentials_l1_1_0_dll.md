# __tailMerge_api_ms_win_security_credentials_l1_1_0_dll

- ea: `0x18000c300`
- end: `0x18000c379`
- name: `__tailMerge_api_ms_win_security_credentials_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000c37f`
- `0x18000c3c7`
- `0x18000c40f`
- `0x18000c49f`
- `0x18000c4b1`

## callees

- `0x180009770`
- `0x18000c300`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_security_credentials_l1_1_0_dll(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_credentials_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000c300  mov     [rsp+arg_0], rcx
0x18000c305  mov     [rsp+arg_8], rdx
0x18000c30a  mov     [rsp+arg_10], r8
0x18000c30f  mov     [rsp+arg_18], r9
0x18000c314  sub     rsp, 68h
0x18000c318  movdqa  [rsp+68h+var_48], xmm0
0x18000c31e  movdqa  [rsp+68h+var_38], xmm1
0x18000c324  movdqa  [rsp+68h+var_28], xmm2
0x18000c32a  movdqa  [rsp+68h+var_18], xmm3
0x18000c330  mov     rdx, rax
0x18000c333  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_credentials_l1_1_0_dll
0x18000c33a  call    __delayLoadHelper2
0x18000c33f  movdqa  xmm0, [rsp+68h+var_48]
0x18000c345  movdqa  xmm1, [rsp+68h+var_38]
0x18000c34b  movdqa  xmm2, [rsp+68h+var_28]
0x18000c351  movdqa  xmm3, [rsp+68h+var_18]
0x18000c357  mov     rcx, [rsp+68h+arg_0]
0x18000c35c  mov     rdx, [rsp+68h+arg_8]
0x18000c361  mov     r8, [rsp+68h+arg_10]
0x18000c369  mov     r9, [rsp+68h+arg_18]
0x18000c371  add     rsp, 68h
0x18000c375  jmp     short $+2
0x18000c377  jmp     rax
```
