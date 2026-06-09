# VmsOmNonGenericSecurityDescriptorFromSddlString

- ea: `0x1401136a0`
- end: `0x140113d77`
- name: `VmsOmNonGenericSecurityDescriptorFromSddlString`
- size: `1751`
- prototype: `__int64 __fastcall(int, int, int, int, PSECURITY_DESCRIPTOR *NewDescriptor)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14010d7e0`

## callees

- `0x140027a64`
- `0x14002e0f0`
- `0x14003a450`
- `0x14008497c`
- `0x14011313c`
- `0x140113378`
- `0x140113524`
- `0x1401136a0`
- `0x140113d80`
- `0x140237c44`

## import_xrefs

- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x14011380a`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x14011380a`
- `ntoskrnl!RtlValidSid` at `0x140113850`
- `ntoskrnl!RtlValidSid` at `0x140113892`
- `ntoskrnl!RtlValidSid` at `0x140113850`
- `ntoskrnl!RtlValidSid` at `0x140113892`
- `ntoskrnl!RtlCreateAcl` at `0x14011395f`
- `ntoskrnl!RtlCreateAcl` at `0x14011395f`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1401139b7`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140113a0f`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140113a67`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1401139b7`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140113a0f`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140113a67`
- `ntoskrnl!RtlGetAce` at `0x140113ac6`
- `ntoskrnl!RtlGetAce` at `0x140113ac6`
- `ntoskrnl!RtlAddAce` at `0x140113af1`
- `ntoskrnl!RtlAddAce` at `0x140113af1`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140113b79`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140113b79`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140113bcf`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140113bcf`
- `ntoskrnl!SeAssignSecurity` at `0x140113c6a`
- `ntoskrnl!SeAssignSecurity` at `0x140113c6a`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140113cd7`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140113cd7`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140113c40`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140113c40`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140113c31`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140113c31`
- `ntoskrnl!RtlLengthSid` at `0x1401138b3`
- `ntoskrnl!RtlLengthSid` at `0x1401138cd`
- `ntoskrnl!RtlLengthSid` at `0x1401138e7`
- `ntoskrnl!RtlLengthSid` at `0x1401138b3`
- `ntoskrnl!RtlLengthSid` at `0x1401138cd`
- `ntoskrnl!RtlLengthSid` at `0x1401138e7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140113c19`
- `ntoskrnl!ExFreePoolWithTag` at `0x140113cc1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140113cf2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140113d09`
- `ntoskrnl!ExFreePoolWithTag` at `0x140113d20`
- `ntoskrnl!ExFreePoolWithTag` at `0x140113d37`
- `ntoskrnl!ExFreePoolWithTag` at `0x140113c19`
- `ntoskrnl!ExFreePoolWithTag` at `0x140113cc1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140113cf2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140113d09`
- `ntoskrnl!ExFreePoolWithTag` at `0x140113d20`
- `ntoskrnl!ExFreePoolWithTag` at `0x140113d37`
- `ntoskrnl!ExAllocatePool2` at `0x140113905`
- `ntoskrnl!ExAllocatePool2` at `0x140113905`
- `ntoskrnl!RtlInitUnicodeString` at `0x140113754`
- `ntoskrnl!RtlInitUnicodeString` at `0x140113754`

## string_xrefs

- `0x14011371f`: `SecurityDescriptor != NULL`
- `0x140113867`: `RtlValidSid(callerSID)`

## pseudocode

