# memcpy_s

- ea: `0x180005dd8`
- end: `0x180005e61`
- name: `memcpy_s`
- size: `137`
- prototype: `static errno_t __cdecl(void *const Destination, const rsize_t DestinationSize, const void *const Source, const rsize_t SourceSize)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180004978`
- `0x180005610`

## callees

- `0x180002b3a`
- `0x180002b8e`
- `0x180005dd8`
- `0x180009730`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180005dfe`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180005e3f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180005dfe`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180005e3f`

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
    v8 = (errno_t *)_o__errno();
    v9 = 22;
LABEL_5:
    *v8 = v9;
    invalid_parameter_noinfo();
    return v9;
  }
  if ( DestinationSize < SourceSize )
  {
    v8 = (errno_t *)_o__errno();
    v9 = 34;
    goto LABEL_5;
  }
  return 22;
}

```

## disassembly

```asm
0x180005dd8  mov     [rsp+arg_0], rbx
0x180005ddd  mov     [rsp+arg_8], rsi
0x180005de2  push    rdi
0x180005de3  sub     rsp, 20h
0x180005de7  mov     rbx, r9
0x180005dea  mov     rsi, r8
0x180005ded  mov     rdi, rdx
0x180005df0  test    r9, r9
0x180005df3  jnz     short loc_180005DF9
0x180005df5  xor     eax, eax
0x180005df7  jmp     short loc_180005E51
0x180005df9  test    rcx, rcx
0x180005dfc  jnz     short loc_180005E14
0x180005dfe  call    cs:__imp__o__errno
0x180005e04  mov     ebx, 16h
0x180005e09  mov     [rax], ebx
0x180005e0b  call    _invalid_parameter_noinfo
0x180005e10  mov     eax, ebx
0x180005e12  jmp     short loc_180005E51
0x180005e14  test    rsi, rsi
0x180005e17  jz      short loc_180005E2B
0x180005e19  cmp     rdi, rbx
0x180005e1c  jb      short loc_180005E2B
0x180005e1e  mov     r8, rbx; Size
0x180005e21  mov     rdx, rsi; Src
0x180005e24  call    memcpy_0
0x180005e29  jmp     short loc_180005DF5
0x180005e2b  mov     r8, rdi; Size
0x180005e2e  xor     edx, edx; Val
0x180005e30  call    memset_0
0x180005e35  test    rsi, rsi
0x180005e38  jz      short loc_180005DFE
0x180005e3a  cmp     rdi, rbx
0x180005e3d  jnb     short loc_180005E4C
0x180005e3f  call    cs:__imp__o__errno
0x180005e45  mov     ebx, 22h ; '"'
0x180005e4a  jmp     short loc_180005E09
0x180005e4c  mov     eax, 16h
0x180005e51  mov     rbx, [rsp+28h+arg_0]
0x180005e56  mov     rsi, [rsp+28h+arg_8]
0x180005e5b  add     rsp, 20h
0x180005e5f  pop     rdi
0x180005e60  retn
```
