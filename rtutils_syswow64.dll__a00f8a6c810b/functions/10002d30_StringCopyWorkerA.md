# StringCopyWorkerA

- ea: `0x10002d30`
- end: `0x10002d71`
- name: `StringCopyWorkerA`
- size: `65`
- prototype: `static HRESULT __stdcall(STRSAFE_LPSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZCH pszSrc, size_t cchToCopy)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x10002c90`

## callees

- `0x10002d30`

## pseudocode

```c
HRESULT __stdcall StringCopyWorkerA(
        STRSAFE_LPSTR pszDest,
        size_t cchDest,
        size_t *pcchNewDestLength,
        STRSAFE_PCNZCH pszSrc,
        size_t cchToCopy)
{
  int v5; // edx
  _BYTE *v6; // ecx
  int v7; // esi

  v7 = 2147483646;
  if ( v5 )
  {
    while ( v7 && *(_BYTE *)cchDest )
    {
      *v6++ = *(_BYTE *)cchDest++;
      --v7;
      if ( !--v5 )
        goto LABEL_5;
    }
    *v6 = 0;
    return 0;
  }
  else
  {
LABEL_5:
    *(v6 - 1) = 0;
    return -2147024774;
  }
}

```

## disassembly

```asm
0x10002d30  mov     edi, edi
0x10002d32  push    ebp
0x10002d33  mov     ebp, esp
0x10002d35  push    esi
0x10002d36  mov     esi, 7FFFFFFEh
0x10002d3b  push    edi
0x10002d3c  test    edx, edx
0x10002d3e  jz      short loc_10002D57
0x10002d40  mov     edi, [ebp+cchDest]
0x10002d43  test    esi, esi
0x10002d45  jz      short loc_10002D66
0x10002d47  mov     al, [edi]
0x10002d49  test    al, al
0x10002d4b  jz      short loc_10002D62
0x10002d4d  mov     [ecx], al
0x10002d4f  inc     edi
0x10002d50  inc     ecx
0x10002d51  dec     esi
0x10002d52  sub     edx, 1
0x10002d55  jnz     short loc_10002D43
0x10002d57  mov     byte ptr [ecx-1], 0
0x10002d5b  mov     eax, 8007007Ah
0x10002d60  jmp     short loc_10002D6B
0x10002d62  test    edx, edx
0x10002d64  jz      short loc_10002D57
0x10002d66  mov     byte ptr [ecx], 0
0x10002d69  xor     eax, eax
0x10002d6b  pop     edi
0x10002d6c  pop     esi
0x10002d6d  pop     ebp
0x10002d6e  retn    0Ch
```
