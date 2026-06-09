# AddCapabilityToDescriptor(void *,ulong,void *)

- ea: `0x14014f2a0`
- end: `0x14014f421`
- name: `?AddCapabilityToDescriptor@@YAHPEAXK0@Z`
- size: `385`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR SecurityDescriptor, ACCESS_MASK AccessMask, PSID Sid)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14014e960`
- `0x1401cc8d0`

## callees

- `0x14004a0d0`
- `0x14004d770`
- `0x14014f2a0`

## import_xrefs

- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x14014f2e4`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x14014f2e4`
- `ntoskrnl!RtlLengthSid` at `0x14014f310`
- `ntoskrnl!RtlLengthSid` at `0x14014f310`
- `ntoskrnl!RtlCreateAcl` at `0x14014f354`
- `ntoskrnl!RtlCreateAcl` at `0x14014f354`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x14014f375`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x14014f375`
- `ntoskrnl!RtlGetAce` at `0x14014f38f`
- `ntoskrnl!RtlGetAce` at `0x14014f38f`
- `ntoskrnl!RtlGetAcesBufferSize` at `0x14014f3a7`
- `ntoskrnl!RtlGetAcesBufferSize` at `0x14014f3a7`
- `ntoskrnl!RtlAddAce` at `0x14014f3d0`
- `ntoskrnl!RtlAddAce` at `0x14014f3d0`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14014f404`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14014f404`

## pseudocode

```c
__int64 __fastcall AddCapabilityToDescriptor(PSECURITY_DESCRIPTOR SecurityDescriptor, ACCESS_MASK AccessMask, PSID Sid)
{
  ULONG v6; // eax
  ULONG v7; // esi
  struct _ACL *v8; // rax
  struct _ACL *v9; // rbx
  unsigned __int8 DaclDefaulted[4]; // [rsp+30h] [rbp-28h] BYREF
  ULONG AceListLength; // [rsp+34h] [rbp-24h] BYREF
  PACL Dacl; // [rsp+38h] [rbp-20h] BYREF
  PVOID Ace; // [rsp+40h] [rbp-18h] BYREF
  unsigned __int8 DaclPresent; // [rsp+A8h] [rbp+50h] BYREF

  AceListLength = 0;
  Dacl = 0;
  DaclPresent = 0;
  DaclDefaulted[0] = 0;
  Ace = 0;
  if ( RtlGetDaclSecurityDescriptor(SecurityDescriptor, &DaclPresent, &Dacl, DaclDefaulted) < 0 )
    return 0;
  if ( !DaclPresent )
    return 0;
  if ( !Dacl )
    return 0;
  v6 = RtlLengthSid(Sid);
  v7 = v6 + Dacl->AclSize + 8;
  v8 = (struct _ACL *)Win32AllocPoolZInitImpl(0x100u, v7, 0x65737355u);
  v9 = v8;
  if ( !v8 )
    return 0;
  if ( RtlCreateAcl(v8, v7, Dacl->AclRevision) < 0
    || RtlAddAccessAllowedAceEx(v9, v9->AclRevision, 0, AccessMask, Sid) < 0
    || RtlGetAce(Dacl, 0, &Ace) < 0
    || (int)RtlGetAcesBufferSize(Dacl, &AceListLength) < 0
    || RtlAddAce(v9, 2u, 1u, Ace, AceListLength) < 0
    || RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, v9, 0) < 0 )
  {
    GreDeleteFastMutex(v9);
    return 0;
  }
  GreDeleteFastMutex(Dacl);
  return 1;
}

