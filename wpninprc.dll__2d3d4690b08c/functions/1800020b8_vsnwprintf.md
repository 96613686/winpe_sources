# _vsnwprintf

- ea: `0x1800020b8`
- end: `0x180002106`
- name: `_vsnwprintf`
- size: `78`
- prototype: `int __cdecl(wchar_t *Buffer, size_t BufferCount, const wchar_t *Format, va_list Args)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002b00`
- `0x180003370`

## callees

- `0x180001144`
- `0x180001fea`

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
0x1800020b8  push    rbx
0x1800020ba  push    rbp
0x1800020bb  push    rsi
0x1800020bc  push    rdi
0x1800020bd  sub     rsp, 38h
0x1800020c1  mov     rbx, r9
0x1800020c4  mov     rdi, r8
0x1800020c7  mov     rsi, rdx
0x1800020ca  mov     rbp, rcx
0x1800020cd  call    __local_stdio_printf_options
0x1800020d2  mov     [rsp+58h+ArgList], rbx; ArgList
0x1800020d7  mov     r9, rdi; Format
0x1800020da  mov     r8, rsi; BufferCount
0x1800020dd  mov     [rsp+58h+Locale], 0; Locale
0x1800020e6  mov     rdx, rbp; Buffer
0x1800020e9  mov     rcx, [rax]
0x1800020ec  or      rcx, 1; Options
0x1800020f0  call    _o___stdio_common_vswprintf_0
0x1800020f5  or      ecx, 0FFFFFFFFh
0x1800020f8  test    eax, eax
0x1800020fa  cmovs   eax, ecx
0x1800020fd  add     rsp, 38h
0x180002101  pop     rdi
0x180002102  pop     rsi
0x180002103  pop     rbp
0x180002104  pop     rbx
0x180002105  retn
```
