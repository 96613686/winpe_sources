# QueryLogCommand::PrintEventText(void *,void *)

- ea: `0x14000be14`
- end: `0x14000c920`
- name: `?PrintEventText@QueryLogCommand@@AEAAXPEAX0@Z`
- size: `2828`
- prototype: `void(QueryLogCommand *__hidden this, void *, void *)`
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14000c928`

## callees

- `0x14000bbd0`
- `0x14000be14`
- `0x14000cabc`
- `0x14000cc04`
- `0x14000cfbc`
- `0x14000d144`
- `0x14000d7e4`
- `0x14000d868`
- `0x14000d8c4`
- `0x14000d968`
- `0x140010450`
- `0x1400163cc`
- `0x14001a2dc`
- `0x14001b714`
- `0x14001c0a8`
- `0x140021b00`
- `0x140022510`
- `0x140022cec`
- `0x140027930`
- `0x140031810`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c310`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c40e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c310`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c40e`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToTzSpecificLocalTime` at `0x14000c0ec`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToTzSpecificLocalTime` at `0x14000c0ec`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x14000c0d5`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x14000c0d5`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x14000c176`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x14000c176`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x14000c1e9`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x14000c1e9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000c206`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000c206`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x14000c302`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x14000c401`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x14000c302`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x14000c401`

## string_xrefs

- `0x14000c6ca`: `  Task`
- `0x14000c821`: `  Computer: `

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall QueryLogCommand::PrintEventText(QueryLogCommand *this, void *a2, void *a3)
{
  void *v6; // rax
  _QWORD *v7; // rdx
  __int64 v8; // r15
  __int64 v9; // rax
  unsigned int v10; // eax
  unsigned int v11; // edi
  __int64 v12; // rdi
  unsigned int v13; // r13d
  FILETIME v14; // rcx
  void *v15; // rcx
  __int64 v16; // r14
  unsigned __int64 v17; // rcx
  size_t v18; // rbx
  DWORD LastError; // eax
  __int64 v20; // r14
  unsigned __int64 v21; // rcx
  __int64 v22; // rax
  size_t v23; // rbx
  __int64 v24; // r14
  unsigned __int64 v25; // rcx
  __int64 v26; // rax
  size_t v27; // rbx
  unsigned __int64 v28; // rdx
  _QWORD *v29; // rcx
  __int64 v30; // r8
  const WCHAR *v31; // r9
  EVT_HANDLE v32; // rdi
  __int64 v33; // rax
  __int64 v34; // rax
  void *v35; // rax
  __int64 v36; // rax
  __int64 v37; // rax
  __int64 v38; // rax
  __int64 v39; // rax
  const char *ReferencedDomainName; // [rsp+20h] [rbp-E0h]
  DWORD cchReferencedDomainName; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cchName; // [rsp+44h] [rbp-BCh] BYREF
  DWORD v43; // [rsp+48h] [rbp-B8h] BYREF
  LPWSTR StringSid; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v45[40]; // [rsp+58h] [rbp-A8h] BYREF
  struct _SYSTEMTIME pExceptionObject; // [rsp+80h] [rbp-80h] BYREF
  __int64 v47; // [rsp+90h] [rbp-70h]
  _SYSTEMTIME SystemTime; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v49; // [rsp+C0h] [rbp-40h]
  FILETIME FileTime; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v51; // [rsp+D8h] [rbp-28h]
  _QWORD v52[2]; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int64 v53; // [rsp+100h] [rbp+0h]
  unsigned __int64 v54; // [rsp+108h] [rbp+8h]
  __int128 v55; // [rsp+110h] [rbp+10h] BYREF
  __m128i si128; // [rsp+120h] [rbp+20h]
  _QWORD v57[4]; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v58[16]; // [rsp+150h] [rbp+50h] BYREF
  __int64 v59; // [rsp+160h] [rbp+60h]
  _BYTE v60[32]; // [rsp+170h] [rbp+70h] BYREF
  _BYTE v61[32]; // [rsp+190h] [rbp+90h] BYREF
  __int64 v62; // [rsp+1B0h] [rbp+B0h] BYREF
  __int128 v63; // [rsp+1B8h] [rbp+B8h]
  __int128 v64; // [rsp+1C8h] [rbp+C8h]
  __int128 v65; // [rsp+1D8h] [rbp+D8h]
  __int16 v66; // [rsp+1E8h] [rbp+E8h]

  v43 = 0;
  std::wstring::wstring(v57, L"Event[");
  std::to_wstring(&pExceptionObject, (unsigned int)dword_140042670);
  v6 = (void *)std::wstring::_Append<wchar_t>(v57);
  std::wstring::_Append<wchar_t>(v6);
  std::wstring::_Tidy_deallocate(&pExceptionObject);
  v7 = v57;
  if ( v57[3] > 7u )
    v7 = (_QWORD *)v57[0];
  v8 = -1;
  v9 = -1;
  do
    ++v9;
  while ( *((_WORD *)v7 + v9) );
  FileTime = (FILETIME)v7;
  v51 = v9;
  FilePuts(*((HANDLE *)this + 2));
  ++dword_140042670;
  v10 = RenderEvent(a3, a2, 0, &v43);
  v11 = v10;
  if ( v10 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_7bd34925a3543a347cbe4ddd5f03596d_Traceguids, v10);
    }
    EvtException::EvtException((EvtException *)&pExceptionObject, v11, 0, 0, ReferencedDomainName, 445, 0x1Bu, 0);
    throw (EvtException *)&pExceptionObject;
  }
  if ( v43 < 0x11 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_7bd34925a3543a347cbe4ddd5f03596d_Traceguids, 13);
    }
    EvtException::EvtException((EvtException *)&pExceptionObject, 0xDu, 0, 0, ReferencedDomainName, 451, 0x1Bu, 0);
    throw (EvtException *)&pExceptionObject;
  }
  v12 = *((_QWORD *)this + 25);
  v55 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v55) = 0;
  if ( *(_DWORD *)(v12 + 12) == 1 && *(_QWORD *)v12 )
    std::wstring::assign(&v55);
  std::wstring::wstring(v58, L"N/A");
  if ( *(_DWORD *)(v12 + 236) == 1 && *(_QWORD *)(v12 + 224) )
    std::wstring::assign(v58);
  v13 = 0;
  if ( *(_DWORD *)(v12 + 44) == 6 )
    v13 = *(unsigned __int16 *)(v12 + 32);
  v62 = 0x41002F004ELL;
  v63 = 0;
  v64 = 0;
  v65 = 0;
  v66 = 0;
  if ( *(_DWORD *)(v12 + 140) == 17 )
  {
    v14 = *(FILETIME *)(v12 + 128);
    FileTime = v14;
    SystemTime = 0;
    FileTimeToSystemTime(&FileTime, &SystemTime);
    pExceptionObject = 0;
    if ( !SystemTimeToTzSpecificLocalTime(0, &SystemTime, &pExceptionObject) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_7bd34925a3543a347cbe4ddd5f03596d_Traceguids, 13);
      }
      EvtException::EvtException((EvtException *)v45, 0xDu, 0, 0, ReferencedDomainName, 484, 0x1Bu, 0);
      throw (EvtException *)v45;
    }
    SystemTimeToFileTime(&pExceptionObject, &FileTime);
    tlx::filetime_to_string<wchar_t>(&v62, &FileTime);
  }
  std::wstring::wstring(v61, L"N/A");
  if ( *(_DWORD *)(v12 + 252) == 1 && *(_QWORD *)(v12 + 240) )
    std::wstring::assign(v61);
  std::wstring::wstring(v60, L"N/A");
  StringSid = 0;
  if ( *(_DWORD *)(v12 + 268) == 19 )
  {
    v15 = *(void **)(v12 + 256);
    if ( v15 )
    {
      if ( ConvertSidToStringSidW(v15, &StringSid) )
      {
        std::wstring::assign(v60);
        LocalFree(StringSid);
      }
    }
  }
  std::wstring::wstring(v52, L"N/A");
  if ( *(_DWORD *)(v12 + 268) == 19 && *(_QWORD *)(v12 + 256) )
  {
    SystemTime = 0;
    v49 = 0;
    pExceptionObject = 0;
    v47 = 0;
    std::vector<wchar_t>::_Resize_reallocate<std::_Value_init_tag>(&SystemTime, 64);
    v16 = *(_QWORD *)&pExceptionObject.wHour;
    v17 = (__int64)(*(_QWORD *)&pExceptionObject.wHour - *(_QWORD *)&pExceptionObject.wYear) >> 1;
    if ( v17 <= 0x40 )
    {
      if ( v17 >= 0x40 )
        goto LABEL_49;
      if ( (unsigned __int64)((v47 - *(_QWORD *)&pExceptionObject.wYear) >> 1) < 0x40 )
      {
        std::vector<wchar_t>::_Resize_reallocate<std::_Value_init_tag>(&pExceptionObject, 64);
        v16 = *(_QWORD *)&pExceptionObject.wHour;
        goto LABEL_49;
      }
      v18 = 2 * (64 - v17);
      memset_0(*(void **)&pExceptionObject.wHour, 0, v18);
      v16 += v18;
    }
    else
    {
      v16 = *(_QWORD *)&pExceptionObject.wYear + 128LL;
    }
    *(_QWORD *)&pExceptionObject.wHour = v16;
LABEL_49:
    cchName = (__int64)(*(_QWORD *)&SystemTime.wHour - *(_QWORD *)&SystemTime.wYear) >> 1;
    cchReferencedDomainName = (v16 - *(_QWORD *)&pExceptionObject.wYear) >> 1;
    FileTime.dwLowDateTime = 0;
    if ( LookupAccountSidW(
           0,
           *(PSID *)(v12 + 256),
           *(LPWSTR *)&SystemTime.wYear,
           &cchName,
           *(LPWSTR *)&pExceptionObject.wYear,
           &cchReferencedDomainName,
           (PSID_NAME_USE)&FileTime) )
    {
      goto LABEL_68;
    }
    LastError = GetLastError();
    if ( LastError != 122 )
    {
LABEL_67:
      if ( LastError )
      {
LABEL_79:
        std::vector<wchar_t>::_Tidy(&pExceptionObject);
        std::vector<wchar_t>::_Tidy(&SystemTime);
        goto LABEL_80;
      }
LABEL_68:
      if ( cchReferencedDomainName && **(_WORD **)&pExceptionObject.wYear )
      {
        std::wstring::assign(v52);
        v28 = v53;
        v29 = v52;
        if ( v53 >= v54 )
        {
          ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__QEAAX_W_Z__W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAX_W_Z__W_Z(v52);
        }
        else
        {
          ++v53;
          if ( v54 > 7 )
            v29 = (_QWORD *)v52[0];
          *(_DWORD *)((char *)v29 + 2 * v28) = 92;
        }
        v30 = -1;
        do
          ++v30;
        while ( *(_WORD *)(*(_QWORD *)&SystemTime.wYear + 2 * v30) );
        std::wstring::_Append<wchar_t>(v52);
      }
      else
      {
        std::wstring::assign(v52);
      }
      goto LABEL_79;
    }
    v20 = *(_QWORD *)&SystemTime.wHour;
    v21 = (__int64)(*(_QWORD *)&SystemTime.wHour - *(_QWORD *)&SystemTime.wYear) >> 1;
    if ( cchName >= v21 )
    {
      if ( cchName <= v21 )
        goto LABEL_58;
      if ( cchName > (unsigned __int64)((v49 - *(_QWORD *)&SystemTime.wYear) >> 1) )
      {
        std::vector<wchar_t>::_Resize_reallocate<std::_Value_init_tag>(&SystemTime, cchName);
        goto LABEL_58;
      }
      v23 = 2 * (cchName - v21);
      memset_0(*(void **)&SystemTime.wHour, 0, v23);
      v22 = v20 + v23;
    }
    else
    {
      v22 = *(_QWORD *)&SystemTime.wYear + 2LL * cchName;
    }
    *(_QWORD *)&SystemTime.wHour = v22;
LABEL_58:
    v24 = *(_QWORD *)&pExceptionObject.wHour;
    v25 = (__int64)(*(_QWORD *)&pExceptionObject.wHour - *(_QWORD *)&pExceptionObject.wYear) >> 1;
    if ( cchReferencedDomainName < v25 )
    {
      v26 = *(_QWORD *)&pExceptionObject.wYear + 2LL * cchReferencedDomainName;
LABEL_64:
      *(_QWORD *)&pExceptionObject.wHour = v26;
      goto LABEL_65;
    }
    if ( cchReferencedDomainName > v25 )
    {
      if ( cchReferencedDomainName <= (unsigned __int64)((v47 - *(_QWORD *)&pExceptionObject.wYear) >> 1) )
      {
        v27 = 2 * (cchReferencedDomainName - v25);
        memset_0(*(void **)&pExceptionObject.wHour, 0, v27);
        v26 = v24 + v27;
        goto LABEL_64;
      }
      std::vector<wchar_t>::_Resize_reallocate<std::_Value_init_tag>(&pExceptionObject, cchReferencedDomainName);
    }
LABEL_65:
    if ( LookupAccountSidW(
           0,
           *(PSID *)(v12 + 256),
           *(LPWSTR *)&SystemTime.wYear,
           &cchName,
           *(LPWSTR *)&pExceptionObject.wYear,
           &cchReferencedDomainName,
           (PSID_NAME_USE)&FileTime) )
    {
      goto LABEL_68;
    }
    LastError = GetLastError();
    goto LABEL_67;
  }
LABEL_80:
  if ( *((_BYTE *)this + 256) )
  {
    v31 = (const WCHAR *)((char *)this + 40);
    if ( *((_QWORD *)this + 8) > 7u )
      v31 = *(const WCHAR **)v31;
  }
  else
  {
    v31 = 0;
  }
  v32 = QueryLogCommand::PublisherCache::Open(
          (_QWORD *)this + 28,
          *((void **)this + 3),
          (__int64)&v55,
          v31,
          *((_DWORD *)this + 62));
  if ( v59 )
  {
    *(_QWORD *)&pExceptionObject.wYear = L"  Log Name: ";
    *(_QWORD *)&pExceptionObject.wHour = 12;
    FilePuts(*((HANDLE *)this + 2));
    v33 = std::wstring::_Append<wchar_t>(v58);
    pExceptionObject = *(struct _SYSTEMTIME *)std::wstring::operator std::wstring_view(v33, &SystemTime);
    FilePuts(*((HANDLE *)this + 2));
  }
  else
  {
    *(_QWORD *)&pExceptionObject.wYear = L"  Log Name";
    *(_QWORD *)&pExceptionObject.wHour = 10;
    QueryLogCommand::PrintMessage(this, 0, a2, 6, &pExceptionObject);
  }
  if ( si128.m128i_i64[0] )
  {
    *(_QWORD *)&pExceptionObject.wYear = L"  Source: ";
    *(_QWORD *)&pExceptionObject.wHour = 10;
    FilePuts(*((HANDLE *)this + 2));
    v34 = std::wstring::_Append<wchar_t>(&v55);
    pExceptionObject = *(struct _SYSTEMTIME *)std::wstring::operator std::wstring_view(v34, &SystemTime);
    FilePuts(*((HANDLE *)this + 2));
  }
  else
  {
    *(_QWORD *)&pExceptionObject.wYear = L"  Source";
    *(_QWORD *)&pExceptionObject.wHour = 8;
    QueryLogCommand::PrintMessage(this, 0, a2, 7, &pExceptionObject);
  }
  *(_QWORD *)&pExceptionObject.wYear = L"  Date: ";
  *(_QWORD *)&pExceptionObject.wHour = 8;
  FilePuts(*((HANDLE *)this + 2));
  do
    ++v8;
  while ( *((_WORD *)&v62 + v8) );
  *(_QWORD *)&pExceptionObject.wYear = &v62;
  *(_QWORD *)&pExceptionObject.wHour = v8;
  FilePuts(*((HANDLE *)this + 2));
  *(_QWORD *)&pExceptionObject.wYear = L"\r\n";
  *(_QWORD *)&pExceptionObject.wHour = 2;
  FilePuts(*((HANDLE *)this + 2));
  *(_QWORD *)&pExceptionObject.wYear = L"  Event ID: ";
  *(_QWORD *)&pExceptionObject.wHour = 12;
  FilePuts(*((HANDLE *)this + 2));
  v35 = (void *)std::to_wstring(&FileTime, v13);
  v36 = std::wstring::_Append<wchar_t>(v35);
  pExceptionObject = *(struct _SYSTEMTIME *)std::wstring::operator std::wstring_view(v36, &SystemTime);
  FilePuts(*((HANDLE *)this + 2));
  std::wstring::_Tidy_deallocate(&FileTime);
  *(_QWORD *)&pExceptionObject.wYear = L"  Task";
  *(_QWORD *)&pExceptionObject.wHour = 6;
  QueryLogCommand::PrintMessage(this, v32, a2, 3, &pExceptionObject);
  *(_QWORD *)&pExceptionObject.wYear = L"  Level";
  *(_QWORD *)&pExceptionObject.wHour = 7;
  QueryLogCommand::PrintMessage(this, v32, a2, 2, &pExceptionObject);
  *(_QWORD *)&pExceptionObject.wYear = L"  Opcode";
  *(_QWORD *)&pExceptionObject.wHour = 8;
  QueryLogCommand::PrintMessage(this, v32, a2, 4, &pExceptionObject);
  *(_QWORD *)&pExceptionObject.wYear = L"  Keyword";
  *(_QWORD *)&pExceptionObject.wHour = 9;
  QueryLogCommand::PrintMessage(this, v32, a2, 5, &pExceptionObject);
  *(_QWORD *)&pExceptionObject.wYear = L"  User: ";
  *(_QWORD *)&pExceptionObject.wHour = 8;
  FilePuts(*((HANDLE *)this + 2));
  v37 = std::wstring::_Append<wchar_t>(v60);
  pExceptionObject = *(struct _SYSTEMTIME *)std::wstring::operator std::wstring_view(v37, &SystemTime);
  FilePuts(*((HANDLE *)this + 2));
  *(_QWORD *)&pExceptionObject.wYear = L"  User Name: ";
  *(_QWORD *)&pExceptionObject.wHour = 13;
  FilePuts(*((HANDLE *)this + 2));
  v38 = std::wstring::_Append<wchar_t>(v52);
  pExceptionObject = *(struct _SYSTEMTIME *)std::wstring::operator std::wstring_view(v38, &SystemTime);
  FilePuts(*((HANDLE *)this + 2));
  *(_QWORD *)&pExceptionObject.wYear = L"  Computer: ";
  *(_QWORD *)&pExceptionObject.wHour = 12;
  FilePuts(*((HANDLE *)this + 2));
  v39 = std::wstring::_Append<wchar_t>(v61);
  pExceptionObject = *(struct _SYSTEMTIME *)std::wstring::operator std::wstring_view(v39, &SystemTime);
  FilePuts(*((HANDLE *)this + 2));
  *(_QWORD *)&pExceptionObject.wYear = L"  Description";
  *(_QWORD *)&pExceptionObject.wHour = 13;
  QueryLogCommand::PrintMessage(this, v32, a2, 1, &pExceptionObject);
  *(_QWORD *)&pExceptionObject.wYear = L"\r\n";
  *(_QWORD *)&pExceptionObject.wHour = 2;
  FilePuts(*((HANDLE *)this + 2));
  std::wstring::_Tidy_deallocate(v52);
  std::wstring::_Tidy_deallocate(v60);
  std::wstring::_Tidy_deallocate(v61);
  std::wstring::_Tidy_deallocate(v58);
  std::wstring::_Tidy_deallocate(&v55);
  std::wstring::_Tidy_deallocate(v57);
}

```

