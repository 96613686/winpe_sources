# __tailMerge_iphlpapi_dll

- ea: `0x1800353e5`
- end: `0x18003545e`
- name: `__tailMerge_iphlpapi_dll`
- size: `121`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180035464`
- `0x180035476`
- `0x180035488`
- `0x18003549a`
- `0x1800354ac`

## callees

- `0x18002be40`
- `0x1800353e5`

## pseudocode

```c
__int64 __fastcall _tailMerge_iphlpapi_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_iphlpapi_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800353e5  mov     [rsp+arg_0], rcx
0x1800353ea  mov     [rsp+arg_8], rdx
0x1800353ef  mov     [rsp+arg_10], r8
0x1800353f4  mov     [rsp+arg_18], r9
0x1800353f9  sub     rsp, 68h
0x1800353fd  movdqa  [rsp+68h+var_48], xmm0
0x180035403  movdqa  [rsp+68h+var_38], xmm1
0x180035409  movdqa  [rsp+68h+var_28], xmm2
0x18003540f  movdqa  [rsp+68h+var_18], xmm3
0x180035415  mov     rdx, rax
0x180035418  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_iphlpapi_dll
0x18003541f  call    __delayLoadHelper2
0x180035424  movdqa  xmm0, [rsp+68h+var_48]
0x18003542a  movdqa  xmm1, [rsp+68h+var_38]
0x180035430  movdqa  xmm2, [rsp+68h+var_28]
0x180035436  movdqa  xmm3, [rsp+68h+var_18]
0x18003543c  mov     rcx, [rsp+68h+arg_0]
0x180035441  mov     rdx, [rsp+68h+arg_8]
0x180035446  mov     r8, [rsp+68h+arg_10]
0x18003544e  mov     r9, [rsp+68h+arg_18]
0x180035456  add     rsp, 68h
0x18003545a  jmp     short $+2
0x18003545c  jmp     rax
```
