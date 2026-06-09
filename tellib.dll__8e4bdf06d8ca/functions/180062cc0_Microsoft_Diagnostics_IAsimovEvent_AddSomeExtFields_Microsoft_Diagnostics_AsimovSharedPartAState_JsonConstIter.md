# Microsoft::Diagnostics::IAsimovEvent::AddSomeExtFields(Microsoft::Diagnostics::AsimovSharedPartAState &,JsonConstIterator,JsonConstIterator,ulong)

- ea: `0x180062cc0`
- end: `0x180065de3`
- name: `?AddSomeExtFields@IAsimovEvent@Diagnostics@Microsoft@@AEAAXAEAVAsimovSharedPartAState@23@VJsonConstIterator@@1K@Z`
- size: `12579`
- prototype: ``
- caller_count: `1`
- callee_count: `72`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18002dc48`

## callees

- `0x180015030`
- `0x18001c210`
- `0x18001d160`
- `0x18001d200`
- `0x18001e638`
- `0x18001f1fc`
- `0x18001f654`
- `0x180020c1c`
- `0x180020fbc`
- `0x180024e2c`
- `0x180024ef8`
- `0x18002d770`
- `0x18002ef74`
- `0x1800326cc`
- `0x18003f14c`
- `0x18003f4e8`
- `0x18003f600`
- `0x18003fd8c`
- `0x18003fe04`
- `0x180040454`
- `0x180043070`
- `0x1800434bc`
- `0x180044d20`
- `0x180044e2c`
- `0x1800498f0`
- `0x180049998`
- `0x18004c234`
- `0x18004c530`
- `0x18004cdf0`
- `0x18004d3ec`
- `0x18004dcf0`
- `0x18004e920`
- `0x18004f774`
- `0x1800507c8`
- `0x1800517d0`
- `0x180054374`
- `0x180054db0`
- `0x180055e08`
- `0x180059478`
- `0x180062cc0`
- `0x18006c624`
- `0x180080054`
- `0x1800817cc`
- `0x18009d3ec`
- `0x1800a0d08`
- `0x1800aac70`
- `0x1800ac770`
- `0x1800ace10`
- `0x1800b0628`
- `0x1800ceab0`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x180064c2c`
- `msvcp_win!_Mtx_unlock` at `0x180064dac`
- `msvcp_win!_Mtx_unlock` at `0x180064f5f`
- `msvcp_win!_Mtx_unlock` at `0x18006511b`
- `msvcp_win!_Mtx_unlock` at `0x180065ae8`
- `msvcp_win!_Mtx_unlock` at `0x180064c2c`
- `msvcp_win!_Mtx_unlock` at `0x180064dac`
- `msvcp_win!_Mtx_unlock` at `0x180064f5f`
- `msvcp_win!_Mtx_unlock` at `0x18006511b`
- `msvcp_win!_Mtx_unlock` at `0x180065ae8`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18006442a`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18006442a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180064262`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180064262`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180064234`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180064279`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180064336`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180064234`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180064279`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180064336`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x180065259`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x180065259`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x18006544a`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x18006544a`

## string_xrefs

- `0x180063d03`: `protocol`
- `0x180065d95`: `onecore\base\telemetry\utc\service\include\LifetimeManager.h`
- `0x180065da7`: `onecore\base\telemetry\utc\service\include\LifetimeManager.h`
- `0x180065db9`: `onecore\base\telemetry\utc\service\include\LifetimeManager.h`
- `0x180064e65`: `onecore\base\telemetry\utc\service\asimov\asimovsharedpartastate.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=28
void __fastcall Microsoft::Diagnostics::IAsimovEvent::AddSomeExtFields(
        __int64 a1,
        __int64 a2,
        _OWORD *a3,
        wchar_t *a4,
        unsigned int a5)
{
  wchar_t *v5; // r15
  _OWORD *v6; // r14
  unsigned int v9; // edi
  int v10; // esi
  struct _Mtx_internal_imp_t *v11; // rdx
  struct _Mtx_internal_imp_t *v12; // r8
  _QWORD *v13; // rax
  _QWORD *v14; // rcx
  _QWORD *v15; // rax
  ULONGLONG v16; // r9
  __int64 UserId; // rax
  const struct std::nothrow_t *v18; // rdx
  void *Ptr; // rcx
  unsigned __int64 v20; // rbx
  void **v21; // rcx
  unsigned __int64 v22; // r8
  _WORD *v23; // rdi
  unsigned __int64 v24; // rbx
  size_t v25; // rbx
  unsigned __int64 v26; // rsi
  size_t v27; // rcx
  void *v28; // rax
  _QWORD *v29; // r14
  size_t v30; // rbx
  __int64 v31; // rax
  const struct std::nothrow_t *v32; // rdx
  void *v33; // rcx
  const struct std::nothrow_t *v34; // rdx
  void *v35; // rcx
  int v36; // r8d
  gsl::details *v37; // rcx
  ULONGLONG v38; // rax
  unsigned __int64 v39; // rbx
  unsigned __int64 v40; // r8
  _WORD *v41; // rdi
  unsigned __int64 v42; // rbx
  size_t v43; // rbx
  unsigned __int64 v44; // r14
  size_t v45; // rcx
  void *v46; // rax
  _QWORD *v47; // r15
  size_t v48; // rbx
  __int64 v49; // rax
  int v50; // r8d
  const struct std::nothrow_t *v51; // rdx
  void *v52; // rcx
  __int64 v53; // rdi
  struct _EVENT_DATA_DESCRIPTOR *v54; // rax
  int v55; // r8d
  unsigned int v56; // eax
  __int64 v57; // r11
  __int64 v58; // r8
  __int64 v59; // r9
  __int64 v60; // r8
  __int64 v61; // r9
  __int64 v62; // r10
  unsigned __int64 v63; // rdx
  __int64 v64; // rax
  unsigned __int64 v65; // rcx
  __int64 v66; // rcx
  _BYTE *v67; // rdi
  unsigned __int64 v68; // r8
  __int64 v69; // rdi
  __int64 v70; // r11
  __int64 v71; // r8
  __int64 v72; // r9
  __int64 v73; // r8
  __int64 v74; // r9
  __int64 v75; // r10
  unsigned __int64 v76; // rdx
  __int64 v77; // r8
  __int64 v78; // r9
  __int64 v79; // r8
  __int64 v80; // r9
  unsigned __int64 v81; // rdx
  unsigned __int64 v82; // rbx
  size_t v83; // rbx
  unsigned __int64 v84; // r14
  size_t v85; // rcx
  void *v86; // rax
  _QWORD *v87; // r15
  size_t v88; // rbx
  __int64 v89; // rax
  int v90; // r8d
  const struct std::nothrow_t *v91; // rdx
  void *v92; // rcx
  struct _EVENT_DATA_DESCRIPTOR *v93; // rax
  const struct std::nothrow_t *v94; // rdx
  void *v95; // rcx
  __int64 v96; // rcx
  __int64 v97; // rdx
  _QWORD *v98; // rbx
  int v99; // r8d
  ULONGLONG v100; // rax
  _QWORD *v101; // rax
  ULONGLONG v102; // rcx
  char IsEnabled; // al
  int v104; // ecx
  struct Microsoft::Diagnostics::UserManager *UserManager; // rax
  void *OmittedId; // rax
  __int64 v107; // rax
  const struct _GUID *v108; // rax
  struct Microsoft::Diagnostics::UserManager *v109; // rax
  void *v110; // rax
  __int64 v111; // rax
  void **v112; // rax
  const char *v113; // r9
  __int64 v114; // rax
  __int64 v115; // rbx
  struct _Mtx_internal_imp_t *v116; // r15
  struct _Mtx_internal_imp_t *v117; // r14
  __int64 v118; // rbx
  __int64 v119; // rax
  __int64 *CachedGroupInfo; // rax
  __int64 v121; // rdx
  _QWORD *v122; // rax
  _QWORD *v123; // rbx
  const char *v124; // r9
  ULONGLONG v125; // rbx
  ULONGLONG v126; // rax
  __int64 v127; // rbx
  ULONGLONG TickCount64; // rax
  __int64 v129; // rdx
  wchar_t *v130; // r14
  gsl::details *v131; // rcx
  ULONGLONG Keyword; // rbx
  unsigned __int64 v133; // rdx
  struct _Mtx_internal_imp_t *p_UserData; // rax
  __int64 v135; // rbx
  void *v136; // rax
  __int64 v137; // rax
  __int64 v138; // rdx
  void *v139; // rax
  __int64 v140; // r14
  __int64 v141; // rdi
  unsigned int v142; // ebx
  char v143; // r15
  __int64 v144; // rcx
  struct _EVENT_DATA_DESCRIPTOR *v145; // xmm6_8
  __m128i v146; // xmm7
  struct _EVENT_DATA_DESCRIPTOR *v147; // rdx
  const char *v148; // r9
  void *v149; // rbx
  _QWORD *ProviderBinaryPath; // rax
  void *v151; // rax
  char v152; // bl
  _QWORD *v153; // rcx
  _QWORD *v154; // r15
  unsigned __int64 v155; // r14
  unsigned __int64 v156; // rbx
  size_t v157; // rax
  void *v158; // rax
  void *v159; // rcx
  _QWORD *v160; // rax
  struct _EVENT_DATA_DESCRIPTOR *v161; // rcx
  int DeviceId; // eax
  void *v163; // rdx
  wchar_t *v164; // rbx
  __int64 v165; // r8
  _QWORD *v166; // rbx
  unsigned __int64 v167; // r14
  __int64 v168; // rcx
  unsigned __int64 v169; // rax
  int v170; // esi
  __int64 v171; // rax
  void *v172; // rax
  __int64 v173; // rax
  void **v174; // rax
  _QWORD *v175; // r14
  unsigned __int64 v176; // rbx
  __int64 v177; // rcx
  unsigned __int64 v178; // r15
  struct _EVENT_DATA_DESCRIPTOR *v179; // r14
  unsigned __int64 v180; // rax
  struct _EVENT_DATA_DESCRIPTOR *v181; // rax
  int v182; // r9d
  const struct _GUID *v183; // rax
  void *v184; // rax
  __int128 v185; // xmm6
  __int64 v186; // rdx
  ULONGLONG v187; // rax
  _OWORD *v188; // rsi
  CONTEXT *v189; // rbx
  __int64 v190; // r8
  __int64 v191; // rax
  void *v192; // rax
  struct _EVENT_DATA_DESCRIPTOR **v193; // rsi
  unsigned __int64 v194; // rbx
  struct _EVENT_DATA_DESCRIPTOR *v195; // r14
  __int64 v196; // rcx
  void *v197; // rax
  unsigned __int64 v198; // rax
  unsigned __int64 v199; // rbx
  __int64 v200; // rcx
  unsigned __int64 v201; // r14
  struct _EVENT_DATA_DESCRIPTOR *v202; // r15
  unsigned __int64 v203; // rax
  struct _EVENT_DATA_DESCRIPTOR *v204; // rcx
  struct _EVENT_DATA_DESCRIPTOR **v205; // rsi
  unsigned __int64 v206; // rbx
  struct _EVENT_DATA_DESCRIPTOR *v207; // r14
  __int64 v208; // rcx
  unsigned __int64 v209; // rax
  unsigned __int64 v210; // rbx
  unsigned __int64 v211; // r14
  struct _EVENT_DATA_DESCRIPTOR *v212; // r15
  __int64 v213; // rcx
  struct _EVENT_DATA_DESCRIPTOR *v214; // rcx
  struct _EVENT_DATA_DESCRIPTOR **v215; // rsi
  unsigned __int64 v216; // rbx
  struct _EVENT_DATA_DESCRIPTOR *v217; // r14
  __int64 v218; // rcx
  unsigned __int64 v219; // rbx
  unsigned __int64 v220; // r14
  struct _EVENT_DATA_DESCRIPTOR *v221; // r15
  __int64 v222; // rcx
  struct _EVENT_DATA_DESCRIPTOR *v223; // rcx
  __int64 v224; // rax
  struct _Mtx_internal_imp_t *v225; // rbx
  struct _Mtx_internal_imp_t *v226; // rax
  ULONGLONG v227; // rcx
  __int128 v228; // xmm6
  __int64 *v229; // rcx
  ULONGLONG v230; // rdx
  __int64 *v231; // rcx
  int UserDataCount; // [rsp+28h] [rbp-E0h]
  _Mtx_t v233[2]; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v234; // [rsp+58h] [rbp-B0h] BYREF
  wchar_t *v235; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v236; // [rsp+70h] [rbp-98h]
  _QWORD v237[2]; // [rsp+78h] [rbp-90h] BYREF
  unsigned __int64 v238[2]; // [rsp+88h] [rbp-80h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+98h] [rbp-70h] BYREF
  __int64 v240; // [rsp+A8h] [rbp-60h]
  unsigned __int64 v241; // [rsp+B0h] [rbp-58h]
  struct _EVENT_DATA_DESCRIPTOR v242; // [rsp+B8h] [rbp-50h] BYREF
  __int128 v243; // [rsp+C8h] [rbp-40h]
  int v244; // [rsp+D8h] [rbp-30h]
  __int64 v245; // [rsp+E0h] [rbp-28h]
  void *v246[2]; // [rsp+E8h] [rbp-20h] BYREF
  __int64 v247; // [rsp+F8h] [rbp-10h]
  unsigned __int64 v248; // [rsp+100h] [rbp-8h]
  _Mtx_t v249[4]; // [rsp+108h] [rbp+0h] BYREF
  int v250[4]; // [rsp+128h] [rbp+20h] BYREF
  void *Src[2]; // [rsp+148h] [rbp+40h] BYREF
  unsigned __int64 v252; // [rsp+158h] [rbp+50h]
  unsigned __int64 v253; // [rsp+160h] [rbp+58h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+168h] [rbp+60h] BYREF
  __int128 v255; // [rsp+178h] [rbp+70h]
  _QWORD v256[13]; // [rsp+188h] [rbp+80h] BYREF
  _BYTE v257[48]; // [rsp+1F2h] [rbp+EAh] BYREF
  _BYTE v258[48]; // [rsp+222h] [rbp+11Ah] BYREF
  _BYTE v259[6]; // [rsp+252h] [rbp+14Ah] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D0h] [rbp+1C8h]

  v5 = a4;
  v235 = a4;
  v6 = a3;
  v237[0] = a3;
  v9 = a5;
  LODWORD(v236) = a5;
  v10 = 0;
  LODWORD(v238[0]) = 0;
  LODWORD(v246[0]) = 0;
  *(_OWORD *)Src = 0;
  v252 = 0;
  v253 = 7;
  LOWORD(Src[0]) = 0;
  if ( (unsigned __int8)(*(_BYTE *)(a1 + 288) - 1) <= 2u )
    goto LABEL_57;
  v11 = (struct _Mtx_internal_imp_t *)(a1 + 304);
  v12 = *(struct _Mtx_internal_imp_t **)(a1 + 320);
  if ( !v12 )
    goto LABEL_57;
  v13 = *(_QWORD **)(a1 + 440);
  v14 = &unk_18043B3B0;
  if ( v13 )
    v14 = v13;
  if ( v14[3] <= 7u )
    v15 = v14;
  else
    v15 = (_QWORD *)*v14;
  v16 = v14[2];
  if ( *((_QWORD *)v11 + 3) > 7u )
    v11 = *(struct _Mtx_internal_imp_t **)v11;
  *(_QWORD *)&EventDescriptor.Id = v15;
  EventDescriptor.Keyword = v16;
  v233[0] = v11;
  v233[1] = v12;
  UserId = Microsoft::Diagnostics::AsimovSharedPartAState::GetUserId(a2, &UserData, v233, &EventDescriptor);
  std::wstring::operator=(Src, UserId);
  if ( *((_QWORD *)&v255 + 1) > 7u )
  {
    v18 = (const struct std::nothrow_t *)(2LL * *((_QWORD *)&v255 + 1) + 2);
    Ptr = (void *)UserData.Ptr;
    if ( (unsigned __int64)v18 >= 0x1000 )
    {
      if ( UserData.Ptr - *(_QWORD *)(UserData.Ptr - 8) - 8 > 0x1F )
        goto LABEL_144;
      v18 = (const struct std::nothrow_t *)(2LL * *((_QWORD *)&v255 + 1) + 41);
      Ptr = *(void **)(UserData.Ptr - 8);
    }
    operator delete(Ptr, v18);
  }
  *(_QWORD *)&v255 = 0;
  *((_QWORD *)&v255 + 1) = 7;
  LOWORD(UserData.Ptr) = 0;
  if ( (*(_BYTE *)(a1 + 696) & 2) == 0 )
    goto LABEL_57;
  v20 = v252;
  v21 = Src;
  if ( v253 > 7 )
    v21 = (void **)Src[0];
  if ( v252 == -1 )
    goto LABEL_427;
  if ( v21 )
  {
    if ( v252 >= 0x7FFFFFFFFFFFFFFFLL )
      goto LABEL_427;
    v20 = 2 * v252;
  }
  else if ( v252 )
  {
    goto LABEL_427;
  }
  v238[0] = a5;
  v246[0] = (void *)a5;
  SpookyHash::Hash128(v21, v20, (unsigned __int64 *)v246, v238);
  v22 = (unsigned __int64)v246[0];
  if ( v20 < 0x10 )
    v22 = (unsigned __int64)v246[0] >> (63 - 4 * (unsigned __int8)v20);
  v23 = v257;
  do
  {
    *--v23 = v22 % 0xA + 48;
    v22 /= 0xAu;
  }
  while ( v22 );
  EventDescriptor = 0;
  v240 = 0;
  v241 = 0;
  if ( v23 != (_WORD *)v257 )
  {
    v24 = (v257 - (_BYTE *)v23) >> 1;
    if ( v24 > 0x7FFFFFFFFFFFFFFELL )
      std::_Xlen_string();
    if ( v24 <= 7 )
    {
      v240 = (v257 - (_BYTE *)v23) >> 1;
      v241 = 7;
      v25 = 2 * v24;
      memcpy_0(&EventDescriptor, v23, v25);
      *(USHORT *)((char *)&EventDescriptor.Id + v25) = 0;
      goto LABEL_46;
    }
    v26 = v24 | 7;
    if ( (v24 | 7) <= 0x7FFFFFFFFFFFFFFELL )
    {
      if ( v26 < 0xA )
        v26 = 10;
      if ( v26 + 1 > 0x7FFFFFFFFFFFFFFFLL )
        goto LABEL_431;
      v27 = 2 * (v26 + 1);
      if ( !v27 )
      {
        v29 = 0;
        goto LABEL_45;
      }
    }
    else
    {
      v26 = 0x7FFFFFFFFFFFFFFELL;
      v27 = -2;
    }
    if ( v27 >= 0x1000 )
    {
      if ( v27 + 39 >= v27 )
      {
        v28 = operator new(v27 + 39);
        if ( !v28 )
          goto LABEL_144;
        v29 = (_QWORD *)(((unsigned __int64)v28 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
        *(v29 - 1) = v28;
        goto LABEL_45;
      }
LABEL_431:
      std::_Throw_bad_array_new_length();
    }
    v29 = operator new(v27);
LABEL_45:
    *(_QWORD *)&EventDescriptor.Id = v29;
    v240 = (v257 - (_BYTE *)v23) >> 1;
    v241 = v26;
    v30 = 2 * v24;
    memcpy_0(v29, v23, v30);
    *(_WORD *)((char *)v29 + v30) = 0;
    v6 = (_OWORD *)v237[0];
    goto LABEL_46;
  }
  v240 = 0;
  v241 = 7;
  EventDescriptor.Id = 0;
LABEL_46:
  v31 = std::wstring::_Insert<wchar_t>(&EventDescriptor);
  UserData = *(struct _EVENT_DATA_DESCRIPTOR *)v31;
  v255 = *(_OWORD *)(v31 + 16);
  *(_QWORD *)(v31 + 16) = 0;
  *(_QWORD *)(v31 + 24) = 7;
  *(_WORD *)v31 = 0;
  v10 = 7;
  LODWORD(v238[0]) = 7;
  std::wstring::operator=(Src, &UserData);
  if ( *((_QWORD *)&v255 + 1) > 7u )
  {
    v32 = (const struct std::nothrow_t *)(2LL * *((_QWORD *)&v255 + 1) + 2);
    v33 = (void *)UserData.Ptr;
    if ( (unsigned __int64)v32 >= 0x1000 )
    {
      if ( UserData.Ptr - *(_QWORD *)(UserData.Ptr - 8) - 8 > 0x1F )
        __fastfail(5u);
      v32 = (const struct std::nothrow_t *)(2LL * *((_QWORD *)&v255 + 1) + 41);
      v33 = *(void **)(UserData.Ptr - 8);
    }
    operator delete(v33, v32);
  }
  if ( v241 > 7 )
  {
    v34 = (const struct std::nothrow_t *)(2 * v241 + 2);
    v35 = *(void **)&EventDescriptor.Id;
    if ( (unsigned __int64)v34 >= 0x1000 )
    {
      if ( (unsigned __int64)(*(_QWORD *)&EventDescriptor.Id - *(_QWORD *)(*(_QWORD *)&EventDescriptor.Id - 8LL) - 8LL) > 0x1F )
        goto LABEL_144;
      v34 = (const struct std::nothrow_t *)(2 * v241 + 41);
      v35 = *(void **)(*(_QWORD *)&EventDescriptor.Id - 8LL);
    }
    operator delete(v35, v34);
  }
  v240 = 0;
  v241 = 7;
  EventDescriptor.Id = 0;
  v9 = v236;
LABEL_57:
  *(_QWORD *)&EventDescriptor.Id = L"device";
  EventDescriptor.Keyword = 6;
  *(_OWORD *)v249 = *v6;
  Microsoft::Diagnostics::IAsimovEvent::CreateOrGetExtensionObject(a1, v233, v249, &EventDescriptor);
  if ( *(_QWORD *)(a2 + 48) <= 7u )
    v37 = (gsl::details *)(a2 + 24);
  else
    v37 = *(gsl::details **)(a2 + 24);
  if ( (unsigned __int8)(*(_BYTE *)(a1 + 288) - 1) <= 1u )
  {
    v56 = *(_DWORD *)(a2 + 1088);
    v57 = 312;
    if ( v56 == 312 )
    {
      do
      {
        v58 = *(_QWORD *)(a2 + 8 * v57 - 1392);
        *(_QWORD *)(a2 + 8 * v57 + 1096) = ((v58 ^ (*(_QWORD *)(a2 + 8 * v57 - 1400) ^ v58) & 0xFFFFFFFF80000000uLL) >> 1)
                                         ^ *(_QWORD *)(a2 + 8 * v57 - 152)
                                         ^ -(__int64)((v58 & 1) != 0)
                                         & 0xB5026F5AA96619E9uLL;
        v59 = *(_QWORD *)(a2 + 8 * v57 - 1384);
        *(_QWORD *)(a2 + 8 * v57 + 1104) = ((v59 ^ (v58 ^ v59) & 0xFFFFFFFF80000000uLL) >> 1)
                                         ^ *(_QWORD *)(a2 + 8 * v57 - 144)
                                         ^ -(__int64)((v59 & 1) != 0)
                                         & 0xB5026F5AA96619E9uLL;
        v60 = *(_QWORD *)(a2 + 8 * v57 - 1376);
        *(_QWORD *)(a2 + 8 * v57 + 1112) = ((v60 ^ (v59 ^ v60) & 0xFFFFFFFF80000000uLL) >> 1)
                                         ^ *(_QWORD *)(a2 + 8 * v57 - 136)
                                         ^ -(__int64)((v60 & 1) != 0)
                                         & 0xB5026F5AA96619E9uLL;
        v61 = *(_QWORD *)(a2 + 8 * v57 - 1368);
        *(_QWORD *)(a2 + 8 * v57 + 1120) = ((v61 ^ (v60 ^ v61) & 0xFFFFFFFF80000000uLL) >> 1)
                                         ^ *(_QWORD *)(a2 + 8 * v57 - 128)
                                         ^ -(__int64)((v61 & 1) != 0)
                                         & 0xB5026F5AA96619E9uLL;
        v62 = *(_QWORD *)(a2 + 8 * v57 - 1360);
        *(_QWORD *)(a2 + 8 * v57 + 1128) = ((v62 ^ (v61 ^ v62) & 0xFFFFFFFF80000000uLL) >> 1)
                                         ^ *(_QWORD *)(a2 + 8 * v57 - 120)
                                         ^ -(__int64)((v62 & 1) != 0)
                                         & 0xB5026F5AA96619E9uLL;
        v63 = v57 + 6;
        *(_QWORD *)(a2 + 8 * v63 + 1088) = ((*(_QWORD *)(a2 + 8 * v57 - 1352)
                                           ^ (v62
                                            ^ *(_QWORD *)(a2 + 8 * v57 - 1352))
                                           & 0xFFFFFFFF80000000uLL) >> 1)
                                         ^ *(_QWORD *)(a2 + 8 * v57 - 112)
                                         ^ -(__int64)((*(_BYTE *)(a2 + 8 * v57 - 1352) & 1) != 0)
                                         & 0xB5026F5AA96619E9uLL;
        v57 += 6;
      }
      while ( v63 < 0x270 );
    }
    else if ( v56 >= 0x270 )
    {
      v69 = 0;
      v70 = 156;
      do
      {
        v71 = *(_QWORD *)(a2 + 8 * v69 + 3600);
        *(_QWORD *)(a2 + 8 * v69 + 1096) = ((v71 ^ (*(_QWORD *)(a2 + 8 * v69 + 3592) ^ v71) & 0xFFFFFFFF80000000uLL) >> 1)
                                         ^ *(_QWORD *)(a2 + 8 * v69 + 4840)
                                         ^ -(__int64)((v71 & 1) != 0)
                                         & 0xB5026F5AA96619E9uLL;
        v72 = *(_QWORD *)(a2 + 8 * v69 + 3608);
        *(_QWORD *)(a2 + 8 * v69 + 1104) = ((v72 ^ (v71 ^ v72) & 0xFFFFFFFF80000000uLL) >> 1)
                                         ^ *(_QWORD *)(a2 + 8 * v69 + 4848)
                                         ^ -(__int64)((v72 & 1) != 0)
                                         & 0xB5026F5AA96619E9uLL;
        v73 = *(_QWORD *)(a2 + 8 * v69 + 3616);
        *(_QWORD *)(a2 + 8 * v69 + 1112) = ((v73 ^ (v72 ^ v73) & 0xFFFFFFFF80000000uLL) >> 1)
                                         ^ *(_QWORD *)(a2 + 8 * v69 + 4856)
                                         ^ -(__int64)((v73 & 1) != 0)
                                         & 0xB5026F5AA96619E9uLL;
        v74 = *(_QWORD *)(a2 + 8 * v69 + 3624);
        *(_QWORD *)(a2 + 8 * v69 + 1120) = ((v74 ^ (v73 ^ v74) & 0xFFFFFFFF80000000uLL) >> 1)
                                         ^ *(_QWORD *)(a2 + 8 * v69 + 4864)
                                         ^ -(__int64)((v74 & 1) != 0)
                                         & 0xB5026F5AA96619E9uLL;
        v75 = *(_QWORD *)(a2 + 8 * v69 + 3632);
        *(_QWORD *)(a2 + 8 * v69 + 1128) = ((v75 ^ (v74 ^ v75) & 0xFFFFFFFF80000000uLL) >> 1)
                                         ^ *(_QWORD *)(a2 + 8 * v69 + 4872)
                                         ^ -(__int64)((v75 & 1) != 0)
                                         & 0xB5026F5AA96619E9uLL;
        v76 = v69 + 6;
        *(_QWORD *)(a2 + 8 * v76 + 1088) = ((*(_QWORD *)(a2 + 8 * v69 + 3640)
                                           ^ (v75
                                            ^ *(_QWORD *)(a2 + 8 * v69 + 3640))
                                           & 0xFFFFFFFF80000000uLL) >> 1)
                                         ^ *(_QWORD *)(a2 + 8 * v69 + 4880)
                                         ^ -(__int64)((*(_BYTE *)(a2 + 8 * v69 + 3640) & 1) != 0)
                                         & 0xB5026F5AA96619E9uLL;
        v69 += 6;
      }
      while ( v76 < 0x9C );
      do
      {
        v77 = *(_QWORD *)(a2 + 8 * v70 + 3600);
        *(_QWORD *)(a2 + 8 * v70 + 1096) = ((v77 ^ (*(_QWORD *)(a2 + 8 * v70 + 3592) ^ v77) & 0xFFFFFFFF80000000uLL) >> 1)
                                         ^ *(_QWORD *)(a2 + 8 * v70 - 152)
                                         ^ -(__int64)((v77 & 1) != 0)
                                         & 0xB5026F5AA96619E9uLL;
        v78 = *(_QWORD *)(a2 + 8 * v70 + 3608);
        *(_QWORD *)(a2 + 8 * v70 + 1104) = ((v78 ^ (v77 ^ v78) & 0xFFFFFFFF80000000uLL) >> 1)
                                         ^ *(_QWORD *)(a2 + 8 * v70 - 144)
                                         ^ -(__int64)((v78 & 1) != 0)
                                         & 0xB5026F5AA96619E9uLL;
        v79 = *(_QWORD *)(a2 + 8 * v70 + 3616);
        *(_QWORD *)(a2 + 8 * v70 + 1112) = ((v79 ^ (v78 ^ v79) & 0xFFFFFFFF80000000uLL) >> 1)
                                         ^ *(_QWORD *)(a2 + 8 * v70 - 136)
                                         ^ -(__int64)((v79 & 1) != 0)
                                         & 0xB5026F5AA96619E9uLL;
        v80 = *(_QWORD *)(a2 + 8 * v70 + 3624);
        *(_QWORD *)(a2 + 8 * v70 + 1120) = ((v80 ^ (v79 ^ v80) & 0xFFFFFFFF80000000uLL) >> 1)
                                         ^ *(_QWORD *)(a2 + 8 * v70 - 128)
                                         ^ -(__int64)((v80 & 1) != 0)
                                         & 0xB5026F5AA96619E9uLL;
        v81 = v70 + 5;
        *(_QWORD *)(a2 + 8 * v81 + 1088) = ((*(_QWORD *)(a2 + 8 * v70 + 3632)
                                           ^ (v80
                                            ^ *(_QWORD *)(a2 + 8 * v70 + 3632))
                                           & 0xFFFFFFFF80000000uLL) >> 1)
                                         ^ *(_QWORD *)(a2 + 8 * v70 - 120)
                                         ^ -(__int64)((*(_BYTE *)(a2 + 8 * v70 + 3632) & 1) != 0)
                                         & 0xB5026F5AA96619E9uLL;
        v70 += 5;
      }
      while ( v81 < 0x137 );
      *(_QWORD *)(a2 + 3584) = ((*(_QWORD *)(a2 + 1096)
                               ^ (*(_QWORD *)(a2 + 6080)
                                ^ *(_QWORD *)(a2 + 1096))
                               & 0xFFFFFFFF80000000uLL) >> 1)
                             ^ *(_QWORD *)(a2 + 2336)
                             ^ -(__int64)((*(_BYTE *)(a2 + 1096) & 1) != 0)
                             & 0xB5026F5AA96619E9uLL;
      *(_DWORD *)(a2 + 1088) = 0;
    }
    v64 = *(unsigned int *)(a2 + 1088);
    v65 = *(_QWORD *)(a2 + 8 * v64 + 1096);
    *(_DWORD *)(a2 + 1088) = v64 + 1;
    v66 = v65
        ^ *(_QWORD *)(a2 + 6088)
        & (v65 >> 29)
        ^ (((v65 ^ *(_QWORD *)(a2 + 6088) & (v65 >> 29)) & 0x38EB3FFFF6D3LL) << 17);
    v67 = v259;
    v68 = v66 ^ ((v66 & 0xFFFFFFFFFFFFBF77uLL) << 37) ^ ((v66 ^ ((v66 & 0xFFFFFFFFFFFFBF77uLL) << 37)) >> 43);
    do
    {
      v67 -= 2;
      *(_WORD *)v67 = v68 % 0xA + 48;
      v68 /= 0xAu;
    }
    while ( v68 );
    *(_OWORD *)v246 = 0;
    v247 = 0;
    v248 = 0;
    v5 = v235;
    if ( v67 == v259 )
    {
      v247 = 0;
      v248 = 7;
      LOWORD(v246[0]) = 0;
      goto LABEL_128;
    }
    v82 = (v259 - v67) >> 1;
    if ( v82 > 0x7FFFFFFFFFFFFFFELL )
      std::_Xlen_string();
    if ( v82 <= 7 )
    {
      v247 = (v259 - v67) >> 1;
      v248 = 7;
      v83 = 2 * v82;
      memcpy_0(v246, v67, v83);
      *(_WORD *)((char *)v246 + v83) = 0;
      goto LABEL_128;
    }
    v84 = v82 | 7;
    if ( (v82 | 7) <= 0x7FFFFFFFFFFFFFFELL )
    {
      if ( v84 < 0xA )
        v84 = 10;
      if ( v84 + 1 > 0x7FFFFFFFFFFFFFFFLL )
        goto LABEL_429;
      v85 = 2 * (v84 + 1);
      if ( !v85 )
      {
        v87 = 0;
        goto LABEL_127;
      }
    }
    else
    {
      v84 = 0x7FFFFFFFFFFFFFFELL;
      v85 = -2;
    }
    if ( v85 >= 0x1000 )
    {
      if ( v85 + 39 >= v85 )
      {
        v86 = operator new(v85 + 39);
        if ( !v86 )
          goto LABEL_144;
        v87 = (_QWORD *)(((unsigned __int64)v86 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
        *(v87 - 1) = v86;
        goto LABEL_127;
      }
LABEL_429:
      std::_Throw_bad_array_new_length();
    }
    v87 = operator new(v85);
LABEL_127:
    v246[0] = v87;
    v247 = (v259 - v67) >> 1;
    v248 = v84;
    v88 = 2 * v82;
    memcpy_0(v87, v67, v88);
    *(_WORD *)((char *)v87 + v88) = 0;
    v5 = v235;
LABEL_128:
    v89 = std::wstring::_Insert<wchar_t>(v246);
    v242 = 0;
    v243 = 0u;
    v242 = *(struct _EVENT_DATA_DESCRIPTOR *)v89;
    v243 = *(_OWORD *)(v89 + 16);
    *(_QWORD *)(v89 + 16) = 0;
    *(_QWORD *)(v89 + 24) = 7;
    *(_WORD *)v89 = 0;
    v10 |= 0x38u;
    LODWORD(v238[0]) = v10;
    if ( v248 > 7 )
    {
      v91 = (const struct std::nothrow_t *)(2 * v248 + 2);
      v92 = v246[0];
      if ( (unsigned __int64)v91 >= 0x1000 )
      {
        if ( (unsigned __int64)v246[0] - *((_QWORD *)v246[0] - 1) - 8 > 0x1F )
          __fastfail(5u);
        v91 = (const struct std::nothrow_t *)(2 * v248 + 41);
        v92 = (void *)*((_QWORD *)v246[0] - 1);
      }
      operator delete(v92, v91);
    }
    v247 = 0;
    v248 = 7;
    LOWORD(v246[0]) = 0;
    v53 = a1 + 16;
    v93 = &v242;
    if ( *((_QWORD *)&v243 + 1) > 7u )
      v93 = (struct _EVENT_DATA_DESCRIPTOR *)v242.Ptr;
    *(_QWORD *)&EventDescriptor.Id = v93;
    EventDescriptor.Keyword = v243;
    v249[0] = (_Mtx_t)L"localId";
    v249[1] = (_Mtx_t)7;
    JsonImplementType<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>>::AddValue(
      (unsigned int)v250,
      a1 + 16,
      v90,
      (unsigned int)v233,
      (__int64)v249,
      (__int64)&EventDescriptor);
    if ( *((_QWORD *)&v243 + 1) > 7u )
    {
      v94 = (const struct std::nothrow_t *)(2LL * *((_QWORD *)&v243 + 1) + 2);
      v95 = (void *)v242.Ptr;
      if ( (unsigned __int64)v94 >= 0x1000 )
      {
        if ( v242.Ptr - *(_QWORD *)(v242.Ptr - 8) - 8 > 0x1F )
          goto LABEL_144;
        v94 = (const struct std::nothrow_t *)(2LL * *((_QWORD *)&v243 + 1) + 41);
        v95 = *(void **)(v242.Ptr - 8);
      }
      operator delete(v95, v94);
    }
    *(_QWORD *)&v243 = 0;
    *((_QWORD *)&v243 + 1) = 7;
    LOWORD(v242.Ptr) = 0;
    goto LABEL_141;
  }
  v38 = *(_QWORD *)(a2 + 40);
  if ( (*(_BYTE *)(a1 + 696) & 2) == 0 )
  {
    v53 = a1 + 16;
    *(_QWORD *)&EventDescriptor.Id = v37;
    EventDescriptor.Keyword = v38;
    v249[0] = (_Mtx_t)L"localId";
    v249[1] = (_Mtx_t)7;
    JsonImplementType<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>>::AddValue(
      (unsigned int)v250,
      a1 + 16,
      v36,
      (unsigned int)v233,
      (__int64)v249,
      (__int64)&EventDescriptor);
    goto LABEL_141;
  }
  if ( v38 == -1 )
    goto LABEL_434;
  if ( !v37 )
  {
    if ( !v38 )
    {
      v39 = 0;
      goto LABEL_69;
    }
LABEL_434:
    gsl::details::terminate(v37);
    __debugbreak();
  }
  if ( v38 >= 0x7FFFFFFFFFFFFFFFLL )
    goto LABEL_434;
  v39 = 2 * v38;
LABEL_69:
  v238[0] = v9;
  v246[0] = (void *)v9;
  SpookyHash::Hash128(v37, v39, (unsigned __int64 *)v246, v238);
  v40 = (unsigned __int64)v246[0];
  if ( v39 < 0x10 )
    v40 = (unsigned __int64)v246[0] >> (63 - 4 * (unsigned __int8)v39);
  v41 = v258;
  do
  {
    *--v41 = v40 % 0xA + 48;
    v40 /= 0xAu;
  }
  while ( v40 );
  *(_OWORD *)v246 = 0;
  v247 = 0;
  v248 = 0;
  v5 = v235;
  if ( v41 != (_WORD *)v258 )
  {
    v42 = (v258 - (_BYTE *)v41) >> 1;
    if ( v42 > 0x7FFFFFFFFFFFFFFELL )
      std::_Xlen_string();
    if ( v42 <= 7 )
    {
      v247 = (v258 - (_BYTE *)v41) >> 1;
      v248 = 7;
      v43 = 2 * v42;
      memcpy_0(v246, v41, v43);
      *(_WORD *)((char *)v246 + v43) = 0;
      goto LABEL_91;
    }
    v44 = v42 | 7;
    if ( (v42 | 7) <= 0x7FFFFFFFFFFFFFFELL )
    {
      if ( v44 < 0xA )
        v44 = 10;
      if ( v44 + 1 > 0x7FFFFFFFFFFFFFFFLL )
        goto LABEL_433;
      v45 = 2 * (v44 + 1);
      if ( !v45 )
      {
        v47 = 0;
        goto LABEL_90;
      }
    }
    else
    {
      v44 = 0x7FFFFFFFFFFFFFFELL;
      v45 = -2;
    }
    if ( v45 < 0x1000 )
    {
      v47 = operator new(v45);
      goto LABEL_90;
    }
    if ( v45 + 39 >= v45 )
    {
      v46 = operator new(v45 + 39);
      if ( v46 )
      {
        v47 = (_QWORD *)(((unsigned __int64)v46 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
        *(v47 - 1) = v46;
LABEL_90:
        v246[0] = v47;
        v247 = (v258 - (_BYTE *)v41) >> 1;
        v248 = v44;
        v48 = 2 * v42;
        memcpy_0(v47, v41, v48);
        *(_WORD *)((char *)v47 + v48) = 0;
        v5 = v235;
        goto LABEL_91;
      }
LABEL_144:
      __fastfail(5u);
    }
LABEL_433:
    std::_Throw_bad_array_new_length();
  }
  v247 = 0;
  v248 = 7;
  LOWORD(v246[0]) = 0;
LABEL_91:
  v49 = std::wstring::_Insert<wchar_t>(v246);
  v242 = 0;
  v243 = 0u;
  v242 = *(struct _EVENT_DATA_DESCRIPTOR *)v49;
  v243 = *(_OWORD *)(v49 + 16);
  *(_QWORD *)(v49 + 16) = 0;
  *(_QWORD *)(v49 + 24) = 7;
  *(_WORD *)v49 = 0;
  v10 |= 0x1C0u;
  LODWORD(v238[0]) = v10;
  if ( v248 > 7 )
  {
    v51 = (const struct std::nothrow_t *)(2 * v248 + 2);
    v52 = v246[0];
    if ( (unsigned __int64)v51 >= 0x1000 )
    {
      if ( (unsigned __int64)v246[0] - *((_QWORD *)v246[0] - 1) - 8 > 0x1F )
        __fastfail(5u);
      v51 = (const struct std::nothrow_t *)(2 * v248 + 41);
      v52 = (void *)*((_QWORD *)v246[0] - 1);
    }
    operator delete(v52, v51);
  }
  v247 = 0;
  v248 = 7;
  LOWORD(v246[0]) = 0;
  v53 = a1 + 16;
  v54 = &v242;
  if ( *((_QWORD *)&v243 + 1) > 7u )
    v54 = (struct _EVENT_DATA_DESCRIPTOR *)v242.Ptr;
  *(_QWORD *)&EventDescriptor.Id = v54;
  EventDescriptor.Keyword = v243;
  v249[0] = (_Mtx_t)L"localId";
  v249[1] = (_Mtx_t)7;
  JsonImplementType<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>>::AddValue(
    (unsigned int)v250,
    a1 + 16,
    v50,
    (unsigned int)v233,
    (__int64)v249,
    (__int64)&EventDescriptor);
  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)&v242);
LABEL_141:
  if ( *(_QWORD *)(a2 + 88) <= 7u )
    v96 = a2 + 64;
  else
    v96 = *(_QWORD *)(a2 + 64);
  *(_QWORD *)&EventDescriptor.Id = v96;
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 80);
  v249[0] = (_Mtx_t)L"deviceClass";
  v249[1] = (_Mtx_t)11;
  JsonImplementType<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>>::AddValue(
    (unsigned int)v250,
    v53,
    v55,
    (unsigned int)v233,
    (__int64)v249,
    (__int64)&EventDescriptor);
  v98 = (_QWORD *)(a2 + 96);
  if ( *(_QWORD *)(a2 + 112) || *(_QWORD *)(a2 + 144) )
  {
    *(_QWORD *)&EventDescriptor.Id = L"protocol";
    EventDescriptor.Keyword = 8;
    *(_OWORD *)v233 = *(_OWORD *)v237[0];
    Microsoft::Diagnostics::IAsimovEvent::CreateOrGetExtensionObject(a1, v249, v233, &EventDescriptor);
    v100 = *(_QWORD *)(a2 + 112);
    if ( v100 )
    {
      if ( *(_QWORD *)(a2 + 120) > 7u )
        v98 = (_QWORD *)*v98;
      *(_QWORD *)&EventDescriptor.Id = v98;
      EventDescriptor.Keyword = v100;
      v233[0] = (_Mtx_t)L"devMake";
      v233[1] = (_Mtx_t)7;
      JsonImplementType<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>>::AddValue(
        (unsigned int)v250,
        v53,
        v99,
        (unsigned int)v249,
        (__int64)v233,
        (__int64)&EventDescriptor);
    }
    v101 = (_QWORD *)(a2 + 128);
    v102 = *(_QWORD *)(a2 + 144);
    if ( v102 )
    {
      if ( *(_QWORD *)(a2 + 152) > 7u )
        v101 = (_QWORD *)*v101;
      *(_QWORD *)&EventDescriptor.Id = v101;
      EventDescriptor.Keyword = v102;
      v233[0] = (_Mtx_t)L"devModel";
      v233[1] = (_Mtx_t)8;
      JsonImplementType<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>>::AddValue(
        (unsigned int)v250,
        v53,
        v99,
        (unsigned int)v249,
        (__int64)v233,
        (__int64)&EventDescriptor);
    }
  }
  if ( (unsigned __int16)(qword_18043C08A - 3) > 1u )
  {
    LOBYTE(v97) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_DpswOneSettingsControl>::ReportUsage(
      &`wil::Feature<__WilFeatureTraits_Feature_DpswOneSettingsControl>::GetImpl'::`2'::impl,
      v97);
  }
  if ( v252 )
  {
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_DmaUtcUpdate>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_DmaUtcUpdate>::GetImpl'::`2'::impl);
    v104 = *(_DWORD *)(a1 + 280) & 0x2000;
    if ( IsEnabled )
    {
      if ( v104
        || !Microsoft::Diagnostics::IAsimovEvent::IsWindowsDiagnosticData((Microsoft::Diagnostics::IAsimovEvent *)a1) )
      {
        goto LABEL_167;
      }
      UserManager = Microsoft::Diagnostics::LifetimeManager::GetUserManager((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
      OmittedId = (void *)Microsoft::Diagnostics::UserManager::GetOmittedId(UserManager, &v242, Src);
      v107 = std::wstring::_Insert<wchar_t>(OmittedId);
      UserData = *(struct _EVENT_DATA_DESCRIPTOR *)v107;
      v255 = *(_OWORD *)(v107 + 16);
      *(_QWORD *)(v107 + 16) = 0;
      *(_QWORD *)(v107 + 24) = 7;
      *(_WORD *)v107 = 0;
      v10 |= 0x200u;
      LODWORD(v238[0]) = v10;
      std::wstring::operator=(Src, &UserData);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)&UserData);
    }
    else
    {
      if ( v104 )
        goto LABEL_167;
      v108 = (const struct _GUID *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 128LL))(a1);
      if ( !Microsoft::Diagnostics::IAsimovEvent::IsGroupBoundToOsPolicies(v108) )
        goto LABEL_167;
      v109 = Microsoft::Diagnostics::LifetimeManager::GetUserManager((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
      v110 = (void *)Microsoft::Diagnostics::UserManager::GetOmittedId(v109, &v242, Src);
      v111 = std::wstring::_Insert<wchar_t>(v110);
      UserData = *(struct _EVENT_DATA_DESCRIPTOR *)v111;
      v255 = *(_OWORD *)(v111 + 16);
      *(_QWORD *)(v111 + 16) = 0;
      *(_QWORD *)(v111 + 24) = 7;
      *(_WORD *)v111 = 0;
      v10 |= 0x400u;
      LODWORD(v238[0]) = v10;
      std::wstring::operator=(Src, &UserData);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)&UserData);
    }
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)&v242);
LABEL_167:
    *(_QWORD *)&EventDescriptor.Id = L"user";
    EventDescriptor.Keyword = 4;
    *(_OWORD *)v233 = *(_OWORD *)v237[0];
    Microsoft::Diagnostics::IAsimovEvent::CreateOrGetExtensionObject(a1, v249, v233, &EventDescriptor);
    v112 = Src;
    if ( v253 > 7 )
      v112 = (void **)Src[0];
    *(_QWORD *)&EventDescriptor.Id = L"localId";
    EventDescriptor.Keyword = 7;
    JsonImplementType<wchar_t *>::AddValue((int)v233, v53, 0, (int)v249, (__int64)&EventDescriptor, v112);
  }
  *(_OWORD *)v233 = *(_OWORD *)v5;
  if ( *(double *)(a1 + 296) != 100.0 )
  {
    v246[0] = *(void **)(a1 + 296);
    *(_QWORD *)&EventDescriptor.Id = L"popSample";
    EventDescriptor.Keyword = 9;
    JsonBuilder::AddValue(v53, (int)v249, 0, (int)v233, (__int64)&EventDescriptor, 248, 8, v246);
  }
  *(_QWORD *)&EventDescriptor.Id = L"eventFlags";
  EventDescriptor.Keyword = 10;
  *(_OWORD *)v233 = *(_OWORD *)v5;
  Microsoft::Diagnostics::IAsimovEvent::AddEventFlags(a1, v233, &EventDescriptor);
  v114 = *(_QWORD *)(a1 + 584);
  if ( v114 )
    _InterlockedIncrement((volatile signed __int32 *)(v114 + 8));
  v115 = *(_QWORD *)(a1 + 576);
  v249[0] = (_Mtx_t)v115;
  v116 = *(struct _Mtx_internal_imp_t **)(a1 + 584);
  v117 = v116;
  v249[1] = v116;
  if ( !v115 )
  {
    if ( !_InterlockedCompareExchange64(&qword_18043BEF8, 0, 0) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x58,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\include\\LifetimeManager.h",
        v113);
    v118 = qword_18043BEF8;
    v119 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 128LL))(a1);
    CachedGroupInfo = (__int64 *)Microsoft::Diagnostics::SettingsManager::GetCachedGroupInfo(
                                   v118,
                                   &EventDescriptor,
                                   v119);
    v115 = *CachedGroupInfo;
    v117 = (struct _Mtx_internal_imp_t *)CachedGroupInfo[1];
    *CachedGroupInfo = 0;
    CachedGroupInfo[1] = 0;
    v249[0] = (_Mtx_t)v115;
    v249[1] = v117;
    if ( v116 )
      std::_Ref_count_base::_Decref(v116);
    if ( EventDescriptor.Keyword )
      std::_Ref_count_base::_Decref((std::_Ref_count_base *)EventDescriptor.Keyword);
  }
  if ( memcmp_0((const void *)v115, &GUID_NULL, 0x10u) )
  {
    UserData = 0;
    *(_QWORD *)&v255 = 0;
    *((_QWORD *)&v255 + 1) = 7;
    LOWORD(UserData.Ptr) = 0;
    if ( *(_QWORD *)(v115 + 64) )
    {
      v123 = (_QWORD *)(v115 + 48);
      if ( v123[3] > 7u )
        v123 = (_QWORD *)*v123;
      *(_QWORD *)&EventDescriptor.Id = L"pgName";
      EventDescriptor.Keyword = 6;
      JsonImplementType<wchar_t *>::AddValue((int)v233, v53, 0, (int)v235, (__int64)&EventDescriptor, v123);
    }
    else
    {
      v122 = (_QWORD *)Microsoft::Diagnostics::Utils::String::StringFromGuidW(&v242, v115, 0);
      if ( v122[3] > 7u )
        v122 = (_QWORD *)*v122;
      *(_QWORD *)&EventDescriptor.Id = L"pgName";
      EventDescriptor.Keyword = 6;
      JsonImplementType<wchar_t *>::AddValue((int)v233, v53, 0, (int)v235, (__int64)&EventDescriptor, v122);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)&v242);
    }
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)&UserData);
  }
  if ( v117 )
    std::_Ref_count_base::_Decref(v117);
  LOBYTE(v121) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommonSchemaPartAEnhancements>::ReportUsage(
    &`wil::Feature<__WilFeatureTraits_Feature_CommonSchemaPartAEnhancements>::GetImpl'::`2'::impl,
    v121);
  v125 = *(_QWORD *)(a1 + 272);
  if ( !v125
    || (v126 = GetTickCount64(), v126 <= v125)
    || v126 - v125 <= 0x3A98
    || (*(_BYTE *)(a1 + 696) & 0x20) != 0
    || IsDebuggerPresent() )
  {
    v130 = v235;
  }
  else
  {
    v127 = *(_QWORD *)(a1 + 272);
    TickCount64 = GetTickCount64();
    v129 = ((TickCount64 - v127) * (unsigned __int128)0x624DD2F1A9FBE77uLL) >> 64;
    v246[0] = (void *)((v129 + ((TickCount64 - v127 - v129) >> 1)) >> 9);
    *(_QWORD *)&EventDescriptor.Id = L"latencyIngest";
    EventDescriptor.Keyword = 13;
    v130 = v235;
    JsonBuilder::push_back<unsigned __int64,JsonIterator (JsonBuilder &,bool,JsonConstIterator const &,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &,unsigned __int64 const &)>(
      v53,
      (unsigned int)v233,
      (_DWORD)v235,
      (unsigned int)&EventDescriptor,
      (__int64)v246);
  }
  if ( (unsigned int)dword_18042D328 > 5 && (qword_18042D338 & 1) != 0 && (qword_18042D340 & 1) == qword_18042D340 )
  {
    *(_QWORD *)v250 = *(_QWORD *)(a1 + 264);
    v249[0] = *(_Mtx_t *)(a1 + 272);
    v233[0] = (_Mtx_t)GetTickCount64();
    LOBYTE(v234) = (*(_BYTE *)(a1 + 696) & 0x20) != 0;
    v256[6] = v250;
    v256[7] = 8;
    v256[4] = v249;
    v256[5] = 8;
    v256[2] = v233;
    v256[3] = 8;
    v256[0] = &v234;
    v256[1] = 1;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    *(_DWORD *)&EventDescriptor.Level = 5;
    EventDescriptor.Keyword = 1;
    UserData.Ptr = (ULONGLONG)off_18042D330;
    UserData.Size = *(unsigned __int16 *)off_18042D330;
    UserData.Reserved = 2;
    *(_QWORD *)&v255 = &unk_1803C1755;
    *((_QWORD *)&v255 + 1) = 0x100000063LL;
    LODWORD(v246[0]) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 6u, &UserData);
  }
  if ( _InterlockedCompareExchange64((volatile signed __int64 *)&xmmword_18043BF10, 0, 0) )
  {
    if ( !_InterlockedCompareExchange64((volatile signed __int64 *)&xmmword_18043BF10, 0, 0) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x5B,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\include\\LifetimeManager.h",
        v124);
    *(double *)v233 = 100.0 - *(double *)(xmmword_18043BF10 + 624);
    *(_QWORD *)&EventDescriptor.Id = L"dvcSample";
    EventDescriptor.Keyword = 9;
    JsonBuilder::AddValue(v53, (int)v249, 0, (int)v130, (__int64)&EventDescriptor, 2, 8, v233);
  }
  if ( *(_QWORD *)((*(__int64 (__fastcall **)(__int64, EVENT_DESCRIPTOR *))(*(_QWORD *)a1 + 88LL))(a1, &EventDescriptor)
                 + 8)
    && (unsigned __int8)(*(_BYTE *)(a1 + 288) - 1) > 1u )
  {
    (*(void (__fastcall **)(__int64, EVENT_DESCRIPTOR *))(*(_QWORD *)a1 + 88LL))(a1, &EventDescriptor);
    if ( (*(_BYTE *)(a1 + 696) & 2) == 0 )
    {
      *(EVENT_DESCRIPTOR *)v249 = EventDescriptor;
      v233[0] = (_Mtx_t)L"stId";
      v233[1] = (_Mtx_t)4;
      JsonBuilder::push_back<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,JsonIterator (JsonBuilder &,bool,JsonConstIterator const &,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &)>(
        v53,
        (unsigned int)v250,
        (_DWORD)v130,
        (unsigned int)v233,
        (__int64)v249);
      goto LABEL_220;
    }
    Keyword = EventDescriptor.Keyword;
    if ( EventDescriptor.Keyword != -1 )
    {
      v131 = *(gsl::details **)&EventDescriptor.Id;
      if ( *(_QWORD *)&EventDescriptor.Id )
      {
        if ( EventDescriptor.Keyword < 0x7FFFFFFFFFFFFFFFLL )
        {
          Keyword = 2 * EventDescriptor.Keyword;
LABEL_214:
          v233[0] = (_Mtx_t)(unsigned int)v236;
          v246[0] = (void *)(unsigned int)v236;
          SpookyHash::Hash128(
            *(const void **)&EventDescriptor.Id,
            Keyword,
            (unsigned __int64 *)v246,
            (unsigned __int64 *)v233);
          v133 = (unsigned __int64)v246[0];
          if ( Keyword < 0x10 )
            v133 = (unsigned __int64)v246[0] >> (63 - 4 * (unsigned __int8)Keyword);
          std::to_wstring(&UserData, v133);
          p_UserData = (struct _Mtx_internal_imp_t *)&UserData;
          if ( *((_QWORD *)&v255 + 1) > 7u )
            p_UserData = (struct _Mtx_internal_imp_t *)UserData.Ptr;
          v233[0] = p_UserData;
          v233[1] = (_Mtx_t)v255;
          v249[0] = (_Mtx_t)L"stId";
          v249[1] = (_Mtx_t)4;
          JsonBuilder::push_back<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,JsonIterator (JsonBuilder &,bool,JsonConstIterator const &,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &)>(
            v53,
            (unsigned int)v250,
            (_DWORD)v130,
            (unsigned int)v249,
            (__int64)v233);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)&UserData);
          goto LABEL_220;
        }
      }
      else if ( !EventDescriptor.Keyword )
      {
        goto LABEL_214;
      }
    }
    gsl::details::terminate(v131);
    __debugbreak();
  }
