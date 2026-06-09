# EfiDeleteDriverEntry

- ea: `0x180014274`
- end: `0x1800142ad`
- name: `EfiDeleteDriverEntry`
- size: `57`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180014784`
- `0x1800149e0`

## callees

- `0x180014094`
- `0x180014274`
- `0x180018010`

## pseudocode

```c
__int64 __fastcall EfiDeleteDriverEntry(unsigned int a1)
{
  if ( !EfipApisInitialized )
    EfiApiInitialize();
  if ( EfipDeleteDriverEntry )
    return EfipDeleteDriverEntry(a1);
  else
    return 3221225474LL;
}

```

## disassembly

```asm
0x180014274  push    rbx
0x180014276  sub     rsp, 20h
0x18001427a  cmp     cs:EfipApisInitialized, 0
0x180014281  mov     ebx, ecx
0x180014283  jnz     short loc_18001428A
0x180014285  call    EfiApiInitialize
0x18001428a  mov     rax, cs:EfipDeleteDriverEntry
0x180014291  test    rax, rax
0x180014294  jz      short loc_1800142A2
0x180014296  mov     ecx, ebx
0x180014298  add     rsp, 20h
0x18001429c  pop     rbx
0x18001429d  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x1800142a2  mov     eax, 0C0000002h
0x1800142a7  add     rsp, 20h
0x1800142ab  pop     rbx
0x1800142ac  retn
```
