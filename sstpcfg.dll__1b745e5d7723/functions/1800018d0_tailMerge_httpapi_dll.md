# __tailMerge_httpapi_dll

- ea: `0x1800018d0`
- end: `0x180001949`
- name: `__tailMerge_httpapi_dll`
- size: `121`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000194f`
- `0x180001961`
- `0x180001973`
- `0x180001985`
- `0x180001997`

## callees

- `0x1800018d0`
- `0x18000ad60`

## pseudocode

```c
__int64 __fastcall _tailMerge_httpapi_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_httpapi_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800018d0  mov     [rsp+arg_0], rcx
0x1800018d5  mov     [rsp+arg_8], rdx
0x1800018da  mov     [rsp+arg_10], r8
0x1800018df  mov     [rsp+arg_18], r9
0x1800018e4  sub     rsp, 68h
0x1800018e8  movdqa  [rsp+68h+var_48], xmm0
0x1800018ee  movdqa  [rsp+68h+var_38], xmm1
0x1800018f4  movdqa  [rsp+68h+var_28], xmm2
0x1800018fa  movdqa  [rsp+68h+var_18], xmm3
0x180001900  mov     rdx, rax
0x180001903  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_httpapi_dll
0x18000190a  call    __delayLoadHelper2
0x18000190f  movdqa  xmm0, [rsp+68h+var_48]
0x180001915  movdqa  xmm1, [rsp+68h+var_38]
0x18000191b  movdqa  xmm2, [rsp+68h+var_28]
0x180001921  movdqa  xmm3, [rsp+68h+var_18]
0x180001927  mov     rcx, [rsp+68h+arg_0]
0x18000192c  mov     rdx, [rsp+68h+arg_8]
0x180001931  mov     r8, [rsp+68h+arg_10]
0x180001939  mov     r9, [rsp+68h+arg_18]
0x180001941  add     rsp, 68h
0x180001945  jmp     short $+2
0x180001947  jmp     rax
```
