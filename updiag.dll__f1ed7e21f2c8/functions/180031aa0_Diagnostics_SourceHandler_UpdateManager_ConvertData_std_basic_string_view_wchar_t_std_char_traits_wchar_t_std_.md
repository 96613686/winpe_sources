# Diagnostics::SourceHandler_UpdateManager::ConvertData(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,std::filesystem::path const &,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>)

- ea: `0x180031aa0`
- end: `0x1800339a6`
- name: `?ConvertData@SourceHandler_UpdateManager@Diagnostics@@UEAAIV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEBVpath@filesystem@4@0@Z`
- size: `7942`
- prototype: ``
- caller_count: `0`
- callee_count: `22`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180015ac8`
- `0x180018eec`
- `0x180019080`
- `0x18001adcc`
- `0x180029a58`
- `0x180029ae0`
- `0x18002a018`
- `0x18002a204`
- `0x18002d4ac`
- `0x18002d73c`
- `0x18002d990`
- `0x18002da90`
- `0x180031aa0`
- `0x1800667c0`
- `0x180066844`
- `0x180068d68`
- `0x180068de8`
- `0x1800691dc`
- `0x180069224`
- `0x18008fe00`
- `0x180096170`
- `0x1800961f0`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180033741`
- `OLEAUT32!__imp_SysFreeString` at `0x180033785`
- `OLEAUT32!__imp_SysFreeString` at `0x180033799`
- `OLEAUT32!__imp_SysFreeString` at `0x1800337ad`
- `OLEAUT32!__imp_SysFreeString` at `0x1800337d0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800337e4`
- `OLEAUT32!__imp_SysFreeString` at `0x1800337f8`
- `OLEAUT32!__imp_SysFreeString` at `0x18003385b`
- `OLEAUT32!__imp_SysFreeString` at `0x18003386f`
- `OLEAUT32!__imp_SysFreeString` at `0x180033883`
- `OLEAUT32!__imp_SysFreeString` at `0x1800338a6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800338ba`
- `OLEAUT32!__imp_SysFreeString` at `0x1800338ce`
- `OLEAUT32!__imp_SysFreeString` at `0x180033741`
- `OLEAUT32!__imp_SysFreeString` at `0x180033785`
- `OLEAUT32!__imp_SysFreeString` at `0x180033799`
- `OLEAUT32!__imp_SysFreeString` at `0x1800337ad`
- `OLEAUT32!__imp_SysFreeString` at `0x1800337d0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800337e4`
- `OLEAUT32!__imp_SysFreeString` at `0x1800337f8`
- `OLEAUT32!__imp_SysFreeString` at `0x18003385b`
- `OLEAUT32!__imp_SysFreeString` at `0x18003386f`
- `OLEAUT32!__imp_SysFreeString` at `0x180033883`
- `OLEAUT32!__imp_SysFreeString` at `0x1800338a6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800338ba`
- `OLEAUT32!__imp_SysFreeString` at `0x1800338ce`
- `OLEAUT32!__imp_VariantInit` at `0x180032d9e`
- `OLEAUT32!__imp_VariantInit` at `0x180032d9e`
- `OLEAUT32!__imp_VariantClear` at `0x1800337bc`
- `OLEAUT32!__imp_VariantClear` at `0x180033892`
- `OLEAUT32!__imp_VariantClear` at `0x1800337bc`
- `OLEAUT32!__imp_VariantClear` at `0x180033892`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x180031b17`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x180031b17`

## string_xrefs

- `0x18003268f`: `IsSecurity`
- `0x1800328fe`: `InstallSize`

## pseudocode

