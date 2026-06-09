# UxUpdateManager::GetRestartRequiredUpdateIdentifiers(void)

- ea: `0x18003e168`
- end: `0x18003e7d3`
- name: `?GetRestartRequiredUpdateIdentifiers@UxUpdateManager@@AEAA?AV?$vector@UUxUpdateIdentifier@UxUpdateManager@@V?$allocator@UUxUpdateIdentifier@UxUpdateManager@@@std@@@std@@XZ`
- size: `1643`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18003b5e0`
- `0x18003fa60`

## callees

- `0x1800108b4`
- `0x1800112d0`
- `0x180011680`
- `0x18001b00c`
- `0x18002ea8c`
- `0x18003e168`
- `0x180040358`
- `0x180060c80`
- `0x180061498`
- `0x1800dd930`
- `0x1800e4630`
- `0x1800e46b0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003e1dc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003e1dc`
- `OLEAUT32!__imp_SysFreeString` at `0x18003e615`
- `OLEAUT32!__imp_SysFreeString` at `0x18003e625`
- `OLEAUT32!__imp_SysFreeString` at `0x18003e635`
- `OLEAUT32!__imp_SysFreeString` at `0x18003e645`
- `OLEAUT32!__imp_SysFreeString` at `0x18003e615`
- `OLEAUT32!__imp_SysFreeString` at `0x18003e625`
- `OLEAUT32!__imp_SysFreeString` at `0x18003e635`
- `OLEAUT32!__imp_SysFreeString` at `0x18003e645`

## string_xrefs

- `0x18003e72e`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\result_macros.h`
- `0x18003e704`: `C:\__w\1\s\src\orchestrator\core\USOSvc\UxUpdateManager.cpp`
- `0x18003e719`: `C:\__w\1\s\src\orchestrator\core\USOSvc\UxUpdateManager.cpp`
- `0x18003e743`: `C:\__w\1\s\src\orchestrator\core\USOSvc\UxUpdateManager.cpp`
- `0x18003e758`: `C:\__w\1\s\src\orchestrator\core\USOSvc\UxUpdateManager.cpp`
- `0x18003e76d`: `C:\__w\1\s\src\orchestrator\core\USOSvc\UxUpdateManager.cpp`
- `0x18003e782`: `C:\__w\1\s\src\orchestrator\core\USOSvc\UxUpdateManager.cpp`
- `0x18003e797`: `C:\__w\1\s\src\orchestrator\core\USOSvc\UxUpdateManager.cpp`
- `0x18003e7ac`: `C:\__w\1\s\src\orchestrator\core\USOSvc\UxUpdateManager.cpp`
- `0x18003e7c1`: `C:\__w\1\s\src\orchestrator\core\USOSvc\UxUpdateManager.cpp`
- `0x18003e225`: `UxUpdateManager`

## pseudocode

