# VhdmpiCreateNonGenericSecurityDescriptorFromSddlString

- ea: `0x1400cc9b0`
- end: `0x1400ccbd4`
- name: `VhdmpiCreateNonGenericSecurityDescriptorFromSddlString`
- size: `548`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400b71a0`
- `0x1400ee42c`

## callees

- `0x140046544`
- `0x140046cf4`
- `0x1400cc9b0`
- `0x1400d3af4`

## import_xrefs

- `ntoskrnl!SeCaptureSubjectContext` at `0x1400ccaf3`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1400ccaf3`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1400ccb7a`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1400ccb7a`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x1400cca62`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x1400cca62`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1400cca9d`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1400cca9d`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1400ccac3`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1400ccac3`
- `ntoskrnl!SeAssignSecurity` at `0x1400ccb30`
- `ntoskrnl!SeAssignSecurity` at `0x1400ccb30`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1400ccb02`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1400ccb02`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400cca1c`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400cca1c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ccadb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ccb65`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ccb97`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ccbae`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ccadb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ccb65`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ccb97`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ccbae`

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
0x1400cc9b0  mov     rax, rsp
0x1400cc9b3  mov     [rax+18h], rbx
0x1400cc9b7  mov     [rax+10h], dl
0x1400cc9ba  mov     [rax+8], rcx
0x1400cc9be  push    rbp
0x1400cc9bf  push    rsi
0x1400cc9c0  push    rdi
0x1400cc9c1  push    r14
0x1400cc9c3  push    r15
0x1400cc9c5  lea     rbp, [rax-5Fh]
0x1400cc9c9  sub     rsp, 0B0h
0x1400cc9d0  xorps   xmm0, xmm0
0x1400cc9d3  mov     [rbp+57h+SecurityDescriptor], 0
0x1400cc9db  xor     eax, eax
0x1400cc9dd  lea     rdx, aDPAGaSyAGaBaAG; "D:P(A;;GA;;;SY)(A;;GA;;;BA)(A;;GA;;;AU)"...
0x1400cc9e4  xor     edi, edi
0x1400cc9e6  mov     [rbp+57h+var_48], rax
0x1400cc9ea  xor     esi, esi
0x1400cc9ec  mov     byte ptr [rbp+57h+DaclPresent], al
0x1400cc9ef  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1400cc9f3  mov     [rbp+57h+Dacl], rax
0x1400cc9f7  movups  [rbp+57h+var_68], xmm0
0x1400cc9fb  mov     [rbp+57h+DaclDefaulted], al
0x1400cc9fe  mov     r15, r8
0x1400cca01  movups  [rbp+57h+var_58], xmm0
0x1400cca05  mov     [rbp+57h+Sid], rdi
0x1400cca09  xor     r14b, r14b
0x1400cca0c  movups  xmmword ptr [rbp+57h+SubjectContext.ClientToken], xmm0
0x1400cca10  mov     [rbp+57h+var_90], rsi
0x1400cca14  movups  xmmword ptr [rbp+57h+SubjectContext.PrimaryToken], xmm0
0x1400cca18  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1400cca1c  call    cs:__imp_RtlInitUnicodeString
0x1400cca23  nop     dword ptr [rax+rax+00h]
0x1400cca28  lea     r8, [rbp+57h+SecurityDescriptor]
0x1400cca2c  lea     rcx, [rbp+57h+DestinationString]
0x1400cca30  call    SeSddlSecurityDescriptorFromSDDL
0x1400cca35  mov     ebx, eax
0x1400cca37  test    eax, eax
0x1400cca39  js      loc_1400CCB51
0x1400cca3f  lea     rcx, [rbp+57h+Sid]; void **
0x1400cca43  call    ?VhdmpiGetVmGroupSid@@YAJPEAPEAX@Z; VhdmpiGetVmGroupSid(void * *)
0x1400cca48  mov     ebx, eax
0x1400cca4a  test    eax, eax
0x1400cca4c  js      loc_1400CCB4D
0x1400cca52  mov     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x1400cca56  lea     r9, [rbp+57h+DaclDefaulted]; DaclDefaulted
0x1400cca5a  lea     r8, [rbp+57h+Dacl]; Dacl
0x1400cca5e  lea     rdx, [rbp+57h+DaclPresent]; DaclPresent
0x1400cca62  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x1400cca69  nop     dword ptr [rax+rax+00h]
0x1400cca6e  mov     ebx, eax
0x1400cca70  test    eax, eax
0x1400cca72  js      loc_1400CCB4D
0x1400cca78  mov     rdi, [rbp+57h+Sid]
0x1400cca7c  lea     r8, [rbp+57h+var_90]; struct _ACL **
0x1400cca80  mov     rcx, [rbp+57h+Dacl]; Acl
0x1400cca84  mov     rdx, rdi; Sid
0x1400cca87  call    ?VhdmpiCreateAclFromSid@@YAJPEAU_ACL@@PEAXPEAPEAU1@@Z; VhdmpiCreateAclFromSid(_ACL *,void *,_ACL * *)
0x1400cca8c  mov     ebx, eax
0x1400cca8e  test    eax, eax
0x1400cca90  js      loc_1400CCB47
0x1400cca96  lea     edx, [rsi+1]; Revision
0x1400cca99  lea     rcx, [rbp+57h+var_68]; SecurityDescriptor
0x1400cca9d  call    cs:__imp_RtlCreateSecurityDescriptor
0x1400ccaa4  nop     dword ptr [rax+rax+00h]
0x1400ccaa9  mov     ebx, eax
0x1400ccaab  test    eax, eax
0x1400ccaad  js      loc_1400CCB47
0x1400ccab3  mov     rsi, [rbp+57h+var_90]
0x1400ccab7  lea     rcx, [rbp+57h+var_68]; SecurityDescriptor
0x1400ccabb  mov     r8, rsi; Dacl
0x1400ccabe  xor     r9d, r9d; DaclDefaulted
0x1400ccac1  mov     dl, 1; DaclPresent
0x1400ccac3  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x1400ccaca  nop     dword ptr [rax+rax+00h]
0x1400ccacf  mov     ebx, eax
0x1400ccad1  test    eax, eax
0x1400ccad3  js      short loc_1400CCB51
0x1400ccad5  mov     rcx, [rbp+57h+SecurityDescriptor]; P
0x1400ccad9  xor     edx, edx; Tag
0x1400ccadb  call    cs:__imp_ExFreePoolWithTag
0x1400ccae2  nop     dword ptr [rax+rax+00h]
0x1400ccae7  lea     rax, [rbp+57h+var_68]
0x1400ccaeb  lea     rcx, [rbp+57h+SubjectContext]; SubjectContext
0x1400ccaef  mov     [rbp+57h+SecurityDescriptor], rax
0x1400ccaf3  call    cs:__imp_SeCaptureSubjectContext
0x1400ccafa  nop     dword ptr [rax+rax+00h]
0x1400ccaff  mov     r14b, 1
0x1400ccb02  call    cs:__imp_IoGetFileObjectGenericMapping
0x1400ccb09  nop     dword ptr [rax+rax+00h]
0x1400ccb0e  mov     rdx, [rbp+57h+SecurityDescriptor]; ExplicitDescriptor
0x1400ccb12  xor     r9d, r9d; IsDirectoryObject
0x1400ccb15  mov     dword ptr [rsp+30h], 1; PoolType
0x1400ccb1d  mov     r8, r15; NewDescriptor
0x1400ccb20  mov     [rsp+0D0h+GenericMapping], rax; GenericMapping
0x1400ccb25  xor     ecx, ecx; ParentDescriptor
0x1400ccb27  lea     rax, [rbp+57h+SubjectContext]
0x1400ccb2b  mov     [rsp+0D0h+var_B0], rax; SubjectContext
0x1400ccb30  call    cs:__imp_SeAssignSecurity
0x1400ccb37  nop     dword ptr [rax+rax+00h]
0x1400ccb3c  mov     ebx, eax
0x1400ccb3e  xor     eax, eax
0x1400ccb40  test    ebx, ebx
0x1400ccb42  cmovns  ebx, eax
0x1400ccb45  jmp     short loc_1400CCB51
0x1400ccb47  mov     rsi, [rbp+57h+var_90]
0x1400ccb4b  jmp     short loc_1400CCB51
0x1400ccb4d  mov     rdi, [rbp+57h+Sid]
0x1400ccb51  mov     rcx, [rbp+57h+SecurityDescriptor]; P
0x1400ccb55  test    rcx, rcx
0x1400ccb58  jz      short loc_1400CCB71
0x1400ccb5a  lea     rax, [rbp+57h+var_68]
0x1400ccb5e  cmp     rcx, rax
0x1400ccb61  jz      short loc_1400CCB71
0x1400ccb63  xor     edx, edx; Tag
0x1400ccb65  call    cs:__imp_ExFreePoolWithTag
0x1400ccb6c  nop     dword ptr [rax+rax+00h]
0x1400ccb71  test    r14b, r14b
0x1400ccb74  jz      short loc_1400CCB86
0x1400ccb76  lea     rcx, [rbp+57h+SubjectContext]; SubjectContext
0x1400ccb7a  call    cs:__imp_SeReleaseSubjectContext
0x1400ccb81  nop     dword ptr [rax+rax+00h]
0x1400ccb86  mov     r14d, 61444856h
0x1400ccb8c  test    rsi, rsi
0x1400ccb8f  jz      short loc_1400CCBA3
0x1400ccb91  mov     edx, r14d; Tag
0x1400ccb94  mov     rcx, rsi; P
0x1400ccb97  call    cs:__imp_ExFreePoolWithTag
0x1400ccb9e  nop     dword ptr [rax+rax+00h]
0x1400ccba3  test    rdi, rdi
0x1400ccba6  jz      short loc_1400CCBBA
0x1400ccba8  mov     edx, r14d; Tag
0x1400ccbab  mov     rcx, rdi; P
0x1400ccbae  call    cs:__imp_ExFreePoolWithTag
0x1400ccbb5  nop     dword ptr [rax+rax+00h]
0x1400ccbba  mov     eax, ebx
0x1400ccbbc  mov     rbx, [rsp+0D0h+arg_10]
0x1400ccbc4  add     rsp, 0B0h
0x1400ccbcb  pop     r15
0x1400ccbcd  pop     r14
0x1400ccbcf  pop     rdi
0x1400ccbd0  pop     rsi
0x1400ccbd1  pop     rbp
0x1400ccbd2  retn
```
