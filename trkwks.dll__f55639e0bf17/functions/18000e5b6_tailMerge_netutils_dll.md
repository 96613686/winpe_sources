# __tailMerge_netutils_dll

- ea: `0x18000e5b6`
- end: `0x18000e62f`
- name: `__tailMerge_netutils_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000e635`

## callees

- `0x18000e5b6`
- `0x180010e60`

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
0x18000e5b6  mov     [rsp+arg_0], rcx
0x18000e5bb  mov     [rsp+arg_8], rdx
0x18000e5c0  mov     [rsp+arg_10], r8
0x18000e5c5  mov     [rsp+arg_18], r9
0x18000e5ca  sub     rsp, 68h
0x18000e5ce  movdqa  [rsp+68h+var_48], xmm0
0x18000e5d4  movdqa  [rsp+68h+var_38], xmm1
0x18000e5da  movdqa  [rsp+68h+var_28], xmm2
0x18000e5e0  movdqa  [rsp+68h+var_18], xmm3
0x18000e5e6  mov     rdx, rax
0x18000e5e9  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_netutils_dll
0x18000e5f0  call    __delayLoadHelper2
0x18000e5f5  movdqa  xmm0, [rsp+68h+var_48]
0x18000e5fb  movdqa  xmm1, [rsp+68h+var_38]
0x18000e601  movdqa  xmm2, [rsp+68h+var_28]
0x18000e607  movdqa  xmm3, [rsp+68h+var_18]
0x18000e60d  mov     rcx, [rsp+68h+arg_0]
0x18000e612  mov     rdx, [rsp+68h+arg_8]
0x18000e617  mov     r8, [rsp+68h+arg_10]
0x18000e61f  mov     r9, [rsp+68h+arg_18]
0x18000e627  add     rsp, 68h
0x18000e62b  jmp     short $+2
0x18000e62d  jmp     rax
```
