# __tailMerge_ws2_32_dll

- ea: `0x180034f7e`
- end: `0x180034ff7`
- name: `__tailMerge_ws2_32_dll`
- size: `121`
- prototype: ``
- caller_count: `22`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180034ffd`
- `0x18003500f`
- `0x180035021`
- `0x1800350be`
- `0x1800350d0`
- `0x1800350e2`
- `0x1800350f4`
- `0x1800352ef`
- `0x180035301`
- `0x180035313`
- `0x180035325`
- `0x180035337`
- `0x180035349`
- `0x18003535b`
- `0x18003536d`
- `0x18003537f`
- `0x180035391`
- `0x1800353a3`
- `0x1800353b5`
- `0x1800353c7`
- `0x1800353d9`
- `0x1800354be`

## callees

- `0x18002be40`
- `0x180034f7e`

## pseudocode

```c
__int64 __fastcall _tailMerge_ws2_32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ws2_32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180034f7e  mov     [rsp+arg_0], rcx
0x180034f83  mov     [rsp+arg_8], rdx
0x180034f88  mov     [rsp+arg_10], r8
0x180034f8d  mov     [rsp+arg_18], r9
0x180034f92  sub     rsp, 68h
0x180034f96  movdqa  [rsp+68h+var_48], xmm0
0x180034f9c  movdqa  [rsp+68h+var_38], xmm1
0x180034fa2  movdqa  [rsp+68h+var_28], xmm2
0x180034fa8  movdqa  [rsp+68h+var_18], xmm3
0x180034fae  mov     rdx, rax
0x180034fb1  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ws2_32_dll
0x180034fb8  call    __delayLoadHelper2
0x180034fbd  movdqa  xmm0, [rsp+68h+var_48]
0x180034fc3  movdqa  xmm1, [rsp+68h+var_38]
0x180034fc9  movdqa  xmm2, [rsp+68h+var_28]
0x180034fcf  movdqa  xmm3, [rsp+68h+var_18]
0x180034fd5  mov     rcx, [rsp+68h+arg_0]
0x180034fda  mov     rdx, [rsp+68h+arg_8]
0x180034fdf  mov     r8, [rsp+68h+arg_10]
0x180034fe7  mov     r9, [rsp+68h+arg_18]
0x180034fef  add     rsp, 68h
0x180034ff3  jmp     short $+2
0x180034ff5  jmp     rax
```
