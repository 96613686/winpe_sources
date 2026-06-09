# SrvLibAuditShareAccess

- ea: `0x1400281b0`
- end: `0x1400286aa`
- name: `SrvLibAuditShareAccess`
- size: `1274`
- prototype: `__int64 __usercall@<rax>(PVOID Data@<rcx>, PVOID@<rdx>, int, int, __int64, __int64, int)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x140007360`
- `0x140007c60`
- `0x1400281b0`
- `0x14002a3e0`
- `0x14002a540`
- `0x14002a840`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140028253`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002826b`
- `ntoskrnl!RtlInitUnicodeString` at `0x140028253`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002826b`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x14002850b`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x14002850b`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x1400285ca`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x140028618`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x1400285ca`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x140028618`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1400284f3`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1400284f3`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14002829f`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14002829f`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140028426`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140028426`
- `ntoskrnl!SeQueryAuthenticationIdToken` at `0x1400282c0`
- `ntoskrnl!SeQueryAuthenticationIdToken` at `0x1400282c0`
- `ntoskrnl!SeSetAuditParameter` at `0x1400282e8`
- `ntoskrnl!SeSetAuditParameter` at `0x140028317`
- `ntoskrnl!SeSetAuditParameter` at `0x140028348`
- `ntoskrnl!SeSetAuditParameter` at `0x140028377`
- `ntoskrnl!SeSetAuditParameter` at `0x1400283a3`
- `ntoskrnl!SeSetAuditParameter` at `0x1400283cb`
- `ntoskrnl!SeSetAuditParameter` at `0x1400283f6`
- `ntoskrnl!SeSetAuditParameter` at `0x1400282e8`
- `ntoskrnl!SeSetAuditParameter` at `0x140028317`
- `ntoskrnl!SeSetAuditParameter` at `0x140028348`
- `ntoskrnl!SeSetAuditParameter` at `0x140028377`
- `ntoskrnl!SeSetAuditParameter` at `0x1400283a3`
- `ntoskrnl!SeSetAuditParameter` at `0x1400283cb`
- `ntoskrnl!SeSetAuditParameter` at `0x1400283f6`
- `ntoskrnl!SeReportSecurityEventWithSubCategory` at `0x140028697`
- `ntoskrnl!SeReportSecurityEventWithSubCategory` at `0x140028697`
- `ntoskrnl!ExFreePoolWithTag` at `0x140028452`
- `ntoskrnl!ExFreePoolWithTag` at `0x140028477`
- `ntoskrnl!ExFreePoolWithTag` at `0x140028452`
- `ntoskrnl!ExFreePoolWithTag` at `0x140028477`

## string_xrefs

- `0x14002820f`: `Security`

## pseudocode

```c
__int64 __fastcall SrvLibAuditShareAccess(
        PVOID Data,
        PVOID a2,
        void *a3,
        void *a4,
        unsigned int a5,
        int a6,
        __int64 a7,
        _OWORD *a8,
        int a9)
{
  __int64 v9; // r12
  char *PoolWithTag; // rsi
  unsigned int *v13; // r14
  char v14; // r13
  USHORT v15; // ax
  PACCESS_TOKEN PrimaryToken; // rcx
  NTSTATUS v17; // edi
  ULONG v18; // r8d
  ULONG v19; // r13d
  NTSTATUS v20; // eax
  ULONG v21; // r8d
  ULONG v22; // r8d
  ULONG v23; // r8d
  ULONG v24; // r8d
  __int64 v25; // rax
  ULONG_PTR v27; // rcx
  _OWORD *v28; // rbx
  ULONG v29; // r15d
  int v30; // ecx
  int v31; // eax
  int v32; // eax
  _OWORD *v33; // rax
  NTSTATUS v34; // eax
  unsigned int *v35; // rax
  ULONG BufferLength; // [rsp+34h] [rbp-CCh] BYREF
  struct _LUID AuthenticationId; // [rsp+38h] [rbp-C8h] BYREF
  PVOID v38; // [rsp+40h] [rbp-C0h]
  PVOID v39; // [rsp+48h] [rbp-B8h]
  struct _UNICODE_STRING Dataa; // [rsp+50h] [rbp-B0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-A0h] BYREF
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+70h] [rbp-90h] BYREF
  _OWORD SecurityDescriptor[2]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v44; // [rsp+B0h] [rbp-50h]
  struct _SE_ADT_PARAMETER_ARRAY AuditParameters; // [rsp+C0h] [rbp-40h] BYREF

  v9 = a7;
  v38 = a3;
  v39 = a4;
  DestinationString = 0;
  memset(&AuditParameters, 0, sizeof(AuditParameters));
  AuthenticationId = 0;
  BufferLength = 0;
  v44 = 0;
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  PoolWithTag = 0;
  v13 = 0;
  v14 = 0;
  Dataa = 0;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  RtlInitUnicodeString(&DestinationString, L"Security");
  RtlInitUnicodeString(&Dataa, L"File");
  v15 = 8;
  AuditParameters.AuditId = 5145;
  AuditParameters.CategoryId = 3;
  if ( a9 < 0 )
    v15 = 16;
  AuditParameters.Type = v15;
  AuditParameters.ParameterCount = 0;
  SeCaptureSubjectContext(&SubjectContext);
  PrimaryToken = SubjectContext.PrimaryToken;
  if ( SubjectContext.ClientToken )
    PrimaryToken = SubjectContext.ClientToken;
  v17 = SeQueryAuthenticationIdToken(PrimaryToken, &AuthenticationId);
  if ( v17 >= 0 )
  {
    v17 = SeSetAuditParameter(&AuditParameters, SeAdtParmTypeLogonId, AuditParameters.ParameterCount, &AuthenticationId);
    v18 = ++AuditParameters.ParameterCount;
    if ( v17 >= 0 )
    {
      v17 = SeSetAuditParameter(&AuditParameters, SeAdtParmTypeString, v18, &Dataa);
      if ( v17 >= 0 )
      {
        v19 = AuditParameters.ParameterCount + 2;
        v20 = SeSetAuditParameter(&AuditParameters, SeAdtParmTypeSockAddr, ++AuditParameters.ParameterCount, a2);
        v21 = AuditParameters.ParameterCount + 1;
        v17 = v20;
        ++AuditParameters.ParameterCount;
        if ( v20 < 0 )
          goto LABEL_15;
        v17 = SeSetAuditParameter(&AuditParameters, SeAdtParmTypeString, v21, Data);
        v22 = ++AuditParameters.ParameterCount;
        if ( v17 < 0 )
          goto LABEL_15;
        v17 = SeSetAuditParameter(&AuditParameters, SeAdtParmTypeString, v22, v38);
        v23 = ++AuditParameters.ParameterCount;
        if ( v17 < 0 )
          goto LABEL_15;
        v17 = SeSetAuditParameter(&AuditParameters, SeAdtParmTypeString, v23, v39);
        v24 = ++AuditParameters.ParameterCount;
        if ( v17 < 0 )
          goto LABEL_15;
        v17 = SeSetAuditParameter(&AuditParameters, SeAdtParmTypeHexUlong, v24, &a5);
        v25 = ++AuditParameters.ParameterCount;
        if ( v17 < 0 )
          goto LABEL_15;
        if ( (unsigned int)v25 >= 0x1F )
        {
          v17 = -2147483643;
LABEL_15:
          v14 = 0;
          goto LABEL_16;
        }
        v27 = a5;
        AuditParameters.Parameters[v25].Type = SeAdtParmTypeAccessMask;
        AuditParameters.Parameters[AuditParameters.ParameterCount].Length = 4;
        AuditParameters.Parameters[AuditParameters.ParameterCount].Data[0] = v27;
        AuditParameters.Parameters[AuditParameters.ParameterCount++].Data[1] = v19;
        if ( v9 )
        {
          v28 = (_OWORD *)v9;
        }
        else
        {
          RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
          v28 = SecurityDescriptor;
        }
        BufferLength = RtlLengthSecurityDescriptor(v28);
        v29 = BufferLength + 144;
        PoolWithTag = (char *)SrvNetAllocatePoolWithTag(256, BufferLength + 144, 1651266380);
        if ( !PoolWithTag )
        {
          v17 = -1073741670;
LABEL_27:
          v14 = 0;
          goto LABEL_16;
        }
        v30 = a9;
        v31 = a9;
        *((_DWORD *)PoolWithTag + 33) = v19;
        *((_DWORD *)PoolWithTag + 34) = v31 >= 0;
        v32 = a5;
        if ( v30 >= 0 )
          v32 = a6;
        *(_DWORD *)PoolWithTag = v32;
        v33 = a8;
        *(_OWORD *)(PoolWithTag + 4) = *a8;
        *(_OWORD *)(PoolWithTag + 20) = v33[1];
        *(_OWORD *)(PoolWithTag + 36) = v33[2];
        *(_OWORD *)(PoolWithTag + 52) = v33[3];
        *(_OWORD *)(PoolWithTag + 68) = v33[4];
        *(_OWORD *)(PoolWithTag + 84) = v33[5];
        *(_OWORD *)(PoolWithTag + 100) = v33[6];
        *(_OWORD *)(PoolWithTag + 116) = v33[7];
        if ( v9 )
        {
          v34 = RtlAbsoluteToSelfRelativeSD(v28, 0, &BufferLength);
          v17 = v34;
          if ( v34 == -1073741789 )
          {
            v35 = (unsigned int *)SrvNetAllocatePoolWithTag(258, BufferLength, 1651266380);
            v13 = v35;
            if ( !v35 )
            {
              v14 = 0;
              v17 = -1073741670;
              goto LABEL_16;
            }
            v14 = 1;
            v17 = RtlAbsoluteToSelfRelativeSD(v28, v35, &BufferLength);
            if ( v17 < 0 )
              goto LABEL_16;
LABEL_38:
            memmove(PoolWithTag + 144, v13, BufferLength);
            AuditParameters.Parameters[AuditParameters.ParameterCount].Type = SeAdtParmTypeAccessReason;
            AuditParameters.Parameters[AuditParameters.ParameterCount].Length = v29;
            AuditParameters.Parameters[AuditParameters.ParameterCount++].Address = PoolWithTag;
            v17 = SeReportSecurityEventWithSubCategory(0, &DestinationString, 0, &AuditParameters, 0x80u);
            goto LABEL_16;
          }
          if ( v34 != -1073741593 )
            goto LABEL_27;
        }
        v14 = 0;
        v13 = (unsigned int *)v28;
        goto LABEL_38;
      }
    }
  }