LABEL_220:
  *(_QWORD *)&EventDescriptor.Id = L"flags";
  EventDescriptor.Keyword = 5;
  if ( !*(_DWORD *)(JsonBuilder::find<>(v53, v233, v130, &EventDescriptor) + 8) )
  {
    v233[0] = (_Mtx_t)Microsoft::Diagnostics::IAsimovEvent::GenerateUtcFlags(
                        (Microsoft::Diagnostics::IAsimovEvent *)a1,
                        (struct Microsoft::Diagnostics::AsimovSharedPartAState *)a2);
    *(_QWORD *)&EventDescriptor.Id = L"flags";
    EventDescriptor.Keyword = 5;
    JsonBuilder::push_back<unsigned __int64,JsonIterator (JsonBuilder &,bool,JsonConstIterator const &,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &,unsigned __int64 const &)>(
      v53,
      (unsigned int)v249,
      (_DWORD)v130,
      (unsigned int)&EventDescriptor,
      (__int64)v233);
  }
  if ( (*(_BYTE *)(a1 + 697) & 2) != 0 )
  {
    v135 = std::to_wstring(v250, *(unsigned int *)(a1 + 692));
    v136 = (void *)std::to_wstring(v249, *(unsigned int *)(a1 + 688));
    v137 = std::wstring::_Append<wchar_t>(v136);
    v242 = *(struct _EVENT_DATA_DESCRIPTOR *)v137;
    v243 = *(_OWORD *)(v137 + 16);
    *(_QWORD *)(v137 + 16) = 0;
    *(_QWORD *)(v137 + 24) = 7;
    *(_WORD *)v137 = 0;
    std::wstring::wstring(&UserData, v138, &v242, v135);
    v10 |= 0x1800u;
    LODWORD(v238[0]) = v10;
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)&v242);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v249);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v250);
    v139 = &UserData;
    if ( *((_QWORD *)&v255 + 1) > 7u )
      v139 = (void *)UserData.Ptr;
    *(_QWORD *)&EventDescriptor.Id = L"mon";
    EventDescriptor.Keyword = 3;
    JsonImplementType<wchar_t *>::AddValue((int)v233, v53, 0, (int)v130, (__int64)&EventDescriptor, v139);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)&UserData);
  }
  if ( (unsigned int)Microsoft::Diagnostics::DynamicConfig<unsigned long>::Get(a2 + 6320)
    && (unsigned __int8)(*(_BYTE *)(a1 + 288) - 1) > 1u )
  {
    if ( *(_BYTE *)(a1 + 284) && *(_BYTE *)(a1 + 286) )
    {
      v140 = *(unsigned __int8 *)(a1 + 285);
      v141 = *(unsigned __int8 *)(a1 + 287);
      v142 = *(unsigned __int8 *)(a1 + 290);
      v143 = *(_BYTE *)(a1 + 696);
      v242 = 0;
      v243 = 0u;
      std::wstring::_Construct<1,wchar_t *>(&v242, &::Src, 0);
      v244 = 0x200000;
      v245 = 0;
      EventDescriptor = *(EVENT_DESCRIPTOR *)&(&Microsoft::Diagnostics::AsimovSharedPartAState::k_storageBufferTypeStrings)[2 * v142];
      Microsoft::Diagnostics::WideStringStream::AppendString(&v242);
      EventDescriptor = *(EVENT_DESCRIPTOR *)&(&Microsoft::Diagnostics::AsimovSharedPartAState::k_latencyStrings)[2 * (unsigned int)v141];
      Microsoft::Diagnostics::WideStringStream::AppendString(&v242);
      EventDescriptor = *(EVENT_DESCRIPTOR *)&(&Microsoft::Diagnostics::AsimovSharedPartAState::k_persistenceStrings)[2 * (unsigned int)v140];
      Microsoft::Diagnostics::WideStringStream::AppendString(&v242);
      Microsoft::Diagnostics::WideStringStream::operator<<(&v242);
      v144 = 6544;
      if ( (v143 & 2) != 0 )
        v144 = 6552;
      _InterlockedExchangeAdd64(
        (volatile signed __int64 *)(v144 + a2 + 16 * (v140 + 2 * (v142 + v141 + 2LL * v142))),
        1u);
      Microsoft::Diagnostics::WideStringStream::operator<<(&v242);
      v145 = (struct _EVENT_DATA_DESCRIPTOR *)v242.Ptr;
      UserData = v242;
      v146 = (__m128i)v243;
      v255 = v243;
      *(_QWORD *)&v243 = 0;
      *((_QWORD *)&v243 + 1) = 7;
      LOWORD(v242.Ptr) = 0;
      v10 = LODWORD(v238[0]) | 0x2000;
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)&v242);
      v147 = &UserData;
      if ( _mm_srli_si128(v146, 8).m128i_u64[0] > 7 )
        v147 = v145;
      *(_QWORD *)&EventDescriptor.Id = L"bSeq";
      EventDescriptor.Keyword = 4;
      LODWORD(v130) = (_DWORD)v235;
      LODWORD(v53) = a1 + 16;
      JsonImplementType<wchar_t *>::AddValue((int)v233, a1 + 16, 0, (int)v235, (__int64)&EventDescriptor, v147);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)&UserData);
      goto LABEL_235;
    }
