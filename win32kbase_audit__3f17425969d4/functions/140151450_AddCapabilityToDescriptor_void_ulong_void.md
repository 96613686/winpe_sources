# AddCapabilityToDescriptor(void *,ulong,void *)

- ea: `0x140151450`
- end: `0x1401515d1`
- name: `?AddCapabilityToDescriptor@@YAHPEAXK0@Z`
- size: `385`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR SecurityDescriptor, ACCESS_MASK AccessMask, PSID Sid)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140150b10`
- `0x1401cd650`

## callees

- `0x14007b930`
- `0x14007efd0`
- `0x140151450`

## import_xrefs

- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x140151494`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x140151494`
- `ntoskrnl!RtlLengthSid` at `0x1401514c0`
- `ntoskrnl!RtlLengthSid` at `0x1401514c0`
- `ntoskrnl!RtlCreateAcl` at `0x140151504`
- `ntoskrnl!RtlCreateAcl` at `0x140151504`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x140151525`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x140151525`
- `ntoskrnl!RtlGetAce` at `0x14015153f`
- `ntoskrnl!RtlGetAce` at `0x14015153f`
- `ntoskrnl!RtlGetAcesBufferSize` at `0x140151557`
- `ntoskrnl!RtlGetAcesBufferSize` at `0x140151557`
- `ntoskrnl!RtlAddAce` at `0x140151580`
- `ntoskrnl!RtlAddAce` at `0x140151580`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1401515b4`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1401515b4`

## pseudocode

```c
__int64 __fastcall AddCapabilityToDescriptor(PSECURITY_DESCRIPTOR SecurityDescriptor, ACCESS_MASK AccessMask, PSID Sid)
{
  ULONG v6; // eax
  ULONG v7; // esi
  struct _ACL *v8; // rax
  struct _ACL *v9; // rbx
  __int64 v10; // rdx
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
  v8 = (struct _ACL *)Win32AllocPoolZInitImpl(256, v7, 0x65737355u);
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
    GreDeleteFastMutex(v9, v10);
    return 0;
  }
  GreDeleteFastMutex(Dacl, v10);
  return 1;
}

