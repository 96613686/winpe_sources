# _vsprintf_s_l

- ea: `0x14004c270`
- end: `0x14004c2bf`
- name: `_vsprintf_s_l`
- size: `79`
- prototype: `int __cdecl(char *const Buffer, const size_t BufferCount, const char *const Format, const _locale_t Locale, va_list ArgList)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14004c2c8`

## callees

- `0x140002408`

## import_xrefs

- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vsprintf_s` at `0x14004c2a8`
- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vsprintf_s` at `0x14004c2a8`

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
0x14004c270  push    rbx
0x14004c272  push    rbp
0x14004c273  push    rsi
0x14004c274  push    rdi
0x14004c275  sub     rsp, 38h
0x14004c279  mov     rbx, r9
0x14004c27c  mov     rdi, r8
0x14004c27f  mov     rsi, rdx
0x14004c282  mov     rbp, rcx
0x14004c285  call    __local_stdio_printf_options
0x14004c28a  mov     r10, [rsp+58h+ArgList]
0x14004c292  mov     r9, rdi; Format
0x14004c295  mov     [rsp+58h+var_30], r10; ArgList
0x14004c29a  mov     r8, rsi; BufferCount
0x14004c29d  mov     rdx, rbp; Buffer
0x14004c2a0  mov     [rsp+58h+Locale], rbx; Locale
0x14004c2a5  mov     rcx, [rax]; Options
0x14004c2a8  call    cs:__imp___stdio_common_vsprintf_s
0x14004c2ae  or      ecx, 0FFFFFFFFh
0x14004c2b1  test    eax, eax
0x14004c2b3  cmovs   eax, ecx
0x14004c2b6  add     rsp, 38h
0x14004c2ba  pop     rdi
0x14004c2bb  pop     rsi
0x14004c2bc  pop     rbp
0x14004c2bd  pop     rbx
0x14004c2be  retn
```
