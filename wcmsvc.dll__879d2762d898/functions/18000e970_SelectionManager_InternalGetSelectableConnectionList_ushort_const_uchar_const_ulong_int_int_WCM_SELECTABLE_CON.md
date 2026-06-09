# SelectionManager::InternalGetSelectableConnectionList(ushort const *,uchar const *,ulong,int,int,_WCM_SELECTABLE_CONNECTION_LIST * *)

- ea: `0x18000e970`
- end: `0x18000fe5f`
- name: `?InternalGetSelectableConnectionList@SelectionManager@@IEAAJPEBGPEBEKHHPEAPEAU_WCM_SELECTABLE_CONNECTION_LIST@@@Z`
- size: `5359`
- prototype: `__int64 __fastcall(SelectionManager *__hidden this, const unsigned __int16 *, const unsigned __int8 *, unsigned int, int, int, struct _WCM_SELECTABLE_CONNECTION_LIST **)`
- caller_count: `2`
- callee_count: `34`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18001abbc`
- `0x18001e090`

## callees

- `0x180007f90`
- `0x18000d594`
- `0x18000d758`
- `0x18000d7d8`
- `0x18000d878`
- `0x18000da78`
- `0x18000dd88`
- `0x18000dda0`
- `0x18000e970`
- `0x180010080`
- `0x180010900`
- `0x180011bb0`
- `0x180011c20`
- `0x1800137a0`
- `0x180019434`
- `0x18001b2b0`
- `0x180023910`
- `0x180024640`
- `0x18002a9e8`
- `0x18002bfb4`
- `0x180037550`
- `0x180041a20`
- `0x18004cdd8`
- `0x180052d04`
- `0x18006c2c0`
- `0x18007898c`
- `0x180084f50`
- `0x18008534c`
- `0x180085bc4`
- `0x180087ab8`
- `0x180089ee0`
- `0x1800cb344`
- `0x1800cb460`
- `0x1800f7010`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000f9a9`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000f9a9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000ea97`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000eaaf`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000eac7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000eadf`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000ea97`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000eaaf`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000eac7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000eadf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000eb15`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000eb15`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f4eb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f4eb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000ed0b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000ed0b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000ec7c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000ec7c`
- `ext-ms-win-net-cmvpn-l1-1-0!VpnCmOracleCheckVpnAvailability` at `0x18000fbf8`
- `ext-ms-win-net-cmvpn-l1-1-0!VpnCmOracleCheckVpnAvailability` at `0x18000fbf8`

## string_xrefs

