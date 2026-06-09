# __tailMerge_sspicli_dll

- ea: `0x18000cf85`
- end: `0x18000cffe`
- name: `__tailMerge_sspicli_dll`
- size: `121`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000d004`
- `0x18000d016`
- `0x18000d028`
- `0x18000d03a`
- `0x18000d04c`
- `0x18000d05e`
- `0x18000d070`

## callees

- `0x180008bd0`
- `0x18000cf85`

## pseudocode

```c
__int64 __fastcall _tailMerge_sspicli_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_sspicli_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000cf85  mov     [rsp+arg_0], rcx
0x18000cf8a  mov     [rsp+arg_8], rdx
0x18000cf8f  mov     [rsp+arg_10], r8
0x18000cf94  mov     [rsp+arg_18], r9
0x18000cf99  sub     rsp, 68h
0x18000cf9d  movdqa  [rsp+68h+var_48], xmm0
0x18000cfa3  movdqa  [rsp+68h+var_38], xmm1
0x18000cfa9  movdqa  [rsp+68h+var_28], xmm2
0x18000cfaf  movdqa  [rsp+68h+var_18], xmm3
0x18000cfb5  mov     rdx, rax
0x18000cfb8  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_sspicli_dll
0x18000cfbf  call    __delayLoadHelper2
0x18000cfc4  movdqa  xmm0, [rsp+68h+var_48]
0x18000cfca  movdqa  xmm1, [rsp+68h+var_38]
0x18000cfd0  movdqa  xmm2, [rsp+68h+var_28]
0x18000cfd6  movdqa  xmm3, [rsp+68h+var_18]
0x18000cfdc  mov     rcx, [rsp+68h+arg_0]
0x18000cfe1  mov     rdx, [rsp+68h+arg_8]
0x18000cfe6  mov     r8, [rsp+68h+arg_10]
0x18000cfee  mov     r9, [rsp+68h+arg_18]
0x18000cff6  add     rsp, 68h
0x18000cffa  jmp     short $+2
0x18000cffc  jmp     rax
```
