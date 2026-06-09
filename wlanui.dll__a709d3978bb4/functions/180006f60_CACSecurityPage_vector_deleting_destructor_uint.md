# CACSecurityPage::`vector deleting destructor'(uint)

- ea: `0x180006f60`
- end: `0x180006f90`
- name: `??_ECACSecurityPage@@UEAAPEAXI@Z`
- size: `48`
- prototype: `void *__fastcall(CACSecurityPage *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180006cd8`
- `0x180006f60`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180006f7c`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006f7c`

## pseudocode

```c
CACSecurityPage *__fastcall CACSecurityPage::`vector deleting destructor'(CACSecurityPage *this, char a2)
{
  CACSecurityPage::~CACSecurityPage(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180006f60  mov     [rsp+arg_0], rbx
0x180006f65  push    rdi
0x180006f66  sub     rsp, 20h
0x180006f6a  mov     ebx, edx
0x180006f6c  mov     rdi, rcx
0x180006f6f  call    ??1CACSecurityPage@@UEAA@XZ; CACSecurityPage::~CACSecurityPage(void)
0x180006f74  test    bl, 1
0x180006f77  jz      short loc_180006F82
0x180006f79  mov     rcx, rdi
0x180006f7c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180006f82  mov     rbx, [rsp+28h+arg_0]
0x180006f87  mov     rax, rdi
0x180006f8a  add     rsp, 20h
0x180006f8e  pop     rdi
0x180006f8f  retn
```