```c
__int64 __fastcall VmsOmNonGenericSecurityDescriptorFromSddlString(
        __int64 a1,
        int a2,
        char a3,
        char a4,
        PSECURITY_DESCRIPTOR *NewDescriptor)
{
  PSECURITY_DESCRIPTOR *v5; // r12
  struct _ACL *v8; // r14
  char v9; // r13
  __int64 v10; // rdx
  int v11; // eax
  int v12; // edx
  int CallerSid; // ebx
  int v14; // edx
  int v15; // r8d
  int v16; // r9d
  char v17; // di
  NTSTATUS DaclSecurityDescriptor; // eax
  int v19; // edx
  int v20; // edx
  int AclSize; // edi
  ULONG v22; // edi
  struct _ACL *Pool2; // rax
  int v24; // edx
  NTSTATUS Acl; // eax
  int v26; // edx
  NTSTATUS v27; // eax
  int v28; // edx
  NTSTATUS v29; // eax
  int v30; // edx
  NTSTATUS v31; // eax
  int v32; // edx
  unsigned int i; // esi
  NTSTATUS v34; // eax
  int v35; // edx
  NTSTATUS v36; // eax
  int v37; // edx
  int v38; // edx
  NTSTATUS v39; // eax
  int v40; // edx
  struct _GENERIC_MAPPING *FileObjectGenericMapping; // rax
  NTSTATUS v42; // eax
  int v43; // ecx
  int AceListLength; // [rsp+28h] [rbp-A1h]
  int GenericMapping; // [rsp+30h] [rbp-99h]
  int PoolType; // [rsp+38h] [rbp-91h]
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+58h] [rbp-71h] BYREF
  PSID Sid; // [rsp+60h] [rbp-69h] BYREF
  PSID P; // [rsp+68h] [rbp-61h] BYREF
  PSID v51; // [rsp+70h] [rbp-59h] BYREF
  PACL Dacl; // [rsp+78h] [rbp-51h] BYREF
  PVOID Ace; // [rsp+80h] [rbp-49h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+88h] [rbp-41h] BYREF
  _OWORD v55[2]; // [rsp+98h] [rbp-31h] BYREF
  __int64 v56; // [rsp+B8h] [rbp-11h]
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+C0h] [rbp-9h] BYREF
  __int64 DaclPresent; // [rsp+128h] [rbp+5Fh] BYREF
  unsigned __int8 DaclDefaulted; // [rsp+130h] [rbp+67h] BYREF

  DaclPresent = a1;
  v5 = NewDescriptor;
  SecurityDescriptor = 0;
  v56 = 0;
  Ace = 0;
  Sid = 0;
  v8 = 0;
  P = 0;
  v9 = 0;
  v51 = 0;
  LOBYTE(DaclPresent) = 0;
  Dacl = 0;
  DaclDefaulted = 0;
  memset(v55, 0, sizeof(v55));
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  DestinationString = 0;
  if ( !NewDescriptor )
  {
    WPP_RECORDER_SF_s(
      VmsIfrLog,
      a2,
      19,
      21,
      (__int64)WPP_8ba27d42bb8b3f236fd12e8dd774299f_Traceguids,
      (__int64)"SecurityDescriptor != NULL");
    MicrosoftTelemetryAssertTriggeredNoArgsKM();
  }
  RtlInitUnicodeString(&DestinationString, L"D:P(A;;GA;;;SY)(A;;GA;;;BA)(D;;GA;;;WD)");
  v11 = SeSddlSecurityDescriptorFromSDDL(&DestinationString, v10, &SecurityDescriptor);
  CallerSid = v11;
  if ( v11 >= 0 )
  {
    CallerSid = VmsOmGetCallerSid(&Sid);
    if ( CallerSid >= 0 )
    {
      if ( a3 && (CallerSid = VmsOmGetVmGroupSid(&P), CallerSid < 0) )
      {
        v17 = 15;
      }
      else if ( a4 && (CallerSid = VmsOmGetVmCapabilitySid(&v51), CallerSid < 0) )
      {
        v17 = 16;
      }
      else
      {
        DaclSecurityDescriptor = RtlGetDaclSecurityDescriptor(
                                   SecurityDescriptor,
                                   (PBOOLEAN)&DaclPresent,
                                   &Dacl,
                                   &DaclDefaulted);
        CallerSid = DaclSecurityDescriptor;
        if ( DaclSecurityDescriptor >= 0 )
        {
          if ( !RtlValidSid(Sid) )
          {
            WPP_RECORDER_SF_s(
              VmsIfrLog,
              v20,
              19,
              24,
              (__int64)WPP_8ba27d42bb8b3f236fd12e8dd774299f_Traceguids,
              (__int64)"RtlValidSid(callerSID)");
            if ( !RtlValidSid(Sid) )
              MicrosoftTelemetryAssertTriggeredNoArgsKM();
          }
          AclSize = Dacl->AclSize;
          v22 = RtlLengthSid(Sid) + AclSize + 8;
          if ( P )
            v22 += RtlLengthSid(P) + 8;
          if ( v51 )
            v22 += RtlLengthSid(v51) + 8;
          Pool2 = (struct _ACL *)ExAllocatePool2(64, v22, 1649374038);
          v8 = Pool2;
          if ( Pool2 )
          {
            Acl = RtlCreateAcl(Pool2, v22, 2u);
            CallerSid = Acl;
            if ( Acl >= 0 )
            {
              v27 = RtlAddAccessAllowedAce(v8, 2u, 0x10000000u, Sid);
              CallerSid = v27;
              if ( v27 >= 0 )
              {
                if ( a3 && (v29 = RtlAddAccessAllowedAce(v8, 2u, 0x10000000u, P), CallerSid = v29, v29 < 0) )
                {
                  LOBYTE(v30) = 2;
                  WPP_RECORDER_SF_d(
                    VmsIfrLog,
                    v30,
                    20,
                    28,
                    (__int64)WPP_8ba27d42bb8b3f236fd12e8dd774299f_Traceguids,
                    v29);
                  v17 = 36;
                }
                else if ( a4 && (v31 = RtlAddAccessAllowedAce(v8, 2u, 0x10000000u, v51), CallerSid = v31, v31 < 0) )
                {
                  LOBYTE(v32) = 2;
                  WPP_RECORDER_SF_d(
                    VmsIfrLog,
                    v32,
                    20,
                    29,
                    (__int64)WPP_8ba27d42bb8b3f236fd12e8dd774299f_Traceguids,
                    v31);
                  v17 = 40;
                }
                else
                {
                  for ( i = 0; i < Dacl->AceCount; ++i )
                  {
                    v34 = RtlGetAce(Dacl, i, &Ace);
                    CallerSid = v34;
                    if ( v34 < 0 )
                    {
                      LOBYTE(v35) = 2;
                      WPP_RECORDER_SF_ld(
                        VmsIfrLog,
                        v35,
                        20,
                        30,
                        (__int64)WPP_8ba27d42bb8b3f236fd12e8dd774299f_Traceguids,
                        i,
                        v34);
                      v17 = 45;
                      goto LABEL_49;
                    }
                    v36 = RtlAddAce(v8, 2u, 0xFFFFFFFF, Ace, *((unsigned __int16 *)Ace + 1));
                    CallerSid = v36;
                    if ( v36 < 0 )
                    {
                      LOBYTE(v37) = 2;
                      WPP_RECORDER_SF_ld(
                        VmsIfrLog,
                        v37,
                        20,
                        31,
                        (__int64)WPP_8ba27d42bb8b3f236fd12e8dd774299f_Traceguids,
                        i,
                        v36);
                      v17 = 50;
                      goto LABEL_49;
                    }
                  }
                  if ( RtlCreateSecurityDescriptor(v55, 1u) >= 0 )
                  {
                    v39 = RtlSetDaclSecurityDescriptor(v55, 1u, v8, 0);
                    CallerSid = v39;
                    if ( v39 < 0 )
                    {
                      LOBYTE(v40) = 2;
                      WPP_RECORDER_SF_d(
                        VmsIfrLog,
                        v40,
                        20,
                        33,
                        (__int64)WPP_8ba27d42bb8b3f236fd12e8dd774299f_Traceguids,
                        v39);
                      v17 = 60;
                      goto LABEL_49;
                    }
                    ExFreePoolWithTag(SecurityDescriptor, 0);
                    SecurityDescriptor = v55;
                    SeCaptureSubjectContext(&SubjectContext);
                    v9 = 1;
                    FileObjectGenericMapping = IoGetFileObjectGenericMapping();
                    v42 = SeAssignSecurity(
                            0,
                            SecurityDescriptor,
                            v5,
                            0,
                            &SubjectContext,
                            FileObjectGenericMapping,
                            PagedPool);
                    CallerSid = v42;
                    if ( v42 >= 0 )
                    {
                      v17 = 0;
                      CallerSid = 0;
                      goto LABEL_49;
                    }
                    LOBYTE(v14) = 2;
                    WPP_RECORDER_SF_d(
                      VmsIfrLog,
                      v14,
                      20,
                      34,
                      (__int64)WPP_8ba27d42bb8b3f236fd12e8dd774299f_Traceguids,
                      v42);
                  }
                  else
                  {
                    CallerSid = -1073741670;
                    LOBYTE(v38) = 2;
                    WPP_RECORDER_SF_d(
                      VmsIfrLog,
                      v38,
                      20,
                      32,
                      (__int64)WPP_8ba27d42bb8b3f236fd12e8dd774299f_Traceguids,
                      154);
                  }
                  v17 = 55;
                }
              }
              else
              {
                LOBYTE(v28) = 2;
                WPP_RECORDER_SF_d(VmsIfrLog, v28, 20, 27, (__int64)WPP_8ba27d42bb8b3f236fd12e8dd774299f_Traceguids, v27);
                v17 = 35;
              }
            }
            else
            {
              LOBYTE(v26) = 2;
              WPP_RECORDER_SF_d(VmsIfrLog, v26, 20, 26, (__int64)WPP_8ba27d42bb8b3f236fd12e8dd774299f_Traceguids, Acl);
              v17 = 30;
            }
          }
          else
          {
            CallerSid = -1073741670;
            LOBYTE(v24) = 2;
            WPP_RECORDER_SF_ld(
              VmsIfrLog,
              v24,
              20,
              25,
              (__int64)WPP_8ba27d42bb8b3f236fd12e8dd774299f_Traceguids,
              v22,
              154);
            v17 = 25;
          }
        }
        else
        {
          LOBYTE(v19) = 2;
          v17 = 20;
          WPP_RECORDER_SF_d(
            VmsIfrLog,
            v19,
            20,
            23,
            (__int64)WPP_8ba27d42bb8b3f236fd12e8dd774299f_Traceguids,
            DaclSecurityDescriptor);
        }
      }
    }
    else
    {
      v17 = 10;
    }
  }
  else
  {
    LOBYTE(v12) = 2;
    WPP_RECORDER_SF_d(VmsIfrLog, v12, 20, 22, (__int64)WPP_8ba27d42bb8b3f236fd12e8dd774299f_Traceguids, v11);
    v17 = 5;
  }
LABEL_49:
  if ( SecurityDescriptor && SecurityDescriptor != v55 )
    ExFreePoolWithTag(SecurityDescriptor, 0);
  if ( v9 == 1 )
    SeReleaseSubjectContext(&SubjectContext);
  if ( v8 )
    ExFreePoolWithTag(v8, 0x624F7356u);
  if ( Sid )
    ExFreePoolWithTag(Sid, 0x624F7356u);
  if ( P )
    ExFreePoolWithTag(P, 0x624F7356u);
  v43 = (int)v51;
  if ( v51 )
    ExFreePoolWithTag(v51, 0x624F7356u);
  if ( CallerSid < 0 )
    WPP_RECORDER_SF_SdqdD(v43, v14, v15, v16, AceListLength, GenericMapping, PoolType, (char)v5, CallerSid, v17);
  return (unsigned int)CallerSid;
}

```

