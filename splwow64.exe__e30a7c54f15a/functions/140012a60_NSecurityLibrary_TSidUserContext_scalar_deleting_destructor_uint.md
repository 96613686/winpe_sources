# NSecurityLibrary::TSidUserContext::`scalar deleting destructor'(uint)

- ea: `0x140012a60`
- end: `0x140012a94`
- name: `??_GTSidUserContext@NSecurityLibrary@@UEAAPEAXI@Z`
- size: `52`
- prototype: `void *__fastcall(NSecurityLibrary::TSidUserContext *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x140001b90`
- `0x140012a20`
- `0x140012a60`

## pseudocode

```c
void **__fastcall NSecurityLibrary::TSidUserContext::`scalar deleting destructor'(void **this, char a2)
{
  NSecurityLibrary::TSidUserContext::~TSidUserContext(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x140012a60  mov     [rsp+arg_0], rbx
0x140012a65  push    rdi
0x140012a66  sub     rsp, 20h
0x140012a6a  mov     ebx, edx
0x140012a6c  mov     rdi, rcx
0x140012a6f  call    ??1TSidUserContext@NSecurityLibrary@@UEAA@XZ; NSecurityLibrary::TSidUserContext::~TSidUserContext(void)
0x140012a74  test    bl, 1
0x140012a77  jz      short loc_140012A86
0x140012a79  mov     edx, 40h ; '@'
0x140012a7e  mov     rcx, rdi; Block
0x140012a81  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140012a86  mov     rbx, [rsp+28h+arg_0]
0x140012a8b  mov     rax, rdi
0x140012a8e  add     rsp, 20h
0x140012a92  pop     rdi
0x140012a93  retn
```
