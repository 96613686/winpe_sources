# memcpy_s

- ea: `0x18000d1bc`
- end: `0x18000d245`
- name: `memcpy_s`
- size: `137`
- prototype: `static errno_t __cdecl(void *const Destination, const rsize_t DestinationSize, const void *const Source, const rsize_t SourceSize)`
- caller_count: `6`
- callee_count: `4`
- tags: ``

## callers

- `0x18000708c`
- `0x18000a934`
- `0x18000ac58`
- `0x18000c468`
- `0x18000c82c`
- `0x18000c964`

## callees

- `0x180002846`
- `0x1800028b4`
- `0x18000d1bc`
- `0x1800198b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000d1e2`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000d223`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000d1e2`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000d223`

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
    v8 = (errno_t *)_o__errno(Destination, DestinationSize, Source);
    v9 = 22;
LABEL_5:
    *v8 = v9;
    invalid_parameter_noinfo();
    return v9;
  }
  if ( DestinationSize < SourceSize )
  {
    v8 = (errno_t *)_o__errno(Destination, DestinationSize, Source);
    v9 = 34;
    goto LABEL_5;
  }
  return 22;
}

```

## disassembly

```asm
0x18000d1bc  mov     [rsp+arg_0], rbx
0x18000d1c1  mov     [rsp+arg_8], rsi
0x18000d1c6  push    rdi
0x18000d1c7  sub     rsp, 20h
0x18000d1cb  mov     rbx, r9
0x18000d1ce  mov     rsi, r8
0x18000d1d1  mov     rdi, rdx
0x18000d1d4  test    r9, r9
0x18000d1d7  jnz     short loc_18000D1DD
0x18000d1d9  xor     eax, eax
0x18000d1db  jmp     short loc_18000D235
0x18000d1dd  test    rcx, rcx
0x18000d1e0  jnz     short loc_18000D1F8
0x18000d1e2  call    cs:__imp__o__errno
0x18000d1e8  mov     ebx, 16h
0x18000d1ed  mov     [rax], ebx
0x18000d1ef  call    _invalid_parameter_noinfo
0x18000d1f4  mov     eax, ebx
0x18000d1f6  jmp     short loc_18000D235
0x18000d1f8  test    rsi, rsi
0x18000d1fb  jz      short loc_18000D20F
0x18000d1fd  cmp     rdi, rbx
0x18000d200  jb      short loc_18000D20F
0x18000d202  mov     r8, rbx; Size
0x18000d205  mov     rdx, rsi; Src
0x18000d208  call    memcpy_0
0x18000d20d  jmp     short loc_18000D1D9
0x18000d20f  mov     r8, rdi; Size
0x18000d212  xor     edx, edx; Val
0x18000d214  call    memset_0
0x18000d219  test    rsi, rsi
0x18000d21c  jz      short loc_18000D1E2
0x18000d21e  cmp     rdi, rbx
0x18000d221  jnb     short loc_18000D230
0x18000d223  call    cs:__imp__o__errno
0x18000d229  mov     ebx, 22h ; '"'
0x18000d22e  jmp     short loc_18000D1ED
0x18000d230  mov     eax, 16h
0x18000d235  mov     rbx, [rsp+28h+arg_0]
0x18000d23a  mov     rsi, [rsp+28h+arg_8]
0x18000d23f  add     rsp, 20h
0x18000d243  pop     rdi
0x18000d244  retn
```
