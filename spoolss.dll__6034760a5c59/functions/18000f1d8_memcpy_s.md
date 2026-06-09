# memcpy_s

- ea: `0x18000f1d8`
- end: `0x18000f261`
- name: `memcpy_s`
- size: `137`
- prototype: `static errno_t __cdecl(void *const Destination, const rsize_t DestinationSize, const void *const Source, const rsize_t SourceSize)`
- caller_count: `8`
- callee_count: `4`
- tags: ``

## callers

- `0x180006d94`
- `0x180006e0c`
- `0x180008a54`
- `0x18000992c`
- `0x18000b4e8`
- `0x18000b9a8`
- `0x18000bcac`
- `0x18000bd0c`

## callees

- `0x180005c56`
- `0x180005cac`
- `0x18000f1d8`
- `0x18001503c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000f1fe`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000f23f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000f1fe`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000f23f`

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
0x18000f1d8  mov     [rsp+arg_0], rbx
0x18000f1dd  mov     [rsp+arg_8], rsi
0x18000f1e2  push    rdi
0x18000f1e3  sub     rsp, 20h
0x18000f1e7  mov     rbx, r9
0x18000f1ea  mov     rsi, r8
0x18000f1ed  mov     rdi, rdx
0x18000f1f0  test    r9, r9
0x18000f1f3  jnz     short loc_18000F1F9
0x18000f1f5  xor     eax, eax
0x18000f1f7  jmp     short loc_18000F251
0x18000f1f9  test    rcx, rcx
0x18000f1fc  jnz     short loc_18000F214
0x18000f1fe  call    cs:__imp__o__errno
0x18000f204  mov     ebx, 16h
0x18000f209  mov     [rax], ebx
0x18000f20b  call    _invalid_parameter_noinfo
0x18000f210  mov     eax, ebx
0x18000f212  jmp     short loc_18000F251
0x18000f214  test    rsi, rsi
0x18000f217  jz      short loc_18000F22B
0x18000f219  cmp     rdi, rbx
0x18000f21c  jb      short loc_18000F22B
0x18000f21e  mov     r8, rbx; Size
0x18000f221  mov     rdx, rsi; Src
0x18000f224  call    memcpy_0
0x18000f229  jmp     short loc_18000F1F5
0x18000f22b  mov     r8, rdi; Size
0x18000f22e  xor     edx, edx; Val
0x18000f230  call    memset_0
0x18000f235  test    rsi, rsi
0x18000f238  jz      short loc_18000F1FE
0x18000f23a  cmp     rdi, rbx
0x18000f23d  jnb     short loc_18000F24C
0x18000f23f  call    cs:__imp__o__errno
0x18000f245  mov     ebx, 22h ; '"'
0x18000f24a  jmp     short loc_18000F209
0x18000f24c  mov     eax, 16h
0x18000f251  mov     rbx, [rsp+28h+arg_0]
0x18000f256  mov     rsi, [rsp+28h+arg_8]
0x18000f25b  add     rsp, 20h
0x18000f25f  pop     rdi
0x18000f260  retn
```
