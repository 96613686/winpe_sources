# __tailMerge_rpcrt4_dll

- ea: `0x140008a07`
- end: `0x140008a80`
- name: `__tailMerge_rpcrt4_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `10`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140008a86`
- `0x140008b23`
- `0x140008b35`
- `0x140008b47`
- `0x140008b59`
- `0x140008b6b`
- `0x140008b7d`
- `0x140008b8f`
- `0x140008bb3`
- `0x140008bc5`

## callees

- `0x140006020`
- `0x140008a07`

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
0x140008a07  mov     [rsp+arg_0], rcx
0x140008a0c  mov     [rsp+arg_8], rdx
0x140008a11  mov     [rsp+arg_10], r8
0x140008a16  mov     [rsp+arg_18], r9
0x140008a1b  sub     rsp, 68h
0x140008a1f  movdqa  [rsp+68h+var_48], xmm0
0x140008a25  movdqa  [rsp+68h+var_38], xmm1
0x140008a2b  movdqa  [rsp+68h+var_28], xmm2
0x140008a31  movdqa  [rsp+68h+var_18], xmm3
0x140008a37  mov     rdx, rax
0x140008a3a  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_rpcrt4_dll
0x140008a41  call    __delayLoadHelper2
0x140008a46  movdqa  xmm0, [rsp+68h+var_48]
0x140008a4c  movdqa  xmm1, [rsp+68h+var_38]
0x140008a52  movdqa  xmm2, [rsp+68h+var_28]
0x140008a58  movdqa  xmm3, [rsp+68h+var_18]
0x140008a5e  mov     rcx, [rsp+68h+arg_0]
0x140008a63  mov     rdx, [rsp+68h+arg_8]
0x140008a68  mov     r8, [rsp+68h+arg_10]
0x140008a70  mov     r9, [rsp+68h+arg_18]
0x140008a78  add     rsp, 68h
0x140008a7c  jmp     short $+2
0x140008a7e  jmp     rax
```
