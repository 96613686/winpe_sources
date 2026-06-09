# VaultCreateCredentialFromSettingUnit(_SETTING_UNIT *,_GUID const *)

- ea: `0x180022290`
- end: `0x180023c83`
- name: `?VaultCreateCredentialFromSettingUnit@@YAKPEAU_SETTING_UNIT@@PEBU_GUID@@@Z`
- size: `6643`
- prototype: `unsigned int(struct _SETTING_UNIT *, const struct _GUID *)`
- caller_count: `2`
- callee_count: `24`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18001fb9c`
- `0x180045df0`

## callees

- `0x180003140`
- `0x180006610`
- `0x180008fec`
- `0x180009020`
- `0x1800091d0`
- `0x180012210`
- `0x18001eda0`
- `0x180020a24`
- `0x180020c80`
- `0x180022290`
- `0x180027340`
- `0x180028600`
- `0x18002a4a0`
- `0x18002a9e0`
- `0x18002d410`
- `0x18002ea00`
- `0x180030320`
- `0x1800311e0`
- `0x18003a580`
- `0x18003b7b0`
- `0x18003b7d8`
- `0x18003be38`
- `0x18003d780`
- `0x18004d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180023784`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180023784`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800226a4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800226a4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022490`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022680`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022f40`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022fc0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023bd0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023c50`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022490`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022680`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022f40`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022fc0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023bd0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023c50`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180022468`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x18002265b`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180022f1e`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180022f9e`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180023bb0`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180023c2e`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180022468`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x18002265b`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180022f1e`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180022f9e`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180023bb0`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180023c2e`

## pseudocode

