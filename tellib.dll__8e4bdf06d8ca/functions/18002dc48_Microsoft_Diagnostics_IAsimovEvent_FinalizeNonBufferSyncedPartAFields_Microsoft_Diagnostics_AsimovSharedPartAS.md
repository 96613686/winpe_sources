# Microsoft::Diagnostics::IAsimovEvent::FinalizeNonBufferSyncedPartAFields(Microsoft::Diagnostics::AsimovSharedPartAState &,ulong &)

- ea: `0x18002dc48`
- end: `0x18002ef6c`
- name: `?FinalizeNonBufferSyncedPartAFields@IAsimovEvent@Diagnostics@Microsoft@@AEAAXAEAVAsimovSharedPartAState@23@AEAK@Z`
- size: `4900`
- prototype: `void __fastcall(Microsoft::Diagnostics::IAsimovEvent *__hidden this, struct Microsoft::Diagnostics::AsimovSharedPartAState *, unsigned int *)`
- caller_count: `2`
- callee_count: `23`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180015efc`
- `0x180177e40`

## callees

- `0x18001c60c`
- `0x18001d160`
- `0x180020c1c`
- `0x180020fbc`
- `0x180024e2c`
- `0x180028188`
- `0x18002d630`
- `0x18002d710`
- `0x18002dc48`
- `0x18002ef74`
- `0x18002f344`
- `0x18003ec00`
- `0x180044138`
- `0x180046714`
- `0x18004bd70`
- `0x180062cc0`
- `0x1800a0d08`
- `0x1800aac70`
- `0x1800d2b24`
- `0x18012d940`
- `0x18012de40`
- `0x18012e324`
- `0x18012eaf0`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18002eed1`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18002ef5f`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18002eed1`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18002ef5f`
- `msvcp_win!_Mtx_unlock` at `0x18002dd07`
- `msvcp_win!_Mtx_unlock` at `0x18002dd07`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18002ee53`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18002ee6c`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18002ee53`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18002ee6c`
- `msvcp_win!_Mtx_lock` at `0x18002dcc2`
- `msvcp_win!_Mtx_lock` at `0x18002dcc2`
- `msvcp_win!?_Xbad_alloc@std@@YAXXZ` at `0x18002ef4b`
- `msvcp_win!?_Xbad_alloc@std@@YAXXZ` at `0x18002ef4b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002e20a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002ec1a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002e20a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002ec1a`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18002e22d`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18002ec3f`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18002e22d`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18002ec3f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002e530`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002ece7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002e530`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002ece7`

## string_xrefs

- `0x18002e6bf`: `onecore\base\telemetry\utc\service\asimov\iasimovevent.cpp`
- `0x18002e981`: `onecore\base\telemetry\utc\service\asimov\iasimovevent.cpp`
- `0x18002e9a0`: `onecore\base\telemetry\utc\service\asimov\iasimovevent.cpp`
- `0x18002e9bf`: `onecore\base\telemetry\utc\service\asimov\iasimovevent.cpp`
- `0x18002eaae`: `onecore\base\telemetry\utc\service\asimov\iasimovevent.cpp`
- `0x18002edd8`: `onecore\base\telemetry\utc\service\asimov\iasimovevent.cpp`
- `0x18002eea6`: `onecore\base\telemetry\utc\service\asimov\iasimovevent.cpp`
- `0x18002eeb8`: `onecore\base\telemetry\utc\service\asimov\iasimovevent.cpp`
- `0x18002ee3c`: `onecore\base\telemetry\utc\service\include\LifetimeManager.h`
- `0x18002eeca`: `JsonBuilder - cbValue too large`
- `0x18002ef58`: `JsonBuilder - too much data`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall Microsoft::Diagnostics::IAsimovEvent::FinalizeNonBufferSyncedPartAFields(
        Microsoft::Diagnostics::IAsimovEvent *this,
        struct Microsoft::Diagnostics::AsimovSharedPartAState *a2,
        unsigned int *a3,
        const char *a4)
{
  unsigned __int64 v7; // rsi
  unsigned __int64 v8; // rdi
  char *v9; // rbx
  int v10; // eax
  __int64 v11; // r9
  _DWORD **v12; // rsi
  unsigned int v13; // r15d
  _BYTE *v14; // rcx
  __int64 v15; // rax
  unsigned int i; // edx
  const wchar_t *v17; // r10
  _WORD *v18; // r11
  char v19; // al
  int v20; // r8d
  __int64 v21; // r13
  const wchar_t *v22; // rbx
  _BYTE *v23; // rcx
  __int64 v24; // r8
  int v25; // edi
  bool j; // zf
  unsigned int v27; // edx
  __int64 v28; // r9
  const wchar_t *v29; // r10
  _WORD *v30; // r11
  unsigned int v31; // edi
  unsigned int v32; // r10d
  const wchar_t *v33; // r14
  __int64 v34; // rcx
  __int64 v35; // r8
  int v36; // ebx
  unsigned int v37; // edx
  __int64 v38; // r9
  const wchar_t *v39; // r10
  _WORD *v40; // r11
  unsigned int v41; // ebx
  __int64 v42; // r14
  int v43; // r12d
  const wchar_t *v44; // r15
  __int64 v45; // rcx
  __int64 v46; // rdx
  bool k; // zf
  unsigned int v48; // r8d
  __int64 v49; // r9
  const wchar_t *v50; // r10
  _WORD *v51; // r11
  SIZE_T v52; // r15
  __int64 v53; // r14
  __int64 v54; // r13
  __int64 v55; // rcx
  __int64 v56; // rdx
  bool m; // zf
  unsigned int v58; // r8d
  __int64 v59; // r9
  const wchar_t *v60; // r10
  _WORD *v61; // r11
  unsigned int v62; // eax
  unsigned __int64 v63; // r14
  unsigned __int64 v64; // rax
  char *v65; // r14
  int v66; // r15d
  unsigned int v67; // edx
  char *v68; // r12
  unsigned int v69; // r10d
  unsigned int v70; // r13d
  unsigned int v71; // r11d
  unsigned int v72; // r15d
  SIZE_T v73; // r13
  HANDLE ProcessHeap; // rax
  _DWORD *v75; // rax
  __int64 v76; // r8
  const wchar_t *v77; // rdx
  char *v78; // r9
  __int64 v79; // rcx
  __int64 v80; // r8
  __int64 v81; // r15
  __int64 v82; // r14
  void *Src; // rax
  __int64 v84; // rax
  char *v85; // r12
  void **v87; // rax
  char *v88; // rbx
  __int64 trivial_2; // rax
  const char *v90; // r9
  const struct std::nothrow_t *v91; // rdx
  void *v92; // rcx
  const struct std::nothrow_t *v93; // rdx
  void *v94; // rcx
  const struct std::nothrow_t *v95; // rdx
  void *v96; // rcx
  __int64 v97; // r12
  char *v98; // rdi
  __int64 v99; // r15
  unsigned int v100; // r14d
  __int64 v101; // rcx
  _DWORD *v102; // rdx
  __int64 v103; // rcx
  __int64 v104; // r8
  __int64 v105; // r12
  char *v106; // rbx
  __int64 v107; // r13
  unsigned int v108; // r15d
  __int64 v109; // rcx
  _DWORD *v110; // rdx
  __int64 v111; // rcx
  __int64 v112; // r8
  char *v113; // r14
  __int64 v114; // r13
  unsigned int v115; // r12d
  __int64 v116; // rdx
  _DWORD *v117; // rdx
  void *v118; // r10
  __int64 v119; // rcx
  __int64 v120; // r8
  char *v121; // r15
  unsigned int v122; // r12d
  __int64 v123; // r8
  const wchar_t *v124; // rcx
  __int64 v125; // r10
  _DWORD *v126; // rdx
  __int64 v127; // rcx
  __int64 v128; // r8
  __int64 v129; // r14
  const wchar_t *v130; // r15
  _BYTE *v131; // r13
  __int64 v132; // rcx
  __int64 v133; // rdx
  unsigned int n; // edx
  __int64 v135; // r9
  const wchar_t *v136; // r10
  _WORD *v137; // r11
  __int64 v138; // r15
  unsigned int v139; // edx
  unsigned __int64 v140; // r11
  __int64 *v141; // r14
  __int64 v142; // r13
  unsigned int v143; // r12d
  HANDLE v144; // rax
  _DWORD *v145; // rax
  __int64 v146; // rdx
  const wchar_t *v147; // r8
  __int64 *v148; // r10
  __int64 v149; // rcx
  __int64 v150; // r8
  char *v151; // r12
  __int64 v152; // r13
  __int64 v153; // rcx
  _DWORD *v154; // rdx
  __int64 v155; // rcx
  __int64 v156; // r8
  __int64 BuildId; // rax
  __int64 v158; // rax
  int v159; // r8d
  unsigned int v160; // [rsp+20h] [rbp-E0h]
  unsigned int v161; // [rsp+20h] [rbp-E0h]
  unsigned int v162; // [rsp+30h] [rbp-D0h]
  unsigned int v163; // [rsp+38h] [rbp-C8h]
  unsigned int v164; // [rsp+40h] [rbp-C0h]
  int dwFlags; // [rsp+44h] [rbp-BCh]
  int dwFlagsa; // [rsp+44h] [rbp-BCh]
  void *v167; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v168[2]; // [rsp+50h] [rbp-B0h] BYREF
  SIZE_T dwBytes[2]; // [rsp+60h] [rbp-A0h] BYREF
  int v170[4]; // [rsp+70h] [rbp-90h] BYREF
  void *v171[2]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int64 v172; // [rsp+90h] [rbp-70h] BYREF
  __int128 v173; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int NewCapacity; // [rsp+B0h] [rbp-50h]
  int v175; // [rsp+B4h] [rbp-4Ch]
  __int64 v176; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int64 v177[2]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned int *v178; // [rsp+D0h] [rbp-30h]
  LPVOID lpMem; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int64 v180; // [rsp+E8h] [rbp-18h]
  __int64 v181; // [rsp+F0h] [rbp-10h]
  unsigned __int64 v182; // [rsp+F8h] [rbp-8h]
  void *v183[2]; // [rsp+100h] [rbp+0h] BYREF
  __int128 v184; // [rsp+110h] [rbp+10h]
  _BYTE v185[32]; // [rsp+120h] [rbp+20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]

  v178 = a3;
  *(_QWORD *)&v173 = a2;
  v172 = (unsigned __int64)this;
  v7 = *((_QWORD *)this + 33);
  if ( !_InterlockedCompareExchange64((volatile signed __int64 *)&xmmword_18043BF50, 0, 0) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x59,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\include\\LifetimeManager.h",
      a4);
  v8 = *(unsigned int *)(xmmword_18043BF50 + 8);
  v9 = (char *)a2 + 616;
  if ( _Mtx_lock((struct Microsoft::Diagnostics::AsimovSharedPartAState *)((char *)a2 + 616)) )
  {
    std::_Throw_Cpp_error(5);
    __debugbreak();
    goto LABEL_213;
  }
  if ( *((_DWORD *)v9 + 19) == 0x7FFFFFFF )
  {
LABEL_213:
    *((_DWORD *)v9 + 19) = 2147483646;
    std::_Throw_Cpp_error(6);
    __debugbreak();
LABEL_214:
    if ( v10 != (_DWORD)v8 + 1 )
    {
      *((_DWORD *)a2 + 174) = v8;
      *((_QWORD *)a2 + 88) = 0;
      *((_QWORD *)a2 + 89) = 0;
    }
    goto LABEL_5;
  }
  v8 = v7 / (600000000 * v8);
  v10 = *((_DWORD *)a2 + 174);
  if ( v10 != (_DWORD)v8 )
    goto LABEL_214;
LABEL_5:
  _Mtx_unlock((_Mtx_t)v9);
  *a3 = v8;
  v12 = (_DWORD **)((char *)this + 16);
  v13 = 0;
  if ( !*((_DWORD *)this + 6) )
    goto LABEL_18;
  v14 = *v12;
  if ( *((_BYTE *)*v12 + 7) < 0xFEu )
    goto LABEL_18;
  v15 = (2 * (*((_DWORD *)v14 + 1) & 0xFFFFFFu) + 15) >> 2;
  if ( (_DWORD)v15 == *((_DWORD *)v14 + 2) )
    goto LABEL_18;
  for ( i = *(_DWORD *)&v14[4 * v15];
        v14[4 * i + 7] == 0xFD || (*(_DWORD *)&v14[4 * i + 4] & 0xFFFFFF) != 1;
        i = *(_DWORD *)&v14[4 * i] )
  {
LABEL_15:
    if ( i == *((_DWORD *)v14 + 2) )
      goto LABEL_18;
  }
  v11 = 1;
  v17 = L"a";
  v18 = &v14[4 * i + 12];
  while ( v11 )
  {
    if ( *v18 != *v17 )
      goto LABEL_15;
    --v11;
    ++v18;
    ++v17;
  }
  v13 = i;
  if ( i )
    v19 = 0;
  else
LABEL_18:
    v19 = 1;
  if ( v19 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x3C,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\asimov\\iasimovevent.cpp",
      (const char *)v11);
  *(_QWORD *)v170 = (char *)this + 16;
  v170[2] = v13;
  v170[3] = HIDWORD(v168[1]);
  if ( (*((_BYTE *)this + 699) & 8) == 0 )
  {
    if ( *((_QWORD *)this + 44) )
    {
      std::wstring::operator std::wstring_view((char *)this + 336, &lpMem);
      dwBytes[0] = (SIZE_T)L"iKey";
      dwBytes[1] = 4;
      JsonImplementType<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>>::AddValue(
        (unsigned int)v168,
        (_DWORD)this + 16,
        v20,
        (unsigned int)v170,
        (__int64)dwBytes,
        (__int64)&lpMem);
      *((_BYTE *)this + 699) |= 8u;
    }
    else
    {
      v84 = *((_QWORD *)this + 48);
      if ( !v84 )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0xE1,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\asimov\\iasimovevent.cpp",
          (const char *)v11);
      v85 = (char *)this + 368;
      if ( *((_QWORD *)this + 49) > 7u )
        v85 = (char *)*((_QWORD *)this + 46);
      v88 = &v85[2 * v84];
      trivial_2 = _std_find_trivial_2(v85, v88, 45);
      if ( (char *)trivial_2 == v88 || (trivial_2 - (__int64)v85) >> 1 == -1 )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0xD5,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\asimov\\iasimovevent.cpp",
          v90);
      *(_OWORD *)v183 = 0;
      v184 = 0;
      std::wstring::_Construct<1,wchar_t *>(v183, L"o:", 2);
      std::wstring::_Append<wchar_t>(v183);
      v87 = v183;
      if ( *((_QWORD *)&v184 + 1) > 7u )
        v87 = (void **)v183[0];
      lpMem = L"iKey";
      v180 = 4;
      JsonImplementType<wchar_t *>::AddValue((int)v168, (_DWORD)this + 16, 0, (int)v170, (__int64)&lpMem, v87);
      *((_BYTE *)this + 699) |= 8u;
      if ( *((_QWORD *)&v184 + 1) > 7u )
      {
        v95 = (const struct std::nothrow_t *)(2LL * *((_QWORD *)&v184 + 1) + 2);
        dwBytes[0] = (SIZE_T)v95;
        v96 = v183[0];
        v167 = v183[0];
        if ( (unsigned __int64)v95 >= 0x1000 )
        {
          std::_Adjust_manually_vector_aligned(&v167, dwBytes);
          v95 = (const struct std::nothrow_t *)dwBytes[0];
          v96 = v167;
        }
        operator delete(v96, v95);
      }
    }
  }
  LODWORD(v21) = 0;
  v162 = 0;
  v22 = L"ext";
  if ( *((_DWORD *)v12 + 2) )
  {
    v23 = *v12;
    if ( HIBYTE((*v12)[v13 + 1]) >= 0xFEu )
    {
      v24 = v13 + ((2 * (*(_DWORD *)&v23[4 * v13 + 4] & 0xFFFFFFu) + 15) >> 2);
      v25 = *(_DWORD *)&v23[4 * v13 + 8];
      for ( j = (_DWORD)v24 == v25; !j; j = v27 == v25 )
      {
        v27 = *(_DWORD *)&v23[4 * v24];
        v24 = v27;
        if ( v23[4 * v27 + 7] != 0xFD && (*(_DWORD *)&v23[4 * v27 + 4] & 0xFFFFFF) == 3 )
        {
          v28 = 3;
          v29 = L"ext";
          v30 = &v23[4 * v27 + 12];
          while ( v28 )
          {
            if ( *v30 != *v29 )
              goto LABEL_33;
            --v28;
            ++v30;
            ++v29;
          }
          LODWORD(v21) = v27;
          v162 = v27;
          break;
        }
LABEL_33:
        ;
      }
    }
  }
  v31 = HIDWORD(v168[1]);
  if ( !(_DWORD)v21 )
  {
    JsonBuilder::EnsureRootExists((JsonBuilder *)v12);
    v97 = v13;
    v98 = (char *)*v12;
    if ( HIBYTE((*v12)[v13 + 1]) < 0xFEu )
      __int2c();
    v21 = *((unsigned int *)v12 + 2);
    v162 = v21;
    v99 = (unsigned int)(v21 + 5);
    v100 = v21 + 7;
    if ( (int)v21 + 7 < (unsigned int)v21 )
      goto LABEL_220;
    JsonInternal::PodVector<unsigned int>::reserve(v12, v100);
    *((_DWORD *)v12 + 2) = v100;
    v101 = (__int64)*v12;
    *(_DWORD *)(v101 + 4 * v21) = 0;
    *(_DWORD *)(v101 + 4 * v21 + 4) = *(_DWORD *)(v101 + 4 * v21 + 4) & 0xFF000000 ^ 3;
    *(_BYTE *)(v101 + 4 * v21 + 7) = -1;
    if ( v98 != (char *)*v12 && v98 < (char *)L"ext" && L"ext" < (wchar_t *)&v98[4 * v21] )
      v22 = (wchar_t *)((char *)L"ext" + (char *)*v12 - v98);
    *(_DWORD *)(v101 + 4 * v21 + 12) = *(_DWORD *)v22;
    *(_WORD *)(v101 + 4 * v21 + 16) = v22[2];
    *(_DWORD *)(v101 + 4 * v21 + 8) = v99;
    v102 = *v12;
    v102[v99] = **v12;
    v102[v99 + 1] &= 0xFF000000;
    HIBYTE(v102[v99 + 1]) = -3;
    *v102 = v99;
    v103 = (unsigned int)(*v12)[v97 + 2];
    (*v12)[v97 + 2] = v21;
    v104 = (__int64)*v12;
    *(_DWORD *)(v104 + 4 * v21) = (*v12)[v103];
    *(_DWORD *)(v104 + 4 * v103) = v21;
    v31 = HIDWORD(v168[1]);
    if ( !(_DWORD)v21 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x472,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\asimov\\iasimovevent.cpp",
        (const char *)0xD,
        v160);
  }
  v32 = 0;
  v164 = 0;
  v33 = L"utc";
  if ( *((_DWORD *)v12 + 2) )
  {
    v34 = (__int64)*v12;
    if ( HIBYTE((*v12)[(unsigned int)v21 + 1]) >= 0xFEu )
    {
      v35 = (unsigned int)v21 + ((2 * (*(_DWORD *)(v34 + 4LL * (unsigned int)v21 + 4) & 0xFFFFFFu) + 15) >> 2);
      v36 = *(_DWORD *)(v34 + 4LL * (unsigned int)v21 + 8);
      if ( (_DWORD)v35 != v36 )
      {
        while ( 1 )
        {
          v37 = *(_DWORD *)(v34 + 4 * v35);
          v35 = v37;
          if ( *(_BYTE *)(v34 + 4LL * v37 + 7) != 0xFD && (*(_DWORD *)(v34 + 4LL * v37 + 4) & 0xFFFFFF) == 3 )
            break;
LABEL_45:
          if ( v37 == v36 )
          {
            v32 = 0;
            goto LABEL_48;
          }
        }
        v38 = 3;
        v39 = L"utc";
        v40 = (_WORD *)(v34 + 12 + 4LL * v37);
        while ( v38 )
        {
          if ( *v40 != *v39 )
            goto LABEL_45;
          --v38;
          ++v40;
          ++v39;
        }
        v32 = v37;
        v164 = v37;
      }
    }
  }
LABEL_48:
  v41 = HIDWORD(v168[1]);
  if ( v32 )
  {
    dwBytes[0] = (unsigned int)v21;
    v42 = (unsigned int)v21;
  }
  else
  {
    JsonBuilder::EnsureRootExists((JsonBuilder *)v12);
    v105 = (unsigned int)v21;
    dwBytes[0] = (unsigned int)v21;
    v106 = (char *)*v12;
    if ( HIBYTE((*v12)[(unsigned int)v21 + 1]) < 0xFEu )
      __int2c();
    v164 = *((_DWORD *)v12 + 2);
    v107 = v164 + 5;
    v108 = v164 + 7;
    if ( v164 + 7 < v164 )
      goto LABEL_220;
    JsonInternal::PodVector<unsigned int>::reserve(v12, v108);
    *((_DWORD *)v12 + 2) = v108;
    v109 = (__int64)*v12;
    *(_DWORD *)(v109 + 4LL * v164) = 0;
    *(_DWORD *)(v109 + 4LL * v164 + 4) = *(_DWORD *)(v109 + 4LL * v164 + 4) & 0xFF000000 ^ 3;
    *(_BYTE *)(v109 + 4LL * v164 + 7) = -1;
    if ( v106 != (char *)*v12 && v106 < (char *)L"utc" && L"utc" < (const wchar_t *)&v106[4 * v164] )
      v33 = (const wchar_t *)((char *)L"utc" + (char *)*v12 - v106);
    *(_DWORD *)(v109 + 4LL * v164 + 12) = *(_DWORD *)v33;
    *(_WORD *)(v109 + 4LL * v164 + 16) = v33[2];
    *(_DWORD *)(v109 + 4LL * v164 + 8) = v107;
    v110 = *v12;
    v110[v107] = **v12;
    v110[v107 + 1] &= 0xFF000000;
    HIBYTE(v110[v107 + 1]) = -3;
    *v110 = v107;
    v111 = (unsigned int)(*v12)[v105 + 2];
    (*v12)[v105 + 2] = v164;
    v112 = (__int64)*v12;
    *(_DWORD *)(v112 + 4LL * v164) = (*v12)[v111];
    *(_DWORD *)(v112 + 4 * v111) = v164;
    v41 = HIDWORD(v168[1]);
    if ( !v164 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x472,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\asimov\\iasimovevent.cpp",
        (const char *)0xD,
        v160);
    v42 = v105;
  }
  v43 = 0;
  v163 = 0;
  v44 = L"os";
  if ( *((_DWORD *)v12 + 2) )
  {
    v42 = v162;
    v45 = (__int64)*v12;
    if ( HIBYTE((*v12)[v162 + 1]) >= 0xFEu )
    {
      v46 = ((2 * (*(_DWORD *)(v45 + 4LL * v162 + 4) & 0xFFFFFFu) + 15) >> 2) + v162;
      for ( k = (_DWORD)v46 == *(_DWORD *)(v45 + 4LL * v162 + 8); !k; k = v48 == *(_DWORD *)(v45 + 4LL * v162 + 8) )
      {
        v48 = *(_DWORD *)(v45 + 4 * v46);
        v46 = v48;
        if ( *(_BYTE *)(v45 + 4LL * v48 + 7) != 0xFD && (*(_DWORD *)(v45 + 4LL * v48 + 4) & 0xFFFFFF) == 2 )
        {
          v49 = 2;
          v50 = L"os";
          v51 = (_WORD *)(v45 + 12 + 4LL * v48);
          while ( v49 )
          {
            if ( *v51 != *v50 )
              goto LABEL_60;
            --v49;
            ++v51;
            ++v50;
          }
          v43 = v48;
          v163 = v48;
          break;
        }
LABEL_60:
        ;
      }
    }
  }
  *(_QWORD *)v170 = v12;
  v170[2] = v43;
  v170[3] = HIDWORD(v168[1]);
  if ( v43 )
  {
    v52 = dwBytes[0];
    v167 = (void *)(4 * dwBytes[0]);
    v53 = 4 * dwBytes[0];
  }
  else
  {
    JsonBuilder::EnsureRootExists((JsonBuilder *)v12);
    v167 = (void *)(4 * v42);
    v113 = (char *)*v12;
    if ( *((_BYTE *)v167 + (_QWORD)*v12 + 7) < 0xFEu )
      __int2c();
    v163 = *((_DWORD *)v12 + 2);
    v114 = v163 + 4;
    v115 = v163 + 6;
    if ( v163 + 6 < v163 )
      goto LABEL_220;
    JsonInternal::PodVector<unsigned int>::reserve(v12, v115);
    *((_DWORD *)v12 + 2) = v115;
    v116 = (__int64)*v12;
    *(_DWORD *)(v116 + 4LL * v163) = 0;
    *(_DWORD *)(v116 + 4LL * v163 + 4) = *(_DWORD *)(v116 + 4LL * v163 + 4) & 0xFF000000 ^ 2;
    *(_BYTE *)(v116 + 4LL * v163 + 7) = -1;
    if ( v113 != (char *)*v12 && v113 < (char *)L"os" && L"os" < (const wchar_t *)&v113[4 * v163] )
      v44 = (const wchar_t *)((char *)L"os" + (char *)*v12 - v113);
    *(_DWORD *)(v116 + 4LL * v163 + 12) = *(_DWORD *)v44;
    *(_DWORD *)(v116 + 4LL * v163 + 8) = v114;
    v117 = *v12;
    v117[v114] = **v12;
    v117[v114 + 1] &= 0xFF000000;
    HIBYTE(v117[v114 + 1]) = -3;
    *v117 = v114;
    v118 = v167;
    v119 = *(unsigned int *)((char *)*v12 + (_QWORD)v167 + 8);
    *(_DWORD *)((char *)*v12 + (_QWORD)v167 + 8) = v163;
    v120 = (__int64)*v12;
    *(_DWORD *)(v120 + 4LL * v163) = (*v12)[v119];
    *(_DWORD *)(v120 + 4 * v119) = v163;
    *(_QWORD *)v170 = v12;
    v170[2] = v163;
    v170[3] = HIDWORD(v168[1]);
    if ( !v163 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x472,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\asimov\\iasimovevent.cpp",
        (const char *)0xD,
        v160);
    v53 = (__int64)v118;
    v52 = dwBytes[0];
  }
  LODWORD(v54) = 0;
  if ( *((_DWORD *)v12 + 2) )
  {
    v53 = 4 * v52;
    v55 = (__int64)*v12;
    if ( HIBYTE((*v12)[v52 + 1]) >= 0xFEu )
    {
      v56 = ((2 * (*(_DWORD *)(v55 + v53 + 4) & 0xFFFFFFu) + 15) >> 2) + v162;
      for ( m = (_DWORD)v56 == *(_DWORD *)(v55 + 4 * v52 + 8); !m; m = v58 == *(_DWORD *)(v55 + 4 * v52 + 8) )
      {
        v58 = *(_DWORD *)(v55 + 4 * v56);
        v56 = v58;
        if ( *(_BYTE *)(v55 + 4LL * v58 + 7) != 0xFD && (*(_DWORD *)(v55 + 4LL * v58 + 4) & 0xFFFFFF) == 7 )
        {
          v59 = 7;
          v60 = L"privacy";
          v61 = (_WORD *)(v55 + 12 + 4LL * v58);
          while ( v59 )
          {
            if ( *v61 != *v60 )
              goto LABEL_74;
            --v59;
            ++v61;
            ++v60;
          }
          LODWORD(v54) = v58;
          break;
        }
LABEL_74:
        ;
      }
    }
  }
  v62 = HIDWORD(v168[1]);
  if ( !(_DWORD)v54 )
  {
    JsonBuilder::EnsureRootExists((JsonBuilder *)v12);
    v121 = (char *)*v12;
    if ( *((_BYTE *)*v12 + v53 + 7) < 0xFEu )
      __int2c();
    v54 = *((unsigned int *)v12 + 2);
    v122 = v54 + 9;
    if ( (int)v54 + 9 < (unsigned int)v54 )
      goto LABEL_220;
    JsonInternal::PodVector<unsigned int>::reserve(v12, v122);
    *((_DWORD *)v12 + 2) = v122;
    v123 = (__int64)*v12;
    *(_DWORD *)(v123 + 4 * v54) = 0;
    *(_DWORD *)(v123 + 4 * v54 + 4) = *(_DWORD *)(v123 + 4 * v54 + 4) & 0xFF000000 ^ 7;
    *(_BYTE *)(v123 + 4 * v54 + 7) = -1;
    v124 = L"privacy";
    if ( v121 != (char *)*v12 && v121 < (char *)L"privacy" && L"privacy" < (wchar_t *)&v121[4 * v54] )
      v124 = (wchar_t *)((char *)L"privacy" + (char *)*v12 - v121);
    *(_QWORD *)(v123 + 4 * v54 + 12) = *(_QWORD *)v124;
    *(_DWORD *)(v123 + 4 * v54 + 20) = *((_DWORD *)v124 + 2);
    *(_WORD *)(v123 + 4 * v54 + 24) = v124[6];
    v125 = (unsigned int)(v54 + 7);
    *(_DWORD *)(v123 + 4 * v54 + 8) = v125;
    v126 = *v12;
    v126[v125] = **v12;
    v126[v125 + 1] &= 0xFF000000;
    HIBYTE(v126[v125 + 1]) = -3;
    *v126 = v125;
    v127 = *(unsigned int *)((char *)*v12 + v53 + 8);
    *(_DWORD *)((char *)*v12 + v53 + 8) = v54;
    v128 = (__int64)*v12;
    *(_DWORD *)(v128 + 4 * v54) = (*v12)[v127];
    *(_DWORD *)(v128 + 4 * v127) = v54;
    v62 = HIDWORD(v168[1]);
    if ( !(_DWORD)v54 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x472,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\asimov\\iasimovevent.cpp",
        (const char *)0xD,
        v160);
  }
  lpMem = v12;
  v180 = __PAIR64__(v62, v54);
  v63 = v172;
  Microsoft::Diagnostics::IAsimovEvent::AddPrivacyFields(v172, &lpMem);
  *(_OWORD *)v168 = *(_OWORD *)v170;
  lpMem = L"name";
  v180 = 4;
  JsonImplementType<wchar_t *>::AddValue((int)v171, (int)v12, 0, (int)v168, (__int64)&lpMem, L"Windows");
  v64 = v63 + 400;
  if ( *(_QWORD *)(v63 + 424) <= 7u )
    v65 = (char *)(v63 + 400);
  else
    v65 = *(char **)v64;
  v66 = *(_DWORD *)(v64 + 16);
  JsonBuilder::EnsureRootExists((JsonBuilder *)v12);
  v68 = (char *)*v12;
  if ( HIBYTE((*v12)[v163 + 1]) < 0xFEu )
    __int2c();
  v69 = 2 * v66;
  v175 = 2 * v66;
  if ( (unsigned int)(2 * v66) > 0xF0000000 )
    std::_Xlength_error("JsonBuilder - cbValue too large");
  v70 = *((_DWORD *)v12 + 2);
  LODWORD(v177[0]) = v70;
  v71 = v70 + 5;
  LODWORD(v171[0]) = v70 + 5;
  v72 = v70 + 5 + (((unsigned __int64)v69 + 3) >> 2);
  if ( v72 <= v70 )
    goto LABEL_220;
  if ( *((_DWORD *)v12 + 3) < v72 )
  {
    NewCapacity = JsonInternal::PodVectorBase::GetNewCapacity(v72, v67);
    v73 = 4LL * NewCapacity;
    lpMem = *v12;
    dwFlags = *((_BYTE *)v12 + 16) != 0 ? 8 : 0;
    ProcessHeap = GetProcessHeap();
    if ( lpMem )
      v75 = HeapReAlloc(ProcessHeap, dwFlags, lpMem, v73);
    else
      v75 = HeapAlloc(ProcessHeap, dwFlags, v73);
    if ( !v75 )
    {
LABEL_219:
      std::_Xbad_alloc();
      __debugbreak();
      goto LABEL_220;
    }
    *v12 = v75;
    *((_DWORD *)v12 + 3) = NewCapacity;
    v69 = v175;
    v70 = v177[0];
    v71 = (unsigned int)v171[0];
  }
  *((_DWORD *)v12 + 2) = v72;
  v76 = (__int64)*v12;
  *(_DWORD *)(v76 + 4LL * v70) = 0;
  *(_DWORD *)(v76 + 4LL * v70 + 4) &= 0xFF000003;
  *(_DWORD *)(v76 + 4LL * v70 + 4) |= 3u;
  *(_BYTE *)(v76 + 4LL * v70 + 7) = -11;
  v77 = L"ver";
  v78 = (char *)*v12;
  if ( v68 != (char *)*v12 && v68 < (char *)L"ver" && L"ver" < (wchar_t *)&v68[4 * v70] )
    v77 = (wchar_t *)((char *)L"ver" + v78 - v68);
  *(_DWORD *)(v76 + 4LL * v70 + 12) = *(_DWORD *)v77;
  *(_WORD *)(v76 + 4LL * v70 + 16) = v77[2];
  *(_DWORD *)(v76 + 4LL * v70 + 8) = v69;
  if ( v65 )
  {
    if ( v68 != v78 && v68 < v65 && v65 < &v68[4 * v70] )
      v65 = &v78[v65 - v68];
    memcpy_0(&(*v12)[v71], v65, v69);
  }
  v79 = (unsigned int)(*v12)[v163 + 2];
  (*v12)[v163 + 2] = v70;
  v80 = (__int64)*v12;
  *(_DWORD *)(v80 + 4LL * v70) = (*v12)[v79];
  *(_DWORD *)(v80 + 4 * v79) = v70;
  v81 = v173;
  v82 = *(_QWORD *)(Microsoft::Diagnostics::AsimovSharedPartAState::GetBuildId(v173, v183) + 16);
  if ( *((_QWORD *)&v184 + 1) > 7u )
  {
    v91 = (const struct std::nothrow_t *)(2LL * *((_QWORD *)&v184 + 1) + 2);
    v177[0] = (unsigned __int64)v91;
    v92 = v183[0];
    v171[0] = v183[0];
    if ( (unsigned __int64)v91 >= 0x1000 )
    {
      std::_Adjust_manually_vector_aligned(v171, v177);
      v92 = v171[0];
      v91 = (const struct std::nothrow_t *)v177[0];
    }
    operator delete(v92, v91);
  }
  if ( v82 )
  {
    BuildId = Microsoft::Diagnostics::AsimovSharedPartAState::GetBuildId(v81, v185);
    v158 = std::wstring::operator std::wstring_view(BuildId, v177);
    lpMem = *(LPVOID *)v158;
    v180 = *(_QWORD *)(v158 + 8);
    v171[0] = L"buildId";
    v171[1] = (void *)7;
    JsonImplementType<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>>::AddValue(
      (unsigned int)v183,
      (_DWORD)v12,
      v159,
      (unsigned int)v168,
      (__int64)v171,
      (__int64)&lpMem);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v185);
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DmaCommonSchema>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_DmaCommonSchema>::GetImpl'::`2'::impl) )
  {
    LODWORD(v129) = 0;
    v130 = L"metadata";
    v131 = v167;
    if ( *((_DWORD *)v12 + 2) )
    {
      v132 = (__int64)*v12;
      if ( *((_BYTE *)v167 + (_QWORD)*v12 + 7) >= 0xFEu )
      {
        v133 = ((2 * (*(_DWORD *)((_BYTE *)v167 + v132 + 4) & 0xFFFFFFu) + 15) >> 2) + v162;
        if ( (_DWORD)v133 != *(_DWORD *)(v132 + 4 * dwBytes[0] + 8) )
        {
          for ( n = *(_DWORD *)(v132 + 4 * v133);
                *(_BYTE *)(v132 + 4LL * n + 7) == 0xFD || (*(_DWORD *)(v132 + 4LL * n + 4) & 0xFFFFFF) != 8;
                n = *(_DWORD *)(v132 + 4LL * n) )
          {
LABEL_180:
            if ( n == *(_DWORD *)(v132 + 4 * dwBytes[0] + 8) )
              goto LABEL_183;
          }
          v135 = 8;
          v136 = L"metadata";
          v137 = (_WORD *)(v132 + 12 + 4LL * n);
          while ( v135 )
          {
            if ( *v137 != *v136 )
              goto LABEL_180;
            --v135;
            ++v137;
            ++v136;
          }
          LODWORD(v129) = n;
        }
      }
    }
LABEL_183:
    if ( !(_DWORD)v129 )
    {
      JsonBuilder::EnsureRootExists((JsonBuilder *)v12);
      v151 = (char *)*v12;
      if ( v131[(_QWORD)*v12 + 7] < 0xFEu )
        __int2c();
      v129 = *((unsigned int *)v12 + 2);
      v152 = (unsigned int)(v129 + 7);
      if ( (int)v129 + 9 < (unsigned int)v129 )
        goto LABEL_220;
      JsonInternal::PodVector<unsigned int>::reserve(v12, (unsigned int)(v129 + 9));
      *((_DWORD *)v12 + 2) = v129 + 9;
      v153 = (__int64)*v12;
      *(_DWORD *)(v153 + 4 * v129) = 0;
      *(_DWORD *)(v153 + 4 * v129 + 4) = *(_DWORD *)(v153 + 4 * v129 + 4) & 0xFF000000 ^ 8;
      *(_BYTE *)(v153 + 4 * v129 + 7) = -1;
      if ( v151 != (char *)*v12 && v151 < (char *)L"metadata" && L"metadata" < (wchar_t *)&v151[4 * v129] )
        v130 = (wchar_t *)((char *)L"metadata" + (char *)*v12 - v151);
      *(_OWORD *)(v153 + 4 * v129 + 12) = *(_OWORD *)v130;
      *(_DWORD *)(v153 + 4 * v129 + 8) = v152;
      v154 = *v12;
      v154[v152] = **v12;
      v154[v152 + 1] &= 0xFF000000;
      HIBYTE(v154[v152 + 1]) = -3;
      *v154 = v152;
      v155 = *(unsigned int *)((char *)*v12 + (_QWORD)v167 + 8);
      *(_DWORD *)((char *)*v12 + (_QWORD)v167 + 8) = v129;
      v156 = (__int64)*v12;
      *(_DWORD *)(v156 + 4 * v129) = (*v12)[v155];
      *(_DWORD *)(v156 + 4 * v155) = v129;
      if ( !(_DWORD)v129 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x472,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\asimov\\iasimovevent.cpp",
          (const char *)0xD,
          v161);
    }
    v138 = qword_18043C210;
    v176 = qword_18043C210;
    JsonBuilder::EnsureRootExists((JsonBuilder *)v12);
    v140 = (unsigned int)v129;
    v167 = (void *)v140;
    v141 = (__int64 *)*v12;
    if ( HIBYTE((*v12)[v140 + 1]) < 0xFEu )
      __int2c();
    v142 = *((unsigned int *)v12 + 2);
    v143 = v142 + 9;
    if ( (int)v142 + 9 >= (unsigned int)v142 )
    {
      if ( *((_DWORD *)v12 + 3) >= v143 )
        goto LABEL_192;
      LODWORD(v171[0]) = JsonInternal::PodVectorBase::GetNewCapacity(v143, v139);
      dwBytes[0] = 4LL * LODWORD(v171[0]);
      lpMem = *v12;
      dwFlagsa = *((_BYTE *)v12 + 16) != 0 ? 8 : 0;
      v144 = GetProcessHeap();
      if ( lpMem )
        v145 = HeapReAlloc(v144, dwFlagsa, lpMem, dwBytes[0]);
      else
        v145 = HeapAlloc(v144, dwFlagsa, dwBytes[0]);
      if ( v145 )
      {
        *v12 = v145;
        *((_DWORD *)v12 + 3) = v171[0];
        v140 = (unsigned __int64)v167;
LABEL_192:
        *((_DWORD *)v12 + 2) = v143;
        v146 = (__int64)*v12;
        *(_DWORD *)(v146 + 4 * v142) = 0;
        *(_DWORD *)(v146 + 4 * v142 + 4) &= 0xFF000008;
        *(_DWORD *)(v146 + 4 * v142 + 4) |= 8u;
        *(_BYTE *)(v146 + 4 * v142 + 7) = -10;
        v147 = L"policies";
        v148 = (__int64 *)*v12;
        if ( v141 != (__int64 *)*v12 && v141 < (__int64 *)L"policies" && L"policies" < (wchar_t *)v141 + 2 * v142 )
          v147 = (wchar_t *)((char *)L"policies" + (char *)v148 - (char *)v141);
        *(_OWORD *)(v146 + 4 * v142 + 12) = *(_OWORD *)v147;
        *(_DWORD *)(v146 + 4 * v142 + 8) = 8;
        if ( v141 != v148 && v141 < &v176 && &v176 < (__int64 *)((char *)v141 + 4 * v142) )
          v138 = *(unsigned __int64 *)((char *)&v177[-1] + (char *)v148 - (char *)v141);
        *(_QWORD *)&(*v12)[(unsigned int)(v142 + 7)] = v138;
        v149 = (unsigned int)(*v12)[v140 + 2];
        (*v12)[v140 + 2] = v142;
        v150 = (__int64)*v12;
        *(_DWORD *)(v150 + 4 * v142) = (*v12)[v149];
        *(_DWORD *)(v150 + 4 * v149) = v142;
        v81 = v173;
        goto LABEL_96;
      }
      goto LABEL_219;
    }
LABEL_220:
    std::_Xlength_error("JsonBuilder - too much data");
  }
