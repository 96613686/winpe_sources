# CAgentUpdateManager::AssembleDependentSetBundleIfNeeded(CExpressionManager *,ulong,CUpdateDetectInfoList &,ISusCancellable const *,_GUID const &,wchar_t const *,ulong *,int *)

- ea: `0x1800295a8`
- end: `0x18002aed4`
- name: `?AssembleDependentSetBundleIfNeeded@CAgentUpdateManager@@AEAAJPEAVCExpressionManager@@KAEAVCUpdateDetectInfoList@@PEBUISusCancellable@@AEBU_GUID@@PEB_WPEAKPEAH@Z`
- size: `6444`
- prototype: `__int64 __fastcall(CAgentUpdateManager *__hidden this, struct CExpressionManager *, unsigned int, struct CUpdateDetectInfoList *, const struct ISusCancellable *, const struct _GUID *, const wchar_t *, unsigned int *, int *)`
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18002e560`

## callees

- `0x18000c824`
- `0x180015c98`
- `0x180019068`
- `0x18001d850`
- `0x180023e64`
- `0x180029294`
- `0x1800295a8`
- `0x180033adc`
- `0x180034798`
- `0x18003a6c4`
- `0x180113ae8`
- `0x180113b9c`
- `0x18012b618`
- `0x18012bed4`
- `0x180132004`
- `0x1801326e8`
- `0x180133a10`
- `0x18017e4c4`
- `0x1801c1010`
- `0x180238960`
- `0x180240cc0`
- `0x180240d40`
- `0x180241780`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180029bcc`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180029bcc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002addc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002addc`
- `RPCRT4!RpcStringFreeW` at `0x18002a45b`
- `RPCRT4!RpcStringFreeW` at `0x18002a594`
- `RPCRT4!RpcStringFreeW` at `0x18002a61d`
- `RPCRT4!RpcStringFreeW` at `0x18002a860`
- `RPCRT4!RpcStringFreeW` at `0x18002adc7`
- `RPCRT4!RpcStringFreeW` at `0x18002a45b`
- `RPCRT4!RpcStringFreeW` at `0x18002a594`
- `RPCRT4!RpcStringFreeW` at `0x18002a61d`
- `RPCRT4!RpcStringFreeW` at `0x18002a860`
- `RPCRT4!RpcStringFreeW` at `0x18002adc7`
- `RPCRT4!UuidToStringW` at `0x18002a3dc`
- `RPCRT4!UuidToStringW` at `0x18002a543`
- `RPCRT4!UuidToStringW` at `0x18002a5cc`
- `RPCRT4!UuidToStringW` at `0x18002a743`
- `RPCRT4!UuidToStringW` at `0x18002a3dc`
- `RPCRT4!UuidToStringW` at `0x18002a543`
- `RPCRT4!UuidToStringW` at `0x18002a5cc`
- `RPCRT4!UuidToStringW` at `0x18002a743`
- `OLEAUT32!__imp_SysAllocString` at `0x180029a69`
- `OLEAUT32!__imp_SysAllocString` at `0x180029aa5`
- `OLEAUT32!__imp_SysAllocString` at `0x180029ae1`
- `OLEAUT32!__imp_SysAllocString` at `0x18002a952`
- `OLEAUT32!__imp_SysAllocString` at `0x18002a9e2`
- `OLEAUT32!__imp_SysAllocString` at `0x18002a9f6`
- `OLEAUT32!__imp_SysAllocString` at `0x18002aa1b`
- `OLEAUT32!__imp_SysAllocString` at `0x18002aa2b`
- `OLEAUT32!__imp_SysAllocString` at `0x18002aa3b`
- `OLEAUT32!__imp_SysAllocString` at `0x18002aa4b`
- `OLEAUT32!__imp_SysAllocString` at `0x18002aa5f`
- `OLEAUT32!__imp_SysAllocString` at `0x18002aa73`
- `OLEAUT32!__imp_SysAllocString` at `0x180029a69`
- `OLEAUT32!__imp_SysAllocString` at `0x180029aa5`
- `OLEAUT32!__imp_SysAllocString` at `0x180029ae1`
- `OLEAUT32!__imp_SysAllocString` at `0x18002a952`
- `OLEAUT32!__imp_SysAllocString` at `0x18002a9e2`
- `OLEAUT32!__imp_SysAllocString` at `0x18002a9f6`
- `OLEAUT32!__imp_SysAllocString` at `0x18002aa1b`
- `OLEAUT32!__imp_SysAllocString` at `0x18002aa2b`
- `OLEAUT32!__imp_SysAllocString` at `0x18002aa3b`
- `OLEAUT32!__imp_SysAllocString` at `0x18002aa4b`
- `OLEAUT32!__imp_SysAllocString` at `0x18002aa5f`
- `OLEAUT32!__imp_SysAllocString` at `0x18002aa73`
- `OLEAUT32!__imp_SysFreeString` at `0x180029a54`
- `OLEAUT32!__imp_SysFreeString` at `0x180029a90`
- `OLEAUT32!__imp_SysFreeString` at `0x180029ac9`
- `OLEAUT32!__imp_SysFreeString` at `0x18002a949`
- `OLEAUT32!__imp_SysFreeString` at `0x18002ae62`
- `OLEAUT32!__imp_SysFreeString` at `0x18002ae6c`
- `OLEAUT32!__imp_SysFreeString` at `0x18002ae76`
- `OLEAUT32!__imp_SysFreeString` at `0x18002ae7f`
- `OLEAUT32!__imp_SysFreeString` at `0x180029a54`
- `OLEAUT32!__imp_SysFreeString` at `0x180029a90`
- `OLEAUT32!__imp_SysFreeString` at `0x180029ac9`
- `OLEAUT32!__imp_SysFreeString` at `0x18002a949`
- `OLEAUT32!__imp_SysFreeString` at `0x18002ae62`
- `OLEAUT32!__imp_SysFreeString` at `0x18002ae6c`
- `OLEAUT32!__imp_SysFreeString` at `0x18002ae76`
- `OLEAUT32!__imp_SysFreeString` at `0x18002ae7f`
- `OLEAUT32!__imp_SysStringLen` at `0x180029b9f`
- `OLEAUT32!__imp_SysStringLen` at `0x180029baf`
- `OLEAUT32!__imp_SysStringLen` at `0x180029b9f`
- `OLEAUT32!__imp_SysStringLen` at `0x180029baf`

## string_xrefs

- `0x1800297ec`: `AssembleDependentSetBundleIfNeeded evaluating update, pass %d, UpdateId = {%ws}.%d`
- `0x180029864`: `AssembleDependentSetBundleIfNeeded selecting current parent update, UpdateId = {%ws}.%d`
- `0x180029992`: `AssembleDependentSetBundleIfNeeded detected important update`
- `0x180029c1f`: ` Dependent set child update has new target group ID; will need to expire existing parent set`
- `0x180029bf8`: ` Dependent set child update has new targeting version; will need to expire existing parent set`
- `0x18002a19d`: ` existing IDP parent contains all %d IDP child updates in correct order`
- `0x18002a8e7`: ` Final dependent set XML: %ws`
- `0x18002ab7f`: ` fail to parse and add dependent set updates with error %#lx`
- `0x18002aba0`: ` dependent set bundle successfully created`
- `0x18002ac59`: ` fail to expire old dependent set update with error %#lx; continuing`
- `0x18002acc0`: ` fail to unhide dependent set updates with error %#lx`
- `0x18002ae2f`: ` AssembleDependentSetBundleIfNeeded complete, hr=%#lx`
- `0x18002a8c0`: `</AtLeastOne></BundledUpdates></Relationships><Files />`
- `0x18002a6f9`: `<UpdateIdentity UpdateID="`
- `0x18002a671`: `</Prerequisites><BundledUpdates><AtLeastOne IsCategory="false">`
- `0x18002a515`: `<UpdateIdentity UpdateID="%s" />`
- `0x18002a5a7`: `<UpdateIdentity UpdateID="%s" />`
- `0x18002a422`: `<UpdateIdentity UpdateID="%s" RevisionNumber="%d" /><Properties UpdateType="Software" ExplicitlyDeployable="true" AutoSelectOnWebSites="%s" />`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CAgentUpdateManager::AssembleDependentSetBundleIfNeeded(
        CAgentUpdateManager *this,
        struct CExpressionManager *a2,
        unsigned int a3,
        struct CUpdateDetectInfoList *a4,
        const struct ISusCancellable *a5,
        const struct _GUID *a6,
        const wchar_t *a7,
        unsigned int *a8,
        int *a9)
{
  int v9; // eax
  wchar_t *v10; // rbx
  OLECHAR *lpString2; // rdi
  OLECHAR *v12; // rsi
  OLECHAR *v13; // r14
  int v14; // r15d
  UUID v15; // xmm7
  struct tagDSUpdateMetadata *v16; // r12
  unsigned int v17; // ecx
  int v18; // r13d
  unsigned int v19; // eax
  unsigned int v20; // edx
  __int64 v21; // r12
  bool v22; // zf
  __int64 v23; // r12
  int v24; // r15d
  __int64 v25; // rax
  int v26; // r15d
  __int64 v27; // rax
  int v28; // r8d
  int v29; // eax
  const OLECHAR *v30; // r15
  const OLECHAR *v31; // r15
  const OLECHAR *v32; // r15
  struct _GUID *v33; // r15
  __int64 v34; // rax
  unsigned __int64 v35; // xmm7_8
  unsigned __int64 v36; // rax
  const WCHAR *v37; // r15
  UINT cchCount2; // eax
  bool v39; // cl
  __int64 v40; // rax
  __int64 v41; // rax
  struct tagDSGuidArray *v42; // r15
  __int64 v43; // r15
  __int64 v44; // rax
  unsigned int v45; // r11d
  struct _GUID *v46; // rax
  const struct _GUID *v47; // r12
  int v48; // eax
  unsigned int v49; // r10d
  __int64 v50; // r12
  _DWORD *v51; // r9
  int v52; // r8d
  __int64 v53; // rcx
  __int64 v54; // rdx
  __m128i v55; // xmm6
  __int64 v56; // rax
  int v57; // r15d
  __int64 v58; // rax
  int v59; // eax
  unsigned int v60; // r15d
  __int64 v61; // rax
  char *v62; // r8
  int v63; // eax
  struct tagDSGuidArray *v64; // rax
  int v65; // eax
  unsigned int v66; // r12d
  unsigned int v67; // r8d
  struct tagDSGuidArray *v68; // rbx
  unsigned int v69; // r15d
  unsigned int v70; // r12d
  unsigned __int64 v71; // r15
  const wchar_t *v72; // rax
  unsigned int v73; // r15d
  int v74; // r15d
  unsigned int v75; // ecx
  unsigned int v76; // r12d
  struct _GUID *v77; // rdx
  _DWORD *v78; // rax
  int v79; // eax
  BSTR v80; // rax
  int v81; // eax
  const OLECHAR *v82; // rcx
  OLECHAR *v83; // rax
  OLECHAR *v84; // rax
  OLECHAR *v85; // rax
  struct CUpdateDetectInfoList *v86; // r15
  int v87; // eax
  int v88; // r9d
  int v89; // eax
  unsigned int v90; // r8d
  unsigned int v91; // edx
  int v92; // ebx
  unsigned __int64 v93; // rdi
  __int64 v94; // rsi
  int v95; // r14d
  __int64 v96; // rcx
  unsigned __int64 *v98; // [rsp+38h] [rbp-E0h]
  __int64 v99; // [rsp+40h] [rbp-D8h]
  __int64 v100; // [rsp+40h] [rbp-D8h]
  __int64 v101; // [rsp+48h] [rbp-D0h]
  wchar_t *v102; // [rsp+98h] [rbp-80h] BYREF
  unsigned __int64 v103; // [rsp+A0h] [rbp-78h] BYREF
  char *v104; // [rsp+A8h] [rbp-70h]
  int v105; // [rsp+B0h] [rbp-68h]
  struct tagDSGuidArray *v106; // [rsp+B8h] [rbp-60h]
  struct _GUID *v107; // [rsp+C0h] [rbp-58h]
  struct CUpdateDetectInfoList *v108; // [rsp+C8h] [rbp-50h]
  int v109; // [rsp+D0h] [rbp-48h]
  int v110; // [rsp+D4h] [rbp-44h]
  int v111; // [rsp+D8h] [rbp-40h]
  char *v112; // [rsp+E0h] [rbp-38h] BYREF
  int v113; // [rsp+E8h] [rbp-30h]
  int v114; // [rsp+ECh] [rbp-2Ch]
  unsigned int v115; // [rsp+F0h] [rbp-28h]
  __int64 Data1; // [rsp+F8h] [rbp-20h]
  const struct _GUID *v117; // [rsp+100h] [rbp-18h]
  unsigned __int64 v118; // [rsp+108h] [rbp-10h]
  __int64 v119; // [rsp+110h] [rbp-8h]
  OLECHAR *v120; // [rsp+118h] [rbp+0h]
  OLECHAR *v121; // [rsp+120h] [rbp+8h]
  OLECHAR *v122; // [rsp+128h] [rbp+10h]
  CAgentUpdateManager *v123; // [rsp+130h] [rbp+18h]
  BSTR v124; // [rsp+138h] [rbp+20h]
  const wchar_t *v125; // [rsp+140h] [rbp+28h]
  const struct ISusCancellable *v126; // [rsp+148h] [rbp+30h]
  struct CExpressionManager *v127; // [rsp+150h] [rbp+38h]
  wchar_t *v128; // [rsp+158h] [rbp+40h]
  unsigned int *v129; // [rsp+160h] [rbp+48h]
  int *v130; // [rsp+168h] [rbp+50h]
  _BYTE v131[80]; // [rsp+178h] [rbp+60h] BYREF
  _BYTE v132[80]; // [rsp+1C8h] [rbp+B0h] BYREF
  unsigned int v133[2]; // [rsp+218h] [rbp+100h] BYREF
  RPC_WSTR StringUuid; // [rsp+220h] [rbp+108h] BYREF
  wchar_t *v135; // [rsp+228h] [rbp+110h] BYREF
  __int64 v136; // [rsp+230h] [rbp+118h] BYREF
  LPVOID pv[2]; // [rsp+238h] [rbp+120h] BYREF
  wchar_t v138[136]; // [rsp+248h] [rbp+130h] BYREF
  int v139; // [rsp+358h] [rbp+240h] BYREF
  FILETIME FileTime; // [rsp+360h] [rbp+248h] BYREF
  UUID Uuid; // [rsp+368h] [rbp+250h] BYREF
  int v142; // [rsp+378h] [rbp+260h]
  void **v143; // [rsp+380h] [rbp+268h] BYREF
  __int64 v144; // [rsp+388h] [rbp+270h]
  __int128 v145; // [rsp+390h] [rbp+278h]
  void **v146; // [rsp+3A0h] [rbp+288h] BYREF
  __int64 v147; // [rsp+3A8h] [rbp+290h]
  __int128 v148; // [rsp+3B0h] [rbp+298h]
  struct _GUID v149; // [rsp+3C0h] [rbp+2A8h] BYREF
  __int64 v150; // [rsp+3D0h] [rbp+2B8h]
  _BYTE Buf2[22]; // [rsp+3D8h] [rbp+2C0h] BYREF
  wchar_t Buffer; // [rsp+3F0h] [rbp+2D8h] BYREF
  __int128 v153; // [rsp+3F2h] [rbp+2DAh]
  int v154; // [rsp+402h] [rbp+2EAh]

  v108 = a4;
  v115 = a3;
  v127 = a2;
  v123 = this;
  v126 = a5;
  v117 = a6;
  v125 = a7;
  v129 = a8;
  v130 = a9;
  v9 = *((_DWORD *)a4 + 5);
  LODWORD(v102) = v9;
  v144 = 0;
  v145 = 0u;
  v143 = &CSusSortedArrayList<CSusMap<_GUID,CUpdateDetectInfo *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpNoop<CUpdateDetectInfo *>>::_tagMapEntry,CSusMap<_GUID,CUpdateDetectInfo *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpNoop<CUpdateDetectInfo *>>::CMapEntryOps>::`vftable';
  v107 = 0;
  v10 = 0;
  v128 = 0;
  v124 = 0;
  lpString2 = 0;
  v120 = 0;
  v12 = 0;
  v121 = 0;
  v13 = 0;
  v122 = 0;
  StringUuid = 0;
  Buffer = 0;
  v153 = 0;
  v154 = 0;
  v113 = 0;
  v114 = 0;
  v109 = 0;
  FileTime = 0;
  v111 = 0;
  v110 = 0;
  v14 = 0;
  v105 = 0;
  v139 = 0;
  v15 = 0;
  v149 = 0;
  Data1 = 0;
  memset(Buf2, 0, 20);
  Uuid = 0;
  v142 = 0;
  v133[0] = 0;
  pv[0] = 0;
  v16 = 0;
  v104 = 0;
  v106 = 0;
  v136 = 0;
  v147 = 0;
  v148 = 0u;
  v146 = &CSusSortedArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>>::`vftable';
  if ( !a8 || !a5 )
  {
    v18 = -2147467261;
    goto LABEL_203;
  }
  if ( a9 )
    *a9 = 0;
  v17 = 0;
  LODWORD(v103) = 0;
  v118 = *(_QWORD *)&Buf2[8];
  v119 = *(_QWORD *)Buf2;
  do
  {
    LODWORD(v135) = 0;
    v18 = 0;
    if ( v9 )
    {
      v19 = 0;
      v20 = (unsigned int)v102;
      while ( 1 )
      {
        v18 = 0;
        if ( v19 < *((_DWORD *)a4 + 5) )
          break;
LABEL_65:
        LODWORD(v135) = ++v19;
        if ( v19 >= v20 )
        {
          v9 = (int)v102;
          goto LABEL_67;
        }
      }
      v21 = 1048LL * (unsigned int)v135;
      v22 = *((_QWORD *)a4 + 1) + v21 == 0;
      v23 = *((_QWORD *)a4 + 1) + v21;
      v112 = (char *)v23;
      if ( !v22 )
      {
        v24 = *(_DWORD *)(v23 + 16);
        v25 = Trace::GuidToString::GuidToString((Trace::GuidToString *)v131, (const struct _GUID *)v23);
        LODWORD(v101) = v24;
        LODWORD(v98) = v103;
        WUTrace(
          0,
          0,
          1,
          5,
          0,
          L"AssembleDependentSetBundleIfNeeded evaluating update, pass %d, UpdateId = {%ws}.%d",
          v98,
          v25,
          v101);
        v17 = v103;
        v18 = 0;
        if ( (_DWORD)v103 )
        {
          if ( (_DWORD)v103 == 1 && *(_DWORD *)(v23 + 816) == 1 )
          {
            v18 = CSusMap<_GUID,CSusSortedArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>> *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpDelete<CSusSortedArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>> *>>::Add(
                    &v143,
                    v23,
                    &v112);
            if ( v18 < 0 )
              goto LABEL_128;
            v23 = (__int64)v112;
            v29 = *((_DWORD *)v112 + 68);
            if ( (v29 & 0x80u) == 0 )
            {
              if ( (v29 & 0x40) != 0 )
              {
                WUTrace(0, 0, 1, 5, 0, L"AssembleDependentSetBundleIfNeeded detected auto firmware");
                v113 = 1;
              }
            }
            else
            {
              WUTrace(0, 0, 1, 5, 0, L"AssembleDependentSetBundleIfNeeded detected UX firmware");
              v114 = 1;
            }
            if ( *(_DWORD *)(v23 + 760) )
            {
              WUTrace(0, 0, 1, 5, 0, L"AssembleDependentSetBundleIfNeeded detected important update");
              v109 = 1;
            }
            if ( !FileTime.dwLowDateTime && !FileTime.dwHighDateTime
              || (int)TimeDiff(&FileTime, (const struct _FILETIME *)(v23 + 744), v28) > 0 )
            {
              if ( (int)FileTimeToString(v138, 0x80u, (FILETIME *)(v23 + 744)) >= 0 )
                WUTrace(
                  0,
                  0,
                  1,
                  5,
                  0,
                  L"AssembleDependentSetBundleIfNeeded found new earliest deployment time: %ws",
                  v138);
              FileTime = *(FILETIME *)(v23 + 744);
            }
            v30 = *(const OLECHAR **)(v23 + 824);
            SysFreeString(lpString2);
            lpString2 = 0;
            v120 = 0;
            if ( v30 )
            {
              lpString2 = SysAllocString(v30);
              v120 = lpString2;
              if ( !lpString2 )
                goto LABEL_70;
            }
            v31 = *(const OLECHAR **)(v23 + 832);
            SysFreeString(v12);
            v12 = 0;
            v121 = 0;
            if ( v31 )
            {
              v12 = SysAllocString(v31);
              v121 = v12;
              if ( !v12 )
                goto LABEL_70;
            }
            v32 = *(const OLECHAR **)(v23 + 848);
            SysFreeString(v13);
            v13 = 0;
            v122 = 0;
            if ( v32 )
            {
              v13 = SysAllocString(v32);
              v122 = v13;
              if ( !v13 )
              {
LABEL_70:
                v18 = -2147024882;
                goto LABEL_71;
              }
            }
            v18 = 0;
            v33 = (struct _GUID *)(v23 + 800);
            if ( *(_QWORD *)(v23 + 800) == *(_QWORD *)&GUID_NULL.Data1
              && *(_QWORD *)(v23 + 808) == *(_QWORD *)GUID_NULL.Data4 )
            {
              WUTrace(0, 0, 1, 1, 0, L" Found dependent set child with NULL target group");
              goto LABEL_73;
            }
            v34 = *(_QWORD *)&v15.Data1;
            v35 = _mm_srli_si128((__m128i)v15, 8).m128i_u64[0];
            if ( v34 != *(_QWORD *)&GUID_NULL.Data1 || v35 != *(_QWORD *)GUID_NULL.Data4 )
            {
              v36 = v34 - *(_QWORD *)&v33->Data1;
              if ( !v36 )
                v36 = v35 - *(_QWORD *)(v23 + 808);
              if ( v36 )
              {
                v43 = Trace::GuidToString::GuidToString((Trace::GuidToString *)v131, (const struct _GUID *)(v23 + 800));
                v44 = Trace::GuidToString::GuidToString((Trace::GuidToString *)v132, &v149);
                WUTrace(0, 0, 1, 1, 0, L" Found two active dependent set target groups: %ws and %ws", v44, v43);
                goto LABEL_73;
              }
            }
            v15 = *v33;
            v149 = *v33;
            if ( v142 )
              goto LABEL_15;
            if ( *(_QWORD *)&v33->Data1 == v119 && *(_QWORD *)(v23 + 808) == v118 )
            {
              if ( !v107 )
                goto LABEL_15;
              v37 = *(const WCHAR **)v107[51].Data4;
              if ( lpString2 && SysStringLen(lpString2) )
              {
                cchCount2 = SysStringLen(lpString2);
                v39 = CompareStringW(0x400u, 0, v37, -1, lpString2, cchCount2) != 2;
              }
              else if ( !v37 || (v39 = 1, !*v37) )
              {
                v39 = 0;
              }
              if ( !v39 )
                goto LABEL_15;
              WUTrace(
                0,
                0,
                1,
                5,
                0,
                L" Dependent set child update has new targeting version; will need to expire existing parent set");
            }
            else
            {
              WUTrace(
                0,
                0,
                1,
                5,
                0,
                L" Dependent set child update has new target group ID; will need to expire existing parent set");
              v40 = Trace::GuidToString::GuidToString((Trace::GuidToString *)v131, (const struct _GUID *)Buf2);
              WUTrace(0, 0, 1, 5, 0, L"   Previous target group: %ws", v40);
              v41 = Trace::GuidToString::GuidToString((Trace::GuidToString *)v131, (const struct _GUID *)(v23 + 800));
              WUTrace(0, 0, 1, 5, 0, L"   New target group: %ws", v41);
            }
            Uuid = v15;
            v142 = Data1 + 1;
            v14 = 1;
            v105 = 1;
LABEL_16:
            v17 = v103;
            v20 = (unsigned int)v102;
            a4 = v108;
            if ( *(_DWORD *)(v23 + 120) == 2 )
              v110 = 1;
            else
              v111 = 1;
            goto LABEL_64;
          }
        }
        else if ( *(_DWORD *)(v23 + 820) == 1 )
        {
          if ( !v107 || *(_DWORD *)(v23 + 16) > v107[1].Data1 )
          {
            v26 = *(_DWORD *)(v23 + 16);
            v27 = Trace::GuidToString::GuidToString((Trace::GuidToString *)v131, (const struct _GUID *)v23);
            LODWORD(v99) = v26;
            WUTrace(
              0,
              0,
              1,
              5,
              0,
              L"AssembleDependentSetBundleIfNeeded selecting current parent update, UpdateId = {%ws}.%d",
              v27,
              v99);
            *(_OWORD *)Buf2 = *(_OWORD *)v23;
            Data1 = *(unsigned int *)(v23 + 16);
            *(_DWORD *)&Buf2[16] = Data1;
            v107 = (struct _GUID *)v23;
            v18 = 0;
            v118 = *(_QWORD *)(v23 + 8);
            v119 = *(_QWORD *)Buf2;
LABEL_15:
            v14 = v105;
            goto LABEL_16;
          }
          v14 = v105;
          v20 = (unsigned int)v102;
          a4 = v108;
          goto LABEL_63;
        }
        v14 = v105;
        v20 = (unsigned int)v102;
        a4 = v108;
LABEL_64:
        v19 = (unsigned int)v135;
        goto LABEL_65;
      }
LABEL_63:
      v17 = v103;
      goto LABEL_64;
    }
LABEL_67:
    LODWORD(v103) = ++v17;
  }
  while ( v17 < 2 );
  if ( !DWORD1(v145) )
  {
    WUTrace(0, 0, 1, 5, 0, L" No IDP children found -- no need for IDP parent");
    goto LABEL_74;
  }
  v18 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)v123 + 281) + 24LL))(
          *((_QWORD *)v123 + 281),
          &v136);
  v45 = 0;
  if ( v18 < 0 )
    goto LABEL_128;
  v46 = v107;
  if ( v107 )
  {
    v49 = 0;
    if ( v14 )
    {
LABEL_99:
      *(struct _GUID *)Buf2 = *v46;
      v55 = *(__m128i *)Buf2;
      Data1 = v46[1].Data1;
      *(_DWORD *)&Buf2[16] = Data1;
      Uuid = v15;
      v142 = Data1 + 1;
      LODWORD(v98) = Data1 + 1;
      WUTrace(0, 0, 1, 5, 0, L" creating new dependent set revision %d", v98);
      v118 = _mm_srli_si128(v55, 8).m128i_u64[0];
      v119 = v55.m128i_i64[0];
    }
    else
    {
      v50 = v144;
      while ( v49 < DWORD1(v145) )
      {
        v51 = *(_DWORD **)(v50 + 24LL * v49);
        v18 = 0;
        v52 = 0;
        v53 = 0;
        do
        {
          if ( v45 >= *(_DWORD *)v107[37].Data4 )
            break;
          v54 = *(_QWORD *)&v107[38].Data1;
          if ( *v51 == *(_DWORD *)(v53 + v54)
            && v51[1] == *(_DWORD *)(v53 + v54 + 4)
            && v51[2] == *(_DWORD *)(v53 + v54 + 8)
            && v51[3] == *(_DWORD *)(v53 + v54 + 12)
            && v51[4] == *(_DWORD *)(v53 + v54 + 16) )
          {
            v52 = 1;
          }
          ++v45;
          v53 += 28;
        }
        while ( !v52 );
        v45 = 0;
        v50 = v144;
        if ( !v52 )
        {
          v60 = v107[1].Data1;
          v61 = Trace::GuidToString::GuidToString((Trace::GuidToString *)v132, v107);
          LODWORD(v99) = v60;
          WUTrace(0, 0, 1, 5, 0, L" found new child for existing dependent set %ws.%lu", v61, v99);
          v14 = 1;
          v46 = v107;
          goto LABEL_99;
        }
        ++v49;
        v14 = v105;
        if ( v105 )
        {
          v18 = 0;
          v46 = v107;
          goto LABEL_99;
        }
      }
      LODWORD(v98) = DWORD1(v145);
      WUTrace(0, 0, 1, 5, 0, L" existing IDP parent contains all %d IDP child updates in correct order", v98);
    }
    v47 = v117;
    if ( v14 )
      goto LABEL_101;
    v86 = v108;
    goto LABEL_179;
  }
  v149 = 0;
  v150 = 0;
  v47 = v117;
  v48 = (*(__int64 (__fastcall **)(__int64, const struct _GUID *, __int64, struct _GUID *))(*(_QWORD *)v136 + 480LL))(
          v136,
          v117,
          1,
          &v149);
  v18 = v48;
  if ( v48 >= 0 )
  {
    v18 = 0;
LABEL_71:
    v42 = 0;
    v16 = 0;
    goto LABEL_204;
  }
  if ( (unsigned int)(v48 + 2145091552) > 9 && v48 != -2145091577 )
  {
    LODWORD(v98) = v48;
    WUTrace(0, 0, 1, 5, 0, L" failed to get dependent set parent with error %#lx", v98);
    goto LABEL_74;
  }
  WUTrace(0, 0, 1, 5, 0, L" couldn't find existing dependent set parent");
