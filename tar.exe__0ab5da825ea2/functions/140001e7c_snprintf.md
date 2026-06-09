# snprintf

- ea: `0x140001e7c`
- end: `0x140001edd`
- name: `snprintf`
- size: `97`
- prototype: `int(char *const Buffer, const size_t BufferCount, const char *const Format, ...)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140004a54`
- `0x140004d0c`
- `0x140005390`

## callees

- `0x140001034`
- `0x140001bd2`

## pseudocode

```c
int snprintf(char *const Buffer, const size_t BufferCount, const char *const Format, ...)
{
  unsigned __int64 *v6; // rax
  int result; // eax
  va_list va; // [rsp+88h] [rbp+20h] BYREF

  va_start(va, Format);
  v6 = _local_stdio_printf_options();
  result = o___stdio_common_vsprintf_0(*v6 | 2, Buffer, BufferCount, Format, 0, va);
  if ( result < 0 )
    return -1;
  return result;
}

```

## disassembly

```asm
0x140001e7c  mov     rax, rsp
0x140001e7f  mov     [rax+18h], r8
0x140001e83  mov     [rax+20h], r9
0x140001e87  push    rbx
0x140001e88  push    rbp
0x140001e89  push    rsi
0x140001e8a  push    rdi
0x140001e8b  sub     rsp, 48h
0x140001e8f  mov     rsi, r8
0x140001e92  mov     qword ptr [rax-38h], 0
0x140001e9a  mov     rbx, rdx
0x140001e9d  lea     rbp, [rax+20h]
0x140001ea1  mov     rdi, rcx
0x140001ea4  call    __local_stdio_printf_options
0x140001ea9  mov     [rsp+68h+ArgList], rbp; ArgList
0x140001eae  mov     r9, rsi; Format
0x140001eb1  mov     r8, rbx; BufferCount
0x140001eb4  mov     [rsp+68h+Locale], 0; Locale
0x140001ebd  mov     rdx, rdi; Buffer
0x140001ec0  mov     rcx, [rax]
0x140001ec3  or      rcx, 2; Options
0x140001ec7  call    _o___stdio_common_vsprintf_0
0x140001ecc  or      ecx, 0FFFFFFFFh
0x140001ecf  test    eax, eax
0x140001ed1  cmovs   eax, ecx
0x140001ed4  add     rsp, 48h
0x140001ed8  pop     rdi
0x140001ed9  pop     rsi
0x140001eda  pop     rbp
0x140001edb  pop     rbx
0x140001edc  retn
```
