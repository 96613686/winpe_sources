# _vsnwprintf

- ea: `0x140002c74`
- end: `0x140002cc2`
- name: `_vsnwprintf`
- size: `78`
- prototype: `int __cdecl(wchar_t *Buffer, size_t BufferCount, const wchar_t *Format, va_list Args)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140004fc0`
- `0x140005dc0`
- `0x14000983c`

## callees

- `0x140001e24`
- `0x140002b3a`

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
0x140002c74  push    rbx
0x140002c76  push    rbp
0x140002c77  push    rsi
0x140002c78  push    rdi
0x140002c79  sub     rsp, 38h
0x140002c7d  mov     rbx, r9
0x140002c80  mov     rdi, r8
0x140002c83  mov     rsi, rdx
0x140002c86  mov     rbp, rcx
0x140002c89  call    __local_stdio_printf_options
0x140002c8e  mov     [rsp+58h+ArgList], rbx; ArgList
0x140002c93  mov     r9, rdi; Format
0x140002c96  mov     r8, rsi; BufferCount
0x140002c99  mov     [rsp+58h+Locale], 0; Locale
0x140002ca2  mov     rdx, rbp; Buffer
0x140002ca5  mov     rcx, [rax]
0x140002ca8  or      rcx, 1; Options
0x140002cac  call    _o___stdio_common_vswprintf_0
0x140002cb1  or      ecx, 0FFFFFFFFh
0x140002cb4  test    eax, eax
0x140002cb6  cmovs   eax, ecx
0x140002cb9  add     rsp, 38h
0x140002cbd  pop     rdi
0x140002cbe  pop     rsi
0x140002cbf  pop     rbp
0x140002cc0  pop     rbx
0x140002cc1  retn
```