```

## disassembly

```asm
0x14014f2a0  push    rbp
0x14014f2a2  push    rbx
0x14014f2a3  push    rsi
0x14014f2a4  push    rdi
0x14014f2a5  push    r14
0x14014f2a7  push    r15
0x14014f2a9  mov     rbp, rsp
0x14014f2ac  sub     rsp, 58h
0x14014f2b0  mov     rdi, r8
0x14014f2b3  mov     [rbp+AceListLength], 0
0x14014f2ba  mov     r15d, edx
0x14014f2bd  mov     [rbp+Dacl], 0
0x14014f2c5  lea     r8, [rbp+Dacl]; Dacl
0x14014f2c9  mov     [rbp+DaclPresent], 0
0x14014f2cd  lea     rdx, [rbp+DaclPresent]; DaclPresent
0x14014f2d1  mov     [rbp+DaclDefaulted], 0
0x14014f2d5  lea     r9, [rbp+DaclDefaulted]; DaclDefaulted
0x14014f2d9  mov     [rbp+Ace], 0
0x14014f2e1  mov     r14, rcx
0x14014f2e4  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x14014f2eb  nop     dword ptr [rax+rax+00h]
0x14014f2f0  test    eax, eax
0x14014f2f2  js      loc_14014F3E8
0x14014f2f8  cmp     [rbp+DaclPresent], 0
0x14014f2fc  jz      loc_14014F3E8
0x14014f302  cmp     [rbp+Dacl], 0
0x14014f307  jz      loc_14014F3E8
0x14014f30d  mov     rcx, rdi; Sid
0x14014f310  call    cs:__imp_RtlLengthSid
0x14014f317  nop     dword ptr [rax+rax+00h]
0x14014f31c  mov     rcx, [rbp+Dacl]
0x14014f320  mov     r8d, 65737355h; unsigned int
0x14014f326  movzx   esi, word ptr [rcx+2]
0x14014f32a  mov     ecx, 100h; unsigned __int64
0x14014f32f  add     esi, 8
0x14014f332  add     esi, eax
0x14014f334  mov     edx, esi; unsigned __int64
0x14014f336  call    ?Win32AllocPoolZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x14014f33b  mov     rbx, rax
0x14014f33e  test    rax, rax
0x14014f341  jz      loc_14014F3E8
0x14014f347  mov     rcx, [rbp+Dacl]
0x14014f34b  mov     edx, esi; AclLength
0x14014f34d  movzx   r8d, byte ptr [rcx]; AclRevision
0x14014f351  mov     rcx, rax; Acl
0x14014f354  call    cs:__imp_RtlCreateAcl
0x14014f35b  nop     dword ptr [rax+rax+00h]
0x14014f360  test    eax, eax
0x14014f362  js      short loc_14014F3E0
0x14014f364  movzx   edx, byte ptr [rbx]; AceRevision
0x14014f367  mov     r9d, r15d; AccessMask
0x14014f36a  xor     r8d, r8d; AceFlags
0x14014f36d  mov     [rsp+58h+Sid], rdi; Sid
0x14014f372  mov     rcx, rbx; Acl
0x14014f375  call    cs:__imp_RtlAddAccessAllowedAceEx
0x14014f37c  nop     dword ptr [rax+rax+00h]
0x14014f381  test    eax, eax
0x14014f383  js      short loc_14014F3E0
0x14014f385  mov     rcx, [rbp+Dacl]; Acl
0x14014f389  lea     r8, [rbp+Ace]; Ace
0x14014f38d  xor     edx, edx; AceIndex
0x14014f38f  call    cs:__imp_RtlGetAce
0x14014f396  nop     dword ptr [rax+rax+00h]
0x14014f39b  test    eax, eax
0x14014f39d  js      short loc_14014F3E0
0x14014f39f  mov     rcx, [rbp+Dacl]
0x14014f3a3  lea     rdx, [rbp+AceListLength]
0x14014f3a7  call    cs:__imp_RtlGetAcesBufferSize
0x14014f3ae  nop     dword ptr [rax+rax+00h]
0x14014f3b3  test    eax, eax
0x14014f3b5  js      short loc_14014F3E0
0x14014f3b7  mov     eax, [rbp+AceListLength]
0x14014f3ba  mov     edi, 1
0x14014f3bf  mov     r9, [rbp+Ace]; AceList
0x14014f3c3  mov     r8d, edi; StartingAceIndex
0x14014f3c6  mov     rcx, rbx; Acl
0x14014f3c9  mov     dword ptr [rsp+58h+Sid], eax; AceListLength
0x14014f3cd  lea     edx, [rdi+1]; AceRevision
0x14014f3d0  call    cs:__imp_RtlAddAce
0x14014f3d7  nop     dword ptr [rax+rax+00h]
0x14014f3dc  test    eax, eax
0x14014f3de  jns     short loc_14014F3F8
0x14014f3e0  mov     rcx, rbx; Buffer
0x14014f3e3  call    GreDeleteFastMutex
0x14014f3e8  xor     eax, eax
0x14014f3ea  add     rsp, 58h
0x14014f3ee  pop     r15
0x14014f3f0  pop     r14
0x14014f3f2  pop     rdi
0x14014f3f3  pop     rsi
0x14014f3f4  pop     rbx
0x14014f3f5  pop     rbp
0x14014f3f6  retn
0x14014f3f8  xor     r9d, r9d; DaclDefaulted
0x14014f3fb  mov     r8, rbx; Dacl
0x14014f3fe  mov     dl, dil; DaclPresent
0x14014f401  mov     rcx, r14; SecurityDescriptor
0x14014f404  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x14014f40b  nop     dword ptr [rax+rax+00h]
0x14014f410  test    eax, eax
0x14014f412  js      short loc_14014F3E0
0x14014f414  mov     rcx, [rbp+Dacl]; Buffer
0x14014f418  call    GreDeleteFastMutex
0x14014f41d  mov     eax, edi
0x14014f41f  jmp     short loc_14014F3EA
```
