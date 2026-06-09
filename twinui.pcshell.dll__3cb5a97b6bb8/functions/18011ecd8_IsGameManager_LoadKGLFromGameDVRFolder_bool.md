# IsGameManager::LoadKGLFromGameDVRFolder(bool)

- ea: `0x18011ecd8`
- end: `0x18011f37f`
- name: `?LoadKGLFromGameDVRFolder@IsGameManager@@AEAAJ_N@Z`
- size: `1703`
- prototype: `__int64 __fastcall(IsGameManager *__hidden this, bool)`
- caller_count: `2`
- callee_count: `15`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180020630`
- `0x18039b8b0`

## callees

- `0x1800134f8`
- `0x180018e24`
- `0x180019a90`
- `0x1800219a0`
- `0x1800237c8`
- `0x180031c70`
- `0x18008b6a0`
- `0x18011ecd8`
- `0x18011f388`
- `0x18011fd44`
- `0x180279e50`
- `0x1802b26e4`
- `0x180356360`
- `0x180356edc`
- `0x1806fa010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18011ee62`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18011ee62`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18011ef07`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18011ef07`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18011eed7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18011eed7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18011f007`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18011f329`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18011f007`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18011f329`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18011ef8d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18011ef8d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18011ed9b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18011ee39`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18011ee4a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18011f023`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18011f032`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18011f345`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18011f354`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18011ed9b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18011ee39`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18011ee4a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18011f023`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18011f032`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18011f345`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18011f354`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18011edb3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18011ee73`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18011edb3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18011ee73`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18011ef31`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18011ef31`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18011f2a9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18011f2a9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18011f2e1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18011f2e1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18011f2f7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18011f2f7`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18011edbe`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18011edbe`

## string_xrefs

- `0x18011ef9b`: `KGLToGCSUpdatedRevision`
- `0x18011ed72`: `pcshell\twinui\broadcastdvrcomponent\lib\isgamemanager.cpp`
- `0x18011edd0`: `pcshell\twinui\broadcastdvrcomponent\lib\isgamemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall IsGameManager::LoadKGLFromGameDVRFolder(RTL_SRWLOCK *this, char a2)
{
  __int64 *v3; // rax
  __int64 v4; // r13
  __int64 v5; // r12
  int KnownFolderSubFolder; // eax
  unsigned int v7; // edi
  HSTRING v9; // rdi
  const WCHAR *StringRawBuffer; // rax
  IsGameManager *v11; // rcx
  int v12; // eax
  int v13; // eax
  unsigned int v14; // esi
  RTL_SRWLOCK *v15; // r15
  HSTRING v16; // rbx
  PCWSTR v17; // rsi
  struct KnownGameList::IQueryKnownGameList **v18; // rdx
  KnownGameList *v19; // rsi
  const unsigned __int16 *v20; // r8
  int QueryKnownGameListInstance; // eax
  __int64 v22; // rcx
  __int64 v23; // rsi
  int updated; // eax
  int v25; // eax
  int v26; // eax
  int v27; // eax
  __int64 v28; // rdx
  unsigned int v29; // eax
  __int64 v30; // rcx
  int Key; // esi
  int dwOptions; // [rsp+20h] [rbp-E0h]
  int dwOptionsa; // [rsp+20h] [rbp-E0h]
  BYTE Data[8]; // [rsp+50h] [rbp-B0h] BYREF
  char v35; // [rsp+58h] [rbp-A8h]
  HSTRING string; // [rsp+60h] [rbp-A0h] BYREF
  int v37; // [rsp+68h] [rbp-98h] BYREF
  HSTRING v38; // [rsp+70h] [rbp-90h] BYREF
  KnownGameList *v39; // [rsp+78h] [rbp-88h]
  _QWORD v40[4]; // [rsp+80h] [rbp-80h] BYREF
  char v41; // [rsp+A0h] [rbp-60h]
  __int128 v42; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v43; // [rsp+B8h] [rbp-48h]
  __int128 v44; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v45; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v46[32]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v47[40]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v48[624]; // [rsp+128h] [rbp+28h] BYREF
  _BYTE v49[4]; // [rsp+398h] [rbp+298h] BYREF
  _BYTE v50[4]; // [rsp+39Ch] [rbp+29Ch] BYREF
  _BYTE v51[16]; // [rsp+3A0h] [rbp+2A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+408h] [rbp+308h]

  v35 = a2;
  *(_QWORD *)Data = this;
  v37 = 0;
  v38 = 0;
  string = 0;
  v3 = (__int64 *)_lambda_6b6168dda817c5975ee7d3438d2331fe_::_lambda_6b6168dda817c5975ee7d3438d2331fe_(v40, this, &v37);
  v4 = *v3;
  v40[2] = *v3;
  v5 = v3[1];
  v40[3] = v5;
  v41 = 1;
  KnownFolderSubFolder = GetKnownFolderSubFolder(
                           &FOLDERID_LocalAppData,
                           L"Microsoft\\GameDVR",
                           0,
                           (struct Windows::Internal::String *)&string);
  v7 = KnownFolderSubFolder;
  if ( KnownFolderSubFolder < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2A2,
      (unsigned int)"pcshell\\twinui\\broadcastdvrcomponent\\lib\\isgamemanager.cpp",
      (const char *)(unsigned int)KnownFolderSubFolder,
      dwOptions);
    BroadcastDVRTraceProvider::KGLLoaded<unsigned long &,long &>(v4 + 44, v5);
    if ( string )
      WindowsDeleteString(string);
    return v7;
  }
  v9 = string;
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  CreateDirectoryW(StringRawBuffer, 0);
  v12 = IsGameManager::EnsureGameDVRFolderAccess(v11);
  if ( v12 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x2A6,
      (unsigned int)"pcshell\\twinui\\broadcastdvrcomponent\\lib\\isgamemanager.cpp",
      (const char *)(unsigned int)v12,
      dwOptions);
  v13 = GetKnownFolderSubFolder(
          &FOLDERID_LocalAppData,
          L"Microsoft\\GameDVR\\KnownGameList.bin",
          0,
          (struct Windows::Internal::String *)&v38);
  v14 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2AB,
      (unsigned int)"pcshell\\twinui\\broadcastdvrcomponent\\lib\\isgamemanager.cpp",
      (const char *)(unsigned int)v13,
      dwOptions);
    BroadcastDVRTraceProvider::KGLLoaded<unsigned long &,long &>(v4 + 44, v5);
    if ( v9 )
      WindowsDeleteString(v9);
    if ( v38 )
      WindowsDeleteString(v38);
    return v14;
  }
  v15 = this + 4;
  v40[0] = this + 4;
  AcquireSRWLockExclusive(this + 4);
  v16 = v38;
  v17 = WindowsGetStringRawBuffer(v38, 0);
  v39 = (KnownGameList *)(*(_QWORD *)Data + 24LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(*(_QWORD *)Data + 24LL);
  v18 = (struct KnownGameList::IQueryKnownGameList **)v17;
  v19 = v39;
  QueryKnownGameListInstance = KnownGameList::CreateQueryKnownGameListInstance(v39, v18, v20);
  v37 = QueryKnownGameListInstance;
  if ( (unsigned int)(QueryKnownGameListInstance + 2147024894) > 1
    && QueryKnownGameListInstance != -2147024809
    && QueryKnownGameListInstance < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x2B4,
      (unsigned int)"pcshell\\twinui\\broadcastdvrcomponent\\lib\\isgamemanager.cpp",
      (const char *)(unsigned int)QueryKnownGameListInstance,
      dwOptions);
  }
  ReleaseSRWLockExclusive(v15);
  if ( v37 < 0 )
    goto LABEL_71;
  v42 = 0;
  v43 = 0;
  v44 = 0;
  v45 = 0;
  v40[0] = v15;
  AcquireSRWLockShared(v15);
  v22 = *(_QWORD *)v19;
  v23 = *(_QWORD *)Data;
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v22 + 80LL))(v22, *(_QWORD *)Data + 44LL);
  if ( v35 )
  {
    *(_QWORD *)(*(_QWORD *)Data + 104LL) = GetTickCount64() + 30000;
    updated = IsGameManager::UpdateGameConfigStoreFromKGL((IsGameManager *)v23);
    if ( updated < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x2CC,
        (unsigned int)"pcshell\\twinui\\broadcastdvrcomponent\\lib\\isgamemanager.cpp",
        (const char *)(unsigned int)updated,
        dwOptions);
    v25 = IsGameManager::ScanKGLForFSECompat((IsGameManager *)v23);
    if ( v25 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x2CE,
        (unsigned int)"pcshell\\twinui\\broadcastdvrcomponent\\lib\\isgamemanager.cpp",
        (const char *)(unsigned int)v25,
        dwOptions);
    if ( WaitForSingleObject(*(HANDLE *)(v23 + 96), 0) )
    {
      v26 = SHRegSetDWORD(
              HKEY_CURRENT_USER,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\GameDVR",
              L"KGLToGCSUpdatedRevision",
              *(_DWORD *)(v23 + 44));
      if ( v26 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x2D5,
          (unsigned int)"pcshell\\twinui\\broadcastdvrcomponent\\lib\\isgamemanager.cpp",
          (const char *)(unsigned int)v26,
          dwOptions);
    }
    v27 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(**(_QWORD **)(v23 + 24) + 72LL))(*(_QWORD *)(v23 + 24), &v42);
    *(_DWORD *)Data = v27;
    if ( v27 < 0 )
    {
      v28 = 728;
LABEL_28:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v28,
        (unsigned int)"pcshell\\twinui\\broadcastdvrcomponent\\lib\\isgamemanager.cpp",
        (const char *)(unsigned int)v27,
        dwOptions);
      ReleaseSRWLockShared(v15);
      BroadcastDVRTraceProvider::KGLLoaded<unsigned long &,long &>(v4 + 44, v5);
      if ( v9 )
        WindowsDeleteString(v9);
      if ( v16 )
        WindowsDeleteString(v16);
      return *(unsigned int *)Data;
    }
    v29 = DWORD1(v42);
    if ( DWORD1(v42) >= 2 )
    {
      v27 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(**(_QWORD **)(v23 + 24) + 104LL))(
              *(_QWORD *)(v23 + 24),
              &v44);
      *(_DWORD *)Data = v27;
      if ( v27 < 0 )
      {
        v28 = 734;
        goto LABEL_28;
      }
      v27 = (*(__int64 (__fastcall **)(_QWORD, __int64, char *))(**(_QWORD **)(v23 + 16) + 88LL))(
              *(_QWORD *)(v23 + 16),
              2,
              (char *)&v45 + 12);
      *(_DWORD *)Data = v27;
      if ( v27 < 0 )
      {
        v28 = 736;
        goto LABEL_28;
      }
      v29 = DWORD1(v42);
    }
    if ( v29 >= 3 )
    {
      memset_0(v46, 0, 0x2B8u);
      v27 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**(_QWORD **)(v23 + 24) + 112LL))(*(_QWORD *)(v23 + 24), v46);
      *(_DWORD *)Data = v27;
      if ( v27 < 0 )
      {
        v28 = 743;
        goto LABEL_28;
      }
      v27 = (*(__int64 (__fastcall **)(_QWORD, __int64, _BYTE *))(**(_QWORD **)(v23 + 16) + 88LL))(
              *(_QWORD *)(v23 + 16),
              3,
              v47);
      *(_DWORD *)Data = v27;
      if ( v27 < 0 )
      {
        v28 = 745;
        goto LABEL_28;
      }
      v27 = (*(__int64 (__fastcall **)(_QWORD, __int64, _BYTE *, __int64))(**(_QWORD **)(v23 + 16) + 88LL))(
              *(_QWORD *)(v23 + 16),
              4,
              v48,
              624);
      *(_DWORD *)Data = v27;
      if ( v27 < 0 )
      {
        v28 = 746;
        goto LABEL_28;
      }
      v29 = DWORD1(v42);
    }
    if ( v29 >= 4 )
    {
      memset_0(v46, 0, 0x2C0u);
      v27 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**(_QWORD **)(v23 + 24) + 120LL))(*(_QWORD *)(v23 + 24), v46);
      *(_DWORD *)Data = v27;
      if ( v27 < 0 )
      {
        v28 = 752;
        goto LABEL_28;
      }
      v27 = (*(__int64 (__fastcall **)(_QWORD, __int64, _BYTE *))(**(_QWORD **)(v23 + 16) + 88LL))(
              *(_QWORD *)(v23 + 16),
              6,
              v49);
      *(_DWORD *)Data = v27;
      if ( v27 < 0 )
      {
        v28 = 754;
        goto LABEL_28;
      }
      v27 = (*(__int64 (__fastcall **)(_QWORD, __int64, _BYTE *))(**(_QWORD **)(v23 + 16) + 88LL))(
              *(_QWORD *)(v23 + 16),
              7,
              v50);
      *(_DWORD *)Data = v27;
      if ( v27 < 0 )
      {
        v28 = 755;
        goto LABEL_28;
      }
      v29 = DWORD1(v42);
    }
    if ( v29 >= 5 )
    {
      memset_0(v46, 0, 0x2C4u);
      v27 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**(_QWORD **)(v23 + 24) + 128LL))(*(_QWORD *)(v23 + 24), v46);
      *(_DWORD *)Data = v27;
      if ( v27 < 0 )
      {
        v28 = 761;
        goto LABEL_28;
      }
      v27 = (*(__int64 (__fastcall **)(_QWORD, __int64, _BYTE *))(**(_QWORD **)(v23 + 16) + 88LL))(
              *(_QWORD *)(v23 + 16),
              8,
              v51);
      *(_DWORD *)Data = v27;
      if ( v27 < 0 )
      {
        v28 = 763;
        goto LABEL_28;
      }
    }
  }
  *(_DWORD *)Data = *(_DWORD *)(v23 + 44);
  string = 0;
  v30 = -2147483647;
  if ( !aSoftwareMicros_21[0] )
  {
    string = (HSTRING)-2147483647LL;
LABEL_64:
    Key = RegSetValueExW((HKEY)v30, L"KGLRevision", 0, 4u, Data, 4u);
    if ( string != (HSTRING)-2147483647LL )
      RegCloseKey((HKEY)string);
    goto LABEL_66;
  }
  Key = RegCreateKeyExW(
          HKEY_CURRENT_USER,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\GameDVR",
          0,
          0,
          0,
          2u,
          0,
          (PHKEY)&string,
          0);
  if ( !Key )
  {
    v30 = (__int64)string;
    goto LABEL_64;
  }
