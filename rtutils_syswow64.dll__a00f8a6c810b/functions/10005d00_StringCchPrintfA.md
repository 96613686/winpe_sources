# _StringCchPrintfA

- ea: `0x10005d00`
- end: `0x10005d3c`
- name: `_StringCchPrintfA`
- size: `60`
- prototype: `HRESULT(STRSAFE_LPSTR pszDest, size_t cchDest, STRSAFE_LPCSTR pszFormat, ...)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x10003000`
- `0x10005dd0`
- `0x100062d0`
- `0x100086c3`

## callees

- `0x10005d00`
- `0x10005d62`

## pseudocode

```c

```

## disassembly

```asm
0x10005d00  mov     edi, edi
0x10005d02  push    ebp; pszFormat
0x10005d03  mov     ebp, esp
0x10005d05  mov     eax, [ebp+cchDest]
0x10005d08  test    eax, eax
0x10005d0a  jz      short loc_10005D29
0x10005d0c  cmp     eax, 7FFFFFFFh
0x10005d11  ja      short loc_10005D29
0x10005d13  lea     ecx, [ebp+pcchNewDestLength]
0x10005d16  mov     edx, eax
0x10005d18  push    ecx; pcchNewDestLength
0x10005d19  push    [ebp+pszFormat]; cchDest
0x10005d1c  push    ecx; pszDest
0x10005d1d  mov     ecx, [ebp+pszDest]
0x10005d20  call    StringVPrintfWorkerA
0x10005d25  mov     ecx, eax
0x10005d27  jmp     short loc_10005D38
0x10005d29  mov     ecx, 80070057h
0x10005d2e  test    eax, eax
0x10005d30  jz      short loc_10005D38
0x10005d32  mov     eax, [ebp+pszDest]
0x10005d35  mov     byte ptr [eax], 0
0x10005d38  mov     eax, ecx
0x10005d3a  pop     ebp
0x10005d3b  retn
```
