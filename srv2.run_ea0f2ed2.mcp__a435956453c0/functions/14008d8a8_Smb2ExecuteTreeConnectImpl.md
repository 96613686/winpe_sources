# Smb2ExecuteTreeConnectImpl

- ea: `0x14008d8a8`
- end: `0x14008eb8b`
- name: `Smb2ExecuteTreeConnectImpl`
- size: `4835`
- prototype: ``
- caller_count: `1`
- callee_count: `40`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14008d880`

## callees

- `0x140004dcc`
- `0x140005070`
- `0x140007400`
- `0x140007900`
- `0x140015354`
- `0x140015960`
- `0x14001a554`
- `0x14001ae40`
- `0x14002019c`
- `0x1400222ec`
- `0x140022690`
- `0x140022958`
- `0x1400229ac`
- `0x140022ad8`
- `0x140025750`
- `0x14002fcd0`
- `0x14002fee4`
- `0x140031e2c`
- `0x140032030`
- `0x140032118`
- `0x140032498`
- `0x140032510`
- `0x1400325f8`
- `0x140037f34`
- `0x140038490`
- `0x140038680`
- `0x140038980`
- `0x14006479c`
- `0x140068560`
- `0x140072e44`
- `0x140077390`
- `0x140077650`
- `0x14007c8d0`
- `0x140085d50`
- `0x14008b540`
- `0x14008d8a8`
- `0x1400917ac`
- `0x140091874`
- `0x1400952cc`
- `0x140095fd8`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x14008e41c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14008e468`
- `ntoskrnl!ExReleaseResourceLite` at `0x14008e41c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14008e468`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14008e3df`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14008e3df`
- `ntoskrnl!ObfDereferenceObject` at `0x14008e192`
- `ntoskrnl!ObfDereferenceObject` at `0x14008ea49`
- `ntoskrnl!ObfDereferenceObject` at `0x14008e192`
- `ntoskrnl!ObfDereferenceObject` at `0x14008ea49`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008ea23`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008ea23`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14008def9`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14008def9`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14008df8a`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14008df8a`
- `ntoskrnl!ObReferenceObjectByHandleWithTag` at `0x14008e095`
- `ntoskrnl!ObReferenceObjectByHandleWithTag` at `0x14008e095`
- `srvnet!SrvLibTruncateDnsName` at `0x14008de70`
- `srvnet!SrvLibTruncateDnsName` at `0x14008de70`
- `srvnet!SrvAdminNodeGetSignature` at `0x14008d938`
- `srvnet!SrvAdminNodeGetSignature` at `0x14008d938`
- `srvnet!SrvAdminSetSessionFlags` at `0x14008e286`
- `srvnet!SrvAdminSetSessionFlags` at `0x14008e286`
- `srvnet!SrvAdminNodeVerifySignature` at `0x14008dc8b`
- `srvnet!SrvAdminNodeVerifySignature` at `0x14008dc8b`
- `srvnet!SrvAdminDoesShareAllowAnonymous` at `0x14008db79`
- `srvnet!SrvAdminDoesShareAllowAnonymous` at `0x14008db79`
- `srvnet!SrvLibAuditShareConnect` at `0x14008df7a`
- `srvnet!SrvLibAuditShareConnect` at `0x14008df7a`
- `srvnet!SrvXsConnect` at `0x14008e37e`
- `srvnet!SrvXsConnect` at `0x14008e37e`
- `srvnet!SrvXsOpenPrinter` at `0x14008e402`
- `srvnet!SrvXsOpenPrinter` at `0x14008e402`
- `srvnet!SrvNetGetConnectionTransportType` at `0x14008eacb`
- `srvnet!SrvNetGetConnectionTransportType` at `0x14008eacb`
- `srvnet!SrvLibSeAccessCheck` at `0x14008df4f`
- `srvnet!SrvLibSeAccessCheck` at `0x14008df4f`
- `ksecdd!FreeContextBuffer` at `0x14008de08`
- `ksecdd!FreeContextBuffer` at `0x14008de08`

## pseudocode

