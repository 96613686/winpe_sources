# SpInitLsaModeContext(unsigned __int64,unsigned __int64,_UNICODE_STRING *,ulong,ulong,_SecBufferDesc *,unsigned __int64 *,_SecBufferDesc *,ulong *,_LARGE_INTEGER *,uchar *,_SecBuffer *)

- ea: `0x180006650`
- end: `0x180007b70`
- name: `?SpInitLsaModeContext@@YAJ_K0PEAU_UNICODE_STRING@@KKPEAU_SecBufferDesc@@PEA_K2PEAKPEAT_LARGE_INTEGER@@PEAEPEAU_SecBuffer@@@Z`
- size: `5408`
- prototype: `__int64 __fastcall(struct _TS_CREDENTIAL *, struct _TS_CONTEXT *, struct _UNICODE_STRING *, int, unsigned int TargetDataRep, struct _SecBufferDesc *, unsigned __int64 *, struct _SecBufferDesc *, unsigned int *, PTimeStamp ptsExpiry, unsigned __int8 *, struct _SecBuffer *)`
- caller_count: `0`
- callee_count: `34`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800022e0`
- `0x1800032c0`
- `0x180003830`
- `0x180003e00`
- `0x180003ea0`
- `0x180004460`
- `0x180004f20`
- `0x1800059a8`
- `0x180005ed0`
- `0x180006650`
- `0x180007df0`
- `0x180008840`
- `0x1800099a8`
- `0x18000a480`
- `0x18000c1a4`
- `0x180014720`
- `0x180014a84`
- `0x18001627c`
- `0x1800168c4`
- `0x180016ac8`
- `0x180016eec`
- `0x180017580`
- `0x180017590`
- `0x180017704`
- `0x1800182f0`
- `0x180018898`
- `0x180018f38`
- `0x180019404`
- `0x180019460`
- `0x18001b810`
- `0x18001bae0`
- `0x18001c630`
- `0x18001c63c`
- `0x18001d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180007048`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800074f5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180007048`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800074f5`
- `SspiCli!CompleteAuthToken` at `0x180006f84`
- `SspiCli!CompleteAuthToken` at `0x180006f84`
- `SspiCli!QueryContextAttributesW` at `0x180007023`
- `SspiCli!QueryContextAttributesW` at `0x1800072d3`
- `SspiCli!QueryContextAttributesW` at `0x1800074d2`
- `SspiCli!QueryContextAttributesW` at `0x180007564`
- `SspiCli!QueryContextAttributesW` at `0x180007023`
- `SspiCli!QueryContextAttributesW` at `0x1800072d3`
- `SspiCli!QueryContextAttributesW` at `0x1800074d2`
- `SspiCli!QueryContextAttributesW` at `0x180007564`
- `SspiCli!FreeContextBuffer` at `0x18000690d`
- `SspiCli!FreeContextBuffer` at `0x18000691c`
- `SspiCli!FreeContextBuffer` at `0x180007077`
- `SspiCli!FreeContextBuffer` at `0x180007a65`
- `SspiCli!FreeContextBuffer` at `0x18000690d`
- `SspiCli!FreeContextBuffer` at `0x18000691c`
- `SspiCli!FreeContextBuffer` at `0x180007077`
- `SspiCli!FreeContextBuffer` at `0x180007a65`
- `SspiCli!InitializeSecurityContextW` at `0x180006f4a`
- `SspiCli!InitializeSecurityContextW` at `0x180006f4a`
- `ntdll!RtlGetLastNtStatus` at `0x180006f5c`
- `ntdll!RtlGetLastNtStatus` at `0x180006f5c`

## pseudocode

```c
__int64 __fastcall SpInitLsaModeContext(
        struct _TS_CREDENTIAL *a1,
        struct _TS_CONTEXT *a2,
        struct _UNICODE_STRING *a3,
        int a4,
        unsigned int TargetDataRep,
        struct _SecBufferDesc *a6,
        unsigned __int64 *a7,
        struct _SecBufferDesc *a8,
        unsigned int *a9,
        PTimeStamp ptsExpiry,
        unsigned __int8 *a11,
        struct _SecBuffer *a12)
{
  struct _TS_CONTEXT *v13; // rsi
  struct _TS_CONTEXT *v15; // rdi
  unsigned __int16 *v16; // r14
  int v17; // edx
  int v18; // r8d
  _QWORD *v19; // r10
  struct _SecBuffer *v21; // rdx
  struct _SecBuffer *v22; // r12
  __int64 v23; // rcx
  struct _SecBuffer *v24; // rsi
  int v25; // eax
  int LastNtStatus; // ebx
  unsigned int cBuffers; // edx
  PSecBuffer pBuffers; // r8
  int v29; // ecx
  struct _SecBuffer *v30; // r15
  __int64 v31; // rcx
  __int64 v32; // rdx
  unsigned int v33; // esi
  wchar_t *v34; // r13
  void *v35; // r12
  struct _TS_PRIMARY_CREDENTIAL *v36; // r15
  int v37; // eax
  unsigned __int8 v38; // r8
  struct _UNICODE_STRING *v39; // rcx
  __int64 v40; // rax
  __int64 v41; // r8
  const void **v42; // rbx
  __int64 v43; // rcx
  unsigned __int16 *v44; // rax
  unsigned __int16 *v45; // rsi
  int v46; // edx
  struct _SecBuffer *v47; // r8
  _DWORD *pvBuffer; // rax
  int v49; // eax
  int v50; // eax
  struct _SecHandle *v51; // rdx
  SECURITY_STATUS v52; // eax
  SECURITY_STATUS v53; // eax
  unsigned int v54; // ecx
  __int64 v55; // r8
  unsigned int v56; // edx
  unsigned int v57; // esi
  unsigned int v58; // ecx
  unsigned int v59; // edx
  unsigned __int8 *v60; // rcx
  unsigned int v61; // eax
  size_t v62; // rcx
  bool v63; // cc
  void *v64; // rax
  int v65; // eax
  struct _TS_PRIMARY_CREDENTIAL *v66; // rax
  __int128 *v67; // rsi
  unsigned int v68; // ecx
  unsigned int v69; // edx
  __int128 v70; // xmm0
  __int128 v71; // xmm1
  __int128 v72; // xmm0
  __int128 v73; // xmm1
  __int128 v74; // xmm0
  __int128 v75; // xmm1
  __int128 v76; // xmm0
  __int128 v77; // xmm1
  __int128 v78; // xmm0
  __int128 v79; // xmm1
  __int128 v80; // xmm0
  __int128 v81; // xmm1
  __int128 v82; // xmm0
  __int128 v83; // xmm1
  wchar_t *v84; // rax
  __int64 v85; // rdx
  __int64 v86; // rax
  unsigned int v87; // esi
  bool v88; // zf
  unsigned int v89; // edi
  void (*FreePrivateHeap)(void); // rax
  void (*FreeHeap)(void); // rax
  unsigned __int8 *v92; // rcx
  __int64 v93; // rdx
  unsigned __int8 *v94; // rax
  void (*v95)(void); // rax
  void (*v96)(void); // rax
  unsigned int Reserved1; // [rsp+20h] [rbp-E0h]
  unsigned int pInput; // [rsp+30h] [rbp-D0h]
  struct _TS_PRIMARY_CREDENTIAL *v99; // [rsp+60h] [rbp-A0h]
  wchar_t *Str; // [rsp+68h] [rbp-98h] BYREF
  void *Buf1; // [rsp+70h] [rbp-90h] BYREF
  SEC_WCHAR *v102; // [rsp+78h] [rbp-88h]
  int v103; // [rsp+80h] [rbp-80h] BYREF
  size_t pfContextAttr; // [rsp+84h] [rbp-7Ch] BYREF
  SEC_WCHAR *pszTargetName; // [rsp+90h] [rbp-70h] BYREF
  size_t Size; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int8 *Src; // [rsp+A0h] [rbp-60h] BYREF
  struct _SecBuffer *pBuffer; // [rsp+A8h] [rbp-58h] BYREF
  PVOID v109; // [rsp+B0h] [rbp-50h] BYREF
  int v110; // [rsp+B8h] [rbp-48h] BYREF
  int v111; // [rsp+BCh] [rbp-44h] BYREF
  unsigned int v112; // [rsp+C0h] [rbp-40h] BYREF
  unsigned int v113; // [rsp+C4h] [rbp-3Ch] BYREF
  struct _SecBufferDesc v114; // [rsp+C8h] [rbp-38h] BYREF
  struct _TS_PRIMARY_CREDENTIAL *v115; // [rsp+D8h] [rbp-28h] BYREF
  size_t v116[2]; // [rsp+E0h] [rbp-20h] BYREF
  struct _TS_CONTEXT *v117; // [rsp+F0h] [rbp-10h] BYREF
  PVOID pvContextBuffer; // [rsp+F8h] [rbp-8h] BYREF
  unsigned __int8 *v119; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int8 *v120; // [rsp+108h] [rbp+8h] BYREF
  struct _SecBufferDesc pToken; // [rsp+110h] [rbp+10h] BYREF
  struct _SecBuffer *v122; // [rsp+120h] [rbp+20h]
  PVOID v123[2]; // [rsp+128h] [rbp+28h] BYREF
  struct _SecBuffer *v124; // [rsp+138h] [rbp+38h]
  __int128 v125; // [rsp+140h] [rbp+40h] BYREF
  __int128 v126; // [rsp+150h] [rbp+50h]
  __int128 v127; // [rsp+160h] [rbp+60h]
  __int128 v128; // [rsp+170h] [rbp+70h]
  __int128 v129; // [rsp+180h] [rbp+80h]
  __int128 v130; // [rsp+190h] [rbp+90h]
  __int128 v131; // [rsp+1A0h] [rbp+A0h]
  __int128 v132; // [rsp+1B0h] [rbp+B0h]
  __int128 v133; // [rsp+1C0h] [rbp+C0h]
  __int128 v134; // [rsp+1D0h] [rbp+D0h]
  __int128 v135; // [rsp+1E0h] [rbp+E0h]
  __int128 v136; // [rsp+1F0h] [rbp+F0h]
  __int128 v137; // [rsp+200h] [rbp+100h]
  __int128 v138; // [rsp+210h] [rbp+110h]
  __int64 v139; // [rsp+220h] [rbp+120h]
  SECURITY_STATUS v140; // [rsp+280h] [rbp+180h]

