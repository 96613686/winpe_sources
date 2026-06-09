# CVssSnapshotSetObject::ThawWriters(void)

- ea: `0x14004500c`
- end: `0x140045e69`
- name: `?ThawWriters@CVssSnapshotSetObject@@AEAAXXZ`
- size: `3677`
- prototype: `void __fastcall(CVssSnapshotSetObject *__hidden this)`
- caller_count: `1`
- callee_count: `25`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400462e0`

## callees

- `0x140003b70`
- `0x140006078`
- `0x1400137c0`
- `0x1400139c0`
- `0x140013b00`
- `0x140015e38`
- `0x1400347a0`
- `0x140042acc`
- `0x1400437e0`
- `0x140044014`
- `0x140044ce8`
- `0x14004500c`
- `0x140046a78`
- `0x1400550f4`
- `0x140058c78`
- `0x14005b1b4`
- `0x14005b284`
- `0x140091560`
- `0x1400921dc`
- `0x140093ff4`
- `0x1400a3390`
- `0x1400a3838`
- `0x1400a6f44`
- `0x1400a7f3c`
- `0x1400f4010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1400455de`
- `OLEAUT32!__imp_SysFreeString` at `0x14004562e`
- `OLEAUT32!__imp_SysFreeString` at `0x1400456dd`
- `OLEAUT32!__imp_SysFreeString` at `0x1400455de`
- `OLEAUT32!__imp_SysFreeString` at `0x14004562e`
- `OLEAUT32!__imp_SysFreeString` at `0x1400456dd`

## string_xrefs

- `0x14004504b`: `CVssSnapshotSetObject::ThawWriters`
- `0x1400451a0`: `CVssSnapshotSetObject::ThawWriters`
- `0x1400452e3`: `CVssSnapshotSetObject::ThawWriters`
- `0x140045572`: `CVssSnapshotSetObject::ThawWriters`
- `0x1400457f8`: `CVssSnapshotSetObject::ThawWriters`
- `0x140045971`: `CVssSnapshotSetObject::ThawWriters`
- `0x140045a15`: `CVssSnapshotSetObject::ThawWriters`
- `0x140045b35`: `CVssSnapshotSetObject::ThawWriters`
- `0x140045d65`: `CVssSnapshotSetObject::ThawWriters`
- `0x140045263`: `bIsDiskMaskNeeded for ThawWriters = %s`
- `0x140045338`: `bIsDiskMaskPossible for ThawWriters = %s`
- `0x140045e52`: `PostCommitSnapshots(ProviderID = {%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x}, {%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x}, %ld)`
- `0x1400459e7`: `PostCommitSnapshots({%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x}, %ld)`
- `0x14004586e`: `PreFinalCommitSnapshots({%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x}, %ld)`
- `0x140045bab`: `PostFinalCommitSnapshots({%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x}, %ld)`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall CVssSnapshotSetObject::ThawWriters(struct IDispatch **this)
{
  OLECHAR *v2; // rbx
  int v3; // r14d
  BOOL v4; // r12d
  const wchar_t *v5; // r15
  const wchar_t *v6; // r9
  unsigned int i; // esi
  OLECHAR *lpVtbl; // rdi
  int v9; // esi
  struct IDispatchVtbl *v10; // rdi
  _BOOL8 v11; // r9
  int v12; // eax
  int v13; // r15d
  struct IDispatchVtbl *v14; // rsi
  __int64 (__fastcall *v15)(struct IDispatchVtbl *, struct _GUID *); // rdi
  OLECHAR *v16; // rdi
  int v17; // esi
  ATL::CComBSTR *v18; // rax
  struct IDispatchVtbl *v19; // rdi
  BOOL v20; // r15d
  int v21; // r13d
  int v22; // r12d
  int v23; // ebx
  int v24; // edi
  int v25; // esi
  int v26; // r14d
  unsigned int v27; // r15d
  struct _GUID v28; // xmm1
  __int64 v29; // rax
  int v30; // r13d
  int v31; // r12d
  int v32; // ebx
  int v33; // edi
  int v34; // esi
  int v35; // r14d
  unsigned int v36; // r15d
  struct _GUID v37; // xmm1
  __int64 v38; // rax
  __int64 v39; // rax
  int v40; // r13d
  int v41; // r12d
  int v42; // ebx
  int v43; // edi
  int v44; // esi
  int v45; // r14d
  unsigned int v46; // r15d
  struct _GUID v47; // xmm1
  __int64 v48; // rax
  __int64 v49; // rax
  int v50; // ebx
  int v51; // edi
  int v52; // esi
  int v53; // r14d
  int Data3; // r15d
  int Data2; // r12d
  __int64 v56; // rdx
  __int64 v57; // rcx
  __int64 v58; // rdx
  __int64 v59; // rcx
  __int64 v60; // rdx
  __int64 v61; // rcx
  __int64 v62; // rdx
  __int64 v63; // rcx
  __int64 v64; // rdx
  __int64 v65; // rcx
  __int64 v66; // rdx
  __int64 v67; // rcx
  __int64 v68; // rdx
  __int64 v69; // rcx
  __int64 v70; // rdx
  __int64 v71; // rcx
  __int64 v72; // rdx
  __int64 v73; // rcx
  __int64 v74; // rdx
  __int64 v75; // rcx
  __int64 v76; // r13
  __int64 v77; // r8
  unsigned int Size; // eax
  int v79; // edx
  int v80; // r9d
  int v81; // r10d
  int v82; // r11d
  int v83; // [rsp+20h] [rbp-140h]
  int v84; // [rsp+20h] [rbp-140h]
  __int64 v85; // [rsp+20h] [rbp-140h]
  __int64 v86; // [rsp+20h] [rbp-140h]
  __int64 v87; // [rsp+20h] [rbp-140h]
  __int64 v88; // [rsp+20h] [rbp-140h]
  __int64 v89; // [rsp+20h] [rbp-140h]
  __int64 v90; // [rsp+28h] [rbp-138h]
  __int64 v91; // [rsp+28h] [rbp-138h]
  __int64 v92; // [rsp+28h] [rbp-138h]
  __int64 v93; // [rsp+28h] [rbp-138h]
  unsigned __int8 v94; // [rsp+E0h] [rbp-80h]
  unsigned __int8 v95; // [rsp+E0h] [rbp-80h]
  unsigned __int8 v96; // [rsp+E0h] [rbp-80h]
  unsigned __int8 v97; // [rsp+E1h] [rbp-7Fh]
  unsigned __int8 v98; // [rsp+E1h] [rbp-7Fh]
  unsigned __int8 v99; // [rsp+E1h] [rbp-7Fh]
  unsigned __int8 v100; // [rsp+E2h] [rbp-7Eh]
  unsigned __int8 v101; // [rsp+E2h] [rbp-7Eh]
  unsigned __int8 v102; // [rsp+E2h] [rbp-7Eh]
  unsigned __int8 v103; // [rsp+E2h] [rbp-7Eh]
  unsigned __int8 v104; // [rsp+E3h] [rbp-7Dh]
  unsigned __int8 v105; // [rsp+E3h] [rbp-7Dh]
  unsigned __int8 v106; // [rsp+E3h] [rbp-7Dh]
  unsigned __int8 v107; // [rsp+E3h] [rbp-7Dh]
  unsigned int v108; // [rsp+E4h] [rbp-7Ch] BYREF
  BSTR bstrString; // [rsp+E8h] [rbp-78h] BYREF
  int v110; // [rsp+F0h] [rbp-70h]
  BSTR v111[3]; // [rsp+F8h] [rbp-68h] BYREF
  struct _GUID v112; // [rsp+110h] [rbp-50h] BYREF
  struct IDispatch **v113; // [rsp+120h] [rbp-40h]
  struct _GUID v114; // [rsp+128h] [rbp-38h] BYREF
  unsigned int Data1; // [rsp+138h] [rbp-28h]
  int v116; // [rsp+13Ch] [rbp-24h]
  int v117; // [rsp+140h] [rbp-20h]
  int v118; // [rsp+144h] [rbp-1Ch]
  int v119; // [rsp+148h] [rbp-18h]
  int v120; // [rsp+14Ch] [rbp-14h]
  int v121; // [rsp+150h] [rbp-10h]
  int v122; // [rsp+154h] [rbp-Ch]
  struct _GUID v123; // [rsp+158h] [rbp-8h] BYREF
  const unsigned __int16 *v124; // [rsp+168h] [rbp+8h] BYREF
  const wchar_t *v125; // [rsp+170h] [rbp+10h]
  const unsigned __int16 *v126; // [rsp+178h] [rbp+18h]
  int v127; // [rsp+180h] [rbp+20h]
  int v128; // [rsp+184h] [rbp+24h]
  int v129; // [rsp+188h] [rbp+28h]
  _BYTE v130[120]; // [rsp+190h] [rbp+30h] BYREF
  int v131; // [rsp+208h] [rbp+A8h]
  struct _GUID v132; // [rsp+210h] [rbp+B0h] BYREF
  BSTR v133; // [rsp+220h] [rbp+C0h] BYREF
  struct _GUID v134; // [rsp+228h] [rbp+C8h] BYREF
  struct _GUID v135; // [rsp+238h] [rbp+D8h] BYREF
  struct _GUID v136; // [rsp+248h] [rbp+E8h] BYREF
  struct _GUID v137; // [rsp+258h] [rbp+F8h] BYREF
  struct _GUID v138; // [rsp+268h] [rbp+108h] BYREF
  struct _GUID v139; // [rsp+278h] [rbp+118h] BYREF
  struct _GUID v140; // [rsp+288h] [rbp+128h] BYREF
  struct _GUID v141; // [rsp+298h] [rbp+138h] BYREF
  LPVOID v142; // [rsp+2B0h] [rbp+150h] BYREF
  int v143; // [rsp+2B8h] [rbp+158h]
  struct _GUID v144; // [rsp+320h] [rbp+1C0h] BYREF

  v113 = this;
  v124 = L"base\\stor\\vss\\modules\\coord\\src\\snap_set.cxx";
  v125 = L"CVssSnapshotSetObject::ThawWriters";
  v126 = L"CORSNPSC";
  v127 = 1242;
  v128 = 1;
  v129 = 255;
  v131 = 0x1000000;
  memset_0(v130, 0, sizeof(v130));
  CVssFunctionTracer::CVssFunctionTracer((__int64)&v142, (__int64)&v124, 0);
  v144 = *CVssGlobalSnapshotSetId::GetID(&v132);
  ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v133, &v144);
  v2 = v133;
  if ( !v133 )
  {
    v49 = CVssDebugInfo::CVssDebugInfo(
            &v124,
            L"base\\stor\\vss\\modules\\coord\\src\\snap_set.cxx",
            L"CORSNPSC",
            L"CVssSnapshotSetObject::ThawWriters",
            1251,
            1);
    CVssFunctionTracer::Throw(&v142, v49, 2147942414LL, L"Memory allocation error");
  }
  CVssSnapshotSetObject::ThawKTM((CVssSnapshotSetObject *)this, 1);
  if ( (unsigned int)CVssSKU::IsEventSystemPresent() )
    CVssSnapshotSetObject::ThawDTC((CVssSnapshotSetObject *)this, 1);
  if ( ((_BYTE)this[8] & 0x10) == 0 )
  {
    v112 = *CVssGlobalSnapshotSetId::GetID((struct _GUID *)v111);
    CVssDiag::RecordWriterEvent(this + 202, 1010, 1);
    v143 = ((__int64 (__fastcall *)(struct IDispatch *, OLECHAR *))this[10]->lpVtbl[1].QueryInterface)(this[10], v2);
    v112 = *CVssGlobalSnapshotSetId::GetID((struct _GUID *)v111);
    v83 = v143;
    CVssDiag::RecordWriterEvent(this + 202, 1010, 0);
    v124 = L"base\\stor\\vss\\modules\\coord\\src\\snap_set.cxx";
    v125 = L"CVssSnapshotSetObject::ThawWriters";
    v126 = L"CORSNPSC";
    v127 = 1290;
    v128 = 1;
    v129 = 255;
    v131 = 0x1000000;
    memset_0(v130, 0, sizeof(v130));
    CVssFunctionTracer::TranslateWriterReturnCode(&v142, &v124, L"Thaw(%s)", v2, v83, &v112);
  }
  v3 = 1;
  v4 = ((_BYTE)this[8] & 0x20) != 0 && ((_DWORD)this[8] & 0x2400000) != 0;
  v124 = L"base\\stor\\vss\\modules\\coord\\src\\snap_set.cxx";
  v125 = L"CVssSnapshotSetObject::ThawWriters";
  v126 = L"CORSNPSC";
  v127 = 1315;
  v128 = 1;
  v129 = 255;
  v131 = 0x1000000;
  memset_0(v130, 0, sizeof(v130));
  v5 = L"TRUE";
  v6 = L"TRUE";
  if ( !v4 )
    v6 = L"FALSE";
  CVssFunctionTracer::Trace(&v142, &v124, L"bIsDiskMaskNeeded for ThawWriters = %s", v6);
  for ( i = 0; i < *((_DWORD *)this + 26); ++i )
  {
    lpVtbl = (OLECHAR *)this[12][i].lpVtbl;
    bstrString = lpVtbl;
    if ( lpVtbl )
      (*(void (__fastcall **)(OLECHAR *))(*(_QWORD *)lpVtbl + 8LL))(lpVtbl);
    v108 = 0;
    (*(void (__fastcall **)(OLECHAR *, unsigned int *))(*(_QWORD *)lpVtbl + 264LL))(lpVtbl, &v108);
    v3 &= v108;
    ATL::CComPtrBase<CVssFileShareProviderWrapper>::~CComPtrBase<CVssFileShareProviderWrapper>((__int64 *)&bstrString);
  }
  v124 = L"base\\stor\\vss\\modules\\coord\\src\\snap_set.cxx";
  v125 = L"CVssSnapshotSetObject::ThawWriters";
  v126 = L"CORSNPSC";
  v127 = 1329;
  v128 = 1;
  v129 = 255;
  v131 = 0x1000000;
  memset_0(v130, 0, sizeof(v130));
  if ( !v3 )
    v5 = L"FALSE";
  CVssFunctionTracer::Trace(&v142, &v124, L"bIsDiskMaskPossible for ThawWriters = %s", v5);
  v9 = *((_DWORD *)this + 26);
  while ( 1 )
  {
    v108 = --v9;
    if ( v9 < 0 )
      break;
    v10 = this[12][v9].lpVtbl;
    v111[0] = (BSTR)v10;
    if ( v10 )
      (*((void (__fastcall **)(struct IDispatchVtbl *))v10->QueryInterface + 1))(v10);
    v11 = v4 && v3;
    v12 = (*((__int64 (__fastcall **)(struct IDispatchVtbl *, struct IDispatch *, char *, _BOOL8))v10->QueryInterface
           + 21))(
            v10,
            this[201],
            (char *)this + 1584,
            v11);
    v143 = v12;
    if ( v12 < 0 )
    {
      if ( v12 == -2147212512 || v12 == -2147212538 || (unsigned int)(v12 + 2147212296) <= 4 )
      {
        v110 = *((_DWORD *)this + 624) + *((_DWORD *)this + 18);
        v107 = CVssGlobalSnapshotSetId::GetID(&v141)->Data4[7];
        v103 = CVssGlobalSnapshotSetId::GetID(&v140)->Data4[6];
        CVssGlobalSnapshotSetId::GetID(&v139);
        CVssGlobalSnapshotSetId::GetID(&v138);
        v50 = CVssGlobalSnapshotSetId::GetID(&v137)->Data4[3];
        v51 = CVssGlobalSnapshotSetId::GetID(&v136)->Data4[2];
        v52 = CVssGlobalSnapshotSetId::GetID(&v135)->Data4[1];
        v53 = CVssGlobalSnapshotSetId::GetID(&v134)->Data4[0];
        Data3 = CVssGlobalSnapshotSetId::GetID(&v132)->Data3;
        Data2 = CVssGlobalSnapshotSetId::GetID(&v144)->Data2;
        Data1 = CVssGlobalSnapshotSetId::GetID(&v123)->Data1;
        v108 = *(unsigned __int8 *)(CVssSimpleMap<_GUID,ATL::CComPtr<IVssSnapshotProvider>>::GetKeyAt(this + 11, v108)
                                  + 15);
        v116 = *(unsigned __int8 *)(CVssSimpleMap<_GUID,ATL::CComPtr<IVssSnapshotProvider>>::GetKeyAt(v57, v56) + 14);
        v117 = *(unsigned __int8 *)(CVssSimpleMap<_GUID,ATL::CComPtr<IVssSnapshotProvider>>::GetKeyAt(v59, v58) + 13);
        v118 = *(unsigned __int8 *)(CVssSimpleMap<_GUID,ATL::CComPtr<IVssSnapshotProvider>>::GetKeyAt(v61, v60) + 12);
        v119 = *(unsigned __int8 *)(CVssSimpleMap<_GUID,ATL::CComPtr<IVssSnapshotProvider>>::GetKeyAt(v63, v62) + 11);
        v120 = *(unsigned __int8 *)(CVssSimpleMap<_GUID,ATL::CComPtr<IVssSnapshotProvider>>::GetKeyAt(v65, v64) + 10);
        v121 = *(unsigned __int8 *)(CVssSimpleMap<_GUID,ATL::CComPtr<IVssSnapshotProvider>>::GetKeyAt(v67, v66) + 9);
        v122 = *(unsigned __int8 *)(CVssSimpleMap<_GUID,ATL::CComPtr<IVssSnapshotProvider>>::GetKeyAt(v69, v68) + 8);
        LODWORD(v113) = *(unsigned __int16 *)(CVssSimpleMap<_GUID,ATL::CComPtr<IVssSnapshotProvider>>::GetKeyAt(
                                                v71,
                                                v70)
                                            + 6);
        v114.Data1 = *(unsigned __int16 *)(CVssSimpleMap<_GUID,ATL::CComPtr<IVssSnapshotProvider>>::GetKeyAt(v73, v72)
                                         + 4);
        LODWORD(bstrString) = *(_DWORD *)CVssSimpleMap<_GUID,ATL::CComPtr<IVssSnapshotProvider>>::GetKeyAt(v75, v74);
        v76 = CVssDebugInfo::CVssDebugInfo(
                &v124,
                L"base\\stor\\vss\\modules\\coord\\src\\snap_set.cxx",
                L"CORSNPSC",
                L"CVssSnapshotSetObject::ThawWriters",
                1347,
                1);
        Size = ATL::CSimpleArray<_HRESOURCE *,ATL::CSimpleArrayEqualHelper<_HRESOURCE *>>::GetSize(
                 &v142,
                 v107,
                 v77,
                 v103);
        LODWORD(v93) = v114.Data1;
        LODWORD(v89) = (_DWORD)bstrString;
        CVssFunctionTracer::Throw(
          &v142,
          v76,
          Size,
          L"PostCommitSnapshots(ProviderID = {%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x}, {%.8x-%.4x-%.4x-%.2x%.2x-"
           "%.2x%.2x%.2x%.2x%.2x%.2x}, %ld)",
          v89,
          v93,
          (_DWORD)v113,
          v122,
          v121,
          v120,
          v119,
          v118,
          v117,
          v116,
          v108,
          Data1,
          Data2,
          Data3,
          v53,
          v52,
          v51,
          v50,
          v82,
          v81,
          v80,
          v79,
          v110);
      }
      v110 = *((_DWORD *)this + 624) + *((_DWORD *)this + 18);
      v95 = CVssGlobalSnapshotSetId::GetID(&v132)->Data4[7];
      v98 = CVssGlobalSnapshotSetId::GetID(&v112)->Data4[6];
      v101 = CVssGlobalSnapshotSetId::GetID(&v114)->Data4[5];
      v105 = CVssGlobalSnapshotSetId::GetID(&v134)->Data4[4];
      v30 = CVssGlobalSnapshotSetId::GetID(&v135)->Data4[3];
      v31 = CVssGlobalSnapshotSetId::GetID(&v136)->Data4[2];
      v32 = CVssGlobalSnapshotSetId::GetID(&v137)->Data4[1];
      v33 = CVssGlobalSnapshotSetId::GetID(&v138)->Data4[0];
      v34 = CVssGlobalSnapshotSetId::GetID(&v139)->Data3;
      v35 = CVssGlobalSnapshotSetId::GetID(&v140)->Data2;
      v36 = CVssGlobalSnapshotSetId::GetID(&v141)->Data1;
      v37 = *(struct _GUID *)CVssSimpleMap<_GUID,ATL::CComPtr<IVssSnapshotProvider>>::GetKeyAt(v113 + 11, v108);
      v38 = CVssDebugInfo::CVssDebugInfo(
              &v124,
              L"base\\stor\\vss\\modules\\coord\\src\\snap_set.cxx",
              L"CORSNPSC",
              L"CVssSnapshotSetObject::ThawWriters",
              1351,
              1);
      v144 = v37;
      LODWORD(v91) = v35;
      LODWORD(v87) = v36;
      CVssFunctionTracer::TranslateProviderError(
        &v142,
        v38,
        &v144,
        L"PostCommitSnapshots({%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x}, %ld)",
        v87,
        v91,
        v34,
        v33,
        v32,
        v31,
        v30,
        v105,
        v101,
        v98,
        v95,
        v110);
    }
    ATL::CComPtrBase<CVssFileShareProviderWrapper>::~CComPtrBase<CVssFileShareProviderWrapper>((__int64 *)v111);
  }
  v13 = *((_DWORD *)this + 26);
  while ( 1 )
  {
    v108 = --v13;
    if ( v13 < 0 )
      break;
    v14 = this[12][v13].lpVtbl;
    v111[0] = (BSTR)v14;
    if ( v14 )
      (*((void (__fastcall **)(struct IDispatchVtbl *))v14->QueryInterface + 1))(v14);
    v15 = (__int64 (__fastcall *)(struct IDispatchVtbl *, struct _GUID *))*((_QWORD *)v14->QueryInterface + 19);
    v112 = *CVssGlobalSnapshotSetId::GetID(&v123);
    v143 = v15(v14, &v112);
    if ( v143 < 0 )
    {
      LODWORD(bstrString) = *((_DWORD *)this + 624) + *((_DWORD *)this + 18);
      v104 = CVssGlobalSnapshotSetId::GetID(&v123)->Data4[7];
      v100 = CVssGlobalSnapshotSetId::GetID(&v141)->Data4[6];
      v97 = CVssGlobalSnapshotSetId::GetID(&v140)->Data4[5];
      v94 = CVssGlobalSnapshotSetId::GetID(&v139)->Data4[4];
      v21 = CVssGlobalSnapshotSetId::GetID(&v138)->Data4[3];
      v22 = CVssGlobalSnapshotSetId::GetID(&v137)->Data4[2];
      v23 = CVssGlobalSnapshotSetId::GetID(&v136)->Data4[1];
      v24 = CVssGlobalSnapshotSetId::GetID(&v135)->Data4[0];
      v25 = CVssGlobalSnapshotSetId::GetID(&v134)->Data3;
      v26 = CVssGlobalSnapshotSetId::GetID(&v132)->Data2;
      v27 = CVssGlobalSnapshotSetId::GetID(&v114)->Data1;
      v28 = *(struct _GUID *)CVssSimpleMap<_GUID,ATL::CComPtr<IVssSnapshotProvider>>::GetKeyAt(v113 + 11, v108);
      v29 = CVssDebugInfo::CVssDebugInfo(
              &v124,
              L"base\\stor\\vss\\modules\\coord\\src\\snap_set.cxx",
              L"CORSNPSC",
              L"CVssSnapshotSetObject::ThawWriters",
              1367,
              1);
      v144 = v28;
      LODWORD(v90) = v26;
      LODWORD(v86) = v27;
      CVssFunctionTracer::TranslateProviderError(
        &v142,
        v29,
        &v144,
        L"PreFinalCommitSnapshots({%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x}, %ld)",
        v86,
        v90,
        v25,
        v24,
        v23,
        v22,
        v21,
        v94,
        v97,
        v100,
        v104,
        (_DWORD)bstrString);
    }
    ATL::CComPtrBase<CVssFileShareProviderWrapper>::~CComPtrBase<CVssFileShareProviderWrapper>((__int64 *)v111);
  }
  if ( ((_BYTE)this[8] & 0x10) == 0 )
  {
    if ( !*((_BYTE *)this + 2540) && !this[201] )
      goto LABEL_51;
    ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, &byte_1400F9C88);
    if ( ((_BYTE)this[8] & 0x20) == 0 || v4 && v3 )
    {
      v18 = (ATL::CComBSTR *)CVssSnapshotSetObject::BuildDevicesString(this, v111);
      ATL::CComBSTR::operator=(&bstrString, v18);
      SysFreeString(v111[0]);
      v16 = bstrString;
      if ( !bstrString )
      {
        v39 = CVssDebugInfo::CVssDebugInfo(
                &v124,
                L"base\\stor\\vss\\modules\\coord\\src\\snap_set.cxx",
                L"CORSNPSC",
                L"CVssSnapshotSetObject::ThawWriters",
                1383,
                1);
        CVssFunctionTracer::Throw(&v142, v39, 2147942414LL, L"out of memory");
      }
    }
    else
    {
      v16 = bstrString;
    }
    *(_QWORD *)&v114.Data1 = 0;
    CVssCoordinatorCallback::Initialize(this[201], (struct IDispatch **)&v114);
    v112 = *CVssGlobalSnapshotSetId::GetID(&v123);
    v84 = v143;
    CVssDiag::RecordWriterEvent(this + 202, 1013, 1);
    v143 = ((__int64 (__fastcall *)(struct IDispatch *, OLECHAR *, _QWORD, OLECHAR *, int, struct _GUID *))this[10]->lpVtbl[1].AddRef)(
             this[10],
             v2,
             *(_QWORD *)&v114.Data1,
             v16,
             v84,
             &v112);
    v112 = *CVssGlobalSnapshotSetId::GetID(&v123);
    LODWORD(v85) = v143;
    CVssDiag::RecordWriterEvent(this + 202, 1013, 0);
    v124 = L"base\\stor\\vss\\modules\\coord\\src\\snap_set.cxx";
    v125 = L"CVssSnapshotSetObject::ThawWriters";
    v126 = L"CORSNPSC";
    v127 = 1407;
    v128 = 1;
    v129 = 255;
    v131 = 0x1000000;
    memset_0(v130, 0, sizeof(v130));
    CVssFunctionTracer::TranslateWriterReturnCode(&v142, &v124, L"PostSnapshot(%s)", v2, v85, &v112);
    ATL::CComPtrBase<CVssFileShareProviderWrapper>::~CComPtrBase<CVssFileShareProviderWrapper>((__int64 *)&v114);
    SysFreeString(v16);
  }
  if ( this[201] && (((_BYTE)this[8] & 0x20) == 0 || v4 && v3) )
    CVssSnapshotSetObject::RequesterPostSnapshot((CVssSnapshotSetObject *)this);
LABEL_51:
  v17 = *((_DWORD *)this + 26);
  while ( 1 )
  {
    v108 = --v17;
    if ( v17 < 0 )
      break;
    v19 = this[12][v17].lpVtbl;
    *(_QWORD *)&v114.Data1 = v19;
    if ( v19 )
      (*((void (__fastcall **)(struct IDispatchVtbl *))v19->QueryInterface + 1))(v19);
    v111[0] = *((BSTR *)v19->QueryInterface + 20);
    v20 = v4 && v3;
    v144 = *CVssGlobalSnapshotSetId::GetID(&v123);
    v143 = ((__int64 (__fastcall *)(struct IDispatchVtbl *, struct _GUID *, BOOL))v111[0])(v19, &v144, v20);
    if ( v143 < 0 )
    {
      LODWORD(bstrString) = *((_DWORD *)this + 624) + *((_DWORD *)this + 18);
      v106 = CVssGlobalSnapshotSetId::GetID(&v123)->Data4[7];
      v102 = CVssGlobalSnapshotSetId::GetID(&v141)->Data4[6];
      v99 = CVssGlobalSnapshotSetId::GetID(&v140)->Data4[5];
      v96 = CVssGlobalSnapshotSetId::GetID(&v139)->Data4[4];
      v40 = CVssGlobalSnapshotSetId::GetID(&v138)->Data4[3];
      v41 = CVssGlobalSnapshotSetId::GetID(&v137)->Data4[2];
      v42 = CVssGlobalSnapshotSetId::GetID(&v136)->Data4[1];
      v43 = CVssGlobalSnapshotSetId::GetID(&v135)->Data4[0];
      v44 = CVssGlobalSnapshotSetId::GetID(&v134)->Data3;
      v45 = CVssGlobalSnapshotSetId::GetID(&v132)->Data2;
      v46 = CVssGlobalSnapshotSetId::GetID((struct _GUID *)v111)->Data1;
      v47 = *(struct _GUID *)CVssSimpleMap<_GUID,ATL::CComPtr<IVssSnapshotProvider>>::GetKeyAt(v113 + 11, v108);
      v48 = CVssDebugInfo::CVssDebugInfo(
              &v124,
              L"base\\stor\\vss\\modules\\coord\\src\\snap_set.cxx",
              L"CORSNPSC",
              L"CVssSnapshotSetObject::ThawWriters",
              1420,
              1);
      v144 = v47;
      LODWORD(v92) = v45;
      LODWORD(v88) = v46;
      CVssFunctionTracer::TranslateProviderError(
        &v142,
        v48,
        &v144,
        L"PostFinalCommitSnapshots({%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x}, %ld)",
        v88,
        v92,
        v44,
        v43,
        v42,
        v41,
        v40,
        v96,
        v99,
        v102,
        v106,
        (_DWORD)bstrString);
    }
    ATL::CComPtrBase<CVssFileShareProviderWrapper>::~CComPtrBase<CVssFileShareProviderWrapper>((__int64 *)&v114);
  }
  SysFreeString(v2);
  CVssFunctionTracer::~CVssFunctionTracer(&v142);
}

```

