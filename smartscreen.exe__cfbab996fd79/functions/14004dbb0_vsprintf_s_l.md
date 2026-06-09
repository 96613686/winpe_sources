# _vsprintf_s_l

- ea: `0x14004dbb0`
- end: `0x14004dc06`
- name: `_vsprintf_s_l`
- size: `86`
- prototype: `int __cdecl(char *const Buffer, const size_t BufferCount, const char *const Format, const _locale_t Locale, va_list ArgList)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14004dc0c`

## callees

- `0x1400024f8`

## import_xrefs

- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vsprintf_s` at `0x14004dbe8`
- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vsprintf_s` at `0x14004dbe8`

## pseudocode

```c
int __cdecl vsprintf_s_l(
        char *const Buffer,
        const size_t BufferCount,
        const char *const Format,
        const _locale_t Locale,
        va_list ArgList)
{
  unsigned __int64 *v9; // rax
  int result; // eax

  v9 = _local_stdio_printf_options();
  result = __stdio_common_vsprintf_s(*v9, Buffer, BufferCount, Format, Locale, ArgList);
  if ( result < 0 )
    return -1;
  return result;
}

```

## disassembly

```asm
0x14004dbb0  push    rbx
0x14004dbb2  push    rbp
0x14004dbb3  push    rsi
0x14004dbb4  push    rdi
0x14004dbb5  sub     rsp, 38h
0x14004dbb9  mov     rbx, r9
0x14004dbbc  mov     rdi, r8
0x14004dbbf  mov     rsi, rdx
0x14004dbc2  mov     rbp, rcx
0x14004dbc5  call    __local_stdio_printf_options
0x14004dbca  mov     r10, [rsp+58h+ArgList]
0x14004dbd2  mov     r9, rdi; Format
0x14004dbd5  mov     [rsp+58h+var_30], r10; ArgList
0x14004dbda  mov     r8, rsi; BufferCount
0x14004dbdd  mov     rdx, rbp; Buffer
0x14004dbe0  mov     [rsp+58h+Locale], rbx; Locale
0x14004dbe5  mov     rcx, [rax]; Options
0x14004dbe8  call    cs:__imp___stdio_common_vsprintf_s
0x14004dbef  nop     dword ptr [rax+rax+00h]
0x14004dbf4  or      ecx, 0FFFFFFFFh
0x14004dbf7  test    eax, eax
0x14004dbf9  cmovs   eax, ecx
0x14004dbfc  add     rsp, 38h
0x14004dc00  pop     rdi
0x14004dc01  pop     rsi
0x14004dc02  pop     rbp
0x14004dc03  pop     rbx
0x14004dc04  retn
```
