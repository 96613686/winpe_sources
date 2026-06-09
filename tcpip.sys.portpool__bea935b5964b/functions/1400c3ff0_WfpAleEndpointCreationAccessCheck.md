# WfpAleEndpointCreationAccessCheck

- ea: `0x1400c3ff0`
- end: `0x1400c41bd`
- name: `WfpAleEndpointCreationAccessCheck`
- size: `461`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400c3d2c`

## callees

- `0x140014a90`
- `0x1400c3930`
- `0x1400c3ff0`
- `0x1400c7fe0`
- `0x14014eafc`
- `0x140178bf8`

## import_xrefs

- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1400c4097`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1401d005a`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1400c4097`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1401d005a`
- `ntoskrnl!SeAccessCheck` at `0x1400c40e1`
- `ntoskrnl!SeAccessCheck` at `0x1401d00a4`
- `ntoskrnl!SeAccessCheck` at `0x1400c40e1`
- `ntoskrnl!SeAccessCheck` at `0x1401d00a4`
- `ntoskrnl!PsGetProcessId` at `0x1401d0106`
- `ntoskrnl!PsGetProcessId` at `0x1401d0106`
- `ntoskrnl!SeQueryInformationToken` at `0x1400c4043`
- `ntoskrnl!SeQueryInformationToken` at `0x1400c4084`
- `ntoskrnl!SeQueryInformationToken` at `0x1400c4043`
- `ntoskrnl!SeQueryInformationToken` at `0x1400c4084`

## string_xrefs

- `0x1401d00c9`: `SeAccessCheck`
- `0x1400c4156`: `InetInspectRawEndpointSetAccessCheckResult`
- `0x1400c41ac`: `InetInspectRawEndpointPerformAccessCheck`
- `0x1401d0142`: `WfpAleEndpointCreationAccessCheck`

## pseudocode

```c
__int64 __fastcall WfpAleEndpointCreationAccessCheck(
        __int64 a1,
        struct _KPROCESS *a2,
        struct _SECURITY_SUBJECT_CONTEXT *a3,
        __int64 a4)
{
  __int64 v5; // rbx
  int IsEnabledDeviceUsageNoInline; // eax
  PACCESS_TOKEN PrimaryToken; // rcx
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // r9
  struct _GENERIC_MAPPING *GenericMapping; // rax
  BOOLEAN v16; // al
  __int16 v17; // dx
  __int64 v18; // r9
  int v19; // eax
  __int64 v20; // r8
  __int64 v21; // rcx
  const char *v22; // rdx
  __int64 v23; // r14
  int v24; // eax
  unsigned int v25; // eax
  struct _GENERIC_MAPPING *FileObjectGenericMapping; // rax
  unsigned int ProcessId; // eax
  __int64 v28; // r8
  PVOID TokenInformation[2]; // [rsp+50h] [rbp-28h] BYREF
  int AccessStatus; // [rsp+98h] [rbp+20h] BYREF

  AccessStatus = 0;
  v5 = 0;
  TokenInformation[0] = 0;
  if ( (Feature_5988_5730__private_featureState & 0x10) != 0 )
    IsEnabledDeviceUsageNoInline = Feature_5988_5730__private_featureState & 1;
  else
    IsEnabledDeviceUsageNoInline = Feature_5988_5730__private_IsEnabledDeviceUsageNoInline(a1, a2, a3, a4);
  PrimaryToken = a3->PrimaryToken;
  if ( IsEnabledDeviceUsageNoInline )
  {
    AccessStatus = SeQueryInformationToken(PrimaryToken, TokenIsAppContainer, TokenInformation);
    GenericMapping = IoGetFileObjectGenericMapping();
    v16 = SeAccessCheck(
            TcpipEndpointCreationAdminSdData,
            a3,
            1u,
            2u,
            0,
            0,
            GenericMapping,
            1,
            (PACCESS_MASK)TokenInformation + 1,
            &AccessStatus);
    v17 = v16;
    if ( v16 )
      _InterlockedOr((volatile signed __int32 *)(a1 + 56), 8u);
    if ( (*(_DWORD *)(a1 + 48) & 0x10) == 0 )
      goto LABEL_5;
    v18 = *(_QWORD *)(a1 + 352);
    if ( v18 )
    {
      v19 = *(_DWORD *)(v18 + 64);
      if ( v19 == 1 || (v20 = (unsigned int)AccessStatus, v19 == 58) )
        v20 = 0;
      v21 = *(_DWORD *)(v18 + 24) ^ ((unsigned __int16)*(_DWORD *)(v18 + 24) ^ (unsigned __int16)(v17 << 10)) & 0x400u;
      *(_DWORD *)(v18 + 24) = v21;
      AccessStatus = v20;
      if ( (_DWORD)v20 )
      {
        v22 = "InetInspectRawEndpointSetAccessCheckResult";
        goto LABEL_28;
      }
    }
  }
  else
  {
    AccessStatus = SeQueryInformationToken(PrimaryToken, TokenIsAppContainer, TokenInformation);
    if ( (*(_DWORD *)(a1 + 48) & 0x10) == 0 )
    {
LABEL_5:
      if ( !LODWORD(TokenInformation[0]) )
        return v5;
      FileObjectGenericMapping = IoGetFileObjectGenericMapping();
      if ( SeAccessCheck(
             TcpipEndpointCreationSdData,
             a3,
             1u,
             0x1200A9u,
             0,
             0,
             FileObjectGenericMapping,
             1,
             (PACCESS_MASK)TokenInformation + 1,
             &AccessStatus) )
      {
        return v5;
      }
      v20 = (unsigned int)AccessStatus;
      if ( !AccessStatus )
        return v5;
      v22 = "SeAccessCheck";
      goto LABEL_28;
    }
    v23 = *(_QWORD *)(a1 + 352);
    if ( v23 )
    {
      if ( (Feature_5988_5730__private_featureState & 0x10) != 0 )
        v24 = Feature_5988_5730__private_featureState & 1;
      else
        v24 = Feature_5988_5730__private_IsEnabledDeviceUsageNoInline(v11, v10, v12, v13);
      if ( v24 )
        __int2c();
      v25 = RawEndpointPerformAccessCheck(v23, a3);
      AccessStatus = v25;
      if ( v25 )
      {
        v20 = v25;
        v22 = "InetInspectRawEndpointPerformAccessCheck";
LABEL_28:
        v5 = WfpReportSysErrorAsNtStatus(v21, v22, v20);
        if ( v5 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10000) != 0 )
          {
            ProcessId = (unsigned int)PsGetProcessId(a2);
            WPP_SF_qldq(
              WPP_GLOBAL_Control->AttachedDevice,
              (*(_DWORD *)(a1 + 48) >> 4) & 1,
              v28,
              a1,
              (*(_DWORD *)(a1 + 48) >> 4) & 1,
              ProcessId,
              *(_QWORD *)(a1 + 352));
          }
          WfpReportError(v5, "WfpAleEndpointCreationAccessCheck");
        }
      }
    }
  }
  return v5;
}

