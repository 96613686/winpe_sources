# AddCapabilityToDescriptor(void *,ulong,void *)

- ea: `0x14014e7f0`
- end: `0x14014e971`
- name: `?AddCapabilityToDescriptor@@YAHPEAXK0@Z`
- size: `385`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR SecurityDescriptor, ACCESS_MASK AccessMask, PSID Sid)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14014deb0`
- `0x1401cce30`

## callees

- `0x1400411c0`
- `0x1400449b0`
- `0x14014e7f0`

## import_xrefs

- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x14014e834`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x14014e834`
- `ntoskrnl!RtlLengthSid` at `0x14014e860`
- `ntoskrnl!RtlLengthSid` at `0x14014e860`
- `ntoskrnl!RtlCreateAcl` at `0x14014e8a4`
- `ntoskrnl!RtlCreateAcl` at `0x14014e8a4`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x14014e8c5`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x14014e8c5`
- `ntoskrnl!RtlGetAce` at `0x14014e8df`
- `ntoskrnl!RtlGetAce` at `0x14014e8df`
- `ntoskrnl!RtlGetAcesBufferSize` at `0x14014e8f7`
- `ntoskrnl!RtlGetAcesBufferSize` at `0x14014e8f7`
- `ntoskrnl!RtlAddAce` at `0x14014e920`
- `ntoskrnl!RtlAddAce` at `0x14014e920`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14014e954`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14014e954`

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
0x14014e7f0  push    rbp
0x14014e7f2  push    rbx
0x14014e7f3  push    rsi
0x14014e7f4  push    rdi
0x14014e7f5  push    r14
0x14014e7f7  push    r15
0x14014e7f9  mov     rbp, rsp
0x14014e7fc  sub     rsp, 58h
0x14014e800  mov     rdi, r8
0x14014e803  mov     [rbp+AceListLength], 0
0x14014e80a  mov     r15d, edx
0x14014e80d  mov     [rbp+Dacl], 0
0x14014e815  lea     r8, [rbp+Dacl]; Dacl
0x14014e819  mov     [rbp+DaclPresent], 0
0x14014e81d  lea     rdx, [rbp+DaclPresent]; DaclPresent
0x14014e821  mov     [rbp+DaclDefaulted], 0
0x14014e825  lea     r9, [rbp+DaclDefaulted]; DaclDefaulted
0x14014e829  mov     [rbp+Ace], 0
0x14014e831  mov     r14, rcx
0x14014e834  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x14014e83b  nop     dword ptr [rax+rax+00h]
0x14014e840  test    eax, eax
0x14014e842  js      loc_14014E938
0x14014e848  cmp     [rbp+DaclPresent], 0
0x14014e84c  jz      loc_14014E938
0x14014e852  cmp     [rbp+Dacl], 0
0x14014e857  jz      loc_14014E938
0x14014e85d  mov     rcx, rdi; Sid
0x14014e860  call    cs:__imp_RtlLengthSid
0x14014e867  nop     dword ptr [rax+rax+00h]
0x14014e86c  mov     rcx, [rbp+Dacl]
0x14014e870  mov     r8d, 65737355h; unsigned int
0x14014e876  movzx   esi, word ptr [rcx+2]
0x14014e87a  mov     ecx, 100h; unsigned __int64
0x14014e87f  add     esi, 8
0x14014e882  add     esi, eax
0x14014e884  mov     edx, esi; unsigned __int64
0x14014e886  call    ?Win32AllocPoolZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x14014e88b  mov     rbx, rax
0x14014e88e  test    rax, rax
0x14014e891  jz      loc_14014E938
0x14014e897  mov     rcx, [rbp+Dacl]
0x14014e89b  mov     edx, esi; AclLength
0x14014e89d  movzx   r8d, byte ptr [rcx]; AclRevision
0x14014e8a1  mov     rcx, rax; Acl
0x14014e8a4  call    cs:__imp_RtlCreateAcl
0x14014e8ab  nop     dword ptr [rax+rax+00h]
0x14014e8b0  test    eax, eax
0x14014e8b2  js      short loc_14014E930
0x14014e8b4  movzx   edx, byte ptr [rbx]; AceRevision
0x14014e8b7  mov     r9d, r15d; AccessMask
0x14014e8ba  xor     r8d, r8d; AceFlags
0x14014e8bd  mov     [rsp+58h+Sid], rdi; Sid
0x14014e8c2  mov     rcx, rbx; Acl
0x14014e8c5  call    cs:__imp_RtlAddAccessAllowedAceEx
0x14014e8cc  nop     dword ptr [rax+rax+00h]
0x14014e8d1  test    eax, eax
0x14014e8d3  js      short loc_14014E930
0x14014e8d5  mov     rcx, [rbp+Dacl]; Acl
0x14014e8d9  lea     r8, [rbp+Ace]; Ace
0x14014e8dd  xor     edx, edx; AceIndex
0x14014e8df  call    cs:__imp_RtlGetAce
0x14014e8e6  nop     dword ptr [rax+rax+00h]
0x14014e8eb  test    eax, eax
0x14014e8ed  js      short loc_14014E930
0x14014e8ef  mov     rcx, [rbp+Dacl]
0x14014e8f3  lea     rdx, [rbp+AceListLength]
0x14014e8f7  call    cs:__imp_RtlGetAcesBufferSize
0x14014e8fe  nop     dword ptr [rax+rax+00h]
0x14014e903  test    eax, eax
0x14014e905  js      short loc_14014E930
0x14014e907  mov     eax, [rbp+AceListLength]
0x14014e90a  mov     edi, 1
0x14014e90f  mov     r9, [rbp+Ace]; AceList
0x14014e913  mov     r8d, edi; StartingAceIndex
0x14014e916  mov     rcx, rbx; Acl
0x14014e919  mov     dword ptr [rsp+58h+Sid], eax; AceListLength
0x14014e91d  lea     edx, [rdi+1]; AceRevision
0x14014e920  call    cs:__imp_RtlAddAce
0x14014e927  nop     dword ptr [rax+rax+00h]
0x14014e92c  test    eax, eax
0x14014e92e  jns     short loc_14014E948
0x14014e930  mov     rcx, rbx; Buffer
0x14014e933  call    GreDeleteFastMutex
0x14014e938  xor     eax, eax
0x14014e93a  add     rsp, 58h
0x14014e93e  pop     r15
0x14014e940  pop     r14
0x14014e942  pop     rdi
0x14014e943  pop     rsi
0x14014e944  pop     rbx
0x14014e945  pop     rbp
0x14014e946  retn
0x14014e948  xor     r9d, r9d; DaclDefaulted
0x14014e94b  mov     r8, rbx; Dacl
0x14014e94e  mov     dl, dil; DaclPresent
0x14014e951  mov     rcx, r14; SecurityDescriptor
0x14014e954  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x14014e95b  nop     dword ptr [rax+rax+00h]
0x14014e960  test    eax, eax
0x14014e962  js      short loc_14014E930
0x14014e964  mov     rcx, [rbp+Dacl]; Buffer
0x14014e968  call    GreDeleteFastMutex
0x14014e96d  mov     eax, edi
0x14014e96f  jmp     short loc_14014E93A
```
