# __tailMerge_mi_dll

- ea: `0x180002aeb`
- end: `0x180002b64`
- name: `__tailMerge_mi_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002b6a`

## callees

- `0x180002aeb`
- `0x18001d240`

## pseudocode

```c
__int64 __fastcall _tailMerge_mi_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_mi_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002aeb  mov     [rsp+arg_0], rcx
0x180002af0  mov     [rsp+arg_8], rdx
0x180002af5  mov     [rsp+arg_10], r8
0x180002afa  mov     [rsp+arg_18], r9
0x180002aff  sub     rsp, 68h
0x180002b03  movdqa  [rsp+68h+var_48], xmm0
0x180002b09  movdqa  [rsp+68h+var_38], xmm1
0x180002b0f  movdqa  [rsp+68h+var_28], xmm2
0x180002b15  movdqa  [rsp+68h+var_18], xmm3
0x180002b1b  mov     rdx, rax
0x180002b1e  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_mi_dll
0x180002b25  call    __delayLoadHelper2
0x180002b2a  movdqa  xmm0, [rsp+68h+var_48]
0x180002b30  movdqa  xmm1, [rsp+68h+var_38]
0x180002b36  movdqa  xmm2, [rsp+68h+var_28]
0x180002b3c  movdqa  xmm3, [rsp+68h+var_18]
0x180002b42  mov     rcx, [rsp+68h+arg_0]
0x180002b47  mov     rdx, [rsp+68h+arg_8]
0x180002b4c  mov     r8, [rsp+68h+arg_10]
0x180002b54  mov     r9, [rsp+68h+arg_18]
0x180002b5c  add     rsp, 68h
0x180002b60  jmp     short $+2
0x180002b62  jmp     rax
```
