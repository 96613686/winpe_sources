# __tailMerge_dsparse_dll

- ea: `0x18000733c`
- end: `0x1800073b5`
- name: `__tailMerge_dsparse_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800073bb`

## callees

- `0x1800054c0`
- `0x18000733c`

## pseudocode

```c
__int64 __fastcall _tailMerge_dsparse_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_dsparse_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000733c  mov     [rsp+arg_0], rcx
0x180007341  mov     [rsp+arg_8], rdx
0x180007346  mov     [rsp+arg_10], r8
0x18000734b  mov     [rsp+arg_18], r9
0x180007350  sub     rsp, 68h
0x180007354  movdqa  [rsp+68h+var_48], xmm0
0x18000735a  movdqa  [rsp+68h+var_38], xmm1
0x180007360  movdqa  [rsp+68h+var_28], xmm2
0x180007366  movdqa  [rsp+68h+var_18], xmm3
0x18000736c  mov     rdx, rax
0x18000736f  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_dsparse_dll
0x180007376  call    __delayLoadHelper2
0x18000737b  movdqa  xmm0, [rsp+68h+var_48]
0x180007381  movdqa  xmm1, [rsp+68h+var_38]
0x180007387  movdqa  xmm2, [rsp+68h+var_28]
0x18000738d  movdqa  xmm3, [rsp+68h+var_18]
0x180007393  mov     rcx, [rsp+68h+arg_0]
0x180007398  mov     rdx, [rsp+68h+arg_8]
0x18000739d  mov     r8, [rsp+68h+arg_10]
0x1800073a5  mov     r9, [rsp+68h+arg_18]
0x1800073ad  add     rsp, 68h
0x1800073b1  jmp     short $+2
0x1800073b3  jmp     rax
```
