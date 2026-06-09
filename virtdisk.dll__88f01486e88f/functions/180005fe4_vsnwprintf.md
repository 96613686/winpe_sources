# _vsnwprintf

- ea: `0x180005fe4`
- end: `0x180006032`
- name: `_vsnwprintf`
- size: `78`
- prototype: `int __cdecl(wchar_t *Buffer, size_t BufferCount, const wchar_t *Format, va_list Args)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002010`
- `0x180008834`

## callees

- `0x180005364`
- `0x180005f6a`

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
0x180005fe4  push    rbx
0x180005fe6  push    rbp
0x180005fe7  push    rsi
0x180005fe8  push    rdi
0x180005fe9  sub     rsp, 38h
0x180005fed  mov     rbx, r9
0x180005ff0  mov     rdi, r8
0x180005ff3  mov     rsi, rdx
0x180005ff6  mov     rbp, rcx
0x180005ff9  call    __local_stdio_printf_options
0x180005ffe  mov     [rsp+58h+ArgList], rbx; ArgList
0x180006003  mov     r9, rdi; Format
0x180006006  mov     r8, rsi; BufferCount
0x180006009  mov     [rsp+58h+Locale], 0; Locale
0x180006012  mov     rdx, rbp; Buffer
0x180006015  mov     rcx, [rax]
0x180006018  or      rcx, 1; Options
0x18000601c  call    _o___stdio_common_vswprintf_0
0x180006021  or      ecx, 0FFFFFFFFh
0x180006024  test    eax, eax
0x180006026  cmovs   eax, ecx
0x180006029  add     rsp, 38h
0x18000602d  pop     rdi
0x18000602e  pop     rsi
0x18000602f  pop     rbp
0x180006030  pop     rbx
0x180006031  retn
```
