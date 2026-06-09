# __tailMerge_sspicli_dll

- ea: `0x18000c742`
- end: `0x18000c7bb`
- name: `__tailMerge_sspicli_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000c7c1`

## callees

- `0x18000b110`
- `0x18000c742`

## pseudocode

```c
__int64 __fastcall _tailMerge_sspicli_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_sspicli_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000c742  mov     [rsp+arg_0], rcx
0x18000c747  mov     [rsp+arg_8], rdx
0x18000c74c  mov     [rsp+arg_10], r8
0x18000c751  mov     [rsp+arg_18], r9
0x18000c756  sub     rsp, 68h
0x18000c75a  movdqa  [rsp+68h+var_48], xmm0
0x18000c760  movdqa  [rsp+68h+var_38], xmm1
0x18000c766  movdqa  [rsp+68h+var_28], xmm2
0x18000c76c  movdqa  [rsp+68h+var_18], xmm3
0x18000c772  mov     rdx, rax
0x18000c775  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_sspicli_dll
0x18000c77c  call    __delayLoadHelper2
0x18000c781  movdqa  xmm0, [rsp+68h+var_48]
0x18000c787  movdqa  xmm1, [rsp+68h+var_38]
0x18000c78d  movdqa  xmm2, [rsp+68h+var_28]
0x18000c793  movdqa  xmm3, [rsp+68h+var_18]
0x18000c799  mov     rcx, [rsp+68h+arg_0]
0x18000c79e  mov     rdx, [rsp+68h+arg_8]
0x18000c7a3  mov     r8, [rsp+68h+arg_10]
0x18000c7ab  mov     r9, [rsp+68h+arg_18]
0x18000c7b3  add     rsp, 68h
0x18000c7b7  jmp     short $+2
0x18000c7b9  jmp     rax
```
