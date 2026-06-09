# sscanf

- ea: `0x14002e7c0`
- end: `0x14002e812`
- name: `sscanf`
- size: `82`
- prototype: `int(const char *const Buffer, const char *const Format, ...)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14002dcd0`

## callees

- `0x140026924`

## import_xrefs

- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vsscanf` at `0x14002e804`
- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vsscanf` at `0x14002e804`

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
0x14002e7c0  mov     [rsp+arg_8], rdx
0x14002e7c5  mov     qword ptr [rsp+arg_10], r8
0x14002e7ca  mov     [rsp+arg_18], r9
0x14002e7cf  push    rbx
0x14002e7d0  push    rsi
0x14002e7d1  push    rdi
0x14002e7d2  sub     rsp, 30h
0x14002e7d6  mov     rdi, rdx
0x14002e7d9  lea     rsi, [rsp+48h+arg_10]
0x14002e7de  mov     rbx, rcx
0x14002e7e1  call    __local_stdio_scanf_options
0x14002e7e6  mov     [rsp+48h+ArgList], rsi; ArgList
0x14002e7eb  mov     r9, rdi; Format
0x14002e7ee  mov     r8, 0FFFFFFFFFFFFFFFFh; BufferCount
0x14002e7f5  mov     [rsp+48h+Locale], 0; Locale
0x14002e7fe  mov     rdx, rbx; Buffer
0x14002e801  mov     rcx, [rax]; Options
0x14002e804  call    cs:__imp___stdio_common_vsscanf
0x14002e80a  add     rsp, 30h
0x14002e80e  pop     rdi
0x14002e80f  pop     rsi
0x14002e810  pop     rbx
0x14002e811  retn
```