  v111 = 0;
  v99 = 0;
  v115 = 0;
  v13 = a2;
  v117 = 0;
  v102 = 0;
  pszTargetName = 0;
  v120 = 0;
  v15 = 0;
  v113 = 0;
  v114 = 0;
  v16 = 0;
  v103 = 0;
  pToken = 0;
  Src = 0;
  *(_OWORD *)v116 = 0;
  pfContextAttr = 0;
  *(_OWORD *)v123 = 0;
  Buf1 = 0;
  Size = 0;
  v119 = 0;
  v112 = 0;
  v110 = 0;
  Str = 0;
  memset_0(&v125, 0, 0xE8u);
  pvContextBuffer = 0;
  v109 = 0;
  v19 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_qqZ(*((_QWORD *)WPP_GLOBAL_Control + 2), v17, v18, (_DWORD)a1, (char)v13, (__int64)a3);
    v19 = WPP_GLOBAL_Control;
  }
  if ( !a1 && !v13 )
    return 2148074241LL;
  if ( !a8 )
    return 3221225485LL;
  v21 = 0;
  v22 = 0;
  v140 = 0;
  v122 = 0;
  pBuffer = 0;
  if ( !a6 )
    goto LABEL_26;
  if ( !a6->cBuffers )
  {
    v16 = 0;
    goto LABEL_26;
  }
  while ( 1 )
  {
    v23 = (unsigned int)v16;
    v24 = &a6->pBuffers[v23];
    v25 = v24->BufferType & 0xFFFFFFF;
    if ( !v22 )
    {
      if ( v25 == 2 && v24->cbBuffer )
      {
        LastNtStatus = ((__int64 (__fastcall *)(struct _SecBuffer *, struct _SecBuffer *))TSGlobalLsaFunctions->MapBuffer)(
                         &a6->pBuffers[v23],
                         &a6->pBuffers[v23]);
        if ( LastNtStatus < 0 )
          goto LABEL_290;
        v21 = pBuffer;
        v22 = v24;
      }
      goto LABEL_21;
    }
    if ( v21 )
      break;
    if ( v25 == 2 )
    {
      LastNtStatus = ((__int64 (__fastcall *)(struct _SecBuffer *, struct _SecBuffer *))TSGlobalLsaFunctions->MapBuffer)(
                       &a6->pBuffers[v23],
                       &a6->pBuffers[v23]);
      if ( LastNtStatus < 0 )
      {
LABEL_290:
        v35 = Buf1;
        v33 = 0;
        v16 = v102;
        v34 = Str;
        goto LABEL_37;
      }
      v21 = v24;
      pBuffer = v24;
    }
LABEL_21:
    LODWORD(v16) = (_DWORD)v16 + 1;
    if ( (unsigned int)v16 >= a6->cBuffers )
    {
      v19 = WPP_GLOBAL_Control;
      v16 = 0;
      v13 = a2;
      goto LABEL_26;
    }
  }
  if ( v25 != 2 )
    goto LABEL_21;
  LastNtStatus = ((__int64 (__fastcall *)(struct _SecBuffer *, struct _SecBuffer *))TSGlobalLsaFunctions->MapBuffer)(
                   &a6->pBuffers[v23],
                   &a6->pBuffers[v23]);
  if ( LastNtStatus < 0 )
    goto LABEL_293;
  v19 = WPP_GLOBAL_Control;
  v16 = 0;
  v122 = v24;
  v13 = a2;
