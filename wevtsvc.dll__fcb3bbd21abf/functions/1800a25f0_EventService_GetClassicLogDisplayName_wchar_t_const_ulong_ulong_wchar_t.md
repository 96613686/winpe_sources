# EventService::GetClassicLogDisplayName(wchar_t const *,ulong,ulong,wchar_t * &)

- ea: `0x1800a25f0`
- end: `0x1800a2f8a`
- name: `?GetClassicLogDisplayName@EventService@@QEAAXPEB_WKKAEAPEA_W@Z`
- size: `2458`
- prototype: `void __fastcall(EventService *this, const wchar_t *, LCID, __int16, wchar_t **)`
- caller_count: `1`
- callee_count: `28`
- tags: `authz_impersonation, registry_config, loader_planting, service_task`

## callers

- `0x1800a8910`

## callees

- `0x180006770`
- `0x180014bd0`
- `0x180016250`
- `0x180017b60`
- `0x180017b98`
- `0x18002afa8`
- `0x18002c668`
- `0x18002c6f4`
- `0x18002d204`
- `0x18002e5ac`
- `0x18002ede4`
- `0x1800338c0`
- `0x18005af7c`
- `0x18006c144`
- `0x18006f06c`
- `0x180070418`
- `0x180075a84`
- `0x18008aa0c`
- `0x18008cb3c`
- `0x180092008`
- `0x18009aee0`
- `0x18009b590`
- `0x18009bb88`
- `0x1800a25f0`
- `0x1800a7b60`
- `0x1800a7cd8`
- `0x1800d334c`
- `0x1800d3370`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a27ca`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a27ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a29e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2aae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2c09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2d94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a29e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2aae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2c09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2d94`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800a29d3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800a29d3`
- `api-ms-win-core-localization-l1-2-4!SetThreadPreferredUILanguages2` at `0x1800a2bff`
- `api-ms-win-core-localization-l1-2-4!SetThreadPreferredUILanguages2` at `0x1800a2bff`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800a2d74`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800a2d74`
- `api-ms-win-core-localization-l1-2-2!LCIDToLocaleName` at `0x1800a2aa0`
- `api-ms-win-core-localization-l1-2-2!LCIDToLocaleName` at `0x1800a2aa0`
- `RPCRT4!RpcImpersonateClient` at `0x1800a26d2`
- `RPCRT4!RpcImpersonateClient` at `0x1800a26d2`
- `RPCRT4!RpcRevertToSelf` at `0x1800a2eea`
- `RPCRT4!RpcRevertToSelf` at `0x1800a2eea`

## string_xrefs

- `0x1800a2762`: `SYSTEM\CurrentControlSet\Services\Eventlog`

## pseudocode

```c
void __fastcall EventService::GetClassicLogDisplayName(
        EventService *this,
        const wchar_t *a2,
        LCID a3,
        __int16 a4,
        wchar_t **a5)
{
  __int64 v8; // rax
  unsigned int v9; // eax
  unsigned int v10; // edi
  unsigned int v11; // eax
  unsigned int v12; // edi
  HKEY *phkResult; // rax
  unsigned int v14; // eax
  unsigned int v15; // edi
  int v16; // edi
  int StringValueNoThrow; // eax
  __int64 v18; // r8
  unsigned int v19; // eax
  int v20; // edi
  HMODULE Library; // rbx
  DWORD LastError; // edi
  int v23; // eax
  DWORD v24; // eax
  unsigned int v25; // edi
  PVOID *v26; // rcx
  DWORD v27; // edi
  PVOID *v28; // rcx
  unsigned __int16 v29; // ax
  int HresultOrFail; // edi
  DWORD v31; // eax
  unsigned int v32; // edx
  void **v33; // rax
  __int64 v34; // rdx
  void **v35; // rcx
  wchar_t *v36; // rax
  void **v37; // rdx
  __int128 v38; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v39; // [rsp+50h] [rbp-B0h]
  int v40; // [rsp+58h] [rbp-A8h]
  int v41; // [rsp+5Ch] [rbp-A4h]
  int v42; // [rsp+60h] [rbp-A0h]
  char v43; // [rsp+64h] [rbp-9Ch]
  WCHAR Buffer[4]; // [rsp+68h] [rbp-98h] BYREF
  LPCWSTR pExceptionObject; // [rsp+70h] [rbp-90h] BYREF
  __int64 v46; // [rsp+78h] [rbp-88h]
  __int64 v47; // [rsp+80h] [rbp-80h]
  unsigned int v48; // [rsp+88h] [rbp-78h]
  int v49; // [rsp+8Ch] [rbp-74h]
  int v50; // [rsp+90h] [rbp-70h]
  char v51; // [rsp+94h] [rbp-6Ch]
  DWORD dwMessageId; // [rsp+98h] [rbp-68h] BYREF
  HKEY hKey; // [rsp+A0h] [rbp-60h] BYREF
  char v54; // [rsp+A9h] [rbp-57h]
  _QWORD v55[2]; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v56[2]; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD *v57; // [rsp+D0h] [rbp-30h] BYREF
  char v58; // [rsp+D8h] [rbp-28h]
  LPCWSTR lpSubKey[4]; // [rsp+E0h] [rbp-20h] BYREF
  LPCWSTR lpSrc[4]; // [rsp+100h] [rbp+0h] BYREF
  void *Src[2]; // [rsp+120h] [rbp+20h] BYREF
  __int64 v62; // [rsp+130h] [rbp+30h]
  unsigned __int64 v63; // [rsp+138h] [rbp+38h]
  WCHAR Name[88]; // [rsp+140h] [rbp+40h] BYREF

  v8 = -1;
  do
    ++v8;
  while ( a2[v8] );
  v56[0] = a2;
  v56[1] = v8;
  v9 = ScanForInvalidChars(v56, 15000);
  v10 = v9;
  if ( v9 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 150, &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids, v9);
    }
    pExceptionObject = &byte_1800EC961;
    v46 = 0;
    v47 = 0;
    v48 = v10;
    v49 = -1;
    v50 = -1;
    v51 = 0;
    throw (EvtException *)&pExceptionObject;
  }
  v11 = RpcImpersonateClient(0);
  v12 = v11;
  if ( v11 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 151, &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids, v11);
    }
    pExceptionObject = &byte_1800EC961;
    v46 = 0;
    v47 = 0;
    v48 = v12;
    v49 = -1;
    v50 = -1;
    v51 = 0;
    throw (EvtException *)&pExceptionObject;
  }
  v54 = 1;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpSubKey);
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                           lpSubKey,
                           L"SYSTEM\\CurrentControlSet\\Services\\Eventlog",
                           42)
    || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                           lpSubKey,
                           92)
    || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                           lpSubKey,
                           a2) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 152, &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids, 14);
    }
    v38 = 0;
    v39 = 0;
    v40 = 14;
    v41 = -1;
    v42 = 3404;
    throw (EvtException *)&v38;
  }
  hKey = 0;
  phkResult = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  v14 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey[0], 0, 1u, phkResult);
  v15 = v14;
  if ( v14 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 153, &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids, v14);
    }
    pExceptionObject = &byte_1800EC961;
    v46 = 0;
    v47 = 0;
    v48 = v15;
    v49 = -1;
    v50 = -1;
    v51 = 0;
    throw (EvtException *)&pExceptionObject;
  }
  dwMessageId = 0;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpSrc);
  v16 = RegReadDWORDValueNoThrow(hKey, 0, L"DisplayNameID", &dwMessageId);
  StringValueNoThrow = RegReadStringValueNoThrow(hKey);
  *(_OWORD *)Src = 0;
  v62 = 0;
  v63 = 7;
  LOWORD(Src[0]) = 0;
  if ( StringValueNoThrow )
  {
    if ( !v16 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 154, &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids, 13);
      }
      v38 = 0;
      v39 = 0;
      v40 = 13;
      v41 = -1;
      v42 = 3435;
      throw (EvtException *)&v38;
    }
    v18 = -1;
    do
      ++v18;
    while ( a2[v18] );
    std::wstring::_Assign<wchar_t>(Src, a2);
  }
  else
  {
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&pExceptionObject);
    v19 = ExpandEnvStringNoThrow(lpSrc[0]);
    v20 = v19;
    if ( v19 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 155, &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids, v19);
      }
      *(_QWORD *)&v38 = &byte_1800EC961;
      *((_QWORD *)&v38 + 1) = 0;
      v39 = 0;
      v40 = v20;
      v41 = -1;
      v42 = -1;
      v43 = 0;
      throw (EvtException *)&v38;
    }
    Library = LoadLibraryExW(pExceptionObject, 0, 0x20u);
    v56[0] = Library;
    if ( !Library )
    {
      LastError = GetLastError();
      if ( !LastError )
        LastError = 1287;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 156, &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids, LastError);
      }
      v38 = 0;
      v39 = 0;
      v40 = LastError;
      v41 = -1;
      v42 = 3448;
      throw (EvtException *)&v38;
    }
    v55[0] = 0;
    v57 = v55;
    v58 = 1;
    if ( (a4 & 0x100) != 0 )
    {
      memset_0(Name, 0, 0xACu);
      v23 = LCIDToLocaleName(a3, Name, 85, 0x8000000u);
      if ( !v23 )
      {
        v24 = GetLastError();
        v25 = v24;
        v26 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_DD(*((_QWORD *)WPP_GLOBAL_Control + 2), 157, &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids, a3, v24);
          v26 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( !v25 )
          v25 = 1287;
        if ( v26 != &WPP_GLOBAL_Control && (*((_BYTE *)v26 + 28) & 8) != 0 && *((_BYTE *)v26 + 25) >= 2u )
          WPP_SF_d(v26[2], 158, &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids, v25);
        v38 = 0;
        v39 = 0;
        v40 = v25;
        v41 = -1;
        v42 = 3466;
        throw (EvtException *)&v38;
      }
      if ( (unsigned __int64)v23 >= 0x56 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 159, &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids, 111);
        }
        v38 = 0;
        v39 = 0;
        v40 = 111;
        v41 = -1;
        v42 = 3471;
        throw (EvtException *)&v38;
      }
      if ( (unsigned __int64)(2LL * v23) >= 0xAC )
        _report_rangecheckfailure();
      Name[v23] = 0;
      *(_DWORD *)Buffer = 0;
      if ( !(unsigned int)SetThreadPreferredUILanguages2(8, Name, Buffer, v55) )
      {
        v27 = GetLastError();
        if ( !v27 )
          v27 = 1287;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 160, &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids, v27);
        }
        v38 = 0;
        v39 = 0;
        v40 = v27;
        v41 = -1;
        v42 = 3480;
        throw (EvtException *)&v38;
      }
      if ( *(_DWORD *)Buffer != 1 )
      {
        v28 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_dDS(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              161,
              (unsigned int)&WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids,
              *(_DWORD *)Buffer,
              a3,
              (__int64)Name);
            v28 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( v28 != &WPP_GLOBAL_Control && (*((_BYTE *)v28 + 28) & 8) != 0 && *((_BYTE *)v28 + 25) >= 2u )
            WPP_SF_d(v28[2], 162, &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids, 87);
        }
        v38 = 0;
        v39 = 0;
        v40 = 87;
        v41 = -1;
        v42 = 3486;
        throw (EvtException *)&v38;
      }
      v29 = 0;
    }
    else
    {
      v29 = a3;
    }
    *(_QWORD *)Buffer = 0;
    if ( FormatMessageW(0xBFFu, Library, dwMessageId, v29, Buffer, 0, 0) )
    {
      std::wstring::_Append<wchar_t>(Src);
      HresultOrFail = 0;
    }
    else
    {
      v31 = GetLastError();
      HresultOrFail = tlx::_LastHresultOrFail((tlx *)v31, v32);
    }
    utl::unique_ptr<EVENT_DECODE_DESCRIPTOR [0],utl::default_delete<EVENT_DECODE_DESCRIPTOR [0]>>::~unique_ptr<EVENT_DECODE_DESCRIPTOR [0],utl::default_delete<EVENT_DECODE_DESCRIPTOR [0]>>(Buffer);
    if ( HresultOrFail < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          163,
          &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids,
          (unsigned int)HresultOrFail);
      }
      *(_QWORD *)&v38 = &byte_1800EC961;
      *((_QWORD *)&v38 + 1) = 0;
      v39 = 0;
      v40 = HresultOrFail;
      v41 = -1;
      v42 = -1;
      v43 = 0;
      throw (EvtException *)&v38;
    }
    if ( v62 )
    {
      v33 = Src;
      if ( v63 > 7 )
        v33 = (void **)Src[0];
      if ( *((_WORD *)v33 + v62 - 1) == 32 )
      {
        v34 = --v62;
        v35 = Src;
        if ( v63 > 7 )
          v35 = (void **)Src[0];
        *((_WORD *)v35 + v34) = 0;
      }
    }
    tlx::_UndoSolo__EventService::GetClassicLogDisplayName_::_25_::_lambda_2___::__UndoSolo__EventService::GetClassicLogDisplayName_::_25_::_lambda_2___(&v57);
    tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),0>>::~unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),0>>(v56);
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&pExceptionObject);
  }
  v36 = (wchar_t *)operator new(saturated_mul(v62 + 1, 2u));
  *a5 = v36;
  v37 = Src;
  if ( v63 > 7 )
    v37 = (void **)Src[0];
  memcpy_0(v36, v37, 2 * v62 + 2);
  std::wstring::~wstring(Src);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpSrc);
  tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpSubKey);
  RpcRevertToSelf();
}

