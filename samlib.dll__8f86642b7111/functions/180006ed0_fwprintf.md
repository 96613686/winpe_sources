# fwprintf

- ea: `0x180006ed0`
- end: `0x180006f1b`
- name: `fwprintf`
- size: `75`
- prototype: `int(FILE *const Stream, const wchar_t *const Format, ...)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180008250`
- `0x1800088b8`
- `0x1800089d8`
- `0x180008a78`
- `0x180008c40`

## callees

- `0x180006254`
- `0x180006e56`

## pseudocode

```c
int fwprintf(FILE *const Stream, const wchar_t *const Format, ...)
{
  unsigned __int64 *v4; // rax
  va_list va; // [rsp+70h] [rbp+18h] BYREF

  va_start(va, Format);
  v4 = _local_stdio_printf_options();
  return _stdio_common_vfwprintf(*v4, Stream, Format, 0, va);
}

```

## disassembly

```asm
0x180006ed0  mov     rax, rsp
0x180006ed3  mov     [rax+10h], rdx
0x180006ed7  mov     [rax+18h], r8
0x180006edb  mov     [rax+20h], r9
0x180006edf  push    rbx
0x180006ee0  push    rsi
0x180006ee1  push    rdi
0x180006ee2  sub     rsp, 40h
0x180006ee6  mov     rdi, rdx
0x180006ee9  mov     qword ptr [rax-28h], 0
0x180006ef1  mov     rbx, rcx
0x180006ef4  lea     rsi, [rax+18h]
0x180006ef8  call    __local_stdio_printf_options
0x180006efd  xor     r9d, r9d; Locale
0x180006f00  mov     [rsp+58h+ArgList], rsi; ArgList
0x180006f05  mov     r8, rdi; Format
0x180006f08  mov     rdx, rbx; Stream
0x180006f0b  mov     rcx, [rax]; Options
0x180006f0e  call    __stdio_common_vfwprintf
0x180006f13  add     rsp, 40h
0x180006f17  pop     rdi
0x180006f18  pop     rsi
0x180006f19  pop     rbx
0x180006f1a  retn
```
