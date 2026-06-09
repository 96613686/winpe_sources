# StringCchCopyW(x,x,x)

- ea: `0x1000362b`
- end: `0x10003652`
- name: `_StringCchCopyW@12`
- size: `39`
- prototype: `HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x100030b0`
- `0x100032d0`
- `0x1000872c`
- `0x10009f60`

## callees

- `0x1000362b`
- `0x10003660`

## pseudocode

```c

```

## disassembly

```asm
0x1000362b  mov     edi, edi
0x1000362d  push    ebp; pszSrc
0x1000362e  mov     ebp, esp
0x10003630  test    edx, edx
0x10003632  jz      loc_10005C6A
0x10003638  cmp     edx, 7FFFFFFFh
0x1000363e  ja      loc_10005C6A
0x10003644  push    ecx; pcchNewDestLength
0x10003645  push    [ebp+pszDest]; cchDest
0x10003648  push    ecx; pszDest
0x10003649  call    StringCopyWorkerW
0x1000364e  pop     ebp
0x1000364f  retn    4
0x10005c6a  mov     eax, 80070057h
0x10005c6f  test    edx, edx
0x10005c71  jz      loc_1000364E
0x10005c77  xor     edx, edx
0x10005c79  mov     [ecx], dx
0x10005c7c  jmp     loc_1000364E
```
