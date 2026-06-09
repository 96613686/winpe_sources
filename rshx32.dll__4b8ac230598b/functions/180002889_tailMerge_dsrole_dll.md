# __tailMerge_dsrole_dll

- ea: `0x180002889`
- end: `0x180002902`
- name: `__tailMerge_dsrole_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002908`
- `0x18000291a`

## callees

- `0x180002889`
- `0x18001d240`

## pseudocode

```c
__int64 __fastcall _tailMerge_dsrole_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_dsrole_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002889  mov     [rsp+arg_0], rcx
0x18000288e  mov     [rsp+arg_8], rdx
0x180002893  mov     [rsp+arg_10], r8
0x180002898  mov     [rsp+arg_18], r9
0x18000289d  sub     rsp, 68h
0x1800028a1  movdqa  [rsp+68h+var_48], xmm0
0x1800028a7  movdqa  [rsp+68h+var_38], xmm1
0x1800028ad  movdqa  [rsp+68h+var_28], xmm2
0x1800028b3  movdqa  [rsp+68h+var_18], xmm3
0x1800028b9  mov     rdx, rax
0x1800028bc  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_dsrole_dll
0x1800028c3  call    __delayLoadHelper2
0x1800028c8  movdqa  xmm0, [rsp+68h+var_48]
0x1800028ce  movdqa  xmm1, [rsp+68h+var_38]
0x1800028d4  movdqa  xmm2, [rsp+68h+var_28]
0x1800028da  movdqa  xmm3, [rsp+68h+var_18]
0x1800028e0  mov     rcx, [rsp+68h+arg_0]
0x1800028e5  mov     rdx, [rsp+68h+arg_8]
0x1800028ea  mov     r8, [rsp+68h+arg_10]
0x1800028f2  mov     r9, [rsp+68h+arg_18]
0x1800028fa  add     rsp, 68h
0x1800028fe  jmp     short $+2
0x180002900  jmp     rax
```
