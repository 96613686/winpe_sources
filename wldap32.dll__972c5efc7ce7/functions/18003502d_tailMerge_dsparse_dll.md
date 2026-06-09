# __tailMerge_dsparse_dll

- ea: `0x18003502d`
- end: `0x1800350a6`
- name: `__tailMerge_dsparse_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800350ac`

## callees

- `0x18002be40`
- `0x18003502d`

## pseudocode

```c
__int64 __fastcall _tailMerge_dsparse_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_dsparse_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18003502d  mov     [rsp+arg_0], rcx
0x180035032  mov     [rsp+arg_8], rdx
0x180035037  mov     [rsp+arg_10], r8
0x18003503c  mov     [rsp+arg_18], r9
0x180035041  sub     rsp, 68h
0x180035045  movdqa  [rsp+68h+var_48], xmm0
0x18003504b  movdqa  [rsp+68h+var_38], xmm1
0x180035051  movdqa  [rsp+68h+var_28], xmm2
0x180035057  movdqa  [rsp+68h+var_18], xmm3
0x18003505d  mov     rdx, rax
0x180035060  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_dsparse_dll
0x180035067  call    __delayLoadHelper2
0x18003506c  movdqa  xmm0, [rsp+68h+var_48]
0x180035072  movdqa  xmm1, [rsp+68h+var_38]
0x180035078  movdqa  xmm2, [rsp+68h+var_28]
0x18003507e  movdqa  xmm3, [rsp+68h+var_18]
0x180035084  mov     rcx, [rsp+68h+arg_0]
0x180035089  mov     rdx, [rsp+68h+arg_8]
0x18003508e  mov     r8, [rsp+68h+arg_10]
0x180035096  mov     r9, [rsp+68h+arg_18]
0x18003509e  add     rsp, 68h
0x1800350a2  jmp     short $+2
0x1800350a4  jmp     rax
```
