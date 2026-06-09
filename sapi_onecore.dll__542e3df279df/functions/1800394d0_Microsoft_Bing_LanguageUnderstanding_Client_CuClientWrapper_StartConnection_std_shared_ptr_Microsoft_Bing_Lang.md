# Microsoft::Bing::LanguageUnderstanding::Client::CuClientWrapper::StartConnection(std::shared_ptr<Microsoft::Bing::LanguageUnderstanding::Client::CuInputSapiInternal> const &)

- ea: `0x1800394d0`
- end: `0x180039a8b`
- name: `?StartConnection@CuClientWrapper@Client@LanguageUnderstanding@Bing@Microsoft@@AEAAJAEBV?$shared_ptr@VCuInputSapiInternal@Client@LanguageUnderstanding@Bing@Microsoft@@@std@@@Z`
- size: `1467`
- prototype: `__int64 __fastcall(Microsoft::Bing::LanguageUnderstanding::Client::CuClientWrapper *this)`
- caller_count: `1`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x18005eba4`

## callees

- `0x180026508`
- `0x18002895c`
- `0x18002d404`
- `0x18002e550`
- `0x18002e6d4`
- `0x180034084`
- `0x1800358ec`
- `0x180038d18`
- `0x1800394d0`
- `0x180039c98`
- `0x18003b510`
- `0x18004b1a8`
- `0x18005398c`
- `0x180057e28`
- `0x18006ba20`
- `0x1801c0b14`
- `0x1801c1a08`
- `0x1801c1c78`
- `0x1801c2234`
- `0x1801c23b8`
- `0x1801c23e8`
- `0x1801c2418`
- `0x1801c2448`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800394f8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180039523`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003955a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180039635`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180039800`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800398db`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800394f8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180039523`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003955a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180039635`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180039800`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800398db`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003953c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180039570`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180039628`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180039819`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180039889`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180039a27`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003953c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180039570`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180039628`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180039819`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180039889`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180039a27`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x1800395b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x1800395b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039584`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039603`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039615`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039584`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039603`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039615`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800395c8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800395da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800395c8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800395da`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Microsoft::Bing::LanguageUnderstanding::Client::CuClientWrapper::StartConnection(
        Microsoft::Bing::LanguageUnderstanding::Client::CuClientWrapper *this,
        __int64 *a2)
{
  __int64 v4; // rbx
  __int128 v5; // xmm6
  __int64 v6; // rbx
  __int128 v7; // xmm6
  __int64 v8; // rbx
  const unsigned __int16 *StringRawBuffer; // rbx
  const unsigned __int16 *v10; // rax
  HSTRING v11; // rbx
  __int64 v12; // rax
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rdx
  std::_Ref_count_base *v16; // rax
  GUID v17; // xmm0
  int v18; // ecx
  struct Halsey::HalseyUtil *v19; // rax
  _BYTE *v20; // r14
  char v21; // r15
  const unsigned __int16 *v22; // rax
  __int64 v23; // r9
  const unsigned __int16 *v24; // rax
  __int64 v25; // r9
  const unsigned __int16 *v26; // rax
  __int64 v27; // r9
  __int64 v28; // rax
  __int64 v29; // rdx
  const unsigned __int16 *v30; // rax
  Halsey::swstring *v31; // r9
  Halsey::swstring *v32; // r9
  const unsigned __int16 *v33; // rax
  const unsigned __int16 *v34; // r8
  __int64 v35; // rcx
  __int64 v36; // rax
  __int64 v37; // rdx
  std::_Ref_count_base *v38; // rcx
  __int64 v39; // rcx
  __int64 v40; // rax
  __int64 v41; // rdx
  std::_Ref_count_base *v42; // rcx
  __int64 v43; // rcx
  __int64 v44; // rax
  __int64 v45; // rdx
  std::_Ref_count_base *v46; // rcx
  const unsigned __int16 *v47; // rax
  __int64 v48; // r14
  __int64 v49; // r8
  const unsigned __int16 *v50; // rax
  int CuClient; // eax
  unsigned int v52; // ebx
  const char *v53; // r9
  __int64 v54; // rax
  int v55[2]; // [rsp+20h] [rbp-48h] BYREF
  std::_Ref_count_base *v56; // [rsp+28h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  char *result; // [rsp+70h] [rbp+8h] BYREF
  HSTRING string2; // [rsp+78h] [rbp+10h] BYREF
  char *v60; // [rsp+80h] [rbp+18h]

  SpPerfTelemetry::CuClientWrapper_StartConnection_Enter();
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
  v60 = (char *)this + 104;
  SpPerfTelemetry::CuClientWrapper_StartConnection_GetIdentityPropertyValue();
  v4 = *((_QWORD *)this + 69);
  v5 = *(_OWORD *)(*a2 + 200);
  EnterCriticalSection((LPCRITICAL_SECTION)(v4 + 24));
  *(_OWORD *)(v4 + 172) = v5;
  if ( v4 != -24 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(v4 + 24));
  v6 = *((_QWORD *)this + 69);
  v7 = *(_OWORD *)(*a2 + 216);
  EnterCriticalSection((LPCRITICAL_SECTION)(v6 + 24));
  *(_OWORD *)(v6 + 156) = v7;
  if ( v6 != -24 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(v6 + 24));
  string2 = 0;
  v8 = *((_QWORD *)this + 69);
  WindowsDeleteString(0);
  string2 = 0;
  try
  {
    Microsoft::Bing::LanguageUnderstanding::Client::Authentication::UserAuthentication::GetIdentityPropertyValue(
      v8,
      0,
      &string2);
    LODWORD(result) = 0;
    WindowsCompareStringOrdinal(*((HSTRING *)this + 68), string2, (INT32 *)&result);
    if ( (_DWORD)result )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(string2, 0);
      v10 = WindowsGetStringRawBuffer(*((HSTRING *)this + 68), 0);
      Windows::Media::Speech::Internal::RemoteNaturalLanguageTelemetry::CuClientSession::CuClientMsaTokenChange(
        (Microsoft::Bing::LanguageUnderstanding::Client::CuClientWrapper *)((char *)this + 200),
        v10,
        StringRawBuffer);
      v11 = string2;
      string2 = 0;
      WindowsDeleteString(*((HSTRING *)this + 68));
      *((_QWORD *)this + 68) = v11;
    }
    WindowsDeleteString(string2);
    string2 = 0;
    if ( this != (Microsoft::Bing::LanguageUnderstanding::Client::CuClientWrapper *)-104LL )
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
    result = (char *)this + 64;
    v12 = *(_QWORD *)(*a2 + 328);
    v13 = (_QWORD *)((char *)this + 408);
    if ( v12 )
    {
      v14 = *(_QWORD *)(v12 + 264);
      if ( v14 )
        _InterlockedIncrement((volatile signed __int32 *)(v14 + 8));
      v15 = *(_QWORD *)(v12 + 264);
      *v13 = *(_QWORD *)(v12 + 256);
      v16 = (std::_Ref_count_base *)*((_QWORD *)this + 52);
      *((_QWORD *)this + 52) = v15;
      if ( v16 )
        std::_Ref_count_base::_Decref(v16);
      v17 = *(GUID *)(*(_QWORD *)(*a2 + 328) + 272LL);
    }
    else
    {
      Halsey::swstring::operator=(v13, &cchOriginalDestLength);
      v17 = GUID_NULL;
    }
    *(GUID *)((char *)this + 520) = v17;
    *((_DWORD *)this + 134) = 2;
    v18 = 2;
    if ( *(_BYTE *)(*a2 + 384) )
    {
      v18 = 6;
      *((_DWORD *)this + 134) = 6;
    }
    if ( *(_DWORD *)(*a2 + 360) == 2 )
    {
      v18 |= 1u;
      *((_DWORD *)this + 134) = v18;
    }
    if ( *(_BYTE *)(*a2 + 407) )
    {
      v18 |= 8u;
      *((_DWORD *)this + 134) = v18;
    }
    if ( *(_DWORD *)(*a2 + 396) == 0x4000 )
      *((_DWORD *)this + 134) = v18 | 0x10;
    v19 = Halsey::HalseyUtil::Instance();
    Halsey::HalseyUtil::GetApplicationId(v19, *((unsigned int *)this + 134), (char *)this + 424);
    v20 = (char *)this + 584;
    if ( *((_QWORD *)this + 24) )
    {
      if ( *v20
        || (v22 = Halsey::swstring::c_str((Halsey::swstring *)(*a2 + 408)),
            (unsigned int)Halsey::swstring::compare(
                            (Microsoft::Bing::LanguageUnderstanding::Client::CuClientWrapper *)((char *)this + 360),
                            v22))
        || (v24 = Halsey::swstring::c_str((Halsey::swstring *)(v23 + 424)),
            (unsigned int)Halsey::swstring::compare(
                            (Microsoft::Bing::LanguageUnderstanding::Client::CuClientWrapper *)((char *)this + 376),
                            v24))
        || (v26 = Halsey::swstring::c_str((Halsey::swstring *)(v25 + 440)),
            (unsigned int)Halsey::swstring::compare(
                            (Microsoft::Bing::LanguageUnderstanding::Client::CuClientWrapper *)((char *)this + 392),
                            v26))
        || *((_BYTE *)this + 352) != *(_BYTE *)(v27 + 472)
        || ((v28 = *(_QWORD *)(v27 + 560)) == 0 ? (v29 = 0) : (v29 = *(_QWORD *)(v28 + 16)),
            v21 = 0,
            *((_BYTE *)this + 585) != (v29 != 0)) )
      {
        v21 = 1;
      }
      EnterCriticalSection(&CriticalSection);
      std::shared_ptr<Bing::Speech::IConnection>::reset(&qword_1803B8D40);
      LeaveCriticalSection(&CriticalSection);
      Microsoft::Bing::LanguageUnderstanding::Client::GetClientID(v55);
      v30 = Halsey::swstring::c_str((Halsey::swstring *)v55);
      if ( (unsigned int)Halsey::swstring::compare(v31, v30) )
      {
        Halsey::swstring::c_strsafe((Halsey::swstring *)v55);
        v33 = Halsey::swstring::c_strsafe(v32);
        Windows::Media::Speech::Internal::RemoteNaturalLanguageTelemetry::CuClientSession::CuClientUserIdChange(
          (Microsoft::Bing::LanguageUnderstanding::Client::CuClientWrapper *)((char *)this + 200),
          v33,
          v34);
        v21 = 1;
      }
      if ( v56 )
        std::_Ref_count_base::_Decref(v56);
    }
    else
    {
      v21 = 0;
    }
    if ( this != (Microsoft::Bing::LanguageUnderstanding::Client::CuClientWrapper *)-64LL )
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
    if ( v21 )
    {
      Microsoft::Bing::LanguageUnderstanding::Client::CuClientWrapper::ResetCuClient(this);
      *v20 = 0;
      v56 = 0;
      v55[1] = -2147200256;
      LOBYTE(v55[0]) = 0;
      Microsoft::Bing::LanguageUnderstanding::Client::CuClientWrapper::OnEvent(
        this,
        (const struct Bing::Speech::ConnectionStatus *)v55);
      std::unique_ptr<Bing::Speech::Cookies>::~unique_ptr<Bing::Speech::Cookies>(&v56);
    }
    if ( *((_QWORD *)this + 24) )
      goto LABEL_66;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
    result = (char *)this + 64;
    v35 = *a2;
    v36 = *(_QWORD *)(*a2 + 416);
    if ( v36 )
      _InterlockedIncrement((volatile signed __int32 *)(v36 + 8));
    v37 = *(_QWORD *)(v35 + 416);
    *((_QWORD *)this + 45) = *(_QWORD *)(v35 + 408);
    v38 = (std::_Ref_count_base *)*((_QWORD *)this + 46);
    *((_QWORD *)this + 46) = v37;
    if ( v38 )
      std::_Ref_count_base::_Decref(v38);
    v39 = *a2;
    v40 = *(_QWORD *)(*a2 + 432);
    if ( v40 )
      _InterlockedIncrement((volatile signed __int32 *)(v40 + 8));
    v41 = *(_QWORD *)(v39 + 432);
    *((_QWORD *)this + 47) = *(_QWORD *)(v39 + 424);
    v42 = (std::_Ref_count_base *)*((_QWORD *)this + 48);
    *((_QWORD *)this + 48) = v41;
    if ( v42 )
      std::_Ref_count_base::_Decref(v42);
    v43 = *a2;
    v44 = *(_QWORD *)(*a2 + 448);
    if ( v44 )
      _InterlockedIncrement((volatile signed __int32 *)(v44 + 8));
    v45 = *(_QWORD *)(v43 + 448);
    *((_QWORD *)this + 49) = *(_QWORD *)(v43 + 440);
    v46 = (std::_Ref_count_base *)*((_QWORD *)this + 50);
    *((_QWORD *)this + 50) = v45;
    if ( v46 )
      std::_Ref_count_base::_Decref(v46);
    *((_BYTE *)this + 352) = *(_BYTE *)(*a2 + 472);
    v47 = Halsey::swstring::c_strsafe((Halsey::swstring *)(*a2 + 560));
    v48 = -1;
    v49 = -1;
    do
      ++v49;
    while ( v47[v49] );
    std::wstring::_Assign<unsigned short>((char *)this + 456, v47, v49);
    v50 = Halsey::swstring::c_strsafe((Halsey::swstring *)(*a2 + 576));
    do
      ++v48;
    while ( v50[v48] );
    std::wstring::_Assign<unsigned short>((char *)this + 488, v50, v48);
    *((_BYTE *)this + 585) = *((_QWORD *)this + 59) != 0;
    if ( this != (Microsoft::Bing::LanguageUnderstanding::Client::CuClientWrapper *)-64LL )
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
    SpPerfTelemetry::CuClientWrapper_StartConnection_CreateConversationController();
    CuClient = Microsoft::Bing::LanguageUnderstanding::Client::CuClientWrapper::CreateCuClient(
                 this,
                 *((_BYTE *)this + 585));
    v52 = CuClient;
    if ( CuClient >= 0 )
    {
LABEL_66:
      SpPerfTelemetry::CuClientWrapper_StartConnection_Exit();
      v54 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1CD,
        (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\rnl\\src\\cuclientwrapper.cpp",
        (const char *)(unsigned int)CuClient,
        v55[0]);
      v54 = v52;
    }
  }
  catch ( ... )
  {
    LODWORD(result) = wil::details::in1diag3::Return_CaughtException(
                        retaddr,
                        (void *)0x1D4,
                        (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\rnl\\src\\cuclientwrapper.cpp",
                        v53);
    return (unsigned int)result;
  }
  return v54;
}

