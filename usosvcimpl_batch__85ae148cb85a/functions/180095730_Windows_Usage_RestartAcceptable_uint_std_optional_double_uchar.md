# Windows::Usage::RestartAcceptable(uint,std::optional<double>,uchar)

- ea: `0x180095730`
- end: `0x1800968fd`
- name: `?RestartAcceptable@Usage@Windows@@UEBA?AUDeferReasons@SystemInterface@@IV?$optional@N@std@@E@Z`
- size: `4557`
- prototype: ``
- caller_count: `0`
- callee_count: `20`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000f2d0`
- `0x18000f780`
- `0x1800107cc`
- `0x180010890`
- `0x1800109f4`
- `0x1800112d0`
- `0x180011680`
- `0x18001c880`
- `0x18002e168`
- `0x180037eac`
- `0x1800420e0`
- `0x180063d70`
- `0x18006ddb0`
- `0x18006ea28`
- `0x180080d80`
- `0x1800952b0`
- `0x180095730`
- `0x1800dd930`
- `0x1800e4630`
- `0x1800e46b0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180096719`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800967a0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180096719`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800967a0`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800966a8`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180096748`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800966a8`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180096748`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1800966e7`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1800966e7`
- `OLEAUT32!__imp_SysFreeString` at `0x180096115`
- `OLEAUT32!__imp_SysFreeString` at `0x180096126`
- `OLEAUT32!__imp_SysFreeString` at `0x180096115`
- `OLEAUT32!__imp_SysFreeString` at `0x180096126`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1800966f5`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180096780`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1800966f5`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180096780`

## string_xrefs

- `0x1800967bd`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x1800967d6`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x1800967f5`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x18009680e`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x18009683c`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x180096855`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x18009686e`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x180096887`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x1800968a0`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x1800968b9`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x1800968d2`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x1800968eb`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x18009650e`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Usage.cpp`
- `0x180096823`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Usage.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
const wchar_t *__fastcall Windows::Usage::RestartAcceptable(
        __int64 a1,
        const wchar_t *a2,
        int a3,
        __int64 a4,
        unsigned __int8 a5)
{
  int v8; // r15d
  int v9; // edi
  __int64 v10; // r14
  _QWORD *v11; // rax
  volatile signed __int32 *v12; // rsi
  char v13; // cl
  int v14; // eax
  volatile signed __int32 *v15; // rbx
  _QWORD *v17; // rax
  bool v18; // r12
  volatile signed __int32 *v19; // rsi
  void (__fastcall *v20)(__int64, const wchar_t **, __int64); // rsi
  int *traits_2_unsigned_short; // rax
  const char *v22; // r9
  __int64 v23; // r11
  __int64 v24; // rax
  volatile signed __int32 *v25; // rsi
  _QWORD *v26; // rax
  bool v27; // r12
  volatile signed __int32 *v28; // rsi
  void (__fastcall *v29)(__int64, const wchar_t **, __int64); // rsi
  wchar_t *v30; // rax
  const char *v31; // r9
  __int64 v32; // r11
  __int64 v33; // rax
  volatile signed __int32 *v34; // rsi
  void (__fastcall *v35)(__int64, const wchar_t **, __int64); // rsi
  int *v36; // rax
  const char *v37; // r9
  __int64 v38; // r11
  __int64 v39; // rax
  volatile signed __int32 *v40; // rsi
  void (__fastcall *v41)(__int64, const wchar_t **, __int64); // rsi
  __int16 *v42; // rax
  const char *v43; // r9
  __int64 v44; // r11
  __int64 v45; // rax
  volatile signed __int32 *v46; // rsi
  void (__fastcall *v47)(__int64, const wchar_t **, __int64); // rsi
  __int64 *v48; // rax
  const char *v49; // r9
  __int64 v50; // r11
  __int64 v51; // rax
  volatile signed __int32 *v52; // rsi
  __int64 v53; // rax
  int v54; // eax
  __int64 v55; // rax
  __int64 v56; // rax
  void (__fastcall *v57)(__int64, int *, __int64); // rsi
  __int16 *v58; // rax
  const char *v59; // r9
  __int64 v60; // r11
  __int64 v61; // rax
  volatile signed __int32 *v62; // rsi
  void (__fastcall *v63)(__int64, int *, __int64); // rsi
  int *v64; // rax
  const char *v65; // r9
  __int64 v66; // r11
  __int64 v67; // rax
  volatile signed __int32 *v68; // rsi
  unsigned int UserDisplayState; // eax
  unsigned int v70; // r15d
  void (__fastcall *v71)(__int64, int *, _QWORD); // rsi
  __int16 *v72; // rax
  const char *v73; // r9
  __int64 v74; // r11
  __int64 v75; // rax
  volatile signed __int32 *v76; // rsi
  void (__fastcall *v77)(__int64, int *, __int64); // rsi
  int *v78; // rax
  const char *v79; // r9
  __int64 v80; // r11
  __int64 v81; // rax
  volatile signed __int32 *v82; // rsi
  void (__fastcall *v83)(__int64, int *, __int64); // rsi
  __int16 *v84; // rax
  const char *v85; // r9
  __int64 v86; // r11
  __int64 v87; // rax
  volatile signed __int32 *v88; // rsi
  void (__fastcall *v89)(__int64, int *, __int64); // rsi
  int *v90; // rax
  const char *v91; // r9
  __int64 v92; // r11
  __int64 v93; // rax
  volatile signed __int32 *v94; // rsi
  int v95; // eax
  const wchar_t *v96; // rdi
  volatile signed __int32 *v97; // rbx
  void (__fastcall *v98)(__int64, int *, __int64); // rbx
  int *v99; // rax
  const char *v100; // r9
  __int64 v101; // r11
  __int64 v102; // rax
  volatile signed __int32 *v103; // rbx
  wchar_t *v104; // rbx
  LPWSTR v105; // rax
  __int64 v106; // rdx
  wchar_t *v107; // rbx
  const WCHAR *v108; // rcx
  LPWSTR FileNameW; // rax
  int v110[2]; // [rsp+20h] [rbp-E0h] BYREF
  volatile signed __int32 *v111; // [rsp+28h] [rbp-D8h]
  char v112[4]; // [rsp+30h] [rbp-D0h] BYREF
  int v113; // [rsp+34h] [rbp-CCh]
  __int128 v114; // [rsp+38h] [rbp-C8h] BYREF
  const wchar_t *v115; // [rsp+48h] [rbp-B8h]
  BSTR bstrString[2]; // [rsp+50h] [rbp-B0h] BYREF
  const wchar_t *v117; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v118; // [rsp+68h] [rbp-98h]
  BSTR v119; // [rsp+70h] [rbp-90h] BYREF
  LPCWSTR pszPath[2]; // [rsp+78h] [rbp-88h] BYREF
  __m128i si128; // [rsp+88h] [rbp-78h]
  __int64 v122; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v123; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v124; // [rsp+B8h] [rbp-48h]
  __int64 v125; // [rsp+C0h] [rbp-40h]
  __int128 v126; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v127; // [rsp+D8h] [rbp-28h]
  __int64 v128; // [rsp+E0h] [rbp-20h]
  __int128 v129; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v130; // [rsp+F8h] [rbp-8h]
  __int64 v131; // [rsp+100h] [rbp+0h]
  __int128 v132; // [rsp+108h] [rbp+8h] BYREF
  __int64 v133; // [rsp+118h] [rbp+18h]
  __int64 v134; // [rsp+120h] [rbp+20h]
  WCHAR ExeName[264]; // [rsp+130h] [rbp+30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+388h] [rbp+288h]

  v115 = a2;
  v117 = a2;
  v8 = 0;
  v113 = 0;
  v122 = 0;
  v123 = 0;
  v124 = 0;
  v125 = 7;
  LOWORD(v123) = 0;
  v126 = 0;
  v127 = 0;
  v128 = 7;
  LOWORD(v126) = 0;
  v129 = 0;
  v130 = 0;
  v131 = 7;
  LOWORD(v129) = 0;
  v132 = 0;
  v133 = 0;
  v134 = 7;
  LOWORD(v132) = 0;
  v9 = 0;
  v114 = 0;
  SystemInterface::Service::GetSystem((__int64 *)&v114);
  v10 = v114;
  v11 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)v114 + 48LL))(v114, v110);
  (*(void (__fastcall **)(_QWORD, BSTR *))(*(_QWORD *)*v11 + 80LL))(*v11, bstrString);
  v12 = v111;
  if ( v111 )
  {
    if ( _InterlockedExchangeAdd(v111 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
      if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
    }
  }
  v13 = BYTE4(bstrString[0]);
  if ( BYTE4(bstrString[0]) )
  {
    v14 = (int)bstrString[0];
    if ( ((__int64)bstrString[0] & 0x400) != 0 )
    {
      std::wstring::operator=(&v132, L"TestOverride_gameModeReason");
      v14 = (int)bstrString[0];
      v13 = BYTE4(bstrString[0]);
    }
    if ( !v13 )
      goto LABEL_168;
    if ( (v14 & 2) != 0 )
    {
      std::wstring::operator=(&v126, L"TestOverride_displayReason");
      v14 = (int)bstrString[0];
      v13 = BYTE4(bstrString[0]);
    }
    if ( !v13 )
      goto LABEL_168;
    if ( (v14 & 0x10) != 0 )
    {
      std::wstring::operator=(&v123, L"TestOverride_systemReason");
      v14 = (int)bstrString[0];
      v13 = BYTE4(bstrString[0]);
    }
    if ( !v13 )
LABEL_168:
      std::_Throw_bad_optional_access();
    LODWORD(v122) = v14 & ~a3;
    SystemInterface::DeferReasons::DeferReasons(a2, &v122);
    v15 = (volatile signed __int32 *)*((_QWORD *)&v114 + 1);
    if ( *((_QWORD *)&v114 + 1)
      && _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v114 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
      if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
    }
    std::wstring::~wstring(&v132);
    std::wstring::~wstring(&v129);
    std::wstring::~wstring(&v126);
    std::wstring::~wstring(&v123);
    return a2;
  }
  else
  {
    v18 = 0;
    if ( (a3 & 4) == 0 )
    {
      v17 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v10 + 56LL))(v10, v110);
      v8 = 2;
      v113 = 2;
      if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)*v17 + 16LL))(*v17) < a5 )
        v18 = 1;
    }
    if ( (v8 & 2) != 0 )
    {
      v8 &= ~2u;
      v19 = v111;
      if ( v111 )
      {
        if ( _InterlockedExchangeAdd(v111 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v19)(v19);
          if ( _InterlockedExchangeAdd(v19 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v19 + 8LL))(v19);
        }
      }
    }
    if ( v18 )
    {
      v9 = 4;
      v20 = *(void (__fastcall **)(__int64, const wchar_t **, __int64))(**(_QWORD **)(*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v10 + 104LL))(
                                                                                       v10,
                                                                                       v110)
                                                                      + 256LL);
      traits_2_unsigned_short = (int *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                                         L"Defer reason: low battery",
                                         &dword_18012496C,
                                         0);
      if ( traits_2_unsigned_short == &dword_18012496C
        || (v24 = ((char *)traits_2_unsigned_short - (char *)L"Defer reason: low battery") >> 1, v24 == -1) )
      {
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0xC9,
          (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
          v22);
      }
      v117 = L"Defer reason: low battery";
      v118 = v24;
      v20(v23, &v117, 1);
      v25 = v111;
      if ( v111 )
      {
        if ( _InterlockedExchangeAdd(v111 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v25)(v25);
          if ( _InterlockedExchangeAdd(v25 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v25 + 8LL))(v25);
        }
      }
    }
    v27 = 0;
    if ( (a3 & 0x40) == 0 )
    {
      v26 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v10 + 56LL))(v10, v110);
      v8 |= 4u;
      v113 = v8;
      if ( !(*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)*v26 + 40LL))(*v26) )
        v27 = 1;
    }
    if ( (v8 & 4) != 0 )
    {
      v28 = v111;
      if ( v111 )
      {
        if ( _InterlockedExchangeAdd(v111 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v28)(v28);
          if ( _InterlockedExchangeAdd(v28 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v28 + 8LL))(v28);
        }
      }
    }
    if ( v27 )
    {
      v9 |= 0x40u;
      v29 = *(void (__fastcall **)(__int64, const wchar_t **, __int64))(**(_QWORD **)(*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v10 + 104LL))(
                                                                                       v10,
                                                                                       v110)
                                                                      + 256LL);
      v30 = (wchar_t *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                         L"Defer reason: not on AC",
                         L"TestOverride_displayReason",
                         0);
      if ( v30 == L"TestOverride_displayReason" || (v33 = v30 - L"Defer reason: not on AC", v33 == -1) )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0xC9,
          (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
          v31);
      v117 = L"Defer reason: not on AC";
      v118 = v33;
      v29(v32, &v117, 1);
      v34 = v111;
      if ( v111 )
      {
        if ( _InterlockedExchangeAdd(v111 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v34)(v34);
          if ( _InterlockedExchangeAdd(v34 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v34 + 8LL))(v34);
        }
      }
    }
    if ( (a3 & 1) == 0 && (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)a1 + 24LL))(a1) )
    {
      v9 |= 1u;
      v35 = *(void (__fastcall **)(__int64, const wchar_t **, __int64))(**(_QWORD **)(*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v10 + 104LL))(
                                                                                       v10,
                                                                                       v110)
                                                                      + 256LL);
      v36 = (int *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                     L"Defer reason: user active",
                     &dword_180124AD4,
                     0);
      if ( v36 == &dword_180124AD4 || (v39 = ((char *)v36 - (char *)L"Defer reason: user active") >> 1, v39 == -1) )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0xC9,
          (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
          v37);
      v117 = L"Defer reason: user active";
      v118 = v39;
      v35(v38, &v117, 1);
      v40 = v111;
      if ( v111 )
      {
        if ( _InterlockedExchangeAdd(v111 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v40)(v40);
          if ( _InterlockedExchangeAdd(v40 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v40 + 8LL))(v40);
        }
      }
    }
    if ( (a3 & 0x12) != 0x12 )
    {
      if ( (a3 & 2) == 0 && (*(unsigned __int8 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)a1 + 40LL))(a1, 0) )
      {
        v9 |= 2u;
        v41 = *(void (__fastcall **)(__int64, const wchar_t **, __int64))(**(_QWORD **)(*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v10 + 104LL))(
                                                                                         v10,
                                                                                         v110)
                                                                        + 256LL);
        v42 = (__int16 *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                           L"Defer reason: display needed",
                           word_180124B12,
                           0);
        if ( v42 == word_180124B12 || (v45 = ((char *)v42 - (char *)L"Defer reason: display needed") >> 1, v45 == -1) )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0xC9,
            (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
            v43);
        v117 = L"Defer reason: display needed";
        v118 = v45;
        v41(v44, &v117, 1);
        v46 = v111;
        if ( v111 )
        {
          if ( !_InterlockedDecrement(v111 + 2) )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v46)(v46);
            if ( !_InterlockedDecrement(v46 + 3) )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v46 + 8LL))(v46);
          }
        }
      }
      if ( (a3 & 0x10) == 0 && (*(unsigned __int8 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)a1 + 48LL))(a1, 0) )
      {
        v9 |= 0x10u;
        v47 = *(void (__fastcall **)(__int64, const wchar_t **, __int64))(**(_QWORD **)(*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v10 + 104LL))(
                                                                                         v10,
                                                                                         v110)
                                                                        + 256LL);
        v48 = (__int64 *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                           L"Defer reason: system needed",
                           &qword_180124A48,
                           0);
        if ( v48 == &qword_180124A48 || (v51 = ((char *)v48 - (char *)L"Defer reason: system needed") >> 1, v51 == -1) )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0xC9,
            (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
            v49);
        v117 = L"Defer reason: system needed";
        v118 = v51;
        v47(v50, &v117, 1);
        v52 = v111;
        if ( v111 )
        {
          if ( !_InterlockedDecrement(v111 + 2) )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v52)(v52);
            if ( !_InterlockedDecrement(v52 + 3) )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v52 + 8LL))(v52);
          }
        }
      }
      if ( (v9 & 0x12) != 0 )
      {
        v117 = 0;
        Windows::DockedHelpers::GetDockedUsage(&v117);
        v119 = 0;
        bstrString[0] = 0;
        v53 = *(_QWORD *)v117;
        bstrString[0] = 0;
        v119 = 0;
        v54 = (*(__int64 (__fastcall **)(const wchar_t *, BSTR *, BSTR *))(v53 + 56))(v117, &v119, bstrString);
        if ( v54 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x1E8,
            (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Usage.cpp",
            (const char *)(unsigned int)v54,
            v110[0]);
        v55 = Windows::Strings::to_wstring(pszPath, &v119);
        std::wstring::operator=(&v123, v55);
        std::wstring::~wstring(pszPath);
        v56 = Windows::Strings::to_wstring(pszPath, bstrString);
        std::wstring::operator=(&v126, v56);
        std::wstring::~wstring(pszPath);
        if ( (v9 & 0x10) != 0 && !v124 )
        {
          v57 = *(void (__fastcall **)(__int64, int *, __int64))(**(_QWORD **)(*(__int64 (__fastcall **)(__int64, LPCWSTR *))(*(_QWORD *)v10 + 104LL))(
                                                                                v10,
                                                                                pszPath)
                                                               + 256LL);
          v58 = (__int16 *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                             L"Defer reason: ignoring system needed",
                             word_180124A9A,
                             0);
          if ( v58 == word_180124A9A
            || (v61 = ((char *)v58 - (char *)L"Defer reason: ignoring system needed") >> 1, v61 == -1) )
          {
            wil::details::in1diag3::_FailFast_Unexpected(
              retaddr,
              (void *)0xC9,
              (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
              v59);
          }
          *(_QWORD *)v110 = L"Defer reason: ignoring system needed";
          v111 = (volatile signed __int32 *)v61;
          v57(v60, v110, 1);
          v62 = (volatile signed __int32 *)pszPath[1];
          if ( pszPath[1] )
          {
            if ( !_InterlockedDecrement((volatile signed __int32 *)pszPath[1] + 2) )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v62)(v62);
              if ( !_InterlockedDecrement(v62 + 3) )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v62 + 8LL))(v62);
            }
          }
          v9 &= ~0x10u;
        }
        if ( (v9 & 2) != 0 && !v127 )
        {
          v63 = *(void (__fastcall **)(__int64, int *, __int64))(**(_QWORD **)(*(__int64 (__fastcall **)(__int64, LPCWSTR *))(*(_QWORD *)v10 + 104LL))(
                                                                                v10,
                                                                                pszPath)
                                                               + 256LL);
          v64 = (int *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                         L"Defer reason: ignoring display needed",
                         &dword_180124BDC,
                         0);
          if ( v64 == &dword_180124BDC
            || (v67 = ((char *)v64 - (char *)L"Defer reason: ignoring display needed") >> 1, v67 == -1) )
          {
            wil::details::in1diag3::_FailFast_Unexpected(
              retaddr,
              (void *)0xC9,
              (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
              v65);
          }
          *(_QWORD *)v110 = L"Defer reason: ignoring display needed";
          v111 = (volatile signed __int32 *)v67;
          v63(v66, v110, 1);
          v68 = (volatile signed __int32 *)pszPath[1];
          if ( pszPath[1] )
          {
            if ( !_InterlockedDecrement((volatile signed __int32 *)pszPath[1] + 2) )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v68)(v68);
              if ( !_InterlockedDecrement(v68 + 3) )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v68 + 8LL))(v68);
            }
          }
          v9 &= ~2u;
        }
        if ( bstrString[0] )
          SysFreeString(bstrString[0]);
        if ( v119 )
          SysFreeString(v119);
        if ( v117 )
          (*(void (__fastcall **)(const wchar_t *))(*(_QWORD *)v117 + 16LL))(v117);
      }
    }
    if ( (a3 & 0x80) == 0 || (a3 & 0x100) == 0 )
    {
      UserDisplayState = Windows::Usage::GetUserDisplayState();
      v70 = UserDisplayState;
      if ( (a3 & 0x80) == 0 && UserDisplayState == 1 )
      {
        v9 |= 0x80u;
        v71 = *(void (__fastcall **)(__int64, int *, _QWORD))(**(_QWORD **)(*(__int64 (__fastcall **)(__int64, LPCWSTR *))(*(_QWORD *)v10 + 104LL))(
                                                                             v10,
                                                                             pszPath)
                                                            + 256LL);
        v72 = (__int16 *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                           L"Defer reason: presenting",
                           word_180124C12,
                           0);
        if ( v72 == word_180124C12 || (v75 = ((char *)v72 - (char *)L"Defer reason: presenting") >> 1, v75 == -1) )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0xC9,
            (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
            v73);
        *(_QWORD *)v110 = L"Defer reason: presenting";
        v111 = (volatile signed __int32 *)v75;
        v71(v74, v110, v70);
        v76 = (volatile signed __int32 *)pszPath[1];
        if ( pszPath[1] )
        {
          if ( !_InterlockedDecrement((volatile signed __int32 *)pszPath[1] + 2) )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v76)(v76);
            if ( !_InterlockedDecrement(v76 + 3) )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v76 + 8LL))(v76);
          }
        }
      }
      if ( (a3 & 0x100) == 0 && v70 - 2 <= 1 )
      {
        v9 |= 0x100u;
        v77 = *(void (__fastcall **)(__int64, int *, __int64))(**(_QWORD **)(*(__int64 (__fastcall **)(__int64, LPCWSTR *))(*(_QWORD *)v10 + 104LL))(
                                                                              v10,
                                                                              pszPath)
                                                             + 256LL);
        v78 = (int *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                       L"Defer reason: full-screen",
                       &dword_180124B4C,
                       0);
        if ( v78 == &dword_180124B4C || (v81 = ((char *)v78 - (char *)L"Defer reason: full-screen") >> 1, v81 == -1) )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0xC9,
            (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
            v79);
        *(_QWORD *)v110 = L"Defer reason: full-screen";
        v111 = (volatile signed __int32 *)v81;
        v77(v80, v110, 1);
        v82 = (volatile signed __int32 *)pszPath[1];
        if ( pszPath[1] )
        {
          if ( !_InterlockedDecrement((volatile signed __int32 *)pszPath[1] + 2) )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v82)(v82);
            if ( !_InterlockedDecrement(v82 + 3) )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v82 + 8LL))(v82);
          }
        }
      }
    }
    if ( (a3 & 8) == 0 && (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)a1 + 64LL))(a1) )
    {
      v9 |= 8u;
      v83 = *(void (__fastcall **)(__int64, int *, __int64))(**(_QWORD **)(*(__int64 (__fastcall **)(__int64, LPCWSTR *))(*(_QWORD *)v10 + 104LL))(
                                                                            v10,
                                                                            pszPath)
                                                           + 256LL);
      v84 = (__int16 *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                         L"Defer reason: phone call",
                         word_180124B82,
                         0);
      if ( v84 == word_180124B82 || (v87 = ((char *)v84 - (char *)L"Defer reason: phone call") >> 1, v87 == -1) )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0xC9,
          (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
          v85);
      *(_QWORD *)v110 = L"Defer reason: phone call";
      v111 = (volatile signed __int32 *)v87;
      v83(v86, v110, 1);
      v88 = (volatile signed __int32 *)pszPath[1];
      if ( pszPath[1] )
      {
        if ( !_InterlockedDecrement((volatile signed __int32 *)pszPath[1] + 2) )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v88)(v88);
          if ( !_InterlockedDecrement(v88 + 3) )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v88 + 8LL))(v88);
        }
      }
    }
    if ( (a3 & 0x200) == 0 && (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)a1 + 56LL))(a1) )
    {
      v9 |= 0x200u;
      v89 = *(void (__fastcall **)(__int64, int *, __int64))(**(_QWORD **)(*(__int64 (__fastcall **)(__int64, LPCWSTR *))(*(_QWORD *)v10 + 104LL))(
                                                                            v10,
                                                                            pszPath)
                                                           + 256LL);
      v90 = (int *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                     L"Defer reason: block requested",
                     &dword_180124CA4,
                     0);
      if ( v90 == &dword_180124CA4 || (v93 = ((char *)v90 - L"Defer reason: block requested") >> 1, v93 == -1) )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0xC9,
          (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
          v91);
      *(_QWORD *)v110 = L"Defer reason: block requested";
      v111 = (volatile signed __int32 *)v93;
      v89(v92, v110, 1);
      v94 = (volatile signed __int32 *)pszPath[1];
      if ( pszPath[1] )
      {
        if ( !_InterlockedDecrement((volatile signed __int32 *)pszPath[1] + 2) )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v94)(v94);
          if ( !_InterlockedDecrement(v94 + 3) )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v94 + 8LL))(v94);
        }
      }
    }
    if ( (a3 & 0x400) == 0 )
    {
      LODWORD(v119) = 0;
      v112[0] = 0;
      v95 = wil::wnf_query_nothrow<unsigned long>(WNF_RM_GAME_MODE_ACTIVE, v112, &v119);
      if ( v95 >= 0 )
      {
        if ( (_DWORD)v119 )
        {
          v9 |= 0x400u;
          v98 = *(void (__fastcall **)(__int64, int *, __int64))(**(_QWORD **)(*(__int64 (__fastcall **)(__int64, LPCWSTR *))(*(_QWORD *)v10 + 104LL))(
                                                                                v10,
                                                                                pszPath)
                                                               + 256LL);
          v99 = (int *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                         L"Defer reason: game active",
                         &dword_180124CDC,
                         0);
          if ( v99 == &dword_180124CDC || (v102 = ((char *)v99 - (char *)L"Defer reason: game active") >> 1, v102 == -1) )
            wil::details::in1diag3::_FailFast_Unexpected(
              retaddr,
              (void *)0xC9,
              (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
              v100);
          *(_QWORD *)v110 = L"Defer reason: game active";
          v111 = (volatile signed __int32 *)v102;
          v98(v101, v110, 1);
          v103 = (volatile signed __int32 *)pszPath[1];
          if ( pszPath[1] )
          {
            if ( !_InterlockedDecrement((volatile signed __int32 *)pszPath[1] + 2) )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v103)(v103);
              if ( !_InterlockedDecrement(v103 + 3) )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v103 + 8LL))(v103);
            }
          }
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_LintFixes_57550863>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_LintFixes_57550863>::GetImpl'::`2'::impl) )
          {
            *(_OWORD *)pszPath = 0;
            si128 = _mm_load_si128((const __m128i *)&_xmm);
            LOWORD(pszPath[0]) = 0;
            v107 = (wchar_t *)OpenProcess(0x400u, 0, (DWORD)v119);
            v117 = v107;
            if ( (unsigned __int64)v107 - 1 <= 0xFFFFFFFFFFFFFFFDuLL
              && (int)wil::QueryFullProcessImageNameW<std::wstring,256>(v107, v106, pszPath) >= 0 )
            {
              v108 = (const WCHAR *)pszPath;
              if ( si128.m128i_i64[1] > 7uLL )
                v108 = pszPath[0];
              FileNameW = PathFindFileNameW(v108);
              std::wstring::operator=(&v132, FileNameW);
            }
            if ( (unsigned __int64)v107 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
              CloseHandle(v107);
            std::wstring::~wstring(pszPath);
          }
          else
          {
            v104 = (wchar_t *)OpenProcess(0x400u, 0, (DWORD)v119);
            v117 = v104;
            memset(ExeName, 0, 0x208u);
            LODWORD(bstrString[0]) = 260;
            if ( (unsigned __int64)v104 - 1 <= 0xFFFFFFFFFFFFFFFDuLL
              && QueryFullProcessImageNameW(v104, 0, ExeName, (PDWORD)bstrString) )
            {
              v105 = PathFindFileNameW(ExeName);
              std::wstring::operator=(&v132, v105);
            }
            if ( (unsigned __int64)v104 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
              CloseHandle(v104);
          }
        }
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x220,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Usage.cpp",
          (const char *)(unsigned int)v95,
          v110[0]);
      }
    }
    LODWORD(v122) = v9;
    v96 = v115;
    SystemInterface::DeferReasons::DeferReasons(v115, &v122);
    v97 = (volatile signed __int32 *)*((_QWORD *)&v114 + 1);
    if ( *((_QWORD *)&v114 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v114 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v97)(v97);
        if ( _InterlockedExchangeAdd(v97 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v97 + 8LL))(v97);
      }
    }
    std::wstring::~wstring(&v132);
    std::wstring::~wstring(&v129);
    std::wstring::~wstring(&v126);
    std::wstring::~wstring(&v123);
    return v96;
  }
}