```c
// Hidden C++ exception states: #wind=24
__int64 __fastcall VaultCreateCredentialFromSettingUnit(struct _SETTING_UNIT *a1, const struct _GUID *a2)
{
  CVaultPackageId *v4; // r15
  unsigned int UserVaultManager; // eax
  unsigned int v6; // edi
  HLOCAL v7; // rsi
  __int64 v8; // rcx
  _BYTE *v9; // rax
  SIZE_T v10; // rax
  _BYTE *v11; // rdx
  const struct _GUID *v12; // rdx
  _BYTE *v13; // rbx
  unsigned int Vault; // eax
  struct CUserVault *v15; // rsi
  unsigned int VaultStore; // eax
  struct IVaultStore *v17; // r13
  __int64 v18; // rcx
  _BYTE *v19; // rax
  SIZE_T v20; // rax
  _BYTE *v21; // rdx
  _QWORD *v22; // rax
  HLOCAL v23; // r12
  PVOID *v24; // rcx
  __int64 v25; // r9
  PVOID *v26; // rcx
  __int64 v27; // rax
  __int64 v28; // rdx
  __int64 v29; // r9
  unsigned int v30; // eax
  __int64 v31; // r9
  __int64 v32; // rdi
  unsigned int v33; // ebx
  const struct _GUID *v35; // rax
  unsigned int Schema; // r14d
  __int64 v37; // rax
  unsigned int v38; // eax
  HLOCAL v39; // rdi
  __int64 (__fastcall *v40)(HLOCAL, __int64); // rbx
  __int64 v41; // rax
  unsigned int v42; // eax
  HLOCAL v43; // rdi
  void (__fastcall *v44)(HLOCAL, _QWORD); // rbx
  _QWORD *v45; // rax
  HLOCAL v46; // rdi
  int v47; // eax
  unsigned int v48; // eax
  __int64 v49; // rdi
  HLOCAL v50; // rbx
  int v51; // eax
  unsigned int v52; // eax
  _BYTE *v53; // rbx
  __int64 v54; // rax
  SIZE_T v55; // rax
  _BYTE *v56; // rcx
  _BYTE *v57; // rbx
  __int64 v58; // rax
  SIZE_T v59; // rax
  _BYTE *v60; // rcx
  HLOCAL v61; // rdi
  int v62; // ebx
  int v63; // eax
  unsigned int v64; // eax
  unsigned int i; // edi
  unsigned int *v66; // rbx
  int v67; // eax
  unsigned int v68; // eax
  unsigned int v69; // r14d
  _BYTE *v70; // rcx
  __int64 v71; // rax
  HLOCAL v72; // rdi
  void (__fastcall *v73)(HLOCAL, _QWORD); // rbx
  unsigned int v74; // eax
  unsigned int v75; // eax
  _BYTE *v76; // rdi
  unsigned int v77; // eax
  __int64 v78; // rcx
  _BYTE *v79; // rax
  _BYTE *v80; // rcx
  __int64 v81; // rax
  unsigned int v82; // eax
  unsigned int v83; // eax
  __int64 v84; // rax
  __int64 v85; // rbx
  CVaultPackageId *v86; // rax
  __int64 v87; // r14
  __int64 v88; // rsi
  __int64 v89; // rdi
  __int64 v90; // rbx
  _OWORD *v91; // rax
  unsigned int v92; // eax
  __int64 v93; // rax
  unsigned int v94; // eax
  unsigned int v95; // eax
  __int64 v96; // rdx
  HLOCAL v97; // rcx
  _BYTE *v98; // rax
  _BYTE *v99; // rcx
  __int64 v100; // rax
  _BYTE *v101; // rbx
  __int64 v102; // rax
  SIZE_T v103; // rax
  _BYTE *v104; // rcx
  _BYTE *v105; // rbx
  __int64 v106; // rax
  SIZE_T v107; // rax
  _BYTE *v108; // rcx
  int v109; // [rsp+20h] [rbp-E0h]
  void (*v110)(void); // [rsp+40h] [rbp-C0h] BYREF
  HLOCAL v111; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v112; // [rsp+50h] [rbp-B0h]
  void (__fastcall *v113)(_BYTE *); // [rsp+58h] [rbp-A8h] BYREF
  HLOCAL v114; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v115; // [rsp+68h] [rbp-98h]
  void (__fastcall *v116)(HLOCAL, __int64); // [rsp+70h] [rbp-90h] BYREF
  HLOCAL v117; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v118; // [rsp+80h] [rbp-80h]
  __int64 (__fastcall *v119)(_QWORD); // [rsp+88h] [rbp-78h] BYREF
  __int64 v120; // [rsp+90h] [rbp-70h]
  int v121; // [rsp+98h] [rbp-68h]
  struct IVaultStore *v122[2]; // [rsp+A0h] [rbp-60h] BYREF
  CVaultPackageId *v123; // [rsp+B0h] [rbp-50h]
  __int64 v124; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v125; // [rsp+C8h] [rbp-38h]
  int v126; // [rsp+D0h] [rbp-30h]
  int v127; // [rsp+D4h] [rbp-2Ch]
  int v128; // [rsp+D8h] [rbp-28h]
  __int128 v129; // [rsp+E0h] [rbp-20h] BYREF
  __int64 (__fastcall *v130)(_QWORD); // [rsp+F0h] [rbp-10h] BYREF
  struct CUserVault *v131; // [rsp+F8h] [rbp-8h]
  int v132; // [rsp+100h] [rbp+0h]
  unsigned int v133; // [rsp+108h] [rbp+8h] BYREF
  unsigned int v134; // [rsp+10Ch] [rbp+Ch] BYREF
  void (__fastcall *v135)(HLOCAL); // [rsp+110h] [rbp+10h] BYREF
  HLOCAL v136; // [rsp+118h] [rbp+18h]
  int v137; // [rsp+120h] [rbp+20h]
  __int64 (__fastcall *v138)(_QWORD); // [rsp+128h] [rbp+28h] BYREF
  struct IVaultStore *v139; // [rsp+130h] [rbp+30h]
  int v140; // [rsp+138h] [rbp+38h]
  _QWORD v141[2]; // [rsp+140h] [rbp+40h] BYREF
  int v142; // [rsp+150h] [rbp+50h]
  __int64 v143; // [rsp+158h] [rbp+58h] BYREF
  void (__fastcall *v144)(HLOCAL); // [rsp+160h] [rbp+60h] BYREF
  HLOCAL hMem; // [rsp+168h] [rbp+68h] BYREF
  unsigned int v146; // [rsp+170h] [rbp+70h]
  __int64 v147; // [rsp+178h] [rbp+78h] BYREF
  char v148[8]; // [rsp+180h] [rbp+80h] BYREF
  __int64 (__fastcall *v149)(_QWORD); // [rsp+188h] [rbp+88h] BYREF
  CUserVault *v150; // [rsp+190h] [rbp+90h] BYREF
  int v151; // [rsp+198h] [rbp+98h]
  _BYTE v152[96]; // [rsp+1C0h] [rbp+C0h] BYREF

  v113 = (void (__fastcall *)(_BYTE *))AutoDereference<IVaultKeyManager>;
  v4 = 0;
  v114 = 0;
  v115 = 0;
  v110 = (void (*)(void))AutoDereference<IVaultKeyManager>;
  v111 = 0;
  v112 = 0;
  v117 = 0;
  v118 = 0;
  v116 = 0;
  v147 = 0;
  v133 = 0;
  v134 = 0;
  v129 = 0;
  std::_Tree<std::_Tmap_traits<_GUID,CUserVault *,GuidCmp,std::allocator<std::pair<_GUID const,CUserVault *>>,0>>::_Alloc_sentinel_and_proxy(&v129);
  v124 = 0;
  v125 = 0;
  v126 = 0;
  v127 = 1;
  v128 = 1;
  v143 = 0;
  v130 = AutoDereference<IVaultKeyManager>;
  v131 = 0;
  v132 = 0;
  v138 = AutoDereference<IVaultKeyManager>;
  v139 = 0;
  v140 = 0;
  v141[1] = 0;
  v142 = 0;
  v141[0] = 0;
  v120 = 0;
  v121 = 0;
  v119 = AutoDereference<IVaultKeyManager>;
  v135 = CVaultRoamingCredential::FreeRoamingCredential;
  v136 = 0;
  v137 = 0;
  v144 = (void (__fastcall *)(HLOCAL))AutoDereference<IVaultKeyManager>;
  hMem = 0;
  v146 = 0;
  v149 = AutoDereference<IVaultKeyManager>;
  v150 = 0;
  v151 = 0;
  v122[0] = (struct IVaultStore *)AutoDereference<IVaultKeyManager>;
  v122[1] = 0;
  LODWORD(v123) = 0;
  UserVaultManager = CVaultMgr::GetUserVaultManager(
                       (CVaultMgr *)AutoDereference<IVaultKeyManager>,
                       1u,
                       (struct CUserVaultMgr **)&hMem,
                       0,
                       0);
  v6 = UserVaultManager;
  if ( UserVaultManager )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        123,
        WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids,
        UserVaultManager);
    v7 = hMem;
    if ( hMem )
    {
      if ( v146 )
      {
        v8 = v146;
        v9 = hMem;
        do
        {
          *v9++ = 0;
          --v8;
        }
        while ( v8 );
      }
      if ( v144 )
      {
        v144(v7);
      }
      else if ( v7 )
      {
        v10 = LocalSize(v7);
        if ( v10 )
        {
          v11 = v7;
          do
          {
            *v11++ = 0;
            --v10;
          }
          while ( v10 );
        }
        LocalFree(v7);
      }
    }
    goto LABEL_27;
  }
  v12 = a2;
  v13 = hMem;
  Vault = CUserVaultMgr::GetVault((CUserVaultMgr *)hMem, v12, &v150);
  v6 = Vault;
  if ( Vault )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 124, WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids, Vault);
LABEL_26:
    CVaultAutoPtr<CUserVault *,void,CUserVault *,0>::Delete(v122);
    CVaultAutoPtr<CUserVault *,void,CUserVault *,0>::Delete(&v149);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v144);
LABEL_27:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 141, WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids, v6);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v135);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v119);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(v141);
    CVaultAutoPtr<CUserVault *,void,CUserVault *,0>::Delete(&v138);
    CVaultAutoPtr<CUserVault *,void,CUserVault *,0>::Delete(&v130);
    CVaultCredDataMap::~CVaultCredDataMap((CVaultCredDataMap *)&v124);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v116);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v110);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v113);
    return v6;
  }
  v15 = v150;
  VaultStore = CUserVault::GetVaultStore(v150, &v122[1], 0);
  v6 = VaultStore;
  if ( VaultStore )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 125, WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids, VaultStore);
    goto LABEL_26;
  }
  v17 = v122[1];
  v139 = v122[1];
  v131 = v15;
  if ( v13 )
  {
    if ( v146 )
    {
      v18 = v146;
      v19 = v13;
      do
      {
        *v19++ = 0;
        --v18;
      }
      while ( v18 );
    }
    if ( v144 )
    {
      v144(v13);
    }
    else
    {
      v20 = LocalSize(v13);
      if ( v20 )
      {
        v21 = v13;
        do
        {
          *v21++ = 0;
          --v20;
        }
        while ( v20 );
      }
      LocalFree(v13);
    }
  }
  v122[0] = (struct IVaultStore *)CVaultRoamingCredential::FreeRoamingCredential;
  v122[1] = 0;
  LODWORD(v123) = 0;
  v22 = LocalAlloc(0x40u, 0xC8u);
  v23 = v22;
  if ( !v22 )
  {
    v6 = 14;
    v24 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_b8c320665cdb3030ba0f4297ba888b62_Traceguids, 14);
      v24 = (PVOID *)WPP_GLOBAL_Control;
    }
    goto LABEL_252;
  }
  *v22 = &CVaultRoamingCredential::`vftable';
  *(_QWORD *)((char *)v22 + 12) = 0;
  v22[3] = 0;
  v22[7] = 0;
  v22[9] = 0;
  *((_DWORD *)v22 + 20) = 0;
  v22[8] = CVaultCredElement::FreeCredElement;
  v22[12] = 0;
  *((_DWORD *)v22 + 26) = 0;
  v22[11] = CVaultCredElement::FreeCredElement;
  v22[15] = 0;
  *((_DWORD *)v22 + 32) = 0;
  v22[14] = CVaultCredElement::FreeCredElement;
  *((_DWORD *)v22 + 34) = 0;
  v22[18] = 0;
  v22[19] = 0;
  v22[20] = 0;
  v22[22] = 0;
  *((_DWORD *)v22 + 46) = 0;
  v22[21] = 0;
  v22[24] = 0;
  *((_OWORD *)v22 + 2) = 0;
  v22[6] = 0;
  LODWORD(v123) = 0;
  v122[1] = (struct IVaultStore *)v22;
  v25 = *((unsigned int *)a1 + 2);
  if ( (_DWORD)v25 )
  {
    v6 = 87;
    v26 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_b8c320665cdb3030ba0f4297ba888b62_Traceguids, v25, 87);
