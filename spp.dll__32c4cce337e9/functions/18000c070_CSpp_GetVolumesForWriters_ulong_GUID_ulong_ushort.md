# CSpp::GetVolumesForWriters(ulong,_GUID *,ulong *,ushort * * *)

- ea: `0x18000c070`
- end: `0x18000c654`
- name: `?GetVolumesForWriters@CSpp@@UEAAJKPEAU_GUID@@PEAKPEAPEAPEAG@Z`
- size: `1508`
- prototype: `__int64 __fastcall(CSpp *this, unsigned int, struct _GUID *, unsigned int *, unsigned __int16 ***)`
- caller_count: `0`
- callee_count: `26`
- tags: `broker_com_uri`

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
- `0x18000c070`
- `0x18000c804`
- `0x18000c894`
- `0x18000cc50`
- `0x18000e080`
- `0x18000e308`
- `0x18000e48c`
- `0x18000e54c`
- `0x18000e58c`
- `0x18000e5cc`
- `0x180016e24`
- `0x180017960`
- `0x18001b1e0`
- `0x180020710`
- `0x1800268b4`
- `0x1800269ac`
- `0x180037010`

## import_xrefs

- `VSSAPI!CreateVssBackupComponentsInternal` at `0x18000c219`
- `VSSAPI!CreateVssBackupComponentsInternal` at `0x18000c219`

## string_xrefs

- `0x18000c0d4`: `CSpp::GetVolumesForWriters`

## pseudocode

