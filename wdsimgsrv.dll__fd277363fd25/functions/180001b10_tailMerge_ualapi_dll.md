# __tailMerge_ualapi_dll

- ea: `0x180001b10`
- end: `0x180001b89`
- name: `__tailMerge_ualapi_dll`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001b8f`
- `0x180001ba1`
- `0x180001bb3`

## callees

- `0x180001b10`
- `0x180015ba0`

## pseudocode

```c
__int64 __fastcall _tailMerge_ualapi_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  char *v4; // rax
  FARPROC Helper2; // rax

  Helper2 = _delayLoadHelper2((const ImgDelayDescr *)&_DELAY_IMPORT_DESCRIPTOR_ualapi_dll, v4);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64))Helper2)(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180001b10  mov     [rsp+arg_0], rcx
0x180001b15  mov     [rsp+arg_8], rdx
0x180001b1a  mov     [rsp+arg_10], r8
0x180001b1f  mov     [rsp+arg_18], r9
0x180001b24  sub     rsp, 68h
0x180001b28  movdqa  [rsp+68h+var_48], xmm0
0x180001b2e  movdqa  [rsp+68h+var_38], xmm1
0x180001b34  movdqa  [rsp+68h+var_28], xmm2
0x180001b3a  movdqa  [rsp+68h+var_18], xmm3
0x180001b40  mov     rdx, rax
0x180001b43  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ualapi_dll
0x180001b4a  call    __delayLoadHelper2
0x180001b4f  movdqa  xmm0, [rsp+68h+var_48]
0x180001b55  movdqa  xmm1, [rsp+68h+var_38]
0x180001b5b  movdqa  xmm2, [rsp+68h+var_28]
0x180001b61  movdqa  xmm3, [rsp+68h+var_18]
0x180001b67  mov     rcx, [rsp+68h+arg_0]
0x180001b6c  mov     rdx, [rsp+68h+arg_8]
0x180001b71  mov     r8, [rsp+68h+arg_10]
0x180001b79  mov     r9, [rsp+68h+arg_18]
0x180001b81  add     rsp, 68h
0x180001b85  jmp     short $+2
0x180001b87  jmp     rax
```
