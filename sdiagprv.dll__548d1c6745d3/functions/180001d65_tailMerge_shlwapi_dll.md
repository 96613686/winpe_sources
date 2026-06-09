# __tailMerge_shlwapi_dll

- ea: `0x180001d65`
- end: `0x180001dde`
- name: `__tailMerge_shlwapi_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001de4`

## callees

- `0x180001d65`
- `0x180017fd0`

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
0x180001d65  mov     [rsp+arg_0], rcx
0x180001d6a  mov     [rsp+arg_8], rdx
0x180001d6f  mov     [rsp+arg_10], r8
0x180001d74  mov     [rsp+arg_18], r9
0x180001d79  sub     rsp, 68h
0x180001d7d  movdqa  [rsp+68h+var_48], xmm0
0x180001d83  movdqa  [rsp+68h+var_38], xmm1
0x180001d89  movdqa  [rsp+68h+var_28], xmm2
0x180001d8f  movdqa  [rsp+68h+var_18], xmm3
0x180001d95  mov     rdx, rax
0x180001d98  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_shlwapi_dll
0x180001d9f  call    __delayLoadHelper2
0x180001da4  movdqa  xmm0, [rsp+68h+var_48]
0x180001daa  movdqa  xmm1, [rsp+68h+var_38]
0x180001db0  movdqa  xmm2, [rsp+68h+var_28]
0x180001db6  movdqa  xmm3, [rsp+68h+var_18]
0x180001dbc  mov     rcx, [rsp+68h+arg_0]
0x180001dc1  mov     rdx, [rsp+68h+arg_8]
0x180001dc6  mov     r8, [rsp+68h+arg_10]
0x180001dce  mov     r9, [rsp+68h+arg_18]
0x180001dd6  add     rsp, 68h
0x180001dda  jmp     short $+2
0x180001ddc  jmp     rax
```
