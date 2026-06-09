# Smb2ValidateSecurityBuffer

- ea: `0x140095798`
- end: `0x140095fd0`
- name: `Smb2ValidateSecurityBuffer`
- size: `2104`
- prototype: `__int64 __usercall@<rax>(PCtxtHandle phContext@<rcx>, __int64, __int64, __int64, __int64, void *, __int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140092240`

## callees

- `0x140005070`
- `0x140018c60`
- `0x14001c768`
- `0x140022958`
- `0x140024260`
- `0x14002d4dc`
- `0x140031ac0`
- `0x140038490`
- `0x140095798`

## import_xrefs

- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140095913`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140095913`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400959b0`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400959b0`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140095a1a`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140095a1a`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140095a39`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140095a5e`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140095a39`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140095a5e`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140095c89`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140095c89`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140095cdd`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140095cdd`
- `ntoskrnl!ExLocalTimeToSystemTime` at `0x140095a73`
- `ntoskrnl!ExLocalTimeToSystemTime` at `0x140095a73`
- `ntoskrnl!SeLockSubjectContext` at `0x140095c99`
- `ntoskrnl!SeLockSubjectContext` at `0x140095c99`
- `ntoskrnl!SeQueryAuthenticationIdToken` at `0x140095cad`
- `ntoskrnl!SeQueryAuthenticationIdToken` at `0x140095cad`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140095ccd`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140095ccd`
- `srvnet!SrvLibQueryCredentialHandle` at `0x140095945`
- `srvnet!SrvLibQueryCredentialHandle` at `0x140095945`
- `ksecdd!FreeContextBuffer` at `0x140095e39`
- `ksecdd!FreeContextBuffer` at `0x140095e39`
- `ksecdd!MapSecurityError` at `0x1400959de`
- `ksecdd!MapSecurityError` at `0x140095a9a`
- `ksecdd!MapSecurityError` at `0x140095b23`
- `ksecdd!MapSecurityError` at `0x140095cbb`
- `ksecdd!MapSecurityError` at `0x140095d75`
- `ksecdd!MapSecurityError` at `0x140095e16`
- `ksecdd!MapSecurityError` at `0x1400959de`
- `ksecdd!MapSecurityError` at `0x140095a9a`
- `ksecdd!MapSecurityError` at `0x140095b23`
- `ksecdd!MapSecurityError` at `0x140095cbb`
- `ksecdd!MapSecurityError` at `0x140095d75`
- `ksecdd!MapSecurityError` at `0x140095e16`
- `ksecdd!QueryContextAttributesW` at `0x140095a8c`
- `ksecdd!QueryContextAttributesW` at `0x140095af3`
- `ksecdd!QueryContextAttributesW` at `0x140095d31`
- `ksecdd!QueryContextAttributesW` at `0x140095d65`
- `ksecdd!QueryContextAttributesW` at `0x140095e08`
- `ksecdd!QueryContextAttributesW` at `0x140095a8c`
- `ksecdd!QueryContextAttributesW` at `0x140095af3`
- `ksecdd!QueryContextAttributesW` at `0x140095d31`
- `ksecdd!QueryContextAttributesW` at `0x140095d65`
- `ksecdd!QueryContextAttributesW` at `0x140095e08`
- `ksecdd!ImpersonateSecurityContext` at `0x140095c45`
- `ksecdd!ImpersonateSecurityContext` at `0x140095c45`
- `ksecdd!RevertSecurityContext` at `0x140095d08`
- `ksecdd!RevertSecurityContext` at `0x140095d08`
- `ksecdd!AcceptSecurityContext` at `0x14009598a`
- `ksecdd!AcceptSecurityContext` at `0x14009598a`

## string_xrefs

- `0x1400958d2`: `Smb2ValidateSecurityBuffer`
- `0x1400959bc`: `Smb2ValidateSecurityBuffer`
- `0x140095ac8`: `Smb2ValidateSecurityBuffer`
- `0x140095aff`: `Smb2ValidateSecurityBuffer`
- `0x140095c6f`: `Smb2ValidateSecurityBuffer`
- `0x140095ce9`: `Smb2ValidateSecurityBuffer`

## pseudocode

