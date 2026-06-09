# __tailMerge_crypt32_dll

- ea: `0x180001e07`
- end: `0x180001e80`
- name: `__tailMerge_crypt32_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001e86`

## callees

- `0x180001e07`
- `0x18000b9e0`

## pseudocode

```c
__int64 __fastcall _tailMerge_crypt32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_crypt32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180001e07  mov     [rsp+arg_0], rcx
0x180001e0c  mov     [rsp+arg_8], rdx
0x180001e11  mov     [rsp+arg_10], r8
0x180001e16  mov     [rsp+arg_18], r9
0x180001e1b  sub     rsp, 68h
0x180001e1f  movdqa  [rsp+68h+var_48], xmm0
0x180001e25  movdqa  [rsp+68h+var_38], xmm1
0x180001e2b  movdqa  [rsp+68h+var_28], xmm2
0x180001e31  movdqa  [rsp+68h+var_18], xmm3
0x180001e37  mov     rdx, rax
0x180001e3a  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_crypt32_dll
0x180001e41  call    __delayLoadHelper2
0x180001e46  movdqa  xmm0, [rsp+68h+var_48]
0x180001e4c  movdqa  xmm1, [rsp+68h+var_38]
0x180001e52  movdqa  xmm2, [rsp+68h+var_28]
0x180001e58  movdqa  xmm3, [rsp+68h+var_18]
0x180001e5e  mov     rcx, [rsp+68h+arg_0]
0x180001e63  mov     rdx, [rsp+68h+arg_8]
0x180001e68  mov     r8, [rsp+68h+arg_10]
0x180001e70  mov     r9, [rsp+68h+arg_18]
0x180001e78  add     rsp, 68h
0x180001e7c  jmp     short $+2
0x180001e7e  jmp     rax
```
