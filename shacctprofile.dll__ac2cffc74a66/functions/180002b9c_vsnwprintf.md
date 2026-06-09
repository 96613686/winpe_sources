# _vsnwprintf

- ea: `0x180002b9c`
- end: `0x180002bea`
- name: `_vsnwprintf`
- size: `78`
- prototype: `int __cdecl(wchar_t *Buffer, size_t BufferCount, const wchar_t *Format, va_list Args)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180005130`
- `0x180005968`

## callees

- `0x180001e64`
- `0x180002ada`

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
0x180002b9c  push    rbx
0x180002b9e  push    rbp
0x180002b9f  push    rsi
0x180002ba0  push    rdi
0x180002ba1  sub     rsp, 38h
0x180002ba5  mov     rbx, r9
0x180002ba8  mov     rdi, r8
0x180002bab  mov     rsi, rdx
0x180002bae  mov     rbp, rcx
0x180002bb1  call    __local_stdio_printf_options
0x180002bb6  mov     [rsp+58h+ArgList], rbx; ArgList
0x180002bbb  mov     r9, rdi; Format
0x180002bbe  mov     r8, rsi; BufferCount
0x180002bc1  mov     [rsp+58h+Locale], 0; Locale
0x180002bca  mov     rdx, rbp; Buffer
0x180002bcd  mov     rcx, [rax]
0x180002bd0  or      rcx, 1; Options
0x180002bd4  call    _o___stdio_common_vswprintf_0
0x180002bd9  or      ecx, 0FFFFFFFFh
0x180002bdc  test    eax, eax
0x180002bde  cmovs   eax, ecx
0x180002be1  add     rsp, 38h
0x180002be5  pop     rdi
0x180002be6  pop     rsi
0x180002be7  pop     rbp
0x180002be8  pop     rbx
0x180002be9  retn
```
