# VmsOmNonGenericSecurityDescriptorFromSddlString

- ea: `0x140113630`
- end: `0x140113d07`
- name: `VmsOmNonGenericSecurityDescriptorFromSddlString`
- size: `1751`
- prototype: `__int64 __fastcall(int, int, int, int, PSECURITY_DESCRIPTOR *NewDescriptor)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14010d770`

## callees

- `0x140027a64`
- `0x14002e0f0`
- `0x14003a450`
- `0x14008497c`
- `0x1401130cc`
- `0x140113308`
- `0x1401134b4`
- `0x140113630`
- `0x140113d10`
- `0x140237be4`

## import_xrefs

- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x14011379a`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x14011379a`
- `ntoskrnl!RtlValidSid` at `0x1401137e0`
- `ntoskrnl!RtlValidSid` at `0x140113822`
- `ntoskrnl!RtlValidSid` at `0x1401137e0`
- `ntoskrnl!RtlValidSid` at `0x140113822`
- `ntoskrnl!RtlCreateAcl` at `0x1401138ef`
- `ntoskrnl!RtlCreateAcl` at `0x1401138ef`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140113947`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14011399f`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1401139f7`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140113947`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14011399f`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1401139f7`
- `ntoskrnl!RtlGetAce` at `0x140113a56`
- `ntoskrnl!RtlGetAce` at `0x140113a56`
- `ntoskrnl!RtlAddAce` at `0x140113a81`
- `ntoskrnl!RtlAddAce` at `0x140113a81`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140113b09`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140113b09`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140113b5f`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140113b5f`
- `ntoskrnl!SeAssignSecurity` at `0x140113bfa`
- `ntoskrnl!SeAssignSecurity` at `0x140113bfa`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140113c67`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140113c67`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140113bd0`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140113bd0`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140113bc1`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140113bc1`
- `ntoskrnl!RtlLengthSid` at `0x140113843`
- `ntoskrnl!RtlLengthSid` at `0x14011385d`
- `ntoskrnl!RtlLengthSid` at `0x140113877`
- `ntoskrnl!RtlLengthSid` at `0x140113843`
- `ntoskrnl!RtlLengthSid` at `0x14011385d`
- `ntoskrnl!RtlLengthSid` at `0x140113877`
- `ntoskrnl!ExFreePoolWithTag` at `0x140113ba9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140113c51`
- `ntoskrnl!ExFreePoolWithTag` at `0x140113c82`
- `ntoskrnl!ExFreePoolWithTag` at `0x140113c99`
- `ntoskrnl!ExFreePoolWithTag` at `0x140113cb0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140113cc7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140113ba9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140113c51`
- `ntoskrnl!ExFreePoolWithTag` at `0x140113c82`
- `ntoskrnl!ExFreePoolWithTag` at `0x140113c99`
- `ntoskrnl!ExFreePoolWithTag` at `0x140113cb0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140113cc7`
- `ntoskrnl!ExAllocatePool2` at `0x140113895`
- `ntoskrnl!ExAllocatePool2` at `0x140113895`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401136e4`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401136e4`

## string_xrefs

