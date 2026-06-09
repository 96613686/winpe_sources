# __tailMerge_wwapi_dll

- ea: `0x180002a13`
- end: `0x180002a8c`
- name: `__tailMerge_wwapi_dll`
- size: `121`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002a92`
- `0x180002aa4`
- `0x180002ab6`
- `0x180002ac8`
- `0x180002ada`

## callees

- `0x180002a13`
- `0x18001be40`

## pseudocode

```c
__int64 __fastcall _tailMerge_wwapi_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_wwapi_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002a13  mov     [rsp+arg_0], rcx
0x180002a18  mov     [rsp+arg_8], rdx
0x180002a1d  mov     [rsp+arg_10], r8
0x180002a22  mov     [rsp+arg_18], r9
0x180002a27  sub     rsp, 68h
0x180002a2b  movdqa  [rsp+68h+var_48], xmm0
0x180002a31  movdqa  [rsp+68h+var_38], xmm1
0x180002a37  movdqa  [rsp+68h+var_28], xmm2
0x180002a3d  movdqa  [rsp+68h+var_18], xmm3
0x180002a43  mov     rdx, rax
0x180002a46  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_wwapi_dll
0x180002a4d  call    __delayLoadHelper2
0x180002a52  movdqa  xmm0, [rsp+68h+var_48]
0x180002a58  movdqa  xmm1, [rsp+68h+var_38]
0x180002a5e  movdqa  xmm2, [rsp+68h+var_28]
0x180002a64  movdqa  xmm3, [rsp+68h+var_18]
0x180002a6a  mov     rcx, [rsp+68h+arg_0]
0x180002a6f  mov     rdx, [rsp+68h+arg_8]
0x180002a74  mov     r8, [rsp+68h+arg_10]
0x180002a7c  mov     r9, [rsp+68h+arg_18]
0x180002a84  add     rsp, 68h
0x180002a88  jmp     short $+2
0x180002a8a  jmp     rax
```
