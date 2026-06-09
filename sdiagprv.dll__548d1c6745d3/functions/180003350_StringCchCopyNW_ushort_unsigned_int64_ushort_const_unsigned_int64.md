# StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)

- ea: `0x180003350`
- end: `0x18000339b`
- name: `?StringCchCopyNW@@YAJPEAG_KPEBG1@Z`
- size: `75`
- prototype: `__int64 __fastcall(unsigned __int16 *, size_t, size_t *, size_t cchToCopy)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180002ac4`
- `0x18000dc8c`

## callees

- `0x180003350`
- `0x18000348c`

## pseudocode

```c
__int64 __fastcall StringCchCopyNW(unsigned __int16 *a1, size_t a2, size_t *a3, size_t cchToCopy)
{
  unsigned int v4; // edx

  if ( a2 )
  {
    if ( a2 > 0x7FFFFFFF || cchToCopy > 0x7FFFFFFE )
    {
      v4 = -2147024809;
      *a1 = 0;
    }
    else
    {
      return (unsigned int)StringCopyWorkerW(a1, a2, a3, (STRSAFE_PCNZWCH)a3, cchToCopy);
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v4;
}

```

## disassembly

```asm
0x180003350  sub     rsp, 38h
0x180003354  mov     rax, rdx
0x180003357  test    rdx, rdx
0x18000335a  jz      short loc_180003385
0x18000335c  cmp     rax, 7FFFFFFFh
0x180003362  jbe     short loc_18000336B
0x180003364  mov     edx, 80070057h; cchDest
0x180003369  jmp     short loc_18000338F
0x18000336b  cmp     r9, 7FFFFFFEh
0x180003372  ja      short loc_180003364
0x180003374  mov     [rsp+38h+cchToCopy], r9; cchToCopy
0x180003379  mov     r9, r8; pszSrc
0x18000337c  call    StringCopyWorkerW
0x180003381  mov     edx, eax
0x180003383  jmp     short loc_180003394
0x180003385  mov     edx, 80070057h
0x18000338a  test    rax, rax
0x18000338d  jz      short loc_180003394
0x18000338f  xor     eax, eax
0x180003391  mov     [rcx], ax
0x180003394  mov     eax, edx
0x180003396  add     rsp, 38h
0x18000339a  retn
```