LABEL_26:
  cBuffers = a8->cBuffers;
  if ( !cBuffers )
  {
LABEL_30:
    LastNtStatus = -1073741811;
    if ( v19 != &WPP_GLOBAL_Control && (*((_BYTE *)v19 + 28) & 1) != 0 )
    {
      v31 = v19[2];
      v32 = 11;
      goto LABEL_33;
    }
    goto LABEL_34;
  }
  pBuffers = a8->pBuffers;
  v29 = 0;
  while ( 1 )
  {
    v30 = &pBuffers[v29];
    v124 = v30;
    if ( (v30->BufferType & 0xFFFFFFF) == 2 )
      break;
    if ( ++v29 >= cBuffers )
      goto LABEL_30;
  }
  LastNtStatus = ((__int64 (__fastcall *)(struct _SecBuffer *, struct _SecBuffer *))TSGlobalLsaFunctions->MapBuffer)(
                   &pBuffers[v29],
                   &pBuffers[v29]);
  if ( LastNtStatus < 0 )
  {
LABEL_293:
    v16 = 0;
    goto LABEL_34;
  }
  if ( !v30 )
  {
    v19 = WPP_GLOBAL_Control;
    goto LABEL_30;
  }
  if ( v13 )
  {
    if ( !v22 )
    {
      LastNtStatus = -1073741811;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v31 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        v32 = 19;
LABEL_33:
        WPP_SF_(v31, v32, WPP_82746c11848034a638789f4e0723fe0c_Traceguids);
      }
LABEL_34:
      v33 = 0;
      goto LABEL_35;
    }
    v15 = v13;
    if ( *((_DWORD *)v13 + 31) == 1 )
      goto LABEL_103;
    if ( a1 && *((struct _TS_CREDENTIAL **)v13 + 2) != a1 )
    {
      v33 = -2146893002;
      goto LABEL_35;
    }
    v42 = (const void **)((char *)v13 + 64);
    if ( v13 == (struct _TS_CONTEXT *)-64LL )
    {
LABEL_103:
      v33 = 0;
      LastNtStatus = -1073741811;
      goto LABEL_35;
    }
    v43 = *(unsigned __int16 *)v42;
    a1 = (struct _TS_CREDENTIAL *)*((_QWORD *)v13 + 2);
    if ( (_WORD)v43 )
    {
      v44 = (unsigned __int16 *)TSAllocate(v43 + 2);
      v45 = v44;
      if ( !v44 )
      {
        v33 = 0;
        LastNtStatus = -1073741670;
        goto LABEL_35;
      }
      memcpy_0(v44, v42[1], *(unsigned __int16 *)v42);
      v16 = v45;
      v102 = v45;
      v13 = a2;
    }
    LastNtStatus = TSParseBuffers(v22, &v114, 0, 0, &Src, (unsigned int *)&pfContextAttr, &v112, &v111, 0, 0);
    if ( LastNtStatus < 0 )
      goto LABEL_60;
    if ( v111 >= 0 )
    {
      v50 = *((_DWORD *)v13 + 29);
      if ( v50 )
      {
        if ( v50 != v112 )
        {
          v33 = 0;
          LastNtStatus = -2146893048;
          goto LABEL_35;
        }
      }
      else
      {
        if ( !v112 )
        {
          v33 = 0;
          LastNtStatus = -2146893048;
          goto LABEL_35;
        }
        *((_DWORD *)v13 + 29) = v112;
      }
      goto LABEL_134;
    }
    v46 = 0;
    LastNtStatus = v111;
    if ( !v114.cBuffers )
    {
      v33 = 0;
      goto LABEL_35;
    }
    while ( 1 )
    {
      v47 = &v114.pBuffers[v46];
      if ( (v47->BufferType & 0xFFFFFFF) == 2 )
        break;
      if ( ++v46 >= v114.cBuffers )
      {
        v33 = 0;
        goto LABEL_35;
      }
    }
    pvBuffer = v47->pvBuffer;
    if ( !pvBuffer || !*pvBuffer )
      goto LABEL_60;
    v49 = TSGetUserNameFromCreds(v13, &Str);
    v34 = Str;
    if ( v49 >= 0 && Str && *Str && !wcschr(Str, 0x40u) )
      LastNtStatus = -2146892951;
    v33 = 0;
    goto LABEL_36;
  }
  if ( v22 )
  {
    LastNtStatus = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v31 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v32 = 12;
      goto LABEL_33;
    }
    goto LABEL_34;
  }
  v37 = TSAllocateContext(&v117, 0);
  v15 = v117;
  LastNtStatus = v37;
  if ( v37 < 0 )
    goto LABEL_60;
  v39 = (struct _UNICODE_STRING *)((char *)v117 + 64);
  *((_DWORD *)v117 + 32) = a4;
  LastNtStatus = TSDuplicateStringEx(v39, a3, v38);
  if ( LastNtStatus < 0 )
    goto LABEL_60;
  LastNtStatus = TSUnicodeStringToString(&pszTargetName, (struct _UNICODE_STRING *)v15 + 4);
  if ( LastNtStatus < 0 )
    goto LABEL_59;
  LastNtStatus = ((__int64 (__fastcall *)(int *))TSGlobalLsaFunctions->GetExtendedCallFlags)(&v110);
  if ( LastNtStatus < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_82746c11848034a638789f4e0723fe0c_Traceguids);
LABEL_59:
    v16 = pszTargetName;
LABEL_60:
    v33 = v140;
    goto LABEL_35;
  }
  v40 = *((_QWORD *)a1 + 18);
  if ( !v40 && (v110 & 4) != 0 )
  {
    LastNtStatus = -2146893042;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_59;
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_82746c11848034a638789f4e0723fe0c_Traceguids);
    v16 = pszTargetName;
    v33 = 0;
    goto LABEL_35;
  }
  if ( (*((_BYTE *)a1 + 108) & 1) != 0 && (*((_BYTE *)v15 + 128) & 1) != 0 )
  {
    LastNtStatus = -2146892963;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_59;
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_82746c11848034a638789f4e0723fe0c_Traceguids);
    v16 = pszTargetName;
    v33 = 0;
    goto LABEL_35;
  }
  if ( !v40 )
  {
    if ( a3 )
    {
      if ( a3->Length )
      {
        LastNtStatus = TSLookForCredmanCreds(
                         a3,
                         (struct _LUID *)a1 + 14,
                         *((_DWORD *)v15 + 32) & 1,
                         (struct _TS_PRIMARY_CREDENTIAL **)v15 + 19);
        if ( LastNtStatus == -1073741275 )
          LastNtStatus = 0;
      }
    }
  }
  if ( *((_QWORD *)a1 + 18) )
  {
    *((_DWORD *)v15 + 36) = 2;
  }
  else if ( *((_QWORD *)v15 + 19) )
  {
    *((_DWORD *)v15 + 36) = 1;
  }
  else
  {
    if ( !*((_QWORD *)a1 + 17) && (*((_BYTE *)v15 + 128) & 1) != 0 )
    {
      v16 = pszTargetName;
      v33 = -2146893042;
      goto LABEL_35;
    }
    *((_DWORD *)v15 + 36) = 0;
  }
  v88 = (*((_BYTE *)v15 + 128) & 1) == 0;
  v16 = pszTargetName;
  v102 = pszTargetName;
  if ( !v88 )
  {
    if ( *((_DWORD *)v15 + 36) || !TSIsLoopback(pszTargetName) )
    {
      if ( (int)IsDelegationAllowed(v16, *((unsigned int *)v15 + 36), &v103) < 0 || !v103 )
      {
        if ( v16 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, v41, v16);
        }
        else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_82746c11848034a638789f4e0723fe0c_Traceguids);
        }
        TSAuditPolicyFailure(a1, v15, v16);
        v33 = -2146892962;
        goto LABEL_35;
      }
    }
    else
    {
      *((_BYTE *)v15 + 140) = 1;
    }
  }
LABEL_134:
  if ( pBuffer && !*((_QWORD *)v15 + 10) )
  {
    LastNtStatus = TSGetPublicKeyFromCertChain(
                     *((_DWORD *)v15 + 29),
                     pBuffer,
                     v122,
                     v16,
                     (unsigned __int8 **)v15 + 10,
                     (unsigned int *)v15 + 22,
                     (unsigned __int8 *)v15 + 92,
                     (struct _CERT_TRUST_STATUS *)((char *)v15 + 132));
    if ( LastNtStatus >= 0 )
    {
      if ( *((_DWORD *)v15 + 22) < 4u )
      {
        v33 = 0;
        LastNtStatus = -2146893043;
        goto LABEL_35;
      }
      goto LABEL_139;
    }
LABEL_199:
    v33 = v140;
    goto LABEL_35;
  }
