# __tailMerge_iphlpapi_dll

- ea: `0x18000e4a0`
- end: `0x18000e519`
- name: `__tailMerge_iphlpapi_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000e51f`
- `0x18000e531`
- `0x18000e543`
- `0x18000e5e0`
- `0x18000e5f2`

## callees

- `0x180007910`
- `0x18000e4a0`

## pseudocode

```c
__int64 __fastcall _tailMerge_iphlpapi_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_iphlpapi_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000e4a0  mov     [rsp+arg_0], rcx
0x18000e4a5  mov     [rsp+arg_8], rdx
0x18000e4aa  mov     [rsp+arg_10], r8
0x18000e4af  mov     [rsp+arg_18], r9
0x18000e4b4  sub     rsp, 68h
0x18000e4b8  movdqa  [rsp+68h+var_48], xmm0
0x18000e4be  movdqa  [rsp+68h+var_38], xmm1
0x18000e4c4  movdqa  [rsp+68h+var_28], xmm2
0x18000e4ca  movdqa  [rsp+68h+var_18], xmm3
0x18000e4d0  mov     rdx, rax
0x18000e4d3  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_iphlpapi_dll
0x18000e4da  call    __delayLoadHelper2
0x18000e4df  movdqa  xmm0, [rsp+68h+var_48]
0x18000e4e5  movdqa  xmm1, [rsp+68h+var_38]
0x18000e4eb  movdqa  xmm2, [rsp+68h+var_28]
0x18000e4f1  movdqa  xmm3, [rsp+68h+var_18]
0x18000e4f7  mov     rcx, [rsp+68h+arg_0]
0x18000e4fc  mov     rdx, [rsp+68h+arg_8]
0x18000e501  mov     r8, [rsp+68h+arg_10]
0x18000e509  mov     r9, [rsp+68h+arg_18]
0x18000e511  add     rsp, 68h
0x18000e515  jmp     short $+2
0x18000e517  jmp     rax
```
