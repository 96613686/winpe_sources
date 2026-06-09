# __tailMerge_rpcrt4_dll

- ea: `0x180001b77`
- end: `0x180001bf0`
- name: `__tailMerge_rpcrt4_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001bf6`

## callees

- `0x180001b77`
- `0x180017fd0`

## pseudocode

```c
__int64 __fastcall _tailMerge_rpcrt4_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_rpcrt4_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180001b77  mov     [rsp+arg_0], rcx
0x180001b7c  mov     [rsp+arg_8], rdx
0x180001b81  mov     [rsp+arg_10], r8
0x180001b86  mov     [rsp+arg_18], r9
0x180001b8b  sub     rsp, 68h
0x180001b8f  movdqa  [rsp+68h+var_48], xmm0
0x180001b95  movdqa  [rsp+68h+var_38], xmm1
0x180001b9b  movdqa  [rsp+68h+var_28], xmm2
0x180001ba1  movdqa  [rsp+68h+var_18], xmm3
0x180001ba7  mov     rdx, rax
0x180001baa  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_rpcrt4_dll
0x180001bb1  call    __delayLoadHelper2
0x180001bb6  movdqa  xmm0, [rsp+68h+var_48]
0x180001bbc  movdqa  xmm1, [rsp+68h+var_38]
0x180001bc2  movdqa  xmm2, [rsp+68h+var_28]
0x180001bc8  movdqa  xmm3, [rsp+68h+var_18]
0x180001bce  mov     rcx, [rsp+68h+arg_0]
0x180001bd3  mov     rdx, [rsp+68h+arg_8]
0x180001bd8  mov     r8, [rsp+68h+arg_10]
0x180001be0  mov     r9, [rsp+68h+arg_18]
0x180001be8  add     rsp, 68h
0x180001bec  jmp     short $+2
0x180001bee  jmp     rax
```
