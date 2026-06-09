# memcpy_s

- ea: `0x180009dfc`
- end: `0x180009e86`
- name: `memcpy_s`
- size: `138`
- prototype: `static errno_t __cdecl(void *const Destination, const rsize_t DestinationSize, const void *const Source, const rsize_t SourceSize)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180007328`
- `0x1800073a0`
- `0x180008244`

## callees

- `0x180009dfc`
- `0x18000bcc0`
- `0x18000c370`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x180009e2f`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x180009e2f`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180009e22`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180009e64`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180009e22`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180009e64`

## pseudocode

```c
errno_t __cdecl memcpy_s(
        void *const Destination,
        const rsize_t DestinationSize,
        const void *const Source,
        const rsize_t SourceSize)
{
  int *v8; // rax
  errno_t v9; // ebx

  if ( !SourceSize )
    return 0;
  if ( !Destination )
    goto LABEL_4;
  if ( Source && DestinationSize >= SourceSize )
  {
    memmove(Destination, Source, SourceSize);
    return 0;
  }
  memset(Destination, 0, DestinationSize);
  if ( !Source )
  {
LABEL_4:
    v8 = _errno();
    v9 = 22;
LABEL_5:
    *v8 = v9;
    _invalid_parameter_noinfo();
    return v9;
  }
  if ( DestinationSize < SourceSize )
  {
    v8 = _errno();
    v9 = 34;
    goto LABEL_5;
  }
  return 22;
}

```

## disassembly

```asm
0x180009dfc  mov     [rsp+arg_0], rbx
0x180009e01  mov     [rsp+arg_8], rsi
0x180009e06  push    rdi
0x180009e07  sub     rsp, 20h
0x180009e0b  mov     rbx, r9
0x180009e0e  mov     rsi, r8
0x180009e11  mov     rdi, rdx
0x180009e14  test    r9, r9
0x180009e17  jnz     short loc_180009E1D
0x180009e19  xor     eax, eax
0x180009e1b  jmp     short loc_180009E76
0x180009e1d  test    rcx, rcx
0x180009e20  jnz     short loc_180009E39
0x180009e22  call    cs:__imp__errno
0x180009e28  mov     ebx, 16h
0x180009e2d  mov     [rax], ebx
0x180009e2f  call    cs:__imp__invalid_parameter_noinfo
0x180009e35  mov     eax, ebx
0x180009e37  jmp     short loc_180009E76
0x180009e39  test    rsi, rsi
0x180009e3c  jz      short loc_180009E50
0x180009e3e  cmp     rdi, rbx
0x180009e41  jb      short loc_180009E50
0x180009e43  mov     r8, rbx; Size
0x180009e46  mov     rdx, rsi; Src
0x180009e49  call    memmove
0x180009e4e  jmp     short loc_180009E19
0x180009e50  mov     r8, rdi; Size
0x180009e53  xor     edx, edx; Val
0x180009e55  call    memset
0x180009e5a  test    rsi, rsi
0x180009e5d  jz      short loc_180009E22
0x180009e5f  cmp     rdi, rbx
0x180009e62  jnb     short loc_180009E71
0x180009e64  call    cs:__imp__errno
0x180009e6a  mov     ebx, 22h ; '"'
0x180009e6f  jmp     short loc_180009E2D
0x180009e71  mov     eax, 16h
0x180009e76  mov     rbx, [rsp+28h+arg_0]
0x180009e7b  mov     rsi, [rsp+28h+arg_8]
0x180009e80  add     rsp, 20h
0x180009e84  pop     rdi
0x180009e85  retn
```