LABEL_247:
        v26 = (PVOID *)WPP_GLOBAL_Control;
      }
LABEL_248:
      if ( v26 != &WPP_GLOBAL_Control && (*((_BYTE *)v26 + 28) & 2) != 0 )
        WPP_SF_d(v26[2], 13, WPP_b8c320665cdb3030ba0f4297ba888b62_Traceguids, v6);
    }
LABEL_251:
    CVaultRoamingCredential::FreeRoamingCredential(v23);
    v24 = (PVOID *)WPP_GLOBAL_Control;
LABEL_252:
    if ( v24 != &WPP_GLOBAL_Control && (*((_BYTE *)v24 + 28) & 2) != 0 )
      WPP_SF_d(v24[2], 142, WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids, v6);
    if ( v17 )
      AutoDereference<IVaultKeyManager>(v17);
    if ( v15 )
      AutoDereference<IVaultKeyManager>(v15);
    CVaultCredDataMap::~CVaultCredDataMap((CVaultCredDataMap *)&v124);
    v101 = v111;
    if ( v111 )
    {
      v102 = v112;
      if ( v112 )
      {
        do
        {
          *v101++ = 0;
          --v102;
        }
        while ( v102 );
        v101 = v111;
      }
      if ( v110 )
      {
        ((void (__fastcall *)(_BYTE *))v110)(v101);
      }
      else if ( v101 )
      {
        v103 = LocalSize(v101);
        if ( v103 )
        {
          v104 = v101;
          do
          {
            *v104++ = 0;
            --v103;
          }
          while ( v103 );
        }
        LocalFree(v101);
      }
      v111 = 0;
    }
    v112 = 0;
    v105 = v114;
    if ( v114 )
    {
      v106 = v115;
      if ( v115 )
      {
        do
        {
          *v105++ = 0;
          --v106;
        }
        while ( v106 );
        v105 = v114;
      }
      if ( v113 )
      {
        v113(v105);
      }
      else if ( v105 )
      {
        v107 = LocalSize(v105);
        if ( v107 )
        {
          v108 = v105;
          do
          {
            *v108++ = 0;
            --v107;
          }
          while ( v107 );
        }
        LocalFree(v105);
      }
    }
    return v6;
  }
  if ( !*(_QWORD *)a1 )
    goto LABEL_242;
  v27 = -1;
  do
    ++v27;
  while ( *(_WORD *)(*(_QWORD *)a1 + 2 * v27) );
  if ( v27 != 40 )
  {
LABEL_242:
    v6 = 87;
    v26 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_251;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_248;
    v28 = 26;
LABEL_245:
    v31 = 87;
    goto LABEL_246;
  }
  if ( !*((_BYTE *)a1 + 40) )
  {
    v6 = 87;
    v26 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_251;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_248;
    v28 = 27;
    goto LABEL_245;
  }
  v29 = *((unsigned int *)a1 + 6);
  if ( !(_DWORD)v29 || !*((_QWORD *)a1 + 4) )
  {
    v6 = 87;
    v26 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_251;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_248;
    v28 = 28;
    goto LABEL_245;
  }
  if ( dword_18005F634 && (unsigned int)v29 > dword_18005F634 )
  {
    v26 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_b8c320665cdb3030ba0f4297ba888b62_Traceguids, v29);
      v26 = (PVOID *)WPP_GLOBAL_Control;
    }
    v6 = 223;
    goto LABEL_248;
  }
  *((_DWORD *)v23 + 4) = 0;
  *((_QWORD *)v23 + 3) = *(_QWORD *)a1;
  *((_QWORD *)v23 + 6) = *(_QWORD *)((char *)a1 + 12);
  v30 = CVaultRoamingCredential::DeserializeRoamingCredential(
          (CVaultRoamingCredential *)v23,
          v15,
          *((unsigned __int8 **)a1 + 4),
          *((_DWORD *)a1 + 6));
  v6 = v30;
  if ( v30 )
  {
    v26 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_251;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_248;
    v28 = 24;
    v31 = v30;
LABEL_246:
    WPP_SF_d(v26[2], v28, WPP_b8c320665cdb3030ba0f4297ba888b62_Traceguids, v31);
    goto LABEL_247;
  }
  *((_DWORD *)v23 + 2) = 1;
  *((_DWORD *)v23 + 3) = 1;
  v136 = v23;
  v32 = (*(unsigned int (__fastcall **)(HLOCAL))(*(_QWORD *)v23 + 8LL))(v23);
  v124 = v32;
  v125 = 0;
  v126 = 0;
  v127 = 1;
  v128 = 1;
  v33 = dword_18005F628;
  if ( dword_18005F628
    && (*(unsigned int (__fastcall **)(struct IVaultStore *, _QWORD))(*(_QWORD *)v17 + 136LL))(v17, 0) + 1 > v33 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        143,
        WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids,
        (unsigned int)dword_18005F628);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v135);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v119);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(v141);
    CVaultAutoPtr<CUserVault *,void,CUserVault *,0>::Delete(&v138);
    CVaultAutoPtr<CUserVault *,void,CUserVault *,0>::Delete(&v130);
    CVaultCredDataMap::~CVaultCredDataMap((CVaultCredDataMap *)&v124);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v116);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v110);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v113);
    return 1381;
  }
  (*(void (__fastcall **)(struct IVaultStore *, __int64 *))(*(_QWORD *)v17 + 72LL))(v17, &v143);
  v35 = (const struct _GUID *)(*(__int64 (__fastcall **)(HLOCAL))(*(_QWORD *)v23 + 48LL))(v23);
  Schema = VaultGetSchema(v15, v35, (struct IVaultSchema **)&v111, 1u);
  if ( Schema )
  {
    if ( (*(__int64 (__fastcall **)(HLOCAL))(*(_QWORD *)v23 + 48LL))(v23) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        v37 = (*(__int64 (__fastcall **)(HLOCAL))(*(_QWORD *)v23 + 48LL))(v23);
        WPP_SF__guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 144, WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids, v37);
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 145, WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids);
    }
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v135);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v119);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(v141);
    CVaultAutoPtr<CUserVault *,void,CUserVault *,0>::Delete(&v138);
    CVaultAutoPtr<CUserVault *,void,CUserVault *,0>::Delete(&v130);
    CVaultCredDataMap::~CVaultCredDataMap((CVaultCredDataMap *)&v124);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v116);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v110);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v113);
    return Schema;
  }
  v38 = (*(__int64 (__fastcall **)(__int64, HLOCAL, _QWORD, __int64, HLOCAL *))(*(_QWORD *)v143 + 16LL))(
          v143,
          v111,
          (unsigned int)v32,
          2,
          &v114);
  v6 = v38;
  if ( v38 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 146, WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids, v38);
