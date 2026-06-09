# SkipWhiteSpace

- ea: `0x18001dadc`
- end: `0x18001db03`
- name: `SkipWhiteSpace`
- size: `39`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x18001d1d8`
- `0x18001d64c`
- `0x18001d6f0`
- `0x18001d71c`
- `0x18001d7a8`
- `0x18001d954`

## callees

- `0x18001dadc`

## pseudocode

```c
char *__fastcall SkipWhiteSpace(char *a1)
{
  char v1; // al

  if ( a1 )
  {
    v1 = *a1;
    if ( !*a1 )
      return 0;
    do
    {
      if ( v1 != 32 && v1 != 9 )
        break;
      v1 = *++a1;
    }
    while ( *a1 );
    if ( !*a1 )
      return 0;
  }
  return a1;
}

```

## disassembly

```asm
0x18001dadc  test    rcx, rcx
0x18001dadf  jz      short loc_18001DAFF
0x18001dae1  mov     al, [rcx]
0x18001dae3  test    al, al
0x18001dae5  jz      short loc_18001DAFD
0x18001dae7  cmp     al, 20h ; ' '
0x18001dae9  jz      short loc_18001DAEF
0x18001daeb  cmp     al, 9
0x18001daed  jnz     short loc_18001DAF8
0x18001daef  inc     rcx
0x18001daf2  mov     al, [rcx]
0x18001daf4  test    al, al
0x18001daf6  jnz     short loc_18001DAE7
0x18001daf8  cmp     byte ptr [rcx], 0
0x18001dafb  jnz     short loc_18001DAFF
0x18001dafd  xor     ecx, ecx
0x18001daff  mov     rax, rcx
0x18001db02  retn
```
