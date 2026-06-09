# CUwfStaticConfiguration::`vector deleting destructor'(uint)

- ea: `0x180005b80`
- end: `0x180005bf6`
- name: `??_ECUwfStaticConfiguration@@UEAAPEAXI@Z`
- size: `118`
- prototype: `CUwfStaticConfiguration *__fastcall(CUwfStaticConfiguration *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callees

- `0x180005a90`
- `0x180005b80`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180005bc8`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180005bc8`
- `msvcrt!??3@YAXPEAX@Z` at `0x180005be1`
- `msvcrt!??3@YAXPEAX@Z` at `0x180005be1`

## pseudocode

```c
CUwfStaticConfiguration *__fastcall CUwfStaticConfiguration::`vector deleting destructor'(
        CUwfStaticConfiguration *this,
        char a2)
{
  char *v4; // r15
  __int64 v5; // r14
  CUwfStaticConfiguration *i; // rdi

  if ( (a2 & 2) != 0 )
  {
    v4 = (char *)this - 8;
    v5 = *((_QWORD *)this - 1);
    for ( i = (CUwfStaticConfiguration *)((char *)this + 48 * v5); v5; --v5 )
    {
      i = (CUwfStaticConfiguration *)((char *)i - 48);
      CUwfStaticConfiguration::~CUwfStaticConfiguration(i);
    }
    if ( (a2 & 1) != 0 )
      operator delete[](v4);
    return (CUwfStaticConfiguration *)v4;
  }
  else
  {
    CUwfStaticConfiguration::~CUwfStaticConfiguration(this);
    if ( (a2 & 1) != 0 )
      operator delete(this);
    return this;
  }
}

```

## disassembly

```asm
0x180005b80  push    rbx
0x180005b82  push    rsi
0x180005b83  push    rdi
0x180005b84  push    r14
0x180005b86  push    r15
0x180005b88  sub     rsp, 20h
0x180005b8c  mov     esi, edx
0x180005b8e  mov     rbx, rcx
0x180005b91  test    dl, 2
0x180005b94  jz      short loc_180005BD3
0x180005b96  lea     r15, [rcx-8]
0x180005b9a  mov     r14, [r15]
0x180005b9d  lea     rdi, [r14+r14*2]
0x180005ba1  shl     rdi, 4
0x180005ba5  add     rdi, rcx
0x180005ba8  test    r14, r14
0x180005bab  jz      short loc_180005BBF
0x180005bad  sub     rdi, 30h ; '0'
0x180005bb1  mov     rcx, rdi; this
0x180005bb4  call    ??1CUwfStaticConfiguration@@UEAA@XZ; CUwfStaticConfiguration::~CUwfStaticConfiguration(void)
0x180005bb9  sub     r14, 1
0x180005bbd  jnz     short loc_180005BAD
0x180005bbf  test    sil, 1
0x180005bc3  jz      short loc_180005BCE
0x180005bc5  mov     rcx, r15
0x180005bc8  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180005bce  mov     rax, r15
0x180005bd1  jmp     short loc_180005BEA
0x180005bd3  call    ??1CUwfStaticConfiguration@@UEAA@XZ; CUwfStaticConfiguration::~CUwfStaticConfiguration(void)
0x180005bd8  test    sil, 1
0x180005bdc  jz      short loc_180005BE7
0x180005bde  mov     rcx, rbx
0x180005be1  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180005be7  mov     rax, rbx
0x180005bea  add     rsp, 20h
0x180005bee  pop     r15
0x180005bf0  pop     r14
0x180005bf2  pop     rdi
0x180005bf3  pop     rsi
0x180005bf4  pop     rbx
0x180005bf5  retn
```
