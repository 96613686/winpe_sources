# Fl6tStart

- ea: `0x1401acca0`
- end: `0x1401acf46`
- name: `Fl6tStart`
- size: `678`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x1400c80d8`
- `0x1401529a4`
- `0x1401a3b80`
- `0x1401acca0`
- `0x1401ad328`
- `0x1401ad3e4`

## import_xrefs

- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1401ace36`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1401ace36`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1401ace13`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1401ace13`
- `ntoskrnl!RtlCreateAcl` at `0x1401acdd4`
- `ntoskrnl!RtlCreateAcl` at `0x1401acdd4`
- `ntoskrnl!RtlLengthSid` at `0x1401acd8c`
- `ntoskrnl!RtlLengthSid` at `0x1401acd8c`
- `ntoskrnl!SeExports` at `0x1401acd78`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1401acd62`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1401acd62`
- `ntoskrnl!KeInitializeSpinLock` at `0x1401acd14`
- `ntoskrnl!KeInitializeSpinLock` at `0x1401acd14`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401acdec`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ace7d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401acdec`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ace7d`
- `ntoskrnl!ExAllocatePool2` at `0x1401acdab`
- `ntoskrnl!ExAllocatePool2` at `0x1401acdab`
- `NETIO!NmrRegisterProvider` at `0x1401acea2`
- `NETIO!NmrRegisterProvider` at `0x1401aced5`
- `NETIO!NmrRegisterProvider` at `0x1401acea2`
- `NETIO!NmrRegisterProvider` at `0x1401aced5`
- `NETIO!NmrWaitForProviderDeregisterComplete` at `0x1401acf06`
- `NETIO!NmrWaitForProviderDeregisterComplete` at `0x1401acf06`
- `NETIO!NmrDeregisterProvider` at `0x1401acef3`
- `NETIO!NmrDeregisterProvider` at `0x1401acef3`
- `NETIO!NsiSetObjectSecurity` at `0x1401ace69`
- `NETIO!NsiSetObjectSecurity` at `0x1401ace69`

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
0x1401acca0  push    rbp
0x1401acca2  push    rbx
0x1401acca3  push    rsi
0x1401acca4  push    rdi
0x1401acca5  push    r12
0x1401acca7  push    r14
0x1401acca9  lea     rbp, [rsp-2Fh]
0x1401accae  sub     rsp, 98h
0x1401accb5  xorps   xmm1, xmm1
0x1401accb8  lea     rcx, Fl6tpProviderState
0x1401accbf  xorps   xmm0, xmm0
0x1401accc2  xor     eax, eax
0x1401accc4  movups  [rbp+57h+SecurityDescriptor], xmm0
0x1401accc8  mov     [rbp+57h+var_70], rax
0x1401acccc  movups  [rbp+57h+var_80], xmm0
0x1401accd0  mov     cs:FlTeredoInterface, rax
0x1401accd7  movups  [rbp+57h+var_68], xmm1
0x1401accdb  movups  [rbp+57h+var_58], xmm1
0x1401accdf  movups  [rbp+57h+var_48], xmm1
0x1401acce3  call    FlpInitializeProviderState
0x1401acce8  test    eax, eax
0x1401accea  js      loc_1401ACF35
0x1401accf0  xor     eax, eax
0x1401accf2  mov     ecx, 840h
0x1401accf7  xchg    eax, cs:Fl6tIpIdentifier
0x1401accfd  call    FlpAllocateMemory
0x1401acd02  mov     cs:TeredoFilterSet, rax
0x1401acd09  mov     rbx, rax
0x1401acd0c  test    rax, rax
0x1401acd0f  jz      short loc_1401ACD59
0x1401acd11  mov     rcx, rax; SpinLock
0x1401acd14  call    cs:__imp_KeInitializeSpinLock
0x1401acd1b  nop     dword ptr [rax+rax+00h]
0x1401acd20  xor     edx, edx
0x1401acd22  mov     dword ptr [rbx+8], 0
0x1401acd29  xor     ecx, ecx
0x1401acd2b  lea     rax, [rbx+10h]
0x1401acd2f  inc     rdx
0x1401acd32  add     rax, rcx
0x1401acd35  mov     [rcx+rbx+18h], rax
0x1401acd3a  mov     [rcx+rbx+10h], rax
0x1401acd3f  add     rcx, 10h
0x1401acd43  cmp     rdx, 83h
0x1401acd4a  jnz     short loc_1401ACD2B
0x1401acd4c  call    FlEtRegisterCallouts
0x1401acd51  test    eax, eax
0x1401acd53  js      loc_1401ACF35
0x1401acd59  mov     edx, 1; Revision
0x1401acd5e  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x1401acd62  call    cs:__imp_RtlCreateSecurityDescriptor
0x1401acd69  nop     dword ptr [rax+rax+00h]
0x1401acd6e  mov     ebx, eax
0x1401acd70  test    eax, eax
0x1401acd72  js      loc_1401ACEB4
0x1401acd78  mov     rax, cs:__imp_SeExports
0x1401acd7f  mov     rcx, [rax]
0x1401acd82  mov     r14, [rcx+0C0h]
0x1401acd89  mov     rcx, r14; Sid
0x1401acd8c  call    cs:__imp_RtlLengthSid
0x1401acd93  nop     dword ptr [rax+rax+00h]
0x1401acd98  mov     r12d, 676E6C46h
0x1401acd9e  mov     ecx, 40h ; '@'
0x1401acda3  mov     r8d, r12d
0x1401acda6  lea     esi, [rax+10h]
0x1401acda9  mov     edx, esi
0x1401acdab  call    cs:__imp_ExAllocatePool2
0x1401acdb2  nop     dword ptr [rax+rax+00h]
0x1401acdb7  mov     rbx, rax
0x1401acdba  test    rax, rax
0x1401acdbd  jnz     short loc_1401ACDC9
0x1401acdbf  mov     ebx, 0C000009Ah
0x1401acdc4  jmp     loc_1401ACEB4
0x1401acdc9  mov     r8d, 2; AclRevision
0x1401acdcf  mov     edx, esi; AclLength
0x1401acdd1  mov     rcx, rbx; Acl
0x1401acdd4  call    cs:__imp_RtlCreateAcl
0x1401acddb  nop     dword ptr [rax+rax+00h]
0x1401acde0  mov     edi, eax
0x1401acde2  mov     rcx, rbx; Acl
0x1401acde5  test    eax, eax
0x1401acde7  jns     short loc_1401ACDFF
0x1401acde9  mov     edx, r12d; Tag
0x1401acdec  call    cs:__imp_ExFreePoolWithTag
0x1401acdf3  nop     dword ptr [rax+rax+00h]
0x1401acdf8  mov     ebx, edi
0x1401acdfa  jmp     loc_1401ACEB4
0x1401acdff  mov     edx, 2; AceRevision
0x1401ace04  mov     [rsp+0C0h+Sid], r14; Sid
0x1401ace09  mov     r9d, 2001Fh; AccessMask
0x1401ace0f  lea     r8d, [rdx+1]; AceFlags
0x1401ace13  call    cs:__imp_RtlAddAccessAllowedAceEx
0x1401ace1a  nop     dword ptr [rax+rax+00h]
0x1401ace1f  mov     edi, eax
0x1401ace21  test    eax, eax
0x1401ace23  jns     short loc_1401ACE2A
0x1401ace25  mov     rcx, rbx
0x1401ace28  jmp     short loc_1401ACDE9
0x1401ace2a  xor     r9d, r9d; DaclDefaulted
0x1401ace2d  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x1401ace31  mov     r8, rbx; Dacl
0x1401ace34  mov     dl, 1; DaclPresent
0x1401ace36  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x1401ace3d  nop     dword ptr [rax+rax+00h]
0x1401ace42  mov     edi, eax
0x1401ace44  test    eax, eax
0x1401ace46  js      short loc_1401ACE25
0x1401ace48  lea     rax, NPI_MS_FL6T_MODULEID
0x1401ace4f  mov     dword ptr [rbp+57h+var_58], 0
0x1401ace56  mov     qword ptr [rbp+57h+var_68+8], rax
0x1401ace5a  lea     rcx, [rbp+57h+var_68]
0x1401ace5e  lea     rax, [rbp+57h+SecurityDescriptor]
0x1401ace62  mov     dword ptr [rbp+57h+var_48+8], esi
0x1401ace65  mov     qword ptr [rbp+57h+var_48], rax
0x1401ace69  call    cs:__imp_NsiSetObjectSecurity
0x1401ace70  nop     dword ptr [rax+rax+00h]
0x1401ace75  mov     edx, r12d; Tag
0x1401ace78  mov     rcx, rbx; P
0x1401ace7b  mov     edi, eax
0x1401ace7d  call    cs:__imp_ExFreePoolWithTag
0x1401ace84  nop     dword ptr [rax+rax+00h]
0x1401ace89  test    edi, edi
0x1401ace8b  jnz     loc_1401ACDF8
0x1401ace91  lea     rcx, stru_14021F618; ProviderCharacteristics
0x1401ace98  mov     rdx, rcx; ProviderContext
0x1401ace9b  lea     r8, qword_14021F660; NmrProviderHandle
0x1401acea2  call    cs:__imp_NmrRegisterProvider
0x1401acea9  nop     dword ptr [rax+rax+00h]
0x1401aceae  test    eax, eax
0x1401aceb0  jns     short loc_1401ACEBD
0x1401aceb2  mov     ebx, eax
0x1401aceb4  call    FlEtUninitializeCallouts
0x1401aceb9  mov     eax, ebx
0x1401acebb  jmp     short loc_1401ACF35
0x1401acebd  lock inc cs:FlpReferenceCount
0x1401acec4  lea     rcx, stru_14021F418; ProviderCharacteristics
0x1401acecb  mov     rdx, rcx; ProviderContext
0x1401acece  lea     r8, qword_14021F460; NmrProviderHandle
0x1401aced5  call    cs:__imp_NmrRegisterProvider
0x1401acedc  nop     dword ptr [rax+rax+00h]
0x1401acee1  mov     ebx, eax
0x1401acee3  test    eax, eax
0x1401acee5  jns     short loc_1401ACF24
0x1401acee7  call    FlEtUninitializeCallouts
0x1401aceec  mov     rcx, cs:qword_14021F660; NmrProviderHandle
0x1401acef3  call    cs:__imp_NmrDeregisterProvider
0x1401acefa  nop     dword ptr [rax+rax+00h]
0x1401aceff  mov     rcx, cs:qword_14021F660; NmrProviderHandle
0x1401acf06  call    cs:__imp_NmrWaitForProviderDeregisterComplete
0x1401acf0d  nop     dword ptr [rax+rax+00h]
0x1401acf12  call    FlpDereferenceDriver
0x1401acf17  mov     cs:qword_14021F660, 0
0x1401acf22  jmp     short loc_1401ACEB9
0x1401acf24  lock inc cs:FlpReferenceCount
0x1401acf2b  or      cs:FlStartedModules, 4
0x1401acf33  xor     eax, eax
0x1401acf35  add     rsp, 98h
0x1401acf3c  pop     r14
0x1401acf3e  pop     r12
0x1401acf40  pop     rdi
0x1401acf41  pop     rsi
0x1401acf42  pop     rbx
0x1401acf43  pop     rbp
0x1401acf44  retn
```
