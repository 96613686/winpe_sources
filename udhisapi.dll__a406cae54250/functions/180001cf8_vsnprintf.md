# _vsnprintf

- ea: `0x180001cf8`
- end: `0x180001d46`
- name: `_vsnprintf`
- size: `78`
- prototype: `int __cdecl(char *const Buffer, const size_t BufferCount, const char *const Format, va_list ArgList)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800034d4`
- `0x180006bc4`

## callees

- `0x180001034`
- `0x180001c2a`

## pseudocode

```c
int __cdecl vsnprintf(char *const Buffer, const size_t BufferCount, const char *const Format, va_list ArgList)
{
  unsigned __int64 *v8; // rax
  int result; // eax

  v8 = _local_stdio_printf_options();
  result = o___stdio_common_vsprintf_0(*v8 | 1, Buffer, BufferCount, Format, 0, ArgList);
  if ( result < 0 )
    return -1;
  return result;
}

```

## disassembly

```asm
0x180001cf8  push    rbx
0x180001cfa  push    rbp
0x180001cfb  push    rsi
0x180001cfc  push    rdi
0x180001cfd  sub     rsp, 38h
0x180001d01  mov     rbx, r9
0x180001d04  mov     rdi, r8
0x180001d07  mov     rsi, rdx
0x180001d0a  mov     rbp, rcx
0x180001d0d  call    __local_stdio_printf_options
0x180001d12  mov     [rsp+58h+ArgList], rbx; ArgList
0x180001d17  mov     r9, rdi; Format
0x180001d1a  mov     r8, rsi; BufferCount
0x180001d1d  mov     [rsp+58h+Locale], 0; Locale
0x180001d26  mov     rdx, rbp; Buffer
0x180001d29  mov     rcx, [rax]
0x180001d2c  or      rcx, 1; Options
0x180001d30  call    _o___stdio_common_vsprintf_0
0x180001d35  or      ecx, 0FFFFFFFFh
0x180001d38  test    eax, eax
0x180001d3a  cmovs   eax, ecx
0x180001d3d  add     rsp, 38h
0x180001d41  pop     rdi
0x180001d42  pop     rsi
0x180001d43  pop     rbp
0x180001d44  pop     rbx
0x180001d45  retn
```
