# VhdmpiCreateNonGenericSecurityDescriptorFromSddlString

- ea: `0x1400cc9a0`
- end: `0x1400ccbc4`
- name: `VhdmpiCreateNonGenericSecurityDescriptorFromSddlString`
- size: `548`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400b7188`
- `0x1400ee42c`

## callees

- `0x140046934`
- `0x1400470e4`
- `0x1400cc9a0`
- `0x1400d3a84`

## import_xrefs

- `ntoskrnl!SeCaptureSubjectContext` at `0x1400ccae3`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1400ccae3`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1400ccb6a`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1400ccb6a`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x1400cca52`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x1400cca52`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1400cca8d`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1400cca8d`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1400ccab3`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1400ccab3`
- `ntoskrnl!SeAssignSecurity` at `0x1400ccb20`
- `ntoskrnl!SeAssignSecurity` at `0x1400ccb20`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1400ccaf2`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1400ccaf2`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400cca0c`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400cca0c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ccacb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ccb55`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ccb87`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ccb9e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ccacb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ccb55`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ccb87`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ccb9e`

## pseudocode

```c
__int64 __fastcall VhdmpiCreateNonGenericSecurityDescriptorFromSddlString(
        __int64 a1,
        __int64 a2,
        PSECURITY_DESCRIPTOR *a3)
{
  PSID v3; // rdi
  PACL v4; // rsi
  char v6; // r14
  __int64 v7; // rdx
  NTSTATUS VmGroupSid; // ebx
  struct _GENERIC_MAPPING *GenericMapping; // rax
  PACL v11; // [rsp+48h] [rbp-39h] BYREF
  PSID Sid; // [rsp+50h] [rbp-31h] BYREF
  PACL Dacl; // [rsp+58h] [rbp-29h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-21h] BYREF
  _OWORD v15[2]; // [rsp+70h] [rbp-11h] BYREF
  __int64 v16; // [rsp+90h] [rbp+Fh]
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+98h] [rbp+17h] BYREF
  __int64 DaclPresent; // [rsp+E8h] [rbp+67h] BYREF
  unsigned __int8 DaclDefaulted; // [rsp+F0h] [rbp+6Fh] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+100h] [rbp+7Fh] BYREF

  DaclPresent = a1;
  SecurityDescriptor = 0;
  v3 = 0;
  v16 = 0;
  v4 = 0;
  LOBYTE(DaclPresent) = 0;
  Dacl = 0;
  memset(v15, 0, sizeof(v15));
  DaclDefaulted = 0;
  Sid = 0;
  v6 = 0;
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  v11 = 0;
  DestinationString = 0;
  RtlInitUnicodeString(
    &DestinationString,
    L"D:P(A;;GA;;;SY)(A;;GA;;;BA)(A;;GA;;;AU)(A;;GA;;;S-1-15-3-1024-2268835264-3721307629-241982045-173645152-1490879176-1"
     "04643441-2915960892-1612460704)");
  VmGroupSid = SeSddlSecurityDescriptorFromSDDL(&DestinationString, v7, &SecurityDescriptor);
  if ( VmGroupSid >= 0 )
  {
    VmGroupSid = VhdmpiGetVmGroupSid(&Sid);
    if ( VmGroupSid < 0
      || (VmGroupSid = RtlGetDaclSecurityDescriptor(SecurityDescriptor, (PBOOLEAN)&DaclPresent, &Dacl, &DaclDefaulted),
          VmGroupSid < 0) )
    {
      v3 = Sid;
    }
    else
    {
      v3 = Sid;
      VmGroupSid = VhdmpiCreateAclFromSid(Dacl, Sid, &v11);
      if ( VmGroupSid < 0 || (VmGroupSid = RtlCreateSecurityDescriptor(v15, 1u), VmGroupSid < 0) )
      {
        v4 = v11;
      }
      else
      {
        v4 = v11;
        VmGroupSid = RtlSetDaclSecurityDescriptor(v15, 1u, v11, 0);
        if ( VmGroupSid >= 0 )
        {
          ExFreePoolWithTag(SecurityDescriptor, 0);
          SecurityDescriptor = v15;
          SeCaptureSubjectContext(&SubjectContext);
          v6 = 1;
          GenericMapping = IoGetFileObjectGenericMapping();
          VmGroupSid = SeAssignSecurity(0, SecurityDescriptor, a3, 0, &SubjectContext, GenericMapping, PagedPool);
          if ( VmGroupSid >= 0 )
            VmGroupSid = 0;
        }
      }
    }
  }
  if ( SecurityDescriptor && SecurityDescriptor != v15 )
    ExFreePoolWithTag(SecurityDescriptor, 0);
  if ( v6 )
    SeReleaseSubjectContext(&SubjectContext);
  if ( v4 )
    ExFreePoolWithTag(v4, 0x61444856u);
  if ( v3 )
    ExFreePoolWithTag(v3, 0x61444856u);
  return (unsigned int)VmGroupSid;
}

```