LABEL_238:
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v135);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v119);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(v141);
    CVaultAutoPtr<CUserVault *,void,CUserVault *,0>::Delete(&v138);
    CVaultAutoPtr<CUserVault *,void,CUserVault *,0>::Delete(&v130);
    CVaultCredDataMap::~CVaultCredDataMap((CVaultCredDataMap *)&v124);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v116);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v110);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v113);
    return v6;
  }
  v39 = v114;
  v40 = *(__int64 (__fastcall **)(HLOCAL, __int64))(*(_QWORD *)v114 + 32LL);
  v41 = (*(__int64 (__fastcall **)(HLOCAL))(*(_QWORD *)v23 + 56LL))(v23);
  v42 = v40(v39, v41);
  v6 = v42;
  if ( v42 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 147, WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids, v42);
    goto LABEL_238;
  }
  v43 = v114;
  v44 = *(void (__fastcall **)(HLOCAL, _QWORD))(*(_QWORD *)v114 + 200LL);
  v45 = (_QWORD *)(*(__int64 (__fastcall **)(HLOCAL, char *))(*(_QWORD *)v23 + 80LL))(v23, v148);
  v44(v43, *v45);
  v46 = v114;
  LODWORD(v44) = (*(__int64 (__fastcall **)(HLOCAL))(*(_QWORD *)v111 + 120LL))(v111);
  v47 = (*(__int64 (__fastcall **)(HLOCAL))(*(_QWORD *)v23 + 24LL))(v23);
  v48 = SetCredentialElement(
          (_DWORD)v15,
          v47,
          (_DWORD)v44,
          (unsigned int) IVaultCredential::`vcall'{40,{flat}},
          (__int64)&v124,
          1,
          (__int64)v46);
  v6 = v48;
  if ( v48 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 148, WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids, v48);
    goto LABEL_238;
  }
  v49 = (*(__int64 (__fastcall **)(HLOCAL))(*(_QWORD *)v111 + 112LL))(v111);
  if ( v49 )
  {
    v50 = v114;
    v51 = (*(__int64 (__fastcall **)(HLOCAL))(*(_QWORD *)v23 + 16LL))(v23);
    v52 = SetCredentialElement(
            (_DWORD)v15,
            v51,
            v49,
            (unsigned int) IVaultCredential::`vcall'{48,{flat}},
            (__int64)&v124,
            1,
            (__int64)v50);
    v6 = v52;
    if ( v52 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 149, WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids, v52);
      CVaultRoamingCredential::FreeRoamingCredential(v23);
      if ( v17 )
        AutoDereference<IVaultKeyManager>(v17);
      if ( v15 )
        AutoDereference<IVaultKeyManager>(v15);
      CVaultCredDataMap::~CVaultCredDataMap((CVaultCredDataMap *)&v124);
      v53 = v111;
      if ( v111 )
      {
        v54 = v112;
        if ( v112 )
        {
          do
          {
            *v53++ = 0;
            --v54;
          }
          while ( v54 );
          v53 = v111;
        }
        if ( v110 )
        {
          ((void (__fastcall *)(_BYTE *))v110)(v53);
        }
        else if ( v53 )
        {
          v55 = LocalSize(v53);
          if ( v55 )
          {
            v56 = v53;
            do
            {
              *v56++ = 0;
              --v55;
            }
            while ( v55 );
          }
          LocalFree(v53);
        }
        v111 = 0;
      }
      v112 = 0;
      v57 = v114;
      if ( v114 )
      {
        v58 = v115;
        if ( v115 )
        {
          do
          {
            *v57++ = 0;
            --v58;
          }
          while ( v58 );
          v57 = v114;
        }
        if ( v113 )
        {
          v113(v57);
        }
        else if ( v57 )
        {
          v59 = LocalSize(v57);
          if ( v59 )
          {
            v60 = v57;
            do
            {
              *v60++ = 0;
              --v59;
            }
            while ( v59 );
          }
          LocalFree(v57);
        }
      }
      return v6;
    }
  }
  if ( (*(__int64 (__fastcall **)(HLOCAL))(*(_QWORD *)v23 + 32LL))(v23) )
  {
    v61 = v114;
    v62 = (*(__int64 (__fastcall **)(HLOCAL))(*(_QWORD *)v111 + 128LL))(v111);
    v63 = (*(__int64 (__fastcall **)(HLOCAL))(*(_QWORD *)v23 + 32LL))(v23);
    v64 = SetCredentialElement(
            (_DWORD)v15,
            v63,
            v62,
            (unsigned int) IVaultCredential::`vcall'{56,{flat}},
            (__int64)&v124,
            1,
            (__int64)v61);
    v6 = v64;
    if ( v64 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 150, WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids, v64);
      goto LABEL_238;
    }
  }
  for ( i = 0; i < (*(unsigned int (__fastcall **)(HLOCAL))(*(_QWORD *)v23 + 64LL))(v23); ++i )
  {
    v66 = (unsigned int *)(*(__int64 (__fastcall **)(HLOCAL, _QWORD))(*(_QWORD *)v23 + 72LL))(v23, i);
    v67 = (*(__int64 (__fastcall **)(HLOCAL, _QWORD))(*(_QWORD *)v111 + 144LL))(v111, *v66);
    v68 = SetCredentialElement(
            (_DWORD)v15,
            (_DWORD)v66,
            v67,
            (unsigned int) IVaultCredential::`vcall'{64,{flat}},
            (__int64)&v124,
            0,
            (__int64)v114);
    v69 = v68;
    if ( v68 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 151, WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids, i, v68);
      CVaultRoamingCredential::FreeRoamingCredential(v23);
      if ( v17 )
        AutoDereference<IVaultKeyManager>(v17);
      if ( v15 )
        AutoDereference<IVaultKeyManager>(v15);
      CVaultCredDataMap::~CVaultCredDataMap((CVaultCredDataMap *)&v124);
      v70 = v111;
      if ( v111 )
      {
        v71 = v112;
        if ( v112 )
        {
          do
          {
            *v70++ = 0;
            --v71;
          }
          while ( v71 );
          v70 = v111;
        }
        if ( v110 )
          v110();
        else
          VaultFreeInternal(v70);
        v111 = 0;
      }
LABEL_158:
      v112 = 0;
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v113);
      return v69;
    }
  }
  v72 = v114;
  v73 = *(void (__fastcall **)(HLOCAL, _QWORD))(*(_QWORD *)v114 + 168LL);
  v74 = (*(__int64 (__fastcall **)(HLOCAL))(*(_QWORD *)v23 + 40LL))(v23);
  v73(v72, v74);
  v75 = CVaultCredDataMap::SerializeData((CVaultCredDataMap *)&v124, (unsigned __int8 **)&v117, &v133);
  v6 = v75;
  if ( v75 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 152, WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids, v75);
    goto LABEL_238;
  }
  LOBYTE(v109) = 1;
  v76 = v117;
  v77 = CUserVault::EncryptData(v15, 1, v117, v133, v109, &v147, &v134);
  v69 = v77;
  if ( v77 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 153, WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids, v77);
    CVaultRoamingCredential::FreeRoamingCredential(v23);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v119);
    if ( v17 )
      AutoDereference<IVaultKeyManager>(v17);
    if ( v15 )
      AutoDereference<IVaultKeyManager>(v15);
    CVaultCredDataMap::~CVaultCredDataMap((CVaultCredDataMap *)&v124);
    if ( v76 )
    {
      if ( v118 )
      {
        v78 = v118;
        v79 = v76;
        do
        {
          *v79++ = 0;
          --v78;
        }
        while ( v78 );
      }
      if ( v116 )
        ((void (__fastcall *)(_BYTE *))v116)(v76);
      else
        VaultFreeInternal(v76);
    }
    v80 = v111;
    if ( v111 )
    {
      v81 = v112;
      if ( v112 )
      {
        do
        {
          *v80++ = 0;
          --v81;
        }
        while ( v81 );
        v80 = v111;
      }
      if ( v110 )
        v110();
      else
        VaultFreeInternal(v80);
      v111 = 0;
    }
    goto LABEL_158;
  }
  v82 = (*(__int64 (__fastcall **)(HLOCAL, __int64, _QWORD))(*(_QWORD *)v114 + 80LL))(v114, v147, v134);
  v6 = v82;
  if ( v82 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 154, WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids, v82);
    goto LABEL_238;
  }
  v83 = (*(__int64 (__fastcall **)(HLOCAL, HLOCAL))(*(_QWORD *)v23 + 104LL))(v23, v114);
  v6 = v83;
  if ( v83 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 155, WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids, v83);
    goto LABEL_238;
  }
  v84 = (*(__int64 (__fastcall **)(HLOCAL))(*(_QWORD *)v114 + 208LL))(v114);
  v85 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v84 + 32LL))(v84);
  CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v119);
  v120 = v85;
  (**(void (__fastcall ***)(__int64))v85)(v85);
  v86 = CVaultPackageId::CVaultPackageId((CVaultPackageId *)&v149, *(void *const *)(v85 + 16));
  v122[0] = (struct IVaultStore *)8;
  HIDWORD(v122[1]) = 0;
  if ( *((_DWORD *)v86 + 10) )
    v4 = v86;
  LODWORD(v122[1]) = *((_DWORD *)v86 + 10);
  v87 = (*(__int64 (__fastcall **)(HLOCAL))(*(_QWORD *)v111 + 112LL))(v111);
  v88 = (*(__int64 (__fastcall **)(HLOCAL))(*(_QWORD *)v23 + 16LL))(v23);
  v89 = (*(__int64 (__fastcall **)(HLOCAL))(*(_QWORD *)v111 + 120LL))(v111);
  v90 = (*(__int64 (__fastcall **)(HLOCAL))(*(_QWORD *)v23 + 24LL))(v23);
  v91 = (_OWORD *)(*(__int64 (__fastcall **)(HLOCAL))(*(_QWORD *)v23 + 48LL))(v23);
  v123 = v4;
  v92 = ComputeItemDigest(v91, v90, v89, v88, v87, (__int64)v122, (__int64)v152);
  v6 = v92;
  if ( v92 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 156, WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids, v92);
    goto LABEL_238;
  }
  if ( (*(unsigned int (__fastcall **)(HLOCAL))(*(_QWORD *)v23 + 88LL))(v23) != 82
    || (v93 = (*(__int64 (__fastcall **)(HLOCAL))(*(_QWORD *)v23 + 96LL))(v23), (unsigned int)_o__wcsicmp(v93, v152)) )
  {
    v6 = 87;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 157, WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids, 87);
    goto LABEL_238;
  }
  v94 = (*(__int64 (__fastcall **)(HLOCAL, _BYTE *, __int64))(*(_QWORD *)v114 + 88LL))(v114, v152, 82);
  v6 = v94;
  if ( v94 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 158, WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids, v94);
    goto LABEL_238;
  }
  v95 = (*(__int64 (__fastcall **)(struct IVaultStore *, HLOCAL, _BYTE *, __int64))(*(_QWORD *)v17 + 104LL))(
          v17,
          v114,
          v152,
          1);
  v6 = v95;
  if ( v95 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 159, WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids, v95);
    goto LABEL_238;
  }
  CVaultRoamingCredential::FreeRoamingCredential(v23);
  CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v119);
  if ( v17 )
    AutoDereference<IVaultKeyManager>(v17);
  CVaultAutoPtr<CUserVault *,void,CUserVault *,0>::Delete(&v130);
  CVaultCredDataMap::~CVaultCredDataMap((CVaultCredDataMap *)&v124);
  v97 = v117;
  if ( v117 )
  {
    if ( v118 )
    {
      v96 = v118;
      v98 = v117;
      do
      {
        *v98++ = 0;
        --v96;
      }
      while ( v96 );
    }
    if ( v116 )
      v116(v97, v96);
    else
      VaultFreeInternal(v97);
  }
  v99 = v111;
  if ( v111 )
  {
    v100 = v112;
    if ( v112 )
    {
      do
      {
        *v99++ = 0;
        --v100;
      }
      while ( v100 );
      v99 = v111;
    }
    if ( v110 )
      v110();
    else
      VaultFreeInternal(v99);
    v111 = 0;
  }
  v112 = 0;
  CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v113);
  return 0;
}

