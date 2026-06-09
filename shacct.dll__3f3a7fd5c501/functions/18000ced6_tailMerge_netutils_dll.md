# __tailMerge_netutils_dll

- ea: `0x18000ced6`
- end: `0x18000cf4f`
- name: `__tailMerge_netutils_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000cf55`

## callees

- `0x180008bd0`
- `0x18000ced6`

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
0x18000ced6  mov     [rsp+arg_0], rcx
0x18000cedb  mov     [rsp+arg_8], rdx
0x18000cee0  mov     [rsp+arg_10], r8
0x18000cee5  mov     [rsp+arg_18], r9
0x18000ceea  sub     rsp, 68h
0x18000ceee  movdqa  [rsp+68h+var_48], xmm0
0x18000cef4  movdqa  [rsp+68h+var_38], xmm1
0x18000cefa  movdqa  [rsp+68h+var_28], xmm2
0x18000cf00  movdqa  [rsp+68h+var_18], xmm3
0x18000cf06  mov     rdx, rax
0x18000cf09  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_netutils_dll
0x18000cf10  call    __delayLoadHelper2
0x18000cf15  movdqa  xmm0, [rsp+68h+var_48]
0x18000cf1b  movdqa  xmm1, [rsp+68h+var_38]
0x18000cf21  movdqa  xmm2, [rsp+68h+var_28]
0x18000cf27  movdqa  xmm3, [rsp+68h+var_18]
0x18000cf2d  mov     rcx, [rsp+68h+arg_0]
0x18000cf32  mov     rdx, [rsp+68h+arg_8]
0x18000cf37  mov     r8, [rsp+68h+arg_10]
0x18000cf3f  mov     r9, [rsp+68h+arg_18]
0x18000cf47  add     rsp, 68h
0x18000cf4b  jmp     short $+2
0x18000cf4d  jmp     rax
```