LABEL_101:
  if ( memcmp(&GUID_NULL, Buf2, 0x10u) )
  {
    v56 = Trace::GuidToString::GuidToString((Trace::GuidToString *)v132, (const struct _GUID *)Buf2);
    v57 = Data1;
    LODWORD(v99) = Data1;
    WUTrace(0, 0, 1, 5, 0, L" expiring existing dependent set %ws.%lu", v56, v99);
    v139 = v57 + 999990000;
    *v129 |= 1u;
  }
  v58 = Trace::GuidToString::GuidToString((Trace::GuidToString *)v132, &Uuid);
  LODWORD(v99) = v142;
  WUTrace(0, 0, 1, 5, 0, L" Creating special bundle parent %ws.%lu", v58, v99);
  v59 = (*(__int64 (__fastcall **)(__int64, const struct _GUID *, __int64, unsigned int *, LPVOID *))(*(_QWORD *)v136 + 488LL))(
          v136,
          v47,
          1,
          v133,
          pv);
  v18 = v59;
  if ( v59 < 0 )
  {
    LODWORD(v98) = v59;
    WUTrace(0, 0, 1, 5, 0, L" failed to get dependent set children with error %#lx", v98);
    goto LABEL_74;
  }
  if ( v133[0] )
  {
    v62 = (char *)SafeSusAllocArray(v133[0], 0x280u);
    v104 = v62;
    if ( !v62 )
    {
      v18 = -2147024882;
      v42 = 0;
      v16 = 0;
      goto LABEL_204;
    }
    v63 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64, _QWORD, const struct _GUID *, unsigned int, LPVOID, char *))(*(_QWORD *)v136 + 208LL))(
            v136,
            0,
            0,
            2048,
            0,
            v47,
            v133[0],
            pv[0],
            v62);
    v18 = v63;
    if ( v63 < 0 )
    {
      LODWORD(v98) = v63;
      WUTrace(0, 0, 1, 5, 0, L" failed to get dependent set child metadata with error %#lx", v98);
      goto LABEL_114;
    }
    v64 = (struct tagDSGuidArray *)SafeSusAllocArray(v133[0], 0x10u);
    v42 = v64;
    v106 = v64;
    if ( !v64 )
    {
      v18 = -2147024882;
LABEL_117:
      v16 = (struct tagDSUpdateMetadata *)v104;
      goto LABEL_204;
    }
    v65 = (*(__int64 (__fastcall **)(__int64, _QWORD, LPVOID, struct tagDSGuidArray *))(*(_QWORD *)v136 + 448LL))(
            v136,
            v133[0],
            pv[0],
            v64);
    v18 = v65;
    if ( v65 < 0 )
    {
      LODWORD(v98) = v65;
      WUTrace(0, 0, 1, 5, 0, L" failed to get dependent set child categories with error %#lx", v98);
      v16 = (struct tagDSUpdateMetadata *)v104;
      goto LABEL_204;
    }
    v66 = 0;
    v67 = v133[0];
    if ( v133[0] )
    {
      v68 = v42;
      do
      {
        v69 = 0;
        if ( *(_DWORD *)v68 )
        {
          do
            CSusSortedArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>>::Add(
              &v146,
              *((_QWORD *)v68 + 1) + 16LL * (int)v69++,
              1);
          while ( v69 < *(_DWORD *)v68 );
          v67 = v133[0];
        }
        ++v66;
        v68 = (struct tagDSGuidArray *)((char *)v68 + 16);
      }
      while ( v66 < v67 );
    }
    v70 = DWORD1(v148);
    v71 = 69LL * (unsigned int)(DWORD1(v148) + 1) + 11161 + 97LL * v67;
    v103 = v71;
    v10 = (wchar_t *)SafeSusAllocArray(v71, 2u);
    v128 = v10;
    v102 = v10;
    if ( !v10 )
      goto LABEL_127;
    if ( UuidToStringW(&Uuid, &StringUuid) )
      goto LABEL_130;
    v72 = L"false";
    if ( v109 )
      v72 = L"true";
    LODWORD(v100) = v142;
    v18 = StringCchPrintfExW(
            v10,
            v71,
            &v102,
            &v103,
            0,
            L"<UpdateIdentity UpdateID=\"%s\" RevisionNumber=\"%d\" /><Properties UpdateType=\"Software\" ExplicitlyDeploy"
             "able=\"true\" AutoSelectOnWebSites=\"%s\" />",
            StringUuid,
            v100,
            v72);
    if ( v18 < 0 )
      goto LABEL_128;
    RpcStringFreeW(&StringUuid);
    StringUuid = 0;
    v18 = ProduceIDPExtendedAndLocalizedPropertyXML(&FileTime, v113, v114, v102, v103, &v102, &v103);
    if ( v18 < 0 )
      goto LABEL_128;
    v18 = StringCchCopyExW(v102, v103, L"<Relationships><Prerequisites>", &v102, &v103, 0);
    if ( v18 < 0 )
      goto LABEL_128;
    v18 = StringCchCopyExW(v102, v103, L"<AtLeastOne IsCategory=\"true\">", &v102, &v103, 0);
    if ( v18 < 0 )
      goto LABEL_128;
    v73 = 0;
    if ( v70 )
    {
      while ( v73 < v70 )
      {
        if ( UuidToStringW((const UUID *)(v147 + 16LL * v73), &StringUuid) )
          goto LABEL_130;
        v18 = StringCchPrintfExW(v102, v103, &v102, &v103, 0, L"<UpdateIdentity UpdateID=\"%s\" />", StringUuid);
        if ( v18 < 0 )
          goto LABEL_128;
        RpcStringFreeW(&StringUuid);
        StringUuid = 0;
        if ( ++v73 >= v70 )
          goto LABEL_142;
      }
      v18 = -2145124345;
      goto LABEL_128;
    }
