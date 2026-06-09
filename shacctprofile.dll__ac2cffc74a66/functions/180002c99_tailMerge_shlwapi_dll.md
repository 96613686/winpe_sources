# __tailMerge_shlwapi_dll

- ea: `0x180002c99`
- end: `0x180002d12`
- name: `__tailMerge_shlwapi_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002d18`
- `0x180002d2a`

## callees

- `0x180002c99`
- `0x1800095f0`

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
0x180002c99  mov     [rsp+arg_0], rcx
0x180002c9e  mov     [rsp+arg_8], rdx
0x180002ca3  mov     [rsp+arg_10], r8
0x180002ca8  mov     [rsp+arg_18], r9
0x180002cad  sub     rsp, 68h
0x180002cb1  movdqa  [rsp+68h+var_48], xmm0
0x180002cb7  movdqa  [rsp+68h+var_38], xmm1
0x180002cbd  movdqa  [rsp+68h+var_28], xmm2
0x180002cc3  movdqa  [rsp+68h+var_18], xmm3
0x180002cc9  mov     rdx, rax
0x180002ccc  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_shlwapi_dll
0x180002cd3  call    __delayLoadHelper2
0x180002cd8  movdqa  xmm0, [rsp+68h+var_48]
0x180002cde  movdqa  xmm1, [rsp+68h+var_38]
0x180002ce4  movdqa  xmm2, [rsp+68h+var_28]
0x180002cea  movdqa  xmm3, [rsp+68h+var_18]
0x180002cf0  mov     rcx, [rsp+68h+arg_0]
0x180002cf5  mov     rdx, [rsp+68h+arg_8]
0x180002cfa  mov     r8, [rsp+68h+arg_10]
0x180002d02  mov     r9, [rsp+68h+arg_18]
0x180002d0a  add     rsp, 68h
0x180002d0e  jmp     short $+2
0x180002d10  jmp     rax
```