```

## disassembly

```asm
0x1800a25f0  mov     [rsp-8+arg_0], rbx
0x1800a25f5  push    rbp
0x1800a25f6  push    rsi
0x1800a25f7  push    rdi
0x1800a25f8  push    r12
0x1800a25fa  push    r13
0x1800a25fc  push    r14
0x1800a25fe  push    r15
0x1800a2600  lea     rbp, [rsp-100h]
0x1800a2608  sub     rsp, 200h
0x1800a260f  mov     rax, cs:__security_cookie
0x1800a2616  xor     rax, rsp
0x1800a2619  mov     [rbp+130h+var_40], rax
0x1800a2620  mov     r14d, r9d
0x1800a2623  mov     esi, r8d
0x1800a2626  mov     rbx, rdx
0x1800a2629  mov     r15, [rbp+130h+arg_20]
0x1800a2630  or      r13, 0FFFFFFFFFFFFFFFFh
0x1800a2634  mov     rax, r13
0x1800a2637  xor     r12d, r12d
0x1800a263a  inc     rax
0x1800a263d  cmp     [rdx+rax*2], r12w
0x1800a2642  jnz     short loc_1800A263A
0x1800a2644  mov     [rbp+130h+var_170], rbx
0x1800a2648  mov     [rbp+130h+var_168], rax
0x1800a264c  mov     edx, 3A98h
0x1800a2651  lea     rcx, [rbp+130h+var_170]
0x1800a2655  call    ScanForInvalidChars
0x1800a265a  mov     edi, eax
0x1800a265c  test    eax, eax
0x1800a265e  jz      short loc_1800A26D0
0x1800a2660  lea     rbx, WPP_GLOBAL_Control
0x1800a2667  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a266e  cmp     rcx, rbx
0x1800a2671  jz      short loc_1800A2697
0x1800a2673  test    byte ptr [rcx+1Ch], 8
0x1800a2677  jz      short loc_1800A2697
0x1800a2679  cmp     byte ptr [rcx+19h], 2
0x1800a267d  jb      short loc_1800A2697
0x1800a267f  mov     edx, 96h
0x1800a2684  mov     r9d, eax
0x1800a2687  lea     r8, WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids
0x1800a268e  mov     rcx, [rcx+10h]
0x1800a2692  call    WPP_SF_d
0x1800a2697  lea     rax, byte_1800EC961
0x1800a269e  mov     [rsp+230h+pExceptionObject], rax
0x1800a26a3  mov     [rsp+230h+var_1B8], r12
0x1800a26a8  mov     [rbp+130h+var_1B0], r12
0x1800a26ac  mov     [rbp+130h+var_1A8], edi
0x1800a26af  mov     [rbp+130h+var_1A4], 0FFFFFFFFh
0x1800a26b6  mov     [rbp+130h+var_1A0], r13d
0x1800a26ba  mov     [rbp+130h+var_19C], r12b
0x1800a26be  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800a26c5  lea     rcx, [rsp+230h+pExceptionObject]; pExceptionObject
0x1800a26ca  call    _CxxThrowException_0
0x1800a26d0  xor     ecx, ecx; BindingHandle
0x1800a26d2  call    cs:__imp_RpcImpersonateClient
0x1800a26d8  mov     edi, eax
0x1800a26da  test    eax, eax
0x1800a26dc  jz      short loc_1800A274E
0x1800a26de  lea     rbx, WPP_GLOBAL_Control
0x1800a26e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a26ec  cmp     rcx, rbx
0x1800a26ef  jz      short loc_1800A2715
0x1800a26f1  test    byte ptr [rcx+1Ch], 8
0x1800a26f5  jz      short loc_1800A2715
0x1800a26f7  cmp     byte ptr [rcx+19h], 2
0x1800a26fb  jb      short loc_1800A2715
0x1800a26fd  mov     edx, 97h
0x1800a2702  mov     r9d, eax
0x1800a2705  lea     r8, WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids
0x1800a270c  mov     rcx, [rcx+10h]
0x1800a2710  call    WPP_SF_d
0x1800a2715  lea     rax, byte_1800EC961
0x1800a271c  mov     [rsp+230h+pExceptionObject], rax
0x1800a2721  mov     [rsp+230h+var_1B8], r12
0x1800a2726  mov     [rbp+130h+var_1B0], r12
0x1800a272a  mov     [rbp+130h+var_1A8], edi
0x1800a272d  mov     [rbp+130h+var_1A4], 0FFFFFFFFh
0x1800a2734  mov     [rbp+130h+var_1A0], r13d
0x1800a2738  mov     [rbp+130h+var_19C], r12b
0x1800a273c  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800a2743  lea     rcx, [rsp+230h+pExceptionObject]; pExceptionObject
0x1800a2748  call    _CxxThrowException_0
0x1800a274e  mov     [rbp+130h+var_187], 1
0x1800a2752  lea     rcx, [rbp+130h+lpSubKey]; void *
0x1800a2756  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800a275b  nop
0x1800a275c  mov     r8d, 2Ah ; '*'
0x1800a2762  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Ev"...
0x1800a2769  lea     rcx, [rbp+130h+lpSubKey]
0x1800a276d  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x1800a2772  test    al, al
0x1800a2774  jz      loc_1800A2F1A
0x1800a277a  mov     edx, 5Ch ; '\'
0x1800a277f  lea     rcx, [rbp+130h+lpSubKey]
0x1800a2783  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x1800a2788  test    al, al
0x1800a278a  jz      loc_1800A2F1A
0x1800a2790  mov     rdx, rbx
0x1800a2793  lea     rcx, [rbp+130h+lpSubKey]
0x1800a2797  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *)
0x1800a279c  test    al, al
0x1800a279e  jz      loc_1800A2F1A
0x1800a27a4  mov     [rbp+130h+hKey], r12
0x1800a27a8  lea     rcx, [rbp+130h+hKey]
0x1800a27ac  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x1800a27b1  mov     [rsp+230h+phkResult], rax; phkResult
0x1800a27b6  mov     r9d, 1; samDesired
0x1800a27bc  xor     r8d, r8d; ulOptions
0x1800a27bf  mov     rdx, [rbp+130h+lpSubKey]; lpSubKey
0x1800a27c3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800a27ca  call    cs:__imp_RegOpenKeyExW
0x1800a27d0  mov     edi, eax
0x1800a27d2  test    eax, eax
0x1800a27d4  jz      short loc_1800A2846
0x1800a27d6  lea     rbx, WPP_GLOBAL_Control
0x1800a27dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a27e4  cmp     rcx, rbx
0x1800a27e7  jz      short loc_1800A280D
0x1800a27e9  test    byte ptr [rcx+1Ch], 8
0x1800a27ed  jz      short loc_1800A280D
0x1800a27ef  cmp     byte ptr [rcx+19h], 2
0x1800a27f3  jb      short loc_1800A280D
0x1800a27f5  mov     edx, 99h
0x1800a27fa  mov     r9d, eax
0x1800a27fd  lea     r8, WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids
0x1800a2804  mov     rcx, [rcx+10h]
0x1800a2808  call    WPP_SF_d
0x1800a280d  lea     rax, byte_1800EC961
0x1800a2814  mov     [rsp+230h+pExceptionObject], rax
0x1800a2819  mov     [rsp+230h+var_1B8], r12
0x1800a281e  mov     [rbp+130h+var_1B0], r12
0x1800a2822  mov     [rbp+130h+var_1A8], edi
0x1800a2825  mov     [rbp+130h+var_1A4], 0FFFFFFFFh
0x1800a282c  mov     [rbp+130h+var_1A0], r13d
0x1800a2830  mov     [rbp+130h+var_19C], r12b
0x1800a2834  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800a283b  lea     rcx, [rsp+230h+pExceptionObject]; pExceptionObject
0x1800a2840  call    _CxxThrowException_0
0x1800a2846  mov     [rbp+130h+dwMessageId], r12d
0x1800a284a  lea     rcx, [rbp+130h+lpSrc]; void *
0x1800a284e  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800a2853  nop
0x1800a2854  lea     r9, [rbp+130h+dwMessageId]; unsigned int *
0x1800a2858  lea     r8, aDisplaynameid; "DisplayNameID"
0x1800a285f  xor     edx, edx; wchar_t *
0x1800a2861  mov     rcx, [rbp+130h+hKey]; HKEY
0x1800a2865  call    ?RegReadDWORDValueNoThrow@@YAJPEAUHKEY__@@PEB_W1AEAK@Z; RegReadDWORDValueNoThrow(HKEY__ *,wchar_t const *,wchar_t const *,ulong &)
0x1800a286a  mov     edi, eax
0x1800a286c  lea     r9, [rbp+130h+lpSrc]
0x1800a2870  lea     r8, aDisplaynamefil; "DisplayNameFile"
0x1800a2877  xor     edx, edx
0x1800a2879  mov     rcx, [rbp+130h+hKey]; hKey
0x1800a287d  call    ?RegReadStringValueNoThrow@@YAJPEAUHKEY__@@PEB_W1AEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; RegReadStringValueNoThrow(HKEY__ *,wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x1800a2882  xorps   xmm0, xmm0
0x1800a2885  movups  xmmword ptr [rbp+130h+Src], xmm0
0x1800a2889  mov     [rbp+130h+var_100], r12
0x1800a288d  mov     [rbp+130h+var_F8], 7
0x1800a2895  mov     word ptr [rbp+130h+Src], r12w
0x1800a289a  test    eax, eax
0x1800a289c  jz      loc_1800A2934
0x1800a28a2  test    edi, edi
0x1800a28a4  jz      short loc_1800A28C4
0x1800a28a6  mov     r8, r13
0x1800a28a9  inc     r8
0x1800a28ac  cmp     [rbx+r8*2], r12w
0x1800a28b1  jnz     short loc_1800A28A9
0x1800a28b3  mov     rdx, rbx
0x1800a28b6  lea     rcx, [rbp+130h+Src]
0x1800a28ba  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x1800a28bf  jmp     loc_1800A2E81
0x1800a28c4  lea     rbx, WPP_GLOBAL_Control
0x1800a28cb  mov     edi, 0Dh
0x1800a28d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a28d7  cmp     rcx, rbx
0x1800a28da  jz      short loc_1800A2900
0x1800a28dc  test    byte ptr [rcx+1Ch], 8
0x1800a28e0  jz      short loc_1800A2900
0x1800a28e2  cmp     byte ptr [rcx+19h], 2
0x1800a28e6  jb      short loc_1800A2900
0x1800a28e8  mov     edx, 9Ah
0x1800a28ed  mov     r9d, edi
0x1800a28f0  lea     r8, WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids
0x1800a28f7  mov     rcx, [rcx+10h]
0x1800a28fb  call    WPP_SF_d
0x1800a2900  xorps   xmm0, xmm0
0x1800a2903  movdqu  [rsp+230h+var_1F0], xmm0
0x1800a2909  mov     [rsp+230h+var_1E0], r12
0x1800a290e  mov     [rsp+230h+var_1D8], edi
0x1800a2912  mov     [rsp+230h+var_1D4], 0FFFFFFFFh
0x1800a291a  mov     [rsp+230h+var_1D0], 0D6Bh
0x1800a2922  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800a2929  lea     rcx, [rsp+230h+var_1F0]; pExceptionObject
0x1800a292e  call    _CxxThrowException_0
0x1800a2934  lea     rcx, [rsp+230h+pExceptionObject]; void *
0x1800a2939  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800a293e  nop
0x1800a293f  lea     rdx, [rsp+230h+pExceptionObject]
0x1800a2944  mov     rcx, [rbp+130h+lpSrc]; lpSrc
0x1800a2948  call    ?ExpandEnvStringNoThrow@@YAKPEB_WAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; ExpandEnvStringNoThrow(wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x1800a294d  mov     edi, eax
0x1800a294f  test    eax, eax
0x1800a2951  jz      short loc_1800A29C8
0x1800a2953  lea     rbx, WPP_GLOBAL_Control
0x1800a295a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a2961  cmp     rcx, rbx
0x1800a2964  jz      short loc_1800A298A
0x1800a2966  test    byte ptr [rcx+1Ch], 8
0x1800a296a  jz      short loc_1800A298A
0x1800a296c  cmp     byte ptr [rcx+19h], 2
0x1800a2970  jb      short loc_1800A298A
0x1800a2972  mov     edx, 9Bh
0x1800a2977  mov     r9d, eax
0x1800a297a  lea     r8, WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids
0x1800a2981  mov     rcx, [rcx+10h]
0x1800a2985  call    WPP_SF_d
0x1800a298a  lea     rax, byte_1800EC961
0x1800a2991  mov     qword ptr [rsp+230h+var_1F0], rax
0x1800a2996  mov     qword ptr [rsp+230h+var_1F0+8], r12
0x1800a299b  mov     [rsp+230h+var_1E0], r12
0x1800a29a0  mov     [rsp+230h+var_1D8], edi
0x1800a29a4  mov     [rsp+230h+var_1D4], 0FFFFFFFFh
0x1800a29ac  mov     [rsp+230h+var_1D0], r13d
0x1800a29b1  mov     [rsp+230h+var_1CC], r12b
0x1800a29b6  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800a29bd  lea     rcx, [rsp+230h+var_1F0]; pExceptionObject
0x1800a29c2  call    _CxxThrowException_0
0x1800a29c8  xor     edx, edx; hFile
0x1800a29ca  lea     r8d, [rdx+20h]; dwFlags
0x1800a29ce  mov     rcx, [rsp+230h+pExceptionObject]; lpLibFileName
0x1800a29d3  call    cs:__imp_LoadLibraryExW
0x1800a29d9  mov     rbx, rax
0x1800a29dc  mov     [rbp+130h+var_170], rax
0x1800a29e0  test    rax, rax
0x1800a29e3  jnz     short loc_1800A2A62
0x1800a29e5  call    cs:__imp_GetLastError
0x1800a29eb  mov     edi, eax
0x1800a29ed  mov     eax, 507h
0x1800a29f2  test    edi, edi
0x1800a29f4  cmovz   edi, eax
0x1800a29f7  lea     rbx, WPP_GLOBAL_Control
0x1800a29fe  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a2a05  cmp     rcx, rbx
0x1800a2a08  jz      short loc_1800A2A2E
0x1800a2a0a  test    byte ptr [rcx+1Ch], 8
0x1800a2a0e  jz      short loc_1800A2A2E
0x1800a2a10  cmp     byte ptr [rcx+19h], 2
0x1800a2a14  jb      short loc_1800A2A2E
0x1800a2a16  mov     edx, 9Ch
0x1800a2a1b  mov     r9d, edi
0x1800a2a1e  lea     r8, WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids
0x1800a2a25  mov     rcx, [rcx+10h]
0x1800a2a29  call    WPP_SF_d
0x1800a2a2e  xorps   xmm0, xmm0
0x1800a2a31  movdqu  [rsp+230h+var_1F0], xmm0
0x1800a2a37  mov     [rsp+230h+var_1E0], r12
0x1800a2a3c  mov     [rsp+230h+var_1D8], edi
0x1800a2a40  mov     [rsp+230h+var_1D4], 0FFFFFFFFh
0x1800a2a48  mov     [rsp+230h+var_1D0], 0D78h
0x1800a2a50  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800a2a57  lea     rcx, [rsp+230h+var_1F0]; pExceptionObject
0x1800a2a5c  call    _CxxThrowException_0
0x1800a2a62  mov     [rbp+130h+var_180], r12
0x1800a2a66  lea     rax, [rbp+130h+var_180]
0x1800a2a6a  mov     [rbp+130h+var_160], rax
0x1800a2a6e  mov     [rbp+130h+var_158], 1
0x1800a2a72  bt      r14d, 8
0x1800a2a77  jnb     loc_1800A2D48
0x1800a2a7d  mov     edi, 0ACh
0x1800a2a82  mov     r8d, edi; Size
0x1800a2a85  xor     edx, edx; Val
0x1800a2a87  lea     rcx, [rbp+130h+Name]; void *
0x1800a2a8b  call    memset_0
0x1800a2a90  mov     r9d, 8000000h; dwFlags
0x1800a2a96  lea     r8d, [rdi-57h]; cchName
0x1800a2a9a  lea     rdx, [rbp+130h+Name]; lpName
0x1800a2a9e  mov     ecx, esi; Locale
0x1800a2aa0  call    cs:__imp_LCIDToLocaleName
0x1800a2aa6  test    eax, eax
0x1800a2aa8  jnz     loc_1800A2B5F
0x1800a2aae  call    cs:__imp_GetLastError
0x1800a2ab4  mov     edi, eax
0x1800a2ab6  lea     rbx, WPP_GLOBAL_Control
0x1800a2abd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a2ac4  cmp     rcx, rbx
0x1800a2ac7  jz      short loc_1800A2AF8
0x1800a2ac9  test    byte ptr [rcx+1Ch], 8
0x1800a2acd  jz      short loc_1800A2AF8
0x1800a2acf  cmp     byte ptr [rcx+19h], 2
0x1800a2ad3  jb      short loc_1800A2AF8
0x1800a2ad5  mov     edx, 9Dh
0x1800a2ada  mov     dword ptr [rsp+230h+phkResult], eax
0x1800a2ade  mov     r9d, esi
0x1800a2ae1  lea     r8, WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids
0x1800a2ae8  mov     rcx, [rcx+10h]
0x1800a2aec  call    WPP_SF_DD
0x1800a2af1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a2af8  mov     eax, 507h
0x1800a2afd  test    edi, edi
  ... truncated ...
```
