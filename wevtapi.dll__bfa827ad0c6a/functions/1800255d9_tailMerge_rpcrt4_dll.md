# __tailMerge_rpcrt4_dll

- ea: `0x1800255d9`
- end: `0x180025652`
- name: `__tailMerge_rpcrt4_dll`
- size: `121`
- prototype: ``
- caller_count: `12`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180025658`
- `0x18002566a`
- `0x18002567c`
- `0x18002568e`
- `0x1800256a0`
- `0x1800256b2`
- `0x1800256c4`
- `0x1800256d6`
- `0x1800256e8`
- `0x1800256fa`
- `0x1800257a9`
- `0x1800257bb`

## callees

- `0x18001d4b0`
- `0x1800255d9`

## pseudocode

```c
__int64 __fastcall _tailMerge_rpcrt4_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_rpcrt4_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800255d9  mov     [rsp+arg_0], rcx
0x1800255de  mov     [rsp+arg_8], rdx
0x1800255e3  mov     [rsp+arg_10], r8
0x1800255e8  mov     [rsp+arg_18], r9
0x1800255ed  sub     rsp, 68h
0x1800255f1  movdqa  [rsp+68h+var_48], xmm0
0x1800255f7  movdqa  [rsp+68h+var_38], xmm1
0x1800255fd  movdqa  [rsp+68h+var_28], xmm2
0x180025603  movdqa  [rsp+68h+var_18], xmm3
0x180025609  mov     rdx, rax
0x18002560c  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_rpcrt4_dll
0x180025613  call    __delayLoadHelper2
0x180025618  movdqa  xmm0, [rsp+68h+var_48]
0x18002561e  movdqa  xmm1, [rsp+68h+var_38]
0x180025624  movdqa  xmm2, [rsp+68h+var_28]
0x18002562a  movdqa  xmm3, [rsp+68h+var_18]
0x180025630  mov     rcx, [rsp+68h+arg_0]
0x180025635  mov     rdx, [rsp+68h+arg_8]
0x18002563a  mov     r8, [rsp+68h+arg_10]
0x180025642  mov     r9, [rsp+68h+arg_18]
0x18002564a  add     rsp, 68h
0x18002564e  jmp     short $+2
0x180025650  jmp     rax
```
