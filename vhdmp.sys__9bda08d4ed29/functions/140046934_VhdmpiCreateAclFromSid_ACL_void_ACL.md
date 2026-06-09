# VhdmpiCreateAclFromSid(_ACL *,void *,_ACL * *)

- ea: `0x140046934`
- end: `0x140046a50`
- name: `?VhdmpiCreateAclFromSid@@YAJPEAU_ACL@@PEAXPEAPEAU1@@Z`
- size: `284`
- prototype: `__int64 __fastcall(PACL Acl, PSID Sid, struct _ACL **)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1400cc9a0`

## callees

- `0x140046934`

## import_xrefs

- `ntoskrnl!RtlLengthSid` at `0x14004695a`
- `ntoskrnl!RtlLengthSid` at `0x14004695a`
- `ntoskrnl!RtlCreateAcl` at `0x1400469a1`
- `ntoskrnl!RtlCreateAcl` at `0x1400469a1`
- `ntoskrnl!RtlGetAce` at `0x1400469c7`
- `ntoskrnl!RtlGetAce` at `0x1400469c7`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400469ee`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140046a15`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400469ee`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140046a15`
- `ntoskrnl!ExFreePoolWithTag` at `0x140046a34`
- `ntoskrnl!ExFreePoolWithTag` at `0x140046a34`
- `ntoskrnl!ExAllocatePool2` at `0x140046978`
- `ntoskrnl!ExAllocatePool2` at `0x140046978`

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
0x140046934  push    rbx
0x140046936  push    rbp
0x140046937  push    rsi
0x140046938  push    rdi
0x140046939  push    r14
0x14004693b  push    r15
0x14004693d  sub     rsp, 28h
0x140046941  movzx   ebx, word ptr [rcx+2]
0x140046945  mov     rbp, rcx
0x140046948  mov     rcx, rdx; Sid
0x14004694b  mov     [rsp+58h+Ace], 0
0x140046954  mov     r14, r8
0x140046957  mov     r15, rdx
0x14004695a  call    cs:__imp_RtlLengthSid
0x140046961  nop     dword ptr [rax+rax+00h]
0x140046966  add     ebx, 8
0x140046969  mov     ecx, 100h
0x14004696e  add     ebx, eax
0x140046970  mov     r8d, 61444856h
0x140046976  mov     edx, ebx
0x140046978  call    cs:__imp_ExAllocatePool2
0x14004697f  nop     dword ptr [rax+rax+00h]
0x140046984  mov     rdi, rax
0x140046987  test    rax, rax
0x14004698a  jnz     short loc_140046996
0x14004698c  mov     ebx, 0C000009Ah
0x140046991  jmp     loc_140046A40
0x140046996  mov     r8d, 2; AclRevision
0x14004699c  mov     edx, ebx; AclLength
0x14004699e  mov     rcx, rdi; Acl
0x1400469a1  call    cs:__imp_RtlCreateAcl
0x1400469a8  nop     dword ptr [rax+rax+00h]
0x1400469ad  mov     ebx, eax
0x1400469af  test    eax, eax
0x1400469b1  js      short loc_140046A2C
0x1400469b3  xor     esi, esi
0x1400469b5  movzx   eax, word ptr [rbp+4]
0x1400469b9  cmp     esi, eax
0x1400469bb  jnb     short loc_140046A04
0x1400469bd  lea     r8, [rsp+58h+Ace]; Ace
0x1400469c2  mov     edx, esi; AceIndex
0x1400469c4  mov     rcx, rbp; Acl
0x1400469c7  call    cs:__imp_RtlGetAce
0x1400469ce  nop     dword ptr [rax+rax+00h]
0x1400469d3  mov     ebx, eax
0x1400469d5  test    eax, eax
0x1400469d7  js      short loc_140046A2C
0x1400469d9  mov     r8, [rsp+58h+Ace]
0x1400469de  mov     edx, 2; AceRevision
0x1400469e3  mov     rcx, rdi; Acl
0x1400469e6  lea     r9, [r8+8]; Sid
0x1400469ea  mov     r8d, [r8+4]; AccessMask
0x1400469ee  call    cs:__imp_RtlAddAccessAllowedAce
0x1400469f5  nop     dword ptr [rax+rax+00h]
0x1400469fa  mov     ebx, eax
0x1400469fc  test    eax, eax
0x1400469fe  js      short loc_140046A2C
0x140046a00  inc     esi
0x140046a02  jmp     short loc_1400469B5
0x140046a04  mov     r9, r15; Sid
0x140046a07  mov     edx, 2; AceRevision
0x140046a0c  mov     r8d, 10000000h; AccessMask
0x140046a12  mov     rcx, rdi; Acl
0x140046a15  call    cs:__imp_RtlAddAccessAllowedAce
0x140046a1c  nop     dword ptr [rax+rax+00h]
0x140046a21  mov     ebx, eax
0x140046a23  test    eax, eax
0x140046a25  js      short loc_140046A2C
0x140046a27  mov     [r14], rdi
0x140046a2a  jmp     short loc_140046A40
0x140046a2c  mov     edx, 61444856h; Tag
0x140046a31  mov     rcx, rdi; P
0x140046a34  call    cs:__imp_ExFreePoolWithTag
0x140046a3b  nop     dword ptr [rax+rax+00h]
0x140046a40  mov     eax, ebx
0x140046a42  add     rsp, 28h
0x140046a46  pop     r15
0x140046a48  pop     r14
0x140046a4a  pop     rdi
0x140046a4b  pop     rsi
0x140046a4c  pop     rbp
0x140046a4d  pop     rbx
0x140046a4e  retn
```
