# __tailMerge_shlwapi_dll

- ea: `0x18000aabc`
- end: `0x18000ab35`
- name: `__tailMerge_shlwapi_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000ab3b`

## callees

- `0x180006050`
- `0x18000aabc`

## pseudocode

```c
__int64 __fastcall _tailMerge_shlwapi_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_shlwapi_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000aabc  mov     [rsp+arg_0], rcx
0x18000aac1  mov     [rsp+arg_8], rdx
0x18000aac6  mov     [rsp+arg_10], r8
0x18000aacb  mov     [rsp+arg_18], r9
0x18000aad0  sub     rsp, 68h
0x18000aad4  movdqa  [rsp+68h+var_48], xmm0
0x18000aada  movdqa  [rsp+68h+var_38], xmm1
0x18000aae0  movdqa  [rsp+68h+var_28], xmm2
0x18000aae6  movdqa  [rsp+68h+var_18], xmm3
0x18000aaec  mov     rdx, rax
0x18000aaef  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_shlwapi_dll
0x18000aaf6  call    __delayLoadHelper2
0x18000aafb  movdqa  xmm0, [rsp+68h+var_48]
0x18000ab01  movdqa  xmm1, [rsp+68h+var_38]
0x18000ab07  movdqa  xmm2, [rsp+68h+var_28]
0x18000ab0d  movdqa  xmm3, [rsp+68h+var_18]
0x18000ab13  mov     rcx, [rsp+68h+arg_0]
0x18000ab18  mov     rdx, [rsp+68h+arg_8]
0x18000ab1d  mov     r8, [rsp+68h+arg_10]
0x18000ab25  mov     r9, [rsp+68h+arg_18]
0x18000ab2d  add     rsp, 68h
0x18000ab31  jmp     short $+2
0x18000ab33  jmp     rax
```
