# __tailMerge_rpcrt4_dll

- ea: `0x140005bcf`
- end: `0x140005c48`
- name: `__tailMerge_rpcrt4_dll`
- size: `121`
- prototype: ``
- caller_count: `10`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140005c4e`
- `0x140005c60`
- `0x140005dab`
- `0x140005dbd`
- `0x140005dcf`
- `0x140005de1`
- `0x140005df3`
- `0x140005e05`
- `0x140005e17`
- `0x140005e29`

## callees

- `0x140002100`
- `0x140005bcf`

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
0x140005bcf  mov     [rsp+arg_0], rcx
0x140005bd4  mov     [rsp+arg_8], rdx
0x140005bd9  mov     [rsp+arg_10], r8
0x140005bde  mov     [rsp+arg_18], r9
0x140005be3  sub     rsp, 68h
0x140005be7  movdqa  [rsp+68h+var_48], xmm0
0x140005bed  movdqa  [rsp+68h+var_38], xmm1
0x140005bf3  movdqa  [rsp+68h+var_28], xmm2
0x140005bf9  movdqa  [rsp+68h+var_18], xmm3
0x140005bff  mov     rdx, rax
0x140005c02  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_rpcrt4_dll
0x140005c09  call    __delayLoadHelper2
0x140005c0e  movdqa  xmm0, [rsp+68h+var_48]
0x140005c14  movdqa  xmm1, [rsp+68h+var_38]
0x140005c1a  movdqa  xmm2, [rsp+68h+var_28]
0x140005c20  movdqa  xmm3, [rsp+68h+var_18]
0x140005c26  mov     rcx, [rsp+68h+arg_0]
0x140005c2b  mov     rdx, [rsp+68h+arg_8]
0x140005c30  mov     r8, [rsp+68h+arg_10]
0x140005c38  mov     r9, [rsp+68h+arg_18]
0x140005c40  add     rsp, 68h
0x140005c44  jmp     short $+2
0x140005c46  jmp     rax
```