```

## disassembly

```asm
0x180095730  mov     [rsp-8+arg_18], rbx
0x180095735  push    rbp
0x180095736  push    rsi
0x180095737  push    rdi
0x180095738  push    r12
0x18009573a  push    r13
0x18009573c  push    r14
0x18009573e  push    r15
0x180095740  lea     rbp, [rsp-250h]
0x180095748  sub     rsp, 350h
0x18009574f  mov     rax, cs:__security_cookie
0x180095756  xor     rax, rsp
0x180095759  mov     [rbp+280h+var_40], rax
0x180095760  mov     ebx, r8d
0x180095763  mov     r12, rdx
0x180095766  mov     [rsp+380h+var_338], rdx
0x18009576b  mov     r13, rcx
0x18009576e  mov     [rsp+380h+var_320], rdx
0x180095773  xor     ecx, ecx
0x180095775  mov     r15d, ecx
0x180095778  mov     [rsp+380h+var_34C], ecx
0x18009577c  mov     [rbp+280h+var_2E0], rcx
0x180095780  xorps   xmm0, xmm0
0x180095783  movups  [rbp+280h+var_2D8], xmm0
0x180095787  mov     [rbp+280h+var_2C8], rcx
0x18009578b  lea     eax, [rcx+7]
0x18009578e  mov     [rbp+280h+var_2C0], rax
0x180095792  mov     word ptr [rbp+280h+var_2D8], cx
0x180095796  movups  [rbp+280h+var_2B8], xmm0
0x18009579a  mov     [rbp+280h+var_2A8], rcx
0x18009579e  mov     [rbp+280h+var_2A0], rax
0x1800957a2  mov     word ptr [rbp+280h+var_2B8], cx
0x1800957a6  movups  [rbp+280h+var_298], xmm0
0x1800957aa  mov     [rbp+280h+var_288], rcx
0x1800957ae  mov     [rbp+280h+var_280], rax
0x1800957b2  mov     word ptr [rbp+280h+var_298], cx
0x1800957b6  movups  [rbp+280h+var_278], xmm0
0x1800957ba  mov     [rbp+280h+var_268], rcx
0x1800957be  mov     [rbp+280h+var_260], rax
0x1800957c2  mov     word ptr [rbp+280h+var_278], cx
0x1800957c6  mov     edi, ecx
0x1800957c8  movups  [rsp+380h+var_348], xmm0
0x1800957cd  lea     rcx, [rsp+380h+var_348]
0x1800957d2  call    ?GetSystem@Service@SystemInterface@@YA?AV?$shared_ptr@VSystem@Service@SystemInterface@@@std@@XZ; SystemInterface::Service::GetSystem(void)
0x1800957d7  nop
0x1800957d8  mov     r14, qword ptr [rsp+380h+var_348]
0x1800957dd  mov     rax, [r14]
0x1800957e0  lea     rdx, [rsp+380h+var_360]
0x1800957e5  mov     rcx, r14
0x1800957e8  mov     rax, [rax+30h]
0x1800957ec  call    _guard_dispatch_icall
0x1800957f1  nop
0x1800957f2  mov     rcx, [rax]
0x1800957f5  mov     rax, [rcx]
0x1800957f8  lea     rdx, [rsp+380h+bstrString]
0x1800957fd  mov     rax, [rax+50h]
0x180095801  call    _guard_dispatch_icall
0x180095806  nop
0x180095807  mov     rsi, [rsp+380h+var_358]
0x18009580c  test    rsi, rsi
0x18009580f  jz      short loc_180095848
0x180095811  or      eax, 0FFFFFFFFh
0x180095814  lock xadd [rsi+8], eax
0x180095819  cmp     eax, 1
0x18009581c  jnz     short loc_180095848
0x18009581e  mov     rax, [rsi]
0x180095821  mov     rcx, rsi
0x180095824  mov     rax, [rax]
0x180095827  call    _guard_dispatch_icall
0x18009582c  or      eax, 0FFFFFFFFh
0x18009582f  lock xadd [rsi+0Ch], eax
0x180095834  cmp     eax, 1
0x180095837  jnz     short loc_180095848
0x180095839  mov     rax, [rsi]
0x18009583c  mov     rcx, rsi
0x18009583f  mov     rax, [rax+8]
0x180095843  call    _guard_dispatch_icall
0x180095848  mov     cl, byte ptr [rsp+380h+bstrString+4]
0x18009584c  test    cl, cl
0x18009584e  jz      loc_18009594C
0x180095854  mov     rax, [rsp+380h+bstrString]
0x180095859  bt      eax, 0Ah
0x18009585d  jnb     short loc_180095878
0x18009585f  lea     rdx, aTestoverrideGa; "TestOverride_gameModeReason"
0x180095866  lea     rcx, [rbp+280h+var_278]; void *
0x18009586a  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@QEB_W@Z; std::wstring::operator=(wchar_t const * const)
0x18009586f  mov     rax, [rsp+380h+bstrString]
0x180095874  mov     cl, byte ptr [rsp+380h+bstrString+4]
0x180095878  test    cl, cl
0x18009587a  jz      loc_1800967E8
0x180095880  test    al, 2
0x180095882  jz      short loc_18009589D
0x180095884  lea     rdx, aTestoverrideDi; "TestOverride_displayReason"
0x18009588b  lea     rcx, [rbp+280h+var_2B8]; void *
0x18009588f  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@QEB_W@Z; std::wstring::operator=(wchar_t const * const)
0x180095894  mov     rax, [rsp+380h+bstrString]
0x180095899  mov     cl, byte ptr [rsp+380h+bstrString+4]
0x18009589d  test    cl, cl
0x18009589f  jz      loc_1800967E8
0x1800958a5  test    al, 10h
0x1800958a7  jz      short loc_1800958C2
0x1800958a9  lea     rdx, aTestoverrideSy; "TestOverride_systemReason"
0x1800958b0  lea     rcx, [rbp+280h+var_2D8]; void *
0x1800958b4  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@QEB_W@Z; std::wstring::operator=(wchar_t const * const)
0x1800958b9  mov     rax, [rsp+380h+bstrString]
0x1800958be  mov     cl, byte ptr [rsp+380h+bstrString+4]
0x1800958c2  test    cl, cl
0x1800958c4  jz      loc_1800967E8
0x1800958ca  not     ebx
0x1800958cc  and     ebx, eax
0x1800958ce  mov     dword ptr [rbp+280h+var_2E0], ebx
0x1800958d1  lea     rdx, [rbp+280h+var_2E0]
0x1800958d5  mov     rcx, r12
0x1800958d8  call    ??0DeferReasons@SystemInterface@@QEAA@$$QEAU01@@Z; SystemInterface::DeferReasons::DeferReasons(SystemInterface::DeferReasons &&)
0x1800958dd  nop
0x1800958de  mov     rbx, qword ptr [rsp+380h+var_348+8]
0x1800958e3  test    rbx, rbx
0x1800958e6  jz      short loc_180095920
0x1800958e8  or      eax, 0FFFFFFFFh
0x1800958eb  lock xadd [rbx+8], eax
0x1800958f0  cmp     eax, 1
0x1800958f3  jnz     short loc_180095920
0x1800958f5  mov     rax, [rbx]
0x1800958f8  mov     rcx, rbx
0x1800958fb  mov     rax, [rax]
0x1800958fe  call    _guard_dispatch_icall
0x180095903  or      eax, 0FFFFFFFFh
0x180095906  lock xadd [rbx+0Ch], eax
0x18009590b  cmp     eax, 1
0x18009590e  jnz     short loc_180095920
0x180095910  mov     rax, [rbx]
0x180095913  mov     rcx, rbx
0x180095916  mov     rax, [rax+8]
0x18009591a  call    _guard_dispatch_icall
0x18009591f  nop
0x180095920  lea     rcx, [rbp+280h+var_278]; void *
0x180095924  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180095929  lea     rcx, [rbp+280h+var_298]; void *
0x18009592d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180095932  lea     rcx, [rbp+280h+var_2B8]; void *
0x180095936  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18009593b  lea     rcx, [rbp+280h+var_2D8]; void *
0x18009593f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180095944  mov     rax, r12
0x180095947  jmp     loc_18009659D
0x18009594c  test    bl, 4
0x18009594f  jnz     short loc_18009598D
0x180095951  mov     rax, [r14]
0x180095954  lea     rdx, [rsp+380h+var_360]
0x180095959  mov     rcx, r14
0x18009595c  mov     rax, [rax+38h]
0x180095960  call    _guard_dispatch_icall
0x180095965  nop
0x180095966  mov     r15d, 2
0x18009596c  mov     [rsp+380h+var_34C], r15d
0x180095971  mov     rcx, [rax]
0x180095974  mov     rax, [rcx]
0x180095977  mov     rax, [rax+10h]
0x18009597b  call    _guard_dispatch_icall
0x180095980  cmp     al, [rbp+280h+arg_20]
0x180095986  jnb     short loc_18009598D
0x180095988  mov     r12b, 1
0x18009598b  jmp     short loc_180095990
0x18009598d  xor     r12b, r12b
0x180095990  test    r15b, 2
0x180095994  jz      short loc_1800959DB
0x180095996  and     r15d, 0FFFFFFFDh
0x18009599a  mov     rsi, [rsp+380h+var_358]
0x18009599f  test    rsi, rsi
0x1800959a2  jz      short loc_1800959DB
0x1800959a4  or      eax, 0FFFFFFFFh
0x1800959a7  lock xadd [rsi+8], eax
0x1800959ac  cmp     eax, 1
0x1800959af  jnz     short loc_1800959DB
0x1800959b1  mov     rax, [rsi]
0x1800959b4  mov     rcx, rsi
0x1800959b7  mov     rax, [rax]
0x1800959ba  call    _guard_dispatch_icall
0x1800959bf  or      eax, 0FFFFFFFFh
0x1800959c2  lock xadd [rsi+0Ch], eax
0x1800959c7  cmp     eax, 1
0x1800959ca  jnz     short loc_1800959DB
0x1800959cc  mov     rax, [rsi]
0x1800959cf  mov     rcx, rsi
0x1800959d2  mov     rax, [rax+8]
0x1800959d6  call    _guard_dispatch_icall
0x1800959db  test    r12b, r12b
0x1800959de  jz      loc_180095AA4
0x1800959e4  mov     edi, 4
0x1800959e9  mov     rax, [r14]
0x1800959ec  lea     rdx, [rsp+380h+var_360]
0x1800959f1  mov     rcx, r14
0x1800959f4  mov     rax, [rax+68h]
0x1800959f8  call    _guard_dispatch_icall
0x1800959fd  nop
0x1800959fe  mov     r11, [rax]
0x180095a01  mov     rax, [r11]
0x180095a04  mov     rsi, [rax+100h]
0x180095a0b  xor     r8d, r8d
0x180095a0e  lea     r12, dword_18012496C
0x180095a15  mov     rdx, r12
0x180095a18  lea     rcx, aDeferReasonLow; "Defer reason: low battery"
0x180095a1f  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x180095a24  cmp     rax, r12
0x180095a27  jz      loc_1800967EE
0x180095a2d  lea     rcx, aDeferReasonLow; "Defer reason: low battery"
0x180095a34  sub     rax, rcx
0x180095a37  sar     rax, 1
0x180095a3a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180095a3e  jz      loc_1800967EE
0x180095a44  mov     [rsp+380h+var_320], rcx
0x180095a49  mov     [rsp+380h+var_318], rax
0x180095a4e  lea     r8d, [rdi-3]
0x180095a52  lea     rdx, [rsp+380h+var_320]
0x180095a57  mov     rcx, r11
0x180095a5a  mov     rax, rsi
0x180095a5d  call    _guard_dispatch_icall
0x180095a62  nop
0x180095a63  mov     rsi, [rsp+380h+var_358]
0x180095a68  test    rsi, rsi
0x180095a6b  jz      short loc_180095AA4
0x180095a6d  or      eax, 0FFFFFFFFh
0x180095a70  lock xadd [rsi+8], eax
0x180095a75  cmp     eax, 1
0x180095a78  jnz     short loc_180095AA4
0x180095a7a  mov     rax, [rsi]
0x180095a7d  mov     rcx, rsi
0x180095a80  mov     rax, [rax]
0x180095a83  call    _guard_dispatch_icall
0x180095a88  or      eax, 0FFFFFFFFh
0x180095a8b  lock xadd [rsi+0Ch], eax
0x180095a90  cmp     eax, 1
0x180095a93  jnz     short loc_180095AA4
0x180095a95  mov     rax, [rsi]
0x180095a98  mov     rcx, rsi
0x180095a9b  mov     rax, [rax+8]
0x180095a9f  call    _guard_dispatch_icall
0x180095aa4  test    bl, 40h
0x180095aa7  jnz     short loc_180095ADF
0x180095aa9  mov     rax, [r14]
0x180095aac  lea     rdx, [rsp+380h+var_360]
0x180095ab1  mov     rcx, r14
0x180095ab4  mov     rax, [rax+38h]
0x180095ab8  call    _guard_dispatch_icall
0x180095abd  nop
0x180095abe  or      r15d, 4
0x180095ac2  mov     [rsp+380h+var_34C], r15d
0x180095ac7  mov     rcx, [rax]
0x180095aca  mov     rax, [rcx]
0x180095acd  mov     rax, [rax+28h]
0x180095ad1  call    _guard_dispatch_icall
0x180095ad6  test    al, al
0x180095ad8  jnz     short loc_180095ADF
0x180095ada  mov     r12b, 1
0x180095add  jmp     short loc_180095AE2
0x180095adf  xor     r12b, r12b
0x180095ae2  test    r15b, 4
0x180095ae6  jz      short loc_180095B2E
0x180095ae8  mov     rsi, [rsp+380h+var_358]
0x180095aed  xor     r15d, r15d
0x180095af0  test    rsi, rsi
0x180095af3  jz      short loc_180095B31
0x180095af5  or      eax, 0FFFFFFFFh
0x180095af8  lock xadd [rsi+8], eax
0x180095afd  cmp     eax, 1
0x180095b00  jnz     short loc_180095B31
0x180095b02  mov     rax, [rsi]
0x180095b05  mov     rcx, rsi
0x180095b08  mov     rax, [rax]
0x180095b0b  call    _guard_dispatch_icall
0x180095b10  or      eax, 0FFFFFFFFh
0x180095b13  lock xadd [rsi+0Ch], eax
0x180095b18  cmp     eax, 1
0x180095b1b  jnz     short loc_180095B31
0x180095b1d  mov     rax, [rsi]
0x180095b20  mov     rcx, rsi
0x180095b23  mov     rax, [rax+8]
0x180095b27  call    _guard_dispatch_icall
0x180095b2c  jmp     short loc_180095B31
0x180095b2e  xor     r15d, r15d
0x180095b31  test    r12b, r12b
0x180095b34  jz      loc_180095C04
0x180095b3a  or      edi, 40h
0x180095b3d  mov     rax, [r14]
0x180095b40  lea     rdx, [rsp+380h+var_360]
0x180095b45  mov     rcx, r14
0x180095b48  mov     rax, [rax+68h]
0x180095b4c  call    _guard_dispatch_icall
0x180095b51  nop
0x180095b52  mov     r11, [rax]
0x180095b55  mov     rax, [r11]
0x180095b58  mov     rsi, [rax+100h]
0x180095b5f  xor     r8d, r8d
0x180095b62  lea     r15, aTestoverrideDi; "TestOverride_displayReason"
0x180095b69  mov     rdx, r15
0x180095b6c  lea     r12, aDeferReasonNot; "Defer reason: not on AC"
0x180095b73  mov     rcx, r12
0x180095b76  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x180095b7b  cmp     rax, r15
0x180095b7e  jz      loc_180096807
  ... truncated ...
```
