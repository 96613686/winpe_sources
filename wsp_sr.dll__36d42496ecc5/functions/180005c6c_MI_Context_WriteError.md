# MI_Context_WriteError

- ea: `0x180005c6c`
- end: `0x180005ca5`
- name: `MI_Context_WriteError`
- size: `57`
- prototype: `static MI_Result __stdcall(MI_Context *context, MI_Uint32 resultCode, const MI_Char *resultType, const MI_Char *errorMessage, MI_Boolean *flag)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180005b68`

## callees

- `0x180005c6c`
- `0x18002d010`

## pseudocode

```c
MI_Result __stdcall MI_Context_WriteError(
        MI_Context *context,
        MI_Uint32 resultCode,
        const MI_Char *resultType,
        const MI_Char *errorMessage,
        MI_Boolean *flag)
{
  if ( context && context->ft )
    return ((unsigned int (__fastcall *)(MI_Context *, MI_Uint32, const MI_Char *, const MI_Char *, MI_Boolean *))context->ft->WriteError)(
             context,
             resultCode,
             resultType,
             errorMessage,
             flag);
  else
    return 4;
}

```

## disassembly

```asm
0x180005c6c  sub     rsp, 38h
0x180005c70  mov     r10, r9
0x180005c73  test    rcx, rcx
0x180005c76  jz      short loc_180005C9B
0x180005c78  mov     rax, [rcx]
0x180005c7b  test    rax, rax
0x180005c7e  jz      short loc_180005C9B
0x180005c80  mov     r9, [rsp+38h+flag]
0x180005c85  mov     rax, [rax+0E8h]
0x180005c8c  mov     [rsp+38h+var_18], r9
0x180005c91  mov     r9, r10
0x180005c94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c99  jmp     short loc_180005CA0
0x180005c9b  mov     eax, 4
0x180005ca0  add     rsp, 38h
0x180005ca4  retn
```
