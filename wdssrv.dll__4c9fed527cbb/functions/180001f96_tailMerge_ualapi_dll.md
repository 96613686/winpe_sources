# __tailMerge_ualapi_dll

- ea: `0x180001f96`
- end: `0x18000200f`
- name: `__tailMerge_ualapi_dll`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002015`
- `0x180002027`

## callees

- `0x180001f96`
- `0x18001bb20`

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
0x180001f96  mov     [rsp+arg_0], rcx
0x180001f9b  mov     [rsp+arg_8], rdx
0x180001fa0  mov     [rsp+arg_10], r8
0x180001fa5  mov     [rsp+arg_18], r9
0x180001faa  sub     rsp, 68h
0x180001fae  movdqa  [rsp+68h+var_48], xmm0
0x180001fb4  movdqa  [rsp+68h+var_38], xmm1
0x180001fba  movdqa  [rsp+68h+var_28], xmm2
0x180001fc0  movdqa  [rsp+68h+var_18], xmm3
0x180001fc6  mov     rdx, rax
0x180001fc9  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ualapi_dll
0x180001fd0  call    __delayLoadHelper2
0x180001fd5  movdqa  xmm0, [rsp+68h+var_48]
0x180001fdb  movdqa  xmm1, [rsp+68h+var_38]
0x180001fe1  movdqa  xmm2, [rsp+68h+var_28]
0x180001fe7  movdqa  xmm3, [rsp+68h+var_18]
0x180001fed  mov     rcx, [rsp+68h+arg_0]
0x180001ff2  mov     rdx, [rsp+68h+arg_8]
0x180001ff7  mov     r8, [rsp+68h+arg_10]
0x180001fff  mov     r9, [rsp+68h+arg_18]
0x180002007  add     rsp, 68h
0x18000200b  jmp     short $+2
0x18000200d  jmp     rax
```