LABEL_96:
  lpMem = v12;
  v180 = __PAIR64__(v41, v164);
  *(_QWORD *)&v173 = v12;
  *((_QWORD *)&v173 + 1) = __PAIR64__(v31, v162);
  Microsoft::Diagnostics::IAsimovEvent::AddSomeExtFields(v172, v81, &v173, (wchar_t *)&lpMem, *v178);
  Microsoft::Diagnostics::AsimovSharedPartAState::GetFlightIdList(v81, &lpMem);
  if ( v181 )
  {
    v168[0] = (__int64)L"expId";
    v168[1] = 5;
    Src = (void *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(&lpMem);
    JsonImplementType<wchar_t *>::AddValue((int)v183, (int)v12, 0, (int)v170, (__int64)v168, Src);
  }
  if ( v182 > 7 )
  {
    v93 = (const struct std::nothrow_t *)(2 * v182 + 2);
    v172 = (unsigned __int64)v93;
    v94 = lpMem;
    *(_QWORD *)&v173 = lpMem;
    if ( (unsigned __int64)v93 >= 0x1000 )
    {
      std::_Adjust_manually_vector_aligned((void **)&v173, &v172);
      v93 = (const struct std::nothrow_t *)v172;
      v94 = (void *)v173;
    }
    operator delete(v94, v93);
  }
}

