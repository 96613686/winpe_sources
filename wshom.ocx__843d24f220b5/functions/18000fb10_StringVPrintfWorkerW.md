# StringVPrintfWorkerW

- ea: `0x18000fb10`
- end: `0x18000fb5e`
- name: `StringVPrintfWorkerW`
- size: `78`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_LPCWSTR pszFormat, va_list argList)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000faac`
- `0x18000fb64`

## callees

- `0x18000fb10`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x18000fb2c`
- `msvcrt!_vsnwprintf` at `0x18000fb2c`

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
0x18000fb10  mov     [rsp+arg_0], rbx
0x18000fb15  push    rdi
0x18000fb16  sub     rsp, 20h
0x18000fb1a  lea     rbx, [rdx-1]
0x18000fb1e  mov     r8, r9; Format
0x18000fb21  mov     r9, [rsp+28h+argList]; Args
0x18000fb26  mov     rdx, rbx; BufferCount
0x18000fb29  mov     rdi, rcx
0x18000fb2c  call    cs:__imp__vsnwprintf
0x18000fb32  test    eax, eax
0x18000fb34  js      short loc_18000FB46
0x18000fb36  cdqe
0x18000fb38  cmp     rax, rbx
0x18000fb3b  ja      short loc_18000FB46
0x18000fb3d  xor     ecx, ecx
0x18000fb3f  cmp     rax, rbx
0x18000fb42  jnz     short loc_18000FB51
0x18000fb44  jmp     short loc_18000FB4B
0x18000fb46  mov     ecx, 8007007Ah
0x18000fb4b  xor     eax, eax
0x18000fb4d  mov     [rdi+rbx*2], ax
0x18000fb51  mov     rbx, [rsp+28h+arg_0]
0x18000fb56  mov     eax, ecx
0x18000fb58  add     rsp, 20h
0x18000fb5c  pop     rdi
0x18000fb5d  retn
```