LABEL_16:
  SeReleaseSubjectContext(&SubjectContext);
  if ( v13 && v14 )
  {
    SrvNetUpdateMemStatistics(*(v13 - 3), *(v13 - 4), 0);
    ExFreePoolWithTag(v13 - 4, 0);
  }
  if ( PoolWithTag )
  {
    SrvNetUpdateMemStatistics(*((unsigned int *)PoolWithTag - 3), *((unsigned int *)PoolWithTag - 4), 0);
    ExFreePoolWithTag(PoolWithTag - 16, 0);
  }
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x1400281b0  push    rbp
0x1400281b2  push    rbx
0x1400281b3  push    rsi
0x1400281b4  push    rdi
0x1400281b5  push    r12
0x1400281b7  push    r13
0x1400281b9  push    r14
0x1400281bb  push    r15
0x1400281bd  lea     rbp, [rsp-3F8h]
0x1400281c5  sub     rsp, 4F8h
0x1400281cc  mov     rax, cs:__security_cookie
0x1400281d3  xor     rax, rsp
0x1400281d6  mov     [rbp+430h+var_50], rax
0x1400281dd  mov     r12, [rbp+430h+arg_30]
0x1400281e4  mov     rbx, rdx
0x1400281e7  mov     [rsp+530h+var_4F0], r8
0x1400281ec  mov     r15, rcx
0x1400281ef  xorps   xmm0, xmm0
0x1400281f2  mov     [rsp+530h+var_4E8], r9
0x1400281f7  xor     edx, edx; Val
0x1400281f9  lea     rcx, [rbp+430h+AuditParameters]; void *
0x1400281fd  mov     r8d, 418h; Size
0x140028203  movups  xmmword ptr [rsp+530h+DestinationString.Length], xmm0
0x140028208  call    memset
0x14002820d  xor     edi, edi
0x14002820f  lea     rdx, SourceString; "Security"
0x140028216  xorps   xmm0, xmm0
0x140028219  mov     qword ptr [rsp+530h+AuthenticationId.LowPart], rdi
0x14002821e  xorps   xmm1, xmm1
0x140028221  mov     [rsp+530h+BufferLength], edi
0x140028225  xor     eax, eax
0x140028227  mov     [rsp+530h+var_500], dil
0x14002822c  lea     rcx, [rsp+530h+DestinationString]; DestinationString
0x140028231  mov     [rbp+430h+var_480], rax
0x140028235  movups  xmmword ptr [rsp+530h+SubjectContext.ClientToken], xmm0
0x14002823a  mov     esi, edi
0x14002823c  mov     r14d, edi
0x14002823f  movups  xmmword ptr [rbp+430h+SubjectContext.PrimaryToken], xmm0
0x140028243  mov     r13b, dil
0x140028246  movups  xmmword ptr [rsp+530h+Data.Length], xmm0
0x14002824b  movups  [rbp+430h+SecurityDescriptor], xmm1
0x14002824f  movups  [rbp+430h+var_490], xmm1
0x140028253  call    cs:__imp_RtlInitUnicodeString
0x14002825a  nop     dword ptr [rax+rax+00h]
0x14002825f  lea     rdx, aFile; "File"
0x140028266  lea     rcx, [rsp+530h+Data]; DestinationString
0x14002826b  call    cs:__imp_RtlInitUnicodeString
0x140028272  nop     dword ptr [rax+rax+00h]
0x140028277  lea     eax, [rdi+8]
0x14002827a  mov     [rbp+430h+AuditParameters.AuditId], 1419h
0x140028281  mov     [rbp+430h+AuditParameters.CategoryId], 3
0x140028288  cmp     [rbp+430h+arg_40], edi
0x14002828e  jge     short loc_140028293
0x140028290  lea     eax, [rdi+10h]
0x140028293  lea     rcx, [rsp+530h+SubjectContext]; SubjectContext
0x140028298  mov     [rbp+430h+AuditParameters.Type], ax
0x14002829c  mov     [rbp+430h+AuditParameters.ParameterCount], edi
0x14002829f  call    cs:__imp_SeCaptureSubjectContext
0x1400282a6  nop     dword ptr [rax+rax+00h]
0x1400282ab  mov     rax, [rsp+530h+SubjectContext.ClientToken]
0x1400282b0  lea     rdx, [rsp+530h+AuthenticationId]; AuthenticationId
0x1400282b5  mov     rcx, [rbp+430h+SubjectContext.PrimaryToken]
0x1400282b9  test    rax, rax
0x1400282bc  cmovnz  rcx, rax; Token
0x1400282c0  call    cs:__imp_SeQueryAuthenticationIdToken
0x1400282c7  nop     dword ptr [rax+rax+00h]
0x1400282cc  mov     edi, eax
0x1400282ce  test    eax, eax
0x1400282d0  js      loc_140028421
0x1400282d6  mov     r8d, [rbp+430h+AuditParameters.ParameterCount]; Index
0x1400282da  lea     r9, [rsp+530h+AuthenticationId]; Data
0x1400282df  mov     edx, 5; Type
0x1400282e4  lea     rcx, [rbp+430h+AuditParameters]; AuditParameters
0x1400282e8  call    cs:__imp_SeSetAuditParameter
0x1400282ef  nop     dword ptr [rax+rax+00h]
0x1400282f4  mov     r8d, [rbp+430h+AuditParameters.ParameterCount]
0x1400282f8  mov     edi, eax
0x1400282fa  inc     r8d; Index
0x1400282fd  mov     [rbp+430h+AuditParameters.ParameterCount], r8d
0x140028301  test    eax, eax
0x140028303  js      loc_140028421
0x140028309  lea     r9, [rsp+530h+Data]; Data
0x14002830e  mov     edx, 1; Type
0x140028313  lea     rcx, [rbp+430h+AuditParameters]; AuditParameters
0x140028317  call    cs:__imp_SeSetAuditParameter
0x14002831e  nop     dword ptr [rax+rax+00h]
0x140028323  mov     edi, eax
0x140028325  test    eax, eax
0x140028327  js      loc_140028421
0x14002832d  mov     r8d, [rbp+430h+AuditParameters.ParameterCount]
0x140028331  lea     rcx, [rbp+430h+AuditParameters]; AuditParameters
0x140028335  mov     r9, rbx; Data
0x140028338  mov     edx, 17h; Type
0x14002833d  lea     r13d, [r8+2]
0x140028341  inc     r8d; Index
0x140028344  mov     [rbp+430h+AuditParameters.ParameterCount], r8d
0x140028348  call    cs:__imp_SeSetAuditParameter
0x14002834f  nop     dword ptr [rax+rax+00h]
0x140028354  mov     r8d, [rbp+430h+AuditParameters.ParameterCount]
0x140028358  mov     ebx, 1
0x14002835d  add     r8d, ebx; Index
0x140028360  mov     edi, eax
0x140028362  mov     [rbp+430h+AuditParameters.ParameterCount], r8d
0x140028366  test    eax, eax
0x140028368  js      loc_14002841E
0x14002836e  mov     r9, r15; Data
0x140028371  lea     rcx, [rbp+430h+AuditParameters]; AuditParameters
0x140028375  mov     edx, ebx; Type
0x140028377  call    cs:__imp_SeSetAuditParameter
0x14002837e  nop     dword ptr [rax+rax+00h]
0x140028383  mov     r8d, [rbp+430h+AuditParameters.ParameterCount]
0x140028387  mov     edi, eax
0x140028389  add     r8d, ebx; Index
0x14002838c  mov     [rbp+430h+AuditParameters.ParameterCount], r8d
0x140028390  test    eax, eax
0x140028392  js      loc_14002841E
0x140028398  mov     r9, [rsp+530h+var_4F0]; Data
0x14002839d  lea     rcx, [rbp+430h+AuditParameters]; AuditParameters
0x1400283a1  mov     edx, ebx; Type
0x1400283a3  call    cs:__imp_SeSetAuditParameter
0x1400283aa  nop     dword ptr [rax+rax+00h]
0x1400283af  mov     r8d, [rbp+430h+AuditParameters.ParameterCount]
0x1400283b3  mov     edi, eax
0x1400283b5  add     r8d, ebx; Index
0x1400283b8  mov     [rbp+430h+AuditParameters.ParameterCount], r8d
0x1400283bc  test    eax, eax
0x1400283be  js      short loc_14002841E
0x1400283c0  mov     r9, [rsp+530h+var_4E8]; Data
0x1400283c5  lea     rcx, [rbp+430h+AuditParameters]; AuditParameters
0x1400283c9  mov     edx, ebx; Type
0x1400283cb  call    cs:__imp_SeSetAuditParameter
0x1400283d2  nop     dword ptr [rax+rax+00h]
0x1400283d7  mov     r8d, [rbp+430h+AuditParameters.ParameterCount]
0x1400283db  mov     edi, eax
0x1400283dd  add     r8d, ebx; Index
0x1400283e0  mov     [rbp+430h+AuditParameters.ParameterCount], r8d
0x1400283e4  test    eax, eax
0x1400283e6  js      short loc_14002841E
0x1400283e8  lea     r9, [rbp+430h+arg_20]; Data
0x1400283ef  lea     edx, [rbx+9]; Type
0x1400283f2  lea     rcx, [rbp+430h+AuditParameters]; AuditParameters
0x1400283f6  call    cs:__imp_SeSetAuditParameter
0x1400283fd  nop     dword ptr [rax+rax+00h]
0x140028402  mov     edi, eax
0x140028404  mov     eax, [rbp+430h+AuditParameters.ParameterCount]
0x140028407  add     eax, ebx
0x140028409  mov     [rbp+430h+AuditParameters.ParameterCount], eax
0x14002840c  test    edi, edi
0x14002840e  js      short loc_14002841E
0x140028410  cmp     eax, 1Fh
0x140028413  jb      loc_1400284A9
0x140028419  mov     edi, 80000005h
0x14002841e  mov     r13b, sil
0x140028421  lea     rcx, [rsp+530h+SubjectContext]; SubjectContext
0x140028426  call    cs:__imp_SeReleaseSubjectContext
0x14002842d  nop     dword ptr [rax+rax+00h]
0x140028432  test    r14, r14
0x140028435  jz      short loc_14002845E
0x140028437  test    r13b, r13b
0x14002843a  jz      short loc_14002845E
0x14002843c  mov     ecx, [r14-0Ch]
0x140028440  xor     r8d, r8d
0x140028443  mov     edx, [r14-10h]
0x140028447  call    SrvNetUpdateMemStatistics
0x14002844c  xor     edx, edx; Tag
0x14002844e  lea     rcx, [r14-10h]; P
0x140028452  call    cs:__imp_ExFreePoolWithTag
0x140028459  nop     dword ptr [rax+rax+00h]
0x14002845e  test    rsi, rsi
0x140028461  jz      short loc_140028483
0x140028463  mov     ecx, [rsi-0Ch]
0x140028466  xor     r8d, r8d
0x140028469  mov     edx, [rsi-10h]
0x14002846c  call    SrvNetUpdateMemStatistics
0x140028471  xor     edx, edx; Tag
0x140028473  lea     rcx, [rsi-10h]; P
0x140028477  call    cs:__imp_ExFreePoolWithTag
0x14002847e  nop     dword ptr [rax+rax+00h]
0x140028483  mov     eax, edi
0x140028485  mov     rcx, [rbp+430h+var_50]
0x14002848c  xor     rcx, rsp; StackCookie
0x14002848f  call    __security_check_cookie
0x140028494  add     rsp, 4F8h
0x14002849b  pop     r15
0x14002849d  pop     r14
0x14002849f  pop     r13
0x1400284a1  pop     r12
0x1400284a3  pop     rdi
0x1400284a4  pop     rsi
0x1400284a5  pop     rbx
0x1400284a6  pop     rbp
0x1400284a7  retn
0x1400284a9  mov     ecx, [rbp+430h+arg_20]
0x1400284af  shl     rax, 5
0x1400284b3  mov     [rbp+rax+430h+AuditParameters.Parameters.Type], 7
0x1400284bb  mov     eax, [rbp+430h+AuditParameters.ParameterCount]
0x1400284be  shl     rax, 5
0x1400284c2  mov     [rbp+rax+430h+AuditParameters.Parameters.Length], 4
0x1400284ca  mov     eax, [rbp+430h+AuditParameters.ParameterCount]
0x1400284cd  shl     rax, 5
0x1400284d1  mov     [rbp+rax+430h+AuditParameters.Parameters.Data], rcx
0x1400284d6  mov     eax, [rbp+430h+AuditParameters.ParameterCount]
0x1400284d9  shl     rax, 5
0x1400284dd  mov     ecx, r13d
0x1400284e0  mov     [rbp+rax+430h+AuditParameters.Parameters.Data+8], rcx
0x1400284e5  add     [rbp+430h+AuditParameters.ParameterCount], ebx
0x1400284e8  test    r12, r12
0x1400284eb  jnz     short loc_140028505
0x1400284ed  mov     edx, ebx; Revision
0x1400284ef  lea     rcx, [rbp+430h+SecurityDescriptor]; SecurityDescriptor
0x1400284f3  call    cs:__imp_RtlCreateSecurityDescriptor
0x1400284fa  nop     dword ptr [rax+rax+00h]
0x1400284ff  lea     rbx, [rbp+430h+SecurityDescriptor]
0x140028503  jmp     short loc_140028508
0x140028505  mov     rbx, r12
0x140028508  mov     rcx, rbx; SecurityDescriptor
0x14002850b  call    cs:__imp_RtlLengthSecurityDescriptor
0x140028512  nop     dword ptr [rax+rax+00h]
0x140028517  mov     ecx, 100h
0x14002851c  mov     r8d, 626C534Ch
0x140028522  mov     [rsp+530h+BufferLength], eax
0x140028526  lea     r15d, [rax+90h]
0x14002852d  mov     edx, r15d
0x140028530  call    SrvNetAllocatePoolWithTag
0x140028535  mov     rsi, rax
0x140028538  test    rax, rax
0x14002853b  jnz     short loc_14002854A
0x14002853d  mov     edi, 0C000009Ah
0x140028542  mov     r13b, r14b
0x140028545  jmp     loc_140028421
0x14002854a  mov     ecx, [rbp+430h+arg_40]
0x140028550  mov     eax, ecx
0x140028552  mov     [rsi+84h], r13d
0x140028559  not     eax
0x14002855b  shr     eax, 1Fh
0x14002855e  mov     [rsi+88h], eax
0x140028564  test    ecx, ecx
0x140028566  mov     eax, [rbp+430h+arg_20]
0x14002856c  cmovns  eax, [rbp+430h+arg_28]
0x140028573  mov     [rsi], eax
0x140028575  mov     rax, [rbp+430h+arg_38]
0x14002857c  movups  xmm0, xmmword ptr [rax]
0x14002857f  movups  xmmword ptr [rsi+4], xmm0
0x140028583  movups  xmm1, xmmword ptr [rax+10h]
0x140028587  movups  xmmword ptr [rsi+14h], xmm1
0x14002858b  movups  xmm0, xmmword ptr [rax+20h]
0x14002858f  movups  xmmword ptr [rsi+24h], xmm0
0x140028593  movups  xmm1, xmmword ptr [rax+30h]
0x140028597  movups  xmmword ptr [rsi+34h], xmm1
0x14002859b  movups  xmm0, xmmword ptr [rax+40h]
0x14002859f  movups  xmmword ptr [rsi+44h], xmm0
0x1400285a3  movups  xmm1, xmmword ptr [rax+50h]
0x1400285a7  movups  xmmword ptr [rsi+54h], xmm1
0x1400285ab  movups  xmm0, xmmword ptr [rax+60h]
0x1400285af  movups  xmmword ptr [rsi+64h], xmm0
0x1400285b3  movups  xmm1, xmmword ptr [rax+70h]
0x1400285b7  movups  xmmword ptr [rsi+74h], xmm1
0x1400285bb  test    r12, r12
0x1400285be  jz      short loc_14002863B
0x1400285c0  lea     r8, [rsp+530h+BufferLength]; BufferLength
0x1400285c5  xor     edx, edx; SelfRelativeSecurityDescriptor
0x1400285c7  mov     rcx, rbx; AbsoluteSecurityDescriptor
0x1400285ca  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x1400285d1  nop     dword ptr [rax+rax+00h]
0x1400285d6  mov     edi, eax
0x1400285d8  cmp     eax, 0C0000023h
0x1400285dd  jnz     short loc_140028630
0x1400285df  mov     edx, [rsp+530h+BufferLength]
0x1400285e3  mov     ecx, 102h
0x1400285e8  mov     r8d, 626C534Ch
0x1400285ee  call    SrvNetAllocatePoolWithTag
0x1400285f3  mov     r14, rax
0x1400285f6  test    rax, rax
0x1400285f9  jnz     short loc_14002860A
0x1400285fb  mov     r13b, [rsp+530h+var_500]
0x140028600  mov     edi, 0C000009Ah
0x140028605  jmp     loc_140028421
0x14002860a  lea     r8, [rsp+530h+BufferLength]; BufferLength
0x14002860f  mov     rdx, rax; SelfRelativeSecurityDescriptor
0x140028612  mov     rcx, rbx; AbsoluteSecurityDescriptor
0x140028615  mov     r13b, 1
0x140028618  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x14002861f  nop     dword ptr [rax+rax+00h]
0x140028624  mov     edi, eax
0x140028626  test    eax, eax
0x140028628  js      loc_140028421
0x14002862e  jmp     short loc_140028643
0x140028630  cmp     eax, 0C00000E7h
0x140028635  jnz     loc_140028542
0x14002863b  mov     r13b, [rsp+530h+var_500]
0x140028640  mov     r14, rbx
0x140028643  mov     r8d, [rsp+530h+BufferLength]; Size
0x140028648  lea     rcx, [rsi+90h]; void *
0x14002864f  mov     rdx, r14; Src
0x140028652  call    memmove
0x140028657  mov     eax, [rbp+430h+AuditParameters.ParameterCount]
0x14002865a  lea     r9, [rbp+430h+AuditParameters]; AuditParameters
0x14002865e  shl     rax, 5
0x140028662  lea     rdx, [rsp+530h+DestinationString]; SourceName
0x140028667  xor     r8d, r8d; UserSid
  ... truncated ...
```
