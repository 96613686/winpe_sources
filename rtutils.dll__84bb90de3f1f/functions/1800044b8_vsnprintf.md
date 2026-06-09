# _vsnprintf

- ea: `0x1800044b8`
- end: `0x180004506`
- name: `_vsnprintf`
- size: `78`
- prototype: `int __cdecl(char *const Buffer, const size_t BufferCount, const char *const Format, va_list ArgList)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003040`
- `0x1800035c0`

## callees

- `0x1800037e4`
- `0x1800043f6`

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
0x1800044b8  push    rbx
0x1800044ba  push    rbp
0x1800044bb  push    rsi
0x1800044bc  push    rdi
0x1800044bd  sub     rsp, 38h
0x1800044c1  mov     rbx, r9
0x1800044c4  mov     rdi, r8
0x1800044c7  mov     rsi, rdx
0x1800044ca  mov     rbp, rcx
0x1800044cd  call    __local_stdio_printf_options
0x1800044d2  mov     [rsp+58h+ArgList], rbx; ArgList
0x1800044d7  mov     r9, rdi; Format
0x1800044da  mov     r8, rsi; BufferCount
0x1800044dd  mov     [rsp+58h+Locale], 0; Locale
0x1800044e6  mov     rdx, rbp; Buffer
0x1800044e9  mov     rcx, [rax]
0x1800044ec  or      rcx, 1; Options
0x1800044f0  call    _o___stdio_common_vsprintf_0
0x1800044f5  or      ecx, 0FFFFFFFFh
0x1800044f8  test    eax, eax
0x1800044fa  cmovs   eax, ecx
0x1800044fd  add     rsp, 38h
0x180004501  pop     rdi
0x180004502  pop     rsi
0x180004503  pop     rbp
0x180004504  pop     rbx
0x180004505  retn
```
