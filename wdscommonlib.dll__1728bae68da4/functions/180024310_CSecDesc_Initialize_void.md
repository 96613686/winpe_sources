# CSecDesc::Initialize(void *)

- ea: `0x180024310`
- end: `0x180024356`
- name: `?Initialize@CSecDesc@@QEAAKPEAX@Z`
- size: `70`
- prototype: `unsigned int __fastcall(void **this, void *Src)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800244c0`

## callees

- `0x180024160`
- `0x180024310`
- `0x180024480`

## import_xrefs

- `ADVAPI32!GetSecurityDescriptorLength` at `0x180024339`
- `ADVAPI32!GetSecurityDescriptorLength` at `0x180024339`

## pseudocode

```c
__int64 __fastcall CSecDesc::Initialize(void **this, void *Src)
{
  unsigned int SelfRelative; // ebx

  CSecDesc::Shutdown((CSecDesc *)this);
  SelfRelative = CSecDesc::CreateSelfRelative(Src, this);
  if ( !SelfRelative )
    *((_DWORD *)this + 2) = GetSecurityDescriptorLength(*this);
  return SelfRelative;
}

```

## disassembly

```asm
0x180024310  mov     [rsp+arg_0], rbx
0x180024315  push    rdi
0x180024316  sub     rsp, 20h
0x18002431a  mov     rbx, rdx
0x18002431d  mov     rdi, rcx
0x180024320  call    ?Shutdown@CSecDesc@@QEAAKXZ; CSecDesc::Shutdown(void)
0x180024325  mov     rdx, rdi; void **
0x180024328  mov     rcx, rbx; Src
0x18002432b  call    ?CreateSelfRelative@CSecDesc@@SAKPEAXPEAPEAX@Z; CSecDesc::CreateSelfRelative(void *,void * *)
0x180024330  mov     ebx, eax
0x180024332  test    eax, eax
0x180024334  jnz     short loc_180024348
0x180024336  mov     rcx, [rdi]; pSecurityDescriptor
0x180024339  call    cs:__imp_GetSecurityDescriptorLength
0x180024340  nop     dword ptr [rax+rax+00h]
0x180024345  mov     [rdi+8], eax
0x180024348  mov     eax, ebx
0x18002434a  mov     rbx, [rsp+28h+arg_0]
0x18002434f  add     rsp, 20h
0x180024353  pop     rdi
0x180024354  retn
```