LABEL_427:
    gsl::details::terminate((gsl::details *)v21);
    __debugbreak();
  }
LABEL_235:
  if ( (unsigned int)Microsoft::Diagnostics::DynamicConfig<unsigned long>::Get(a2 + 6096) )
  {
    v149 = (void *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 80LL))(a1);
    *(_QWORD *)&EventDescriptor.Id = L"providerGuid";
    EventDescriptor.Keyword = 12;
    JsonBuilder::AddValue(v53, (int)v233, 0, (int)v130, (__int64)&EventDescriptor, 251, 16, v149);
    ProviderBinaryPath = (_QWORD *)Microsoft::Diagnostics::WmiBinaryPathHandler::GetProviderBinaryPath((_Mtx_t)&qword_18043BE98);
    if ( ProviderBinaryPath[3] > 7u )
      ProviderBinaryPath = (_QWORD *)*ProviderBinaryPath;
    *(_QWORD *)&EventDescriptor.Id = L"loggingBinary";
    EventDescriptor.Keyword = 13;
    JsonImplementType<wchar_t *>::AddValue((int)v233, v53, 0, (int)v130, (__int64)&EventDescriptor, ProviderBinaryPath);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v256);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)&UserData);
  }
  if ( (unsigned __int16)(qword_18043C08A - 3) > 1u )
  {
    if ( !_InterlockedCompareExchange64((_QWORD *)&xmmword_18043BF70 + 1, 0, 0) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x63,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\include\\LifetimeManager.h",
        v148);
    Microsoft::Diagnostics::EnterpriseData::GetCommercialId(*((_QWORD *)&xmmword_18043BF70 + 1), &UserData);
    if ( (_QWORD)v255 )
    {
      *(_QWORD *)&EventDescriptor.Id = L"m365a";
      EventDescriptor.Keyword = 5;
      *(_OWORD *)v233 = *(_OWORD *)v237[0];
      Microsoft::Diagnostics::IAsimovEvent::CreateOrGetExtensionObject(a1, v249, v233, &EventDescriptor);
      v151 = &UserData;
      if ( *((_QWORD *)&v255 + 1) > 7u )
        v151 = (void *)UserData.Ptr;
      *(_QWORD *)&EventDescriptor.Id = L"enrolledTenantId";
      EventDescriptor.Keyword = 16;
      JsonImplementType<wchar_t *>::AddValue((int)v233, v53, 0, (int)v249, (__int64)&EventDescriptor, v151);
    }
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)&UserData);
  }
  LODWORD(v246[0]) = *(_DWORD *)(a2 + 736);
  if ( LODWORD(v246[0]) )
  {
    *(_QWORD *)&EventDescriptor.Id = L"wsId";
    EventDescriptor.Keyword = 4;
    JsonBuilder::push_back<unsigned long,JsonIterator (JsonBuilder &,bool,JsonConstIterator const &,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &,unsigned long const &)>(
      v53,
      (unsigned int)v233,
      (_DWORD)v130,
      (unsigned int)&EventDescriptor,
      (__int64)v246);
  }
  LOWORD(v234) = *(_WORD *)(a2 + 740);
  if ( (_WORD)v234 )
  {
    *(_QWORD *)&EventDescriptor.Id = L"wcmp";
    EventDescriptor.Keyword = 4;
    JsonBuilder::push_back<unsigned short,JsonIterator (JsonBuilder &,bool,JsonConstIterator const &,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &,unsigned short const &)>(
      v53,
      (unsigned int)v233,
      (_DWORD)v130,
      (unsigned int)&EventDescriptor,
      (__int64)&v234);
  }
  LODWORD(v246[0]) = *(_DWORD *)(a2 + 8);
  if ( LODWORD(v246[0]) )
  {
    *(_QWORD *)&EventDescriptor.Id = L"wPId";
    EventDescriptor.Keyword = 4;
    JsonBuilder::push_back<unsigned long,JsonIterator (JsonBuilder &,bool,JsonConstIterator const &,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &,unsigned long const &)>(
      v53,
      (unsigned int)v233,
      (_DWORD)v130,
      (unsigned int)&EventDescriptor,
      (__int64)v246);
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EditionCommonSchema>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_EditionCommonSchema>::GetImpl'::`2'::impl) )
  {
    LOWORD(v234) = *(_WORD *)(a2 + 16);
    *(_QWORD *)&EventDescriptor.Id = L"edition";
    EventDescriptor.Keyword = 7;
    JsonBuilder::push_back<unsigned short,JsonIterator (JsonBuilder &,bool,JsonConstIterator const &,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &,unsigned short const &)>(
      v53,
      (unsigned int)v233,
      (_DWORD)v130,
      (unsigned int)&EventDescriptor,
      (__int64)&v234);
  }
  std::lock_guard<std::mutex>::lock_guard<std::mutex>(v233, a2 + 6928);
  v152 = *(_BYTE *)(a2 + 7008);
  _Mtx_unlock(v233[0]);
  if ( !v152 )
    goto LABEL_328;
  v153 = &unk_18043B3B0;
  if ( *(_QWORD *)(a1 + 504) )
    v153 = *(_QWORD **)(a1 + 504);
  if ( v153[2] )
    goto LABEL_328;
  *(_QWORD *)&EventDescriptor.Id = L"xbl";
  EventDescriptor.Keyword = 3;
  *(_OWORD *)v233 = *(_OWORD *)v237[0];
  Microsoft::Diagnostics::IAsimovEvent::CreateOrGetExtensionObject(a1, v250, v233, &EventDescriptor);
  std::lock_guard<std::mutex>::lock_guard<std::mutex>(v233, a2 + 6928);
  v154 = (_QWORD *)(a2 + 7048);
  v242 = 0;
  v243 = 0u;
  v155 = *(_QWORD *)(a2 + 7064);
  if ( *(_QWORD *)(a2 + 7072) > 7u )
    v154 = (_QWORD *)*v154;
  if ( v155 > 0x7FFFFFFFFFFFFFFELL )
    std::_Xlen_string();
  if ( v155 > 7 )
  {
    v156 = v155 | 7;
    if ( (v155 | 7) <= 0x7FFFFFFFFFFFFFFELL )
    {
      if ( v156 < 0xA )
        v156 = 10;
      if ( v156 + 1 > 0x7FFFFFFFFFFFFFFFLL )
        goto LABEL_442;
      v157 = 2 * (v156 + 1);
      if ( !v157 )
      {
        v160 = 0;
        goto LABEL_276;
      }
    }
    else
    {
      v156 = 0x7FFFFFFFFFFFFFFELL;
      v157 = -2;
    }
    if ( v157 >= 0x1000 )
    {
      if ( v157 + 39 >= v157 )
      {
        v158 = operator new(v157 + 39);
        v159 = v158;
        if ( !v158 )
          __fastfail(5u);
        v160 = (_QWORD *)(((unsigned __int64)v158 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
        *(v160 - 1) = v159;
        goto LABEL_276;
      }
LABEL_442:
      std::_Throw_bad_array_new_length();
    }
    v160 = operator new(v157);
LABEL_276:
    v242.Ptr = (ULONGLONG)v160;
    *(_QWORD *)&v243 = v155;
    *((_QWORD *)&v243 + 1) = v156;
    memcpy_0(v160, v154, 2 * v155 + 2);
    goto LABEL_277;
  }
  *(_QWORD *)&v243 = *(_QWORD *)(a2 + 7064);
  *((_QWORD *)&v243 + 1) = 7;
  v242 = *(struct _EVENT_DATA_DESCRIPTOR *)v154;
LABEL_277:
  v10 |= 0x4000u;
  _Mtx_unlock(v233[0]);
  v161 = &v242;
  if ( *((_QWORD *)&v243 + 1) > 7u )
    v161 = (struct _EVENT_DATA_DESCRIPTOR *)v242.Ptr;
  *(_QWORD *)&EventDescriptor.Id = v161;
  EventDescriptor.Keyword = v243;
  v233[0] = (_Mtx_t)L"sbx";
  v233[1] = (_Mtx_t)3;
  JsonBuilder::push_back<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,JsonIterator (JsonBuilder &,bool,JsonConstIterator const &,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &)>(
    v53,
    (unsigned int)v249,
    (unsigned int)v250,
    (unsigned int)v233,
    (__int64)&EventDescriptor);
  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)&v242);
  if ( (unsigned __int8)(*(_BYTE *)(a1 + 288) - 1) > 1u )
  {
    std::lock_guard<std::mutex>::lock_guard<std::mutex>(v233, a2 + 6928);
    if ( !*(_QWORD *)(a2 + 7032) )
    {
      v235 = 0;
      DeviceId = XblAuthConfig::GetDeviceId(&v235);
      v164 = v235;
      if ( DeviceId >= 0 )
      {
        if ( v235 )
        {
          v165 = -1;
          do
            ++v165;
          while ( v235[v165] );
          std::wstring::_Assign<wchar_t>((char **)(a2 + 7016), v235, (char *)v165);
        }
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x33D,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\asimov\\asimovsharedpartastate.cpp",
          (const char *)(unsigned int)DeviceId,
          UserDataCount);
      }
      if ( v164 )
        wilp::CloseHeapPointer((wilp *)v164, v163);
    }
    v166 = (_QWORD *)(a2 + 7016);
    *(_OWORD *)v246 = 0;
    v247 = 0;
    v248 = 0;
    v167 = *(_QWORD *)(a2 + 7032);
    if ( *(_QWORD *)(a2 + 7040) > 7u )
      v166 = (_QWORD *)*v166;
    v168 = 0x7FFFFFFFFFFFFFFELL;
    if ( v167 > 0x7FFFFFFFFFFFFFFELL )
      std::_Xlen_string();
    if ( v167 > 7 )
    {
      v169 = v167 | 7;
      if ( (v167 | 7) <= 0x7FFFFFFFFFFFFFFELL )
      {
        v168 = 10;
        if ( v169 < 0xA )
          v169 = 10;
      }
      else
      {
        v169 = 0x7FFFFFFFFFFFFFFELL;
      }
      v235 = (wchar_t *)v169;
      v246[0] = (void *)std::wstring::_Allocate_for_capacity<0>(v168, &v235);
      v247 = v167;
      v248 = (unsigned __int64)v235;
      memcpy_0(v246[0], v166, 2 * v167 + 2);
    }
    else
    {
      v247 = *(_QWORD *)(a2 + 7032);
      v248 = 7;
      *(_OWORD *)v246 = *(_OWORD *)v166;
    }
    v170 = v10 | 0x8000;
    _Mtx_unlock(v233[0]);
    if ( (*(_BYTE *)(a1 + 696) & 2) != 0 )
    {
      EventDescriptor = *(EVENT_DESCRIPTOR *)gslp::container_to_bytes<std::wstring>(v233, v246);
      v171 = PiiHash((unsigned int)v236, &EventDescriptor);
      v172 = (void *)std::to_wstring(&v242, v171);
      v173 = std::wstring::_Insert<wchar_t>(v172);
      UserData = *(struct _EVENT_DATA_DESCRIPTOR *)v173;
      v255 = *(_OWORD *)(v173 + 16);
      *(_QWORD *)(v173 + 16) = 0;
      *(_QWORD *)(v173 + 24) = 7;
      *(_WORD *)v173 = 0;
      v170 |= 0x10000u;
      std::wstring::operator=(v246, &UserData);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)&UserData);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)&v242);
    }
    if ( v247 )
    {
      v174 = v246;
      if ( v248 > 7 )
        v174 = (void **)v246[0];
      *(_QWORD *)&EventDescriptor.Id = L"did";
      EventDescriptor.Keyword = 3;
      JsonImplementType<wchar_t *>::AddValue((int)v233, v53, 0, (int)v250, (__int64)&EventDescriptor, v174);
    }
    std::lock_guard<std::mutex>::lock_guard<std::mutex>(v249, a2 + 7096);
    v175 = (_QWORD *)(a2 + 7176);
    v242 = 0;
    v243 = 0u;
    v176 = *(_QWORD *)(a2 + 7192);
    if ( *(_QWORD *)(a2 + 7200) > 7u )
      v175 = (_QWORD *)*v175;
    v177 = 0x7FFFFFFFFFFFFFFELL;
    if ( v176 > 0x7FFFFFFFFFFFFFFELL )
      std::_Xlen_string();
    if ( v176 > 7 )
    {
      v180 = v176 | 7;
      if ( (v176 | 7) <= 0x7FFFFFFFFFFFFFFELL )
      {
        v177 = 10;
        if ( v180 < 0xA )
          v180 = 10;
      }
      else
      {
        v180 = 0x7FFFFFFFFFFFFFFELL;
      }
      v235 = (wchar_t *)v180;
      v233[0] = (_Mtx_t)std::wstring::_Allocate_for_capacity<0>(v177, &v235);
      v242.Ptr = (ULONGLONG)v233[0];
      *(_QWORD *)&v243 = v176;
      v178 = (unsigned __int64)v235;
      *((_QWORD *)&v243 + 1) = v235;
      memcpy_0(v233[0], v175, 2 * v176 + 2);
      v179 = (struct _EVENT_DATA_DESCRIPTOR *)v233[0];
    }
    else
    {
      *(_QWORD *)&v243 = *(_QWORD *)(a2 + 7192);
      v178 = 7;
      *((_QWORD *)&v243 + 1) = 7;
      v242 = *(struct _EVENT_DATA_DESCRIPTOR *)v175;
      v179 = (struct _EVENT_DATA_DESCRIPTOR *)v242.Ptr;
    }
    v10 = v170 | 0x20000;
    _Mtx_unlock(v249[0]);
    if ( v176 )
    {
      v181 = &v242;
      if ( v178 > 7 )
        v181 = v179;
      *(_QWORD *)&EventDescriptor.Id = L"cid";
      EventDescriptor.Keyword = 3;
      JsonImplementType<wchar_t *>::AddValue((int)v233, v53, 0, (int)v250, (__int64)&EventDescriptor, v181);
    }
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)&v242);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v246);
  }
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DmaUtcUpdate>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_DmaUtcUpdate>::GetImpl'::`2'::impl) )
  {
    LOBYTE(v182) = (unsigned __int8)(*(_BYTE *)(a1 + 288) - 1) <= 1u;
    Microsoft::Diagnostics::AsimovSharedPartAState::GetXuidsString(
      (*(_BYTE *)(a1 + 696) & 2) != 0,
      (unsigned int)&UserData,
      a1 + 520,
      v182,
      (*(_BYTE *)(a1 + 696) & 2) != 0,
      v236);
    if ( (_QWORD)v255 )
    {
      v197 = &UserData;
      if ( *((_QWORD *)&v255 + 1) > 7u )
        v197 = (void *)UserData.Ptr;
      *(_QWORD *)&EventDescriptor.Id = L"xid";
      EventDescriptor.Keyword = 3;
      JsonImplementType<wchar_t *>::AddValue((int)v233, v53, 0, (int)v250, (__int64)&EventDescriptor, v197);
    }
    goto LABEL_327;
  }
  if ( *(_BYTE *)(a2 + 56) == 1
    || (v183 = (const struct _GUID *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 128LL))(a1),
        (unsigned int)InlineIsEqualGUID(v183, &s_xboxXsapiGroupId)) )
  {
    LOBYTE(v182) = (unsigned __int8)(*(_BYTE *)(a1 + 288) - 1) <= 1u;
    Microsoft::Diagnostics::AsimovSharedPartAState::GetXuidsString(
      (*(_BYTE *)(a1 + 696) & 2) != 0,
      (unsigned int)&UserData,
      a1 + 520,
      v182,
      (*(_BYTE *)(a1 + 696) & 2) != 0,
      v236);
    if ( (_QWORD)v255 )
    {
      v184 = &UserData;
      if ( *((_QWORD *)&v255 + 1) > 7u )
        v184 = (void *)UserData.Ptr;
      *(_QWORD *)&EventDescriptor.Id = L"xid";
      EventDescriptor.Keyword = 3;
      JsonImplementType<wchar_t *>::AddValue((int)v233, v53, 0, (int)v250, (__int64)&EventDescriptor, v184);
    }
LABEL_327:
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)&UserData);
  }
