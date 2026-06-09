# IppStartInterfaceManager

- ea: `0x1401846e0`
- end: `0x140184946`
- name: `IppStartInterfaceManager`
- size: `614`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x140054138`
- `0x1401822e4`
- `0x1401846e0`

## import_xrefs

- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140184884`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140184884`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x140184862`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x140184862`
- `ntoskrnl!RtlCreateAcl` at `0x140184835`
- `ntoskrnl!RtlCreateAcl` at `0x140184835`
- `ntoskrnl!RtlLengthSid` at `0x1401847d0`
- `ntoskrnl!RtlLengthSid` at `0x1401847d0`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140184745`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140184745`
- `ntoskrnl!KeInitializeSpinLock` at `0x1401848d2`
- `ntoskrnl!KeInitializeSpinLock` at `0x1401848d2`
- `ntoskrnl!RtlLengthRequiredSid` at `0x140184760`
- `ntoskrnl!RtlLengthRequiredSid` at `0x140184760`
- `ntoskrnl!ExFreePoolWithTag` at `0x140184910`
- `ntoskrnl!ExFreePoolWithTag` at `0x140184926`
- `ntoskrnl!ExFreePoolWithTag` at `0x140184910`
- `ntoskrnl!ExFreePoolWithTag` at `0x140184926`
- `ntoskrnl!ExAllocatePool2` at `0x14018477f`
- `ntoskrnl!ExAllocatePool2` at `0x1401847e9`
- `ntoskrnl!ExAllocatePool2` at `0x14018477f`
- `ntoskrnl!ExAllocatePool2` at `0x1401847e9`
- `NETIO!NsiSetObjectSecurity` at `0x1401848af`
- `NETIO!NsiSetObjectSecurity` at `0x1401848af`
- `NETIO!NsiResetPersistentSetting` at `0x140184730`
- `NETIO!NsiResetPersistentSetting` at `0x140184730`

## string_xrefs

- `0x140184805`: `interface manager ACL (IPNG)`
- `0x14018479b`: `interface manager SID (IPNG)`

## pseudocode

```c
__int64 __fastcall IppStartInterfaceManager(__int64 a1)
{
  bool v1; // zf
  NTSTATUS Acl; // ebx
  ULONG v4; // eax
  char *Pool2; // rax
  __int64 v6; // r8
  void *Sid; // rsi
  __int64 v8; // r12
  struct _ACL *v9; // rax
  __int64 v10; // r8
  struct _ACL *v11; // r14
  _OWORD SecurityDescriptor[2]; // [rsp+30h] [rbp-39h] BYREF
  __int64 v14; // [rsp+50h] [rbp-19h]
  __int128 v15; // [rsp+58h] [rbp-11h] BYREF
  __int128 v16; // [rsp+68h] [rbp-1h]
  __int128 v17; // [rsp+78h] [rbp+Fh]

  v1 = *(_DWORD *)(a1 + 24) == 41;
  v14 = 0;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  v15 = 0;
  v16 = 0;
  v17 = 0;
  if ( !v1 )
  {
    Sid = 0;
    v11 = 0;
    goto LABEL_16;
  }
  NsiResetPersistentSetting(*(_QWORD *)(a1 + 32), 25, 0, 0);
  Acl = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
  if ( Acl < 0 )
    return (unsigned int)Acl;
  v4 = RtlLengthRequiredSid(1u);
  Pool2 = (char *)ExAllocatePool2(64, v4, 1735290953);
  Sid = Pool2;
  if ( Pool2 )
  {
    *(_DWORD *)Pool2 = 257;
    *(_QWORD *)(Pool2 + 4) = 0x1000000;
    v8 = RtlLengthSid(Pool2) + 16;
    v9 = (struct _ACL *)ExAllocatePool2(64, v8, 1735290953);
    v11 = v9;
    if ( !v9 )
    {
      if ( SBYTE3(WPP_MAIN_CB.Reserved) < 0 )
        McTemplateK0z_EtwWriteTransfer(
          &MICROSOFT_TCPIP_PROVIDER_Context,
          &TCPIP_MEMORY_FAILURES,
          v10,
          L"interface manager ACL (IPNG)");
      Acl = -1073741670;
      goto LABEL_19;
    }
    Acl = RtlCreateAcl(v9, v8, 2u);
    if ( Acl < 0
      || (Acl = RtlAddAccessAllowedAceEx(v11, 2u, 3u, 0x2001Fu, Sid), Acl < 0)
      || (RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, v11, 0),
          *((_QWORD *)&v15 + 1) = *(_QWORD *)(a1 + 32),
          *(_QWORD *)&v17 = SecurityDescriptor,
          LODWORD(v16) = 25,
          DWORD2(v17) = v8,
          (Acl = NsiSetObjectSecurity(&v15)) != 0) )
    {
LABEL_17:
      ExFreePoolWithTag(v11, 0);
LABEL_18:
      if ( !Sid )
        return (unsigned int)Acl;
LABEL_19:
      ExFreePoolWithTag(Sid, 0);
      return (unsigned int)Acl;
    }
LABEL_16:
    KeInitializeSpinLock((PKSPIN_LOCK)(a1 + 20176));
    *(_DWORD *)(a1 + 20184) = 0;
    IppInitializeLockedList(a1 + 19896);
    _InterlockedIncrement(&IpngpReferenceCount);
    _InterlockedAdd((volatile signed __int32 *)(a1 + 19860), 0x2000u);
    Acl = 0;
    if ( !v11 )
      goto LABEL_18;
    goto LABEL_17;
  }
  if ( SBYTE3(WPP_MAIN_CB.Reserved) < 0 )
    McTemplateK0z_EtwWriteTransfer(
      &MICROSOFT_TCPIP_PROVIDER_Context,
      &TCPIP_MEMORY_FAILURES,
      v6,
      L"interface manager SID (IPNG)");
  return (unsigned int)-1073741670;
}

