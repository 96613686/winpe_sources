# WapSslInitializeSecurityContext

- ea: `0x18000ff50`
- end: `0x180010fc6`
- name: `WapSslInitializeSecurityContext`
- size: `4214`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180011090`
- `0x180048b94`

## callees

- `0x18000eea4`
- `0x18000ff50`
- `0x1800180e0`
- `0x180023a30`
- `0x1800391c0`
- `0x180039e50`
- `0x1800722f0`
- `0x180072c70`
- `0x180092500`
- `0x1800971ec`
- `0x180097810`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800102f8`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001036b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800102f8`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001036b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001063d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001063d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001068b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001068b`
- `SspiCli!InitializeSecurityContextW` at `0x180010350`
- `SspiCli!InitializeSecurityContextW` at `0x180010350`
- `SspiCli!QueryContextAttributesExW` at `0x1800104af`
- `SspiCli!QueryContextAttributesExW` at `0x1800104af`
- `SspiCli!SetContextAttributesW` at `0x180010da3`
- `SspiCli!SetContextAttributesW` at `0x180010da3`
- `SspiCli!FreeContextBuffer` at `0x180010fb5`
- `SspiCli!FreeContextBuffer` at `0x180010fb5`

## pseudocode

```c
__int64 __fastcall WapSslInitializeSecurityContext(
        __int64 a1,
        _QWORD *a2,
        _BYTE *a3,
        _BYTE *a4,
        _BYTE *a5,
        _BYTE *a6,
        _BYTE *a7)
{
  unsigned int TransformedW; // r14d
  __int64 v9; // r13
  struct _SecHandle *v10; // r15
  __int64 *v11; // r8
  struct _SecBufferDesc *pInput; // rdi
  unsigned __int64 v13; // rcx
  __int64 v14; // rdx
  unsigned int v15; // r12d
  SEC_WCHAR *v16; // rsi
  _QWORD *v17; // r9
  char v18; // al
  __int64 v19; // rcx
  __int64 v20; // rax
  bool v21; // zf
  unsigned int v22; // eax
  const wchar_t *v23; // rcx
  SECURITY_STATUS v24; // eax
  int v25; // r12d
  __int64 v26; // rcx
  unsigned __int64 v27; // r8
  _QWORD *v28; // rdi
  _QWORD *v29; // r15
  LARGE_INTEGER v30; // r9
  LARGE_INTEGER v31; // r10
  unsigned __int64 v32; // rax
  unsigned __int64 v33; // rdx
  __int64 v34; // rcx
  __int64 v35; // rax
  __int64 *v36; // r15
  _BYTE *v37; // rax
  char v38; // al
  RTL_SRWLOCK **v40; // rax
  RTL_SRWLOCK *v41; // r12
  _BYTE *Ptr; // rax
  unsigned __int8 v43; // r14
  RTL_SRWLOCK *v44; // r9
  RTL_SRWLOCK *v45; // rax
  LARGE_INTEGER v46; // rsi
  unsigned __int8 v47; // r10
  int i; // r11d
  __int64 *v49; // rcx
  int *v50; // rdx
  int *v51; // rax
  PVOID v52; // rdi
  __int64 v53; // r14
  _QWORD *Heap; // rax
  unsigned __int64 v55; // rax
  DWORD v56; // ecx
  _QWORD *v57; // rax
  LARGE_INTEGER *v58; // rdx
  __int64 v59; // rcx
  unsigned __int64 v60; // r8
  _QWORD *v61; // rax
  __int64 v62; // rcx
  __int64 v63; // rdx
  __int64 v64; // rcx
  unsigned int v65; // r13d
  SECURITY_STATUS v66; // eax
  _QWORD *v67; // [rsp+68h] [rbp-A0h]
  DWORD v68; // [rsp+70h] [rbp-98h]
  HANDLE hObject; // [rsp+88h] [rbp-80h] BYREF
  unsigned __int64 v72; // [rsp+90h] [rbp-78h] BYREF
  __int64 v73; // [rsp+98h] [rbp-70h] BYREF
  __int64 v74; // [rsp+A0h] [rbp-68h] BYREF
  _BYTE *v75; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v76; // [rsp+B0h] [rbp-58h] BYREF
  _DWORD v77[2]; // [rsp+B8h] [rbp-50h] BYREF
  int *v78; // [rsp+C0h] [rbp-48h]
  struct _SecBufferDesc pOutput; // [rsp+C8h] [rbp-40h] BYREF
  __int64 v80; // [rsp+D8h] [rbp-30h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+E0h] [rbp-28h] BYREF
  unsigned int v82; // [rsp+E8h] [rbp-20h] BYREF
  LARGE_INTEGER v83; // [rsp+F0h] [rbp-18h] BYREF
  unsigned int pfContextAttr; // [rsp+F8h] [rbp-10h] BYREF
  int v85; // [rsp+100h] [rbp-8h] BYREF
  unsigned int v86; // [rsp+108h] [rbp+0h] BYREF
  int v87; // [rsp+110h] [rbp+8h] BYREF
  int v88; // [rsp+118h] [rbp+10h] BYREF
  _BYTE *v89; // [rsp+120h] [rbp+18h] BYREF
  _BYTE *v90; // [rsp+128h] [rbp+20h] BYREF
  _BYTE *v91; // [rsp+130h] [rbp+28h] BYREF
  __int64 v92; // [rsp+138h] [rbp+30h] BYREF
  _OWORD pBuffer[2]; // [rsp+140h] [rbp+38h] BYREF
  __int64 v94; // [rsp+160h] [rbp+58h]
  SECURITY_INTEGER ptsExpiry; // [rsp+168h] [rbp+60h] BYREF
  __int64 v96; // [rsp+170h] [rbp+68h] BYREF
  __int64 v97; // [rsp+178h] [rbp+70h] BYREF
  int v98; // [rsp+180h] [rbp+78h] BYREF
  int v99; // [rsp+184h] [rbp+7Ch] BYREF
  _OWORD *v100; // [rsp+188h] [rbp+80h] BYREF
  __int64 v101; // [rsp+190h] [rbp+88h] BYREF
  __int64 v102; // [rsp+198h] [rbp+90h] BYREF
  PVOID pvContextBuffer[2]; // [rsp+1A0h] [rbp+98h] BYREF
  _BYTE v104[16]; // [rsp+1B8h] [rbp+B0h] BYREF
  __int64 *v105; // [rsp+1C8h] [rbp+C0h]
  __int64 v106; // [rsp+1D0h] [rbp+C8h]
  __int64 *v107; // [rsp+1D8h] [rbp+D0h]
  __int64 v108; // [rsp+1E0h] [rbp+D8h]
  __int64 *v109; // [rsp+1E8h] [rbp+E0h]
  __int64 v110; // [rsp+1F0h] [rbp+E8h]
  unsigned __int64 *v111; // [rsp+1F8h] [rbp+F0h]
  __int64 v112; // [rsp+200h] [rbp+F8h]
  LARGE_INTEGER *v113; // [rsp+208h] [rbp+100h]
  __int64 v114; // [rsp+210h] [rbp+108h]
  LARGE_INTEGER *v115; // [rsp+218h] [rbp+110h]
  __int64 v116; // [rsp+220h] [rbp+118h]
  LARGE_INTEGER *v117; // [rsp+228h] [rbp+120h]
  __int64 v118; // [rsp+230h] [rbp+128h]
  __int64 *v119; // [rsp+238h] [rbp+130h]
  __int64 v120; // [rsp+240h] [rbp+138h]
  LARGE_INTEGER *v121; // [rsp+248h] [rbp+140h]
  __int64 v122; // [rsp+250h] [rbp+148h]
  unsigned int *v123; // [rsp+258h] [rbp+150h]
  __int64 v124; // [rsp+260h] [rbp+158h]
  unsigned int *v125; // [rsp+268h] [rbp+160h]
  __int64 v126; // [rsp+270h] [rbp+168h]
  __int64 *v127; // [rsp+278h] [rbp+170h]
  __int64 v128; // [rsp+280h] [rbp+178h]
  LARGE_INTEGER *v129; // [rsp+288h] [rbp+180h]
  __int64 v130; // [rsp+290h] [rbp+188h]
  LARGE_INTEGER *p_PerformanceCount; // [rsp+298h] [rbp+190h]
  __int64 v132; // [rsp+2A0h] [rbp+198h]
  _OWORD v133[2]; // [rsp+2A8h] [rbp+1A0h] BYREF

  TransformedW = 0;
  *a2 = 0;
  v9 = -1;
  v10 = 0;
  *a3 = 0;
  v11 = (__int64 *)(a1 + 48);
  *a4 = 0;
  *a5 = 0;
  *a6 = 0;
  *a7 = 0;
  memset(v133, 0, 28);
  v91 = a4;
  v89 = a5;
  v75 = a6;
  v90 = a7;
  ptsExpiry.QuadPart = 0;
  pOutput = 0;
  pfContextAttr = 0;
  *(_OWORD *)pvContextBuffer = 0;
  hObject = (HANDLE)-1LL;
  v88 = 0;
  if ( *(_QWORD *)(a1 + 48) != -1 && *(_QWORD *)(a1 + 56) != -1 )
    v10 = (struct _SecHandle *)(a1 + 48);
  pInput = (struct _SecBufferDesc *)v77;
  v13 = *(_QWORD *)(a1 + 1336);
  v14 = *(_QWORD *)(a1 + 1328);
  v15 = 49564;
  if ( !*(_BYTE *)(a1 + 105) )
    v15 = 49436;
  v100 = *(_OWORD **)(a1 + 1328);
  v98 = *(_DWORD *)(a1 + 1336);
  if ( !v13 )
    pInput = 0;
  v68 = v15;
  v99 = 2;
  v102 = 0;
  v101 = 0;
  v77[1] = 2;
  v78 = &v98;
  v77[0] = 0;
  v72 = v13;
  if ( !*(_BYTE *)(a1 + 1432) && v13 >= 3 )
  {
    *(_BYTE *)(a1 + 1432) = 1;
    *(_DWORD *)(a1 + 1428) = *(unsigned __int8 *)(v14 + 2) | (*(unsigned __int8 *)(v14 + 1) << 8);
  }
  pOutput.pBuffers = (PSecBuffer)pvContextBuffer;
  HIDWORD(pvContextBuffer[0]) = 2;
  pOutput.cBuffers = 1;
  pOutput.ulVersion = 0;
  if ( v10 )
  {
    v16 = 0;
    v17 = (_QWORD *)(a1 + 64);
    goto LABEL_11;
  }
  if ( *(_BYTE *)(a1 + 184) )
    v40 = (RTL_SRWLOCK **)(a1 + 176);
  else
    v40 = (RTL_SRWLOCK **)(a1 + 168);
  v41 = *v40;
  DWORD2(pBuffer[0]) = 0;
  *(_QWORD *)((char *)&pBuffer[1] + 4) = 0;
  HIDWORD(pBuffer[1]) = 0;
  Ptr = v41[4].Ptr;
  *(_QWORD *)&pBuffer[0] = 4;
  *(_QWORD *)((char *)pBuffer + 12) = 201326596;
  v43 = Ptr[240] & 8;
  if ( !v43 )
  {
    TransformedW = 87;
    goto LABEL_63;
  }
  AcquireSRWLockShared(v41 + 1);
  v44 = (RTL_SRWLOCK *)v41[2].Ptr;
  v45 = v41 + 2;
  if ( v44 == &v41[2] )
  {
    v46.QuadPart = 0;
  }
  else
  {
    while ( 1 )
    {
      v46.QuadPart = (LONGLONG)&v44[-1];
      if ( LOBYTE(v44[29].Ptr) == v43 )
        break;
LABEL_95:
      v44 = (RTL_SRWLOCK *)v44->Ptr;
      v46.QuadPart = 0;
      if ( v44 == v45 )
        goto LABEL_75;
    }
    v47 = v43;
    for ( i = 0; v47 && i < 8; ++i )
    {
      v82 = (unsigned __int8)(1 << i);
      if ( ((unsigned __int8)v82 & v47) != 0 )
      {
        if ( (*((_DWORD *)v41[4].Ptr + 6 * i + 10) & ~*((_DWORD *)pBuffer + i)) != *(_DWORD *)(24LL * i
                                                                                             + v46.QuadPart
                                                                                             + 40) )
        {
          v45 = v41 + 2;
          goto LABEL_95;
        }
        v47 ^= v82;
      }
    }
  }
LABEL_75:
  PerformanceCount = v46;
  ReleaseSRWLockShared(v41 + 1);
  if ( !v46.QuadPart )
  {
    TransformedW = WapUriCreateTransformedW(v41, v43, pBuffer);
    if ( TransformedW )
      goto LABEL_63;
    v46 = PerformanceCount;
  }
  if ( *(_QWORD *)(v46.QuadPart + 224) > 0xC3500u )
  {
    TransformedW = 534;
    goto LABEL_63;
  }
  v16 = *(SEC_WCHAR **)(v46.QuadPart + 216);
  TransformedW = 0;
  v17 = (_QWORD *)(a1 + 64);
  v67 = (_QWORD *)(a1 + 64);
  if ( (*(_BYTE *)(a1 + 1052) & 1) != 0 )
  {
    if ( (*(_DWORD *)(*v17 + 4LL) & 0x2800) != 0 )
    {
      pInput = (struct _SecBufferDesc *)v77;
      *(_QWORD *)&v133[0] = 0x200000018LL;
      WORD4(v133[0]) = 12;
      v49 = &v102;
      v50 = (int *)&v101;
      *(_DWORD *)((char *)&v133[1] + 2) = 825110831;
      v100 = v133;
      v51 = (int *)&v101 + 1;
      *(_QWORD *)((char *)v133 + 10) = 0x7074746808326802LL;
      v99 = 18;
      v98 = 28;
      *(_BYTE *)(a1 + 1240) = 1;
      goto LABEL_82;
    }
    v67 = (_QWORD *)(a1 + 64);
  }
  v50 = &v98;
  v49 = (__int64 *)&v100;
  v51 = &v99;
LABEL_82:
  v11 = (__int64 *)(a1 + 48);
  v15 = v68;
  if ( *(_DWORD *)(a1 + 112) )
  {
    *v51 = 21;
    pInput = (struct _SecBufferDesc *)v77;
    *v49 = WaSslTokenBindingNegotiator;
    *v50 = WaSslTokenBindingNegotiatorSize;
    *(_BYTE *)(a1 + 1241) = 1;
    goto LABEL_12;
  }
LABEL_11:
  v67 = v17;
LABEL_12:
  if ( *(_BYTE *)(a1 + 104) && *(_QWORD *)(*v17 + 32LL) != -1 && *(_QWORD *)(*v17 + 40LL) != -1 )
  {
    TransformedW = WaImpersonateToken(0, (__int64 *)&hObject);
    if ( TransformedW )
      goto LABEL_63;
    v17 = v67;
    v11 = (__int64 *)(a1 + 48);
  }
  v18 = BYTE2(Microsoft_Windows_WebIOEnableBits);
  if ( (Microsoft_Windows_WebIOEnableBits & 0x40000) != 0 )
  {
    v19 = *v17;
    v86 = *(_DWORD *)(a1 + 1344);
    v85 = *(_DWORD *)(a1 + 1336);
    v74 = *(_QWORD *)(a1 + 1376);
    PerformanceCount.LowPart = 0;
    v83.LowPart = 0;
    v73 = 0;
    v87 = 0;
    v82 = v15;
    v92 = *(_QWORD *)(v19 + 32);
    v76 = *(_QWORD *)(v19 + 40);
    v96 = *v11;
    v97 = *(_QWORD *)(a1 + 56);
    v80 = *(_QWORD *)(a1 + 8);
    v105 = &v80;
    v107 = &v97;
    v109 = &v96;
    v111 = (unsigned __int64 *)&v76;
    v113 = (LARGE_INTEGER *)&v92;
    v106 = 8;
    v108 = 8;
    v110 = 8;
    v112 = 8;
    v114 = 8;
    if ( v16 )
    {
      v20 = -1;
      do
        v21 = v16[++v20] == 0;
      while ( !v21 );
      v22 = 2 * v20 + 2;
      v23 = v16;
    }
    else
    {
      v22 = 10;
      v23 = L"NULL";
    }
    v116 = v22;
    v115 = (LARGE_INTEGER *)v23;
    v117 = (LARGE_INTEGER *)&v82;
    v119 = &v74;
    v118 = 4;
    v121 = (LARGE_INTEGER *)&v85;
    v123 = &v86;
    v125 = (unsigned int *)&v87;
    v127 = &v73;
    v129 = &v83;
    p_PerformanceCount = &PerformanceCount;
    v120 = 8;
    v122 = 4;
    v124 = 4;
    v126 = 4;
    v128 = 8;
    v130 = 4;
    v132 = 4;
    McGenEventWrite_EventWriteTransfer(&WEB_ETW_PROVIDER_ID_Context, SSLInitializeSecurityContext, v11, 15, v104);
    v18 = BYTE2(Microsoft_Windows_WebIOEnableBits);
  }
  if ( (v18 & 8) != 0 )
  {
    v56 = *(_DWORD *)(a1 + 1336);
    v83.LowPart = *(_DWORD *)(a1 + 1344);
    v76 = *(_QWORD *)(a1 + 1376);
    v92 = *(_QWORD *)(a1 + 48);
    v74 = *(_QWORD *)(a1 + 56);
    v73 = *(_QWORD *)(a1 + 8);
    v105 = &v73;
    v107 = &v74;
    v109 = &v92;
    v111 = (unsigned __int64 *)&v76;
    v113 = &PerformanceCount;
    v115 = &v83;
    v117 = *(LARGE_INTEGER **)(a1 + 1328);
    PerformanceCount.LowPart = v56;
    v118 = v56;
    v106 = 8;
    v108 = 8;
    v110 = 8;
    v112 = 8;
    v114 = 4;
    v116 = 4;
    McGenEventWrite_EventWriteTransfer(
      &WEB_ETW_PROVIDER_ID_Context,
      SSLInitializeSecurityContextDetailsPre,
      v11,
      8,
      v104);
  }
  PerformanceCount.QuadPart = 0;
  QueryPerformanceCounter(&PerformanceCount);
  v24 = InitializeSecurityContextW(
          (PCredHandle)(*(_QWORD *)(a1 + 64) + 32LL),
          v10,
          v16,
          v15,
          0,
          0x10u,
          pInput,
          0,
          (PCtxtHandle)(a1 + 48),
          &pOutput,
          &pfContextAttr,
          &ptsExpiry);
  v83.QuadPart = 0;
  v25 = v24;
  QueryPerformanceCounter(&v83);
  WaRestoreToken(hObject);
  if ( v25 == 590610 )
  {
    if ( *(_BYTE *)(a1 + 1076) && !v10 )
    {
      v88 = 1;
      v66 = SetContextAttributesW((PCtxtHandle)(a1 + 48), 0x69u, &v88, 4u);
      if ( (xmmword_1800AD720 & 8) != 0 )
        WPP_SF_qD(1027, 40, WPP_56419e6f729131a1bc9745be6fd81bf0_Traceguids, a1, v66);
      v25 = 590610;
    }
  }
  else if ( v25 != 590694 && v25 && (v25 >= 0 || (pfContextAttr & 0x4000) == 0) )
  {
    v28 = a2;
    goto LABEL_91;
  }
  v29 = 0;
  if ( LODWORD(pvContextBuffer[0]) && (v52 = pvContextBuffer[1]) != 0 )
  {
    v53 = LODWORD(pvContextBuffer[0]);
    Heap = (_QWORD *)WxAllocateHeapEx(v26, 136);
    v29 = Heap;
    if ( !Heap )
    {
      if ( (xmmword_1800AD710 & 8) != 0 )
      {
        WPP_SF_d(515, 31, WPP_170392fd7cf134a4357a7b9a1157466f_Traceguids, 8);
        if ( (xmmword_1800AD710 & 8) != 0 )
          WPP_SF_d(515, 30, WPP_170392fd7cf134a4357a7b9a1157466f_Traceguids, 8);
      }
      v28 = a2;
      TransformedW = 8;
      v36 = v67;
      goto LABEL_61;
    }
    memset_0(Heap, 0, 0x88u);
    *(_DWORD *)v29 = 1330205523;
    v29[3] = a1;
    _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(a1 + 8) + 4LL));
    *((_BYTE *)v29 + 92) = 0;
    v29[13] = 0;
    v29[14] = 0;
    *((_DWORD *)v29 + 30) = 997;
    v29[2] = v29 + 1;
    v29[1] = v29 + 1;
    v29[6] = v29 + 8;
    *((_DWORD *)v29 + 16) = 0;
    *((_DWORD *)v29 + 14) = 1;
    v29[9] = v52;
    v29[10] = v53;
    *((_DWORD *)v29 + 24) = *(_DWORD *)(a1 + 32);
    v28 = a2;
    TransformedW = 0;
    pvContextBuffer[1] = 0;
    LODWORD(pvContextBuffer[0]) = 0;
    *a2 = v29;
  }
  else
  {
    v28 = a2;
  }
  if ( v25 && v25 != 590610 && v25 != 590694 )
  {
LABEL_91:
    v36 = v67;
    if ( v25 != -2146893032 )
    {
      if ( v25 != 590624 )
      {
        TransformedW = v25;
        goto LABEL_61;
      }
      v37 = v91;
      goto LABEL_60;
    }
    goto LABEL_59;
  }
  v30 = PerformanceCount;
  v31 = v83;
  v32 = *(_QWORD *)(a1 + 1336);
  v33 = *(_QWORD *)(a1 + 1352);
  if ( HIDWORD(v101) == 5 )
  {
    v34 = (unsigned int)v101;
    v55 = v32 - (unsigned int)v101;
    v27 = v55;
    if ( v55 > v33 )
      *(_QWORD *)(a1 + 1352) = v55;
    *(_QWORD *)(a1 + 1328) += v55;
  }
  else
  {
    v27 = *(_QWORD *)(a1 + 1336);
    if ( v32 > v33 )
      *(_QWORD *)(a1 + 1352) = v32;
    v34 = 0;
    *(_QWORD *)(a1 + 1328) = *(_QWORD *)(a1 + 1376);
  }
  *(_QWORD *)(a1 + 1336) = v34;
  v94 = 0;
  v35 = 0;
  memset(pBuffer, 0, sizeof(pBuffer));
  if ( v29 )
    v35 = v29[10];
  if ( !*(_BYTE *)(a1 + 1128) )
  {
    if ( v25 == 590610 )
    {
      if ( !*(_QWORD *)(a1 + 1136) )
      {
        *(LARGE_INTEGER *)(a1 + 1136) = v30;
        *(LARGE_INTEGER *)(a1 + 1144) = v31;
        *(_QWORD *)(a1 + 1192) = v35;
        goto LABEL_53;
      }
    }
    else if ( v25 != 590694 )
    {
LABEL_41:
      if ( !v25 && !*(_QWORD *)(a1 + 1168) )
      {
        if ( *(_QWORD *)(a1 + 1152) )
        {
          *(_QWORD *)(a1 + 1216) += v27;
          *(LARGE_INTEGER *)(a1 + 1168) = v30;
          *(LARGE_INTEGER *)(a1 + 1176) = v31;
        }
        else
        {
          *(_QWORD *)(a1 + 1200) += v27;
          *(LARGE_INTEGER *)(a1 + 1152) = v30;
          *(LARGE_INTEGER *)(a1 + 1160) = v31;
        }
      }
      QueryContextAttributesExW((PCtxtHandle)(a1 + 48), 0x5Du, pBuffer, 0x28u);
      if ( (pBuffer[0] & 1) != 0 )
        *(_BYTE *)(a1 + 1184) = 1;
      goto LABEL_53;
    }
    if ( *(_QWORD *)(a1 + 1152) )
    {
      if ( v25 == 590610 )
      {
        *(_QWORD *)(a1 + 1216) += v27;
        goto LABEL_53;
      }
      goto LABEL_41;
    }
    if ( v35 )
    {
      *(LARGE_INTEGER *)(a1 + 1152) = v30;
      *(LARGE_INTEGER *)(a1 + 1160) = v31;
      *(_QWORD *)(a1 + 1208) = v35;
    }
    *(_QWORD *)(a1 + 1200) += v27;
    if ( v25 == 590694 )
      *(_BYTE *)(a1 + 1185) = 1;
  }
LABEL_53:
  v36 = v67;
  if ( (*(_BYTE *)(a1 + 105) || *(_QWORD *)(*v67 + 16LL)) && v72 && *v28 )
    *v89 = 1;
  if ( !v25 )
  {
    v37 = v90;
LABEL_60:
    *v37 = 1;
    goto LABEL_61;
  }
  if ( v25 == 590694 )
  {
    *v75 = 1;
    *a3 = 1;
    if ( (xmmword_1800AD720 & 8) != 0 )
      WPP_SF_q(1027, 41, WPP_56419e6f729131a1bc9745be6fd81bf0_Traceguids, a1);
    goto LABEL_61;
  }
  if ( !*(_QWORD *)(a1 + 1336) )
  {
LABEL_59:
    v37 = a3;
    goto LABEL_60;
  }
LABEL_61:
  v38 = BYTE2(Microsoft_Windows_WebIOEnableBits);
  if ( (Microsoft_Windows_WebIOEnableBits & 0x40000) != 0 )
  {
    v61 = (_QWORD *)*v28;
    if ( *v28 )
    {
      v62 = v61[10];
      v63 = v61[6];
    }
    else
    {
      LODWORD(v62) = 0;
      v63 = 0;
    }
    v86 = pfContextAttr;
    v87 = *(_DWORD *)(a1 + 1344);
    v83.LowPart = *(_DWORD *)(a1 + 1336);
    v73 = *(_QWORD *)(a1 + 1376);
    PerformanceCount.LowPart = v68;
    v85 = v62;
    v64 = *v36;
    v74 = v63;
    v82 = v25;
    v106 = 8;
    v91 = *(_BYTE **)(v64 + 32);
    v72 = *(_QWORD *)(v64 + 40);
    v89 = *(_BYTE **)(a1 + 48);
    v90 = *(_BYTE **)(a1 + 56);
    v75 = *(_BYTE **)(a1 + 8);
    v105 = (__int64 *)&v75;
    v107 = (__int64 *)&v90;
    v109 = (__int64 *)&v89;
    v111 = &v72;
    v113 = (LARGE_INTEGER *)&v91;
    v108 = 8;
    v110 = 8;
    v112 = 8;
    v114 = 8;
    if ( v16 )
    {
      do
        v21 = v16[++v9] == 0;
      while ( !v21 );
      v65 = 2 * v9 + 2;
    }
    else
    {
      v16 = L"NULL";
      v65 = 10;
    }
    v115 = (LARGE_INTEGER *)v16;
    v117 = &PerformanceCount;
    v116 = v65;
    v119 = &v73;
    v121 = &v83;
    v118 = 4;
    v123 = (unsigned int *)&v87;
    v125 = &v86;
    v127 = &v74;
    v129 = (LARGE_INTEGER *)&v85;
    p_PerformanceCount = (LARGE_INTEGER *)&v82;
    v120 = 8;
    v122 = 4;
    v124 = 4;
    v126 = 4;
    v128 = 8;
    v130 = 4;
    v132 = 4;
    McGenEventWrite_EventWriteTransfer(
      &WEB_ETW_PROVIDER_ID_Context,
      SSLInitializeSecurityContextComplete,
      v27,
      15,
      v104);
    v38 = BYTE2(Microsoft_Windows_WebIOEnableBits);
  }
  if ( (v38 & 8) != 0 )
  {
    v57 = (_QWORD *)*v28;
    if ( *v28 )
    {
      v58 = (LARGE_INTEGER *)v57[9];
      v59 = v57[10];
      v60 = v57[6];
    }
    else
    {
      v58 = 0;
      LODWORD(v59) = 0;
      v60 = 0;
    }
    v89 = *(_BYTE **)(a1 + 48);
    v90 = *(_BYTE **)(a1 + 56);
    v75 = *(_BYTE **)(a1 + 8);
    v105 = (__int64 *)&v75;
    v107 = (__int64 *)&v90;
    v109 = (__int64 *)&v89;
    v111 = &v72;
    v113 = &PerformanceCount;
    PerformanceCount.LowPart = v59;
    v115 = v58;
    v116 = (unsigned int)v59;
    v72 = v60;
    v106 = 8;
    v108 = 8;
    v110 = 8;
    v112 = 8;
    v114 = 4;
    McGenEventWrite_EventWriteTransfer(
      &WEB_ETW_PROVIDER_ID_Context,
      SSLInitializeSecurityContextDetailsPost,
      v60,
      7,
      v104);
  }
LABEL_63:
  if ( pvContextBuffer[1] && LODWORD(pvContextBuffer[0]) )
    FreeContextBuffer(pvContextBuffer[1]);
  if ( TransformedW && TransformedW != 997 && TransformedW != 234 && (xmmword_1800AD710 & 8) != 0 )
    WPP_SF_d(515, 42, WPP_56419e6f729131a1bc9745be6fd81bf0_Traceguids, TransformedW);
  return TransformedW;
}

```

