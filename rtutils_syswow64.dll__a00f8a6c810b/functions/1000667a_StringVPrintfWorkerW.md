# StringVPrintfWorkerW

- ea: `0x1000667a`
- end: `0x100066b9`
- name: `StringVPrintfWorkerW`
- size: `63`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_LPCWSTR pszFormat, va_list argList)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x100065eb`
- `0x10006616`
- `0x10006636`

## callees

- `0x100045ad`
- `0x1000667a`

## pseudocode

```c
HRESULT __stdcall StringVPrintfWorkerW(
        STRSAFE_LPWSTR pszDest,
        size_t cchDest,
        size_t *pcchNewDestLength,
        STRSAFE_LPCWSTR pszFormat,
        va_list argList)
{
  int v5; // edx
  wchar_t *v6; // ecx
  unsigned int v7; // esi
  wchar_t *v8; // edi
  HRESULT v9; // ebx
  int v10; // eax

  v7 = v5 - 1;
  v8 = v6;
  v9 = 0;
  v10 = _vsnwprintf(v6, v5 - 1, (const wchar_t *)cchDest, (va_list)pcchNewDestLength);
  if ( v10 < 0 || v10 > v7 )
  {
    v9 = -2147024774;
LABEL_6:
    v8[v7] = 0;
    return v9;
  }
  if ( v10 == v7 )
    goto LABEL_6;
  return v9;
}

```

## disassembly

```asm
0x1000667a  mov     edi, edi
0x1000667c  push    ebp
0x1000667d  mov     ebp, esp
0x1000667f  push    ebx
0x10006680  push    esi
0x10006681  push    edi
0x10006682  push    [ebp+pcchNewDestLength]; Args
0x10006685  lea     esi, [edx-1]
0x10006688  mov     edi, ecx
0x1000668a  push    [ebp+cchDest]; Format
0x1000668d  xor     ebx, ebx
0x1000668f  push    esi; BufferCount
0x10006690  push    edi; Buffer
0x10006691  call    __vsnwprintf
0x10006696  add     esp, 10h
0x10006699  test    eax, eax
0x1000669b  js      short loc_100066A5
0x1000669d  cmp     eax, esi
0x1000669f  ja      short loc_100066A5
0x100066a1  jnz     short loc_100066B0
0x100066a3  jmp     short loc_100066AA
0x100066a5  mov     ebx, 8007007Ah
0x100066aa  xor     eax, eax
0x100066ac  mov     [edi+esi*2], ax
0x100066b0  pop     edi
0x100066b1  pop     esi
0x100066b2  mov     eax, ebx
0x100066b4  pop     ebx
0x100066b5  pop     ebp
0x100066b6  retn    0Ch
```