- `0x18000ecbd`: `onecoreuap\net\wcm\service\base\cspmanager\cspmanager.cpp`
- `0x18000f990`: `onecoreuap\net\wcm\service\base\selection\lib\selectionmanager.cpp`
- `0x18000f9b6`: `onecoreuap\net\wcm\service\base\selection\lib\selectableconnection.cpp`
- `0x18000f9ce`: `onecoreuap\net\wcm\service\base\selection\lib\selectableconnection.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall SelectionManager::InternalGetSelectableConnectionList(
        SelectionManager *this,
        unsigned __int16 *a2,
        const unsigned __int8 *a3,
        unsigned int a4,
        int a5,
        unsigned int a6,
        struct _WCM_SELECTABLE_CONNECTION_LIST **a7)
{
  __int128 v11; // xmm0
  bool v12; // al
  unsigned __int64 v13; // rbx
  __int64 v14; // rcx
  _QWORD *v15; // rdi
  _QWORD *i; // rbx
  __int64 *v17; // r14
  __int64 v18; // r12
  int v19; // r15d
  const char *v20; // r9
  _QWORD *v21; // rcx
  int Property; // esi
  _OWORD *v23; // rsi
  _OWORD *v24; // r10
  int v25; // eax
  _QWORD *v26; // rdx
  __int64 v27; // rcx
  __int64 v28; // r8
  char *v29; // r9
  __int16 v30; // ax
  char v31; // al
  __int64 v32; // rcx
  __int64 v33; // rdx
  char *v34; // r8
  __int16 v35; // ax
  char v36; // al
  int v37; // esi
  __int64 v38; // rax
  _QWORD *v39; // r9
  int v40; // edx
  __int128 *v41; // rdx
  __int128 *v42; // rax
  __int64 v43; // rcx
  _DWORD *v44; // r8
  int ApplicationIdentifier; // esi
  unsigned int v46; // r12d
  char v47; // r15
  int v48; // edx
  int v49; // r8d
  std::_Ref_count_base *v50; // rbx
  std::_Ref_count_base *v51; // rdx
  signed __int32 v52; // eax
  signed __int32 v53; // ett
  int v54; // r14d
  char v55; // di
  std::_Ref_count_base *v56; // rbx
  std::_Ref_count_base *v57; // rdx
  signed __int32 v58; // eax
  signed __int32 v59; // ett
  char v60; // di
  __int64 v61; // r10
  unsigned int v62; // r14d
  _BYTE *v63; // rdi
  _DWORD *j; // rbx
  SelectionManager *v65; // rcx
  bool v66; // al
  volatile signed __int32 *v67; // rdi
  void *v68; // rcx
  struct std::nothrow_t *v69; // rdx
  struct std::nothrow_t *v70; // rdx
  __int64 *v72; // rax
  __int64 v73; // r8
  char v74; // al
  __int64 *v75; // rax
  __int64 v76; // r8
  _QWORD *v77; // r9
  _DWORD *v78; // rax
  const char *v79; // r9
  unsigned int v80; // eax
  struct std::nothrow_t *v81; // r10
  unsigned int v82; // edx
  __int64 v83; // r8
  __int128 *v84; // rax
  __int128 *v85; // rcx
  __int64 v86; // r9
  __int128 *v87; // rcx
  __int128 *v88; // rax
  __int64 v89; // r8
  __int64 v90; // [rsp+20h] [rbp-628h]
  bool v91; // [rsp+50h] [rbp-5F8h]
  char v92; // [rsp+50h] [rbp-5F8h]
  char v93; // [rsp+51h] [rbp-5F7h]
  bool v94; // [rsp+52h] [rbp-5F6h]
  void *v95; // [rsp+58h] [rbp-5F0h] BYREF
  int v96; // [rsp+60h] [rbp-5E8h]
  _OWORD *v97; // [rsp+68h] [rbp-5E0h] BYREF
  SelectionManager *v98; // [rsp+70h] [rbp-5D8h]
  struct std::nothrow_t *v99; // [rsp+78h] [rbp-5D0h] BYREF
  __int128 v100; // [rsp+80h] [rbp-5C8h] BYREF
  _BYTE v101[20]; // [rsp+90h] [rbp-5B8h] BYREF
  SelectionManager *v102; // [rsp+A8h] [rbp-5A0h]
  unsigned __int16 *v103; // [rsp+B0h] [rbp-598h]
  char *v104; // [rsp+B8h] [rbp-590h]
  _OWORD *v105; // [rsp+C0h] [rbp-588h]
  int *v106; // [rsp+C8h] [rbp-580h]
  char v107; // [rsp+D0h] [rbp-578h]
  int v108; // [rsp+D8h] [rbp-570h] BYREF
  void *v109[2]; // [rsp+E0h] [rbp-568h] BYREF
  _BYTE *v110; // [rsp+F0h] [rbp-558h]
  __int128 v111; // [rsp+F8h] [rbp-550h] BYREF
  __int64 v112; // [rsp+108h] [rbp-540h]
  __int128 v113; // [rsp+110h] [rbp-538h] BYREF
  int v114; // [rsp+120h] [rbp-528h]
  int v115; // [rsp+124h] [rbp-524h]
  _DWORD v116[2]; // [rsp+128h] [rbp-520h] BYREF
  __int128 v117; // [rsp+130h] [rbp-518h]
  __int128 v118; // [rsp+140h] [rbp-508h]
  __int128 v119; // [rsp+150h] [rbp-4F8h]
  int v120; // [rsp+160h] [rbp-4E8h]
  char v121; // [rsp+164h] [rbp-4E4h] BYREF
  char v122; // [rsp+364h] [rbp-2E4h] BYREF
  unsigned __int16 v123[8]; // [rsp+570h] [rbp-D8h] BYREF
  __int128 v124; // [rsp+580h] [rbp-C8h]
  __int128 v125; // [rsp+590h] [rbp-B8h]
  __int128 v126; // [rsp+5A0h] [rbp-A8h]
  __int128 v127; // [rsp+5B0h] [rbp-98h]
  __int128 v128; // [rsp+5C0h] [rbp-88h]
  __int128 v129; // [rsp+5D0h] [rbp-78h]
  __int128 v130; // [rsp+5E0h] [rbp-68h]
  __int16 v131; // [rsp+5F0h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+648h] [rbp+0h]

  v95 = a2;
  v98 = this;
  v102 = this;
  v103 = a2;
  v99 = (struct std::nothrow_t *)a7;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u
    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    WPP_SF_s(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      41,
      WPP_1e598accbd0633246e27c279a8537074_Traceguids,
      "SelectionManager::InternalGetSelectableConnectionList");
  }
  v11 = 0;
  *(_OWORD *)v123 = 0;
  v124 = 0;
  v125 = 0;
  v126 = 0;
  v127 = 0;
  v128 = 0;
  v129 = 0;
  v130 = 0;
  v131 = 0;
  *(_OWORD *)v109 = 0;
  v110 = 0;
  *(double *)&v11 = std::vector<FirewallManager::TrafficDescriptor>::vector<FirewallManager::TrafficDescriptor>(v109);
  v111 = v11;
  v112 = 0;
  *(double *)&v11 = std::vector<FirewallManager::TrafficDescriptor>::vector<FirewallManager::TrafficDescriptor>(&v111);
  v100 = v11;
  SelectionFilterEngine::CreateSelectionFilterInstance(&v100, a3, a4);
  *a7 = 0;
  v12 = !(unsigned int)_o__wcsicmp(a2, L"localhost")
     || !(unsigned int)_o__wcsicmp(a2, L"127.0.0.1")
     || !(unsigned int)_o__wcsicmp(a2, L"::1")
     || !(unsigned int)_o__wcsicmp(a2, L"[::1]");
  v94 = v12;
  if ( !a5 && v12 )
  {
    ApplicationIdentifier = 1;
    j = v109[0];
    v61 = WPP_GLOBAL_Control;
    goto LABEL_112;
  }
  v91 = RouteManager::IsInFailoverState();
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
  v104 = (char *)this + 112;
  v13 = *((_QWORD *)this + 20);
  v97 = (_OWORD *)v13;
  if ( v13 > 0xEE70C03B25E4463DuLL * ((v110 - (char *)v109[0]) >> 2) )
  {
    if ( v13 > 0x3B25E4463CFF13LL )
      goto LABEL_200;
    std::vector<_WCM_SELECTABLE_CONNECTION_DETAIL>::_Reallocate<0>(v109, &v97);
  }
  v97 = (_OWORD *)v13;
  if ( v13 <= (v112 - (__int64)v111) >> 2 )
    goto LABEL_15;
  if ( v13 > 0x3FFFFFFFFFFFFFFFLL )
LABEL_200:
    std::_Xlength_error("vector too long");
  std::vector<unsigned long>::_Reallocate<0>(&v111, &v97);
LABEL_15:
  v93 = 0;
  v14 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u
    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    WPP_SF_d(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      42,
      WPP_1e598accbd0633246e27c279a8537074_Traceguids,
      (unsigned int)v13);
    v14 = WPP_GLOBAL_Control;
  }
  v15 = (_QWORD *)*((_QWORD *)this + 19);
  for ( i = (_QWORD *)*v15; i != v15; i = (_QWORD *)*i )
  {
    v17 = (__int64 *)i[2];
    if ( *((_BYTE *)v17 + 100) )
    {
      memset_0(&v113, 0, 0x454u);
      v113 = *(_OWORD *)((char *)v17 + 68);
      v114 = *((_DWORD *)v17 + 22);
      v115 = *((_DWORD *)v17 + 21);
      memset_0(v116, 0, 0x43Cu);
      *(_OWORD *)v101 = 0;
      if ( (unsigned __int64)v17[3] <= 7 )
        v18 = (__int64)v17;
      else
        v18 = *v17;
      v19 = *((_DWORD *)v17 + 21);
      *(_OWORD *)v101 = 0;
      v96 = 0;
      v97 = 0;
      AcquireSRWLockShared(&stru_18013F9C0);
      v21 = (_QWORD *)qword_18013FF70;
      if ( qword_18013FF70 == (_QWORD)xmmword_18013FF78 )
LABEL_24:
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x91,
          (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\cspmanager\\cspmanager.cpp",
          v20);
      while ( v19 != *(_DWORD *)(*v21 + 128LL) )
      {
        if ( ++v21 == (_QWORD *)xmmword_18013FF78 )
          goto LABEL_24;
      }
      Property = CspLoader::GetProperty(*v21, (char *)v17 + 68, v18, 32);
      ReleaseSRWLockShared(&stru_18013F9C0);
      if ( Property )
      {
        v37 = 0;
        v24 = *(_OWORD **)&v101[8];
      }
      else
      {
        v108 = v19;
        v23 = v97;
        v105 = v97;
        v106 = &v108;
        v107 = 1;
        v24 = operator new(0x20u);
        v97 = v24;
        *v24 = 0;
        v24[1] = 0;
        v25 = v108;
        *v24 = 0;
        *((_DWORD *)v24 + 2) = 1;
        *((_DWORD *)v24 + 3) = 1;
        *(_QWORD *)v24 = off_1800F8188;
        *((_DWORD *)v24 + 4) = v25;
        *((_QWORD *)v24 + 3) = v23;
        *(_QWORD *)v101 = v23;
        v117 = *v23;
        v118 = v23[1];
        v119 = v23[2];
        v120 = *((_DWORD *)v23 + 12);
        v116[1] = *((_DWORD *)v17 + 24);
        v116[0] = *((_DWORD *)v17 + 16);
        v26 = v17 + 4;
        if ( (unsigned __int64)v17[7] > 7 )
          v26 = (_QWORD *)*v26;
        v27 = 2147483646;
        v28 = 256;
        v29 = &v122;
        while ( v27 )
        {
          v30 = *(_WORD *)v26;
          if ( !*(_WORD *)v26 )
            break;
          v26 = (_QWORD *)((char *)v26 + 2);
          *(_WORD *)v29 = v30;
          v29 += 2;
          --v27;
          if ( !--v28 )
          {
            *((_WORD *)v29 - 1) = 0;
            v31 = 0;
            goto LABEL_33;
          }
        }
        *(_WORD *)v29 = 0;
        v31 = 1;
LABEL_33:
        if ( !v31 )
          wil::details::in1diag3::_FailFast_Hr(
            retaddr,
            (void *)0x4B,
            (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\selection\\lib\\selectableconnection.cpp",
            (const char *)0x8000FFFFLL,
            0);
        if ( (unsigned __int64)v17[3] > 7 )
          v17 = (__int64 *)*v17;
        v32 = 2147483646;
        v33 = 256;
        v34 = &v121;
        while ( v32 )
        {
          v35 = *(_WORD *)v17;
          if ( !*(_WORD *)v17 )
            break;
          v17 = (__int64 *)((char *)v17 + 2);
          *(_WORD *)v34 = v35;
          v34 += 2;
          --v32;
          if ( !--v33 )
          {
            *((_WORD *)v34 - 1) = 0;
            v36 = 0;
            goto LABEL_41;
          }
        }
        *(_WORD *)v34 = 0;
        v36 = 1;
LABEL_41:
        if ( !v36 )
          wil::details::in1diag3::_FailFast_Hr(
            retaddr,
            (void *)0x51,
            (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\selection\\lib\\selectableconnection.cpp",
            (const char *)0x8000FFFFLL,
            0);
        v37 = 1;
      }
      if ( v24 )
        std::_Ref_count_base::_Decref((std::_Ref_count_base *)v24);
      if ( v37 )
      {
        if ( v115 == 2 && v91 )
        {
          v14 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u
            && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          {
            v72 = (__int64 *)i[2];
            if ( (unsigned __int64)v72[3] <= 7 )
              v73 = i[2];
            else
              v73 = *v72;
            v39 = v72 + 4;
            if ( (unsigned __int64)v72[7] > 7 )
              v39 = (_QWORD *)*v39;
            v40 = 45;
            v90 = v73;
            goto LABEL_59;
          }
        }
        else if ( (*(unsigned __int8 (__fastcall **)(_QWORD, __int128 *, _QWORD))(*(_QWORD *)v100 + 8LL))(
                    v100,
                    &v113,
                    a6) )
        {
          v41 = (__int128 *)v109[1];
          if ( v109[1] == v110 )
          {
            std::vector<_WCM_SELECTABLE_CONNECTION_DETAIL>::_Emplace_reallocate<_WCM_SELECTABLE_CONNECTION_DETAIL const &>(
              v109,
              v109[1],
              &v113);
          }
          else
          {
            v42 = &v113;
            v43 = 8;
            do
            {
              *v41 = *v42;
              v41[1] = v42[1];
              v41[2] = v42[2];
              v41[3] = v42[3];
              v41[4] = v42[4];
              v41[5] = v42[5];
              v41[6] = v42[6];
              v41[7] = v42[7];
              v41 += 8;
              v42 += 8;
              --v43;
            }
            while ( v43 );
            *v41 = *v42;
            v41[1] = v42[1];
            v41[2] = v42[2];
            v41[3] = v42[3];
            v41[4] = v42[4];
            *((_DWORD *)v41 + 20) = *((_DWORD *)v42 + 20);
            v109[1] = (char *)v109[1] + 1108;
          }
          v44 = (_DWORD *)(i[2] + 88LL);
          if ( *((_QWORD *)&v111 + 1) == v112 )
          {
            std::vector<unsigned long>::_Emplace_reallocate<unsigned long const &>(&v111, *((_QWORD *)&v111 + 1), v44);
          }
          else
          {
            **((_DWORD **)&v111 + 1) = *v44;
            *((_QWORD *)&v111 + 1) += 4LL;
          }
          v14 = WPP_GLOBAL_Control;
        }
        else
        {
          v93 = 1;
          v14 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u
            && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          {
            v77 = (_QWORD *)(i[2] + 32LL);
            if ( *(_QWORD *)(i[2] + 56LL) > 7u )
              v77 = (_QWORD *)*v77;
            WPP_SF_S(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 46, WPP_1e598accbd0633246e27c279a8537074_Traceguids, v77);
            v14 = WPP_GLOBAL_Control;
          }
        }
      }
      else
      {
        v14 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u
          && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        {
          v75 = (__int64 *)i[2];
          if ( (unsigned __int64)v75[3] <= 7 )
            v76 = i[2];
          else
            v76 = *v75;
          v39 = v75 + 4;
          if ( (unsigned __int64)v75[7] > 7 )
            v39 = (_QWORD *)*v39;
          v40 = 44;
          v90 = v76;
LABEL_59:
          WPP_SF_SS(
            *(_QWORD *)(v14 + 16),
            v40,
            (unsigned int)WPP_1e598accbd0633246e27c279a8537074_Traceguids,
            (_DWORD)v39,
            v90);
          v14 = WPP_GLOBAL_Control;
          continue;
        }
      }
    }
    else if ( (_UNKNOWN *)v14 != &WPP_GLOBAL_Control && *(_BYTE *)(v14 + 25) >= 4u && (*(_BYTE *)(v14 + 28) & 1) != 0 )
    {
      if ( (unsigned __int64)v17[3] <= 7 )
        v38 = i[2];
      else
        v38 = *v17;
      v39 = v17 + 4;
      if ( (unsigned __int64)v17[7] > 7 )
        v39 = (_QWORD *)*v39;
      v40 = 43;
      v90 = v38;
      goto LABEL_59;
    }
  }
  ApplicationIdentifier = 0;
  v96 = 0;
  v46 = 0;
  v108 = 0;
  v47 = 0;
  v92 = 0;
  if ( v98 != (SelectionManager *)-112LL )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v98 + 112));
  std::_Sort_unchecked<_WCM_SELECTABLE_CONNECTION_DETAIL *,bool (*)(_WCM_SELECTABLE_CONNECTION_DETAIL const &,_WCM_SELECTABLE_CONNECTION_DETAIL const &)>(
    v109[0],
    v109[1],
    0xEE70C03B25E4463DuLL * (((char *)v109[1] - (char *)v109[0]) >> 2),
    SelectableConnectionSort);
  if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)v100 + 96LL))(v100) )
    goto LABEL_95;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u
    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 47, WPP_1e598accbd0633246e27c279a8537074_Traceguids);
  }
  ApplicationIdentifier = GetApplicationIdentifier(v123);
  v96 = ApplicationIdentifier;
  if ( ApplicationIdentifier < 0 )
  {
    v61 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 48, WPP_1e598accbd0633246e27c279a8537074_Traceguids);
        j = v109[0];
        v61 = WPP_GLOBAL_Control;
        goto LABEL_112;
      }
      goto LABEL_236;
    }
LABEL_147:
    j = v109[0];
  }
  else
  {
    v47 = 1;
    v92 = 1;
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v100 + 104LL))(v100);
    v50 = 0;
    v51 = qword_180140120;
    if ( qword_180140120 )
    {
      v52 = *((_DWORD *)qword_180140120 + 2);
      while ( v52 )
      {
        v53 = v52;
        v52 = _InterlockedCompareExchange((volatile signed __int32 *)v51 + 2, v52 + 1, v52);
        if ( v53 == v52 )
        {
          v50 = qword_180140120;
          if ( !qword_180140118 )
            break;
          v54 = (int)v95;
          v55 = MappingPolicyManager::InternalFilterConnectionsByMappingPolicy(qword_180140118, (__int64)v109);
          if ( v50 )
            std::_Ref_count_base::_Decref(v50);
          if ( !v55 )
            goto LABEL_82;
          v61 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 4u
            || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          {
LABEL_172:
            v46 = 1;
            v108 = 1;
            goto LABEL_96;
          }
          WPP_SF_SS(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            49,
            (unsigned int)WPP_1e598accbd0633246e27c279a8537074_Traceguids,
            (_DWORD)v95,
            (__int64)v123);
          v46 = 1;
          v108 = 1;
          goto LABEL_95;
        }
      }
    }
    if ( v50 )
      std::_Ref_count_base::_Decref(v50);
    v54 = (int)v95;
LABEL_82:
    v56 = 0;
    v57 = qword_1801400D0;
    if ( qword_1801400D0 )
    {
      v58 = *((_DWORD *)qword_1801400D0 + 2);
      while ( v58 )
      {
        v59 = v58;
        v58 = _InterlockedCompareExchange((volatile signed __int32 *)v57 + 2, v58 + 1, v58);
        if ( v59 == v58 )
        {
          v56 = qword_1801400D0;
          if ( !qword_1801400C8 )
            break;
          v60 = RoutePolicyManager::InternalFilterConnectionsByRoutePolicy(qword_1801400C8);
          if ( v56 )
            std::_Ref_count_base::_Decref(v56);
          if ( v60 )
          {
            v61 = WPP_GLOBAL_Control;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u
              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
            {
              WPP_SF_SS(
                *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                50,
                (unsigned int)WPP_1e598accbd0633246e27c279a8537074_Traceguids,
                (_DWORD)v95,
                (__int64)v123);
              v61 = WPP_GLOBAL_Control;
            }
            goto LABEL_172;
          }
          goto LABEL_90;
        }
      }
    }
    if ( v56 )
      std::_Ref_count_base::_Decref(v56);
LABEL_90:
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      WPP_SF_SS(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        51,
        (unsigned int)WPP_1e598accbd0633246e27c279a8537074_Traceguids,
        v54,
        (__int64)v123);
    }
    MappingPolicyManager::FilterConnectionsByDefaultPolicy(v109);
LABEL_95:
    v61 = WPP_GLOBAL_Control;
LABEL_96:
    v62 = v46;
    LODWORD(v97) = v46;
    if ( (_UNKNOWN *)v61 != &WPP_GLOBAL_Control && *(_BYTE *)(v61 + 25) >= 4u && (*(_BYTE *)(v61 + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *(_QWORD *)(v61 + 16),
        52,
        WPP_1e598accbd0633246e27c279a8537074_Traceguids,
        0xEE70C03B25E4463DuLL * (((char *)v109[1] - (char *)v109[0]) >> 2));
      v61 = WPP_GLOBAL_Control;
    }
    v63 = v109[1];
    j = v109[0];
    if ( v109[0] != v109[1] )
    {
      do
      {
        if ( (_UNKNOWN *)v61 != &WPP_GLOBAL_Control && *(_BYTE *)(v61 + 25) >= 4u && (*(_BYTE *)(v61 + 28) & 1) != 0 )
        {
          WPP_SF_SS_guid_Ddd(
            *(_QWORD *)(v61 + 16),
            v48,
            v49,
            (_DWORD)j + 596,
            (__int64)(j + 21),
            (__int64)j,
            j[4],
            j[5],
            j[8]);
          v61 = WPP_GLOBAL_Control;
        }
        j += 277;
      }
      while ( j != (_DWORD *)v63 );
      v63 = v109[1];
      j = v109[0];
    }
    v65 = v98;
    if ( 0xEE70C03B25E4463DuLL * ((v63 - (_BYTE *)j) >> 2) && j[5] == 3 && j[8] == 1 && !j[7] && !*((_BYTE *)v98 + 464) )
    {
      if ( (_UNKNOWN *)v61 != &WPP_GLOBAL_Control && *(_BYTE *)(v61 + 25) >= 4u && (*(_BYTE *)(v61 + 28) & 1) != 0 )
      {
        WPP_SF__guid_S(
          *(_QWORD *)(v61 + 16),
          53,
          (unsigned int)WPP_1e598accbd0633246e27c279a8537074_Traceguids,
          (_DWORD)j,
          (__int64)(j + 149));
        j = v109[0];
        v65 = v98;
      }
      try
      {
        *(_DWORD *)v101 = j[5];
        *(_OWORD *)&v101[4] = *(_OWORD *)j;
        WcmCommon::ThreadPoolProcessLatestWorkItem_1_::SubmitWork__SelectionManager::InternalGetSelectableConnectionList_::_41_::_lambda_1___(
          (char *)v65 + 232,
          v101);
        v65 = v98;
      }
      catch ( std::exception )
      {
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u
          && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        {
          WPP_SF__guid_(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            55,
            WPP_1e598accbd0633246e27c279a8537074_Traceguids,
            v109[0]);
        }
        ApplicationIdentifier = v96;
        v46 = v108;
        v47 = v92;
        v62 = (unsigned int)v97;
        v65 = v102;
        v95 = v103;
      }
      v61 = WPP_GLOBAL_Control;
      j = v109[0];
      v63 = v109[1];
    }
    v66 = j != (_DWORD *)v63 && j[8] == 4;
    if ( !a5 && !v93 && !v62 && v66 )
    {
      ApplicationIdentifier = 1;
      goto LABEL_112;
    }
    if ( *((_BYTE *)v65 + 465) && !v94 && j != (_DWORD *)v63 )
    {
      if ( !v47 )
      {
        ApplicationIdentifier = GetApplicationIdentifier(v123);
        if ( ApplicationIdentifier < 0 )
        {
          v61 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
          {
            if ( *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
            {
              WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 56, WPP_1e598accbd0633246e27c279a8537074_Traceguids);
              j = v109[0];
              v61 = WPP_GLOBAL_Control;
              goto LABEL_112;
            }
LABEL_236:
            j = v109[0];
            goto LABEL_112;
          }
          goto LABEL_147;
        }
      }
      v80 = VpnCmOracleCheckVpnAvailability(v95, v46, v111, (__int64)(*((_QWORD *)&v111 + 1) - v111) >> 2, v123);
      ApplicationIdentifier = v80;
      v61 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u
        && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 57, WPP_1e598accbd0633246e27c279a8537074_Traceguids, v80);
        v61 = WPP_GLOBAL_Control;
      }
      if ( ApplicationIdentifier < 0 || ApplicationIdentifier == 1 && !a5 )
        goto LABEL_236;
      v63 = v109[1];
      j = v109[0];
    }
    if ( !v62 && 0xEE70C03B25E4463DuLL * ((v63 - (_BYTE *)j) >> 2) > 1 )
    {
      if ( (_UNKNOWN *)v61 != &WPP_GLOBAL_Control && *(_BYTE *)(v61 + 25) >= 4u && (*(_BYTE *)(v61 + 28) & 1) != 0 )
      {
        WPP_SF_(*(_QWORD *)(v61 + 16), 58, WPP_1e598accbd0633246e27c279a8537074_Traceguids);
        v63 = v109[1];
        j = v109[0];
        v61 = WPP_GLOBAL_Control;
      }
      ApplicationIdentifier = 2;
    }
    if ( j == (_DWORD *)v63 )
    {
      ApplicationIdentifier = -2147023728;
    }
    else
    {
      v78 = MIDL_user_allocate(1108 * (0xEE70C03B25E4463DuLL * ((v63 - (_BYTE *)j) >> 2) - 1) + 1112);
      if ( !v78 )
        wil::details::in1diag3::_Throw_NullAlloc(
          retaddr,
          (void *)0x4CF,
          (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\selection\\lib\\selectionmanager.cpp",
          v79);
      v81 = v99;
      *(_QWORD *)v99 = v78;
      *v78 = 635717181 * (((char *)v109[1] - (char *)v109[0]) >> 2);
      v82 = 0;
      for ( j = v109[0]; v82 < 0xEE70C03B25E4463DuLL * (((char *)v109[1] - (char *)v109[0]) >> 2); j = v109[0] )
      {
        v83 = 277LL * v82;
        v84 = (__int128 *)&j[v83];
        v85 = &v113;
        v86 = 8;
        do
        {
          *v85 = *v84;
          v85[1] = v84[1];
          v85[2] = v84[2];
          v85[3] = v84[3];
          v85[4] = v84[4];
          v85[5] = v84[5];
          v85[6] = v84[6];
          v85[7] = v84[7];
          v85 += 8;
          v84 += 8;
          --v86;
        }
        while ( v86 );
        *v85 = *v84;
        v85[1] = v84[1];
        v85[2] = v84[2];
        v85[3] = v84[3];
        v85[4] = v84[4];
        *((_DWORD *)v85 + 20) = *((_DWORD *)v84 + 20);
        v87 = (__int128 *)(v83 * 4 + *(_QWORD *)v81 + 4LL);
        v88 = &v113;
        v89 = 8;
        do
        {
          *v87 = *v88;
          v87[1] = v88[1];
          v87[2] = v88[2];
          v87[3] = v88[3];
          v87[4] = v88[4];
          v87[5] = v88[5];
          v87[6] = v88[6];
          v87[7] = v88[7];
          v87 += 8;
          v88 += 8;
          --v89;
        }
        while ( v89 );
        *v87 = *v88;
        v87[1] = v88[1];
        v87[2] = v88[2];
        v87[3] = v88[3];
        v87[4] = v88[4];
        *((_DWORD *)v87 + 20) = *((_DWORD *)v88 + 20);
        ++v82;
      }
      v61 = WPP_GLOBAL_Control;
    }
LABEL_112:
    if ( (_UNKNOWN *)v61 != &WPP_GLOBAL_Control && *(_BYTE *)(v61 + 25) >= 5u && (*(_BYTE *)(v61 + 28) & 1) != 0 )
    {
      if ( ApplicationIdentifier < 0 )
      {
        v74 = ApplicationIdentifier;
        if ( (ApplicationIdentifier & 0x1FFF0000) != 0x70000 )
          v74 = ApplicationIdentifier;
      }
      else
      {
        v74 = 0;
      }
      WPP_SF_sL(
        *(_QWORD *)(v61 + 16),
        59,
        (unsigned int)WPP_1e598accbd0633246e27c279a8537074_Traceguids,
        (unsigned int)"SelectionManager::InternalGetSelectableConnectionList",
        v74);
      goto LABEL_147;
    }
  }
  v67 = (volatile signed __int32 *)*((_QWORD *)&v100 + 1);
  if ( *((_QWORD *)&v100 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v100 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v67)(v67);
      if ( _InterlockedExchangeAdd(v67 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v67 + 8LL))(v67);
    }
    j = v109[0];
  }
  v68 = (void *)v111;
  if ( (_QWORD)v111 )
  {
    v69 = (struct std::nothrow_t *)((v112 - v111) & 0xFFFFFFFFFFFFFFFCuLL);
    v99 = v69;
    v95 = (void *)v111;
    if ( (unsigned __int64)v69 >= 0x1000 )
    {
      std::_Adjust_manually_vector_aligned(&v95, (unsigned __int64 *)&v99);
      v69 = v99;
      v68 = v95;
    }
    operator delete(v68, v69);
    v111 = 0;
    v112 = 0;
    j = v109[0];
  }
  if ( j )
  {
    v70 = (struct std::nothrow_t *)(4 * ((v110 - (_BYTE *)j) >> 2));
    v99 = v70;
    v95 = j;
    if ( (unsigned __int64)v70 >= 0x1000 )
    {
      std::_Adjust_manually_vector_aligned(&v95, (unsigned __int64 *)&v99);
      v70 = v99;
      j = v95;
    }
    operator delete(j, v70);
  }
  return (unsigned int)ApplicationIdentifier;
}

```

