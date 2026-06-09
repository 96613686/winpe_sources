# StringVPrintfWorkerW

- ea: `0x1800096bc`
- end: `0x180009734`
- name: `StringVPrintfWorkerW`
- size: `120`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_LPCWSTR pszFormat, va_list argList)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180008a48`
- `0x1800095ec`

## callees

- `0x1800096bc`
- `0x180009dec`

## import_xrefs

- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vswprintf` at `0x1800096fd`
- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vswprintf` at `0x1800096fd`

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
0x1800096bc  mov     [rsp+arg_0], rbx
0x1800096c1  mov     [rsp+arg_8], rsi
0x1800096c6  push    rdi
0x1800096c7  sub     rsp, 30h
0x1800096cb  mov     rbx, r9
0x1800096ce  lea     rdi, [rdx-1]
0x1800096d2  mov     rsi, rcx
0x1800096d5  call    __local_stdio_printf_options
0x1800096da  mov     r9, rbx; Format
0x1800096dd  mov     r8, rdi; BufferCount
0x1800096e0  mov     rdx, rsi; Buffer
0x1800096e3  mov     rcx, [rax]
0x1800096e6  mov     rax, [rsp+38h+argList]
0x1800096eb  or      rcx, 1; Options
0x1800096ef  mov     [rsp+38h+ArgList], rax; ArgList
0x1800096f4  mov     [rsp+38h+Locale], 0; Locale
0x1800096fd  call    cs:__imp___stdio_common_vswprintf
0x180009703  test    eax, eax
0x180009705  js      short loc_180009717
0x180009707  cdqe
0x180009709  cmp     rax, rdi
0x18000970c  ja      short loc_180009717
0x18000970e  xor     ecx, ecx
0x180009710  cmp     rax, rdi
0x180009713  jnz     short loc_180009722
0x180009715  jmp     short loc_18000971C
0x180009717  mov     ecx, 8007007Ah
0x18000971c  xor     eax, eax
0x18000971e  mov     [rsi+rdi*2], ax
0x180009722  mov     rbx, [rsp+38h+arg_0]
0x180009727  mov     eax, ecx
0x180009729  mov     rsi, [rsp+38h+arg_8]
0x18000972e  add     rsp, 30h
0x180009732  pop     rdi
0x180009733  retn
```
