# NSecurityLibrary::TSidUserContext::~TSidUserContext(void)

- ea: `0x140012a20`
- end: `0x140012a58`
- name: `??1TSidUserContext@NSecurityLibrary@@UEAA@XZ`
- size: `56`
- prototype: `void __fastcall(NSecurityLibrary::TSidUserContext *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x140006f98`
- `0x14000805c`
- `0x14000fae0`
- `0x140012a60`

## callees

- `0x140001b90`
- `0x1400146d4`

## pseudocode

```c
void __fastcall NSecurityLibrary::TSidUserContext::~TSidUserContext(void **this)
{
  *this = &NSecurityLibrary::TSidUserContext::`vftable';
  operator delete(this[6]);
  *((_DWORD *)this + 14) = -2147467259;
  this[6] = 0;
  NSecurityLibrary::TUserContext::~TUserContext((NSecurityLibrary::TUserContext *)this);
}

```

## disassembly

```asm
0x140012a20  push    rbx
0x140012a22  sub     rsp, 20h
0x140012a26  lea     rax, ??_7TSidUserContext@NSecurityLibrary@@6B@; const NSecurityLibrary::TSidUserContext::`vftable'
0x140012a2d  mov     rbx, rcx
0x140012a30  mov     [rcx], rax
0x140012a33  mov     rcx, [rcx+30h]; Block
0x140012a37  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140012a3c  mov     rcx, rbx; this
0x140012a3f  mov     dword ptr [rbx+38h], 80004005h
0x140012a46  mov     qword ptr [rbx+30h], 0
0x140012a4e  add     rsp, 20h
0x140012a52  pop     rbx
0x140012a53  jmp     ??1TUserContext@NSecurityLibrary@@UEAA@XZ; NSecurityLibrary::TUserContext::~TUserContext(void)
```
