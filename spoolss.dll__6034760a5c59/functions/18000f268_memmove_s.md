# memmove_s

- ea: `0x18000f268`
- end: `0x18000f2bb`
- name: `memmove_s`
- size: `83`
- prototype: `static errno_t __cdecl(void *const Destination, const rsize_t DestinationSize, const void *const Source, const rsize_t SourceSize)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180003af0`

## callees

- `0x180005c56`
- `0x18000f268`
- `0x180015048`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000f27b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000f29b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000f27b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000f29b`

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
0x18000f268  push    rbx
0x18000f26a  sub     rsp, 20h
0x18000f26e  mov     rax, r8
0x18000f271  test    r9, r9
0x18000f274  jz      short loc_18000F2B3
0x18000f276  test    rcx, rcx
0x18000f279  jnz     short loc_18000F291
0x18000f27b  call    cs:__imp__o__errno
0x18000f281  mov     ebx, 16h
0x18000f286  mov     [rax], ebx
0x18000f288  call    _invalid_parameter_noinfo
0x18000f28d  mov     eax, ebx
0x18000f28f  jmp     short loc_18000F2B5
0x18000f291  test    rax, rax
0x18000f294  jz      short loc_18000F27B
0x18000f296  cmp     rdx, r9
0x18000f299  jnb     short loc_18000F2A8
0x18000f29b  call    cs:__imp__o__errno
0x18000f2a1  mov     ebx, 22h ; '"'
0x18000f2a6  jmp     short loc_18000F286
0x18000f2a8  mov     r8, r9; Size
0x18000f2ab  mov     rdx, rax; Src
0x18000f2ae  call    memmove_0
0x18000f2b3  xor     eax, eax
0x18000f2b5  add     rsp, 20h
0x18000f2b9  pop     rbx
0x18000f2ba  retn
```