```

## disassembly

```asm
0x180022290  mov     [rsp-8+arg_10], rbx
0x180022295  push    rbp
0x180022296  push    rsi
0x180022297  push    rdi
0x180022298  push    r12
0x18002229a  push    r13
0x18002229c  push    r14
0x18002229e  push    r15
0x1800222a0  lea     rbp, [rsp-130h]
0x1800222a8  sub     rsp, 230h
0x1800222af  mov     rax, cs:__security_cookie
0x1800222b6  xor     rax, rsp
0x1800222b9  mov     [rbp+160h+var_40], rax
0x1800222c0  mov     rbx, rdx
0x1800222c3  mov     r14, rcx
0x1800222c6  lea     rax, ??$AutoDereference@UIVaultKeyManager@@@@YAXPEAUIVaultKeyManager@@@Z; AutoDereference<IVaultKeyManager>(IVaultKeyManager *)
0x1800222cd  mov     [rsp+260h+var_208], rax
0x1800222d2  xor     r15d, r15d
0x1800222d5  mov     [rsp+260h+var_200], r15
0x1800222da  mov     [rsp+260h+var_1F8], r15d
0x1800222df  lea     rax, ??$AutoDereference@UIVaultKeyManager@@@@YAXPEAUIVaultKeyManager@@@Z; AutoDereference<IVaultKeyManager>(IVaultKeyManager *)
0x1800222e6  mov     [rsp+260h+var_220], rax
0x1800222eb  mov     [rsp+260h+var_218], r15
0x1800222f0  mov     [rsp+260h+var_210], r15d
0x1800222f5  mov     [rsp+260h+var_1E8], r15
0x1800222fa  mov     [rbp+160h+var_1E0], r15d
0x1800222fe  mov     [rsp+260h+var_1F0], r15
0x180022303  mov     [rbp+160h+var_E8], r15
0x180022307  mov     [rbp+160h+var_158], r15d
0x18002230b  mov     [rbp+160h+var_154], r15d
0x18002230f  xorps   xmm0, xmm0
0x180022312  movdqu  [rbp+160h+var_180], xmm0
0x180022317  lea     rcx, [rbp+160h+var_180]
0x18002231b  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tmap_traits@U_GUID@@PEAVCUserVault@@UGuidCmp@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVCUserVault@@@std@@@std@@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<_GUID,CUserVault *,GuidCmp,std::allocator<std::pair<_GUID const,CUserVault *>>,0>>::_Alloc_sentinel_and_proxy(void)
0x180022320  mov     [rbp+160h+var_1A0], r15
0x180022324  mov     [rbp+160h+var_198], r15
0x180022328  mov     [rbp+160h+var_190], r15d
0x18002232c  mov     [rbp+160h+var_18C], 1
0x180022333  mov     [rbp+160h+var_188], 1
0x18002233a  mov     [rbp+160h+var_108], r15
0x18002233e  lea     rdx, ??$AutoDereference@UIVaultKeyManager@@@@YAXPEAUIVaultKeyManager@@@Z; AutoDereference<IVaultKeyManager>(IVaultKeyManager *)
0x180022345  mov     [rbp+160h+var_170], rdx
0x180022349  mov     [rbp+160h+var_168], r15
0x18002234d  mov     [rbp+160h+var_160], r15d
0x180022351  lea     rcx, ??$AutoDereference@UIVaultKeyManager@@@@YAXPEAUIVaultKeyManager@@@Z; this
0x180022358  mov     [rbp+160h+var_138], rcx
0x18002235c  mov     [rbp+160h+var_130], r15
0x180022360  mov     [rbp+160h+var_128], r15d
0x180022364  mov     [rbp+160h+var_118], r15
0x180022368  mov     [rbp+160h+var_110], r15d
0x18002236c  mov     [rbp+160h+var_120], r15
0x180022370  mov     [rbp+160h+var_1D0], r15
0x180022374  mov     [rbp+160h+var_1C8], r15d
0x180022378  lea     rax, ??$AutoDereference@UIVaultKeyManager@@@@YAXPEAUIVaultKeyManager@@@Z; AutoDereference<IVaultKeyManager>(IVaultKeyManager *)
0x18002237f  mov     [rbp+160h+var_1D8], rax
0x180022383  lea     rax, ?FreeRoamingCredential@CVaultRoamingCredential@@SAXPEAV1@@Z; CVaultRoamingCredential::FreeRoamingCredential(CVaultRoamingCredential *)
0x18002238a  mov     [rbp+160h+var_150], rax
0x18002238e  mov     [rbp+160h+var_148], r15
0x180022392  mov     [rbp+160h+var_140], r15d
0x180022396  lea     rax, ??$AutoDereference@UIVaultKeyManager@@@@YAXPEAUIVaultKeyManager@@@Z; AutoDereference<IVaultKeyManager>(IVaultKeyManager *)
0x18002239d  mov     [rbp+160h+var_100], rax
0x1800223a1  mov     [rbp+160h+hMem], r15
0x1800223a5  mov     [rbp+160h+var_F0], r15d
0x1800223a9  mov     [rbp+160h+var_D8], rdx
0x1800223b0  mov     [rbp+160h+var_D0], r15
0x1800223b7  mov     [rbp+160h+var_C8], r15d
0x1800223be  mov     [rbp+160h+var_1C0], rcx
0x1800223c2  mov     [rbp+160h+var_1C0+8], r15
0x1800223c6  mov     dword ptr [rbp+160h+var_1B0], r15d
0x1800223ca  mov     [rsp+260h+var_240], r15; struct _LUID *
0x1800223cf  xor     r9d, r9d; unsigned __int8 *
0x1800223d2  lea     r8, [rbp+160h+hMem]; struct CUserVaultMgr **
0x1800223d6  mov     dl, 1; unsigned __int8
0x1800223d8  call    ?GetUserVaultManager@CVaultMgr@@QEAAKEPEAPEAVCUserVaultMgr@@QEAEPEAU_LUID@@PEAKPEAPEAX@Z; CVaultMgr::GetUserVaultManager(uchar,CUserVaultMgr * *,uchar * const,_LUID *,ulong *,void * *)
0x1800223dd  mov     edi, eax
0x1800223df  test    eax, eax
0x1800223e1  jz      loc_18002249C
0x1800223e7  lea     rbx, WPP_GLOBAL_Control
0x1800223ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800223f5  cmp     rcx, rbx
0x1800223f8  jz      short loc_180022419
0x1800223fa  test    byte ptr [rcx+1Ch], 2
0x1800223fe  jz      short loc_180022419
0x180022400  mov     edx, 7Bh ; '{'
0x180022405  mov     r9d, eax
0x180022408  lea     r8, WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids
0x18002240f  mov     rcx, [rcx+10h]
0x180022413  call    WPP_SF_d
0x180022418  nop
0x180022419  mov     rsi, [rbp+160h+hMem]
0x18002241d  test    rsi, rsi
0x180022420  jz      short loc_180022497
0x180022422  mov     eax, [rbp+160h+var_F0]
0x180022425  test    eax, eax
0x180022427  jz      short loc_18002244D
0x180022429  test    rsi, rsi
0x18002242c  jz      short loc_18002244D
0x18002242e  mov     ecx, eax
0x180022430  test    eax, eax
0x180022432  jz      short loc_18002244D
0x180022434  mov     rax, rsi
0x180022437  nop     word ptr [rax+rax+00000000h]
0x180022440  mov     byte ptr [rax], 0
0x180022443  lea     rax, [rax+1]
0x180022447  sub     rcx, 1
0x18002244b  jnz     short loc_180022440
0x18002244d  mov     rax, [rbp+160h+var_100]
0x180022451  test    rax, rax
0x180022454  jz      short loc_180022460
0x180022456  mov     rcx, rsi
0x180022459  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002245e  jmp     short loc_180022497
0x180022460  test    rsi, rsi
0x180022463  jz      short loc_180022497
0x180022465  mov     rcx, rsi; hMem
0x180022468  call    cs:__imp_LocalSize
0x18002246e  test    rax, rax
0x180022471  jz      short loc_18002248D
0x180022473  mov     rdx, rsi
0x180022476  nop     word ptr [rax+rax+00000000h]
0x180022480  mov     byte ptr [rdx], 0
0x180022483  lea     rdx, [rdx+1]
0x180022487  sub     rax, 1
0x18002248b  jnz     short loc_180022480
0x18002248d  mov     rcx, rsi; hMem
0x180022490  call    cs:__imp_LocalFree
0x180022496  nop
0x180022497  jmp     loc_180022580
0x18002249c  lea     r8, [rbp+160h+var_D0]; struct CUserVault **
0x1800224a3  mov     rdx, rbx; struct _GUID *
0x1800224a6  mov     rbx, [rbp+160h+hMem]
0x1800224aa  mov     rcx, rbx; this
0x1800224ad  call    ?GetVault@CUserVaultMgr@@QEAAKPEBU_GUID@@PEAPEAVCUserVault@@@Z; CUserVaultMgr::GetVault(_GUID const *,CUserVault * *)
0x1800224b2  mov     edi, eax
0x1800224b4  test    eax, eax
0x1800224b6  jz      short loc_18002250D
0x1800224b8  lea     rbx, WPP_GLOBAL_Control
0x1800224bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800224c6  cmp     rcx, rbx
0x1800224c9  jz      short loc_1800224EA
0x1800224cb  test    byte ptr [rcx+1Ch], 2
0x1800224cf  jz      short loc_1800224EA
0x1800224d1  mov     edx, 7Ch ; '|'
0x1800224d6  mov     r9d, eax
0x1800224d9  lea     r8, WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids
0x1800224e0  mov     rcx, [rcx+10h]
0x1800224e4  call    WPP_SF_d
0x1800224e9  nop
0x1800224ea  lea     rcx, [rbp+160h+var_1C0]
0x1800224ee  call    ?Delete@?$CVaultAutoPtr@PEAVCUserVault@@XPEAV1@$0A@@@QEAAXXZ; CVaultAutoPtr<CUserVault *,void,CUserVault *,0>::Delete(void)
0x1800224f3  nop
0x1800224f4  lea     rcx, [rbp+160h+var_D8]
0x1800224fb  call    ?Delete@?$CVaultAutoPtr@PEAVCUserVault@@XPEAV1@$0A@@@QEAAXXZ; CVaultAutoPtr<CUserVault *,void,CUserVault *,0>::Delete(void)
0x180022500  nop
0x180022501  lea     rcx, [rbp+160h+var_100]
0x180022505  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18002250a  nop
0x18002250b  jmp     short loc_180022580
0x18002250d  mov     rsi, [rbp+160h+var_D0]
0x180022514  xor     r8d, r8d; unsigned __int8
0x180022517  lea     rdx, [rbp+160h+var_1C0+8]; struct IVaultStore **
0x18002251b  mov     rcx, rsi; this
0x18002251e  call    ?GetVaultStore@CUserVault@@QEAAKPEAPEAUIVaultStore@@E@Z; CUserVault::GetVaultStore(IVaultStore * *,uchar)
0x180022523  mov     edi, eax
0x180022525  test    eax, eax
0x180022527  jz      loc_18002260D
0x18002252d  lea     rbx, WPP_GLOBAL_Control
0x180022534  mov     rcx, cs:WPP_GLOBAL_Control
0x18002253b  cmp     rcx, rbx
0x18002253e  jz      short loc_18002255F
0x180022540  test    byte ptr [rcx+1Ch], 8
0x180022544  jz      short loc_18002255F
0x180022546  mov     edx, 7Dh ; '}'
0x18002254b  mov     r9d, eax
0x18002254e  lea     r8, WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids
0x180022555  mov     rcx, [rcx+10h]
0x180022559  call    WPP_SF_d
0x18002255e  nop
0x18002255f  lea     rcx, [rbp+160h+var_1C0]
0x180022563  call    ?Delete@?$CVaultAutoPtr@PEAVCUserVault@@XPEAV1@$0A@@@QEAAXXZ; CVaultAutoPtr<CUserVault *,void,CUserVault *,0>::Delete(void)
0x180022568  nop
0x180022569  lea     rcx, [rbp+160h+var_D8]
0x180022570  call    ?Delete@?$CVaultAutoPtr@PEAVCUserVault@@XPEAV1@$0A@@@QEAAXXZ; CVaultAutoPtr<CUserVault *,void,CUserVault *,0>::Delete(void)
0x180022575  nop
0x180022576  lea     rcx, [rbp+160h+var_100]
0x18002257a  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18002257f  nop
0x180022580  mov     rcx, cs:WPP_GLOBAL_Control
0x180022587  cmp     rcx, rbx
0x18002258a  jz      short loc_1800225AB
0x18002258c  test    byte ptr [rcx+1Ch], 2
0x180022590  jz      short loc_1800225AB
0x180022592  mov     edx, 8Dh
0x180022597  mov     r9d, edi
0x18002259a  lea     r8, WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids
0x1800225a1  mov     rcx, [rcx+10h]
0x1800225a5  call    WPP_SF_d
0x1800225aa  nop
0x1800225ab  lea     rcx, [rbp+160h+var_150]
0x1800225af  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800225b4  nop
0x1800225b5  lea     rcx, [rbp+160h+var_1D8]
0x1800225b9  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800225be  nop
0x1800225bf  lea     rcx, [rbp+160h+var_120]
0x1800225c3  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800225c8  nop
0x1800225c9  lea     rcx, [rbp+160h+var_138]
0x1800225cd  call    ?Delete@?$CVaultAutoPtr@PEAVCUserVault@@XPEAV1@$0A@@@QEAAXXZ; CVaultAutoPtr<CUserVault *,void,CUserVault *,0>::Delete(void)
0x1800225d2  nop
0x1800225d3  lea     rcx, [rbp+160h+var_170]
0x1800225d7  call    ?Delete@?$CVaultAutoPtr@PEAVCUserVault@@XPEAV1@$0A@@@QEAAXXZ; CVaultAutoPtr<CUserVault *,void,CUserVault *,0>::Delete(void)
0x1800225dc  nop
0x1800225dd  lea     rcx, [rbp+160h+var_1A0]; this
0x1800225e1  call    ??1CVaultCredDataMap@@QEAA@XZ; CVaultCredDataMap::~CVaultCredDataMap(void)
0x1800225e6  nop
0x1800225e7  lea     rcx, [rsp+260h+var_1F0]
0x1800225ec  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800225f1  nop
0x1800225f2  lea     rcx, [rsp+260h+var_220]
0x1800225f7  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800225fc  nop
0x1800225fd  lea     rcx, [rsp+260h+var_208]
0x180022602  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180022607  nop
0x180022608  jmp     loc_180023C57
0x18002260d  mov     r13, [rbp+160h+var_1C0+8]
0x180022611  mov     [rbp+160h+var_130], r13
0x180022615  mov     [rbp+160h+var_168], rsi
0x180022619  test    rbx, rbx
0x18002261c  jz      short loc_180022687
0x18002261e  mov     eax, [rbp+160h+var_F0]
0x180022621  test    eax, eax
0x180022623  jz      short loc_180022640
0x180022625  test    rbx, rbx
0x180022628  jz      short loc_180022640
0x18002262a  mov     ecx, eax
0x18002262c  test    eax, eax
0x18002262e  jz      short loc_180022640
0x180022630  mov     rax, rbx
0x180022633  mov     byte ptr [rax], 0
0x180022636  lea     rax, [rax+1]
0x18002263a  sub     rcx, 1
0x18002263e  jnz     short loc_180022633
0x180022640  mov     rax, [rbp+160h+var_100]
0x180022644  test    rax, rax
0x180022647  jz      short loc_180022653
0x180022649  mov     rcx, rbx
0x18002264c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022651  jmp     short loc_180022687
0x180022653  test    rbx, rbx
0x180022656  jz      short loc_180022687
0x180022658  mov     rcx, rbx; hMem
0x18002265b  call    cs:__imp_LocalSize
0x180022661  test    rax, rax
0x180022664  jz      short loc_18002267D
0x180022666  mov     rdx, rbx
0x180022669  nop     dword ptr [rax+00000000h]
0x180022670  mov     byte ptr [rdx], 0
0x180022673  lea     rdx, [rdx+1]
0x180022677  sub     rax, 1
0x18002267b  jnz     short loc_180022670
0x18002267d  mov     rcx, rbx; hMem
0x180022680  call    cs:__imp_LocalFree
0x180022686  nop
0x180022687  lea     rax, ?FreeRoamingCredential@CVaultRoamingCredential@@SAXPEAV1@@Z; CVaultRoamingCredential::FreeRoamingCredential(CVaultRoamingCredential *)
0x18002268e  mov     [rbp+160h+var_1C0], rax
0x180022692  mov     [rbp+160h+var_1C0+8], r15
0x180022696  mov     dword ptr [rbp+160h+var_1B0], r15d
0x18002269a  mov     edx, 0C8h; uBytes
0x18002269f  mov     ecx, 40h ; '@'; uFlags
0x1800226a4  call    cs:__imp_LocalAlloc
0x1800226aa  mov     r12, rax
0x1800226ad  test    rax, rax
0x1800226b0  jnz     short loc_1800226F4
0x1800226b2  lea     rbx, WPP_GLOBAL_Control
0x1800226b9  mov     edi, 0Eh
0x1800226be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800226c5  cmp     rcx, rbx
0x1800226c8  jz      short loc_1800226EF
0x1800226ca  test    byte ptr [rcx+1Ch], 2
0x1800226ce  jz      short loc_1800226EF
0x1800226d0  mov     edx, 0Ch
0x1800226d5  mov     r9d, edi
0x1800226d8  lea     r8, WPP_b8c320665cdb3030ba0f4297ba888b62_Traceguids
0x1800226df  mov     rcx, [rcx+10h]
0x1800226e3  call    WPP_SF_d
0x1800226e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800226ef  jmp     loc_180023B1C
0x1800226f4  lea     rax, ??_7CVaultRoamingCredential@@6B@; const CVaultRoamingCredential::`vftable'
0x1800226fb  mov     [r12], rax
0x1800226ff  mov     [r12+0Ch], r15
0x180022704  mov     [r12+18h], r15
0x180022709  mov     [r12+38h], r15
0x18002270e  mov     [r12+48h], r15
0x180022713  mov     [r12+50h], r15d
0x180022718  lea     rax, ?FreeCredElement@CVaultCredElement@@SAXPEAV1@@Z; CVaultCredElement::FreeCredElement(CVaultCredElement *)
0x18002271f  mov     [r12+40h], rax
0x180022724  mov     [r12+60h], r15
0x180022729  mov     [r12+68h], r15d
  ... truncated ...
```
