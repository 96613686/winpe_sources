# _vsnwprintf

- ea: `0x180001cb0`
- end: `0x180001cfe`
- name: `_vsnwprintf`
- size: `78`
- prototype: `int __cdecl(wchar_t *Buffer, size_t BufferCount, const wchar_t *Format, va_list Args)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800024f0`

## callees

- `0x180001034`
- `0x180001c42`

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
0x180001cb0  push    rbx
0x180001cb2  push    rbp
0x180001cb3  push    rsi
0x180001cb4  push    rdi
0x180001cb5  sub     rsp, 38h
0x180001cb9  mov     rbx, r9
0x180001cbc  mov     rdi, r8
0x180001cbf  mov     rsi, rdx
0x180001cc2  mov     rbp, rcx
0x180001cc5  call    __local_stdio_printf_options
0x180001cca  mov     [rsp+58h+ArgList], rbx; ArgList
0x180001ccf  mov     r9, rdi; Format
0x180001cd2  mov     r8, rsi; BufferCount
0x180001cd5  mov     [rsp+58h+Locale], 0; Locale
0x180001cde  mov     rdx, rbp; Buffer
0x180001ce1  mov     rcx, [rax]
0x180001ce4  or      rcx, 1; Options
0x180001ce8  call    _o___stdio_common_vswprintf_0
0x180001ced  or      ecx, 0FFFFFFFFh
0x180001cf0  test    eax, eax
0x180001cf2  cmovs   eax, ecx
0x180001cf5  add     rsp, 38h
0x180001cf9  pop     rdi
0x180001cfa  pop     rsi
0x180001cfb  pop     rbp
0x180001cfc  pop     rbx
0x180001cfd  retn
```