LABEL_139:
  if ( Src )
  {
    v103 = 0;
    v140 = QueryContextAttributesW((PCtxtHandle)((char *)v15 + 24), 0x25u, &v103);
    v33 = v140;
    if ( v140 >= 0 )
    {
      if ( v103 )
        *((_DWORD *)a1 + 27) &= ~1u;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_82746c11848034a638789f4e0723fe0c_Traceguids);
      v103 = 0;
      v33 = 0;
      v140 = 0;
    }
    LastNtStatus = TSDecryptBuffer(
                     (PCtxtHandle)((char *)v15 + 24),
                     Src,
                     (unsigned int)pfContextAttr,
                     (unsigned __int8 **)&Buf1,
                     (unsigned int *)&Size);
    if ( LastNtStatus >= 0 )
    {
      v61 = *((_DWORD *)v15 + 29);
      if ( v61 >= 5 )
      {
        v35 = Buf1;
        if ( (_DWORD)Size != 32 )
        {
          v16 = v102;
          LastNtStatus = -2146893044;
          v34 = Str;
          goto LABEL_37;
        }
        if ( memcmp_0(Buf1, (char *)v15 + 248, 0x20u) )
        {
          LastNtStatus = -2146893044;
LABEL_213:
          v16 = v102;
          goto LABEL_214;
        }
        goto LABEL_223;
      }
      v62 = (unsigned int)Size;
      if ( (_DWORD)Size == *((_DWORD *)v15 + 22) )
      {
        v63 = v61 <= 1;
        v64 = Buf1;
        if ( v63 )
          --*(_DWORD *)Buf1;
        else
          --*(_BYTE *)Buf1;
        v65 = memcmp_0(v64, *((const void **)v15 + 10), v62);
        v35 = Buf1;
        if ( v65 )
        {
          v16 = v102;
          LastNtStatus = -2146893044;
          v34 = Str;
          goto LABEL_37;
        }
LABEL_223:
        if ( !*((_DWORD *)v15 + 30) && (*((_BYTE *)v15 + 128) & 2) != 0 )
        {
          v16 = v102;
          v33 = -2146892957;
          v34 = Str;
          goto LABEL_37;
        }
        if ( *((_BYTE *)v15 + 140) )
        {
          v66 = (struct _TS_PRIMARY_CREDENTIAL *)TSAllocate(0xE8u);
          v99 = v66;
          if ( !v66 )
          {
LABEL_228:
            LastNtStatus = -1073741670;
            goto LABEL_229;
          }
          *(_DWORD *)v66 = 4;
LABEL_267:
          LastNtStatus = TSPackCreds(v66, &v119, (unsigned int *)&Size + 1);
          if ( LastNtStatus < 0 )
            goto LABEL_213;
          LastNtStatus = TSEncryptBuffer((PCtxtHandle)((char *)v15 + 24), v119, HIDWORD(Size), &v120, &v113);
          if ( LastNtStatus < 0 )
            goto LABEL_213;
          LastNtStatus = TSPackBuffers(0, v120, v113, 0, 0, (struct _SecBuffer *)v116, 0, 0, 0);
          if ( LastNtStatus >= 0 )
          {
            LastNtStatus = TSMapContext(v15, a11, a12);
            if ( LastNtStatus >= 0 )
            {
              *((_DWORD *)v15 + 31) = 1;
              goto LABEL_272;
            }
          }
LABEL_229:
          v33 = v140;
          v16 = v102;
          v34 = Str;
          goto LABEL_37;
        }
        if ( (*((_BYTE *)v15 + 128) & 1) == 0 && (*((_BYTE *)a1 + 108) & 1) == 0 )
        {
          v66 = (struct _TS_PRIMARY_CREDENTIAL *)TSAllocate(0xE8u);
          v99 = v66;
          if ( !v66 )
            goto LABEL_228;
          *(_DWORD *)v66 = 1;
          goto LABEL_267;
        }
        v67 = (__int128 *)*((_QWORD *)a1 + 18);
        if ( v67 )
          goto LABEL_239;
        v67 = (__int128 *)*((_QWORD *)v15 + 19);
        if ( v67 )
          goto LABEL_239;
        v67 = (__int128 *)*((_QWORD *)a1 + 17);
        if ( !v67 )
        {
          if ( (*((_BYTE *)a1 + 108) & 1) == 0 )
          {
            v16 = v102;
            v33 = -2146893042;
            v34 = Str;
            goto LABEL_37;
          }
          goto LABEL_261;
        }
        if ( v67 == *((__int128 **)v15 + 19) )
        {
LABEL_239:
          v140 = QueryContextAttributesW((PCtxtHandle)((char *)v15 + 24), 0xAu, &pvContextBuffer);
          if ( v140 < 0 )
            goto LABEL_213;
          if ( !(unsigned int)_o__wcsicmp(*((_QWORD *)pvContextBuffer + 2), L"pku2u") && !*((_WORD *)v67 + 4) )
          {
            v68 = 0;
            v69 = *((unsigned __int16 *)v67 + 12) >> 1;
            if ( v69 )
            {
              while ( *(_WORD *)(*((_QWORD *)v67 + 4) + 2LL * v68) != 92 )
              {
                if ( ++v68 >= v69 )
                  goto LABEL_245;
              }
            }
            else
            {
LABEL_245:
              if ( v68 == v69 && *((_WORD *)v67 + 12) )
              {
                v140 = QueryContextAttributesW((PCtxtHandle)((char *)v15 + 24), 1u, &v109);
                if ( v140 < 0 )
                  goto LABEL_213;
                if ( v109 && *(_WORD *)v109 )
                {
                  v70 = *v67;
                  v71 = v67[1];
                  v139 = *((_QWORD *)v67 + 28);
                  v125 = v70;
                  v72 = v67[2];
                  v126 = v71;
                  v73 = v67[3];
                  v127 = v72;
                  v74 = v67[4];
                  v128 = v73;
                  v75 = v67[5];
                  v129 = v74;
                  v76 = v67[6];
                  v130 = v75;
                  v77 = v67[7];
                  v131 = v76;
                  v78 = v67[8];
                  v132 = v77;
                  v79 = v67[9];
                  v133 = v78;
                  v80 = v67[10];
                  v134 = v79;
                  v81 = v67[11];
                  v135 = v80;
                  v82 = v67[12];
                  v136 = v81;
                  v83 = v67[13];
                  v137 = v82;
                  v138 = v83;
                  v84 = wcschr((const wchar_t *)v109, 0x5Cu);
                  v85 = -1;
                  do
                    ++v85;
                  while ( *((_WORD *)v109 + v85) );
                  if ( v84 )
                  {
                    v86 = ((char *)v84 - (_BYTE *)v109) >> 1;
                    if ( !(_WORD)v86
                      || (unsigned int)(unsigned __int16)v86 + 1 < (unsigned __int16)v86
                      || (unsigned int)(unsigned __int16)v86 + 1 > (unsigned __int16)v85 )
                    {
                      v33 = v140;
                      LastNtStatus = -1073741726;
                      v16 = v102;
                      v34 = Str;
                      goto LABEL_37;
                    }
                    *(_QWORD *)&v126 = v109;
                    WORD4(v125) = 2 * v86;
                    WORD4(v126) = 2 * (v85 - v86) - 2;
                    WORD5(v126) = WORD4(v126);
                    WORD5(v125) = 2 * v86;
                    *(_QWORD *)&v127 = (char *)v109 + 2 * (unsigned __int16)v86 + 2;
                  }
                  else
                  {
                    DWORD2(v125) = 0;
                    *(_QWORD *)&v126 = 0;
                    *(_QWORD *)&v127 = v109;
                    WORD4(v126) = 2 * v85;
                    WORD5(v126) = 2 * v85;
                  }
                  v67 = &v125;
                }
              }
            }
          }
        }
        if ( (*((_BYTE *)a1 + 108) & 1) == 0 )
        {
          LastNtStatus = TSObtainClearCreds((struct _TS_PRIMARY_CREDENTIAL *)v67, &v115);
          goto LABEL_265;
        }
LABEL_261:
        ((void (__fastcall *)(_QWORD, _QWORD))TSGlobalLsaFunctions->LsaUnprotectMemory)(
          *((_QWORD *)a1 + 19),
          *((unsigned int *)a1 + 40));
        LastNtStatus = TSObtainRedirectableCreds(
                         (PCtxtHandle)((char *)v15 + 24),
                         (struct _UNICODE_STRING *)v15 + 4,
                         *((void **)a1 + 19),
                         v15,
                         &v115);
        ((void (__fastcall *)(_QWORD, _QWORD))TSGlobalLsaFunctions->LsaProtectMemory)(
          *((_QWORD *)a1 + 19),
          *((unsigned int *)a1 + 40));
LABEL_265:
        if ( LastNtStatus < 0 )
        {
          v36 = v115;
          v16 = v102;
          v33 = v140;
          v34 = Str;
          goto LABEL_38;
        }
        v66 = v115;
        v99 = v115;
        goto LABEL_267;
      }
      LastNtStatus = -2146893044;
    }
    v16 = v102;
    goto LABEL_35;
  }
  pToken.cBuffers = 1;
  pToken.pBuffers = (PSecBuffer)v123;
  v51 = (struct _SecHandle *)((char *)v15 + 24);
  pToken.ulVersion = 0;
  if ( !a2 )
    v51 = 0;
  v123[0] = (PVOID)0x200000000LL;
  v123[1] = 0;
  v52 = InitializeSecurityContextW(
          (PCredHandle)((char *)a1 + 120),
          v51,
          v16,
          0x132u,
          0,
          TargetDataRep,
          &v114,
          0,
          (PCtxtHandle)((char *)v15 + 24),
          &pToken,
          (unsigned int *)&pfContextAttr + 1,
          ptsExpiry);
  v140 = v52;
  v33 = v52;
  if ( v52 < 0 )
  {
    LastNtStatus = RtlGetLastNtStatus();
    goto LABEL_35;
  }
  if ( (unsigned int)(v52 - 590611) <= 1 )
  {
    v53 = CompleteAuthToken((PCtxtHandle)((char *)v15 + 24), &pToken);
    if ( v53 < 0 )
    {
      v33 = v53;
      goto LABEL_35;
    }
    if ( v33 != 590612 )
    {
      v33 = 0;
      goto LABEL_154;
    }
    v33 = 590610;
    v140 = 590610;
  }
  else if ( v52 != 590610 )
  {
LABEL_154:
    pBuffer = 0;
    if ( (pfContextAttr & 0x1000000000LL) == 0 )
    {
      LastNtStatus = -1073741637;
      goto LABEL_35;
    }
    if ( !*((_QWORD *)v15 + 10) )
    {
      LastNtStatus = -1073741637;
      goto LABEL_35;
    }
    v140 = QueryContextAttributesW((PCtxtHandle)((char *)v15 + 24), 0xAu, &pBuffer);
    v33 = v140;
    if ( v140 >= 0 )
    {
      if ( (unsigned int)_o__wcsicmp(*(_QWORD *)&pBuffer[1].cbBuffer, L"NTLM") && (pfContextAttr & 0x200000000LL) != 0 )
        *((_DWORD *)v15 + 30) |= 1u;
      if ( *((_BYTE *)v15 + 92) )
        *((_DWORD *)v15 + 30) |= 2u;
      if ( *((_BYTE *)v15 + 140) )
        *((_DWORD *)v15 + 30) |= 4u;
      FreeContextBuffer(pBuffer);
      if ( !*((_DWORD *)v15 + 30) )
      {
        if ( (*((_BYTE *)v15 + 128) & 1) != 0
          && !*((_BYTE *)v15 + 140)
          && ((int)IsNTLMServerAuthAllowed(v16, *((unsigned int *)v15 + 36), &v103) < 0 || !v103) )
        {
          if ( v16 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, v55, v16);
          }
          else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_82746c11848034a638789f4e0723fe0c_Traceguids);
          }
          TSAuditPolicyFailure(a1, v15, v16);
          v33 = -2146892961;
          goto LABEL_35;
        }
        if ( (*((_BYTE *)v15 + 128) & 2) != 0 )
        {
          LastNtStatus = TSMapContext(v15, a11, a12);
          if ( LastNtStatus < 0 )
            goto LABEL_35;
        }
      }
      v56 = *((_DWORD *)v15 + 29);
      v57 = 32;
      if ( v56 < 5 )
      {
        if ( g_dwEncryptionOracle <= 1 || v56 == 1 && g_dwEncryptionOracle < 3 )
        {
          TSReportNoVersionMatch(a3, v56);
          v33 = v140;
          LastNtStatus = -1073741637;
          goto LABEL_35;
        }
        LastNtStatus = TSEncryptBuffer(
                         (PCtxtHandle)((char *)v15 + 24),
                         *((unsigned __int8 **)v15 + 10),
                         *((unsigned int *)v15 + 22),
                         &Src,
                         (unsigned int *)&pfContextAttr);
        if ( LastNtStatus < 0 )
          goto LABEL_60;
      }
      else
      {
        LastNtStatus = TSGenRandom(v54, (unsigned __int8 *)v15 + 184);
        if ( LastNtStatus < 0
          || (LastNtStatus = TSCalculateBindingHashes(
                               v58,
                               (unsigned __int8 *)v15 + 184,
                               *((_DWORD *)v15 + 22),
                               *((unsigned __int8 **)v15 + 10),
                               Reserved1,
                               (unsigned __int8 *)v15 + 216,
                               pInput,
                               (unsigned __int8 *)v15 + 248),
              LastNtStatus < 0) )
        {
          v16 = v102;
          goto LABEL_199;
        }
        v16 = v102;
        LastNtStatus = TSEncryptBuffer(
                         (PCtxtHandle)((char *)v15 + 24),
                         (unsigned __int8 *)v15 + 216,
                         0x20u,
                         &Src,
                         (unsigned int *)&pfContextAttr);
        if ( LastNtStatus < 0 )
          goto LABEL_60;
        v30 = v124;
      }
      v59 = *((_DWORD *)v15 + 29);
      if ( v59 < 5 )
        v60 = 0;
      else
        v60 = (unsigned __int8 *)v15 + 184;
      if ( v59 < 5 )
        v57 = 0;
      v35 = Buf1;
      LastNtStatus = TSPackBuffers(&pToken, 0, 0, Src, pfContextAttr, (struct _SecBuffer *)v116, 0, v60, v57);
      if ( LastNtStatus >= 0 )
      {
        v140 = 590610;
        goto LABEL_272;
      }