## disassembly

```asm
0x1401136a0  mov     rax, rsp
0x1401136a3  mov     [rax+18h], rbx
0x1401136a7  mov     [rax+10h], dl
0x1401136aa  mov     [rax+8], rcx
0x1401136ae  push    rbp
0x1401136af  push    rsi
0x1401136b0  push    rdi
0x1401136b1  push    r12
0x1401136b3  push    r13
0x1401136b5  push    r14
0x1401136b7  push    r15
0x1401136b9  lea     rbp, [rax-57h]
0x1401136bd  sub     rsp, 0E0h
0x1401136c4  mov     r12, [rbp+4Fh+NewDescriptor]
0x1401136c8  lea     rcx, WPP_8ba27d42bb8b3f236fd12e8dd774299f_Traceguids
0x1401136cf  xor     edi, edi
0x1401136d1  xorps   xmm0, xmm0
0x1401136d4  xor     eax, eax
0x1401136d6  mov     [rbp+4Fh+SecurityDescriptor], rdi
0x1401136da  mov     [rbp+4Fh+var_60], rax
0x1401136de  mov     r15b, r9b
0x1401136e1  mov     [rbp+4Fh+Ace], rdi
0x1401136e5  mov     sil, r8b
0x1401136e8  mov     [rbp+4Fh+Sid], rdi
0x1401136ec  mov     r14d, edi
0x1401136ef  mov     [rbp+4Fh+P], rdi
0x1401136f3  mov     r13b, dil
0x1401136f6  mov     [rbp+4Fh+var_A8], rdi
0x1401136fa  mov     byte ptr [rbp+4Fh+DaclPresent], dil
0x1401136fe  mov     [rbp+4Fh+Dacl], rdi
0x140113702  mov     [rbp+4Fh+DaclDefaulted], dil
0x140113706  movups  [rbp+4Fh+var_80], xmm0
0x14011370a  movups  [rbp+4Fh+var_70], xmm0
0x14011370e  movups  xmmword ptr [rbp+4Fh+SubjectContext.ClientToken], xmm0
0x140113712  movups  xmmword ptr [rbp+4Fh+SubjectContext.PrimaryToken], xmm0
0x140113716  movups  xmmword ptr [rbp+4Fh+DestinationString.Length], xmm0
0x14011371a  test    r12, r12
0x14011371d  jnz     short loc_140113749
0x14011371f  lea     rax, aSecuritydescri; "SecurityDescriptor != NULL"
0x140113726  mov     [rsp+110h+GenericMapping], rax
0x14011372b  lea     r9d, [rdi+15h]
0x14011372f  mov     qword ptr [rsp+110h+AceListLength], rcx
0x140113734  lea     r8d, [rdi+13h]
0x140113738  mov     rcx, cs:VmsIfrLog
0x14011373f  call    WPP_RECORDER_SF_s
0x140113744  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "SecurityDescriptor != ((void *)0)")
0x140113749  lea     rdx, aDPAGaSyAGaBaDG; "D:P(A;;GA;;;SY)(A;;GA;;;BA)(D;;GA;;;WD)"
0x140113750  lea     rcx, [rbp+4Fh+DestinationString]; DestinationString
0x140113754  call    cs:__imp_RtlInitUnicodeString
0x14011375b  nop     dword ptr [rax+rax+00h]
0x140113760  lea     r8, [rbp+4Fh+SecurityDescriptor]
0x140113764  lea     rcx, [rbp+4Fh+DestinationString]
0x140113768  call    SeSddlSecurityDescriptorFromSDDL
0x14011376d  mov     ebx, eax
0x14011376f  test    eax, eax
0x140113771  jns     short loc_1401137A5
0x140113773  mov     rcx, cs:VmsIfrLog
0x14011377a  mov     r9d, 16h
0x140113780  mov     dword ptr [rsp+110h+GenericMapping], eax
0x140113784  mov     dl, 2
0x140113786  lea     rax, WPP_8ba27d42bb8b3f236fd12e8dd774299f_Traceguids
0x14011378d  mov     qword ptr [rsp+110h+AceListLength], rax
0x140113792  lea     r8d, [r9-2]
0x140113796  call    WPP_RECORDER_SF_d
0x14011379b  mov     edi, 5
0x1401137a0  jmp     loc_140113CAD
0x1401137a5  lea     rcx, [rbp+4Fh+Sid]
0x1401137a9  call    VmsOmGetCallerSid
0x1401137ae  mov     ebx, eax
0x1401137b0  test    eax, eax
0x1401137b2  jns     short loc_1401137BE
0x1401137b4  mov     edi, 0Ah
0x1401137b9  jmp     loc_140113CAD
0x1401137be  test    sil, sil
0x1401137c1  jz      short loc_1401137DC
0x1401137c3  lea     rcx, [rbp+4Fh+P]
0x1401137c7  call    VmsOmGetVmGroupSid
0x1401137cc  mov     ebx, eax
0x1401137ce  test    eax, eax
0x1401137d0  jns     short loc_1401137DC
0x1401137d2  mov     edi, 0Fh
0x1401137d7  jmp     loc_140113CAD
0x1401137dc  test    r15b, r15b
0x1401137df  jz      short loc_1401137FA
0x1401137e1  lea     rcx, [rbp+4Fh+var_A8]
0x1401137e5  call    VmsOmGetVmCapabilitySid
0x1401137ea  mov     ebx, eax
0x1401137ec  test    eax, eax
0x1401137ee  jns     short loc_1401137FA
0x1401137f0  mov     edi, 10h
0x1401137f5  jmp     loc_140113CAD
0x1401137fa  mov     rcx, [rbp+4Fh+SecurityDescriptor]; SecurityDescriptor
0x1401137fe  lea     r9, [rbp+4Fh+DaclDefaulted]; DaclDefaulted
0x140113802  lea     r8, [rbp+4Fh+Dacl]; Dacl
0x140113806  lea     rdx, [rbp+4Fh+DaclPresent]; DaclPresent
0x14011380a  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x140113811  nop     dword ptr [rax+rax+00h]
0x140113816  mov     ebx, eax
0x140113818  test    eax, eax
0x14011381a  jns     short loc_14011384C
0x14011381c  mov     rcx, cs:VmsIfrLog
0x140113823  mov     r9d, 17h
0x140113829  mov     dword ptr [rsp+110h+GenericMapping], eax
0x14011382d  mov     dl, 2
0x14011382f  lea     rax, WPP_8ba27d42bb8b3f236fd12e8dd774299f_Traceguids
0x140113836  mov     qword ptr [rsp+110h+AceListLength], rax
0x14011383b  lea     edi, [r9-3]
0x14011383f  mov     r8d, edi
0x140113842  call    WPP_RECORDER_SF_d
0x140113847  jmp     loc_140113CAD
0x14011384c  mov     rcx, [rbp+4Fh+Sid]; Sid
0x140113850  call    cs:__imp_RtlValidSid
0x140113857  nop     dword ptr [rax+rax+00h]
0x14011385c  test    al, al
0x14011385e  jnz     short loc_1401138A7
0x140113860  mov     rcx, cs:VmsIfrLog
0x140113867  lea     rax, aRtlvalidsidCal; "RtlValidSid(callerSID)"
0x14011386e  mov     [rsp+110h+GenericMapping], rax
0x140113873  mov     r9d, 18h
0x140113879  lea     rax, WPP_8ba27d42bb8b3f236fd12e8dd774299f_Traceguids
0x140113880  mov     qword ptr [rsp+110h+AceListLength], rax
0x140113885  lea     r8d, [r9-5]
0x140113889  call    WPP_RECORDER_SF_s
0x14011388e  mov     rcx, [rbp+4Fh+Sid]; Sid
0x140113892  call    cs:__imp_RtlValidSid
0x140113899  nop     dword ptr [rax+rax+00h]
0x14011389e  test    al, al
0x1401138a0  jnz     short loc_1401138A7
0x1401138a2  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "RtlValidSid(callerSID)")
0x1401138a7  mov     rax, [rbp+4Fh+Dacl]
0x1401138ab  mov     rcx, [rbp+4Fh+Sid]; Sid
0x1401138af  movzx   edi, word ptr [rax+2]
0x1401138b3  call    cs:__imp_RtlLengthSid
0x1401138ba  nop     dword ptr [rax+rax+00h]
0x1401138bf  mov     rcx, [rbp+4Fh+P]; Sid
0x1401138c3  add     edi, 8
0x1401138c6  add     edi, eax
0x1401138c8  test    rcx, rcx
0x1401138cb  jz      short loc_1401138DE
0x1401138cd  call    cs:__imp_RtlLengthSid
0x1401138d4  nop     dword ptr [rax+rax+00h]
0x1401138d9  add     edi, 8
0x1401138dc  add     edi, eax
0x1401138de  mov     rcx, [rbp+4Fh+var_A8]; Sid
0x1401138e2  test    rcx, rcx
0x1401138e5  jz      short loc_1401138F8
0x1401138e7  call    cs:__imp_RtlLengthSid
0x1401138ee  nop     dword ptr [rax+rax+00h]
0x1401138f3  add     eax, 8
0x1401138f6  add     edi, eax
0x1401138f8  mov     edx, edi
0x1401138fa  mov     ecx, 40h ; '@'
0x1401138ff  mov     r8d, 624F7356h
0x140113905  call    cs:__imp_ExAllocatePool2
0x14011390c  nop     dword ptr [rax+rax+00h]
0x140113911  mov     r14, rax
0x140113914  test    rax, rax
0x140113917  jnz     short loc_140113954
0x140113919  mov     eax, 0C000009Ah
0x14011391e  mov     ebx, eax
0x140113920  mov     rcx, cs:VmsIfrLog
0x140113927  lea     esi, [r14+19h]
0x14011392b  mov     [rsp+110h+PoolType], eax
0x14011392f  lea     r8d, [r14+14h]
0x140113933  lea     rax, WPP_8ba27d42bb8b3f236fd12e8dd774299f_Traceguids
0x14011393a  mov     dword ptr [rsp+110h+GenericMapping], edi
0x14011393e  mov     r9d, esi
0x140113941  mov     qword ptr [rsp+110h+AceListLength], rax
0x140113946  mov     dl, 2
0x140113948  call    WPP_RECORDER_SF_ld
0x14011394d  mov     edi, esi
0x14011394f  jmp     loc_140113CAD
0x140113954  mov     r8d, 2; AclRevision
0x14011395a  mov     edx, edi; AclLength
0x14011395c  mov     rcx, r14; Acl
0x14011395f  call    cs:__imp_RtlCreateAcl
0x140113966  nop     dword ptr [rax+rax+00h]
0x14011396b  mov     ebx, eax
0x14011396d  test    eax, eax
0x14011396f  jns     short loc_1401139A3
0x140113971  mov     rcx, cs:VmsIfrLog
0x140113978  mov     r9d, 1Ah
0x14011397e  mov     dword ptr [rsp+110h+GenericMapping], eax
0x140113982  mov     dl, 2
0x140113984  lea     rax, WPP_8ba27d42bb8b3f236fd12e8dd774299f_Traceguids
0x14011398b  mov     qword ptr [rsp+110h+AceListLength], rax
0x140113990  lea     r8d, [r9-6]
0x140113994  call    WPP_RECORDER_SF_d
0x140113999  mov     edi, 1Eh
0x14011399e  jmp     loc_140113CAD
0x1401139a3  mov     r9, [rbp+4Fh+Sid]; Sid
0x1401139a7  mov     edi, 10000000h
0x1401139ac  mov     r8d, edi; AccessMask
0x1401139af  mov     edx, 2; AceRevision
0x1401139b4  mov     rcx, r14; Acl
0x1401139b7  call    cs:__imp_RtlAddAccessAllowedAce
0x1401139be  nop     dword ptr [rax+rax+00h]
0x1401139c3  mov     ebx, eax
0x1401139c5  test    eax, eax
0x1401139c7  jns     short loc_1401139FB
0x1401139c9  mov     rcx, cs:VmsIfrLog
0x1401139d0  mov     r9d, 1Bh
0x1401139d6  mov     dword ptr [rsp+110h+GenericMapping], eax
0x1401139da  mov     dl, 2
0x1401139dc  lea     rax, WPP_8ba27d42bb8b3f236fd12e8dd774299f_Traceguids
0x1401139e3  mov     qword ptr [rsp+110h+AceListLength], rax
0x1401139e8  lea     r8d, [r9-7]
0x1401139ec  call    WPP_RECORDER_SF_d
0x1401139f1  mov     edi, 23h ; '#'
0x1401139f6  jmp     loc_140113CAD
0x1401139fb  test    sil, sil
0x1401139fe  jz      short loc_140113A53
0x140113a00  mov     r9, [rbp+4Fh+P]; Sid
0x140113a04  mov     r8d, edi; AccessMask
0x140113a07  mov     edx, 2; AceRevision
0x140113a0c  mov     rcx, r14; Acl
0x140113a0f  call    cs:__imp_RtlAddAccessAllowedAce
0x140113a16  nop     dword ptr [rax+rax+00h]
0x140113a1b  mov     ebx, eax
0x140113a1d  test    eax, eax
0x140113a1f  jns     short loc_140113A53
0x140113a21  mov     rcx, cs:VmsIfrLog
0x140113a28  mov     r9d, 1Ch
0x140113a2e  mov     dword ptr [rsp+110h+GenericMapping], eax
0x140113a32  mov     dl, 2
0x140113a34  lea     rax, WPP_8ba27d42bb8b3f236fd12e8dd774299f_Traceguids
0x140113a3b  mov     qword ptr [rsp+110h+AceListLength], rax
0x140113a40  lea     r8d, [r9-8]
0x140113a44  call    WPP_RECORDER_SF_d
0x140113a49  mov     edi, 24h ; '$'
0x140113a4e  jmp     loc_140113CAD
0x140113a53  test    r15b, r15b
0x140113a56  jz      short loc_140113AAB
0x140113a58  mov     r9, [rbp+4Fh+var_A8]; Sid
0x140113a5c  mov     r8d, edi; AccessMask
0x140113a5f  mov     edx, 2; AceRevision
0x140113a64  mov     rcx, r14; Acl
0x140113a67  call    cs:__imp_RtlAddAccessAllowedAce
0x140113a6e  nop     dword ptr [rax+rax+00h]
0x140113a73  mov     ebx, eax
0x140113a75  test    eax, eax
0x140113a77  jns     short loc_140113AAB
0x140113a79  mov     rcx, cs:VmsIfrLog
0x140113a80  mov     r9d, 1Dh
0x140113a86  mov     dword ptr [rsp+110h+GenericMapping], eax
0x140113a8a  mov     dl, 2
0x140113a8c  lea     rax, WPP_8ba27d42bb8b3f236fd12e8dd774299f_Traceguids
0x140113a93  mov     qword ptr [rsp+110h+AceListLength], rax
0x140113a98  lea     r8d, [r9-9]
0x140113a9c  call    WPP_RECORDER_SF_d
0x140113aa1  mov     edi, 28h ; '('
0x140113aa6  jmp     loc_140113CAD
0x140113aab  xor     esi, esi
0x140113aad  lea     edi, [rsi+1]
0x140113ab0  mov     rcx, [rbp+4Fh+Dacl]; Acl
0x140113ab4  movzx   eax, word ptr [rcx+4]
0x140113ab8  cmp     esi, eax
0x140113aba  jnb     loc_140113B73
0x140113ac0  lea     r8, [rbp+4Fh+Ace]; Ace
0x140113ac4  mov     edx, esi; AceIndex
0x140113ac6  call    cs:__imp_RtlGetAce
0x140113acd  nop     dword ptr [rax+rax+00h]
0x140113ad2  mov     ebx, eax
0x140113ad4  test    eax, eax
0x140113ad6  js      short loc_140113B3D
0x140113ad8  mov     r9, [rbp+4Fh+Ace]; AceList
0x140113adc  or      r8d, 0FFFFFFFFh; StartingAceIndex
0x140113ae0  mov     edx, 2; AceRevision
0x140113ae5  mov     rcx, r14; Acl
0x140113ae8  movzx   eax, word ptr [r9+2]
0x140113aed  mov     [rsp+110h+AceListLength], eax; AceListLength
0x140113af1  call    cs:__imp_RtlAddAce
0x140113af8  nop     dword ptr [rax+rax+00h]
0x140113afd  mov     ebx, eax
0x140113aff  test    eax, eax
0x140113b01  js      short loc_140113B07
0x140113b03  add     esi, edi
0x140113b05  jmp     short loc_140113AB0
0x140113b07  mov     rcx, cs:VmsIfrLog
0x140113b0e  mov     r9d, 1Fh
0x140113b14  mov     [rsp+110h+PoolType], eax
0x140113b18  mov     dl, 2
0x140113b1a  lea     rax, WPP_8ba27d42bb8b3f236fd12e8dd774299f_Traceguids
0x140113b21  mov     dword ptr [rsp+110h+GenericMapping], esi
0x140113b25  mov     qword ptr [rsp+110h+AceListLength], rax
0x140113b2a  lea     r8d, [r9-0Bh]
0x140113b2e  call    WPP_RECORDER_SF_ld
0x140113b33  mov     edi, 32h ; '2'
0x140113b38  jmp     loc_140113CAD
0x140113b3d  mov     rcx, cs:VmsIfrLog
0x140113b44  mov     r9d, 1Eh
0x140113b4a  mov     [rsp+110h+PoolType], eax
0x140113b4e  mov     dl, 2
0x140113b50  lea     rax, WPP_8ba27d42bb8b3f236fd12e8dd774299f_Traceguids
0x140113b57  mov     dword ptr [rsp+110h+GenericMapping], esi
0x140113b5b  mov     qword ptr [rsp+110h+AceListLength], rax
0x140113b60  lea     r8d, [r9-0Ah]
0x140113b64  call    WPP_RECORDER_SF_ld
0x140113b69  mov     edi, 2Dh ; '-'
0x140113b6e  jmp     loc_140113CAD
  ... truncated ...
```
