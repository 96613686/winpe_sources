# StringCchCatW(x,x,x)

- ea: `0x100036b5`
- end: `0x100036fb`
- name: `_StringCchCatW@12`
- size: `70`
- prototype: `HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x100032d0`
- `0x10004de8`
- `0x10006770`
- `0x10007954`
- `0x10007bcc`
- `0x100080a7`

## callees

- `0x10003660`
- `0x100036b5`
- `0x10003710`

## pseudocode

```c
HRESULT __stdcall StringCchCatW(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)
{
  int v3; // edx
  HRESULT result; // eax
  wchar_t *v5; // ecx
  size_t v6; // [esp+0h] [ebp-Ch]
  const wchar_t *v7; // [esp+0h] [ebp-Ch]
  size_t *v8; // [esp+4h] [ebp-8h]
  size_t v9; // [esp+4h] [ebp-8h]
  wchar_t psz[2]; // [esp+8h] [ebp-4h] BYREF

  if ( v3 <= 0 )
    return -2147024809;
  result = StringLengthWorkerW(psz, v6, v8);
  if ( result >= 0 )
    return StringCopyWorkerW(v5, (size_t)pszDest, (size_t *)v5, v7, v9);
  return result;
}

```

## disassembly

```asm
0x100036b5  mov     edi, edi
0x100036b7  push    ebp
0x100036b8  mov     ebp, esp
0x100036ba  push    ecx
0x100036bb  push    esi; pcchLength
0x100036bc  mov     esi, edx
0x100036be  push    edi; cchMax
0x100036bf  mov     edi, ecx
0x100036c1  test    esi, esi
0x100036c3  jz      short loc_100036F4
0x100036c5  cmp     esi, 7FFFFFFFh
0x100036cb  ja      short loc_100036F4
0x100036cd  lea     eax, [ebp+psz]
0x100036d0  push    eax; psz
0x100036d1  call    StringLengthWorkerW
0x100036d6  test    eax, eax
0x100036d8  js      short loc_100036EE
0x100036da  mov     eax, dword ptr [ebp+psz]
0x100036dd  sub     esi, eax
0x100036df  push    ecx; pcchNewDestLength
0x100036e0  push    [ebp+pszDest]; cchDest
0x100036e3  mov     edx, esi
0x100036e5  push    ecx; pszDest
0x100036e6  lea     ecx, [edi+eax*2]
0x100036e9  call    StringCopyWorkerW
0x100036ee  pop     edi
0x100036ef  pop     esi
0x100036f0  leave
0x100036f1  retn    4
0x100036f4  mov     eax, 80070057h
0x100036f9  jmp     short loc_100036EE
```