## disassembly

```asm
0x14000be14  mov     [rsp-8+arg_18], rbx
0x14000be19  push    rbp
0x14000be1a  push    rsi
0x14000be1b  push    rdi
0x14000be1c  push    r12
0x14000be1e  push    r13
0x14000be20  push    r14
0x14000be22  push    r15
0x14000be24  lea     rbp, [rsp-100h]
0x14000be2c  sub     rsp, 200h
0x14000be33  mov     rax, cs:__security_cookie
0x14000be3a  xor     rax, rsp
0x14000be3d  mov     [rbp+130h+var_40], rax
0x14000be44  mov     rdi, r8
0x14000be47  mov     r12, rdx
0x14000be4a  mov     rsi, rcx
0x14000be4d  xor     r14d, r14d
0x14000be50  mov     [rsp+230h+var_1E8], r14d
0x14000be55  lea     rdx, aEvent_0; "Event["
0x14000be5c  lea     rcx, [rbp+130h+var_100]
0x14000be60  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x14000be65  nop
0x14000be66  mov     edx, cs:dword_140042670
0x14000be6c  lea     rcx, [rbp+130h+pExceptionObject]
0x14000be70  call    ?to_wstring@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@I@Z; std::to_wstring(uint)
0x14000be75  nop
0x14000be76  mov     r8, [rax+10h]
0x14000be7a  cmp     qword ptr [rax+18h], 7
0x14000be7f  jbe     short loc_14000BE84
0x14000be81  mov     rax, [rax]
0x14000be84  mov     rdx, rax
0x14000be87  lea     rcx, [rbp+130h+var_100]; Src
0x14000be8b  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x14000be90  mov     r8d, 3
0x14000be96  lea     rdx, asc_140037970; "]\r\n"
0x14000be9d  mov     rcx, rax; Src
0x14000bea0  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x14000bea5  nop
0x14000bea6  lea     rcx, [rbp+130h+pExceptionObject]
0x14000beaa  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14000beaf  lea     rdx, [rbp+130h+var_100]
0x14000beb3  cmp     [rbp+130h+var_E8], 7
0x14000beb8  cmova   rdx, [rbp+130h+var_100]
0x14000bebd  or      r15, 0FFFFFFFFFFFFFFFFh
0x14000bec1  mov     rax, r15
0x14000bec4  inc     rax
0x14000bec7  cmp     [rdx+rax*2], r14w
0x14000becc  jnz     short loc_14000BEC4
0x14000bece  mov     qword ptr [rbp+130h+FileTime.dwLowDateTime], rdx
0x14000bed2  mov     [rbp+130h+var_158], rax
0x14000bed6  lea     rdx, [rbp+130h+FileTime]
0x14000beda  mov     rcx, [rsi+10h]; hFile
0x14000bede  call    ?FilePuts@@YAJPEAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; FilePuts(void *,std::wstring_view)
0x14000bee3  inc     cs:dword_140042670
0x14000bee9  lea     rbx, [rsi+0C8h]
0x14000bef0  lea     rax, [rsp+230h+var_1E8]
0x14000bef5  mov     [rsp+230h+ReferencedDomainName], rax; char *
0x14000befa  mov     r9, rbx
0x14000befd  xor     r8d, r8d; Flags
0x14000bf00  mov     rdx, r12; Fragment
0x14000bf03  mov     rcx, rdi; Context
0x14000bf06  call    ?RenderEvent@@YAKPEAX0KAEAV?$vector@EV?$allocator@E@std@@@std@@AEAK@Z; RenderEvent(void *,void *,ulong,std::vector<uchar> &,ulong &)
0x14000bf0b  mov     edi, eax
0x14000bf0d  test    eax, eax
0x14000bf0f  jz      short loc_14000BF86
0x14000bf11  lea     rcx, WPP_GLOBAL_Control
0x14000bf18  mov     r10, cs:WPP_GLOBAL_Control
0x14000bf1f  cmp     r10, rcx
0x14000bf22  jz      short loc_14000BF4F
0x14000bf24  test    dword ptr [r10+1Ch], 400000h
0x14000bf2c  jz      short loc_14000BF4F
0x14000bf2e  mov     ebx, 2
0x14000bf33  cmp     [r10+19h], bl
0x14000bf37  jb      short loc_14000BF4F
0x14000bf39  lea     edx, [rbx+1Ch]
0x14000bf3c  mov     r9d, eax
0x14000bf3f  lea     r8, WPP_7bd34925a3543a347cbe4ddd5f03596d_Traceguids
0x14000bf46  mov     rcx, [r10+10h]
0x14000bf4a  call    WPP_SF_d
0x14000bf4f  mov     [rsp+230h+Src], r14; Src
0x14000bf54  mov     dword ptr [rsp+230h+peUse], 1Bh; unsigned int
0x14000bf5c  mov     dword ptr [rsp+230h+cchReferencedDomainName], 1BDh; int
0x14000bf64  xor     r9d, r9d; unsigned int
0x14000bf67  xor     r8d, r8d; unsigned int
0x14000bf6a  mov     edx, edi; unsigned int
0x14000bf6c  lea     rcx, [rbp+130h+pExceptionObject]; this
0x14000bf70  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x14000bf75  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14000bf7c  lea     rcx, [rbp+130h+pExceptionObject]; pExceptionObject
0x14000bf80  call    _CxxThrowException_0
0x14000bf86  cmp     [rsp+230h+var_1E8], 11h
0x14000bf8b  jnb     short loc_14000C003
0x14000bf8d  lea     rcx, WPP_GLOBAL_Control
0x14000bf94  mov     rax, cs:WPP_GLOBAL_Control
0x14000bf9b  cmp     rax, rcx
0x14000bf9e  jz      short loc_14000BFCA
0x14000bfa0  test    dword ptr [rax+1Ch], 400000h
0x14000bfa7  jz      short loc_14000BFCA
0x14000bfa9  mov     ebx, 2
0x14000bfae  cmp     [rax+19h], bl
0x14000bfb1  jb      short loc_14000BFCA
0x14000bfb3  lea     edx, [rbx+1Dh]
0x14000bfb6  lea     r9d, [rbx+0Bh]
0x14000bfba  lea     r8, WPP_7bd34925a3543a347cbe4ddd5f03596d_Traceguids
0x14000bfc1  mov     rcx, [rax+10h]
0x14000bfc5  call    WPP_SF_d
0x14000bfca  mov     [rsp+230h+Src], r14; Src
0x14000bfcf  mov     dword ptr [rsp+230h+peUse], 1Bh; unsigned int
0x14000bfd7  mov     dword ptr [rsp+230h+cchReferencedDomainName], 1C3h; int
0x14000bfdf  xor     r9d, r9d; unsigned int
0x14000bfe2  xor     r8d, r8d; unsigned int
0x14000bfe5  lea     edx, [r9+0Dh]; unsigned int
0x14000bfe9  lea     rcx, [rbp+130h+pExceptionObject]; this
0x14000bfed  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x14000bff2  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14000bff9  lea     rcx, [rbp+130h+pExceptionObject]; pExceptionObject
0x14000bffd  call    _CxxThrowException_0
0x14000c003  mov     rdi, [rbx]
0x14000c006  xorps   xmm0, xmm0
0x14000c009  movups  [rbp+130h+var_120], xmm0
0x14000c00d  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x14000c015  movdqu  [rbp+130h+var_110], xmm1
0x14000c01a  mov     word ptr [rbp+130h+var_120], r14w
0x14000c01f  cmp     dword ptr [rdi+0Ch], 1
0x14000c023  jnz     short loc_14000C036
0x14000c025  mov     rdx, [rdi]
0x14000c028  test    rdx, rdx
0x14000c02b  jz      short loc_14000C036
0x14000c02d  lea     rcx, [rbp+130h+var_120]
0x14000c031  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x14000c036  lea     rbx, aNA; "N/A"
0x14000c03d  mov     rdx, rbx
0x14000c040  lea     rcx, [rbp+130h+var_E0]
0x14000c044  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x14000c049  nop
0x14000c04a  cmp     dword ptr [rdi+0ECh], 1
0x14000c051  jnz     short loc_14000C068
0x14000c053  mov     rdx, [rdi+0E0h]
0x14000c05a  test    rdx, rdx
0x14000c05d  jz      short loc_14000C068
0x14000c05f  lea     rcx, [rbp+130h+var_E0]
0x14000c063  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x14000c068  mov     r13d, r14d
0x14000c06b  cmp     dword ptr [rdi+2Ch], 6
0x14000c06f  jnz     short loc_14000C076
0x14000c071  movzx   r13d, word ptr [rdi+20h]
0x14000c076  mov     rax, 41002F004Eh
0x14000c080  mov     [rbp+130h+var_80], rax
0x14000c087  xorps   xmm0, xmm0
0x14000c08a  xor     eax, eax
0x14000c08c  movups  [rbp+130h+var_78], xmm0
0x14000c093  movups  [rbp+130h+var_68], xmm0
0x14000c09a  movups  [rbp+130h+var_58], xmm0
0x14000c0a1  mov     [rbp+130h+var_48], ax
0x14000c0a8  cmp     dword ptr [rdi+8Ch], 11h
0x14000c0af  jnz     loc_14000C18C
0x14000c0b5  mov     rcx, [rdi+80h]
0x14000c0bc  mov     rax, rcx
0x14000c0bf  shr     rax, 20h
0x14000c0c3  mov     [rbp+130h+FileTime.dwHighDateTime], eax
0x14000c0c6  mov     [rbp+130h+FileTime.dwLowDateTime], ecx
0x14000c0c9  movups  xmmword ptr [rbp+130h+SystemTime.wYear], xmm0
0x14000c0cd  lea     rdx, [rbp+130h+SystemTime]; lpSystemTime
0x14000c0d1  lea     rcx, [rbp+130h+FileTime]; lpFileTime
0x14000c0d5  call    cs:__imp_FileTimeToSystemTime
0x14000c0db  xorps   xmm0, xmm0
0x14000c0de  movups  [rbp+130h+pExceptionObject], xmm0
0x14000c0e2  lea     r8, [rbp+130h+pExceptionObject]; lpLocalTime
0x14000c0e6  lea     rdx, [rbp+130h+SystemTime]; lpUniversalTime
0x14000c0ea  xor     ecx, ecx; lpTimeZoneInformation
0x14000c0ec  call    cs:__imp_SystemTimeToTzSpecificLocalTime
0x14000c0f2  test    eax, eax
0x14000c0f4  jnz     short loc_14000C16E
0x14000c0f6  lea     rcx, WPP_GLOBAL_Control
0x14000c0fd  mov     rax, cs:WPP_GLOBAL_Control
0x14000c104  cmp     rax, rcx
0x14000c107  jz      short loc_14000C133
0x14000c109  test    dword ptr [rax+1Ch], 400000h
0x14000c110  jz      short loc_14000C133
0x14000c112  mov     ebx, 2
0x14000c117  cmp     [rax+19h], bl
0x14000c11a  jb      short loc_14000C133
0x14000c11c  lea     edx, [rbx+1Eh]
0x14000c11f  lea     r9d, [rbx+0Bh]
0x14000c123  lea     r8, WPP_7bd34925a3543a347cbe4ddd5f03596d_Traceguids
0x14000c12a  mov     rcx, [rax+10h]
0x14000c12e  call    WPP_SF_d
0x14000c133  mov     [rsp+230h+Src], r14; Src
0x14000c138  mov     dword ptr [rsp+230h+peUse], 1Bh; unsigned int
0x14000c140  mov     dword ptr [rsp+230h+cchReferencedDomainName], 1E4h; int
0x14000c148  xor     r9d, r9d; unsigned int
0x14000c14b  xor     r8d, r8d; unsigned int
0x14000c14e  lea     edx, [r9+0Dh]; unsigned int
0x14000c152  lea     rcx, [rsp+230h+var_1D8]; this
0x14000c157  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x14000c15c  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14000c163  lea     rcx, [rsp+230h+var_1D8]; pExceptionObject
0x14000c168  call    _CxxThrowException_0
0x14000c16e  lea     rdx, [rbp+130h+FileTime]; lpFileTime
0x14000c172  lea     rcx, [rbp+130h+pExceptionObject]; lpSystemTime
0x14000c176  call    cs:__imp_SystemTimeToFileTime
0x14000c17c  lea     rdx, [rbp+130h+FileTime]
0x14000c180  lea     rcx, [rbp+130h+var_80]
0x14000c187  call    ??$filetime_to_string@_W@tlx@@YAXPEA_WAEBU_FILETIME@@_N@Z; tlx::filetime_to_string<wchar_t>(wchar_t *,_FILETIME const &,bool)
0x14000c18c  mov     rdx, rbx
0x14000c18f  lea     rcx, [rbp+130h+var_A0]
0x14000c196  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x14000c19b  nop
0x14000c19c  cmp     dword ptr [rdi+0FCh], 1
0x14000c1a3  jnz     short loc_14000C1BD
0x14000c1a5  mov     rdx, [rdi+0F0h]
0x14000c1ac  test    rdx, rdx
0x14000c1af  jz      short loc_14000C1BD
0x14000c1b1  lea     rcx, [rbp+130h+var_A0]
0x14000c1b8  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x14000c1bd  mov     rdx, rbx
0x14000c1c0  lea     rcx, [rbp+130h+var_C0]
0x14000c1c4  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x14000c1c9  nop
0x14000c1ca  mov     [rsp+230h+StringSid], r14
0x14000c1cf  cmp     dword ptr [rdi+10Ch], 13h
0x14000c1d6  jnz     short loc_14000C20C
0x14000c1d8  mov     rcx, [rdi+100h]; Sid
0x14000c1df  test    rcx, rcx
0x14000c1e2  jz      short loc_14000C20C
0x14000c1e4  lea     rdx, [rsp+230h+StringSid]; StringSid
0x14000c1e9  call    cs:__imp_ConvertSidToStringSidW
0x14000c1ef  test    eax, eax
0x14000c1f1  jz      short loc_14000C20C
0x14000c1f3  mov     rdx, [rsp+230h+StringSid]
0x14000c1f8  lea     rcx, [rbp+130h+var_C0]
0x14000c1fc  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x14000c201  mov     rcx, [rsp+230h+StringSid]; hMem
0x14000c206  call    cs:__imp_LocalFree
0x14000c20c  mov     rdx, rbx
0x14000c20f  lea     rcx, [rbp+130h+var_140]
0x14000c213  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x14000c218  nop
0x14000c219  cmp     dword ptr [rdi+10Ch], 13h
0x14000c220  jnz     loc_14000C4A3
0x14000c226  cmp     [rdi+100h], r14
0x14000c22d  jz      loc_14000C4A3
0x14000c233  xorps   xmm0, xmm0
0x14000c236  movdqu  xmmword ptr [rbp+130h+SystemTime.wYear], xmm0
0x14000c23b  mov     [rbp+130h+var_170], r14
0x14000c23f  movdqu  [rbp+130h+pExceptionObject], xmm0
0x14000c244  mov     [rbp+130h+var_1A0], r14
0x14000c248  mov     ebx, 40h ; '@'
0x14000c24d  mov     edx, ebx
0x14000c24f  lea     rcx, [rbp+130h+SystemTime]
0x14000c253  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@_WV?$allocator@_W@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<wchar_t>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x14000c258  mov     rdx, qword ptr [rbp+130h+pExceptionObject]
0x14000c25c  mov     r14, qword ptr [rbp+130h+pExceptionObject+8]
0x14000c260  mov     rcx, r14
0x14000c263  sub     rcx, rdx
0x14000c266  sar     rcx, 1
0x14000c269  cmp     rcx, rbx
0x14000c26c  jbe     short loc_14000C277
0x14000c26e  lea     r14, [rdx+80h]
0x14000c275  jmp     short loc_14000C2B0
0x14000c277  jnb     short loc_14000C2B4
0x14000c279  mov     rax, [rbp+130h+var_1A0]
0x14000c27d  sub     rax, rdx
0x14000c280  sar     rax, 1
0x14000c283  cmp     rax, rbx
0x14000c286  jnb     short loc_14000C29A
0x14000c288  mov     rdx, rbx
0x14000c28b  lea     rcx, [rbp+130h+pExceptionObject]
0x14000c28f  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@_WV?$allocator@_W@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<wchar_t>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x14000c294  mov     r14, qword ptr [rbp+130h+pExceptionObject+8]
0x14000c298  jmp     short loc_14000C2B4
0x14000c29a  sub     rbx, rcx
0x14000c29d  add     rbx, rbx
0x14000c2a0  mov     r8, rbx; Size
0x14000c2a3  xor     edx, edx; Val
0x14000c2a5  mov     rcx, r14; void *
0x14000c2a8  call    memset_0
0x14000c2ad  add     r14, rbx
0x14000c2b0  mov     qword ptr [rbp+130h+pExceptionObject+8], r14
0x14000c2b4  mov     r8, qword ptr [rbp+130h+SystemTime.wYear]; Name
0x14000c2b8  mov     rax, qword ptr [rbp+130h+SystemTime.wHour]
0x14000c2bc  sub     rax, r8
0x14000c2bf  sar     rax, 1
0x14000c2c2  mov     [rsp+230h+cchName], eax
0x14000c2c6  mov     rax, qword ptr [rbp+130h+pExceptionObject]
0x14000c2ca  sub     r14, rax
0x14000c2cd  sar     r14, 1
0x14000c2d0  mov     [rsp+230h+var_1F0], r14d
0x14000c2d5  xor     r14d, r14d
0x14000c2d8  mov     [rbp+130h+FileTime.dwLowDateTime], r14d
0x14000c2dc  lea     rcx, [rbp+130h+FileTime]
0x14000c2e0  mov     [rsp+230h+peUse], rcx; peUse
0x14000c2e5  lea     rcx, [rsp+230h+var_1F0]
0x14000c2ea  mov     [rsp+230h+cchReferencedDomainName], rcx; cchReferencedDomainName
0x14000c2ef  mov     [rsp+230h+ReferencedDomainName], rax; ReferencedDomainName
0x14000c2f4  lea     r9, [rsp+230h+cchName]; cchName
0x14000c2f9  mov     rdx, [rdi+100h]; Sid
0x14000c300  xor     ecx, ecx; lpSystemName
0x14000c302  call    cs:__imp_LookupAccountSidW
0x14000c308  test    eax, eax
  ... truncated ...
```
