# __tailMerge_rpcrt4_dll

- ea: `0x180002b86`
- end: `0x180002bff`
- name: `__tailMerge_rpcrt4_dll`
- size: `121`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002c05`
- `0x180002c2c`
- `0x180002c3e`
- `0x180002c50`

## callees

- `0x180001850`
- `0x180002b86`

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
0x180002b86  mov     [rsp+arg_0], rcx
0x180002b8b  mov     [rsp+arg_8], rdx
0x180002b90  mov     [rsp+arg_10], r8
0x180002b95  mov     [rsp+arg_18], r9
0x180002b9a  sub     rsp, 68h
0x180002b9e  movdqa  [rsp+68h+var_48], xmm0
0x180002ba4  movdqa  [rsp+68h+var_38], xmm1
0x180002baa  movdqa  [rsp+68h+var_28], xmm2
0x180002bb0  movdqa  [rsp+68h+var_18], xmm3
0x180002bb6  mov     rdx, rax
0x180002bb9  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_rpcrt4_dll
0x180002bc0  call    __delayLoadHelper2
0x180002bc5  movdqa  xmm0, [rsp+68h+var_48]
0x180002bcb  movdqa  xmm1, [rsp+68h+var_38]
0x180002bd1  movdqa  xmm2, [rsp+68h+var_28]
0x180002bd7  movdqa  xmm3, [rsp+68h+var_18]
0x180002bdd  mov     rcx, [rsp+68h+arg_0]
0x180002be2  mov     rdx, [rsp+68h+arg_8]
0x180002be7  mov     r8, [rsp+68h+arg_10]
0x180002bef  mov     r9, [rsp+68h+arg_18]
0x180002bf7  add     rsp, 68h
0x180002bfb  jmp     short $+2
0x180002bfd  jmp     rax
```