## disassembly

```asm
0x18000ff50  mov     r11, rsp
0x18000ff53  push    rbp
0x18000ff54  push    r14
0x18000ff56  lea     rbp, [r11-218h]
0x18000ff5d  sub     rsp, 308h
0x18000ff64  mov     rax, cs:__security_cookie
0x18000ff6b  xor     rax, rsp
0x18000ff6e  mov     [rbp+210h+var_50], rax
0x18000ff75  mov     r10, [rbp+210h+arg_28]
0x18000ff7c  xor     r14d, r14d
0x18000ff7f  mov     [r11-18h], rbx
0x18000ff83  mov     rax, r9
0x18000ff86  mov     r9, [rbp+210h+arg_20]
0x18000ff8d  xorps   xmm0, xmm0
0x18000ff90  mov     [rdx], r14
0x18000ff93  mov     rbx, rcx
0x18000ff96  mov     rcx, [rbp+210h+arg_30]
0x18000ff9d  xorps   xmm1, xmm1
0x18000ffa0  mov     [r11-28h], rdi
0x18000ffa4  mov     [r11-30h], r12
0x18000ffa8  mov     [r11-38h], r13
0x18000ffac  mov     r13, 0FFFFFFFFFFFFFFFFh
0x18000ffb3  mov     [r11-40h], r15
0x18000ffb7  mov     r15d, r14d
0x18000ffba  xor     r11d, r11d
0x18000ffbd  mov     [rsp+78h], r8
0x18000ffc2  mov     [r8], r11b
0x18000ffc5  lea     r8, [rbx+30h]
0x18000ffc9  mov     [rax], r11b
0x18000ffcc  mov     [r9], r11b
0x18000ffcf  mov     [r10], r11b
0x18000ffd2  mov     [rcx], r11b
0x18000ffd5  movups  [rbp+210h+var_70], xmm0
0x18000ffdc  mov     [rbp+210h+var_1E8], rax
0x18000ffe0  mov     [rsp+310h+var_2A0], rdx
0x18000ffe5  mov     [rbp+210h+var_1F8], r9
0x18000ffe9  mov     [rbp+210h+var_270], r10
0x18000ffed  mov     [rbp+210h+var_1F0], rcx
0x18000fff1  mov     qword ptr [rbp+210h+var_1B0], r14
0x18000fff5  movups  xmmword ptr [rbp+210h+var_250.ulVersion], xmm0
0x18000fff9  mov     [rbp+210h+var_220], r14d
0x18000fffd  movups  xmmword ptr [rbp+210h+pvContextBuffer], xmm1
0x180010004  mov     [rbp+210h+hObject], r13
0x180010008  movups  [rbp+210h+var_70+0Ch], xmm0
0x18001000f  mov     [rbp+210h+var_200], r14d
0x180010013  cmp     [r8], r13
0x180010016  jnz     loc_1800105DC
0x18001001c  cmp     [rbx+69h], r11b
0x180010020  lea     rdi, [rbp+210h+var_260]
0x180010024  mov     rcx, [rbx+538h]
0x18001002b  mov     eax, 0C11Ch
0x180010030  mov     rdx, [rbx+530h]
0x180010037  mov     r12d, 0C19Ch
0x18001003d  cmovz   r12d, eax
0x180010041  mov     [rbp+210h+var_190], rdx
0x180010048  mov     eax, [rbx+538h]
0x18001004e  test    rcx, rcx
0x180010051  mov     [rbp+210h+var_198], eax
0x180010054  lea     rax, [rbp+210h+var_198]
0x180010058  cmovz   rdi, r14
0x18001005c  mov     dword ptr [rsp+310h+var_2A8], r12d
0x180010061  mov     [rbp+210h+var_194], 2
0x180010068  mov     [rbp+210h+var_180], r14
0x18001006f  mov     [rbp+210h+var_188], r14
0x180010076  mov     [rbp+210h+var_25C], 2
0x18001007d  mov     [rbp+210h+var_258], rax
0x180010081  mov     [rbp+210h+var_260], r14d
0x180010085  mov     [rbp+210h+var_288], rcx
0x180010089  cmp     [rbx+598h], r11b
0x180010090  jnz     short loc_1800100B2
0x180010092  cmp     rcx, 3
0x180010096  jb      short loc_1800100B2
0x180010098  mov     byte ptr [rbx+598h], 1
0x18001009f  movzx   ecx, byte ptr [rdx+1]
0x1800100a3  movzx   eax, byte ptr [rdx+2]
0x1800100a7  shl     ecx, 8
0x1800100aa  or      ecx, eax
0x1800100ac  mov     [rbx+594h], ecx
0x1800100b2  mov     [rsp+310h+var_18], rsi
0x1800100ba  lea     rax, [rbp+210h+pvContextBuffer]
0x1800100c1  mov     [rbp+210h+var_250.pBuffers], rax
0x1800100c5  mov     dword ptr [rbp+210h+pvContextBuffer+4], 2
0x1800100cf  mov     [rbp+210h+var_250.cBuffers], 1
0x1800100d6  mov     [rbp+210h+var_250.ulVersion], r14d
0x1800100da  test    r15, r15
0x1800100dd  jz      loc_1800105EE
0x1800100e3  mov     rsi, r14
0x1800100e6  lea     r9, [rbx+40h]
0x1800100ea  mov     [rsp+310h+var_2B0], r9
0x1800100ef  cmp     byte ptr [rbx+68h], 0
0x1800100f3  jnz     loc_180010E9B
0x1800100f9  movzx   eax, byte ptr cs:Microsoft_Windows_WebIOEnableBits+2
0x180010100  test    al, 4
0x180010102  jz      loc_1800102E4
0x180010108  mov     eax, [rbx+540h]
0x18001010e  xor     edx, edx
0x180010110  mov     rcx, [r9]
0x180010113  mov     [rbp+210h+var_210], eax
0x180010116  mov     eax, [rbx+538h]
0x18001011c  mov     [rbp+210h+var_218], eax
0x18001011f  mov     rax, [rbx+560h]
0x180010126  mov     [rbp+210h+var_278], rax
0x18001012a  mov     dword ptr [rbp+210h+PerformanceCount], edx
0x18001012d  mov     dword ptr [rbp+210h+var_228], edx
0x180010130  mov     [rbp+210h+var_280], rdx
0x180010134  mov     [rbp+210h+var_208], edx
0x180010137  mov     [rbp+210h+var_230], r12d
0x18001013b  mov     rax, [rcx+20h]
0x18001013f  mov     [rbp+210h+var_1E0], rax
0x180010143  mov     rax, [rcx+28h]
0x180010147  mov     [rbp+210h+var_268], rax
0x18001014b  mov     rax, [r8]
0x18001014e  mov     [rbp+210h+var_1A8], rax
0x180010152  mov     rax, [rbx+38h]
0x180010156  mov     [rbp+210h+var_1A0], rax
0x18001015a  mov     rax, [rbx+8]
0x18001015e  mov     [rbp+210h+var_240], rax
0x180010162  lea     rax, [rbp+210h+var_240]
0x180010166  mov     [rbp+210h+var_150], rax
0x18001016d  lea     rax, [rbp+210h+var_1A0]
0x180010171  mov     [rbp+210h+var_140], rax
0x180010178  lea     rax, [rbp+210h+var_1A8]
0x18001017c  mov     [rbp+210h+var_130], rax
0x180010183  lea     rax, [rbp+210h+var_268]
0x180010187  mov     [rbp+210h+var_120], rax
0x18001018e  lea     rax, [rbp+210h+var_1E0]
0x180010192  mov     [rbp+210h+var_110], rax
0x180010199  mov     [rbp+210h+var_148], 8
0x1800101a4  mov     [rbp+210h+var_138], 8
0x1800101af  mov     [rbp+210h+var_128], 8
0x1800101ba  mov     [rbp+210h+var_118], 8
0x1800101c5  mov     [rbp+210h+var_108], 8
0x1800101d0  test    rsi, rsi
0x1800101d3  jz      loc_180010CF7
0x1800101d9  mov     rax, r13
0x1800101dc  nop     dword ptr [rax+00h]
0x1800101e0  cmp     [rsi+rax*2+2], dx
0x1800101e5  lea     rax, [rax+1]
0x1800101e9  jnz     short loc_1800101E0
0x1800101eb  lea     eax, ds:2[rax*2]
0x1800101f2  mov     rcx, rsi
0x1800101f5  mov     dword ptr [rbp+210h+var_F8], eax
0x1800101fb  mov     r9d, 0Fh
0x180010201  lea     rax, [rbp+210h+var_230]
0x180010205  mov     [rbp+210h+var_100], rcx
0x18001020c  mov     [rbp+210h+var_F0], rax
0x180010213  lea     rcx, WEB_ETW_PROVIDER_ID_Context
0x18001021a  lea     rax, [rbp+210h+var_278]
0x18001021e  mov     dword ptr [rbp+210h+var_F8+4], edx
0x180010224  mov     [rbp+210h+var_E0], rax
0x18001022b  lea     rdx, SSLInitializeSecurityContext
0x180010232  lea     rax, [rbp+210h+var_218]
0x180010236  mov     [rbp+210h+var_E8], 4
0x180010241  mov     [rbp+210h+var_D0], rax
0x180010248  lea     rax, [rbp+210h+var_210]
0x18001024c  mov     [rbp+210h+var_C0], rax
0x180010253  lea     rax, [rbp+210h+var_208]
0x180010257  mov     [rbp+210h+var_B0], rax
0x18001025e  lea     rax, [rbp+210h+var_280]
0x180010262  mov     [rbp+210h+var_A0], rax
0x180010269  lea     rax, [rbp+210h+var_228]
0x18001026d  mov     [rbp+210h+var_90], rax
0x180010274  lea     rax, [rbp+210h+PerformanceCount]
0x180010278  mov     [rbp+210h+var_80], rax
0x18001027f  lea     rax, [rbp+210h+var_160]
0x180010286  mov     qword ptr [rsp+310h+Reserved1], rax
0x18001028b  mov     [rbp+210h+var_D8], 8
0x180010296  mov     [rbp+210h+var_C8], 4
0x1800102a1  mov     [rbp+210h+var_B8], 4
0x1800102ac  mov     [rbp+210h+var_A8], 4
0x1800102b7  mov     [rbp+210h+var_98], 8
0x1800102c2  mov     [rbp+210h+var_88], 4
0x1800102cd  mov     [rbp+210h+var_78], 4
0x1800102d8  call    McGenEventWrite_EventWriteTransfer
0x1800102dd  movzx   eax, byte ptr cs:Microsoft_Windows_WebIOEnableBits+2
0x1800102e4  test    al, 8
0x1800102e6  jnz     loc_1800108CA
0x1800102ec  lea     rcx, [rbp+210h+PerformanceCount]; lpPerformanceCount
0x1800102f0  mov     qword ptr [rbp+210h+PerformanceCount], 0
0x1800102f8  call    cs:__imp_QueryPerformanceCounter
0x1800102ff  nop     dword ptr [rax+rax+00h]
0x180010304  mov     rcx, [rbx+40h]
0x180010308  lea     rax, [rbp+210h+var_1B0]
0x18001030c  mov     [rsp+310h+ptsExpiry], rax; ptsExpiry
0x180010311  add     rcx, 20h ; ' '; phCredential
0x180010315  lea     rax, [rbp+210h+var_220]
0x180010319  mov     r9d, r12d; fContextReq
0x18001031c  mov     [rsp+310h+pfContextAttr], rax; pfContextAttr
0x180010321  mov     r8, rsi; pszTargetName
0x180010324  lea     rax, [rbp+210h+var_250]
0x180010328  mov     rdx, r15; phContext
0x18001032b  mov     [rsp+310h+pOutput], rax; pOutput
0x180010330  lea     rax, [rbx+30h]
0x180010334  mov     [rsp+310h+phNewContext], rax; phNewContext
0x180010339  xor     eax, eax
0x18001033b  mov     [rsp+310h+Reserved2], eax; Reserved2
0x18001033f  mov     [rsp+310h+pInput], rdi; pInput
0x180010344  mov     [rsp+310h+TargetDataRep], 10h; TargetDataRep
0x18001034c  mov     [rsp+310h+Reserved1], eax; Reserved1
0x180010350  call    cs:__imp_InitializeSecurityContextW
0x180010357  nop     dword ptr [rax+rax+00h]
0x18001035c  lea     rcx, [rbp+210h+var_228]; lpPerformanceCount
0x180010360  mov     qword ptr [rbp+210h+var_228], 0
0x180010368  mov     r12d, eax
0x18001036b  call    cs:__imp_QueryPerformanceCounter
0x180010372  nop     dword ptr [rax+rax+00h]
0x180010377  mov     rcx, [rbp+210h+hObject]; hObject
0x18001037b  call    WaRestoreToken
0x180010380  cmp     r12d, 90312h
0x180010387  jz      short loc_1800103AC
0x180010389  cmp     r12d, 90366h
0x180010390  jz      short loc_1800103B9
0x180010392  test    r12d, r12d
0x180010395  jz      short loc_1800103B9
0x180010397  jns     short loc_1800103A2
0x180010399  test    [rbp+210h+var_220], 4000h
0x1800103a0  jnz     short loc_1800103B9
0x1800103a2  mov     rdi, [rsp+310h+var_2A0]
0x1800103a7  jmp     loc_1800108A2
0x1800103ac  cmp     byte ptr [rbx+434h], 0
0x1800103b3  jnz     loc_180010D80
0x1800103b9  mov     eax, dword ptr [rbp+210h+pvContextBuffer]
0x1800103bf  xor     r11d, r11d
0x1800103c2  mov     r15d, r11d
0x1800103c5  test    eax, eax
0x1800103c7  jnz     loc_1800107C2
0x1800103cd  mov     rdi, [rsp+310h+var_2A0]
0x1800103d2  test    r12d, r12d
0x1800103d5  jz      short loc_1800103E4
0x1800103d7  cmp     r12d, 90312h
0x1800103de  jnz     loc_180010895
0x1800103e4  cmp     dword ptr [rbp+210h+var_188+4], 5
0x1800103eb  mov     r9, qword ptr [rbp+210h+PerformanceCount]
0x1800103ef  mov     r10, qword ptr [rbp+210h+var_228]
0x1800103f3  mov     rax, [rbx+538h]
0x1800103fa  mov     rdx, [rbx+548h]
0x180010401  jz      loc_180010871
0x180010407  mov     r8, rax
0x18001040a  cmp     rax, rdx
0x18001040d  jbe     short loc_180010416
0x18001040f  mov     [rbx+548h], rax
0x180010416  mov     rax, [rbx+560h]
0x18001041d  mov     rcx, r11
0x180010420  mov     [rbx+530h], rax
0x180010427  xor     eax, eax
0x180010429  mov     [rbx+538h], rcx
0x180010430  mov     [rbp+210h+var_1B8], rax
0x180010434  xorps   xmm0, xmm0
0x180010437  mov     rax, r11
0x18001043a  movups  [rbp+210h+pBuffer], xmm0
0x18001043e  movups  [rbp+210h+var_1C8], xmm0
0x180010442  test    r15, r15
0x180010445  jz      short loc_18001044B
0x180010447  mov     rax, [r15+50h]
0x18001044b  cmp     byte ptr [rbx+468h], 0
0x180010452  jnz     loc_180010514
0x180010458  cmp     r12d, 90312h
0x18001045f  jz      short loc_1800104CA
0x180010461  cmp     r12d, 90366h
0x180010468  jz      short loc_1800104D8
0x18001046a  test    r12d, r12d
0x18001046d  jnz     short loc_18001049C
0x18001046f  cmp     qword ptr [rbx+490h], 0
0x180010477  jnz     short loc_18001049C
0x180010479  cmp     qword ptr [rbx+480h], 0
0x180010481  jz      loc_180010D1F
0x180010487  add     [rbx+4C0h], r8
0x18001048e  mov     [rbx+490h], r9
0x180010495  mov     [rbx+498h], r10
0x18001049c  mov     r9d, 28h ; '('; cbBuffer
0x1800104a2  lea     r8, [rbp+210h+pBuffer]; pBuffer
0x1800104a6  mov     edx, 5Dh ; ']'; ulAttribute
0x1800104ab  lea     rcx, [rbx+30h]; phContext
0x1800104af  call    cs:__imp_QueryContextAttributesExW
0x1800104b6  nop     dword ptr [rax+rax+00h]
0x1800104bb  test    byte ptr [rbp+210h+pBuffer], 1
0x1800104bf  jz      short loc_180010514
0x1800104c1  mov     byte ptr [rbx+4A0h], 1
0x1800104c8  jmp     short loc_180010514
0x1800104ca  cmp     qword ptr [rbx+470h], 0
0x1800104d2  jz      loc_180010CBC
0x1800104d8  cmp     qword ptr [rbx+480h], 0
0x1800104e0  jnz     loc_180010D67
0x1800104e6  test    rax, rax
0x1800104e9  jz      short loc_180010500
0x1800104eb  mov     [rbx+480h], r9
0x1800104f2  mov     [rbx+488h], r10
0x1800104f9  mov     [rbx+4B8h], rax
0x180010500  add     [rbx+4B0h], r8
0x180010507  cmp     r12d, 90366h
0x18001050e  jz      loc_180010F5F
0x180010514  cmp     byte ptr [rbx+69h], 0
0x180010518  mov     r15, [rsp+310h+var_2B0]
0x18001051d  jnz     loc_180010CD6
0x180010523  mov     rax, [r15]
0x180010526  cmp     qword ptr [rax+10h], 0
0x18001052b  jnz     loc_180010CD6
0x180010531  test    r12d, r12d
0x180010534  jnz     short loc_18001053C
0x180010536  mov     rax, [rbp+210h+var_1F0]
  ... truncated ...
```
