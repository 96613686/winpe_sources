# CSpp::GetVolumesForComponents(ulong,_SPP_WRITER_COMPONENT_INFO *,ulong,ushort const * const *,ulong *,ushort * * *)

- ea: `0x18000b8c0`
- end: `0x18000c05c`
- name: `?GetVolumesForComponents@CSpp@@UEAAJKPEAU_SPP_WRITER_COMPONENT_INFO@@KPEBQEBGPEAKPEAPEAPEAG@Z`
- size: `1948`
- prototype: `__int64 __fastcall(CSpp *this, unsigned int, struct _SPP_WRITER_COMPONENT_INFO *, unsigned int, const unsigned __int16 *const *, unsigned int *, unsigned __int16 ***)`
- caller_count: `0`
- callee_count: `27`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800021f8`
- `0x18000232c`
- `0x180007344`
- `0x180007650`
- `0x180007804`
- `0x180007884`
- `0x180008c74`
- `0x18000907c`
- `0x18000b5f4`
- `0x18000b8c0`
- `0x18000c804`
- `0x18000c894`
- `0x18000cc50`
- `0x18000e080`
- `0x18000e308`
- `0x18000e48c`
- `0x18000e54c`
- `0x18000e58c`
- `0x18000e5cc`
- `0x180017960`
- `0x18001b1e0`
- `0x180020710`
- `0x180020908`
- `0x1800268b4`
- `0x1800269ac`
- `0x18002f2b0`
- `0x180037010`

## import_xrefs

- `VSSAPI!CreateVssBackupComponentsInternal` at `0x18000bae2`
- `VSSAPI!CreateVssBackupComponentsInternal` at `0x18000bae2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000bf9d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000bf9d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ba84`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ba84`

## string_xrefs

- `0x18000b928`: `CSpp::GetVolumesForComponents`

## pseudocode

