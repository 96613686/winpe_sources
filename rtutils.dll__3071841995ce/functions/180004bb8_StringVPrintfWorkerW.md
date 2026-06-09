# StringVPrintfWorkerW

- ea: `0x180004bb8`
- end: `0x180004c05`
- name: `StringVPrintfWorkerW`
- size: `77`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_LPCWSTR pszFormat, va_list argList)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800049c8`
- `0x180004afc`
- `0x18000570c`

## callees

- `0x180004464`
- `0x180004bb8`

## pseudocode

```c
HRESULT __stdcall StringVPrintfWorkerW(
        STRSAFE_LPWSTR pszDest,
        size_t cchDest,
        size_t *pcchNewDestLength,
        STRSAFE_LPCWSTR pszFormat,
        va_list argList)
{
  size_t v5; // rbx
  int v7; // eax
  HRESULT v8; // ecx

  v5 = cchDest - 1;
  v7 = vsnwprintf(pszDest, cchDest - 1, pszFormat, argList);
  if ( v7 < 0 || v7 > v5 )
  {
    v8 = -2147024774;
LABEL_6:
    pszDest[v5] = 0;
    return v8;
  }
  v8 = 0;
  if ( v7 == v5 )
    goto LABEL_6;
  return v8;
}

```

## disassembly

```asm
0x180004bb8  mov     [rsp+arg_0], rbx
0x180004bbd  push    rdi
0x180004bbe  sub     rsp, 20h
0x180004bc2  lea     rbx, [rdx-1]
0x180004bc6  mov     r8, r9; Format
0x180004bc9  mov     r9, [rsp+28h+argList]; Args
0x180004bce  mov     rdx, rbx; BufferCount
0x180004bd1  mov     rdi, rcx
0x180004bd4  call    _vsnwprintf
0x180004bd9  test    eax, eax
0x180004bdb  js      short loc_180004BED
0x180004bdd  cdqe
0x180004bdf  cmp     rax, rbx
0x180004be2  ja      short loc_180004BED
0x180004be4  xor     ecx, ecx
0x180004be6  cmp     rax, rbx
0x180004be9  jnz     short loc_180004BF8
0x180004beb  jmp     short loc_180004BF2
0x180004bed  mov     ecx, 8007007Ah
0x180004bf2  xor     eax, eax
0x180004bf4  mov     [rdi+rbx*2], ax
0x180004bf8  mov     rbx, [rsp+28h+arg_0]
0x180004bfd  mov     eax, ecx
0x180004bff  add     rsp, 20h
0x180004c03  pop     rdi
0x180004c04  retn
```
