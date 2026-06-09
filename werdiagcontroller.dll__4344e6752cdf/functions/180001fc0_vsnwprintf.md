# _vsnwprintf

- ea: `0x180001fc0`
- end: `0x18000200e`
- name: `_vsnwprintf`
- size: `78`
- prototype: `int __cdecl(wchar_t *Buffer, size_t BufferCount, const wchar_t *Format, va_list Args)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800039e0`
- `0x180006128`

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
0x180001fc0  push    rbx
0x180001fc2  push    rbp
0x180001fc3  push    rsi
0x180001fc4  push    rdi
0x180001fc5  sub     rsp, 38h
0x180001fc9  mov     rbx, r9
0x180001fcc  mov     rdi, r8
0x180001fcf  mov     rsi, rdx
0x180001fd2  mov     rbp, rcx
0x180001fd5  call    __local_stdio_printf_options
0x180001fda  mov     [rsp+58h+ArgList], rbx; ArgList
0x180001fdf  mov     r9, rdi; Format
0x180001fe2  mov     r8, rsi; BufferCount
0x180001fe5  mov     [rsp+58h+Locale], 0; Locale
0x180001fee  mov     rdx, rbp; Buffer
0x180001ff1  mov     rcx, [rax]
0x180001ff4  or      rcx, 1; Options
0x180001ff8  call    _o___stdio_common_vswprintf_0
0x180001ffd  or      ecx, 0FFFFFFFFh
0x180002000  test    eax, eax
0x180002002  cmovs   eax, ecx
0x180002005  add     rsp, 38h
0x180002009  pop     rdi
0x18000200a  pop     rsi
0x18000200b  pop     rbp
0x18000200c  pop     rbx
0x18000200d  retn
```
