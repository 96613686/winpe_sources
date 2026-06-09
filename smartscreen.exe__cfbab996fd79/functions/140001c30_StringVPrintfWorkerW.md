# StringVPrintfWorkerW

- ea: `0x140001c30`
- end: `0x140001caf`
- name: `StringVPrintfWorkerW`
- size: `127`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_LPCWSTR pszFormat, va_list argList)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14002f740`
- `0x14003129c`

## callees

- `0x140001c30`
- `0x1400024f8`

## import_xrefs

- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vswprintf` at `0x140001c71`
- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vswprintf` at `0x140001c71`

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
0x140001c30  mov     [rsp+arg_0], rbx
0x140001c35  mov     [rsp+arg_8], rsi
0x140001c3a  push    rdi
0x140001c3b  sub     rsp, 30h
0x140001c3f  mov     rbx, r9
0x140001c42  lea     rdi, [rdx-1]
0x140001c46  mov     rsi, rcx
0x140001c49  call    __local_stdio_printf_options
0x140001c4e  mov     r9, rbx; Format
0x140001c51  mov     r8, rdi; BufferCount
0x140001c54  mov     rdx, rsi; Buffer
0x140001c57  mov     rcx, [rax]
0x140001c5a  mov     rax, [rsp+38h+argList]
0x140001c5f  or      rcx, 1; Options
0x140001c63  mov     [rsp+38h+ArgList], rax; ArgList
0x140001c68  mov     [rsp+38h+Locale], 0; Locale
0x140001c71  call    cs:__imp___stdio_common_vswprintf
0x140001c78  nop     dword ptr [rax+rax+00h]
0x140001c7d  test    eax, eax
0x140001c7f  js      short loc_140001C91
0x140001c81  cdqe
0x140001c83  cmp     rax, rdi
0x140001c86  ja      short loc_140001C91
0x140001c88  xor     ecx, ecx
0x140001c8a  cmp     rax, rdi
0x140001c8d  jnz     short loc_140001C9C
0x140001c8f  jmp     short loc_140001C96
0x140001c91  mov     ecx, 8007007Ah
0x140001c96  xor     eax, eax
0x140001c98  mov     [rsi+rdi*2], ax
0x140001c9c  mov     rbx, [rsp+38h+arg_0]
0x140001ca1  mov     eax, ecx
0x140001ca3  mov     rsi, [rsp+38h+arg_8]
0x140001ca8  add     rsp, 30h
0x140001cac  pop     rdi
0x140001cad  retn
```
