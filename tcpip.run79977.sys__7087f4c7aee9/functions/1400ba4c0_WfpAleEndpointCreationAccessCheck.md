# WfpAleEndpointCreationAccessCheck

- ea: `0x1400ba4c0`
- end: `0x1400ba68d`
- name: `WfpAleEndpointCreationAccessCheck`
- size: `461`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400ba1fc`

## callees

- `0x1400541c0`
- `0x1400b9e00`
- `0x1400ba4c0`
- `0x1400be690`
- `0x14014cf54`
- `0x140177038`

## import_xrefs

- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1400ba567`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1401cae88`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1400ba567`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1401cae88`
- `ntoskrnl!SeAccessCheck` at `0x1400ba5b1`
- `ntoskrnl!SeAccessCheck` at `0x1401caed2`
- `ntoskrnl!SeAccessCheck` at `0x1400ba5b1`
- `ntoskrnl!SeAccessCheck` at `0x1401caed2`
- `ntoskrnl!PsGetProcessId` at `0x1401caf34`
- `ntoskrnl!PsGetProcessId` at `0x1401caf34`
- `ntoskrnl!SeQueryInformationToken` at `0x1400ba513`
- `ntoskrnl!SeQueryInformationToken` at `0x1400ba554`
- `ntoskrnl!SeQueryInformationToken` at `0x1400ba513`
- `ntoskrnl!SeQueryInformationToken` at `0x1400ba554`

## string_xrefs

- `0x1401caf70`: `WfpAleEndpointCreationAccessCheck`
- `0x1401caef7`: `SeAccessCheck`
- `0x1400ba626`: `InetInspectRawEndpointSetAccessCheckResult`
- `0x1400ba67c`: `InetInspectRawEndpointPerformAccessCheck`

## pseudocode

```c
__int64 __fastcall WfpAleEndpointCreationAccessCheck(
        __int64 a1,
        struct _KPROCESS *a2,
        struct _SECURITY_SUBJECT_CONTEXT *a3)
{
  __int64 v4; // rbx
  int IsEnabledDeviceUsageNoInline; // eax
  PACCESS_TOKEN PrimaryToken; // rcx
  struct _GENERIC_MAPPING *GenericMapping; // rax
  BOOLEAN v11; // al
  __int16 v12; // dx
  __int64 v13; // r9
  int v14; // eax
  __int64 v15; // r8
  __int64 v16; // rcx
  const char *v17; // rdx
  __int64 v18; // r14
  int v19; // eax
  unsigned int v20; // eax
  struct _GENERIC_MAPPING *FileObjectGenericMapping; // rax
  unsigned int ProcessId; // eax
  __int64 v23; // r8
  PVOID TokenInformation[2]; // [rsp+50h] [rbp-28h] BYREF
  int AccessStatus; // [rsp+98h] [rbp+20h] BYREF

