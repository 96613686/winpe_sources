# AttemptAADConnect(_WLSM_GLOBAL_CONTEXT *,void *,bool,_LUID,void *)

- ea: `0x14004f0b4`
- end: `0x14004f6f1`
- name: `?AttemptAADConnect@@YAHPEAU_WLSM_GLOBAL_CONTEXT@@PEAX_NU_LUID@@1@Z`
- size: `1597`
- prototype: `int(struct _WLSM_GLOBAL_CONTEXT *, void *, bool, struct _LUID, void *)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x140044c90`

## callees

- `0x1400057f4`
- `0x140012c24`
- `0x140013050`
- `0x1400198e0`
- `0x14001a200`
- `0x140032550`
- `0x140041c34`
- `0x14004f0b4`
- `0x14004f6f8`
- `0x140053720`
- `0x1400544e0`
- `0x140056230`
- `0x14008abcc`
- `0x14009cc54`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CopySid` at `0x14004f24f`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x14004f24f`
- `ntdll!RtlInitString` at `0x14004f2c6`
- `ntdll!RtlInitString` at `0x14004f2c6`
- `ntdll!RtlNtStatusToDosError` at `0x14004f1e0`
- `ntdll!RtlNtStatusToDosError` at `0x14004f1e0`
- `SspiCli!LsaCallAuthenticationPackage` at `0x14004f359`
- `SspiCli!LsaCallAuthenticationPackage` at `0x14004f359`
- `SspiCli!LsaFreeReturnBuffer` at `0x14004f64d`
- `SspiCli!LsaFreeReturnBuffer` at `0x14004f64d`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x14004f2d9`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x14004f2d9`
- `api-ms-win-security-lsalookup-l1-1-2!LsaLookupUserAccountType` at `0x14004f197`
- `api-ms-win-security-lsalookup-l1-1-2!LsaLookupUserAccountType` at `0x14004f197`
- `ext-ms-win-session-candidateaccountmgr-l1-1-0!CamConnectCandidateUser` at `0x14004f57d`
- `ext-ms-win-session-candidateaccountmgr-l1-1-0!CamConnectCandidateUser` at `0x14004f57d`

## pseudocode

