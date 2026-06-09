# __tailMerge_api_ms_win_security_base_l1_1_0_dll

- ea: `0x180007375`
- end: `0x1800073ee`
- name: `__tailMerge_api_ms_win_security_base_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800073f4`
- `0x180007491`
- `0x18000752e`
- `0x180007540`
- `0x180007b08`
- `0x180007b1a`
- `0x180007b2c`

## callees

- `0x180004ab0`
- `0x180007375`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_security_base_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_base_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180007375  mov     [rsp+arg_0], rcx
0x18000737a  mov     [rsp+arg_8], rdx
0x18000737f  mov     [rsp+arg_10], r8
0x180007384  mov     [rsp+arg_18], r9
0x180007389  sub     rsp, 68h
0x18000738d  movdqa  [rsp+68h+var_48], xmm0
0x180007393  movdqa  [rsp+68h+var_38], xmm1
0x180007399  movdqa  [rsp+68h+var_28], xmm2
0x18000739f  movdqa  [rsp+68h+var_18], xmm3
0x1800073a5  mov     rdx, rax
0x1800073a8  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_base_l1_1_0_dll
0x1800073af  call    __delayLoadHelper2
0x1800073b4  movdqa  xmm0, [rsp+68h+var_48]
0x1800073ba  movdqa  xmm1, [rsp+68h+var_38]
0x1800073c0  movdqa  xmm2, [rsp+68h+var_28]
0x1800073c6  movdqa  xmm3, [rsp+68h+var_18]
0x1800073cc  mov     rcx, [rsp+68h+arg_0]
0x1800073d1  mov     rdx, [rsp+68h+arg_8]
0x1800073d6  mov     r8, [rsp+68h+arg_10]
0x1800073de  mov     r9, [rsp+68h+arg_18]
0x1800073e6  add     rsp, 68h
0x1800073ea  jmp     short $+2
0x1800073ec  jmp     rax
```