LABEL_214:
      v33 = v140;
      v34 = Str;
      goto LABEL_37;
    }
LABEL_35:
    v34 = Str;
LABEL_36:
    v35 = Buf1;
    goto LABEL_37;
  }
  LastNtStatus = TSPackBuffers(&pToken, 0, 0, 0, 0, (struct _SecBuffer *)v116, 0, 0, 0);
  if ( LastNtStatus < 0 )
    goto LABEL_35;
  v35 = Buf1;
LABEL_272:
  if ( (a4 & 0x100) != 0 )
  {
    v30->pvBuffer = (void *)v116[1];
    v30->cbBuffer = v116[0];
    *a9 |= 0x100u;
    v116[1] = 0;
  }
  else
  {
    v87 = v116[0];
    if ( v30->cbBuffer < LODWORD(v116[0]) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_82746c11848034a638789f4e0723fe0c_Traceguids);
      v16 = v102;
      LastNtStatus = -1073741789;
      v34 = Str;
      v30->cbBuffer = v87;
      v33 = v140;
      goto LABEL_37;
    }
    memcpy_0(v30->pvBuffer, (const void *)v116[1], LODWORD(v116[0]));
    v30->cbBuffer = v87;
  }
  if ( !*((_QWORD *)v15 + 2) )
  {
    if ( a1 )
      _InterlockedIncrement((volatile signed __int32 *)a1);
    *((_QWORD *)v15 + 2) = a1;
  }
  if ( (*((_BYTE *)v15 + 128) & 1) != 0 )
    v88 = (pfContextAttr & 0x200000000LL) == 0;
  else
    v88 = *((_DWORD *)v15 + 30) == 0;
  if ( !v88 )
    *a9 |= 2u;
  v16 = v102;
  LastNtStatus = 0;
  v34 = Str;
  *a7 = (unsigned __int64)v15;
  v15 = 0;
  v33 = v140;
  ptsExpiry->QuadPart = 0x7FFFFF36D5969FFFLL;