```c
_BOOL8 __fastcall AttemptAADConnect(struct _WLSM_GLOBAL_CONTEXT *a1, void *a2, char a3, struct _LUID a4, void *a5)
{
  int IsAutoAadConnectEnabled; // eax
  __int64 v10; // rdx
  _BYTE *v11; // r12
  int v12; // esi
  bool v13; // r14
  const void *v14; // r13
  int v15; // eax
  NTSTATUS v16; // edi
  NTSTATUS v17; // ecx
  ULONG v18; // edi
  unsigned int v19; // eax
  NTSTATUS v20; // r15d
  CUser *v21; // rcx
  __int64 v22; // rdx
  NTSTATUS v23; // eax
  ULONG v24; // eax
  __int64 v25; // r9
  unsigned __int16 *v26; // r15
  _OWORD *v27; // rax
  CUser *v28; // rcx
  __int64 v29; // rdx
  __int128 v30; // xmm1
  __int128 v31; // xmm0
  __int128 v32; // xmm1
  size_t v33; // rbx
  unsigned int v34; // r15d
  _QWORD *v35; // rax
  int v36; // eax
  ULONG v37; // ebx
  __int64 v38; // rcx
  _BYTE *v39; // rax
  __int64 v40; // rcx
  _BYTE *v41; // rax
  char v43; // [rsp+40h] [rbp-C0h] BYREF
  char v44; // [rsp+48h] [rbp-B8h] BYREF
  bool v45; // [rsp+50h] [rbp-B0h] BYREF
  bool v46; // [rsp+51h] [rbp-AFh] BYREF
  PSID pSourceSid; // [rsp+58h] [rbp-A8h] BYREF
  int ProtocolStatus; // [rsp+60h] [rbp-A0h] BYREF
  ULONG ReturnBufferLength; // [rsp+64h] [rbp-9Ch] BYREF
  size_t Size; // [rsp+68h] [rbp-98h] BYREF
  ULONG AuthenticationPackage; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v52; // [rsp+74h] [rbp-8Ch]
  PVOID Buffer; // [rsp+78h] [rbp-88h] BYREF
  HANDLE LsaHandle; // [rsp+80h] [rbp-80h] BYREF
  struct _WLSM_GLOBAL_CONTEXT *v55; // [rsp+88h] [rbp-78h]
  struct _STRING DestinationString; // [rsp+90h] [rbp-70h] BYREF
  __int128 v57; // [rsp+A0h] [rbp-60h]
  __int128 v58; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v59; // [rsp+D0h] [rbp-30h]
  __int128 v60; // [rsp+E0h] [rbp-20h]
  __int128 v61; // [rsp+F0h] [rbp-10h]
  int ProtocolSubmitBuffer; // [rsp+100h] [rbp+0h] BYREF
  __int128 v63; // [rsp+104h] [rbp+4h]
  _BYTE pDestinationSid[76]; // [rsp+114h] [rbp+14h] BYREF

  pSourceSid = a5;
  v55 = a1;
  v44 = a3;
  IsAutoAadConnectEnabled = CandidateAccountManagerPolicy::IsAutoAadConnectEnabled();
  v10 = *((_QWORD *)a1 + 4);
  v11 = 0;
  v12 = IsAutoAadConnectEnabled;
  v46 = IsAutoAadConnectEnabled != 0;
  v13 = (unsigned int)(*(_DWORD *)(v10 + 528) - 1) <= 1;
  v45 = v13;
  v43 = IsAdmin(a2);
  memset_0(&ProtocolSubmitBuffer, 0, 0x58u);
  LsaHandle = 0;
  Buffer = 0;
  ReturnBufferLength = 0;
  ProtocolStatus = 0;
  DestinationString = 0;
  AuthenticationPackage = 0;
  memset_0(&v58, 0, 0x40u);
  *(_QWORD *)&v57 = 0;
  v14 = 0;
  HIDWORD(v57) = 0;
  Size = 0;
  v52 = 0;
  v15 = LsaLookupUserAccountType(a5, (char *)&Size + 4);
  v16 = v15;
  if ( v15 < 0 )
  {
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        74,
        WPP_1f80ccb0ea51320fbaee2b4e4d0a6e34_Traceguids,
        (unsigned int)v15);
    }
    v17 = v16;
    goto LABEL_7;
  }
  if ( !v12
    || !v13
    || v43
    || a3
    || !(unsigned __int8)IsCamCleanupDisardedCandidateAccountsPresent()
    || HIDWORD(Size) != 5 )
  {
    v18 = 50;
    goto LABEL_71;
  }
  ProtocolSubmitBuffer = 15;
  v63 = xmmword_1400B1CE8;
  CopySid(0x44u, pDestinationSid, pSourceSid);
  v19 = CGlobalStore::GetLsaHandle(xGlobalContext, &LsaHandle);
  LODWORD(pSourceSid) = v19;
  v18 = v19;
  if ( !v19 )
  {
    RtlInitString(&DestinationString, "CloudAP");
    v20 = LsaLookupAuthenticationPackage(LsaHandle, (PLSA_STRING)&DestinationString, &AuthenticationPackage);
    if ( v20 < 0 )
    {
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_25;
      }
      v22 = 76;
LABEL_24:
      WPP_SF_d(*((_QWORD *)v21 + 2), v22, WPP_1f80ccb0ea51320fbaee2b4e4d0a6e34_Traceguids, (unsigned int)v20);
LABEL_25:
      v17 = v20;
LABEL_7:
      v18 = RtlNtStatusToDosError(v17);
      LODWORD(pSourceSid) = v18;
      goto LABEL_72;
    }
    v23 = LsaCallAuthenticationPackage(
            LsaHandle,
            AuthenticationPackage,
            &ProtocolSubmitBuffer,
            0x58u,
            &Buffer,
            &ReturnBufferLength,
            &ProtocolStatus);
    v20 = v23;
    if ( v23 < 0 )
    {
      MicrosoftTelemetryAssertTriggeredArgs("lsass.exe", (unsigned int)v23, (unsigned int)ProtocolStatus);
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_25;
      }
      v22 = 77;
      goto LABEL_24;
    }
    if ( !Buffer )
      MicrosoftTelemetryAssertTriggeredArgs("lsass.exe", (unsigned int)v23, (unsigned int)ProtocolStatus);
    v24 = ReturnBufferLength;
    if ( ReturnBufferLength < 8 )
    {
      MicrosoftTelemetryAssertTriggeredArgs("lsass.exe", ReturnBufferLength, 8);
      v24 = ReturnBufferLength;
    }
    if ( Buffer && v24 >= 8 )
    {
      v25 = (unsigned int)ProtocolStatus;
      if ( ProtocolStatus < 0 )
      {
        MicrosoftTelemetryAssertTriggeredArgs("lsass.exe", (unsigned int)ProtocolStatus, 0);
        v25 = (unsigned int)ProtocolStatus;
      }
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 79, WPP_1f80ccb0ea51320fbaee2b4e4d0a6e34_Traceguids, v25);
      }
      v26 = (unsigned __int16 *)Buffer;
      LODWORD(Size) = *((unsigned __int16 *)Buffer + 21) + 64;
      v27 = WLAlloc((unsigned int)Size);
      v14 = v27;
      if ( !v27 )
      {
        v18 = 14;
        LODWORD(pSourceSid) = 14;
        v28 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_72;
        }
        v29 = 80;
        goto LABEL_64;
      }
      DWORD2(v59) = *((_DWORD *)v26 + 10);
      v30 = v59;
      LODWORD(v58) = 84;
      *v27 = v58;
      *(_QWORD *)&v60 = 64;
      v31 = v60;
      v27[1] = v30;
      *((struct _LUID *)&v61 + 1) = a4;
      v32 = v61;
      v27[2] = v31;
      v27[3] = v32;
      memcpy_0(v27 + 4, *((const void **)v26 + 6), v26[21]);
      v33 = (unsigned int)Size;
      DWORD2(v57) = Size;
      v34 = Size + 24;
      v52 = Size + 24;
      v35 = WLAlloc((unsigned int)(Size + 24));
      v11 = v35;
      if ( !v35 )
      {
        v18 = 14;
        LODWORD(pSourceSid) = 14;
        v28 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_72;
        }
        v29 = 81;
        goto LABEL_64;
      }
      *(_OWORD *)v35 = v57;
      v35[2] = v14;
      memcpy_0(v35 + 3, v14, v33);
      v36 = CamConnectCandidateUser(*(_QWORD *)(*((_QWORD *)v55 + 4) + 136LL), v11, v34);
      v37 = v36;
      if ( v36 >= 0 )
      {
        v28 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
        {
          goto LABEL_72;
        }
        v29 = 83;
LABEL_64:
        WPP_SF_(*((_QWORD *)v28 + 2), v29, WPP_1f80ccb0ea51320fbaee2b4e4d0a6e34_Traceguids);
        goto LABEL_72;
      }
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          82,
          WPP_1f80ccb0ea51320fbaee2b4e4d0a6e34_Traceguids,
          (unsigned int)v36);
      }
      v18 = (unsigned __int16)v37;
      if ( (v37 & 0x1FFF0000) != 0x70000 )
        v18 = v37;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 78, WPP_1f80ccb0ea51320fbaee2b4e4d0a6e34_Traceguids);
      }
      v18 = 13;
    }
LABEL_71:
    LODWORD(pSourceSid) = v18;
    goto LABEL_72;
  }
  if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 75, WPP_1f80ccb0ea51320fbaee2b4e4d0a6e34_Traceguids, v19);
  }
LABEL_72:
  if ( Buffer )
    LsaFreeReturnBuffer(Buffer);
  if ( v11 )
  {
    v38 = v52;
    v39 = v11;
    if ( v52 )
    {
      do
      {
        *v39++ = 0;
        --v38;
      }
      while ( v38 );
    }
    UHHeapFree(v11);
  }
  if ( v14 )
  {
    v40 = (unsigned int)Size;
    v41 = v14;
    if ( (_DWORD)Size )
    {
      do
      {
        *v41++ = 0;
        --v40;
      }
      while ( v40 );
    }
    UHHeapFree(v14);
  }
  v43 ^= 1u;
  WinlogonProvider::ConnectCandidateUser<bool const &,bool const &,bool,bool &,unsigned long &>(
    (unsigned int)&v46,
    (unsigned int)&v45,
    (unsigned int)&v43,
    (unsigned int)&v44,
    (__int64)&pSourceSid);
  return v18 == 0;
}

```