## disassembly

```asm
0x14004500c  push    rbp
0x14004500e  push    rbx
0x14004500f  push    rsi
0x140045010  push    rdi
0x140045011  push    r12
0x140045013  push    r13
0x140045015  push    r14
0x140045017  push    r15
0x140045019  lea     rbp, [rsp-1E8h]
0x140045021  sub     rsp, 348h
0x140045028  mov     rax, cs:__security_cookie
0x14004502f  xor     rax, rsp
0x140045032  mov     [rbp+220h+var_50], rax
0x140045039  mov     r13, rcx
0x14004503c  mov     [rbp+220h+var_260], rcx
0x140045040  lea     rdi, aBaseStorVssMod; "base\\stor\\vss\\modules\\coord\\src\\s"...
0x140045047  mov     [rbp+220h+var_218], rdi
0x14004504b  lea     rsi, aCvsssnapshotse_38; "CVssSnapshotSetObject::ThawWriters"
0x140045052  mov     [rbp+220h+var_210], rsi
0x140045056  lea     r14, aCorsnpsc; "CORSNPSC"
0x14004505d  mov     [rbp+220h+var_208], r14
0x140045061  mov     [rbp+220h+var_200], 4DAh
0x140045068  mov     r15d, 1
0x14004506e  mov     [rbp+220h+var_1FC], r15d
0x140045072  mov     r12d, 0FFh
0x140045078  mov     [rbp+220h+var_1F8], r12d
0x14004507c  mov     [rbp+220h+var_178], 1000000h
0x140045086  xor     edx, edx; Val
0x140045088  lea     r8d, [r15+77h]; Size
0x14004508c  lea     rcx, [rbp+220h+var_1F0]; void *
0x140045090  call    memset_0
0x140045095  xor     r8d, r8d
0x140045098  lea     rdx, [rbp+220h+var_218]
0x14004509c  lea     rcx, [rbp+220h+var_D0]
0x1400450a3  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x1400450a8  nop
0x1400450a9  lea     rcx, [rbp+220h+var_170]; retstr
0x1400450b0  call    ?GetID@CVssGlobalSnapshotSetId@@SA?AU_GUID@@XZ; CVssGlobalSnapshotSetId::GetID(void)
0x1400450b5  movups  xmm0, xmmword ptr [rax]
0x1400450b8  movdqu  xmmword ptr [rbp+220h+var_60.Data1], xmm0
0x1400450c0  lea     rdx, [rbp+220h+var_60]; struct _GUID *
0x1400450c7  lea     rcx, [rbp+220h+var_160]; this
0x1400450ce  call    ??0CComBSTR@ATL@@QEAA@AEBU_GUID@@@Z; ATL::CComBSTR::CComBSTR(_GUID const &)
0x1400450d3  nop
0x1400450d4  mov     rbx, [rbp+220h+var_160]
0x1400450db  test    rbx, rbx
0x1400450de  jz      loc_140045BC9
0x1400450e4  mov     dl, r15b; bool
0x1400450e7  mov     rcx, r13; this
0x1400450ea  call    ?ThawKTM@CVssSnapshotSetObject@@AEAAX_N@Z; CVssSnapshotSetObject::ThawKTM(bool)
0x1400450ef  call    ?IsEventSystemPresent@CVssSKU@@SAHXZ; CVssSKU::IsEventSystemPresent(void)
0x1400450f4  test    eax, eax
0x1400450f6  jz      short loc_140045103
0x1400450f8  mov     dl, r15b; bool
0x1400450fb  mov     rcx, r13; this
0x1400450fe  call    ?ThawDTC@CVssSnapshotSetObject@@AEAAX_N@Z; CVssSnapshotSetObject::ThawDTC(bool)
0x140045103  test    byte ptr [r13+40h], 10h
0x140045108  jnz     loc_1400451F1
0x14004510e  lea     rdi, [r13+650h]
0x140045115  lea     rcx, [rbp+220h+var_288]; retstr
0x140045119  call    ?GetID@CVssGlobalSnapshotSetId@@SA?AU_GUID@@XZ; CVssGlobalSnapshotSetId::GetID(void)
0x14004511e  movups  xmm0, xmmword ptr [rax]
0x140045121  movdqu  xmmword ptr [rbp+220h+var_270.Data1], xmm0
0x140045126  lea     rax, [rbp+220h+var_270]
0x14004512a  mov     [rsp+380h+var_358], rax
0x14004512f  mov     eax, [rbp+220h+var_C8]
0x140045135  mov     dword ptr [rsp+380h+var_360], eax
0x140045139  mov     r8d, r15d
0x14004513c  mov     esi, 3F2h
0x140045141  mov     edx, esi
0x140045143  mov     rcx, rdi
0x140045146  call    ?RecordWriterEvent@CVssDiag@@QEAAXW4VSS_OPERATION@@KKJU_GUID@@@Z; CVssDiag::RecordWriterEvent(VSS_OPERATION,ulong,ulong,long,_GUID)
0x14004514b  mov     rcx, [r13+50h]
0x14004514f  mov     rax, [rcx]
0x140045152  mov     rdx, rbx
0x140045155  mov     rax, [rax+38h]
0x140045159  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004515e  mov     [rbp+220h+var_C8], eax
0x140045164  lea     rcx, [rbp+220h+var_288]; retstr
0x140045168  call    ?GetID@CVssGlobalSnapshotSetId@@SA?AU_GUID@@XZ; CVssGlobalSnapshotSetId::GetID(void)
0x14004516d  movups  xmm0, xmmword ptr [rax]
0x140045170  movdqu  xmmword ptr [rbp+220h+var_270.Data1], xmm0
0x140045175  lea     rax, [rbp+220h+var_270]
0x140045179  mov     [rsp+380h+var_358], rax
0x14004517e  mov     eax, [rbp+220h+var_C8]
0x140045184  mov     dword ptr [rsp+380h+var_360], eax
0x140045188  xor     r8d, r8d
0x14004518b  mov     edx, esi
0x14004518d  mov     rcx, rdi
0x140045190  call    ?RecordWriterEvent@CVssDiag@@QEAAXW4VSS_OPERATION@@KKJU_GUID@@@Z; CVssDiag::RecordWriterEvent(VSS_OPERATION,ulong,ulong,long,_GUID)
0x140045195  lea     rdi, aBaseStorVssMod; "base\\stor\\vss\\modules\\coord\\src\\s"...
0x14004519c  mov     [rbp+220h+var_218], rdi
0x1400451a0  lea     rsi, aCvsssnapshotse_38; "CVssSnapshotSetObject::ThawWriters"
0x1400451a7  mov     [rbp+220h+var_210], rsi
0x1400451ab  mov     [rbp+220h+var_208], r14
0x1400451af  mov     [rbp+220h+var_200], 50Ah
0x1400451b6  mov     [rbp+220h+var_1FC], r15d
0x1400451ba  mov     [rbp+220h+var_1F8], r12d
0x1400451be  mov     [rbp+220h+var_178], 1000000h
0x1400451c8  xor     edx, edx; Val
0x1400451ca  lea     r8d, [rdx+78h]; Size
0x1400451ce  lea     rcx, [rbp+220h+var_1F0]; void *
0x1400451d2  call    memset_0
0x1400451d7  mov     r9, rbx
0x1400451da  lea     r8, aThawS; "Thaw(%s)"
0x1400451e1  lea     rdx, [rbp+220h+var_218]
0x1400451e5  lea     rcx, [rbp+220h+var_D0]
0x1400451ec  call    ?TranslateWriterReturnCode@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBGZZ; CVssFunctionTracer::TranslateWriterReturnCode(CVssDebugInfo,ushort const *,...)
0x1400451f1  mov     r14d, r15d
0x1400451f4  test    byte ptr [r13+40h], 20h
0x1400451f9  jz      short loc_14004520A
0x1400451fb  test    dword ptr [r13+40h], 2400000h
0x140045203  jz      short loc_14004520A
0x140045205  mov     r12d, r15d
0x140045208  jmp     short loc_14004520D
0x14004520a  xor     r12d, r12d
0x14004520d  mov     [rbp+220h+var_218], rdi
0x140045211  mov     [rbp+220h+var_210], rsi
0x140045215  lea     rax, aCorsnpsc; "CORSNPSC"
0x14004521c  mov     [rbp+220h+var_208], rax
0x140045220  mov     [rbp+220h+var_200], 523h
0x140045227  mov     [rbp+220h+var_1FC], r15d
0x14004522b  mov     [rbp+220h+var_1F8], 0FFh
0x140045232  mov     [rbp+220h+var_178], 1000000h
0x14004523c  xor     edx, edx; Val
0x14004523e  lea     r8d, [rdx+78h]; Size
0x140045242  lea     rcx, [rbp+220h+var_1F0]; void *
0x140045246  call    memset_0
0x14004524b  lea     rax, aFalse; "FALSE"
0x140045252  lea     r15, aTrue; "TRUE"
0x140045259  mov     r9, r15
0x14004525c  test    r12d, r12d
0x14004525f  cmovz   r9, rax
0x140045263  lea     r8, aBisdiskmasknee; "bIsDiskMaskNeeded for ThawWriters = %s"
0x14004526a  lea     rdx, [rbp+220h+var_218]
0x14004526e  lea     rcx, [rbp+220h+var_D0]
0x140045275  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x14004527a  xor     esi, esi
0x14004527c  cmp     [r13+68h], esi
0x140045280  jbe     short loc_1400452DF
0x140045282  movsxd  rcx, esi
0x140045285  mov     rax, [r13+60h]
0x140045289  mov     rdi, [rax+rcx*8]
0x14004528d  mov     [rbp+220h+bstrString], rdi
0x140045291  test    rdi, rdi
0x140045294  jz      short loc_1400452A6
0x140045296  mov     rax, [rdi]
0x140045299  mov     rcx, rdi
0x14004529c  mov     rax, [rax+8]
0x1400452a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400452a5  nop
0x1400452a6  mov     [rbp+220h+var_29C], 0
0x1400452ad  mov     rax, [rdi]
0x1400452b0  lea     rdx, [rbp+220h+var_29C]
0x1400452b4  mov     rcx, rdi
0x1400452b7  mov     rax, [rax+108h]
0x1400452be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400452c3  and     r14d, [rbp+220h+var_29C]
0x1400452c7  lea     rcx, [rbp+220h+bstrString]
0x1400452cb  call    ??1?$CComPtrBase@VCVssFileShareProviderWrapper@@@ATL@@QEAA@XZ; ATL::CComPtrBase<CVssFileShareProviderWrapper>::~CComPtrBase<CVssFileShareProviderWrapper>(void)
0x1400452d0  inc     esi
0x1400452d2  cmp     esi, [r13+68h]
0x1400452d6  jb      short loc_140045282
0x1400452d8  lea     rdi, aBaseStorVssMod; "base\\stor\\vss\\modules\\coord\\src\\s"...
0x1400452df  mov     [rbp+220h+var_218], rdi
0x1400452e3  lea     rax, aCvsssnapshotse_38; "CVssSnapshotSetObject::ThawWriters"
0x1400452ea  mov     [rbp+220h+var_210], rax
0x1400452ee  lea     rax, aCorsnpsc; "CORSNPSC"
0x1400452f5  mov     [rbp+220h+var_208], rax
0x1400452f9  mov     [rbp+220h+var_200], 531h
0x140045300  mov     [rbp+220h+var_1FC], 1
0x140045307  mov     [rbp+220h+var_1F8], 0FFh
0x14004530e  mov     [rbp+220h+var_178], 1000000h
0x140045318  xor     edx, edx; Val
0x14004531a  lea     r8d, [rdx+78h]; Size
0x14004531e  lea     rcx, [rbp+220h+var_1F0]; void *
0x140045322  call    memset_0
0x140045327  test    r14d, r14d
0x14004532a  lea     rax, aFalse; "FALSE"
0x140045331  cmovz   r15, rax
0x140045335  mov     r9, r15
0x140045338  lea     r8, aBisdiskmaskpos; "bIsDiskMaskPossible for ThawWriters = %"...
0x14004533f  lea     rdx, [rbp+220h+var_218]
0x140045343  lea     rcx, [rbp+220h+var_D0]
0x14004534a  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x14004534f  mov     esi, [r13+68h]
0x140045353  jmp     short loc_1400453C1
0x140045355  movsxd  rcx, esi
0x140045358  mov     rax, [r13+60h]
0x14004535c  mov     rdi, [rax+rcx*8]
0x140045360  mov     [rbp+220h+var_288], rdi
0x140045364  test    rdi, rdi
0x140045367  jz      short loc_140045379
0x140045369  mov     rax, [rdi]
0x14004536c  mov     rcx, rdi
0x14004536f  mov     rax, [rax+8]
0x140045373  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045378  nop
0x140045379  mov     rax, [rdi]
0x14004537c  test    r12d, r12d
0x14004537f  jz      short loc_14004538E
0x140045381  test    r14d, r14d
0x140045384  jz      short loc_14004538E
0x140045386  mov     r9d, 1
0x14004538c  jmp     short loc_140045391
0x14004538e  xor     r9d, r9d
0x140045391  lea     r8, [r13+630h]
0x140045398  mov     rdx, [r13+648h]
0x14004539f  mov     rcx, rdi
0x1400453a2  mov     rax, [rax+0A8h]
0x1400453a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400453ae  mov     [rbp+220h+var_C8], eax
0x1400453b4  test    eax, eax
0x1400453b6  js      short loc_1400453D2
0x1400453b8  lea     rcx, [rbp+220h+var_288]
0x1400453bc  call    ??1?$CComPtrBase@VCVssFileShareProviderWrapper@@@ATL@@QEAA@XZ; ATL::CComPtrBase<CVssFileShareProviderWrapper>::~CComPtrBase<CVssFileShareProviderWrapper>(void)
0x1400453c1  sub     esi, 1
0x1400453c4  mov     [rbp+220h+var_29C], esi
0x1400453c7  jns     short loc_140045355
0x1400453c9  mov     r15d, [r13+68h]
0x1400453cd  jmp     loc_140045460
0x1400453d2  cmp     eax, 80042320h
0x1400453d7  jz      loc_140045C05
0x1400453dd  cmp     eax, 80042306h
0x1400453e2  jz      loc_140045C05
0x1400453e8  add     eax, 7FFBDC08h
0x1400453ed  cmp     eax, 4
0x1400453f0  ja      loc_14004588C
0x1400453f6  jmp     loc_140045C05
0x1400453fb  movsxd  rcx, r15d
0x1400453fe  mov     rax, [r13+60h]
0x140045402  mov     rsi, [rax+rcx*8]
0x140045406  mov     [rbp+220h+var_288], rsi
0x14004540a  test    rsi, rsi
0x14004540d  jz      short loc_14004541F
0x14004540f  mov     rax, [rsi]
0x140045412  mov     rcx, rsi
0x140045415  mov     rax, [rax+8]
0x140045419  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004541e  nop
0x14004541f  mov     rax, [rsi]
0x140045422  mov     rdi, [rax+98h]
0x140045429  lea     rcx, [rbp+220h+var_228]; retstr
0x14004542d  call    ?GetID@CVssGlobalSnapshotSetId@@SA?AU_GUID@@XZ; CVssGlobalSnapshotSetId::GetID(void)
0x140045432  movups  xmm0, xmmword ptr [rax]
0x140045435  movdqu  xmmword ptr [rbp+220h+var_270.Data1], xmm0
0x14004543a  lea     rdx, [rbp+220h+var_270]
0x14004543e  mov     rcx, rsi
0x140045441  mov     rax, rdi
0x140045444  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045449  mov     [rbp+220h+var_C8], eax
0x14004544f  test    eax, eax
0x140045451  js      loc_140045713
0x140045457  lea     rcx, [rbp+220h+var_288]
0x14004545b  call    ??1?$CComPtrBase@VCVssFileShareProviderWrapper@@@ATL@@QEAA@XZ; ATL::CComPtrBase<CVssFileShareProviderWrapper>::~CComPtrBase<CVssFileShareProviderWrapper>(void)
0x140045460  sub     r15d, 1
0x140045464  mov     [rbp+220h+var_29C], r15d
0x140045468  jns     short loc_1400453FB
0x14004546a  test    byte ptr [r13+40h], 10h
0x14004546f  jnz     loc_1400455E4
0x140045475  cmp     byte ptr [r13+9ECh], 0
0x14004547d  jnz     short loc_14004548D
0x14004547f  cmp     qword ptr [r13+648h], 0
0x140045487  jz      loc_140045607
0x14004548d  lea     rdx, byte_1400F9C88; unsigned __int16 *
0x140045494  lea     rcx, [rbp+220h+bstrString]; this
0x140045498  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x14004549d  nop
0x14004549e  test    byte ptr [r13+40h], 20h
0x1400454a3  jz      loc_140045610
0x1400454a9  test    r12d, r12d
0x1400454ac  jz      short loc_1400454B7
0x1400454ae  test    r14d, r14d
0x1400454b1  jnz     loc_140045610
0x1400454b7  mov     rdi, [rbp+220h+bstrString]
0x1400454bb  mov     qword ptr [rbp+220h+var_258.Data1], 0
0x1400454c3  lea     rdx, [rbp+220h+var_258]; struct IDispatch **
0x1400454c7  mov     rcx, [r13+648h]; struct IDispatch *
0x1400454ce  call    ?Initialize@CVssCoordinatorCallback@@SAXPEAUIDispatch@@PEAPEAU2@@Z; CVssCoordinatorCallback::Initialize(IDispatch *,IDispatch * *)
0x1400454d3  lea     rsi, [r13+650h]
0x1400454da  lea     rcx, [rbp+220h+var_228]; retstr
0x1400454de  call    ?GetID@CVssGlobalSnapshotSetId@@SA?AU_GUID@@XZ; CVssGlobalSnapshotSetId::GetID(void)
0x1400454e3  movups  xmm0, xmmword ptr [rax]
0x1400454e6  movdqu  xmmword ptr [rbp+220h+var_270.Data1], xmm0
0x1400454eb  lea     rax, [rbp+220h+var_270]
0x1400454ef  mov     [rsp+380h+var_358], rax
0x1400454f4  mov     eax, [rbp+220h+var_C8]
0x1400454fa  mov     dword ptr [rsp+380h+var_360], eax
0x1400454fe  mov     r8d, 1
0x140045504  mov     r15d, 3F5h
0x14004550a  mov     edx, r15d
0x14004550d  mov     rcx, rsi
0x140045510  call    ?RecordWriterEvent@CVssDiag@@QEAAXW4VSS_OPERATION@@KKJU_GUID@@@Z; CVssDiag::RecordWriterEvent(VSS_OPERATION,ulong,ulong,long,_GUID)
0x140045515  mov     rcx, [r13+50h]
0x140045519  mov     rax, [rcx]
0x14004551c  mov     r9, rdi
0x14004551f  mov     r8, qword ptr [rbp+220h+var_258.Data1]
0x140045523  mov     rdx, rbx
0x140045526  mov     rax, [rax+40h]
0x14004552a  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
