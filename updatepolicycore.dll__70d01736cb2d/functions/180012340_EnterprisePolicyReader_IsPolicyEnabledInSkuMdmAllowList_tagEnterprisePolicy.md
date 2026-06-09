# EnterprisePolicyReader::IsPolicyEnabledInSkuMdmAllowList(tagEnterprisePolicy)

- ea: `0x180012340`
- end: `0x1800149aa`
- name: `?IsPolicyEnabledInSkuMdmAllowList@EnterprisePolicyReader@@SAHW4tagEnterprisePolicy@@@Z`
- size: `9834`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180016f90`

## callees

- `0x18000e7e4`
- `0x18000fcc4`
- `0x180010260`
- `0x180012340`
- `0x1800149b0`
- `0x1800149f4`
- `0x180014e6c`
- `0x180014ee4`
- `0x180016e74`
- `0x1800258e0`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800123ae`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800123ae`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180012386`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180012386`

## pseudocode

```c
__int64 __fastcall EnterprisePolicyReader::IsPolicyEnabledInSkuMdmAllowList(int a1)
{
  unsigned __int8 v2; // bl
  unsigned __int64 v3; // rdi
  unsigned __int64 v4; // r8
  __int64 v5; // rcx
  unsigned __int64 v6; // r8
  __int64 v7; // rcx
  unsigned __int64 v8; // r8
  __int64 v9; // rcx
  unsigned __int64 v10; // r8
  __int64 v11; // rcx
  unsigned __int64 v12; // r8
  __int64 v13; // rcx
  unsigned __int64 v14; // r8
  __int64 v15; // rcx
  unsigned __int64 v16; // r8
  __int64 v17; // rcx
  unsigned __int64 v18; // r8
  __int64 v19; // rcx
  unsigned __int64 v20; // r8
  __int64 v21; // rcx
  unsigned __int64 v22; // r8
  __int64 v23; // rcx
  unsigned __int64 v24; // r8
  __int64 v25; // rcx
  unsigned __int64 v26; // r8
  __int64 v27; // rcx
  unsigned __int64 v28; // r8
  __int64 v29; // rcx
  unsigned __int64 v30; // r8
  __int64 v31; // rcx
  unsigned __int64 v32; // r8
  __int64 v33; // rcx
  unsigned __int64 v34; // r8
  __int64 v35; // rcx
  unsigned __int64 v36; // r8
  __int64 v37; // rcx
  unsigned __int64 v38; // r8
  __int64 v39; // rcx
  unsigned __int64 v40; // r8
  __int64 v41; // rcx
  unsigned __int64 v42; // r8
  __int64 v43; // rcx
  unsigned __int64 v44; // r8
  __int64 v45; // rcx
  unsigned __int64 v46; // r8
  __int64 v47; // rcx
  unsigned __int64 v48; // r8
  __int64 v49; // rcx
  unsigned __int64 v50; // r8
  __int64 v51; // rcx
  unsigned __int64 v52; // r8
  __int64 v53; // rcx
  unsigned __int64 v54; // r8
  __int64 v55; // rcx
  unsigned __int64 v56; // r8
  __int64 v57; // rcx
  unsigned __int64 v58; // r8
  __int64 v59; // rcx
  unsigned __int64 v60; // r8
  __int64 v61; // rcx
  unsigned __int64 v62; // r8
  __int64 v63; // rcx
  unsigned __int64 v64; // r8
  __int64 v65; // rcx
  unsigned __int64 v66; // r8
  __int64 v67; // rcx
  unsigned __int64 v68; // r8
  __int64 v69; // rcx
  unsigned __int64 v70; // r8
  __int64 v71; // rcx
  unsigned __int64 v72; // r8
  __int64 v73; // rcx
  unsigned __int64 v74; // r8
  __int64 v75; // rcx
  unsigned __int64 v76; // r8
  __int64 v77; // rcx
  unsigned __int64 v78; // r8
  __int64 v79; // rcx
  unsigned __int64 v80; // r8
  __int64 v81; // rcx
  unsigned __int64 v82; // r8
  __int64 v83; // rcx
  unsigned __int64 v84; // r8
  __int64 v85; // rcx
  unsigned __int64 v86; // r8
  __int64 v87; // rcx
  unsigned __int64 v88; // r8
  __int64 v89; // rcx
  unsigned __int64 v90; // r8
  __int64 v91; // rcx
  unsigned __int64 v92; // r8
  __int64 v93; // rcx
  unsigned __int64 v94; // r8
  __int64 v95; // rcx
  unsigned __int64 v96; // r8
  __int64 v97; // rcx
  unsigned __int64 v98; // r8
  __int64 v99; // rcx
  unsigned __int64 v100; // r8
  __int64 v101; // rcx
  unsigned __int64 v102; // r8
  __int64 v103; // rcx
  unsigned __int64 v104; // r8
  __int64 v105; // rcx
  unsigned __int64 v106; // r8
  __int64 v107; // rcx
  unsigned __int64 v108; // r8
  __int64 v109; // rcx
  unsigned __int64 v110; // r8
  __int64 v111; // rcx
  unsigned __int64 v112; // r8
  __int64 v113; // rcx
  unsigned __int64 v114; // r8
  __int64 v115; // rcx
  unsigned __int64 v116; // r8
  __int64 v117; // rcx
  unsigned __int64 v118; // r8
  __int64 v119; // rcx
  unsigned __int64 v120; // r8
  __int64 v121; // rcx
  unsigned __int64 v122; // r8
  __int64 v123; // rcx
  unsigned __int64 v124; // r8
  __int64 v125; // rcx
  unsigned __int64 v126; // r8
  __int64 v127; // rcx
  unsigned __int64 v128; // r8
  __int64 v129; // rcx
  unsigned __int64 v130; // r8
  __int64 v131; // rcx
  unsigned __int64 v132; // r8
  __int64 v133; // rcx
  unsigned __int64 v134; // r8
  __int64 v135; // rcx
  unsigned __int64 v136; // r8
  __int64 v137; // rcx
  unsigned __int64 v138; // r8
  __int64 v139; // rcx
  unsigned __int64 v140; // r8
  __int64 v141; // rcx
  unsigned __int64 v142; // r8
  __int64 v143; // rcx
  unsigned __int64 v144; // r8
  __int64 v145; // rcx
  unsigned __int64 v146; // r8
  __int64 v147; // rcx
  unsigned __int64 v148; // r8
  __int64 v149; // rcx
  unsigned __int64 v150; // r8
  __int64 v151; // rcx
  unsigned __int64 v152; // r8
  __int64 v153; // rcx
  unsigned __int64 v154; // r8
  __int64 v155; // rcx
  unsigned __int64 v156; // r8
  __int64 v157; // rcx
  unsigned __int64 v158; // r8
  __int64 v159; // rcx
  unsigned __int64 v160; // r8
  __int64 v161; // rcx
  unsigned __int64 v162; // r8
  __int64 v163; // rcx
  __int64 v164; // rcx
  __int64 v165; // rax
  __int64 v166; // rbx
  _BYTE v168[12]; // [rsp+20h] [rbp-29h] BYREF
  int v169; // [rsp+2Ch] [rbp-1Dh]
  __int128 v170; // [rsp+38h] [rbp-11h] BYREF
  __int128 v171; // [rsp+48h] [rbp-1h]
  char v172; // [rsp+58h] [rbp+Fh]
  int v173; // [rsp+59h] [rbp+10h]
  __int16 v174; // [rsp+5Dh] [rbp+14h]
  char v175; // [rsp+5Fh] [rbp+16h]
  int v176; // [rsp+60h] [rbp+17h] BYREF
  _QWORD v177[4]; // [rsp+68h] [rbp+1Fh] BYREF
  char v178; // [rsp+88h] [rbp+3Fh]
  int v179; // [rsp+B0h] [rbp+67h] BYREF

  v2 = 1;
  if ( !(_BYTE)word_18004EF30 )
  {
    if ( _InterlockedCompareExchange(&dword_18004EDA8, 1, 0) != 1 )
      goto LABEL_7;
    while ( _InterlockedCompareExchange(&dword_18004EDA8, 1, 0) == 1 )
      Sleep(0x64u);
    if ( !(_BYTE)word_18004EF30 )
    {
LABEL_7:
      OutputDebugStringW(L"Populating EnterprisePolicy AllowList");
      v170 = 0;
      v171 = 0;
      v3 = -1;
      v4 = -1;
      do
        ++v4;
      while ( off_18004B568[0][v4] );
      std::wstring::_Construct<1,wchar_t const *>(&v170, off_18004B568[0], v4);
      v172 = 1;
      v173 = 0;
      v174 = 0;
      v175 = 0;
      v176 = 1;
      std::wstring::wstring((__int64)v177, (__int64)&v170);
      v178 = v172;
      std::_Tree<std::_Tmap_traits<enum tagEnterprisePolicy,AllowInfo,std::less<enum tagEnterprisePolicy>,std::allocator<std::pair<enum tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v5,
        (__int64)v168,
        (__int64)&v176);
      std::wstring::~wstring(v177);
      std::wstring::~wstring(&v170);
      v170 = 0;
      v171 = 0;
      v6 = -1;
      do
        ++v6;
      while ( off_18004B5E0[0][v6] );
      std::wstring::_Construct<1,wchar_t const *>(&v170, off_18004B5E0[0], v6);
      v172 = 1;
      v173 = 0;
      v174 = 0;
      v175 = 0;
      v176 = 2;
      std::wstring::wstring((__int64)v177, (__int64)&v170);
      v178 = v172;
      std::_Tree<std::_Tmap_traits<enum tagEnterprisePolicy,AllowInfo,std::less<enum tagEnterprisePolicy>,std::allocator<std::pair<enum tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v7,
        (__int64)v168,
        (__int64)&v176);
      std::wstring::~wstring(v177);
      std::wstring::~wstring(&v170);
      v170 = 0;
      v171 = 0;
      v8 = -1;
      do
        ++v8;
      while ( off_18004B658[0][v8] );
      std::wstring::_Construct<1,wchar_t const *>(&v170, off_18004B658[0], v8);
      v172 = 1;
      v173 = 0;
      v174 = 0;
      v175 = 0;
      v176 = 3;
      std::wstring::wstring((__int64)v177, (__int64)&v170);
      v178 = v172;
      std::_Tree<std::_Tmap_traits<enum tagEnterprisePolicy,AllowInfo,std::less<enum tagEnterprisePolicy>,std::allocator<std::pair<enum tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v9,
        (__int64)v168,
        (__int64)&v176);
      std::wstring::~wstring(v177);
      std::wstring::~wstring(&v170);
      v170 = 0;
      v171 = 0;
      v10 = -1;
      do
        ++v10;
      while ( off_18004B6D0[0][v10] );
      std::wstring::_Construct<1,wchar_t const *>(&v170, off_18004B6D0[0], v10);
      v172 = 1;
      v173 = 0;
      v174 = 0;
      v175 = 0;
      v176 = 4;
      std::wstring::wstring((__int64)v177, (__int64)&v170);
      v178 = v172;
      std::_Tree<std::_Tmap_traits<enum tagEnterprisePolicy,AllowInfo,std::less<enum tagEnterprisePolicy>,std::allocator<std::pair<enum tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v11,
        (__int64)v168,
        (__int64)&v176);
      std::wstring::~wstring(v177);
      std::wstring::~wstring(&v170);
      v170 = 0;
      v171 = 0;
      v12 = -1;
      do
        ++v12;
      while ( off_18004B748[0][v12] );
      std::wstring::_Construct<1,wchar_t const *>(&v170, off_18004B748[0], v12);
      v172 = 1;
      v173 = 0;
      v174 = 0;
      v175 = 0;
      v176 = 5;
      std::wstring::wstring((__int64)v177, (__int64)&v170);
      v178 = v172;
      std::_Tree<std::_Tmap_traits<enum tagEnterprisePolicy,AllowInfo,std::less<enum tagEnterprisePolicy>,std::allocator<std::pair<enum tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v13,
        (__int64)v168,
        (__int64)&v176);
      std::wstring::~wstring(v177);
      std::wstring::~wstring(&v170);
      v170 = 0;
      v171 = 0;
      v14 = -1;
      do
        ++v14;
      while ( off_18004B7C0[0][v14] );
      std::wstring::_Construct<1,wchar_t const *>(&v170, off_18004B7C0[0], v14);
      v172 = 1;
      v173 = 0;
      v174 = 0;
      v175 = 0;
      v176 = 6;
      std::wstring::wstring((__int64)v177, (__int64)&v170);
      v178 = v172;
      std::_Tree<std::_Tmap_traits<enum tagEnterprisePolicy,AllowInfo,std::less<enum tagEnterprisePolicy>,std::allocator<std::pair<enum tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v15,
        (__int64)v168,
        (__int64)&v176);
      std::wstring::~wstring(v177);
      std::wstring::~wstring(&v170);
      v170 = 0;
      v171 = 0;
      v16 = -1;
      do
        ++v16;
      while ( off_18004B838[0][v16] );
      std::wstring::_Construct<1,wchar_t const *>(&v170, off_18004B838[0], v16);
      v172 = 1;
      v173 = 0;
      v174 = 0;
      v175 = 0;
      v176 = 7;
      std::wstring::wstring((__int64)v177, (__int64)&v170);
      v178 = v172;
      std::_Tree<std::_Tmap_traits<enum tagEnterprisePolicy,AllowInfo,std::less<enum tagEnterprisePolicy>,std::allocator<std::pair<enum tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v17,
        (__int64)v168,
        (__int64)&v176);
      std::wstring::~wstring(v177);
      std::wstring::~wstring(&v170);
      v170 = 0;
      v171 = 0;
      v18 = -1;
      do
        ++v18;
      while ( off_18004B8B0[0][v18] );
      std::wstring::_Construct<1,wchar_t const *>(&v170, off_18004B8B0[0], v18);
      v172 = 1;
      v173 = 0;
      v174 = 0;
      v175 = 0;
      v176 = 8;
      std::wstring::wstring((__int64)v177, (__int64)&v170);
      v178 = v172;
      std::_Tree<std::_Tmap_traits<enum tagEnterprisePolicy,AllowInfo,std::less<enum tagEnterprisePolicy>,std::allocator<std::pair<enum tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v19,
        (__int64)v168,
        (__int64)&v176);
      std::wstring::~wstring(v177);
      std::wstring::~wstring(&v170);
      v170 = 0;
      v171 = 0;
      v20 = -1;
      do
        ++v20;
      while ( off_18004B928[0][v20] );
      std::wstring::_Construct<1,wchar_t const *>(&v170, off_18004B928[0], v20);
      v172 = 1;
      v173 = 0;
      v174 = 0;
      v175 = 0;
      v176 = 9;
      std::wstring::wstring((__int64)v177, (__int64)&v170);
      v178 = v172;
      std::_Tree<std::_Tmap_traits<enum tagEnterprisePolicy,AllowInfo,std::less<enum tagEnterprisePolicy>,std::allocator<std::pair<enum tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v21,
        (__int64)v168,
        (__int64)&v176);
      std::wstring::~wstring(v177);
      std::wstring::~wstring(&v170);
      v170 = 0;
      v171 = 0;
      v22 = -1;
      do
        ++v22;
      while ( off_18004B9A0[0][v22] );
      std::wstring::_Construct<1,wchar_t const *>(&v170, off_18004B9A0[0], v22);
      v172 = 1;
      v173 = 0;
      v174 = 0;
      v175 = 0;
      v176 = 10;
      std::wstring::wstring((__int64)v177, (__int64)&v170);
      v178 = v172;
      std::_Tree<std::_Tmap_traits<enum tagEnterprisePolicy,AllowInfo,std::less<enum tagEnterprisePolicy>,std::allocator<std::pair<enum tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v23,
        (__int64)v168,
        (__int64)&v176);
      std::wstring::~wstring(v177);
      std::wstring::~wstring(&v170);
      v170 = 0;
      v171 = 0;
      v24 = -1;
      do
        ++v24;
      while ( off_18004BA18[0][v24] );
      std::wstring::_Construct<1,wchar_t const *>(&v170, off_18004BA18[0], v24);
      v172 = 1;
      v173 = 0;
      v174 = 0;
      v175 = 0;
      v176 = 11;
      std::wstring::wstring((__int64)v177, (__int64)&v170);
      v178 = v172;
      std::_Tree<std::_Tmap_traits<enum tagEnterprisePolicy,AllowInfo,std::less<enum tagEnterprisePolicy>,std::allocator<std::pair<enum tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v25,
        (__int64)v168,
        (__int64)&v176);
      std::wstring::~wstring(v177);
      std::wstring::~wstring(&v170);
      v170 = 0;
      v171 = 0;
      v26 = -1;
      do
        ++v26;
      while ( off_18004BA90[0][v26] );
      std::wstring::_Construct<1,wchar_t const *>(&v170, off_18004BA90[0], v26);
      v172 = 1;
      v173 = 0;
      v174 = 0;
      v175 = 0;
      v176 = 12;
      std::wstring::wstring((__int64)v177, (__int64)&v170);
      v178 = v172;
      std::_Tree<std::_Tmap_traits<enum tagEnterprisePolicy,AllowInfo,std::less<enum tagEnterprisePolicy>,std::allocator<std::pair<enum tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v27,
        (__int64)v168,
        (__int64)&v176);
      std::wstring::~wstring(v177);
      std::wstring::~wstring(&v170);
      v170 = 0;
      v171 = 0;
      v28 = -1;
      do
        ++v28;
      while ( off_18004BB08[0][v28] );
      std::wstring::_Construct<1,wchar_t const *>(&v170, off_18004BB08[0], v28);
      v172 = 1;
      v173 = 0;
      v174 = 0;
      v175 = 0;
      v176 = 13;
      std::wstring::wstring((__int64)v177, (__int64)&v170);
      v178 = v172;
      std::_Tree<std::_Tmap_traits<enum tagEnterprisePolicy,AllowInfo,std::less<enum tagEnterprisePolicy>,std::allocator<std::pair<enum tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v29,
        (__int64)v168,
        (__int64)&v176);
      std::wstring::~wstring(v177);
      std::wstring::~wstring(&v170);
      v170 = 0;
      v171 = 0;
      v30 = -1;
      do
        ++v30;
      while ( off_18004BB80[0][v30] );
      std::wstring::_Construct<1,wchar_t const *>(&v170, off_18004BB80[0], v30);
      v172 = 1;
      v173 = 0;
      v174 = 0;
      v175 = 0;
      v176 = 14;
      std::wstring::wstring((__int64)v177, (__int64)&v170);
      v178 = v172;
      std::_Tree<std::_Tmap_traits<enum tagEnterprisePolicy,AllowInfo,std::less<enum tagEnterprisePolicy>,std::allocator<std::pair<enum tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v31,
        (__int64)v168,
        (__int64)&v176);
      std::wstring::~wstring(v177);
      std::wstring::~wstring(&v170);
      v170 = 0;
      v171 = 0;
      v32 = -1;
      do
        ++v32;
      while ( off_18004BBF8[0][v32] );
      std::wstring::_Construct<1,wchar_t const *>(&v170, off_18004BBF8[0], v32);
      v172 = 1;
      v173 = 0;
      v174 = 0;
      v175 = 0;
      v176 = 15;
      std::wstring::wstring((__int64)v177, (__int64)&v170);
      v178 = v172;
      std::_Tree<std::_Tmap_traits<enum tagEnterprisePolicy,AllowInfo,std::less<enum tagEnterprisePolicy>,std::allocator<std::pair<enum tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v33,
        (__int64)v168,
        (__int64)&v176);
      std::wstring::~wstring(v177);
      std::wstring::~wstring(&v170);
      v170 = 0;
      v171 = 0;
      v34 = -1;
      do
        ++v34;
      while ( off_18004BC70[0][v34] );
      std::wstring::_Construct<1,wchar_t const *>(&v170, off_18004BC70[0], v34);
      v172 = 1;
      v173 = 0;
      v174 = 0;
      v175 = 0;
      v176 = 16;
      std::wstring::wstring((__int64)v177, (__int64)&v170);
      v178 = v172;
      std::_Tree<std::_Tmap_traits<enum tagEnterprisePolicy,AllowInfo,std::less<enum tagEnterprisePolicy>,std::allocator<std::pair<enum tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v35,
        (__int64)v168,
        (__int64)&v176);
      std::wstring::~wstring(v177);
      std::wstring::~wstring(&v170);
      v170 = 0;
      v171 = 0;
      v36 = -1;
      do
        ++v36;
      while ( off_18004BCE8[0][v36] );
      std::wstring::_Construct<1,wchar_t const *>(&v170, off_18004BCE8[0], v36);
      v172 = 1;
      v173 = 0;
      v174 = 0;
      v175 = 0;
      v176 = 17;
      std::wstring::wstring((__int64)v177, (__int64)&v170);
      v178 = v172;
      std::_Tree<std::_Tmap_traits<enum tagEnterprisePolicy,AllowInfo,std::less<enum tagEnterprisePolicy>,std::allocator<std::pair<enum tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v37,
        (__int64)v168,
        (__int64)&v176);
      std::wstring::~wstring(v177);
      std::wstring::~wstring(&v170);
      v170 = 0;
      v171 = 0;
      v38 = -1;
      do
        ++v38;
      while ( off_18004BD60[0][v38] );
      std::wstring::_Construct<1,wchar_t const *>(&v170, off_18004BD60[0], v38);
      v172 = 1;
      v173 = 0;
      v174 = 0;
      v175 = 0;
      v176 = 18;
      std::wstring::wstring((__int64)v177, (__int64)&v170);
      v178 = v172;
      std::_Tree<std::_Tmap_traits<enum tagEnterprisePolicy,AllowInfo,std::less<enum tagEnterprisePolicy>,std::allocator<std::pair<enum tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v39,
        (__int64)v168,
        (__int64)&v176);
      std::wstring::~wstring(v177);
      std::wstring::~wstring(&v170);
      v170 = 0;
      v171 = 0;
      v40 = -1;
      do
        ++v40;
      while ( off_18004BDD8[0][v40] );
      std::wstring::_Construct<1,wchar_t const *>(&v170, off_18004BDD8[0], v40);
      v172 = 1;
      v173 = 0;
      v174 = 0;
      v175 = 0;
      v176 = 19;
      std::wstring::wstring((__int64)v177, (__int64)&v170);
      v178 = v172;
      std::_Tree<std::_Tmap_traits<enum tagEnterprisePolicy,AllowInfo,std::less<enum tagEnterprisePolicy>,std::allocator<std::pair<enum tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v41,
        (__int64)v168,
        (__int64)&v176);
      std::wstring::~wstring(v177);
      std::wstring::~wstring(&v170);
      v170 = 0;
      v171 = 0;
      v42 = -1;
      do
        ++v42;
      while ( off_18004BE50[0][v42] );
      std::wstring::_Construct<1,wchar_t const *>(&v170, off_18004BE50[0], v42);
      v172 = 1;
      v173 = 0;
      v174 = 0;
      v175 = 0;
      v176 = 20;
      std::wstring::wstring((__int64)v177, (__int64)&v170);
      v178 = v172;
      std::_Tree<std::_Tmap_traits<enum tagEnterprisePolicy,AllowInfo,std::less<enum tagEnterprisePolicy>,std::allocator<std::pair<enum tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v43,
        (__int64)v168,
        (__int64)&v176);
      std::wstring::~wstring(v177);
      std::wstring::~wstring(&v170);
      v170 = 0;
      v171 = 0;
      v44 = -1;
      do
        ++v44;
      while ( off_18004BEC8[0][v44] );
      std::wstring::_Construct<1,wchar_t const *>(&v170, off_18004BEC8[0], v44);
      v172 = 1;
      v173 = 0;
      v174 = 0;
      v175 = 0;
      v176 = 21;
      std::wstring::wstring((__int64)v177, (__int64)&v170);
      v178 = v172;
      std::_Tree<std::_Tmap_traits<enum tagEnterprisePolicy,AllowInfo,std::less<enum tagEnterprisePolicy>,std::allocator<std::pair<enum tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v45,
        (__int64)v168,
        (__int64)&v176);
      std::wstring::~wstring(v177);
      std::wstring::~wstring(&v170);
      v170 = 0;
      v171 = 0;
      v46 = -1;
      do
        ++v46;
      while ( off_18004BF40[0][v46] );
      std::wstring::_Construct<1,wchar_t const *>(&v170, off_18004BF40[0], v46);
      v172 = 1;
      v173 = 0;
      v174 = 0;
      v175 = 0;
      v176 = 22;
      std::wstring::wstring((__int64)v177, (__int64)&v170);
      v178 = v172;
      std::_Tree<std::_Tmap_traits<enum tagEnterprisePolicy,AllowInfo,std::less<enum tagEnterprisePolicy>,std::allocator<std::pair<enum tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v47,
        (__int64)v168,
        (__int64)&v176);
      std::wstring::~wstring(v177);
      std::wstring::~wstring(&v170);
      v170 = 0;
      v171 = 0;
      v48 = -1;
      do
        ++v48;
      while ( off_18004BFB8[0][v48] );
      std::wstring::_Construct<1,wchar_t const *>(&v170, off_18004BFB8[0], v48);
      v172 = 1;
      v173 = 0;
      v174 = 0;
      v175 = 0;
      v176 = 23;
      std::wstring::wstring((__int64)v177, (__int64)&v170);
      v178 = v172;
      std::_Tree<std::_Tmap_traits<enum tagEnterprisePolicy,AllowInfo,std::less<enum tagEnterprisePolicy>,std::allocator<std::pair<enum tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v49,
        (__int64)v168,
        (__int64)&v176);
      std::wstring::~wstring(v177);
      std::wstring::~wstring(&v170);
      v170 = 0;
      v171 = 0;
      v50 = -1;
      do
        ++v50;
      while ( off_18004C030[0][v50] );
      std::wstring::_Construct<1,wchar_t const *>(&v170, off_18004C030[0], v50);
      v172 = 1;
      v173 = 0;
      v174 = 0;
      v175 = 0;
      v176 = 24;
      std::wstring::wstring((__int64)v177, (__int64)&v170);
      v178 = v172;
      std::_Tree<std::_Tmap_traits<enum tagEnterprisePolicy,AllowInfo,std::less<enum tagEnterprisePolicy>,std::allocator<std::pair<enum tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v51,
        (__int64)v168,
        (__int64)&v176);
      std::wstring::~wstring(v177);
      std::wstring::~wstring(&v170);
      v170 = 0;
      v171 = 0;
      v52 = -1;
      do
        ++v52;
      while ( off_18004C0A8[0][v52] );
      std::wstring::_Construct<1,wchar_t const *>(&v170, off_18004C0A8[0], v52);
      v172 = 1;
      v173 = 0;
      v174 = 0;
      v175 = 0;
      v176 = 25;
      std::wstring::wstring((__int64)v177, (__int64)&v170);
      v178 = v172;
      std::_Tree<std::_Tmap_traits<enum tagEnterprisePolicy,AllowInfo,std::less<enum tagEnterprisePolicy>,std::allocator<std::pair<enum tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v53,
        (__int64)v168,
        (__int64)&v176);
      std::wstring::~wstring(v177);
      std::wstring::~wstring(&v170);
      v170 = 0;
      v171 = 0;
      v54 = -1;
      do
        ++v54;
      while ( off_18004C120[0][v54] );
      std::wstring::_Construct<1,wchar_t const *>(&v170, off_18004C120[0], v54);
      v172 = 1;
      v173 = 0;
      v174 = 0;
      v175 = 0;
      v176 = 26;
      std::wstring::wstring((__int64)v177, (__int64)&v170);
      v178 = v172;
      std::_Tree<std::_Tmap_traits<enum tagEnterprisePolicy,AllowInfo,std::less<enum tagEnterprisePolicy>,std::allocator<std::pair<enum tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v55,
        (__int64)v168,
        (__int64)&v176);
      std::wstring::~wstring(v177);
      std::wstring::~wstring(&v170);
      v170 = 0;
      v171 = 0;
      v56 = -1;
      do
        ++v56;
      while ( off_18004C198[0][v56] );
      std::wstring::_Construct<1,wchar_t const *>(&v170, off_18004C198[0], v56);
      v172 = 1;
      v173 = 0;
      v174 = 0;
      v175 = 0;
      v176 = 27;
      std::wstring::wstring((__int64)v177, (__int64)&v170);
      v178 = v172;
      std::_Tree<std::_Tmap_traits<enum tagEnterprisePolicy,AllowInfo,std::less<enum tagEnterprisePolicy>,std::allocator<std::pair<enum tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v57,
        (__int64)v168,
        (__int64)&v176);
      std::wstring::~wstring(v177);
      std::wstring::~wstring(&v170);
      v170 = 0;
      v171 = 0;
      v58 = -1;
      do
        ++v58;
      while ( off_18004C210[0][v58] );
      std::wstring::_Construct<1,wchar_t const *>(&v170, off_18004C210[0], v58);
      v172 = 1;
      v173 = 0;
      v174 = 0;
      v175 = 0;
      v176 = 28;
      std::wstring::wstring((__int64)v177, (__int64)&v170);
      v178 = v172;
      std::_Tree<std::_Tmap_traits<enum tagEnterprisePolicy,AllowInfo,std::less<enum tagEnterprisePolicy>,std::allocator<std::pair<enum tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v59,
        (__int64)v168,
        (__int64)&v176);
      std::wstring::~wstring(v177);
      std::wstring::~wstring(&v170);
      v170 = 0;
      v171 = 0;
      v60 = -1;
      do
        ++v60;
      while ( off_18004C288[0][v60] );
      std::wstring::_Construct<1,wchar_t const *>(&v170, off_18004C288[0], v60);
      v172 = 1;
      v173 = 0;
      v174 = 0;
      v175 = 0;
      v176 = 29;
      std::wstring::wstring((__int64)v177, (__int64)&v170);
      v178 = v172;
      std::_Tree<std::_Tmap_traits<enum tagEnterprisePolicy,AllowInfo,std::less<enum tagEnterprisePolicy>,std::allocator<std::pair<enum tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v61,
        (__int64)v168,
        (__int64)&v176);
      std::wstring::~wstring(v177);
      std::wstring::~wstring(&v170);
      v170 = 0;
      v171 = 0;
      v62 = -1;
      do
        ++v62;
      while ( off_18004C300[0][v62] );
      std::wstring::_Construct<1,wchar_t const *>(&v170, off_18004C300[0], v62);
      v172 = 1;
      v173 = 0;
      v174 = 0;
      v175 = 0;
      v176 = 30;
      std::wstring::wstring((__int64)v177, (__int64)&v170);
      v178 = v172;
      std::_Tree<std::_Tmap_traits<enum tagEnterprisePolicy,AllowInfo,std::less<enum tagEnterprisePolicy>,std::allocator<std::pair<enum tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v63,
        (__int64)v168,
        (__int64)&v176);
      std::wstring::~wstring(v177);
      std::wstring::~wstring(&v170);
      v170 = 0;
      v171 = 0;
      v64 = -1;
      do
        ++v64;
      while ( off_18004C378[0][v64] );
      std::wstring::_Construct<1,wchar_t const *>(&v170, off_18004C378[0], v64);
      v172 = 1;
      v173 = 0;
      v174 = 0;
      v175 = 0;
      v176 = 31;
      std::wstring::wstring((__int64)v177, (__int64)&v170);
      v178 = v172;
      std::_Tree<std::_Tmap_traits<enum tagEnterprisePolicy,AllowInfo,std::less<enum tagEnterprisePolicy>,std::allocator<std::pair<enum tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v65,
        (__int64)v168,
        (__int64)&v176);
      std::wstring::~wstring(v177);
      std::wstring::~wstring(&v170);
      v170 = 0;
      v171 = 0;
      v66 = -1;
      do
        ++v66;
      while ( off_18004C3F0[0][v66] );
      std::wstring::_Construct<1,wchar_t const *>(&v170, off_18004C3F0[0], v66);
      v172 = 1;
      v173 = 0;
      v174 = 0;
      v175 = 0;
      v176 = 32;
      std::wstring::wstring((__int64)v177, (__int64)&v170);
      v178 = v172;
      std::_Tree<std::_Tmap_traits<enum tagEnterprisePolicy,AllowInfo,std::less<enum tagEnterprisePolicy>,std::allocator<std::pair<enum tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v67,
        (__int64)v168,
        (__int64)&v176);
      std::wstring::~wstring(v177);
      std::wstring::~wstring(&v170);
      v170 = 0;
      v171 = 0;
      v68 = -1;
      do
        ++v68;
      while ( off_18004C468[0][v68] );
      std::wstring::_Construct<1,wchar_t const *>(&v170, off_18004C468[0], v68);
      v172 = 1;
      v173 = 0;
      v174 = 0;
      v175 = 0;
      v176 = 33;
      std::wstring::wstring((__int64)v177, (__int64)&v170);
      v178 = v172;
      std::_Tree<std::_Tmap_traits<enum tagEnterprisePolicy,AllowInfo,std::less<enum tagEnterprisePolicy>,std::allocator<std::pair<enum tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v69,
        (__int64)v168,
        (__int64)&v176);
      std::wstring::~wstring(v177);
      std::wstring::~wstring(&v170);
      v170 = 0;
      v171 = 0;
      v70 = -1;
      do
        ++v70;
      while ( off_18004C4E0[0][v70] );
      std::wstring::_Construct<1,wchar_t const *>(&v170, off_18004C4E0[0], v70);
      v172 = 1;
      v173 = 0;
      v174 = 0;
      v175 = 0;
      v176 = 34;
      std::wstring::wstring((__int64)v177, (__int64)&v170);
      v178 = v172;
      std::_Tree<std::_Tmap_traits<enum tagEnterprisePolicy,AllowInfo,std::less<enum tagEnterprisePolicy>,std::allocator<std::pair<enum tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v71,
        (__int64)v168,
        (__int64)&v176);
      std::wstring::~wstring(v177);
      std::wstring::~wstring(&v170);
      v170 = 0;
      v171 = 0;
      v72 = -1;
      do
        ++v72;
      while ( off_18004C558[0][v72] );
      std::wstring::_Construct<1,wchar_t const *>(&v170, off_18004C558[0], v72);
      v172 = 1;
      v173 = 0;
      v174 = 0;
      v175 = 0;
      v176 = 35;
      std::wstring::wstring((__int64)v177, (__int64)&v170);
      v178 = v172;
      std::_Tree<std::_Tmap_traits<enum tagEnterprisePolicy,AllowInfo,std::less<enum tagEnterprisePolicy>,std::allocator<std::pair<enum tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v73,
        (__int64)v168,
        (__int64)&v176);
      std::wstring::~wstring(v177);
      std::wstring::~wstring(&v170);
      v170 = 0;
      v171 = 0;
      v74 = -1;
      do
        ++v74;
      while ( off_18004C5D0[0][v74] );
      std::wstring::_Construct<1,wchar_t const *>(&v170, off_18004C5D0[0], v74);
      v172 = 1;
      v173 = 0;
      v174 = 0;
      v175 = 0;
      v176 = 36;
      std::wstring::wstring((__int64)v177, (__int64)&v170);
      v178 = v172;
      std::_Tree<std::_Tmap_traits<enum tagEnterprisePolicy,AllowInfo,std::less<enum tagEnterprisePolicy>,std::allocator<std::pair<enum tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v75,
        (__int64)v168,
        (__int64)&v176);
      std::wstring::~wstring(v177);
      std::wstring::~wstring(&v170);
      v170 = 0;
      v171 = 0;
      v76 = -1;
      do
        ++v76;
      while ( off_18004C648[0][v76] );
      std::wstring::_Construct<1,wchar_t const *>(&v170, off_18004C648[0], v76);
      v172 = 1;
      v173 = 0;
      v174 = 0;
      v175 = 0;
      v176 = 37;
      std::wstring::wstring((__int64)v177, (__int64)&v170);
      v178 = v172;
      std::_Tree<std::_Tmap_traits<enum tagEnterprisePolicy,AllowInfo,std::less<enum tagEnterprisePolicy>,std::allocator<std::pair<enum tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v77,
        (__int64)v168,
        (__int64)&v176);
      std::wstring::~wstring(v177);
      std::wstring::~wstring(&v170);
      v170 = 0;
      v171 = 0;
      v78 = -1;
      do
        ++v78;
      while ( off_18004C6C0[0][v78] );
      std::wstring::_Construct<1,wchar_t const *>(&v170, off_18004C6C0[0], v78);
      v172 = 1;
      v173 = 0;
      v174 = 0;
      v175 = 0;
      v176 = 38;
      std::wstring::wstring((__int64)v177, (__int64)&v170);
      v178 = v172;
      std::_Tree<std::_Tmap_traits<enum tagEnterprisePolicy,AllowInfo,std::less<enum tagEnterprisePolicy>,std::allocator<std::pair<enum tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v79,
        (__int64)v168,
        (__int64)&v176);
      std::wstring::~wstring(v177);
      std::wstring::~wstring(&v170);
      v170 = 0;
      v171 = 0;
      v80 = -1;
      do
        ++v80;
      while ( off_18004C738[0][v80] );
      std::wstring::_Construct<1,wchar_t const *>(&v170, off_18004C738[0], v80);
      v172 = 1;
      v173 = 0;
      v174 = 0;
      v175 = 0;
      v176 = 39;
      std::wstring::wstring((__int64)v177, (__int64)&v170);
      v178 = v172;
      std::_Tree<std::_Tmap_traits<enum tagEnterprisePolicy,AllowInfo,std::less<enum tagEnterprisePolicy>,std::allocator<std::pair<enum tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v81,
        (__int64)v168,
        (__int64)&v176);
      std::wstring::~wstring(v177);
      std::wstring::~wstring(&v170);
      v170 = 0;
      v171 = 0;
      v82 = -1;
      do
        ++v82;
      while ( off_18004C7B0[0][v82] );
      std::wstring::_Construct<1,wchar_t const *>(&v170, off_18004C7B0[0], v82);
      v172 = 1;
      v173 = 0;
      v174 = 0;
      v175 = 0;
      v176 = 40;
      std::wstring::wstring((__int64)v177, (__int64)&v170);
      v178 = v172;
      std::_Tree<std::_Tmap_traits<enum tagEnterprisePolicy,AllowInfo,std::less<enum tagEnterprisePolicy>,std::allocator<std::pair<enum tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v83,
        (__int64)v168,
        (__int64)&v176);
      std::wstring::~wstring(v177);
      std::wstring::~wstring(&v170);
      v170 = 0;
      v171 = 0;
      v84 = -1;
      do
        ++v84;
      while ( off_18004C828[0][v84] );
      std::wstring::_Construct<1,wchar_t const *>(&v170, off_18004C828[0], v84);
      v172 = 1;
      v173 = 0;
      v174 = 0;
      v175 = 0;
      v176 = 41;
      std::wstring::wstring((__int64)v177, (__int64)&v170);
      v178 = v172;
      std::_Tree<std::_Tmap_traits<enum tagEnterprisePolicy,AllowInfo,std::less<enum tagEnterprisePolicy>,std::allocator<std::pair<enum tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v85,
        (__int64)v168,
        (__int64)&v176);
      std::wstring::~wstring(v177);
      std::wstring::~wstring(&v170);
      v170 = 0;
      v171 = 0;
      v86 = -1;
      do
        ++v86;
      while ( off_18004C8A0[0][v86] );
      std::wstring::_Construct<1,wchar_t const *>(&v170, off_18004C8A0[0], v86);
      v172 = 1;
      v173 = 0;
      v174 = 0;
      v175 = 0;
      v176 = 42;
      std::wstring::wstring((__int64)v177, (__int64)&v170);
      v178 = v172;
      std::_Tree<std::_Tmap_traits<enum tagEnterprisePolicy,AllowInfo,std::less<enum tagEnterprisePolicy>,std::allocator<std::pair<enum tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v87,
        (__int64)v168,
        (__int64)&v176);
      std::wstring::~wstring(v177);
      std::wstring::~wstring(&v170);
      v170 = 0;
      v171 = 0;
      v88 = -1;
      do
        ++v88;
      while ( off_18004C918[0][v88] );
      std::wstring::_Construct<1,wchar_t const *>(&v170, off_18004C918[0], v88);
      v172 = 1;
      v173 = 0;
      v174 = 0;
      v175 = 0;
      v176 = 43;
      std::wstring::wstring((__int64)v177, (__int64)&v170);
      v178 = v172;
      std::_Tree<std::_Tmap_traits<enum tagEnterprisePolicy,AllowInfo,std::less<enum tagEnterprisePolicy>,std::allocator<std::pair<enum tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v89,
        (__int64)v168,
        (__int64)&v176);
      std::wstring::~wstring(v177);
      std::wstring::~wstring(&v170);
      v170 = 0;
      v171 = 0;
      v90 = -1;
      do
        ++v90;
      while ( off_18004C990[0][v90] );
      std::wstring::_Construct<1,wchar_t const *>(&v170, off_18004C990[0], v90);
      v172 = 1;
      v173 = 0;
      v174 = 0;
      v175 = 0;
      v176 = 44;
      std::wstring::wstring((__int64)v177, (__int64)&v170);
      v178 = v172;
      std::_Tree<std::_Tmap_traits<enum tagEnterprisePolicy,AllowInfo,std::less<enum tagEnterprisePolicy>,std::allocator<std::pair<enum tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v91,
        (__int64)v168,
        (__int64)&v176);
      std::wstring::~wstring(v177);
      std::wstring::~wstring(&v170);
      v170 = 0;
      v171 = 0;
      v92 = -1;
      do
        ++v92;
      while ( off_18004CA08[0][v92] );
      std::wstring::_Construct<1,wchar_t const *>(&v170, off_18004CA08[0], v92);
      v172 = 1;
      v173 = 0;
      v174 = 0;
      v175 = 0;
      v176 = 45;
      std::wstring::wstring((__int64)v177, (__int64)&v170);
      v178 = v172;
      std::_Tree<std::_Tmap_traits<enum tagEnterprisePolicy,AllowInfo,std::less<enum tagEnterprisePolicy>,std::allocator<std::pair<enum tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v93,
        (__int64)v168,
        (__int64)&v176);
      std::wstring::~wstring(v177);
      std::wstring::~wstring(&v170);
      v170 = 0;
      v171 = 0;
      v94 = -1;
      do
        ++v94;
      while ( off_18004CA80[0][v94] );
      std::wstring::_Construct<1,wchar_t const *>(&v170, off_18004CA80[0], v94);
      v172 = 1;
      v173 = 0;
      v174 = 0;
      v175 = 0;
      v176 = 46;
      std::wstring::wstring((__int64)v177, (__int64)&v170);
      v178 = v172;
      std::_Tree<std::_Tmap_traits<enum tagEnterprisePolicy,AllowInfo,std::less<enum tagEnterprisePolicy>,std::allocator<std::pair<enum tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v95,
        (__int64)v168,
        (__int64)&v176);
      std::wstring::~wstring(v177);
      std::wstring::~wstring(&v170);
      v170 = 0;
      v171 = 0;
      v96 = -1;
      do
        ++v96;
      while ( off_18004CAF8[0][v96] );
      std::wstring::_Construct<1,wchar_t const *>(&v170, off_18004CAF8[0], v96);
      v172 = 1;
      v173 = 0;
      v174 = 0;
      v175 = 0;
      v176 = 47;
      std::wstring::wstring((__int64)v177, (__int64)&v170);
      v178 = v172;
      std::_Tree<std::_Tmap_traits<enum tagEnterprisePolicy,AllowInfo,std::less<enum tagEnterprisePolicy>,std::allocator<std::pair<enum tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v97,
        (__int64)v168,
        (__int64)&v176);
      std::wstring::~wstring(v177);
      std::wstring::~wstring(&v170);
      v170 = 0;
      v171 = 0;
      v98 = -1;
      do
        ++v98;
      while ( off_18004CB70[0][v98] );
      std::wstring::_Construct<1,wchar_t const *>(&v170, off_18004CB70[0], v98);
      v172 = 1;
      v173 = 0;
      v174 = 0;
      v175 = 0;
      v176 = 48;
      std::wstring::wstring((__int64)v177, (__int64)&v170);
      v178 = v172;
      std::_Tree<std::_Tmap_traits<enum tagEnterprisePolicy,AllowInfo,std::less<enum tagEnterprisePolicy>,std::allocator<std::pair<enum tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v99,
        (__int64)v168,
        (__int64)&v176);
      std::wstring::~wstring(v177);
      std::wstring::~wstring(&v170);
      v170 = 0;
      v171 = 0;
      v100 = -1;
      do
        ++v100;
      while ( off_18004CD50[0][v100] );
      std::wstring::_Construct<1,wchar_t const *>(&v170, off_18004CD50[0], v100);
      v172 = 1;
      v173 = 0;
      v174 = 0;
      v175 = 0;
      v176 = 52;
      std::wstring::wstring((__int64)v177, (__int64)&v170);
      v178 = v172;
      std::_Tree<std::_Tmap_traits<enum tagEnterprisePolicy,AllowInfo,std::less<enum tagEnterprisePolicy>,std::allocator<std::pair<enum tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v101,
        (__int64)v168,
        (__int64)&v176);
      std::wstring::~wstring(v177);
      std::wstring::~wstring(&v170);
      v170 = 0;
      v171 = 0;
      v102 = -1;
      do
        ++v102;
      while ( off_18004CBE8[0][v102] );
      std::wstring::_Construct<1,wchar_t const *>(&v170, off_18004CBE8[0], v102);
      v172 = 1;
      v173 = 0;
      v174 = 0;
      v175 = 0;
      v176 = 49;
      std::wstring::wstring((__int64)v177, (__int64)&v170);
      v178 = v172;
      std::_Tree<std::_Tmap_traits<enum tagEnterprisePolicy,AllowInfo,std::less<enum tagEnterprisePolicy>,std::allocator<std::pair<enum tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v103,
        (__int64)v168,
        (__int64)&v176);
      std::wstring::~wstring(v177);
      std::wstring::~wstring(&v170);
      v170 = 0;
      v171 = 0;
      v104 = -1;
      do
        ++v104;
      while ( off_18004CC60[0][v104] );
      std::wstring::_Construct<1,wchar_t const *>(&v170, off_18004CC60[0], v104);
      v172 = 1;
      v173 = 0;
      v174 = 0;
      v175 = 0;
      v176 = 50;
      std::wstring::wstring((__int64)v177, (__int64)&v170);
      v178 = v172;
      std::_Tree<std::_Tmap_traits<enum tagEnterprisePolicy,AllowInfo,std::less<enum tagEnterprisePolicy>,std::allocator<std::pair<enum tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v105,
        (__int64)v168,
        (__int64)&v176);
      std::wstring::~wstring(v177);
      std::wstring::~wstring(&v170);
      v170 = 0;
      v171 = 0;
      v106 = -1;
      do
        ++v106;
      while ( off_18004CCD8[0][v106] );
      std::wstring::_Construct<1,wchar_t const *>(&v170, off_18004CCD8[0], v106);
      v172 = 1;
      v173 = 0;
      v174 = 0;
      v175 = 0;
      v176 = 51;
      std::wstring::wstring((__int64)v177, (__int64)&v170);
      v178 = v172;
      std::_Tree<std::_Tmap_traits<enum tagEnterprisePolicy,AllowInfo,std::less<enum tagEnterprisePolicy>,std::allocator<std::pair<enum tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v107,
        (__int64)v168,
        (__int64)&v176);
      std::wstring::~wstring(v177);
      std::wstring::~wstring(&v170);
      v170 = 0;
      v171 = 0;
      v108 = -1;
      do
        ++v108;
      while ( off_18004CE40[0][v108] );
      std::wstring::_Construct<1,wchar_t const *>(&v170, off_18004CE40[0], v108);
      v172 = 1;
      v173 = 0;
      v174 = 0;
      v175 = 0;
      v176 = 54;
      std::wstring::wstring((__int64)v177, (__int64)&v170);
      v178 = v172;
      std::_Tree<std::_Tmap_traits<enum tagEnterprisePolicy,AllowInfo,std::less<enum tagEnterprisePolicy>,std::allocator<std::pair<enum tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v109,
        (__int64)v168,
        (__int64)&v176);
      std::wstring::~wstring(v177);
      std::wstring::~wstring(&v170);
      v170 = 0;
      v171 = 0;
      v110 = -1;
      do
        ++v110;
      while ( off_18004CFA8[0][v110] );
      std::wstring::_Construct<1,wchar_t const *>(&v170, off_18004CFA8[0], v110);
      v172 = 1;
      v173 = 0;
      v174 = 0;
      v175 = 0;
      v176 = 57;
      std::wstring::wstring((__int64)v177, (__int64)&v170);
      v178 = v172;
      std::_Tree<std::_Tmap_traits<enum tagEnterprisePolicy,AllowInfo,std::less<enum tagEnterprisePolicy>,std::allocator<std::pair<enum tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v111,
        (__int64)v168,
        (__int64)&v176);
      std::wstring::~wstring(v177);
      std::wstring::~wstring(&v170);
      v170 = 0;
      v171 = 0;
      v112 = -1;
      do
        ++v112;
      while ( off_18004D098[0][v112] );
      std::wstring::_Construct<1,wchar_t const *>(&v170, off_18004D098[0], v112);
      v172 = 1;
      v173 = 0;
      v174 = 0;
      v175 = 0;
      v176 = 59;
      std::wstring::wstring((__int64)v177, (__int64)&v170);
      v178 = v172;
      std::_Tree<std::_Tmap_traits<enum tagEnterprisePolicy,AllowInfo,std::less<enum tagEnterprisePolicy>,std::allocator<std::pair<enum tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v113,
        (__int64)v168,
        (__int64)&v176);
      std::wstring::~wstring(v177);
      std::wstring::~wstring(&v170);
      v170 = 0;
      v171 = 0;
      v114 = -1;
      do
        ++v114;
      while ( off_18004D110[0][v114] );
      std::wstring::_Construct<1,wchar_t const *>(&v170, off_18004D110[0], v114);
      v172 = 1;
      v173 = 0;
      v174 = 0;
      v175 = 0;
      v176 = 60;
      std::wstring::wstring((__int64)v177, (__int64)&v170);
      v178 = v172;
      std::_Tree<std::_Tmap_traits<enum tagEnterprisePolicy,AllowInfo,std::less<enum tagEnterprisePolicy>,std::allocator<std::pair<enum tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v115,
        (__int64)v168,
        (__int64)&v176);
      std::wstring::~wstring(v177);
      std::wstring::~wstring(&v170);
      v170 = 0;
      v171 = 0;
      v116 = -1;
      do
        ++v116;
      while ( off_18004D188[0][v116] );
      std::wstring::_Construct<1,wchar_t const *>(&v170, off_18004D188[0], v116);
      v172 = 1;
      v173 = 0;
      v174 = 0;
      v175 = 0;
      v176 = 61;
      std::wstring::wstring((__int64)v177, (__int64)&v170);
      v178 = v172;
      std::_Tree<std::_Tmap_traits<enum tagEnterprisePolicy,AllowInfo,std::less<enum tagEnterprisePolicy>,std::allocator<std::pair<enum tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v117,
        (__int64)v168,
        (__int64)&v176);
      std::wstring::~wstring(v177);
      std::wstring::~wstring(&v170);
      v170 = 0;
      v171 = 0;
      v118 = -1;
      do
        ++v118;
      while ( off_18004D200[0][v118] );
      std::wstring::_Construct<1,wchar_t const *>(&v170, off_18004D200[0], v118);
      v172 = 1;
      v173 = 0;
      v174 = 0;
      v175 = 0;
      v176 = 62;
      std::wstring::wstring((__int64)v177, (__int64)&v170);
      v178 = v172;
      std::_Tree<std::_Tmap_traits<enum tagEnterprisePolicy,AllowInfo,std::less<enum tagEnterprisePolicy>,std::allocator<std::pair<enum tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v119,
        (__int64)v168,
        (__int64)&v176);
      std::wstring::~wstring(v177);
      std::wstring::~wstring(&v170);
      v170 = 0;
      v171 = 0;
      v120 = -1;
      do
        ++v120;
      while ( off_18004D278[0][v120] );
      std::wstring::_Construct<1,wchar_t const *>(&v170, off_18004D278[0], v120);
      v172 = 1;
      v173 = 0;
      v174 = 0;
      v175 = 0;
      v176 = 63;
      std::wstring::wstring((__int64)v177, (__int64)&v170);
      v178 = v172;
      std::_Tree<std::_Tmap_traits<enum tagEnterprisePolicy,AllowInfo,std::less<enum tagEnterprisePolicy>,std::allocator<std::pair<enum tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v121,
        (__int64)v168,
        (__int64)&v176);
      std::wstring::~wstring(v177);
      std::wstring::~wstring(&v170);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_QuickMachineRecoveryEnrolled_59112206>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_QuickMachineRecoveryEnrolled_59112206>::GetImpl'::`2'::impl) )
      {
        v179 = 64;
        v170 = 0;
        v171 = 0;
        v122 = -1;
        do
          ++v122;
        while ( off_18004D2F0[0][v122] );
        std::wstring::_Construct<1,wchar_t const *>(&v170, off_18004D2F0[0], v122);
        v172 = 1;
        v173 = 0;
        v174 = 0;
        v175 = 0;
        std::pair<enum tagEnterprisePolicy const,AllowInfo>::pair<enum tagEnterprisePolicy const,AllowInfo>(
          (__int64)&v176,
          &v179,
          (__int64)&v170);
        std::_Tree<std::_Tmap_traits<enum tagEnterprisePolicy,AllowInfo,std::less<enum tagEnterprisePolicy>,std::allocator<std::pair<enum tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(
          v123,
          (__int64)v168,
          (__int64)&v176);
        std::wstring::~wstring(v177);
        std::wstring::~wstring(&v170);
      }
      if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_MaintenanceWindow_UpdatePolicyReader>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_MaintenanceWindow_UpdatePolicyReader>::GetImpl'::`2'::impl) )
      {
        v170 = 0;
        v171 = 0;
        v124 = -1;
        do
          ++v124;
        while ( off_18004D368[0][v124] );
        std::wstring::_Construct<1,wchar_t const *>(&v170, off_18004D368[0], v124);
        v172 = 1;
        v173 = 0;
        v174 = 0;
        v175 = 0;
        v176 = 65;
        std::wstring::wstring((__int64)v177, (__int64)&v170);
        v178 = v172;
        std::_Tree<std::_Tmap_traits<enum tagEnterprisePolicy,AllowInfo,std::less<enum tagEnterprisePolicy>,std::allocator<std::pair<enum tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(
          v125,
          (__int64)v168,
          (__int64)&v176);
        std::wstring::~wstring(v177);
        std::wstring::~wstring(&v170);
        v179 = 66;
        v170 = 0;
        v171 = 0;
        v126 = -1;
        do
          ++v126;
        while ( off_18004D3E0[0][v126] );
        std::wstring::_Construct<1,wchar_t const *>(&v170, off_18004D3E0[0], v126);
        v172 = 1;
        v173 = 0;
        v174 = 0;
        v175 = 0;
        std::pair<enum tagEnterprisePolicy const,AllowInfo>::pair<enum tagEnterprisePolicy const,AllowInfo>(
          (__int64)&v176,
          &v179,
          (__int64)&v170);
        std::_Tree<std::_Tmap_traits<enum tagEnterprisePolicy,AllowInfo,std::less<enum tagEnterprisePolicy>,std::allocator<std::pair<enum tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(
          v127,
          (__int64)v168,
          (__int64)&v176);
        std::wstring::~wstring(v177);
        std::wstring::~wstring(&v170);
        v170 = 0;
        v171 = 0;
        v128 = -1;
        do
          ++v128;
        while ( off_18004D458[0][v128] );
        std::wstring::_Construct<1,wchar_t const *>(&v170, off_18004D458[0], v128);
        v172 = 1;
        v173 = 0;
        v174 = 0;
        v175 = 0;
        v176 = 67;
        std::wstring::wstring((__int64)v177, (__int64)&v170);
        v178 = v172;
        std::_Tree<std::_Tmap_traits<enum tagEnterprisePolicy,AllowInfo,std::less<enum tagEnterprisePolicy>,std::allocator<std::pair<enum tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(
          v129,
          (__int64)v168,
          (__int64)&v176);
        std::wstring::~wstring(v177);
        std::wstring::~wstring(&v170);
        v170 = 0;
        v171 = 0;
        v130 = -1;
        do
          ++v130;
        while ( off_18004D4D0[0][v130] );
        std::wstring::_Construct<1,wchar_t const *>(&v170, off_18004D4D0[0], v130);
        v172 = 1;
        v173 = 0;
        v174 = 0;
        v175 = 0;
        v176 = 68;
        std::wstring::wstring((__int64)v177, (__int64)&v170);
        v178 = v172;
        std::_Tree<std::_Tmap_traits<enum tagEnterprisePolicy,AllowInfo,std::less<enum tagEnterprisePolicy>,std::allocator<std::pair<enum tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(
          v131,
          (__int64)v168,
          (__int64)&v176);
        std::wstring::~wstring(v177);
        std::wstring::~wstring(&v170);
        v170 = 0;
        v171 = 0;
        v132 = -1;
        do
          ++v132;
        while ( off_18004D548[0][v132] );
        std::wstring::_Construct<1,wchar_t const *>(&v170, off_18004D548[0], v132);
        v172 = 1;
        v173 = 0;
        v174 = 0;
        v175 = 0;
        v176 = 69;
        std::wstring::wstring((__int64)v177, (__int64)&v170);
        v178 = v172;
        std::_Tree<std::_Tmap_traits<enum tagEnterprisePolicy,AllowInfo,std::less<enum tagEnterprisePolicy>,std::allocator<std::pair<enum tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(
          v133,
          (__int64)v168,
          (__int64)&v176);
        std::wstring::~wstring(v177);
        std::wstring::~wstring(&v170);
        v170 = 0;
        v171 = 0;
        v134 = -1;
        do
          ++v134;
        while ( off_18004D5C0[0][v134] );
        std::wstring::_Construct<1,wchar_t const *>(&v170, off_18004D5C0[0], v134);
        v172 = 1;
        v173 = 0;
        v174 = 0;
        v175 = 0;
        v176 = 70;
        std::wstring::wstring((__int64)v177, (__int64)&v170);
        v178 = v172;
        std::_Tree<std::_Tmap_traits<enum tagEnterprisePolicy,AllowInfo,std::less<enum tagEnterprisePolicy>,std::allocator<std::pair<enum tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(
          v135,
          (__int64)v168,
          (__int64)&v176);
        std::wstring::~wstring(v177);
        std::wstring::~wstring(&v170);
        v179 = 71;
        v170 = 0;
        v171 = 0;
        v136 = -1;
        do
          ++v136;
        while ( off_18004D638[0][v136] );
        std::wstring::_Construct<1,wchar_t const *>(&v170, off_18004D638[0], v136);
        v172 = 1;
        v173 = 0;
        v174 = 0;
        v175 = 0;
        std::pair<enum tagEnterprisePolicy const,AllowInfo>::pair<enum tagEnterprisePolicy const,AllowInfo>(
          (__int64)&v176,
          &v179,
          (__int64)&v170);
        std::_Tree<std::_Tmap_traits<enum tagEnterprisePolicy,AllowInfo,std::less<enum tagEnterprisePolicy>,std::allocator<std::pair<enum tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(
          v137,
          (__int64)v168,
          (__int64)&v176);
        std::wstring::~wstring(v177);
        std::wstring::~wstring(&v170);
        v179 = 72;
        v170 = 0;
        v171 = 0;
        v138 = -1;
        do
          ++v138;
        while ( off_18004D6B0[0][v138] );
        std::wstring::_Construct<1,wchar_t const *>(&v170, off_18004D6B0[0], v138);
        v172 = 1;
        v173 = 0;
        v174 = 0;
        v175 = 0;
        std::pair<enum tagEnterprisePolicy const,AllowInfo>::pair<enum tagEnterprisePolicy const,AllowInfo>(
          (__int64)&v176,
          &v179,
          (__int64)&v170);
        std::_Tree<std::_Tmap_traits<enum tagEnterprisePolicy,AllowInfo,std::less<enum tagEnterprisePolicy>,std::allocator<std::pair<enum tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(
          v139,
          (__int64)v168,
          (__int64)&v176);
        std::wstring::~wstring(v177);
        std::wstring::~wstring(&v170);
        v179 = 73;
        v170 = 0;
        v171 = 0;
        v140 = -1;
        do
          ++v140;
        while ( off_18004D728[0][v140] );
        std::wstring::_Construct<1,wchar_t const *>(&v170, off_18004D728[0], v140);
        v172 = 1;
        v173 = 0;
        v174 = 0;
        v175 = 0;
        std::pair<enum tagEnterprisePolicy const,AllowInfo>::pair<enum tagEnterprisePolicy const,AllowInfo>(
          (__int64)&v176,
          &v179,
          (__int64)&v170);
        std::_Tree<std::_Tmap_traits<enum tagEnterprisePolicy,AllowInfo,std::less<enum tagEnterprisePolicy>,std::allocator<std::pair<enum tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(
          v141,
          (__int64)v168,
          (__int64)&v176);
        std::wstring::~wstring(v177);
        std::wstring::~wstring(&v170);
        v179 = 74;
        v170 = 0;
        v171 = 0;
        v142 = -1;
        do
          ++v142;
        while ( off_18004D7A0[0][v142] );
        std::wstring::_Construct<1,wchar_t const *>(&v170, off_18004D7A0[0], v142);
        v172 = 1;
        v173 = 0;
        v174 = 0;
        v175 = 0;
        std::pair<enum tagEnterprisePolicy const,AllowInfo>::pair<enum tagEnterprisePolicy const,AllowInfo>(
          (__int64)&v176,
          &v179,
          (__int64)&v170);
        std::_Tree<std::_Tmap_traits<enum tagEnterprisePolicy,AllowInfo,std::less<enum tagEnterprisePolicy>,std::allocator<std::pair<enum tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(
          v143,
          (__int64)v168,
          (__int64)&v176);
        std::wstring::~wstring(v177);
        std::wstring::~wstring(&v170);
        v179 = 75;
        v170 = 0;
        v171 = 0;
        v144 = -1;
        do
          ++v144;
        while ( off_18004D818[0][v144] );
        std::wstring::_Construct<1,wchar_t const *>(&v170, off_18004D818[0], v144);
        v172 = 1;
        v173 = 0;
        v174 = 0;
        v175 = 0;
        std::pair<enum tagEnterprisePolicy const,AllowInfo>::pair<enum tagEnterprisePolicy const,AllowInfo>(
          (__int64)&v176,
          &v179,
          (__int64)&v170);
        std::_Tree<std::_Tmap_traits<enum tagEnterprisePolicy,AllowInfo,std::less<enum tagEnterprisePolicy>,std::allocator<std::pair<enum tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(
          v145,
          (__int64)v168,
          (__int64)&v176);
        std::wstring::~wstring(v177);
        std::wstring::~wstring(&v170);
        v179 = 76;
        v170 = 0;
        v171 = 0;
        v146 = -1;
        do
          ++v146;
        while ( off_18004D890[0][v146] );
        std::wstring::_Construct<1,wchar_t const *>(&v170, off_18004D890[0], v146);
        v172 = 1;
        v173 = 0;
        v174 = 0;
        v175 = 0;
        std::pair<enum tagEnterprisePolicy const,AllowInfo>::pair<enum tagEnterprisePolicy const,AllowInfo>(
          (__int64)&v176,
          &v179,
          (__int64)&v170);
        std::_Tree<std::_Tmap_traits<enum tagEnterprisePolicy,AllowInfo,std::less<enum tagEnterprisePolicy>,std::allocator<std::pair<enum tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(
          v147,
          (__int64)v168,
          (__int64)&v176);
        std::wstring::~wstring(v177);
        std::wstring::~wstring(&v170);
        v179 = 77;
        v170 = 0;
        v171 = 0;
        v148 = -1;
        do
          ++v148;
        while ( off_18004D908[0][v148] );
        std::wstring::_Construct<1,wchar_t const *>(&v170, off_18004D908[0], v148);
        v172 = 1;
        v173 = 0;
        v174 = 0;
        v175 = 0;
        std::pair<enum tagEnterprisePolicy const,AllowInfo>::pair<enum tagEnterprisePolicy const,AllowInfo>(
          (__int64)&v176,
          &v179,
          (__int64)&v170);
        std::_Tree<std::_Tmap_traits<enum tagEnterprisePolicy,AllowInfo,std::less<enum tagEnterprisePolicy>,std::allocator<std::pair<enum tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(
          v149,
          (__int64)v168,
          (__int64)&v176);
        std::wstring::~wstring(v177);
        std::wstring::~wstring(&v170);
        v179 = 78;
        v170 = 0;
        v171 = 0;
        v150 = -1;
        do
          ++v150;
        while ( off_18004D980[0][v150] );
        std::wstring::_Construct<1,wchar_t const *>(&v170, off_18004D980[0], v150);
        v172 = 1;
        v173 = 0;
        v174 = 0;
        v175 = 0;
        std::pair<enum tagEnterprisePolicy const,AllowInfo>::pair<enum tagEnterprisePolicy const,AllowInfo>(
          (__int64)&v176,
          &v179,
          (__int64)&v170);
        std::_Tree<std::_Tmap_traits<enum tagEnterprisePolicy,AllowInfo,std::less<enum tagEnterprisePolicy>,std::allocator<std::pair<enum tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(
          v151,
          (__int64)v168,
          (__int64)&v176);
        std::wstring::~wstring(v177);
        std::wstring::~wstring(&v170);
        v179 = 79;
        v170 = 0;
        v171 = 0;
        v152 = -1;
        do
          ++v152;
        while ( off_18004D9F8[0][v152] );
        std::wstring::_Construct<1,wchar_t const *>(&v170, off_18004D9F8[0], v152);
        v172 = 1;
        v173 = 0;
        v174 = 0;
        v175 = 0;
        std::pair<enum tagEnterprisePolicy const,AllowInfo>::pair<enum tagEnterprisePolicy const,AllowInfo>(
          (__int64)&v176,
          &v179,
          (__int64)&v170);
        std::_Tree<std::_Tmap_traits<enum tagEnterprisePolicy,AllowInfo,std::less<enum tagEnterprisePolicy>,std::allocator<std::pair<enum tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(
          v153,
          (__int64)v168,
          (__int64)&v176);
        std::wstring::~wstring(v177);
        std::wstring::~wstring(&v170);
        v179 = 80;
        v170 = 0;
        v171 = 0;
        v154 = -1;
        do
          ++v154;
        while ( off_18004DA70[0][v154] );
        std::wstring::_Construct<1,wchar_t const *>(&v170, off_18004DA70[0], v154);
        v172 = 1;
        v173 = 0;
        v174 = 0;
        v175 = 0;
        std::pair<enum tagEnterprisePolicy const,AllowInfo>::pair<enum tagEnterprisePolicy const,AllowInfo>(
          (__int64)&v176,
          &v179,
          (__int64)&v170);
        std::_Tree<std::_Tmap_traits<enum tagEnterprisePolicy,AllowInfo,std::less<enum tagEnterprisePolicy>,std::allocator<std::pair<enum tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(
          v155,
          (__int64)v168,
          (__int64)&v176);
        std::wstring::~wstring(v177);
        std::wstring::~wstring(&v170);
        v179 = 81;
        v170 = 0;
        v171 = 0;
        v156 = -1;
        do
          ++v156;
        while ( off_18004DAE8[0][v156] );
        std::wstring::_Construct<1,wchar_t const *>(&v170, off_18004DAE8[0], v156);
        v172 = 1;
        v173 = 0;
        v174 = 0;
        v175 = 0;
        std::pair<enum tagEnterprisePolicy const,AllowInfo>::pair<enum tagEnterprisePolicy const,AllowInfo>(
          (__int64)&v176,
          &v179,
          (__int64)&v170);
        std::_Tree<std::_Tmap_traits<enum tagEnterprisePolicy,AllowInfo,std::less<enum tagEnterprisePolicy>,std::allocator<std::pair<enum tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(
          v157,
          (__int64)v168,
          (__int64)&v176);
        std::wstring::~wstring(v177);
        std::wstring::~wstring(&v170);
        v179 = 82;
        v170 = 0;
        v171 = 0;
        v158 = -1;
        do
          ++v158;
        while ( off_18004DB60[0][v158] );
        std::wstring::_Construct<1,wchar_t const *>(&v170, off_18004DB60[0], v158);
        v172 = 1;
        v173 = 0;
        v174 = 0;
        v175 = 0;
        std::pair<enum tagEnterprisePolicy const,AllowInfo>::pair<enum tagEnterprisePolicy const,AllowInfo>(
          (__int64)&v176,
          &v179,
          (__int64)&v170);
        std::_Tree<std::_Tmap_traits<enum tagEnterprisePolicy,AllowInfo,std::less<enum tagEnterprisePolicy>,std::allocator<std::pair<enum tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(
          v159,
          (__int64)v168,
          (__int64)&v176);
        std::wstring::~wstring(v177);
        std::wstring::~wstring(&v170);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_MaintenanceWindow_RepeatIntervals>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_MaintenanceWindow_RepeatIntervals>::GetImpl'::`2'::impl) )
        {
          v179 = 83;
          v170 = 0;
          v171 = 0;
          v160 = -1;
          do
            ++v160;
          while ( off_18004DBD8[0][v160] );
          std::wstring::_Construct<1,wchar_t const *>(&v170, off_18004DBD8[0], v160);
          v172 = 1;
          v173 = 0;
          v174 = 0;
          v175 = 0;
          std::pair<enum tagEnterprisePolicy const,AllowInfo>::pair<enum tagEnterprisePolicy const,AllowInfo>(
            (__int64)&v176,
            &v179,
            (__int64)&v170);
          std::_Tree<std::_Tmap_traits<enum tagEnterprisePolicy,AllowInfo,std::less<enum tagEnterprisePolicy>,std::allocator<std::pair<enum tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(
            v161,
            (__int64)v168,
            (__int64)&v176);
          std::wstring::~wstring(v177);
          std::wstring::~wstring(&v170);
          v179 = 84;
          v170 = 0;
          v171 = 0;
          v162 = -1;
          do
            ++v162;
          while ( off_18004DC50[0][v162] );
          std::wstring::_Construct<1,wchar_t const *>(&v170, off_18004DC50[0], v162);
          v172 = 1;
          v173 = 0;
          v174 = 0;
          v175 = 0;
          std::pair<enum tagEnterprisePolicy const,AllowInfo>::pair<enum tagEnterprisePolicy const,AllowInfo>(
            (__int64)&v176,
            &v179,
            (__int64)&v170);
          std::_Tree<std::_Tmap_traits<enum tagEnterprisePolicy,AllowInfo,std::less<enum tagEnterprisePolicy>,std::allocator<std::pair<enum tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(
            v163,
            (__int64)v168,
            (__int64)&v176);
          std::wstring::~wstring(v177);
          std::wstring::~wstring(&v170);
          v179 = 85;
          v170 = 0;
          v171 = 0;
          do
            ++v3;
          while ( off_18004DCC8[0][v3] );
          std::wstring::_Construct<1,wchar_t const *>(&v170, off_18004DCC8[0], v3);
          v172 = 1;
          v173 = 0;
          v174 = 0;
          v175 = 0;
          std::pair<enum tagEnterprisePolicy const,AllowInfo>::pair<enum tagEnterprisePolicy const,AllowInfo>(
            (__int64)&v176,
            &v179,
            (__int64)&v170);
          std::_Tree<std::_Tmap_traits<enum tagEnterprisePolicy,AllowInfo,std::less<enum tagEnterprisePolicy>,std::allocator<std::pair<enum tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(
            v164,
            (__int64)v168,
            (__int64)&v176);
          std::wstring::~wstring(v177);
          std::wstring::~wstring(&v170);
        }
      }
      PolicyAllowList<enum tagEnterprisePolicy>::Populate();
    }
    _InterlockedExchange(&dword_18004EDA8, 0);
  }
  if ( !HIBYTE(word_18004EF30) )
  {
    v165 = *(_QWORD *)(qword_18004EF38 + 8);
    v169 = 0;
    v166 = qword_18004EF38;
    while ( !*(_BYTE *)(v165 + 25) )
    {
      if ( *(_DWORD *)(v165 + 32) >= a1 )
        v166 = v165;
      else
        v165 += 16;
      v165 = *(_QWORD *)v165;
    }
    if ( *(_BYTE *)(v166 + 25) || a1 < *(_DWORD *)(v166 + 32) )
      v166 = qword_18004EF38;
    if ( qword_18004EF38 == v166 )
      return 0;
    else
      return *(unsigned __int8 *)(v166 + 72);
  }
  return v2;
}

