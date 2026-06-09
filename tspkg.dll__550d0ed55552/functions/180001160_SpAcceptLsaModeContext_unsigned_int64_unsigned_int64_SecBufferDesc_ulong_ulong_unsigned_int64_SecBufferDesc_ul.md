# SpAcceptLsaModeContext(unsigned __int64,unsigned __int64,_SecBufferDesc *,ulong,ulong,unsigned __int64 *,_SecBufferDesc *,ulong *,_LARGE_INTEGER *,uchar *,_SecBuffer *)

- ea: `0x180001160`
- end: `0x1800021ae`
- name: `?SpAcceptLsaModeContext@@YAJ_K0PEAU_SecBufferDesc@@KKPEA_K1PEAKPEAT_LARGE_INTEGER@@PEAEPEAU_SecBuffer@@@Z`
- size: `4174`
- prototype: `__int64 __fastcall(volatile signed __int32 *, unsigned __int64, struct _SecBufferDesc *, __int16, unsigned int, unsigned __int64 *, struct _SecBufferDesc *, unsigned int *, PTimeStamp ptsExpiry, unsigned __int8 *, struct _SecBuffer *)`
- caller_count: `0`
- callee_count: `22`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001160`
- `0x180003830`
- `0x180004170`
- `0x180004440`
- `0x180004460`
- `0x180005520`
- `0x180005ed0`
- `0x180008840`
- `0x1800090a0`
- `0x1800099a8`
- `0x18000b920`
- `0x18000b92c`
- `0x18000c1a4`
- `0x18001627c`
- `0x180016868`
- `0x1800168c4`
- `0x1800176b0`
- `0x180018898`
- `0x180019958`
- `0x18001c630`
- `0x18001c63c`
- `0x18001d010`

## import_xrefs

- `SspiCli!CompleteAuthToken` at `0x180001998`
- `SspiCli!CompleteAuthToken` at `0x180001998`
- `SspiCli!FreeContextBuffer` at `0x18000217c`
- `SspiCli!FreeContextBuffer` at `0x18000217c`
- `SspiCli!SspiEncryptAuthIdentityEx` at `0x180001f1f`
- `SspiCli!SspiEncryptAuthIdentityEx` at `0x180001f1f`
- `SspiCli!AcceptSecurityContext` at `0x18000181b`
- `SspiCli!AcceptSecurityContext` at `0x18000181b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180001945`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180001945`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002174`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002174`
- `MSASN1!ASN1_CloseEncoder` at `0x180001d81`
- `MSASN1!ASN1_CloseEncoder` at `0x180001d81`
- `MSASN1!ASN1_CreateEncoder` at `0x180001cc3`
- `MSASN1!ASN1_CreateEncoder` at `0x180001cc3`
- `MSASN1!ASN1_CreateModule` at `0x180001c98`
- `MSASN1!ASN1_CreateModule` at `0x180001c98`
- `MSASN1!ASN1_Encode` at `0x180001cfc`
- `MSASN1!ASN1_Encode` at `0x180001cfc`
- `MSASN1!ASN1_FreeEncoded` at `0x180001d6f`
- `MSASN1!ASN1_FreeEncoded` at `0x180001d6f`
- `ntdll!RtlEnterCriticalSection` at `0x1800015b7`
- `ntdll!RtlEnterCriticalSection` at `0x1800015b7`
- `ntdll!RtlLeaveCriticalSection` at `0x180001638`
- `ntdll!RtlLeaveCriticalSection` at `0x18000166f`
- `ntdll!RtlLeaveCriticalSection` at `0x180001638`
- `ntdll!RtlLeaveCriticalSection` at `0x18000166f`
- `ntdll!RtlAvlInsertNodeEx` at `0x180001662`
- `ntdll!RtlAvlInsertNodeEx` at `0x180001662`
- `ntdll!RtlInitializeCriticalSection` at `0x180001560`
- `ntdll!RtlInitializeCriticalSection` at `0x180001560`
- `ntdll!RtlGetLastNtStatus` at `0x18000183f`
- `ntdll!RtlGetLastNtStatus` at `0x18000183f`
- `dsreg!DsrIsDeviceJoined` at `0x1800018e0`
- `dsreg!DsrIsDeviceJoined` at `0x1800018e0`

## pseudocode

