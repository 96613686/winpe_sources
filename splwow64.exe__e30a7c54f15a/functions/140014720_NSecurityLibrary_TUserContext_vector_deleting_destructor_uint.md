# NSecurityLibrary::TUserContext::`vector deleting destructor'(uint)

- ea: `0x140014720`
- end: `0x140014754`
- name: `??_ETUserContext@NSecurityLibrary@@UEAAPEAXI@Z`
- size: `52`
- prototype: `void *__fastcall(NSecurityLibrary::TUserContext *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140001b90`
- `0x1400146d4`
- `0x140014720`

## pseudocode

```c
NSecurityLibrary::TUserContext *__fastcall NSecurityLibrary::TUserContext::`vector deleting destructor'(
        NSecurityLibrary::TUserContext *this,
        char a2)
{
  NSecurityLibrary::TUserContext::~TUserContext(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x140014720  mov     [rsp+arg_0], rbx
0x140014725  push    rdi
0x140014726  sub     rsp, 20h
0x14001472a  mov     ebx, edx
0x14001472c  mov     rdi, rcx
0x14001472f  call    ??1TUserContext@NSecurityLibrary@@UEAA@XZ; NSecurityLibrary::TUserContext::~TUserContext(void)
0x140014734  test    bl, 1
0x140014737  jz      short loc_140014746
0x140014739  mov     edx, 28h ; '('
0x14001473e  mov     rcx, rdi; Block
0x140014741  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140014746  mov     rbx, [rsp+28h+arg_0]
0x14001474b  mov     rax, rdi
0x14001474e  add     rsp, 20h
0x140014752  pop     rdi
0x140014753  retn
```