```c
__int64 __fastcall Smb2ValidateSecurityBuffer(
        PCtxtHandle phContext,
        __int64 a2,
        __int64 a3,
        int a4,
        __int64 a5,
        _DWORD *a6,
        union _LARGE_INTEGER *a7,
        void *a8,
        int *a9,
        struct _LUID *a10,
        _BYTE *a11,
        _BYTE *a12,
        _WORD *a13,
        __int64 a14,
        __int64 a15)
{
  struct _SecHandle *v15; // rbx
  _DWORD *v17; // rdx
  unsigned int v19; // r10d
  __int64 v20; // rax
  struct _SecHandle *CredentialHandle; // rax
  SECURITY_STATUS v22; // ebx
  NTSTATUS v23; // eax
  SECURITY_STATUS v24; // ebx
  __int64 v25; // rax
  SECURITY_STATUS v27; // eax
  NTSTATUS v28; // eax
  __int64 v29; // rdx
  SECURITY_STATUS ContextAttributesW; // ebx
  NTSTATUS v31; // eax
  int v32; // r8d
  int v33; // ecx
  int v34; // eax
  __int64 v35; // rdx
  SECURITY_STATUS AuthenticationIdToken; // eax
  SECURITY_STATUS v37; // ebx
  NTSTATUS v38; // eax
  __int64 v39; // rax
  SECURITY_STATUS v40; // eax
  PVOID v41; // rcx
  int TargetDataRepb; // [rsp+20h] [rbp-E0h]
  int TargetDataRep; // [rsp+20h] [rbp-E0h]
  int TargetDataRepc; // [rsp+20h] [rbp-E0h]
  int TargetDataRepa; // [rsp+20h] [rbp-E0h]
  int TargetDataRepd; // [rsp+20h] [rbp-E0h]
  int v47; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int pfContextAttr; // [rsp+54h] [rbp-ACh] BYREF
  PLARGE_INTEGER SystemTime; // [rsp+58h] [rbp-A8h] BYREF
  int pBuffer; // [rsp+60h] [rbp-A0h] BYREF
  PVOID pvContextBuffer; // [rsp+68h] [rbp-98h] BYREF
  int v52; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v53; // [rsp+74h] [rbp-8Ch]
  __int128 v54; // [rsp+78h] [rbp-88h] BYREF
  SECURITY_INTEGER LocalTime; // [rsp+88h] [rbp-78h] BYREF
  struct _SecBufferDesc pInput; // [rsp+90h] [rbp-70h] BYREF
  struct _SecBufferDesc pOutput; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v58; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v59; // [rsp+B8h] [rbp-48h] BYREF
  PLUID AuthenticationId; // [rsp+C0h] [rbp-40h]
  _BYTE *v61; // [rsp+C8h] [rbp-38h]
  _DWORD *v62; // [rsp+D0h] [rbp-30h]
  __int64 v63; // [rsp+D8h] [rbp-28h]
  __int64 v64; // [rsp+E0h] [rbp-20h]
  __int64 v65; // [rsp+E8h] [rbp-18h]
  _DWORD v66[2]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v67; // [rsp+F8h] [rbp-8h]
  int v68; // [rsp+100h] [rbp+0h]
  int v69; // [rsp+104h] [rbp+4h]
  __int64 v70; // [rsp+108h] [rbp+8h]
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+110h] [rbp+10h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v72; // [rsp+130h] [rbp+30h] BYREF
  __int64 *v73; // [rsp+150h] [rbp+50h]
  __int64 v74; // [rsp+158h] [rbp+58h]
  __int64 *v75; // [rsp+160h] [rbp+60h]
  __int64 v76; // [rsp+168h] [rbp+68h]
  int *v77; // [rsp+170h] [rbp+70h]
  __int64 v78; // [rsp+178h] [rbp+78h]
  int *v79; // [rsp+180h] [rbp+80h]
  __int64 v80; // [rsp+188h] [rbp+88h]
  PLARGE_INTEGER *p_SystemTime; // [rsp+190h] [rbp+90h]
  __int64 v82; // [rsp+198h] [rbp+98h]

  v15 = 0;
  v17 = a6;
  v19 = *a6;
  pvContextBuffer = a8;
  SystemTime = a7;
  AuthenticationId = a10;
  pBuffer = 0;
  pfContextAttr = 0;
  LocalTime.QuadPart = 0;
  v62 = a6;
  v61 = a11;
  v53 = v19;
  pInput = 0;
  pOutput = 0;
  v54 = 0;
  v20 = MEMORY[0xFFFFF78000000014];
  *a11 = 0;
  *a12 = 0;
  *a6 = 0;
  v64 = v20;
  if ( a13 )
    *a13 = -1;
  pInput.pBuffers = (PSecBuffer)v66;
  if ( a14 )
  {
    pInput.cBuffers = 2;
    v70 = a14;
    v68 = 32;
    v69 = 129;
  }
  else
  {
    pInput.cBuffers = 1;
  }
  v67 = a3;
  pOutput.pBuffers = (PSecBuffer)&v54;
  LOBYTE(v17) = 7;
  *((_QWORD *)&v54 + 1) = a5;
  v66[0] = a4;
  v66[1] = 2;
  pInput.ulVersion = 0;
  pOutput.cBuffers = 1;
  pOutput.ulVersion = 0;
  *(_QWORD *)&v54 = v19 | 0x200000000LL;
  pfContextAttr = 0;
  ++*(_DWORD *)(Srv2Statistics + 24);
  SRV2_PERF_ENTER_EX(a15 + 584, v17, 1098, "Smb2ValidateSecurityBuffer", 1);
  ExAcquireResourceSharedLite(&Smb2ExtensibleCredHandleLock, 1u);
  v63 = MEMORY[0xFFFFF78000000014];
  if ( *(_OWORD *)phContext != 0 )
    v15 = phContext;
  CredentialHandle = (struct _SecHandle *)SrvLibQueryCredentialHandle(Smb2ExtensibleCredentialHandle);
  v22 = AcceptSecurityContext(
          CredentialHandle,
          v15,
          &pInput,
          0x908001u,
          0x10u,
          phContext,
          &pOutput,
          &pfContextAttr,
          &LocalTime);
  v65 = MEMORY[0xFFFFF78000000014];
  ExReleaseResourceLite(&Smb2ExtensibleCredHandleLock);
  LOBYTE(TargetDataRepb) = 1;
  SRV2_PERF_ENTER_EX(a15 + 584, 0, 1120, "Smb2ValidateSecurityBuffer", TargetDataRepb);
  v23 = MapSecurityError(v22);
  v24 = v23;
  if ( v23 == -1073741816 || v23 == -1073741570 )
  {
    v24 = -1073741623;
LABEL_47:
    if ( (pfContextAttr & 0x8000) == 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_qqD(
          WPP_GLOBAL_Control->AttachedDevice,
          37,
          WPP_10a5358526963fec2a0dab82e9006e3d_Traceguids,
          a15,
          a2,
          v24);
      }
      goto LABEL_58;
    }
    goto LABEL_52;
  }
  if ( v23 < 0 )
    goto LABEL_47;
  if ( v23 )
  {
LABEL_52:
    v24 = -1073741802;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_qqD(
        WPP_GLOBAL_Control->AttachedDevice,
        36,
        WPP_10a5358526963fec2a0dab82e9006e3d_Traceguids,
        a15,
        a2,
        -1073741802);
    }
    goto LABEL_56;
  }
  ExAcquirePushLockExclusiveEx(*(_QWORD *)(a2 + 24) + 80LL, 0);
  v25 = *(_QWORD *)(a2 + 24);
  if ( *(_DWORD *)(v25 + 12) == 221 )
  {
    ExReleasePushLockExclusiveEx(v25 + 80, 0);
    return 3221226332LL;
  }
  *(_DWORD *)(v25 + 12) = 220;
  ExReleasePushLockExclusiveEx(*(_QWORD *)(a2 + 24) + 80LL, 0);
  ExLocalTimeToSystemTime(&LocalTime, SystemTime);
  v27 = QueryContextAttributesW(phContext, 0x25u, &pBuffer);
  v28 = MapSecurityError(v27);
  v24 = v28;
  if ( v28 == -1073741637 )
  {
    *a12 = 0;
  }
  else if ( v28 < 0 )
  {
LABEL_26:
    v34 = 0;
    LODWORD(v54) = 0;
LABEL_57:
    *v62 = v34;
    goto LABEL_58;
  }
  if ( pBuffer )
    *a12 = 1;
  LOBYTE(TargetDataRep) = 1;
  LOBYTE(v29) = 7;
  SRV2_PERF_ENTER_EX(a15 + 584, v29, 1175, "Smb2ValidateSecurityBuffer", TargetDataRep);
  LOBYTE(TargetDataRepc) = 1;
  ContextAttributesW = QueryContextAttributesW(phContext, 9u, a9);
  SRV2_PERF_ENTER_EX(a15 + 584, 0, 1181, "Smb2ValidateSecurityBuffer", TargetDataRepc);
  v31 = MapSecurityError(ContextAttributesW);
  LOBYTE(v32) = 0;
  v24 = v31;
  if ( v31 < 0 )
    goto LABEL_26;
  if ( (unsigned int)dword_1400583B0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1400583B0, 0x400000000000LL, 0) )
  {
    v58 = 0x2000000;
    v73 = &v58;
    v74 = 8;
    v75 = &v59;
    v47 = *a9;
    v77 = &v47;
    v52 = *(_DWORD *)(a2 + 292);
    v79 = &v52;
    LODWORD(SystemTime) = Smb2MinSessionKeyCbLength;
    p_SystemTime = &SystemTime;
    v59 = 1;
    v76 = 8;
    v78 = 4;
    v80 = 4;
    v82 = 4;
    tlgWriteAgg(v33, (int)&byte_140043447, v32, v32 + 7, &v72);
    LOBYTE(v32) = 0;
  }
  if ( *a12 == (_BYTE)v32 && *a9 < (unsigned int)Smb2MinSessionKeyCbLength )
  {
    Smb2LogTooShortKeyError(a15, a2, phContext, a9);
    v24 = -1073740521;
    goto LABEL_26;
  }
  v24 = ImpersonateSecurityContext(phContext);
  if ( v24 < 0 )
    goto LABEL_26;
  LOBYTE(TargetDataRepa) = 1;
  LOBYTE(v35) = 7;
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  SRV2_PERF_ENTER_EX(a15 + 584, v35, 1219, "Smb2ValidateSecurityBuffer", TargetDataRepa);
  SeCaptureSubjectContext(&SubjectContext);
  SeLockSubjectContext(&SubjectContext);
  AuthenticationIdToken = SeQueryAuthenticationIdToken(SubjectContext.ClientToken, AuthenticationId);
  v24 = MapSecurityError(AuthenticationIdToken);
  SeUnlockSubjectContext(&SubjectContext);
  SeReleaseSubjectContext(&SubjectContext);
  LOBYTE(TargetDataRepd) = 1;
  SRV2_PERF_ENTER_EX(a15 + 584, 0, 1235, "Smb2ValidateSecurityBuffer", TargetDataRepd);
  RevertSecurityContext(phContext);
  if ( v24 < 0 )
    goto LABEL_26;
  v47 = 0;
  if ( !QueryContextAttributesW(phContext, 0xBu, &v47) && (v47 & 1) != 0 )
    *v61 = 1;
  SystemTime = 0;
  v37 = QueryContextAttributesW(phContext, 0x15u, &SystemTime);
  v38 = MapSecurityError(v37);
  if ( v38 < 0 )
  {
    if ( v38 != -1073741637 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 35, WPP_10a5358526963fec2a0dab82e9006e3d_Traceguids, a15, v37);
      }
      v24 = -1073741616;
      goto LABEL_26;
    }
    v39 = 0x7FFFFFFFFFFFFFFFLL;
  }
  else
  {
    v39 = (__int64)SystemTime;
  }
  *(_QWORD *)pvContextBuffer = v39;
  if ( a13 )
  {
    pvContextBuffer = 0;
    v40 = QueryContextAttributesW(phContext, 0xAu, &pvContextBuffer);
    if ( MapSecurityError(v40) >= 0 )
    {
      v41 = pvContextBuffer;
      if ( pvContextBuffer )
      {
        *a13 = *((_WORD *)pvContextBuffer + 3);
        FreeContextBuffer(v41);
      }
    }
  }
  v24 = 0;
LABEL_56:
  v34 = v54;
  if ( (unsigned int)v54 <= v53 )
    goto LABEL_57;
LABEL_58:
  if ( MEMORY[0xFFFFF78000000014] - v64 > 50000000 && (byte_14004C339 & 0x10) != 0 )
    McTemplateK0hxxxx_EtwWriteTransfer(
      (unsigned __int64)(v65 - v64 + ((unsigned __int128)((v65 - v64) * (__int128)(__int64)0xD6BF94D5E57A42BDuLL) >> 64)) >> 63,
      (v63 - v64) / 10000000,
      (v65 - v64) / 10000000,
      1,
      (v63 - v64) / 10000000,
      (v65 - v64) / 10000000,
      (MEMORY[0xFFFFF78000000014] - v64) / 10000000);
  return (unsigned int)v24;
}

```