```

## disassembly

```asm
0x1800394d0  mov     [rsp+arg_18], rbx
0x1800394d5  push    rsi
0x1800394d6  push    rdi
0x1800394d7  push    r12
0x1800394d9  push    r14
0x1800394db  push    r15
0x1800394dd  sub     rsp, 40h
0x1800394e1  movaps  [rsp+68h+var_38], xmm6
0x1800394e6  mov     rsi, rdx
0x1800394e9  mov     rdi, rcx
0x1800394ec  call    ?CuClientWrapper_StartConnection_Enter@SpPerfTelemetry@@SAXXZ; SpPerfTelemetry::CuClientWrapper_StartConnection_Enter(void)
0x1800394f1  lea     r14, [rdi+68h]
0x1800394f5  mov     rcx, r14; lpCriticalSection
0x1800394f8  call    cs:__imp_EnterCriticalSection
0x1800394fe  mov     [rsp+68h+arg_10], r14
0x180039506  call    ?CuClientWrapper_StartConnection_GetIdentityPropertyValue@SpPerfTelemetry@@SAXXZ; SpPerfTelemetry::CuClientWrapper_StartConnection_GetIdentityPropertyValue(void)
0x18003950b  mov     rbx, [rdi+228h]
0x180039512  mov     rax, [rsi]
0x180039515  movups  xmm6, xmmword ptr [rax+0C8h]
0x18003951c  lea     r15, [rbx+18h]
0x180039520  mov     rcx, r15; lpCriticalSection
0x180039523  call    cs:__imp_EnterCriticalSection
0x180039529  movdqu  xmmword ptr [rbx+0ACh], xmm6
0x180039531  xor     r12d, r12d
0x180039534  test    r15, r15
0x180039537  jz      short loc_180039542
0x180039539  mov     rcx, r15; lpCriticalSection
0x18003953c  call    cs:__imp_LeaveCriticalSection
0x180039542  mov     rbx, [rdi+228h]
0x180039549  mov     rax, [rsi]
0x18003954c  movups  xmm6, xmmword ptr [rax+0D8h]
0x180039553  lea     r15, [rbx+18h]
0x180039557  mov     rcx, r15; lpCriticalSection
0x18003955a  call    cs:__imp_EnterCriticalSection
0x180039560  movdqu  xmmword ptr [rbx+9Ch], xmm6
0x180039568  test    r15, r15
0x18003956b  jz      short loc_180039576
0x18003956d  mov     rcx, r15; lpCriticalSection
0x180039570  call    cs:__imp_LeaveCriticalSection
0x180039576  mov     [rsp+68h+string2], r12
0x18003957b  mov     rbx, [rdi+228h]
0x180039582  xor     ecx, ecx; string
0x180039584  call    cs:__imp_WindowsDeleteString
0x18003958a  mov     [rsp+68h+string2], r12
0x18003958f  lea     r8, [rsp+68h+string2]
0x180039594  xor     edx, edx
0x180039596  mov     rcx, rbx
0x180039599  call    ?GetIdentityPropertyValue@UserAuthentication@Authentication@Client@LanguageUnderstanding@Bing@Microsoft@@QEAAJW4IdentityProp@23456@PEAPEAUHSTRING__@@@Z; Microsoft::Bing::LanguageUnderstanding::Client::Authentication::UserAuthentication::GetIdentityPropertyValue(Microsoft::Bing::LanguageUnderstanding::Client::Authentication::IdentityProp,HSTRING__ * *)
0x18003959e  mov     dword ptr [rsp+68h+result], r12d
0x1800395a3  lea     r8, [rsp+68h+result]; result
0x1800395a8  mov     rdx, [rsp+68h+string2]; string2
0x1800395ad  mov     rcx, [rdi+220h]; string1
0x1800395b4  call    cs:__imp_WindowsCompareStringOrdinal
0x1800395ba  cmp     dword ptr [rsp+68h+result], r12d
0x1800395bf  jz      short loc_180039610
0x1800395c1  xor     edx, edx; length
0x1800395c3  mov     rcx, [rsp+68h+string2]; string
0x1800395c8  call    cs:__imp_WindowsGetStringRawBuffer
0x1800395ce  mov     rbx, rax
0x1800395d1  xor     edx, edx; length
0x1800395d3  mov     rcx, [rdi+220h]; string
0x1800395da  call    cs:__imp_WindowsGetStringRawBuffer
0x1800395e0  lea     rcx, [rdi+0C8h]; this
0x1800395e7  mov     r8, rbx; unsigned __int16 *
0x1800395ea  mov     rdx, rax; unsigned __int16 *
0x1800395ed  call    ?CuClientMsaTokenChange@CuClientSession@RemoteNaturalLanguageTelemetry@Internal@Speech@Media@Windows@@QEAAXPEBG0@Z; Windows::Media::Speech::Internal::RemoteNaturalLanguageTelemetry::CuClientSession::CuClientMsaTokenChange(ushort const *,ushort const *)
0x1800395f2  mov     rbx, [rsp+68h+string2]
0x1800395f7  mov     [rsp+68h+string2], r12
0x1800395fc  mov     rcx, [rdi+220h]; string
0x180039603  call    cs:__imp_WindowsDeleteString
0x180039609  mov     [rdi+220h], rbx
0x180039610  mov     rcx, [rsp+68h+string2]; string
0x180039615  call    cs:__imp_WindowsDeleteString
0x18003961b  mov     [rsp+68h+string2], r12
0x180039620  test    r14, r14
0x180039623  jz      short loc_18003962E
0x180039625  mov     rcx, r14; lpCriticalSection
0x180039628  call    cs:__imp_LeaveCriticalSection
0x18003962e  lea     rbx, [rdi+40h]
0x180039632  mov     rcx, rbx; lpCriticalSection
0x180039635  call    cs:__imp_EnterCriticalSection
0x18003963b  mov     [rsp+68h+result], rbx
0x180039640  mov     rax, [rsi]
0x180039643  mov     rax, [rax+148h]
0x18003964a  lea     rcx, [rdi+198h]
0x180039651  test    rax, rax
0x180039654  jz      short loc_18003969F
0x180039656  mov     rdx, [rax+108h]
0x18003965d  test    rdx, rdx
0x180039660  jz      short loc_180039666
0x180039662  lock inc dword ptr [rdx+8]
0x180039666  mov     rdx, [rax+108h]
0x18003966d  mov     rax, [rax+100h]
0x180039674  mov     [rcx], rax
0x180039677  mov     rax, [rcx+8]
0x18003967b  mov     [rcx+8], rdx
0x18003967f  test    rax, rax
0x180039682  jz      short loc_18003968C
0x180039684  mov     rcx, rax; this
0x180039687  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003968c  mov     rax, [rsi]
0x18003968f  mov     rcx, [rax+148h]
0x180039696  movups  xmm0, xmmword ptr [rcx+110h]
0x18003969d  jmp     short loc_1800396B2
0x18003969f  lea     rdx, cchOriginalDestLength
0x1800396a6  call    ??4swstring@Halsey@@QEAAAEBV01@PEBG@Z; Halsey::swstring::operator=(ushort const *)
0x1800396ab  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800396b2  movdqu  xmmword ptr [rdi+208h], xmm0
0x1800396ba  mov     edx, 2
0x1800396bf  mov     [rdi+218h], edx
0x1800396c5  mov     ecx, edx
0x1800396c7  mov     rax, [rsi]
0x1800396ca  cmp     [rax+180h], r12b
0x1800396d1  jz      short loc_1800396DC
0x1800396d3  lea     ecx, [rdx+4]
0x1800396d6  mov     [rdi+218h], ecx
0x1800396dc  mov     rax, [rsi]
0x1800396df  cmp     [rax+168h], edx
0x1800396e5  jnz     short loc_1800396F0
0x1800396e7  or      ecx, 1
0x1800396ea  mov     [rdi+218h], ecx
0x1800396f0  mov     rax, [rsi]
0x1800396f3  cmp     [rax+197h], r12b
0x1800396fa  jz      short loc_180039705
0x1800396fc  or      ecx, 8
0x1800396ff  mov     [rdi+218h], ecx
0x180039705  mov     rax, [rsi]
0x180039708  cmp     dword ptr [rax+18Ch], 4000h
0x180039712  jnz     short loc_18003971D
0x180039714  or      ecx, 10h
0x180039717  mov     [rdi+218h], ecx
0x18003971d  call    ?Instance@HalseyUtil@Halsey@@SAPEAV12@XZ; Halsey::HalseyUtil::Instance(void)
0x180039722  lea     r8, [rdi+1A8h]
0x180039729  mov     edx, [rdi+218h]
0x18003972f  mov     rcx, rax
0x180039732  call    ?GetApplicationId@HalseyUtil@Halsey@@QEAAXIAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Halsey::HalseyUtil::GetApplicationId(uint,std::wstring &)
0x180039737  lea     r14, [rdi+248h]
0x18003973e  cmp     [rdi+0C0h], r12
0x180039745  jnz     short loc_18003974F
0x180039747  mov     r15b, r12b
0x18003974a  jmp     loc_180039881
0x18003974f  mov     al, [r14]
0x180039752  nop
0x180039753  test    al, al
0x180039755  jnz     loc_1800397F6
0x18003975b  mov     r9, [rsi]
0x18003975e  lea     rcx, [r9+198h]; this
0x180039765  call    ?c_str@swstring@Halsey@@QEBAPEBGXZ; Halsey::swstring::c_str(void)
0x18003976a  mov     rdx, rax; unsigned __int16 *
0x18003976d  lea     rcx, [rdi+168h]; this
0x180039774  call    ?compare@swstring@Halsey@@AEBAHPEBG@Z; Halsey::swstring::compare(ushort const *)
0x180039779  test    eax, eax
0x18003977b  jnz     short loc_1800397F6
0x18003977d  lea     rcx, [r9+1A8h]; this
0x180039784  call    ?c_str@swstring@Halsey@@QEBAPEBGXZ; Halsey::swstring::c_str(void)
0x180039789  mov     rdx, rax; unsigned __int16 *
0x18003978c  lea     rcx, [rdi+178h]; this
0x180039793  call    ?compare@swstring@Halsey@@AEBAHPEBG@Z; Halsey::swstring::compare(ushort const *)
0x180039798  test    eax, eax
0x18003979a  jnz     short loc_1800397F6
0x18003979c  lea     rcx, [r9+1B8h]; this
0x1800397a3  call    ?c_str@swstring@Halsey@@QEBAPEBGXZ; Halsey::swstring::c_str(void)
0x1800397a8  mov     rdx, rax; unsigned __int16 *
0x1800397ab  lea     rcx, [rdi+188h]; this
0x1800397b2  call    ?compare@swstring@Halsey@@AEBAHPEBG@Z; Halsey::swstring::compare(ushort const *)
0x1800397b7  test    eax, eax
0x1800397b9  jnz     short loc_1800397F6
0x1800397bb  mov     al, [r9+1D8h]
0x1800397c2  cmp     [rdi+160h], al
0x1800397c8  jnz     short loc_1800397F6
0x1800397ca  mov     rax, [r9+230h]
0x1800397d1  test    rax, rax
0x1800397d4  jz      short loc_1800397DC
0x1800397d6  mov     rdx, [rax+10h]
0x1800397da  jmp     short loc_1800397DF
0x1800397dc  mov     rdx, r12
0x1800397df  mov     ecx, r12d
0x1800397e2  test    rdx, rdx
0x1800397e5  setnz   cl
0x1800397e8  movzx   eax, byte ptr [rdi+249h]
0x1800397ef  cmp     eax, ecx
0x1800397f1  mov     r15b, r12b
0x1800397f4  jz      short loc_1800397F9
0x1800397f6  mov     r15b, 1
0x1800397f9  lea     rcx, CriticalSection; lpCriticalSection
0x180039800  call    cs:__imp_EnterCriticalSection
0x180039806  lea     rcx, qword_1803B8D40
0x18003980d  call    ?reset@?$shared_ptr@VIConnection@Speech@Bing@@@std@@QEAAXXZ; std::shared_ptr<Bing::Speech::IConnection>::reset(void)
0x180039812  lea     rcx, CriticalSection; lpCriticalSection
0x180039819  call    cs:__imp_LeaveCriticalSection
0x18003981f  lea     rcx, [rsp+68h+var_48]
0x180039824  call    ?GetClientID@Client@LanguageUnderstanding@Bing@Microsoft@@YA?AVswstring@Halsey@@XZ; Microsoft::Bing::LanguageUnderstanding::Client::GetClientID(void)
0x180039829  nop
0x18003982a  lea     r9, [rdi+238h]
0x180039831  lea     rcx, [rsp+68h+var_48]; this
0x180039836  call    ?c_str@swstring@Halsey@@QEBAPEBGXZ; Halsey::swstring::c_str(void)
0x18003983b  mov     rdx, rax; unsigned __int16 *
0x18003983e  mov     rcx, r9; this
0x180039841  call    ?compare@swstring@Halsey@@AEBAHPEBG@Z; Halsey::swstring::compare(ushort const *)
0x180039846  test    eax, eax
0x180039848  jz      short loc_180039871
0x18003984a  lea     rcx, [rsp+68h+var_48]; this
0x18003984f  call    ?c_strsafe@swstring@Halsey@@QEBAPEBGXZ; Halsey::swstring::c_strsafe(void)
0x180039854  mov     r8, rax
0x180039857  mov     rcx, r9; this
0x18003985a  call    ?c_strsafe@swstring@Halsey@@QEBAPEBGXZ; Halsey::swstring::c_strsafe(void)
0x18003985f  lea     rcx, [rdi+0C8h]; this
0x180039866  mov     rdx, rax; unsigned __int16 *
0x180039869  call    ?CuClientUserIdChange@CuClientSession@RemoteNaturalLanguageTelemetry@Internal@Speech@Media@Windows@@QEAAXPEBG0@Z; Windows::Media::Speech::Internal::RemoteNaturalLanguageTelemetry::CuClientSession::CuClientUserIdChange(ushort const *,ushort const *)
0x18003986e  mov     r15b, 1
0x180039871  mov     rcx, [rsp+68h+var_40]; this
0x180039876  test    rcx, rcx
0x180039879  jz      short loc_180039881
0x18003987b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180039880  nop
0x180039881  test    rbx, rbx
0x180039884  jz      short loc_18003988F
0x180039886  mov     rcx, rbx; lpCriticalSection
0x180039889  call    cs:__imp_LeaveCriticalSection
0x18003988f  test    r15b, r15b
0x180039892  jz      short loc_1800398CB
0x180039894  mov     rcx, rdi; this
0x180039897  call    ?ResetCuClient@CuClientWrapper@Client@LanguageUnderstanding@Bing@Microsoft@@AEAAXXZ; Microsoft::Bing::LanguageUnderstanding::Client::CuClientWrapper::ResetCuClient(void)
0x18003989c  mov     eax, r12d
0x18003989f  xchg    al, [r14]
0x1800398a2  mov     [rsp+68h+var_40], r12
0x1800398a7  mov     [rsp+68h+var_44], 80045300h
0x1800398af  mov     byte ptr [rsp+68h+var_48], r12b; int
0x1800398b4  lea     rdx, [rsp+68h+var_48]; struct Bing::Speech::ConnectionStatus *
0x1800398b9  mov     rcx, rdi; this
0x1800398bc  call    ?OnEvent@CuClientWrapper@Client@LanguageUnderstanding@Bing@Microsoft@@AEAAXPEBUConnectionStatus@Speech@4@@Z; Microsoft::Bing::LanguageUnderstanding::Client::CuClientWrapper::OnEvent(Bing::Speech::ConnectionStatus const *)
0x1800398c1  lea     rcx, [rsp+68h+var_40]
0x1800398c6  call    ??1?$unique_ptr@VCookies@Speech@Bing@@U?$default_delete@VCookies@Speech@Bing@@@std@@@std@@QEAA@XZ; std::unique_ptr<Bing::Speech::Cookies>::~unique_ptr<Bing::Speech::Cookies>(void)
0x1800398cb  cmp     [rdi+0C0h], r12
0x1800398d2  jnz     loc_180039A63
0x1800398d8  mov     rcx, rbx; lpCriticalSection
0x1800398db  call    cs:__imp_EnterCriticalSection
0x1800398e1  mov     [rsp+68h+result], rbx
0x1800398e6  mov     rcx, [rsi]
0x1800398e9  mov     rax, [rcx+1A0h]
0x1800398f0  test    rax, rax
0x1800398f3  jz      short loc_1800398F9
0x1800398f5  lock inc dword ptr [rax+8]
0x1800398f9  mov     rdx, [rcx+1A0h]
0x180039900  mov     rax, [rcx+198h]
0x180039907  mov     [rdi+168h], rax
0x18003990e  mov     rcx, [rdi+170h]; this
0x180039915  mov     [rdi+170h], rdx
0x18003991c  test    rcx, rcx
0x18003991f  jz      short loc_180039926
0x180039921  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180039926  mov     rcx, [rsi]
0x180039929  mov     rax, [rcx+1B0h]
0x180039930  test    rax, rax
0x180039933  jz      short loc_180039939
0x180039935  lock inc dword ptr [rax+8]
0x180039939  mov     rdx, [rcx+1B0h]
0x180039940  mov     rax, [rcx+1A8h]
0x180039947  mov     [rdi+178h], rax
0x18003994e  mov     rcx, [rdi+180h]; this
0x180039955  mov     [rdi+180h], rdx
0x18003995c  test    rcx, rcx
0x18003995f  jz      short loc_180039966
0x180039961  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180039966  mov     rcx, [rsi]
0x180039969  mov     rax, [rcx+1C0h]
0x180039970  test    rax, rax
0x180039973  jz      short loc_180039979
0x180039975  lock inc dword ptr [rax+8]
0x180039979  mov     rdx, [rcx+1C0h]
0x180039980  mov     rax, [rcx+1B8h]
0x180039987  mov     [rdi+188h], rax
0x18003998e  mov     rcx, [rdi+190h]; this
0x180039995  mov     [rdi+190h], rdx
0x18003999c  test    rcx, rcx
0x18003999f  jz      short loc_1800399A6
0x1800399a1  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800399a6  mov     rax, [rsi]
0x1800399a9  mov     cl, [rax+1D8h]
0x1800399af  mov     [rdi+160h], cl
0x1800399b5  mov     rcx, [rsi]
0x1800399b8  add     rcx, 230h; this
0x1800399bf  call    ?c_strsafe@swstring@Halsey@@QEBAPEBGXZ; Halsey::swstring::c_strsafe(void)
0x1800399c4  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800399c8  mov     r8, r14
0x1800399cb  inc     r8
0x1800399ce  cmp     [rax+r8*2], r12w
0x1800399d3  jnz     short loc_1800399CB
0x1800399d5  lea     rcx, [rdi+1C8h]
0x1800399dc  mov     rdx, rax
0x1800399df  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800399e4  mov     rcx, [rsi]
0x1800399e7  add     rcx, 240h; this
0x1800399ee  call    ?c_strsafe@swstring@Halsey@@QEBAPEBGXZ; Halsey::swstring::c_strsafe(void)
0x1800399f3  inc     r14
0x1800399f6  cmp     [rax+r14*2], r12w
0x1800399fb  jnz     short loc_1800399F3
0x1800399fd  lea     rcx, [rdi+1E8h]
0x180039a04  mov     r8, r14
0x180039a07  mov     rdx, rax
  ... truncated ...
```
