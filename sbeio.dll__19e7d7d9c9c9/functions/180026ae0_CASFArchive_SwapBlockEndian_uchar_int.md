# CASFArchive::SwapBlockEndian(uchar *,int)

- ea: `0x180026ae0`
- end: `0x180026b01`
- name: `?SwapBlockEndian@CASFArchive@@QEAAXPEAEH@Z`
- size: `33`
- prototype: `void __fastcall(CASFArchive *__hidden this, unsigned __int8 *, int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x18001d340`
- `0x18001d424`
- `0x18001d484`
- `0x1800266d8`
- `0x1800267b0`
- `0x180026824`

## callees

- `0x180026ae0`

## pseudocode

```c
void __fastcall CASFArchive::SwapBlockEndian(CASFArchive *this, unsigned __int8 *a2, int a3)
{
  unsigned __int8 *i; // r8
  unsigned __int8 v4; // cl

  for ( i = &a2[a3 - 1]; a2 < i; --i )
  {
    v4 = *a2;
    *a2++ = *i;
    *i = v4;
  }
}

```

## disassembly

```asm
0x180026ae0  movsxd  r8, r8d
0x180026ae3  dec     r8
0x180026ae6  add     r8, rdx
0x180026ae9  jmp     short loc_180026AFB
0x180026aeb  mov     al, [r8]
0x180026aee  mov     cl, [rdx]
0x180026af0  mov     [rdx], al
0x180026af2  inc     rdx
0x180026af5  mov     [r8], cl
0x180026af8  dec     r8
0x180026afb  cmp     rdx, r8
0x180026afe  jb      short loc_180026AEB
0x180026b00  retn
```
