# __tailMerge_powrprof_dll

- ea: `0x180001e14`
- end: `0x180001e8d`
- name: `__tailMerge_powrprof_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001e93`

## callees

- `0x180001e14`
- `0x180017fd0`

## pseudocode

```c
__int64 __fastcall _tailMerge_powrprof_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_powrprof_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180001e14  mov     [rsp+arg_0], rcx
0x180001e19  mov     [rsp+arg_8], rdx
0x180001e1e  mov     [rsp+arg_10], r8
0x180001e23  mov     [rsp+arg_18], r9
0x180001e28  sub     rsp, 68h
0x180001e2c  movdqa  [rsp+68h+var_48], xmm0
0x180001e32  movdqa  [rsp+68h+var_38], xmm1
0x180001e38  movdqa  [rsp+68h+var_28], xmm2
0x180001e3e  movdqa  [rsp+68h+var_18], xmm3
0x180001e44  mov     rdx, rax
0x180001e47  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_powrprof_dll
0x180001e4e  call    __delayLoadHelper2
0x180001e53  movdqa  xmm0, [rsp+68h+var_48]
0x180001e59  movdqa  xmm1, [rsp+68h+var_38]
0x180001e5f  movdqa  xmm2, [rsp+68h+var_28]
0x180001e65  movdqa  xmm3, [rsp+68h+var_18]
0x180001e6b  mov     rcx, [rsp+68h+arg_0]
0x180001e70  mov     rdx, [rsp+68h+arg_8]
0x180001e75  mov     r8, [rsp+68h+arg_10]
0x180001e7d  mov     r9, [rsp+68h+arg_18]
0x180001e85  add     rsp, 68h
0x180001e89  jmp     short $+2
0x180001e8b  jmp     rax
```