```c
// Hidden C++ exception states: #wind=24
_QWORD *__fastcall UxUpdateManager::GetRestartRequiredUpdateIdentifiers(__int64 a1, _QWORD *a2)
{
  HRESULT v3; // eax
  __int64 v4; // rax
  int v5; // eax
  __int64 v6; // rax
  int v7; // eax
  int v8; // eax
  int v9; // esi
  unsigned int v10; // edi
  __m128i si128; // xmm7
  __m128i v12; // xmm6
  __int64 v13; // rax
  int v14; // eax
  int v15; // eax
  __int64 v16; // rax
  int v17; // eax
  __int64 v18; // rax
  int v19; // eax
  __int64 v20; // rax
  int v21; // eax
  __int64 v22; // rax
  int v23; // eax
  unsigned __int64 v24; // r8
  unsigned __int64 v25; // r8
  unsigned __int64 v26; // r8
  unsigned __int64 v27; // r8
  __int128 *v28; // r8
  void (__fastcall ***v29)(_QWORD, __int64); // rax
  __int64 v30; // rdx
  int ppv; // [rsp+28h] [rbp-E0h]
  __int128 v33; // [rsp+40h] [rbp-C8h] BYREF
  __int128 v34; // [rsp+50h] [rbp-B8h]
  _QWORD *v35; // [rsp+60h] [rbp-A8h]
  __int64 *v36; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v37; // [rsp+70h] [rbp-98h] BYREF
  __int64 *v38; // [rsp+78h] [rbp-90h] BYREF
  BSTR bstrString; // [rsp+80h] [rbp-88h] BYREF
  BSTR v40; // [rsp+88h] [rbp-80h] BYREF
  BSTR v41; // [rsp+90h] [rbp-78h] BYREF
  BSTR v42; // [rsp+98h] [rbp-70h] BYREF
  __int64 *v43; // [rsp+A0h] [rbp-68h] BYREF
  __int64 *v44; // [rsp+A8h] [rbp-60h] BYREF
  LPVOID v45; // [rsp+B0h] [rbp-58h] BYREF
  __int64 v46; // [rsp+B8h] [rbp-50h] BYREF
  int v47; // [rsp+C0h] [rbp-48h]
  __int128 v48; // [rsp+C8h] [rbp-40h] BYREF
  __m128i v49; // [rsp+D8h] [rbp-30h]
  __int128 v50; // [rsp+E8h] [rbp-20h] BYREF
  __m128i v51; // [rsp+F8h] [rbp-10h]
  __int128 v52; // [rsp+108h] [rbp+0h] BYREF
  __m128i v53; // [rsp+118h] [rbp+10h]
  __int128 v54; // [rsp+128h] [rbp+20h] BYREF
  __m128i v55; // [rsp+138h] [rbp+30h]
  _QWORD v56[16]; // [rsp+148h] [rbp+40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+210h] [rbp+108h]

  v35 = a2;
  v45 = 0;
  v3 = CoCreateInstance(
         &GUID_b91d5831_b1bd_4608_8198_d72e155020f7,
         0,
         4u,
         &GUID_07f3afac_7c8a_4ce7_a5e0_3d24ee8a77e0,
         &v45);
  if ( v3 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1C96,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)v3,
      ppv);
  v44 = 0;
  wil::com_ptr_t<IUpdateSessionOrchestrator,wil::err_exception_policy>::query<IMoUsoOrchestrator>(
    (__int64 (__fastcall ****)(_QWORD, GUID *, _QWORD *))&v45,
    &v44);
  v43 = 0;
  v4 = *v44;
  v43 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, const OLECHAR *, __int64 **))(v4 + 24))(
         v44,
         L"UxUpdateManager",
         &S1,
         &v43);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x49B,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\UxUpdateManager.cpp",
      (const char *)(unsigned int)v5,
      ppv);
  v38 = 0;
  v6 = *v43;
  v38 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64 *, __int64 **))(v6 + 48))(v43, &v38);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x49E,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\UxUpdateManager.cpp",
      (const char *)(unsigned int)v7,
      ppv);
  LODWORD(v37) = 0;
  v8 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(*v38 + 32))(v38, &v37);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x4A1,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\UxUpdateManager.cpp",
      (const char *)(unsigned int)v8,
      ppv);
  *(_OWORD *)a2 = 0;
  *a2 = 0;
  a2[1] = 0;
  a2[2] = 0;
  v9 = 9;
  v10 = 0;
  if ( (_DWORD)v37 )
  {
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    v12 = _mm_load_si128((const __m128i *)&_xmm);
    do
    {
      v36 = 0;
      v13 = *v38;
      v36 = 0;
      v14 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 **))(v13 + 24))(v38, v10, &v36);
      if ( v14 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x4A7,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\UxUpdateManager.cpp",
          (const char *)(unsigned int)v14,
          ppv);
      v46 = 0;
      v47 = 0;
      v15 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(*v36 + 128))(v36, &v46);
      if ( v15 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x4AA,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\UxUpdateManager.cpp",
          (const char *)(unsigned int)v15,
          ppv);
      if ( v47 == 2 )
      {
        v42 = 0;
        v16 = *v36;
        v42 = 0;
        v17 = (*(__int64 (__fastcall **)(__int64 *, BSTR *))(v16 + 112))(v36, &v42);
        if ( v17 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x4B2,
            (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\UxUpdateManager.cpp",
            (const char *)(unsigned int)v17,
            ppv);
        v41 = 0;
        v18 = *v36;
        v41 = 0;
        v19 = (*(__int64 (__fastcall **)(__int64 *, BSTR *))(v18 + 160))(v36, &v41);
        if ( v19 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x4B5,
            (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\UxUpdateManager.cpp",
            (const char *)(unsigned int)v19,
            ppv);
        v40 = 0;
        v20 = *v36;
        v40 = 0;
        v21 = (*(__int64 (__fastcall **)(__int64 *, BSTR *))(v20 + 248))(v36, &v40);
        if ( v21 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x4B8,
            (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\UxUpdateManager.cpp",
            (const char *)(unsigned int)v21,
            ppv);
        bstrString = 0;
        v22 = *v36;
        bstrString = 0;
        v23 = (*(__int64 (__fastcall **)(__int64 *, BSTR *))(v22 + 256))(v36, &bstrString);
        if ( v23 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x4BB,
            (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\UxUpdateManager.cpp",
            (const char *)(unsigned int)v23,
            ppv);
        v48 = 0;
        v49 = 0;
        v24 = -1;
        do
          ++v24;
        while ( v42[v24] );
        std::wstring::_Construct<1,wchar_t const *>(&v48, v42, v24);
        v50 = 0;
        v51 = 0;
        v25 = -1;
        do
          ++v25;
        while ( v41[v25] );
        std::wstring::_Construct<1,wchar_t const *>(&v50, v41, v25);
        v52 = 0;
        v53 = 0;
        v26 = -1;
        do
          ++v26;
        while ( v40[v26] );
        std::wstring::_Construct<1,wchar_t const *>(&v52, v40, v26);
        v33 = 0;
        v34 = 0;
        v27 = -1;
        do
          ++v27;
        while ( bstrString[v27] );
        std::wstring::_Construct<1,wchar_t const *>(&v33, bstrString, v27);
        memset(v56, 0, 0x78u);
        std::wstring_convert<std::codecvt_utf8<wchar_t,1114111,0>,wchar_t,std::allocator<wchar_t>,std::allocator<char>>::wstring_convert<std::codecvt_utf8<wchar_t,1114111,0>,wchar_t,std::allocator<wchar_t>,std::allocator<char>>(v56);
        v28 = &v33;
        if ( *((_QWORD *)&v34 + 1) > 7u )
          v28 = (__int128 *)v33;
        std::wstring_convert<std::codecvt_utf8<wchar_t,1114111,0>,wchar_t,std::allocator<wchar_t>,std::allocator<char>>::to_bytes(
          v56,
          &v54,
          v28,
          (char *)v28 + 2 * v34);
        v9 |= 6u;
        v56[0] = &std::wstring_convert<std::codecvt_utf8<wchar_t,1114111,0>,wchar_t,std::allocator<wchar_t>,std::allocator<char>>::`vftable';
        std::wstring::~wstring(&v56[8]);
        std::string::~string((__int64)&v56[4]);
        if ( v56[3] )
        {
          v29 = (void (__fastcall ***)(_QWORD, __int64))(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v56[3] + 16LL))(v56[3]);
          if ( v29 )
            (**v29)(v29, 1);
        }
        std::wstring::~wstring(&v33);
        v30 = a2[1];
        if ( v30 == a2[2] )
        {
          std::vector<UxUpdateManager::UxUpdateIdentifier>::_Emplace_reallocate<UxUpdateManager::UxUpdateIdentifier>(
            a2,
            (_QWORD *)v30,
            &v48);
        }
        else
        {
          *(_OWORD *)v30 = v48;
          *(__m128i *)(v30 + 16) = v49;
          v49 = v12;
          LOWORD(v48) = 0;
          *(_OWORD *)(v30 + 32) = v50;
          *(__m128i *)(v30 + 48) = v51;
          v51 = v12;
          LOWORD(v50) = 0;
          *(_OWORD *)(v30 + 64) = v52;
          *(__m128i *)(v30 + 80) = v53;
          v53 = v12;
          LOWORD(v52) = 0;
          *(_OWORD *)(v30 + 96) = v54;
          *(__m128i *)(v30 + 112) = v55;
          v55 = si128;
          LOBYTE(v54) = 0;
          a2[1] += 128LL;
        }
        std::string::~string((__int64)&v54);
        std::wstring::~wstring(&v52);
        std::wstring::~wstring(&v50);
        std::wstring::~wstring(&v48);
        if ( bstrString )
          SysFreeString(bstrString);
        if ( v40 )
          SysFreeString(v40);
        if ( v41 )
          SysFreeString(v41);
        if ( v42 )
          SysFreeString(v42);
        if ( v36 )
          (*(void (__fastcall **)(__int64 *))(*v36 + 16))(v36);
      }
      else if ( v36 )
      {
        (*(void (__fastcall **)(__int64 *))(*v36 + 16))(v36);
      }
      ++v10;
    }
    while ( v10 < (unsigned int)v37 );
  }
  if ( v38 )
    (*(void (__fastcall **)(__int64 *))(*v38 + 16))(v38);
  if ( v43 )
    (*(void (__fastcall **)(__int64 *))(*v43 + 16))(v43);
  if ( v44 )
    (*(void (__fastcall **)(__int64 *))(*v44 + 16))(v44);
  if ( v45 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v45 + 16LL))(v45);
  return a2;
}