```

## disassembly

```asm
0x180012340  mov     [rsp-8+arg_8], rbx
0x180012345  mov     [rsp-8+arg_10], rsi
0x18001234a  push    rbp
0x18001234b  push    rdi
0x18001234c  push    r14
0x18001234e  lea     rbp, [rsp-47h]
0x180012353  sub     rsp, 90h
0x18001235a  mov     esi, ecx
0x18001235c  mov     ebx, 1
0x180012361  xor     r14d, r14d
0x180012364  cmp     byte ptr cs:word_18004EF30, r14b
0x18001236b  jnz     loc_18001493F
0x180012371  xor     eax, eax
0x180012373  lock cmpxchg cs:dword_18004EDA8, ebx
0x18001237b  cmp     eax, ebx
0x18001237d  jnz     short loc_1800123A7
0x18001237f  jmp     short loc_18001238C
0x180012381  mov     ecx, 64h ; 'd'; dwMilliseconds
0x180012386  call    cs:__imp_Sleep
0x18001238c  xor     eax, eax
0x18001238e  lock cmpxchg cs:dword_18004EDA8, ebx
0x180012396  cmp     eax, ebx
0x180012398  jz      short loc_180012381
0x18001239a  cmp     byte ptr cs:word_18004EF30, r14b
0x1800123a1  jnz     loc_180014936
0x1800123a7  lea     rcx, OutputString; "Populating EnterprisePolicy AllowList"
0x1800123ae  call    cs:__imp_OutputDebugStringW
0x1800123b4  xorps   xmm0, xmm0
0x1800123b7  movups  [rbp+57h+var_68], xmm0
0x1800123bb  xorps   xmm1, xmm1
0x1800123be  movdqu  [rbp+57h+var_58], xmm1
0x1800123c3  mov     rdx, cs:off_18004B568; "RequireDeferUpgrade"
0x1800123ca  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800123ce  mov     r8, rdi
0x1800123d1  inc     r8
0x1800123d4  cmp     [rdx+r8*2], r14w
0x1800123d9  jnz     short loc_1800123D1
0x1800123db  lea     rcx, [rbp+57h+var_68]
0x1800123df  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800123e4  mov     [rbp+57h+var_48], bl
0x1800123e7  xor     eax, eax
0x1800123e9  mov     [rbp+57h+var_47], eax
0x1800123ec  mov     [rbp+57h+var_43], ax
0x1800123f0  mov     [rbp+57h+var_41], al
0x1800123f3  mov     [rbp+57h+var_40], ebx
0x1800123f6  lea     rdx, [rbp+57h+var_68]
0x1800123fa  lea     rcx, [rbp+57h+var_38]
0x1800123fe  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180012403  mov     al, [rbp+57h+var_48]
0x180012406  mov     [rbp+57h+var_18], al
0x180012409  lea     r8, [rbp+57h+var_40]
0x18001240d  lea     rdx, [rbp+57h+var_80]
0x180012411  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tmap_traits@W4tagEnterprisePolicy@@UAllowInfo@@U?$less@W4tagEnterprisePolicy@@@std@@V?$allocator@U?$pair@$$CBW4tagEnterprisePolicy@@UAllowInfo@@@std@@@4@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4tagEnterprisePolicy@@UAllowInfo@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@$$CBW4tagEnterprisePolicy@@UAllowInfo@@@1@@Z; std::_Tree<std::_Tmap_traits<tagEnterprisePolicy,AllowInfo,std::less<tagEnterprisePolicy>,std::allocator<std::pair<tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(std::pair<tagEnterprisePolicy const,AllowInfo> &&)
0x180012416  nop
0x180012417  lea     rcx, [rbp+57h+var_38]; void *
0x18001241b  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180012420  nop
0x180012421  lea     rcx, [rbp+57h+var_68]; void *
0x180012425  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001242a  xorps   xmm0, xmm0
0x18001242d  movups  [rbp+57h+var_68], xmm0
0x180012431  xorps   xmm1, xmm1
0x180012434  movdqu  [rbp+57h+var_58], xmm1
0x180012439  mov     rdx, cs:off_18004B5E0; "DeferUpgradePeriod"
0x180012440  mov     r8, rdi
0x180012443  inc     r8
0x180012446  cmp     [rdx+r8*2], r14w
0x18001244b  jnz     short loc_180012443
0x18001244d  lea     rcx, [rbp+57h+var_68]
0x180012451  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180012456  mov     [rbp+57h+var_48], bl
0x180012459  xor     eax, eax
0x18001245b  mov     [rbp+57h+var_47], eax
0x18001245e  mov     [rbp+57h+var_43], ax
0x180012462  mov     [rbp+57h+var_41], al
0x180012465  mov     [rbp+57h+var_40], 2
0x18001246c  lea     rdx, [rbp+57h+var_68]
0x180012470  lea     rcx, [rbp+57h+var_38]
0x180012474  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180012479  mov     al, [rbp+57h+var_48]
0x18001247c  mov     [rbp+57h+var_18], al
0x18001247f  lea     r8, [rbp+57h+var_40]
0x180012483  lea     rdx, [rbp+57h+var_80]
0x180012487  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tmap_traits@W4tagEnterprisePolicy@@UAllowInfo@@U?$less@W4tagEnterprisePolicy@@@std@@V?$allocator@U?$pair@$$CBW4tagEnterprisePolicy@@UAllowInfo@@@std@@@4@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4tagEnterprisePolicy@@UAllowInfo@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@$$CBW4tagEnterprisePolicy@@UAllowInfo@@@1@@Z; std::_Tree<std::_Tmap_traits<tagEnterprisePolicy,AllowInfo,std::less<tagEnterprisePolicy>,std::allocator<std::pair<tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(std::pair<tagEnterprisePolicy const,AllowInfo> &&)
0x18001248c  nop
0x18001248d  lea     rcx, [rbp+57h+var_38]; void *
0x180012491  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180012496  nop
0x180012497  lea     rcx, [rbp+57h+var_68]; void *
0x18001249b  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800124a0  xorps   xmm0, xmm0
0x1800124a3  movups  [rbp+57h+var_68], xmm0
0x1800124a7  xorps   xmm1, xmm1
0x1800124aa  movdqu  [rbp+57h+var_58], xmm1
0x1800124af  mov     rdx, cs:off_18004B658; "DeferUpdatePeriod"
0x1800124b6  mov     r8, rdi
0x1800124b9  inc     r8
0x1800124bc  cmp     [rdx+r8*2], r14w
0x1800124c1  jnz     short loc_1800124B9
0x1800124c3  lea     rcx, [rbp+57h+var_68]
0x1800124c7  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800124cc  mov     [rbp+57h+var_48], bl
0x1800124cf  xor     eax, eax
0x1800124d1  mov     [rbp+57h+var_47], eax
0x1800124d4  mov     [rbp+57h+var_43], ax
0x1800124d8  mov     [rbp+57h+var_41], al
0x1800124db  mov     [rbp+57h+var_40], 3
0x1800124e2  lea     rdx, [rbp+57h+var_68]
0x1800124e6  lea     rcx, [rbp+57h+var_38]
0x1800124ea  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800124ef  mov     al, [rbp+57h+var_48]
0x1800124f2  mov     [rbp+57h+var_18], al
0x1800124f5  lea     r8, [rbp+57h+var_40]
0x1800124f9  lea     rdx, [rbp+57h+var_80]
0x1800124fd  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tmap_traits@W4tagEnterprisePolicy@@UAllowInfo@@U?$less@W4tagEnterprisePolicy@@@std@@V?$allocator@U?$pair@$$CBW4tagEnterprisePolicy@@UAllowInfo@@@std@@@4@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4tagEnterprisePolicy@@UAllowInfo@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@$$CBW4tagEnterprisePolicy@@UAllowInfo@@@1@@Z; std::_Tree<std::_Tmap_traits<tagEnterprisePolicy,AllowInfo,std::less<tagEnterprisePolicy>,std::allocator<std::pair<tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(std::pair<tagEnterprisePolicy const,AllowInfo> &&)
0x180012502  nop
0x180012503  lea     rcx, [rbp+57h+var_38]; void *
0x180012507  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001250c  nop
0x18001250d  lea     rcx, [rbp+57h+var_68]; void *
0x180012511  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180012516  xorps   xmm0, xmm0
0x180012519  movups  [rbp+57h+var_68], xmm0
0x18001251d  xorps   xmm1, xmm1
0x180012520  movdqu  [rbp+57h+var_58], xmm1
0x180012525  mov     rdx, cs:off_18004B6D0; "PauseDeferrals"
0x18001252c  mov     r8, rdi
0x18001252f  inc     r8
0x180012532  cmp     [rdx+r8*2], r14w
0x180012537  jnz     short loc_18001252F
0x180012539  lea     rcx, [rbp+57h+var_68]
0x18001253d  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180012542  mov     [rbp+57h+var_48], bl
0x180012545  xor     eax, eax
0x180012547  mov     [rbp+57h+var_47], eax
0x18001254a  mov     [rbp+57h+var_43], ax
0x18001254e  mov     [rbp+57h+var_41], al
0x180012551  mov     [rbp+57h+var_40], 4
0x180012558  lea     rdx, [rbp+57h+var_68]
0x18001255c  lea     rcx, [rbp+57h+var_38]
0x180012560  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180012565  mov     al, [rbp+57h+var_48]
0x180012568  mov     [rbp+57h+var_18], al
0x18001256b  lea     r8, [rbp+57h+var_40]
0x18001256f  lea     rdx, [rbp+57h+var_80]
0x180012573  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tmap_traits@W4tagEnterprisePolicy@@UAllowInfo@@U?$less@W4tagEnterprisePolicy@@@std@@V?$allocator@U?$pair@$$CBW4tagEnterprisePolicy@@UAllowInfo@@@std@@@4@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4tagEnterprisePolicy@@UAllowInfo@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@$$CBW4tagEnterprisePolicy@@UAllowInfo@@@1@@Z; std::_Tree<std::_Tmap_traits<tagEnterprisePolicy,AllowInfo,std::less<tagEnterprisePolicy>,std::allocator<std::pair<tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(std::pair<tagEnterprisePolicy const,AllowInfo> &&)
0x180012578  nop
0x180012579  lea     rcx, [rbp+57h+var_38]; void *
0x18001257d  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180012582  nop
0x180012583  lea     rcx, [rbp+57h+var_68]; void *
0x180012587  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001258c  xorps   xmm0, xmm0
0x18001258f  movups  [rbp+57h+var_68], xmm0
0x180012593  xorps   xmm1, xmm1
0x180012596  movdqu  [rbp+57h+var_58], xmm1
0x18001259b  mov     rdx, cs:off_18004B748; "BranchReadinessLevel"
0x1800125a2  mov     r8, rdi
0x1800125a5  inc     r8
0x1800125a8  cmp     [rdx+r8*2], r14w
0x1800125ad  jnz     short loc_1800125A5
0x1800125af  lea     rcx, [rbp+57h+var_68]
0x1800125b3  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800125b8  mov     [rbp+57h+var_48], bl
0x1800125bb  xor     eax, eax
0x1800125bd  mov     [rbp+57h+var_47], eax
0x1800125c0  mov     [rbp+57h+var_43], ax
0x1800125c4  mov     [rbp+57h+var_41], al
0x1800125c7  mov     [rbp+57h+var_40], 5
0x1800125ce  lea     rdx, [rbp+57h+var_68]
0x1800125d2  lea     rcx, [rbp+57h+var_38]
0x1800125d6  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800125db  mov     al, [rbp+57h+var_48]
0x1800125de  mov     [rbp+57h+var_18], al
0x1800125e1  lea     r8, [rbp+57h+var_40]
0x1800125e5  lea     rdx, [rbp+57h+var_80]
0x1800125e9  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tmap_traits@W4tagEnterprisePolicy@@UAllowInfo@@U?$less@W4tagEnterprisePolicy@@@std@@V?$allocator@U?$pair@$$CBW4tagEnterprisePolicy@@UAllowInfo@@@std@@@4@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4tagEnterprisePolicy@@UAllowInfo@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@$$CBW4tagEnterprisePolicy@@UAllowInfo@@@1@@Z; std::_Tree<std::_Tmap_traits<tagEnterprisePolicy,AllowInfo,std::less<tagEnterprisePolicy>,std::allocator<std::pair<tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(std::pair<tagEnterprisePolicy const,AllowInfo> &&)
0x1800125ee  nop
0x1800125ef  lea     rcx, [rbp+57h+var_38]; void *
0x1800125f3  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800125f8  nop
0x1800125f9  lea     rcx, [rbp+57h+var_68]; void *
0x1800125fd  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180012602  xorps   xmm0, xmm0
0x180012605  movups  [rbp+57h+var_68], xmm0
0x180012609  xorps   xmm1, xmm1
0x18001260c  movdqu  [rbp+57h+var_58], xmm1
0x180012611  mov     rdx, cs:off_18004B7C0; "DeferQualityUpdates"
0x180012618  mov     r8, rdi
0x18001261b  inc     r8
0x18001261e  cmp     [rdx+r8*2], r14w
0x180012623  jnz     short loc_18001261B
0x180012625  lea     rcx, [rbp+57h+var_68]
0x180012629  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18001262e  mov     [rbp+57h+var_48], bl
0x180012631  xor     eax, eax
0x180012633  mov     [rbp+57h+var_47], eax
0x180012636  mov     [rbp+57h+var_43], ax
0x18001263a  mov     [rbp+57h+var_41], al
0x18001263d  mov     [rbp+57h+var_40], 6
0x180012644  lea     rdx, [rbp+57h+var_68]
0x180012648  lea     rcx, [rbp+57h+var_38]
0x18001264c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180012651  mov     al, [rbp+57h+var_48]
0x180012654  mov     [rbp+57h+var_18], al
0x180012657  lea     r8, [rbp+57h+var_40]
0x18001265b  lea     rdx, [rbp+57h+var_80]
0x18001265f  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tmap_traits@W4tagEnterprisePolicy@@UAllowInfo@@U?$less@W4tagEnterprisePolicy@@@std@@V?$allocator@U?$pair@$$CBW4tagEnterprisePolicy@@UAllowInfo@@@std@@@4@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4tagEnterprisePolicy@@UAllowInfo@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@$$CBW4tagEnterprisePolicy@@UAllowInfo@@@1@@Z; std::_Tree<std::_Tmap_traits<tagEnterprisePolicy,AllowInfo,std::less<tagEnterprisePolicy>,std::allocator<std::pair<tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(std::pair<tagEnterprisePolicy const,AllowInfo> &&)
0x180012664  nop
0x180012665  lea     rcx, [rbp+57h+var_38]; void *
0x180012669  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001266e  nop
0x18001266f  lea     rcx, [rbp+57h+var_68]; void *
0x180012673  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180012678  xorps   xmm0, xmm0
0x18001267b  movups  [rbp+57h+var_68], xmm0
0x18001267f  xorps   xmm1, xmm1
0x180012682  movdqu  [rbp+57h+var_58], xmm1
0x180012687  mov     rdx, cs:off_18004B838; "DeferQualityUpdatesPeriodInDays"
0x18001268e  mov     r8, rdi
0x180012691  inc     r8
0x180012694  cmp     [rdx+r8*2], r14w
0x180012699  jnz     short loc_180012691
0x18001269b  lea     rcx, [rbp+57h+var_68]
0x18001269f  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800126a4  mov     [rbp+57h+var_48], bl
0x1800126a7  xor     eax, eax
0x1800126a9  mov     [rbp+57h+var_47], eax
0x1800126ac  mov     [rbp+57h+var_43], ax
0x1800126b0  mov     [rbp+57h+var_41], al
0x1800126b3  mov     [rbp+57h+var_40], 7
0x1800126ba  lea     rdx, [rbp+57h+var_68]
0x1800126be  lea     rcx, [rbp+57h+var_38]
0x1800126c2  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800126c7  mov     al, [rbp+57h+var_48]
0x1800126ca  mov     [rbp+57h+var_18], al
0x1800126cd  lea     r8, [rbp+57h+var_40]
0x1800126d1  lea     rdx, [rbp+57h+var_80]
0x1800126d5  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tmap_traits@W4tagEnterprisePolicy@@UAllowInfo@@U?$less@W4tagEnterprisePolicy@@@std@@V?$allocator@U?$pair@$$CBW4tagEnterprisePolicy@@UAllowInfo@@@std@@@4@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4tagEnterprisePolicy@@UAllowInfo@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@$$CBW4tagEnterprisePolicy@@UAllowInfo@@@1@@Z; std::_Tree<std::_Tmap_traits<tagEnterprisePolicy,AllowInfo,std::less<tagEnterprisePolicy>,std::allocator<std::pair<tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(std::pair<tagEnterprisePolicy const,AllowInfo> &&)
0x1800126da  nop
0x1800126db  lea     rcx, [rbp+57h+var_38]; void *
0x1800126df  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800126e4  nop
0x1800126e5  lea     rcx, [rbp+57h+var_68]; void *
0x1800126e9  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800126ee  xorps   xmm0, xmm0
0x1800126f1  movups  [rbp+57h+var_68], xmm0
0x1800126f5  xorps   xmm1, xmm1
0x1800126f8  movdqu  [rbp+57h+var_58], xmm1
0x1800126fd  mov     rdx, cs:off_18004B8B0; "DeferFeatureUpdates"
0x180012704  mov     r8, rdi
0x180012707  inc     r8
0x18001270a  cmp     [rdx+r8*2], r14w
0x18001270f  jnz     short loc_180012707
0x180012711  lea     rcx, [rbp+57h+var_68]
0x180012715  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18001271a  mov     [rbp+57h+var_48], bl
0x18001271d  xor     eax, eax
0x18001271f  mov     [rbp+57h+var_47], eax
0x180012722  mov     [rbp+57h+var_43], ax
0x180012726  mov     [rbp+57h+var_41], al
0x180012729  mov     [rbp+57h+var_40], 8
0x180012730  lea     rdx, [rbp+57h+var_68]
0x180012734  lea     rcx, [rbp+57h+var_38]
0x180012738  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001273d  mov     al, [rbp+57h+var_48]
0x180012740  mov     [rbp+57h+var_18], al
0x180012743  lea     r8, [rbp+57h+var_40]
0x180012747  lea     rdx, [rbp+57h+var_80]
0x18001274b  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tmap_traits@W4tagEnterprisePolicy@@UAllowInfo@@U?$less@W4tagEnterprisePolicy@@@std@@V?$allocator@U?$pair@$$CBW4tagEnterprisePolicy@@UAllowInfo@@@std@@@4@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4tagEnterprisePolicy@@UAllowInfo@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@$$CBW4tagEnterprisePolicy@@UAllowInfo@@@1@@Z; std::_Tree<std::_Tmap_traits<tagEnterprisePolicy,AllowInfo,std::less<tagEnterprisePolicy>,std::allocator<std::pair<tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(std::pair<tagEnterprisePolicy const,AllowInfo> &&)
0x180012750  nop
0x180012751  lea     rcx, [rbp+57h+var_38]; void *
0x180012755  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001275a  nop
0x18001275b  lea     rcx, [rbp+57h+var_68]; void *
0x18001275f  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180012764  xorps   xmm0, xmm0
0x180012767  movups  [rbp+57h+var_68], xmm0
0x18001276b  xorps   xmm1, xmm1
0x18001276e  movdqu  [rbp+57h+var_58], xmm1
0x180012773  mov     rdx, cs:off_18004B928; "DeferFeatureUpdatesPeriodInDays"
0x18001277a  mov     r8, rdi
0x18001277d  inc     r8
0x180012780  cmp     [rdx+r8*2], r14w
0x180012785  jnz     short loc_18001277D
0x180012787  lea     rcx, [rbp+57h+var_68]
0x18001278b  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180012790  mov     [rbp+57h+var_48], bl
0x180012793  xor     eax, eax
0x180012795  mov     [rbp+57h+var_47], eax
0x180012798  mov     [rbp+57h+var_43], ax
0x18001279c  mov     [rbp+57h+var_41], al
0x18001279f  mov     [rbp+57h+var_40], 9
0x1800127a6  lea     rdx, [rbp+57h+var_68]
0x1800127aa  lea     rcx, [rbp+57h+var_38]
0x1800127ae  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800127b3  mov     al, [rbp+57h+var_48]
0x1800127b6  mov     [rbp+57h+var_18], al
0x1800127b9  lea     r8, [rbp+57h+var_40]
0x1800127bd  lea     rdx, [rbp+57h+var_80]
  ... truncated ...
```
