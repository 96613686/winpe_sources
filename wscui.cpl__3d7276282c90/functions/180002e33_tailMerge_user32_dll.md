# __tailMerge_user32_dll

- ea: `0x180002e33`
- end: `0x180002eac`
- name: `__tailMerge_user32_dll`
- size: `121`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002eb2`
- `0x180002ec4`
- `0x180002ed6`
- `0x180002ee8`
- `0x180002efa`
- `0x180002f0c`
- `0x180002f1e`
- `0x180003573`

## callees

- `0x180001850`
- `0x180002e33`

## pseudocode

```c
__int64 __fastcall _tailMerge_user32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_user32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002e33  mov     [rsp+arg_0], rcx
0x180002e38  mov     [rsp+arg_8], rdx
0x180002e3d  mov     [rsp+arg_10], r8
0x180002e42  mov     [rsp+arg_18], r9
0x180002e47  sub     rsp, 68h
0x180002e4b  movdqa  [rsp+68h+var_48], xmm0
0x180002e51  movdqa  [rsp+68h+var_38], xmm1
0x180002e57  movdqa  [rsp+68h+var_28], xmm2
0x180002e5d  movdqa  [rsp+68h+var_18], xmm3
0x180002e63  mov     rdx, rax
0x180002e66  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_user32_dll
0x180002e6d  call    __delayLoadHelper2
0x180002e72  movdqa  xmm0, [rsp+68h+var_48]
0x180002e78  movdqa  xmm1, [rsp+68h+var_38]
0x180002e7e  movdqa  xmm2, [rsp+68h+var_28]
0x180002e84  movdqa  xmm3, [rsp+68h+var_18]
0x180002e8a  mov     rcx, [rsp+68h+arg_0]
0x180002e8f  mov     rdx, [rsp+68h+arg_8]
0x180002e94  mov     r8, [rsp+68h+arg_10]
0x180002e9c  mov     r9, [rsp+68h+arg_18]
0x180002ea4  add     rsp, 68h
0x180002ea8  jmp     short $+2
0x180002eaa  jmp     rax
```