LABEL_142:
    StringUuid = 0;
    if ( UuidToStringW(&categoryWUZeroDayPriority, &StringUuid) )
    {
LABEL_130:
      v18 = -2145120257;
      goto LABEL_128;
    }
    v18 = StringCchPrintfExW(v102, v103, &v102, &v103, 0, L"<UpdateIdentity UpdateID=\"%s\" />", StringUuid);
    if ( v18 < 0 )
      goto LABEL_128;
    RpcStringFreeW(&StringUuid);
    StringUuid = 0;
    v18 = StringCchCopyExW(v102, v103, L"</AtLeastOne>", &v102, &v103, 0);
    if ( v18 < 0 )
      goto LABEL_128;
    v18 = StringCchCopyExW(
            v102,
            v103,
            L"</Prerequisites><BundledUpdates><AtLeastOne IsCategory=\"false\">",
            &v102,
            &v103,
            0);
    if ( v18 < 0 )
      goto LABEL_128;
    v74 = 0;
    v75 = v133[0];
    do
    {
      v76 = 0;
      if ( v75 )
      {
        v77 = 0;
        v107 = 0;
        v78 = v104 + 184;
        v112 = v104 + 184;
        do
        {
          v79 = *v78 & 0xC0;
          if ( (v74 || !v79) && (v74 != 1 || v79) )
          {
            v18 = StringCchCopyExW(v102, v103, L"<UpdateIdentity UpdateID=\"", &v102, &v103, 0);
            if ( v18 < 0 || v103 < 0x24 )
              goto LABEL_128;
            if ( UuidToStringW((const UUID *)((char *)pv[0] + 24 * (int)v76 + 4), &StringUuid) )
              goto LABEL_130;
            v18 = StringCchCopyExW(v102, v103, StringUuid, &v102, &v103, 0);
            if ( v18 < 0 )
              goto LABEL_128;
            v18 = StringCchCopyExW(v102, v103, L"\" RevisionNumber=\"", &v102, &v103, 0);
            if ( v18 < 0 )
              goto LABEL_128;
            v18 = StringCchPrintfW(
                    &Buffer,
                    0xBu,
                    L"%lu",
                    *(unsigned int *)((char *)&v107[1].Data2 + (unsigned __int64)pv[0]));
            if ( v18 < 0 )
              goto LABEL_128;
            v18 = StringCchCopyExW(v102, v103, &Buffer, &v102, &v103, 0);
            if ( v18 < 0 )
              goto LABEL_128;
            v18 = StringCchCopyExW(v102, v103, L"\" />", &v102, &v103, 0);
            if ( v18 < 0 )
              goto LABEL_128;
            RpcStringFreeW(&StringUuid);
            StringUuid = 0;
            v75 = v133[0];
            v77 = v107;
          }
          ++v76;
          v78 = v112 + 640;
          v112 += 640;
          v77 = (struct _GUID *)((char *)v77 + 24);
          v107 = v77;
        }
        while ( v76 < v75 );
      }
      ++v74;
    }
    while ( v74 < 2 );
    v18 = StringCchCopyExW(v102, v103, L"</AtLeastOne></BundledUpdates></Relationships><Files />", &v102, &v103, 0);
    if ( v18 < 0 )
      goto LABEL_128;
    WUTrace(0, 0, 1, 5, 0, L" Final dependent set XML: %ws", v10);
    memset(v138, 0, sizeof(v138));
    v135 = v138;
    *(_DWORD *)v138 = v142 + 999990000;
    v138[108] = 1;
    SysFreeString(0);
    v80 = SysAllocString(v10);
    v124 = v80;
    if ( !v80 )
    {
LABEL_127:
      v18 = -2147024882;
LABEL_128:
      v42 = v106;
      goto LABEL_117;
    }
    v124 = 0;
    *(_QWORD *)&v138[112] = v80;
    *(_DWORD *)&v138[4] = *(_DWORD *)v138;
    *(_DWORD *)&v138[6] = 1;
    *(_QWORD *)&v138[8] = 0;
    LOBYTE(v138[12]) = v109 != 0;
    memset(Buf2, 0, sizeof(Buf2));
    v81 = FileTimeToString((wchar_t *)Buf2, 0xBu, &FileTime);
    v82 = (const OLECHAR *)Buf2;
    if ( v81 < 0 )
      v82 = L"2012-01-01";
    *(_QWORD *)&v138[16] = SysAllocString(v82);
    *(_QWORD *)&v138[20] = SysAllocString(L"Normal");
    *(_QWORD *)&v138[24] = 0;
    *(_DWORD *)&v138[28] = 0;
    *(_QWORD *)&v138[48] = SysAllocString(L"0");
    *(_QWORD *)&v138[52] = SysAllocString(L"0");
    *(_QWORD *)&v138[56] = SysAllocString(L"0");
    *(_QWORD *)&v138[60] = SysAllocString(L"0");
    *(_QWORD *)&v138[64] = SysAllocString(&OutputString);
    *(_QWORD *)&v138[68] = SysAllocString(&OutputString);
    *(UUID *)&v138[72] = v15;
    v83 = lpString2;
    lpString2 = 0;
    v120 = 0;
    *(_QWORD *)&v138[84] = v83;
    v84 = v12;
    v12 = 0;
    v121 = 0;
    *(_QWORD *)&v138[88] = v84;
    v85 = v13;
    v13 = 0;
    v122 = 0;
    *(_QWORD *)&v138[96] = v85;
    *(_DWORD *)&v138[82] = 1;
    *(_DWORD *)&v138[80] = 0;
    if ( DWORD1(v145) )
      DWORD1(v145) = 0;
    v86 = v108;
    v47 = v117;
    v18 = CAgentUpdateManager::ParseAndAddUpdates(
            (_DWORD)v123,
            (_DWORD)v127,
            0,
            0,
            (__int64)v126,
            v136,
            (__int64)v117,
            v115,
            (__int64)&v135,
            1,
            0,
            0,
            0,
            0,
            (__int64)v125,
            (__int64)v108,
            0,
            0);
    SusWsStructs::SusUpdateInfo::Clear((SusWsStructs::SusUpdateInfo *)v138);
    if ( v18 < 0 )
    {
      LODWORD(v98) = v18;
      WUTrace(0, 0, 1, 5, 0, L" fail to parse and add dependent set updates with error %#lx", v98);
LABEL_114:
      v16 = (struct tagDSUpdateMetadata *)v104;
LABEL_203:
      v42 = v106;
      goto LABEL_204;
    }
    WUTrace(0, 0, 1, 5, 0, L" dependent set bundle successfully created");
    if ( v130 )
      *v130 = 1;
    if ( v139 )
    {
      v87 = CAgentUpdateManager::ParseAndAddUpdates(
              (_DWORD)v123,
              (_DWORD)v127,
              0,
              0,
              (__int64)v126,
              v136,
              (__int64)v47,
              v115,
              0,
              0,
              (__int64)&v139,
              1,
              0,
              0,
              (__int64)v125,
              (__int64)v86,
              0,
              0);
      v18 = v87;
      if ( v87 < 0 )
      {
        LODWORD(v98) = v87;
        WUTrace(0, 0, 1, 5, 0, L" fail to expire old dependent set update with error %#lx; continuing", v98);
        v18 = 0;
      }
    }
