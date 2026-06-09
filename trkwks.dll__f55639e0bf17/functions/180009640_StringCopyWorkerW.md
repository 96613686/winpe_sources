# StringCopyWorkerW

- ea: `0x180009640`
- end: `0x18000968f`
- name: `StringCopyWorkerW`
- size: `79`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180009364`
- `0x18000a09c`

## callees

- `0x180009640`

## pseudocode

```c
HRESULT __stdcall StringCopyWorkerW(
        STRSAFE_LPWSTR pszDest,
        size_t cchDest,
        size_t *pcchNewDestLength,
        STRSAFE_PCNZWCH pszSrc,
        size_t cchToCopy)
{
  HRESULT v5; // r11d
  __int64 v7; // rax
  HRESULT result; // eax

  v5 = 0;
  v7 = 2147483646;
  if ( cchDest )
  {
    while ( v7 && *pszSrc )
    {
      *pszDest++ = *pszSrc++;
      --v7;
      if ( !--cchDest )
        goto LABEL_5;
    }
  }
  else
  {
LABEL_5:
    --pszDest;
    v5 = -2147024774;
  }
  result = v5;
  *pszDest = 0;
  return result;
}

```

## disassembly

```asm
0x180009640  xor     r11d, r11d
0x180009643  mov     r10, rcx
0x180009646  mov     eax, 7FFFFFFEh
0x18000964b  test    rdx, rdx
0x18000964e  jz      short loc_180009674
0x180009650  test    rax, rax
0x180009653  jz      short loc_180009685
0x180009655  movzx   r8d, word ptr [r9]
0x180009659  test    r8w, r8w
0x18000965d  jz      short loc_180009680
0x18000965f  mov     [r10], r8w
0x180009663  add     r9, 2
0x180009667  add     r10, 2
0x18000966b  dec     rax
0x18000966e  sub     rdx, 1
0x180009672  jnz     short loc_180009650
0x180009674  sub     r10, 2
0x180009678  mov     r11d, 8007007Ah
0x18000967e  jmp     short loc_180009685
0x180009680  test    rdx, rdx
0x180009683  jz      short loc_180009674
0x180009685  xor     ecx, ecx
0x180009687  mov     eax, r11d
0x18000968a  mov     [r10], cx
0x18000968e  retn
```
