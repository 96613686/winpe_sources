# __tailMerge_wintrust_dll

- ea: `0x180002dba`
- end: `0x180002e33`
- name: `__tailMerge_wintrust_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003561`

## callees

- `0x180001850`
- `0x180002dba`

## pseudocode

```c
__int64 __fastcall _tailMerge_wintrust_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_wintrust_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002dba  mov     [rsp+arg_0], rcx
0x180002dbf  mov     [rsp+arg_8], rdx
0x180002dc4  mov     [rsp+arg_10], r8
0x180002dc9  mov     [rsp+arg_18], r9
0x180002dce  sub     rsp, 68h
0x180002dd2  movdqa  [rsp+68h+var_48], xmm0
0x180002dd8  movdqa  [rsp+68h+var_38], xmm1
0x180002dde  movdqa  [rsp+68h+var_28], xmm2
0x180002de4  movdqa  [rsp+68h+var_18], xmm3
0x180002dea  mov     rdx, rax
0x180002ded  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_wintrust_dll
0x180002df4  call    __delayLoadHelper2
0x180002df9  movdqa  xmm0, [rsp+68h+var_48]
0x180002dff  movdqa  xmm1, [rsp+68h+var_38]
0x180002e05  movdqa  xmm2, [rsp+68h+var_28]
0x180002e0b  movdqa  xmm3, [rsp+68h+var_18]
0x180002e11  mov     rcx, [rsp+68h+arg_0]
0x180002e16  mov     rdx, [rsp+68h+arg_8]
0x180002e1b  mov     r8, [rsp+68h+arg_10]
0x180002e23  mov     r9, [rsp+68h+arg_18]
0x180002e2b  add     rsp, 68h
0x180002e2f  jmp     short $+2
0x180002e31  jmp     rax
```