LABEL_328:
  if ( (unsigned int)RtlGetCurrentServiceSessionId() )
  {
    if ( (((_WORD)qword_18043C08A - 2) & 0xFFFD) != 0 )
    {
      *(_QWORD *)&EventDescriptor.Id = L"container";
      EventDescriptor.Keyword = 9;
      *(_OWORD *)v233 = *(_OWORD *)v237[0];
      Microsoft::Diagnostics::IAsimovEvent::CreateOrGetExtensionObject(a1, v249, v233, &EventDescriptor);
      LODWORD(v246[0]) = *(_DWORD *)(a2 + 232);
      *(_QWORD *)&EventDescriptor.Id = L"type";
      EventDescriptor.Keyword = 4;
      v185 = *(_OWORD *)v249;
      *(_OWORD *)v233 = *(_OWORD *)v249;
      Microsoft::Diagnostics::IAsimovEvent::AddValueIfNotPresent<unsigned long>(a1, v233, &EventDescriptor, v246);
      LOBYTE(v186) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_ArgonContainerCommonSchema>::ReportUsage(
        &`wil::Feature<__WilFeatureTraits_Feature_ArgonContainerCommonSchema>::GetImpl'::`2'::impl,
        v186);
      if ( *(_QWORD *)(a2 + 256) )
      {
        v242 = 0;
        v243 = 0u;
        std::wstring::_Construct<1,wchar_t *>(&v242, L"s:", 2);
        UserData = v242;
        v255 = v243;
        *(_QWORD *)&v243 = 0;
        *((_QWORD *)&v243 + 1) = 7;
        LOWORD(v242.Ptr) = 0;
        LODWORD(v246[0]) = v10 | 0x40000;
        std::wstring::_Append<wchar_t>(&UserData);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)&v242);
        v187 = (ULONGLONG)&UserData;
        if ( *((_QWORD *)&v255 + 1) > 7u )
          v187 = UserData.Ptr;
        *(_QWORD *)&EventDescriptor.Id = v187;
        EventDescriptor.Keyword = v255;
        v233[0] = (_Mtx_t)L"hostId";
        v233[1] = (_Mtx_t)6;
        *(_OWORD *)v249 = v185;
        Microsoft::Diagnostics::IAsimovEvent::AddValueIfNotPresent<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>>(
          a1,
          v249,
          v233,
          &EventDescriptor);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)&UserData);
      }
    }
  }
  *(_QWORD *)&EventDescriptor.Id = L"loc";
  EventDescriptor.Keyword = 3;
  v188 = (_OWORD *)v237[0];
  *(_OWORD *)v233 = *(_OWORD *)v237[0];
  Microsoft::Diagnostics::IAsimovEvent::CreateOrGetExtensionObject(a1, v249, v233, &EventDescriptor);
  UserData = 0;
  *(_QWORD *)&v255 = 0;
  *((_QWORD *)&v255 + 1) = 7;
  LOWORD(UserData.Ptr) = 0;
  v189 = (CONTEXT *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 64LL);
  RtlCaptureContext(v189);
  LOBYTE(v190) = 1;
  Microsoft::Diagnostics::UtcWatchdog::ThreadMonitor::ThreadMonitor(&EventDescriptor, 120000, v190, v189);
  v191 = Microsoft::Diagnostics::Utils::Time::Get8601TimeZoneString(&v242);
  std::wstring::operator=(&UserData, v191);
  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)&v242);
  Microsoft::Diagnostics::UtcWatchdog::ThreadMonitor::~ThreadMonitor((Microsoft::Diagnostics::UtcWatchdog::ThreadMonitor *)&EventDescriptor);
  v192 = &UserData;
  if ( *((_QWORD *)&v255 + 1) > 7u )
    v192 = (void *)UserData.Ptr;
  *(_QWORD *)&EventDescriptor.Id = L"tz";
  EventDescriptor.Keyword = 2;
  JsonImplementType<wchar_t *>::AddValue((int)v233, v53, 0, (int)v249, (__int64)&EventDescriptor, v192);
  if ( *(_BYTE *)(a2 + 368) )
  {
    v233[0] = (_Mtx_t)L"azureHost";
    v233[1] = (_Mtx_t)9;
    *(_OWORD *)v249 = *v188;
    Microsoft::Diagnostics::IAsimovEvent::CreateOrGetExtensionObject(a1, &EventDescriptor, v249, v233);
    v193 = (struct _EVENT_DATA_DESCRIPTOR **)(a2 + 272);
    *(_QWORD *)&v242.Size = 0;
    v194 = *(_QWORD *)(a2 + 288);
    v195 = (struct _EVENT_DATA_DESCRIPTOR *)(a2 + 272);
    if ( *(_QWORD *)(a2 + 296) > 7u )
      v195 = *v193;
    v196 = 0x7FFFFFFFFFFFFFFELL;
    if ( v194 <= 0x7FFFFFFFFFFFFFFELL )
    {
      if ( v194 > 7 )
      {
        v198 = v194 | 7;
        if ( (v194 | 7) <= 0x7FFFFFFFFFFFFFFELL )
        {
          v196 = 10;
          if ( v198 < 0xA )
            v198 = 10;
        }
        else
        {
          v198 = 0x7FFFFFFFFFFFFFFELL;
        }
        v235 = (wchar_t *)v198;
        v242.Ptr = std::wstring::_Allocate_for_capacity<0>(v196, &v235);
        *(_QWORD *)&v243 = v194;
        *((_QWORD *)&v243 + 1) = v235;
        memcpy_0((void *)v242.Ptr, v195, 2 * v194 + 2);
      }
      else
      {
        *(_QWORD *)&v243 = *(_QWORD *)(a2 + 288);
        *((_QWORD *)&v243 + 1) = 7;
        v242 = *v195;
      }
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)&v242);
      if ( v194 )
      {
        v242 = 0;
        v243 = 0u;
        v199 = *(_QWORD *)(a2 + 288);
        if ( *(_QWORD *)(a2 + 296) > 7u )
          v193 = (struct _EVENT_DATA_DESCRIPTOR **)*v193;
        v200 = 0x7FFFFFFFFFFFFFFELL;
        if ( v199 > 0x7FFFFFFFFFFFFFFELL )
          goto LABEL_426;
        if ( v199 > 7 )
        {
          v203 = v199 | 7;
          if ( (v199 | 7) <= 0x7FFFFFFFFFFFFFFELL )
          {
            v200 = 10;
            if ( v203 < 0xA )
              v203 = 10;
          }
          else
          {
            v203 = 0x7FFFFFFFFFFFFFFELL;
          }
          v235 = (wchar_t *)v203;
          v202 = (struct _EVENT_DATA_DESCRIPTOR *)std::wstring::_Allocate_for_capacity<0>(v200, &v235);
          v242.Ptr = (ULONGLONG)v202;
          *(_QWORD *)&v243 = v199;
          v201 = (unsigned __int64)v235;
          *((_QWORD *)&v243 + 1) = v235;
          memcpy_0(v202, v193, 2 * v199 + 2);
        }
        else
        {
          *(_QWORD *)&v243 = *(_QWORD *)(a2 + 288);
          v201 = 7;
          *((_QWORD *)&v243 + 1) = 7;
          v242 = *(struct _EVENT_DATA_DESCRIPTOR *)v193;
          v202 = (struct _EVENT_DATA_DESCRIPTOR *)v242.Ptr;
        }
        v204 = &v242;
        if ( v201 > 7 )
          v204 = v202;
        v233[0] = (_Mtx_t)L"nodeId";
        v233[1] = (_Mtx_t)6;
        JsonImplementType<wchar_t *>::AddValue((int)v249, v53, 0, (int)&EventDescriptor, (__int64)v233, v204);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)&v242);
      }
      v205 = (struct _EVENT_DATA_DESCRIPTOR **)(a2 + 304);
      *(_QWORD *)&v242.Size = 0;
      v206 = *(_QWORD *)(a2 + 320);
      v207 = (struct _EVENT_DATA_DESCRIPTOR *)(a2 + 304);
      if ( *(_QWORD *)(a2 + 328) > 7u )
        v207 = *v205;
      v208 = 0x7FFFFFFFFFFFFFFELL;
      if ( v206 <= 0x7FFFFFFFFFFFFFFELL )
      {
        if ( v206 > 7 )
        {
          v209 = v206 | 7;
          if ( (v206 | 7) <= 0x7FFFFFFFFFFFFFFELL )
          {
            v208 = 10;
            if ( v209 < 0xA )
              v209 = 10;
          }
          else
          {
            v209 = 0x7FFFFFFFFFFFFFFELL;
          }
          v235 = (wchar_t *)v209;
          v242.Ptr = std::wstring::_Allocate_for_capacity<0>(v208, &v235);
          *(_QWORD *)&v243 = v206;
          *((_QWORD *)&v243 + 1) = v235;
          memcpy_0((void *)v242.Ptr, v207, 2 * v206 + 2);
        }
        else
        {
          *(_QWORD *)&v243 = *(_QWORD *)(a2 + 320);
          *((_QWORD *)&v243 + 1) = 7;
          v242 = *v207;
        }
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)&v242);
        if ( v206 )
        {
          v242 = 0;
          v243 = 0u;
          v210 = *(_QWORD *)(a2 + 320);
          if ( *(_QWORD *)(a2 + 328) > 7u )
            v205 = (struct _EVENT_DATA_DESCRIPTOR **)*v205;
          if ( v210 > 0x7FFFFFFFFFFFFFFELL )
            goto LABEL_426;
          if ( v210 > 7 )
          {
            v235 = (wchar_t *)std::wstring::_Calculate_growth(v210, 7);
            v212 = (struct _EVENT_DATA_DESCRIPTOR *)std::wstring::_Allocate_for_capacity<0>(v213, &v235);
            v242.Ptr = (ULONGLONG)v212;
            *(_QWORD *)&v243 = v210;
            v211 = (unsigned __int64)v235;
            *((_QWORD *)&v243 + 1) = v235;
            memcpy_0(v212, v205, 2 * v210 + 2);
          }
          else
          {
            *(_QWORD *)&v243 = *(_QWORD *)(a2 + 320);
            v211 = 7;
            *((_QWORD *)&v243 + 1) = 7;
            v242 = *(struct _EVENT_DATA_DESCRIPTOR *)v205;
            v212 = (struct _EVENT_DATA_DESCRIPTOR *)v242.Ptr;
          }
          v214 = &v242;
          if ( v211 > 7 )
            v214 = v212;
          v233[0] = (_Mtx_t)L"ccOsVer";
          v233[1] = (_Mtx_t)7;
          JsonImplementType<wchar_t *>::AddValue((int)v249, v53, 0, (int)&EventDescriptor, (__int64)v233, v214);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)&v242);
        }
        v215 = (struct _EVENT_DATA_DESCRIPTOR **)(a2 + 336);
        *(_QWORD *)&v242.Size = 0;
        v216 = *(_QWORD *)(a2 + 352);
        v217 = (struct _EVENT_DATA_DESCRIPTOR *)(a2 + 336);
        if ( *(_QWORD *)(a2 + 360) > 7u )
          v217 = *v215;
        if ( v216 <= 0x7FFFFFFFFFFFFFFELL )
        {
          if ( v216 > 7 )
          {
            v235 = (wchar_t *)std::wstring::_Calculate_growth(*(_QWORD *)(a2 + 352), 7);
            v242.Ptr = std::wstring::_Allocate_for_capacity<0>(v218, &v235);
            *(_QWORD *)&v243 = v216;
            *((_QWORD *)&v243 + 1) = v235;
            memcpy_0((void *)v242.Ptr, v217, 2 * v216 + 2);
          }
          else
          {
            *(_QWORD *)&v243 = *(_QWORD *)(a2 + 352);
            *((_QWORD *)&v243 + 1) = 7;
            v242 = *v217;
          }
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)&v242);
          if ( !v216 )
          {
LABEL_402:
            v188 = (_OWORD *)v237[0];
            goto LABEL_403;
          }
          v242 = 0;
          v243 = 0u;
          v219 = *(_QWORD *)(a2 + 352);
          if ( *(_QWORD *)(a2 + 360) > 7u )
            v215 = (struct _EVENT_DATA_DESCRIPTOR **)*v215;
          if ( v219 <= 0x7FFFFFFFFFFFFFFELL )
          {
            if ( v219 > 7 )
            {
              v235 = (wchar_t *)std::wstring::_Calculate_growth(v219, 7);
              v221 = (struct _EVENT_DATA_DESCRIPTOR *)std::wstring::_Allocate_for_capacity<0>(v222, &v235);
              v242.Ptr = (ULONGLONG)v221;
              *(_QWORD *)&v243 = v219;
              v220 = (unsigned __int64)v235;
              *((_QWORD *)&v243 + 1) = v235;
              memcpy_0(v221, v215, 2 * v219 + 2);
            }
            else
            {
              *(_QWORD *)&v243 = *(_QWORD *)(a2 + 352);
              v220 = 7;
              *((_QWORD *)&v243 + 1) = 7;
              v242 = *(struct _EVENT_DATA_DESCRIPTOR *)v215;
              v221 = (struct _EVENT_DATA_DESCRIPTOR *)v242.Ptr;
            }
            v223 = &v242;
            if ( v220 > 7 )
              v223 = v221;
            v233[0] = (_Mtx_t)L"ccsOsVer";
            v233[1] = (_Mtx_t)8;
            JsonImplementType<wchar_t *>::AddValue((int)v249, v53, 0, (int)&EventDescriptor, (__int64)v233, v223);
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)&v242);
            goto LABEL_402;
          }
        }
      }
    }
