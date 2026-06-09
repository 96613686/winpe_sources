# __tailMerge_shell32_dll

- ea: `0x180003f27`
- end: `0x180003fa0`
- name: `__tailMerge_shell32_dll`
- size: `121`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800040ce`
- `0x1800040e0`
- `0x1800040f2`
- `0x180004104`
- `0x180004309`

## callees

- `0x180002eb0`
- `0x180003f27`

## pseudocode

```c
__int64 __fastcall _tailMerge_shell32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_shell32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180003f27  mov     [rsp+arg_0], rcx
0x180003f2c  mov     [rsp+arg_8], rdx
0x180003f31  mov     [rsp+arg_10], r8
0x180003f36  mov     [rsp+arg_18], r9
0x180003f3b  sub     rsp, 68h
0x180003f3f  movdqa  [rsp+68h+var_48], xmm0
0x180003f45  movdqa  [rsp+68h+var_38], xmm1
0x180003f4b  movdqa  [rsp+68h+var_28], xmm2
0x180003f51  movdqa  [rsp+68h+var_18], xmm3
0x180003f57  mov     rdx, rax
0x180003f5a  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_shell32_dll
0x180003f61  call    __delayLoadHelper2
0x180003f66  movdqa  xmm0, [rsp+68h+var_48]
0x180003f6c  movdqa  xmm1, [rsp+68h+var_38]
0x180003f72  movdqa  xmm2, [rsp+68h+var_28]
0x180003f78  movdqa  xmm3, [rsp+68h+var_18]
0x180003f7e  mov     rcx, [rsp+68h+arg_0]
0x180003f83  mov     rdx, [rsp+68h+arg_8]
0x180003f88  mov     r8, [rsp+68h+arg_10]
0x180003f90  mov     r9, [rsp+68h+arg_18]
0x180003f98  add     rsp, 68h
0x180003f9c  jmp     short $+2
0x180003f9e  jmp     rax
```
