# __tailMerge_ncrypt_dll

- ea: `0x180002147`
- end: `0x1800021c0`
- name: `__tailMerge_ncrypt_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800021c6`
- `0x1800021d8`
- `0x1800021ea`
- `0x1800021fc`

## callees

- `0x180002147`
- `0x18002ce10`

## pseudocode

```c
__int64 __fastcall _tailMerge_ncrypt_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_ncrypt_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002147  mov     [rsp+arg_0], rcx
0x18000214c  mov     [rsp+arg_8], rdx
0x180002151  mov     [rsp+arg_10], r8
0x180002156  mov     [rsp+arg_18], r9
0x18000215b  sub     rsp, 68h
0x18000215f  movdqa  [rsp+68h+var_48], xmm0
0x180002165  movdqa  [rsp+68h+var_38], xmm1
0x18000216b  movdqa  [rsp+68h+var_28], xmm2
0x180002171  movdqa  [rsp+68h+var_18], xmm3
0x180002177  mov     rdx, rax
0x18000217a  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ncrypt_dll
0x180002181  call    __delayLoadHelper2
0x180002186  movdqa  xmm0, [rsp+68h+var_48]
0x18000218c  movdqa  xmm1, [rsp+68h+var_38]
0x180002192  movdqa  xmm2, [rsp+68h+var_28]
0x180002198  movdqa  xmm3, [rsp+68h+var_18]
0x18000219e  mov     rcx, [rsp+68h+arg_0]
0x1800021a3  mov     rdx, [rsp+68h+arg_8]
0x1800021a8  mov     r8, [rsp+68h+arg_10]
0x1800021b0  mov     r9, [rsp+68h+arg_18]
0x1800021b8  add     rsp, 68h
0x1800021bc  jmp     short $+2
0x1800021be  jmp     rax
```