```c
__int64 __fastcall CSpp::GetVolumesForComponents(
        CSpp *this,
        unsigned int a2,
        struct _SPP_WRITER_COMPONENT_INFO *a3,
        unsigned int a4,
        const unsigned __int16 *const *a5,
        unsigned int *a6,
        unsigned __int16 ***a7)
{
  __int64 v8; // r12
  struct CWriterEntry *v10; // rbx
  struct CSxVolumeInfoArray *v11; // r13
  CComponentEntry *v12; // r15
  wchar_t **v13; // rsi
  __int16 v14; // ax
  CVolumeEntryMap *v15; // r14
  __int64 i; // rdi
  int v17; // eax
  bool v18; // sf
  struct CWriterEntry *v19; // rdx
  CWriterEntryMap *v20; // rcx
  char *v21; // rax
  __int64 v22; // rdx
  char *v23; // rdi
  __int64 v24; // rax
  __int64 v25; // rcx
  CSpp *v26; // rcx
  int v27; // eax
  int v28; // eax
  unsigned int v29; // r14d
  unsigned int v30; // edi
  unsigned int v31; // eax
  int v32; // eax
  __int16 v33; // r10
  CWriterEntry *v34; // rcx
  int v35; // eax
  unsigned int v36; // r13d
  unsigned int v37; // eax
  int v38; // eax
  __int16 v39; // ax
  char v40; // cl
  unsigned int v41; // r13d
  __int64 v42; // r12
  struct _SPP_WRITER_COMPONENT_INFO *v43; // rdx
  __int64 v44; // rdi
  __int64 v45; // rax
  CVolumeEntryMap *v46; // rax
  __int64 v47; // rcx
  int v48; // eax
  unsigned int k; // edi
  unsigned int v50; // edi
  __int64 v51; // rdx
  __int64 v52; // r8
  CVolumeEntryMap *v54; // [rsp+28h] [rbp-C1h] BYREF
  int v55; // [rsp+30h] [rbp-B9h]
  int inited; // [rsp+38h] [rbp-B1h] BYREF
  __int16 j; // [rsp+3Ch] [rbp-ADh]
  __int16 v58; // [rsp+3Eh] [rbp-ABh]
  struct CSxVolumeInfoArray *v59; // [rsp+70h] [rbp-79h] BYREF
  CVolumeEntry *v60; // [rsp+78h] [rbp-71h] BYREF
  struct CWriterEntry *v61; // [rsp+80h] [rbp-69h] BYREF
  unsigned int v62; // [rsp+88h] [rbp-61h]
  unsigned int v63; // [rsp+8Ch] [rbp-5Dh]
  struct IVssBackupComponents *v64; // [rsp+90h] [rbp-59h] BYREF
  int v65; // [rsp+98h] [rbp-51h] BYREF
  CVolumeEntryMap *v66[2]; // [rsp+A0h] [rbp-49h]
  CComponentEntry *v67; // [rsp+B0h] [rbp-39h] BYREF
  LPVOID pv; // [rsp+B8h] [rbp-31h]
  CWriterEntry *v69; // [rsp+C0h] [rbp-29h] BYREF
  CWriterEntryMap *v70; // [rsp+C8h] [rbp-21h] BYREF
  unsigned int v71; // [rsp+D0h] [rbp-19h]
  unsigned int v72; // [rsp+D4h] [rbp-15h]
  wchar_t **v73; // [rsp+D8h] [rbp-11h]
  unsigned __int64 v74; // [rsp+E0h] [rbp-9h] BYREF
  CVolumeEntry *v75; // [rsp+E8h] [rbp-1h]

  v8 = a2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 190, &WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&inited, "CSpp::GetVolumesForComponents", 11064, 1);
  ATL::CComPtr<IVssBackupComponents>::CComPtr<IVssBackupComponents>(&v64);
  v59 = 0;
  v10 = 0;
  v61 = 0;
  v11 = 0;
  v74 = 0;
  v12 = 0;
  v67 = 0;
  v13 = 0;
  v75 = 0;
  v14 = 11087;
  v60 = 0;
  v70 = 0;
  v54 = 0;
  v65 = 0;
  v69 = 0;
  pv = 0;
  *(_OWORD *)v66 = 0;
  if ( !(_DWORD)v8 || (j = 11087, v14 = 11088, !a3) || (j = 11088, v14 = 11089, !a6) || (j = 11089, v14 = 11090, !a7) )
  {
    inited = -2147024809;
    goto LABEL_6;
  }
  inited = 0;
  j = 11090;
  *a6 = 0;
  *a7 = 0;
  inited = CWriterEntryMap::CreateInstance(&v70);
  v14 = 11098;
  if ( inited < 0 )
    goto LABEL_6;
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    j = v14;
    if ( (unsigned int)i >= (unsigned int)v8 )
      break;
    if ( v10 )
    {
      v61 = 0;
      CWriterEntry::Release(v10);
    }
    v17 = CWriterEntry::CreateInstance(&v61);
    v10 = v61;
    v18 = v17 < 0;
    inited = v17;
    v14 = 11102;
    if ( v18 )
      goto LABEL_6;
    j = 11102;
    v19 = v61;
    v20 = v70;
    *((_OWORD *)v61 + 2) = *((_OWORD *)a3 + 3 * i);
    inited = CSxRefMap<CWriterEntryMap,CWriterEntry>::Insert(v20, v19);
    v14 = 11105;
    if ( inited < 0 )
      goto LABEL_6;
  }
  v21 = (char *)CoTaskMemAlloc(16 * v8);
  pv = v21;
  if ( !v21 )
  {
    inited = -2147024882;
    v58 = 11111;
    goto LABEL_7;
  }
  v22 = 0;
  inited = 0;
  j = 11111;
  v23 = v21;
  do
  {
    v24 = 6 * v22;
    v25 = 2LL * (unsigned int)v22;
    v22 = (unsigned int)(v22 + 1);
    *(_OWORD *)&v23[8 * v25] = *(_OWORD *)((char *)a3 + 8 * v24);
  }
  while ( (unsigned int)v22 < (unsigned int)v8 );
  inited = CreateVssBackupComponentsInternal(&v64, v22);
  v14 = 11122;
  if ( inited < 0 )
    goto LABEL_6;
  j = 11122;
  inited = (*(__int64 (__fastcall **)(struct IVssBackupComponents *, _QWORD))(*(_QWORD *)v64 + 40LL))(v64, 0);
  v14 = 11124;
  if ( inited < 0 )
    goto LABEL_6;
  j = 11124;
  inited = CSpp::_InitTimer(v26, 0xFFFFFFFFLL, &v74);
  v14 = 11126;
  if ( inited < 0 )
    goto LABEL_6;
  j = 11126;
  inited = (*(__int64 (__fastcall **)(struct IVssBackupComponents *, char *, _QWORD))(*(_QWORD *)v64 + 368LL))(
             v64,
             v23,
             (unsigned int)v8);
  v14 = 11128;
  if ( inited < 0 )
    goto LABEL_6;
  j = 11128;
  v27 = CSxVolumeInfoArray::CreateInstance(&v59);
  v11 = v59;
  v18 = v27 < 0;
  inited = v27;
  v14 = 11131;
  if ( v18 )
    goto LABEL_6;
  j = 11131;
  v28 = CSpp::_GatherWriterMetadata(this, v64, v59, v74);
  v29 = 0;
  inited = v28;
  v18 = v28 < 0;
  v14 = 11132;
  if ( v18 || (j = 11132, inited = CVolumeEntryMap::CreateInstance((LPVOID **)&v54), v14 = 11137, inited < 0) )
  {
LABEL_6:
    v58 = v14;
    goto LABEL_7;
  }
  j = 11137;
  v30 = 0;
  v31 = *((_DWORD *)v11 + 2);
  v72 = v31;
  while ( 1 )
  {
    v63 = v30;
    if ( v30 >= v31 )
    {
      v15 = v54;
      inited = CVolumeEntryMap::GetVolumeNameArray(v54, a6, a7);
      if ( inited >= 0 )
        j = 11228;
      else
        v58 = 11228;
      goto LABEL_99;
    }
    if ( v10 )
    {
      v61 = 0;
      CWriterEntry::Release(v10);
    }
    v32 = CSxRefArray<CWriterEntryArray,CWriterEntry>::Get(v11, v30, &v61);
    v10 = v61;
    inited = v32;
    if ( v32 < 0 )
    {
      v58 = v33;
      goto LABEL_7;
    }
    j = v33;
    if ( !*((_DWORD *)v61 + 20) )
    {
      v34 = v69;
      if ( v69 )
      {
        v69 = 0;
        CWriterEntry::Release(v34);
      }
      v35 = CSxRefMap<CPathCache,CPathCacheNode>::Find(v70, v10, &v69);
      inited = v35;
      if ( v35 < 0 )
      {
        v14 = 11151;
        goto LABEL_6;
      }
      j = 11151;
      if ( !v35 )
        break;
    }
LABEL_86:
    v31 = v72;
    ++v30;
  }
  v36 = 0;
  v37 = *(_DWORD *)(*((_QWORD *)v10 + 8) + 8LL);
  v71 = v37;
  while ( 1 )
  {
    v62 = v36;
    if ( v36 >= v37 )
    {
      v11 = v59;
      v30 = v63;
      goto LABEL_86;
    }
    if ( v12 )
    {
      v67 = 0;
      CComponentEntry::Release(v12);
    }
    v38 = CSxRefArray<CWriterEntryArray,CWriterEntry>::Get(*((_QWORD *)v10 + 8), v36, &v67);
    v12 = v67;
    v18 = v38 < 0;
    inited = v38;
    v39 = 11163;
    if ( v18 )
      goto LABEL_92;
    j = 11163;
    v40 = 0;
    LOBYTE(v55) = 0;
    v41 = 0;
    v73 = (wchar_t **)v67;
    if ( (_DWORD)v8 )
      break;
LABEL_84:
    v37 = v71;
    v36 = v62 + 1;
  }
  v42 = 0;
  v43 = a3;
  do
  {
    v44 = 48 * v42;
    v45 = *((_QWORD *)v10 + 4) - *((_QWORD *)v43 + 6 * v42);
    if ( !v45 )
      v45 = *((_QWORD *)v10 + 5) - *(_QWORD *)((char *)v43 + v44 + 8);
    if ( !v45 )
    {
      while ( v29 < *(_DWORD *)((char *)v43 + v44 + 32) )
      {
        if ( SxStringCompare(v73[1], *(wchar_t **)(*(_QWORD *)((char *)v43 + v44 + 40) + 16LL * v29 + 8)) )
        {
          v12 = (CComponentEntry *)v73;
          if ( SxStringCompare(v73[5], *(wchar_t **)(*(_QWORD *)((char *)a3 + v44 + 40) + 16LL * v29)) )
          {
            v43 = a3;
            v40 = 1;
            LOBYTE(v55) = 1;
            goto LABEL_57;
          }
        }
        else
        {
          v12 = (CComponentEntry *)v73;
        }
        v43 = a3;
        ++v29;
      }
      v40 = v55;
LABEL_57:
      v29 = 0;
    }
    ++v41;
    ++v42;
  }
  while ( v41 < a2 );
  v13 = (wchar_t **)v75;
  if ( !v40 )
  {
LABEL_83:
    LODWORD(v8) = a2;
    goto LABEL_84;
  }
  v46 = v66[0];
  if ( v66[0] )
  {
    CVolumeEntryMap::Release(v66[0]);
    v46 = 0;
    v66[0] = 0;
  }
  v65 = 0;
  v66[1] = 0;
  v47 = *((_QWORD *)v12 + 15);
  if ( !v47 )
  {
    inited = -2147024809;
    goto LABEL_91;
  }
  if ( v46 )
  {
    inited = -2147418113;
LABEL_91:
    v39 = 11200;
    goto LABEL_92;
  }
  v66[0] = *((CVolumeEntryMap **)v12 + 15);
  _InterlockedIncrement((volatile signed __int32 *)(v47 + 16));
  v65 = *((_DWORD *)v66[0] + 2);
  v66[1] = 0;
  inited = 0;
  j = 11200;
  if ( v13 )
  {
    v60 = 0;
    CVolumeEntry::Release((CVolumeEntry *)v13);
  }
  v48 = CSxRefMap<CSxStringMap,CSxStringEntry>::CSxIter::Next(&v65, &v60);
  inited = v48;
  if ( v48 < 0 )
  {
    v13 = (wchar_t **)v60;
    v39 = 11203;
LABEL_92:
    v58 = v39;
    goto LABEL_93;
  }
  for ( j = 11203; ; j = 11223 )
  {
    v13 = (wchar_t **)v60;
    if ( v48 == 1 )
    {
      v75 = v60;
      goto LABEL_83;
    }
    for ( k = 0; k < a4; ++k )
    {
      if ( SxStringCompare(v13[1], (wchar_t *)a5[k]) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 191, &WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids, v13[1]);
        goto LABEL_78;
      }
    }
    inited = CSxRefMap<CVolumeOnDiskPropCacheMap,CVolumeOnDiskPropCacheEntry>::Insert(v54, v13, 0);
    v39 = 11219;
    if ( inited < 0 )
      goto LABEL_92;
    j = 11219;
LABEL_78:
    if ( v13 )
    {
      v60 = 0;
      CVolumeEntry::Release((CVolumeEntry *)v13);
    }
    v48 = CSxRefMap<CSxStringMap,CSxStringEntry>::CSxIter::Next(&v65, &v60);
    inited = v48;
    if ( v48 < 0 )
      break;
  }
  v13 = (wchar_t **)v60;
  v58 = 11223;
LABEL_93:
  v11 = v59;
LABEL_7:
  v15 = v54;
LABEL_99:
  CoTaskMemFree(pv);
  v50 = inited;
  if ( v69 )
    CWriterEntry::Release(v69);
  if ( v66[0] )
  {
    CVolumeEntryMap::Release(v66[0]);
    v66[0] = 0;
  }
  v65 = 0;
  v66[1] = 0;
  if ( v15 )
    CVolumeEntryMap::Release(v15);
  if ( v70 )
    CWriterEntryMap::Release(v70);
  if ( v13 )
    CVolumeEntry::Release((CVolumeEntry *)v13);
  if ( v12 )
    CComponentEntry::Release(v12);
  if ( v10 )
    CWriterEntry::Release(v10);
  if ( v11 )
    CWriterEntryArray::Release(v11);
  ATL::CComPtr<IVssExamineWriterMetadata>::~CComPtr<IVssExamineWriterMetadata>();
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&inited, v51, v52);
  return v50;
}

```