LABEL_426:
    std::_Xlen_string();
  }
LABEL_403:
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UtcAzureVmPartAExtenstion>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_UtcAzureVmPartAExtenstion>::GetImpl'::`2'::impl)
    && *(_BYTE *)(a2 + 472) )
  {
    std::unique_lock<std::recursive_mutex>::unique_lock<std::recursive_mutex>(&EventDescriptor, a2 + 376);
    v224 = *(_QWORD *)(a2 + 464);
    if ( v224 )
      _InterlockedIncrement((volatile signed __int32 *)(v224 + 8));
    v225 = *(struct _Mtx_internal_imp_t **)(a2 + 456);
    v249[0] = v225;
    v249[1] = *(_Mtx_t *)(a2 + 464);
    if ( LOBYTE(EventDescriptor.Keyword) )
      _Mtx_unlock(*(_Mtx_t *)&EventDescriptor.Id);
    if ( v225 )
    {
      *(_QWORD *)&EventDescriptor.Id = L"azureVm";
      EventDescriptor.Keyword = 7;
      *(_OWORD *)v233 = *v188;
      Microsoft::Diagnostics::IAsimovEvent::CreateOrGetExtensionObject(a1, v250, v233, &EventDescriptor);
      if ( *((_QWORD *)v225 + 3) <= 7u )
        v226 = v225;
      else
        v226 = *(struct _Mtx_internal_imp_t **)v225;
      v227 = *((_QWORD *)v225 + 2);
      v228 = *(_OWORD *)v250;
      if ( v227 )
      {
        *(_QWORD *)&EventDescriptor.Id = v226;
        EventDescriptor.Keyword = v227;
        v233[0] = (_Mtx_t)L"cloudEnv";
        v233[1] = (_Mtx_t)8;
        Microsoft::Diagnostics::IAsimovEvent::AddValueIfNotPresent<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>>(
          a1,
          v250,
          v233,
          &EventDescriptor);
      }
      if ( *((_QWORD *)v225 + 23) <= 7u )
        v229 = (__int64 *)((char *)v225 + 160);
      else
        v229 = (__int64 *)*((_QWORD *)v225 + 20);
      v230 = *((_QWORD *)v225 + 22);
      if ( v230 )
      {
        *(_QWORD *)&EventDescriptor.Id = v229;
        EventDescriptor.Keyword = v230;
        v233[0] = (_Mtx_t)L"vmId";
        v233[1] = (_Mtx_t)4;
        *(_OWORD *)v250 = v228;
        Microsoft::Diagnostics::IAsimovEvent::AddValueIfNotPresent<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>>(
          a1,
          v250,
          v233,
          &EventDescriptor);
      }
      if ( *((_QWORD *)v225 + 11) <= 7u )
        v231 = (__int64 *)((char *)v225 + 64);
      else
        v231 = (__int64 *)*((_QWORD *)v225 + 8);
      *(_QWORD *)&EventDescriptor.Id = v231;
      EventDescriptor.Keyword = *((_QWORD *)v225 + 10);
      *(_OWORD *)v233 = *(_OWORD *)std::wstring_view::basic_string_view<wchar_t,std::char_traits<wchar_t>>(
                                     v237,
                                     L"name");
      *(_OWORD *)v250 = v228;
      Microsoft::Diagnostics::IAsimovEvent::AddNonEmptyStringIfNotPresent(a1, v250, v233, &EventDescriptor);
      EventDescriptor = *(EVENT_DESCRIPTOR *)std::wstring::operator std::wstring_view((char *)v225 + 32, v237);
      *(_OWORD *)v233 = *(_OWORD *)std::wstring_view::basic_string_view<wchar_t,std::char_traits<wchar_t>>(
                                     &v235,
                                     L"region");
      *(_OWORD *)v250 = v228;
      Microsoft::Diagnostics::IAsimovEvent::AddNonEmptyStringIfNotPresent(a1, v250, v233, &EventDescriptor);
      EventDescriptor = *(EVENT_DESCRIPTOR *)std::wstring::operator std::wstring_view((char *)v225 + 96, v237);
      *(_OWORD *)v233 = *(_OWORD *)std::wstring_view::basic_string_view<wchar_t,std::char_traits<wchar_t>>(
                                     v246,
                                     L"resourceId");
      *(_OWORD *)v250 = v228;
      Microsoft::Diagnostics::IAsimovEvent::AddNonEmptyStringIfNotPresent(a1, v250, v233, &EventDescriptor);
      EventDescriptor = *(EVENT_DESCRIPTOR *)std::wstring::operator std::wstring_view((char *)v225 + 128, v237);
      *(_OWORD *)v233 = *(_OWORD *)std::wstring_view::basic_string_view<wchar_t,std::char_traits<wchar_t>>(
                                     v238,
                                     L"subscription");
      *(_OWORD *)v250 = v228;
      Microsoft::Diagnostics::IAsimovEvent::AddNonEmptyStringIfNotPresent(a1, v250, v233, &EventDescriptor);
    }
    std::shared_ptr<Microsoft::Diagnostics::ProviderGroupInfo const>::~shared_ptr<Microsoft::Diagnostics::ProviderGroupInfo const>(v249);
  }
  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)&UserData);
  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)Src);
}

