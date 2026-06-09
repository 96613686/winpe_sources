# CUwfConfiguration::`vector deleting destructor'(uint)

- ea: `0x180005b00`
- end: `0x180005b76`
- name: `??_ECUwfConfiguration@@UEAAPEAXI@Z`
- size: `118`
- prototype: `CUwfConfiguration *__fastcall(CUwfConfiguration *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callees

- `0x180005a40`
- `0x180005b00`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180005b49`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180005b49`
- `msvcrt!??3@YAXPEAX@Z` at `0x180005b62`
- `msvcrt!??3@YAXPEAX@Z` at `0x180005b62`

## pseudocode

```c
CUwfConfiguration *__fastcall CUwfConfiguration::`vector deleting destructor'(CUwfConfiguration *this, char a2)
{
  char *v4; // rsi
  __int64 v5; // rbp
  CUwfConfiguration *i; // r14

  if ( (a2 & 2) != 0 )
  {
    v4 = (char *)this - 8;
    v5 = *((_QWORD *)this - 1);
    for ( i = (CUwfConfiguration *)((char *)this + 136 * v5); v5; --v5 )
    {
      i = (CUwfConfiguration *)((char *)i - 136);
      CUwfConfiguration::~CUwfConfiguration(i);
    }
    if ( (a2 & 1) != 0 )
      operator delete[](v4);
    return (CUwfConfiguration *)v4;
  }
  else
  {
    CUwfConfiguration::~CUwfConfiguration(this);
    if ( (a2 & 1) != 0 )
      operator delete(this);
    return this;
  }
}

```

## disassembly

```asm
0x180005b00  push    rbx
0x180005b02  push    rbp
0x180005b03  push    rsi
0x180005b04  push    rdi
0x180005b05  push    r14
0x180005b07  sub     rsp, 20h
0x180005b0b  mov     edi, edx
0x180005b0d  mov     rbx, rcx
0x180005b10  test    dl, 2
0x180005b13  jz      short loc_180005B54
0x180005b15  lea     rsi, [rcx-8]
0x180005b19  mov     rbp, [rsi]
0x180005b1c  imul    r14, rbp, 88h
0x180005b23  add     r14, rcx
0x180005b26  test    rbp, rbp
0x180005b29  jz      short loc_180005B40
0x180005b2b  sub     r14, 88h
0x180005b32  mov     rcx, r14; this
0x180005b35  call    ??1CUwfConfiguration@@UEAA@XZ; CUwfConfiguration::~CUwfConfiguration(void)
0x180005b3a  sub     rbp, 1
0x180005b3e  jnz     short loc_180005B2B
0x180005b40  test    dil, 1
0x180005b44  jz      short loc_180005B4F
0x180005b46  mov     rcx, rsi
0x180005b49  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180005b4f  mov     rax, rsi
0x180005b52  jmp     short loc_180005B6B
0x180005b54  call    ??1CUwfConfiguration@@UEAA@XZ; CUwfConfiguration::~CUwfConfiguration(void)
0x180005b59  test    dil, 1
0x180005b5d  jz      short loc_180005B68
0x180005b5f  mov     rcx, rbx
0x180005b62  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180005b68  mov     rax, rbx
0x180005b6b  add     rsp, 20h
0x180005b6f  pop     r14
0x180005b71  pop     rdi
0x180005b72  pop     rsi
0x180005b73  pop     rbp
0x180005b74  pop     rbx
0x180005b75  retn
```