```

## disassembly

```asm
0x18003e168  mov     rax, rsp
0x18003e16b  mov     [rax+8], rbx
0x18003e16f  mov     [rax+18h], rsi
0x18003e173  mov     [rax+20h], rdi
0x18003e177  push    rbp
0x18003e178  push    r14
0x18003e17a  push    r15
0x18003e17c  lea     rbp, [rax-108h]
0x18003e183  sub     rsp, 1F0h
0x18003e18a  movaps  xmmword ptr [rax-28h], xmm6
0x18003e18e  movaps  xmmword ptr [rax-38h], xmm7
0x18003e192  mov     rax, cs:__security_cookie
0x18003e199  xor     rax, rsp
0x18003e19c  mov     [rbp+100h+var_40], rax
0x18003e1a3  mov     rbx, rdx
0x18003e1a6  mov     [rsp+200h+var_1A8], rdx
0x18003e1ab  xor     r14d, r14d
0x18003e1ae  mov     dword ptr [rsp+200h+var_1D0], r14d
0x18003e1b3  mov     dword ptr [rsp+200h+var_1D0], 10h
0x18003e1bb  mov     [rbp+100h+var_158], r14
0x18003e1bf  lea     rax, [rbp+100h+var_158]
0x18003e1c3  mov     qword ptr [rsp+200h+ppv], rax; int
0x18003e1c8  lea     r9, _GUID_07f3afac_7c8a_4ce7_a5e0_3d24ee8a77e0; riid
0x18003e1cf  xor     edx, edx; pUnkOuter
0x18003e1d1  lea     r8d, [r14+4]; dwClsContext
0x18003e1d5  lea     rcx, _GUID_b91d5831_b1bd_4608_8198_d72e155020f7; rclsid
0x18003e1dc  call    cs:__imp_CoCreateInstance
0x18003e1e2  mov     rcx, [rbp+108h]; this
0x18003e1e9  test    eax, eax
0x18003e1eb  js      loc_18003E72B
0x18003e1f1  mov     dword ptr [rsp+200h+var_1D0], 8
0x18003e1f9  mov     [rbp+100h+var_160], r14
0x18003e1fd  lea     rdx, [rbp+100h+var_160]
0x18003e201  lea     rcx, [rbp+100h+var_158]
0x18003e205  call    ??$query@UIMoUsoOrchestrator@@@?$com_ptr_t@UIUpdateSessionOrchestrator@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIMoUsoOrchestrator@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<IUpdateSessionOrchestrator,wil::err_exception_policy>::query<IMoUsoOrchestrator>(void)
0x18003e20a  nop
0x18003e20b  mov     [rbp+100h+var_168], r14
0x18003e20f  mov     rcx, [rbp+100h+var_160]
0x18003e213  mov     rax, [rcx]
0x18003e216  mov     [rbp+100h+var_168], r14
0x18003e21a  lea     r9, [rbp+100h+var_168]
0x18003e21e  lea     r8, S1
0x18003e225  lea     rdx, aUxupdatemanage; "UxUpdateManager"
0x18003e22c  mov     rax, [rax+18h]
0x18003e230  call    _guard_dispatch_icall
0x18003e235  mov     rcx, [rbp+108h]; this
0x18003e23c  test    eax, eax
0x18003e23e  js      loc_18003E740
0x18003e244  mov     [rsp+200h+var_190], r14
0x18003e249  mov     rcx, [rbp+100h+var_168]
0x18003e24d  mov     rax, [rcx]
0x18003e250  mov     [rsp+200h+var_190], r14
0x18003e255  lea     rdx, [rsp+200h+var_190]
0x18003e25a  mov     rax, [rax+30h]
0x18003e25e  call    _guard_dispatch_icall
0x18003e263  mov     rcx, [rbp+108h]; this
0x18003e26a  test    eax, eax
0x18003e26c  js      loc_18003E755
0x18003e272  mov     dword ptr [rsp+200h+var_198], r14d
0x18003e277  mov     rcx, [rsp+200h+var_190]
0x18003e27c  mov     rax, [rcx]
0x18003e27f  lea     rdx, [rsp+200h+var_198]
0x18003e284  mov     rax, [rax+20h]
0x18003e288  call    _guard_dispatch_icall
0x18003e28d  mov     rcx, [rbp+108h]; this
0x18003e294  test    eax, eax
0x18003e296  js      loc_18003E76A
0x18003e29c  xorps   xmm0, xmm0
0x18003e29f  movups  xmmword ptr [rbx], xmm0
0x18003e2a2  mov     [rbx], r14
0x18003e2a5  mov     [rbx+8], r14
0x18003e2a9  mov     [rbx+10h], r14
0x18003e2ad  lea     esi, [r14+9]
0x18003e2b1  mov     dword ptr [rsp+200h+var_1D0], esi
0x18003e2b5  mov     edi, r14d
0x18003e2b8  cmp     dword ptr [rsp+200h+var_198], r14d
0x18003e2bd  jbe     loc_18003E66F
0x18003e2c3  or      r15, 0FFFFFFFFFFFFFFFFh
0x18003e2c7  movdqa  xmm7, cs:__xmm@000000000000000f0000000000000000
0x18003e2cf  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x18003e2d7  mov     [rsp+200h+var_1A0], r14
0x18003e2dc  mov     rcx, [rsp+200h+var_190]
0x18003e2e1  mov     rax, [rcx]
0x18003e2e4  mov     [rsp+200h+var_1A0], r14
0x18003e2e9  lea     r8, [rsp+200h+var_1A0]
0x18003e2ee  mov     edx, edi
0x18003e2f0  mov     rax, [rax+18h]
0x18003e2f4  call    _guard_dispatch_icall
0x18003e2f9  mov     rcx, [rbp+108h]; this
0x18003e300  test    eax, eax
0x18003e302  js      loc_18003E716
0x18003e308  xor     eax, eax
0x18003e30a  mov     [rbp+100h+var_150], rax
0x18003e30e  mov     [rbp+100h+var_148], eax
0x18003e311  mov     rcx, [rsp+200h+var_1A0]
0x18003e316  mov     rax, [rcx]
0x18003e319  lea     rdx, [rbp+100h+var_150]
0x18003e31d  mov     rax, [rax+80h]
0x18003e324  call    _guard_dispatch_icall
0x18003e329  mov     rcx, [rbp+108h]; this
0x18003e330  test    eax, eax
0x18003e332  js      loc_18003E701
0x18003e338  cmp     [rbp+100h+var_148], 2
0x18003e33c  jz      short loc_18003E35A
0x18003e33e  mov     rcx, [rsp+200h+var_1A0]
0x18003e343  test    rcx, rcx
0x18003e346  jz      short loc_18003E355
0x18003e348  mov     rax, [rcx]
0x18003e34b  mov     rax, [rax+10h]
0x18003e34f  call    _guard_dispatch_icall
0x18003e354  nop
0x18003e355  jmp     loc_18003E663
0x18003e35a  mov     [rbp+100h+var_170], r14
0x18003e35e  mov     rcx, [rsp+200h+var_1A0]
0x18003e363  mov     rax, [rcx]
0x18003e366  mov     [rbp+100h+var_170], r14
0x18003e36a  lea     rdx, [rbp+100h+var_170]
0x18003e36e  mov     rax, [rax+70h]
0x18003e372  call    _guard_dispatch_icall
0x18003e377  mov     rcx, [rbp+108h]; this
0x18003e37e  test    eax, eax
0x18003e380  js      loc_18003E7BE
0x18003e386  mov     [rbp+100h+var_178], r14
0x18003e38a  mov     rcx, [rsp+200h+var_1A0]
0x18003e38f  mov     rax, [rcx]
0x18003e392  mov     [rbp+100h+var_178], r14
0x18003e396  lea     rdx, [rbp+100h+var_178]
0x18003e39a  mov     rax, [rax+0A0h]
0x18003e3a1  call    _guard_dispatch_icall
0x18003e3a6  mov     rcx, [rbp+108h]; this
0x18003e3ad  test    eax, eax
0x18003e3af  js      loc_18003E7A9
0x18003e3b5  mov     [rbp+100h+var_180], r14
0x18003e3b9  mov     rcx, [rsp+200h+var_1A0]
0x18003e3be  mov     rax, [rcx]
0x18003e3c1  mov     [rbp+100h+var_180], r14
0x18003e3c5  lea     rdx, [rbp+100h+var_180]
0x18003e3c9  mov     rax, [rax+0F8h]
0x18003e3d0  call    _guard_dispatch_icall
0x18003e3d5  mov     rcx, [rbp+108h]; this
0x18003e3dc  test    eax, eax
0x18003e3de  js      loc_18003E794
0x18003e3e4  mov     [rsp+200h+bstrString], r14
0x18003e3e9  mov     rcx, [rsp+200h+var_1A0]
0x18003e3ee  mov     rax, [rcx]
0x18003e3f1  mov     [rsp+200h+bstrString], r14
0x18003e3f6  lea     rdx, [rsp+200h+bstrString]
0x18003e3fb  mov     rax, [rax+100h]
0x18003e402  call    _guard_dispatch_icall
0x18003e407  mov     rcx, [rbp+108h]; this
0x18003e40e  test    eax, eax
0x18003e410  js      loc_18003E77F
0x18003e416  xorps   xmm0, xmm0
0x18003e419  movups  [rbp+100h+var_140], xmm0
0x18003e41d  xorps   xmm1, xmm1
0x18003e420  movdqa  [rbp+100h+var_130], xmm1
0x18003e425  mov     rdx, [rbp+100h+var_170]
0x18003e429  mov     r8, r15
0x18003e42c  inc     r8
0x18003e42f  cmp     [rdx+r8*2], r14w
0x18003e434  jnz     short loc_18003E42C
0x18003e436  lea     rcx, [rbp+100h+var_140]
0x18003e43a  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18003e43f  nop
0x18003e440  xorps   xmm0, xmm0
0x18003e443  movups  [rbp+100h+var_120], xmm0
0x18003e447  xorps   xmm1, xmm1
0x18003e44a  movdqa  [rbp+100h+var_110], xmm1
0x18003e44f  mov     rdx, [rbp+100h+var_178]
0x18003e453  mov     r8, r15
0x18003e456  inc     r8
0x18003e459  cmp     [rdx+r8*2], r14w
0x18003e45e  jnz     short loc_18003E456
0x18003e460  lea     rcx, [rbp+100h+var_120]
0x18003e464  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18003e469  nop
0x18003e46a  xorps   xmm0, xmm0
0x18003e46d  movups  [rbp+100h+var_100], xmm0
0x18003e471  xorps   xmm1, xmm1
0x18003e474  movdqa  [rbp+100h+var_F0], xmm1
0x18003e479  mov     rdx, [rbp+100h+var_180]
0x18003e47d  mov     r8, r15
0x18003e480  inc     r8
0x18003e483  cmp     [rdx+r8*2], r14w
0x18003e488  jnz     short loc_18003E480
0x18003e48a  lea     rcx, [rbp+100h+var_100]
0x18003e48e  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18003e493  nop
0x18003e494  xorps   xmm0, xmm0
0x18003e497  movups  [rsp+200h+var_1D0+8], xmm0
0x18003e49c  xorps   xmm1, xmm1
0x18003e49f  movdqu  [rsp+200h+var_1C0+8], xmm1
0x18003e4a5  mov     rdx, [rsp+200h+bstrString]
0x18003e4aa  mov     r8, r15
0x18003e4ad  inc     r8
0x18003e4b0  cmp     [rdx+r8*2], r14w
0x18003e4b5  jnz     short loc_18003E4AD
0x18003e4b7  lea     rcx, [rsp+200h+var_1D0+8]
0x18003e4bc  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18003e4c1  nop
0x18003e4c2  xor     edx, edx; Val
0x18003e4c4  lea     r8d, [rdx+78h]; Size
0x18003e4c8  lea     rcx, [rbp+100h+var_C0]; void *
0x18003e4cc  call    memset
0x18003e4d1  lea     rcx, [rbp+100h+var_C0]
0x18003e4d5  call    ??0?$wstring_convert@V?$codecvt_utf8@_W$0BAPPPP@$0A@@std@@_WV?$allocator@_W@2@V?$allocator@D@2@@std@@QEAA@XZ; std::wstring_convert<std::codecvt_utf8<wchar_t,1114111,0>,wchar_t,std::allocator<wchar_t>,std::allocator<char>>::wstring_convert<std::codecvt_utf8<wchar_t,1114111,0>,wchar_t,std::allocator<wchar_t>,std::allocator<char>>(void)
0x18003e4da  nop
0x18003e4db  lea     r8, [rsp+200h+var_1D0+8]
0x18003e4e0  cmp     [rsp+200h+var_1B0], 7
0x18003e4e6  cmova   r8, qword ptr [rsp+200h+var_1D0+8]
0x18003e4ec  mov     rax, qword ptr [rsp+200h+var_1C0+8]
0x18003e4f1  lea     r9, [r8+rax*2]
0x18003e4f5  lea     rdx, [rbp+100h+var_E0]
0x18003e4f9  lea     rcx, [rbp+100h+var_C0]
0x18003e4fd  call    ?to_bytes@?$wstring_convert@V?$codecvt_utf8@_W$0BAPPPP@$0A@@std@@_WV?$allocator@_W@2@V?$allocator@D@2@@std@@QEAA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@PEB_W0@Z; std::wstring_convert<std::codecvt_utf8<wchar_t,1114111,0>,wchar_t,std::allocator<wchar_t>,std::allocator<char>>::to_bytes(wchar_t const *,wchar_t const *)
0x18003e502  or      esi, 6
0x18003e505  mov     dword ptr [rsp+200h+var_1D0], esi
0x18003e509  lea     rax, ??_7?$wstring_convert@V?$codecvt_utf8@_W$0BAPPPP@$0A@@std@@_WV?$allocator@_W@2@V?$allocator@D@2@@std@@6B@; const std::wstring_convert<std::codecvt_utf8<wchar_t,1114111,0>,wchar_t,std::allocator<wchar_t>,std::allocator<char>>::`vftable'
0x18003e510  mov     [rbp+100h+var_C0], rax
0x18003e514  lea     rcx, [rbp+100h+var_80]; void *
0x18003e51b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003e520  lea     rcx, [rbp+100h+var_A0]
0x18003e524  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18003e529  mov     rcx, [rbp+100h+var_A8]
0x18003e52d  test    rcx, rcx
0x18003e530  jz      short loc_18003E557
0x18003e532  mov     rax, [rcx]
0x18003e535  mov     rax, [rax+10h]
0x18003e539  call    _guard_dispatch_icall
0x18003e53e  mov     rcx, rax
0x18003e541  test    rax, rax
0x18003e544  jz      short loc_18003E557
0x18003e546  mov     rax, [rax]
0x18003e549  mov     edx, 1
0x18003e54e  mov     rax, [rax]
0x18003e551  call    _guard_dispatch_icall
0x18003e556  nop
0x18003e557  lea     rcx, [rsp+200h+var_1D0+8]; void *
0x18003e55c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003e561  nop
0x18003e562  mov     rdx, [rbx+8]
0x18003e566  cmp     rdx, [rbx+10h]
0x18003e56a  jz      short loc_18003E5D9
0x18003e56c  movaps  xmm0, [rbp+100h+var_140]
0x18003e570  movups  xmmword ptr [rdx], xmm0
0x18003e573  movaps  xmm1, [rbp+100h+var_130]
0x18003e577  movups  xmmword ptr [rdx+10h], xmm1
0x18003e57b  movdqa  [rbp+100h+var_130], xmm6
0x18003e580  mov     word ptr [rbp+100h+var_140], r14w
0x18003e585  movaps  xmm0, [rbp+100h+var_120]
0x18003e589  movups  xmmword ptr [rdx+20h], xmm0
0x18003e58d  movaps  xmm1, [rbp+100h+var_110]
0x18003e591  movups  xmmword ptr [rdx+30h], xmm1
0x18003e595  movdqa  [rbp+100h+var_110], xmm6
0x18003e59a  mov     word ptr [rbp+100h+var_120], r14w
0x18003e59f  movaps  xmm0, [rbp+100h+var_100]
0x18003e5a3  movups  xmmword ptr [rdx+40h], xmm0
0x18003e5a7  movaps  xmm1, [rbp+100h+var_F0]
0x18003e5ab  movups  xmmword ptr [rdx+50h], xmm1
0x18003e5af  movdqa  [rbp+100h+var_F0], xmm6
0x18003e5b4  mov     word ptr [rbp+100h+var_100], r14w
0x18003e5b9  movaps  xmm0, [rbp+100h+var_E0]
0x18003e5bd  movups  xmmword ptr [rdx+60h], xmm0
0x18003e5c1  movaps  xmm1, [rbp+100h+var_D0]
0x18003e5c5  movups  xmmword ptr [rdx+70h], xmm1
0x18003e5c9  movdqa  [rbp+100h+var_D0], xmm7
0x18003e5ce  mov     byte ptr [rbp+100h+var_E0], r14b
0x18003e5d2  sub     qword ptr [rbx+8], 0FFFFFFFFFFFFFF80h
0x18003e5d7  jmp     short loc_18003E5E6
0x18003e5d9  lea     r8, [rbp+100h+var_140]
0x18003e5dd  mov     rcx, rbx
0x18003e5e0  call    ??$_Emplace_reallocate@UUxUpdateIdentifier@UxUpdateManager@@@?$vector@UUxUpdateIdentifier@UxUpdateManager@@V?$allocator@UUxUpdateIdentifier@UxUpdateManager@@@std@@@std@@AEAAPEAUUxUpdateIdentifier@UxUpdateManager@@QEAU23@$$QEAU23@@Z; std::vector<UxUpdateManager::UxUpdateIdentifier>::_Emplace_reallocate<UxUpdateManager::UxUpdateIdentifier>(UxUpdateManager::UxUpdateIdentifier * const,UxUpdateManager::UxUpdateIdentifier &&)
0x18003e5e5  nop
0x18003e5e6  lea     rcx, [rbp+100h+var_E0]
0x18003e5ea  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18003e5ef  lea     rcx, [rbp+100h+var_100]; void *
0x18003e5f3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003e5f8  lea     rcx, [rbp+100h+var_120]; void *
0x18003e5fc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003e601  lea     rcx, [rbp+100h+var_140]; void *
0x18003e605  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003e60a  nop
0x18003e60b  mov     rcx, [rsp+200h+bstrString]; bstrString
0x18003e610  test    rcx, rcx
0x18003e613  jz      short loc_18003E61C
0x18003e615  call    cs:__imp_SysFreeString
0x18003e61b  nop
0x18003e61c  mov     rcx, [rbp+100h+var_180]; bstrString
0x18003e620  test    rcx, rcx
0x18003e623  jz      short loc_18003E62C
0x18003e625  call    cs:__imp_SysFreeString
0x18003e62b  nop
0x18003e62c  mov     rcx, [rbp+100h+var_178]; bstrString
0x18003e630  test    rcx, rcx
0x18003e633  jz      short loc_18003E63C
0x18003e635  call    cs:__imp_SysFreeString
0x18003e63b  nop
0x18003e63c  mov     rcx, [rbp+100h+var_170]; bstrString
0x18003e640  test    rcx, rcx
0x18003e643  jz      short loc_18003E64C
  ... truncated ...
```