LABEL_179:
    v88 = v110;
    if ( v110 && v111 )
    {
      v89 = (*(__int64 (__fastcall **)(__int64, const struct _GUID *, _QWORD))(*(_QWORD *)v136 + 368LL))(v136, v47, 0);
      v18 = v89;
      if ( v89 < 0 )
      {
        LODWORD(v98) = v89;
        WUTrace(0, 0, 1, 5, 0, L" fail to unhide dependent set updates with error %#lx", v98);
        goto LABEL_114;
      }
      v88 = v110;
    }
    else if ( !v139 )
    {
      goto LABEL_128;
    }
    v90 = *((_DWORD *)v86 + 5);
    v91 = 0;
    if ( v90 )
    {
      v92 = Data1;
      v93 = v118;
      v94 = v119;
      v95 = v111;
      do
      {
        if ( v91 < *((_DWORD *)v86 + 5) )
        {
          v96 = *((_QWORD *)v86 + 1) + 1048LL * v91;
          if ( v96 )
          {
            if ( v139 && v94 == *(_QWORD *)v96 && v93 == *(_QWORD *)(v96 + 8) && v92 == *(_DWORD *)(v96 + 16) )
            {
              *(_DWORD *)(v96 + 120) = 2;
            }
            else if ( v88 && v95 && (*(_DWORD *)(v96 + 820) == 1 || *(_DWORD *)(v96 + 816) == 1) )
            {
              *(_DWORD *)(v96 + 120) = 0;
            }
          }
        }
        ++v91;
      }
      while ( v91 < v90 );
      v10 = v128;
      lpString2 = v120;
      v12 = v121;
      v13 = v122;
    }
    goto LABEL_128;
  }
  WUTrace(0, 0, 1, 5, 0, L" unexpectedly found zero dependent set children");
