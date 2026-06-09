# _vsnwprintf

- ea: `0x1400028c4`
- end: `0x140002912`
- name: `_vsnwprintf`
- size: `78`
- prototype: `int __cdecl(wchar_t *Buffer, size_t BufferCount, const wchar_t *Format, va_list Args)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140005210`
- `0x140005f18`
- `0x1400085d8`
- `0x1400086e0`
- `0x140014c34`

## callees

- `0x140001bd4`
- `0x140002786`

## pseudocode

```c
int __cdecl vsnwprintf(wchar_t *Buffer, size_t BufferCount, const wchar_t *Format, va_list Args)
{
  unsigned __int64 *v8; // rax
  int result; // eax

  v8 = _local_stdio_printf_options();
  result = o___stdio_common_vswprintf_0(*v8 | 1, Buffer, BufferCount, Format, 0, Args);
  if ( result < 0 )
    return -1;
  return result;
}

```

## disassembly

```asm
0x1400028c4  push    rbx
0x1400028c6  push    rbp
0x1400028c7  push    rsi
0x1400028c8  push    rdi
0x1400028c9  sub     rsp, 38h
0x1400028cd  mov     rbx, r9
0x1400028d0  mov     rdi, r8
0x1400028d3  mov     rsi, rdx
0x1400028d6  mov     rbp, rcx
0x1400028d9  call    __local_stdio_printf_options
0x1400028de  mov     [rsp+58h+ArgList], rbx; ArgList
0x1400028e3  mov     r9, rdi; Format
0x1400028e6  mov     r8, rsi; BufferCount
0x1400028e9  mov     [rsp+58h+Locale], 0; Locale
0x1400028f2  mov     rdx, rbp; Buffer
0x1400028f5  mov     rcx, [rax]
0x1400028f8  or      rcx, 1; Options
0x1400028fc  call    _o___stdio_common_vswprintf_0
0x140002901  or      ecx, 0FFFFFFFFh
0x140002904  test    eax, eax
0x140002906  cmovs   eax, ecx
0x140002909  add     rsp, 38h
0x14000290d  pop     rdi
0x14000290e  pop     rsi
0x14000290f  pop     rbp
0x140002910  pop     rbx
0x140002911  retn
```