```c
__int64 __fastcall Smb2ExecuteTreeConnectImpl(_QWORD *a1)
{
  __int64 v1; // rax
  __int64 v2; // r13
  _QWORD *v3; // r14
  __int64 v4; // rax
  __int64 v5; // r12
  __int16 Signature; // di
  int ShareAndSetServerName; // eax
  unsigned int v8; // ecx
  __int64 v9; // r9
  __int64 v10; // rdx
  char *v11; // r15
  unsigned __int16 MaxClusterDialect; // ax
  __int64 v13; // r9
  unsigned __int16 v14; // bx
  int v15; // edx
  unsigned __int16 *ExtendedErrorBuffer; // rax
  int v17; // eax
  ADDRESS_FAMILY *v18; // rbx
  UCHAR v19; // al
  __int64 v20; // r10
  __int16 v21; // r11
  __int64 v22; // rax
  __int64 v23; // rdx
  char v24; // bl
  int v25; // r8d
  int v26; // edi
  char v27; // si
  __int64 *v28; // rax
  __int64 v29; // rdi
  __int64 v30; // rbx
  __int64 v31; // rdx
  PDEVICE_OBJECT v32; // rcx
  __int64 v33; // rdx
  char v34; // bl
  int v35; // r8d
  void *v36; // rcx
  NTSTATUS v37; // eax
  PDEVICE_OBJECT v38; // rcx
  __int64 v39; // rdx
  __int64 SecurityContext; // rax
  __int64 v41; // rbx
  __int64 v42; // r8
  __int64 v43; // rax
  int v44; // eax
  __int64 v45; // r9
  bool v46; // zf
  unsigned int v47; // ecx
  __int64 v48; // r8
  int v49; // ecx
  __int64 v50; // rcx
  __int64 v51; // rax
  int v52; // ecx
  __int64 v53; // rdx
  __int64 v54; // rcx
  __int64 v55; // rdx
  __int64 v56; // rcx
  unsigned __int128 v57; // rax
  __int64 v58; // rbx
  __int64 v59; // r9
  ULONG v60; // r8d
  ULONG v61; // ecx
  int v62; // edx
  ULONG v63; // r8d
  unsigned int v64; // ebx
  __int64 v65; // r9
  _DWORD *v66; // rax
  size_t v67; // r8
  _DWORD *v68; // rbx
  unsigned __int16 v69; // cx
  int v70; // r8d
  ULONG v71; // edx
  int v72; // eax
  int *v73; // rcx
  char *v74; // rbx
  unsigned __int16 v75; // r14
  int v76; // eax
  ADDRESS_FAMILY v77; // cx
  UCHAR v78; // al
  __int64 v79; // r8
  unsigned __int16 v80; // ax
  void *v81; // rcx
  char v82; // si
  int v83; // r12d
  char v84; // di
  __int64 v85; // r14
  __int16 v86; // bx
  UCHAR v87; // al
  _QWORD *v88; // r10
  __int64 v89; // rdx
  char v90; // r11
  int Tag; // [rsp+20h] [rbp-E0h]
  int Tagb; // [rsp+20h] [rbp-E0h]
  int Taga; // [rsp+20h] [rbp-E0h]
  int v95; // [rsp+38h] [rbp-C8h]
  int v96; // [rsp+48h] [rbp-B8h]
  int TreeConnect; // [rsp+80h] [rbp-80h] BYREF
  PVOID pvContextBuffer; // [rsp+88h] [rbp-78h] BYREF
  ULONG pulResult[2]; // [rsp+90h] [rbp-70h] BYREF
  HANDLE Handle; // [rsp+98h] [rbp-68h]
  __int128 v101; // [rsp+A0h] [rbp-60h] BYREF
  PVOID Token; // [rsp+B0h] [rbp-50h] BYREF
  PVOID P; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v104; // [rsp+C0h] [rbp-40h]
  int v105; // [rsp+C8h] [rbp-38h] BYREF
  int v106; // [rsp+CCh] [rbp-34h] BYREF
  _QWORD *v107; // [rsp+D0h] [rbp-30h]
  PVOID v108; // [rsp+D8h] [rbp-28h]
  __int128 v109; // [rsp+E0h] [rbp-20h] BYREF
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v111[128]; // [rsp+110h] [rbp+10h] BYREF

  v1 = a1[12];
  v2 = a1[70];
  TreeConnect = 0;
  v3 = a1;
  v107 = a1;
  *(_QWORD *)&v101 = *(_QWORD *)(v1 + 496);
  v4 = a1[39];
  pvContextBuffer = 0;
  v5 = *(_QWORD *)(v4 + 24);
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  v105 = 0;
  v109 = 0;
  memset(v111, 0, sizeof(v111));
  Handle = 0;
  Token = 0;
  v106 = 0;
  P = 0;
  Signature = SrvAdminNodeGetSignature();
  ShareAndSetServerName = Smb2FindShareAndSetServerName(
                            *(_QWORD *)(v3[8] + 160LL),
                            v2 + 208,
                            v2 + 192,
                            &pvContextBuffer,
                            v3[12],
                            *(_QWORD *)(v2 + 32),
                            1,
                            0);
  TreeConnect = ShareAndSetServerName;
  v8 = ShareAndSetServerName;
  if ( ShareAndSetServerName < 0 )
  {
    if ( ShareAndSetServerName != -1073740698 )
      goto LABEL_8;
    if ( *(_WORD *)(*(_QWORD *)(v2 + 32) + 288LL) >= 0x300u )
    {
      if ( (Signature & 0xFF00) != 0 )
        goto LABEL_8;
      v8 = -1073741620;
    }
    else
    {
      v8 = -1073741623;
    }
    TreeConnect = v8;
LABEL_8:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x13u)
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 24, &WPP_96979ddc25293f57567f1ce1635deb2d_Traceguids, v3, v8);
      v8 = TreeConnect;
    }
    v9 = 615;
    v10 = v8;
LABEL_249:
    Smb2SetError(v3, v10, "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\treecon.c", v9);
    return 0;
  }
  v11 = (char *)pvContextBuffer;
  v104 = 0;
  v108 = pvContextBuffer;
  if ( *((_BYTE *)pvContextBuffer + 278) )
  {
    TreeConnect = -1073741225;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x13u)
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        25,
        &WPP_96979ddc25293f57567f1ce1635deb2d_Traceguids,
        v3,
        -1073741225);
    }
    goto LABEL_237;
  }
  if ( *((_DWORD *)pvContextBuffer + 92) )
  {
    if ( !*(_BYTE *)(v2 + 244) )
    {
      MaxClusterDialect = Smb2GetMaxClusterDialect((unsigned int)ShareAndSetServerName);
      v14 = MaxClusterDialect;
      v15 = *(unsigned __int16 *)(*(_QWORD *)(v2 + 32) + 288LL);
      if ( (unsigned __int16)v15 > MaxClusterDialect )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x13u)
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_qDD(
            WPP_GLOBAL_Control->AttachedDevice,
            26,
            &WPP_96979ddc25293f57567f1ce1635deb2d_Traceguids,
            v3,
            v15,
            MaxClusterDialect);
        }
        LOBYTE(v13) = 1;
        ExtendedErrorBuffer = (unsigned __int16 *)Smb2AllocateExtendedErrorBuffer(v3, 0, 2, v13);
        if ( ExtendedErrorBuffer )
        {
          *ExtendedErrorBuffer = v14;
          v17 = -1067646975;
          goto LABEL_32;
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x13u)
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 27, &WPP_96979ddc25293f57567f1ce1635deb2d_Traceguids, v3);
        }
LABEL_30:
        v17 = -1073741670;
LABEL_32:
        TreeConnect = v17;
        goto LABEL_237;
      }
    }
  }
  if ( *(_BYTE *)(*(_QWORD *)(v2 + 32) + 273LL)
    && *((_DWORD *)v11 + 71) != 1
    && !(unsigned __int8)SrvAdminDoesShareAllowAnonymous(v2 + 208) )
  {
    if ( Microsoft_Windows_SMBServerEnableBits < 0 )
    {
      v18 = (ADDRESS_FAMILY *)(v3[12] + 216LL);
      v19 = SOCKADDR_SIZE(*v18);
      McTemplateK0hzr0hzr2qbr4hzr6_EtwWriteTransfer(
        *((_WORD *)v11 + 60) >> 1,
        v19,
        (_DWORD)v3 + 584,
        *((_WORD *)v11 + 52) >> 1,
        *((_QWORD *)v11 + 14),
        *((_WORD *)v11 + 60) >> 1,
        *((_QWORD *)v11 + 16),
        v19,
        (__int64)v18,
        v21,
        *(_QWORD *)(v20 + 368));
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x13u)
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 28, &WPP_96979ddc25293f57567f1ce1635deb2d_Traceguids, v3);
    }
LABEL_42:
    TreeConnect = -1073741790;
    goto LABEL_237;
  }
  if ( (*((_DWORD *)v11 + 72) & 0x4000) != 0 )
  {
    v22 = v3[8];
    v23 = *(_QWORD *)(v2 + 32);
    LODWORD(pvContextBuffer) = 0;
    *(_QWORD *)pulResult = 0;
    RfsTable64GetEntrySignature(**(_QWORD **)(v22 + 160), v23, pulResult);
    v24 = pulResult[0];
    if ( !(unsigned __int8)SrvAdminNodeVerifySignature(*(_QWORD *)pulResult, &pvContextBuffer)
      || !(_DWORD)pvContextBuffer )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x13u)
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_qqZDI(
          WPP_GLOBAL_Control->AttachedDevice,
          (_DWORD)pvContextBuffer,
          v25,
          (_DWORD)v3,
          *(_QWORD *)(v2 + 32),
          (__int64)(v11 + 72),
          (char)pvContextBuffer,
          v24);
      }
      Smb2CloseSessionEx(*(_QWORD *)(v2 + 32), 0, 0);
      *((_BYTE *)v3 + 474) = 1;
      TreeConnect = -1073741309;
      goto LABEL_237;
    }
  }
  v26 = 8;
  if ( (*((_DWORD *)v11 + 72) & 0x8000) != 0 )
  {
    if ( (*(_BYTE *)(v101 + 49) & 8) != 0 )
    {
      v27 = 1;
      goto LABEL_67;
    }
    if ( !Smb2AllowUnencryptedAccess )
    {
      pvContextBuffer = 0;
      v101 = 0u;
      Smb2GetUserName(v2, &pvContextBuffer, &v101);
      if ( (byte_14004C339 & 0x40) != 0 )
      {
        v28 = *(__int64 **)(v2 + 32);
        if ( v28 )
          v29 = *v28;
        else
          LOBYTE(v29) = 0;
        v30 = v3[12];
        v96 = *(_WORD *)(v30 + 216) != 0 ? 2 : 0;
        McTemplateK0hzr0hzr2hzr4qbr6ih_EtwWriteTransfer(
          v96,
          (unsigned __int16)v101 >> 1,
          (_DWORD)v3 + 584,
          *((_WORD *)v11 + 36) >> 1,
          *((_QWORD *)v11 + 10),
          *(_WORD *)(v30 + 360) >> 1,
          *(_QWORD *)(v30 + 368),
          (unsigned __int16)v101 >> 1,
          *((__int64 *)&v101 + 1),
          v96,
          v30 + 216,
          v29,
          *(_WORD *)(v2 + 14));
      }
      if ( pvContextBuffer )
        FreeContextBuffer(pvContextBuffer);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 30, &WPP_96979ddc25293f57567f1ce1635deb2d_Traceguids);
      }
      goto LABEL_42;
    }
  }
  v27 = 0;
LABEL_67:
  v109 = *(_OWORD *)(v2 + 192);
  SrvLibTruncateDnsName(&v109);
  TreeConnect = Smb2ImpersonateSecurityContext(*(_QWORD *)(v2 + 48));
  if ( TreeConnect < 0 )
  {
    v32 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || !_bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x13u)
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_237;
    }
    v33 = 32;
    goto LABEL_72;
  }
  LOBYTE(Tag) = 1;
  LOBYTE(v31) = 7;
  SRV2_PERF_ENTER_EX(v3 + 73, v31, 903, "Smb2ExecuteTreeConnectImpl", Tag);
  SeCaptureSubjectContext(&SubjectContext);
  LOBYTE(v95) = 1;
  LOBYTE(Tagb) = SrvLibSeAccessCheck(
                   *((_QWORD *)v11 + 32),
                   &SubjectContext,
                   0,
                   1,
                   0,
                   0,
                   &Smb2ShareConnectMapping,
                   v95,
                   &v105,
                   v111,
                   &TreeConnect);
  v34 = Tagb;
  SrvLibAuditShareConnect(v11 + 104, v3[12] + 216LL, v11 + 120, 1, Tagb);
  SeReleaseSubjectContext(&SubjectContext);
  if ( !v34 )
  {
    Smb2Revert();
    v32 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || !_bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x13u)
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_237;
    }
    v33 = 33;
LABEL_72:
    WPP_SF_q(v32->AttachedDevice, v33, &WPP_96979ddc25293f57567f1ce1635deb2d_Traceguids, v3);
    goto LABEL_237;
  }
  LOBYTE(Taga) = 1;
  SRV2_PERF_ENTER_EX(v3 + 73, 0, 936, "Smb2ExecuteTreeConnectImpl", Taga);
  Smb2Revert();
  v36 = *(void **)(v2 + 232);
  if ( v36 && (*((_DWORD *)v11 + 72) & 0x40000) != 0 )
  {
    v37 = SmbCamGetToken(v36, *(unsigned int *)(v2 + 240));
    TreeConnect = v37;
    if ( v37 < 0 )
    {
      v38 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || !_bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x13u)
        || !BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        goto LABEL_237;
      }
      v39 = 34;
      goto LABEL_85;
    }
    v37 = ObReferenceObjectByHandleWithTag(Handle, 0xF01FFu, 0, 0, 0x4F424D53u, &Token, 0);
    TreeConnect = v37;
    if ( v37 < 0 )
    {
      Token = 0;
      v38 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || !_bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x13u)
        || !BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        goto LABEL_237;
      }
      v39 = 35;
      goto LABEL_85;
    }
    v37 = Smb2ImpersonateTunneledAccessToken(Token);
    TreeConnect = v37;
    if ( v37 < 0 )
    {
      v38 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || !_bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x13u)
        || !BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        goto LABEL_237;
      }
      v39 = 36;
      goto LABEL_85;
    }
    SecurityContext = Smb2AllocateSecurityContext();
    v104 = SecurityContext;
    v41 = SecurityContext;
    if ( !SecurityContext )
    {
      Smb2Revert();
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x13u)
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 37, &WPP_96979ddc25293f57567f1ce1635deb2d_Traceguids, v3);
      }
      TreeConnect = -1073741307;
      goto LABEL_237;
    }
    Smb2SecurityContextCaptureThreadToken(SecurityContext);
    Smb2Revert();
    ObfDereferenceObject(Token);
    Token = 0;
    if ( !*(_BYTE *)(v41 + 24) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x13u)
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 38, &WPP_96979ddc25293f57567f1ce1635deb2d_Traceguids, v3);
      }
      TreeConnect = -1073741732;
      goto LABEL_237;
    }
  }
  else
  {
    v41 = v104;
  }
  LOBYTE(v35) = *(_BYTE *)(v2 + 245);
  TreeConnect = Smb2AllocateTreeConnect((_DWORD)v3, (_DWORD)v11, v35, 0, (__int64)&v109, (__int64)&P, v27);
  if ( TreeConnect >= 0 )
  {
    if ( (*((_DWORD *)v11 + 72) & 0x200000) != 0 )
      *(_BYTE *)(*(_QWORD *)(v2 + 56) + 92LL) = 1;
    v43 = *(_QWORD *)(v2 + 56);
    v104 = 0;
    *(_QWORD *)(v43 + 120) = v41;
    if ( (*(_DWORD *)(*(_QWORD *)(v2 + 56) + 84LL) & 0x1000000) != 0 )
    {
      *(_BYTE *)(v3[12] + 509LL) = 1;
      *(_BYTE *)(*(_QWORD *)(v2 + 32) + 285LL) = 1;
      v37 = SrvAdminSetSessionFlags(*(_QWORD *)(*(_QWORD *)(v2 + 32) + 64LL), *(unsigned __int8 *)v3[8], 4);
      TreeConnect = v37;
      if ( v37 < 0 )
      {
        v38 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || !_bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x13u)
          || !BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          goto LABEL_237;
        }
        v39 = 39;
        goto LABEL_85;
      }
    }
    *(_WORD *)(v5 + 64) = 16;
    v44 = Smb2MapSharePropertyToShareFlag(
            *(unsigned __int16 *)(*(_QWORD *)(v2 + 32) + 288LL),
            (unsigned int)(*((_DWORD *)v11 + 72) | *((_DWORD *)v11 + 73)));
    v46 = Smb2CompressionDisabled == 0;
    *(_DWORD *)(v5 + 68) = v44;
    if ( v46 )
    {
      if ( !Smb2EnableCompressedTraffic || *(_BYTE *)v3[8] )
      {
LABEL_124:
        *(_BYTE *)(v5 + 67) = 0;
        v48 = 1;
        *(_DWORD *)(v5 + 36) = *(_DWORD *)(*(_QWORD *)(v2 + 56) + 72LL);
        v49 = *(_DWORD *)(*(_QWORD *)(v2 + 56) + 76LL);
        if ( v49 == 1 )
        {
          *(_BYTE *)(v5 + 66) = 2;
          goto LABEL_142;
        }
        if ( v49 == 127 )
        {
          *(_BYTE *)(v5 + 66) = 3;
          if ( !Smb2XsInitialized )
          {
            v37 = SrvXsConnect(&Smb2XsProtocolName);
            TreeConnect = v37;
            if ( v37 < 0 )
            {
              v38 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                || !_bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x13u)
                || !BYTE1(WPP_GLOBAL_Control->Timer) )
              {
                goto LABEL_237;
              }
              v39 = 40;
              goto LABEL_85;
            }
            Smb2XsInitialized = 1;
          }
          ExAcquireResourceExclusiveLite((PERESOURCE)(*(_QWORD *)v11 + 96LL), 1u);
          if ( !*((_QWORD *)v11 + 45) )
          {
            TreeConnect = SrvXsOpenPrinter(v11 + 152, v11 + 360, &v106);
            if ( TreeConnect < 0 )
            {
              ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)v11 + 96LL));
              v38 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                || !_bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x13u)
                || !BYTE1(WPP_GLOBAL_Control->Timer) )
              {
                goto LABEL_237;
              }
              v37 = TreeConnect;
              v39 = 41;
LABEL_85:
              WPP_SF_qD(v38->AttachedDevice, v39, &WPP_96979ddc25293f57567f1ce1635deb2d_Traceguids, v3, v37);
              goto LABEL_237;
            }
          }
          ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)v11 + 96LL));
        }
        else
        {
          v52 = Smb2HashCacheLevel;
          *(_BYTE *)(v5 + 66) = 1;
          if ( v52 == 1 || (v53 = *(_QWORD *)(v2 + 56), *(_BYTE *)(*(_QWORD *)(v53 + 96) + 280LL)) )
          {
            *(_DWORD *)(v5 + 68) &= 0xFFFF9FFF;
LABEL_142:
            *(_DWORD *)(v5 + 72) = 0;
            v50 = *(_QWORD *)(v2 + 56);
            v51 = *(_QWORD *)(v50 + 96);
            if ( *(_BYTE *)(v51 + 276) || *(_BYTE *)(v51 + 277) )
            {
              *(_DWORD *)(v5 + 72) = 8;
              v50 = *(_QWORD *)(v2 + 56);
            }
            else
            {
              v26 = 0;
            }
            if ( *(_WORD *)(*(_QWORD *)(v2 + 32) + 288LL) >= 0x300u && *(_DWORD *)(v50 + 76) != 1 )
            {
              if ( (*(_DWORD *)(v50 + 84) & 0xE000000) != 0 )
              {
                v26 |= 0x40u;
                *(_DWORD *)(v5 + 72) = v26;
              }
              if ( _bittest((const signed __int32 *)(*(_QWORD *)(v2 + 56) + 84LL), 0x1Au) )
              {
                v26 |= 0x20u;
                *(_DWORD *)(v5 + 72) = v26;
              }
              v54 = *(_QWORD *)(v2 + 56);
              if ( !*(_DWORD *)(v54 + 76) && (*(_DWORD *)(v54 + 80) & 0x4000) != 0 )
              {
                *(_DWORD *)(v5 + 72) = v45 | v26;
                v54 = *(_QWORD *)(v2 + 56);
              }
              v55 = 770;
              if ( *(_WORD *)(*(_QWORD *)(v2 + 32) + 288LL) >= 0x302u
                && _bittest((const signed __int32 *)(v54 + 84), 0x1Au)
                && (unsigned __int8)Smb2ShareCheckForAsymmetry(*(_QWORD *)(v54 + 96), 770, v48, v45) )
              {
                *(_DWORD *)(v5 + 72) |= 0x80u;
              }
              if ( Smb2SyncRedirectEnabled )
              {
                if ( *(_WORD *)(*(_QWORD *)(v2 + 32) + 288LL) >= 0x311u )
                {
                  v56 = *(_QWORD *)(v2 + 56);
                  if ( _bittest((const signed __int32 *)(v56 + 84), 0x1Au) )
                  {
                    if ( (unsigned __int8)Smb2ShareCheckForAsymmetry(*(_QWORD *)(v56 + 96), v55, v48, v45)
                      && *(_BYTE *)(v2 + 245) )
                    {
                      *(_DWORD *)(v5 + 72) |= 0x100u;
                    }
                  }
                }
              }
            }
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x13u)
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            {
              WPP_SF_qD(
                WPP_GLOBAL_Control->AttachedDevice,
                42,
                &WPP_96979ddc25293f57567f1ce1635deb2d_Traceguids,
                v3,
                *(_DWORD *)(v5 + 72));
            }
            *(_DWORD *)(v5 + 76) = *(_DWORD *)(*(_QWORD *)(v2 + 56) + 136LL);
            *(_DWORD *)(v3[39] + 36LL) = 80;
            TreeConnect = 0;
            goto LABEL_237;
          }
          if ( v52 == 2 || !v52 && (*(_DWORD *)(v53 + 80) & 0x2000) != 0 )
          {
            switch ( Smb2HashSupportVersion )
            {
              case 1:
                *(_DWORD *)(v5 + 68) = *(_DWORD *)(v5 + 68) & 0xFFFF9FFF | 0x2000;
                break;
              case 2:
                if ( *(_WORD *)(*(_QWORD *)(v2 + 32) + 288LL) >= 0x300u )
                  *(_DWORD *)(v5 + 68) |= 0x4000u;
                *(_DWORD *)(v5 + 68) &= ~0x2000u;
                break;
              case 3:
                if ( *(_WORD *)(*(_QWORD *)(v2 + 32) + 288LL) >= 0x300u )
                  *(_DWORD *)(v5 + 68) |= 0x4000u;
                *(_DWORD *)(v5 + 68) |= 0x2000u;
                break;
            }
          }
        }
        v45 = 16;
        goto LABEL_142;
      }
      v47 = v44 | 0x100000;
    }
    else
    {
      v47 = v44 & 0xFFEFFFFF;
    }
    *(_DWORD *)(v5 + 68) = v47;
    goto LABEL_124;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x13u)
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_qqdd(
      WPP_GLOBAL_Control->AttachedDevice,
      *(unsigned __int8 *)(v2 + 245),
      v42,
      v3,
      P,
      *(unsigned __int8 *)(v2 + 245),
      TreeConnect);
  }
  if ( P && *((_DWORD *)P + 11) + *((_DWORD *)P + 12) == *((_DWORD *)P + 13) && TreeConnect == -1073741620 )
  {
    pulResult[0] = 0;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qDDD(
        WPP_GLOBAL_Control->AttachedDevice,
        44,
        &WPP_96979ddc25293f57567f1ce1635deb2d_Traceguids,
        v11,
        *((_DWORD *)P + 6),
        *((_DWORD *)P + 3),
        *((_DWORD *)P + 4));
    }
    LODWORD(pvContextBuffer) = *((unsigned __int16 *)v11 + 52);
    v57 = *((unsigned int *)P + 12) * (unsigned __int128)0x2492492492492493uLL;
    v58 = (unsigned __int16)((*((_QWORD *)&v57 + 1)
                            + (((unsigned __int64)*((unsigned int *)P + 12) - *((_QWORD *)&v57 + 1)) >> 1)) >> 4);
    if ( RtlULongLongToULong(24 * v58, pulResult) == -1073741675 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x13u)
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_qDD(
          WPP_GLOBAL_Control->AttachedDevice,
          45,
          &WPP_96979ddc25293f57567f1ce1635deb2d_Traceguids,
          v59,
          v58,
          -1073741675);
      }
      LODWORD(v58) = 0;
      v60 = 0;
    }
    else
    {
      v60 = pulResult[0];
    }
    pulResult[0] = v60;
    LODWORD(Handle) = v58;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x13u)
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_DD(
        WPP_GLOBAL_Control->AttachedDevice,
        46,
        &WPP_96979ddc25293f57567f1ce1635deb2d_Traceguids,
        (unsigned __int16)v58,
        v60);
    }
    v61 = (unsigned __int16)pvContextBuffer + pulResult[0];
    if ( v61 >= (unsigned __int16)pvContextBuffer )
      v62 = (int)Handle;
    else
      v62 = 0;
    if ( v61 < (unsigned __int16)pvContextBuffer )
      v61 = (unsigned __int16)pvContextBuffer;
    v63 = v61 + 48;
    if ( v61 + 48 < v61 )
      LODWORD(pvContextBuffer) = 0;
    v64 = v61 + 48;
    v65 = 48;
    if ( v63 < v61 )
      v64 = 48;
    LOBYTE(v65) = 1;
    if ( v63 < v61 )
      LOWORD(v62) = 0;
    LODWORD(Handle) = v62;
    v66 = (_DWORD *)Smb2AllocateExtendedErrorBuffer(v3, 1919177299, v64, v65);
    v67 = v64;
    v68 = v66;
    memset(v66, 0, v67);
    if ( !v68 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x13u)
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 47, &WPP_96979ddc25293f57567f1ce1635deb2d_Traceguids, v3, 0);
      }
      goto LABEL_30;
    }
    v69 = (unsigned __int16)pvContextBuffer;
    v70 = (unsigned __int16)Handle;
    v71 = pulResult[0] + 48;
    v72 = (unsigned __int16)pvContextBuffer;
    *v68 = 48;
    v68[1] = 3;
    v68[4] = 0;
    v68[2] = v71;
    v68[3] = v72;
    v68[5] = v70;
    if ( v69 )
    {
      memmove((char *)v68 + v71, *((const void **)v11 + 14), v69);
      LOWORD(v70) = (_WORD)Handle;
    }
    v73 = v68 + 6;
    *(_QWORD *)pulResult = v68 + 6;
    LODWORD(pvContextBuffer) = 0;
    v74 = (char *)P + *((unsigned int *)P + 11);
    if ( (_WORD)v70 )
    {
      v75 = 0;
      do
      {
        if ( *(_WORD *)v74 == 23 )
        {
          v76 = 2;
          *(_OWORD *)(v73 + 2) = *(_OWORD *)(v74 + 8);
        }
        else
        {
          *(_OWORD *)v73 = 0;
          *((_QWORD *)v73 + 2) = 0;
          v73[2] = *((_DWORD *)v74 + 1);
          v76 = 1;
        }
        *v73 = v76;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x13u)
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          v77 = *(_WORD *)v74;
          v101 = (unsigned __int64)v74;
          v78 = SOCKADDR_SIZE(v77);
          WORD4(v101) = v78;
          WPP_SF_d_SOCKADDR_(*(_QWORD *)(v79 + 24), v78, v79, v75, (__int64)&v101);
          v73 = *(int **)pulResult;
        }
        v80 = (unsigned __int16)Handle;
        v74 += 28;
        v73[1] = 0;
        ++v75;
        v73 += 6;
        *(_QWORD *)pulResult = v73;
      }
      while ( v75 < v80 );
      v3 = v107;
    }
  }
LABEL_237:
  if ( v11 )
    Smb2DereferenceShare(v11);
  if ( P )
    ExFreePoolWithTag(P, 0x6232534Cu);
  if ( v104 )
    Smb2DereferenceSecurityContext(v104);
  if ( Token )
  {
    ObfDereferenceObject(Token);
    Token = 0;
  }
  if ( TreeConnect < 0 )
  {
    v81 = *(void **)(v2 + 56);
    if ( v81 )
      Smb2CloseTreeConnect(v81);
    v10 = (unsigned int)TreeConnect;
    v9 = 1431;
    goto LABEL_249;
  }
  Smb2SetSuccess(v3, (unsigned int)TreeConnect);
  if ( (byte_14004C33C & 0x10) != 0 )
  {
    v82 = *(_BYTE *)(*(_QWORD *)(v2 + 56) + 90LL);
    v83 = (*(_DWORD *)(v5 + 68) >> 20) & 1;
    v84 = *(_BYTE *)(*(_QWORD *)(v2 + 32) + 57LL);
    SrvNetGetConnectionTransportType(*(_QWORD *)(v3[12] + 480LL));
    v85 = v3[12];
    v86 = *(_WORD *)(v85 + 360) >> 1;
    v87 = SOCKADDR_SIZE(*(_WORD *)(v85 + 216));
    McTemplateK0hzr0qbr2hzr4xqqttt_EtwWriteTransfer(
      v87,
      v89,
      (_DWORD)v107 + 584,
      *((_WORD *)v108 + 36) >> 1,
      *((_QWORD *)v108 + 10),
      v87,
      v85 + 216,
      v86,
      *(_QWORD *)(v85 + 368),
      *v88,
      *(_DWORD *)(v89 + 72),
      v90,
      v84,
      v82,
      v83);
  }
  return 0;
}

```

