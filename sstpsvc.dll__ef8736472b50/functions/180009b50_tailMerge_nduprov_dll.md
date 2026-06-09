# __tailMerge_nduprov_dll

- ea: `0x180009b50`
- end: `0x180009bc9`
- name: `__tailMerge_nduprov_dll`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180009bcf`
- `0x180009be1`
- `0x180009bf3`

## callees

- `0x180007990`
- `0x180009b50`

## pseudocode

```c
__int64 __fastcall _tailMerge_nduprov_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_nduprov_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180009b50  mov     [rsp+arg_0], rcx
0x180009b55  mov     [rsp+arg_8], rdx
0x180009b5a  mov     [rsp+arg_10], r8
0x180009b5f  mov     [rsp+arg_18], r9
0x180009b64  sub     rsp, 68h
0x180009b68  movdqa  [rsp+68h+var_48], xmm0
0x180009b6e  movdqa  [rsp+68h+var_38], xmm1
0x180009b74  movdqa  [rsp+68h+var_28], xmm2
0x180009b7a  movdqa  [rsp+68h+var_18], xmm3
0x180009b80  mov     rdx, rax
0x180009b83  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_nduprov_dll
0x180009b8a  call    __delayLoadHelper2
0x180009b8f  movdqa  xmm0, [rsp+68h+var_48]
0x180009b95  movdqa  xmm1, [rsp+68h+var_38]
0x180009b9b  movdqa  xmm2, [rsp+68h+var_28]
0x180009ba1  movdqa  xmm3, [rsp+68h+var_18]
0x180009ba7  mov     rcx, [rsp+68h+arg_0]
0x180009bac  mov     rdx, [rsp+68h+arg_8]
0x180009bb1  mov     r8, [rsp+68h+arg_10]
0x180009bb9  mov     r9, [rsp+68h+arg_18]
0x180009bc1  add     rsp, 68h
0x180009bc5  jmp     short $+2
0x180009bc7  jmp     rax
```
