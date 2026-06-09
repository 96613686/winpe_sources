# __tailMerge_netutils_dll

- ea: `0x180007400`
- end: `0x180007479`
- name: `__tailMerge_netutils_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000747f`

## callees

- `0x180004ab0`
- `0x180007400`

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
0x180007400  mov     [rsp+arg_0], rcx
0x180007405  mov     [rsp+arg_8], rdx
0x18000740a  mov     [rsp+arg_10], r8
0x18000740f  mov     [rsp+arg_18], r9
0x180007414  sub     rsp, 68h
0x180007418  movdqa  [rsp+68h+var_48], xmm0
0x18000741e  movdqa  [rsp+68h+var_38], xmm1
0x180007424  movdqa  [rsp+68h+var_28], xmm2
0x18000742a  movdqa  [rsp+68h+var_18], xmm3
0x180007430  mov     rdx, rax
0x180007433  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_netutils_dll
0x18000743a  call    __delayLoadHelper2
0x18000743f  movdqa  xmm0, [rsp+68h+var_48]
0x180007445  movdqa  xmm1, [rsp+68h+var_38]
0x18000744b  movdqa  xmm2, [rsp+68h+var_28]
0x180007451  movdqa  xmm3, [rsp+68h+var_18]
0x180007457  mov     rcx, [rsp+68h+arg_0]
0x18000745c  mov     rdx, [rsp+68h+arg_8]
0x180007461  mov     r8, [rsp+68h+arg_10]
0x180007469  mov     r9, [rsp+68h+arg_18]
0x180007471  add     rsp, 68h
0x180007475  jmp     short $+2
0x180007477  jmp     rax
```