## disassembly

```asm
0x1400cc9a0  mov     rax, rsp
0x1400cc9a3  mov     [rax+18h], rbx
0x1400cc9a7  mov     [rax+10h], dl
0x1400cc9aa  mov     [rax+8], rcx
0x1400cc9ae  push    rbp
0x1400cc9af  push    rsi
0x1400cc9b0  push    rdi
0x1400cc9b1  push    r14
0x1400cc9b3  push    r15
0x1400cc9b5  lea     rbp, [rax-5Fh]
0x1400cc9b9  sub     rsp, 0B0h
0x1400cc9c0  xorps   xmm0, xmm0
0x1400cc9c3  mov     [rbp+57h+SecurityDescriptor], 0
0x1400cc9cb  xor     eax, eax
0x1400cc9cd  lea     rdx, aDPAGaSyAGaBaAG; "D:P(A;;GA;;;SY)(A;;GA;;;BA)(A;;GA;;;AU)"...
0x1400cc9d4  xor     edi, edi
0x1400cc9d6  mov     [rbp+57h+var_48], rax
0x1400cc9da  xor     esi, esi
0x1400cc9dc  mov     byte ptr [rbp+57h+DaclPresent], al
0x1400cc9df  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1400cc9e3  mov     [rbp+57h+Dacl], rax
0x1400cc9e7  movups  [rbp+57h+var_68], xmm0
0x1400cc9eb  mov     [rbp+57h+DaclDefaulted], al
0x1400cc9ee  mov     r15, r8
0x1400cc9f1  movups  [rbp+57h+var_58], xmm0
0x1400cc9f5  mov     [rbp+57h+Sid], rdi
0x1400cc9f9  xor     r14b, r14b
0x1400cc9fc  movups  xmmword ptr [rbp+57h+SubjectContext.ClientToken], xmm0
0x1400cca00  mov     [rbp+57h+var_90], rsi
0x1400cca04  movups  xmmword ptr [rbp+57h+SubjectContext.PrimaryToken], xmm0
0x1400cca08  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1400cca0c  call    cs:__imp_RtlInitUnicodeString
0x1400cca13  nop     dword ptr [rax+rax+00h]
0x1400cca18  lea     r8, [rbp+57h+SecurityDescriptor]
0x1400cca1c  lea     rcx, [rbp+57h+DestinationString]
0x1400cca20  call    SeSddlSecurityDescriptorFromSDDL
0x1400cca25  mov     ebx, eax
0x1400cca27  test    eax, eax
0x1400cca29  js      loc_1400CCB41
0x1400cca2f  lea     rcx, [rbp+57h+Sid]; void **
0x1400cca33  call    ?VhdmpiGetVmGroupSid@@YAJPEAPEAX@Z; VhdmpiGetVmGroupSid(void * *)
0x1400cca38  mov     ebx, eax
0x1400cca3a  test    eax, eax
0x1400cca3c  js      loc_1400CCB3D
0x1400cca42  mov     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x1400cca46  lea     r9, [rbp+57h+DaclDefaulted]; DaclDefaulted
0x1400cca4a  lea     r8, [rbp+57h+Dacl]; Dacl
0x1400cca4e  lea     rdx, [rbp+57h+DaclPresent]; DaclPresent
0x1400cca52  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x1400cca59  nop     dword ptr [rax+rax+00h]
0x1400cca5e  mov     ebx, eax
0x1400cca60  test    eax, eax
0x1400cca62  js      loc_1400CCB3D
0x1400cca68  mov     rdi, [rbp+57h+Sid]
0x1400cca6c  lea     r8, [rbp+57h+var_90]; struct _ACL **
0x1400cca70  mov     rcx, [rbp+57h+Dacl]; Acl
0x1400cca74  mov     rdx, rdi; Sid
0x1400cca77  call    ?VhdmpiCreateAclFromSid@@YAJPEAU_ACL@@PEAXPEAPEAU1@@Z; VhdmpiCreateAclFromSid(_ACL *,void *,_ACL * *)
0x1400cca7c  mov     ebx, eax
0x1400cca7e  test    eax, eax
0x1400cca80  js      loc_1400CCB37
0x1400cca86  lea     edx, [rsi+1]; Revision
0x1400cca89  lea     rcx, [rbp+57h+var_68]; SecurityDescriptor
0x1400cca8d  call    cs:__imp_RtlCreateSecurityDescriptor
0x1400cca94  nop     dword ptr [rax+rax+00h]
0x1400cca99  mov     ebx, eax
0x1400cca9b  test    eax, eax
0x1400cca9d  js      loc_1400CCB37
0x1400ccaa3  mov     rsi, [rbp+57h+var_90]
0x1400ccaa7  lea     rcx, [rbp+57h+var_68]; SecurityDescriptor
0x1400ccaab  mov     r8, rsi; Dacl
0x1400ccaae  xor     r9d, r9d; DaclDefaulted
0x1400ccab1  mov     dl, 1; DaclPresent
0x1400ccab3  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x1400ccaba  nop     dword ptr [rax+rax+00h]
0x1400ccabf  mov     ebx, eax
0x1400ccac1  test    eax, eax
0x1400ccac3  js      short loc_1400CCB41
0x1400ccac5  mov     rcx, [rbp+57h+SecurityDescriptor]; P
0x1400ccac9  xor     edx, edx; Tag
0x1400ccacb  call    cs:__imp_ExFreePoolWithTag
0x1400ccad2  nop     dword ptr [rax+rax+00h]
0x1400ccad7  lea     rax, [rbp+57h+var_68]
0x1400ccadb  lea     rcx, [rbp+57h+SubjectContext]; SubjectContext
0x1400ccadf  mov     [rbp+57h+SecurityDescriptor], rax
0x1400ccae3  call    cs:__imp_SeCaptureSubjectContext
0x1400ccaea  nop     dword ptr [rax+rax+00h]
0x1400ccaef  mov     r14b, 1
0x1400ccaf2  call    cs:__imp_IoGetFileObjectGenericMapping
0x1400ccaf9  nop     dword ptr [rax+rax+00h]
0x1400ccafe  mov     rdx, [rbp+57h+SecurityDescriptor]; ExplicitDescriptor
0x1400ccb02  xor     r9d, r9d; IsDirectoryObject
0x1400ccb05  mov     dword ptr [rsp+30h], 1; PoolType
0x1400ccb0d  mov     r8, r15; NewDescriptor
0x1400ccb10  mov     [rsp+0D0h+GenericMapping], rax; GenericMapping
0x1400ccb15  xor     ecx, ecx; ParentDescriptor
0x1400ccb17  lea     rax, [rbp+57h+SubjectContext]
0x1400ccb1b  mov     [rsp+0D0h+var_B0], rax; SubjectContext
0x1400ccb20  call    cs:__imp_SeAssignSecurity
0x1400ccb27  nop     dword ptr [rax+rax+00h]
0x1400ccb2c  mov     ebx, eax
0x1400ccb2e  xor     eax, eax
0x1400ccb30  test    ebx, ebx
0x1400ccb32  cmovns  ebx, eax
0x1400ccb35  jmp     short loc_1400CCB41
0x1400ccb37  mov     rsi, [rbp+57h+var_90]
0x1400ccb3b  jmp     short loc_1400CCB41
0x1400ccb3d  mov     rdi, [rbp+57h+Sid]
0x1400ccb41  mov     rcx, [rbp+57h+SecurityDescriptor]; P
0x1400ccb45  test    rcx, rcx
0x1400ccb48  jz      short loc_1400CCB61
0x1400ccb4a  lea     rax, [rbp+57h+var_68]
0x1400ccb4e  cmp     rcx, rax
0x1400ccb51  jz      short loc_1400CCB61
0x1400ccb53  xor     edx, edx; Tag
0x1400ccb55  call    cs:__imp_ExFreePoolWithTag
0x1400ccb5c  nop     dword ptr [rax+rax+00h]
0x1400ccb61  test    r14b, r14b
0x1400ccb64  jz      short loc_1400CCB76
0x1400ccb66  lea     rcx, [rbp+57h+SubjectContext]; SubjectContext
0x1400ccb6a  call    cs:__imp_SeReleaseSubjectContext
0x1400ccb71  nop     dword ptr [rax+rax+00h]
0x1400ccb76  mov     r14d, 61444856h
0x1400ccb7c  test    rsi, rsi
0x1400ccb7f  jz      short loc_1400CCB93
0x1400ccb81  mov     edx, r14d; Tag
0x1400ccb84  mov     rcx, rsi; P
0x1400ccb87  call    cs:__imp_ExFreePoolWithTag
0x1400ccb8e  nop     dword ptr [rax+rax+00h]
0x1400ccb93  test    rdi, rdi
0x1400ccb96  jz      short loc_1400CCBAA
0x1400ccb98  mov     edx, r14d; Tag
0x1400ccb9b  mov     rcx, rdi; P
0x1400ccb9e  call    cs:__imp_ExFreePoolWithTag
0x1400ccba5  nop     dword ptr [rax+rax+00h]
0x1400ccbaa  mov     eax, ebx
0x1400ccbac  mov     rbx, [rsp+0D0h+arg_10]
0x1400ccbb4  add     rsp, 0B0h
0x1400ccbbb  pop     r15
0x1400ccbbd  pop     r14
0x1400ccbbf  pop     rdi
0x1400ccbc0  pop     rsi
0x1400ccbc1  pop     rbp
0x1400ccbc2  retn
```
