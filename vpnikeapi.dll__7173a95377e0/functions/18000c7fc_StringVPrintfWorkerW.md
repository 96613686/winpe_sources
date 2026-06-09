# StringVPrintfWorkerW

- ea: `0x18000c7fc`
- end: `0x18000c84a`
- name: `StringVPrintfWorkerW`
- size: `78`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_LPCWSTR pszFormat, va_list argList)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180009954`
- `0x18000c740`
- `0x18000ce1c`

## callees

- `0x18000c7fc`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x18000c818`
- `msvcrt!_vsnwprintf` at `0x18000c818`

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
  v7 = _vsnwprintf(pszDest, cchDest - 1, pszFormat, argList);
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
0x18000c7fc  mov     [rsp+arg_0], rbx
0x18000c801  push    rdi
0x18000c802  sub     rsp, 20h
0x18000c806  lea     rbx, [rdx-1]
0x18000c80a  mov     r8, r9; Format
0x18000c80d  mov     r9, [rsp+28h+argList]; Args
0x18000c812  mov     rdx, rbx; BufferCount
0x18000c815  mov     rdi, rcx
0x18000c818  call    cs:__imp__vsnwprintf
0x18000c81e  test    eax, eax
0x18000c820  js      short loc_18000C832
0x18000c822  cdqe
0x18000c824  cmp     rax, rbx
0x18000c827  ja      short loc_18000C832
0x18000c829  xor     ecx, ecx
0x18000c82b  cmp     rax, rbx
0x18000c82e  jnz     short loc_18000C83D
0x18000c830  jmp     short loc_18000C837
0x18000c832  mov     ecx, 8007007Ah
0x18000c837  xor     eax, eax
0x18000c839  mov     [rdi+rbx*2], ax
0x18000c83d  mov     rbx, [rsp+28h+arg_0]
0x18000c842  mov     eax, ecx
0x18000c844  add     rsp, 20h
0x18000c848  pop     rdi
0x18000c849  retn
```
