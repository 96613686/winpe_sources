# __tailMerge_netutils_dll

- ea: `0x1800351d3`
- end: `0x18003524c`
- name: `__tailMerge_netutils_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180035252`

## callees

- `0x18002be40`
- `0x1800351d3`

## pseudocode

```c
__int64 __fastcall _tailMerge_netutils_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_netutils_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800351d3  mov     [rsp+arg_0], rcx
0x1800351d8  mov     [rsp+arg_8], rdx
0x1800351dd  mov     [rsp+arg_10], r8
0x1800351e2  mov     [rsp+arg_18], r9
0x1800351e7  sub     rsp, 68h
0x1800351eb  movdqa  [rsp+68h+var_48], xmm0
0x1800351f1  movdqa  [rsp+68h+var_38], xmm1
0x1800351f7  movdqa  [rsp+68h+var_28], xmm2
0x1800351fd  movdqa  [rsp+68h+var_18], xmm3
0x180035203  mov     rdx, rax
0x180035206  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_netutils_dll
0x18003520d  call    __delayLoadHelper2
0x180035212  movdqa  xmm0, [rsp+68h+var_48]
0x180035218  movdqa  xmm1, [rsp+68h+var_38]
0x18003521e  movdqa  xmm2, [rsp+68h+var_28]
0x180035224  movdqa  xmm3, [rsp+68h+var_18]
0x18003522a  mov     rcx, [rsp+68h+arg_0]
0x18003522f  mov     rdx, [rsp+68h+arg_8]
0x180035234  mov     r8, [rsp+68h+arg_10]
0x18003523c  mov     r9, [rsp+68h+arg_18]
0x180035244  add     rsp, 68h
0x180035248  jmp     short $+2
0x18003524a  jmp     rax
```
