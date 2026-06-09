# StringVPrintfWorkerW

- ea: `0x140001ba0`
- end: `0x140001c18`
- name: `StringVPrintfWorkerW`
- size: `120`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_LPCWSTR pszFormat, va_list argList)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14002e518`
- `0x14002ff1c`

## callees

- `0x140001ba0`
- `0x140002408`

## import_xrefs

- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vswprintf` at `0x140001be1`
- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vswprintf` at `0x140001be1`

## pseudocode

```c
HRESULT __stdcall StringVPrintfWorkerW(
        STRSAFE_LPWSTR pszDest,
        size_t cchDest,
        size_t *pcchNewDestLength,
        STRSAFE_LPCWSTR pszFormat,
        va_list argList)
{
  size_t v6; // rdi
  unsigned __int64 v8; // rcx
  int v9; // eax
  HRESULT v10; // ecx

  v6 = cchDest - 1;
  v8 = *_local_stdio_printf_options();
  v9 = __stdio_common_vswprintf(v8 | 1, pszDest, v6, pszFormat, 0, argList);
  if ( v9 < 0 || v9 > v6 )
  {
    v10 = -2147024774;
LABEL_6:
    pszDest[v6] = 0;
    return v10;
  }
  v10 = 0;
  if ( v9 == v6 )
    goto LABEL_6;
  return v10;
}

```

## disassembly

```asm
0x140001ba0  mov     [rsp+arg_0], rbx
0x140001ba5  mov     [rsp+arg_8], rsi
0x140001baa  push    rdi
0x140001bab  sub     rsp, 30h
0x140001baf  mov     rbx, r9
0x140001bb2  lea     rdi, [rdx-1]
0x140001bb6  mov     rsi, rcx
0x140001bb9  call    __local_stdio_printf_options
0x140001bbe  mov     r9, rbx; Format
0x140001bc1  mov     r8, rdi; BufferCount
0x140001bc4  mov     rdx, rsi; Buffer
0x140001bc7  mov     rcx, [rax]
0x140001bca  mov     rax, [rsp+38h+argList]
0x140001bcf  or      rcx, 1; Options
0x140001bd3  mov     [rsp+38h+ArgList], rax; ArgList
0x140001bd8  mov     [rsp+38h+Locale], 0; Locale
0x140001be1  call    cs:__imp___stdio_common_vswprintf
0x140001be7  test    eax, eax
0x140001be9  js      short loc_140001BFB
0x140001beb  cdqe
0x140001bed  cmp     rax, rdi
0x140001bf0  ja      short loc_140001BFB
0x140001bf2  xor     ecx, ecx
0x140001bf4  cmp     rax, rdi
0x140001bf7  jnz     short loc_140001C06
0x140001bf9  jmp     short loc_140001C00
0x140001bfb  mov     ecx, 8007007Ah
0x140001c00  xor     eax, eax
0x140001c02  mov     [rsi+rdi*2], ax
0x140001c06  mov     rbx, [rsp+38h+arg_0]
0x140001c0b  mov     eax, ecx
0x140001c0d  mov     rsi, [rsp+38h+arg_8]
0x140001c12  add     rsp, 30h
0x140001c16  pop     rdi
0x140001c17  retn
```