## disassembly

```asm
0x14008d8a8  push    rbp
0x14008d8aa  push    rbx
0x14008d8ab  push    rsi
0x14008d8ac  push    rdi
0x14008d8ad  push    r12
0x14008d8af  push    r13
0x14008d8b1  push    r14
0x14008d8b3  push    r15
0x14008d8b5  lea     rbp, [rsp-0A8h]
0x14008d8bd  sub     rsp, 1A8h
0x14008d8c4  mov     rax, cs:__security_cookie
0x14008d8cb  xor     rax, rsp
0x14008d8ce  mov     [rbp+0E0h+var_50], rax
0x14008d8d5  mov     rax, [rcx+60h]
0x14008d8d9  xorps   xmm0, xmm0
0x14008d8dc  mov     r13, [rcx+230h]
0x14008d8e3  xor     ebx, ebx
0x14008d8e5  mov     [rbp+0E0h+var_160], ebx
0x14008d8e8  mov     r14, rcx
0x14008d8eb  mov     [rbp+0E0h+var_110], rcx
0x14008d8ef  xor     edx, edx; Val
0x14008d8f1  mov     rax, [rax+1F0h]
0x14008d8f8  mov     r8d, 80h; Size
0x14008d8fe  mov     qword ptr [rbp+0E0h+var_140], rax
0x14008d902  mov     rax, [rcx+138h]
0x14008d909  lea     rcx, [rbp+0E0h+var_D0]; void *
0x14008d90d  mov     [rbp+0E0h+pvContextBuffer], rbx
0x14008d911  mov     r12, [rax+18h]
0x14008d915  movups  xmmword ptr [rbp+0E0h+SubjectContext.ClientToken], xmm0
0x14008d919  mov     [rbp+0E0h+var_118], ebx
0x14008d91c  movups  xmmword ptr [rbp+0E0h+SubjectContext.PrimaryToken], xmm0
0x14008d920  movups  [rbp+0E0h+var_100], xmm0
0x14008d924  call    memset
0x14008d929  mov     [rbp+0E0h+Handle], rbx
0x14008d92d  mov     [rbp+0E0h+Token], rbx
0x14008d931  mov     [rbp+0E0h+var_114], ebx
0x14008d934  mov     [rbp+0E0h+P], rbx
0x14008d938  call    cs:__imp_SrvAdminNodeGetSignature
0x14008d93f  nop     dword ptr [rax+rax+00h]
0x14008d944  mov     rcx, [r13+20h]
0x14008d948  lea     r15d, [rbx+1]
0x14008d94c  mov     r10, [r14+40h]
0x14008d950  lea     rsi, [r13+0D0h]
0x14008d957  mov     byte ptr [rsp+1E0h+var_1A8], bl
0x14008d95b  lea     r8, [r13+0C0h]
0x14008d962  mov     byte ptr [rsp+1E0h+HandleInformation], r15b
0x14008d967  lea     r9, [rbp+0E0h+pvContextBuffer]
0x14008d96b  mov     [rsp+1E0h+Object], rcx
0x14008d970  mov     rdx, rsi
0x14008d973  mov     rcx, [r14+60h]
0x14008d977  movzx   edi, ax
0x14008d97a  mov     qword ptr [rsp+1E0h+Tag], rcx
0x14008d97f  mov     rcx, [r10+0A0h]
0x14008d986  call    Smb2FindShareAndSetServerName
0x14008d98b  mov     [rbp+0E0h+var_160], eax
0x14008d98e  mov     ecx, eax
0x14008d990  test    eax, eax
0x14008d992  jns     short loc_14008DA13
0x14008d994  cmp     eax, 0C0000466h
0x14008d999  jnz     short loc_14008D9C6
0x14008d99b  mov     rax, [r13+20h]
0x14008d99f  mov     ebx, 300h
0x14008d9a4  cmp     [rax+120h], bx
0x14008d9ab  jnb     short loc_14008D9B4
0x14008d9ad  mov     ecx, 0C00000C9h
0x14008d9b2  jmp     short loc_14008D9C3
0x14008d9b4  mov     eax, 0FF00h
0x14008d9b9  test    ax, di
0x14008d9bc  jnz     short loc_14008D9C6
0x14008d9be  mov     ecx, 0C00000CCh
0x14008d9c3  mov     [rbp+0E0h+var_160], ecx
0x14008d9c6  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14008d9cd  lea     rdi, WPP_GLOBAL_Control
0x14008d9d4  cmp     r10, rdi
0x14008d9d7  jz      short loc_14008DA06
0x14008d9d9  bt      dword ptr [r10+2Ch], 13h
0x14008d9df  jnb     short loc_14008DA06
0x14008d9e1  cmp     [r10+29h], r15b
0x14008d9e5  jb      short loc_14008DA06
0x14008d9e7  mov     [rsp+1E0h+Tag], ecx
0x14008d9eb  lea     r8, WPP_96979ddc25293f57567f1ce1635deb2d_Traceguids
0x14008d9f2  mov     rcx, [r10+18h]
0x14008d9f6  mov     edx, 18h
0x14008d9fb  mov     r9, r14
0x14008d9fe  call    WPP_SF_qD
0x14008da03  mov     ecx, [rbp+0E0h+var_160]
0x14008da06  mov     r9d, 267h
0x14008da0c  mov     edx, ecx
0x14008da0e  jmp     loc_14008EA77
0x14008da13  mov     r15, [rbp+0E0h+pvContextBuffer]
0x14008da17  mov     [rbp+0E0h+var_120], rbx
0x14008da1b  mov     [rbp+0E0h+var_108], r15
0x14008da1f  cmp     [r15+116h], bl
0x14008da26  jz      short loc_14008DA80
0x14008da28  mov     r8d, 0C0000257h
0x14008da2e  mov     [rbp+0E0h+var_160], r8d
0x14008da32  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14008da39  lea     rdi, WPP_GLOBAL_Control
0x14008da40  cmp     rcx, rdi
0x14008da43  jz      loc_14008EA03
0x14008da49  bt      dword ptr [rcx+2Ch], 13h
0x14008da4e  jnb     loc_14008EA03
0x14008da54  cmp     byte ptr [rcx+29h], 1
0x14008da58  jb      loc_14008EA03
0x14008da5e  mov     edx, 19h
0x14008da63  mov     [rsp+1E0h+Tag], r8d
0x14008da68  mov     rcx, [rcx+18h]
0x14008da6c  lea     r8, WPP_96979ddc25293f57567f1ce1635deb2d_Traceguids
0x14008da73  mov     r9, r14
0x14008da76  call    WPP_SF_qD
0x14008da7b  jmp     loc_14008EA03
0x14008da80  cmp     [r15+170h], ebx
0x14008da87  jz      loc_14008DB58
0x14008da8d  cmp     [r13+0F4h], bl
0x14008da94  jnz     loc_14008DB58
0x14008da9a  call    Smb2GetMaxClusterDialect
0x14008da9f  mov     rcx, [r13+20h]
0x14008daa3  movzx   ebx, ax
0x14008daa6  movzx   edx, word ptr [rcx+120h]
0x14008daad  cmp     dx, bx
0x14008dab0  jbe     loc_14008DB56
0x14008dab6  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14008dabd  lea     rdi, WPP_GLOBAL_Control
0x14008dac4  cmp     rcx, rdi
0x14008dac7  jz      short loc_14008DAFA
0x14008dac9  bt      dword ptr [rcx+2Ch], 13h
0x14008dace  jnb     short loc_14008DAFA
0x14008dad0  cmp     byte ptr [rcx+29h], 1
0x14008dad4  jb      short loc_14008DAFA
0x14008dad6  mov     rcx, [rcx+18h]
0x14008dada  mov     r8d, edx
0x14008dadd  mov     dword ptr [rsp+1E0h+Object], ebx
0x14008dae1  mov     edx, 1Ah
0x14008dae6  mov     [rsp+1E0h+Tag], r8d
0x14008daeb  mov     r9, r14
0x14008daee  lea     r8, WPP_96979ddc25293f57567f1ce1635deb2d_Traceguids
0x14008daf5  call    WPP_SF_qDD
0x14008dafa  xor     edx, edx
0x14008dafc  mov     r9b, 1
0x14008daff  mov     rcx, r14
0x14008db02  lea     r8d, [rdx+2]
0x14008db06  call    Smb2AllocateExtendedErrorBuffer
0x14008db0b  test    rax, rax
0x14008db0e  jnz     short loc_14008DB46
0x14008db10  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14008db17  cmp     rcx, rdi
0x14008db1a  jz      short loc_14008DB3F
0x14008db1c  bt      dword ptr [rcx+2Ch], 13h
0x14008db21  jnb     short loc_14008DB3F
0x14008db23  cmp     byte ptr [rcx+29h], 1
0x14008db27  jb      short loc_14008DB3F
0x14008db29  mov     rcx, [rcx+18h]
0x14008db2d  lea     edx, [rax+1Bh]
0x14008db30  mov     r9, r14
0x14008db33  lea     r8, WPP_96979ddc25293f57567f1ce1635deb2d_Traceguids
0x14008db3a  call    WPP_SF_q
0x14008db3f  mov     eax, 0C000009Ah
0x14008db44  jmp     short loc_14008DB4E
0x14008db46  mov     [rax], bx
0x14008db49  mov     eax, 0C05D0001h
0x14008db4e  mov     [rbp+0E0h+var_160], eax
0x14008db51  jmp     loc_14008EA03
0x14008db56  xor     ebx, ebx
0x14008db58  mov     rax, [r13+20h]
0x14008db5c  cmp     [rax+111h], bl
0x14008db62  jz      loc_14008DC4D
0x14008db68  cmp     dword ptr [r15+11Ch], 1
0x14008db70  jz      loc_14008DC4D
0x14008db76  mov     rcx, rsi
0x14008db79  call    cs:__imp_SrvAdminDoesShareAllowAnonymous
0x14008db80  nop     dword ptr [rax+rax+00h]
0x14008db85  test    al, al
0x14008db87  jnz     loc_14008DC4D
0x14008db8d  cmp     cs:Microsoft_Windows_SMBServerEnableBits, bl
0x14008db93  jge     short loc_14008DC09
0x14008db95  mov     r10, [r14+60h]
0x14008db99  movzx   r11d, word ptr [r10+168h]
0x14008dba1  lea     rbx, [r10+0D8h]
0x14008dba8  movzx   ecx, word ptr [rbx]; af
0x14008dbab  shr     r11w, 1
0x14008dbaf  call    SOCKADDR_SIZE
0x14008dbb4  movzx   ecx, word ptr [r15+78h]
0x14008dbb9  lea     r8, [r14+248h]
0x14008dbc0  movzx   r9d, word ptr [r15+68h]
0x14008dbc5  movzx   edx, al
0x14008dbc8  mov     rax, [r10+170h]
0x14008dbcf  mov     [rsp+1E0h+var_190], rax
0x14008dbd4  mov     rax, [r15+80h]
0x14008dbdb  mov     word ptr [rsp+1E0h+var_198], r11w
0x14008dbe1  mov     [rsp+1E0h+var_1A0], rbx
0x14008dbe6  mov     dword ptr [rsp+1E0h+var_1A8], edx
0x14008dbea  mov     [rsp+1E0h+HandleInformation], rax
0x14008dbef  mov     rax, [r15+70h]
0x14008dbf3  shr     cx, 1
0x14008dbf6  mov     word ptr [rsp+1E0h+Object], cx
0x14008dbfb  shr     r9w, 1
0x14008dbff  mov     qword ptr [rsp+1E0h+Tag], rax
0x14008dc04  call    McTemplateK0hzr0hzr2qbr4hzr6_EtwWriteTransfer
0x14008dc09  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14008dc10  lea     rdi, WPP_GLOBAL_Control
0x14008dc17  cmp     rcx, rdi
0x14008dc1a  jz      short loc_14008DC41
0x14008dc1c  bt      dword ptr [rcx+2Ch], 13h
0x14008dc21  jnb     short loc_14008DC41
0x14008dc23  cmp     byte ptr [rcx+29h], 1
0x14008dc27  jb      short loc_14008DC41
0x14008dc29  mov     rcx, [rcx+18h]
0x14008dc2d  lea     r8, WPP_96979ddc25293f57567f1ce1635deb2d_Traceguids
0x14008dc34  mov     edx, 1Ch
0x14008dc39  mov     r9, r14
0x14008dc3c  call    WPP_SF_q
0x14008dc41  mov     [rbp+0E0h+var_160], 0C0000022h
0x14008dc48  jmp     loc_14008EA03
0x14008dc4d  test    dword ptr [r15+120h], 4000h
0x14008dc58  jz      loc_14008DD0D
0x14008dc5e  mov     rax, [r14+40h]
0x14008dc62  lea     r8, [rbp+0E0h+pulResult]
0x14008dc66  mov     rdx, [r13+20h]
0x14008dc6a  mov     dword ptr [rbp+0E0h+pvContextBuffer], ebx
0x14008dc6d  mov     qword ptr [rbp+0E0h+pulResult], rbx
0x14008dc71  mov     rcx, [rax+0A0h]
0x14008dc78  mov     rcx, [rcx]
0x14008dc7b  call    RfsTable64GetEntrySignature
0x14008dc80  mov     rbx, qword ptr [rbp+0E0h+pulResult]
0x14008dc84  lea     rdx, [rbp+0E0h+pvContextBuffer]
0x14008dc88  mov     rcx, rbx
0x14008dc8b  call    cs:__imp_SrvAdminNodeVerifySignature
0x14008dc92  nop     dword ptr [rax+rax+00h]
0x14008dc97  mov     edx, dword ptr [rbp+0E0h+pvContextBuffer]
0x14008dc9a  test    al, al
0x14008dc9c  jz      short loc_14008DCA2
0x14008dc9e  test    edx, edx
0x14008dca0  jnz     short loc_14008DD0B
0x14008dca2  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14008dca9  lea     rdi, WPP_GLOBAL_Control
0x14008dcb0  cmp     rcx, rdi
0x14008dcb3  jz      short loc_14008DCE9
0x14008dcb5  bt      dword ptr [rcx+2Ch], 13h
0x14008dcba  jnb     short loc_14008DCE9
0x14008dcbc  cmp     byte ptr [rcx+29h], 1
0x14008dcc0  jb      short loc_14008DCE9
0x14008dcc2  mov     rcx, [rcx+18h]
0x14008dcc6  lea     rax, [r15+48h]
0x14008dcca  mov     [rsp+1E0h+var_1A8], rbx
0x14008dccf  mov     r9, r14
0x14008dcd2  mov     dword ptr [rsp+1E0h+HandleInformation], edx
0x14008dcd6  mov     [rsp+1E0h+Object], rax
0x14008dcdb  mov     rax, [r13+20h]
0x14008dcdf  mov     qword ptr [rsp+1E0h+Tag], rax
0x14008dce4  call    WPP_SF_qqZDI
0x14008dce9  mov     rcx, [r13+20h]
0x14008dced  xor     r8d, r8d
0x14008dcf0  xor     edx, edx
0x14008dcf2  call    Smb2CloseSessionEx
0x14008dcf7  mov     byte ptr [r14+1DAh], 1
0x14008dcff  mov     [rbp+0E0h+var_160], 0C0000203h
0x14008dd06  jmp     loc_14008EA03
0x14008dd0b  xor     ebx, ebx
0x14008dd0d  test    dword ptr [r15+120h], 8000h
0x14008dd18  mov     edi, 8
0x14008dd1d  jz      loc_14008DE5C
0x14008dd23  mov     rax, qword ptr [rbp+0E0h+var_140]
0x14008dd27  test    [rax+31h], dil
0x14008dd2b  jz      short loc_14008DD35
0x14008dd2d  mov     sil, 1
0x14008dd30  jmp     loc_14008DE5F
0x14008dd35  cmp     cs:Smb2AllowUnencryptedAccess, bl
0x14008dd3b  jnz     loc_14008DE5C
0x14008dd41  lea     r8, [rbp+0E0h+var_140]
0x14008dd45  mov     [rbp+0E0h+pvContextBuffer], rbx
0x14008dd49  lea     rdx, [rbp+0E0h+pvContextBuffer]
0x14008dd4d  mov     qword ptr [rbp+0E0h+var_140], 0
0x14008dd55  mov     rcx, r13
0x14008dd58  mov     qword ptr [rbp+0E0h+var_140+8], rbx
0x14008dd5c  call    Smb2GetUserName
0x14008dd61  test    cs:byte_14004C339, 40h
0x14008dd68  jz      loc_14008DDFF
0x14008dd6e  mov     rax, [r13+20h]
0x14008dd72  test    rax, rax
0x14008dd75  jz      short loc_14008DD7C
0x14008dd77  mov     rdi, [rax]
0x14008dd7a  jmp     short loc_14008DD7F
0x14008dd7c  mov     rdi, rbx
0x14008dd7f  mov     rbx, [r14+60h]
0x14008dd83  lea     r8, [r14+248h]
0x14008dd8a  movzx   edx, word ptr [rbp+0E0h+var_140]
0x14008dd8e  movzx   r9d, word ptr [r15+48h]
0x14008dd93  movzx   r10d, word ptr [rbx+168h]
0x14008dd9b  lea     r11, [rbx+0D8h]
0x14008dda2  movzx   eax, word ptr [r11]
0x14008dda6  neg     ax
0x14008dda9  movzx   eax, word ptr [r13+0Eh]
0x14008ddae  mov     word ptr [rsp+1E0h+var_180], ax
0x14008ddb3  sbb     ecx, ecx
0x14008ddb5  mov     rax, qword ptr [rbp+0E0h+var_140+8]
0x14008ddb9  and     ecx, 2
0x14008ddbc  mov     [rsp+1E0h+var_188], rdi
0x14008ddc1  mov     [rsp+1E0h+var_190], r11
0x14008ddc6  mov     dword ptr [rsp+1E0h+var_198], ecx
0x14008ddca  mov     [rsp+1E0h+var_1A0], rax
  ... truncated ...
```