```

## disassembly

```asm
0x1400c3ff0  mov     rax, rsp
0x1400c3ff3  mov     [rax+8], rbx
0x1400c3ff7  mov     [rax+10h], rbp
0x1400c3ffb  push    rsi
0x1400c3ffc  push    rdi
0x1400c3ffd  push    r14
0x1400c3fff  sub     rsp, 60h
0x1400c4003  xor     r14d, r14d
0x1400c4006  mov     rdi, r8
0x1400c4009  mov     [rax+20h], r14d
0x1400c400d  mov     ebx, r14d
0x1400c4010  mov     [rax-24h], r14d
0x1400c4014  mov     rbp, rdx
0x1400c4017  mov     [rax-28h], r14d
0x1400c401b  mov     rsi, rcx
0x1400c401e  mov     eax, cs:Feature_5988_5730__private_featureState
0x1400c4024  test    al, 10h
0x1400c4026  jnz     loc_1400C4162
0x1400c402c  call    Feature_5988_5730__private_IsEnabledDeviceUsageNoInline
0x1400c4031  mov     rcx, [rdi+10h]; Token
0x1400c4035  lea     r8, [rsp+78h+TokenInformation]; TokenInformation
0x1400c403a  mov     edx, 1Dh; TokenInformationClass
0x1400c403f  test    eax, eax
0x1400c4041  jnz     short loc_1400C4084
0x1400c4043  call    cs:__imp_SeQueryInformationToken
0x1400c404a  nop     dword ptr [rax+rax+00h]
0x1400c404f  mov     [rsp+78h+arg_18], eax
0x1400c4056  mov     eax, [rsi+30h]
0x1400c4059  test    al, 10h
0x1400c405b  jnz     loc_1400C416A
0x1400c4061  cmp     dword ptr [rsp+78h+TokenInformation], ebx
0x1400c4065  jnz     loc_1401D005A
0x1400c406b  lea     r11, [rsp+78h+var_18]
0x1400c4070  mov     rax, rbx
0x1400c4073  mov     rbx, [r11+20h]
0x1400c4077  mov     rbp, [r11+28h]
0x1400c407b  mov     rsp, r11
0x1400c407e  pop     r14
0x1400c4080  pop     rdi
0x1400c4081  pop     rsi
0x1400c4082  retn
0x1400c4084  call    cs:__imp_SeQueryInformationToken
0x1400c408b  nop     dword ptr [rax+rax+00h]
0x1400c4090  mov     [rsp+78h+arg_18], eax
0x1400c4097  call    cs:__imp_IoGetFileObjectGenericMapping
0x1400c409e  nop     dword ptr [rax+rax+00h]
0x1400c40a3  lea     rcx, [rsp+78h+arg_18]
0x1400c40ab  mov     r9d, 2; DesiredAccess
0x1400c40b1  mov     [rsp+78h+AccessStatus], rcx; AccessStatus
0x1400c40b6  mov     r8b, 1; SubjectContextLocked
0x1400c40b9  lea     rcx, [rsp+78h+TokenInformation+4]
0x1400c40be  mov     rdx, rdi; SubjectSecurityContext
0x1400c40c1  mov     [rsp+78h+GrantedAccess], rcx; GrantedAccess
0x1400c40c6  lea     rcx, TcpipEndpointCreationAdminSdData; SecurityDescriptor
0x1400c40cd  mov     [rsp+78h+AccessMode], 1; AccessMode
0x1400c40d2  mov     [rsp+78h+GenericMapping], rax; GenericMapping
0x1400c40d7  mov     [rsp+78h+Privileges], r14; Privileges
0x1400c40dc  mov     [rsp+78h+PreviouslyGrantedAccess], r14d; PreviouslyGrantedAccess
0x1400c40e1  call    cs:__imp_SeAccessCheck
0x1400c40e8  nop     dword ptr [rax+rax+00h]
0x1400c40ed  movzx   edx, al
0x1400c40f0  test    al, al
0x1400c40f2  jz      short loc_1400C40F9
0x1400c40f4  lock or dword ptr [rsi+38h], 8
0x1400c40f9  mov     ecx, [rsi+30h]
0x1400c40fc  test    cl, 10h
0x1400c40ff  jz      loc_1400C4061
0x1400c4105  mov     r9, [rsi+160h]
0x1400c410c  test    r9, r9
0x1400c410f  jz      loc_1400C406B
0x1400c4115  mov     eax, [r9+40h]
0x1400c4119  cmp     eax, 1
0x1400c411c  jz      short loc_1400C412B
0x1400c411e  mov     r8d, [rsp+78h+arg_18]
0x1400c4126  cmp     eax, 3Ah ; ':'
0x1400c4129  jnz     short loc_1400C412E
0x1400c412b  mov     r8d, r14d
0x1400c412e  mov     eax, [r9+18h]
0x1400c4132  mov     ecx, edx
0x1400c4134  shl     ecx, 0Ah
0x1400c4137  xor     ecx, eax
0x1400c4139  and     ecx, 400h
0x1400c413f  xor     ecx, eax
0x1400c4141  mov     [r9+18h], ecx
0x1400c4145  mov     [rsp+78h+arg_18], r8d
0x1400c414d  test    r8d, r8d
0x1400c4150  jz      loc_1400C406B
0x1400c4156  lea     rdx, aInetinspectraw; "InetInspectRawEndpointSetAccessCheckRes"...
0x1400c415d  jmp     loc_1401D00D0
0x1400c4162  and     eax, 1
0x1400c4165  jmp     loc_1400C4031
0x1400c416a  mov     r14, [rsi+160h]
0x1400c4171  test    r14, r14
0x1400c4174  jz      loc_1400C406B
0x1400c417a  mov     eax, cs:Feature_5988_5730__private_featureState
0x1400c4180  test    al, 10h
0x1400c4182  jnz     short loc_1400C41B8
0x1400c4184  call    Feature_5988_5730__private_IsEnabledDeviceUsageNoInline
0x1400c4189  test    eax, eax
0x1400c418b  jz      short loc_1400C418F
0x1400c418d  int     2Ch; Windows NT - assertion failure
0x1400c418f  mov     rdx, rdi
0x1400c4192  mov     rcx, r14
0x1400c4195  call    RawEndpointPerformAccessCheck
0x1400c419a  mov     [rsp+78h+arg_18], eax
0x1400c41a1  test    eax, eax
0x1400c41a3  jz      loc_1400C406B
0x1400c41a9  mov     r8d, eax
0x1400c41ac  lea     rdx, aInetinspectraw_0; "InetInspectRawEndpointPerformAccessChec"...
0x1400c41b3  jmp     loc_1401D00D0
0x1400c41b8  and     eax, 1
0x1400c41bb  jmp     short loc_1400C4189
0x1401d005a  call    cs:__imp_IoGetFileObjectGenericMapping
0x1401d0061  nop     dword ptr [rax+rax+00h]
0x1401d0066  lea     rcx, [rsp+78h+arg_18]
0x1401d006e  mov     r9d, 1200A9h; DesiredAccess
0x1401d0074  mov     [rsp+78h+AccessStatus], rcx; AccessStatus
0x1401d0079  mov     r8b, 1; SubjectContextLocked
0x1401d007c  lea     rcx, [rsp+78h+TokenInformation+4]
0x1401d0081  mov     rdx, rdi; SubjectSecurityContext
0x1401d0084  mov     [rsp+78h+GrantedAccess], rcx; GrantedAccess
0x1401d0089  lea     rcx, TcpipEndpointCreationSdData; SecurityDescriptor
0x1401d0090  mov     [rsp+78h+AccessMode], 1; AccessMode
0x1401d0095  mov     [rsp+78h+GenericMapping], rax; GenericMapping
0x1401d009a  mov     [rsp+78h+Privileges], r14; Privileges
0x1401d009f  mov     [rsp+78h+PreviouslyGrantedAccess], r14d; PreviouslyGrantedAccess
0x1401d00a4  call    cs:__imp_SeAccessCheck
0x1401d00ab  nop     dword ptr [rax+rax+00h]
0x1401d00b0  test    al, al
0x1401d00b2  jnz     loc_1400C406B
0x1401d00b8  mov     r8d, [rsp+78h+arg_18]
0x1401d00c0  test    r8d, r8d
0x1401d00c3  jz      loc_1400C406B
0x1401d00c9  lea     rdx, aSeaccesscheck; "SeAccessCheck"
0x1401d00d0  call    WfpReportSysErrorAsNtStatus
0x1401d00d5  mov     rbx, rax
0x1401d00d8  test    rax, rax
0x1401d00db  jz      loc_1400C406B
0x1401d00e1  mov     rax, cs:WPP_GLOBAL_Control
0x1401d00e8  lea     rcx, WPP_GLOBAL_Control
0x1401d00ef  cmp     rax, rcx
0x1401d00f2  jz      short loc_1401D0142
0x1401d00f4  cmp     byte ptr [rax+29h], 2
0x1401d00f8  jb      short loc_1401D0142
0x1401d00fa  test    dword ptr [rax+2Ch], 10000h
0x1401d0101  jz      short loc_1401D0142
0x1401d0103  mov     rcx, rbp; Process
0x1401d0106  call    cs:__imp_PsGetProcessId
0x1401d010d  nop     dword ptr [rax+rax+00h]
0x1401d0112  mov     edx, [rsi+30h]
0x1401d0115  mov     r9, rsi
0x1401d0118  mov     rcx, [rsi+160h]
0x1401d011f  mov     [rsp+78h+GenericMapping], rcx
0x1401d0124  mov     rcx, cs:WPP_GLOBAL_Control
0x1401d012b  shr     edx, 4
0x1401d012e  and     edx, 1
0x1401d0131  mov     dword ptr [rsp+78h+Privileges], eax
0x1401d0135  mov     [rsp+78h+PreviouslyGrantedAccess], edx
0x1401d0139  mov     rcx, [rcx+18h]
0x1401d013d  call    WPP_SF_qldq
0x1401d0142  lea     rdx, aWfpaleendpoint_0; "WfpAleEndpointCreationAccessCheck"
0x1401d0149  mov     rcx, rbx
0x1401d014c  call    WfpReportError
0x1401d0151  nop
0x1401d0152  jmp     loc_1400C406B
```
