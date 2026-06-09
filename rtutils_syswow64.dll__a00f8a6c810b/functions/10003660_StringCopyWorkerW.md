# StringCopyWorkerW

- ea: `0x10003660`
- end: `0x100036af`
- name: `StringCopyWorkerW`
- size: `79`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1000362b`
- `0x100036b5`

## callees

- `0x10003660`

## pseudocode

```c
HRESULT __stdcall StringCopyWorkerW(
        STRSAFE_LPWSTR pszDest,
        size_t cchDest,
        size_t *pcchNewDestLength,
        STRSAFE_PCNZWCH pszSrc,
        size_t cchToCopy)
{
  int v5; // edx
  _WORD *v6; // ecx
  HRESULT v7; // ebx
  int v8; // eax
  _WORD *v9; // edi

  v7 = 0;
  v8 = 2147483646;
  v9 = v6;
  if ( v5 )
  {
    while ( v8 && *(_WORD *)cchDest )
    {
      *v9 = *(_WORD *)cchDest;
      cchDest += 2;
      ++v9;
      --v8;
      if ( !--v5 )
        goto LABEL_5;
    }
  }
  else
  {
LABEL_5:
    --v9;
    v7 = -2147024774;
  }
  *v9 = 0;
  return v7;
}

```

## disassembly

```asm
0x10003660  mov     edi, edi
0x10003662  push    ebp
0x10003663  mov     ebp, esp
0x10003665  push    ebx
0x10003666  push    esi
0x10003667  xor     ebx, ebx
0x10003669  mov     eax, 7FFFFFFEh
0x1000366e  push    edi
0x1000366f  mov     edi, ecx
0x10003671  test    edx, edx
0x10003673  jz      short loc_10003693
0x10003675  mov     esi, [ebp+cchDest]
0x10003678  test    eax, eax
0x1000367a  jz      short loc_100036A1
0x1000367c  movzx   ecx, word ptr [esi]
0x1000367f  test    cx, cx
0x10003682  jz      short loc_1000369D
0x10003684  mov     [edi], cx
0x10003687  add     esi, 2
0x1000368a  add     edi, 2
0x1000368d  dec     eax
0x1000368e  sub     edx, 1
0x10003691  jnz     short loc_10003678
0x10003693  sub     edi, 2
0x10003696  mov     ebx, 8007007Ah
0x1000369b  jmp     short loc_100036A1
0x1000369d  test    edx, edx
0x1000369f  jz      short loc_10003693
0x100036a1  xor     eax, eax
0x100036a3  mov     [edi], ax
0x100036a6  mov     eax, ebx
0x100036a8  pop     edi
0x100036a9  pop     esi
0x100036aa  pop     ebx
0x100036ab  pop     ebp
0x100036ac  retn    0Ch
```
