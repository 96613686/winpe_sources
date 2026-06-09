# memcpy_s

- ea: `0x180009b1c`
- end: `0x180009ba5`
- name: `memcpy_s`
- size: `137`
- prototype: `static errno_t __cdecl(void *const Destination, const rsize_t DestinationSize, const void *const Source, const rsize_t SourceSize)`
- caller_count: `7`
- callee_count: `4`
- tags: ``

## callers

- `0x180004f74`
- `0x180004fec`
- `0x1800064c4`
- `0x180006bd0`
- `0x180007094`
- `0x180008b7c`
- `0x180009be0`

## callees

- `0x180003346`
- `0x1800033b4`
- `0x180009b1c`
- `0x180010640`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180009b42`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180009b83`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180009b42`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180009b83`

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
0x180009b1c  mov     [rsp+arg_0], rbx
0x180009b21  mov     [rsp+arg_8], rsi
0x180009b26  push    rdi
0x180009b27  sub     rsp, 20h
0x180009b2b  mov     rbx, r9
0x180009b2e  mov     rsi, r8
0x180009b31  mov     rdi, rdx
0x180009b34  test    r9, r9
0x180009b37  jnz     short loc_180009B3D
0x180009b39  xor     eax, eax
0x180009b3b  jmp     short loc_180009B95
0x180009b3d  test    rcx, rcx
0x180009b40  jnz     short loc_180009B58
0x180009b42  call    cs:__imp__o__errno
0x180009b48  mov     ebx, 16h
0x180009b4d  mov     [rax], ebx
0x180009b4f  call    _invalid_parameter_noinfo
0x180009b54  mov     eax, ebx
0x180009b56  jmp     short loc_180009B95
0x180009b58  test    rsi, rsi
0x180009b5b  jz      short loc_180009B6F
0x180009b5d  cmp     rdi, rbx
0x180009b60  jb      short loc_180009B6F
0x180009b62  mov     r8, rbx; Size
0x180009b65  mov     rdx, rsi; Src
0x180009b68  call    memcpy_0
0x180009b6d  jmp     short loc_180009B39
0x180009b6f  mov     r8, rdi; Size
0x180009b72  xor     edx, edx; Val
0x180009b74  call    memset_0
0x180009b79  test    rsi, rsi
0x180009b7c  jz      short loc_180009B42
0x180009b7e  cmp     rdi, rbx
0x180009b81  jnb     short loc_180009B90
0x180009b83  call    cs:__imp__o__errno
0x180009b89  mov     ebx, 22h ; '"'
0x180009b8e  jmp     short loc_180009B4D
0x180009b90  mov     eax, 16h
0x180009b95  mov     rbx, [rsp+28h+arg_0]
0x180009b9a  mov     rsi, [rsp+28h+arg_8]
0x180009b9f  add     rsp, 20h
0x180009ba3  pop     rdi
0x180009ba4  retn
```
