# MI_Context_PostResult_0

- ea: `0x1800039a4`
- end: `0x1800039bf`
- name: `MI_Context_PostResult_0`
- size: `27`
- prototype: `static MI_Result __stdcall(MI_Context *context, MI_Result result)`
- caller_count: `45`
- callee_count: `2`
- tags: ``

## callers

- `0x180002b60`
- `0x180002c00`
- `0x180002c80`
- `0x180002d20`
- `0x180002da0`
- `0x180002e40`
- `0x180002ec0`
- `0x180002f60`
- `0x180002fe0`
- `0x180003080`
- `0x180003100`
- `0x1800031a0`
- `0x180003220`
- `0x180003390`
- `0x180003430`
- `0x1800039d0`
- `0x1800039f0`
- `0x180003a80`
- `0x180003aa0`
- `0x180003ab0`
- `0x180003b40`
- `0x180003bf0`
- `0x180003cc0`
- `0x180003db0`
- `0x180003e80`
- `0x180003f40`
- `0x180004010`
- `0x1800040e0`
- `0x1800041b0`
- `0x180004240`
- `0x1800042f0`
- `0x1800043b0`
- `0x180004470`
- `0x180004530`
- `0x1800045f0`
- `0x1800046b0`
- `0x180004770`
- `0x180004800`
- `0x180004890`
- `0x180004920`
- `0x1800049d0`
- `0x180004a60`
- `0x180004b18`
- `0x180004f80`
- `0x180005220`

## callees

- `0x1800039a4`
- `0x18002d010`

## pseudocode

```c
MI_Result __stdcall MI_Context_PostResult_0(MI_Context *context, MI_Result result)
{
  if ( context && context->ft )
    return ((__int64 (__fastcall *)(MI_Context *, MI_Result))context->ft->PostResult)(context, result);
  else
    return 4;
}

```

## disassembly

```asm
0x1800039a4  test    rcx, rcx
0x1800039a7  jz      short loc_1800039B9
0x1800039a9  mov     rax, [rcx]
0x1800039ac  test    rax, rax
0x1800039af  jz      short loc_1800039B9
0x1800039b1  mov     rax, [rax]
0x1800039b4  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x1800039b9  mov     eax, 4
0x1800039be  retn
```