```

## disassembly

```asm
0x1401846e0  push    rbp
0x1401846e2  push    rbx
0x1401846e3  push    rsi
0x1401846e4  push    r12
0x1401846e6  push    r14
0x1401846e8  push    r15
0x1401846ea  lea     rbp, [rsp-2Fh]
0x1401846ef  sub     rsp, 98h
0x1401846f6  xorps   xmm1, xmm1
0x1401846f9  xor     eax, eax
0x1401846fb  cmp     dword ptr [rcx+18h], 29h ; ')'
0x1401846ff  xorps   xmm0, xmm0
0x140184702  mov     r15, rcx
0x140184705  mov     [rbp+57h+var_70], rax
0x140184709  movups  [rbp+57h+SecurityDescriptor], xmm0
0x14018470d  movups  [rbp+57h+var_80], xmm0
0x140184711  movups  [rbp+57h+var_68], xmm1
0x140184715  movups  [rbp+57h+var_58], xmm1
0x140184719  movups  [rbp+57h+var_48], xmm1
0x14018471d  jnz     loc_1401848C3
0x140184723  mov     rcx, [rcx+20h]
0x140184727  lea     edx, [rax+19h]
0x14018472a  xor     r9d, r9d
0x14018472d  xor     r8d, r8d
0x140184730  call    cs:__imp_NsiResetPersistentSetting
0x140184737  nop     dword ptr [rax+rax+00h]
0x14018473c  mov     edx, 1; Revision
0x140184741  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x140184745  call    cs:__imp_RtlCreateSecurityDescriptor
0x14018474c  nop     dword ptr [rax+rax+00h]
0x140184751  mov     ebx, eax
0x140184753  test    eax, eax
0x140184755  js      loc_140184932
0x14018475b  mov     ecx, 1; SubAuthorityCount
0x140184760  call    cs:__imp_RtlLengthRequiredSid
0x140184767  nop     dword ptr [rax+rax+00h]
0x14018476c  mov     ebx, 676E7049h
0x140184771  mov     r14d, 40h ; '@'
0x140184777  mov     edx, eax
0x140184779  mov     r8d, ebx
0x14018477c  mov     ecx, r14d
0x14018477f  call    cs:__imp_ExAllocatePool2
0x140184786  nop     dword ptr [rax+rax+00h]
0x14018478b  mov     rsi, rax
0x14018478e  test    rax, rax
0x140184791  jnz     short loc_1401847BF
0x140184793  cmp     byte ptr cs:WPP_MAIN_CB.Reserved+3, al
0x140184799  jge     short loc_1401847B5
0x14018479b  lea     r9, aInterfaceManag; "interface manager SID (IPNG)"
0x1401847a2  lea     rdx, TCPIP_MEMORY_FAILURES
0x1401847a9  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x1401847b0  call    McTemplateK0z_EtwWriteTransfer
0x1401847b5  mov     ebx, 0C000009Ah
0x1401847ba  jmp     loc_140184932
0x1401847bf  mov     dword ptr [rax], 101h
0x1401847c5  mov     rcx, rsi; Sid
0x1401847c8  mov     qword ptr [rax+4], 1000000h
0x1401847d0  call    cs:__imp_RtlLengthSid
0x1401847d7  nop     dword ptr [rax+rax+00h]
0x1401847dc  mov     r8d, ebx
0x1401847df  mov     rcx, r14
0x1401847e2  lea     r12d, [rax+10h]
0x1401847e6  mov     edx, r12d
0x1401847e9  call    cs:__imp_ExAllocatePool2
0x1401847f0  nop     dword ptr [rax+rax+00h]
0x1401847f5  mov     r14, rax
0x1401847f8  test    rax, rax
0x1401847fb  jnz     short loc_140184829
0x1401847fd  cmp     byte ptr cs:WPP_MAIN_CB.Reserved+3, al
0x140184803  jge     short loc_14018481F
0x140184805  lea     r9, aInterfaceManag_0; "interface manager ACL (IPNG)"
0x14018480c  lea     rdx, TCPIP_MEMORY_FAILURES
0x140184813  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x14018481a  call    McTemplateK0z_EtwWriteTransfer
0x14018481f  mov     ebx, 0C000009Ah
0x140184824  jmp     loc_140184921
0x140184829  mov     r8d, 2; AclRevision
0x14018482f  mov     edx, r12d; AclLength
0x140184832  mov     rcx, r14; Acl
0x140184835  call    cs:__imp_RtlCreateAcl
0x14018483c  nop     dword ptr [rax+rax+00h]
0x140184841  mov     ebx, eax
0x140184843  test    eax, eax
0x140184845  js      loc_14018490B
0x14018484b  mov     edx, 2; AceRevision
0x140184850  mov     [rsp+0C0h+Sid], rsi; Sid
0x140184855  mov     r9d, 2001Fh; AccessMask
0x14018485b  mov     rcx, r14; Acl
0x14018485e  lea     r8d, [rdx+1]; AceFlags
0x140184862  call    cs:__imp_RtlAddAccessAllowedAceEx
0x140184869  nop     dword ptr [rax+rax+00h]
0x14018486e  mov     ebx, eax
0x140184870  test    eax, eax
0x140184872  js      loc_14018490B
0x140184878  xor     r9d, r9d; DaclDefaulted
0x14018487b  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x14018487f  mov     r8, r14; Dacl
0x140184882  mov     dl, 1; DaclPresent
0x140184884  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x14018488b  nop     dword ptr [rax+rax+00h]
0x140184890  mov     rax, [r15+20h]
0x140184894  lea     rcx, [rbp+57h+var_68]
0x140184898  mov     qword ptr [rbp+57h+var_68+8], rax
0x14018489c  lea     rax, [rbp+57h+SecurityDescriptor]
0x1401848a0  mov     qword ptr [rbp+57h+var_48], rax
0x1401848a4  mov     dword ptr [rbp+57h+var_58], 19h
0x1401848ab  mov     dword ptr [rbp+57h+var_48+8], r12d
0x1401848af  call    cs:__imp_NsiSetObjectSecurity
0x1401848b6  nop     dword ptr [rax+rax+00h]
0x1401848bb  mov     ebx, eax
0x1401848bd  test    eax, eax
0x1401848bf  jnz     short loc_14018490B
0x1401848c1  jmp     short loc_1401848C8
0x1401848c3  xor     esi, esi
0x1401848c5  xor     r14d, r14d
0x1401848c8  lea     rbx, [r15+4ED0h]
0x1401848cf  mov     rcx, rbx; SpinLock
0x1401848d2  call    cs:__imp_KeInitializeSpinLock
0x1401848d9  nop     dword ptr [rax+rax+00h]
0x1401848de  lea     rcx, [r15+4DB8h]
0x1401848e5  mov     dword ptr [rbx+8], 0
0x1401848ec  call    IppInitializeLockedList
0x1401848f1  lock inc cs:IpngpReferenceCount
0x1401848f8  lock add dword ptr [r15+4D94h], 2000h
0x140184904  xor     ebx, ebx
0x140184906  test    r14, r14
0x140184909  jz      short loc_14018491C
0x14018490b  xor     edx, edx; Tag
0x14018490d  mov     rcx, r14; P
0x140184910  call    cs:__imp_ExFreePoolWithTag
0x140184917  nop     dword ptr [rax+rax+00h]
0x14018491c  test    rsi, rsi
0x14018491f  jz      short loc_140184932
0x140184921  xor     edx, edx; Tag
0x140184923  mov     rcx, rsi; P
0x140184926  call    cs:__imp_ExFreePoolWithTag
0x14018492d  nop     dword ptr [rax+rax+00h]
0x140184932  mov     eax, ebx
0x140184934  add     rsp, 98h
0x14018493b  pop     r15
0x14018493d  pop     r14
0x14018493f  pop     r12
0x140184941  pop     rsi
0x140184942  pop     rbx
0x140184943  pop     rbp
0x140184944  retn
```
