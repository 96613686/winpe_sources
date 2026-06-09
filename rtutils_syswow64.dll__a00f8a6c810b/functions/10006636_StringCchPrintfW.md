# _StringCchPrintfW

- ea: `0x10006636`
- end: `0x10006674`
- name: `_StringCchPrintfW`
- size: `62`
- prototype: `HRESULT(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszFormat, ...)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x10006770`
- `0x10008d80`
- `0x10009400`
- `0x1000a2ae`

## callees

- `0x10006636`
- `0x1000667a`

## pseudocode

```c

```

## disassembly

```asm
0x10006636  mov     edi, edi
0x10006638  push    ebp; pszFormat
0x10006639  mov     ebp, esp
0x1000663b  mov     eax, [ebp+cchDest]
0x1000663e  test    eax, eax
0x10006640  jz      short loc_1000665F
0x10006642  cmp     eax, 7FFFFFFFh
0x10006647  ja      short loc_1000665F
0x10006649  lea     ecx, [ebp+arg_C]
0x1000664c  mov     edx, eax
0x1000664e  push    ecx; pcchNewDestLength
0x1000664f  push    [ebp+pszFormat]; cchDest
0x10006652  push    ecx; pszDest
0x10006653  mov     ecx, [ebp+pszDest]
0x10006656  call    StringVPrintfWorkerW
0x1000665b  mov     ecx, eax
0x1000665d  jmp     short loc_10006670
0x1000665f  mov     ecx, 80070057h
0x10006664  test    eax, eax
0x10006666  jz      short loc_10006670
0x10006668  mov     eax, [ebp+pszDest]
0x1000666b  xor     edx, edx
0x1000666d  mov     [eax], dx
0x10006670  mov     eax, ecx
0x10006672  pop     ebp
0x10006673  retn
```
