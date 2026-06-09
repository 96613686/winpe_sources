# WfpAleEndpointCreationAccessCheck

- ea: `0x1400ba8a0`
- end: `0x1400baa6d`
- name: `WfpAleEndpointCreationAccessCheck`
- size: `461`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400ba5dc`

## callees

- `0x140053f20`
- `0x1400ba1e0`
- `0x1400ba8a0`
- `0x1400be890`
- `0x14014cdc4`
- `0x140176ef8`

## import_xrefs

- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1400ba947`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1401cad64`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1400ba947`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1401cad64`
- `ntoskrnl!SeAccessCheck` at `0x1400ba991`
- `ntoskrnl!SeAccessCheck` at `0x1401cadae`
- `ntoskrnl!SeAccessCheck` at `0x1400ba991`
- `ntoskrnl!SeAccessCheck` at `0x1401cadae`
- `ntoskrnl!PsGetProcessId` at `0x1401cae10`
- `ntoskrnl!PsGetProcessId` at `0x1401cae10`
- `ntoskrnl!SeQueryInformationToken` at `0x1400ba8f3`
- `ntoskrnl!SeQueryInformationToken` at `0x1400ba934`
- `ntoskrnl!SeQueryInformationToken` at `0x1400ba8f3`
- `ntoskrnl!SeQueryInformationToken` at `0x1400ba934`

## string_xrefs

- `0x1400baa5c`: `InetInspectRawEndpointPerformAccessCheck`
- `0x1401cae4c`: `WfpAleEndpointCreationAccessCheck`
- `0x1401cadd3`: `SeAccessCheck`
- `0x1400baa06`: `InetInspectRawEndpointSetAccessCheckResult`

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
0x1400ba8a0  mov     rax, rsp
0x1400ba8a3  mov     [rax+8], rbx
0x1400ba8a7  mov     [rax+10h], rbp
0x1400ba8ab  push    rsi
0x1400ba8ac  push    rdi
0x1400ba8ad  push    r14
0x1400ba8af  sub     rsp, 60h
0x1400ba8b3  xor     r14d, r14d
0x1400ba8b6  mov     rdi, r8
0x1400ba8b9  mov     [rax+20h], r14d
0x1400ba8bd  mov     ebx, r14d
0x1400ba8c0  mov     [rax-24h], r14d
0x1400ba8c4  mov     rbp, rdx
0x1400ba8c7  mov     [rax-28h], r14d
0x1400ba8cb  mov     rsi, rcx
0x1400ba8ce  mov     eax, cs:Feature_5988_5730__private_featureState
0x1400ba8d4  test    al, 10h
0x1400ba8d6  jnz     loc_1400BAA12
0x1400ba8dc  call    Feature_5988_5730__private_IsEnabledDeviceUsageNoInline
0x1400ba8e1  mov     rcx, [rdi+10h]; Token
0x1400ba8e5  lea     r8, [rsp+78h+TokenInformation]; TokenInformation
0x1400ba8ea  mov     edx, 1Dh; TokenInformationClass
0x1400ba8ef  test    eax, eax
0x1400ba8f1  jnz     short loc_1400BA934
0x1400ba8f3  call    cs:__imp_SeQueryInformationToken
0x1400ba8fa  nop     dword ptr [rax+rax+00h]
0x1400ba8ff  mov     [rsp+78h+arg_18], eax
0x1400ba906  mov     eax, [rsi+30h]
0x1400ba909  test    al, 10h
0x1400ba90b  jnz     loc_1400BAA1A
0x1400ba911  cmp     dword ptr [rsp+78h+TokenInformation], ebx
0x1400ba915  jnz     loc_1401CAD64
0x1400ba91b  lea     r11, [rsp+78h+var_18]
0x1400ba920  mov     rax, rbx
0x1400ba923  mov     rbx, [r11+20h]
0x1400ba927  mov     rbp, [r11+28h]
0x1400ba92b  mov     rsp, r11
0x1400ba92e  pop     r14
0x1400ba930  pop     rdi
0x1400ba931  pop     rsi
0x1400ba932  retn
0x1400ba934  call    cs:__imp_SeQueryInformationToken
0x1400ba93b  nop     dword ptr [rax+rax+00h]
0x1400ba940  mov     [rsp+78h+arg_18], eax
0x1400ba947  call    cs:__imp_IoGetFileObjectGenericMapping
0x1400ba94e  nop     dword ptr [rax+rax+00h]
0x1400ba953  lea     rcx, [rsp+78h+arg_18]
0x1400ba95b  mov     r9d, 2; DesiredAccess
0x1400ba961  mov     [rsp+78h+AccessStatus], rcx; AccessStatus
0x1400ba966  mov     r8b, 1; SubjectContextLocked
0x1400ba969  lea     rcx, [rsp+78h+TokenInformation+4]
0x1400ba96e  mov     rdx, rdi; SubjectSecurityContext
0x1400ba971  mov     [rsp+78h+GrantedAccess], rcx; GrantedAccess
0x1400ba976  lea     rcx, TcpipEndpointCreationAdminSdData; SecurityDescriptor
0x1400ba97d  mov     [rsp+78h+AccessMode], 1; AccessMode
0x1400ba982  mov     [rsp+78h+GenericMapping], rax; GenericMapping
0x1400ba987  mov     [rsp+78h+Privileges], r14; Privileges
0x1400ba98c  mov     [rsp+78h+PreviouslyGrantedAccess], r14d; PreviouslyGrantedAccess
0x1400ba991  call    cs:__imp_SeAccessCheck
0x1400ba998  nop     dword ptr [rax+rax+00h]
0x1400ba99d  movzx   edx, al
0x1400ba9a0  test    al, al
0x1400ba9a2  jz      short loc_1400BA9A9
0x1400ba9a4  lock or dword ptr [rsi+38h], 8
0x1400ba9a9  mov     ecx, [rsi+30h]
0x1400ba9ac  test    cl, 10h
0x1400ba9af  jz      loc_1400BA911
0x1400ba9b5  mov     r9, [rsi+160h]
0x1400ba9bc  test    r9, r9
0x1400ba9bf  jz      loc_1400BA91B
0x1400ba9c5  mov     eax, [r9+40h]
0x1400ba9c9  cmp     eax, 1
0x1400ba9cc  jz      short loc_1400BA9DB
0x1400ba9ce  mov     r8d, [rsp+78h+arg_18]
0x1400ba9d6  cmp     eax, 3Ah ; ':'
0x1400ba9d9  jnz     short loc_1400BA9DE
0x1400ba9db  mov     r8d, r14d
0x1400ba9de  mov     eax, [r9+18h]
0x1400ba9e2  mov     ecx, edx
0x1400ba9e4  shl     ecx, 0Ah
0x1400ba9e7  xor     ecx, eax
0x1400ba9e9  and     ecx, 400h
0x1400ba9ef  xor     ecx, eax
0x1400ba9f1  mov     [r9+18h], ecx
0x1400ba9f5  mov     [rsp+78h+arg_18], r8d
0x1400ba9fd  test    r8d, r8d
0x1400baa00  jz      loc_1400BA91B
0x1400baa06  lea     rdx, aInetinspectraw; "InetInspectRawEndpointSetAccessCheckRes"...
0x1400baa0d  jmp     loc_1401CADDA
0x1400baa12  and     eax, 1
0x1400baa15  jmp     loc_1400BA8E1
0x1400baa1a  mov     r14, [rsi+160h]
0x1400baa21  test    r14, r14
0x1400baa24  jz      loc_1400BA91B
0x1400baa2a  mov     eax, cs:Feature_5988_5730__private_featureState
0x1400baa30  test    al, 10h
0x1400baa32  jnz     short loc_1400BAA68
0x1400baa34  call    Feature_5988_5730__private_IsEnabledDeviceUsageNoInline
0x1400baa39  test    eax, eax
0x1400baa3b  jz      short loc_1400BAA3F
0x1400baa3d  int     2Ch; Windows NT - assertion failure
0x1400baa3f  mov     rdx, rdi
0x1400baa42  mov     rcx, r14
0x1400baa45  call    RawEndpointPerformAccessCheck
0x1400baa4a  mov     [rsp+78h+arg_18], eax
0x1400baa51  test    eax, eax
0x1400baa53  jz      loc_1400BA91B
0x1400baa59  mov     r8d, eax
0x1400baa5c  lea     rdx, aInetinspectraw_0; "InetInspectRawEndpointPerformAccessChec"...
0x1400baa63  jmp     loc_1401CADDA
0x1400baa68  and     eax, 1
0x1400baa6b  jmp     short loc_1400BAA39
0x1401cad64  call    cs:__imp_IoGetFileObjectGenericMapping
0x1401cad6b  nop     dword ptr [rax+rax+00h]
0x1401cad70  lea     rcx, [rsp+78h+arg_18]
0x1401cad78  mov     r9d, 1200A9h; DesiredAccess
0x1401cad7e  mov     [rsp+78h+AccessStatus], rcx; AccessStatus
0x1401cad83  mov     r8b, 1; SubjectContextLocked
0x1401cad86  lea     rcx, [rsp+78h+TokenInformation+4]
0x1401cad8b  mov     rdx, rdi; SubjectSecurityContext
0x1401cad8e  mov     [rsp+78h+GrantedAccess], rcx; GrantedAccess
0x1401cad93  lea     rcx, TcpipEndpointCreationSdData; SecurityDescriptor
0x1401cad9a  mov     [rsp+78h+AccessMode], 1; AccessMode
0x1401cad9f  mov     [rsp+78h+GenericMapping], rax; GenericMapping
0x1401cada4  mov     [rsp+78h+Privileges], r14; Privileges
0x1401cada9  mov     [rsp+78h+PreviouslyGrantedAccess], r14d; PreviouslyGrantedAccess
0x1401cadae  call    cs:__imp_SeAccessCheck
0x1401cadb5  nop     dword ptr [rax+rax+00h]
0x1401cadba  test    al, al
0x1401cadbc  jnz     loc_1400BA91B
0x1401cadc2  mov     r8d, [rsp+78h+arg_18]
0x1401cadca  test    r8d, r8d
0x1401cadcd  jz      loc_1400BA91B
0x1401cadd3  lea     rdx, aSeaccesscheck; "SeAccessCheck"
0x1401cadda  call    WfpReportSysErrorAsNtStatus
0x1401caddf  mov     rbx, rax
0x1401cade2  test    rax, rax
0x1401cade5  jz      loc_1400BA91B
0x1401cadeb  mov     rax, cs:WPP_GLOBAL_Control
0x1401cadf2  lea     rcx, WPP_GLOBAL_Control
0x1401cadf9  cmp     rax, rcx
0x1401cadfc  jz      short loc_1401CAE4C
0x1401cadfe  cmp     byte ptr [rax+29h], 2
0x1401cae02  jb      short loc_1401CAE4C
0x1401cae04  test    dword ptr [rax+2Ch], 10000h
0x1401cae0b  jz      short loc_1401CAE4C
0x1401cae0d  mov     rcx, rbp; Process
0x1401cae10  call    cs:__imp_PsGetProcessId
0x1401cae17  nop     dword ptr [rax+rax+00h]
0x1401cae1c  mov     edx, [rsi+30h]
0x1401cae1f  mov     r9, rsi
0x1401cae22  mov     rcx, [rsi+160h]
0x1401cae29  mov     [rsp+78h+GenericMapping], rcx
0x1401cae2e  mov     rcx, cs:WPP_GLOBAL_Control
0x1401cae35  shr     edx, 4
0x1401cae38  and     edx, 1
0x1401cae3b  mov     dword ptr [rsp+78h+Privileges], eax
0x1401cae3f  mov     [rsp+78h+PreviouslyGrantedAccess], edx
0x1401cae43  mov     rcx, [rcx+18h]
0x1401cae47  call    WPP_SF_qldq
0x1401cae4c  lea     rdx, aWfpaleendpoint_0; "WfpAleEndpointCreationAccessCheck"
0x1401cae53  mov     rcx, rbx
0x1401cae56  call    WfpReportError
0x1401cae5b  nop
0x1401cae5c  jmp     loc_1400BA91B
```
