# memcpy_s

- ea: `0x180010e4c`
- end: `0x180010ed5`
- name: `memcpy_s`
- size: `137`
- prototype: `static errno_t __cdecl(void *const Destination, const rsize_t DestinationSize, const void *const Source, const rsize_t SourceSize)`
- caller_count: `8`
- callee_count: `4`
- tags: ``

## callers

- `0x18000d198`
- `0x18000e594`
- `0x18000f188`
- `0x18000fa84`
- `0x18001045c`
- `0x1800107d8`
- `0x180010a1c`
- `0x180010a7c`

## callees

- `0x18000c110`
- `0x18000c1a4`
- `0x180010e4c`
- `0x18001c63c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180010e72`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180010eb3`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180010e72`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180010eb3`

## pseudocode

```c
errno_t __cdecl memcpy_s(
        void *const Destination,
        const rsize_t DestinationSize,
        const void *const Source,
        const rsize_t SourceSize)
{
  errno_t *v8; // rax
  errno_t v9; // ebx

  if ( !SourceSize )
    return 0;
  if ( !Destination )
    goto LABEL_4;
  if ( Source && DestinationSize >= SourceSize )
  {
    memcpy_0(Destination, Source, SourceSize);
    return 0;
  }
  memset_0(Destination, 0, DestinationSize);
  if ( !Source )
  {
LABEL_4:
    v8 = (errno_t *)_o__errno(Destination, DestinationSize);
    v9 = 22;
LABEL_5:
    *v8 = v9;
    invalid_parameter_noinfo();
    return v9;
  }
  if ( DestinationSize < SourceSize )
  {
    v8 = (errno_t *)_o__errno(Destination, DestinationSize);
    v9 = 34;
    goto LABEL_5;
  }
  return 22;
}

```

## disassembly

```asm
0x180010e4c  mov     [rsp+arg_0], rbx
0x180010e51  mov     [rsp+arg_8], rsi
0x180010e56  push    rdi
0x180010e57  sub     rsp, 20h
0x180010e5b  mov     rbx, r9
0x180010e5e  mov     rsi, r8
0x180010e61  mov     rdi, rdx
0x180010e64  test    r9, r9
0x180010e67  jnz     short loc_180010E6D
0x180010e69  xor     eax, eax
0x180010e6b  jmp     short loc_180010EC5
0x180010e6d  test    rcx, rcx
0x180010e70  jnz     short loc_180010E88
0x180010e72  call    cs:__imp__o__errno
0x180010e78  mov     ebx, 16h
0x180010e7d  mov     [rax], ebx
0x180010e7f  call    _invalid_parameter_noinfo
0x180010e84  mov     eax, ebx
0x180010e86  jmp     short loc_180010EC5
0x180010e88  test    rsi, rsi
0x180010e8b  jz      short loc_180010E9F
0x180010e8d  cmp     rdi, rbx
0x180010e90  jb      short loc_180010E9F
0x180010e92  mov     r8, rbx; Size
0x180010e95  mov     rdx, rsi; Src
0x180010e98  call    memcpy_0
0x180010e9d  jmp     short loc_180010E69
0x180010e9f  mov     r8, rdi; Size
0x180010ea2  xor     edx, edx; Val
0x180010ea4  call    memset_0
0x180010ea9  test    rsi, rsi
0x180010eac  jz      short loc_180010E72
0x180010eae  cmp     rdi, rbx
0x180010eb1  jnb     short loc_180010EC0
0x180010eb3  call    cs:__imp__o__errno
0x180010eb9  mov     ebx, 22h ; '"'
0x180010ebe  jmp     short loc_180010E7D
0x180010ec0  mov     eax, 16h
0x180010ec5  mov     rbx, [rsp+28h+arg_0]
0x180010eca  mov     rsi, [rsp+28h+arg_8]
0x180010ecf  add     rsp, 20h
0x180010ed3  pop     rdi
0x180010ed4  retn
```
