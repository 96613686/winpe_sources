# IppStartInterfaceManager

- ea: `0x1401845a0`
- end: `0x140184806`
- name: `IppStartInterfaceManager`
- size: `614`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x140053e98`
- `0x1401821a4`
- `0x1401845a0`

## import_xrefs

- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140184744`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140184744`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x140184722`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x140184722`
- `ntoskrnl!RtlCreateAcl` at `0x1401846f5`
- `ntoskrnl!RtlCreateAcl` at `0x1401846f5`
- `ntoskrnl!RtlLengthSid` at `0x140184690`
- `ntoskrnl!RtlLengthSid` at `0x140184690`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140184605`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140184605`
- `ntoskrnl!KeInitializeSpinLock` at `0x140184792`
- `ntoskrnl!KeInitializeSpinLock` at `0x140184792`
- `ntoskrnl!RtlLengthRequiredSid` at `0x140184620`
- `ntoskrnl!RtlLengthRequiredSid` at `0x140184620`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401847d0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401847e6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401847d0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401847e6`
- `ntoskrnl!ExAllocatePool2` at `0x14018463f`
- `ntoskrnl!ExAllocatePool2` at `0x1401846a9`
- `ntoskrnl!ExAllocatePool2` at `0x14018463f`
- `ntoskrnl!ExAllocatePool2` at `0x1401846a9`
- `NETIO!NsiSetObjectSecurity` at `0x14018476f`
- `NETIO!NsiSetObjectSecurity` at `0x14018476f`
- `NETIO!NsiResetPersistentSetting` at `0x1401845f0`
- `NETIO!NsiResetPersistentSetting` at `0x1401845f0`

## string_xrefs