LABEL_37:
  v36 = v99;
LABEL_38:
  if ( pvContextBuffer )
    FreeContextBuffer(pvContextBuffer);
  if ( v109 )
    FreeContextBuffer(v109);
  if ( v15 )
  {
    if ( v15 == a2 )
      *((_DWORD *)v15 + 31) = 1;
    else
      TSDereferenceContext(v15);
  }
  if ( v16 )
  {
    if ( TSGlobalState == 1 )
      ((void (__fastcall *)(unsigned __int16 *))TSGlobalLsaFunctions->FreePrivateHeap)(v16);
    else
      ((void (__fastcall *)(unsigned __int16 *))TSGlobalDllFunctions->FreeHeap)(v16);
  }
  if ( v34 )
    TSFree(v34);
  if ( v114.cBuffers && v114.pBuffers )
  {
    v89 = 0;
    do
    {
      if ( v114.pBuffers[v89].pvBuffer )
      {
        if ( TSGlobalState == 1 )
          FreePrivateHeap = (void (*)(void))TSGlobalLsaFunctions->FreePrivateHeap;
        else
          FreePrivateHeap = (void (*)(void))TSGlobalDllFunctions->FreeHeap;
        FreePrivateHeap();
      }
      ++v89;
    }
    while ( v89 < v114.cBuffers );
    if ( v114.pBuffers )
    {
      if ( TSGlobalState == 1 )
        FreeHeap = (void (*)(void))TSGlobalLsaFunctions->FreePrivateHeap;
      else
        FreeHeap = (void (*)(void))TSGlobalDllFunctions->FreeHeap;
      FreeHeap();
    }
    v114 = 0;
  }
  if ( v123[1] )
    FreeContextBuffer(v123[1]);
  if ( v116[1] )
    ((void (*)(void))TSGlobalLsaFunctions->FreeLsaHeap)();
  v92 = v119;
  if ( v119 )
  {
    v93 = HIDWORD(Size);
    v94 = v119;
    if ( HIDWORD(Size) )
    {
      do
      {
        *v94++ = 0;
        --v93;
      }
      while ( v93 );
    }
    TSFree(v92);
  }
  if ( v120 )
  {
    if ( TSGlobalState == 1 )
      v95 = (void (*)(void))TSGlobalLsaFunctions->FreePrivateHeap;
    else
      v95 = (void (*)(void))TSGlobalDllFunctions->FreeHeap;
    v95();
  }
  if ( Src )
  {
    if ( TSGlobalState == 1 )
      v96 = (void (*)(void))TSGlobalLsaFunctions->FreePrivateHeap;
    else
      v96 = (void (*)(void))TSGlobalDllFunctions->FreeHeap;
    v96();
  }
  if ( v35 )
  {
    if ( TSGlobalState == 1 )
      ((void (__fastcall *)(void *))TSGlobalLsaFunctions->FreePrivateHeap)(v35);
    else
      ((void (__fastcall *)(void *))TSGlobalDllFunctions->FreeHeap)(v35);
  }
  TSFreePrimaryCredentials(v36);
  if ( LastNtStatus >= 0 )
    return v33;
  return (unsigned int)LastNtStatus;
}

