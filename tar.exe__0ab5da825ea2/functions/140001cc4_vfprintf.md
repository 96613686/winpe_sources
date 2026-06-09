# vfprintf

- ea: `0x140001cc4`
- end: `0x140001d07`
- name: `vfprintf`
- size: `67`
- prototype: `int __cdecl(FILE *const Stream, const char *const Format, va_list ArgList)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140005680`
- `0x1400071f0`

## callees

- `0x140001034`
- `0x140001bc6`

## pseudocode

```c
int __cdecl vfprintf(FILE *const Stream, const char *const Format, va_list ArgList)
{
  unsigned __int64 *v6; // rax

  v6 = _local_stdio_printf_options();
  return o___stdio_common_vfprintf_0(*v6, Stream, Format, 0, ArgList);
}

```

## disassembly

```asm
0x140001cc4  mov     [rsp+arg_0], rbx
0x140001cc9  mov     [rsp+arg_8], rsi
0x140001cce  push    rdi
0x140001ccf  sub     rsp, 30h
0x140001cd3  mov     rbx, r8
0x140001cd6  mov     rdi, rdx
0x140001cd9  mov     rsi, rcx
0x140001cdc  call    __local_stdio_printf_options
0x140001ce1  xor     r9d, r9d; Locale
0x140001ce4  mov     [rsp+38h+ArgList], rbx; ArgList
0x140001ce9  mov     r8, rdi; Format
0x140001cec  mov     rdx, rsi; Stream
0x140001cef  mov     rcx, [rax]; Options
0x140001cf2  call    _o___stdio_common_vfprintf_0
0x140001cf7  mov     rbx, [rsp+38h+arg_0]
0x140001cfc  mov     rsi, [rsp+38h+arg_8]
0x140001d01  add     rsp, 30h
0x140001d05  pop     rdi
0x140001d06  retn
```
