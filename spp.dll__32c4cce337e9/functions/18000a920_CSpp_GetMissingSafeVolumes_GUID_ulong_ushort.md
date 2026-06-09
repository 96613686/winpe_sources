# CSpp::GetMissingSafeVolumes(_GUID,ulong *,ushort * * *)

- ea: `0x18000a920`
- end: `0x18000b0c8`
- name: `?GetMissingSafeVolumes@CSpp@@UEAAJU_GUID@@PEAKPEAPEAPEAG@Z`
- size: `1960`
- prototype: `__int64 __fastcall(CSpp *__hidden this, struct _GUID *__struct_ptr, unsigned int *, unsigned __int16 ***)`
- caller_count: `0`
- callee_count: `21`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800021f8`
- `0x18000232c`
- `0x180007650`
- `0x18000a920`
- `0x18000b5f4`
- `0x18000c804`
- `0x18000cc50`
- `0x18000dce0`
- `0x18000e308`
- `0x18000e48c`
- `0x180011558`
- `0x180016e24`
- `0x180017dfc`
- `0x180018328`
- `0x18001b1e0`
- `0x1800211a4`
- `0x1800268b4`
- `0x1800269ac`
- `0x180035b76`
- `0x180035bd0`
- `0x180037010`

## import_xrefs

- `ntdll!RtlNumberGenericTableElementsAvl` at `0x18000ac39`
- `ntdll!RtlNumberGenericTableElementsAvl` at `0x18000afa3`
- `ntdll!RtlNumberGenericTableElementsAvl` at `0x18000ac39`
- `ntdll!RtlNumberGenericTableElementsAvl` at `0x18000afa3`
- `VSSAPI!CreateVssBackupComponentsInternal` at `0x18000aabd`
- `VSSAPI!CreateVssBackupComponentsInternal` at `0x18000aabd`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ad7e`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b065`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ad7e`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b065`

## pseudocode

```c
__int64 __fastcall CSpp::GetMissingSafeVolumes(CSpp *this, struct _GUID *a2, unsigned int *a3, unsigned __int16 ***a4)
{
  struct CVolumeEntryMap *v8; // r12
  unsigned __int64 v9; // rdx
  OLECHAR *v10; // rdx
  volatile signed __int32 *v11; // r14
  CVolumeEntryMap *v12; // rsi
  __int16 k; // ax
  int inited; // ebx
  int Instance; // eax
  struct _GUID v16; // xmm0
  __int64 v17; // rdx
  CSpp *v18; // rcx
  CSpp *v19; // rcx
  CSpp *v20; // rcx
  int v21; // eax
  CVolumeEntry *v22; // rcx
  CVolumeEntry *v23; // rdi
  unsigned int i; // r13d
  unsigned int j; // r15d
  CVolumeEntry *v26; // rcx
  bool v27; // sf
  CVolumeEntry *v28; // rdi
  ULONG v29; // eax
  __int64 v30; // rdx
  __int64 v31; // r8
  CVolumeEntry *v33; // [rsp+40h] [rbp-C0h] BYREF
  int ClientVolumes; // [rsp+48h] [rbp-B8h] BYREF
  __int16 v35; // [rsp+4Ch] [rbp-B4h]
  __int16 v36; // [rsp+4Eh] [rbp-B2h]
  int v37; // [rsp+80h] [rbp-80h] BYREF
  CVolumeEntryMap *v38[2]; // [rsp+88h] [rbp-78h]
  struct IVssBackupComponents *v39; // [rsp+98h] [rbp-68h] BYREF
  CVolumeEntryMap *v40; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v41; // [rsp+A8h] [rbp-58h] BYREF
  unsigned int v42; // [rsp+B0h] [rbp-50h] BYREF
  unsigned int v43; // [rsp+B4h] [rbp-4Ch] BYREF
  int v44; // [rsp+B8h] [rbp-48h] BYREF
  BSTR bstrString; // [rsp+C0h] [rbp-40h] BYREF
  struct IVssWMComponent *v46; // [rsp+C8h] [rbp-38h] BYREF
  struct IVssAsync *v47; // [rsp+D0h] [rbp-30h] BYREF
  int v48; // [rsp+D8h] [rbp-28h] BYREF
  int v49; // [rsp+DCh] [rbp-24h] BYREF
  int v50; // [rsp+E0h] [rbp-20h] BYREF
  int v51; // [rsp+E4h] [rbp-1Ch] BYREF
  CVolumeEntryMap *v52; // [rsp+E8h] [rbp-18h] BYREF
  CVolumeEntryMap *v53; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int64 v54; // [rsp+F8h] [rbp-8h] BYREF
  CSpp *v55; // [rsp+100h] [rbp+0h]
  unsigned __int16 ***v56; // [rsp+108h] [rbp+8h]
  unsigned int *v57; // [rsp+110h] [rbp+10h]
  struct _GUID v58; // [rsp+120h] [rbp+20h] BYREF
  GUID Buf1; // [rsp+130h] [rbp+30h] BYREF
  GUID v60; // [rsp+140h] [rbp+40h] BYREF
  GUID v61; // [rsp+150h] [rbp+50h] BYREF

  v56 = a4;
  v57 = a3;
  v55 = this;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF__guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 185, a3, a2);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&ClientVolumes, "CSpp::GetMissingSafeVolumes", 10583, 1);
  v8 = 0;
  v52 = 0;
  ATL::CComPtr<IVssBackupComponents>::CComPtr<IVssBackupComponents>(&v39);
  ATL::CComPtr<IVssBackupComponents>::CComPtr<IVssBackupComponents>(&v47);
  v54 = v9;
  v42 = v9;
  ATL::CComPtr<IVssBackupComponents>::CComPtr<IVssBackupComponents>(&v41);
  ATL::CComPtr<IVssBackupComponents>::CComPtr<IVssBackupComponents>(&v46);
  bstrString = v10;
  v11 = (volatile signed __int32 *)(unsigned int)v10;
  v49 = (int)v10;
  v12 = (CVolumeEntryMap *)(unsigned int)v10;
  v48 = (int)v10;
  v51 = (int)v10;
  v50 = (int)v10;
  v43 = (unsigned int)v10;
  v44 = (int)v10;
  v40 = (CVolumeEntryMap *)v10;
  v53 = (CVolumeEntryMap *)v10;
  v37 = (int)v10;
  v33 = (CVolumeEntry *)v10;
  v60 = GUID_NULL;
  v61 = GUID_NULL;
  Buf1 = GUID_NULL;
  *(_OWORD *)v38 = 0;
  if ( a3 )
    *a3 = (unsigned int)v10;
  if ( a4 )
    *a4 = (unsigned __int16 **)v10;
  k = 10613;
  if ( !a3 || (v35 = 10613, k = 10614, !a4) )
  {
    inited = -2147024809;
    ClientVolumes = -2147024809;
    goto LABEL_72;
  }
  ClientVolumes = (int)v10;
  v35 = 10614;
  Instance = CVolumeEntryMap::CreateInstance((LPVOID **)&v52);
  v8 = v52;
  inited = Instance;
  ClientVolumes = Instance;
  v27 = Instance < 0;
  k = 10619;
  if ( v27 )
    goto LABEL_72;
  v16 = *a2;
  v35 = 10619;
  v58 = v16;
  ClientVolumes = CSpp::_GetClientVolumes(this, &v58, v52);
  inited = ClientVolumes;
  k = 10620;
  if ( ClientVolumes < 0 )
    goto LABEL_72;
  v35 = 10620;
  inited = CreateVssBackupComponentsInternal(&v39, v17);
  ClientVolumes = inited;
  k = 10626;
  if ( inited < 0 )
    goto LABEL_72;
  v35 = 10626;
  inited = (*(__int64 (__fastcall **)(struct IVssBackupComponents *, _QWORD))(*(_QWORD *)v39 + 40LL))(v39, 0);
  ClientVolumes = inited;
  k = 10628;
  if ( inited < 0 )
    goto LABEL_72;
  v35 = 10628;
  inited = CSpp::_InitTimer(v18, 0xFFFFFFFFLL, &v54);
  ClientVolumes = inited;
  k = 10630;
  if ( inited < 0 )
    goto LABEL_72;
  v35 = 10630;
  inited = CSpp::_EnableInterestingWriters(v19, 0, v39);
  ClientVolumes = inited;
  k = 10632;
  if ( inited < 0 )
    goto LABEL_72;
  v35 = 10632;
  ATL::CComPtrBase<IVssWMComponent>::Release(&v47);
  inited = (*(__int64 (__fastcall **)(struct IVssBackupComponents *, struct IVssAsync **))(*(_QWORD *)v39 + 72LL))(
             v39,
             &v47);
  ClientVolumes = inited;
  k = 10635;
  if ( inited < 0 )
    goto LABEL_72;
  v35 = 10635;
  inited = CSpp::_AsyncWaitWithTimeout(v20, v47, 0xFFFFFFFF, v54);
  ClientVolumes = inited;
  k = 10638;
  if ( inited < 0 )
    goto LABEL_72;
  v35 = 10638;
  inited = (*(__int64 (__fastcall **)(struct IVssBackupComponents *, unsigned int *))(*(_QWORD *)v39 + 80LL))(v39, &v42);
  ClientVolumes = inited;
  k = 10640;
  if ( inited < 0 )
    goto LABEL_72;
  v35 = 10640;
  inited = CVolumeEntryMap::CreateInstance((LPVOID **)&v40);
  ClientVolumes = inited;
  k = 10642;
  if ( inited < 0 )
  {
    v11 = (volatile signed __int32 *)v40;
LABEL_72:
    v36 = k;
    goto LABEL_73;
  }
  v35 = 10642;
  v21 = CVolumeEntryMap::CreateInstance((LPVOID **)&v53);
  v11 = (volatile signed __int32 *)v40;
  inited = v21;
  v12 = v53;
  v27 = v21 < 0;
  ClientVolumes = v21;
  k = 10643;
  if ( v27 )
    goto LABEL_72;
  v35 = 10643;
  do
  {
    LODWORD(v40) = RtlNumberGenericTableElementsAvl(*(PRTL_AVL_TABLE *)v12);
    if ( v38[0] )
    {
      CVolumeEntryMap::Release(v38[0]);
      v38[0] = 0;
    }
    v37 = 0;
    v38[1] = 0;
    if ( !v12 )
    {
      inited = -2147024809;
      k = 10661;
LABEL_71:
      ClientVolumes = -2147024809;
      goto LABEL_72;
    }
    v38[0] = v12;
    _InterlockedIncrement((volatile signed __int32 *)v12 + 4);
    v37 = *((_DWORD *)v38[0] + 2);
    v38[1] = 0;
    v22 = v33;
    ClientVolumes = 0;
    v35 = 10661;
    if ( v33 )
    {
      v33 = 0;
      CVolumeEntry::Release(v22);
    }
    ClientVolumes = CSxRefMap<CSxStringMap,CSxStringEntry>::CSxIter::Next(&v37, &v33);
    inited = ClientVolumes;
    if ( ClientVolumes < 0 )
    {
      v36 = 10664;
      goto LABEL_73;
    }
    v35 = 10664;
    while ( inited != 1 )
    {
      v23 = v33;
      ClientVolumes = CSxRefMap<CVolumeOnDiskPropCacheMap,CVolumeOnDiskPropCacheEntry>::Insert(v8, v33, 0);
      inited = ClientVolumes;
      if ( ClientVolumes < 0 )
      {
        v36 = 10667;
        goto LABEL_73;
      }
      v35 = 10667;
      if ( v23 )
      {
        v33 = 0;
        CVolumeEntry::Release(v23);
      }
      ClientVolumes = CSxRefMap<CSxStringMap,CSxStringEntry>::CSxIter::Next(&v37, &v33);
      inited = ClientVolumes;
      if ( ClientVolumes < 0 )
      {
        v36 = 10670;
        goto LABEL_73;
      }
      v35 = 10670;
    }
    for ( i = 0; i < v42; ++i )
    {
      ATL::CComPtrBase<IVssWMComponent>::Release(&v41);
      inited = (*(__int64 (__fastcall **)(struct IVssBackupComponents *, _QWORD, GUID *, __int64 *))(*(_QWORD *)v39 + 88LL))(
                 v39,
                 i,
                 &v60,
                 &v41);
      ClientVolumes = inited;
      k = 10682;
      if ( inited < 0 )
        goto LABEL_72;
      v35 = 10682;
      SysFreeString(bstrString);
      bstrString = 0;
      inited = (*(__int64 (__fastcall **)(__int64, GUID *, GUID *, BSTR *, int *, int *))(*(_QWORD *)v41 + 24LL))(
                 v41,
                 &v61,
                 &Buf1,
                 &bstrString,
                 &v49,
                 &v48);
      ClientVolumes = inited;
      k = 10693;
      if ( inited < 0 )
        goto LABEL_72;
      v35 = 10693;
      if ( memcmp_0(&Buf1, &unk_18003B650, 0x10u) )
      {
        inited = (*(__int64 (__fastcall **)(__int64, int *, int *, unsigned int *))(*(_QWORD *)v41 + 32LL))(
                   v41,
                   &v51,
                   &v50,
                   &v43);
        ClientVolumes = inited;
        k = 10708;
        if ( inited < 0 )
          goto LABEL_72;
        v35 = 10708;
        for ( j = 0; j < v43; ++j )
        {
          ATL::CComPtrBase<IVssWMComponent>::Release(&v46);
          inited = (*(__int64 (__fastcall **)(__int64, _QWORD, struct IVssWMComponent **))(*(_QWORD *)v41 + 56LL))(
                     v41,
                     j,
                     &v46);
          ClientVolumes = inited;
          k = 10713;
          if ( inited < 0 )
            goto LABEL_72;
          v35 = 10713;
          inited = CSpp::_GetComponentMissingVolumes(v55, v46, v8, &v44, (struct CVolumeEntryMap *)v11);
          ClientVolumes = inited;
          k = 10718;
          if ( inited < 0 )
            goto LABEL_72;
          v35 = 10718;
          if ( v44 == 1 )
          {
            if ( v38[0] )
            {
              CVolumeEntryMap::Release(v38[0]);
              v38[0] = 0;
            }
            v37 = 0;
            v38[1] = 0;
            if ( !v11 )
            {
              inited = -2147024809;
              k = 10728;
              goto LABEL_71;
            }
            v38[0] = (CVolumeEntryMap *)v11;
            _InterlockedIncrement(v11 + 4);
            v37 = *((_DWORD *)v38[0] + 2);
            v38[1] = 0;
            v26 = v33;
            ClientVolumes = 0;
            v35 = 10728;
            if ( v33 )
            {
              v33 = 0;
              CVolumeEntry::Release(v26);
            }
            inited = CSxRefMap<CSxStringMap,CSxStringEntry>::CSxIter::Next(&v37, &v33);
            ClientVolumes = inited;
            v27 = inited < 0;
            for ( k = 10731; !v27; k = 10738 )
            {
              v35 = k;
              if ( inited == 1 )
                goto LABEL_61;
              v28 = v33;
              inited = CSxRefMap<CVolumeOnDiskPropCacheMap,CVolumeOnDiskPropCacheEntry>::Insert(v12, v33, 0);
              ClientVolumes = inited;
              k = 10735;
              if ( inited < 0 )
                break;
              v35 = 10735;
              if ( v28 )
              {
                v33 = 0;
                CVolumeEntry::Release(v28);
              }
              ClientVolumes = CSxRefMap<CSxStringMap,CSxStringEntry>::CSxIter::Next(&v37, &v33);
              v27 = ClientVolumes < 0;
              inited = ClientVolumes;
            }
            goto LABEL_72;
          }
LABEL_61:
          ;
        }
      }
    }
    v29 = RtlNumberGenericTableElementsAvl(*(PRTL_AVL_TABLE *)v12);
  }
  while ( (_DWORD)v40 != v29 );
  inited = CVolumeEntryMap::GetVolumeNameArray(v12, v57, v56);
  ClientVolumes = inited;
  k = 10747;
  if ( inited < 0 )
    goto LABEL_72;
  v35 = 10747;
