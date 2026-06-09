# StringCchPrintfA

- ea: `0x18000fb9c`
- end: `0x18000fc16`
- name: `StringCchPrintfA`
- size: `122`
- prototype: `HRESULT(STRSAFE_LPSTR pszDest, size_t cchDest, STRSAFE_LPCSTR pszFormat, ...)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000df10`
- `0x1800104d8`
- `0x1800175cc`
- `0x1800177e0`

## callees

- `0x18000fb9c`

## import_xrefs

- `msvcrt!_vsnprintf` at `0x18000fbd9`
- `msvcrt!_vsnprintf` at `0x18000fbd9`

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
0x18000fb9c  mov     [rsp+arg_10], r8
0x18000fba1  mov     qword ptr [rsp+ArgList], r9
0x18000fba6  push    rbx
0x18000fba7  push    rdi
0x18000fba8  sub     rsp, 38h
0x18000fbac  mov     rdi, rcx
0x18000fbaf  test    rdx, rdx
0x18000fbb2  jz      short loc_18000FC02
0x18000fbb4  cmp     rdx, 7FFFFFFFh
0x18000fbbb  jbe     short loc_18000FBC4
0x18000fbbd  mov     eax, 80070057h
0x18000fbc2  jmp     short loc_18000FC0C
0x18000fbc4  lea     rbx, [rdx-1]
0x18000fbc8  mov     [rsp+48h+var_28], 0
0x18000fbd1  mov     rdx, rbx; BufferCount
0x18000fbd4  lea     r9, [rsp+48h+ArgList]; ArgList
0x18000fbd9  call    cs:__imp__vsnprintf
0x18000fbdf  test    eax, eax
0x18000fbe1  js      short loc_18000FBF7
0x18000fbe3  movsxd  rcx, eax
0x18000fbe6  cmp     rcx, rbx
0x18000fbe9  ja      short loc_18000FBF7
0x18000fbeb  xor     eax, eax
0x18000fbed  cmp     rcx, rbx
0x18000fbf0  jnz     short loc_18000FC0F
0x18000fbf2  mov     [rbx+rdi], al
0x18000fbf5  jmp     short loc_18000FC0F
0x18000fbf7  mov     byte ptr [rbx+rdi], 0
0x18000fbfb  mov     eax, 8007007Ah
0x18000fc00  jmp     short loc_18000FC0F
0x18000fc02  mov     eax, 80070057h
0x18000fc07  test    rdx, rdx
0x18000fc0a  jz      short loc_18000FC0F
0x18000fc0c  mov     byte ptr [rcx], 0
0x18000fc0f  add     rsp, 38h
0x18000fc13  pop     rdi
0x18000fc14  pop     rbx
0x18000fc15  retn
```