```

## disassembly

```asm
0x180006650  mov     [rsp-8+arg_18], r9d
0x180006655  mov     [rsp-8+arg_10], r8
0x18000665a  mov     [rsp-8+arg_8], rdx
0x18000665f  push    rbp
0x180006660  push    rbx
0x180006661  push    rsi
0x180006662  push    rdi
0x180006663  push    r13
0x180006665  push    r14
0x180006667  push    r15
0x180006669  lea     rbp, [rsp-140h]
0x180006671  sub     rsp, 240h
0x180006678  xor     r15d, r15d
0x18000667b  xorps   xmm0, xmm0
0x18000667e  mov     eax, r15d
0x180006681  mov     [rbp+170h+var_1B4], r15d
0x180006685  xorps   xmm1, xmm1
0x180006688  mov     [rsp+270h+var_210], rax
0x18000668d  mov     rbx, r8
0x180006690  mov     [rbp+170h+var_198], rax
0x180006694  mov     rsi, rdx
0x180006697  mov     [rbp+170h+var_180], r15
0x18000669b  mov     r13, rcx
0x18000669e  mov     [rsp+270h+var_1F8], r15
0x1800066a3  xor     edx, edx; Val
0x1800066a5  mov     [rbp+170h+pszTargetName], r15
0x1800066a9  mov     r8d, 0E8h; Size
0x1800066af  mov     dword ptr [rbp+170h+var_1EC+4], r15d
0x1800066b3  lea     rcx, [rbp+170h+var_130]; void *
0x1800066b7  mov     [rbp+170h+var_168], r15
0x1800066bb  mov     edi, r15d
0x1800066be  mov     [rbp+170h+var_1AC], r15d
0x1800066c2  movups  xmmword ptr [rbp+170h+var_1A8.ulVersion], xmm0
0x1800066c6  mov     r14d, r15d
0x1800066c9  mov     [rbp+170h+var_1F0], r15d
0x1800066cd  movups  xmmword ptr [rbp+170h+pToken.ulVersion], xmm1
0x1800066d1  mov     [rbp+170h+Src], r15
0x1800066d5  movups  xmmword ptr [rbp+170h+var_190], xmm0
0x1800066d9  mov     dword ptr [rbp+170h+var_1EC], r15d
0x1800066dd  movups  xmmword ptr [rbp+170h+var_148], xmm1
0x1800066e1  mov     [rsp+270h+Buf1], r15
0x1800066e6  mov     dword ptr [rbp+170h+Size], r15d
0x1800066ea  mov     [rbp+170h+var_170], r15
0x1800066ee  mov     dword ptr [rbp+170h+Size+4], r15d
0x1800066f2  mov     [rbp+170h+var_1B0], r15d
0x1800066f6  mov     [rbp+170h+var_1B8], r15d
0x1800066fa  mov     [rsp+270h+Str], r15
0x1800066ff  call    memset_0
0x180006704  mov     [rbp+170h+pvContextBuffer], r15
0x180006708  mov     [rbp+170h+var_1C0], r15
0x18000670c  mov     r10, cs:WPP_GLOBAL_Control
0x180006713  lea     rax, WPP_GLOBAL_Control
0x18000671a  cmp     r10, rax
0x18000671d  jz      short loc_180006743
0x18000671f  test    byte ptr [r10+1Ch], 20h
0x180006724  jz      short loc_180006743
0x180006726  mov     rcx, [r10+10h]
0x18000672a  mov     r9, r13
0x18000672d  mov     qword ptr [rsp+270h+TargetDataRep], rbx
0x180006732  mov     qword ptr [rsp+270h+Reserved1], rsi
0x180006737  call    WPP_SF_qqZ
0x18000673c  mov     r10, cs:WPP_GLOBAL_Control
0x180006743  test    r13, r13
0x180006746  jnz     short loc_180006757
0x180006748  test    rsi, rsi
0x18000674b  jnz     short loc_180006757
0x18000674d  mov     eax, 80090301h
0x180006752  jmp     loc_180007B5E
0x180006757  cmp     [rbp+170h+arg_38], rdi
0x18000675e  jnz     short loc_18000676A
0x180006760  mov     eax, 0C000000Dh
0x180006765  jmp     loc_180007B5E
0x18000676a  mov     rdx, r15
0x18000676d  mov     [rsp+270h+var_38], r12
0x180006775  mov     r12, r15
0x180006778  mov     [rbp+170h+arg_0], r15d
0x18000677f  mov     [rbp+170h+var_150], r15
0x180006783  mov     r15, [rbp+170h+arg_28]
0x18000678a  mov     [rbp+170h+pBuffer], rdx
0x18000678e  test    r15, r15
0x180006791  jz      loc_180006889
0x180006797  cmp     [r15+4], edx
0x18000679b  jbe     loc_180006886
0x1800067a1  mov     rsi, [r15+8]
0x1800067a5  mov     ecx, r14d
0x1800067a8  shl     rcx, 4
0x1800067ac  add     rsi, rcx
0x1800067af  mov     eax, [rsi+4]
0x1800067b2  and     eax, 0FFFFFFFh
0x1800067b7  test    r12, r12
0x1800067ba  jnz     short loc_1800067F1
0x1800067bc  cmp     eax, 2
0x1800067bf  jnz     short loc_18000682C
0x1800067c1  cmp     [rsi], edi
0x1800067c3  jz      short loc_18000682C
0x1800067c5  mov     rax, cs:?TSGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * TSGlobalLsaFunctions
0x1800067cc  mov     rdx, rsi
0x1800067cf  mov     rcx, rsi
0x1800067d2  mov     rax, [rax+98h]
0x1800067d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800067de  mov     ebx, eax
0x1800067e0  test    eax, eax
0x1800067e2  js      loc_180007937
0x1800067e8  mov     rdx, [rbp+170h+pBuffer]
0x1800067ec  mov     r12, rsi
0x1800067ef  jmp     short loc_18000682C
0x1800067f1  test    rdx, rdx
0x1800067f4  jnz     short loc_180006827
0x1800067f6  cmp     eax, 2
0x1800067f9  jnz     short loc_18000682C
0x1800067fb  mov     rax, cs:?TSGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * TSGlobalLsaFunctions
0x180006802  mov     rdx, rsi
0x180006805  mov     rcx, rsi
0x180006808  mov     rax, [rax+98h]
0x18000680f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006814  mov     ebx, eax
0x180006816  test    eax, eax
0x180006818  js      loc_180007937
0x18000681e  mov     rdx, rsi
0x180006821  mov     [rbp+170h+pBuffer], rdx
0x180006825  jmp     short loc_18000682C
0x180006827  cmp     eax, 2
0x18000682a  jz      short loc_18000684C
0x18000682c  inc     r14d
0x18000682f  cmp     r14d, [r15+4]
0x180006833  jb      loc_1800067A1
0x180006839  mov     r10, cs:WPP_GLOBAL_Control
0x180006840  mov     r14, rdi
0x180006843  mov     rsi, [rbp+170h+arg_8]
0x18000684a  jmp     short loc_180006889
0x18000684c  mov     rax, cs:?TSGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * TSGlobalLsaFunctions
0x180006853  mov     rdx, rsi
0x180006856  mov     rcx, rsi
0x180006859  mov     rax, [rax+98h]
0x180006860  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006865  mov     ebx, eax
0x180006867  test    eax, eax
0x180006869  js      loc_180007976
0x18000686f  mov     r10, cs:WPP_GLOBAL_Control
0x180006876  mov     r14, rdi
0x180006879  mov     [rbp+170h+var_150], rsi
0x18000687d  mov     rsi, [rbp+170h+arg_8]
0x180006884  jmp     short loc_180006889
0x180006886  mov     r14, rdx
0x180006889  mov     r15, [rbp+170h+arg_38]
0x180006890  mov     edx, [r15+4]
0x180006894  test    edx, edx
0x180006896  jz      short loc_1800068C6
0x180006898  mov     r8, [r15+8]
0x18000689c  xor     ecx, ecx
0x18000689e  xchg    ax, ax
0x1800068a0  mov     r15d, ecx
0x1800068a3  shl     r15, 4
0x1800068a7  add     r15, r8
0x1800068aa  mov     [rbp+170h+var_138], r15
0x1800068ae  mov     eax, [r15+4]
0x1800068b2  and     eax, 0FFFFFFFh
0x1800068b7  cmp     eax, 2
0x1800068ba  jz      loc_180006945
0x1800068c0  inc     ecx
0x1800068c2  cmp     ecx, edx
0x1800068c4  jb      short loc_1800068A0
0x1800068c6  mov     ebx, 0C000000Dh
0x1800068cb  lea     rax, WPP_GLOBAL_Control
0x1800068d2  cmp     r10, rax
0x1800068d5  jz      short loc_1800068F3
0x1800068d7  test    byte ptr [r10+1Ch], 1
0x1800068dc  jz      short loc_1800068F3
0x1800068de  mov     rcx, [r10+10h]
0x1800068e2  mov     edx, 0Bh
0x1800068e7  lea     r8, WPP_82746c11848034a638789f4e0723fe0c_Traceguids
0x1800068ee  call    WPP_SF_
0x1800068f3  mov     esi, edi
0x1800068f5  mov     r13, [rsp+270h+Str]
0x1800068fa  mov     r12, [rsp+270h+Buf1]
0x1800068ff  mov     r15, [rsp+270h+var_210]
0x180006904  mov     rcx, [rbp+170h+pvContextBuffer]; pvContextBuffer
0x180006908  test    rcx, rcx
0x18000690b  jz      short loc_180006913
0x18000690d  call    cs:__imp_FreeContextBuffer
0x180006913  mov     rcx, [rbp+170h+var_1C0]; pvContextBuffer
0x180006917  test    rcx, rcx
0x18000691a  jz      short loc_180006922
0x18000691c  call    cs:__imp_FreeContextBuffer
0x180006922  test    rdi, rdi
0x180006925  jz      loc_180007985
0x18000692b  cmp     rdi, [rbp+170h+arg_8]
0x180006932  jz      loc_18000797E
0x180006938  mov     rcx, rdi; struct _TS_CONTEXT *
0x18000693b  call    ?TSDereferenceContext@@YAXPEAU_TS_CONTEXT@@@Z; TSDereferenceContext(_TS_CONTEXT *)
0x180006940  jmp     loc_180007985
0x180006945  mov     rax, cs:?TSGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * TSGlobalLsaFunctions
0x18000694c  mov     rdx, r15
0x18000694f  mov     rcx, r15
0x180006952  mov     rax, [rax+98h]
0x180006959  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000695e  mov     ebx, eax
0x180006960  test    eax, eax
0x180006962  js      loc_180007976
0x180006968  test    r15, r15
0x18000696b  jz      loc_18000796A
0x180006971  test    rsi, rsi
0x180006974  jnz     loc_180006C6D
0x18000697a  test    r12, r12
0x18000697d  jz      short loc_1800069B3
0x18000697f  mov     ebx, 0C000000Dh
0x180006984  mov     rcx, cs:WPP_GLOBAL_Control
0x18000698b  lea     rax, WPP_GLOBAL_Control
0x180006992  cmp     rcx, rax
0x180006995  jz      loc_1800068F3
0x18000699b  test    byte ptr [rcx+1Ch], 1
0x18000699f  jz      loc_1800068F3
0x1800069a5  mov     rcx, [rcx+10h]
0x1800069a9  mov     edx, 0Ch
0x1800069ae  jmp     loc_1800068E7
0x1800069b3  xor     edx, edx; unsigned __int8
0x1800069b5  lea     rcx, [rbp+170h+var_180]; struct _TS_CONTEXT **
0x1800069b9  call    ?TSAllocateContext@@YAJPEAPEAU_TS_CONTEXT@@E@Z; TSAllocateContext(_TS_CONTEXT * *,uchar)
0x1800069be  mov     rdi, [rbp+170h+var_180]
0x1800069c2  mov     ebx, eax
0x1800069c4  test    eax, eax
0x1800069c6  js      loc_180006A53
0x1800069cc  mov     eax, [rbp+170h+arg_18]
0x1800069d2  lea     rcx, [rdi+40h]; struct _UNICODE_STRING *
0x1800069d6  mov     r12, [rbp+170h+arg_10]
0x1800069dd  mov     rdx, r12; struct _UNICODE_STRING *
0x1800069e0  mov     [rdi+80h], eax
0x1800069e6  call    ?TSDuplicateStringEx@@YAJPEAU_UNICODE_STRING@@PEBU1@E@Z; TSDuplicateStringEx(_UNICODE_STRING *,_UNICODE_STRING const *,uchar)
0x1800069eb  mov     ebx, eax
0x1800069ed  test    eax, eax
0x1800069ef  js      short loc_180006A53
0x1800069f1  lea     rdx, [rdi+40h]; struct _UNICODE_STRING *
0x1800069f5  lea     rcx, [rbp+170h+pszTargetName]; unsigned __int16 **
0x1800069f9  call    ?TSUnicodeStringToString@@YAJPEAPEAGPEAU_UNICODE_STRING@@@Z; TSUnicodeStringToString(ushort * *,_UNICODE_STRING *)
0x1800069fe  mov     ebx, eax
0x180006a00  test    eax, eax
0x180006a02  js      short loc_180006A4F
0x180006a04  mov     rax, cs:?TSGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * TSGlobalLsaFunctions
0x180006a0b  lea     rcx, [rbp+170h+var_1B8]
0x180006a0f  mov     rax, [rax+1B0h]
0x180006a16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a1b  mov     ebx, eax
0x180006a1d  test    eax, eax
0x180006a1f  jns     short loc_180006A5E
0x180006a21  mov     rcx, cs:WPP_GLOBAL_Control
0x180006a28  lea     rax, WPP_GLOBAL_Control
0x180006a2f  cmp     rcx, rax
0x180006a32  jz      short loc_180006A4F
0x180006a34  test    byte ptr [rcx+1Ch], 1
0x180006a38  jz      short loc_180006A4F
0x180006a3a  mov     rcx, [rcx+10h]
0x180006a3e  lea     r8, WPP_82746c11848034a638789f4e0723fe0c_Traceguids
0x180006a45  mov     edx, 0Eh
0x180006a4a  call    WPP_SF_
0x180006a4f  mov     r14, [rbp+170h+pszTargetName]
0x180006a53  mov     esi, [rbp+170h+arg_0]
0x180006a59  jmp     loc_1800068F5
0x180006a5e  mov     rax, [r13+90h]
0x180006a65  test    rax, rax
0x180006a68  jnz     short loc_180006AB2
0x180006a6a  test    byte ptr [rbp+170h+var_1B8], 4
0x180006a6e  jz      short loc_180006AB2
0x180006a70  mov     ebx, 8009030Eh
0x180006a75  mov     rcx, cs:WPP_GLOBAL_Control
0x180006a7c  lea     rax, WPP_GLOBAL_Control
0x180006a83  cmp     rcx, rax
0x180006a86  jz      short loc_180006A4F
0x180006a88  test    byte ptr [rcx+1Ch], 1
0x180006a8c  jz      short loc_180006A4F
0x180006a8e  mov     rcx, [rcx+10h]
0x180006a92  lea     r8, WPP_82746c11848034a638789f4e0723fe0c_Traceguids
0x180006a99  mov     edx, 0Fh
0x180006a9e  call    WPP_SF_
0x180006aa3  mov     r14, [rbp+170h+pszTargetName]
0x180006aa7  mov     esi, [rbp+170h+arg_0]
0x180006aad  jmp     loc_1800068F5
0x180006ab2  test    byte ptr [r13+6Ch], 1
0x180006ab7  jz      short loc_180006B0C
0x180006ab9  test    byte ptr [rdi+80h], 1
0x180006ac0  jz      short loc_180006B0C
0x180006ac2  mov     ebx, 8009035Dh
0x180006ac7  mov     rcx, cs:WPP_GLOBAL_Control
0x180006ace  lea     rax, WPP_GLOBAL_Control
0x180006ad5  cmp     rcx, rax
0x180006ad8  jz      loc_180006A4F
0x180006ade  test    byte ptr [rcx+1Ch], 1
0x180006ae2  jz      loc_180006A4F
0x180006ae8  mov     rcx, [rcx+10h]
0x180006aec  lea     r8, WPP_82746c11848034a638789f4e0723fe0c_Traceguids
0x180006af3  mov     edx, 10h
0x180006af8  call    WPP_SF_
0x180006afd  mov     r14, [rbp+170h+pszTargetName]
0x180006b01  mov     esi, [rbp+170h+arg_0]
0x180006b07  jmp     loc_1800068F5
0x180006b0c  test    rax, rax
0x180006b0f  jnz     short loc_180006B48
0x180006b11  test    r12, r12
0x180006b14  jz      short loc_180006B48
0x180006b16  cmp     ax, [r12]
0x180006b1b  jz      short loc_180006B48
  ... truncated ...
```