- `0x1401846c5`: `interface manager ACL (IPNG)`
- `0x14018465b`: `interface manager SID (IPNG)`

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
  if ( SBYTE3(WPP_MAIN_CB.Reserved) < 0 )
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
0x1401845a0  push    rbp
0x1401845a2  push    rbx
0x1401845a3  push    rsi
0x1401845a4  push    r12
0x1401845a6  push    r14
0x1401845a8  push    r15
0x1401845aa  lea     rbp, [rsp-2Fh]
0x1401845af  sub     rsp, 98h
0x1401845b6  xorps   xmm1, xmm1
0x1401845b9  xor     eax, eax
0x1401845bb  cmp     dword ptr [rcx+18h], 29h ; ')'
0x1401845bf  xorps   xmm0, xmm0
0x1401845c2  mov     r15, rcx
0x1401845c5  mov     [rbp+57h+var_70], rax
0x1401845c9  movups  [rbp+57h+SecurityDescriptor], xmm0
0x1401845cd  movups  [rbp+57h+var_80], xmm0
0x1401845d1  movups  [rbp+57h+var_68], xmm1
0x1401845d5  movups  [rbp+57h+var_58], xmm1
0x1401845d9  movups  [rbp+57h+var_48], xmm1
0x1401845dd  jnz     loc_140184783
0x1401845e3  mov     rcx, [rcx+20h]
0x1401845e7  lea     edx, [rax+19h]
0x1401845ea  xor     r9d, r9d
0x1401845ed  xor     r8d, r8d
0x1401845f0  call    cs:__imp_NsiResetPersistentSetting
0x1401845f7  nop     dword ptr [rax+rax+00h]
0x1401845fc  mov     edx, 1; Revision
0x140184601  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x140184605  call    cs:__imp_RtlCreateSecurityDescriptor
0x14018460c  nop     dword ptr [rax+rax+00h]
0x140184611  mov     ebx, eax
0x140184613  test    eax, eax
0x140184615  js      loc_1401847F2
0x14018461b  mov     ecx, 1; SubAuthorityCount
0x140184620  call    cs:__imp_RtlLengthRequiredSid
0x140184627  nop     dword ptr [rax+rax+00h]
0x14018462c  mov     ebx, 676E7049h
0x140184631  mov     r14d, 40h ; '@'
0x140184637  mov     edx, eax
0x140184639  mov     r8d, ebx
0x14018463c  mov     ecx, r14d
0x14018463f  call    cs:__imp_ExAllocatePool2
0x140184646  nop     dword ptr [rax+rax+00h]
0x14018464b  mov     rsi, rax
0x14018464e  test    rax, rax
0x140184651  jnz     short loc_14018467F
0x140184653  cmp     byte ptr cs:WPP_MAIN_CB.Reserved+3, al
0x140184659  jge     short loc_140184675
0x14018465b  lea     r9, aInterfaceManag; "interface manager SID (IPNG)"
0x140184662  lea     rdx, TCPIP_MEMORY_FAILURES
0x140184669  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x140184670  call    McTemplateK0z_EtwWriteTransfer
0x140184675  mov     ebx, 0C000009Ah
0x14018467a  jmp     loc_1401847F2
0x14018467f  mov     dword ptr [rax], 101h
0x140184685  mov     rcx, rsi; Sid
0x140184688  mov     qword ptr [rax+4], 1000000h
0x140184690  call    cs:__imp_RtlLengthSid
0x140184697  nop     dword ptr [rax+rax+00h]
0x14018469c  mov     r8d, ebx
0x14018469f  mov     rcx, r14
0x1401846a2  lea     r12d, [rax+10h]
0x1401846a6  mov     edx, r12d
0x1401846a9  call    cs:__imp_ExAllocatePool2
0x1401846b0  nop     dword ptr [rax+rax+00h]
0x1401846b5  mov     r14, rax
0x1401846b8  test    rax, rax
0x1401846bb  jnz     short loc_1401846E9
0x1401846bd  cmp     byte ptr cs:WPP_MAIN_CB.Reserved+3, al
0x1401846c3  jge     short loc_1401846DF
0x1401846c5  lea     r9, aInterfaceManag_0; "interface manager ACL (IPNG)"
0x1401846cc  lea     rdx, TCPIP_MEMORY_FAILURES
0x1401846d3  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x1401846da  call    McTemplateK0z_EtwWriteTransfer
0x1401846df  mov     ebx, 0C000009Ah
0x1401846e4  jmp     loc_1401847E1
0x1401846e9  mov     r8d, 2; AclRevision
0x1401846ef  mov     edx, r12d; AclLength
0x1401846f2  mov     rcx, r14; Acl
0x1401846f5  call    cs:__imp_RtlCreateAcl
0x1401846fc  nop     dword ptr [rax+rax+00h]
0x140184701  mov     ebx, eax
0x140184703  test    eax, eax
0x140184705  js      loc_1401847CB
0x14018470b  mov     edx, 2; AceRevision
0x140184710  mov     [rsp+0C0h+Sid], rsi; Sid
0x140184715  mov     r9d, 2001Fh; AccessMask
0x14018471b  mov     rcx, r14; Acl
0x14018471e  lea     r8d, [rdx+1]; AceFlags
0x140184722  call    cs:__imp_RtlAddAccessAllowedAceEx
0x140184729  nop     dword ptr [rax+rax+00h]
0x14018472e  mov     ebx, eax
0x140184730  test    eax, eax
0x140184732  js      loc_1401847CB
0x140184738  xor     r9d, r9d; DaclDefaulted
0x14018473b  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x14018473f  mov     r8, r14; Dacl
0x140184742  mov     dl, 1; DaclPresent
0x140184744  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x14018474b  nop     dword ptr [rax+rax+00h]
0x140184750  mov     rax, [r15+20h]
0x140184754  lea     rcx, [rbp+57h+var_68]
0x140184758  mov     qword ptr [rbp+57h+var_68+8], rax
0x14018475c  lea     rax, [rbp+57h+SecurityDescriptor]
0x140184760  mov     qword ptr [rbp+57h+var_48], rax
0x140184764  mov     dword ptr [rbp+57h+var_58], 19h
0x14018476b  mov     dword ptr [rbp+57h+var_48+8], r12d
0x14018476f  call    cs:__imp_NsiSetObjectSecurity
0x140184776  nop     dword ptr [rax+rax+00h]
0x14018477b  mov     ebx, eax
0x14018477d  test    eax, eax
0x14018477f  jnz     short loc_1401847CB
0x140184781  jmp     short loc_140184788
0x140184783  xor     esi, esi
0x140184785  xor     r14d, r14d
0x140184788  lea     rbx, [r15+4ED0h]
0x14018478f  mov     rcx, rbx; SpinLock
0x140184792  call    cs:__imp_KeInitializeSpinLock
0x140184799  nop     dword ptr [rax+rax+00h]
0x14018479e  lea     rcx, [r15+4DB8h]
0x1401847a5  mov     dword ptr [rbx+8], 0
0x1401847ac  call    IppInitializeLockedList
0x1401847b1  lock inc cs:IpngpReferenceCount
0x1401847b8  lock add dword ptr [r15+4D94h], 2000h
0x1401847c4  xor     ebx, ebx
0x1401847c6  test    r14, r14
0x1401847c9  jz      short loc_1401847DC
0x1401847cb  xor     edx, edx; Tag
0x1401847cd  mov     rcx, r14; P
0x1401847d0  call    cs:__imp_ExFreePoolWithTag
0x1401847d7  nop     dword ptr [rax+rax+00h]
0x1401847dc  test    rsi, rsi
0x1401847df  jz      short loc_1401847F2
0x1401847e1  xor     edx, edx; Tag
0x1401847e3  mov     rcx, rsi; P
0x1401847e6  call    cs:__imp_ExFreePoolWithTag
0x1401847ed  nop     dword ptr [rax+rax+00h]
0x1401847f2  mov     eax, ebx
0x1401847f4  add     rsp, 98h
0x1401847fb  pop     r15
0x1401847fd  pop     r14
0x1401847ff  pop     r12
0x140184801  pop     rsi
0x140184802  pop     rbx
0x140184803  pop     rbp
0x140184804  retn
```