```

## disassembly

```asm
0x18002dc48  mov     [rsp-8+arg_18], rbx
0x18002dc4d  push    rbp
0x18002dc4e  push    rsi
0x18002dc4f  push    rdi
0x18002dc50  push    r12
0x18002dc52  push    r13
0x18002dc54  push    r14
0x18002dc56  push    r15
0x18002dc58  lea     rbp, [rsp-50h]
0x18002dc5d  sub     rsp, 150h
0x18002dc64  mov     rax, cs:__security_cookie
0x18002dc6b  xor     rax, rsp
0x18002dc6e  mov     [rbp+80h+var_40], rax
0x18002dc72  mov     r15, r8
0x18002dc75  mov     [rbp+80h+var_B0], r8
0x18002dc79  mov     r14, rdx
0x18002dc7c  mov     [rbp+80h+var_E0], rdx
0x18002dc80  mov     r13, rcx
0x18002dc83  mov     [rbp+80h+var_F0], rcx
0x18002dc87  mov     rsi, [rcx+108h]
0x18002dc8e  xor     ecx, ecx
0x18002dc90  xor     eax, eax
0x18002dc92  lock cmpxchg qword ptr cs:xmmword_18043BF50, rcx
0x18002dc9b  setz    al
0x18002dc9e  mov     rcx, [rbp+88h]; this
0x18002dca5  test    al, al
0x18002dca7  jnz     loc_18002EE3C
0x18002dcad  mov     rax, qword ptr cs:xmmword_18043BF50
0x18002dcb4  mov     edi, [rax+8]
0x18002dcb7  nop
0x18002dcb8  lea     rbx, [rdx+268h]
0x18002dcbf  mov     rcx, rbx; _Mtx_t
0x18002dcc2  call    cs:__imp__Mtx_lock
0x18002dcc9  nop     dword ptr [rax+rax+00h]
0x18002dcce  test    eax, eax
0x18002dcd0  jnz     loc_18002EE4E
0x18002dcd6  cmp     dword ptr [rbx+4Ch], 7FFFFFFFh
0x18002dcdd  jz      loc_18002EE60
0x18002dce3  imul    r8, rdi, 23C34600h
0x18002dcea  xor     edx, edx
0x18002dcec  mov     rax, rsi
0x18002dcef  div     r8
0x18002dcf2  mov     rdi, rax
0x18002dcf5  mov     eax, [r14+2B8h]
0x18002dcfc  cmp     eax, edi
0x18002dcfe  jnz     loc_18002EE79
0x18002dd04  mov     rcx, rbx; _Mtx_t
0x18002dd07  call    cs:__imp__Mtx_unlock
0x18002dd0e  nop     dword ptr [rax+rax+00h]
0x18002dd13  nop
0x18002dd14  mov     [r15], edi
0x18002dd17  lea     rsi, [r13+10h]
0x18002dd1b  xor     r15d, r15d
0x18002dd1e  mov     r14d, 0FFFFFFh
0x18002dd24  cmp     [rsi+8], r15d
0x18002dd28  jz      short loc_18002DDA7
0x18002dd2a  mov     rcx, [rsi]
0x18002dd2d  cmp     byte ptr [rcx+7], 0FEh
0x18002dd31  jb      short loc_18002DDA7
0x18002dd33  mov     eax, [rcx+4]
0x18002dd36  and     eax, r14d
0x18002dd39  lea     eax, ds:0Fh[rax*2]
0x18002dd40  shr     eax, 2
0x18002dd43  cmp     eax, [rcx+8]
0x18002dd46  jz      short loc_18002DDA7
0x18002dd48  mov     edx, [rcx+rax*4]
0x18002dd4b  mov     r8d, edx
0x18002dd4e  cmp     byte ptr [rcx+r8*4+7], 0FDh
0x18002dd54  jz      short loc_18002DD91
0x18002dd56  mov     eax, [rcx+r8*4+4]
0x18002dd5b  and     eax, r14d
0x18002dd5e  cmp     eax, 1
0x18002dd61  jnz     short loc_18002DD91
0x18002dd63  mov     r9d, eax; char *
0x18002dd66  lea     r10, aA_1; "a"
0x18002dd6d  lea     r11, [rcx+0Ch]
0x18002dd71  lea     r11, [r11+r8*4]
0x18002dd75  test    r9, r9
0x18002dd78  jz      short loc_18002DD9C
0x18002dd7a  movzx   eax, word ptr [r10]
0x18002dd7e  cmp     [r11], ax
0x18002dd82  jnz     short loc_18002DD91
0x18002dd84  dec     r9
0x18002dd87  add     r11, 2
0x18002dd8b  add     r10, 2
0x18002dd8f  jmp     short loc_18002DD75
0x18002dd91  cmp     edx, [rcx+8]
0x18002dd94  jz      short loc_18002DDA7
0x18002dd96  mov     edx, [rcx+r8*4]
0x18002dd9a  jmp     short loc_18002DD4B
0x18002dd9c  mov     r15d, edx
0x18002dd9f  test    edx, edx
0x18002dda1  jnz     loc_18002E4DE
0x18002dda7  mov     al, 1
0x18002dda9  mov     rcx, [rbp+88h]; this
0x18002ddb0  test    al, al
0x18002ddb2  jnz     loc_18002EEA6
0x18002ddb8  mov     qword ptr [rsp+180h+var_110], rsi
0x18002ddbd  mov     [rsp+180h+var_110+8], r15d
0x18002ddc2  mov     eax, dword ptr [rsp+180h+var_130+0Ch]
0x18002ddc6  mov     [rsp+180h+var_110+0Ch], eax
0x18002ddca  test    byte ptr [r13+2BBh], 8
0x18002ddd2  jnz     short loc_18002DE41
0x18002ddd4  lea     rcx, [r13+150h]
0x18002dddb  cmp     qword ptr [rcx+10h], 0
0x18002dde0  jz      loc_18002E3EE
0x18002dde6  lea     rdx, [rbp+80h+lpMem]
0x18002ddea  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18002ddef  mov     rcx, [rbp+80h+lpMem]
0x18002ddf3  mov     rax, [rbp+80h+var_98]
0x18002ddf7  mov     [rbp+80h+lpMem], rcx
0x18002ddfb  mov     [rbp+80h+var_98], rax
0x18002ddff  lea     rcx, aIkey_1; "iKey"
0x18002de06  mov     [rsp+180h+dwBytes], rcx
0x18002de0b  mov     [rsp+180h+var_118], 4
0x18002de14  lea     rax, [rbp+80h+lpMem]
0x18002de18  mov     [rsp+180h+Src], rax
0x18002de1d  lea     rax, [rsp+180h+dwBytes]
0x18002de22  mov     qword ptr [rsp+180h+var_160], rax; unsigned int
0x18002de27  lea     r9, [rsp+180h+var_110]
0x18002de2c  mov     rdx, rsi
0x18002de2f  lea     rcx, [rsp+180h+var_130]
0x18002de34  call    ?AddValue@?$JsonImplementType@V?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@@SA?AVJsonIterator@@AEAVJsonBuilder@@_NAEBVJsonConstIterator@@AEBV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@3@Z; JsonImplementType<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>>::AddValue(JsonBuilder &,bool,JsonConstIterator const &,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &)
0x18002de39  or      byte ptr [r13+2BBh], 8
0x18002de41  xor     r13d, r13d
0x18002de44  mov     [rsp+180h+var_150], r13d
0x18002de49  lea     rbx, aExt; "ext"
0x18002de50  cmp     [rsi+8], r13d
0x18002de54  jz      short loc_18002DED3
0x18002de56  mov     edx, r15d
0x18002de59  mov     rcx, [rsi]
0x18002de5c  cmp     byte ptr [rcx+rdx*4+7], 0FEh
0x18002de61  jb      short loc_18002DED3
0x18002de63  mov     eax, [rcx+rdx*4+4]
0x18002de67  and     eax, r14d
0x18002de6a  lea     r8d, ds:0Fh[rax*2]
0x18002de72  shr     r8d, 2
0x18002de76  add     r8d, r15d
0x18002de79  mov     edi, [rcx+rdx*4+8]
0x18002de7d  cmp     r8d, edi
0x18002de80  jz      short loc_18002DED3
0x18002de82  mov     edx, [rcx+r8*4]
0x18002de86  mov     r8d, edx
0x18002de89  cmp     byte ptr [rcx+r8*4+7], 0FDh
0x18002de8f  jz      short loc_18002DEC8
0x18002de91  mov     eax, [rcx+r8*4+4]
0x18002de96  and     eax, r14d
0x18002de99  cmp     eax, 3
0x18002de9c  jnz     short loc_18002DEC8
0x18002de9e  mov     r9d, eax
0x18002dea1  mov     r10, rbx
0x18002dea4  lea     r11, [rcx+0Ch]
0x18002dea8  lea     r11, [r11+r8*4]
0x18002deac  test    r9, r9
0x18002deaf  jz      short loc_18002DECC
0x18002deb1  movzx   eax, word ptr [r10]
0x18002deb5  cmp     [r11], ax
0x18002deb9  jnz     short loc_18002DEC8
0x18002debb  dec     r9
0x18002debe  add     r11, 2
0x18002dec2  add     r10, 2
0x18002dec6  jmp     short loc_18002DEAC
0x18002dec8  cmp     edx, edi
0x18002deca  jmp     short loc_18002DE80
0x18002decc  mov     r13d, edx
0x18002decf  mov     [rsp+180h+var_150], edx
0x18002ded3  mov     edi, dword ptr [rsp+180h+var_130+0Ch]
0x18002ded7  test    r13d, r13d
0x18002deda  jz      loc_18002E5E8
0x18002dee0  xor     r10d, r10d
0x18002dee3  mov     [rsp+180h+var_140], r10d
0x18002dee8  lea     r14, aUtc_3; "utc"
0x18002deef  cmp     [rsi+8], r10d
0x18002def3  jz      loc_18002DF83
0x18002def9  mov     edx, r13d
0x18002defc  mov     rcx, [rsi]
0x18002deff  cmp     byte ptr [rcx+rdx*4+7], 0FEh
0x18002df04  jb      short loc_18002DF83
0x18002df06  mov     eax, [rcx+rdx*4+4]
0x18002df0a  mov     r15d, 0FFFFFFh
0x18002df10  and     eax, r15d
0x18002df13  lea     r8d, ds:0Fh[rax*2]
0x18002df1b  shr     r8d, 2
0x18002df1f  add     r8d, r13d
0x18002df22  mov     ebx, [rcx+rdx*4+8]
0x18002df26  cmp     r8d, ebx
0x18002df29  jz      short loc_18002DF83
0x18002df2b  mov     edx, [rcx+r8*4]
0x18002df2f  mov     r8d, edx
0x18002df32  cmp     byte ptr [rcx+r8*4+7], 0FDh
0x18002df38  jz      short loc_18002DF71
0x18002df3a  mov     eax, [rcx+r8*4+4]
0x18002df3f  and     eax, r15d
0x18002df42  cmp     eax, 3
0x18002df45  jnz     short loc_18002DF71
0x18002df47  mov     r9d, eax
0x18002df4a  mov     r10, r14
0x18002df4d  lea     r11, [rcx+0Ch]
0x18002df51  lea     r11, [r11+r8*4]
0x18002df55  test    r9, r9
0x18002df58  jz      short loc_18002DF7C
0x18002df5a  movzx   eax, word ptr [r10]
0x18002df5e  cmp     [r11], ax
0x18002df62  jnz     short loc_18002DF71
0x18002df64  dec     r9
0x18002df67  add     r11, 2
0x18002df6b  add     r10, 2
0x18002df6f  jmp     short loc_18002DF55
0x18002df71  cmp     edx, ebx
0x18002df73  jnz     short loc_18002DF2B
0x18002df75  mov     r10d, [rsp+180h+var_140]
0x18002df7a  jmp     short loc_18002DF83
0x18002df7c  mov     r10d, edx
0x18002df7f  mov     [rsp+180h+var_140], edx
0x18002df83  mov     ebx, dword ptr [rsp+180h+var_130+0Ch]
0x18002df87  test    r10d, r10d
0x18002df8a  jz      loc_18002E6D1
0x18002df90  mov     r12d, r13d
0x18002df93  mov     [rsp+180h+dwBytes], r12
0x18002df98  mov     r14d, r13d
0x18002df9b  mov     r13, rsi
0x18002df9e  xor     r12d, r12d
0x18002dfa1  mov     [rsp+180h+var_148], r12d
0x18002dfa6  lea     r15, aOs; "os"
0x18002dfad  cmp     [rsi+8], r12d
0x18002dfb1  jz      loc_18002E039
0x18002dfb7  mov     edx, [rsp+180h+var_150]
0x18002dfbb  mov     r14d, edx
0x18002dfbe  mov     rcx, [rsi]
0x18002dfc1  cmp     byte ptr [rcx+rdx*4+7], 0FEh
0x18002dfc6  jb      short loc_18002E039
0x18002dfc8  mov     eax, [rcx+rdx*4+4]
0x18002dfcc  and     eax, 0FFFFFFh
0x18002dfd1  lea     eax, ds:0Fh[rax*2]
0x18002dfd8  shr     eax, 2
0x18002dfdb  add     edx, eax
0x18002dfdd  cmp     edx, [rcx+r14*4+8]
0x18002dfe2  jz      short loc_18002E039
0x18002dfe4  mov     r8d, [rcx+rdx*4]
0x18002dfe8  mov     edx, r8d
0x18002dfeb  cmp     byte ptr [rcx+rdx*4+7], 0FDh
0x18002dff0  jz      short loc_18002E02A
0x18002dff2  mov     eax, [rcx+rdx*4+4]
0x18002dff6  and     eax, 0FFFFFFh
0x18002dffb  cmp     eax, 2
0x18002dffe  jnz     short loc_18002E02A
0x18002e000  mov     r9d, eax
0x18002e003  mov     r10, r15
0x18002e006  lea     r11, [rcx+0Ch]
0x18002e00a  lea     r11, [r11+rdx*4]
0x18002e00e  test    r9, r9
0x18002e011  jz      short loc_18002E031
0x18002e013  movzx   eax, word ptr [r10]
0x18002e017  cmp     [r11], ax
0x18002e01b  jnz     short loc_18002E02A
0x18002e01d  dec     r9
0x18002e020  add     r11, 2
0x18002e024  add     r10, 2
0x18002e028  jmp     short loc_18002E00E
0x18002e02a  cmp     r8d, [rcx+r14*4+8]
0x18002e02f  jmp     short loc_18002DFE2
0x18002e031  mov     r12d, r8d
0x18002e034  mov     [rsp+180h+var_148], r8d
0x18002e039  mov     qword ptr [rsp+180h+var_110], r13
0x18002e03e  mov     [rsp+180h+var_110+8], r12d
0x18002e043  mov     eax, dword ptr [rsp+180h+var_130+0Ch]
0x18002e047  mov     [rsp+180h+var_110+0Ch], eax
0x18002e04b  test    r12d, r12d
0x18002e04e  jz      loc_18002E7AF
0x18002e054  mov     r15, [rsp+180h+dwBytes]
0x18002e059  lea     rax, ds:0[r15*4]
0x18002e061  mov     [rsp+180h+var_138], rax
0x18002e066  mov     r14, rax
0x18002e069  xor     r13d, r13d
0x18002e06c  cmp     [rsi+8], r13d
0x18002e070  jz      loc_18002E0FE
0x18002e076  lea     r14, ds:0[r15*4]
0x18002e07e  mov     rcx, [rsi]
0x18002e081  cmp     byte ptr [rcx+r14+7], 0FEh
0x18002e087  jb      short loc_18002E0FE
0x18002e089  mov     eax, [rcx+r14+4]
0x18002e08e  and     eax, 0FFFFFFh
0x18002e093  lea     eax, ds:0Fh[rax*2]
0x18002e09a  shr     eax, 2
0x18002e09d  mov     edx, [rsp+180h+var_150]
0x18002e0a1  add     edx, eax
0x18002e0a3  cmp     edx, [rcx+r15*4+8]
0x18002e0a8  jz      short loc_18002E0FE
0x18002e0aa  mov     r8d, [rcx+rdx*4]
0x18002e0ae  mov     edx, r8d
0x18002e0b1  cmp     byte ptr [rcx+rdx*4+7], 0FDh
0x18002e0b6  jz      short loc_18002E0F4
0x18002e0b8  mov     eax, [rcx+rdx*4+4]
0x18002e0bc  and     eax, 0FFFFFFh
0x18002e0c1  cmp     eax, 7
0x18002e0c4  jnz     short loc_18002E0F4
0x18002e0c6  mov     r9d, eax
0x18002e0c9  lea     r10, aPrivacy; "privacy"
0x18002e0d0  lea     r11, [rcx+0Ch]
0x18002e0d4  lea     r11, [r11+rdx*4]
  ... truncated ...
```
