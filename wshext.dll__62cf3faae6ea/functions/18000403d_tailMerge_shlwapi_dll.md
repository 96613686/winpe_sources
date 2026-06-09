# __tailMerge_shlwapi_dll

- ea: `0x18000403d`
- end: `0x1800040b6`
- name: `__tailMerge_shlwapi_dll`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800040bc`
- `0x180004116`
- `0x180004128`

## callees

- `0x180002eb0`
- `0x18000403d`

## pseudocode

```c
__int64 __fastcall _tailMerge_shlwapi_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_shlwapi_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000403d  mov     [rsp+arg_0], rcx
0x180004042  mov     [rsp+arg_8], rdx
0x180004047  mov     [rsp+arg_10], r8
0x18000404c  mov     [rsp+arg_18], r9
0x180004051  sub     rsp, 68h
0x180004055  movdqa  [rsp+68h+var_48], xmm0
0x18000405b  movdqa  [rsp+68h+var_38], xmm1
0x180004061  movdqa  [rsp+68h+var_28], xmm2
0x180004067  movdqa  [rsp+68h+var_18], xmm3
0x18000406d  mov     rdx, rax
0x180004070  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_shlwapi_dll
0x180004077  call    __delayLoadHelper2
0x18000407c  movdqa  xmm0, [rsp+68h+var_48]
0x180004082  movdqa  xmm1, [rsp+68h+var_38]
0x180004088  movdqa  xmm2, [rsp+68h+var_28]
0x18000408e  movdqa  xmm3, [rsp+68h+var_18]
0x180004094  mov     rcx, [rsp+68h+arg_0]
0x180004099  mov     rdx, [rsp+68h+arg_8]
0x18000409e  mov     r8, [rsp+68h+arg_10]
0x1800040a6  mov     r9, [rsp+68h+arg_18]
0x1800040ae  add     rsp, 68h
0x1800040b2  jmp     short $+2
0x1800040b4  jmp     rax
```
