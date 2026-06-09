# memcpy_s

- ea: `0x180002fb0`
- end: `0x180003039`
- name: `memcpy_s`
- size: `137`
- prototype: `static errno_t __cdecl(void *const Destination, const rsize_t DestinationSize, const void *const Source, const rsize_t SourceSize)`
- caller_count: `7`
- callee_count: `4`
- tags: ``

## callers

- `0x180005b00`
- `0x1800062dc`
- `0x18000883c`
- `0x180008f2c`
- `0x180008fa4`
- `0x18000b208`
- `0x18000e760`

## callees

- `0x180002e76`
- `0x180002ec0`
- `0x180002fb0`
- `0x1800031c8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180002fd6`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180003017`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180002fd6`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180003017`

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
0x180002fb0  mov     [rsp+arg_0], rbx
0x180002fb5  mov     [rsp+arg_8], rsi
0x180002fba  push    rdi
0x180002fbb  sub     rsp, 20h
0x180002fbf  mov     rbx, r9
0x180002fc2  mov     rsi, r8
0x180002fc5  mov     rdi, rdx
0x180002fc8  test    r9, r9
0x180002fcb  jnz     short loc_180002FD1
0x180002fcd  xor     eax, eax
0x180002fcf  jmp     short loc_180003029
0x180002fd1  test    rcx, rcx
0x180002fd4  jnz     short loc_180002FEC
0x180002fd6  call    cs:__imp__o__errno
0x180002fdc  mov     ebx, 16h
0x180002fe1  mov     [rax], ebx
0x180002fe3  call    _invalid_parameter_noinfo
0x180002fe8  mov     eax, ebx
0x180002fea  jmp     short loc_180003029
0x180002fec  test    rsi, rsi
0x180002fef  jz      short loc_180003003
0x180002ff1  cmp     rdi, rbx
0x180002ff4  jb      short loc_180003003
0x180002ff6  mov     r8, rbx; Size
0x180002ff9  mov     rdx, rsi; Src
0x180002ffc  call    memcpy_0
0x180003001  jmp     short loc_180002FCD
0x180003003  mov     r8, rdi; Size
0x180003006  xor     edx, edx; Val
0x180003008  call    memset_0
0x18000300d  test    rsi, rsi
0x180003010  jz      short loc_180002FD6
0x180003012  cmp     rdi, rbx
0x180003015  jnb     short loc_180003024
0x180003017  call    cs:__imp__o__errno
0x18000301d  mov     ebx, 22h ; '"'
0x180003022  jmp     short loc_180002FE1
0x180003024  mov     eax, 16h
0x180003029  mov     rbx, [rsp+28h+arg_0]
0x18000302e  mov     rsi, [rsp+28h+arg_8]
0x180003033  add     rsp, 20h
0x180003037  pop     rdi
0x180003038  retn
```