LABEL_66:
  if ( Key > 0 )
    Key = (unsigned __int16)Key | 0x80070000;
  if ( Key < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x2FF,
      (unsigned int)"pcshell\\twinui\\broadcastdvrcomponent\\lib\\isgamemanager.cpp",
      (const char *)(unsigned int)Key,
      dwOptionsa);
  ReleaseSRWLockShared(v15);
LABEL_71:
  BroadcastDVRTraceProvider::KGLLoaded<unsigned long &,long &>(v4 + 44, v5);
  if ( v9 )
    WindowsDeleteString(v9);
  if ( v16 )
    WindowsDeleteString(v16);
  return 0;
}

```

## disassembly

```asm
0x18011ecd8  push    rbp
0x18011ecda  push    rbx
0x18011ecdb  push    rsi
0x18011ecdc  push    rdi
0x18011ecdd  push    r12
0x18011ecdf  push    r13
0x18011ece1  push    r14
0x18011ece3  push    r15
0x18011ece5  lea     rbp, [rsp-2C8h]
0x18011eced  sub     rsp, 3C8h
0x18011ecf4  mov     rax, cs:__security_cookie
0x18011ecfb  xor     rax, rsp
0x18011ecfe  mov     [rbp+300h+var_50], rax
0x18011ed05  mov     [rsp+400h+var_3A8], dl
0x18011ed09  mov     rbx, rcx
0x18011ed0c  mov     qword ptr [rsp+400h+Data], rcx
0x18011ed11  xor     r15d, r15d
0x18011ed14  mov     [rsp+400h+var_398], r15d
0x18011ed19  mov     [rsp+400h+var_390], r15
0x18011ed1e  mov     [rsp+400h+string], r15
0x18011ed23  lea     r8, [rsp+400h+var_398]
0x18011ed28  mov     rdx, rcx
0x18011ed2b  lea     rcx, [rbp+300h+var_380]
0x18011ed2f  call    ??0_lambda_6b6168dda817c5975ee7d3438d2331fe_@@QEAA@AEBUMeetAndChatFallbackProp@Shell@Internal@Windows@winrt@@PEBU?$vector_view_base@U?$vector_impl@UMeetAndChatFallbackProp@Shell@Internal@Windows@winrt@@V?$vector@UMeetAndChatFallbackProp@Shell@Internal@Windows@winrt@@V?$allocator@UMeetAndChatFallbackProp@Shell@Internal@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@UMeetAndChatFallbackProp@Shell@Internal@Windows@3@Ucollection_version@23@@5@@Z; _lambda_6b6168dda817c5975ee7d3438d2331fe_::_lambda_6b6168dda817c5975ee7d3438d2331fe_(winrt::Windows::Internal::Shell::MeetAndChatFallbackProp const &,winrt::vector_view_base<winrt::impl::vector_impl<winrt::Windows::Internal::Shell::MeetAndChatFallbackProp,std::vector<winrt::Windows::Internal::Shell::MeetAndChatFallbackProp>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Internal::Shell::MeetAndChatFallbackProp,winrt::impl::collection_version> const *)
0x18011ed34  mov     r13, [rax]
0x18011ed37  mov     [rbp+300h+var_370], r13
0x18011ed3b  mov     r12, [rax+8]
0x18011ed3f  mov     [rbp+300h+var_368], r12
0x18011ed43  mov     [rbp+300h+var_360], 1
0x18011ed47  lea     r9, [rsp+400h+string]; struct Windows::Internal::String *
0x18011ed4c  xor     r8d, r8d; unsigned __int16 *
0x18011ed4f  lea     rdx, aMicrosoftGamed_0; "Microsoft\\GameDVR"
0x18011ed56  lea     rcx, FOLDERID_LocalAppData; struct _GUID *
0x18011ed5d  call    ?GetKnownFolderSubFolder@@YAJAEBU_GUID@@PEBG1PEAVString@Internal@Windows@@@Z; GetKnownFolderSubFolder(_GUID const &,ushort const *,ushort const *,Windows::Internal::String *)
0x18011ed62  mov     edi, eax
0x18011ed64  test    eax, eax
0x18011ed66  jns     short loc_18011EDA9
0x18011ed68  mov     rcx, [rbp+308h]; this
0x18011ed6f  mov     r9d, eax; char *
0x18011ed72  lea     r8, aPcshellTwinuiB; "pcshell\\twinui\\broadcastdvrcomponent"...
0x18011ed79  mov     edx, 2A2h; void *
0x18011ed7e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011ed83  nop
0x18011ed84  lea     rcx, [r13+2Ch]
0x18011ed88  mov     rdx, r12
0x18011ed8b  call    ??$KGLLoaded@AEAKAEAJ@BroadcastDVRTraceProvider@@SAXAEAKAEAJ@Z; BroadcastDVRTraceProvider::KGLLoaded<ulong &,long &>(ulong &,long &)
0x18011ed90  nop
0x18011ed91  mov     rcx, [rsp+400h+string]; string
0x18011ed96  test    rcx, rcx
0x18011ed99  jz      short loc_18011EDA2
0x18011ed9b  call    cs:__imp_WindowsDeleteString
0x18011eda1  nop
0x18011eda2  mov     eax, edi
0x18011eda4  jmp     loc_18011F35C
0x18011eda9  xor     edx, edx; length
0x18011edab  mov     rdi, [rsp+400h+string]
0x18011edb0  mov     rcx, rdi; string
0x18011edb3  call    cs:__imp_WindowsGetStringRawBuffer
0x18011edb9  xor     edx, edx; lpSecurityAttributes
0x18011edbb  mov     rcx, rax; lpPathName
0x18011edbe  call    cs:__imp_CreateDirectoryW
0x18011edc4  call    ?EnsureGameDVRFolderAccess@IsGameManager@@AEAAJXZ; IsGameManager::EnsureGameDVRFolderAccess(void)
0x18011edc9  mov     rcx, [rbp+308h]; this
0x18011edd0  lea     r14, aPcshellTwinuiB; "pcshell\\twinui\\broadcastdvrcomponent"...
0x18011edd7  test    eax, eax
0x18011edd9  jns     short loc_18011EDEB
0x18011eddb  mov     r9d, eax; char *
0x18011edde  mov     r8, r14; unsigned int
0x18011ede1  mov     edx, 2A6h; void *
0x18011ede6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18011edeb  lea     r9, [rsp+400h+var_390]; struct Windows::Internal::String *
0x18011edf0  xor     r8d, r8d; unsigned __int16 *
0x18011edf3  lea     rdx, aMicrosoftGamed; "Microsoft\\GameDVR\\KnownGameList.bin"
0x18011edfa  lea     rcx, FOLDERID_LocalAppData; struct _GUID *
0x18011ee01  call    ?GetKnownFolderSubFolder@@YAJAEBU_GUID@@PEBG1PEAVString@Internal@Windows@@@Z; GetKnownFolderSubFolder(_GUID const &,ushort const *,ushort const *,Windows::Internal::String *)
0x18011ee06  mov     esi, eax
0x18011ee08  test    eax, eax
0x18011ee0a  jns     short loc_18011EE57
0x18011ee0c  mov     rcx, [rbp+308h]; this
0x18011ee13  mov     r9d, eax; char *
0x18011ee16  mov     r8, r14; unsigned int
0x18011ee19  mov     edx, 2ABh; void *
0x18011ee1e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011ee23  nop
0x18011ee24  lea     rcx, [r13+2Ch]
0x18011ee28  mov     rdx, r12
0x18011ee2b  call    ??$KGLLoaded@AEAKAEAJ@BroadcastDVRTraceProvider@@SAXAEAKAEAJ@Z; BroadcastDVRTraceProvider::KGLLoaded<ulong &,long &>(ulong &,long &)
0x18011ee30  nop
0x18011ee31  test    rdi, rdi
0x18011ee34  jz      short loc_18011EE40
0x18011ee36  mov     rcx, rdi; string
0x18011ee39  call    cs:__imp_WindowsDeleteString
0x18011ee3f  nop
0x18011ee40  mov     rcx, [rsp+400h+var_390]; string
0x18011ee45  test    rcx, rcx
0x18011ee48  jz      short loc_18011EE50
0x18011ee4a  call    cs:__imp_WindowsDeleteString
0x18011ee50  mov     eax, esi
0x18011ee52  jmp     loc_18011F35C
0x18011ee57  lea     r15, [rbx+20h]
0x18011ee5b  mov     [rbp+300h+var_380], r15
0x18011ee5f  mov     rcx, r15; SRWLock
0x18011ee62  call    cs:__imp_AcquireSRWLockExclusive
0x18011ee68  nop
0x18011ee69  xor     edx, edx; length
0x18011ee6b  mov     rbx, [rsp+400h+var_390]
0x18011ee70  mov     rcx, rbx; string
0x18011ee73  call    cs:__imp_WindowsGetStringRawBuffer
0x18011ee79  mov     rsi, rax
0x18011ee7c  mov     rax, qword ptr [rsp+400h+Data]
0x18011ee81  add     rax, 18h
0x18011ee85  mov     [rsp+400h+var_388], rax
0x18011ee8a  mov     rcx, rax
0x18011ee8d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18011ee92  mov     rdx, rsi; struct KnownGameList::IQueryKnownGameList **
0x18011ee95  mov     rsi, [rsp+400h+var_388]
0x18011ee9a  mov     rcx, rsi; this
0x18011ee9d  call    ?CreateQueryKnownGameListInstance@KnownGameList@@YAJPEAPEAUIQueryKnownGameList@1@PEBG@Z; KnownGameList::CreateQueryKnownGameListInstance(KnownGameList::IQueryKnownGameList * *,ushort const *)
0x18011eea2  mov     [rsp+400h+var_398], eax
0x18011eea6  lea     ecx, [rax+7FF8FFFEh]
0x18011eeac  cmp     ecx, 1
0x18011eeaf  jbe     short loc_18011EED4
0x18011eeb1  cmp     eax, 80070057h
0x18011eeb6  jz      short loc_18011EED4
0x18011eeb8  mov     rcx, [rbp+308h]; this
0x18011eebf  test    eax, eax
0x18011eec1  jns     short loc_18011EED4
0x18011eec3  mov     r9d, eax; char *
0x18011eec6  mov     r8, r14; unsigned int
0x18011eec9  mov     edx, 2B4h; void *
0x18011eece  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18011eed3  nop
0x18011eed4  mov     rcx, r15; SRWLock
0x18011eed7  call    cs:__imp_ReleaseSRWLockExclusive
0x18011eedd  cmp     [rsp+400h+var_398], 0
0x18011eee2  jl      loc_18011F330
0x18011eee8  xorps   xmm0, xmm0
0x18011eeeb  xor     eax, eax
0x18011eeed  movups  [rbp+300h+var_358], xmm0
0x18011eef1  mov     [rbp+300h+var_348], rax
0x18011eef5  xorps   xmm1, xmm1
0x18011eef8  movups  [rbp+300h+var_340], xmm1
0x18011eefc  movups  [rbp+300h+var_330], xmm1
0x18011ef00  mov     [rbp+300h+var_380], r15
0x18011ef04  mov     rcx, r15; SRWLock
0x18011ef07  call    cs:__imp_AcquireSRWLockShared
0x18011ef0d  nop
0x18011ef0e  mov     rcx, [rsi]
0x18011ef11  mov     rsi, qword ptr [rsp+400h+Data]
0x18011ef16  lea     rdx, [rsi+2Ch]
0x18011ef1a  mov     rax, [rcx]
0x18011ef1d  mov     rax, [rax+50h]
0x18011ef21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011ef26  cmp     [rsp+400h+var_3A8], 0
0x18011ef2b  jz      loc_18011F25E
0x18011ef31  call    cs:__imp_GetTickCount64
0x18011ef37  add     rax, 7530h
0x18011ef3d  mov     [rsi+68h], rax
0x18011ef41  mov     rcx, rsi; this
0x18011ef44  call    ?UpdateGameConfigStoreFromKGL@IsGameManager@@AEAAJXZ; IsGameManager::UpdateGameConfigStoreFromKGL(void)
0x18011ef49  mov     rcx, [rbp+308h]; this
0x18011ef50  test    eax, eax
0x18011ef52  jns     short loc_18011EF64
0x18011ef54  mov     r9d, eax; char *
0x18011ef57  mov     r8, r14; unsigned int
0x18011ef5a  mov     edx, 2CCh; void *
0x18011ef5f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18011ef64  mov     rcx, rsi; this
0x18011ef67  call    ?ScanKGLForFSECompat@IsGameManager@@AEAAJXZ; IsGameManager::ScanKGLForFSECompat(void)
0x18011ef6c  mov     rcx, [rbp+308h]; this
0x18011ef73  test    eax, eax
0x18011ef75  jns     short loc_18011EF87
0x18011ef77  mov     r9d, eax; char *
0x18011ef7a  mov     r8, r14; unsigned int
0x18011ef7d  mov     edx, 2CEh; void *
0x18011ef82  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18011ef87  xor     edx, edx; dwMilliseconds
0x18011ef89  mov     rcx, [rsi+60h]; hHandle
0x18011ef8d  call    cs:__imp_WaitForSingleObject
0x18011ef93  test    eax, eax
0x18011ef95  jz      short loc_18011EFD0
0x18011ef97  mov     r9d, [rsi+2Ch]; unsigned int
0x18011ef9b  lea     r8, aKgltogcsupdate; "KGLToGCSUpdatedRevision"
0x18011efa2  lea     rdx, aSoftwareMicros_21; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18011efa9  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x18011efb0  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x18011efb5  mov     rcx, [rbp+308h]; this
0x18011efbc  test    eax, eax
0x18011efbe  jns     short loc_18011EFD0
0x18011efc0  mov     r9d, eax; char *
0x18011efc3  mov     r8, r14; unsigned int
0x18011efc6  mov     edx, 2D5h; void *
0x18011efcb  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18011efd0  mov     rcx, [rsi+18h]
0x18011efd4  mov     rax, [rcx]
0x18011efd7  lea     rdx, [rbp+300h+var_358]
0x18011efdb  mov     rax, [rax+48h]
0x18011efdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011efe4  mov     dword ptr [rsp+400h+Data], eax
0x18011efe8  test    eax, eax
0x18011efea  jns     short loc_18011F041
0x18011efec  mov     edx, 2D8h; void *
0x18011eff1  mov     r8, r14; unsigned int
0x18011eff4  mov     r9d, eax; char *
0x18011eff7  mov     rcx, [rbp+308h]; this
0x18011effe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011f003  nop
0x18011f004  mov     rcx, r15; SRWLock
0x18011f007  call    cs:__imp_ReleaseSRWLockShared
0x18011f00d  nop
0x18011f00e  mov     rdx, r12
0x18011f011  lea     rcx, [r13+2Ch]
0x18011f015  call    ??$KGLLoaded@AEAKAEAJ@BroadcastDVRTraceProvider@@SAXAEAKAEAJ@Z; BroadcastDVRTraceProvider::KGLLoaded<ulong &,long &>(ulong &,long &)
0x18011f01a  nop
0x18011f01b  test    rdi, rdi
0x18011f01e  jz      short loc_18011F02A
0x18011f020  mov     rcx, rdi; string
0x18011f023  call    cs:__imp_WindowsDeleteString
0x18011f029  nop
0x18011f02a  test    rbx, rbx
0x18011f02d  jz      short loc_18011F038
0x18011f02f  mov     rcx, rbx; string
0x18011f032  call    cs:__imp_WindowsDeleteString
0x18011f038  mov     eax, dword ptr [rsp+400h+Data]
0x18011f03c  jmp     loc_18011F35C
0x18011f041  mov     eax, dword ptr [rbp+300h+var_358+4]
0x18011f044  cmp     eax, 2
0x18011f047  jb      short loc_18011F09F
0x18011f049  mov     rcx, [rsi+18h]
0x18011f04d  mov     rax, [rcx]
0x18011f050  lea     rdx, [rbp+300h+var_340]
0x18011f054  mov     rax, [rax+68h]
0x18011f058  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011f05d  mov     dword ptr [rsp+400h+Data], eax
0x18011f061  test    eax, eax
0x18011f063  jns     short loc_18011F06C
0x18011f065  mov     edx, 2DEh
0x18011f06a  jmp     short loc_18011EFF1
0x18011f06c  mov     rcx, [rsi+10h]
0x18011f070  mov     rax, [rcx]
0x18011f073  mov     r9d, 4
0x18011f079  lea     r8, [rbp+300h+var_330+0Ch]
0x18011f07d  lea     edx, [r9-2]
0x18011f081  mov     rax, [rax+58h]
0x18011f085  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011f08a  mov     dword ptr [rsp+400h+Data], eax
0x18011f08e  test    eax, eax
0x18011f090  jns     short loc_18011F09C
0x18011f092  mov     edx, 2E0h
0x18011f097  jmp     loc_18011EFF1
0x18011f09c  mov     eax, dword ptr [rbp+300h+var_358+4]
0x18011f09f  cmp     eax, 3
0x18011f0a2  jb      loc_18011F143
0x18011f0a8  xor     edx, edx; Val
0x18011f0aa  mov     r8d, 2B8h; Size
0x18011f0b0  lea     rcx, [rbp+300h+var_320]; void *
0x18011f0b4  call    memset_0
0x18011f0b9  mov     rcx, [rsi+18h]
0x18011f0bd  mov     rax, [rcx]
0x18011f0c0  lea     rdx, [rbp+300h+var_320]
0x18011f0c4  mov     rax, [rax+70h]
0x18011f0c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011f0cd  mov     dword ptr [rsp+400h+Data], eax
0x18011f0d1  test    eax, eax
0x18011f0d3  jns     short loc_18011F0DF
0x18011f0d5  mov     edx, 2E7h
0x18011f0da  jmp     loc_18011EFF1
0x18011f0df  mov     rcx, [rsi+10h]
0x18011f0e3  mov     rax, [rcx]
0x18011f0e6  mov     r9d, 28h ; '('
0x18011f0ec  lea     r8, [rbp+300h+var_300]
0x18011f0f0  lea     edx, [r9-25h]
0x18011f0f4  mov     rax, [rax+58h]
0x18011f0f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011f0fd  mov     dword ptr [rsp+400h+Data], eax
0x18011f101  test    eax, eax
0x18011f103  jns     short loc_18011F10F
0x18011f105  mov     edx, 2E9h
0x18011f10a  jmp     loc_18011EFF1
0x18011f10f  mov     rcx, [rsi+10h]
0x18011f113  mov     rax, [rcx]
0x18011f116  mov     r9d, 270h
0x18011f11c  lea     r8, [rbp+300h+var_2D8]
0x18011f120  mov     edx, 4
0x18011f125  mov     rax, [rax+58h]
0x18011f129  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011f12e  mov     dword ptr [rsp+400h+Data], eax
0x18011f132  test    eax, eax
0x18011f134  jns     short loc_18011F140
0x18011f136  mov     edx, 2EAh
0x18011f13b  jmp     loc_18011EFF1
0x18011f140  mov     eax, dword ptr [rbp+300h+var_358+4]
0x18011f143  cmp     eax, 4
0x18011f146  jb      loc_18011F1EC
0x18011f14c  xor     edx, edx; Val
0x18011f14e  mov     r8d, 2C0h; Size
0x18011f154  lea     rcx, [rbp+300h+var_320]; void *
0x18011f158  call    memset_0
0x18011f15d  mov     rcx, [rsi+18h]
0x18011f161  mov     rax, [rcx]
  ... truncated ...
```
