# __tailMerge_setupapi_dll

- ea: `0x180001d18`
- end: `0x180001d91`
- name: `__tailMerge_setupapi_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x180001d97`
- `0x180001da9`
- `0x180001dbb`
- `0x180001dcd`

## callees

- `0x180001d18`
- `0x18001b110`

## pseudocode

```c
__int64 __fastcall _tailMerge_setupapi_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  FARPROC *v4; // rax
  FARPROC Helper2; // rax

  Helper2 = _delayLoadHelper2((unsigned int *)&_DELAY_IMPORT_DESCRIPTOR_setupapi_dll, v4);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64))Helper2)(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180001d18  mov     [rsp+arg_0], rcx
0x180001d1d  mov     [rsp+arg_8], rdx
0x180001d22  mov     [rsp+arg_10], r8
0x180001d27  mov     [rsp+arg_18], r9
0x180001d2c  sub     rsp, 68h
0x180001d30  movdqa  [rsp+68h+var_48], xmm0
0x180001d36  movdqa  [rsp+68h+var_38], xmm1
0x180001d3c  movdqa  [rsp+68h+var_28], xmm2
0x180001d42  movdqa  [rsp+68h+var_18], xmm3
0x180001d48  mov     rdx, rax
0x180001d4b  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_setupapi_dll
0x180001d52  call    __delayLoadHelper2
0x180001d57  movdqa  xmm0, [rsp+68h+var_48]
0x180001d5d  movdqa  xmm1, [rsp+68h+var_38]
0x180001d63  movdqa  xmm2, [rsp+68h+var_28]
0x180001d69  movdqa  xmm3, [rsp+68h+var_18]
0x180001d6f  mov     rcx, [rsp+68h+arg_0]
0x180001d74  mov     rdx, [rsp+68h+arg_8]
0x180001d79  mov     r8, [rsp+68h+arg_10]
0x180001d81  mov     r9, [rsp+68h+arg_18]
0x180001d89  add     rsp, 68h
0x180001d8d  jmp     short $+2
0x180001d8f  jmp     rax
```