LABEL_73:
  v18 = -2145120257;
LABEL_74:
  v42 = v106;
  v16 = v106;
LABEL_204:
  if ( v136 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v136 + 16LL))(v136);
  if ( StringUuid )
    RpcStringFreeW(&StringUuid);
  if ( pv[0] )
    CoTaskMemFree(pv[0]);
  if ( v16 )
  {
    DsqFreeObject(v16, v133[0], 12207, 0);
    SusFree(v16);
  }
  if ( v42 )
  {
    DsqFreeObject(v42, v133[0]);
    SusFree(v42);
  }
  LODWORD(v98) = v18;
  WUTrace(0, 0, 1, 5, 0, L" AssembleDependentSetBundleIfNeeded complete, hr=%#lx", v98);
  CSusArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>>::~CSusArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>>(&v146);
  SysFreeString(v13);
  SysFreeString(v12);
  SysFreeString(lpString2);
  SysFreeString(0);
  if ( v10 )
    SusFree(v10);
  CSusArrayList<CSusMap<_GUID,UploaderHandlers<CUpdateManagerReportingEvent,CLegacyEventUploader> *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpNoop<UploaderHandlers<CUpdateManagerReportingEvent,CLegacyEventUploader> *>>::_tagMapEntry,CSusMap<_GUID,UploaderHandlers<CUpdateManagerReportingEvent,CLegacyEventUploader> *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpNoop<UploaderHandlers<CUpdateManagerReportingEvent,CLegacyEventUploader> *>>::CMapEntryOps>::~CSusArrayList<CSusMap<_GUID,UploaderHandlers<CUpdateManagerReportingEvent,CLegacyEventUploader> *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpNoop<UploaderHandlers<CUpdateManagerReportingEvent,CLegacyEventUploader> *>>::_tagMapEntry,CSusMap<_GUID,UploaderHandlers<CUpdateManagerReportingEvent,CLegacyEventUploader> *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpNoop<UploaderHandlers<CUpdateManagerReportingEvent,CLegacyEventUploader> *>>::CMapEntryOps>(&v143);
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x1800295a8  mov     rax, rsp
0x1800295ab  push    rbp
0x1800295ac  push    rbx
0x1800295ad  push    rsi
0x1800295ae  push    rdi
0x1800295af  push    r12
0x1800295b1  push    r13
0x1800295b3  push    r14
0x1800295b5  push    r15
0x1800295b7  lea     rbp, [rax-368h]
0x1800295be  sub     rsp, 438h
0x1800295c5  movaps  xmmword ptr [rax-58h], xmm6
0x1800295c9  movaps  xmmword ptr [rax-68h], xmm7
0x1800295cd  mov     rax, cs:__security_cookie
0x1800295d4  xor     rax, rsp
0x1800295d7  mov     [rbp+360h+var_70], rax
0x1800295de  mov     [rbp+360h+var_3B0], r9
0x1800295e2  mov     [rbp+360h+var_388], r8d
0x1800295e6  mov     [rbp+360h+var_328], rdx
0x1800295ea  mov     [rbp+360h+var_348], rcx
0x1800295ee  mov     r11, [rbp+360h+arg_20]
0x1800295f5  mov     [rbp+360h+var_330], r11
0x1800295f9  mov     rax, [rbp+360h+arg_28]
0x180029600  mov     [rbp+360h+var_378], rax
0x180029604  mov     rax, [rbp+360h+arg_30]
0x18002960b  mov     [rbp+360h+var_338], rax
0x18002960f  mov     rdx, [rbp+360h+arg_38]
0x180029616  mov     [rbp+360h+var_318], rdx
0x18002961a  mov     r10, [rbp+360h+arg_40]
0x180029621  mov     [rbp+360h+var_310], r10
0x180029625  mov     eax, [r9+14h]
0x180029629  mov     dword ptr [rbp+360h+var_3E0], eax
0x18002962c  xorps   xmm0, xmm0
0x18002962f  movups  [rbp+360h+var_F8], xmm0
0x180029636  movups  [rbp+360h+var_E8], xmm0
0x18002963d  xor     r13d, r13d
0x180029640  mov     qword ptr [rbp+360h+var_F8+8], r13
0x180029647  mov     qword ptr [rbp+360h+var_E8], r13
0x18002964e  lea     rcx, ??_7?$CSusSortedArrayList@U_tagMapEntry@?$CSusMap@U_GUID@@PEAVCUpdateDetectInfo@@V?$CSusSortedArrayListItemOpsBasic@U_GUID@@@@V?$CSusArrayListItemOpNoop@PEAVCUpdateDetectInfo@@@@@@VCMapEntryOps@2@@@6B@; const CSusSortedArrayList<CSusMap<_GUID,CUpdateDetectInfo *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpNoop<CUpdateDetectInfo *>>::_tagMapEntry,CSusMap<_GUID,CUpdateDetectInfo *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpNoop<CUpdateDetectInfo *>>::CMapEntryOps>::`vftable'
0x180029655  mov     qword ptr [rbp+360h+var_F8], rcx
0x18002965c  mov     dword ptr [rbp+360h+var_E8+8], r13d
0x180029663  mov     [rbp+360h+var_3B8], r13
0x180029667  mov     ebx, r13d
0x18002966a  mov     [rbp+360h+var_320], rbx
0x18002966e  mov     [rbp+360h+var_340], r13
0x180029672  mov     edi, r13d
0x180029675  mov     [rbp+360h+var_360], r13
0x180029679  mov     esi, r13d
0x18002967c  mov     [rbp+360h+var_358], r13
0x180029680  mov     r14d, r13d
0x180029683  mov     [rbp+360h+var_350], r13
0x180029687  mov     [rbp+360h+StringUuid], r13
0x18002968e  mov     [rbp+360h+Buffer], r13w
0x180029696  xor     ecx, ecx
0x180029698  movups  [rbp+360h+var_86], xmm0
0x18002969f  mov     [rbp+360h+var_76], ecx
0x1800296a5  mov     [rbp+360h+var_390], r13d
0x1800296a9  mov     [rbp+360h+var_38C], r13d
0x1800296ad  mov     [rbp+360h+var_3A8], r13d
0x1800296b1  mov     qword ptr [rbp+360h+FileTime.dwLowDateTime], r13
0x1800296b8  mov     [rbp+360h+var_3A0], r13d
0x1800296bc  mov     [rbp+360h+var_3A4], r13d
0x1800296c0  mov     r15d, r13d
0x1800296c3  mov     [rbp+360h+var_3C8], r13d
0x1800296c7  mov     [rbp+360h+var_120], r13d
0x1800296ce  xorps   xmm7, xmm7
0x1800296d1  movups  xmmword ptr [rbp+360h+var_B8.Data1], xmm7
0x1800296d8  xor     r8d, r8d
0x1800296db  mov     [rbp+360h+var_380], r8
0x1800296df  movups  [rbp+360h+Buf2], xmm0
0x1800296e6  mov     [rbp+360h+var_90], r8d
0x1800296ed  movups  xmmword ptr [rbp+360h+Uuid.Data1], xmm0
0x1800296f4  mov     [rbp+360h+var_100], ecx
0x1800296fa  mov     [rbp+360h+var_260], r13d
0x180029701  mov     [rbp+360h+pv], r13
0x180029708  mov     r12d, r13d
0x18002970b  mov     [rbp+360h+var_3D0], r13
0x18002970f  mov     [rbp+360h+var_3C0], r13
0x180029713  mov     [rbp+360h+var_248], r13
0x18002971a  movups  [rbp+360h+var_D8], xmm0
0x180029721  movups  [rbp+360h+var_C8], xmm0
0x180029728  mov     qword ptr [rbp+360h+var_D8+8], r13
0x18002972f  mov     qword ptr [rbp+360h+var_C8], r13
0x180029736  lea     rcx, ??_7?$CSusSortedArrayList@U_GUID@@V?$CSusSortedArrayListItemOpsBasic@U_GUID@@@@@@6B@; const CSusSortedArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>>::`vftable'
0x18002973d  mov     qword ptr [rbp+360h+var_D8], rcx
0x180029744  mov     dword ptr [rbp+360h+var_C8+8], r13d
0x18002974b  test    rdx, rdx
0x18002974e  jz      loc_18002AD8F
0x180029754  test    r11, r11
0x180029757  jz      loc_18002AD8F
0x18002975d  xor     r11d, r11d
0x180029760  test    r10, r10
0x180029763  jz      short loc_180029768
0x180029765  mov     [r10], r11d
0x180029768  mov     ecx, r11d
0x18002976b  mov     dword ptr [rbp+360h+var_3D8], ecx
0x18002976e  mov     r8, qword ptr [rbp+360h+Buf2+8]
0x180029775  mov     [rbp+360h+var_370], r8
0x180029779  mov     r8, qword ptr [rbp+360h+Buf2]
0x180029780  mov     [rbp+360h+var_368], r8
0x180029784  mov     r12d, 1
0x18002978a  mov     dword ptr [rbp+360h+var_250], r11d
0x180029791  mov     r13d, r11d
0x180029794  test    eax, eax
0x180029796  jz      loc_180029D16
0x18002979c  mov     eax, r11d
0x18002979f  mov     edx, dword ptr [rbp+360h+var_3E0]
0x1800297a2  mov     r13d, r11d
0x1800297a5  cmp     eax, [r9+14h]
0x1800297a9  jnb     loc_180029D02
0x1800297af  mov     eax, dword ptr [rbp+360h+var_250]
0x1800297b5  imul    r12, rax, 418h
0x1800297bc  add     r12, [r9+8]
0x1800297c0  mov     [rbp+360h+var_398], r12
0x1800297c4  jz      loc_180029CF3
0x1800297ca  mov     r15d, [r12+10h]
0x1800297cf  mov     rdx, r12; struct _GUID *
0x1800297d2  lea     rcx, [rbp+360h+var_300]; this
0x1800297d6  call    ??0GuidToString@Trace@@QEAA@AEBU_GUID@@@Z; Trace::GuidToString::GuidToString(_GUID const &)
0x1800297db  mov     dword ptr [rsp+470h+var_430], r15d
0x1800297e0  mov     [rsp+470h+var_438], rax
0x1800297e5  mov     eax, dword ptr [rbp+360h+var_3D8]
0x1800297e8  mov     dword ptr [rsp+470h+var_440], eax
0x1800297ec  lea     rax, aAssembledepend_3; "AssembleDependentSetBundleIfNeeded eval"...
0x1800297f3  mov     qword ptr [rsp+470h+cchCount2], rax
0x1800297f8  xor     eax, eax
0x1800297fa  mov     [rsp+470h+lpString2], rax
0x1800297ff  lea     r9d, [rax+5]
0x180029803  lea     r15d, [rax+1]
0x180029807  mov     r8d, r15d
0x18002980a  xor     edx, edx
0x18002980c  xor     ecx, ecx
0x18002980e  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180029813  mov     ecx, dword ptr [rbp+360h+var_3D8]
0x180029816  xor     r11d, r11d
0x180029819  mov     r13d, r11d
0x18002981c  test    ecx, ecx
0x18002981e  jnz     loc_1800298EB
0x180029824  cmp     [r12+334h], r15d
0x18002982c  jnz     loc_180029CDB
0x180029832  mov     rcx, [rbp+360h+var_3B8]
0x180029836  test    rcx, rcx
0x180029839  jz      short loc_180029849
0x18002983b  mov     eax, [rcx+10h]
0x18002983e  cmp     [r12+10h], eax
0x180029843  jbe     loc_180029CE8
0x180029849  mov     r15d, [r12+10h]
0x18002984e  mov     rdx, r12; struct _GUID *
0x180029851  lea     rcx, [rbp+360h+var_300]; this
0x180029855  call    ??0GuidToString@Trace@@QEAA@AEBU_GUID@@@Z; Trace::GuidToString::GuidToString(_GUID const &)
0x18002985a  mov     dword ptr [rsp+470h+var_438], r15d
0x18002985f  mov     [rsp+470h+var_440], rax
0x180029864  lea     rax, aAssembledepend_2; "AssembleDependentSetBundleIfNeeded sele"...
0x18002986b  mov     qword ptr [rsp+470h+cchCount2], rax
0x180029870  xor     eax, eax
0x180029872  mov     [rsp+470h+lpString2], rax
0x180029877  xor     edx, edx
0x180029879  xor     ecx, ecx
0x18002987b  lea     r9d, [rax+5]
0x18002987f  lea     r8d, [rax+1]
0x180029883  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180029888  movups  xmm1, xmmword ptr [r12]
0x18002988d  movups  [rbp+360h+Buf2], xmm1
0x180029894  mov     eax, [r12+10h]
0x180029899  mov     [rbp+360h+var_380], rax
0x18002989d  mov     [rbp+360h+var_90], eax
0x1800298a3  mov     [rbp+360h+var_3B8], r12
0x1800298a7  xor     r11d, r11d
0x1800298aa  mov     r13d, r11d
0x1800298ad  movq    xmm0, qword ptr [r12+8]
0x1800298b4  movq    [rbp+360h+var_370], xmm0
0x1800298b9  movq    [rbp+360h+var_368], xmm1
0x1800298be  mov     eax, 1
0x1800298c3  mov     r15d, [rbp+360h+var_3C8]
0x1800298c7  mov     ecx, dword ptr [rbp+360h+var_3D8]
0x1800298ca  mov     edx, dword ptr [rbp+360h+var_3E0]
0x1800298cd  mov     r9, [rbp+360h+var_3B0]
0x1800298d1  cmp     dword ptr [r12+78h], 2
0x1800298d7  mov     r12d, 1
0x1800298dd  jnz     loc_180029CD6
0x1800298e3  mov     [rbp+360h+var_3A4], eax
0x1800298e6  jmp     loc_180029CFC
0x1800298eb  cmp     ecx, r15d
0x1800298ee  jnz     loc_180029CDB
0x1800298f4  cmp     [r12+330h], r15d
0x1800298fc  jnz     loc_180029CDB
0x180029902  lea     r8, [rbp+360h+var_398]
0x180029906  mov     rdx, r12
0x180029909  lea     rcx, [rbp+360h+var_F8]
0x180029910  call    ?Add@?$CSusMap@U_GUID@@PEAV?$CSusSortedArrayList@U_GUID@@V?$CSusSortedArrayListItemOpsBasic@U_GUID@@@@@@V?$CSusSortedArrayListItemOpsBasic@U_GUID@@@@V?$CSusArrayListItemOpDelete@PEAV?$CSusSortedArrayList@U_GUID@@V?$CSusSortedArrayListItemOpsBasic@U_GUID@@@@@@@@@@QEAAJAEBU_GUID@@AEBQEAV?$CSusSortedArrayList@U_GUID@@V?$CSusSortedArrayListItemOpsBasic@U_GUID@@@@@@@Z; CSusMap<_GUID,CSusSortedArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>> *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpDelete<CSusSortedArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>> *>>::Add(_GUID const &,CSusSortedArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>> * const &)
0x180029915  mov     r13d, eax
0x180029918  xor     r11d, r11d
0x18002991b  test    eax, eax
0x18002991d  js      loc_18002A3C5
0x180029923  mov     r12, [rbp+360h+var_398]
0x180029927  mov     eax, [r12+110h]
0x18002992f  test    al, al
0x180029931  jns     short loc_18002995A
0x180029933  lea     rax, aAssembledepend_1; "AssembleDependentSetBundleIfNeeded dete"...
0x18002993a  mov     qword ptr [rsp+470h+cchCount2], rax
0x18002993f  mov     [rsp+470h+lpString2], r11
0x180029944  lea     r9d, [r11+5]
0x180029948  mov     r8d, r15d
0x18002994b  xor     edx, edx
0x18002994d  xor     ecx, ecx
0x18002994f  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180029954  mov     [rbp+360h+var_38C], r15d
0x180029958  jmp     short loc_180029985
0x18002995a  test    al, 40h
0x18002995c  jz      short loc_180029988
0x18002995e  lea     rax, aAssembledepend_4; "AssembleDependentSetBundleIfNeeded dete"...
0x180029965  mov     qword ptr [rsp+470h+cchCount2], rax
0x18002996a  mov     [rsp+470h+lpString2], r11
0x18002996f  mov     r9d, 5
0x180029975  mov     r8d, r15d
0x180029978  xor     edx, edx
0x18002997a  xor     ecx, ecx
0x18002997c  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180029981  mov     [rbp+360h+var_390], r15d
0x180029985  xor     r11d, r11d
0x180029988  cmp     [r12+2F8h], r11d
0x180029990  jz      short loc_1800299BC
0x180029992  lea     rax, aAssembledepend_0; "AssembleDependentSetBundleIfNeeded dete"...
0x180029999  mov     qword ptr [rsp+470h+cchCount2], rax
0x18002999e  mov     [rsp+470h+lpString2], r11
0x1800299a3  mov     r9d, 5
0x1800299a9  mov     r8d, r15d
0x1800299ac  xor     edx, edx
0x1800299ae  xor     ecx, ecx
0x1800299b0  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800299b5  mov     [rbp+360h+var_3A8], r15d
0x1800299b9  xor     r11d, r11d
0x1800299bc  cmp     [rbp+360h+FileTime.dwLowDateTime], r11d
0x1800299c3  jnz     short loc_1800299CE
0x1800299c5  cmp     [rbp+360h+FileTime.dwHighDateTime], r11d
0x1800299cc  jz      short loc_1800299E6
0x1800299ce  lea     rdx, [r12+2E8h]; struct _FILETIME *
0x1800299d6  lea     rcx, [rbp+360h+FileTime]; struct _FILETIME *
0x1800299dd  call    ?TimeDiff@@YAHAEBU_FILETIME@@0H@Z; TimeDiff(_FILETIME const &,_FILETIME const &,int)
0x1800299e2  test    eax, eax
0x1800299e4  jle     short loc_180029A46
0x1800299e6  lea     r15, [r12+2E8h]
0x1800299ee  xor     r9d, r9d
0x1800299f1  mov     r8, r15; lpFileTime
0x1800299f4  mov     edx, 80h; unsigned __int64
0x1800299f9  lea     rcx, [rbp+360h+var_230]; wchar_t *
0x180029a00  call    FileTimeToString
0x180029a05  xor     r13d, r13d
0x180029a08  test    eax, eax
0x180029a0a  js      short loc_180029A3A
0x180029a0c  lea     rax, [rbp+360h+var_230]
0x180029a13  mov     [rsp+470h+var_440], rax
0x180029a18  lea     rax, aAssembledepend; "AssembleDependentSetBundleIfNeeded foun"...
0x180029a1f  mov     qword ptr [rsp+470h+cchCount2], rax
0x180029a24  mov     [rsp+470h+lpString2], r13
0x180029a29  xor     edx, edx
0x180029a2b  xor     ecx, ecx
0x180029a2d  lea     r9d, [r13+5]
0x180029a31  lea     r8d, [r13+1]
0x180029a35  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180029a3a  mov     rax, [r15]
0x180029a3d  mov     qword ptr [rbp+360h+FileTime.dwLowDateTime], rax
0x180029a44  jmp     short loc_180029A49
0x180029a46  xor     r13d, r13d
0x180029a49  mov     r15, [r12+338h]
0x180029a51  mov     rcx, rdi; bstrString
0x180029a54  call    cs:__imp_SysFreeString
0x180029a5a  mov     rdi, r13
0x180029a5d  mov     [rbp+360h+var_360], r13
0x180029a61  test    r15, r15
0x180029a64  jz      short loc_180029A85
0x180029a66  mov     rcx, r15; psz
0x180029a69  call    cs:__imp_SysAllocString
0x180029a6f  mov     rdi, rax
0x180029a72  mov     [rbp+360h+var_360], rax
0x180029a76  xor     r11d, r11d
0x180029a79  test    rax, rax
0x180029a7c  jz      loc_180029D57
0x180029a82  xor     r13d, r13d
0x180029a85  mov     r15, [r12+340h]
0x180029a8d  mov     rcx, rsi; bstrString
0x180029a90  call    cs:__imp_SysFreeString
0x180029a96  mov     rsi, r13
0x180029a99  mov     [rbp+360h+var_358], r13
0x180029a9d  test    r15, r15
0x180029aa0  jz      short loc_180029ABE
0x180029aa2  mov     rcx, r15; psz
0x180029aa5  call    cs:__imp_SysAllocString
0x180029aab  mov     rsi, rax
0x180029aae  mov     [rbp+360h+var_358], rax
0x180029ab2  xor     r11d, r11d
0x180029ab5  test    rax, rax
0x180029ab8  jz      loc_180029D57
0x180029abe  mov     r15, [r12+350h]
0x180029ac6  mov     rcx, r14; bstrString
0x180029ac9  call    cs:__imp_SysFreeString
0x180029acf  xor     r11d, r11d
0x180029ad2  mov     r14d, r11d
0x180029ad5  mov     [rbp+360h+var_350], r11
0x180029ad9  test    r15, r15
  ... truncated ...
```