```c
__int64 __fastcall CSpp::GetVolumesForWriters(
        CSpp *this,
        unsigned int a2,
        struct _GUID *a3,
        unsigned int *a4,
        unsigned __int16 ***a5)
{
  struct CSxVolumeInfoArray *v9; // rsi
  struct CWriterEntry *v10; // rdi
  CVolumeEntry *v11; // r12
  __int16 i; // ax
  int inited; // ebx
  CComponentEntry *v14; // r14
  CVolumeEntryMap *v15; // r15
  __int64 v16; // rdx
  int v17; // eax
  CWriterEntryMap *v18; // rcx
  struct CWriterEntry *v19; // rdx
  CSpp *v20; // rcx
  CSpp *v21; // rcx
  int v22; // eax
  unsigned int v23; // eax
  unsigned int v24; // r13d
  int v25; // eax
  __int16 v26; // r10
  CWriterEntry *v27; // rcx
  int v28; // eax
  int v29; // r15d
  unsigned int v30; // esi
  unsigned int v31; // eax
  int v32; // eax
  __int64 v33; // rax
  bool v34; // sf
  __int64 v35; // rdx
  __int64 v36; // r8
  CVolumeEntryMap *v38; // [rsp+20h] [rbp-91h] BYREF
  CComponentEntry *v39; // [rsp+28h] [rbp-89h]
  struct CSxVolumeInfoArray *v40; // [rsp+30h] [rbp-81h] BYREF
  int v41; // [rsp+38h] [rbp-79h] BYREF
  __int16 v42; // [rsp+3Ch] [rbp-75h]
  __int16 v43; // [rsp+3Eh] [rbp-73h]
  CVolumeEntry *v44; // [rsp+70h] [rbp-41h] BYREF
  struct CWriterEntry *v45; // [rsp+78h] [rbp-39h] BYREF
  struct IVssBackupComponents *v46; // [rsp+80h] [rbp-31h] BYREF
  int v47; // [rsp+88h] [rbp-29h] BYREF
  CVolumeEntryMap *v48[2]; // [rsp+90h] [rbp-21h]
  CComponentEntry *v49; // [rsp+A0h] [rbp-11h] BYREF
  CWriterEntry *v50; // [rsp+A8h] [rbp-9h] BYREF
  CWriterEntryMap *v51; // [rsp+B0h] [rbp-1h] BYREF
  unsigned int v52; // [rsp+B8h] [rbp+7h]
  unsigned __int64 v53[8]; // [rsp+C0h] [rbp+Fh] BYREF
  unsigned int v54; // [rsp+118h] [rbp+67h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 189, &WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v41, "CSpp::GetVolumesForWriters", 10924, 1);
  ATL::CComPtr<IVssBackupComponents>::CComPtr<IVssBackupComponents>(&v46);
  v9 = 0;
  v10 = 0;
  v39 = 0;
  v11 = 0;
  v49 = 0;
  v51 = 0;
  v38 = 0;
  v47 = 0;
  v50 = 0;
  i = 10942;
  v40 = 0;
  v53[0] = 0;
  v45 = 0;
  v44 = 0;
  *(_OWORD *)v48 = 0;
  if ( !a2 || (v42 = 10942, i = 10943, !a3) || (v42 = 10943, i = 10944, !a4) || (v42 = 10944, i = 10945, !a5) )
  {
    inited = -2147024809;
    v41 = -2147024809;
LABEL_6:
    v14 = 0;
    goto LABEL_7;
  }
  v41 = 0;
  v42 = 10945;
  *a4 = 0;
  *a5 = 0;
  inited = CWriterEntryMap::CreateInstance(&v51);
  v41 = inited;
  i = 10953;
  if ( inited < 0 )
    goto LABEL_6;
  while ( 1 )
  {
    v42 = i;
    if ( (unsigned int)v9 >= a2 )
      break;
    if ( v10 )
    {
      v45 = 0;
      CWriterEntry::Release(v10);
    }
    v17 = CWriterEntry::CreateInstance(&v45);
    v10 = v45;
    inited = v17;
    v41 = v17;
    v34 = v17 < 0;
    i = 10957;
    if ( v34 )
      goto LABEL_18;
    v18 = v51;
    v19 = v45;
    v42 = 10957;
    *((struct _GUID *)v45 + 2) = a3[(unsigned int)v9];
    inited = CSxRefMap<CWriterEntryMap,CWriterEntry>::Insert(v18, v19);
    v41 = inited;
    i = 10960;
    if ( inited < 0 )
      goto LABEL_18;
    LODWORD(v9) = (_DWORD)v9 + 1;
  }
  inited = CreateVssBackupComponentsInternal(&v46, v16);
  v41 = inited;
  i = 10966;
  if ( inited < 0 )
    goto LABEL_18;
  v42 = 10966;
  inited = (*(__int64 (__fastcall **)(struct IVssBackupComponents *, _QWORD))(*(_QWORD *)v46 + 40LL))(v46, 0);
  v41 = inited;
  i = 10968;
  if ( inited < 0 )
    goto LABEL_18;
  v42 = 10968;
  inited = CSpp::_InitTimer(v20, 0xFFFFFFFFLL, v53);
  v41 = inited;
  i = 10970;
  if ( inited < 0
    || (v42 = 10970, inited = CSpp::_EnableInterestingWriters(v21, 0, v46), v41 = inited, i = 10972, inited < 0) )
  {
LABEL_18:
    v14 = 0;
    goto LABEL_19;
  }
  v42 = 10972;
  v22 = CSxVolumeInfoArray::CreateInstance(&v40);
  v9 = v40;
  inited = v22;
  v41 = v22;
  v34 = v22 < 0;
  i = 10975;
  if ( v34 )
    goto LABEL_25;
  v42 = 10975;
  inited = CSpp::_GatherWriterMetadata(this, v46, v40, v53[0]);
  v41 = inited;
  i = 10976;
  if ( inited < 0
    || (v42 = 10976, inited = CVolumeEntryMap::CreateInstance((LPVOID **)&v38), v41 = inited, i = 10981, inited < 0) )
  {
LABEL_25:
    v14 = 0;
    goto LABEL_7;
  }
  v42 = 10981;
  v23 = *((_DWORD *)v9 + 2);
  v24 = 0;
  v52 = v23;
  while ( 1 )
  {
    if ( v24 >= v23 )
    {
      v15 = v38;
      inited = CVolumeEntryMap::GetVolumeNameArray(v38, a4, a5);
      v41 = inited;
      if ( inited >= 0 )
        v42 = 11030;
      else
        v43 = 11030;
      goto LABEL_69;
    }
    if ( v10 )
    {
      v45 = 0;
      CWriterEntry::Release(v10);
    }
    v25 = CSxRefArray<CWriterEntryArray,CWriterEntry>::Get(v9, v24, &v45);
    v10 = v45;
    inited = v25;
    v41 = v25;
    if ( v25 < 0 )
    {
      v43 = v26;
LABEL_64:
      v15 = v38;
LABEL_69:
      v14 = v39;
      goto LABEL_70;
    }
    v42 = v26;
    if ( *((_DWORD *)v45 + 20) )
      goto LABEL_61;
    v27 = v50;
    if ( v50 )
    {
      v50 = 0;
      CWriterEntry::Release(v27);
    }
    v28 = CSxRefMap<CPathCache,CPathCacheNode>::Find(v51, v10, &v50);
    v41 = v28;
    inited = v28;
    if ( v28 < 0 )
    {
      v43 = 10995;
      goto LABEL_64;
    }
    v42 = 10995;
    if ( !v28 )
      break;
    v29 = 0;
    if ( *((_DWORD *)v10 + 19) )
      goto LABEL_40;
LABEL_61:
    v23 = v52;
    ++v24;
  }
  v29 = 1;
LABEL_40:
  v30 = 0;
  v14 = v39;
  v31 = *(_DWORD *)(*((_QWORD *)v10 + 8) + 8LL);
  v54 = v31;
  while ( 1 )
  {
    if ( v30 >= v31 )
    {
      v9 = v40;
      goto LABEL_61;
    }
    if ( v14 )
    {
      v49 = 0;
      CComponentEntry::Release(v14);
    }
    v32 = CSxRefArray<CWriterEntryArray,CWriterEntry>::Get(*((_QWORD *)v10 + 8), v30, &v49);
    v14 = v49;
    inited = v32;
    v41 = v32;
    v34 = v32 < 0;
    i = 11007;
    if ( v34 )
      goto LABEL_19;
    v42 = 11007;
    v39 = v49;
    if ( v29 || *((_DWORD *)v49 + 28) )
      break;
LABEL_59:
    v31 = v54;
    ++v30;
  }
  if ( v48[0] )
  {
    CVolumeEntryMap::Release(v48[0]);
    v48[0] = 0;
  }
  v47 = 0;
  v48[1] = 0;
  v33 = *((_QWORD *)v14 + 15);
  if ( v33 )
  {
    v48[0] = *((CVolumeEntryMap **)v14 + 15);
    _InterlockedIncrement((volatile signed __int32 *)(v33 + 16));
    v47 = *((_DWORD *)v48[0] + 2);
    v48[1] = 0;
    v41 = 0;
    v42 = 11016;
    if ( v11 )
    {
      v44 = 0;
      CVolumeEntry::Release(v11);
    }
    inited = CSxRefMap<CSxStringMap,CSxStringEntry>::CSxIter::Next(&v47, &v44);
    v41 = inited;
    v34 = inited < 0;
    for ( i = 11019; ; i = 11025 )
    {
      v11 = v44;
      if ( v34 )
        break;
      v42 = i;
      if ( inited == 1 )
        goto LABEL_59;
      inited = CSxRefMap<CVolumeOnDiskPropCacheMap,CVolumeOnDiskPropCacheEntry>::Insert(v38, v44, 0);
      v41 = inited;
      i = 11022;
      if ( inited < 0 )
        break;
      v42 = 11022;
      if ( v11 )
      {
        v44 = 0;
        CVolumeEntry::Release(v11);
      }
      inited = CSxRefMap<CSxStringMap,CSxStringEntry>::CSxIter::Next(&v47, &v44);
      v41 = inited;
      v34 = inited < 0;
    }
  }
  else
  {
    inited = -2147024809;
    v41 = -2147024809;
    i = 11016;
  }
LABEL_19:
  v9 = v40;
LABEL_7:
  v15 = v38;
  v43 = i;
LABEL_70:
  if ( v50 )
    CWriterEntry::Release(v50);
  if ( v48[0] )
  {
    CVolumeEntryMap::Release(v48[0]);
    v48[0] = 0;
  }
  v47 = 0;
  v48[1] = 0;
  if ( v15 )
    CVolumeEntryMap::Release(v15);
  if ( v51 )
    CWriterEntryMap::Release(v51);
  if ( v11 )
    CVolumeEntry::Release(v11);
  if ( v14 )
    CComponentEntry::Release(v14);
  if ( v10 )
    CWriterEntry::Release(v10);
  if ( v9 )
    CWriterEntryArray::Release(v9);
  ATL::CComPtr<IVssExamineWriterMetadata>::~CComPtr<IVssExamineWriterMetadata>();
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v41, v35, v36);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18000c070  mov     [rsp-8+arg_0], rbx
0x18000c075  mov     [rsp-8+arg_18], r9
0x18000c07a  push    rbp
0x18000c07b  push    rsi
0x18000c07c  push    rdi
0x18000c07d  push    r12
0x18000c07f  push    r13
0x18000c081  push    r14
0x18000c083  push    r15
0x18000c085  lea     rbp, [rsp-1Fh]
0x18000c08a  sub     rsp, 0D0h
0x18000c091  mov     rbx, r9
0x18000c094  mov     r15, r8
0x18000c097  mov     r14d, edx
0x18000c09a  mov     r13, rcx
0x18000c09d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c0a4  lea     rax, WPP_GLOBAL_Control
0x18000c0ab  cmp     rcx, rax
0x18000c0ae  jz      short loc_18000C0CE
0x18000c0b0  test    dword ptr [rcx+1Ch], 20000000h
0x18000c0b7  jz      short loc_18000C0CE
0x18000c0b9  mov     rcx, [rcx+10h]
0x18000c0bd  lea     r8, WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids
0x18000c0c4  mov     edx, 0BDh
0x18000c0c9  call    WPP_SF_
0x18000c0ce  mov     r9d, 1; unsigned __int16
0x18000c0d4  lea     rdx, aCsppGetvolumes; "CSpp::GetVolumesForWriters"
0x18000c0db  mov     r8d, 2AACh; unsigned __int16
0x18000c0e1  lea     rcx, [rbp+4Fh+var_C8]; this
0x18000c0e5  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18000c0ea  lea     rcx, [rbp+4Fh+var_80]
0x18000c0ee  call    ??0?$CComPtr@VIVssBackupComponents@@@ATL@@QEAA@H@Z; ATL::CComPtr<IVssBackupComponents>::CComPtr<IVssBackupComponents>(int)
0x18000c0f3  xor     eax, eax
0x18000c0f5  xor     esi, esi
0x18000c0f7  xor     edi, edi
0x18000c0f9  mov     [rsp+100h+var_D8], rax
0x18000c0fe  xor     r12d, r12d
0x18000c101  mov     [rbp+4Fh+var_60], rax
0x18000c105  mov     [rbp+4Fh+var_50], rax
0x18000c109  xorps   xmm0, xmm0
0x18000c10c  mov     [rsp+100h+var_E0], rax
0x18000c111  mov     [rbp+4Fh+var_78], eax
0x18000c114  mov     [rbp+4Fh+var_58], rax
0x18000c118  mov     eax, 2ABEh
0x18000c11d  mov     [rsp+100h+var_D0], rsi
0x18000c122  mov     [rbp+4Fh+var_40], rsi
0x18000c126  mov     [rbp+4Fh+var_88], rdi
0x18000c12a  mov     [rbp+4Fh+var_90], r12
0x18000c12e  movdqu  xmmword ptr [rbp+4Fh+var_70], xmm0
0x18000c133  test    r14d, r14d
0x18000c136  jnz     short loc_18000C151
0x18000c138  mov     ebx, 80070057h
0x18000c13d  mov     [rbp+4Fh+var_C8], ebx
0x18000c140  mov     r14, rsi
0x18000c143  mov     r15, [rsp+100h+var_E0]
0x18000c148  mov     [rbp+4Fh+var_C2], ax
0x18000c14c  jmp     loc_18000C5A0
0x18000c151  mov     [rbp+4Fh+var_C4], ax
0x18000c155  mov     eax, 2ABFh
0x18000c15a  test    r15, r15
0x18000c15d  jz      short loc_18000C138
0x18000c15f  mov     [rbp+4Fh+var_C4], ax
0x18000c163  mov     eax, 2AC0h
0x18000c168  test    rbx, rbx
0x18000c16b  jz      short loc_18000C138
0x18000c16d  mov     rcx, [rbp+4Fh+arg_20]
0x18000c171  mov     [rbp+4Fh+var_C4], ax
0x18000c175  mov     eax, 2AC1h
0x18000c17a  test    rcx, rcx
0x18000c17d  jz      short loc_18000C138
0x18000c17f  mov     [rbp+4Fh+var_C8], esi
0x18000c182  mov     [rbp+4Fh+var_C4], ax
0x18000c186  mov     [rbx], esi
0x18000c188  mov     [rcx], rsi
0x18000c18b  lea     rcx, [rbp+4Fh+var_50]; struct CWriterEntryMap **
0x18000c18f  call    ?CreateInstance@CWriterEntryMap@@SAJPEAPEAV1@@Z; CWriterEntryMap::CreateInstance(CWriterEntryMap * *)
0x18000c194  mov     ebx, eax
0x18000c196  mov     [rbp+4Fh+var_C8], eax
0x18000c199  test    eax, eax
0x18000c19b  mov     eax, 2AC9h
0x18000c1a0  js      short loc_18000C140
0x18000c1a2  mov     [rbp+4Fh+var_C4], ax
0x18000c1a6  cmp     esi, r14d
0x18000c1a9  jnb     short loc_18000C215
0x18000c1ab  test    rdi, rdi
0x18000c1ae  jz      short loc_18000C1BC
0x18000c1b0  mov     rcx, rdi; this
0x18000c1b3  mov     [rbp+4Fh+var_88], r12
0x18000c1b7  call    ?Release@CWriterEntry@@QEAAKXZ; CWriterEntry::Release(void)
0x18000c1bc  lea     rcx, [rbp+4Fh+var_88]; struct CWriterEntry **
0x18000c1c0  call    ?CreateInstance@CWriterEntry@@SAJPEAPEAV1@@Z; CWriterEntry::CreateInstance(CWriterEntry * *)
0x18000c1c5  mov     rdi, [rbp+4Fh+var_88]
0x18000c1c9  mov     ebx, eax
0x18000c1cb  mov     [rbp+4Fh+var_C8], eax
0x18000c1ce  test    eax, eax
0x18000c1d0  mov     eax, 2ACDh
0x18000c1d5  js      short loc_18000C208
0x18000c1d7  mov     rcx, [rbp+4Fh+var_50]
0x18000c1db  mov     rdx, rdi
0x18000c1de  mov     [rbp+4Fh+var_C4], ax
0x18000c1e2  mov     eax, esi
0x18000c1e4  add     rax, rax
0x18000c1e7  movups  xmm0, xmmword ptr [r15+rax*8]
0x18000c1ec  movdqu  xmmword ptr [rdi+20h], xmm0
0x18000c1f1  call    ?Insert@?$CSxRefMap@VCWriterEntryMap@@VCWriterEntry@@@@QEAAJPEAVCWriterEntry@@PEAPEAV2@@Z; CSxRefMap<CWriterEntryMap,CWriterEntry>::Insert(CWriterEntry *,CWriterEntry * *)
0x18000c1f6  mov     ebx, eax
0x18000c1f8  mov     [rbp+4Fh+var_C8], eax
0x18000c1fb  test    eax, eax
0x18000c1fd  mov     eax, 2AD0h
0x18000c202  js      short loc_18000C208
0x18000c204  inc     esi
0x18000c206  jmp     short loc_18000C1A2
0x18000c208  mov     r14, r12
0x18000c20b  mov     rsi, [rsp+100h+var_D0]
0x18000c210  jmp     loc_18000C143
0x18000c215  lea     rcx, [rbp+4Fh+var_80]
0x18000c219  call    cs:__imp_CreateVssBackupComponentsInternal
0x18000c21f  mov     ebx, eax
0x18000c221  mov     [rbp+4Fh+var_C8], eax
0x18000c224  test    eax, eax
0x18000c226  mov     eax, 2AD6h
0x18000c22b  js      short loc_18000C208
0x18000c22d  mov     rcx, [rbp+4Fh+var_80]
0x18000c231  xor     edx, edx
0x18000c233  mov     [rbp+4Fh+var_C4], ax
0x18000c237  mov     rax, [rcx]
0x18000c23a  mov     rax, [rax+28h]
0x18000c23e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c243  mov     ebx, eax
0x18000c245  mov     [rbp+4Fh+var_C8], eax
0x18000c248  test    eax, eax
0x18000c24a  mov     eax, 2AD8h
0x18000c24f  js      short loc_18000C208
0x18000c251  lea     r8, [rbp+4Fh+var_40]; unsigned __int64 *
0x18000c255  mov     [rbp+4Fh+var_C4], ax
0x18000c259  or      edx, 0FFFFFFFFh; unsigned int
0x18000c25c  call    ?_InitTimer@CSpp@@AEAAJKPEA_K@Z; CSpp::_InitTimer(ulong,unsigned __int64 *)
0x18000c261  mov     ebx, eax
0x18000c263  mov     [rbp+4Fh+var_C8], eax
0x18000c266  test    eax, eax
0x18000c268  mov     eax, 2ADAh
0x18000c26d  js      short loc_18000C208
0x18000c26f  mov     r8, [rbp+4Fh+var_80]; struct IVssBackupComponents *
0x18000c273  xor     edx, edx; int
0x18000c275  mov     [rbp+4Fh+var_C4], ax
0x18000c279  call    ?_EnableInterestingWriters@CSpp@@AEAAJHPEAVIVssBackupComponents@@@Z; CSpp::_EnableInterestingWriters(int,IVssBackupComponents *)
0x18000c27e  mov     ebx, eax
0x18000c280  mov     [rbp+4Fh+var_C8], eax
0x18000c283  test    eax, eax
0x18000c285  mov     eax, 2ADCh
0x18000c28a  js      loc_18000C208
0x18000c290  lea     rcx, [rsp+100h+var_D0]; struct CSxVolumeInfoArray **
0x18000c295  mov     [rbp+4Fh+var_C4], ax
0x18000c299  call    ?CreateInstance@CSxVolumeInfoArray@@SAJPEAPEAV1@@Z; CSxVolumeInfoArray::CreateInstance(CSxVolumeInfoArray * *)
0x18000c29e  mov     rsi, [rsp+100h+var_D0]
0x18000c2a3  mov     ebx, eax
0x18000c2a5  mov     [rbp+4Fh+var_C8], eax
0x18000c2a8  test    eax, eax
0x18000c2aa  mov     eax, 2ADFh
0x18000c2af  jns     short loc_18000C2B9
0x18000c2b1  mov     r14, r12
0x18000c2b4  jmp     loc_18000C143
0x18000c2b9  mov     r9, [rbp+4Fh+var_40]; unsigned __int64
0x18000c2bd  mov     r8, rsi; struct CWriterEntryArray *
0x18000c2c0  mov     rdx, [rbp+4Fh+var_80]; struct IVssBackupComponents *
0x18000c2c4  mov     rcx, r13; this
0x18000c2c7  mov     [rbp+4Fh+var_C4], ax
0x18000c2cb  call    ?_GatherWriterMetadata@CSpp@@AEAAJPEAVIVssBackupComponents@@PEAVCWriterEntryArray@@_K@Z; CSpp::_GatherWriterMetadata(IVssBackupComponents *,CWriterEntryArray *,unsigned __int64)
0x18000c2d0  mov     ebx, eax
0x18000c2d2  mov     [rbp+4Fh+var_C8], eax
0x18000c2d5  test    eax, eax
0x18000c2d7  mov     eax, 2AE0h
0x18000c2dc  js      short loc_18000C2B1
0x18000c2de  lea     rcx, [rsp+100h+var_E0]; struct CVolumeEntryMap **
0x18000c2e3  mov     [rbp+4Fh+var_C4], ax
0x18000c2e7  call    ?CreateInstance@CVolumeEntryMap@@SAJPEAPEAV1@@Z; CVolumeEntryMap::CreateInstance(CVolumeEntryMap * *)
0x18000c2ec  mov     ebx, eax
0x18000c2ee  mov     [rbp+4Fh+var_C8], eax
0x18000c2f1  test    eax, eax
0x18000c2f3  mov     eax, 2AE5h
0x18000c2f8  js      short loc_18000C2B1
0x18000c2fa  mov     r10d, 2AEBh
0x18000c300  mov     [rbp+4Fh+var_C4], ax
0x18000c304  mov     eax, [rsi+8]
0x18000c307  xor     r13d, r13d
0x18000c30a  mov     [rbp+4Fh+var_48], eax
0x18000c30d  lea     r14d, [r10+8]
0x18000c311  cmp     r13d, eax
0x18000c314  jnb     loc_18000C56E
0x18000c31a  test    rdi, rdi
0x18000c31d  jz      short loc_18000C335
0x18000c31f  mov     rcx, rdi; this
0x18000c322  mov     [rbp+4Fh+var_88], 0
0x18000c32a  call    ?Release@CWriterEntry@@QEAAKXZ; CWriterEntry::Release(void)
0x18000c32f  mov     r10d, 2AEBh
0x18000c335  lea     r8, [rbp+4Fh+var_88]
0x18000c339  mov     edx, r13d
0x18000c33c  mov     rcx, rsi
0x18000c33f  call    ?Get@?$CSxRefArray@VCWriterEntryArray@@VCWriterEntry@@@@QEAAJKPEAPEAVCWriterEntry@@@Z; CSxRefArray<CWriterEntryArray,CWriterEntry>::Get(ulong,CWriterEntry * *)
0x18000c344  mov     rdi, [rbp+4Fh+var_88]
0x18000c348  mov     ebx, eax
0x18000c34a  mov     [rbp+4Fh+var_C8], eax
0x18000c34d  test    eax, eax
0x18000c34f  js      loc_18000C567
0x18000c355  mov     [rbp+4Fh+var_C4], r10w
0x18000c35a  cmp     dword ptr [rdi+50h], 0
0x18000c35e  jnz     loc_18000C537
0x18000c364  mov     rcx, [rbp+4Fh+var_58]; this
0x18000c368  test    rcx, rcx
0x18000c36b  jz      short loc_18000C37A
0x18000c36d  mov     [rbp+4Fh+var_58], 0
0x18000c375  call    ?Release@CWriterEntry@@QEAAKXZ; CWriterEntry::Release(void)
0x18000c37a  mov     rcx, [rbp+4Fh+var_50]
0x18000c37e  lea     r8, [rbp+4Fh+var_58]
0x18000c382  mov     rdx, rdi
0x18000c385  call    ?Find@?$CSxRefMap@VCPathCache@@VCPathCacheNode@@@@QEAAJPEAVCPathCacheNode@@PEAPEAV2@@Z; CSxRefMap<CPathCache,CPathCacheNode>::Find(CPathCacheNode *,CPathCacheNode * *)
0x18000c38a  mov     [rbp+4Fh+var_C8], eax
0x18000c38d  mov     ebx, eax
0x18000c38f  test    eax, eax
0x18000c391  js      loc_18000C55B
0x18000c397  mov     [rbp+4Fh+var_C4], r14w
0x18000c39c  jnz     short loc_18000C3A6
0x18000c39e  mov     r15d, 1
0x18000c3a4  jmp     short loc_18000C3B3
0x18000c3a6  xor     r15d, r15d
0x18000c3a9  cmp     [rdi+4Ch], r15d
0x18000c3ad  jz      loc_18000C531
0x18000c3b3  mov     rax, [rdi+40h]
0x18000c3b7  xor     esi, esi
0x18000c3b9  mov     r14, [rsp+100h+var_D8]
0x18000c3be  mov     eax, [rax+8]
0x18000c3c1  mov     [rbp+4Fh+arg_8], eax
0x18000c3c4  cmp     esi, eax
0x18000c3c6  jnb     loc_18000C526
0x18000c3cc  test    r14, r14
0x18000c3cf  jz      short loc_18000C3E1
0x18000c3d1  mov     rcx, r14; this
0x18000c3d4  mov     [rbp+4Fh+var_60], 0
0x18000c3dc  call    ?Release@CComponentEntry@@QEAAKXZ; CComponentEntry::Release(void)
0x18000c3e1  mov     rcx, [rdi+40h]
0x18000c3e5  lea     r8, [rbp+4Fh+var_60]
0x18000c3e9  mov     edx, esi
0x18000c3eb  call    ?Get@?$CSxRefArray@VCWriterEntryArray@@VCWriterEntry@@@@QEAAJKPEAPEAVCWriterEntry@@@Z; CSxRefArray<CWriterEntryArray,CWriterEntry>::Get(ulong,CWriterEntry * *)
0x18000c3f0  mov     r14, [rbp+4Fh+var_60]
0x18000c3f4  mov     ebx, eax
0x18000c3f6  mov     [rbp+4Fh+var_C8], eax
0x18000c3f9  test    eax, eax
0x18000c3fb  mov     eax, 2AFFh
0x18000c400  js      loc_18000C20B
0x18000c406  mov     [rbp+4Fh+var_C4], ax
0x18000c40a  mov     [rsp+100h+var_D8], r14
0x18000c40f  test    r15d, r15d
0x18000c412  jnz     short loc_18000C41E
0x18000c414  cmp     [r14+70h], r15d
0x18000c418  jz      loc_18000C51C
0x18000c41e  mov     rcx, [rbp+4Fh+var_70]; this
0x18000c422  test    rcx, rcx
0x18000c425  jz      short loc_18000C434
0x18000c427  call    ?Release@CVolumeEntryMap@@QEAAKXZ; CVolumeEntryMap::Release(void)
0x18000c42c  mov     [rbp+4Fh+var_70], 0
0x18000c434  mov     [rbp+4Fh+var_78], 0
0x18000c43b  mov     [rbp+4Fh+var_70+8], 0
0x18000c443  mov     rax, [r14+78h]
0x18000c447  test    rax, rax
0x18000c44a  jz      loc_18000C549
0x18000c450  cmp     [rbp+4Fh+var_70], 0
0x18000c455  jnz     loc_18000C542
0x18000c45b  mov     [rbp+4Fh+var_70], rax
0x18000c45f  lock inc dword ptr [rax+10h]
0x18000c463  mov     rax, [rbp+4Fh+var_70]
0x18000c467  mov     ecx, [rax+8]
0x18000c46a  mov     [rbp+4Fh+var_78], ecx
0x18000c46d  mov     [rbp+4Fh+var_70+8], 0
0x18000c475  mov     [rbp+4Fh+var_C8], 0
0x18000c47c  mov     eax, 2B08h
0x18000c481  mov     [rbp+4Fh+var_C4], ax
0x18000c485  test    r12, r12
0x18000c488  jz      short loc_18000C49A
0x18000c48a  mov     rcx, r12; this
0x18000c48d  mov     [rbp+4Fh+var_90], 0
0x18000c495  call    ?Release@CVolumeEntry@@QEAAKXZ; CVolumeEntry::Release(void)
0x18000c49a  lea     rdx, [rbp+4Fh+var_90]
0x18000c49e  lea     rcx, [rbp+4Fh+var_78]
0x18000c4a2  call    ?Next@CSxIter@?$CSxRefMap@VCSxStringMap@@VCSxStringEntry@@@@QEAAJPEAPEAVCSxStringEntry@@@Z; CSxRefMap<CSxStringMap,CSxStringEntry>::CSxIter::Next(CSxStringEntry * *)
0x18000c4a7  mov     ebx, eax
0x18000c4a9  mov     [rbp+4Fh+var_C8], eax
0x18000c4ac  test    eax, eax
0x18000c4ae  mov     eax, 2B0Bh
0x18000c4b3  mov     r12, [rbp+4Fh+var_90]
0x18000c4b7  js      loc_18000C20B
0x18000c4bd  mov     [rbp+4Fh+var_C4], ax
0x18000c4c1  cmp     ebx, 1
0x18000c4c4  jz      short loc_18000C51C
0x18000c4c6  mov     rcx, [rsp+100h+var_E0]
0x18000c4cb  xor     r8d, r8d
0x18000c4ce  mov     rdx, r12
0x18000c4d1  call    ?Insert@?$CSxRefMap@VCVolumeOnDiskPropCacheMap@@VCVolumeOnDiskPropCacheEntry@@@@QEAAJPEAVCVolumeOnDiskPropCacheEntry@@PEAPEAV2@@Z; CSxRefMap<CVolumeOnDiskPropCacheMap,CVolumeOnDiskPropCacheEntry>::Insert(CVolumeOnDiskPropCacheEntry *,CVolumeOnDiskPropCacheEntry * *)
0x18000c4d6  mov     ebx, eax
0x18000c4d8  mov     [rbp+4Fh+var_C8], eax
0x18000c4db  test    eax, eax
  ... truncated ...
```
