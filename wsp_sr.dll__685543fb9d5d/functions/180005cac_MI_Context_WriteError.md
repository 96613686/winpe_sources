# MI_Context_WriteError

- ea: `0x180005cac`
- end: `0x180005ce6`
- name: `MI_Context_WriteError`
- size: `58`
- prototype: `static MI_Result __stdcall(MI_Context *context, MI_Uint32 resultCode, const MI_Char *resultType, const MI_Char *errorMessage, MI_Boolean *flag)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180005bac`

## callees

- `0x180005cac`
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
0x180005cac  sub     rsp, 38h
0x180005cb0  mov     r10, r9
0x180005cb3  test    rcx, rcx
0x180005cb6  jz      short loc_180005CDB
0x180005cb8  mov     rax, [rcx]
0x180005cbb  test    rax, rax
0x180005cbe  jz      short loc_180005CDB
0x180005cc0  mov     r9, [rsp+38h+flag]
0x180005cc5  mov     rax, [rax+0E8h]
0x180005ccc  mov     [rsp+38h+var_18], r9
0x180005cd1  mov     r9, r10
0x180005cd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005cd9  jmp     short loc_180005CE0
0x180005cdb  mov     eax, 4
0x180005ce0  add     rsp, 38h
0x180005ce4  retn
```