## disassembly

```asm
0x18000e970  push    rbx
0x18000e972  push    rsi
0x18000e973  push    rdi
0x18000e974  push    r12
0x18000e976  push    r13
0x18000e978  push    r14
0x18000e97a  push    r15
0x18000e97c  sub     rsp, 610h
0x18000e983  mov     rax, cs:__security_cookie
0x18000e98a  xor     rax, rsp
0x18000e98d  mov     [rsp+648h+var_48], rax
0x18000e995  mov     ebx, r9d
0x18000e998  mov     rdi, r8
0x18000e99b  mov     r14, rdx
0x18000e99e  mov     [rsp+648h+var_5F0], rdx
0x18000e9a3  mov     r15, rcx
0x18000e9a6  mov     [rsp+648h+var_5D8], rcx
0x18000e9ab  mov     [rsp+648h+var_5A0], rcx
0x18000e9b3  mov     [rsp+648h+var_598], rdx
0x18000e9bb  mov     r12, [rsp+648h+arg_30]
0x18000e9c3  mov     [rsp+648h+var_5D0], r12
0x18000e9c8  lea     rsi, WPP_GLOBAL_Control
0x18000e9cf  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e9d6  cmp     rcx, rsi
0x18000e9d9  jnz     loc_18000F5F8
0x18000e9df  xorps   xmm0, xmm0
0x18000e9e2  xor     eax, eax
0x18000e9e4  movups  xmmword ptr [rsp+648h+var_D8], xmm0
0x18000e9ec  movups  [rsp+648h+var_C8], xmm0
0x18000e9f4  movups  [rsp+648h+var_B8], xmm0
0x18000e9fc  movups  [rsp+648h+var_A8], xmm0
0x18000ea04  movups  [rsp+648h+var_98], xmm0
0x18000ea0c  movups  [rsp+648h+var_88], xmm0
0x18000ea14  movups  [rsp+648h+var_78], xmm0
0x18000ea1c  movups  [rsp+648h+var_68], xmm0
0x18000ea24  mov     [rsp+648h+var_58], ax
0x18000ea2c  movups  xmmword ptr [rsp+648h+var_568], xmm0
0x18000ea34  mov     [rsp+648h+var_558], rax
0x18000ea3c  lea     rcx, [rsp+648h+var_568]
0x18000ea44  call    ??0?$vector@UTrafficDescriptor@FirewallManager@@V?$allocator@UTrafficDescriptor@FirewallManager@@@std@@@std@@QEAA@XZ; std::vector<FirewallManager::TrafficDescriptor>::vector<FirewallManager::TrafficDescriptor>(void)
0x18000ea49  nop
0x18000ea4a  xor     eax, eax
0x18000ea4c  movups  [rsp+648h+var_550], xmm0
0x18000ea54  mov     [rsp+648h+var_540], rax
0x18000ea5c  lea     rcx, [rsp+648h+var_550]
0x18000ea64  call    ??0?$vector@UTrafficDescriptor@FirewallManager@@V?$allocator@UTrafficDescriptor@FirewallManager@@@std@@@std@@QEAA@XZ; std::vector<FirewallManager::TrafficDescriptor>::vector<FirewallManager::TrafficDescriptor>(void)
0x18000ea69  nop
0x18000ea6a  movups  [rsp+648h+var_5C8], xmm0
0x18000ea72  mov     r8d, ebx
0x18000ea75  mov     rdx, rdi
0x18000ea78  lea     rcx, [rsp+648h+var_5C8]
0x18000ea80  call    ?CreateSelectionFilterInstance@SelectionFilterEngine@@YA?AV?$shared_ptr@VSelectionFilter@@@std@@PEBEK@Z; SelectionFilterEngine::CreateSelectionFilterInstance(uchar const *,ulong)
0x18000ea85  nop
0x18000ea86  xor     r13d, r13d
0x18000ea89  mov     [r12], r13
0x18000ea8d  lea     rdx, aLocalhost; "localhost"
0x18000ea94  mov     rcx, r14
0x18000ea97  call    cs:__imp__o__wcsicmp
0x18000ea9d  test    eax, eax
0x18000ea9f  jz      loc_18000F6F7
0x18000eaa5  lea     rdx, a127001; "127.0.0.1"
0x18000eaac  mov     rcx, r14
0x18000eaaf  call    cs:__imp__o__wcsicmp
0x18000eab5  test    eax, eax
0x18000eab7  jz      loc_18000F6F7
0x18000eabd  lea     rdx, a1_1; "::1"
0x18000eac4  mov     rcx, r14
0x18000eac7  call    cs:__imp__o__wcsicmp
0x18000eacd  test    eax, eax
0x18000eacf  jz      loc_18000F6F7
0x18000ead5  lea     rdx, a1_0; "[::1]"
0x18000eadc  mov     rcx, r14
0x18000eadf  call    cs:__imp__o__wcsicmp
0x18000eae5  test    eax, eax
0x18000eae7  jz      loc_18000F6F7
0x18000eaed  xor     al, al
0x18000eaef  mov     [rsp+648h+var_5F6], al
0x18000eaf3  cmp     [rsp+648h+arg_20], r13d
0x18000eafb  jnz     short loc_18000EB05
0x18000eafd  test    al, al
0x18000eaff  jnz     loc_18000F7DC
0x18000eb05  call    ?IsInFailoverState@RouteManager@@SA_NXZ; RouteManager::IsInFailoverState(void)
0x18000eb0a  mov     [rsp+648h+var_5F8], al
0x18000eb0e  lea     r14, [r15+70h]
0x18000eb12  mov     rcx, r14; lpCriticalSection
0x18000eb15  call    cs:__imp_EnterCriticalSection
0x18000eb1b  mov     [rsp+648h+var_590], r14
0x18000eb23  mov     rbx, [r15+0A0h]
0x18000eb2a  mov     [rsp+648h+var_5E0], rbx
0x18000eb2f  mov     rcx, [rsp+648h+var_558]
0x18000eb37  sub     rcx, [rsp+648h+var_568]
0x18000eb3f  sar     rcx, 2
0x18000eb43  mov     rax, 0EE70C03B25E4463Dh
0x18000eb4d  imul    rcx, rax
0x18000eb51  cmp     rbx, rcx
0x18000eb54  jbe     short loc_18000EB7B
0x18000eb56  mov     rax, 3B25E4463CFF13h
0x18000eb60  cmp     rbx, rax
0x18000eb63  ja      loc_18000F9A2
0x18000eb69  lea     rdx, [rsp+648h+var_5E0]
0x18000eb6e  lea     rcx, [rsp+648h+var_568]
0x18000eb76  call    ??$_Reallocate@$0A@@?$vector@U_WCM_SELECTABLE_CONNECTION_DETAIL@@V?$allocator@U_WCM_SELECTABLE_CONNECTION_DETAIL@@@std@@@std@@AEAAXAEA_K@Z; std::vector<_WCM_SELECTABLE_CONNECTION_DETAIL>::_Reallocate<0>(unsigned __int64 &)
0x18000eb7b  mov     [rsp+648h+var_5E0], rbx
0x18000eb80  mov     rax, [rsp+648h+var_540]
0x18000eb88  sub     rax, qword ptr [rsp+648h+var_550]
0x18000eb90  sar     rax, 2
0x18000eb94  cmp     rbx, rax
0x18000eb97  jbe     short loc_18000EBBE
0x18000eb99  mov     rax, 3FFFFFFFFFFFFFFFh
0x18000eba3  cmp     rbx, rax
0x18000eba6  ja      loc_18000F9A2
0x18000ebac  lea     rdx, [rsp+648h+var_5E0]
0x18000ebb1  lea     rcx, [rsp+648h+var_550]
0x18000ebb9  call    ??$_Reallocate@$0A@@?$vector@KV?$allocator@K@std@@@std@@AEAAXAEA_K@Z; std::vector<ulong>::_Reallocate<0>(unsigned __int64 &)
0x18000ebbe  mov     [rsp+648h+var_5F7], 0
0x18000ebc3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ebca  cmp     rcx, rsi
0x18000ebcd  jnz     loc_18000F4F6
0x18000ebd3  mov     rdi, [r15+98h]
0x18000ebda  mov     rbx, [rdi]
0x18000ebdd  nop     dword ptr [rax]
0x18000ebe0  cmp     rbx, rdi
0x18000ebe3  jz      loc_18000F088
0x18000ebe9  mov     r14, [rbx+10h]
0x18000ebed  cmp     byte ptr [r14+64h], 0
0x18000ebf2  jz      loc_18000EF0E
0x18000ebf8  xor     edx, edx; Val
0x18000ebfa  mov     r8d, 454h; Size
0x18000ec00  lea     rcx, [rsp+648h+var_538]; void *
0x18000ec08  call    memset_0
0x18000ec0d  movups  xmm0, xmmword ptr [r14+44h]
0x18000ec12  movaps  [rsp+648h+var_538], xmm0
0x18000ec1a  mov     eax, [r14+58h]
0x18000ec1e  mov     [rsp+648h+var_528], eax
0x18000ec25  mov     eax, [r14+54h]
0x18000ec29  mov     [rsp+648h+var_524], eax
0x18000ec30  xor     edx, edx; Val
0x18000ec32  mov     r8d, 43Ch; Size
0x18000ec38  lea     rcx, [rsp+648h+var_520]; void *
0x18000ec40  call    memset_0
0x18000ec45  xorps   xmm0, xmm0
0x18000ec48  movups  xmmword ptr [rsp+648h+var_5B8], xmm0
0x18000ec50  cmp     qword ptr [r14+18h], 7
0x18000ec55  jbe     loc_18000EEE3
0x18000ec5b  mov     r12, [r14]
0x18000ec5e  mov     r15d, [r14+54h]
0x18000ec62  movdqu  xmmword ptr [rsp+648h+var_5B8], xmm0
0x18000ec6b  mov     [rsp+648h+var_5E8], r13d
0x18000ec70  mov     [rsp+648h+var_5E0], r13
0x18000ec75  lea     rcx, stru_18013F9C0; SRWLock
0x18000ec7c  call    cs:__imp_AcquireSRWLockShared
0x18000ec82  mov     rcx, cs:qword_18013FF70
0x18000ec89  mov     rdx, qword ptr cs:xmmword_18013FF78
0x18000ec90  cmp     rcx, rdx
0x18000ec93  jz      short loc_18000ECB5
0x18000ec95  nop     word ptr [rax+rax+00000000h]
0x18000eca0  mov     rax, [rcx]
0x18000eca3  cmp     r15d, [rax+80h]
0x18000ecaa  jz      short loc_18000ECCF
0x18000ecac  add     rcx, 8
0x18000ecb0  cmp     rcx, rdx
0x18000ecb3  jnz     short loc_18000ECA0
0x18000ecb5  mov     rcx, [rsp+648h]; this
0x18000ecbd  lea     r8, aOnecoreuapNetW_32; "onecoreuap\\net\\wcm\\service\\base\\cs"...
0x18000ecc4  mov     edx, 91h; void *
0x18000ecc9  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18000eccf  lea     rax, [rsp+648h+var_5E0]
0x18000ecd4  mov     [rsp+648h+var_610], rax
0x18000ecd9  lea     rax, [rsp+648h+var_5E8]
0x18000ecde  mov     [rsp+648h+var_618], rax
0x18000ece3  mov     [rsp+648h+var_620], r13
0x18000ece8  mov     dword ptr [rsp+648h+var_628], r13d; int
0x18000eced  mov     r9d, 20h ; ' '
0x18000ecf3  mov     r8, r12
0x18000ecf6  lea     rdx, [r14+44h]
0x18000ecfa  mov     rcx, [rcx]
0x18000ecfd  call    ?GetProperty@CspLoader@@QEAAKPEBU_GUID@@PEBGW4WCM_CSP_PROPERTY@@KPEAEPEAKPEAPEAEK@Z; CspLoader::GetProperty(_GUID const *,ushort const *,WCM_CSP_PROPERTY,ulong,uchar *,ulong *,uchar * *,ulong)
0x18000ed02  mov     esi, eax
0x18000ed04  lea     rcx, stru_18013F9C0; SRWLock
0x18000ed0b  call    cs:__imp_ReleaseSRWLockShared
0x18000ed11  test    esi, esi
0x18000ed13  jnz     loc_18000F858
0x18000ed19  mov     [rsp+648h+var_570], r15d
0x18000ed21  mov     rsi, [rsp+648h+var_5E0]
0x18000ed26  mov     [rsp+648h+var_588], rsi
0x18000ed2e  lea     rax, [rsp+648h+var_570]
0x18000ed36  mov     [rsp+648h+var_580], rax
0x18000ed3e  mov     [rsp+648h+var_578], 1
0x18000ed46  mov     ecx, 20h ; ' '; Size
0x18000ed4b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000ed50  mov     r10, rax
0x18000ed53  mov     [rsp+648h+var_5E0], rax
0x18000ed58  xorps   xmm0, xmm0
0x18000ed5b  movups  xmmword ptr [rax], xmm0
0x18000ed5e  movups  xmmword ptr [rax+10h], xmm0
0x18000ed62  mov     eax, [rsp+648h+var_570]
0x18000ed69  movups  xmmword ptr [r10], xmm0
0x18000ed6d  mov     dword ptr [r10+8], 1
0x18000ed75  mov     dword ptr [r10+0Ch], 1
0x18000ed7d  lea     rcx, off_1800F8188
0x18000ed84  mov     [r10], rcx
0x18000ed87  mov     [r10+10h], eax
0x18000ed8b  mov     [r10+18h], rsi
0x18000ed8f  mov     qword ptr [rsp+648h+var_5B8], rsi
0x18000ed97  movups  xmm0, xmmword ptr [rsi]
0x18000ed9a  movaps  [rsp+648h+var_518], xmm0
0x18000eda2  movups  xmm1, xmmword ptr [rsi+10h]
0x18000eda6  movaps  [rsp+648h+var_508], xmm1
0x18000edae  movups  xmm0, xmmword ptr [rsi+20h]
0x18000edb2  movaps  [rsp+648h+var_4F8], xmm0
0x18000edba  mov     eax, [rsi+30h]
0x18000edbd  mov     [rsp+648h+var_4E8], eax
0x18000edc4  mov     eax, [r14+60h]
0x18000edc8  mov     [rsp+648h+var_51C], eax
0x18000edcf  mov     eax, [r14+40h]
0x18000edd3  mov     [rsp+648h+var_520], eax
0x18000edda  lea     rdx, [r14+20h]
0x18000edde  cmp     qword ptr [rdx+18h], 7
0x18000ede3  ja      loc_18000EEEB
0x18000ede9  mov     ecx, 7FFFFFFEh
0x18000edee  mov     r8d, 100h
0x18000edf4  lea     r9, [rsp+648h+var_2E4]
0x18000edfc  nop     dword ptr [rax+00h]
0x18000ee00  test    rcx, rcx
0x18000ee03  jz      loc_18000EEFB
0x18000ee09  movzx   eax, word ptr [rdx]
0x18000ee0c  test    ax, ax
0x18000ee0f  jz      short loc_18000EE28
0x18000ee11  add     rdx, 2
0x18000ee15  mov     [r9], ax
0x18000ee19  add     r9, 2
0x18000ee1d  dec     rcx
0x18000ee20  sub     r8, 1
0x18000ee24  jnz     short loc_18000EE00
0x18000ee26  jmp     short loc_18000EE31
0x18000ee28  test    r8, r8
0x18000ee2b  jnz     loc_18000EEFB
0x18000ee31  mov     [r9-2], r13w
0x18000ee36  xor     al, al
0x18000ee38  mov     rcx, [rsp+648h]; this
0x18000ee40  test    al, al
0x18000ee42  jz      loc_18000F9C8
0x18000ee48  cmp     qword ptr [r14+18h], 7
0x18000ee4d  ja      loc_18000EEF3
0x18000ee53  mov     ecx, 7FFFFFFEh
0x18000ee58  mov     edx, 100h
0x18000ee5d  lea     r8, [rsp+648h+var_4E4]
0x18000ee65  test    rcx, rcx
0x18000ee68  jz      loc_18000EF06
0x18000ee6e  movzx   eax, word ptr [r14]
0x18000ee72  test    ax, ax
0x18000ee75  jz      short loc_18000EE8E
0x18000ee77  add     r14, 2
0x18000ee7b  mov     [r8], ax
0x18000ee7f  add     r8, 2
0x18000ee83  dec     rcx
0x18000ee86  sub     rdx, 1
0x18000ee8a  jnz     short loc_18000EE65
0x18000ee8c  jmp     short loc_18000EE93
0x18000ee8e  test    rdx, rdx
0x18000ee91  jnz     short loc_18000EF06
0x18000ee93  mov     [r8-2], r13w
0x18000ee98  xor     al, al
0x18000ee9a  mov     rcx, [rsp+648h]; this
0x18000eea2  test    al, al
0x18000eea4  jz      loc_18000F9B0
0x18000eeaa  mov     esi, 1
0x18000eeaf  test    r10, r10
0x18000eeb2  jz      short loc_18000EEBC
0x18000eeb4  mov     rcx, r10; this
0x18000eeb7  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000eebc  test    esi, esi
0x18000eebe  jnz     loc_18000EF62
0x18000eec4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eecb  lea     rsi, WPP_GLOBAL_Control
0x18000eed2  cmp     rcx, rsi
0x18000eed5  jnz     loc_18000F9E0
0x18000eedb  mov     rbx, [rbx]
0x18000eede  jmp     loc_18000EBE0
0x18000eee3  mov     r12, r14
0x18000eee6  jmp     loc_18000EC5E
0x18000eeeb  mov     rdx, [rdx]
0x18000eeee  jmp     loc_18000EDE9
0x18000eef3  mov     r14, [r14]
0x18000eef6  jmp     loc_18000EE53
0x18000eefb  mov     [r9], r13w
0x18000eeff  mov     al, 1
0x18000ef01  jmp     loc_18000EE38
0x18000ef06  mov     [r8], r13w
0x18000ef0a  mov     al, 1
0x18000ef0c  jmp     short loc_18000EE9A
0x18000ef0e  cmp     rcx, rsi
0x18000ef11  jz      short loc_18000EEDB
0x18000ef13  cmp     byte ptr [rcx+19h], 4
0x18000ef17  jb      short loc_18000EEDB
0x18000ef19  test    byte ptr [rcx+1Ch], 1
0x18000ef1d  jz      short loc_18000EEDB
0x18000ef1f  cmp     qword ptr [r14+18h], 7
0x18000ef24  jbe     loc_18000F848
0x18000ef2a  mov     rax, [r14]
  ... truncated ...
```
