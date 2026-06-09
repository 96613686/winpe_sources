# __tailMerge_rpcrt4_dll

- ea: `0x180013789`
- end: `0x180013802`
- name: `__tailMerge_rpcrt4_dll`
- size: `121`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180013808`
- `0x18001381a`
- `0x18001382c`
- `0x18001383e`
- `0x180013850`
- `0x180013862`
- `0x180013874`
- `0x180013886`

## callees

- `0x180013789`
- `0x1800376a0`

## pseudocode

```c
__int64 __fastcall _tailMerge_rpcrt4_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_rpcrt4_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180013789  mov     [rsp+arg_0], rcx
0x18001378e  mov     [rsp+arg_8], rdx
0x180013793  mov     [rsp+arg_10], r8
0x180013798  mov     [rsp+arg_18], r9
0x18001379d  sub     rsp, 68h
0x1800137a1  movdqa  [rsp+68h+var_48], xmm0
0x1800137a7  movdqa  [rsp+68h+var_38], xmm1
0x1800137ad  movdqa  [rsp+68h+var_28], xmm2
0x1800137b3  movdqa  [rsp+68h+var_18], xmm3
0x1800137b9  mov     rdx, rax
0x1800137bc  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_rpcrt4_dll
0x1800137c3  call    __delayLoadHelper2
0x1800137c8  movdqa  xmm0, [rsp+68h+var_48]
0x1800137ce  movdqa  xmm1, [rsp+68h+var_38]
0x1800137d4  movdqa  xmm2, [rsp+68h+var_28]
0x1800137da  movdqa  xmm3, [rsp+68h+var_18]
0x1800137e0  mov     rcx, [rsp+68h+arg_0]
0x1800137e5  mov     rdx, [rsp+68h+arg_8]
0x1800137ea  mov     r8, [rsp+68h+arg_10]
0x1800137f2  mov     r9, [rsp+68h+arg_18]
0x1800137fa  add     rsp, 68h
0x1800137fe  jmp     short $+2
0x180013800  jmp     rax
```
