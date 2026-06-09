# sscanf

- ea: `0x14002d5f0`
- end: `0x14002d642`
- name: `sscanf`
- size: `82`
- prototype: `int(const char *const Buffer, const char *const Format, ...)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14002cb00`

## callees

- `0x1400257a4`

## import_xrefs

- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vsscanf` at `0x14002d634`
- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vsscanf` at `0x14002d634`

## pseudocode

```c
int sscanf(const char *const Buffer, const char *const Format, ...)
{
  unsigned __int64 *v4; // rax
  va_list va; // [rsp+60h] [rbp+18h] BYREF

  va_start(va, Format);
  v4 = _local_stdio_scanf_options();
  return __stdio_common_vsscanf(*v4, Buffer, 0xFFFFFFFFFFFFFFFFuLL, Format, 0, va);
}

```

## disassembly

```asm
0x14002d5f0  mov     [rsp+arg_8], rdx
0x14002d5f5  mov     qword ptr [rsp+arg_10], r8
0x14002d5fa  mov     [rsp+arg_18], r9
0x14002d5ff  push    rbx
0x14002d600  push    rsi
0x14002d601  push    rdi
0x14002d602  sub     rsp, 30h
0x14002d606  mov     rdi, rdx
0x14002d609  lea     rsi, [rsp+48h+arg_10]
0x14002d60e  mov     rbx, rcx
0x14002d611  call    __local_stdio_scanf_options
0x14002d616  mov     [rsp+48h+ArgList], rsi; ArgList
0x14002d61b  mov     r9, rdi; Format
0x14002d61e  mov     r8, 0FFFFFFFFFFFFFFFFh; BufferCount
0x14002d625  mov     [rsp+48h+Locale], 0; Locale
0x14002d62e  mov     rdx, rbx; Buffer
0x14002d631  mov     rcx, [rax]; Options
0x14002d634  call    cs:__imp___stdio_common_vsscanf
0x14002d63a  add     rsp, 30h
0x14002d63e  pop     rdi
0x14002d63f  pop     rsi
0x14002d640  pop     rbx
0x14002d641  retn
```
