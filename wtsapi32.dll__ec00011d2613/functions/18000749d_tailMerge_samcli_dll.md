# __tailMerge_samcli_dll

- ea: `0x18000749d`
- end: `0x180007516`
- name: `__tailMerge_samcli_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000751c`

## callees

- `0x180004ab0`
- `0x18000749d`

## pseudocode

```c
__int64 __fastcall _tailMerge_samcli_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_samcli_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000749d  mov     [rsp+arg_0], rcx
0x1800074a2  mov     [rsp+arg_8], rdx
0x1800074a7  mov     [rsp+arg_10], r8
0x1800074ac  mov     [rsp+arg_18], r9
0x1800074b1  sub     rsp, 68h
0x1800074b5  movdqa  [rsp+68h+var_48], xmm0
0x1800074bb  movdqa  [rsp+68h+var_38], xmm1
0x1800074c1  movdqa  [rsp+68h+var_28], xmm2
0x1800074c7  movdqa  [rsp+68h+var_18], xmm3
0x1800074cd  mov     rdx, rax
0x1800074d0  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_samcli_dll
0x1800074d7  call    __delayLoadHelper2
0x1800074dc  movdqa  xmm0, [rsp+68h+var_48]
0x1800074e2  movdqa  xmm1, [rsp+68h+var_38]
0x1800074e8  movdqa  xmm2, [rsp+68h+var_28]
0x1800074ee  movdqa  xmm3, [rsp+68h+var_18]
0x1800074f4  mov     rcx, [rsp+68h+arg_0]
0x1800074f9  mov     rdx, [rsp+68h+arg_8]
0x1800074fe  mov     r8, [rsp+68h+arg_10]
0x180007506  mov     r9, [rsp+68h+arg_18]
0x18000750e  add     rsp, 68h
0x180007512  jmp     short $+2
0x180007514  jmp     rax
```
