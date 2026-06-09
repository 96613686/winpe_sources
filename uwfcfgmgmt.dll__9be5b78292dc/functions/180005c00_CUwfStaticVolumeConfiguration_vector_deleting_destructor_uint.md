# CUwfStaticVolumeConfiguration::`vector deleting destructor'(uint)

- ea: `0x180005c00`
- end: `0x180005c6f`
- name: `??_ECUwfStaticVolumeConfiguration@@UEAAPEAXI@Z`
- size: `111`
- prototype: `CUwfStaticVolumeConfiguration *__fastcall(CUwfStaticVolumeConfiguration *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callees

- `0x180005ad0`
- `0x180005c00`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180005c43`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180005c43`
- `msvcrt!??3@YAXPEAX@Z` at `0x180005c5c`
- `msvcrt!??3@YAXPEAX@Z` at `0x180005c5c`

## pseudocode

```c
CUwfStaticVolumeConfiguration *__fastcall CUwfStaticVolumeConfiguration::`vector deleting destructor'(
        CUwfStaticVolumeConfiguration *this,
        char a2)
{
  char *v4; // r14
  __int64 v5; // rdi
  CUwfStaticVolumeConfiguration *i; // rbx

  if ( (a2 & 2) != 0 )
  {
    v4 = (char *)this - 8;
    v5 = *((_QWORD *)this - 1);
    for ( i = (CUwfStaticVolumeConfiguration *)((char *)this + 40 * v5); v5; --v5 )
    {
      i = (CUwfStaticVolumeConfiguration *)((char *)i - 40);
      CUwfStaticVolumeConfiguration::~CUwfStaticVolumeConfiguration(i);
    }
    if ( (a2 & 1) != 0 )
      operator delete[](v4);
    return (CUwfStaticVolumeConfiguration *)v4;
  }
  else
  {
    CUwfStaticVolumeConfiguration::~CUwfStaticVolumeConfiguration(this);
    if ( (a2 & 1) != 0 )
      operator delete(this);
    return this;
  }
}

```

## disassembly

```asm
0x180005c00  push    rbx
0x180005c02  push    rsi
0x180005c03  push    rdi
0x180005c04  push    r14
0x180005c06  sub     rsp, 28h
0x180005c0a  mov     esi, edx
0x180005c0c  mov     rbx, rcx
0x180005c0f  test    dl, 2
0x180005c12  jz      short loc_180005C4E
0x180005c14  lea     r14, [rcx-8]
0x180005c18  mov     rdi, [r14]
0x180005c1b  lea     rax, [rdi+rdi*4]
0x180005c1f  lea     rbx, [rcx+rax*8]
0x180005c23  test    rdi, rdi
0x180005c26  jz      short loc_180005C3A
0x180005c28  sub     rbx, 28h ; '('
0x180005c2c  mov     rcx, rbx; this
0x180005c2f  call    ??1CUwfStaticVolumeConfiguration@@UEAA@XZ; CUwfStaticVolumeConfiguration::~CUwfStaticVolumeConfiguration(void)
0x180005c34  sub     rdi, 1
0x180005c38  jnz     short loc_180005C28
0x180005c3a  test    sil, 1
0x180005c3e  jz      short loc_180005C49
0x180005c40  mov     rcx, r14
0x180005c43  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180005c49  mov     rax, r14
0x180005c4c  jmp     short loc_180005C65
0x180005c4e  call    ??1CUwfStaticVolumeConfiguration@@UEAA@XZ; CUwfStaticVolumeConfiguration::~CUwfStaticVolumeConfiguration(void)
0x180005c53  test    sil, 1
0x180005c57  jz      short loc_180005C62
0x180005c59  mov     rcx, rbx
0x180005c5c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180005c62  mov     rax, rbx
0x180005c65  add     rsp, 28h
0x180005c69  pop     r14
0x180005c6b  pop     rdi
0x180005c6c  pop     rsi
0x180005c6d  pop     rbx
0x180005c6e  retn
```