- `0x1401136af`: `SecurityDescriptor != NULL`
- `0x1401137f7`: `RtlValidSid(callerSID)`

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
0x140113630  mov     rax, rsp
0x140113633  mov     [rax+18h], rbx
0x140113637  mov     [rax+10h], dl
0x14011363a  mov     [rax+8], rcx
0x14011363e  push    rbp
0x14011363f  push    rsi
0x140113640  push    rdi
0x140113641  push    r12
0x140113643  push    r13
0x140113645  push    r14
0x140113647  push    r15
0x140113649  lea     rbp, [rax-57h]
0x14011364d  sub     rsp, 0E0h
0x140113654  mov     r12, [rbp+4Fh+NewDescriptor]
0x140113658  lea     rcx, WPP_8ba27d42bb8b3f236fd12e8dd774299f_Traceguids
0x14011365f  xor     edi, edi
0x140113661  xorps   xmm0, xmm0
0x140113664  xor     eax, eax
0x140113666  mov     [rbp+4Fh+SecurityDescriptor], rdi
0x14011366a  mov     [rbp+4Fh+var_60], rax
0x14011366e  mov     r15b, r9b
0x140113671  mov     [rbp+4Fh+Ace], rdi
0x140113675  mov     sil, r8b
0x140113678  mov     [rbp+4Fh+Sid], rdi
0x14011367c  mov     r14d, edi
0x14011367f  mov     [rbp+4Fh+P], rdi
0x140113683  mov     r13b, dil
0x140113686  mov     [rbp+4Fh+var_A8], rdi
0x14011368a  mov     byte ptr [rbp+4Fh+DaclPresent], dil
0x14011368e  mov     [rbp+4Fh+Dacl], rdi
0x140113692  mov     [rbp+4Fh+DaclDefaulted], dil
0x140113696  movups  [rbp+4Fh+var_80], xmm0
0x14011369a  movups  [rbp+4Fh+var_70], xmm0
0x14011369e  movups  xmmword ptr [rbp+4Fh+SubjectContext.ClientToken], xmm0
0x1401136a2  movups  xmmword ptr [rbp+4Fh+SubjectContext.PrimaryToken], xmm0
0x1401136a6  movups  xmmword ptr [rbp+4Fh+DestinationString.Length], xmm0
0x1401136aa  test    r12, r12
0x1401136ad  jnz     short loc_1401136D9
0x1401136af  lea     rax, aSecuritydescri; "SecurityDescriptor != NULL"
0x1401136b6  mov     [rsp+110h+GenericMapping], rax
0x1401136bb  lea     r9d, [rdi+15h]
0x1401136bf  mov     qword ptr [rsp+110h+AceListLength], rcx
0x1401136c4  lea     r8d, [rdi+13h]
0x1401136c8  mov     rcx, cs:VmsIfrLog
0x1401136cf  call    WPP_RECORDER_SF_s
0x1401136d4  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "SecurityDescriptor != ((void *)0)")
0x1401136d9  lea     rdx, aDPAGaSyAGaBaDG; "D:P(A;;GA;;;SY)(A;;GA;;;BA)(D;;GA;;;WD)"
0x1401136e0  lea     rcx, [rbp+4Fh+DestinationString]; DestinationString
0x1401136e4  call    cs:__imp_RtlInitUnicodeString
0x1401136eb  nop     dword ptr [rax+rax+00h]
0x1401136f0  lea     r8, [rbp+4Fh+SecurityDescriptor]
0x1401136f4  lea     rcx, [rbp+4Fh+DestinationString]
0x1401136f8  call    SeSddlSecurityDescriptorFromSDDL
0x1401136fd  mov     ebx, eax
0x1401136ff  test    eax, eax
0x140113701  jns     short loc_140113735
0x140113703  mov     rcx, cs:VmsIfrLog
0x14011370a  mov     r9d, 16h
0x140113710  mov     dword ptr [rsp+110h+GenericMapping], eax
0x140113714  mov     dl, 2
0x140113716  lea     rax, WPP_8ba27d42bb8b3f236fd12e8dd774299f_Traceguids
0x14011371d  mov     qword ptr [rsp+110h+AceListLength], rax
0x140113722  lea     r8d, [r9-2]
0x140113726  call    WPP_RECORDER_SF_d
0x14011372b  mov     edi, 5
0x140113730  jmp     loc_140113C3D
0x140113735  lea     rcx, [rbp+4Fh+Sid]
0x140113739  call    VmsOmGetCallerSid
0x14011373e  mov     ebx, eax
0x140113740  test    eax, eax
0x140113742  jns     short loc_14011374E
0x140113744  mov     edi, 0Ah
0x140113749  jmp     loc_140113C3D
0x14011374e  test    sil, sil
0x140113751  jz      short loc_14011376C
0x140113753  lea     rcx, [rbp+4Fh+P]
0x140113757  call    VmsOmGetVmGroupSid
0x14011375c  mov     ebx, eax
0x14011375e  test    eax, eax
0x140113760  jns     short loc_14011376C
0x140113762  mov     edi, 0Fh
0x140113767  jmp     loc_140113C3D
0x14011376c  test    r15b, r15b
0x14011376f  jz      short loc_14011378A
0x140113771  lea     rcx, [rbp+4Fh+var_A8]
0x140113775  call    VmsOmGetVmCapabilitySid
0x14011377a  mov     ebx, eax
0x14011377c  test    eax, eax
0x14011377e  jns     short loc_14011378A
0x140113780  mov     edi, 10h
0x140113785  jmp     loc_140113C3D
0x14011378a  mov     rcx, [rbp+4Fh+SecurityDescriptor]; SecurityDescriptor
0x14011378e  lea     r9, [rbp+4Fh+DaclDefaulted]; DaclDefaulted
0x140113792  lea     r8, [rbp+4Fh+Dacl]; Dacl
0x140113796  lea     rdx, [rbp+4Fh+DaclPresent]; DaclPresent
0x14011379a  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x1401137a1  nop     dword ptr [rax+rax+00h]
0x1401137a6  mov     ebx, eax
0x1401137a8  test    eax, eax
0x1401137aa  jns     short loc_1401137DC
0x1401137ac  mov     rcx, cs:VmsIfrLog
0x1401137b3  mov     r9d, 17h
0x1401137b9  mov     dword ptr [rsp+110h+GenericMapping], eax
0x1401137bd  mov     dl, 2
0x1401137bf  lea     rax, WPP_8ba27d42bb8b3f236fd12e8dd774299f_Traceguids
0x1401137c6  mov     qword ptr [rsp+110h+AceListLength], rax
0x1401137cb  lea     edi, [r9-3]
0x1401137cf  mov     r8d, edi
0x1401137d2  call    WPP_RECORDER_SF_d
0x1401137d7  jmp     loc_140113C3D
0x1401137dc  mov     rcx, [rbp+4Fh+Sid]; Sid
0x1401137e0  call    cs:__imp_RtlValidSid
0x1401137e7  nop     dword ptr [rax+rax+00h]
0x1401137ec  test    al, al
0x1401137ee  jnz     short loc_140113837
0x1401137f0  mov     rcx, cs:VmsIfrLog
0x1401137f7  lea     rax, aRtlvalidsidCal; "RtlValidSid(callerSID)"
0x1401137fe  mov     [rsp+110h+GenericMapping], rax
0x140113803  mov     r9d, 18h
0x140113809  lea     rax, WPP_8ba27d42bb8b3f236fd12e8dd774299f_Traceguids
0x140113810  mov     qword ptr [rsp+110h+AceListLength], rax
0x140113815  lea     r8d, [r9-5]
0x140113819  call    WPP_RECORDER_SF_s
0x14011381e  mov     rcx, [rbp+4Fh+Sid]; Sid
0x140113822  call    cs:__imp_RtlValidSid
0x140113829  nop     dword ptr [rax+rax+00h]
0x14011382e  test    al, al
0x140113830  jnz     short loc_140113837
0x140113832  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "RtlValidSid(callerSID)")
0x140113837  mov     rax, [rbp+4Fh+Dacl]
0x14011383b  mov     rcx, [rbp+4Fh+Sid]; Sid
0x14011383f  movzx   edi, word ptr [rax+2]
0x140113843  call    cs:__imp_RtlLengthSid
0x14011384a  nop     dword ptr [rax+rax+00h]
0x14011384f  mov     rcx, [rbp+4Fh+P]; Sid
0x140113853  add     edi, 8
0x140113856  add     edi, eax
0x140113858  test    rcx, rcx
0x14011385b  jz      short loc_14011386E
0x14011385d  call    cs:__imp_RtlLengthSid
0x140113864  nop     dword ptr [rax+rax+00h]
0x140113869  add     edi, 8
0x14011386c  add     edi, eax
0x14011386e  mov     rcx, [rbp+4Fh+var_A8]; Sid
0x140113872  test    rcx, rcx
0x140113875  jz      short loc_140113888
0x140113877  call    cs:__imp_RtlLengthSid
0x14011387e  nop     dword ptr [rax+rax+00h]
0x140113883  add     eax, 8
0x140113886  add     edi, eax
0x140113888  mov     edx, edi
0x14011388a  mov     ecx, 40h ; '@'
0x14011388f  mov     r8d, 624F7356h
0x140113895  call    cs:__imp_ExAllocatePool2
0x14011389c  nop     dword ptr [rax+rax+00h]
0x1401138a1  mov     r14, rax
0x1401138a4  test    rax, rax
0x1401138a7  jnz     short loc_1401138E4
0x1401138a9  mov     eax, 0C000009Ah
0x1401138ae  mov     ebx, eax
0x1401138b0  mov     rcx, cs:VmsIfrLog
0x1401138b7  lea     esi, [r14+19h]
0x1401138bb  mov     [rsp+110h+PoolType], eax
0x1401138bf  lea     r8d, [r14+14h]
0x1401138c3  lea     rax, WPP_8ba27d42bb8b3f236fd12e8dd774299f_Traceguids
0x1401138ca  mov     dword ptr [rsp+110h+GenericMapping], edi
0x1401138ce  mov     r9d, esi
0x1401138d1  mov     qword ptr [rsp+110h+AceListLength], rax
0x1401138d6  mov     dl, 2
0x1401138d8  call    WPP_RECORDER_SF_ld
0x1401138dd  mov     edi, esi
0x1401138df  jmp     loc_140113C3D
0x1401138e4  mov     r8d, 2; AclRevision
0x1401138ea  mov     edx, edi; AclLength
0x1401138ec  mov     rcx, r14; Acl
0x1401138ef  call    cs:__imp_RtlCreateAcl
0x1401138f6  nop     dword ptr [rax+rax+00h]
0x1401138fb  mov     ebx, eax
0x1401138fd  test    eax, eax
0x1401138ff  jns     short loc_140113933
0x140113901  mov     rcx, cs:VmsIfrLog
0x140113908  mov     r9d, 1Ah
0x14011390e  mov     dword ptr [rsp+110h+GenericMapping], eax
0x140113912  mov     dl, 2
0x140113914  lea     rax, WPP_8ba27d42bb8b3f236fd12e8dd774299f_Traceguids
0x14011391b  mov     qword ptr [rsp+110h+AceListLength], rax
0x140113920  lea     r8d, [r9-6]
0x140113924  call    WPP_RECORDER_SF_d
0x140113929  mov     edi, 1Eh
0x14011392e  jmp     loc_140113C3D
0x140113933  mov     r9, [rbp+4Fh+Sid]; Sid
0x140113937  mov     edi, 10000000h
0x14011393c  mov     r8d, edi; AccessMask
0x14011393f  mov     edx, 2; AceRevision
0x140113944  mov     rcx, r14; Acl
0x140113947  call    cs:__imp_RtlAddAccessAllowedAce
0x14011394e  nop     dword ptr [rax+rax+00h]
0x140113953  mov     ebx, eax
0x140113955  test    eax, eax
0x140113957  jns     short loc_14011398B
0x140113959  mov     rcx, cs:VmsIfrLog
0x140113960  mov     r9d, 1Bh
0x140113966  mov     dword ptr [rsp+110h+GenericMapping], eax
0x14011396a  mov     dl, 2
0x14011396c  lea     rax, WPP_8ba27d42bb8b3f236fd12e8dd774299f_Traceguids
0x140113973  mov     qword ptr [rsp+110h+AceListLength], rax
0x140113978  lea     r8d, [r9-7]
0x14011397c  call    WPP_RECORDER_SF_d
0x140113981  mov     edi, 23h ; '#'
0x140113986  jmp     loc_140113C3D
0x14011398b  test    sil, sil
0x14011398e  jz      short loc_1401139E3
0x140113990  mov     r9, [rbp+4Fh+P]; Sid
0x140113994  mov     r8d, edi; AccessMask
0x140113997  mov     edx, 2; AceRevision
0x14011399c  mov     rcx, r14; Acl
0x14011399f  call    cs:__imp_RtlAddAccessAllowedAce
0x1401139a6  nop     dword ptr [rax+rax+00h]
0x1401139ab  mov     ebx, eax
0x1401139ad  test    eax, eax
0x1401139af  jns     short loc_1401139E3
0x1401139b1  mov     rcx, cs:VmsIfrLog
0x1401139b8  mov     r9d, 1Ch
0x1401139be  mov     dword ptr [rsp+110h+GenericMapping], eax
0x1401139c2  mov     dl, 2
0x1401139c4  lea     rax, WPP_8ba27d42bb8b3f236fd12e8dd774299f_Traceguids
0x1401139cb  mov     qword ptr [rsp+110h+AceListLength], rax
0x1401139d0  lea     r8d, [r9-8]
0x1401139d4  call    WPP_RECORDER_SF_d
0x1401139d9  mov     edi, 24h ; '$'
0x1401139de  jmp     loc_140113C3D
0x1401139e3  test    r15b, r15b
0x1401139e6  jz      short loc_140113A3B
0x1401139e8  mov     r9, [rbp+4Fh+var_A8]; Sid
0x1401139ec  mov     r8d, edi; AccessMask
0x1401139ef  mov     edx, 2; AceRevision
0x1401139f4  mov     rcx, r14; Acl
0x1401139f7  call    cs:__imp_RtlAddAccessAllowedAce
0x1401139fe  nop     dword ptr [rax+rax+00h]
0x140113a03  mov     ebx, eax
0x140113a05  test    eax, eax
0x140113a07  jns     short loc_140113A3B
0x140113a09  mov     rcx, cs:VmsIfrLog
0x140113a10  mov     r9d, 1Dh
0x140113a16  mov     dword ptr [rsp+110h+GenericMapping], eax
0x140113a1a  mov     dl, 2
0x140113a1c  lea     rax, WPP_8ba27d42bb8b3f236fd12e8dd774299f_Traceguids
0x140113a23  mov     qword ptr [rsp+110h+AceListLength], rax
0x140113a28  lea     r8d, [r9-9]
0x140113a2c  call    WPP_RECORDER_SF_d
0x140113a31  mov     edi, 28h ; '('
0x140113a36  jmp     loc_140113C3D
0x140113a3b  xor     esi, esi
0x140113a3d  lea     edi, [rsi+1]
0x140113a40  mov     rcx, [rbp+4Fh+Dacl]; Acl
0x140113a44  movzx   eax, word ptr [rcx+4]
0x140113a48  cmp     esi, eax
0x140113a4a  jnb     loc_140113B03
0x140113a50  lea     r8, [rbp+4Fh+Ace]; Ace
0x140113a54  mov     edx, esi; AceIndex
0x140113a56  call    cs:__imp_RtlGetAce
0x140113a5d  nop     dword ptr [rax+rax+00h]
0x140113a62  mov     ebx, eax
0x140113a64  test    eax, eax
0x140113a66  js      short loc_140113ACD
0x140113a68  mov     r9, [rbp+4Fh+Ace]; AceList
0x140113a6c  or      r8d, 0FFFFFFFFh; StartingAceIndex
0x140113a70  mov     edx, 2; AceRevision
0x140113a75  mov     rcx, r14; Acl
0x140113a78  movzx   eax, word ptr [r9+2]
0x140113a7d  mov     [rsp+110h+AceListLength], eax; AceListLength
0x140113a81  call    cs:__imp_RtlAddAce
0x140113a88  nop     dword ptr [rax+rax+00h]
0x140113a8d  mov     ebx, eax
0x140113a8f  test    eax, eax
0x140113a91  js      short loc_140113A97
0x140113a93  add     esi, edi
0x140113a95  jmp     short loc_140113A40
0x140113a97  mov     rcx, cs:VmsIfrLog
0x140113a9e  mov     r9d, 1Fh
0x140113aa4  mov     [rsp+110h+PoolType], eax
0x140113aa8  mov     dl, 2
0x140113aaa  lea     rax, WPP_8ba27d42bb8b3f236fd12e8dd774299f_Traceguids
0x140113ab1  mov     dword ptr [rsp+110h+GenericMapping], esi
0x140113ab5  mov     qword ptr [rsp+110h+AceListLength], rax
0x140113aba  lea     r8d, [r9-0Bh]
0x140113abe  call    WPP_RECORDER_SF_ld
0x140113ac3  mov     edi, 32h ; '2'
0x140113ac8  jmp     loc_140113C3D
0x140113acd  mov     rcx, cs:VmsIfrLog
0x140113ad4  mov     r9d, 1Eh
0x140113ada  mov     [rsp+110h+PoolType], eax
0x140113ade  mov     dl, 2
0x140113ae0  lea     rax, WPP_8ba27d42bb8b3f236fd12e8dd774299f_Traceguids
0x140113ae7  mov     dword ptr [rsp+110h+GenericMapping], esi
0x140113aeb  mov     qword ptr [rsp+110h+AceListLength], rax
0x140113af0  lea     r8d, [r9-0Ah]
0x140113af4  call    WPP_RECORDER_SF_ld
0x140113af9  mov     edi, 2Dh ; '-'
0x140113afe  jmp     loc_140113C3D
  ... truncated ...
```
