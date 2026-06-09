# __tailMerge_userenv_dll

- ea: `0x180002a25`
- end: `0x180002a9e`
- name: `__tailMerge_userenv_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002aa4`

## callees

- `0x180002a25`
- `0x18000da70`

## pseudocode

```c
__int64 __fastcall _tailMerge_userenv_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_userenv_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002a25  mov     [rsp+arg_0], rcx
0x180002a2a  mov     [rsp+arg_8], rdx
0x180002a2f  mov     [rsp+arg_10], r8
0x180002a34  mov     [rsp+arg_18], r9
0x180002a39  sub     rsp, 68h
0x180002a3d  movdqa  [rsp+68h+var_48], xmm0
0x180002a43  movdqa  [rsp+68h+var_38], xmm1
0x180002a49  movdqa  [rsp+68h+var_28], xmm2
0x180002a4f  movdqa  [rsp+68h+var_18], xmm3
0x180002a55  mov     rdx, rax
0x180002a58  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_userenv_dll
0x180002a5f  call    __delayLoadHelper2
0x180002a64  movdqa  xmm0, [rsp+68h+var_48]
0x180002a6a  movdqa  xmm1, [rsp+68h+var_38]
0x180002a70  movdqa  xmm2, [rsp+68h+var_28]
0x180002a76  movdqa  xmm3, [rsp+68h+var_18]
0x180002a7c  mov     rcx, [rsp+68h+arg_0]
0x180002a81  mov     rdx, [rsp+68h+arg_8]
0x180002a86  mov     r8, [rsp+68h+arg_10]
0x180002a8e  mov     r9, [rsp+68h+arg_18]
0x180002a96  add     rsp, 68h
0x180002a9a  jmp     short $+2
0x180002a9c  jmp     rax
```
