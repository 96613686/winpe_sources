# WriteBytes

- ea: `0x180011fc8`
- end: `0x18001200f`
- name: `WriteBytes`
- size: `71`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x180010b90`
- `0x180011640`
- `0x180012a18`
- `0x180016770`
- `0x180029228`

## callees

- `0x180011fc8`
- `0x180012020`
- `0x18002a54e`

## pseudocode

```c
__int64 __fastcall WriteBytes(_QWORD *a1, const void *a2, unsigned int a3, size_t a4)
{
  __int64 result; // rax

  result = CheckOutOffset(a1, a3);
  if ( !(_WORD)result )
  {
    memcpy_0((void *)(*a1 + a3), a2, a4);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180011fc8  push    rbx
0x180011fca  push    rbp
0x180011fcb  push    rsi
0x180011fcc  push    rdi
0x180011fcd  push    r14
0x180011fcf  sub     rsp, 20h
0x180011fd3  mov     edi, r8d
0x180011fd6  mov     rbp, rdx
0x180011fd9  mov     edx, edi
0x180011fdb  mov     r8, r9
0x180011fde  mov     rbx, r9
0x180011fe1  mov     rsi, rcx
0x180011fe4  call    CheckOutOffset
0x180011fe9  xor     r14d, r14d
0x180011fec  test    ax, ax
0x180011fef  jnz     short loc_180012004
0x180011ff1  mov     ecx, edi
0x180011ff3  mov     r8, rbx; Size
0x180011ff6  add     rcx, [rsi]; void *
0x180011ff9  mov     rdx, rbp; Src
0x180011ffc  call    memcpy_0
0x180012001  mov     eax, r14d
0x180012004  add     rsp, 20h
0x180012008  pop     r14
0x18001200a  pop     rdi
0x18001200b  pop     rsi
0x18001200c  pop     rbp
0x18001200d  pop     rbx
0x18001200e  retn
```
