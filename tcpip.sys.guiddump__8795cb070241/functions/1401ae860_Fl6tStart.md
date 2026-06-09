# Fl6tStart

- ea: `0x1401ae860`
- end: `0x1401aeb06`
- name: `Fl6tStart`
- size: `678`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x14007b0e8`
- `0x140154884`
- `0x1401a5744`
- `0x1401ae860`
- `0x1401aeee8`
- `0x1401aefa4`

## import_xrefs

- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1401ae9f6`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1401ae9f6`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1401ae9d3`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1401ae9d3`
- `ntoskrnl!RtlCreateAcl` at `0x1401ae994`
- `ntoskrnl!RtlCreateAcl` at `0x1401ae994`
- `ntoskrnl!RtlLengthSid` at `0x1401ae94c`
- `ntoskrnl!RtlLengthSid` at `0x1401ae94c`
- `ntoskrnl!SeExports` at `0x1401ae938`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1401ae922`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1401ae922`
- `ntoskrnl!KeInitializeSpinLock` at `0x1401ae8d4`
- `ntoskrnl!KeInitializeSpinLock` at `0x1401ae8d4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ae9ac`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401aea3d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ae9ac`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401aea3d`
- `ntoskrnl!ExAllocatePool2` at `0x1401ae96b`
- `ntoskrnl!ExAllocatePool2` at `0x1401ae96b`
- `NETIO!NmrRegisterProvider` at `0x1401aea62`
- `NETIO!NmrRegisterProvider` at `0x1401aea95`
- `NETIO!NmrRegisterProvider` at `0x1401aea62`
- `NETIO!NmrRegisterProvider` at `0x1401aea95`
- `NETIO!NmrWaitForProviderDeregisterComplete` at `0x1401aeac6`
- `NETIO!NmrWaitForProviderDeregisterComplete` at `0x1401aeac6`
- `NETIO!NmrDeregisterProvider` at `0x1401aeab3`
- `NETIO!NmrDeregisterProvider` at `0x1401aeab3`
- `NETIO!NsiSetObjectSecurity` at `0x1401aea29`
- `NETIO!NsiSetObjectSecurity` at `0x1401aea29`

## pseudocode

```c
__int64 Fl6tStart()
{
  __int64 result; // rax
  KSPIN_LOCK *Memory; // rax
  KSPIN_LOCK *v2; // rbx
  __int64 v3; // rdx
  __int64 v4; // rcx
  KSPIN_LOCK *v5; // rax
  NTSTATUS v6; // ebx
  PSID Sid; // r14
  __int64 v8; // rsi
  struct _ACL *Pool2; // rax
  struct _ACL *v10; // rbx
  NTSTATUS Acl; // edi
  struct _ACL *v12; // rcx
  NTSTATUS v13; // eax
  _OWORD SecurityDescriptor[2]; // [rsp+30h] [rbp-39h] BYREF
  __int64 v15; // [rsp+50h] [rbp-19h]
  __int128 v16; // [rsp+58h] [rbp-11h] BYREF
  __int128 v17; // [rsp+68h] [rbp-1h]
  __int128 v18; // [rsp+78h] [rbp+Fh]

  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  v15 = 0;
  FlTeredoInterface = 0;
  v16 = 0;
  v17 = 0;
  v18 = 0;
  result = FlpInitializeProviderState(&Fl6tpProviderState);
  if ( (int)result >= 0 )
  {
    _InterlockedExchange(&Fl6tIpIdentifier, 0);
    Memory = (KSPIN_LOCK *)FlpAllocateMemory(2112);
    TeredoFilterSet = Memory;
    v2 = Memory;
    if ( !Memory )
      goto LABEL_6;
    KeInitializeSpinLock(Memory);
    v3 = 0;
    *((_DWORD *)v2 + 2) = 0;
    v4 = 0;
    do
    {
      ++v3;
      v5 = &v2[v4 + 2];
      v2[v4 + 3] = (KSPIN_LOCK)v5;
      v2[v4 + 2] = (KSPIN_LOCK)v5;
      v4 += 2;
    }
    while ( v3 != 131 );
    result = FlEtRegisterCallouts(v4 * 8);
    if ( (int)result >= 0 )
    {
LABEL_6:
      v6 = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
      if ( v6 < 0 )
      {
LABEL_18:
        FlEtUninitializeCallouts();
        return (unsigned int)v6;
      }
      Sid = SeExports->SeWorldSid;
      v8 = RtlLengthSid(Sid) + 16;
      Pool2 = (struct _ACL *)ExAllocatePool2(64, v8, 1735289926);
      v10 = Pool2;
      if ( !Pool2 )
      {
        v6 = -1073741670;
        goto LABEL_18;
      }
      Acl = RtlCreateAcl(Pool2, v8, 2u);
      v12 = v10;
      if ( Acl < 0 )
        goto LABEL_10;
      Acl = RtlAddAccessAllowedAceEx(v10, 2u, 3u, 0x2001Fu, Sid);
      if ( Acl < 0 || (Acl = RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, v10, 0), Acl < 0) )
      {
        v12 = v10;
LABEL_10:
        ExFreePoolWithTag(v12, 0x676E6C46u);
LABEL_11:
        v6 = Acl;
        goto LABEL_18;
      }
      LODWORD(v17) = 0;
      *((_QWORD *)&v16 + 1) = &NPI_MS_FL6T_MODULEID;
      DWORD2(v18) = v8;
      *(_QWORD *)&v18 = SecurityDescriptor;
      Acl = NsiSetObjectSecurity(&v16);
      ExFreePoolWithTag(v10, 0x676E6C46u);
      if ( Acl )
        goto LABEL_11;
      v13 = NmrRegisterProvider(&stru_140223618, &stru_140223618, &qword_140223660);
      if ( v13 < 0 )
      {
        v6 = v13;
        goto LABEL_18;
      }
      _InterlockedIncrement(&FlpReferenceCount);
      v6 = NmrRegisterProvider(&stru_140223418, &stru_140223418, &qword_140223460);
      if ( v6 < 0 )
      {
        FlEtUninitializeCallouts();
        NmrDeregisterProvider(qword_140223660);
        NmrWaitForProviderDeregisterComplete(qword_140223660);
        FlpDereferenceDriver();
        qword_140223660 = 0;
        return (unsigned int)v6;
      }
      _InterlockedIncrement(&FlpReferenceCount);
      FlStartedModules |= 4uLL;
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1401ae860  push    rbp
0x1401ae862  push    rbx
0x1401ae863  push    rsi
0x1401ae864  push    rdi
0x1401ae865  push    r12
0x1401ae867  push    r14
0x1401ae869  lea     rbp, [rsp-2Fh]
0x1401ae86e  sub     rsp, 98h
0x1401ae875  xorps   xmm1, xmm1
0x1401ae878  lea     rcx, Fl6tpProviderState
0x1401ae87f  xorps   xmm0, xmm0
0x1401ae882  xor     eax, eax
0x1401ae884  movups  [rbp+57h+SecurityDescriptor], xmm0
0x1401ae888  mov     [rbp+57h+var_70], rax
0x1401ae88c  movups  [rbp+57h+var_80], xmm0
0x1401ae890  mov     cs:FlTeredoInterface, rax
0x1401ae897  movups  [rbp+57h+var_68], xmm1
0x1401ae89b  movups  [rbp+57h+var_58], xmm1
0x1401ae89f  movups  [rbp+57h+var_48], xmm1
0x1401ae8a3  call    FlpInitializeProviderState
0x1401ae8a8  test    eax, eax
0x1401ae8aa  js      loc_1401AEAF5
0x1401ae8b0  xor     eax, eax
0x1401ae8b2  mov     ecx, 840h
0x1401ae8b7  xchg    eax, cs:Fl6tIpIdentifier
0x1401ae8bd  call    FlpAllocateMemory
0x1401ae8c2  mov     cs:TeredoFilterSet, rax
0x1401ae8c9  mov     rbx, rax
0x1401ae8cc  test    rax, rax
0x1401ae8cf  jz      short loc_1401AE919
0x1401ae8d1  mov     rcx, rax; SpinLock
0x1401ae8d4  call    cs:__imp_KeInitializeSpinLock
0x1401ae8db  nop     dword ptr [rax+rax+00h]
0x1401ae8e0  xor     edx, edx
0x1401ae8e2  mov     dword ptr [rbx+8], 0
0x1401ae8e9  xor     ecx, ecx
0x1401ae8eb  lea     rax, [rbx+10h]
0x1401ae8ef  inc     rdx
0x1401ae8f2  add     rax, rcx
0x1401ae8f5  mov     [rcx+rbx+18h], rax
0x1401ae8fa  mov     [rcx+rbx+10h], rax
0x1401ae8ff  add     rcx, 10h
0x1401ae903  cmp     rdx, 83h
0x1401ae90a  jnz     short loc_1401AE8EB
0x1401ae90c  call    FlEtRegisterCallouts
0x1401ae911  test    eax, eax
0x1401ae913  js      loc_1401AEAF5
0x1401ae919  mov     edx, 1; Revision
0x1401ae91e  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x1401ae922  call    cs:__imp_RtlCreateSecurityDescriptor
0x1401ae929  nop     dword ptr [rax+rax+00h]
0x1401ae92e  mov     ebx, eax
0x1401ae930  test    eax, eax
0x1401ae932  js      loc_1401AEA74
0x1401ae938  mov     rax, cs:__imp_SeExports
0x1401ae93f  mov     rcx, [rax]
0x1401ae942  mov     r14, [rcx+0C0h]
0x1401ae949  mov     rcx, r14; Sid
0x1401ae94c  call    cs:__imp_RtlLengthSid
0x1401ae953  nop     dword ptr [rax+rax+00h]
0x1401ae958  mov     r12d, 676E6C46h
0x1401ae95e  mov     ecx, 40h ; '@'
0x1401ae963  mov     r8d, r12d
0x1401ae966  lea     esi, [rax+10h]
0x1401ae969  mov     edx, esi
0x1401ae96b  call    cs:__imp_ExAllocatePool2
0x1401ae972  nop     dword ptr [rax+rax+00h]
0x1401ae977  mov     rbx, rax
0x1401ae97a  test    rax, rax
0x1401ae97d  jnz     short loc_1401AE989
0x1401ae97f  mov     ebx, 0C000009Ah
0x1401ae984  jmp     loc_1401AEA74
0x1401ae989  mov     r8d, 2; AclRevision
0x1401ae98f  mov     edx, esi; AclLength
0x1401ae991  mov     rcx, rbx; Acl
0x1401ae994  call    cs:__imp_RtlCreateAcl
0x1401ae99b  nop     dword ptr [rax+rax+00h]
0x1401ae9a0  mov     edi, eax
0x1401ae9a2  mov     rcx, rbx; Acl
0x1401ae9a5  test    eax, eax
0x1401ae9a7  jns     short loc_1401AE9BF
0x1401ae9a9  mov     edx, r12d; Tag
0x1401ae9ac  call    cs:__imp_ExFreePoolWithTag
0x1401ae9b3  nop     dword ptr [rax+rax+00h]
0x1401ae9b8  mov     ebx, edi
0x1401ae9ba  jmp     loc_1401AEA74
0x1401ae9bf  mov     edx, 2; AceRevision
0x1401ae9c4  mov     [rsp+0C0h+Sid], r14; Sid
0x1401ae9c9  mov     r9d, 2001Fh; AccessMask
0x1401ae9cf  lea     r8d, [rdx+1]; AceFlags
0x1401ae9d3  call    cs:__imp_RtlAddAccessAllowedAceEx
0x1401ae9da  nop     dword ptr [rax+rax+00h]
0x1401ae9df  mov     edi, eax
0x1401ae9e1  test    eax, eax
0x1401ae9e3  jns     short loc_1401AE9EA
0x1401ae9e5  mov     rcx, rbx
0x1401ae9e8  jmp     short loc_1401AE9A9
0x1401ae9ea  xor     r9d, r9d; DaclDefaulted
0x1401ae9ed  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x1401ae9f1  mov     r8, rbx; Dacl
0x1401ae9f4  mov     dl, 1; DaclPresent
0x1401ae9f6  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x1401ae9fd  nop     dword ptr [rax+rax+00h]
0x1401aea02  mov     edi, eax
0x1401aea04  test    eax, eax
0x1401aea06  js      short loc_1401AE9E5
0x1401aea08  lea     rax, NPI_MS_FL6T_MODULEID
0x1401aea0f  mov     dword ptr [rbp+57h+var_58], 0
0x1401aea16  mov     qword ptr [rbp+57h+var_68+8], rax
0x1401aea1a  lea     rcx, [rbp+57h+var_68]
0x1401aea1e  lea     rax, [rbp+57h+SecurityDescriptor]
0x1401aea22  mov     dword ptr [rbp+57h+var_48+8], esi
0x1401aea25  mov     qword ptr [rbp+57h+var_48], rax
0x1401aea29  call    cs:__imp_NsiSetObjectSecurity
0x1401aea30  nop     dword ptr [rax+rax+00h]
0x1401aea35  mov     edx, r12d; Tag
0x1401aea38  mov     rcx, rbx; P
0x1401aea3b  mov     edi, eax
0x1401aea3d  call    cs:__imp_ExFreePoolWithTag
0x1401aea44  nop     dword ptr [rax+rax+00h]
0x1401aea49  test    edi, edi
0x1401aea4b  jnz     loc_1401AE9B8
0x1401aea51  lea     rcx, stru_140223618; ProviderCharacteristics
0x1401aea58  mov     rdx, rcx; ProviderContext
0x1401aea5b  lea     r8, qword_140223660; NmrProviderHandle
0x1401aea62  call    cs:__imp_NmrRegisterProvider
0x1401aea69  nop     dword ptr [rax+rax+00h]
0x1401aea6e  test    eax, eax
0x1401aea70  jns     short loc_1401AEA7D
0x1401aea72  mov     ebx, eax
0x1401aea74  call    FlEtUninitializeCallouts
0x1401aea79  mov     eax, ebx
0x1401aea7b  jmp     short loc_1401AEAF5
0x1401aea7d  lock inc cs:FlpReferenceCount
0x1401aea84  lea     rcx, stru_140223418; ProviderCharacteristics
0x1401aea8b  mov     rdx, rcx; ProviderContext
0x1401aea8e  lea     r8, qword_140223460; NmrProviderHandle
0x1401aea95  call    cs:__imp_NmrRegisterProvider
0x1401aea9c  nop     dword ptr [rax+rax+00h]
0x1401aeaa1  mov     ebx, eax
0x1401aeaa3  test    eax, eax
0x1401aeaa5  jns     short loc_1401AEAE4
0x1401aeaa7  call    FlEtUninitializeCallouts
0x1401aeaac  mov     rcx, cs:qword_140223660; NmrProviderHandle
0x1401aeab3  call    cs:__imp_NmrDeregisterProvider
0x1401aeaba  nop     dword ptr [rax+rax+00h]
0x1401aeabf  mov     rcx, cs:qword_140223660; NmrProviderHandle
0x1401aeac6  call    cs:__imp_NmrWaitForProviderDeregisterComplete
0x1401aeacd  nop     dword ptr [rax+rax+00h]
0x1401aead2  call    FlpDereferenceDriver
0x1401aead7  mov     cs:qword_140223660, 0
0x1401aeae2  jmp     short loc_1401AEA79
0x1401aeae4  lock inc cs:FlpReferenceCount
0x1401aeaeb  or      cs:FlStartedModules, 4
0x1401aeaf3  xor     eax, eax
0x1401aeaf5  add     rsp, 98h
0x1401aeafc  pop     r14
0x1401aeafe  pop     r12
0x1401aeb00  pop     rdi
0x1401aeb01  pop     rsi
0x1401aeb02  pop     rbx
0x1401aeb03  pop     rbp
0x1401aeb04  retn
```
