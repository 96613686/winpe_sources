# IppStartInterfaceManager

- ea: `0x1401861c0`
- end: `0x140186426`
- name: `IppStartInterfaceManager`
- size: `614`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x140014a08`
- `0x140183e54`
- `0x1401861c0`

## import_xrefs

- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140186364`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140186364`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x140186342`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x140186342`
- `ntoskrnl!RtlCreateAcl` at `0x140186315`
- `ntoskrnl!RtlCreateAcl` at `0x140186315`
- `ntoskrnl!RtlLengthSid` at `0x1401862b0`
- `ntoskrnl!RtlLengthSid` at `0x1401862b0`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140186225`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140186225`
- `ntoskrnl!KeInitializeSpinLock` at `0x1401863b2`
- `ntoskrnl!KeInitializeSpinLock` at `0x1401863b2`
- `ntoskrnl!RtlLengthRequiredSid` at `0x140186240`
- `ntoskrnl!RtlLengthRequiredSid` at `0x140186240`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401863f0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140186406`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401863f0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140186406`
- `ntoskrnl!ExAllocatePool2` at `0x14018625f`
- `ntoskrnl!ExAllocatePool2` at `0x1401862c9`
- `ntoskrnl!ExAllocatePool2` at `0x14018625f`
- `ntoskrnl!ExAllocatePool2` at `0x1401862c9`
- `NETIO!NsiSetObjectSecurity` at `0x14018638f`
- `NETIO!NsiSetObjectSecurity` at `0x14018638f`
- `NETIO!NsiResetPersistentSetting` at `0x140186210`
- `NETIO!NsiResetPersistentSetting` at `0x140186210`

## string_xrefs

- `0x1401862e5`: `interface manager ACL (IPNG)`
- `0x14018627b`: `interface manager SID (IPNG)`

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
      if ( SBYTE3(WPP_MAIN_CB.Dpc.DeferredRoutine) < 0 )
        McTemplateK0z_EtwWriteTransfer(
          &MICROSOFT_TCPIP_PROVIDER_Context,
          TCPIP_MEMORY_FAILURES,
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
  if ( SBYTE3(WPP_MAIN_CB.Dpc.DeferredRoutine) < 0 )
    McTemplateK0z_EtwWriteTransfer(
      &MICROSOFT_TCPIP_PROVIDER_Context,
      TCPIP_MEMORY_FAILURES,
      v6,
      L"interface manager SID (IPNG)");
  return (unsigned int)-1073741670;
}

```

## disassembly