```

## disassembly

```asm
0x140151450  push    rbp
0x140151452  push    rbx
0x140151453  push    rsi
0x140151454  push    rdi
0x140151455  push    r14
0x140151457  push    r15
0x140151459  mov     rbp, rsp
0x14015145c  sub     rsp, 58h
0x140151460  mov     rdi, r8
0x140151463  mov     [rbp+AceListLength], 0
0x14015146a  mov     r15d, edx
0x14015146d  mov     [rbp+Dacl], 0
0x140151475  lea     r8, [rbp+Dacl]; Dacl
0x140151479  mov     [rbp+DaclPresent], 0
0x14015147d  lea     rdx, [rbp+DaclPresent]; DaclPresent
0x140151481  mov     [rbp+DaclDefaulted], 0
0x140151485  lea     r9, [rbp+DaclDefaulted]; DaclDefaulted
0x140151489  mov     [rbp+Ace], 0
0x140151491  mov     r14, rcx
0x140151494  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x14015149b  nop     dword ptr [rax+rax+00h]
0x1401514a0  test    eax, eax
0x1401514a2  js      loc_140151598
0x1401514a8  cmp     [rbp+DaclPresent], 0
0x1401514ac  jz      loc_140151598
0x1401514b2  cmp     [rbp+Dacl], 0
0x1401514b7  jz      loc_140151598
0x1401514bd  mov     rcx, rdi; Sid
0x1401514c0  call    cs:__imp_RtlLengthSid
0x1401514c7  nop     dword ptr [rax+rax+00h]
0x1401514cc  mov     rcx, [rbp+Dacl]
0x1401514d0  mov     r8d, 65737355h; unsigned int
0x1401514d6  movzx   esi, word ptr [rcx+2]
0x1401514da  mov     ecx, 100h; unsigned __int64
0x1401514df  add     esi, 8
0x1401514e2  add     esi, eax
0x1401514e4  mov     edx, esi; unsigned __int64
0x1401514e6  call    ?Win32AllocPoolZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x1401514eb  mov     rbx, rax
0x1401514ee  test    rax, rax
0x1401514f1  jz      loc_140151598
0x1401514f7  mov     rcx, [rbp+Dacl]
0x1401514fb  mov     edx, esi; AclLength
0x1401514fd  movzx   r8d, byte ptr [rcx]; AclRevision
0x140151501  mov     rcx, rax; Acl
0x140151504  call    cs:__imp_RtlCreateAcl
0x14015150b  nop     dword ptr [rax+rax+00h]
0x140151510  test    eax, eax
0x140151512  js      short loc_140151590
0x140151514  movzx   edx, byte ptr [rbx]; AceRevision
0x140151517  mov     r9d, r15d; AccessMask
0x14015151a  xor     r8d, r8d; AceFlags
0x14015151d  mov     [rsp+58h+Sid], rdi; Sid
0x140151522  mov     rcx, rbx; Acl
0x140151525  call    cs:__imp_RtlAddAccessAllowedAceEx
0x14015152c  nop     dword ptr [rax+rax+00h]
0x140151531  test    eax, eax
0x140151533  js      short loc_140151590
0x140151535  mov     rcx, [rbp+Dacl]; Acl
0x140151539  lea     r8, [rbp+Ace]; Ace
0x14015153d  xor     edx, edx; AceIndex
0x14015153f  call    cs:__imp_RtlGetAce
0x140151546  nop     dword ptr [rax+rax+00h]
0x14015154b  test    eax, eax
0x14015154d  js      short loc_140151590
0x14015154f  mov     rcx, [rbp+Dacl]
0x140151553  lea     rdx, [rbp+AceListLength]
0x140151557  call    cs:__imp_RtlGetAcesBufferSize
0x14015155e  nop     dword ptr [rax+rax+00h]
0x140151563  test    eax, eax
0x140151565  js      short loc_140151590
0x140151567  mov     eax, [rbp+AceListLength]
0x14015156a  mov     edi, 1
0x14015156f  mov     r9, [rbp+Ace]; AceList
0x140151573  mov     r8d, edi; StartingAceIndex
0x140151576  mov     rcx, rbx; Acl
0x140151579  mov     dword ptr [rsp+58h+Sid], eax; AceListLength
0x14015157d  lea     edx, [rdi+1]; AceRevision
0x140151580  call    cs:__imp_RtlAddAce
0x140151587  nop     dword ptr [rax+rax+00h]
0x14015158c  test    eax, eax
0x14015158e  jns     short loc_1401515A8
0x140151590  mov     rcx, rbx; Buffer
0x140151593  call    GreDeleteFastMutex
0x140151598  xor     eax, eax
0x14015159a  add     rsp, 58h
0x14015159e  pop     r15
0x1401515a0  pop     r14
0x1401515a2  pop     rdi
0x1401515a3  pop     rsi
0x1401515a4  pop     rbx
0x1401515a5  pop     rbp
0x1401515a6  retn
0x1401515a8  xor     r9d, r9d; DaclDefaulted
0x1401515ab  mov     r8, rbx; Dacl
0x1401515ae  mov     dl, dil; DaclPresent
0x1401515b1  mov     rcx, r14; SecurityDescriptor
0x1401515b4  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x1401515bb  nop     dword ptr [rax+rax+00h]
0x1401515c0  test    eax, eax
0x1401515c2  js      short loc_140151590
0x1401515c4  mov     rcx, [rbp+Dacl]; Buffer
0x1401515c8  call    GreDeleteFastMutex
0x1401515cd  mov     eax, edi
0x1401515cf  jmp     short loc_14015159A
```
