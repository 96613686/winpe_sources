# StringCchLengthW

- ea: `0x180006edc`
- end: `0x180006f40`
- name: `StringCchLengthW`
- size: `100`
- prototype: `HRESULT __stdcall(STRSAFE_PCNZWCH psz, size_t cchMax, size_t *pcchLength)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180002740`
- `0x180007b7c`

## callees

- `0x180006edc`

## pseudocode

```c
HRESULT __stdcall StringCchLengthW(STRSAFE_PCNZWCH psz, size_t cchMax, size_t *pcchLength)
{
  size_t i; // r9
  HRESULT result; // eax

  if ( !psz || cchMax > 0x7FFFFFFF )
  {
    result = -2147024809;
    goto LABEL_13;
  }
  for ( i = cchMax; i; --i )
  {
    if ( !*psz )
      break;
    ++psz;
  }
  result = i == 0 ? 0x80070057 : 0;
  if ( !pcchLength )
  {
    if ( i )
      return result;
LABEL_13:
    if ( !pcchLength )
      return result;
    goto LABEL_14;
  }
  if ( i )
  {
    *pcchLength = cchMax - i;
    return result;
  }
  *pcchLength = 0;
LABEL_14:
  *pcchLength = 0;
  return result;
}

```

## disassembly

```asm
0x180006edc  xor     r10d, r10d
0x180006edf  test    rcx, rcx
0x180006ee2  jz      short loc_180006F32
0x180006ee4  cmp     rdx, 7FFFFFFFh
0x180006eeb  ja      short loc_180006F32
0x180006eed  mov     r9, rdx
0x180006ef0  test    rdx, rdx
0x180006ef3  jz      short loc_180006F05
0x180006ef5  cmp     [rcx], r10w
0x180006ef9  jz      short loc_180006F05
0x180006efb  add     rcx, 2
0x180006eff  sub     r9, 1
0x180006f03  jnz     short loc_180006EF5
0x180006f05  mov     rax, r9
0x180006f08  neg     rax
0x180006f0b  sbb     eax, eax
0x180006f0d  not     eax
0x180006f0f  and     eax, 80070057h
0x180006f14  test    r8, r8
0x180006f17  jz      short loc_180006F2B
0x180006f19  test    r9, r9
0x180006f1c  jz      short loc_180006F26
0x180006f1e  sub     rdx, r9
0x180006f21  mov     [r8], rdx
0x180006f24  retn
0x180006f26  mov     [r8], r10
0x180006f29  jmp     short loc_180006F3C
0x180006f2b  test    r9, r9
0x180006f2e  jnz     short locret_180006F3F
0x180006f30  jmp     short loc_180006F37
0x180006f32  mov     eax, 80070057h
0x180006f37  test    r8, r8
0x180006f3a  jz      short locret_180006F3F
0x180006f3c  mov     [r8], r10
0x180006f3f  retn
```