## disassembly

```asm
0x18000b8c0  mov     rax, rsp
0x18000b8c3  mov     [rax+8], rbx
0x18000b8c7  mov     [rax+20h], r9d
0x18000b8cb  mov     [rax+18h], r8
0x18000b8cf  mov     [rax+10h], edx
0x18000b8d2  push    rbp
0x18000b8d3  push    rsi
0x18000b8d4  push    rdi
0x18000b8d5  push    r12
0x18000b8d7  push    r13
0x18000b8d9  push    r14
0x18000b8db  push    r15
0x18000b8dd  lea     rbp, [rax-47h]
0x18000b8e1  sub     rsp, 0F0h
0x18000b8e8  mov     rdi, r8
0x18000b8eb  mov     r12d, edx
0x18000b8ee  mov     r14, rcx
0x18000b8f1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b8f8  lea     rax, WPP_GLOBAL_Control
0x18000b8ff  cmp     rcx, rax
0x18000b902  jz      short loc_18000B922
0x18000b904  test    dword ptr [rcx+1Ch], 20000000h
0x18000b90b  jz      short loc_18000B922
0x18000b90d  mov     rcx, [rcx+10h]
0x18000b911  lea     r8, WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids
0x18000b918  mov     edx, 0BEh
0x18000b91d  call    WPP_SF_
0x18000b922  mov     r9d, 1; unsigned __int16
0x18000b928  lea     rdx, aCsppGetvolumes_0; "CSpp::GetVolumesForComponents"
0x18000b92f  mov     r8d, 2B38h; unsigned __int16
0x18000b935  lea     rcx, [rsp+120h+var_F0]; this
0x18000b93a  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18000b93f  lea     rcx, [rbp+3Fh+var_98]
0x18000b943  call    ??0?$CComPtr@VIVssBackupComponents@@@ATL@@QEAA@H@Z; ATL::CComPtr<IVssBackupComponents>::CComPtr<IVssBackupComponents>(int)
0x18000b948  xor     r8d, r8d
0x18000b94b  xorps   xmm0, xmm0
0x18000b94e  mov     [rbp+3Fh+var_B8], r8
0x18000b952  mov     ebx, r8d
0x18000b955  mov     [rbp+3Fh+var_A8], rbx
0x18000b959  mov     r13d, r8d
0x18000b95c  mov     [rbp+3Fh+var_48], r8
0x18000b960  mov     r15d, r8d
0x18000b963  mov     [rbp+3Fh+var_78], r8
0x18000b967  mov     esi, r8d
0x18000b96a  mov     [rbp+3Fh+var_40], r8
0x18000b96e  mov     eax, 2B4Fh
0x18000b973  mov     [rbp+3Fh+var_B0], r8
0x18000b977  mov     [rbp+3Fh+var_60], r8
0x18000b97b  mov     [rsp+120h+var_100], r8
0x18000b980  mov     [rbp+3Fh+var_90], r8d
0x18000b984  mov     [rbp+3Fh+var_68], r8
0x18000b988  mov     [rbp+3Fh+pv], r8
0x18000b98c  movdqu  xmmword ptr [rbp+3Fh+var_88], xmm0
0x18000b991  test    r12d, r12d
0x18000b994  jnz     short loc_18000B9AD
0x18000b996  mov     [rsp+120h+var_F0], 80070057h
0x18000b99e  mov     [rsp+120h+var_EA], ax
0x18000b9a3  mov     r14, [rsp+120h+var_100]
0x18000b9a8  jmp     loc_18000BF99
0x18000b9ad  mov     [rsp+120h+var_EC], ax
0x18000b9b2  mov     eax, 2B50h
0x18000b9b7  test    rdi, rdi
0x18000b9ba  jz      short loc_18000B996
0x18000b9bc  mov     rdx, [rbp+3Fh+arg_28]
0x18000b9c0  mov     [rsp+120h+var_EC], ax
0x18000b9c5  mov     eax, 2B51h
0x18000b9ca  test    rdx, rdx
0x18000b9cd  jz      short loc_18000B996
0x18000b9cf  mov     rcx, [rbp+3Fh+arg_30]
0x18000b9d3  mov     [rsp+120h+var_EC], ax
0x18000b9d8  mov     eax, 2B52h
0x18000b9dd  test    rcx, rcx
0x18000b9e0  jz      short loc_18000B996
0x18000b9e2  mov     [rsp+120h+var_F0], r8d
0x18000b9e7  mov     [rsp+120h+var_EC], ax
0x18000b9ec  mov     [rdx], r8d
0x18000b9ef  mov     [rcx], r8
0x18000b9f2  lea     rcx, [rbp+3Fh+var_60]; struct CWriterEntryMap **
0x18000b9f6  call    ?CreateInstance@CWriterEntryMap@@SAJPEAPEAV1@@Z; CWriterEntryMap::CreateInstance(CWriterEntryMap * *)
0x18000b9fb  mov     [rsp+120h+var_F0], eax
0x18000b9ff  test    eax, eax
0x18000ba01  mov     eax, 2B5Ah
0x18000ba06  js      short loc_18000B99E
0x18000ba08  xor     edi, edi
0x18000ba0a  mov     [rsp+120h+var_EC], ax
0x18000ba0f  cmp     edi, r12d
0x18000ba12  jnb     short loc_18000BA7D
0x18000ba14  test    rbx, rbx
0x18000ba17  jz      short loc_18000BA25
0x18000ba19  mov     rcx, rbx; this
0x18000ba1c  mov     [rbp+3Fh+var_A8], rsi
0x18000ba20  call    ?Release@CWriterEntry@@QEAAKXZ; CWriterEntry::Release(void)
0x18000ba25  lea     rcx, [rbp+3Fh+var_A8]; struct CWriterEntry **
0x18000ba29  call    ?CreateInstance@CWriterEntry@@SAJPEAPEAV1@@Z; CWriterEntry::CreateInstance(CWriterEntry * *)
0x18000ba2e  mov     rbx, [rbp+3Fh+var_A8]
0x18000ba32  test    eax, eax
0x18000ba34  mov     [rsp+120h+var_F0], eax
0x18000ba38  mov     eax, 2B5Eh
0x18000ba3d  js      loc_18000B99E
0x18000ba43  mov     [rsp+120h+var_EC], ax
0x18000ba48  lea     rcx, [rdi+rdi*2]
0x18000ba4c  mov     rax, [rbp+3Fh+arg_10]
0x18000ba50  add     rcx, rcx
0x18000ba53  mov     rdx, rbx
0x18000ba56  movups  xmm0, xmmword ptr [rax+rcx*8]
0x18000ba5a  mov     rcx, [rbp+3Fh+var_60]
0x18000ba5e  movdqu  xmmword ptr [rbx+20h], xmm0
0x18000ba63  call    ?Insert@?$CSxRefMap@VCWriterEntryMap@@VCWriterEntry@@@@QEAAJPEAVCWriterEntry@@PEAPEAV2@@Z; CSxRefMap<CWriterEntryMap,CWriterEntry>::Insert(CWriterEntry *,CWriterEntry * *)
0x18000ba68  mov     [rsp+120h+var_F0], eax
0x18000ba6c  test    eax, eax
0x18000ba6e  mov     eax, 2B61h
0x18000ba73  js      loc_18000B99E
0x18000ba79  inc     edi
0x18000ba7b  jmp     short loc_18000BA0A
0x18000ba7d  mov     rcx, r12
0x18000ba80  shl     rcx, 4; cb
0x18000ba84  call    cs:__imp_CoTaskMemAlloc
0x18000ba8a  mov     [rbp+3Fh+pv], rax
0x18000ba8e  mov     ecx, 2B67h
0x18000ba93  test    rax, rax
0x18000ba96  jnz     short loc_18000BAAA
0x18000ba98  mov     [rsp+120h+var_F0], 8007000Eh
0x18000baa0  mov     [rsp+120h+var_EA], cx
0x18000baa5  jmp     loc_18000B9A3
0x18000baaa  xor     edx, edx
0x18000baac  mov     [rsp+120h+var_F0], esi
0x18000bab0  mov     [rsp+120h+var_EC], cx
0x18000bab5  mov     rdi, rax
0x18000bab8  test    r12d, r12d
0x18000babb  jz      short loc_18000BADE
0x18000babd  mov     r8, [rbp+3Fh+arg_10]
0x18000bac1  lea     rax, [rdx+rdx*2]
0x18000bac5  mov     ecx, edx
0x18000bac7  add     rax, rax
0x18000baca  add     rcx, rcx
0x18000bacd  inc     edx
0x18000bacf  movups  xmm0, xmmword ptr [r8+rax*8]
0x18000bad4  movdqu  xmmword ptr [rdi+rcx*8], xmm0
0x18000bad9  cmp     edx, r12d
0x18000badc  jb      short loc_18000BAC1
0x18000bade  lea     rcx, [rbp+3Fh+var_98]
0x18000bae2  call    cs:__imp_CreateVssBackupComponentsInternal
0x18000bae8  mov     [rsp+120h+var_F0], eax
0x18000baec  test    eax, eax
0x18000baee  mov     eax, 2B72h
0x18000baf3  js      loc_18000B99E
0x18000baf9  mov     rcx, [rbp+3Fh+var_98]
0x18000bafd  xor     edx, edx
0x18000baff  mov     [rsp+120h+var_EC], ax
0x18000bb04  mov     rax, [rcx]
0x18000bb07  mov     rax, [rax+28h]
0x18000bb0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb10  mov     [rsp+120h+var_F0], eax
0x18000bb14  test    eax, eax
0x18000bb16  mov     eax, 2B74h
0x18000bb1b  js      loc_18000B99E
0x18000bb21  lea     r8, [rbp+3Fh+var_48]; unsigned __int64 *
0x18000bb25  mov     [rsp+120h+var_EC], ax
0x18000bb2a  or      edx, 0FFFFFFFFh; unsigned int
0x18000bb2d  call    ?_InitTimer@CSpp@@AEAAJKPEA_K@Z; CSpp::_InitTimer(ulong,unsigned __int64 *)
0x18000bb32  mov     [rsp+120h+var_F0], eax
0x18000bb36  test    eax, eax
0x18000bb38  mov     eax, 2B76h
0x18000bb3d  js      loc_18000B99E
0x18000bb43  mov     rcx, [rbp+3Fh+var_98]
0x18000bb47  mov     r8d, r12d
0x18000bb4a  mov     [rsp+120h+var_EC], ax
0x18000bb4f  mov     rdx, rdi
0x18000bb52  mov     rax, [rcx]
0x18000bb55  mov     rax, [rax+170h]
0x18000bb5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb61  mov     [rsp+120h+var_F0], eax
0x18000bb65  test    eax, eax
0x18000bb67  mov     eax, 2B78h
0x18000bb6c  js      loc_18000B99E
0x18000bb72  lea     rcx, [rbp+3Fh+var_B8]; struct CSxVolumeInfoArray **
0x18000bb76  mov     [rsp+120h+var_EC], ax
0x18000bb7b  call    ?CreateInstance@CSxVolumeInfoArray@@SAJPEAPEAV1@@Z; CSxVolumeInfoArray::CreateInstance(CSxVolumeInfoArray * *)
0x18000bb80  mov     r13, [rbp+3Fh+var_B8]
0x18000bb84  test    eax, eax
0x18000bb86  mov     [rsp+120h+var_F0], eax
0x18000bb8a  mov     eax, 2B7Bh
0x18000bb8f  js      loc_18000B99E
0x18000bb95  mov     r9, [rbp+3Fh+var_48]; unsigned __int64
0x18000bb99  mov     r8, r13; struct CWriterEntryArray *
0x18000bb9c  mov     rdx, [rbp+3Fh+var_98]; struct IVssBackupComponents *
0x18000bba0  mov     rcx, r14; this
0x18000bba3  mov     [rsp+120h+var_EC], ax
0x18000bba8  call    ?_GatherWriterMetadata@CSpp@@AEAAJPEAVIVssBackupComponents@@PEAVCWriterEntryArray@@_K@Z; CSpp::_GatherWriterMetadata(IVssBackupComponents *,CWriterEntryArray *,unsigned __int64)
0x18000bbad  xor     r14d, r14d
0x18000bbb0  mov     [rsp+120h+var_F0], eax
0x18000bbb4  test    eax, eax
0x18000bbb6  mov     eax, 2B7Ch
0x18000bbbb  js      loc_18000B99E
0x18000bbc1  lea     rcx, [rsp+120h+var_100]; struct CVolumeEntryMap **
0x18000bbc6  mov     [rsp+120h+var_EC], ax
0x18000bbcb  call    ?CreateInstance@CVolumeEntryMap@@SAJPEAPEAV1@@Z; CVolumeEntryMap::CreateInstance(CVolumeEntryMap * *)
0x18000bbd0  mov     [rsp+120h+var_F0], eax
0x18000bbd4  test    eax, eax
0x18000bbd6  mov     eax, 2B81h
0x18000bbdb  js      loc_18000B99E
0x18000bbe1  mov     [rsp+120h+var_EC], ax
0x18000bbe6  mov     edi, r14d
0x18000bbe9  mov     eax, [r13+8]
0x18000bbed  mov     r10d, 2B87h
0x18000bbf3  mov     [rbp+3Fh+var_54], eax
0x18000bbf6  mov     [rbp+3Fh+var_9C], edi
0x18000bbf9  cmp     edi, eax
0x18000bbfb  jnb     loc_18000BF6B
0x18000bc01  test    rbx, rbx
0x18000bc04  jz      short loc_18000BC18
0x18000bc06  mov     rcx, rbx; this
0x18000bc09  mov     [rbp+3Fh+var_A8], r14
0x18000bc0d  call    ?Release@CWriterEntry@@QEAAKXZ; CWriterEntry::Release(void)
0x18000bc12  mov     r10d, 2B87h
0x18000bc18  lea     r8, [rbp+3Fh+var_A8]
0x18000bc1c  mov     edx, edi
0x18000bc1e  mov     rcx, r13
0x18000bc21  call    ?Get@?$CSxRefArray@VCWriterEntryArray@@VCWriterEntry@@@@QEAAJKPEAPEAVCWriterEntry@@@Z; CSxRefArray<CWriterEntryArray,CWriterEntry>::Get(ulong,CWriterEntry * *)
0x18000bc26  mov     rbx, [rbp+3Fh+var_A8]
0x18000bc2a  mov     [rsp+120h+var_F0], eax
0x18000bc2e  test    eax, eax
0x18000bc30  js      loc_18000BF60
0x18000bc36  mov     [rsp+120h+var_EC], r10w
0x18000bc3c  cmp     [rbx+50h], r14d
0x18000bc40  jnz     loc_18000BF10
0x18000bc46  mov     rcx, [rbp+3Fh+var_68]; this
0x18000bc4a  test    rcx, rcx
0x18000bc4d  jz      short loc_18000BC58
0x18000bc4f  mov     [rbp+3Fh+var_68], r14
0x18000bc53  call    ?Release@CWriterEntry@@QEAAKXZ; CWriterEntry::Release(void)
0x18000bc58  mov     rcx, [rbp+3Fh+var_60]
0x18000bc5c  lea     r8, [rbp+3Fh+var_68]
0x18000bc60  mov     rdx, rbx
0x18000bc63  call    ?Find@?$CSxRefMap@VCPathCache@@VCPathCacheNode@@@@QEAAJPEAVCPathCacheNode@@PEAPEAV2@@Z; CSxRefMap<CPathCache,CPathCacheNode>::Find(CPathCacheNode *,CPathCacheNode * *)
0x18000bc68  mov     [rsp+120h+var_F0], eax
0x18000bc6c  test    eax, eax
0x18000bc6e  js      loc_18000BF56
0x18000bc74  mov     ecx, 2B8Fh
0x18000bc79  mov     [rsp+120h+var_EC], cx
0x18000bc7e  jnz     loc_18000BF0A
0x18000bc84  mov     rax, [rbx+40h]
0x18000bc88  mov     r13d, r14d
0x18000bc8b  mov     eax, [rax+8]
0x18000bc8e  mov     [rbp+3Fh+var_58], eax
0x18000bc91  mov     [rbp+3Fh+var_A0], r13d
0x18000bc95  cmp     r13d, eax
0x18000bc98  jnb     loc_18000BF03
0x18000bc9e  test    r15, r15
0x18000bca1  jz      short loc_18000BCAF
0x18000bca3  mov     rcx, r15; this
0x18000bca6  mov     [rbp+3Fh+var_78], r14
0x18000bcaa  call    ?Release@CComponentEntry@@QEAAKXZ; CComponentEntry::Release(void)
0x18000bcaf  mov     rcx, [rbx+40h]
0x18000bcb3  lea     r8, [rbp+3Fh+var_78]
0x18000bcb7  mov     edx, r13d
0x18000bcba  call    ?Get@?$CSxRefArray@VCWriterEntryArray@@VCWriterEntry@@@@QEAAJKPEAPEAVCWriterEntry@@@Z; CSxRefArray<CWriterEntryArray,CWriterEntry>::Get(ulong,CWriterEntry * *)
0x18000bcbf  mov     r15, [rbp+3Fh+var_78]
0x18000bcc3  test    eax, eax
0x18000bcc5  mov     [rsp+120h+var_F0], eax
0x18000bcc9  mov     eax, 2B9Bh
0x18000bcce  js      loc_18000BF48
0x18000bcd4  mov     [rsp+120h+var_EC], ax
0x18000bcd9  mov     cl, r14b
0x18000bcdc  mov     byte ptr [rsp+120h+var_F8], cl
0x18000bce0  mov     r13d, r14d
0x18000bce3  mov     [rbp+3Fh+var_50], r15
0x18000bce7  test    r12d, r12d
0x18000bcea  jz      loc_18000BEF4
0x18000bcf0  mov     esi, [rbp+3Fh+arg_8]
0x18000bcf3  mov     r12, r14
0x18000bcf6  mov     rdx, [rbp+3Fh+arg_10]
0x18000bcfa  mov     rax, [rbx+20h]
0x18000bcfe  lea     rdi, [r12+r12*2]
0x18000bd02  shl     rdi, 4
0x18000bd06  sub     rax, [rdi+rdx]
0x18000bd0a  jnz     short loc_18000BD15
0x18000bd0c  mov     rax, [rbx+28h]
0x18000bd10  sub     rax, [rdi+rdx+8]
0x18000bd15  test    rax, rax
0x18000bd18  jnz     short loc_18000BD80
0x18000bd1a  cmp     r14d, [rdi+rdx+20h]
0x18000bd1f  jnb     short loc_18000BD79
0x18000bd21  mov     rdx, [rdi+rdx+28h]
0x18000bd26  mov     rcx, [rbp+3Fh+var_50]
0x18000bd2a  mov     r15d, r14d
0x18000bd2d  add     r15, r15
0x18000bd30  mov     rcx, [rcx+8]; String1
0x18000bd34  mov     rdx, [rdx+r15*8+8]; String2
0x18000bd39  call    ?SxStringCompare@@YAEPEBG0@Z; SxStringCompare(ushort const *,ushort const *)
0x18000bd3e  test    al, al
0x18000bd40  jz      short loc_18000BD6C
0x18000bd42  mov     rax, [rbp+3Fh+arg_10]
0x18000bd46  mov     rdx, [rdi+rax+28h]
0x18000bd4b  mov     rdx, [rdx+r15*8]; String2
0x18000bd4f  mov     r15, [rbp+3Fh+var_50]
0x18000bd53  mov     rcx, [r15+28h]; String1
0x18000bd57  call    ?SxStringCompare@@YAEPEBG0@Z; SxStringCompare(ushort const *,ushort const *)
0x18000bd5c  test    al, al
0x18000bd5e  jz      short loc_18000BD70
  ... truncated ...
```
