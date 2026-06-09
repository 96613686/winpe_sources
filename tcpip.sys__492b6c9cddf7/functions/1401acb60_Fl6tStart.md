# Fl6tStart

- ea: `0x1401acb60`
- end: `0x1401ace06`
- name: `Fl6tStart`
- size: `678`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x1400c82f8`
- `0x140152864`
- `0x1401a3a40`
- `0x1401acb60`
- `0x1401ad1e8`
- `0x1401ad2a4`

## import_xrefs

- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1401accf6`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1401accf6`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1401accd3`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1401accd3`
- `ntoskrnl!RtlCreateAcl` at `0x1401acc94`
- `ntoskrnl!RtlCreateAcl` at `0x1401acc94`
- `ntoskrnl!RtlLengthSid` at `0x1401acc4c`
- `ntoskrnl!RtlLengthSid` at `0x1401acc4c`
- `ntoskrnl!SeExports` at `0x1401acc38`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1401acc22`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1401acc22`
- `ntoskrnl!KeInitializeSpinLock` at `0x1401acbd4`
- `ntoskrnl!KeInitializeSpinLock` at `0x1401acbd4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401accac`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401acd3d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401accac`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401acd3d`
- `ntoskrnl!ExAllocatePool2` at `0x1401acc6b`
- `ntoskrnl!ExAllocatePool2` at `0x1401acc6b`
- `NETIO!NmrRegisterProvider` at `0x1401acd62`
- `NETIO!NmrRegisterProvider` at `0x1401acd95`
- `NETIO!NmrRegisterProvider` at `0x1401acd62`
- `NETIO!NmrRegisterProvider` at `0x1401acd95`
- `NETIO!NmrWaitForProviderDeregisterComplete` at `0x1401acdc6`
- `NETIO!NmrWaitForProviderDeregisterComplete` at `0x1401acdc6`
- `NETIO!NmrDeregisterProvider` at `0x1401acdb3`
- `NETIO!NmrDeregisterProvider` at `0x1401acdb3`
- `NETIO!NsiSetObjectSecurity` at `0x1401acd29`
- `NETIO!NsiSetObjectSecurity` at `0x1401acd29`

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
      v13 = NmrRegisterProvider(&stru_14021F618, &stru_14021F618, &qword_14021F660);
      if ( v13 < 0 )
      {
        v6 = v13;
        goto LABEL_18;
      }
      _InterlockedIncrement(&FlpReferenceCount);
      v6 = NmrRegisterProvider(&stru_14021F418, &stru_14021F418, &qword_14021F460);
      if ( v6 < 0 )
      {
        FlEtUninitializeCallouts();
        NmrDeregisterProvider(qword_14021F660);
        NmrWaitForProviderDeregisterComplete(qword_14021F660);
        FlpDereferenceDriver();
        qword_14021F660 = 0;
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
0x1401acb60  push    rbp
0x1401acb62  push    rbx
0x1401acb63  push    rsi
0x1401acb64  push    rdi
0x1401acb65  push    r12
0x1401acb67  push    r14
0x1401acb69  lea     rbp, [rsp-2Fh]
0x1401acb6e  sub     rsp, 98h
0x1401acb75  xorps   xmm1, xmm1
0x1401acb78  lea     rcx, Fl6tpProviderState
0x1401acb7f  xorps   xmm0, xmm0
0x1401acb82  xor     eax, eax
0x1401acb84  movups  [rbp+57h+SecurityDescriptor], xmm0
0x1401acb88  mov     [rbp+57h+var_70], rax
0x1401acb8c  movups  [rbp+57h+var_80], xmm0
0x1401acb90  mov     cs:FlTeredoInterface, rax
0x1401acb97  movups  [rbp+57h+var_68], xmm1
0x1401acb9b  movups  [rbp+57h+var_58], xmm1
0x1401acb9f  movups  [rbp+57h+var_48], xmm1
0x1401acba3  call    FlpInitializeProviderState
0x1401acba8  test    eax, eax
0x1401acbaa  js      loc_1401ACDF5
0x1401acbb0  xor     eax, eax
0x1401acbb2  mov     ecx, 840h
0x1401acbb7  xchg    eax, cs:Fl6tIpIdentifier
0x1401acbbd  call    FlpAllocateMemory
0x1401acbc2  mov     cs:TeredoFilterSet, rax
0x1401acbc9  mov     rbx, rax
0x1401acbcc  test    rax, rax
0x1401acbcf  jz      short loc_1401ACC19
0x1401acbd1  mov     rcx, rax; SpinLock
0x1401acbd4  call    cs:__imp_KeInitializeSpinLock
0x1401acbdb  nop     dword ptr [rax+rax+00h]
0x1401acbe0  xor     edx, edx
0x1401acbe2  mov     dword ptr [rbx+8], 0
0x1401acbe9  xor     ecx, ecx
0x1401acbeb  lea     rax, [rbx+10h]
0x1401acbef  inc     rdx
0x1401acbf2  add     rax, rcx
0x1401acbf5  mov     [rcx+rbx+18h], rax
0x1401acbfa  mov     [rcx+rbx+10h], rax
0x1401acbff  add     rcx, 10h
0x1401acc03  cmp     rdx, 83h
0x1401acc0a  jnz     short loc_1401ACBEB
0x1401acc0c  call    FlEtRegisterCallouts
0x1401acc11  test    eax, eax
0x1401acc13  js      loc_1401ACDF5
0x1401acc19  mov     edx, 1; Revision
0x1401acc1e  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x1401acc22  call    cs:__imp_RtlCreateSecurityDescriptor
0x1401acc29  nop     dword ptr [rax+rax+00h]
0x1401acc2e  mov     ebx, eax
0x1401acc30  test    eax, eax
0x1401acc32  js      loc_1401ACD74
0x1401acc38  mov     rax, cs:__imp_SeExports
0x1401acc3f  mov     rcx, [rax]
0x1401acc42  mov     r14, [rcx+0C0h]
0x1401acc49  mov     rcx, r14; Sid
0x1401acc4c  call    cs:__imp_RtlLengthSid
0x1401acc53  nop     dword ptr [rax+rax+00h]
0x1401acc58  mov     r12d, 676E6C46h
0x1401acc5e  mov     ecx, 40h ; '@'
0x1401acc63  mov     r8d, r12d
0x1401acc66  lea     esi, [rax+10h]
0x1401acc69  mov     edx, esi
0x1401acc6b  call    cs:__imp_ExAllocatePool2
0x1401acc72  nop     dword ptr [rax+rax+00h]
0x1401acc77  mov     rbx, rax
0x1401acc7a  test    rax, rax
0x1401acc7d  jnz     short loc_1401ACC89
0x1401acc7f  mov     ebx, 0C000009Ah
0x1401acc84  jmp     loc_1401ACD74
0x1401acc89  mov     r8d, 2; AclRevision
0x1401acc8f  mov     edx, esi; AclLength
0x1401acc91  mov     rcx, rbx; Acl
0x1401acc94  call    cs:__imp_RtlCreateAcl
0x1401acc9b  nop     dword ptr [rax+rax+00h]
0x1401acca0  mov     edi, eax
0x1401acca2  mov     rcx, rbx; Acl
0x1401acca5  test    eax, eax
0x1401acca7  jns     short loc_1401ACCBF
0x1401acca9  mov     edx, r12d; Tag
0x1401accac  call    cs:__imp_ExFreePoolWithTag
0x1401accb3  nop     dword ptr [rax+rax+00h]
0x1401accb8  mov     ebx, edi
0x1401accba  jmp     loc_1401ACD74
0x1401accbf  mov     edx, 2; AceRevision
0x1401accc4  mov     [rsp+0C0h+Sid], r14; Sid
0x1401accc9  mov     r9d, 2001Fh; AccessMask
0x1401acccf  lea     r8d, [rdx+1]; AceFlags
0x1401accd3  call    cs:__imp_RtlAddAccessAllowedAceEx
0x1401accda  nop     dword ptr [rax+rax+00h]
0x1401accdf  mov     edi, eax
0x1401acce1  test    eax, eax
0x1401acce3  jns     short loc_1401ACCEA
0x1401acce5  mov     rcx, rbx
0x1401acce8  jmp     short loc_1401ACCA9
0x1401accea  xor     r9d, r9d; DaclDefaulted
0x1401acced  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x1401accf1  mov     r8, rbx; Dacl
0x1401accf4  mov     dl, 1; DaclPresent
0x1401accf6  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x1401accfd  nop     dword ptr [rax+rax+00h]
0x1401acd02  mov     edi, eax
0x1401acd04  test    eax, eax
0x1401acd06  js      short loc_1401ACCE5
0x1401acd08  lea     rax, NPI_MS_FL6T_MODULEID
0x1401acd0f  mov     dword ptr [rbp+57h+var_58], 0
0x1401acd16  mov     qword ptr [rbp+57h+var_68+8], rax
0x1401acd1a  lea     rcx, [rbp+57h+var_68]
0x1401acd1e  lea     rax, [rbp+57h+SecurityDescriptor]
0x1401acd22  mov     dword ptr [rbp+57h+var_48+8], esi
0x1401acd25  mov     qword ptr [rbp+57h+var_48], rax
0x1401acd29  call    cs:__imp_NsiSetObjectSecurity
0x1401acd30  nop     dword ptr [rax+rax+00h]
0x1401acd35  mov     edx, r12d; Tag
0x1401acd38  mov     rcx, rbx; P
0x1401acd3b  mov     edi, eax
0x1401acd3d  call    cs:__imp_ExFreePoolWithTag
0x1401acd44  nop     dword ptr [rax+rax+00h]
0x1401acd49  test    edi, edi
0x1401acd4b  jnz     loc_1401ACCB8
0x1401acd51  lea     rcx, stru_14021F618; ProviderCharacteristics
0x1401acd58  mov     rdx, rcx; ProviderContext
0x1401acd5b  lea     r8, qword_14021F660; NmrProviderHandle
0x1401acd62  call    cs:__imp_NmrRegisterProvider
0x1401acd69  nop     dword ptr [rax+rax+00h]
0x1401acd6e  test    eax, eax
0x1401acd70  jns     short loc_1401ACD7D
0x1401acd72  mov     ebx, eax
0x1401acd74  call    FlEtUninitializeCallouts
0x1401acd79  mov     eax, ebx
0x1401acd7b  jmp     short loc_1401ACDF5
0x1401acd7d  lock inc cs:FlpReferenceCount
0x1401acd84  lea     rcx, stru_14021F418; ProviderCharacteristics
0x1401acd8b  mov     rdx, rcx; ProviderContext
0x1401acd8e  lea     r8, qword_14021F460; NmrProviderHandle
0x1401acd95  call    cs:__imp_NmrRegisterProvider
0x1401acd9c  nop     dword ptr [rax+rax+00h]
0x1401acda1  mov     ebx, eax
0x1401acda3  test    eax, eax
0x1401acda5  jns     short loc_1401ACDE4
0x1401acda7  call    FlEtUninitializeCallouts
0x1401acdac  mov     rcx, cs:qword_14021F660; NmrProviderHandle
0x1401acdb3  call    cs:__imp_NmrDeregisterProvider
0x1401acdba  nop     dword ptr [rax+rax+00h]
0x1401acdbf  mov     rcx, cs:qword_14021F660; NmrProviderHandle
0x1401acdc6  call    cs:__imp_NmrWaitForProviderDeregisterComplete
0x1401acdcd  nop     dword ptr [rax+rax+00h]
0x1401acdd2  call    FlpDereferenceDriver
0x1401acdd7  mov     cs:qword_14021F660, 0
0x1401acde2  jmp     short loc_1401ACD79
0x1401acde4  lock inc cs:FlpReferenceCount
0x1401acdeb  or      cs:FlStartedModules, 4
0x1401acdf3  xor     eax, eax
0x1401acdf5  add     rsp, 98h
0x1401acdfc  pop     r14
0x1401acdfe  pop     r12
0x1401ace00  pop     rdi
0x1401ace01  pop     rsi
0x1401ace02  pop     rbx
0x1401ace03  pop     rbp
0x1401ace04  retn
```