```c
__int64 __fastcall SpAcceptLsaModeContext(
        volatile signed __int32 *a1,
        unsigned __int64 a2,
        struct _SecBufferDesc *a3,
        __int16 a4,
        unsigned int a5,
        unsigned __int64 *a6,
        struct _SecBufferDesc *a7,
        unsigned int *a8,
        PTimeStamp ptsExpiry,
        unsigned __int8 *a10,
        struct _SecBuffer *a11)
{
  unsigned int v11; // esi
  struct _SecBufferDesc *v14; // rbx
  int v15; // edi
  unsigned __int8 *v16; // r12
  struct _TS_PRIMARY_CREDENTIAL *v17; // r14
  void (*FreeHeap)(void); // rax
  unsigned int cBuffers; // edx
  struct _SecBuffer *v20; // r13
  PSecBuffer pBuffers; // r8
  int v22; // ecx
  struct _SecBuffer *v23; // rbx
  struct _SecBuffer *v24; // r14
  struct _SecBuffer *v25; // r12
  struct _SecBuffer *v26; // rbx
  int v27; // eax
  __int64 v28; // r8
  unsigned int v29; // r15d
  __int64 v30; // r14
  bool v31; // zf
  __int64 v32; // rax
  void *v33; // rax
  char *v34; // rax
  _QWORD *v35; // rdi
  __int64 v36; // r8
  _QWORD *v37; // rbx
  int v38; // eax
  _QWORD *v39; // rbx
  _QWORD *v40; // rax
  unsigned __int64 v41; // rsi
  volatile signed __int32 *v42; // rcx
  int v43; // eax
  unsigned int v44; // r15d
  PTimeStamp v45; // r13
  struct _SecHandle *v46; // rdx
  SECURITY_STATUS v47; // eax
  NTSTATUS LastNtStatus; // eax
  unsigned __int64 pvBuffer; // rdx
  unsigned int v50; // ecx
  unsigned __int8 *v51; // rcx
  void (*FreePrivateHeap)(void); // rax
  int v53; // r15d
  unsigned int v54; // eax
  __int64 v55; // r14
  PSecBuffer v56; // rbx
  SECURITY_STATUS v57; // eax
  int v58; // eax
  unsigned int v59; // ecx
  unsigned int v60; // edi
  unsigned int v61; // r15d
  unsigned __int8 *v62; // rax
  unsigned int v63; // ebx
  unsigned __int8 *v64; // r14
  bool v65; // cf
  unsigned __int8 *v66; // rdx
  unsigned int v67; // r14d
  unsigned int pBuffers_high; // r14d
  __int16 v69; // ax
  __int64 Module; // rax
  void *v71; // rax
  struct _SecBufferDesc *v72; // rcx
  _QWORD *v73; // rcx
  _QWORD *v74; // rbx
  unsigned int *v75; // rbx
  unsigned int *v76; // rdi
  unsigned int *p_cbBuffer; // rcx
  void *v78; // rax
  unsigned __int8 *v79; // rbx
  unsigned __int8 *v80; // rdx
  int v81; // eax
  int v82; // edi
  struct _SecBuffer *v83; // r8
  void *v84; // rdx
  int v85; // eax
  void (*v86)(void); // rax
  void (*v87)(void); // rax
  void (*v88)(void); // rax
  __int64 v89; // rcx
  unsigned __int8 *v90; // rax
  unsigned int v91; // ebx
  void (*v92)(void); // rax
  void (*v93)(void); // rax
  unsigned int TargetDataRep; // [rsp+28h] [rbp-E0h]
  unsigned int pOutput; // [rsp+38h] [rbp-D0h]
  unsigned int v97; // [rsp+58h] [rbp-B0h]
  unsigned __int8 *v98; // [rsp+60h] [rbp-A8h] BYREF
  struct _TS_PRIMARY_CREDENTIAL *v99; // [rsp+68h] [rbp-A0h]
  size_t v100; // [rsp+70h] [rbp-98h] BYREF
  unsigned __int8 *pToken; // [rsp+78h] [rbp-90h] BYREF
  struct _SecBufferDesc pToken_8; // [rsp+80h] [rbp-88h] BYREF
  int Src; // [rsp+90h] [rbp-78h] BYREF
  size_t Size; // [rsp+94h] [rbp-74h] BYREF
  int v105; // [rsp+9Ch] [rbp-6Ch] BYREF
  int v106; // [rsp+A0h] [rbp-68h] BYREF
  unsigned int v107; // [rsp+A4h] [rbp-64h] BYREF
  int v108; // [rsp+A8h] [rbp-60h] BYREF
  unsigned int v109; // [rsp+ACh] [rbp-5Ch] BYREF
  unsigned int pfContextAttr; // [rsp+B0h] [rbp-58h] BYREF
  unsigned int v111[5]; // [rsp+B4h] [rbp-54h] BYREF
  struct _SecBuffer *v112; // [rsp+C8h] [rbp-40h]
  void *Buf1; // [rsp+D0h] [rbp-38h] BYREF
  _SecBufferDesc pInput; // [rsp+D8h] [rbp-30h] BYREF
  struct _TS_PRIMARY_CREDENTIAL *v115; // [rsp+E8h] [rbp-20h] BYREF
  unsigned __int8 *v116; // [rsp+F0h] [rbp-18h] BYREF
  unsigned __int8 *v117; // [rsp+F8h] [rbp-10h] BYREF
  HLOCAL hMem[3]; // [rsp+100h] [rbp-8h] BYREF
  _OWORD v119[2]; // [rsp+118h] [rbp+10h] BYREF
  __int128 v120; // [rsp+138h] [rbp+30h]
  __int128 v121; // [rsp+148h] [rbp+40h]
  __int64 v122; // [rsp+158h] [rbp+50h]
  __int128 v123; // [rsp+168h] [rbp+60h] BYREF
  __int64 v124; // [rsp+178h] [rbp+70h]
  volatile signed __int32 *v125; // [rsp+1C8h] [rbp+C0h]

  v125 = a1;
  v11 = 0;
  v106 = 0;
  v97 = 0;
  v99 = 0;
  v115 = 0;
  pInput = 0;
  pfContextAttr = 0;
  pToken_8 = 0;
  v116 = 0;
  memset(v111, 0, sizeof(v111));
  *(_OWORD *)hMem = 0;
  pToken = 0;
  v100 = 0;
  Buf1 = 0;
  Size = 0;
  v98 = 0;
  v117 = 0;
  v109 = 0;
  v107 = 0;
  v105 = 0;
  Src = 0;
  v108 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 2), &WPP_GLOBAL_Control, a3, a1, a2);
  v14 = a7;
  if ( !a7 || !a3 )
  {
    v16 = v98;
    v15 = -1073741811;
    v17 = v99;
    goto LABEL_12;
  }
  if ( !a2 )
  {
    v15 = ((__int64 (__fastcall *)(int *))TSGlobalLsaFunctions->GetExtendedCallFlags)(&v105);
    if ( v15 < 0 )
      goto LABEL_10;
    if ( (v105 & 3) == 1 )
    {
      v15 = -2146893044;
      goto LABEL_10;
    }
  }
  cBuffers = v14->cBuffers;
  v20 = 0;
  v112 = 0;
  if ( cBuffers )
  {
    pBuffers = v14->pBuffers;
    v22 = 0;
    while ( 1 )
    {
      v23 = &pBuffers[v22];
      if ( (v23->BufferType & 0xFFFFFFF) == 2 )
        break;
      if ( ++v22 >= cBuffers )
        goto LABEL_22;
    }
    v15 = ((__int64 (__fastcall *)(struct _SecBuffer *, struct _SecBuffer *))TSGlobalLsaFunctions->MapBuffer)(
            &pBuffers[v22],
            &pBuffers[v22]);
    if ( v15 < 0 )
      goto LABEL_10;
    v20 = v23;
    v112 = v23;
  }
LABEL_22:
  v24 = 0;
  v25 = 0;
  if ( a3->cBuffers )
  {
    do
    {
      v26 = &a3->pBuffers[v11];
      v27 = v26->BufferType & 0xFFFFFFF;
      if ( v24 )
      {
        if ( v27 == 2 )
        {
          v15 = ((__int64 (__fastcall *)(struct _SecBuffer *, struct _SecBuffer *))TSGlobalLsaFunctions->MapBuffer)(
                  &a3->pBuffers[v11],
                  &a3->pBuffers[v11]);
          if ( v15 >= 0 )
          {
            v25 = v26;
            break;
          }
LABEL_10:
          v16 = v98;
LABEL_11:
          v17 = v99;
          goto LABEL_12;
        }
      }
      else if ( v27 == 2 )
      {
        v15 = ((__int64 (__fastcall *)(struct _SecBuffer *, struct _SecBuffer *))TSGlobalLsaFunctions->MapBuffer)(
                &a3->pBuffers[v11],
                &a3->pBuffers[v11]);
        if ( v15 < 0 )
          goto LABEL_10;
        v24 = v26;
      }
      ++v11;
    }
    while ( v11 < a3->cBuffers );
  }
  if ( !v20 || !v24 )
    goto LABEL_39;
  v15 = TSParseBuffers(v24, &pInput, &v116, v111, &pToken, (unsigned int *)&v100, &v107, &v106, &v117, &v109);
  if ( v15 < 0 )
    goto LABEL_10;
  if ( v106 < 0 )
  {
    v15 = v106;
    goto LABEL_10;
  }
  v28 = a2;
  v29 = v107;
  if ( a2 )
  {
    v41 = a2;
    if ( *(_DWORD *)(a2 + 124) == 1 )
    {
      v16 = v98;
      v15 = -1073741811;
      *(_DWORD *)(a2 + 124) = 1;
    }
    else
    {
      if ( !v125 || *(volatile signed __int32 **)(a2 + 16) == v125 )
      {
        v42 = *(volatile signed __int32 **)(a2 + 16);
        v125 = v42;
        goto LABEL_83;
      }
      v16 = v98;
      v97 = -2146893002;
      *(_DWORD *)(a2 + 124) = 1;
    }
    goto LABEL_11;
  }
  if ( !v25 )
  {
LABEL_39:
    v15 = -2146893048;
    goto LABEL_10;
  }
  v124 = 0;
  v123 = 0;
  if ( !((unsigned __int8 (__fastcall *)(__int128 *))TSGlobalLsaFunctions->GetCallInfo)(&v123) )
    goto LABEL_75;
  if ( TSGlobalState == 1 )
  {
    v30 = ((__int64 (__fastcall *)(__int64))TSGlobalLsaFunctions->AllocatePrivateHeap)(280);
    goto LABEL_43;
  }
  v33 = (void *)((__int64 (__fastcall *)(__int64))TSGlobalDllFunctions->AllocateHeap)(280);
  v30 = (__int64)v33;
  if ( !v33 )
  {
LABEL_43:
    if ( v30 )
      goto LABEL_44;
LABEL_75:
    v15 = -1073741670;
    goto LABEL_10;
  }
  memset_0(v33, 0, 0x118u);
LABEL_44:
  v31 = TSGlobalState == 1;
  *(_DWORD *)(v30 + 8) = v123;
  *(_DWORD *)v30 = 1;
  *(_DWORD *)(v30 + 124) = 0;
  *(_DWORD *)(v30 + 144) = 0;
  if ( v31 )
  {
    v32 = ((__int64 (__fastcall *)(__int64))TSGlobalLsaFunctions->AllocatePrivateHeap)(40);
    goto LABEL_46;
  }
  v32 = ((__int64 (__fastcall *)(__int64))TSGlobalDllFunctions->AllocateHeap)(40);
  if ( !v32 )
  {
LABEL_46:
    *(_QWORD *)(v30 + 176) = v32;
    if ( !v32 )
    {
      v15 = -1073741670;
      goto LABEL_71;
    }
    goto LABEL_52;
  }
  *(_OWORD *)v32 = 0;
  *(_OWORD *)(v32 + 16) = 0;
  *(_QWORD *)(v32 + 32) = 0;
  *(_QWORD *)(v30 + 176) = v32;
LABEL_52:
  v15 = RtlInitializeCriticalSection((PRTL_CRITICAL_SECTION)v32);
  if ( v15 < 0 )
    goto LABEL_71;
  v34 = (char *)operator new(0x40u, (const struct std::nothrow_t *)TSGlobalNoThrow);
  v35 = v34;
  if ( !v34 )
  {
    v15 = -1073741801;
LABEL_71:
    TSFreeContext((struct _TS_CONTEXT *)v30);
    goto LABEL_10;
  }
  *(_OWORD *)v34 = 0;
  *((_QWORD *)v34 + 2) = 0;
  *(_OWORD *)(v34 + 24) = 0;
  *((_QWORD *)v34 + 5) = 0;
  *((_QWORD *)v34 + 6) = 0;
  *((_QWORD *)v34 + 7) = 0;
  RtlEnterCriticalSection(&CriticalSection);
  v37 = qword_1800258C8;
  if ( !qword_1800258C8 )
    goto LABEL_60;
  while ( 1 )
  {
    v38 = TSContextCompareCallback(v30, v37);
    if ( v38 >= 0 )
      break;
    v37 = (_QWORD *)*v37;
LABEL_59:
    if ( !v37 )
      goto LABEL_60;
  }
  if ( v38 > 0 )
  {
    v37 = (_QWORD *)v37[1];
    goto LABEL_59;
  }
  if ( v37 )
  {
    operator delete(v35, 0x40u);
    RtlLeaveCriticalSection(&CriticalSection);
    v15 = -1073741270;
    goto LABEL_71;
  }
LABEL_60:
  v35[7] = v30;
  LOBYTE(v36) = 0;
  v39 = qword_1800258C8;
  if ( qword_1800258C8 )
  {
    while ( 1 )
    {
      if ( (int)TSContextCompareCallback(v30, v39) < 0 )
      {
        v40 = (_QWORD *)*v39;
        if ( !*v39 )
        {
          LOBYTE(v36) = 0;
          break;
        }
      }
      else
      {
        v40 = (_QWORD *)v39[1];
        if ( !v40 )
        {
          LOBYTE(v36) = 1;
          break;
        }
      }
      v39 = v40;
    }
  }
  RtlAvlInsertNodeEx(&qword_1800258C8, v39, v36, v35);
  RtlLeaveCriticalSection(&CriticalSection);
  v41 = v30;
  v15 = TSGetPublicKeyFromCertFormat(v29, v25, (unsigned __int8 **)(v30 + 80), (unsigned int *)(v30 + 88));
  if ( v15 < 0 )
    goto LABEL_86;
  if ( *(_DWORD *)(v30 + 88) < 4u )
  {
    v15 = -2146893043;
    goto LABEL_86;
  }
  v42 = v125;
  v28 = 0;
LABEL_83:
  v43 = *(_DWORD *)(v41 + 116);
  if ( !v43 )
  {
    if ( v29 )
    {
      *(_DWORD *)(v41 + 116) = v29;
      goto LABEL_93;
    }
LABEL_85:
    v15 = -2146893048;
LABEL_86:
    v44 = v97;
LABEL_87:
    v16 = v98;
    goto LABEL_88;
  }
  if ( v43 != v29 )
    goto LABEL_85;
LABEL_93:
  v45 = ptsExpiry;
  *(_QWORD *)&pToken_8.ulVersion = 0x100000000LL;
  pToken_8.pBuffers = (PSecBuffer)hMem;
  hMem[0] = (HLOCAL)0x200000000LL;
  hMem[1] = 0;
  if ( !g_dwEncryptionOracle && *(_DWORD *)(v41 + 116) < 5u )
  {
    v15 = -1073741637;
    goto LABEL_127;
  }
  if ( !pInput.cBuffers )
    goto LABEL_127;
  v46 = (struct _SecHandle *)(v41 + 24);
  if ( !v28 )
    v46 = 0;
  v47 = AcceptSecurityContext(
          (PCredHandle)(v42 + 30),
          v46,
          &pInput,
          0x112u,
          a5,
          (PCtxtHandle)(v41 + 24),
          &pToken_8,
          &pfContextAttr,
          ptsExpiry);
  v44 = v47;
  v97 = v47;
  if ( (unsigned int)(v47 - 590611) <= 1 )
  {
    v57 = CompleteAuthToken((PCtxtHandle)(v41 + 24), &pToken_8);
    if ( v57 < 0 )
    {
      v44 = v57;
      v97 = v57;
      goto LABEL_87;
    }
    v58 = 0;
    if ( v44 == 590612 )
      v58 = 590610;
    v97 = v58;
LABEL_127:
    pvBuffer = (unsigned __int64)pToken;
    if ( pToken )
    {
      v15 = TSDecryptBuffer(
              (PCtxtHandle)(v41 + 24),
              pToken,
              (unsigned int)v100,
              (unsigned __int8 **)&Buf1,
              (unsigned int *)&Size);
      if ( v15 < 0 )
        goto LABEL_86;
      v60 = *(_DWORD *)(v41 + 116);
      v61 = 32;
      if ( v60 < 5 )
      {
        if ( !g_dwEncryptionOracle )
        {
          v15 = -1073741637;
          goto LABEL_86;
        }
        v63 = Size;
        if ( (_DWORD)Size != *(_DWORD *)(v41 + 88)
          || (v64 = (unsigned __int8 *)Buf1, memcmp_0(Buf1, *(const void **)(v41 + 80), (unsigned int)Size)) )
        {
LABEL_135:
          v15 = -2146893044;
          goto LABEL_86;
        }
        if ( v60 <= 1 )
          ++*(_DWORD *)v64;
        else
          ++*v64;
      }
      else
      {
        v62 = v117;
        if ( !v117 || v109 != 32 )
          goto LABEL_135;
        *(_OWORD *)(v41 + 184) = *(_OWORD *)v117;
        *(_OWORD *)(v41 + 200) = *((_OWORD *)v62 + 1);
        v15 = TSCalculateBindingHashes(
                v59,
                (unsigned __int8 *)(v41 + 184),
                *(_DWORD *)(v41 + 88),
                *(unsigned __int8 **)(v41 + 80),
                TargetDataRep,
                (unsigned __int8 *)(v41 + 216),
                pOutput,
                (unsigned __int8 *)(v41 + 248));
        if ( v15 < 0 )
          goto LABEL_86;
        v63 = Size;
        if ( (_DWORD)Size != 32 )
          goto LABEL_135;
        v64 = (unsigned __int8 *)Buf1;
        if ( memcmp_0(Buf1, (const void *)(v41 + 216), 0x20u) )
          goto LABEL_135;
      }
      TSFree(pToken);
      v65 = *(_DWORD *)(v41 + 116) < 5u;
      pToken = 0;
      LODWORD(v100) = 0;
      if ( v65 )
      {
        v66 = v64;
        v61 = v63;
      }
      else
      {
        v66 = (unsigned __int8 *)(v41 + 248);
      }
      v15 = TSEncryptBuffer((PCtxtHandle)(v41 + 24), v66, v61, &pToken, (unsigned int *)&v100);
      if ( v15 < 0 )
        goto LABEL_86;
    }
    v53 = v100;
    goto LABEL_148;
  }
  if ( v47 >= 0 )
    goto LABEL_127;
  LastNtStatus = RtlGetLastNtStatus();
  v50 = *(_DWORD *)(v41 + 116);
  v15 = LastNtStatus;
  if ( v50 <= 2 || v50 == 5 )
    goto LABEL_87;
  v51 = pToken;
  *(_DWORD *)(v41 + 124) = 1;
  if ( v51 )
  {
    if ( TSGlobalState == 1 )
      FreePrivateHeap = (void (*)(void))TSGlobalLsaFunctions->FreePrivateHeap;
    else
      FreePrivateHeap = (void (*)(void))TSGlobalDllFunctions->FreeHeap;
    FreePrivateHeap();
  }
  pToken = 0;
  v53 = 0;
  if ( v15 == -1073741715 )
  {
    v54 = *(_DWORD *)(v41 + 116);
    if ( v54 >= 3
      && v54 != 5
      && (int)IsDeviceDomainJoined(&v108) >= 0
      && !v108
      && (int)DsrIsDeviceJoined(&Src, 0) >= 0
      && Src == 1 )
    {
      pvBuffer = 0;
      if ( pToken_8.cBuffers )
      {
        while ( 1 )
        {
          v55 = (unsigned int)pvBuffer;
          if ( (pToken_8.pBuffers[(unsigned int)pvBuffer].BufferType & 0xFFFFFFF) == 2 )
            break;
          pvBuffer = (unsigned int)(pvBuffer + 1);
          if ( (unsigned int)pvBuffer >= pToken_8.cBuffers )
            goto LABEL_148;
        }
        v56 = pToken_8.pBuffers;
        v56[(unsigned int)pvBuffer].pvBuffer = LocalAlloc(0x40u, 4u);
        if ( !pToken_8.pBuffers[v55].pvBuffer )
        {
          v15 = -1073741670;
          goto LABEL_86;
        }
        pToken_8.pBuffers[v55].cbBuffer = 4;
        HIDWORD(v100) = 1;
        memcpy_0(pToken_8.pBuffers[v55].pvBuffer, &Src, pToken_8.pBuffers[v55].cbBuffer);
      }
    }
  }
LABEL_148:
  v67 = 0;
  v122 = 0;
  memset(v119, 0, sizeof(v119));
  v120 = 0;
  v121 = 0;
  if ( pToken_8.cBuffers )
  {
    do
    {
      if ( pToken_8.pBuffers[v67].cbBuffer )
      {
        LOWORD(v119[0]) |= 0x80u;
        if ( TSGlobalState == 1 )
        {
          v28 = ((__int64 (__fastcall *)(__int64))TSGlobalLsaFunctions->AllocatePrivateHeap)(24);
          if ( !v28 )
            goto LABEL_152;
        }
        else
        {
          v28 = ((__int64 (__fastcall *)(__int64))TSGlobalDllFunctions->AllocateHeap)(24);
          if ( !v28 )
          {
LABEL_152:
            pBuffers_high = v111[1];
            v15 = -1073741670;
            goto LABEL_178;
          }
          *(_OWORD *)v28 = 0;
          *(_QWORD *)(v28 + 16) = 0;
        }
        pvBuffer = (unsigned __int64)pToken_8.pBuffers[v67].pvBuffer;
        *(_QWORD *)(v28 + 16) = pvBuffer;
        *(_DWORD *)(v28 + 8) = pToken_8.pBuffers[v67].cbBuffer;
        if ( *((_QWORD *)&v119[0] + 1) )
          *(_QWORD *)v28 = *((_QWORD *)&v119[0] + 1);
        *((_QWORD *)&v119[0] + 1) = v28;
      }
      ++v67;
    }
    while ( v67 < pToken_8.cBuffers );
  }
  v69 = v119[0];
  if ( pToken )
  {
    v69 = LOWORD(v119[0]) | 0x20;
    LODWORD(v120) = v53;
    LOWORD(v119[0]) |= 0x20u;
    *((_QWORD *)&v120 + 1) = pToken;
  }
  if ( v15 < 0 )
  {
    v69 |= 0x10u;
    LODWORD(v121) = v15;
    LOWORD(v119[0]) = v69;
  }
  if ( v69 )
  {
    DWORD1(v119[0]) = 6;
    a7 = 0;
    if ( fTSSSPModuleStarted )
    {
      Module = TSSSP_Module;
    }
    else
    {
      fTSSSPModuleStarted = 1;
      Module = ASN1_CreateModule(
                 0x10000,
                 1024,
                 4096,
                 6,
                 off_18001E1E0,
                 off_18001E1B0,
                 off_18001E180,
                 qword_18001F2E8,
                 1936946036);
      TSSSP_Module = Module;
    }
    if ( (unsigned int)ASN1_CreateEncoder(Module, &a7, 0, 0, 0) )
    {
      pBuffers_high = v111[1];
      v15 = -1073741823;
    }
    else if ( (int)ASN1_Encode(a7, v119, 3, 16, 0, 0) >= 0 )
    {
      v71 = (void *)((__int64 (__fastcall *)(_QWORD))TSGlobalLsaFunctions->AllocateLsaHeap)(HIDWORD(a7[1].pBuffers));
      *(_QWORD *)&v111[3] = v71;
      if ( v71 )
      {
        v15 = 0;
        memcpy_0(v71, *(const void **)&a7[1].ulVersion, HIDWORD(a7[1].pBuffers));
        v72 = a7;
        pBuffers_high = HIDWORD(a7[1].pBuffers);
      }
      else
      {
        pBuffers_high = v111[1];
        v15 = -1073741823;
        v72 = a7;
      }
      ASN1_FreeEncoded(v72, *(_QWORD *)&v72[1].ulVersion);
    }
    else
    {
      pBuffers_high = v111[1];
      v15 = -1073741823;
    }
    if ( a7 )
      ASN1_CloseEncoder();
  }
  else
  {
    v15 = 0;
    pBuffers_high = 0;
  }
LABEL_178:
  v73 = (_QWORD *)*((_QWORD *)&v119[0] + 1);
  if ( *((_QWORD *)&v119[0] + 1) )
  {
    do
    {
      v74 = (_QWORD *)*v73;
      if ( TSGlobalState == 1 )
        ((void (__fastcall *)(_QWORD *, unsigned __int64, __int64))TSGlobalLsaFunctions->FreePrivateHeap)(
          v73,
          pvBuffer,
          v28);
      else
        ((void (__fastcall *)(_QWORD *, unsigned __int64, __int64))TSGlobalDllFunctions->FreeHeap)(v73, pvBuffer, v28);
      v73 = v74;
    }
    while ( v74 );
  }
  if ( v15 < 0 )
    goto LABEL_86;
  v75 = a8;
  if ( *(_QWORD *)&v111[3] )
  {
    if ( (a4 & 0x100) != 0 )
    {
      p_cbBuffer = &v112->cbBuffer;
      v78 = *(void **)&v111[3];
      *(_QWORD *)&v111[3] = 0;
      v112->pvBuffer = v78;
      *p_cbBuffer = pBuffers_high;
      *v75 |= 0x100u;
    }
    else
    {
      v76 = &v112->cbBuffer;
      if ( v112->cbBuffer < pBuffers_high )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_82746c11848034a638789f4e0723fe0c_Traceguids);
        *v76 = pBuffers_high;
        v15 = -1073741789;
        goto LABEL_86;
      }
      memcpy_0(v112->pvBuffer, *(const void **)&v111[3], pBuffers_high);
      *v76 = pBuffers_high;
    }
  }
  else
  {
    v112->cbBuffer = 0;
  }
  if ( (pfContextAttr & 2) != 0 )
    *v75 |= 2u;
  v79 = a10;
  v80 = v116;
  *a10 = 0;
  if ( !v80 )
  {
    v85 = v97;
    v16 = v98;
    if ( !*(_QWORD *)(v41 + 96) )
      v85 = 590610;
    v97 = v85;
    goto LABEL_208;
  }
  v81 = TSDecryptBuffer((PCtxtHandle)(v41 + 24), v80, v111[0], &v98, (unsigned int *)&Size + 1);
  v16 = v98;
  v15 = v81;
  if ( v81 < 0 )
    goto LABEL_204;
  v15 = TSParseCreds((struct _TS_CONTEXT *)v41, v98, HIDWORD(Size), &v115);
  if ( v15 < 0 )
  {
    v99 = v115;
LABEL_204:
    v44 = v97;
LABEL_88:
    if ( v41 )
    {
      v97 = v44;
      if ( v41 == a2 )
      {
        v97 = v44;
        *(_DWORD *)(v41 + 124) = 1;
      }
      else
      {
        TSFreeContext((struct _TS_CONTEXT *)v41);
      }
    }
    goto LABEL_11;
  }
  v82 = *(_DWORD *)v115;
  v83 = a11;
  *(_QWORD *)(v41 + 96) = v115;
  v99 = 0;
  TSMapContext((struct _TS_CONTEXT *)v41, v79, v83);
  TSHidePassword((struct _UNICODE_STRING *)(*(_QWORD *)(v41 + 96) + 40LL));
  v84 = *(void **)(*(_QWORD *)(v41 + 96) + 168LL);
  if ( v84 )
    SspiEncryptAuthIdentityEx(2u, v84);
  *(_DWORD *)(v41 + 124) = 1;
  if ( v82 != 6 )
  {
    v17 = *(struct _TS_PRIMARY_CREDENTIAL **)(v41 + 96);
    *(_QWORD *)(v41 + 96) = 0;
    goto LABEL_209;
  }
LABEL_208:
  v17 = v99;
LABEL_209:
  if ( !*(_QWORD *)(v41 + 16) )
  {
    if ( v125 )
      _InterlockedIncrement(v125);
    *(_QWORD *)(v41 + 16) = v125;
  }
  v15 = 0;
  *a6 = v41;
  v45->QuadPart = 0x7FFFFF36D5969FFFLL;
LABEL_12:
  if ( v116 )
  {
    if ( TSGlobalState == 1 )
      FreeHeap = (void (*)(void))TSGlobalLsaFunctions->FreePrivateHeap;
    else
      FreeHeap = (void (*)(void))TSGlobalDllFunctions->FreeHeap;
    FreeHeap();
  }
  if ( Buf1 )
  {
    if ( TSGlobalState == 1 )
      v86 = (void (*)(void))TSGlobalLsaFunctions->FreePrivateHeap;
    else
      v86 = (void (*)(void))TSGlobalDllFunctions->FreeHeap;
    v86();
  }
  if ( pToken )
  {
    if ( TSGlobalState == 1 )
      v87 = (void (*)(void))TSGlobalLsaFunctions->FreePrivateHeap;
    else
      v87 = (void (*)(void))TSGlobalDllFunctions->FreeHeap;
    v87();
  }
  if ( v117 )
  {
    if ( TSGlobalState == 1 )
      v88 = (void (*)(void))TSGlobalLsaFunctions->FreePrivateHeap;
    else
      v88 = (void (*)(void))TSGlobalDllFunctions->FreeHeap;
    v88();
  }
  if ( v16 )
  {
    v89 = HIDWORD(Size);
    v90 = v16;
    if ( HIDWORD(Size) )
    {
      do
      {
        *v90++ = 0;
        --v89;
      }
      while ( v89 );
    }
    TSFree(v16);
  }
  if ( pInput.cBuffers && pInput.pBuffers )
  {
    v91 = 0;
    do
    {
      if ( pInput.pBuffers[v91].pvBuffer )
      {
        if ( TSGlobalState == 1 )
          v92 = (void (*)(void))TSGlobalLsaFunctions->FreePrivateHeap;
        else
          v92 = (void (*)(void))TSGlobalDllFunctions->FreeHeap;
        v92();
      }
      ++v91;
    }
    while ( v91 < pInput.cBuffers );
    if ( pInput.pBuffers )
    {
      if ( TSGlobalState == 1 )
        v93 = (void (*)(void))TSGlobalLsaFunctions->FreePrivateHeap;
      else
        v93 = (void (*)(void))TSGlobalDllFunctions->FreeHeap;
      v93();
    }
    pInput = 0;
  }
  TSFreePrimaryCredentials(v17);
  if ( hMem[1] )
  {
    if ( HIDWORD(v100) )
      LocalFree(hMem[1]);
    else
      FreeContextBuffer(hMem[1]);
  }
  if ( *(_QWORD *)&v111[3] )
    ((void (*)(void))TSGlobalLsaFunctions->FreeLsaHeap)();
  if ( v15 >= 0 )
    return v97;
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180001160  mov     rax, rsp
0x180001163  mov     [rax+20h], r9d
0x180001167  mov     [rax+10h], rdx
0x18000116b  mov     [rax+8], rcx
0x18000116f  push    rbp
0x180001170  push    rdi
0x180001171  lea     rbp, [rax-0B8h]
0x180001178  sub     rsp, 1A8h
0x18000117f  mov     [rax+18h], rbx
0x180001183  xorps   xmm0, xmm0
0x180001186  mov     [rax-18h], rsi
0x18000118a  xorps   xmm1, xmm1
0x18000118d  xor     esi, esi
0x18000118f  mov     [rax-20h], r12
0x180001193  mov     [rax-30h], r14
0x180001197  mov     r14, rdx
0x18000119a  mov     [rax-38h], r15
0x18000119e  mov     r15, r8
0x1800011a1  mov     rax, rcx
0x1800011a4  mov     [rbp+0B0h+var_118], esi
0x1800011a7  mov     ecx, esi
0x1800011a9  mov     dword ptr [rsp+1B0h+var_160], esi
0x1800011ad  mov     [rsp+1B0h+var_150], rcx
0x1800011b2  mov     [rbp+0B0h+var_D0], rcx
0x1800011b6  movups  xmmword ptr [rbp+0B0h+pInput.ulVersion], xmm0
0x1800011ba  mov     [rbp+0B0h+var_108], esi
0x1800011bd  movups  xmmword ptr [rsp+1B0h+pToken.pBuffers], xmm1
0x1800011c2  mov     [rbp+0B0h+var_C8], rsi
0x1800011c6  movups  xmmword ptr [rbp+0B0h+var_104+4], xmm0
0x1800011ca  mov     dword ptr [rbp+0B0h+var_104], esi
0x1800011cd  movups  xmmword ptr [rbp+0B0h+hMem], xmm1
0x1800011d1  mov     qword ptr [rsp+1B0h+pToken.ulVersion], rsi
0x1800011d6  mov     dword ptr [rsp+1B0h+var_148], esi
0x1800011da  mov     [rbp+0B0h+Buf1], rsi
0x1800011de  mov     dword ptr [rbp+0B0h+Size], esi
0x1800011e1  mov     [rsp+1B0h+var_158], rsi
0x1800011e6  mov     dword ptr [rbp+0B0h+Size+4], esi
0x1800011e9  mov     [rbp+0B0h+var_C0], rsi
0x1800011ed  mov     [rbp+0B0h+var_10C], esi
0x1800011f0  mov     [rbp+0B0h+var_114], esi
0x1800011f3  mov     [rbp+0B0h+var_11C], esi
0x1800011f6  mov     [rbp+0B0h+Src], esi
0x1800011f9  mov     [rbp+0B0h+var_110], esi
0x1800011fc  mov     dword ptr [rsp+1B0h+var_148+4], esi
0x180001200  mov     rcx, cs:WPP_GLOBAL_Control
0x180001207  lea     rdx, WPP_GLOBAL_Control
0x18000120e  cmp     rcx, rdx
0x180001211  jz      short loc_18000122A
0x180001213  test    byte ptr [rcx+1Ch], 20h
0x180001217  jz      short loc_18000122A
0x180001219  mov     rcx, [rcx+10h]
0x18000121d  mov     r9, rax
0x180001220  mov     qword ptr [rsp+1B0h+TargetDataRep], r14
0x180001225  call    WPP_SF_qq
0x18000122a  mov     rbx, [rbp+0B0h+arg_30]
0x180001231  test    rbx, rbx
0x180001234  jz      loc_180001FBB
0x18000123a  test    r15, r15
0x18000123d  jz      loc_180001FBB
0x180001243  mov     [rsp+1B0h+var_20], r13
0x18000124b  test    r14, r14
0x18000124e  jnz     short loc_1800012CA
0x180001250  mov     rax, cs:?TSGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * TSGlobalLsaFunctions
0x180001257  lea     rcx, [rbp+0B0h+var_11C]
0x18000125b  mov     rax, [rax+1B0h]
0x180001262  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001267  mov     edi, eax
0x180001269  test    eax, eax
0x18000126b  js      short loc_18000127B
0x18000126d  mov     eax, [rbp+0B0h+var_11C]
0x180001270  and     al, 3
0x180001272  cmp     al, 1
0x180001274  jnz     short loc_1800012CA
0x180001276  mov     edi, 8009030Ch
0x18000127b  mov     r12, [rsp+1B0h+var_158]
0x180001280  mov     r14, [rsp+1B0h+var_150]
0x180001285  mov     r13, [rsp+1B0h+var_20]
0x18000128d  mov     rcx, [rbp+0B0h+var_C8]
0x180001291  mov     r15, [rsp+1B0h+var_30]
0x180001299  mov     rsi, [rsp+1A0h]
0x1800012a1  test    rcx, rcx
0x1800012a4  jz      loc_180001FDF
0x1800012aa  cmp     cs:?TSGlobalState@@3W4_TS_STATE@@A, 1; _TS_STATE TSGlobalState
0x1800012b1  jnz     loc_180001FCF
0x1800012b7  mov     rax, cs:?TSGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * TSGlobalLsaFunctions
0x1800012be  mov     rax, [rax+188h]
0x1800012c5  jmp     loc_180001FDA
0x1800012ca  mov     edx, [rbx+4]
0x1800012cd  mov     r13, rsi
0x1800012d0  mov     [rbp+0B0h+var_F0], rsi
0x1800012d4  test    edx, edx
0x1800012d6  jz      short loc_180001328
0x1800012d8  mov     r8, [rbx+8]
0x1800012dc  mov     ecx, esi
0x1800012de  xchg    ax, ax
0x1800012e0  mov     ebx, ecx
0x1800012e2  shl     rbx, 4
0x1800012e6  add     rbx, r8
0x1800012e9  mov     eax, [rbx+4]
0x1800012ec  and     eax, 0FFFFFFFh
0x1800012f1  cmp     eax, 2
0x1800012f4  jz      short loc_1800012FE
0x1800012f6  inc     ecx
0x1800012f8  cmp     ecx, edx
0x1800012fa  jb      short loc_1800012E0
0x1800012fc  jmp     short loc_180001328
0x1800012fe  mov     rax, cs:?TSGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * TSGlobalLsaFunctions
0x180001305  mov     rdx, rbx
0x180001308  mov     rcx, rbx
0x18000130b  mov     rax, [rax+98h]
0x180001312  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001317  mov     edi, eax
0x180001319  test    eax, eax
0x18000131b  js      loc_18000127B
0x180001321  mov     r13, rbx
0x180001324  mov     [rbp+0B0h+var_F0], rbx
0x180001328  mov     r14, rsi
0x18000132b  mov     r12, rsi
0x18000132e  cmp     [r15+4], esi
0x180001332  jbe     loc_1800013B9
0x180001338  nop     dword ptr [rax+rax+00000000h]
0x180001340  mov     ebx, esi
0x180001342  shl     rbx, 4
0x180001346  add     rbx, [r15+8]
0x18000134a  mov     eax, [rbx+4]
0x18000134d  and     eax, 0FFFFFFFh
0x180001352  test    r14, r14
0x180001355  jnz     short loc_180001384
0x180001357  cmp     eax, 2
0x18000135a  jnz     short loc_180001389
0x18000135c  mov     rax, cs:?TSGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * TSGlobalLsaFunctions
0x180001363  mov     rdx, rbx
0x180001366  mov     rcx, rbx
0x180001369  mov     rax, [rax+98h]
0x180001370  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001375  mov     edi, eax
0x180001377  test    eax, eax
0x180001379  js      loc_18000127B
0x18000137f  mov     r14, rbx
0x180001382  jmp     short loc_180001389
0x180001384  cmp     eax, 2
0x180001387  jz      short loc_180001393
0x180001389  inc     esi
0x18000138b  cmp     esi, [r15+4]
0x18000138f  jb      short loc_180001340
0x180001391  jmp     short loc_1800013B9
0x180001393  mov     rax, cs:?TSGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * TSGlobalLsaFunctions
0x18000139a  mov     rdx, rbx
0x18000139d  mov     rcx, rbx
0x1800013a0  mov     rax, [rax+98h]
0x1800013a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800013ac  mov     edi, eax
0x1800013ae  test    eax, eax
0x1800013b0  js      loc_18000127B
0x1800013b6  mov     r12, rbx
0x1800013b9  test    r13, r13
0x1800013bc  jz      loc_180001444
0x1800013c2  test    r14, r14
0x1800013c5  jz      short loc_180001444
0x1800013c7  lea     rax, [rbp+0B0h+var_10C]
0x1800013cb  mov     rcx, r14; struct _SecBuffer *
0x1800013ce  mov     [rsp+1B0h+var_168], rax; unsigned int *
0x1800013d3  lea     r9, [rbp+0B0h+var_104]; unsigned int *
0x1800013d7  lea     rax, [rbp+0B0h+var_C0]
0x1800013db  mov     [rsp+1B0h+ptsExpiry], rax; unsigned __int8 **
0x1800013e0  lea     r8, [rbp+0B0h+var_C8]; unsigned __int8 **
0x1800013e4  lea     rax, [rbp+0B0h+var_118]
0x1800013e8  mov     [rsp+1B0h+pfContextAttr], rax; int *
0x1800013ed  lea     rdx, [rbp+0B0h+pInput]; struct _SecBufferDesc *
0x1800013f1  lea     rax, [rbp+0B0h+var_114]
0x1800013f5  mov     [rsp+1B0h+pOutput], rax; unsigned int *
0x1800013fa  lea     rax, [rsp+1B0h+var_148]
0x1800013ff  mov     [rsp+1B0h+phNewContext], rax; unsigned int *
0x180001404  lea     rax, [rsp+1B0h+pToken]
0x180001409  mov     qword ptr [rsp+1B0h+TargetDataRep], rax; unsigned __int8 **
0x18000140e  call    ?TSParseBuffers@@YAJPEAU_SecBuffer@@PEAU_SecBufferDesc@@PEAPEAEPEAK233PEAJ23@Z; TSParseBuffers(_SecBuffer *,_SecBufferDesc *,uchar * *,ulong *,uchar * *,ulong *,ulong *,long *,uchar * *,ulong *)
0x180001413  mov     edi, eax
0x180001415  test    eax, eax
0x180001417  js      loc_18000127B
0x18000141d  mov     eax, [rbp+0B0h+var_118]
0x180001420  test    eax, eax
0x180001422  jns     short loc_18000142B
0x180001424  mov     edi, eax
0x180001426  jmp     loc_18000127B
0x18000142b  mov     r8, [rbp+0B0h+arg_8]
0x180001432  mov     r15d, [rbp+0B0h+var_114]
0x180001436  test    r8, r8
0x180001439  jnz     loc_1800016C6
0x18000143f  test    r12, r12
0x180001442  jnz     short loc_18000144E
0x180001444  mov     edi, 80090308h
0x180001449  jmp     loc_18000127B
0x18000144e  xor     eax, eax
0x180001450  lea     rcx, [rbp+0B0h+var_50]
0x180001454  mov     [rbp+0B0h+var_40], rax
0x180001458  xorps   xmm0, xmm0
0x18000145b  mov     rax, cs:?TSGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * TSGlobalLsaFunctions
0x180001462  movups  [rbp+0B0h+var_50], xmm0
0x180001466  mov     rax, [rax+0C0h]
0x18000146d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001472  test    al, al
0x180001474  jz      loc_1800016BC
0x18000147a  cmp     cs:?TSGlobalState@@3W4_TS_STATE@@A, 1; _TS_STATE TSGlobalState
0x180001481  jnz     short loc_1800014FC
0x180001483  mov     rax, cs:?TSGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * TSGlobalLsaFunctions
0x18000148a  mov     ecx, 118h
0x18000148f  mov     rax, [rax+180h]
0x180001496  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000149b  mov     r14, rax
0x18000149e  test    r14, r14
0x1800014a1  jz      loc_1800016BC
0x1800014a7  mov     eax, dword ptr [rbp+0B0h+var_50]
0x1800014aa  xor     esi, esi
0x1800014ac  cmp     cs:?TSGlobalState@@3W4_TS_STATE@@A, 1; _TS_STATE TSGlobalState
0x1800014b3  mov     rbx, r14
0x1800014b6  mov     [r14+8], eax
0x1800014ba  mov     dword ptr [r14], 1
0x1800014c1  mov     [r14+7Ch], esi
0x1800014c5  mov     [r14+90h], esi
0x1800014cc  jnz     short loc_18000152D
0x1800014ce  mov     rax, cs:?TSGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * TSGlobalLsaFunctions
0x1800014d5  mov     ecx, 28h ; '('
0x1800014da  mov     rax, [rax+180h]
0x1800014e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800014e6  mov     [r14+0B0h], rax
0x1800014ed  test    rax, rax
0x1800014f0  jnz     short loc_18000155D
0x1800014f2  mov     edi, 0C000009Ah
0x1800014f7  jmp     loc_18000167F
0x1800014fc  mov     rax, cs:?TSGlobalDllFunctions@@3PEAU_SECPKG_DLL_FUNCTIONS@@EA; _SECPKG_DLL_FUNCTIONS * TSGlobalDllFunctions
0x180001503  mov     ecx, 118h
0x180001508  mov     rax, [rax]
0x18000150b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001510  mov     r14, rax
0x180001513  test    rax, rax
0x180001516  jz      short loc_18000149E
0x180001518  xor     edx, edx; Val
0x18000151a  mov     r8d, 118h; Size
0x180001520  mov     rcx, rax; void *
0x180001523  call    memset_0
0x180001528  jmp     loc_1800014A7
0x18000152d  mov     rax, cs:?TSGlobalDllFunctions@@3PEAU_SECPKG_DLL_FUNCTIONS@@EA; _SECPKG_DLL_FUNCTIONS * TSGlobalDllFunctions
0x180001534  mov     ecx, 28h ; '('
0x180001539  mov     rax, [rax]
0x18000153c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001541  test    rax, rax
0x180001544  jz      short loc_1800014E6
0x180001546  xorps   xmm0, xmm0
0x180001549  xor     ecx, ecx
0x18000154b  movups  xmmword ptr [rax], xmm0
0x18000154e  movups  xmmword ptr [rax+10h], xmm0
0x180001552  mov     [rax+20h], rcx
0x180001556  mov     [rbx+0B0h], rax
0x18000155d  mov     rcx, rax; CriticalSection
0x180001560  call    cs:__imp_RtlInitializeCriticalSection
0x180001566  mov     edi, eax
0x180001568  test    eax, eax
0x18000156a  js      loc_18000167F
0x180001570  lea     rdx, ?TSGlobalNoThrow@@3Unothrow_t@std@@A; struct std::nothrow_t *
0x180001577  mov     ecx, 40h ; '@'; unsigned __int64
0x18000157c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180001581  mov     rdi, rax
0x180001584  test    rax, rax
0x180001587  jz      loc_18000167A
0x18000158d  xor     eax, eax
0x18000158f  lea     rcx, CriticalSection; CriticalSection
0x180001596  xorps   xmm0, xmm0
0x180001599  movups  xmmword ptr [rdi], xmm0
0x18000159c  mov     [rdi+10h], rax
0x1800015a0  movups  xmmword ptr [rdi+18h], xmm0
0x1800015a4  mov     [rdi+28h], rax
0x1800015a8  mov     rax, cs:qword_18001F2E0
0x1800015af  mov     [rdi+30h], rax
0x1800015b3  mov     [rdi+38h], rsi
0x1800015b7  call    cs:__imp_RtlEnterCriticalSection
0x1800015bd  mov     rbx, cs:qword_1800258C8
0x1800015c4  test    rbx, rbx
0x1800015c7  jz      short loc_1800015EF
0x1800015c9  nop     dword ptr [rax+00000000h]
0x1800015d0  mov     rdx, rbx
0x1800015d3  mov     rcx, r14
0x1800015d6  call    TSContextCompareCallback
0x1800015db  test    eax, eax
0x1800015dd  jns     short loc_1800015E4
0x1800015df  mov     rbx, [rbx]
0x1800015e2  jmp     short loc_1800015EA
0x1800015e4  jle     short loc_18000161F
0x1800015e6  mov     rbx, [rbx+8]
0x1800015ea  test    rbx, rbx
0x1800015ed  jnz     short loc_1800015D0
0x1800015ef  mov     [rdi+38h], r14
0x1800015f3  xor     r8b, r8b
0x1800015f6  mov     rbx, cs:qword_1800258C8
0x1800015fd  test    rbx, rbx
0x180001600  jz      short loc_180001655
0x180001602  mov     rdx, rbx
0x180001605  mov     rcx, r14
0x180001608  call    TSContextCompareCallback
0x18000160d  test    eax, eax
0x18000160f  js      short loc_180001645
  ... truncated ...
```
