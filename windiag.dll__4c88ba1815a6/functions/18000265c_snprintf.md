# snprintf

- ea: `0x18000265c`
- end: `0x1800026be`
- name: `snprintf`
- size: `98`
- prototype: `int(char *const Buffer, const size_t BufferCount, const char *const Format, ...)`
- caller_count: `9`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000ecd0`
- `0x18000f600`
- `0x1800288d0`
- `0x18002a010`
- `0x18004e2f0`
- `0x18004ead8`
- `0x18004f3d8`
- `0x180059b9c`
- `0x18008607c`

## callees

- `0x18000264c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___stdio_common_vsprintf` at `0x1800026a7`
- `api-ms-win-crt-private-l1-1-0!_o___stdio_common_vsprintf` at `0x1800026a7`

## pseudocode

```c
int snprintf(char *const Buffer, const size_t BufferCount, const char *const Format, ...)
{
  unsigned __int64 *v6; // rax
  int result; // eax
  va_list va; // [rsp+88h] [rbp+20h] BYREF

  va_start(va, Format);
  v6 = _local_stdio_printf_options();
  result = __stdio_common_vsprintf(*v6 | 2, Buffer, BufferCount, Format, 0, va);
  if ( result < 0 )
    return -1;
  return result;
}

```

## disassembly

```asm
0x18000265c  mov     rax, rsp
0x18000265f  mov     [rax+18h], r8
0x180002663  mov     [rax+20h], r9
0x180002667  push    rbx
0x180002668  push    rbp
0x180002669  push    rsi
0x18000266a  push    rdi
0x18000266b  sub     rsp, 48h
0x18000266f  mov     rsi, r8
0x180002672  mov     qword ptr [rax-38h], 0
0x18000267a  mov     rbx, rdx
0x18000267d  lea     rbp, [rax+20h]
0x180002681  mov     rdi, rcx
0x180002684  call    __local_stdio_printf_options
0x180002689  mov     [rsp+68h+ArgList], rbp; ArgList
0x18000268e  mov     r9, rsi; Format
0x180002691  mov     r8, rbx; BufferCount
0x180002694  mov     [rsp+68h+Locale], 0; Locale
0x18000269d  mov     rdx, rdi; Buffer
0x1800026a0  mov     rcx, [rax]
0x1800026a3  or      rcx, 2; Options
0x1800026a7  call    cs:__imp___stdio_common_vsprintf
0x1800026ad  or      ecx, 0FFFFFFFFh
0x1800026b0  test    eax, eax
0x1800026b2  cmovs   eax, ecx
0x1800026b5  add     rsp, 48h
0x1800026b9  pop     rdi
0x1800026ba  pop     rsi
0x1800026bb  pop     rbp
0x1800026bc  pop     rbx
0x1800026bd  retn
```
