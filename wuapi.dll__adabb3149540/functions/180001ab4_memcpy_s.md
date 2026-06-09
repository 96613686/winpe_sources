# memcpy_s

- ea: `0x180001ab4`
- end: `0x180001b3b`
- name: `memcpy_s`
- size: `135`
- prototype: `static errno_t __cdecl(void *const Destination, const rsize_t DestinationSize, const void *const Source, const rsize_t SourceSize)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x18000280c`
- `0x180003bb0`
- `0x180003f10`
- `0x1800044a4`

## callees

- `0x180001ab4`
- `0x18000fc12`
- `0x18000fc4e`
- `0x180015a80`
- `0x180015e40`

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
    memmove(Destination, Source, SourceSize);
    return 0;
  }
  memset(Destination, 0, DestinationSize);
  if ( !Source )
  {
LABEL_4:
    v8 = (errno_t *)o__errno_0();
    v9 = 22;
LABEL_5:
    *v8 = v9;
    invalid_parameter_noinfo();
    return v9;
  }
  if ( DestinationSize < SourceSize )
  {
    v8 = (errno_t *)o__errno_0();
    v9 = 34;
    goto LABEL_5;
  }
  return 22;
}

```

## disassembly

```asm
0x180001ab4  mov     [rsp+arg_0], rbx
0x180001ab9  mov     [rsp+arg_8], rsi
0x180001abe  push    rdi
0x180001abf  sub     rsp, 20h
0x180001ac3  mov     rbx, r9
0x180001ac6  mov     rsi, r8
0x180001ac9  mov     rdi, rdx
0x180001acc  test    r9, r9
0x180001acf  jnz     short loc_180001AD5
0x180001ad1  xor     eax, eax
0x180001ad3  jmp     short loc_180001B2B
0x180001ad5  test    rcx, rcx
0x180001ad8  jnz     short loc_180001AEF
0x180001ada  call    _o__errno_0
0x180001adf  mov     ebx, 16h
0x180001ae4  mov     [rax], ebx
0x180001ae6  call    _invalid_parameter_noinfo
0x180001aeb  mov     eax, ebx
0x180001aed  jmp     short loc_180001B2B
0x180001aef  test    rsi, rsi
0x180001af2  jz      short loc_180001B06
0x180001af4  cmp     rdi, rbx
0x180001af7  jb      short loc_180001B06
0x180001af9  mov     r8, rbx; Size
0x180001afc  mov     rdx, rsi; Src
0x180001aff  call    memmove
0x180001b04  jmp     short loc_180001AD1
0x180001b06  mov     r8, rdi; Size
0x180001b09  xor     edx, edx; Val
0x180001b0b  call    memset
0x180001b10  test    rsi, rsi
0x180001b13  jz      short loc_180001ADA
0x180001b15  cmp     rdi, rbx
0x180001b18  jnb     short loc_180001B26
0x180001b1a  call    _o__errno_0
0x180001b1f  mov     ebx, 22h ; '"'
0x180001b24  jmp     short loc_180001AE4
0x180001b26  mov     eax, 16h
0x180001b2b  mov     rbx, [rsp+28h+arg_0]
0x180001b30  mov     rsi, [rsp+28h+arg_8]
0x180001b35  add     rsp, 20h
0x180001b39  pop     rdi
0x180001b3a  retn
```
