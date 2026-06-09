# StringVPrintfWorkerA

- ea: `0x10005d62`
- end: `0x10005da1`
- name: `StringVPrintfWorkerA`
- size: `63`
- prototype: `static HRESULT __stdcall(STRSAFE_LPSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_LPCSTR pszFormat, va_list argList)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x10005d00`
- `0x10005d42`

## callees

- `0x1000460a`
- `0x10005d62`

## pseudocode

```c
HRESULT __stdcall StringVPrintfWorkerA(
        STRSAFE_LPSTR pszDest,
        size_t cchDest,
        size_t *pcchNewDestLength,
        STRSAFE_LPCSTR pszFormat,
        va_list argList)
{
  int v5; // edx
  char *v6; // ecx
  unsigned int v7; // esi
  char *v8; // edi
  HRESULT v9; // ebx
  int v10; // eax

  v7 = v5 - 1;
  v8 = v6;
  v9 = 0;
  v10 = _vsnprintf(v6, v5 - 1, (const char *const)cchDest, (va_list)pcchNewDestLength);
  if ( v10 < 0 || v10 > v7 )
  {
    v8[v7] = 0;
    return -2147024774;
  }
  else if ( v10 == v7 )
  {
    v8[v7] = 0;
  }
  return v9;
}

```

## disassembly

```asm
0x10005d62  mov     edi, edi
0x10005d64  push    ebp
0x10005d65  mov     ebp, esp
0x10005d67  push    ebx
0x10005d68  push    esi
0x10005d69  push    edi
0x10005d6a  push    [ebp+pcchNewDestLength]; ArgList
0x10005d6d  lea     esi, [edx-1]
0x10005d70  mov     edi, ecx
0x10005d72  push    [ebp+cchDest]; Format
0x10005d75  xor     ebx, ebx
0x10005d77  push    esi; BufferCount
0x10005d78  push    edi; Buffer
0x10005d79  call    __vsnprintf
0x10005d7e  add     esp, 10h
0x10005d81  test    eax, eax
0x10005d83  js      short loc_10005D90
0x10005d85  cmp     eax, esi
0x10005d87  ja      short loc_10005D90
0x10005d89  jnz     short loc_10005D98
0x10005d8b  mov     [esi+edi], bl
0x10005d8e  jmp     short loc_10005D98
0x10005d90  mov     [esi+edi], bl
0x10005d93  mov     ebx, 8007007Ah
0x10005d98  pop     edi
0x10005d99  pop     esi
0x10005d9a  mov     eax, ebx
0x10005d9c  pop     ebx
0x10005d9d  pop     ebp
0x10005d9e  retn    0Ch
```
