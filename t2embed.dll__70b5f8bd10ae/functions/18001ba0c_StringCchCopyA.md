# StringCchCopyA

- ea: `0x18001ba0c`
- end: `0x18001ba41`
- name: `StringCchCopyA`
- size: `53`
- prototype: `HRESULT __stdcall(STRSAFE_LPSTR pszDest, size_t cchDest, STRSAFE_LPCSTR pszSrc)`
- caller_count: `12`
- callee_count: `2`
- tags: ``

## callers

- `0x180019a88`
- `0x18001edf0`
- `0x18001ef44`
- `0x18001f620`
- `0x180020260`
- `0x180021ffc`
- `0x18002218c`
- `0x18002231c`
- `0x18002252c`
- `0x1800229a8`
- `0x180022de8`
- `0x180023224`

## callees

- `0x18001ba0c`
- `0x18001ba48`

## pseudocode

```c
HRESULT __stdcall StringCchCopyA(STRSAFE_LPSTR pszDest, size_t cchDest, STRSAFE_LPCSTR pszSrc)
{
  HRESULT result; // eax
  size_t v4; // [rsp+20h] [rbp-18h]

  if ( !cchDest )
    return -2147024809;
  if ( cchDest <= 0x7FFFFFFF )
    return StringCopyWorkerA(pszDest, cchDest, (size_t *)pszSrc, pszSrc, v4);
  result = -2147024809;
  *pszDest = 0;
  return result;
}

```

## disassembly

```asm
0x18001ba0c  sub     rsp, 38h
0x18001ba10  test    rdx, rdx
0x18001ba13  jz      short loc_18001BA32
0x18001ba15  cmp     rdx, 7FFFFFFFh
0x18001ba1c  ja      short loc_18001BA2B
0x18001ba1e  mov     r9, r8; pszSrc
0x18001ba21  call    StringCopyWorkerA
0x18001ba26  add     rsp, 38h
0x18001ba2a  retn
0x18001ba2b  mov     eax, 80070057h
0x18001ba30  jmp     short loc_18001BA3C
0x18001ba32  mov     eax, 80070057h
0x18001ba37  test    rdx, rdx
0x18001ba3a  jz      short loc_18001BA26
0x18001ba3c  mov     byte ptr [rcx], 0
0x18001ba3f  jmp     short loc_18001BA26
```
