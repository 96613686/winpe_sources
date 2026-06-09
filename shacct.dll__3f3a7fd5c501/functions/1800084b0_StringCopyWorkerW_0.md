# StringCopyWorkerW_0

- ea: `0x1800084b0`
- end: `0x180008505`
- name: `StringCopyWorkerW_0`
- size: `85`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ec7c`

## callees

- `0x1800084b0`

## pseudocode

```c
HRESULT __stdcall StringCopyWorkerW_0(
        STRSAFE_LPWSTR pszDest,
        size_t cchDest,
        size_t *pcchNewDestLength,
        STRSAFE_PCNZWCH pszSrc,
        size_t cchToCopy)
{
  HRESULT result; // eax

  result = 0;
  if ( cchDest )
  {
    while ( cchToCopy && *pszSrc )
    {
      *pszDest++ = *pszSrc++;
      --cchToCopy;
      if ( !--cchDest )
      {
        result = -2147024774;
        *(pszDest - 1) = 0;
        return result;
      }
    }
  }
  else
  {
    --pszDest;
    result = -2147024774;
  }
  *pszDest = 0;
  return result;
}

```

## disassembly

```asm
0x1800084b0  xor     eax, eax
0x1800084b2  test    rdx, rdx
0x1800084b5  jz      short loc_1800084F6
0x1800084b7  mov     r8, [rsp+cchToCopy]
0x1800084bc  nop     dword ptr [rax+00h]
0x1800084c0  test    r8, r8
0x1800084c3  jz      short loc_1800084FF
0x1800084c5  movzx   r10d, word ptr [r9]
0x1800084c9  test    r10w, r10w
0x1800084cd  jz      short loc_1800084F1
0x1800084cf  mov     [rcx], r10w
0x1800084d3  add     r9, 2
0x1800084d7  add     rcx, 2
0x1800084db  dec     r8
0x1800084de  sub     rdx, 1
0x1800084e2  jnz     short loc_1800084C0
0x1800084e4  sub     rcx, 2
0x1800084e8  mov     eax, 8007007Ah
0x1800084ed  mov     [rcx], dx
0x1800084f0  retn
0x1800084f1  test    rdx, rdx
0x1800084f4  jnz     short loc_1800084FF
0x1800084f6  sub     rcx, 2
0x1800084fa  mov     eax, 8007007Ah
0x1800084ff  xor     edx, edx
0x180008501  mov     [rcx], dx
0x180008504  retn
```
