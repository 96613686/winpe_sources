# __tailMerge_dhcpsapi_dll

- ea: `0x180001f30`
- end: `0x180001fa9`
- name: `__tailMerge_dhcpsapi_dll`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001faf`
- `0x180001fc1`

## callees

- `0x180001f30`
- `0x180011470`

## pseudocode

```c
__int64 __fastcall _tailMerge_dhcpsapi_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  char *v4; // rax
  FARPROC Helper2; // rax

  Helper2 = _delayLoadHelper2((const ImgDelayDescr *)&_DELAY_IMPORT_DESCRIPTOR_dhcpsapi_dll, v4);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64))Helper2)(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180001f30  mov     [rsp+arg_0], rcx
0x180001f35  mov     [rsp+arg_8], rdx
0x180001f3a  mov     [rsp+arg_10], r8
0x180001f3f  mov     [rsp+arg_18], r9
0x180001f44  sub     rsp, 68h
0x180001f48  movdqa  [rsp+68h+var_48], xmm0
0x180001f4e  movdqa  [rsp+68h+var_38], xmm1
0x180001f54  movdqa  [rsp+68h+var_28], xmm2
0x180001f5a  movdqa  [rsp+68h+var_18], xmm3
0x180001f60  mov     rdx, rax
0x180001f63  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_dhcpsapi_dll
0x180001f6a  call    __delayLoadHelper2
0x180001f6f  movdqa  xmm0, [rsp+68h+var_48]
0x180001f75  movdqa  xmm1, [rsp+68h+var_38]
0x180001f7b  movdqa  xmm2, [rsp+68h+var_28]
0x180001f81  movdqa  xmm3, [rsp+68h+var_18]
0x180001f87  mov     rcx, [rsp+68h+arg_0]
0x180001f8c  mov     rdx, [rsp+68h+arg_8]
0x180001f91  mov     r8, [rsp+68h+arg_10]
0x180001f99  mov     r9, [rsp+68h+arg_18]
0x180001fa1  add     rsp, 68h
0x180001fa5  jmp     short $+2
0x180001fa7  jmp     rax
```
