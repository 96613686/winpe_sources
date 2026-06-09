# __tailMerge_gdi32_dll

- ea: `0x180001c1d`
- end: `0x180001c96`
- name: `__tailMerge_gdi32_dll`
- size: `121`
- prototype: ``
- caller_count: `13`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001c9c`
- `0x180001cae`
- `0x180001cc0`
- `0x180001cd2`
- `0x180001ce4`
- `0x180001cf6`
- `0x180001d08`
- `0x180001d1a`
- `0x180001d2c`
- `0x180001d3e`
- `0x180001d50`
- `0x180001d62`
- `0x180001d74`

## callees

- `0x180001c1d`
- `0x180012d30`

## pseudocode

```c
__int64 __fastcall _tailMerge_gdi32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_gdi32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180001c1d  mov     [rsp+arg_0], rcx
0x180001c22  mov     [rsp+arg_8], rdx
0x180001c27  mov     [rsp+arg_10], r8
0x180001c2c  mov     [rsp+arg_18], r9
0x180001c31  sub     rsp, 68h
0x180001c35  movdqa  [rsp+68h+var_48], xmm0
0x180001c3b  movdqa  [rsp+68h+var_38], xmm1
0x180001c41  movdqa  [rsp+68h+var_28], xmm2
0x180001c47  movdqa  [rsp+68h+var_18], xmm3
0x180001c4d  mov     rdx, rax
0x180001c50  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_gdi32_dll
0x180001c57  call    __delayLoadHelper2
0x180001c5c  movdqa  xmm0, [rsp+68h+var_48]
0x180001c62  movdqa  xmm1, [rsp+68h+var_38]
0x180001c68  movdqa  xmm2, [rsp+68h+var_28]
0x180001c6e  movdqa  xmm3, [rsp+68h+var_18]
0x180001c74  mov     rcx, [rsp+68h+arg_0]
0x180001c79  mov     rdx, [rsp+68h+arg_8]
0x180001c7e  mov     r8, [rsp+68h+arg_10]
0x180001c86  mov     r9, [rsp+68h+arg_18]
0x180001c8e  add     rsp, 68h
0x180001c92  jmp     short $+2
0x180001c94  jmp     rax
```