```asm
0x1401861c0  push    rbp
0x1401861c2  push    rbx
0x1401861c3  push    rsi
0x1401861c4  push    r12
0x1401861c6  push    r14
0x1401861c8  push    r15
0x1401861ca  lea     rbp, [rsp-2Fh]
0x1401861cf  sub     rsp, 98h
0x1401861d6  xorps   xmm1, xmm1
0x1401861d9  xor     eax, eax
0x1401861db  cmp     dword ptr [rcx+18h], 29h ; ')'
0x1401861df  xorps   xmm0, xmm0
0x1401861e2  mov     r15, rcx
0x1401861e5  mov     [rbp+57h+var_70], rax
0x1401861e9  movups  [rbp+57h+SecurityDescriptor], xmm0
0x1401861ed  movups  [rbp+57h+var_80], xmm0
0x1401861f1  movups  [rbp+57h+var_68], xmm1
0x1401861f5  movups  [rbp+57h+var_58], xmm1
0x1401861f9  movups  [rbp+57h+var_48], xmm1
0x1401861fd  jnz     loc_1401863A3
0x140186203  mov     rcx, [rcx+20h]
0x140186207  lea     edx, [rax+19h]
0x14018620a  xor     r9d, r9d
0x14018620d  xor     r8d, r8d
0x140186210  call    cs:__imp_NsiResetPersistentSetting
0x140186217  nop     dword ptr [rax+rax+00h]
0x14018621c  mov     edx, 1; Revision
0x140186221  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x140186225  call    cs:__imp_RtlCreateSecurityDescriptor
0x14018622c  nop     dword ptr [rax+rax+00h]
0x140186231  mov     ebx, eax
0x140186233  test    eax, eax
0x140186235  js      loc_140186412
0x14018623b  mov     ecx, 1; SubAuthorityCount
0x140186240  call    cs:__imp_RtlLengthRequiredSid
0x140186247  nop     dword ptr [rax+rax+00h]
0x14018624c  mov     ebx, 676E7049h
0x140186251  mov     r14d, 40h ; '@'
0x140186257  mov     edx, eax
0x140186259  mov     r8d, ebx
0x14018625c  mov     ecx, r14d
0x14018625f  call    cs:__imp_ExAllocatePool2
0x140186266  nop     dword ptr [rax+rax+00h]
0x14018626b  mov     rsi, rax
0x14018626e  test    rax, rax
0x140186271  jnz     short loc_14018629F
0x140186273  cmp     byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+3, al
0x140186279  jge     short loc_140186295
0x14018627b  lea     r9, aInterfaceManag; "interface manager SID (IPNG)"
0x140186282  lea     rdx, TCPIP_MEMORY_FAILURES
0x140186289  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x140186290  call    McTemplateK0z_EtwWriteTransfer
0x140186295  mov     ebx, 0C000009Ah
0x14018629a  jmp     loc_140186412
0x14018629f  mov     dword ptr [rax], 101h
0x1401862a5  mov     rcx, rsi; Sid
0x1401862a8  mov     qword ptr [rax+4], 1000000h
0x1401862b0  call    cs:__imp_RtlLengthSid
0x1401862b7  nop     dword ptr [rax+rax+00h]
0x1401862bc  mov     r8d, ebx
0x1401862bf  mov     rcx, r14
0x1401862c2  lea     r12d, [rax+10h]
0x1401862c6  mov     edx, r12d
0x1401862c9  call    cs:__imp_ExAllocatePool2
0x1401862d0  nop     dword ptr [rax+rax+00h]
0x1401862d5  mov     r14, rax
0x1401862d8  test    rax, rax
0x1401862db  jnz     short loc_140186309
0x1401862dd  cmp     byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+3, al
0x1401862e3  jge     short loc_1401862FF
0x1401862e5  lea     r9, aInterfaceManag_0; "interface manager ACL (IPNG)"
0x1401862ec  lea     rdx, TCPIP_MEMORY_FAILURES
0x1401862f3  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x1401862fa  call    McTemplateK0z_EtwWriteTransfer
0x1401862ff  mov     ebx, 0C000009Ah
0x140186304  jmp     loc_140186401
0x140186309  mov     r8d, 2; AclRevision
0x14018630f  mov     edx, r12d; AclLength
0x140186312  mov     rcx, r14; Acl
0x140186315  call    cs:__imp_RtlCreateAcl
0x14018631c  nop     dword ptr [rax+rax+00h]
0x140186321  mov     ebx, eax
0x140186323  test    eax, eax
0x140186325  js      loc_1401863EB
0x14018632b  mov     edx, 2; AceRevision
0x140186330  mov     [rsp+0C0h+Sid], rsi; Sid
0x140186335  mov     r9d, 2001Fh; AccessMask
0x14018633b  mov     rcx, r14; Acl
0x14018633e  lea     r8d, [rdx+1]; AceFlags
0x140186342  call    cs:__imp_RtlAddAccessAllowedAceEx
0x140186349  nop     dword ptr [rax+rax+00h]
0x14018634e  mov     ebx, eax
0x140186350  test    eax, eax
0x140186352  js      loc_1401863EB
0x140186358  xor     r9d, r9d; DaclDefaulted
0x14018635b  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x14018635f  mov     r8, r14; Dacl
0x140186362  mov     dl, 1; DaclPresent
0x140186364  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x14018636b  nop     dword ptr [rax+rax+00h]
0x140186370  mov     rax, [r15+20h]
0x140186374  lea     rcx, [rbp+57h+var_68]
0x140186378  mov     qword ptr [rbp+57h+var_68+8], rax
0x14018637c  lea     rax, [rbp+57h+SecurityDescriptor]
0x140186380  mov     qword ptr [rbp+57h+var_48], rax
0x140186384  mov     dword ptr [rbp+57h+var_58], 19h
0x14018638b  mov     dword ptr [rbp+57h+var_48+8], r12d
0x14018638f  call    cs:__imp_NsiSetObjectSecurity
0x140186396  nop     dword ptr [rax+rax+00h]
0x14018639b  mov     ebx, eax
0x14018639d  test    eax, eax
0x14018639f  jnz     short loc_1401863EB
0x1401863a1  jmp     short loc_1401863A8
0x1401863a3  xor     esi, esi
0x1401863a5  xor     r14d, r14d
0x1401863a8  lea     rbx, [r15+4ED0h]
0x1401863af  mov     rcx, rbx; SpinLock
0x1401863b2  call    cs:__imp_KeInitializeSpinLock
0x1401863b9  nop     dword ptr [rax+rax+00h]
0x1401863be  lea     rcx, [r15+4DB8h]
0x1401863c5  mov     dword ptr [rbx+8], 0
0x1401863cc  call    IppInitializeLockedList
0x1401863d1  lock inc cs:IpngpReferenceCount
0x1401863d8  lock add dword ptr [r15+4D94h], 2000h
0x1401863e4  xor     ebx, ebx
0x1401863e6  test    r14, r14
0x1401863e9  jz      short loc_1401863FC
0x1401863eb  xor     edx, edx; Tag
0x1401863ed  mov     rcx, r14; P
0x1401863f0  call    cs:__imp_ExFreePoolWithTag
0x1401863f7  nop     dword ptr [rax+rax+00h]
0x1401863fc  test    rsi, rsi
0x1401863ff  jz      short loc_140186412
0x140186401  xor     edx, edx; Tag
0x140186403  mov     rcx, rsi; P
0x140186406  call    cs:__imp_ExFreePoolWithTag
0x14018640d  nop     dword ptr [rax+rax+00h]
0x140186412  mov     eax, ebx
0x140186414  add     rsp, 98h
0x14018641b  pop     r15
0x14018641d  pop     r14
0x14018641f  pop     r12
0x140186421  pop     rsi
0x140186422  pop     rbx
0x140186423  pop     rbp
0x140186424  retn
```
