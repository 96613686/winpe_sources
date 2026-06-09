# _StringCbPrintfW

- ea: `0x100065eb`
- end: `0x10006610`
- name: `_StringCbPrintfW`
- size: `37`
- prototype: `HRESULT(STRSAFE_LPWSTR pszDest, size_t cbDest, STRSAFE_LPCWSTR pszFormat, ...)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x100020d0`
- `0x10006b80`

## callees

- `0x100065eb`
- `0x1000667a`

## pseudocode

```c

```

## disassembly

```asm
0x100065eb  mov     edi, edi
0x100065ed  push    ebp; pszFormat
0x100065ee  mov     ebp, esp
0x100065f0  mov     edx, [ebp+cbDest]
0x100065f3  shr     edx, 1
0x100065f5  jnz     short loc_100065FE
0x100065f7  mov     eax, 80070057h
0x100065fc  pop     ebp
0x100065fd  retn
0x100065fe  lea     eax, [ebp+pcchNewDestLength]
0x10006601  push    eax; pcchNewDestLength
0x10006602  push    [ebp+pszFormat]; cchDest
0x10006605  push    ecx; pszDest
0x10006606  mov     ecx, [ebp+pszDest]
0x10006609  call    StringVPrintfWorkerW
0x1000660e  pop     ebp
0x1000660f  retn
```
