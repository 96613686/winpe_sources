# __tailMerge_winhttp_dll

- ea: `0x180001c02`
- end: `0x180001c7b`
- name: `__tailMerge_winhttp_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `13`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001c81`
- `0x180001c93`
- `0x180001ca5`
- `0x180001cb7`
- `0x180001cc9`
- `0x180001cdb`
- `0x180001ced`
- `0x180001cff`
- `0x180001d11`
- `0x180001d23`
- `0x180001d35`
- `0x180001d47`
- `0x180001d59`

## callees

- `0x180001c02`
- `0x180017fd0`

## pseudocode

```c
__int64 __fastcall _tailMerge_winhttp_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_winhttp_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180001c02  mov     [rsp+arg_0], rcx
0x180001c07  mov     [rsp+arg_8], rdx
0x180001c0c  mov     [rsp+arg_10], r8
0x180001c11  mov     [rsp+arg_18], r9
0x180001c16  sub     rsp, 68h
0x180001c1a  movdqa  [rsp+68h+var_48], xmm0
0x180001c20  movdqa  [rsp+68h+var_38], xmm1
0x180001c26  movdqa  [rsp+68h+var_28], xmm2
0x180001c2c  movdqa  [rsp+68h+var_18], xmm3
0x180001c32  mov     rdx, rax
0x180001c35  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_winhttp_dll
0x180001c3c  call    __delayLoadHelper2
0x180001c41  movdqa  xmm0, [rsp+68h+var_48]
0x180001c47  movdqa  xmm1, [rsp+68h+var_38]
0x180001c4d  movdqa  xmm2, [rsp+68h+var_28]
0x180001c53  movdqa  xmm3, [rsp+68h+var_18]
0x180001c59  mov     rcx, [rsp+68h+arg_0]
0x180001c5e  mov     rdx, [rsp+68h+arg_8]
0x180001c63  mov     r8, [rsp+68h+arg_10]
0x180001c6b  mov     r9, [rsp+68h+arg_18]
0x180001c73  add     rsp, 68h
0x180001c77  jmp     short $+2
0x180001c79  jmp     rax
```
