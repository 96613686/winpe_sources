# VhdmpiCreateAclFromSid(_ACL *,void *,_ACL * *)

- ea: `0x140046544`
- end: `0x140046660`
- name: `?VhdmpiCreateAclFromSid@@YAJPEAU_ACL@@PEAXPEAPEAU1@@Z`
- size: `284`
- prototype: `__int64 __fastcall(PACL Acl, PSID Sid, struct _ACL **)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1400cc9b0`

## callees

- `0x140046544`

## import_xrefs

- `ntoskrnl!RtlLengthSid` at `0x14004656a`
- `ntoskrnl!RtlLengthSid` at `0x14004656a`
- `ntoskrnl!RtlCreateAcl` at `0x1400465b1`
- `ntoskrnl!RtlCreateAcl` at `0x1400465b1`
- `ntoskrnl!RtlGetAce` at `0x1400465d7`
- `ntoskrnl!RtlGetAce` at `0x1400465d7`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400465fe`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140046625`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400465fe`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140046625`
- `ntoskrnl!ExFreePoolWithTag` at `0x140046644`
- `ntoskrnl!ExFreePoolWithTag` at `0x140046644`
- `ntoskrnl!ExAllocatePool2` at `0x140046588`
- `ntoskrnl!ExAllocatePool2` at `0x140046588`

## pseudocode

```c
__int64 __fastcall VhdmpiCreateAclFromSid(PACL Acl, PSID Sid, struct _ACL **a3)
{
  int AclSize; // ebx
  ULONG v7; // ebx
  struct _ACL *Pool2; // rax
  struct _ACL *v9; // rdi
  NTSTATUS v10; // ebx
  ULONG i; // esi
  PVOID Ace; // [rsp+60h] [rbp+8h] BYREF

  AclSize = Acl->AclSize;
  Ace = 0;
  v7 = RtlLengthSid(Sid) + AclSize + 8;
  Pool2 = (struct _ACL *)ExAllocatePool2(256, v7, 1631864918);
  v9 = Pool2;
  if ( Pool2 )
  {
    v10 = RtlCreateAcl(Pool2, v7, 2u);
    if ( v10 < 0 )
      goto LABEL_11;
    for ( i = 0; i < Acl->AceCount; ++i )
    {
      v10 = RtlGetAce(Acl, i, &Ace);
      if ( v10 < 0 )
        goto LABEL_11;
      v10 = RtlAddAccessAllowedAce(v9, 2u, *((_DWORD *)Ace + 1), (char *)Ace + 8);
      if ( v10 < 0 )
        goto LABEL_11;
    }
    v10 = RtlAddAccessAllowedAce(v9, 2u, 0x10000000u, Sid);
    if ( v10 < 0 )
LABEL_11:
      ExFreePoolWithTag(v9, 0x61444856u);
    else
      *a3 = v9;
  }
  else
  {
    return (unsigned int)-1073741670;
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140046544  push    rbx
0x140046546  push    rbp
0x140046547  push    rsi
0x140046548  push    rdi
0x140046549  push    r14
0x14004654b  push    r15
0x14004654d  sub     rsp, 28h
0x140046551  movzx   ebx, word ptr [rcx+2]
0x140046555  mov     rbp, rcx
0x140046558  mov     rcx, rdx; Sid
0x14004655b  mov     [rsp+58h+Ace], 0
0x140046564  mov     r14, r8
0x140046567  mov     r15, rdx
0x14004656a  call    cs:__imp_RtlLengthSid
0x140046571  nop     dword ptr [rax+rax+00h]
0x140046576  add     ebx, 8
0x140046579  mov     ecx, 100h
0x14004657e  add     ebx, eax
0x140046580  mov     r8d, 61444856h
0x140046586  mov     edx, ebx
0x140046588  call    cs:__imp_ExAllocatePool2
0x14004658f  nop     dword ptr [rax+rax+00h]
0x140046594  mov     rdi, rax
0x140046597  test    rax, rax
0x14004659a  jnz     short loc_1400465A6
0x14004659c  mov     ebx, 0C000009Ah
0x1400465a1  jmp     loc_140046650
0x1400465a6  mov     r8d, 2; AclRevision
0x1400465ac  mov     edx, ebx; AclLength
0x1400465ae  mov     rcx, rdi; Acl
0x1400465b1  call    cs:__imp_RtlCreateAcl
0x1400465b8  nop     dword ptr [rax+rax+00h]
0x1400465bd  mov     ebx, eax
0x1400465bf  test    eax, eax
0x1400465c1  js      short loc_14004663C
0x1400465c3  xor     esi, esi
0x1400465c5  movzx   eax, word ptr [rbp+4]
0x1400465c9  cmp     esi, eax
0x1400465cb  jnb     short loc_140046614
0x1400465cd  lea     r8, [rsp+58h+Ace]; Ace
0x1400465d2  mov     edx, esi; AceIndex
0x1400465d4  mov     rcx, rbp; Acl
0x1400465d7  call    cs:__imp_RtlGetAce
0x1400465de  nop     dword ptr [rax+rax+00h]
0x1400465e3  mov     ebx, eax
0x1400465e5  test    eax, eax
0x1400465e7  js      short loc_14004663C
0x1400465e9  mov     r8, [rsp+58h+Ace]
0x1400465ee  mov     edx, 2; AceRevision
0x1400465f3  mov     rcx, rdi; Acl
0x1400465f6  lea     r9, [r8+8]; Sid
0x1400465fa  mov     r8d, [r8+4]; AccessMask
0x1400465fe  call    cs:__imp_RtlAddAccessAllowedAce
0x140046605  nop     dword ptr [rax+rax+00h]
0x14004660a  mov     ebx, eax
0x14004660c  test    eax, eax
0x14004660e  js      short loc_14004663C
0x140046610  inc     esi
0x140046612  jmp     short loc_1400465C5
0x140046614  mov     r9, r15; Sid
0x140046617  mov     edx, 2; AceRevision
0x14004661c  mov     r8d, 10000000h; AccessMask
0x140046622  mov     rcx, rdi; Acl
0x140046625  call    cs:__imp_RtlAddAccessAllowedAce
0x14004662c  nop     dword ptr [rax+rax+00h]
0x140046631  mov     ebx, eax
0x140046633  test    eax, eax
0x140046635  js      short loc_14004663C
0x140046637  mov     [r14], rdi
0x14004663a  jmp     short loc_140046650
0x14004663c  mov     edx, 61444856h; Tag
0x140046641  mov     rcx, rdi; P
0x140046644  call    cs:__imp_ExFreePoolWithTag
0x14004664b  nop     dword ptr [rax+rax+00h]
0x140046650  mov     eax, ebx
0x140046652  add     rsp, 28h
0x140046656  pop     r15
0x140046658  pop     r14
0x14004665a  pop     rdi
0x14004665b  pop     rsi
0x14004665c  pop     rbp
0x14004665d  pop     rbx
0x14004665e  retn
```