```

## disassembly

```asm
0x180062cc0  mov     rax, rsp
0x180062cc3  push    rbp
0x180062cc4  push    rbx
0x180062cc5  push    rsi
0x180062cc6  push    rdi
0x180062cc7  push    r12
0x180062cc9  push    r13
0x180062ccb  push    r14
0x180062ccd  push    r15
0x180062ccf  lea     rbp, [rax-1C8h]
0x180062cd6  sub     rsp, 288h
0x180062cdd  movaps  xmmword ptr [rax-58h], xmm6
0x180062ce1  movaps  xmmword ptr [rax-68h], xmm7
0x180062ce5  mov     rax, cs:__security_cookie
0x180062cec  xor     rax, rsp
0x180062cef  mov     [rbp+1C0h+var_70], rax
0x180062cf6  mov     r15, r9
0x180062cf9  mov     [rsp+2C0h+var_268], r9
0x180062cfe  mov     r14, r8
0x180062d01  mov     [rsp+70h], r8
0x180062d06  mov     r12, rdx
0x180062d09  mov     r13, rcx
0x180062d0c  mov     edi, [rbp+1C0h+arg_20]
0x180062d12  mov     dword ptr [rsp+2C0h+var_258], edi
0x180062d16  xor     ebx, ebx
0x180062d18  mov     esi, ebx
0x180062d1a  mov     dword ptr [rbp+1C0h+var_240], ebx
0x180062d1d  mov     dword ptr [rbp+1C0h+var_1E0], ebx
0x180062d20  xorps   xmm0, xmm0
0x180062d23  movups  xmmword ptr [rbp+1C0h+Src], xmm0
0x180062d27  mov     [rbp+1C0h+var_170], rbx
0x180062d2b  mov     [rbp+1C0h+var_168], 7
0x180062d33  mov     word ptr [rbp+1C0h+Src], bx
0x180062d37  movzx   eax, byte ptr [rcx+120h]
0x180062d3e  dec     al
0x180062d40  cmp     al, 2
0x180062d42  jbe     loc_1800630ED
0x180062d48  lea     rdx, [rcx+130h]
0x180062d4f  mov     r8, [rdx+10h]
0x180062d53  test    r8, r8
0x180062d56  jz      loc_1800630ED
0x180062d5c  mov     rax, [rcx+1B8h]
0x180062d63  lea     rcx, unk_18043B3B0
0x180062d6a  test    rax, rax
0x180062d6d  cmovnz  rcx, rax
0x180062d71  cmp     qword ptr [rcx+18h], 7
0x180062d76  jbe     short loc_180062D7D
0x180062d78  mov     rax, [rcx]
0x180062d7b  jmp     short loc_180062D80
0x180062d7d  mov     rax, rcx
0x180062d80  mov     r9, [rcx+10h]
0x180062d84  cmp     qword ptr [rdx+18h], 7
0x180062d89  jbe     short loc_180062D8E
0x180062d8b  mov     rdx, [rdx]
0x180062d8e  mov     qword ptr [rbp+1C0h+EventDescriptor.Id], rax
0x180062d92  mov     [rbp+1C0h+EventDescriptor.Keyword], r9
0x180062d96  mov     [rsp+2C0h+var_288+8], rdx
0x180062d9b  mov     qword ptr [rsp+2C0h+var_278], r8
0x180062da0  lea     r9, [rbp+1C0h+EventDescriptor]
0x180062da4  lea     r8, [rsp+2C0h+var_288+8]
0x180062da9  lea     rdx, [rbp+1C0h+var_160]
0x180062dad  mov     rcx, r12
0x180062db0  call    ?GetUserId@AsimovSharedPartAState@Diagnostics@Microsoft@@QEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@5@0@Z; Microsoft::Diagnostics::AsimovSharedPartAState::GetUserId(std::wstring_view,std::wstring_view)
0x180062db5  mov     rdx, rax
0x180062db8  lea     rcx, [rbp+1C0h+Src]
0x180062dbc  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180062dc1  mov     rdx, qword ptr [rbp+1C0h+var_150+8]
0x180062dc5  cmp     rdx, 7
0x180062dc9  jbe     short loc_180062E01
0x180062dcb  lea     rdx, ds:2[rdx*2]
0x180062dd3  mov     rcx, [rbp+1C0h+var_160.Ptr]
0x180062dd7  cmp     rdx, 1000h
0x180062dde  jb      short loc_180062DFC
0x180062de0  mov     rax, [rcx-8]
0x180062de4  sub     rcx, rax
0x180062de7  sub     rcx, 8
0x180062deb  cmp     rcx, 1Fh
0x180062def  ja      loc_180063C99
0x180062df5  add     rdx, 27h ; '''; struct std::nothrow_t *
0x180062df9  mov     rcx, rax; void *
0x180062dfc  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180062e01  mov     qword ptr [rbp+1C0h+var_150], rbx
0x180062e05  mov     qword ptr [rbp+1C0h+var_150+8], 7
0x180062e0d  mov     word ptr [rbp+1C0h+var_160.Ptr], bx
0x180062e11  test    byte ptr [r13+2B8h], 2
0x180062e19  jz      loc_1800630ED
0x180062e1f  mov     rbx, [rbp+1C0h+var_170]
0x180062e23  lea     rcx, [rbp+1C0h+Src]
0x180062e27  cmp     [rbp+1C0h+var_168], 7
0x180062e2c  cmova   rcx, [rbp+1C0h+Src]; this
0x180062e31  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180062e35  jz      loc_180065D5F
0x180062e3b  test    rcx, rcx
0x180062e3e  jnz     short loc_180062E4B
0x180062e40  test    rbx, rbx
0x180062e43  jnz     loc_180065D5F
0x180062e49  jmp     short loc_180062E66
0x180062e4b  mov     rax, 7FFFFFFFFFFFFFFFh
0x180062e55  cmp     rbx, rax
0x180062e58  jnb     loc_180065D5F
0x180062e5e  add     rbx, rbx
0x180062e61  test    rcx, rcx
0x180062e64  jnz     short loc_180062E6F
0x180062e66  test    rbx, rbx
0x180062e69  jnz     loc_180065D5F
0x180062e6f  mov     rax, rdi
0x180062e72  mov     [rbp+1C0h+var_240], rax
0x180062e76  mov     [rbp+1C0h+var_1E0], rax
0x180062e7a  lea     r9, [rbp+1C0h+var_240]; unsigned __int64 *
0x180062e7e  lea     r8, [rbp+1C0h+var_1E0]; unsigned __int64 *
0x180062e82  mov     rdx, rbx; unsigned __int64
0x180062e85  call    ?Hash128@SpookyHash@@SAXPEBX_KPEA_K2@Z; SpookyHash::Hash128(void const *,unsigned __int64,unsigned __int64 *,unsigned __int64 *)
0x180062e8a  mov     r8, [rbp+1C0h+var_1E0]
0x180062e8e  cmp     rbx, 10h
0x180062e92  jnb     short loc_180062EA1
0x180062e94  shl     bl, 2
0x180062e97  mov     ecx, 3Fh ; '?'
0x180062e9c  sub     cl, bl
0x180062e9e  shr     r8, cl
0x180062ea1  lea     rdi, [rbp+1C0h+var_D6]
0x180062ea8  mov     r9, 0CCCCCCCCCCCCCCCDh
0x180062eb2  sub     rdi, 2
0x180062eb6  mov     rax, r9
0x180062eb9  mul     r8
0x180062ebc  shr     rdx, 3
0x180062ec0  movzx   eax, dx
0x180062ec3  shl     ax, 2
0x180062ec7  lea     ecx, [rax+rdx]
0x180062eca  add     cx, cx
0x180062ecd  sub     r8w, cx
0x180062ed1  add     r8w, 30h ; '0'
0x180062ed6  mov     [rdi], r8w
0x180062eda  mov     r8, rdx
0x180062edd  test    rdx, rdx
0x180062ee0  jnz     short loc_180062EB2
0x180062ee2  xorps   xmm0, xmm0
0x180062ee5  movups  xmmword ptr [rbp+1C0h+EventDescriptor.Id], xmm0
0x180062ee9  xor     ebx, ebx
0x180062eeb  mov     [rbp+1C0h+var_220], rbx
0x180062eef  mov     [rbp+1C0h+var_218], rbx
0x180062ef3  lea     rax, [rbp+1C0h+var_D6]
0x180062efa  cmp     rdi, rax
0x180062efd  jnz     short loc_180062F14
0x180062eff  mov     [rbp+1C0h+var_220], rbx
0x180062f03  mov     [rbp+1C0h+var_218], 7
0x180062f0b  mov     [rbp+1C0h+EventDescriptor.Id], bx
0x180062f0f  jmp     loc_180063010
0x180062f14  lea     rbx, [rbp+1C0h+var_D6]
0x180062f1b  sub     rbx, rdi
0x180062f1e  sar     rbx, 1
0x180062f21  mov     rax, 7FFFFFFFFFFFFFFEh
0x180062f2b  cmp     rbx, rax
0x180062f2e  ja      loc_180065D71
0x180062f34  cmp     rbx, 7
0x180062f38  ja      short loc_180062F64
0x180062f3a  mov     [rbp+1C0h+var_220], rbx
0x180062f3e  mov     [rbp+1C0h+var_218], 7
0x180062f46  add     rbx, rbx
0x180062f49  mov     r8, rbx; Size
0x180062f4c  mov     rdx, rdi; Src
0x180062f4f  lea     rcx, [rbp+1C0h+EventDescriptor]; void *
0x180062f53  call    memcpy_0
0x180062f58  xor     eax, eax
0x180062f5a  mov     [rbp+rbx+1C0h+EventDescriptor.Id], ax
0x180062f5f  jmp     loc_18006300E
0x180062f64  mov     rsi, rbx
0x180062f67  or      rsi, 7
0x180062f6b  cmp     rsi, rax
0x180062f6e  jbe     short loc_180062FAF
0x180062f70  mov     rsi, rax
0x180062f73  mov     rcx, 0FFFFFFFFFFFFFFFEh; Size
0x180062f7a  cmp     rcx, 1000h
0x180062f81  jb      short loc_180062FDD
0x180062f83  lea     rax, [rcx+27h]
0x180062f87  cmp     rax, rcx
0x180062f8a  jbe     loc_180065D77
0x180062f90  mov     rcx, rax; Size
0x180062f93  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180062f98  test    rax, rax
0x180062f9b  jz      loc_180063C99
0x180062fa1  lea     r14, [rax+27h]
0x180062fa5  and     r14, 0FFFFFFFFFFFFFFE0h
0x180062fa9  mov     [r14-8], rax
0x180062fad  jmp     short loc_180062FE5
0x180062faf  cmp     rsi, 0Ah
0x180062fb3  mov     eax, 0Ah
0x180062fb8  cmovb   rsi, rax
0x180062fbc  lea     rcx, [rsi+1]
0x180062fc0  mov     rax, 7FFFFFFFFFFFFFFFh
0x180062fca  cmp     rcx, rax
0x180062fcd  ja      loc_180065D77
0x180062fd3  add     rcx, rcx
0x180062fd6  jnz     short loc_180062F7A
0x180062fd8  xor     r14d, r14d
0x180062fdb  jmp     short loc_180062FE5
0x180062fdd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180062fe2  mov     r14, rax
0x180062fe5  mov     qword ptr [rbp+1C0h+EventDescriptor.Id], r14
0x180062fe9  mov     [rbp+1C0h+var_220], rbx
0x180062fed  mov     [rbp+1C0h+var_218], rsi
0x180062ff1  add     rbx, rbx
0x180062ff4  mov     r8, rbx; Size
0x180062ff7  mov     rdx, rdi; Src
0x180062ffa  mov     rcx, r14; void *
0x180062ffd  call    memcpy_0
0x180063002  xor     ecx, ecx
0x180063004  mov     [rbx+r14], cx
0x180063009  mov     r14, [rsp+70h]
0x18006300e  xor     ebx, ebx
0x180063010  mov     r9d, 2
0x180063016  lea     r8, aD_0; "d:"
0x18006301d  lea     rcx, [rbp+1C0h+EventDescriptor]; Src
0x180063021  call    ??$_Insert@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KQEB_W0@Z; std::wstring::_Insert<wchar_t>(unsigned __int64,wchar_t const * const,unsigned __int64)
0x180063026  movups  xmm0, xmmword ptr [rax]
0x180063029  movups  xmmword ptr [rbp+1C0h+var_160.Ptr], xmm0
0x18006302d  movups  xmm1, xmmword ptr [rax+10h]
0x180063031  movups  [rbp+1C0h+var_150], xmm1
0x180063035  mov     [rax+10h], rbx
0x180063039  mov     qword ptr [rax+18h], 7
0x180063041  mov     [rax], bx
0x180063044  mov     esi, 7
0x180063049  mov     dword ptr [rbp+1C0h+var_240], esi
0x18006304c  lea     rdx, [rbp+1C0h+var_160]
0x180063050  lea     rcx, [rbp+1C0h+Src]
0x180063054  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180063059  mov     rdx, qword ptr [rbp+1C0h+var_150+8]
0x18006305d  cmp     rdx, rsi
0x180063060  jbe     short loc_180063099
0x180063062  lea     rdx, ds:2[rdx*2]
0x18006306a  mov     rcx, [rbp+1C0h+var_160.Ptr]
0x18006306e  cmp     rdx, 1000h
0x180063075  jb      short loc_180063093
0x180063077  mov     rax, [rcx-8]
0x18006307b  sub     rcx, rax
0x18006307e  sub     rcx, 8
0x180063082  cmp     rcx, 1Fh
0x180063086  ja      loc_18006312C
0x18006308c  add     rdx, 27h ; '''; struct std::nothrow_t *
0x180063090  mov     rcx, rax; void *
0x180063093  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180063098  nop
0x180063099  mov     rdx, [rbp+1C0h+var_218]
0x18006309d  cmp     rdx, 7
0x1800630a1  jbe     short loc_1800630D9
0x1800630a3  lea     rdx, ds:2[rdx*2]
0x1800630ab  mov     rcx, qword ptr [rbp+1C0h+EventDescriptor.Id]
0x1800630af  cmp     rdx, 1000h
0x1800630b6  jb      short loc_1800630D4
0x1800630b8  mov     rax, [rcx-8]
0x1800630bc  sub     rcx, rax
0x1800630bf  sub     rcx, 8
0x1800630c3  cmp     rcx, 1Fh
0x1800630c7  ja      loc_180063C99
0x1800630cd  add     rdx, 27h ; '''; struct std::nothrow_t *
0x1800630d1  mov     rcx, rax; void *
0x1800630d4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800630d9  mov     [rbp+1C0h+var_220], rbx
0x1800630dd  mov     [rbp+1C0h+var_218], 7
0x1800630e5  mov     [rbp+1C0h+EventDescriptor.Id], bx
0x1800630e9  mov     edi, dword ptr [rsp+2C0h+var_258]
0x1800630ed  lea     rax, aDevice_1; "device"
0x1800630f4  mov     qword ptr [rbp+1C0h+EventDescriptor.Id], rax
0x1800630f8  mov     [rbp+1C0h+EventDescriptor.Keyword], 6
0x180063100  movups  xmm0, xmmword ptr [r14]
0x180063104  movaps  xmmword ptr [rbp+1C0h+var_1C0], xmm0
0x180063108  lea     r9, [rbp+1C0h+EventDescriptor]
0x18006310c  lea     r8, [rbp+1C0h+var_1C0]
0x180063110  lea     rdx, [rsp+2C0h+var_288+8]
0x180063115  mov     rcx, r13
0x180063118  call    ?CreateOrGetExtensionObject@IAsimovEvent@Diagnostics@Microsoft@@IEAA?AVJsonConstIterator@@V4@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::IAsimovEvent::CreateOrGetExtensionObject(JsonConstIterator,std::wstring_view)
0x18006311d  cmp     qword ptr [r12+30h], 7
0x180063123  jbe     short loc_180063133
0x180063125  mov     rcx, [r12+18h]
0x18006312a  jmp     short loc_180063138
0x18006312c  mov     ecx, 5
0x180063131  int     29h; Win8: RtlFailFast(ecx)
0x180063133  lea     rcx, [r12+18h]; this
0x180063138  movzx   eax, byte ptr [r13+120h]
0x180063140  dec     al
0x180063142  cmp     al, 1
0x180063144  jbe     loc_180063496
0x18006314a  mov     rax, [r12+28h]
0x18006314f  test    byte ptr [r13+2B8h], 2
0x180063157  jz      loc_18006344F
0x18006315d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180063161  jz      loc_180065D89
0x180063167  test    rcx, rcx
0x18006316a  jnz     short loc_18006317B
0x18006316c  test    rax, rax
0x18006316f  jnz     loc_180065D89
0x180063175  lea     rbx, [rax+rax]
0x180063179  jmp     short loc_180063197
0x18006317b  mov     rdx, 7FFFFFFFFFFFFFFFh
0x180063185  cmp     rax, rdx
0x180063188  jnb     loc_180065D89
0x18006318e  lea     rbx, [rax+rax]
0x180063192  test    rcx, rcx
0x180063195  jnz     short loc_1800631A0
0x180063197  test    rbx, rbx
0x18006319a  jnz     loc_180065D89
  ... truncated ...
```