## disassembly

```asm
0x14004f0b4  push    rbp
0x14004f0b6  push    rbx
0x14004f0b7  push    rsi
0x14004f0b8  push    rdi
0x14004f0b9  push    r12
0x14004f0bb  push    r13
0x14004f0bd  push    r14
0x14004f0bf  push    r15
0x14004f0c1  lea     rbp, [rsp-78h]
0x14004f0c6  sub     rsp, 178h
0x14004f0cd  mov     rax, cs:__security_cookie
0x14004f0d4  xor     rax, rsp
0x14004f0d7  mov     [rbp+0B0h+var_50], rax
0x14004f0db  mov     rax, [rbp+0B0h+arg_20]
0x14004f0e2  mov     rbx, r9
0x14004f0e5  mov     [rsp+1B0h+pSourceSid], rax
0x14004f0ea  mov     r15b, r8b
0x14004f0ed  mov     rdi, rdx
0x14004f0f0  mov     [rbp+0B0h+var_128], rcx
0x14004f0f4  mov     r14, rcx
0x14004f0f7  mov     [rsp+1B0h+var_168], r8b
0x14004f0fc  call    ?IsAutoAadConnectEnabled@CandidateAccountManagerPolicy@@SAHXZ; CandidateAccountManagerPolicy::IsAutoAadConnectEnabled(void)
0x14004f101  mov     rdx, [r14+20h]
0x14004f105  xor     r12d, r12d
0x14004f108  test    eax, eax
0x14004f10a  mov     rcx, rdi; hExistingToken
0x14004f10d  mov     esi, eax
0x14004f10f  setnz   [rsp+1B0h+var_15F]
0x14004f114  mov     r8d, [rdx+210h]
0x14004f11b  dec     r8d
0x14004f11e  cmp     r8d, 1
0x14004f122  setbe   r14b
0x14004f126  mov     [rsp+1B0h+var_160], r14b
0x14004f12b  call    ?IsAdmin@@YA_NPEAX@Z; IsAdmin(void *)
0x14004f130  xor     edx, edx; Val
0x14004f132  mov     [rsp+1B0h+var_170], al
0x14004f136  lea     r8d, [r12+58h]; Size
0x14004f13b  lea     rcx, [rbp+0B0h+ProtocolSubmitBuffer]; void *
0x14004f13f  call    memset_0
0x14004f144  xorps   xmm0, xmm0
0x14004f147  mov     [rbp+0B0h+LsaHandle], r12
0x14004f14b  xor     edx, edx; Val
0x14004f14d  mov     [rsp+1B0h+Buffer], r12
0x14004f152  lea     r8d, [r12+40h]; Size
0x14004f157  mov     [rsp+1B0h+var_14C], r12d
0x14004f15c  lea     rcx, [rbp+0B0h+var_F0]; void *
0x14004f160  mov     [rsp+1B0h+var_150], r12d
0x14004f165  movups  xmmword ptr [rbp+0B0h+DestinationString.Length], xmm0
0x14004f169  mov     [rsp+1B0h+AuthenticationPackage], r12d
0x14004f16e  call    memset_0
0x14004f173  mov     rcx, [rsp+1B0h+pSourceSid]
0x14004f178  lea     rdx, [rsp+1B0h+Size+4]
0x14004f17d  mov     qword ptr [rbp+0B0h+var_110], r12
0x14004f181  mov     r13d, r12d
0x14004f184  mov     dword ptr [rbp+0B0h+var_110+0Ch], r12d
0x14004f188  mov     dword ptr [rsp+1B0h+Size], r12d
0x14004f18d  mov     [rsp+1B0h+var_13C], r12d
0x14004f192  mov     dword ptr [rsp+1B0h+Size+4], r12d
0x14004f197  call    cs:__imp_LsaLookupUserAccountType
0x14004f19d  mov     edi, eax
0x14004f19f  test    eax, eax
0x14004f1a1  jns     short loc_14004F1F1
0x14004f1a3  mov     rcx, cs:WPP_GLOBAL_Control
0x14004f1aa  lea     r14, WPP_GLOBAL_Control
0x14004f1b1  cmp     rcx, r14
0x14004f1b4  jz      short loc_14004F1DE
0x14004f1b6  mov     esi, 1000h
0x14004f1bb  test    [rcx+1Ch], esi
0x14004f1be  jz      short loc_14004F1DE
0x14004f1c0  cmp     byte ptr [rcx+19h], 2
0x14004f1c4  jb      short loc_14004F1DE
0x14004f1c6  mov     rcx, [rcx+10h]
0x14004f1ca  lea     edx, [r12+4Ah]
0x14004f1cf  mov     r9d, eax
0x14004f1d2  lea     r8, WPP_1f80ccb0ea51320fbaee2b4e4d0a6e34_Traceguids
0x14004f1d9  call    WPP_SF_d
0x14004f1de  mov     ecx, edi; Status
0x14004f1e0  call    cs:__imp_RtlNtStatusToDosError
0x14004f1e6  mov     edi, eax
0x14004f1e8  mov     dword ptr [rsp+1B0h+pSourceSid], eax
0x14004f1ec  jmp     loc_14004F643
0x14004f1f1  test    esi, esi
0x14004f1f3  jz      loc_14004F63A
0x14004f1f9  xor     esi, esi
0x14004f1fb  test    r14b, r14b
0x14004f1fe  jz      loc_14004F63A
0x14004f204  cmp     [rsp+1B0h+var_170], sil
0x14004f209  jnz     loc_14004F63A
0x14004f20f  test    r15b, r15b
0x14004f212  jnz     loc_14004F63A
0x14004f218  call    IsCamCleanupDisardedCandidateAccountsPresent
0x14004f21d  test    al, al
0x14004f21f  jz      loc_14004F63A
0x14004f225  cmp     dword ptr [rsp+1B0h+Size+4], 5
0x14004f22a  jnz     loc_14004F63A
0x14004f230  movups  xmm0, cs:xmmword_1400B1CE8
0x14004f237  mov     r8, [rsp+1B0h+pSourceSid]; pSourceSid
0x14004f23c  lea     rdx, [rbp+0B0h+pDestinationSid]; pDestinationSid
0x14004f240  lea     ecx, [rsi+44h]; nDestinationSidLength
0x14004f243  mov     [rbp+0B0h+ProtocolSubmitBuffer], 0Fh
0x14004f24a  movdqu  [rbp+0B0h+var_AC], xmm0
0x14004f24f  call    cs:__imp_CopySid
0x14004f255  mov     rcx, cs:?xGlobalContext@@3U_WLSM_GLOBAL_CONTEXT@@A; this
0x14004f25c  lea     rdx, [rbp+0B0h+LsaHandle]; void **
0x14004f260  call    ?GetLsaHandle@CGlobalStore@@QEAAKPEAPEAX@Z; CGlobalStore::GetLsaHandle(void * *)
0x14004f265  mov     dword ptr [rsp+1B0h+pSourceSid], eax
0x14004f269  mov     edi, eax
0x14004f26b  test    eax, eax
0x14004f26d  jz      short loc_14004F2BB
0x14004f26f  mov     rcx, cs:WPP_GLOBAL_Control
0x14004f276  lea     r14, WPP_GLOBAL_Control
0x14004f27d  cmp     rcx, r14
0x14004f280  jz      loc_14004F643
0x14004f286  mov     esi, 1000h
0x14004f28b  test    [rcx+1Ch], esi
0x14004f28e  jz      loc_14004F643
0x14004f294  cmp     byte ptr [rcx+19h], 2
0x14004f298  jb      loc_14004F643
0x14004f29e  mov     rcx, [rcx+10h]
0x14004f2a2  lea     r8, WPP_1f80ccb0ea51320fbaee2b4e4d0a6e34_Traceguids
0x14004f2a9  mov     edx, 4Bh ; 'K'
0x14004f2ae  mov     r9d, eax
0x14004f2b1  call    WPP_SF_d
0x14004f2b6  jmp     loc_14004F643
0x14004f2bb  lea     rdx, SourceString; "CloudAP"
0x14004f2c2  lea     rcx, [rbp+0B0h+DestinationString]; DestinationString
0x14004f2c6  call    cs:__imp_RtlInitString
0x14004f2cc  mov     rcx, [rbp+0B0h+LsaHandle]; LsaHandle
0x14004f2d0  lea     r8, [rsp+1B0h+AuthenticationPackage]; AuthenticationPackage
0x14004f2d5  lea     rdx, [rbp+0B0h+DestinationString]; PackageName
0x14004f2d9  call    cs:__imp_LsaLookupAuthenticationPackage
0x14004f2df  mov     r15d, eax
0x14004f2e2  test    eax, eax
0x14004f2e4  jns     short loc_14004F329
0x14004f2e6  mov     rcx, cs:WPP_GLOBAL_Control
0x14004f2ed  lea     r14, WPP_GLOBAL_Control
0x14004f2f4  cmp     rcx, r14
0x14004f2f7  jz      short loc_14004F321
0x14004f2f9  mov     esi, 1000h
0x14004f2fe  test    [rcx+1Ch], esi
0x14004f301  jz      short loc_14004F321
0x14004f303  cmp     byte ptr [rcx+19h], 2
0x14004f307  jb      short loc_14004F321
0x14004f309  mov     edx, 4Ch ; 'L'
0x14004f30e  mov     rcx, [rcx+10h]
0x14004f312  lea     r8, WPP_1f80ccb0ea51320fbaee2b4e4d0a6e34_Traceguids
0x14004f319  mov     r9d, r15d
0x14004f31c  call    WPP_SF_d
0x14004f321  mov     ecx, r15d
0x14004f324  jmp     loc_14004F1E0
0x14004f329  mov     edx, [rsp+1B0h+AuthenticationPackage]; AuthenticationPackage
0x14004f32d  lea     rax, [rsp+1B0h+var_150]
0x14004f332  mov     rcx, [rbp+0B0h+LsaHandle]; LsaHandle
0x14004f336  lea     r8, [rbp+0B0h+ProtocolSubmitBuffer]; ProtocolSubmitBuffer
0x14004f33a  mov     [rsp+1B0h+ProtocolStatus], rax; ProtocolStatus
0x14004f33f  mov     r9d, 58h ; 'X'; SubmitBufferLength
0x14004f345  lea     rax, [rsp+1B0h+var_14C]
0x14004f34a  mov     [rsp+1B0h+ReturnBufferLength], rax; ReturnBufferLength
0x14004f34f  lea     rax, [rsp+1B0h+Buffer]
0x14004f354  mov     [rsp+1B0h+ProtocolReturnBuffer], rax; ProtocolReturnBuffer
0x14004f359  call    cs:__imp_LsaCallAuthenticationPackage
0x14004f35f  mov     r15d, eax
0x14004f362  test    eax, eax
0x14004f364  jns     short loc_14004F3A6
0x14004f366  mov     r8d, [rsp+1B0h+var_150]; __annotation("Debug", "TelemetryAssert", "NT_SUCCESS(status)", "LsaCallAuthenticationPackage with CONNECTED_PROV_UNTRUSTED_GET_ACCOUNT_INFO")
0x14004f36b  lea     rcx, aLsassExe; "lsass.exe"
0x14004f372  mov     edx, eax
0x14004f374  call    MicrosoftTelemetryAssertTriggeredArgs
0x14004f379  mov     rcx, cs:WPP_GLOBAL_Control
0x14004f380  lea     r14, WPP_GLOBAL_Control
0x14004f387  cmp     rcx, r14
0x14004f38a  jz      short loc_14004F321
0x14004f38c  mov     esi, 1000h
0x14004f391  test    [rcx+1Ch], esi
0x14004f394  jz      short loc_14004F321
0x14004f396  cmp     byte ptr [rcx+19h], 2
0x14004f39a  jb      short loc_14004F321
0x14004f39c  mov     edx, 4Dh ; 'M'
0x14004f3a1  jmp     loc_14004F30E
0x14004f3a6  cmp     [rsp+1B0h+Buffer], rsi
0x14004f3ab  jnz     short loc_14004F3C1
0x14004f3ad  mov     r8d, [rsp+1B0h+var_150]; __annotation("Debug", "TelemetryAssert", "returnBuffer", "LsaCallAuthenticationPackage with CONNECTED_PROV_UNTRUSTED_GET_ACCOUNT_INFO returnBuffer not null")
0x14004f3b2  lea     rcx, aLsassExe; "lsass.exe"
0x14004f3b9  mov     edx, r15d
0x14004f3bc  call    MicrosoftTelemetryAssertTriggeredArgs
0x14004f3c1  mov     eax, [rsp+1B0h+var_14C]
0x14004f3c5  cmp     eax, 8
0x14004f3c8  jnb     short loc_14004F3E2
0x14004f3ca  mov     r8d, 8; __annotation("Debug", "TelemetryAssert", "returnBufferSize >= sizeof(PCLOUD_AP_GET_ACCOUNT_INFO_OUTPUT)", "LsaCallAuthenticationPackage with CONNECTED_PROV_UNTRUSTED_GET_ACCOUNT_INFO returnBufferSize invalid")
0x14004f3d0  lea     rcx, aLsassExe; "lsass.exe"
0x14004f3d7  mov     edx, eax
0x14004f3d9  call    MicrosoftTelemetryAssertTriggeredArgs
0x14004f3de  mov     eax, [rsp+1B0h+var_14C]
0x14004f3e2  cmp     [rsp+1B0h+Buffer], rsi
0x14004f3e7  jz      loc_14004F5FB
0x14004f3ed  cmp     eax, 8
0x14004f3f0  jb      loc_14004F5FB
0x14004f3f6  mov     r9d, [rsp+1B0h+var_150]
0x14004f3fb  test    r9d, r9d
0x14004f3fe  jns     short loc_14004F417
0x14004f400  xor     r8d, r8d; __annotation("Debug", "TelemetryAssert", "NT_SUCCESS(subStatus)", "LsaCallAuthenticationPackage with CONNECTED_PROV_UNTRUSTED_GET_ACCOUNT_INFO SubStatus")
0x14004f403  lea     rcx, aLsassExe; "lsass.exe"
0x14004f40a  mov     edx, r9d
0x14004f40d  call    MicrosoftTelemetryAssertTriggeredArgs
0x14004f412  mov     r9d, [rsp+1B0h+var_150]
0x14004f417  mov     rcx, cs:WPP_GLOBAL_Control
0x14004f41e  lea     r14, WPP_GLOBAL_Control
0x14004f425  mov     esi, 1000h
0x14004f42a  cmp     rcx, r14
0x14004f42d  jz      short loc_14004F44F
0x14004f42f  test    [rcx+1Ch], esi
0x14004f432  jz      short loc_14004F44F
0x14004f434  cmp     byte ptr [rcx+19h], 5
0x14004f438  jb      short loc_14004F44F
0x14004f43a  mov     rcx, [rcx+10h]
0x14004f43e  lea     r8, WPP_1f80ccb0ea51320fbaee2b4e4d0a6e34_Traceguids
0x14004f445  mov     edx, 4Fh ; 'O'
0x14004f44a  call    WPP_SF_d
0x14004f44f  mov     r15, [rsp+1B0h+Buffer]
0x14004f454  movzx   eax, word ptr [r15+2Ah]
0x14004f459  add     eax, 40h ; '@'
0x14004f45c  mov     ecx, eax; unsigned __int64
0x14004f45e  mov     dword ptr [rsp+1B0h+Size], eax
0x14004f462  call    ?WLAlloc@@YAPEAX_K@Z; WLAlloc(unsigned __int64)
0x14004f467  mov     r13, rax
0x14004f46a  test    rax, rax
0x14004f46d  jnz     short loc_14004F4A1
0x14004f46f  lea     edi, [rax+0Eh]
0x14004f472  mov     dword ptr [rsp+1B0h+pSourceSid], edi
0x14004f476  mov     rcx, cs:WPP_GLOBAL_Control
0x14004f47d  cmp     rcx, r14
0x14004f480  jz      loc_14004F643
0x14004f486  test    [rcx+1Ch], esi
0x14004f489  jz      loc_14004F643
0x14004f48f  cmp     byte ptr [rcx+19h], 2
0x14004f493  jb      loc_14004F643
0x14004f499  lea     edx, [rax+50h]
0x14004f49c  jmp     loc_14004F5E9
0x14004f4a1  movzx   eax, word ptr [r15+28h]
0x14004f4a6  lea     rcx, [r13+40h]; void *
0x14004f4aa  mov     [rbp+0B0h+var_D8], ax
0x14004f4ae  movzx   eax, word ptr [r15+2Ah]
0x14004f4b3  mov     [rbp+0B0h+var_D6], ax
0x14004f4b7  movaps  xmm1, xmmword ptr [rbp-30h]
0x14004f4bb  mov     dword ptr [rbp+0B0h+var_F0], 54h ; 'T'
0x14004f4c2  movaps  xmm0, [rbp+0B0h+var_F0]
0x14004f4c6  movups  xmmword ptr [r13+0], xmm0
0x14004f4cb  mov     qword ptr [rbp+0B0h+var_D0], 40h ; '@'
0x14004f4d3  movaps  xmm0, [rbp+0B0h+var_D0]
0x14004f4d7  movups  xmmword ptr [r13+10h], xmm1
0x14004f4dc  mov     [rbp+0B0h+var_B8], rbx
0x14004f4e0  movaps  xmm1, xmmword ptr [rbp-10h]
0x14004f4e4  movups  xmmword ptr [r13+20h], xmm0
0x14004f4e9  movups  xmmword ptr [r13+30h], xmm1
0x14004f4ee  movzx   r8d, word ptr [r15+2Ah]; Size
0x14004f4f3  mov     rdx, [r15+30h]; Src
0x14004f4f7  call    memcpy_0
0x14004f4fc  mov     ebx, dword ptr [rsp+1B0h+Size]
0x14004f500  mov     dword ptr [rbp+0B0h+var_110+8], ebx
0x14004f503  lea     r15d, [rbx+18h]
0x14004f507  mov     ecx, r15d; unsigned __int64
0x14004f50a  mov     [rsp+1B0h+var_13C], r15d
0x14004f50f  call    ?WLAlloc@@YAPEAX_K@Z; WLAlloc(unsigned __int64)
0x14004f514  mov     r12, rax
0x14004f517  test    rax, rax
0x14004f51a  jnz     short loc_14004F54E
0x14004f51c  lea     edi, [rax+0Eh]
0x14004f51f  mov     dword ptr [rsp+1B0h+pSourceSid], edi
0x14004f523  mov     rcx, cs:WPP_GLOBAL_Control
0x14004f52a  cmp     rcx, r14
0x14004f52d  jz      loc_14004F643
0x14004f533  test    [rcx+1Ch], esi
0x14004f536  jz      loc_14004F643
0x14004f53c  cmp     byte ptr [rcx+19h], 2
0x14004f540  jb      loc_14004F643
0x14004f546  lea     edx, [rax+51h]
0x14004f549  jmp     loc_14004F5E9
0x14004f54e  movups  xmm0, [rbp+0B0h+var_110]
0x14004f552  lea     rcx, [rax+18h]; void *
0x14004f556  mov     r8, rbx; Size
0x14004f559  mov     rdx, r13; Src
0x14004f55c  movups  xmmword ptr [rax], xmm0
0x14004f55f  mov     [rax+10h], r13
0x14004f563  call    memcpy_0
0x14004f568  mov     rax, [rbp+0B0h+var_128]
0x14004f56c  mov     r8d, r15d
0x14004f56f  mov     rdx, r12
0x14004f572  mov     rcx, [rax+20h]
0x14004f576  mov     rcx, [rcx+88h]
0x14004f57d  call    cs:__imp_CamConnectCandidateUser
0x14004f583  mov     ebx, eax
0x14004f585  test    eax, eax
0x14004f587  jns     short loc_14004F5CD
0x14004f589  mov     rcx, cs:WPP_GLOBAL_Control
0x14004f590  cmp     rcx, r14
0x14004f593  jz      short loc_14004F5B8
0x14004f595  test    [rcx+1Ch], esi
0x14004f598  jz      short loc_14004F5B8
0x14004f59a  cmp     byte ptr [rcx+19h], 2
0x14004f59e  jb      short loc_14004F5B8
  ... truncated ...
```