```c
// Hidden C++ exception states: #wind=35
__int64 __fastcall Diagnostics::SourceHandler_UpdateManager::ConvertData(
        __int64 a1,
        const void **a2,
        const struct std::filesystem::path *a3)
{
  int v6; // r14d
  _WORD *v7; // rbx
  unsigned __int64 v8; // r8
  const wchar_t *p_Src; // rax
  const wchar_t *v10; // rcx
  __int64 v11; // rax
  const wchar_t *v12; // rcx
  __int64 v13; // rax
  const wchar_t *v14; // rax
  const wchar_t *v15; // rcx
  const wchar_t *v16; // rax
  const wchar_t *v17; // rcx
  const wchar_t *v18; // rax
  __int64 *v19; // rcx
  __int64 v20; // rax
  __int64 *v21; // rcx
  unsigned __int64 v22; // r8
  __int64 i; // rdx
  __int64 v24; // rax
  __int128 *v25; // rax
  __int64 v26; // rax
  unsigned __int64 v27; // r8
  wchar_t **v28; // rax
  __int64 v29; // rax
  unsigned __int64 v30; // r8
  wchar_t **v31; // rax
  __int64 v32; // rax
  unsigned __int64 v33; // r8
  wchar_t **v34; // rax
  const wchar_t *v35; // rcx
  __int64 v36; // rax
  const wchar_t *v37; // rcx
  __int64 v38; // rax
  const wchar_t *v39; // rcx
  __int64 v40; // rax
  const wchar_t *v41; // rcx
  __int64 v42; // rax
  const wchar_t *v43; // rcx
  __int64 v44; // rax
  const wchar_t *v45; // rcx
  __int64 v46; // rax
  const wchar_t *v47; // rcx
  __int64 v48; // rax
  const wchar_t *v49; // rcx
  __int64 v50; // rax
  __int64 v51; // rax
  __int128 *v52; // rax
  __int64 v53; // rax
  __int128 *v54; // rax
  __int64 v55; // rax
  __int128 *v56; // rax
  const wchar_t *v57; // rcx
  __int64 v58; // rax
  double v59; // xmm6_8
  __int64 v60; // rbx
  int v61; // r14d
  wchar_t *v62; // rcx
  wchar_t **v63; // rax
  _QWORD *v64; // rax
  _QWORD *v65; // rcx
  unsigned __int64 v66; // r8
  wchar_t **v67; // rax
  _QWORD *v68; // rax
  _QWORD *v69; // rcx
  _QWORD *v70; // rax
  _QWORD *v71; // rcx
  _QWORD *v72; // rax
  _QWORD *v73; // rcx
  unsigned __int64 v74; // r8
  wchar_t **v75; // rax
  _QWORD *v76; // rax
  _QWORD *v77; // rcx
  __int128 *v78; // rax
  __int64 v79; // rax
  unsigned __int64 v80; // r8
  wchar_t **v81; // rax
  const wchar_t *v82; // rcx
  __int64 v83; // rax
  const wchar_t *v84; // rcx
  __int64 v85; // rax
  __int64 v86; // rax
  unsigned __int64 v87; // r8
  wchar_t **v88; // rax
  __int64 v89; // rax
  unsigned __int64 v90; // r8
  wchar_t **v91; // rax
  __int64 v92; // rax
  int v93; // eax
  OLECHAR *v94; // rcx
  unsigned __int64 v95; // r8
  __int128 *v96; // rax
  unsigned int v97; // ebx
  int v99; // [rsp+20h] [rbp-B68h]
  int v100; // [rsp+24h] [rbp-B64h]
  unsigned __int64 v101; // [rsp+28h] [rbp-B60h] BYREF
  __int128 v102; // [rsp+30h] [rbp-B58h] BYREF
  _QWORD v103[2]; // [rsp+40h] [rbp-B48h] BYREF
  _QWORD v104[2]; // [rsp+50h] [rbp-B38h] BYREF
  _QWORD v105[2]; // [rsp+60h] [rbp-B28h] BYREF
  _QWORD v106[2]; // [rsp+70h] [rbp-B18h] BYREF
  _QWORD v107[2]; // [rsp+80h] [rbp-B08h] BYREF
  _QWORD v108[2]; // [rsp+90h] [rbp-AF8h] BYREF
  _QWORD v109[2]; // [rsp+A0h] [rbp-AE8h] BYREF
  _QWORD v110[2]; // [rsp+B0h] [rbp-AD8h] BYREF
  _QWORD v111[2]; // [rsp+C0h] [rbp-AC8h] BYREF
  _QWORD v112[2]; // [rsp+D0h] [rbp-AB8h] BYREF
  _QWORD v113[2]; // [rsp+E0h] [rbp-AA8h] BYREF
  _QWORD v114[2]; // [rsp+F0h] [rbp-A98h] BYREF
  _QWORD v115[2]; // [rsp+100h] [rbp-A88h] BYREF
  _QWORD v116[2]; // [rsp+110h] [rbp-A78h] BYREF
  _QWORD v117[2]; // [rsp+120h] [rbp-A68h] BYREF
  _QWORD v118[2]; // [rsp+130h] [rbp-A58h] BYREF
  _QWORD v119[2]; // [rsp+140h] [rbp-A48h] BYREF
  _QWORD v120[2]; // [rsp+150h] [rbp-A38h] BYREF
  _QWORD v121[2]; // [rsp+160h] [rbp-A28h] BYREF
  _QWORD v122[2]; // [rsp+170h] [rbp-A18h] BYREF
  _QWORD v123[2]; // [rsp+180h] [rbp-A08h] BYREF
  _QWORD v124[2]; // [rsp+190h] [rbp-9F8h] BYREF
  _QWORD v125[2]; // [rsp+1A0h] [rbp-9E8h] BYREF
  _QWORD v126[2]; // [rsp+1B0h] [rbp-9D8h] BYREF
  _QWORD v127[2]; // [rsp+1C0h] [rbp-9C8h] BYREF
  _QWORD v128[2]; // [rsp+1D0h] [rbp-9B8h] BYREF
  _QWORD v129[2]; // [rsp+1E0h] [rbp-9A8h] BYREF
  _QWORD v130[2]; // [rsp+1F0h] [rbp-998h] BYREF
  _QWORD v131[2]; // [rsp+200h] [rbp-988h] BYREF
  _QWORD v132[2]; // [rsp+210h] [rbp-978h] BYREF
  _QWORD v133[2]; // [rsp+220h] [rbp-968h] BYREF
  _QWORD v134[2]; // [rsp+230h] [rbp-958h] BYREF
  _QWORD v135[2]; // [rsp+240h] [rbp-948h] BYREF
  _QWORD v136[2]; // [rsp+250h] [rbp-938h] BYREF
  _QWORD v137[2]; // [rsp+260h] [rbp-928h] BYREF
  _QWORD v138[2]; // [rsp+270h] [rbp-918h] BYREF
  _QWORD v139[2]; // [rsp+280h] [rbp-908h] BYREF
  _QWORD v140[2]; // [rsp+290h] [rbp-8F8h] BYREF
  _QWORD v141[2]; // [rsp+2A0h] [rbp-8E8h] BYREF
  _QWORD v142[2]; // [rsp+2B0h] [rbp-8D8h] BYREF
  _QWORD v143[2]; // [rsp+2C0h] [rbp-8C8h] BYREF
  _QWORD v144[2]; // [rsp+2D0h] [rbp-8B8h] BYREF
  _QWORD v145[2]; // [rsp+2E0h] [rbp-8A8h] BYREF
  _QWORD v146[2]; // [rsp+2F0h] [rbp-898h] BYREF
  _QWORD v147[2]; // [rsp+300h] [rbp-888h] BYREF
  _QWORD v148[2]; // [rsp+310h] [rbp-878h] BYREF
  _QWORD v149[2]; // [rsp+320h] [rbp-868h] BYREF
  _QWORD v150[2]; // [rsp+330h] [rbp-858h] BYREF
  _QWORD v151[2]; // [rsp+340h] [rbp-848h] BYREF
  _QWORD v152[2]; // [rsp+350h] [rbp-838h] BYREF
  _QWORD v153[2]; // [rsp+360h] [rbp-828h] BYREF
  _QWORD v154[2]; // [rsp+370h] [rbp-818h] BYREF
  _QWORD v155[2]; // [rsp+380h] [rbp-808h] BYREF
  _QWORD v156[2]; // [rsp+390h] [rbp-7F8h] BYREF
  _QWORD v157[2]; // [rsp+3A0h] [rbp-7E8h] BYREF
  _QWORD v158[2]; // [rsp+3B0h] [rbp-7D8h] BYREF
  _QWORD v159[2]; // [rsp+3C0h] [rbp-7C8h] BYREF
  _QWORD v160[2]; // [rsp+3D0h] [rbp-7B8h] BYREF
  _QWORD v161[2]; // [rsp+3E0h] [rbp-7A8h] BYREF
  _QWORD v162[2]; // [rsp+3F0h] [rbp-798h] BYREF
  const wchar_t *v163; // [rsp+400h] [rbp-788h] BYREF
  __int64 v164; // [rsp+408h] [rbp-780h]
  const wchar_t *v165; // [rsp+410h] [rbp-778h] BYREF
  __int64 v166; // [rsp+418h] [rbp-770h]
  int v167; // [rsp+420h] [rbp-768h] BYREF
  int v168; // [rsp+424h] [rbp-764h] BYREF
  int v169; // [rsp+428h] [rbp-760h] BYREF
  int v170; // [rsp+42Ch] [rbp-75Ch] BYREF
  int v171; // [rsp+430h] [rbp-758h] BYREF
  int v172; // [rsp+434h] [rbp-754h] BYREF
  int v173; // [rsp+438h] [rbp-750h] BYREF
  int v174; // [rsp+43Ch] [rbp-74Ch] BYREF
  int v175; // [rsp+440h] [rbp-748h] BYREF
  int v176; // [rsp+444h] [rbp-744h] BYREF
  int v177; // [rsp+448h] [rbp-740h] BYREF
  int v178; // [rsp+44Ch] [rbp-73Ch] BYREF
  __int128 v179; // [rsp+450h] [rbp-738h] BYREF
  __int128 v180; // [rsp+460h] [rbp-728h]
  __int64 v181; // [rsp+470h] [rbp-718h] BYREF
  __int64 v182; // [rsp+478h] [rbp-710h] BYREF
  __int64 v183; // [rsp+480h] [rbp-708h] BYREF
  __int64 v184; // [rsp+488h] [rbp-700h] BYREF
  unsigned int v185; // [rsp+490h] [rbp-6F8h]
  __int128 v186; // [rsp+498h] [rbp-6F0h] BYREF
  __int64 v187; // [rsp+4A8h] [rbp-6E0h]
  VARIANTARG pvarg; // [rsp+4B0h] [rbp-6D8h] BYREF
  __int128 v189; // [rsp+4C8h] [rbp-6C0h] BYREF
  __int64 *v190; // [rsp+4D8h] [rbp-6B0h] BYREF
  __int128 v191; // [rsp+4E0h] [rbp-6A8h] BYREF
  __int128 v192; // [rsp+4F0h] [rbp-698h]
  __int64 *v193; // [rsp+500h] [rbp-688h] BYREF
  __int64 *v194; // [rsp+508h] [rbp-680h] BYREF
  BSTR v195; // [rsp+510h] [rbp-678h] BYREF
  BSTR v196; // [rsp+518h] [rbp-670h] BYREF
  unsigned int v197; // [rsp+520h] [rbp-668h] BYREF
  BSTR bstrString; // [rsp+528h] [rbp-660h] BYREF
  BSTR v199; // [rsp+530h] [rbp-658h] BYREF
  BSTR v200; // [rsp+538h] [rbp-650h] BYREF
  BSTR v201; // [rsp+540h] [rbp-648h] BYREF
  __int64 v202; // [rsp+548h] [rbp-640h] BYREF
  __int128 v203; // [rsp+550h] [rbp-638h] BYREF
  __int64 v204; // [rsp+560h] [rbp-628h]
  unsigned __int64 v205; // [rsp+568h] [rbp-620h]
  __int128 Src; // [rsp+570h] [rbp-618h] BYREF
  __int64 v207; // [rsp+580h] [rbp-608h]
  unsigned __int64 v208; // [rsp+588h] [rbp-600h]
  _BYTE v209[336]; // [rsp+590h] [rbp-5F8h] BYREF
  _BYTE v210[336]; // [rsp+6E0h] [rbp-4A8h] BYREF
  _DWORD v211[176]; // [rsp+830h] [rbp-358h] BYREF
  wchar_t *Buffer[2]; // [rsp+AF0h] [rbp-98h] BYREF
  __int128 v213; // [rsp+B00h] [rbp-88h]
  _BYTE v214[6]; // [rsp+B1Ah] [rbp-6Eh] BYREF

  v6 = 0;
  v99 = 0;
  memset(v211, 0, sizeof(v211));
  Diagnostics::OTelFile::OTelFile((Diagnostics::OTelFile *)v211, a3);
  v193 = 0;
  GetSystemTimePreciseAsFileTime(&v193);
  v101 = ((unsigned __int64)HIDWORD(v193) << 32) - 116444736000000000LL + (unsigned int)v193;
  v7 = *a2;
  Src = 0;
  v207 = 0;
  v208 = 0;
  v8 = -1;
  do
    ++v8;
  while ( v7[v8] );
  std::wstring::_Construct<1,wchar_t const *>(&Src, v7, v8);
  std::wstring::append(&Src);
  memset(v210, 0, sizeof(v210));
  p_Src = (const wchar_t *)&Src;
  if ( v208 > 7 )
    p_Src = (const wchar_t *)Src;
  v102 = *(_OWORD *)&Diagnostics::OTelLogRecord::DefaultVersion;
  v163 = p_Src;
  v164 = v207;
  Diagnostics::OTelLogRecord::OTelLogRecord(v210, &v101, &v163, &v102);
  v167 = 0;
  if ( (*(int (__fastcall **)(_QWORD, int *))(**(_QWORD **)(a1 + 40) + 24LL))(*(_QWORD *)(a1 + 40), &v167) >= 0 )
  {
    v10 = L"false";
    if ( v167 )
      v10 = L"true";
    v11 = -1;
    do
      ++v11;
    while ( v10[v11] );
    v163 = v10;
    v164 = v11;
    v165 = L"Is_Scanning";
    v166 = 11;
    Diagnostics::OTelLogRecord::AddAttribute(v210, &v165, &v163);
  }
  v168 = 0;
  if ( (*(int (__fastcall **)(_QWORD, int *))(**(_QWORD **)(a1 + 40) + 32LL))(*(_QWORD *)(a1 + 40), &v168) >= 0 )
  {
    v12 = L"false";
    if ( v168 )
      v12 = L"true";
    v13 = -1;
    do
      ++v13;
    while ( v12[v13] );
    v163 = v12;
    v164 = v13;
    v165 = L"Is_Working";
    v166 = 10;
    Diagnostics::OTelLogRecord::AddAttribute(v210, &v165, &v163);
  }
  v189 = 0;
  if ( (*(int (__fastcall **)(_QWORD, __int128 *))(**(_QWORD **)(a1 + 40) + 40LL))(*(_QWORD *)(a1 + 40), &v189) >= 0 )
  {
    v14 = (const wchar_t *)std::to_wstring(&v191, DWORD2(v189));
    v15 = v14;
    if ( *((_QWORD *)v14 + 3) > 7u )
      v15 = *(const wchar_t **)v14;
    v163 = v15;
    v164 = *((_QWORD *)v14 + 2);
    v165 = L"Last_Scan_Error";
    v166 = 15;
    Diagnostics::OTelLogRecord::AddAttribute(v210, &v165, &v163);
    std::wstring::~wstring((__int64)&v191);
  }
  v184 = 0;
  v185 = 0;
  if ( (*(int (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)(a1 + 40) + 56LL))(*(_QWORD *)(a1 + 40), &v184) >= 0 )
  {
    v16 = (const wchar_t *)std::to_wstring(&v191, v185);
    v17 = v16;
    if ( *((_QWORD *)v16 + 3) > 7u )
      v17 = *(const wchar_t **)v16;
    v163 = v17;
    v164 = *((_QWORD *)v16 + 2);
    v165 = L"Attention_Required";
    v166 = 18;
    Diagnostics::OTelLogRecord::AddAttribute(v210, &v165, &v163);
    std::wstring::~wstring((__int64)&v191);
  }
  v202 = 0;
  if ( (*(int (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)(a1 + 40) + 64LL))(*(_QWORD *)(a1 + 40), &v202) >= 0
    && v202 )
  {
    v179 = 0;
    v180 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v179, L"INVALID_FILE_TIME", 0x11u);
    Diagnostics::DataStyles::FileTime_NoThrow(&v191, &v202, &v179);
    std::wstring::~wstring((__int64)&v179);
    if ( (_QWORD)v192 )
    {
      v18 = (const wchar_t *)&v191;
      if ( *((_QWORD *)&v192 + 1) > 7u )
        v18 = (const wchar_t *)v191;
      v163 = v18;
      v164 = v192;
      v165 = L"Last_Successful_Scan";
      v166 = 20;
      Diagnostics::OTelLogRecord::AddAttribute(v210, &v165, &v163);
    }
    std::wstring::~wstring((__int64)&v191);
  }
  Diagnostics::OTelFile::AppendLogRecord((Diagnostics::OTelFile *)v211, (const struct Diagnostics::OTelLogRecord *)v210);
  v194 = 0;
  v19 = *(__int64 **)(a1 + 40);
  v20 = *v19;
  v194 = 0;
  if ( (*(int (__fastcall **)(__int64 *, __int64 **))(v20 + 48))(v19, &v194) < 0 )
  {
LABEL_247:
    v21 = v194;
  }
  else
  {
    v21 = v194;
    if ( v194 )
    {
      v197 = 0;
      if ( (*(int (__fastcall **)(__int64 *, unsigned int *))(*v194 + 32))(v194, &v197) < 0 )
        goto LABEL_247;
      v203 = 0;
      v204 = 0;
      v205 = 0;
      v22 = -1;
      do
        ++v22;
      while ( v7[v22] );
      std::wstring::_Construct<1,wchar_t const *>(&v203, v7, v22);
      std::wstring::append(&v203);
      for ( i = 0; ; i = (unsigned int)(v100 + 1) )
      {
        v100 = i;
        if ( (unsigned int)i >= v197 )
        {
          std::wstring::~wstring((__int64)&v203);
          goto LABEL_247;
        }
        v190 = 0;
        v24 = *v194;
        v190 = 0;
        if ( (*(int (__fastcall **)(__int64 *, __int64, __int64 **))(v24 + 24))(v194, i, &v190) >= 0 )
        {
          memset(v209, 0, sizeof(v209));
          v25 = &v203;
          if ( v205 > 7 )
            v25 = (__int128 *)v203;
          *(_OWORD *)Buffer = *(_OWORD *)&Diagnostics::OTelLogRecord::DefaultVersion;
          v133[0] = v25;
          v133[1] = v204;
          Diagnostics::OTelLogRecord::OTelLogRecord(v209, &v101, v133, Buffer);
          v196 = 0;
          v26 = *v190;
          v196 = 0;
          if ( (*(int (__fastcall **)(__int64 *, BSTR *))(v26 + 24))(v190, &v196) >= 0 && v196 )
          {
            *(_OWORD *)Buffer = 0;
            v213 = 0;
            v27 = -1;
            do
              ++v27;
            while ( v196[v27] );
            std::wstring::_Construct<1,wchar_t const *>(Buffer, v196, v27);
            v6 |= 0x4000u;
            v28 = Buffer;
            if ( *((_QWORD *)&v213 + 1) > 7u )
              v28 = (wchar_t **)Buffer[0];
            v134[0] = v28;
            v134[1] = v213;
            v135[0] = L"Alias";
            v135[1] = 5;
            Diagnostics::OTelLogRecord::AddAttribute(v209, v135, v134);
            std::wstring::~wstring((__int64)Buffer);
            v99 = v6;
          }
          v195 = 0;
          v29 = *v190;
          v195 = 0;
          if ( (*(int (__fastcall **)(__int64 *, BSTR *))(v29 + 32))(v190, &v195) >= 0 && v195 )
          {
            *(_OWORD *)Buffer = 0;
            v213 = 0;
            v30 = -1;
            do
              ++v30;
            while ( v195[v30] );
            std::wstring::_Construct<1,wchar_t const *>(Buffer, v195, v30);
            v6 |= 0x1000u;
            v31 = Buffer;
            if ( *((_QWORD *)&v213 + 1) > 7u )
              v31 = (wchar_t **)Buffer[0];
            v136[0] = v31;
            v136[1] = v213;
            v137[0] = L"Description";
            v137[1] = 11;
            Diagnostics::OTelLogRecord::AddAttribute(v209, v137, v136);
            std::wstring::~wstring((__int64)Buffer);
            v99 = v6;
          }
          v201 = 0;
          v32 = *v190;
          v201 = 0;
          if ( (*(int (__fastcall **)(__int64 *, BSTR *))(v32 + 112))(v190, &v201) >= 0 && v201 )
          {
            *(_OWORD *)Buffer = 0;
            v213 = 0;
            v33 = -1;
            do
              ++v33;
            while ( v201[v33] );
            std::wstring::_Construct<1,wchar_t const *>(Buffer, v201, v33);
            v6 |= 0x10000u;
            v34 = Buffer;
            if ( *((_QWORD *)&v213 + 1) > 7u )
              v34 = (wchar_t **)Buffer[0];
            v138[0] = v34;
            v138[1] = v213;
            v139[0] = L"ID";
            v139[1] = 2;
            Diagnostics::OTelLogRecord::AddAttribute(v209, v139, v138);
            std::wstring::~wstring((__int64)Buffer);
            v99 = v6;
          }
          v169 = 0;
          if ( (*(int (__fastcall **)(__int64 *, int *))(*v190 + 208))(v190, &v169) >= 0 )
          {
            v35 = L"false";
            if ( v169 )
              v35 = L"true";
            v36 = -1;
            do
              ++v36;
            while ( v35[v36] );
            v140[0] = v35;
            v140[1] = v36;
            v141[0] = L"IsForOs";
            v141[1] = 7;
            Diagnostics::OTelLogRecord::AddAttribute(v209, v141, v140);
          }
          v170 = 0;
          if ( (*(int (__fastcall **)(__int64 *, int *))(*v190 + 200))(v190, &v170) >= 0 )
          {
            v37 = L"false";
            if ( v170 )
              v37 = L"true";
            v38 = -1;
            do
              ++v38;
            while ( v37[v38] );
            v142[0] = v37;
            v142[1] = v38;
            v143[0] = L"IsDriver";
            v143[1] = 8;
            Diagnostics::OTelLogRecord::AddAttribute(v209, v143, v142);
          }
          v171 = 0;
          if ( (*(int (__fastcall **)(__int64 *, int *))(*v190 + 216))(v190, &v171) >= 0 )
          {
            v39 = L"false";
            if ( v171 )
              v39 = L"true";
            v40 = -1;
            do
              ++v40;
            while ( v39[v40] );
            v144[0] = v39;
            v144[1] = v40;
            v145[0] = L"IsUrgent";
            v145[1] = 8;
            Diagnostics::OTelLogRecord::AddAttribute(v209, v145, v144);
          }
          v172 = 0;
          if ( (*(int (__fastcall **)(__int64 *, int *))(*v190 + 224))(v190, &v172) >= 0 )
          {
            v41 = L"false";
            if ( v172 )
              v41 = L"true";
            v42 = -1;
            do
              ++v42;
            while ( v41[v42] );
            v146[0] = v41;
            v146[1] = v42;
            v147[0] = L"IsMandatory";
            v147[1] = 11;
            Diagnostics::OTelLogRecord::AddAttribute(v209, v147, v146);
          }
          v173 = 0;
          if ( (*(int (__fastcall **)(__int64 *, int *))(*v190 + 232))(v190, &v173) >= 0 )
          {
            v43 = L"false";
            if ( v173 )
              v43 = L"true";
            v44 = -1;
            do
              ++v44;
            while ( v43[v44] );
            v148[0] = v43;
            v148[1] = v44;
            v149[0] = L"IsSecurity";
            v149[1] = 10;
            Diagnostics::OTelLogRecord::AddAttribute(v209, v149, v148);
          }
          v174 = 0;
          if ( (*(int (__fastcall **)(__int64 *, int *))(*v190 + 240))(v190, &v174) >= 0 )
          {
            v45 = L"false";
            if ( v174 )
              v45 = L"true";
            v46 = -1;
            do
              ++v46;
            while ( v45[v46] );
            v150[0] = v45;
            v150[1] = v46;
            v151[0] = L"IsCritical";
            v151[1] = 10;
            Diagnostics::OTelLogRecord::AddAttribute(v209, v151, v150);
          }
          v175 = 0;
          if ( (*(int (__fastcall **)(__int64 *, int *))(*v190 + 152))(v190, &v175) >= 0 )
          {
            v47 = L"false";
            if ( v175 )
              v47 = L"true";
            v48 = -1;
            do
              ++v48;
            while ( v47[v48] );
            v152[0] = v47;
            v152[1] = v48;
            v153[0] = L"IsSeeker";
            v153[1] = 8;
            Diagnostics::OTelLogRecord::AddAttribute(v209, v153, v152);
          }
          v176 = 0;
          if ( (*(int (__fastcall **)(__int64 *, int *))(*v190 + 40))(v190, &v176) >= 0 )
          {
            v49 = L"false";
            if ( v176 )
              v49 = L"true";
            v50 = -1;
            do
              ++v50;
            while ( v49[v50] );
            v154[0] = v49;
            v154[1] = v50;
            v155[0] = L"EulaAccepted";
            v155[1] = 12;
            Diagnostics::OTelLogRecord::AddAttribute(v209, v155, v154);
          }
          v181 = 0;
          if ( (*(int (__fastcall **)(__int64 *, __int64 *))(*v190 + 80))(v190, &v181) >= 0 )
          {
            v51 = std::_UIntegral_to_buff<wchar_t,unsigned __int64>(v214);
            std::wstring::wstring(&v191, v51, v214);
            v6 |= 7u;
            v99 = v6;
            v52 = &v191;
            if ( *((_QWORD *)&v192 + 1) > 7u )
              v52 = (__int128 *)v191;
            v156[0] = v52;
            v156[1] = v192;
            v157[0] = L"InstallSize";
            v157[1] = 11;
            Diagnostics::OTelLogRecord::AddAttribute(v209, v157, v156);
            std::wstring::~wstring((__int64)&v191);
          }
          v182 = 0;
          if ( (*(int (__fastcall **)(__int64 *, __int64 *))(*v190 + 88))(v190, &v182) >= 0 )
          {
            v53 = std::_UIntegral_to_buff<wchar_t,unsigned __int64>(v214);
            std::wstring::wstring(&v191, v53, v214);
            v6 |= 0x38u;
            v99 = v6;
            v54 = &v191;
            if ( *((_QWORD *)&v192 + 1) > 7u )
              v54 = (__int128 *)v191;
            v158[0] = v54;
            v158[1] = v192;
            v159[0] = L"MinDownloadSize";
            v159[1] = 15;
            Diagnostics::OTelLogRecord::AddAttribute(v209, v159, v158);
            std::wstring::~wstring((__int64)&v191);
          }
          v183 = 0;
          if ( (*(int (__fastcall **)(__int64 *, __int64 *))(*v190 + 96))(v190, &v183) >= 0 )
          {
            v55 = std::_UIntegral_to_buff<wchar_t,unsigned __int64>(v214);
            std::wstring::wstring(&v191, v55, v214);
            v6 |= 0x1C0u;
            v99 = v6;
            v56 = &v191;
            if ( *((_QWORD *)&v192 + 1) > 7u )
              v56 = (__int128 *)v191;
            v160[0] = v56;
            v160[1] = v192;
            v161[0] = L"MaxDownloadSize";
            v161[1] = 15;
            Diagnostics::OTelLogRecord::AddAttribute(v209, v161, v160);
            std::wstring::~wstring((__int64)&v191);
          }
          v186 = 0;
          v187 = 0;
          if ( (*(int (__fastcall **)(__int64 *, __int128 *))(*v190 + 120))(v190, &v186) >= 0 )
          {
            v57 = L"false";
            if ( HIDWORD(v186) )
              v57 = L"true";
            v58 = -1;
            do
              ++v58;
            while ( v57[v58] );
            v162[0] = v57;
            v162[1] = v58;
            v103[0] = L"InProgress";
            v103[1] = 10;
            Diagnostics::OTelLogRecord::AddAttribute(v209, v103, v162);
            v59 = (double)(int)v187;
            v60 = scwprintf(L"%f", (double)(int)v187);
            std::wstring::wstring(Buffer, v60);
            v61 = v6 | 0x400;
            v62 = (wchar_t *)Buffer;
            if ( *((_QWORD *)&v213 + 1) > 7u )
              v62 = Buffer[0];
            swprintf_s(v62, v60 + 1, L"%f", v59);
            v6 = v61 | 0x200;
            v99 = v6;
            v63 = Buffer;
            if ( *((_QWORD *)&v213 + 1) > 7u )
              v63 = (wchar_t **)Buffer[0];
            v104[0] = v63;
            v104[1] = v213;
            v105[0] = L"Progress";
            v105[1] = 8;
            Diagnostics::OTelLogRecord::AddAttribute(v209, v105, v104);
            std::wstring::~wstring((__int64)Buffer);
            v64 = (_QWORD *)std::to_wstring(&v191, DWORD2(v186));
            v65 = v64;
            if ( v64[3] > 7u )
              v65 = (_QWORD *)*v64;
            v106[0] = v65;
            v106[1] = v64[2];
            v107[0] = L"ActionClass";
            v107[1] = 11;
            Diagnostics::OTelLogRecord::AddAttribute(v209, v107, v106);
            std::wstring::~wstring((__int64)&v191);
            if ( (_QWORD)v186 )
            {
              *(_OWORD *)Buffer = 0;
              v213 = 0;
              v66 = -1;
              do
                ++v66;
              while ( *(_WORD *)(v186 + 2 * v66) );
              std::wstring::_Construct<1,wchar_t const *>(Buffer, (const void *)v186, v66);
              v67 = Buffer;
              if ( *((_QWORD *)&v213 + 1) > 7u )
                v67 = (wchar_t **)Buffer[0];
              v108[0] = v67;
              v108[1] = v213;
              v109[0] = L"Action";
              v109[1] = 6;
              Diagnostics::OTelLogRecord::AddAttribute(v209, v109, v108);
              std::wstring::~wstring((__int64)Buffer);
            }
          }
          VariantInit(&pvarg);
          if ( (*(int (__fastcall **)(__int64 *, VARIANTARG *))(*v190 + 64))(v190, &pvarg) >= 0 && pvarg.vt == 7 )
          {
            v68 = (_QWORD *)Diagnostics::DataStyles::Date(&v191);
            v69 = v68;
            if ( v68[3] > 7u )
              v69 = (_QWORD *)*v68;
            v110[0] = v69;
            v110[1] = v68[2];
            v111[0] = L"Deadline";
            v111[1] = 8;
            Diagnostics::OTelLogRecord::AddAttribute(v209, v111, v110);
            std::wstring::~wstring((__int64)&v191);
          }
          v165 = 0;
          if ( (*(int (__fastcall **)(__int64 *, const wchar_t **))(*v190 + 56))(v190, &v165) >= 0 )
          {
            v70 = (_QWORD *)Diagnostics::DataStyles::Date(&v191);
            v71 = v70;
            if ( v70[3] > 7u )
              v71 = (_QWORD *)*v70;
            v112[0] = v71;
            v112[1] = v70[2];
            v113[0] = L"LastDeploymentChangeTime";
            v113[1] = 24;
            Diagnostics::OTelLogRecord::AddAttribute(v209, v113, v112);
            std::wstring::~wstring((__int64)&v191);
          }
          v163 = 0;
          LODWORD(v164) = 0;
          if ( (*(int (__fastcall **)(__int64 *, const wchar_t **))(*v190 + 128))(v190, &v163) >= 0 )
          {
            v72 = (_QWORD *)std::to_wstring(&v191, (unsigned int)v164);
            v73 = v72;
            if ( v72[3] > 7u )
              v73 = (_QWORD *)*v72;
            v114[0] = v73;
            v114[1] = v72[2];
            v115[0] = L"AttentionRequiredReason";
            v115[1] = 23;
            Diagnostics::OTelLogRecord::AddAttribute(v209, v115, v114);
            std::wstring::~wstring((__int64)&v191);
          }
          v179 = 0;
          v180 = 0;
          if ( (*(int (__fastcall **)(__int64 *, __int128 *))(*v190 + 136))(v190, &v179) >= 0 )
          {
            if ( (_QWORD)v180 )
            {
              *(_OWORD *)Buffer = 0;
              v213 = 0;
              v74 = -1;
              do
                ++v74;
              while ( *(_WORD *)(v180 + 2 * v74) );
              std::wstring::_Construct<1,wchar_t const *>(Buffer, (const void *)v180, v74);
              v75 = Buffer;
              if ( *((_QWORD *)&v213 + 1) > 7u )
                v75 = (wchar_t **)Buffer[0];
              v116[0] = v75;
              v116[1] = v213;
              v117[0] = L"FailureAction";
              v117[1] = 13;
              Diagnostics::OTelLogRecord::AddAttribute(v209, v117, v116);
              std::wstring::~wstring((__int64)Buffer);
            }
            v76 = (_QWORD *)std::to_wstring(&v191, DWORD2(v179));
            v77 = v76;
            if ( v76[3] > 7u )
              v77 = (_QWORD *)*v76;
            v118[0] = v77;
            v118[1] = v76[2];
            v119[0] = L"FailureResult";
            v119[1] = 13;
            Diagnostics::OTelLogRecord::AddAttribute(v209, v119, v118);
            std::wstring::~wstring((__int64)&v191);
            if ( (_QWORD)v179 )
            {
              *(_OWORD *)Buffer = 0;
              v213 = 0;
              std::wstring::_Construct<1,wchar_t const *>(Buffer, L"INVALID_FILE_TIME", 0x11u);
              Diagnostics::DataStyles::FileTime_NoThrow(&v191, &v179, Buffer);
              std::wstring::~wstring((__int64)Buffer);
              if ( (_QWORD)v192 )
              {
                v78 = &v191;
                if ( *((_QWORD *)&v192 + 1) > 7u )
                  v78 = (__int128 *)v191;
                v120[0] = v78;
                v120[1] = v192;
                v121[0] = L"FailureTime";
                v121[1] = 11;
                Diagnostics::OTelLogRecord::AddAttribute(v209, v121, v120);
              }
              std::wstring::~wstring((__int64)&v191);
            }
          }
          v200 = 0;
          v79 = *v190;
          v200 = 0;
          if ( (*(int (__fastcall **)(__int64 *, BSTR *))(v79 + 160))(v190, &v200) >= 0 && v200 )
          {
            *(_OWORD *)Buffer = 0;
            v213 = 0;
            v80 = -1;
            do
              ++v80;
            while ( v200[v80] );
            std::wstring::_Construct<1,wchar_t const *>(Buffer, v200, v80);
            v6 |= 0x800u;
            v81 = Buffer;
            if ( *((_QWORD *)&v213 + 1) > 7u )
              v81 = (wchar_t **)Buffer[0];
            v122[0] = v81;
            v122[1] = v213;
            v123[0] = L"ProviderId";
            v123[1] = 10;
            Diagnostics::OTelLogRecord::AddAttribute(v209, v123, v122);
            std::wstring::~wstring((__int64)Buffer);
            v99 = v6;
          }
          v177 = 0;
          if ( (*(int (__fastcall **)(__int64 *, int *))(*v190 + 168))(v190, &v177) >= 0 )
          {
            v82 = L"false";
            if ( v177 )
              v82 = L"true";
            v83 = -1;
            do
              ++v83;
            while ( v82[v83] );
            v124[0] = v82;
            v124[1] = v83;
            v125[0] = L"IsApproved";
            v125[1] = 10;
            Diagnostics::OTelLogRecord::AddAttribute(v209, v125, v124);
          }
          v178 = 0;
          if ( (*(int (__fastcall **)(__int64 *, int *))(*v190 + 192))(v190, &v178) >= 0 )
          {
            v84 = L"false";
            if ( v178 )
              v84 = L"true";
            v85 = -1;
            do
              ++v85;
            while ( v84[v85] );
            v126[0] = v84;
            v126[1] = v85;
            v127[0] = L"IsFeature";
            v127[1] = 9;
            Diagnostics::OTelLogRecord::AddAttribute(v209, v127, v126);
          }
          v199 = 0;
          v86 = *v190;
          v199 = 0;
          if ( (*(int (__fastcall **)(__int64 *, BSTR *))(v86 + 248))(v190, &v199) >= 0 && v199 )
          {
            *(_OWORD *)Buffer = 0;
            v213 = 0;
            v87 = -1;
            do
              ++v87;
            while ( v199[v87] );
            std::wstring::_Construct<1,wchar_t const *>(Buffer, v199, v87);
            v6 |= 0x2000u;
            v88 = Buffer;
            if ( *((_QWORD *)&v213 + 1) > 7u )
              v88 = (wchar_t **)Buffer[0];
            v128[0] = v88;
            v128[1] = v213;
            v129[0] = L"FlightId";
            v129[1] = 8;
            Diagnostics::OTelLogRecord::AddAttribute(v209, v129, v128);
            std::wstring::~wstring((__int64)Buffer);
            v99 = v6;
          }
          bstrString = 0;
          v89 = *v190;
          bstrString = 0;
          if ( (*(int (__fastcall **)(__int64 *, BSTR *))(v89 + 264))(v190, &bstrString) >= 0 && bstrString )
          {
            *(_OWORD *)Buffer = 0;
            v213 = 0;
            v90 = -1;
            do
              ++v90;
            while ( bstrString[v90] );
            std::wstring::_Construct<1,wchar_t const *>(Buffer, bstrString, v90);
            v6 |= 0x8000u;
            v91 = Buffer;
            if ( *((_QWORD *)&v213 + 1) > 7u )
              v91 = (wchar_t **)Buffer[0];
            v130[0] = v91;
            v130[1] = v213;
            v131[0] = L"Properties";
            v131[1] = 10;
            Diagnostics::OTelLogRecord::AddAttribute(v209, v131, v130);
            std::wstring::~wstring((__int64)Buffer);
            v99 = v6;
          }
          v193 = 0;
          (*(void (__fastcall **)(__int64 *, GUID *, __int64 **))*v190)(
            v190,
            &GUID_094c3761_2220_471d_9830_3baa13cea544,
            &v193);
          if ( v193 )
          {
            Buffer[0] = 0;
            v92 = *v193;
            Buffer[0] = 0;
            v93 = (*(__int64 (__fastcall **)(__int64 *, wchar_t **))(v92 + 328))(v193, Buffer);
            v94 = Buffer[0];
            if ( v93 >= 0 && Buffer[0] )
            {
              v191 = 0;
              v192 = 0;
              v95 = -1;
              do
                ++v95;
              while ( Buffer[0][v95] );
              std::wstring::_Construct<1,wchar_t const *>(&v191, Buffer[0], v95);
              v6 |= 0x20000u;
              v96 = &v191;
              if ( *((_QWORD *)&v192 + 1) > 7u )
                v96 = (__int128 *)v191;
              v132[0] = v96;
              v132[1] = v192;
              *(_QWORD *)&v102 = L"Metadata";
              *((_QWORD *)&v102 + 1) = 8;
              Diagnostics::OTelLogRecord::AddAttribute(v209, &v102, v132);
              std::wstring::~wstring((__int64)&v191);
              v99 = v6;
              v94 = Buffer[0];
            }
            if ( v94 )
              SysFreeString(v94);
          }
          try
          {
            Diagnostics::OTelFile::AppendLogRecord(
              (Diagnostics::OTelFile *)v211,
              (const struct Diagnostics::OTelLogRecord *)v209);
          }
          catch ( ... )
          {
            if ( v193 )
              (*(void (__fastcall **)(__int64 *))(*v193 + 16))(v193);
            if ( bstrString )
              SysFreeString(bstrString);
            if ( v199 )
              SysFreeString(v199);
            if ( v200 )
              SysFreeString(v200);
            VariantClear(&pvarg);
            if ( v201 )
              SysFreeString(v201);
            if ( v195 )
              SysFreeString(v195);
            if ( v196 )
              SysFreeString(v196);
            Diagnostics::OTelLogRecord::~OTelLogRecord((Diagnostics::OTelLogRecord *)v209);
            if ( v190 )
              (*(void (__fastcall **)(__int64 *))(*v190 + 16))(v190);
            v6 = v99;
            continue;
          }
          if ( v193 )
            (*(void (__fastcall **)(__int64 *))(*v193 + 16))(v193);
          if ( bstrString )
            SysFreeString(bstrString);
          if ( v199 )
            SysFreeString(v199);
          if ( v200 )
            SysFreeString(v200);
          VariantClear(&pvarg);
          if ( v201 )
            SysFreeString(v201);
          if ( v195 )
            SysFreeString(v195);
          if ( v196 )
            SysFreeString(v196);
          Diagnostics::OTelLogRecord::~OTelLogRecord((Diagnostics::OTelLogRecord *)v209);
        }
        if ( v190 )
          (*(void (__fastcall **)(__int64 *))(*v190 + 16))(v190);
      }
    }
  }
  v97 = v211[174];
  if ( v21 )
    (*(void (__fastcall **)(__int64 *))(*v21 + 16))(v21);
  Diagnostics::OTelLogRecord::~OTelLogRecord((Diagnostics::OTelLogRecord *)v210);
  std::wstring::~wstring((__int64)&Src);
  Diagnostics::OTelFile::~OTelFile((Diagnostics::OTelFile *)v211);
  return v97;
}

```

