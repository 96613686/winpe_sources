# __tailMerge_audioses_dll

- ea: `0x18000c4ab`
- end: `0x18000c524`
- name: `__tailMerge_audioses_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000c52a`

## callees

- `0x180009370`
- `0x18000c4ab`

## pseudocode

```c
__int64 __fastcall _tailMerge_audioses_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_audioses_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000c4ab  mov     [rsp+arg_0], rcx
0x18000c4b0  mov     [rsp+arg_8], rdx
0x18000c4b5  mov     [rsp+arg_10], r8
0x18000c4ba  mov     [rsp+arg_18], r9
0x18000c4bf  sub     rsp, 68h
0x18000c4c3  movdqa  [rsp+68h+var_48], xmm0
0x18000c4c9  movdqa  [rsp+68h+var_38], xmm1
0x18000c4cf  movdqa  [rsp+68h+var_28], xmm2
0x18000c4d5  movdqa  [rsp+68h+var_18], xmm3
0x18000c4db  mov     rdx, rax
0x18000c4de  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_audioses_dll
0x18000c4e5  call    __delayLoadHelper2
0x18000c4ea  movdqa  xmm0, [rsp+68h+var_48]
0x18000c4f0  movdqa  xmm1, [rsp+68h+var_38]
0x18000c4f6  movdqa  xmm2, [rsp+68h+var_28]
0x18000c4fc  movdqa  xmm3, [rsp+68h+var_18]
0x18000c502  mov     rcx, [rsp+68h+arg_0]
0x18000c507  mov     rdx, [rsp+68h+arg_8]
0x18000c50c  mov     r8, [rsp+68h+arg_10]
0x18000c514  mov     r9, [rsp+68h+arg_18]
0x18000c51c  add     rsp, 68h
0x18000c520  jmp     short $+2
0x18000c522  jmp     rax
```
