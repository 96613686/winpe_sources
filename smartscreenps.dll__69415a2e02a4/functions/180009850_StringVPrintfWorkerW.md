# StringVPrintfWorkerW

- ea: `0x180009850`
- end: `0x1800098cf`
- name: `StringVPrintfWorkerW`
- size: `127`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_LPCWSTR pszFormat, va_list argList)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180008b6c`
- `0x180009780`

## callees

- `0x180009850`
- `0x18000a018`

## import_xrefs

- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vswprintf` at `0x180009891`
- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vswprintf` at `0x180009891`

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
0x180009850  mov     [rsp+arg_0], rbx
0x180009855  mov     [rsp+arg_8], rsi
0x18000985a  push    rdi
0x18000985b  sub     rsp, 30h
0x18000985f  mov     rbx, r9
0x180009862  lea     rdi, [rdx-1]
0x180009866  mov     rsi, rcx
0x180009869  call    __local_stdio_printf_options
0x18000986e  mov     r9, rbx; Format
0x180009871  mov     r8, rdi; BufferCount
0x180009874  mov     rdx, rsi; Buffer
0x180009877  mov     rcx, [rax]
0x18000987a  mov     rax, [rsp+38h+argList]
0x18000987f  or      rcx, 1; Options
0x180009883  mov     [rsp+38h+ArgList], rax; ArgList
0x180009888  mov     [rsp+38h+Locale], 0; Locale
0x180009891  call    cs:__imp___stdio_common_vswprintf
0x180009898  nop     dword ptr [rax+rax+00h]
0x18000989d  test    eax, eax
0x18000989f  js      short loc_1800098B1
0x1800098a1  cdqe
0x1800098a3  cmp     rax, rdi
0x1800098a6  ja      short loc_1800098B1
0x1800098a8  xor     ecx, ecx
0x1800098aa  cmp     rax, rdi
0x1800098ad  jnz     short loc_1800098BC
0x1800098af  jmp     short loc_1800098B6
0x1800098b1  mov     ecx, 8007007Ah
0x1800098b6  xor     eax, eax
0x1800098b8  mov     [rsi+rdi*2], ax
0x1800098bc  mov     rbx, [rsp+38h+arg_0]
0x1800098c1  mov     eax, ecx
0x1800098c3  mov     rsi, [rsp+38h+arg_8]
0x1800098c8  add     rsp, 30h
0x1800098cc  pop     rdi
0x1800098cd  retn
```