LABEL_73:
  if ( v33 )
    CVolumeEntry::Release(v33);
  if ( v38[0] )
  {
    CVolumeEntryMap::Release(v38[0]);
    v38[0] = 0;
  }
  v37 = 0;
  v38[1] = 0;
  if ( v12 )
    CVolumeEntryMap::Release(v12);
  if ( v11 )
    CVolumeEntryMap::Release((CVolumeEntryMap *)v11);
  SysFreeString(bstrString);
  ATL::CComPtr<IVssExamineWriterMetadata>::~CComPtr<IVssExamineWriterMetadata>();
  ATL::CComPtr<IVssExamineWriterMetadata>::~CComPtr<IVssExamineWriterMetadata>();
  ATL::CComPtr<IVssExamineWriterMetadata>::~CComPtr<IVssExamineWriterMetadata>();
  ATL::CComPtr<IVssExamineWriterMetadata>::~CComPtr<IVssExamineWriterMetadata>();
  if ( v8 )
    CVolumeEntryMap::Release(v8);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&ClientVolumes, v30, v31);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18000a920  push    rbp
0x18000a922  push    rbx
0x18000a923  push    rsi
0x18000a924  push    rdi
0x18000a925  push    r12
0x18000a927  push    r13
0x18000a929  push    r14
0x18000a92b  push    r15
0x18000a92d  lea     rbp, [rsp-78h]
0x18000a932  sub     rsp, 178h
0x18000a939  mov     rax, cs:__security_cookie
0x18000a940  xor     rax, rsp
0x18000a943  mov     [rbp+0B0h+var_50], rax
0x18000a947  mov     rbx, r8
0x18000a94a  mov     [rbp+0B0h+var_A8], r9
0x18000a94e  mov     [rbp+0B0h+var_A0], rbx
0x18000a952  mov     r15, r9
0x18000a955  mov     rdi, rdx
0x18000a958  mov     [rbp+0B0h+var_B0], rcx
0x18000a95c  mov     r13, rcx
0x18000a95f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a966  lea     rax, WPP_GLOBAL_Control
0x18000a96d  cmp     rcx, rax
0x18000a970  jz      short loc_18000A98C
0x18000a972  test    dword ptr [rcx+1Ch], 20000000h
0x18000a979  jz      short loc_18000A98C
0x18000a97b  mov     rcx, [rcx+10h]
0x18000a97f  mov     edx, 0B9h
0x18000a984  mov     r9, rdi
0x18000a987  call    WPP_SF__guid_
0x18000a98c  mov     r9d, 1; unsigned __int16
0x18000a992  lea     rdx, aCsppGetmissing; "CSpp::GetMissingSafeVolumes"
0x18000a999  mov     r8d, 2957h; unsigned __int16
0x18000a99f  lea     rcx, [rsp+1B0h+var_168]; this
0x18000a9a4  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18000a9a9  xor     edx, edx
0x18000a9ab  lea     rcx, [rbp+0B0h+var_118]
0x18000a9af  mov     r12d, edx
0x18000a9b2  mov     [rbp+0B0h+var_C8], rdx
0x18000a9b6  call    ??0?$CComPtr@VIVssBackupComponents@@@ATL@@QEAA@H@Z; ATL::CComPtr<IVssBackupComponents>::CComPtr<IVssBackupComponents>(int)
0x18000a9bb  lea     rcx, [rbp+0B0h+var_E0]
0x18000a9bf  call    ??0?$CComPtr@VIVssBackupComponents@@@ATL@@QEAA@H@Z; ATL::CComPtr<IVssBackupComponents>::CComPtr<IVssBackupComponents>(int)
0x18000a9c4  lea     rcx, [rbp+0B0h+var_108]
0x18000a9c8  mov     [rbp+0B0h+var_B8], rdx
0x18000a9cc  mov     [rbp+0B0h+var_100], edx
0x18000a9cf  call    ??0?$CComPtr@VIVssBackupComponents@@@ATL@@QEAA@H@Z; ATL::CComPtr<IVssBackupComponents>::CComPtr<IVssBackupComponents>(int)
0x18000a9d4  lea     rcx, [rbp+0B0h+var_E8]
0x18000a9d8  call    ??0?$CComPtr@VIVssBackupComponents@@@ATL@@QEAA@H@Z; ATL::CComPtr<IVssBackupComponents>::CComPtr<IVssBackupComponents>(int)
0x18000a9dd  mov     [rbp+0B0h+bstrString], rdx
0x18000a9e1  mov     r14d, edx
0x18000a9e4  mov     [rbp+0B0h+var_D4], edx
0x18000a9e7  mov     esi, edx
0x18000a9e9  mov     [rbp+0B0h+var_D8], edx
0x18000a9ec  mov     [rbp+0B0h+var_CC], edx
0x18000a9ef  mov     [rbp+0B0h+var_D0], edx
0x18000a9f2  mov     [rbp+0B0h+var_FC], edx
0x18000a9f5  mov     [rbp+0B0h+var_F8], edx
0x18000a9f8  mov     [rbp+0B0h+var_110], rdx
0x18000a9fc  mov     [rbp+0B0h+var_C0], rdx
0x18000aa00  mov     [rbp+0B0h+var_130], edx
0x18000aa03  mov     [rsp+1B0h+var_170], rdx
0x18000aa08  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18000aa0f  movdqu  [rbp+0B0h+var_70], xmm0
0x18000aa14  movdqu  [rbp+0B0h+var_60], xmm0
0x18000aa19  movdqu  [rbp+0B0h+Buf1], xmm0
0x18000aa1e  xorps   xmm0, xmm0
0x18000aa21  movdqu  xmmword ptr [rbp+0B0h+var_128], xmm0
0x18000aa26  test    rbx, rbx
0x18000aa29  jz      short loc_18000AA2D
0x18000aa2b  mov     [rbx], edx
0x18000aa2d  test    r15, r15
0x18000aa30  jz      short loc_18000AA35
0x18000aa32  mov     [r15], rdx
0x18000aa35  mov     eax, 2975h
0x18000aa3a  test    rbx, rbx
0x18000aa3d  jnz     short loc_18000AA4F
0x18000aa3f  mov     ebx, 80070057h
0x18000aa44  mov     [rsp+1B0h+var_168], ebx
0x18000aa48  xor     edi, edi
0x18000aa4a  jmp     loc_18000B01A
0x18000aa4f  mov     [rsp+1B0h+var_164], ax
0x18000aa54  mov     eax, 2976h
0x18000aa59  test    r15, r15
0x18000aa5c  jz      short loc_18000AA3F
0x18000aa5e  lea     rcx, [rbp+0B0h+var_C8]; struct CVolumeEntryMap **
0x18000aa62  mov     [rsp+1B0h+var_168], edx
0x18000aa66  mov     [rsp+1B0h+var_164], ax
0x18000aa6b  call    ?CreateInstance@CVolumeEntryMap@@SAJPEAPEAV1@@Z; CVolumeEntryMap::CreateInstance(CVolumeEntryMap * *)
0x18000aa70  mov     r12, [rbp+0B0h+var_C8]
0x18000aa74  mov     ebx, eax
0x18000aa76  mov     [rsp+1B0h+var_168], eax
0x18000aa7a  test    eax, eax
0x18000aa7c  mov     eax, 297Bh
0x18000aa81  js      short loc_18000AA48
0x18000aa83  movups  xmm0, xmmword ptr [rdi]
0x18000aa86  mov     r8, r12; struct CVolumeEntryMap *
0x18000aa89  mov     [rsp+1B0h+var_164], ax
0x18000aa8e  lea     rdx, [rbp+0B0h+var_90]; Buf1
0x18000aa92  mov     rcx, r13; this
0x18000aa95  movdqu  xmmword ptr [rbp+0B0h+var_90.Data1], xmm0
0x18000aa9a  call    ?_GetClientVolumes@CSpp@@AEAAJU_GUID@@PEAVCVolumeEntryMap@@@Z; CSpp::_GetClientVolumes(_GUID,CVolumeEntryMap *)
0x18000aa9f  xor     edi, edi
0x18000aaa1  mov     [rsp+1B0h+var_168], eax
0x18000aaa5  test    eax, eax
0x18000aaa7  mov     ebx, eax
0x18000aaa9  mov     eax, 297Ch
0x18000aaae  js      loc_18000B01A
0x18000aab4  lea     rcx, [rbp+0B0h+var_118]
0x18000aab8  mov     [rsp+1B0h+var_164], ax
0x18000aabd  call    cs:__imp_CreateVssBackupComponentsInternal
0x18000aac3  mov     ebx, eax
0x18000aac5  mov     [rsp+1B0h+var_168], eax
0x18000aac9  test    eax, eax
0x18000aacb  mov     eax, 2982h
0x18000aad0  js      loc_18000B01A
0x18000aad6  mov     rcx, [rbp+0B0h+var_118]
0x18000aada  xor     edx, edx
0x18000aadc  mov     [rsp+1B0h+var_164], ax
0x18000aae1  mov     rax, [rcx]
0x18000aae4  mov     rax, [rax+28h]
0x18000aae8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aaed  mov     ebx, eax
0x18000aaef  mov     [rsp+1B0h+var_168], eax
0x18000aaf3  test    eax, eax
0x18000aaf5  mov     eax, 2984h
0x18000aafa  js      loc_18000B01A
0x18000ab00  or      r15d, 0FFFFFFFFh
0x18000ab04  mov     [rsp+1B0h+var_164], ax
0x18000ab09  mov     edx, r15d; unsigned int
0x18000ab0c  lea     r8, [rbp+0B0h+var_B8]; unsigned __int64 *
0x18000ab10  call    ?_InitTimer@CSpp@@AEAAJKPEA_K@Z; CSpp::_InitTimer(ulong,unsigned __int64 *)
0x18000ab15  mov     ebx, eax
0x18000ab17  mov     [rsp+1B0h+var_168], eax
0x18000ab1b  test    eax, eax
0x18000ab1d  mov     eax, 2986h
0x18000ab22  js      loc_18000B01A
0x18000ab28  mov     r8, [rbp+0B0h+var_118]; struct IVssBackupComponents *
0x18000ab2c  xor     edx, edx; int
0x18000ab2e  mov     [rsp+1B0h+var_164], ax
0x18000ab33  call    ?_EnableInterestingWriters@CSpp@@AEAAJHPEAVIVssBackupComponents@@@Z; CSpp::_EnableInterestingWriters(int,IVssBackupComponents *)
0x18000ab38  mov     ebx, eax
0x18000ab3a  mov     [rsp+1B0h+var_168], eax
0x18000ab3e  test    eax, eax
0x18000ab40  mov     eax, 2988h
0x18000ab45  js      loc_18000B01A
0x18000ab4b  lea     rcx, [rbp+0B0h+var_E0]
0x18000ab4f  mov     [rsp+1B0h+var_164], ax
0x18000ab54  call    ?Release@?$CComPtrBase@VIVssWMComponent@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IVssWMComponent>::Release(void)
0x18000ab59  mov     rcx, [rbp+0B0h+var_118]
0x18000ab5d  lea     rdx, [rbp+0B0h+var_E0]
0x18000ab61  mov     rax, [rcx]
0x18000ab64  mov     rax, [rax+48h]
0x18000ab68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab6d  mov     ebx, eax
0x18000ab6f  mov     [rsp+1B0h+var_168], eax
0x18000ab73  test    eax, eax
0x18000ab75  mov     eax, 298Bh
0x18000ab7a  js      loc_18000B01A
0x18000ab80  mov     r9, [rbp+0B0h+var_B8]; unsigned __int64
0x18000ab84  mov     r8d, r15d; unsigned int
0x18000ab87  mov     rdx, [rbp+0B0h+var_E0]; struct IVssAsync *
0x18000ab8b  mov     [rsp+1B0h+var_164], ax
0x18000ab90  call    ?_AsyncWaitWithTimeout@CSpp@@AEAAJPEAUIVssAsync@@K_K@Z; CSpp::_AsyncWaitWithTimeout(IVssAsync *,ulong,unsigned __int64)
0x18000ab95  mov     ebx, eax
0x18000ab97  mov     [rsp+1B0h+var_168], eax
0x18000ab9b  test    eax, eax
0x18000ab9d  mov     eax, 298Eh
0x18000aba2  js      loc_18000B01A
0x18000aba8  mov     rcx, [rbp+0B0h+var_118]
0x18000abac  lea     rdx, [rbp+0B0h+var_100]
0x18000abb0  mov     [rsp+1B0h+var_164], ax
0x18000abb5  mov     rax, [rcx]
0x18000abb8  mov     rax, [rax+50h]
0x18000abbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000abc1  mov     ebx, eax
0x18000abc3  mov     [rsp+1B0h+var_168], eax
0x18000abc7  test    eax, eax
0x18000abc9  mov     eax, 2990h
0x18000abce  js      loc_18000B01A
0x18000abd4  lea     rcx, [rbp+0B0h+var_110]; struct CVolumeEntryMap **
0x18000abd8  mov     [rsp+1B0h+var_164], ax
0x18000abdd  call    ?CreateInstance@CVolumeEntryMap@@SAJPEAPEAV1@@Z; CVolumeEntryMap::CreateInstance(CVolumeEntryMap * *)
0x18000abe2  mov     ebx, eax
0x18000abe4  mov     [rsp+1B0h+var_168], eax
0x18000abe8  test    eax, eax
0x18000abea  mov     eax, 2992h
0x18000abef  jns     short loc_18000ABFA
0x18000abf1  mov     r14, [rbp+0B0h+var_110]
0x18000abf5  jmp     loc_18000B01A
0x18000abfa  lea     rcx, [rbp+0B0h+var_C0]; struct CVolumeEntryMap **
0x18000abfe  mov     [rsp+1B0h+var_164], ax
0x18000ac03  call    ?CreateInstance@CVolumeEntryMap@@SAJPEAPEAV1@@Z; CVolumeEntryMap::CreateInstance(CVolumeEntryMap * *)
0x18000ac08  mov     r14, [rbp+0B0h+var_110]
0x18000ac0c  mov     ebx, eax
0x18000ac0e  mov     rsi, [rbp+0B0h+var_C0]
0x18000ac12  test    eax, eax
0x18000ac14  mov     [rsp+1B0h+var_168], eax
0x18000ac18  mov     eax, 2993h
0x18000ac1d  js      loc_18000B01A
0x18000ac23  mov     [rsp+1B0h+var_164], ax
0x18000ac28  mov     rcx, [rsi]; Table
0x18000ac2b  mov     r15d, 29AEh
0x18000ac31  lea     r13d, [r15-6]
0x18000ac35  lea     ebx, [r15-9]
0x18000ac39  call    cs:__imp_RtlNumberGenericTableElementsAvl
0x18000ac3f  mov     rcx, [rbp+0B0h+var_128]; this
0x18000ac43  mov     dword ptr [rbp+0B0h+var_110], eax
0x18000ac46  test    rcx, rcx
0x18000ac49  jz      short loc_18000AC54
0x18000ac4b  call    ?Release@CVolumeEntryMap@@QEAAKXZ; CVolumeEntryMap::Release(void)
0x18000ac50  mov     [rbp+0B0h+var_128], rdi
0x18000ac54  mov     [rbp+0B0h+var_130], edi
0x18000ac57  mov     [rbp+0B0h+var_128+8], rdi
0x18000ac5b  test    rsi, rsi
0x18000ac5e  jz      loc_18000B00C
0x18000ac64  cmp     [rbp+0B0h+var_128], rdi
0x18000ac68  jnz     loc_18000B005
0x18000ac6e  mov     [rbp+0B0h+var_128], rsi
0x18000ac72  lock inc dword ptr [rsi+10h]
0x18000ac76  mov     rax, [rbp+0B0h+var_128]
0x18000ac7a  mov     ecx, [rax+8]
0x18000ac7d  mov     [rbp+0B0h+var_130], ecx
0x18000ac80  mov     [rbp+0B0h+var_128+8], rdi
0x18000ac84  mov     rcx, [rsp+1B0h+var_170]; this
0x18000ac89  mov     [rsp+1B0h+var_168], edi
0x18000ac8d  mov     [rsp+1B0h+var_164], bx
0x18000ac92  test    rcx, rcx
0x18000ac95  jz      short loc_18000ACA1
0x18000ac97  mov     [rsp+1B0h+var_170], rdi
0x18000ac9c  call    ?Release@CVolumeEntry@@QEAAKXZ; CVolumeEntry::Release(void)
0x18000aca1  lea     rdx, [rsp+1B0h+var_170]
0x18000aca6  lea     rcx, [rbp+0B0h+var_130]
0x18000acaa  call    ?Next@CSxIter@?$CSxRefMap@VCSxStringMap@@VCSxStringEntry@@@@QEAAJPEAPEAVCSxStringEntry@@@Z; CSxRefMap<CSxStringMap,CSxStringEntry>::CSxIter::Next(CSxStringEntry * *)
0x18000acaf  mov     [rsp+1B0h+var_168], eax
0x18000acb3  mov     ebx, eax
0x18000acb5  test    eax, eax
0x18000acb7  js      loc_18000AFFD
0x18000acbd  mov     [rsp+1B0h+var_164], r13w
0x18000acc3  mov     r13d, 29ABh
0x18000acc9  cmp     ebx, 1
0x18000accc  jz      short loc_18000AD31
0x18000acce  mov     rdi, [rsp+1B0h+var_170]
0x18000acd3  xor     r8d, r8d
0x18000acd6  mov     rdx, rdi
0x18000acd9  mov     rcx, r12
0x18000acdc  call    ?Insert@?$CSxRefMap@VCVolumeOnDiskPropCacheMap@@VCVolumeOnDiskPropCacheEntry@@@@QEAAJPEAVCVolumeOnDiskPropCacheEntry@@PEAPEAV2@@Z; CSxRefMap<CVolumeOnDiskPropCacheMap,CVolumeOnDiskPropCacheEntry>::Insert(CVolumeOnDiskPropCacheEntry *,CVolumeOnDiskPropCacheEntry * *)
0x18000ace1  mov     [rsp+1B0h+var_168], eax
0x18000ace5  mov     ebx, eax
0x18000ace7  test    eax, eax
0x18000ace9  js      loc_18000AFE0
0x18000acef  mov     [rsp+1B0h+var_164], r13w
0x18000acf5  test    rdi, rdi
0x18000acf8  jz      short loc_18000AD0B
0x18000acfa  mov     rcx, rdi; this
0x18000acfd  mov     [rsp+1B0h+var_170], 0
0x18000ad06  call    ?Release@CVolumeEntry@@QEAAKXZ; CVolumeEntry::Release(void)
0x18000ad0b  lea     rdx, [rsp+1B0h+var_170]
0x18000ad10  lea     rcx, [rbp+0B0h+var_130]
0x18000ad14  call    ?Next@CSxIter@?$CSxRefMap@VCSxStringMap@@VCSxStringEntry@@@@QEAAJPEAPEAVCSxStringEntry@@@Z; CSxRefMap<CSxStringMap,CSxStringEntry>::CSxIter::Next(CSxStringEntry * *)
0x18000ad19  xor     edi, edi
0x18000ad1b  mov     [rsp+1B0h+var_168], eax
0x18000ad1f  mov     ebx, eax
0x18000ad21  test    eax, eax
0x18000ad23  js      loc_18000AFD8
0x18000ad29  mov     [rsp+1B0h+var_164], r15w
0x18000ad2f  jmp     short loc_18000ACC9
0x18000ad31  mov     r13d, edi
0x18000ad34  cmp     r13d, [rbp+0B0h+var_100]
0x18000ad38  jnb     loc_18000AFA0
0x18000ad3e  lea     rcx, [rbp+0B0h+var_108]
0x18000ad42  call    ?Release@?$CComPtrBase@VIVssWMComponent@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IVssWMComponent>::Release(void)
0x18000ad47  mov     rcx, [rbp+0B0h+var_118]
0x18000ad4b  lea     r9, [rbp+0B0h+var_108]
0x18000ad4f  lea     r8, [rbp+0B0h+var_70]
0x18000ad53  mov     edx, r13d
0x18000ad56  mov     rax, [rcx]
0x18000ad59  mov     rax, [rax+58h]
0x18000ad5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad62  mov     ebx, eax
0x18000ad64  mov     [rsp+1B0h+var_168], eax
0x18000ad68  test    eax, eax
0x18000ad6a  mov     eax, 29BAh
0x18000ad6f  js      loc_18000B01A
0x18000ad75  mov     rcx, [rbp+0B0h+bstrString]; bstrString
0x18000ad79  mov     [rsp+1B0h+var_164], ax
0x18000ad7e  call    cs:__imp_SysFreeString
0x18000ad84  mov     rcx, [rbp+0B0h+var_108]
0x18000ad88  lea     rdx, [rbp+0B0h+var_D8]
0x18000ad8c  mov     [rsp+1B0h+var_188], rdx
0x18000ad91  lea     r9, [rbp+0B0h+bstrString]
0x18000ad95  mov     [rbp+0B0h+bstrString], rdi
0x18000ad99  lea     rdx, [rbp+0B0h+var_D4]
0x18000ad9d  mov     [rsp+1B0h+var_190], rdx
0x18000ada2  lea     r8, [rbp+0B0h+Buf1]
0x18000ada6  mov     rax, [rcx]
0x18000ada9  lea     rdx, [rbp+0B0h+var_60]
0x18000adad  mov     rax, [rax+18h]
0x18000adb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000adb6  mov     ebx, eax
0x18000adb8  mov     [rsp+1B0h+var_168], eax
  ... truncated ...
```