## disassembly

```asm
0x180031aa0  mov     rax, rsp
0x180031aa3  push    rbx
0x180031aa4  push    rsi
0x180031aa5  push    rdi
0x180031aa6  push    r12
0x180031aa8  push    r13
0x180031aaa  push    r14
0x180031aac  push    r15
0x180031aae  sub     rsp, 0B50h
0x180031ab5  movaps  xmmword ptr [rax-48h], xmm6
0x180031ab9  movaps  xmmword ptr [rax-58h], xmm7
0x180031abd  mov     rax, cs:__security_cookie
0x180031ac4  xor     rax, rsp
0x180031ac7  mov     [rsp+0B88h+var_68], rax
0x180031acf  mov     rbx, r8
0x180031ad2  mov     rdi, rdx
0x180031ad5  mov     r13, rcx
0x180031ad8  xor     esi, esi
0x180031ada  mov     r14d, esi
0x180031add  mov     [rsp+0B88h+var_B68], esi
0x180031ae1  xor     edx, edx; Val
0x180031ae3  mov     r8d, 2C0h; Size
0x180031ae9  lea     rcx, [rsp+0B88h+var_358]; void *
0x180031af1  call    memset
0x180031af6  mov     rdx, rbx; struct std::filesystem::path *
0x180031af9  lea     rcx, [rsp+0B88h+var_358]; this
0x180031b01  call    ??0OTelFile@Diagnostics@@QEAA@AEBVpath@filesystem@std@@@Z; Diagnostics::OTelFile::OTelFile(std::filesystem::path const &)
0x180031b06  nop
0x180031b07  mov     [rsp+0B88h+var_688], rsi
0x180031b0f  lea     rcx, [rsp+0B88h+var_688]
0x180031b17  call    cs:__imp_GetSystemTimePreciseAsFileTime
0x180031b1d  mov     eax, dword ptr [rsp+0B88h+var_688+4]
0x180031b24  shl     rax, 20h
0x180031b28  mov     ecx, dword ptr [rsp+0B88h+var_688]
0x180031b2f  mov     rdx, 0FE624E212AC18000h
0x180031b39  add     rax, rdx
0x180031b3c  add     rcx, rax
0x180031b3f  mov     [rsp+0B88h+var_B60], rcx
0x180031b44  mov     rbx, [rdi]
0x180031b47  xorps   xmm0, xmm0
0x180031b4a  movups  [rsp+0B88h+Src], xmm0
0x180031b52  mov     [rsp+0B88h+var_608], rsi
0x180031b5a  mov     [rsp+0B88h+var_600], rsi
0x180031b62  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180031b66  mov     r8, rdi
0x180031b69  inc     r8
0x180031b6c  cmp     [rbx+r8*2], si
0x180031b71  jnz     short loc_180031B69
0x180031b73  mov     rdx, rbx
0x180031b76  lea     rcx, [rsp+0B88h+Src]
0x180031b7e  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180031b83  nop
0x180031b84  mov     r8d, 6
0x180031b8a  mov     rdx, cs:off_1800B1750; ".Props"
0x180031b91  lea     rcx, [rsp+0B88h+Src]; Src
0x180031b99  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::append(wchar_t const * const,unsigned __int64)
0x180031b9e  xor     edx, edx; Val
0x180031ba0  mov     r8d, 150h; Size
0x180031ba6  lea     rcx, [rsp+0B88h+var_4A8]; void *
0x180031bae  call    memset
0x180031bb3  lea     rax, [rsp+0B88h+Src]
0x180031bbb  mov     r15d, 7
0x180031bc1  cmp     [rsp+0B88h+var_600], r15
0x180031bc9  cmova   rax, qword ptr [rsp+0B88h+Src]
0x180031bd2  movups  xmm0, xmmword ptr cs:?DefaultVersion@OTelLogRecord@Diagnostics@@0V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@B; std::wstring_view const Diagnostics::OTelLogRecord::DefaultVersion
0x180031bd9  movdqu  [rsp+0B88h+var_B58], xmm0
0x180031bdf  mov     [rsp+0B88h+var_788], rax
0x180031be7  mov     rax, [rsp+0B88h+var_608]
0x180031bef  mov     [rsp+0B88h+var_780], rax
0x180031bf7  lea     r9, [rsp+0B88h+var_B58]
0x180031bfc  lea     r8, [rsp+0B88h+var_788]
0x180031c04  lea     rdx, [rsp+0B88h+var_B60]
0x180031c09  lea     rcx, [rsp+0B88h+var_4A8]
0x180031c11  call    ??0OTelLogRecord@Diagnostics@@QEAA@AEBV?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@4@1@Z; Diagnostics::OTelLogRecord::OTelLogRecord(std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>> const &,std::wstring_view,std::wstring_view)
0x180031c16  nop
0x180031c17  mov     [rsp+0B88h+var_768], esi
0x180031c1e  mov     rcx, [r13+28h]
0x180031c22  mov     rax, [rcx]
0x180031c25  lea     rdx, [rsp+0B88h+var_768]
0x180031c2d  mov     rax, [rax+18h]
0x180031c31  call    _guard_dispatch_icall
0x180031c36  lea     r12, aFalse_0; "false"
0x180031c3d  test    eax, eax
0x180031c3f  js      short loc_180031CAA
0x180031c41  lea     rax, aTrue; "true"
0x180031c48  mov     rcx, r12
0x180031c4b  cmp     [rsp+0B88h+var_768], esi
0x180031c52  cmovnz  rcx, rax
0x180031c56  mov     rax, rdi
0x180031c59  inc     rax
0x180031c5c  cmp     [rcx+rax*2], si
0x180031c60  jnz     short loc_180031C59
0x180031c62  mov     [rsp+0B88h+var_788], rcx
0x180031c6a  mov     [rsp+0B88h+var_780], rax
0x180031c72  lea     rax, aIsScanning; "Is_Scanning"
0x180031c79  mov     [rsp+0B88h+var_778], rax
0x180031c81  mov     [rsp+0B88h+var_770], 0Bh
0x180031c8d  lea     r8, [rsp+0B88h+var_788]
0x180031c95  lea     rdx, [rsp+0B88h+var_778]
0x180031c9d  lea     rcx, [rsp+0B88h+var_4A8]
0x180031ca5  call    ?AddAttribute@OTelLogRecord@Diagnostics@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; Diagnostics::OTelLogRecord::AddAttribute(std::wstring_view,std::wstring_view)
0x180031caa  mov     [rsp+0B88h+var_764], esi
0x180031cb1  mov     rcx, [r13+28h]
0x180031cb5  mov     rax, [rcx]
0x180031cb8  lea     rdx, [rsp+0B88h+var_764]
0x180031cc0  mov     rax, [rax+20h]
0x180031cc4  call    _guard_dispatch_icall
0x180031cc9  test    eax, eax
0x180031ccb  js      short loc_180031D36
0x180031ccd  mov     rcx, r12
0x180031cd0  cmp     [rsp+0B88h+var_764], esi
0x180031cd7  lea     rax, aTrue; "true"
0x180031cde  cmovnz  rcx, rax
0x180031ce2  mov     rax, rdi
0x180031ce5  inc     rax
0x180031ce8  cmp     [rcx+rax*2], si
0x180031cec  jnz     short loc_180031CE5
0x180031cee  mov     [rsp+0B88h+var_788], rcx
0x180031cf6  mov     [rsp+0B88h+var_780], rax
0x180031cfe  lea     rax, aIsWorking; "Is_Working"
0x180031d05  mov     [rsp+0B88h+var_778], rax
0x180031d0d  mov     [rsp+0B88h+var_770], 0Ah
0x180031d19  lea     r8, [rsp+0B88h+var_788]
0x180031d21  lea     rdx, [rsp+0B88h+var_778]
0x180031d29  lea     rcx, [rsp+0B88h+var_4A8]
0x180031d31  call    ?AddAttribute@OTelLogRecord@Diagnostics@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; Diagnostics::OTelLogRecord::AddAttribute(std::wstring_view,std::wstring_view)
0x180031d36  xorps   xmm0, xmm0
0x180031d39  movups  [rsp+0B88h+var_6C0], xmm0
0x180031d41  mov     rcx, [r13+28h]
0x180031d45  mov     rax, [rcx]
0x180031d48  lea     rdx, [rsp+0B88h+var_6C0]
0x180031d50  mov     rax, [rax+28h]
0x180031d54  call    _guard_dispatch_icall
0x180031d59  test    eax, eax
0x180031d5b  js      short loc_180031DD8
0x180031d5d  mov     edx, dword ptr [rsp+0B88h+var_6C0+8]
0x180031d64  lea     rcx, [rsp+0B88h+var_6A8]
0x180031d6c  call    ?to_wstring@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@I@Z; std::to_wstring(uint)
0x180031d71  nop
0x180031d72  mov     rcx, rax
0x180031d75  cmp     [rax+18h], r15
0x180031d79  jbe     short loc_180031D7E
0x180031d7b  mov     rcx, [rax]
0x180031d7e  mov     [rsp+0B88h+var_788], rcx
0x180031d86  mov     rax, [rax+10h]
0x180031d8a  mov     [rsp+0B88h+var_780], rax
0x180031d92  lea     rax, aLastScanError; "Last_Scan_Error"
0x180031d99  mov     [rsp+0B88h+var_778], rax
0x180031da1  mov     [rsp+0B88h+var_770], 0Fh
0x180031dad  lea     r8, [rsp+0B88h+var_788]
0x180031db5  lea     rdx, [rsp+0B88h+var_778]
0x180031dbd  lea     rcx, [rsp+0B88h+var_4A8]
0x180031dc5  call    ?AddAttribute@OTelLogRecord@Diagnostics@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; Diagnostics::OTelLogRecord::AddAttribute(std::wstring_view,std::wstring_view)
0x180031dca  nop
0x180031dcb  lea     rcx, [rsp+0B88h+var_6A8]
0x180031dd3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180031dd8  xor     eax, eax
0x180031dda  mov     [rsp+0B88h+var_700], rax
0x180031de2  mov     [rsp+0B88h+var_6F8], eax
0x180031de9  mov     rcx, [r13+28h]
0x180031ded  mov     rax, [rcx]
0x180031df0  lea     rdx, [rsp+0B88h+var_700]
0x180031df8  mov     rax, [rax+38h]
0x180031dfc  call    _guard_dispatch_icall
0x180031e01  test    eax, eax
0x180031e03  js      short loc_180031E80
0x180031e05  mov     edx, [rsp+0B88h+var_6F8]
0x180031e0c  lea     rcx, [rsp+0B88h+var_6A8]
0x180031e14  call    ?to_wstring@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@H@Z; std::to_wstring(int)
0x180031e19  nop
0x180031e1a  mov     rcx, rax
0x180031e1d  cmp     [rax+18h], r15
0x180031e21  jbe     short loc_180031E26
0x180031e23  mov     rcx, [rax]
0x180031e26  mov     [rsp+0B88h+var_788], rcx
0x180031e2e  mov     rax, [rax+10h]
0x180031e32  mov     [rsp+0B88h+var_780], rax
0x180031e3a  lea     rax, aAttentionRequi; "Attention_Required"
0x180031e41  mov     [rsp+0B88h+var_778], rax
0x180031e49  mov     [rsp+0B88h+var_770], 12h
0x180031e55  lea     r8, [rsp+0B88h+var_788]
0x180031e5d  lea     rdx, [rsp+0B88h+var_778]
0x180031e65  lea     rcx, [rsp+0B88h+var_4A8]
0x180031e6d  call    ?AddAttribute@OTelLogRecord@Diagnostics@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; Diagnostics::OTelLogRecord::AddAttribute(std::wstring_view,std::wstring_view)
0x180031e72  nop
0x180031e73  lea     rcx, [rsp+0B88h+var_6A8]
0x180031e7b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180031e80  mov     [rsp+0B88h+var_640], rsi
0x180031e88  mov     rcx, [r13+28h]
0x180031e8c  mov     rax, [rcx]
0x180031e8f  lea     rdx, [rsp+0B88h+var_640]
0x180031e97  mov     rax, [rax+40h]
0x180031e9b  call    _guard_dispatch_icall
0x180031ea0  test    eax, eax
0x180031ea2  js      loc_180031F97
0x180031ea8  cmp     dword ptr [rsp+0B88h+var_640], esi
0x180031eaf  jnz     short loc_180031EBE
0x180031eb1  cmp     dword ptr [rsp+0B88h+var_640+4], esi
0x180031eb8  jz      loc_180031F97
0x180031ebe  xorps   xmm0, xmm0
0x180031ec1  movups  [rsp+0B88h+var_738], xmm0
0x180031ec9  xorps   xmm1, xmm1
0x180031ecc  movdqu  [rsp+0B88h+var_728], xmm1
0x180031ed5  mov     r8d, 11h
0x180031edb  lea     rdx, aInvalidFileTim; "INVALID_FILE_TIME"
0x180031ee2  lea     rcx, [rsp+0B88h+var_738]
0x180031eea  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180031eef  nop
0x180031ef0  lea     r8, [rsp+0B88h+var_738]
0x180031ef8  lea     rdx, [rsp+0B88h+var_640]
0x180031f00  lea     rcx, [rsp+0B88h+var_6A8]
0x180031f08  call    ?FileTime_NoThrow@DataStyles@Diagnostics@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBU_FILETIME@@AEBV34@@Z; Diagnostics::DataStyles::FileTime_NoThrow(_FILETIME const &,std::wstring const &)
0x180031f0d  nop
0x180031f0e  lea     rcx, [rsp+0B88h+var_738]
0x180031f16  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180031f1b  mov     rcx, qword ptr [rsp+0B88h+var_698]
0x180031f23  test    rcx, rcx
0x180031f26  jz      short loc_180031F8A
0x180031f28  lea     rax, [rsp+0B88h+var_6A8]
0x180031f30  cmp     qword ptr [rsp+0B88h+var_698+8], r15
0x180031f38  cmova   rax, qword ptr [rsp+0B88h+var_6A8]
0x180031f41  mov     [rsp+0B88h+var_788], rax
0x180031f49  mov     [rsp+0B88h+var_780], rcx
0x180031f51  lea     rax, aLastSuccessful; "Last_Successful_Scan"
0x180031f58  mov     [rsp+0B88h+var_778], rax
0x180031f60  mov     [rsp+0B88h+var_770], 14h
0x180031f6c  lea     r8, [rsp+0B88h+var_788]
0x180031f74  lea     rdx, [rsp+0B88h+var_778]
0x180031f7c  lea     rcx, [rsp+0B88h+var_4A8]
0x180031f84  call    ?AddAttribute@OTelLogRecord@Diagnostics@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; Diagnostics::OTelLogRecord::AddAttribute(std::wstring_view,std::wstring_view)
0x180031f89  nop
0x180031f8a  lea     rcx, [rsp+0B88h+var_6A8]
0x180031f92  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180031f97  lea     rdx, [rsp+0B88h+var_4A8]; struct Diagnostics::OTelLogRecord *
0x180031f9f  lea     rcx, [rsp+0B88h+var_358]; this
0x180031fa7  call    ?AppendLogRecord@OTelFile@Diagnostics@@QEAAXAEBVOTelLogRecord@2@@Z; Diagnostics::OTelFile::AppendLogRecord(Diagnostics::OTelLogRecord const &)
0x180031fac  mov     [rsp+0B88h+var_680], rsi
0x180031fb4  mov     rcx, [r13+28h]
0x180031fb8  mov     rax, [rcx]
0x180031fbb  mov     [rsp+0B88h+var_680], rsi
0x180031fc3  lea     rdx, [rsp+0B88h+var_680]
0x180031fcb  mov     rax, [rax+30h]
0x180031fcf  call    _guard_dispatch_icall
0x180031fd4  test    eax, eax
0x180031fd6  js      loc_180033929
0x180031fdc  mov     rcx, [rsp+0B88h+var_680]
0x180031fe4  test    rcx, rcx
0x180031fe7  jz      loc_180033931
0x180031fed  mov     [rsp+0B88h+var_668], esi
0x180031ff4  mov     rax, [rcx]
0x180031ff7  lea     rdx, [rsp+0B88h+var_668]
0x180031fff  mov     rax, [rax+20h]
0x180032003  call    _guard_dispatch_icall
0x180032008  test    eax, eax
0x18003200a  js      loc_180033929
0x180032010  xorps   xmm0, xmm0
0x180032013  movups  [rsp+0B88h+var_638], xmm0
0x18003201b  mov     [rsp+0B88h+var_628], rsi
0x180032023  mov     [rsp+0B88h+var_620], rsi
0x18003202b  mov     r8, rdi
0x18003202e  inc     r8
0x180032031  cmp     [rbx+r8*2], si
0x180032036  jnz     short loc_18003202E
0x180032038  mov     rdx, rbx
0x18003203b  lea     rcx, [rsp+0B88h+var_638]
0x180032043  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180032048  nop
0x180032049  mov     r8d, 12h
0x18003204f  mov     rdx, cs:off_1800B1760; ".ApplicableUpdates"
0x180032056  lea     rcx, [rsp+0B88h+var_638]; Src
0x18003205e  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::append(wchar_t const * const,unsigned __int64)
0x180032063  mov     edx, esi
0x180032065  mov     ebx, 8
0x18003206a  xorps   xmm7, xmm7
0x18003206d  mov     [rsp+0B88h+var_B64], edx
0x180032071  cmp     edx, [rsp+0B88h+var_668]
0x180032078  jnb     loc_18003391C
0x18003207e  mov     [rsp+0B88h+var_6B0], rsi
0x180032086  mov     rcx, [rsp+0B88h+var_680]
0x18003208e  mov     rax, [rcx]
0x180032091  mov     [rsp+0B88h+var_6B0], rsi
0x180032099  lea     r8, [rsp+0B88h+var_6B0]
0x1800320a1  mov     rax, [rax+18h]
0x1800320a5  call    _guard_dispatch_icall
0x1800320aa  test    eax, eax
0x1800320ac  js      loc_18003380D
0x1800320b2  xor     edx, edx; Val
0x1800320b4  mov     r8d, 150h; Size
0x1800320ba  lea     rcx, [rsp+0B88h+var_5F8]; void *
0x1800320c2  call    memset
0x1800320c7  lea     rax, [rsp+0B88h+var_638]
0x1800320cf  cmp     [rsp+0B88h+var_620], r15
0x1800320d7  cmova   rax, qword ptr [rsp+0B88h+var_638]
0x1800320e0  movups  xmm0, xmmword ptr cs:?DefaultVersion@OTelLogRecord@Diagnostics@@0V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@B; std::wstring_view const Diagnostics::OTelLogRecord::DefaultVersion
0x1800320e7  movdqu  xmmword ptr [rsp+0B88h+Buffer], xmm0
0x1800320f0  mov     [rsp+0B88h+var_968], rax
0x1800320f8  mov     rax, [rsp+0B88h+var_628]
0x180032100  mov     [rsp+0B88h+var_960], rax
0x180032108  lea     r9, [rsp+0B88h+Buffer]
0x180032110  lea     r8, [rsp+0B88h+var_968]
  ... truncated ...
```
