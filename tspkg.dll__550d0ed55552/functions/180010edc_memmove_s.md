# memmove_s

- ea: `0x180010edc`
- end: `0x180010f2f`
- name: `memmove_s`
- size: `83`
- prototype: `static errno_t __cdecl(void *const Destination, const rsize_t DestinationSize, const void *const Source, const rsize_t SourceSize)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000ae64`

## callees

- `0x18000c110`
- `0x180010edc`
- `0x18001c648`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180010eef`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180010f0f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180010eef`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180010f0f`

## pseudocode

```c
errno_t __cdecl memmove_s(
        void *const Destination,
        const rsize_t DestinationSize,
        const void *const Source,
        const rsize_t SourceSize)
{
  errno_t *v4; // rax
  errno_t v5; // ebx

  if ( SourceSize )
  {
    if ( !Destination || !Source )
    {
      v4 = (errno_t *)_o__errno(Destination, DestinationSize);
      v5 = 22;
LABEL_4:
      *v4 = v5;
      invalid_parameter_noinfo();
      return v5;
    }
    if ( DestinationSize < SourceSize )
    {
      v4 = (errno_t *)((__int64 (*)(void))_o__errno)();
      v5 = 34;
      goto LABEL_4;
    }
    memmove_0(Destination, Source, SourceSize);
  }
  return 0;
}

```

## disassembly

```asm
0x180010edc  push    rbx
0x180010ede  sub     rsp, 20h
0x180010ee2  mov     rax, r8
0x180010ee5  test    r9, r9
0x180010ee8  jz      short loc_180010F27
0x180010eea  test    rcx, rcx
0x180010eed  jnz     short loc_180010F05
0x180010eef  call    cs:__imp__o__errno
0x180010ef5  mov     ebx, 16h
0x180010efa  mov     [rax], ebx
0x180010efc  call    _invalid_parameter_noinfo
0x180010f01  mov     eax, ebx
0x180010f03  jmp     short loc_180010F29
0x180010f05  test    rax, rax
0x180010f08  jz      short loc_180010EEF
0x180010f0a  cmp     rdx, r9
0x180010f0d  jnb     short loc_180010F1C
0x180010f0f  call    cs:__imp__o__errno
0x180010f15  mov     ebx, 22h ; '"'
0x180010f1a  jmp     short loc_180010EFA
0x180010f1c  mov     r8, r9; Size
0x180010f1f  mov     rdx, rax; Src
0x180010f22  call    memmove_0
0x180010f27  xor     eax, eax
0x180010f29  add     rsp, 20h
0x180010f2d  pop     rbx
0x180010f2e  retn
```
