# __tailMerge_sspicli_dll

- ea: `0x18003525e`
- end: `0x1800352d7`
- name: `__tailMerge_sspicli_dll`
- size: `121`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800352dd`
- `0x1800354d0`
- `0x1800354e2`
- `0x1800354f4`

## callees

- `0x18002be40`
- `0x18003525e`

## pseudocode

```c
__int64 __fastcall _tailMerge_sspicli_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_sspicli_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18003525e  mov     [rsp+arg_0], rcx
0x180035263  mov     [rsp+arg_8], rdx
0x180035268  mov     [rsp+arg_10], r8
0x18003526d  mov     [rsp+arg_18], r9
0x180035272  sub     rsp, 68h
0x180035276  movdqa  [rsp+68h+var_48], xmm0
0x18003527c  movdqa  [rsp+68h+var_38], xmm1
0x180035282  movdqa  [rsp+68h+var_28], xmm2
0x180035288  movdqa  [rsp+68h+var_18], xmm3
0x18003528e  mov     rdx, rax
0x180035291  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_sspicli_dll
0x180035298  call    __delayLoadHelper2
0x18003529d  movdqa  xmm0, [rsp+68h+var_48]
0x1800352a3  movdqa  xmm1, [rsp+68h+var_38]
0x1800352a9  movdqa  xmm2, [rsp+68h+var_28]
0x1800352af  movdqa  xmm3, [rsp+68h+var_18]
0x1800352b5  mov     rcx, [rsp+68h+arg_0]
0x1800352ba  mov     rdx, [rsp+68h+arg_8]
0x1800352bf  mov     r8, [rsp+68h+arg_10]
0x1800352c7  mov     r9, [rsp+68h+arg_18]
0x1800352cf  add     rsp, 68h
0x1800352d3  jmp     short $+2
0x1800352d5  jmp     rax
```