## disassembly

```asm
0x140095798  mov     [rsp-8+arg_10], rbx
0x14009579d  push    rbp
0x14009579e  push    rsi
0x14009579f  push    rdi
0x1400957a0  push    r12
0x1400957a2  push    r13
0x1400957a4  push    r14
0x1400957a6  push    r15
0x1400957a8  lea     rbp, [rsp-0B0h]
0x1400957b0  sub     rsp, 1B0h
0x1400957b7  mov     rax, cs:__security_cookie
0x1400957be  xor     rax, rsp
0x1400957c1  mov     [rbp+0E0h+var_40], rax
0x1400957c8  mov     rax, [rbp+0E0h+arg_38]
0x1400957cf  xor     ebx, ebx
0x1400957d1  mov     r15, [rbp+0E0h+arg_58]
0x1400957d8  xorps   xmm0, xmm0
0x1400957db  mov     r12, [rbp+0E0h+arg_60]
0x1400957e2  mov     rsi, rdx
0x1400957e5  mov     rdx, [rbp+0E0h+arg_28]
0x1400957ec  mov     rdi, rcx
0x1400957ef  mov     rcx, [rbp+0E0h+arg_50]
0x1400957f6  xorps   xmm1, xmm1
0x1400957f9  mov     r13, [rbp+0E0h+arg_40]
0x140095800  mov     r14, [rbp+0E0h+arg_70]
0x140095807  mov     r10d, [rdx]
0x14009580a  mov     [rsp+1E0h+pvContextBuffer], rax
0x14009580f  mov     rax, [rbp+0E0h+arg_30]
0x140095816  mov     [rsp+1E0h+SystemTime], rax
0x14009581b  mov     rax, [rbp+0E0h+arg_48]
0x140095822  mov     [rbp+0E0h+AuthenticationId], rax
0x140095826  mov     rax, 0FFFFF78000000014h
0x140095830  mov     [rsp+1E0h+pBuffer], ebx
0x140095834  mov     [rsp+1E0h+var_18C], ebx
0x140095838  mov     qword ptr [rbp+0E0h+LocalTime], rbx
0x14009583c  mov     [rbp+0E0h+var_110], rdx
0x140095840  mov     [rbp+0E0h+var_118], rcx
0x140095844  mov     [rsp+1E0h+var_16C], r10d
0x140095849  movups  xmmword ptr [rbp+0E0h+pInput.ulVersion], xmm0
0x14009584d  movups  xmmword ptr [rbp+0E0h+var_140.ulVersion], xmm1
0x140095851  movups  [rsp+1E0h+var_168], xmm0
0x140095856  mov     rax, [rax]
0x140095859  mov     [rcx], bl
0x14009585b  mov     [r15], bl
0x14009585e  mov     [rdx], ebx
0x140095860  mov     [rbp+0E0h+var_100], rax
0x140095864  test    r12, r12
0x140095867  jz      short loc_140095870
0x140095869  mov     word ptr [r12], 0FFFFh
0x140095870  lea     rax, [rbp+0E0h+var_F0]
0x140095874  mov     ecx, 2
0x140095879  mov     [rbp+0E0h+pInput.pBuffers], rax
0x14009587d  mov     rax, [rbp+0E0h+arg_68]
0x140095884  test    rax, rax
0x140095887  jz      short loc_1400958A0
0x140095889  mov     [rbp+0E0h+pInput.cBuffers], ecx
0x14009588c  mov     [rbp+0E0h+var_D8], rax
0x140095890  mov     [rbp+0E0h+var_E0], 20h ; ' '
0x140095897  mov     [rbp+0E0h+var_DC], 81h
0x14009589e  jmp     short loc_1400958A7
0x1400958a0  mov     [rbp+0E0h+pInput.cBuffers], 1
0x1400958a7  mov     [rbp+0E0h+var_E8], r8
0x1400958ab  lea     rax, [rsp+1E0h+var_168]
0x1400958b0  mov     [rbp+0E0h+var_140.pBuffers], rax
0x1400958b4  mov     r8d, 44Ah
0x1400958ba  mov     rax, [rbp+0E0h+arg_20]
0x1400958c1  mov     dl, 7
0x1400958c3  mov     qword ptr [rbp+0E0h+var_168+8], rax
0x1400958c7  mov     rax, cs:Srv2Statistics
0x1400958ce  mov     [rbp+0E0h+var_F0], r9d
0x1400958d2  lea     r9, aSmb2validatese; "Smb2ValidateSecurityBuffer"
0x1400958d9  mov     [rbp+0E0h+var_EC], ecx
0x1400958dc  mov     dword ptr [rsp+1E0h+var_168+4], ecx
0x1400958e0  lea     rcx, [r14+248h]
0x1400958e7  mov     [rbp+0E0h+pInput.ulVersion], ebx
0x1400958ea  mov     [rbp+0E0h+var_140.cBuffers], 1
0x1400958f1  mov     [rbp+0E0h+var_140.ulVersion], ebx
0x1400958f4  mov     dword ptr [rsp+1E0h+var_168], r10d
0x1400958f9  mov     [rsp+1E0h+var_18C], ebx
0x1400958fd  inc     dword ptr [rax+18h]
0x140095900  mov     byte ptr [rsp+1E0h+TargetDataRep], 1
0x140095905  call    SRV2_PERF_ENTER_EX
0x14009590a  mov     dl, 1; Wait
0x14009590c  lea     rcx, Smb2ExtensibleCredHandleLock; Resource
0x140095913  call    cs:__imp_ExAcquireResourceSharedLite
0x14009591a  nop     dword ptr [rax+rax+00h]
0x14009591f  mov     rcx, 0FFFFF78000000014h
0x140095929  mov     rax, [rcx]
0x14009592c  mov     [rbp+0E0h+var_108], rax
0x140095930  cmp     [rdi], rbx
0x140095933  jnz     short loc_14009593B
0x140095935  cmp     [rdi+8], rbx
0x140095939  jz      short loc_14009593E
0x14009593b  mov     rbx, rdi
0x14009593e  mov     rcx, cs:Smb2ExtensibleCredentialHandle
0x140095945  call    cs:__imp_SrvLibQueryCredentialHandle
0x14009594c  nop     dword ptr [rax+rax+00h]
0x140095951  mov     r9d, 908001h; fContextReq
0x140095957  lea     r8, [rbp+0E0h+pInput]; pInput
0x14009595b  mov     rcx, rax; phCredential
0x14009595e  mov     rdx, rbx; phContext
0x140095961  lea     rax, [rbp+0E0h+LocalTime]
0x140095965  mov     [rsp+1E0h+ptsExpiry], rax; ptsExpiry
0x14009596a  lea     rax, [rsp+1E0h+var_18C]
0x14009596f  mov     [rsp+1E0h+pfContextAttr], rax; pfContextAttr
0x140095974  lea     rax, [rbp+0E0h+var_140]
0x140095978  mov     [rsp+1E0h+pOutput], rax; pOutput
0x14009597d  mov     [rsp+1E0h+phNewContext], rdi; phNewContext
0x140095982  mov     [rsp+1E0h+TargetDataRep], 10h; TargetDataRep
0x14009598a  call    cs:__imp_AcceptSecurityContext
0x140095991  nop     dword ptr [rax+rax+00h]
0x140095996  mov     ebx, eax
0x140095998  lea     rcx, Smb2ExtensibleCredHandleLock; Resource
0x14009599f  mov     rax, 0FFFFF78000000014h
0x1400959a9  mov     rax, [rax]
0x1400959ac  mov     [rbp+0E0h+var_F8], rax
0x1400959b0  call    cs:__imp_ExReleaseResourceLite
0x1400959b7  nop     dword ptr [rax+rax+00h]
0x1400959bc  lea     r9, aSmb2validatese; "Smb2ValidateSecurityBuffer"
0x1400959c3  mov     byte ptr [rsp+1E0h+TargetDataRep], 1
0x1400959c8  xor     edx, edx
0x1400959ca  lea     rcx, [r14+248h]
0x1400959d1  mov     r8d, 460h
0x1400959d7  call    SRV2_PERF_ENTER_EX
0x1400959dc  mov     ecx, ebx; SecStatus
0x1400959de  call    cs:__imp_MapSecurityError
0x1400959e5  nop     dword ptr [rax+rax+00h]
0x1400959ea  mov     ebx, eax
0x1400959ec  cmp     eax, 0C0000008h
0x1400959f1  jz      loc_140095E4C
0x1400959f7  cmp     eax, 0C00000FEh
0x1400959fc  jz      loc_140095E4C
0x140095a02  test    eax, eax
0x140095a04  js      loc_140095E51
0x140095a0a  jnz     loc_140095EA8
0x140095a10  mov     rcx, [rsi+18h]
0x140095a14  xor     edx, edx
0x140095a16  add     rcx, 50h ; 'P'
0x140095a1a  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140095a21  nop     dword ptr [rax+rax+00h]
0x140095a26  mov     rax, [rsi+18h]
0x140095a2a  xor     edx, edx
0x140095a2c  cmp     dword ptr [rax+0Ch], 0DDh
0x140095a33  jnz     short loc_140095A4F
0x140095a35  lea     rcx, [rax+50h]
0x140095a39  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140095a40  nop     dword ptr [rax+rax+00h]
0x140095a45  mov     eax, 0C000035Ch
0x140095a4a  jmp     loc_140095FA5
0x140095a4f  mov     dword ptr [rax+0Ch], 0DCh
0x140095a56  mov     rcx, [rsi+18h]
0x140095a5a  add     rcx, 50h ; 'P'
0x140095a5e  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140095a65  nop     dword ptr [rax+rax+00h]
0x140095a6a  mov     rdx, [rsp+1E0h+SystemTime]; SystemTime
0x140095a6f  lea     rcx, [rbp+0E0h+LocalTime]; LocalTime
0x140095a73  call    cs:__imp_ExLocalTimeToSystemTime
0x140095a7a  nop     dword ptr [rax+rax+00h]
0x140095a7f  lea     r8, [rsp+1E0h+pBuffer]; pBuffer
0x140095a84  mov     edx, 25h ; '%'; ulAttribute
0x140095a89  mov     rcx, rdi; phContext
0x140095a8c  call    cs:__imp_QueryContextAttributesW
0x140095a93  nop     dword ptr [rax+rax+00h]
0x140095a98  mov     ecx, eax; SecStatus
0x140095a9a  call    cs:__imp_MapSecurityError
0x140095aa1  nop     dword ptr [rax+rax+00h]
0x140095aa6  mov     ebx, eax
0x140095aa8  cmp     eax, 0C00000BBh
0x140095aad  jnz     short loc_140095AB5
0x140095aaf  mov     byte ptr [r15], 0
0x140095ab3  jmp     short loc_140095ABD
0x140095ab5  test    eax, eax
0x140095ab7  js      loc_140095C37
0x140095abd  cmp     [rsp+1E0h+pBuffer], 0
0x140095ac2  jz      short loc_140095AC8
0x140095ac4  mov     byte ptr [r15], 1
0x140095ac8  lea     r9, aSmb2validatese; "Smb2ValidateSecurityBuffer"
0x140095acf  mov     byte ptr [rsp+1E0h+TargetDataRep], 1
0x140095ad4  mov     r8d, 497h
0x140095ada  lea     rcx, [r14+248h]
0x140095ae1  mov     dl, 7
0x140095ae3  call    SRV2_PERF_ENTER_EX
0x140095ae8  mov     r8, r13; pBuffer
0x140095aeb  mov     edx, 9; ulAttribute
0x140095af0  mov     rcx, rdi; phContext
0x140095af3  call    cs:__imp_QueryContextAttributesW
0x140095afa  nop     dword ptr [rax+rax+00h]
0x140095aff  lea     r9, aSmb2validatese; "Smb2ValidateSecurityBuffer"
0x140095b06  mov     byte ptr [rsp+1E0h+TargetDataRep], 1
0x140095b0b  xor     edx, edx
0x140095b0d  lea     rcx, [r14+248h]
0x140095b14  mov     r8d, 49Dh
0x140095b1a  mov     ebx, eax
0x140095b1c  call    SRV2_PERF_ENTER_EX
0x140095b21  mov     ecx, ebx; SecStatus
0x140095b23  call    cs:__imp_MapSecurityError
0x140095b2a  nop     dword ptr [rax+rax+00h]
0x140095b2f  xor     r8d, r8d
0x140095b32  mov     ebx, eax
0x140095b34  test    eax, eax
0x140095b36  js      loc_140095C37
0x140095b3c  mov     eax, cs:dword_1400583B0
0x140095b42  cmp     eax, 5
0x140095b45  jbe     loc_140095C10
0x140095b4b  mov     rdx, 400000000000h
0x140095b55  lea     rcx, dword_1400583B0
0x140095b5c  call    _tlgKeywordOn
0x140095b61  test    al, al
0x140095b63  jz      loc_140095C10
0x140095b69  lea     rax, [rbp+0E0h+var_130]
0x140095b6d  mov     [rbp+0E0h+var_130], 2000000h
0x140095b75  mov     [rbp+0E0h+var_90], rax
0x140095b79  lea     r9d, [r8+7]; int
0x140095b7d  lea     rax, [rbp+0E0h+var_128]
0x140095b81  mov     [rbp+0E0h+var_88], 8
0x140095b89  mov     [rbp+0E0h+var_80], rax
0x140095b8d  lea     rdx, byte_140043447; int
0x140095b94  mov     eax, [r13+0]
0x140095b98  mov     [rsp+1E0h+var_190], eax
0x140095b9c  lea     rax, [rsp+1E0h+var_190]
0x140095ba1  mov     [rbp+0E0h+var_70], rax
0x140095ba5  mov     eax, [rsi+124h]
0x140095bab  mov     [rsp+1E0h+var_170], eax
0x140095baf  lea     rax, [rsp+1E0h+var_170]
0x140095bb4  mov     [rbp+0E0h+var_60], rax
0x140095bbb  mov     eax, cs:Smb2MinSessionKeyCbLength
0x140095bc1  mov     dword ptr [rsp+1E0h+SystemTime], eax
0x140095bc5  lea     rax, [rsp+1E0h+SystemTime]
0x140095bca  mov     [rbp+0E0h+var_50], rax
0x140095bd1  lea     rax, [rbp+0E0h+var_B0]
0x140095bd5  mov     qword ptr [rsp+1E0h+TargetDataRep], rax; PEVENT_DATA_DESCRIPTOR
0x140095bda  mov     [rbp+0E0h+var_128], 1
0x140095be2  mov     [rbp+0E0h+var_78], 8
0x140095bea  mov     [rbp+0E0h+var_68], 4
0x140095bf2  mov     [rbp+0E0h+var_58], 4
0x140095bfd  mov     [rbp+0E0h+var_48], 4
0x140095c08  call    _tlgWriteAgg
0x140095c0d  xor     r8d, r8d
0x140095c10  cmp     [r15], r8b
0x140095c13  jnz     short loc_140095C42
0x140095c15  mov     eax, cs:Smb2MinSessionKeyCbLength
0x140095c1b  cmp     [r13+0], eax
0x140095c1f  jnb     short loc_140095C42
0x140095c21  mov     r9, r13
0x140095c24  mov     r8, rdi
0x140095c27  mov     rdx, rsi
0x140095c2a  mov     rcx, r14
0x140095c2d  call    Smb2LogTooShortKeyError
0x140095c32  mov     ebx, 0C0000517h
0x140095c37  xor     eax, eax
0x140095c39  mov     dword ptr [rsp+1E0h+var_168], eax
0x140095c3d  jmp     loc_140095EFE
0x140095c42  mov     rcx, rdi; phContext
0x140095c45  call    cs:__imp_ImpersonateSecurityContext
0x140095c4c  nop     dword ptr [rax+rax+00h]
0x140095c51  mov     ebx, eax
0x140095c53  test    eax, eax
0x140095c55  js      short loc_140095C37
0x140095c57  xorps   xmm0, xmm0
0x140095c5a  mov     byte ptr [rsp+1E0h+TargetDataRep], 1
0x140095c5f  lea     rsi, [r14+248h]
0x140095c66  mov     r8d, 4C3h
0x140095c6c  mov     rcx, rsi
0x140095c6f  lea     r9, aSmb2validatese; "Smb2ValidateSecurityBuffer"
0x140095c76  mov     dl, 7
0x140095c78  movups  xmmword ptr [rbp+0E0h+SubjectContext.ClientToken], xmm0
0x140095c7c  movups  xmmword ptr [rbp+0E0h+SubjectContext.PrimaryToken], xmm0
0x140095c80  call    SRV2_PERF_ENTER_EX
0x140095c85  lea     rcx, [rbp+0E0h+SubjectContext]; SubjectContext
0x140095c89  call    cs:__imp_SeCaptureSubjectContext
0x140095c90  nop     dword ptr [rax+rax+00h]
0x140095c95  lea     rcx, [rbp+0E0h+SubjectContext]; SubjectContext
0x140095c99  call    cs:__imp_SeLockSubjectContext
0x140095ca0  nop     dword ptr [rax+rax+00h]
0x140095ca5  mov     rdx, [rbp+0E0h+AuthenticationId]; AuthenticationId
0x140095ca9  mov     rcx, [rbp+0E0h+SubjectContext.ClientToken]; Token
0x140095cad  call    cs:__imp_SeQueryAuthenticationIdToken
0x140095cb4  nop     dword ptr [rax+rax+00h]
0x140095cb9  mov     ecx, eax; SecStatus
0x140095cbb  call    cs:__imp_MapSecurityError
0x140095cc2  nop     dword ptr [rax+rax+00h]
0x140095cc7  lea     rcx, [rbp+0E0h+SubjectContext]; SubjectContext
0x140095ccb  mov     ebx, eax
0x140095ccd  call    cs:__imp_SeUnlockSubjectContext
0x140095cd4  nop     dword ptr [rax+rax+00h]
0x140095cd9  lea     rcx, [rbp+0E0h+SubjectContext]; SubjectContext
0x140095cdd  call    cs:__imp_SeReleaseSubjectContext
0x140095ce4  nop     dword ptr [rax+rax+00h]
0x140095ce9  lea     r9, aSmb2validatese; "Smb2ValidateSecurityBuffer"
0x140095cf0  mov     byte ptr [rsp+1E0h+TargetDataRep], 1
0x140095cf5  xor     edx, edx
0x140095cf7  mov     r8d, 4D3h
0x140095cfd  mov     rcx, rsi
0x140095d00  call    SRV2_PERF_ENTER_EX
0x140095d05  mov     rcx, rdi; phContext
0x140095d08  call    cs:__imp_RevertSecurityContext
0x140095d0f  nop     dword ptr [rax+rax+00h]
0x140095d14  test    ebx, ebx
0x140095d16  js      loc_140095C37
0x140095d1c  lea     r8, [rsp+1E0h+var_190]; pBuffer
  ... truncated ...
```
