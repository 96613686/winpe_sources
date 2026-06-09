# CSecDesc::Initialize(void *)

- ea: `0x180023270`
- end: `0x1800232b6`
- name: `?Initialize@CSecDesc@@QEAAKPEAX@Z`
- size: `70`
- prototype: `unsigned int __fastcall(void **this, void *Src)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180023410`

## callees

- `0x1800230d0`
- `0x180023270`
- `0x1800233e0`

## import_xrefs

- `ADVAPI32!GetSecurityDescriptorLength` at `0x180023299`
- `ADVAPI32!GetSecurityDescriptorLength` at `0x180023299`

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
0x180023270  mov     [rsp+arg_0], rbx
0x180023275  push    rdi
0x180023276  sub     rsp, 20h
0x18002327a  mov     rbx, rdx
0x18002327d  mov     rdi, rcx
0x180023280  call    ?Shutdown@CSecDesc@@QEAAKXZ; CSecDesc::Shutdown(void)
0x180023285  mov     rdx, rdi; void **
0x180023288  mov     rcx, rbx; Src
0x18002328b  call    ?CreateSelfRelative@CSecDesc@@SAKPEAXPEAPEAX@Z; CSecDesc::CreateSelfRelative(void *,void * *)
0x180023290  mov     ebx, eax
0x180023292  test    eax, eax
0x180023294  jnz     short loc_1800232A8
0x180023296  mov     rcx, [rdi]; pSecurityDescriptor
0x180023299  call    cs:__imp_GetSecurityDescriptorLength
0x1800232a0  nop     dword ptr [rax+rax+00h]
0x1800232a5  mov     [rdi+8], eax
0x1800232a8  mov     eax, ebx
0x1800232aa  mov     rbx, [rsp+28h+arg_0]
0x1800232af  add     rsp, 20h
0x1800232b3  pop     rdi
0x1800232b4  retn
```
