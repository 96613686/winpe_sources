# StringCchCatA(x,x,x)

- ea: `0x10002c90`
- end: `0x10002cd8`
- name: `_StringCchCatA@12`
- size: `72`
- prototype: `HRESULT __stdcall(STRSAFE_LPSTR pszDest, size_t cchDest, STRSAFE_LPCSTR pszSrc)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x10002870`
- `0x100049a9`
- `0x10005dd0`
- `0x10006fd6`
- `0x10007174`
- `0x100075de`

## callees

- `0x10002c90`
- `0x10002ce0`
- `0x10002d30`

## pseudocode

```c
HRESULT __stdcall StringCchCatA(STRSAFE_LPSTR pszDest, size_t cchDest, STRSAFE_LPCSTR pszSrc)
{
  int v3; // edx
  HRESULT result; // eax
  char *v5; // ecx
  size_t v6; // [esp+0h] [ebp-Ch]
  const char *v7; // [esp+0h] [ebp-Ch]
  size_t *v8; // [esp+4h] [ebp-8h]
  size_t v9; // [esp+4h] [ebp-8h]
  char psz[4]; // [esp+8h] [ebp-4h] BYREF

  if ( v3 <= 0 )
    return -2147024809;
  result = StringLengthWorkerA(psz, v6, v8);
  if ( result >= 0 )
    return StringCopyWorkerA(v5, (size_t)pszDest, (size_t *)v5, v7, v9);
  return result;
}

```

## disassembly

```asm
0x10002c90  mov     edi, edi
0x10002c92  push    ebp
0x10002c93  mov     ebp, esp
0x10002c95  push    ecx
0x10002c96  push    esi; cchToCopy
0x10002c97  mov     esi, edx
0x10002c99  push    edi; pszSrc
0x10002c9a  mov     edi, ecx
0x10002c9c  test    esi, esi
0x10002c9e  jz      short loc_10002CD1
0x10002ca0  cmp     esi, 7FFFFFFFh
0x10002ca6  ja      short loc_10002CD1
0x10002ca8  lea     eax, [ebp+psz]
0x10002cab  push    eax; psz
0x10002cac  call    StringLengthWorkerA
0x10002cb1  test    eax, eax
0x10002cb3  js      short loc_10002CC9
0x10002cb5  mov     eax, dword ptr [ebp+psz]
0x10002cb8  sub     esi, eax
0x10002cba  push    ecx; pcchNewDestLength
0x10002cbb  push    [ebp+pszDest]; cchDest
0x10002cbe  mov     edx, esi
0x10002cc0  push    ecx; pszDest
0x10002cc1  lea     ecx, [eax+edi]
0x10002cc4  call    StringCopyWorkerA
0x10002cc9  pop     edi
0x10002cca  pop     esi
0x10002ccb  mov     esp, ebp
0x10002ccd  pop     ebp
0x10002cce  retn    4
0x10002cd1  mov     eax, 80070057h
0x10002cd6  jmp     short loc_10002CC9
```
