# StringCchPrintfA

- ea: `0x180005768`
- end: `0x1800057e2`
- name: `StringCchPrintfA`
- size: `122`
- prototype: `HRESULT(STRSAFE_LPSTR pszDest, size_t cchDest, STRSAFE_LPCSTR pszFormat, ...)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180004300`
- `0x180004920`
- `0x180004b50`
- `0x180005530`

## callees

- `0x180005768`

## import_xrefs

- `msvcrt!_vsnprintf` at `0x1800057a5`
- `msvcrt!_vsnprintf` at `0x1800057a5`

## pseudocode

```c
HRESULT StringCchPrintfA(STRSAFE_LPSTR pszDest, size_t cchDest, STRSAFE_LPCSTR pszFormat, ...)
{
  HRESULT result; // eax
  size_t v5; // rbx
  int v6; // eax
  __int64 v7; // rcx
  va_list ArgList; // [rsp+68h] [rbp+20h] BYREF

  va_start(ArgList, pszFormat);
  if ( !cchDest )
    return -2147024809;
  if ( cchDest <= 0x7FFFFFFF )
  {
    v5 = cchDest - 1;
    v6 = _vsnprintf(pszDest, cchDest - 1, pszFormat, ArgList);
    if ( v6 < 0 || (v7 = v6, v6 > v5) )
    {
      pszDest[v5] = 0;
      return -2147024774;
    }
    else
    {
      result = 0;
      if ( v7 == v5 )
        pszDest[v5] = 0;
    }
  }
  else
  {
    result = -2147024809;
    *pszDest = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180005768  mov     [rsp+arg_10], r8
0x18000576d  mov     qword ptr [rsp+ArgList], r9
0x180005772  push    rbx
0x180005773  push    rdi
0x180005774  sub     rsp, 38h
0x180005778  mov     rdi, rcx
0x18000577b  test    rdx, rdx
0x18000577e  jz      short loc_1800057CE
0x180005780  cmp     rdx, 7FFFFFFFh
0x180005787  jbe     short loc_180005790
0x180005789  mov     eax, 80070057h
0x18000578e  jmp     short loc_1800057D8
0x180005790  lea     rbx, [rdx-1]
0x180005794  mov     [rsp+48h+var_28], 0
0x18000579d  mov     rdx, rbx; BufferCount
0x1800057a0  lea     r9, [rsp+48h+ArgList]; ArgList
0x1800057a5  call    cs:__imp__vsnprintf
0x1800057ab  test    eax, eax
0x1800057ad  js      short loc_1800057C3
0x1800057af  movsxd  rcx, eax
0x1800057b2  cmp     rcx, rbx
0x1800057b5  ja      short loc_1800057C3
0x1800057b7  xor     eax, eax
0x1800057b9  cmp     rcx, rbx
0x1800057bc  jnz     short loc_1800057DB
0x1800057be  mov     [rbx+rdi], al
0x1800057c1  jmp     short loc_1800057DB
0x1800057c3  mov     byte ptr [rbx+rdi], 0
0x1800057c7  mov     eax, 8007007Ah
0x1800057cc  jmp     short loc_1800057DB
0x1800057ce  mov     eax, 80070057h
0x1800057d3  test    rdx, rdx
0x1800057d6  jz      short loc_1800057DB
0x1800057d8  mov     byte ptr [rcx], 0
0x1800057db  add     rsp, 38h
0x1800057df  pop     rdi
0x1800057e0  pop     rbx
0x1800057e1  retn
```