  AccessStatus = 0;
  v4 = 0;
  TokenInformation[0] = 0;
  if ( (Feature_5988_5730__private_featureState & 0x10) != 0 )
    IsEnabledDeviceUsageNoInline = Feature_5988_5730__private_featureState & 1;
  else
    IsEnabledDeviceUsageNoInline = Feature_5988_5730__private_IsEnabledDeviceUsageNoInline();
  PrimaryToken = a3->PrimaryToken;
  if ( IsEnabledDeviceUsageNoInline )
  {
    AccessStatus = SeQueryInformationToken(PrimaryToken, TokenIsAppContainer, TokenInformation);
    GenericMapping = IoGetFileObjectGenericMapping();
    v11 = SeAccessCheck(
            &TcpipEndpointCreationAdminSdData,
            a3,
            1u,
            2u,
            0,
            0,
            GenericMapping,
            1,
            (PACCESS_MASK)TokenInformation + 1,
            &AccessStatus);
    v12 = v11;
    if ( v11 )
      _InterlockedOr((volatile signed __int32 *)(a1 + 56), 8u);
    if ( (*(_DWORD *)(a1 + 48) & 0x10) == 0 )
      goto LABEL_5;
    v13 = *(_QWORD *)(a1 + 352);
    if ( v13 )
    {
      v14 = *(_DWORD *)(v13 + 64);
      if ( v14 == 1 || (v15 = (unsigned int)AccessStatus, v14 == 58) )
        v15 = 0;
      v16 = *(_DWORD *)(v13 + 24) ^ ((unsigned __int16)*(_DWORD *)(v13 + 24) ^ (unsigned __int16)(v12 << 10)) & 0x400u;
      *(_DWORD *)(v13 + 24) = v16;
      AccessStatus = v15;
      if ( (_DWORD)v15 )
      {
        v17 = "InetInspectRawEndpointSetAccessCheckResult";
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
        return v4;
      FileObjectGenericMapping = IoGetFileObjectGenericMapping();
      if ( SeAccessCheck(
             &TcpipEndpointCreationSdData,
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
        return v4;
      }
      v15 = (unsigned int)AccessStatus;
      if ( !AccessStatus )
        return v4;
      v17 = "SeAccessCheck";
      goto LABEL_28;
    }
    v18 = *(_QWORD *)(a1 + 352);
    if ( v18 )
    {
      if ( (Feature_5988_5730__private_featureState & 0x10) != 0 )
        v19 = Feature_5988_5730__private_featureState & 1;
      else
        v19 = Feature_5988_5730__private_IsEnabledDeviceUsageNoInline();
      if ( v19 )
        __int2c();
      v20 = RawEndpointPerformAccessCheck(v18, a3);
      AccessStatus = v20;
      if ( v20 )
      {
        v15 = v20;
        v17 = "InetInspectRawEndpointPerformAccessCheck";
LABEL_28:
        v4 = WfpReportSysErrorAsNtStatus(v16, v17, v15);
        if ( v4 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10000) != 0 )
          {
            ProcessId = (unsigned int)PsGetProcessId(a2);
            WPP_SF_qldq(
              WPP_GLOBAL_Control->AttachedDevice,
              (*(_DWORD *)(a1 + 48) >> 4) & 1,
              v23,
              a1,
              (*(_DWORD *)(a1 + 48) >> 4) & 1,
              ProcessId,
              *(_QWORD *)(a1 + 352));
          }
          WfpReportError(v4, "WfpAleEndpointCreationAccessCheck");
        }
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x1400ba4c0  mov     rax, rsp
0x1400ba4c3  mov     [rax+8], rbx
0x1400ba4c7  mov     [rax+10h], rbp
0x1400ba4cb  push    rsi
0x1400ba4cc  push    rdi
0x1400ba4cd  push    r14
0x1400ba4cf  sub     rsp, 60h
0x1400ba4d3  xor     r14d, r14d
0x1400ba4d6  mov     rdi, r8
0x1400ba4d9  mov     [rax+20h], r14d
0x1400ba4dd  mov     ebx, r14d
0x1400ba4e0  mov     [rax-24h], r14d
0x1400ba4e4  mov     rbp, rdx
0x1400ba4e7  mov     [rax-28h], r14d
0x1400ba4eb  mov     rsi, rcx
0x1400ba4ee  mov     eax, cs:Feature_5988_5730__private_featureState
0x1400ba4f4  test    al, 10h
0x1400ba4f6  jnz     loc_1400BA632
0x1400ba4fc  call    Feature_5988_5730__private_IsEnabledDeviceUsageNoInline
0x1400ba501  mov     rcx, [rdi+10h]; Token
0x1400ba505  lea     r8, [rsp+78h+TokenInformation]; TokenInformation
0x1400ba50a  mov     edx, 1Dh; TokenInformationClass
0x1400ba50f  test    eax, eax
0x1400ba511  jnz     short loc_1400BA554
0x1400ba513  call    cs:__imp_SeQueryInformationToken
0x1400ba51a  nop     dword ptr [rax+rax+00h]
0x1400ba51f  mov     [rsp+78h+arg_18], eax
0x1400ba526  mov     eax, [rsi+30h]
0x1400ba529  test    al, 10h
0x1400ba52b  jnz     loc_1400BA63A
0x1400ba531  cmp     dword ptr [rsp+78h+TokenInformation], ebx
0x1400ba535  jnz     loc_1401CAE88
0x1400ba53b  lea     r11, [rsp+78h+var_18]
0x1400ba540  mov     rax, rbx
0x1400ba543  mov     rbx, [r11+20h]
0x1400ba547  mov     rbp, [r11+28h]
0x1400ba54b  mov     rsp, r11
0x1400ba54e  pop     r14
0x1400ba550  pop     rdi
0x1400ba551  pop     rsi
0x1400ba552  retn
0x1400ba554  call    cs:__imp_SeQueryInformationToken
0x1400ba55b  nop     dword ptr [rax+rax+00h]
0x1400ba560  mov     [rsp+78h+arg_18], eax
0x1400ba567  call    cs:__imp_IoGetFileObjectGenericMapping
0x1400ba56e  nop     dword ptr [rax+rax+00h]
0x1400ba573  lea     rcx, [rsp+78h+arg_18]
0x1400ba57b  mov     r9d, 2; DesiredAccess
0x1400ba581  mov     [rsp+78h+AccessStatus], rcx; AccessStatus
0x1400ba586  mov     r8b, 1; SubjectContextLocked
0x1400ba589  lea     rcx, [rsp+78h+TokenInformation+4]
0x1400ba58e  mov     rdx, rdi; SubjectSecurityContext
0x1400ba591  mov     [rsp+78h+GrantedAccess], rcx; GrantedAccess
0x1400ba596  lea     rcx, TcpipEndpointCreationAdminSdData; SecurityDescriptor
0x1400ba59d  mov     [rsp+78h+AccessMode], 1; AccessMode
0x1400ba5a2  mov     [rsp+78h+GenericMapping], rax; GenericMapping
0x1400ba5a7  mov     [rsp+78h+Privileges], r14; Privileges
0x1400ba5ac  mov     [rsp+78h+PreviouslyGrantedAccess], r14d; PreviouslyGrantedAccess
0x1400ba5b1  call    cs:__imp_SeAccessCheck
0x1400ba5b8  nop     dword ptr [rax+rax+00h]
0x1400ba5bd  movzx   edx, al
0x1400ba5c0  test    al, al
0x1400ba5c2  jz      short loc_1400BA5C9
0x1400ba5c4  lock or dword ptr [rsi+38h], 8
0x1400ba5c9  mov     ecx, [rsi+30h]
0x1400ba5cc  test    cl, 10h
0x1400ba5cf  jz      loc_1400BA531
0x1400ba5d5  mov     r9, [rsi+160h]
0x1400ba5dc  test    r9, r9
0x1400ba5df  jz      loc_1400BA53B
0x1400ba5e5  mov     eax, [r9+40h]
0x1400ba5e9  cmp     eax, 1
0x1400ba5ec  jz      short loc_1400BA5FB
0x1400ba5ee  mov     r8d, [rsp+78h+arg_18]
0x1400ba5f6  cmp     eax, 3Ah ; ':'
0x1400ba5f9  jnz     short loc_1400BA5FE
0x1400ba5fb  mov     r8d, r14d
0x1400ba5fe  mov     eax, [r9+18h]
0x1400ba602  mov     ecx, edx
0x1400ba604  shl     ecx, 0Ah
0x1400ba607  xor     ecx, eax
0x1400ba609  and     ecx, 400h
0x1400ba60f  xor     ecx, eax
0x1400ba611  mov     [r9+18h], ecx
0x1400ba615  mov     [rsp+78h+arg_18], r8d
0x1400ba61d  test    r8d, r8d
0x1400ba620  jz      loc_1400BA53B
0x1400ba626  lea     rdx, aInetinspectraw; "InetInspectRawEndpointSetAccessCheckRes"...
0x1400ba62d  jmp     loc_1401CAEFE
0x1400ba632  and     eax, 1
0x1400ba635  jmp     loc_1400BA501
0x1400ba63a  mov     r14, [rsi+160h]
0x1400ba641  test    r14, r14
0x1400ba644  jz      loc_1400BA53B
0x1400ba64a  mov     eax, cs:Feature_5988_5730__private_featureState
0x1400ba650  test    al, 10h
0x1400ba652  jnz     short loc_1400BA688
0x1400ba654  call    Feature_5988_5730__private_IsEnabledDeviceUsageNoInline
0x1400ba659  test    eax, eax
0x1400ba65b  jz      short loc_1400BA65F
0x1400ba65d  int     2Ch; Windows NT - assertion failure
0x1400ba65f  mov     rdx, rdi
0x1400ba662  mov     rcx, r14
0x1400ba665  call    RawEndpointPerformAccessCheck
0x1400ba66a  mov     [rsp+78h+arg_18], eax
0x1400ba671  test    eax, eax
0x1400ba673  jz      loc_1400BA53B
0x1400ba679  mov     r8d, eax
0x1400ba67c  lea     rdx, aInetinspectraw_0; "InetInspectRawEndpointPerformAccessChec"...
0x1400ba683  jmp     loc_1401CAEFE
0x1400ba688  and     eax, 1
0x1400ba68b  jmp     short loc_1400BA659
0x1401cae88  call    cs:__imp_IoGetFileObjectGenericMapping
0x1401cae8f  nop     dword ptr [rax+rax+00h]
0x1401cae94  lea     rcx, [rsp+78h+arg_18]
0x1401cae9c  mov     r9d, 1200A9h; DesiredAccess
0x1401caea2  mov     [rsp+78h+AccessStatus], rcx; AccessStatus
0x1401caea7  mov     r8b, 1; SubjectContextLocked
0x1401caeaa  lea     rcx, [rsp+78h+TokenInformation+4]
0x1401caeaf  mov     rdx, rdi; SubjectSecurityContext
0x1401caeb2  mov     [rsp+78h+GrantedAccess], rcx; GrantedAccess
0x1401caeb7  lea     rcx, TcpipEndpointCreationSdData; SecurityDescriptor
0x1401caebe  mov     [rsp+78h+AccessMode], 1; AccessMode
0x1401caec3  mov     [rsp+78h+GenericMapping], rax; GenericMapping
0x1401caec8  mov     [rsp+78h+Privileges], r14; Privileges
0x1401caecd  mov     [rsp+78h+PreviouslyGrantedAccess], r14d; PreviouslyGrantedAccess
0x1401caed2  call    cs:__imp_SeAccessCheck
0x1401caed9  nop     dword ptr [rax+rax+00h]
0x1401caede  test    al, al
0x1401caee0  jnz     loc_1400BA53B
0x1401caee6  mov     r8d, [rsp+78h+arg_18]
0x1401caeee  test    r8d, r8d
0x1401caef1  jz      loc_1400BA53B
0x1401caef7  lea     rdx, aSeaccesscheck; "SeAccessCheck"
0x1401caefe  call    WfpReportSysErrorAsNtStatus
0x1401caf03  mov     rbx, rax
0x1401caf06  test    rax, rax
0x1401caf09  jz      loc_1400BA53B
0x1401caf0f  mov     rax, cs:WPP_GLOBAL_Control
0x1401caf16  lea     rcx, WPP_GLOBAL_Control
0x1401caf1d  cmp     rax, rcx
0x1401caf20  jz      short loc_1401CAF70
0x1401caf22  cmp     byte ptr [rax+29h], 2
0x1401caf26  jb      short loc_1401CAF70
0x1401caf28  test    dword ptr [rax+2Ch], 10000h
0x1401caf2f  jz      short loc_1401CAF70
0x1401caf31  mov     rcx, rbp; Process
0x1401caf34  call    cs:__imp_PsGetProcessId
0x1401caf3b  nop     dword ptr [rax+rax+00h]
0x1401caf40  mov     edx, [rsi+30h]
0x1401caf43  mov     r9, rsi
0x1401caf46  mov     rcx, [rsi+160h]
0x1401caf4d  mov     [rsp+78h+GenericMapping], rcx
0x1401caf52  mov     rcx, cs:WPP_GLOBAL_Control
0x1401caf59  shr     edx, 4
0x1401caf5c  and     edx, 1
0x1401caf5f  mov     dword ptr [rsp+78h+Privileges], eax
0x1401caf63  mov     [rsp+78h+PreviouslyGrantedAccess], edx
0x1401caf67  mov     rcx, [rcx+18h]
0x1401caf6b  call    WPP_SF_qldq
0x1401caf70  lea     rdx, aWfpaleendpoint_0; "WfpAleEndpointCreationAccessCheck"
0x1401caf77  mov     rcx, rbx
0x1401caf7a  call    WfpReportError
0x1401caf7f  nop
0x1401caf80  jmp     loc_1400BA53B
```
