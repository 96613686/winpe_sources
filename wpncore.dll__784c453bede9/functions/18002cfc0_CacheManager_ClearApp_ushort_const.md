# CacheManager::ClearApp(ushort const *)

- ea: `0x18002cfc0`
- end: `0x18002d3cf`
- name: `?ClearApp@CacheManager@@UEAAJPEBG@Z`
- size: `1039`
- prototype: `__int64 __fastcall(CacheManager *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800117c0`
- `0x1800193e8`
- `0x180020f48`
- `0x18002cfc0`
- `0x18002d3d8`
- `0x18002e450`
- `0x18002e730`
- `0x18002ee38`
- `0x1800307d0`
- `0x180061ba8`
- `0x180080548`
- `0x1800af0a4`
- `0x1800b99f0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18002d084`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18002d084`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002d19e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002d19e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002d020`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002d020`

## string_xrefs

- `0x18002d0d2`: `onecoreuap\base\diagnosis\platform\notifications\platform\ui\cachemetadatastorage.cpp`
- `0x18002d336`: `onecoreuap\base\diagnosis\platform\notifications\platform\ui\cachemetadatastorage.cpp`
- `0x18002d10f`: `CacheMetadataStorage::FindNextUrlCacheEntry`
- `0x18002d35d`: `CacheMetadataStorage::FindNextUrlCacheEntry`
- `0x18002d0fc`: `onecoreuap\base\diagnosis\platform\notifications\platform\ui\cachemetadatastorage.cpp`
- `0x18002d364`: `onecoreuap\base\diagnosis\platform\notifications\platform\ui\cachemetadatastorage.cpp`
- `0x18002d20b`: `onecoreuap\base\diagnosis\platform\notifications\platform\ui\cachemanager.cpp`
- `0x18002d257`: `onecoreuap\base\diagnosis\platform\notifications\platform\ui\cachemanager.cpp`
- `0x18002d2a2`: `onecoreuap\base\diagnosis\platform\notifications\platform\ui\cachemanager.cpp`
- `0x18002d37f`: `onecoreuap\base\diagnosis\platform\notifications\platform\ui\cachemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CacheManager::ClearApp(CacheManager *this, const unsigned __int16 *a2)
{
  int FirstUrlCacheEntry; // eax
  unsigned int v5; // edi
  int v6; // r15d
  _QWORD *v7; // rcx
  __int64 v8; // rcx
  struct RegistryHelper *v9; // rbx
  char v10; // r14
  int v11; // eax
  CacheMetadataStorage *v12; // rcx
  __int64 v13; // r8
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // r9
  const unsigned __int16 *v18; // r8
  const unsigned __int16 *v19; // rdx
  int UrlCacheEntryInfo; // eax
  unsigned int v21; // ecx
  int *v22; // [rsp+20h] [rbp-E0h]
  bool v23; // [rsp+30h] [rbp-D0h] BYREF
  struct RegistryHelper *v24; // [rsp+38h] [rbp-C8h] BYREF
  int v25; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v26; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v27[4]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v28[4]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *v29[10]; // [rsp+90h] [rbp-70h] BYREF
  int v30; // [rsp+E0h] [rbp-20h] BYREF
  const unsigned __int16 *v31; // [rsp+F0h] [rbp-10h]
  __int64 v32; // [rsp+F8h] [rbp-8h]
  const unsigned __int16 *v33; // [rsp+100h] [rbp+0h]
  __int64 v34; // [rsp+108h] [rbp+8h]
  int *v35; // [rsp+110h] [rbp+10h]
  __int64 v36; // [rsp+118h] [rbp+18h]
  unsigned int *v37; // [rsp+120h] [rbp+20h]
  __int64 v38; // [rsp+128h] [rbp+28h]
  const WCHAR *v39; // [rsp+130h] [rbp+30h]
  __int64 v40; // [rsp+138h] [rbp+38h]
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]

  v24 = 0;
  v23 = 0;
  std::wstring::wstring(v27);
  std::wstring::wstring(v28);
  std::wstring::wstring(v29);
  AcquireSRWLockShared((PSRWLOCK)this + 2);
  if ( !a2 )
  {
    v5 = -2147024809;
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x322,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\cachemanager.cpp",
      (const char *)0x80070057LL,
      (int)v22);
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    {
      v16 = 35;
      v17 = 2147942487LL;
      goto LABEL_40;
    }
    goto LABEL_17;
  }
  FirstUrlCacheEntry = CacheMetadataStorage::FindFirstUrlCacheEntry(
                         *((CacheMetadataStorage **)this + 11),
                         (struct CacheEntry *)v27,
                         (void **)&v24,
                         &v23);
  v5 = FirstUrlCacheEntry;
  if ( FirstUrlCacheEntry < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x325,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\cachemanager.cpp",
      (const char *)(unsigned int)FirstUrlCacheEntry,
      (int)v22);
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    {
      v16 = 36;
      goto LABEL_39;
    }
    goto LABEL_17;
  }
  if ( v23 )
  {
    v6 = (int)v24;
    while ( v27[3] > 7u )
    {
      v7 = (_QWORD *)v27[0];
      if ( v27[0] )
        goto LABEL_7;
LABEL_29:
      v18 = (const unsigned __int16 *)v28;
      if ( v28[3] > (unsigned __int16 *)7 )
        v18 = v28[0];
      v19 = (const unsigned __int16 *)v29;
      if ( v29[3] > (unsigned __int16 *)7 )
        v19 = v29[0];
      CacheMetadataStorage::DeleteUrlCacheEntry(*((CacheMetadataStorage **)this + 11), v19, v18);
LABEL_8:
      v9 = 0;
      v24 = 0;
      if ( v6 )
      {
        v10 = 1;
        v11 = RegistryHelper::OpenSubKeyByIndex(*(_QWORD *)(*((_QWORD *)this + 11) + 16LL), (unsigned int)--v6, &v24);
        v5 = v11;
        if ( v11 >= 0 )
        {
          v9 = v24;
          UrlCacheEntryInfo = CacheMetadataStorage::GetUrlCacheEntryInfo(v12, (HKEY *)v24, (struct CacheEntry *)v27);
          v5 = UrlCacheEntryInfo;
          if ( UrlCacheEntryInfo < 0 )
          {
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x113,
              (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\cachemetadatastorage.cpp",
              (const char *)(unsigned int)UrlCacheEntryInfo,
              (int)v22);
            WpnDebugTrace(
              v21,
              L"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\cachemetadatastorage.cpp",
              L"CacheMetadataStorage::FindNextUrlCacheEntry",
              275,
              v5,
              &word_180124798);
          }
        }
        else
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x110,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\cachemetadatastorage.cpp",
            (const char *)(unsigned int)v11,
            (int)v22);
          if ( (Microsoft_Windows_PushNotifications_PlatformEnableBits & 1) != 0 )
          {
            v26 = v5;
            v25 = 272;
            v31 = L"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\cachemetadatastorage.cpp";
            v32 = 172;
            v33 = L"CacheMetadataStorage::FindNextUrlCacheEntry";
            v34 = 88;
            v35 = &v25;
            v36 = 4;
            v37 = &v26;
            v38 = 4;
            v39 = &word_180124798;
            v40 = 2;
            v22 = &v30;
            McGenEventWrite_EventWriteTransfer(&WPNCORE_PROVIDER_GUID_Context, WPNCORE_EVENT_DEBUG, v13, 6);
          }
          v9 = v24;
        }
      }
      else
      {
        v5 = 0;
        v10 = 0;
      }
      if ( v9 )
        std::default_delete<NotificationPlatform>::operator()(v8, v9);
      if ( (v5 & 0x80000000) != 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x343,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\cachemanager.cpp",
          (const char *)v5,
          (int)v22);
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
        {
          v16 = 39;
LABEL_39:
          v17 = v5;
LABEL_40:
          WPP_SF_d(v15[2], v16, WPP_54d166b4b7773830bae608bc87214534_Traceguids, v17);
        }
        goto LABEL_17;
      }
      if ( !v10 )
        goto LABEL_17;
    }
    v7 = v27;
LABEL_7:
    if ( (unsigned int)_o__wcsnicmp(v7, a2, 130) )
      goto LABEL_8;
    goto LABEL_29;
  }
  v5 = -2147024894;
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x32A,
    (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\cachemanager.cpp",
    (const char *)0x80070002LL,
    (int)v22);
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
  {
    v16 = 37;
    v17 = 2147942402LL;
    goto LABEL_40;
  }
LABEL_17:
  ReleaseSRWLockShared((PSRWLOCK)this + 2);
  std::pair<std::wstring const,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>::~pair<std::wstring const,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>(v29);
  std::pair<std::wstring const,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>::~pair<std::wstring const,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>(v28);
  std::pair<std::wstring const,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>::~pair<std::wstring const,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>(v27);
  return v5;
}

```

## disassembly

```asm
0x18002cfc0  mov     [rsp-8+arg_10], rbx
0x18002cfc5  push    rbp
0x18002cfc6  push    rsi
0x18002cfc7  push    rdi
0x18002cfc8  push    r12
0x18002cfca  push    r13
0x18002cfcc  push    r14
0x18002cfce  push    r15
0x18002cfd0  lea     rbp, [rsp-50h]
0x18002cfd5  sub     rsp, 150h
0x18002cfdc  mov     rax, cs:__security_cookie
0x18002cfe3  xor     rax, rsp
0x18002cfe6  mov     [rbp+80h+var_40], rax
0x18002cfea  mov     r12, rdx
0x18002cfed  mov     rsi, rcx
0x18002cff0  mov     [rsp+180h+var_148], 0
0x18002cff9  mov     [rsp+180h+var_150], 0
0x18002cffe  lea     rcx, [rsp+180h+var_130]
0x18002d003  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002d008  lea     rcx, [rsp+180h+var_110]
0x18002d00d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002d012  lea     rcx, [rbp+80h+var_F0]
0x18002d016  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002d01b  nop
0x18002d01c  lea     rcx, [rsi+10h]; SRWLock
0x18002d020  call    cs:__imp_AcquireSRWLockShared
0x18002d026  test    r12, r12
0x18002d029  jz      loc_18002D1FC
0x18002d02f  lea     r9, [rsp+180h+var_150]; bool *
0x18002d034  lea     r8, [rsp+180h+var_148]; void **
0x18002d039  lea     rdx, [rsp+180h+var_130]; struct CacheEntry *
0x18002d03e  mov     rcx, [rsi+58h]; this
0x18002d042  call    ?FindFirstUrlCacheEntry@CacheMetadataStorage@@QEAAJAEAVCacheEntry@@AEAPEAXAEA_N@Z; CacheMetadataStorage::FindFirstUrlCacheEntry(CacheEntry &,void * &,bool &)
0x18002d047  mov     edi, eax
0x18002d049  test    eax, eax
0x18002d04b  js      loc_18002D24D
0x18002d051  cmp     [rsp+180h+var_150], 0
0x18002d056  jz      loc_18002D293
0x18002d05c  mov     r15, [rsp+180h+var_148]
0x18002d061  cmp     [rsp+180h+var_118], 7
0x18002d067  jbe     loc_18002D1EB
0x18002d06d  mov     rcx, [rsp+180h+var_130]
0x18002d072  test    rcx, rcx
0x18002d075  jz      loc_18002D2E4
0x18002d07b  mov     r8d, 82h
0x18002d081  mov     rdx, r12
0x18002d084  call    cs:__imp__o__wcsnicmp
0x18002d08a  test    eax, eax
0x18002d08c  jz      loc_18002D2E4
0x18002d092  xor     ebx, ebx
0x18002d094  mov     [rsp+180h+var_148], rbx
0x18002d099  test    r15d, r15d
0x18002d09c  jz      loc_18002D1F5
0x18002d0a2  mov     r14b, 1
0x18002d0a5  lea     edx, [r15-1]
0x18002d0a9  mov     r15d, edx
0x18002d0ac  mov     rcx, [rsi+58h]
0x18002d0b0  lea     r8, [rsp+180h+var_148]
0x18002d0b5  mov     rcx, [rcx+10h]
0x18002d0b9  call    ?OpenSubKeyByIndex@RegistryHelper@@QEAAJKAEAV?$unique_ptr@VRegistryHelper@@U?$default_delete@VRegistryHelper@@@std@@@std@@@Z; RegistryHelper::OpenSubKeyByIndex(ulong,std::unique_ptr<RegistryHelper> &)
0x18002d0be  mov     edi, eax
0x18002d0c0  test    eax, eax
0x18002d0c2  jns     loc_18002D310
0x18002d0c8  mov     rcx, [rbp+88h]; this
0x18002d0cf  mov     r9d, eax; char *
0x18002d0d2  lea     r8, aOnecoreuapBase_76; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18002d0d9  mov     edx, 110h; void *
0x18002d0de  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002d0e3  test    cs:Microsoft_Windows_PushNotifications_PlatformEnableBits, r14b
0x18002d0ea  jz      loc_18002D177
0x18002d0f0  mov     [rsp+180h+var_138], edi
0x18002d0f4  mov     [rsp+180h+var_140], 110h
0x18002d0fc  lea     rax, aOnecoreuapBase_95; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18002d103  mov     [rbp+80h+var_90], rax
0x18002d107  mov     [rbp+80h+var_88], 0ACh
0x18002d10f  lea     rax, aCachemetadatas_2; "CacheMetadataStorage::FindNextUrlCacheE"...
0x18002d116  mov     [rbp+80h+var_80], rax
0x18002d11a  mov     [rbp+80h+var_78], 58h ; 'X'
0x18002d122  lea     rax, [rsp+180h+var_140]
0x18002d127  mov     [rbp+80h+var_70], rax
0x18002d12b  mov     [rbp+80h+var_68], 4
0x18002d133  lea     rax, [rsp+180h+var_138]
0x18002d138  mov     [rbp+80h+var_60], rax
0x18002d13c  mov     [rbp+80h+var_58], 4
0x18002d144  lea     rax, word_180124798
0x18002d14b  mov     [rbp+80h+var_50], rax
0x18002d14f  mov     [rbp+80h+var_48], 2
0x18002d157  lea     rax, [rbp+80h+var_A0]
0x18002d15b  mov     qword ptr [rsp+180h+var_160], rax; int
0x18002d160  lea     r9d, [rbx+6]
0x18002d164  lea     rdx, WPNCORE_EVENT_DEBUG
0x18002d16b  lea     rcx, WPNCORE_PROVIDER_GUID_Context
0x18002d172  call    McGenEventWrite_EventWriteTransfer
0x18002d177  mov     rbx, [rsp+180h+var_148]
0x18002d17c  test    rbx, rbx
0x18002d17f  jz      short loc_18002D189
0x18002d181  mov     rdx, rbx
0x18002d184  call    ??R?$default_delete@VNotificationPlatform@@@std@@QEBAXPEAVNotificationPlatform@@@Z; std::default_delete<NotificationPlatform>::operator()(NotificationPlatform *)
0x18002d189  test    edi, edi
0x18002d18b  js      loc_18002D375
0x18002d191  test    r14b, r14b
0x18002d194  jnz     loc_18002D061
0x18002d19a  lea     rcx, [rsi+10h]; SRWLock
0x18002d19e  call    cs:__imp_ReleaseSRWLockShared
0x18002d1a4  nop
0x18002d1a5  lea     rcx, [rbp+80h+var_F0]; void *
0x18002d1a9  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4__MIDL___MIDL_itf_wpntypes_0000_0000_0005@@@std@@QEAA@XZ; std::pair<std::wstring const,__MIDL___MIDL_itf_wpntypes_0000_0000_0005>::~pair<std::wstring const,__MIDL___MIDL_itf_wpntypes_0000_0000_0005>(void)
0x18002d1ae  lea     rcx, [rsp+180h+var_110]; void *
0x18002d1b3  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4__MIDL___MIDL_itf_wpntypes_0000_0000_0005@@@std@@QEAA@XZ; std::pair<std::wstring const,__MIDL___MIDL_itf_wpntypes_0000_0000_0005>::~pair<std::wstring const,__MIDL___MIDL_itf_wpntypes_0000_0000_0005>(void)
0x18002d1b8  lea     rcx, [rsp+180h+var_130]; void *
0x18002d1bd  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4__MIDL___MIDL_itf_wpntypes_0000_0000_0005@@@std@@QEAA@XZ; std::pair<std::wstring const,__MIDL___MIDL_itf_wpntypes_0000_0000_0005>::~pair<std::wstring const,__MIDL___MIDL_itf_wpntypes_0000_0000_0005>(void)
0x18002d1c2  mov     eax, edi
0x18002d1c4  mov     rcx, [rbp+80h+var_40]
0x18002d1c8  xor     rcx, rsp; StackCookie
0x18002d1cb  call    __security_check_cookie
0x18002d1d0  mov     rbx, [rsp+180h+arg_10]
0x18002d1d8  add     rsp, 150h
0x18002d1df  pop     r15
0x18002d1e1  pop     r14
0x18002d1e3  pop     r13
0x18002d1e5  pop     r12
0x18002d1e7  pop     rdi
0x18002d1e8  pop     rsi
0x18002d1e9  pop     rbp
0x18002d1ea  retn
0x18002d1eb  lea     rcx, [rsp+180h+var_130]
0x18002d1f0  jmp     loc_18002D07B
0x18002d1f5  xor     edi, edi
0x18002d1f7  xor     r14b, r14b
0x18002d1fa  jmp     short loc_18002D17C
0x18002d1fc  mov     edi, 80070057h
0x18002d201  mov     rcx, [rbp+88h]; this
0x18002d208  mov     r9d, edi; char *
0x18002d20b  lea     r8, aOnecoreuapBase_64; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18002d212  mov     edx, 322h; void *
0x18002d217  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002d21c  lea     rax, WPP_GLOBAL_Control
0x18002d223  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d22a  cmp     rcx, rax
0x18002d22d  jz      loc_18002D19A
0x18002d233  test    byte ptr [rcx+1Ch], 80h
0x18002d237  jz      loc_18002D19A
0x18002d23d  mov     edx, 23h ; '#'
0x18002d242  mov     r9d, 80070057h
0x18002d248  jmp     loc_18002D3B9
0x18002d24d  mov     rcx, [rbp+88h]; this
0x18002d254  mov     r9d, edi; char *
0x18002d257  lea     r8, aOnecoreuapBase_64; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18002d25e  mov     edx, 325h; void *
0x18002d263  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002d268  lea     rax, WPP_GLOBAL_Control
0x18002d26f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d276  cmp     rcx, rax
0x18002d279  jz      loc_18002D19A
0x18002d27f  test    byte ptr [rcx+1Ch], 80h
0x18002d283  jz      loc_18002D19A
0x18002d289  mov     edx, 24h ; '$'
0x18002d28e  jmp     loc_18002D3B6
0x18002d293  mov     edi, 80070002h
0x18002d298  mov     rcx, [rbp+88h]; this
0x18002d29f  mov     r9d, edi; char *
0x18002d2a2  lea     r8, aOnecoreuapBase_64; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18002d2a9  mov     edx, 32Ah; void *
0x18002d2ae  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002d2b3  lea     rax, WPP_GLOBAL_Control
0x18002d2ba  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d2c1  cmp     rcx, rax
0x18002d2c4  jz      loc_18002D19A
0x18002d2ca  test    byte ptr [rcx+1Ch], 80h
0x18002d2ce  jz      loc_18002D19A
0x18002d2d4  mov     edx, 25h ; '%'
0x18002d2d9  mov     r9d, 80070002h
0x18002d2df  jmp     loc_18002D3B9
0x18002d2e4  lea     r8, [rsp+180h+var_110]
0x18002d2e9  cmp     [rbp+80h+var_F8], 7
0x18002d2ee  cmova   r8, [rsp+180h+var_110]; unsigned __int16 *
0x18002d2f4  lea     rdx, [rbp+80h+var_F0]
0x18002d2f8  cmp     [rbp+80h+var_D8], 7
0x18002d2fd  cmova   rdx, [rbp+80h+var_F0]; unsigned __int16 *
0x18002d302  mov     rcx, [rsi+58h]; this
0x18002d306  call    ?DeleteUrlCacheEntry@CacheMetadataStorage@@QEAAJPEBG0@Z; CacheMetadataStorage::DeleteUrlCacheEntry(ushort const *,ushort const *)
0x18002d30b  jmp     loc_18002D092
0x18002d310  lea     r8, [rsp+180h+var_130]; struct CacheEntry *
0x18002d315  mov     rbx, [rsp+180h+var_148]
0x18002d31a  mov     rdx, rbx; struct RegistryHelper *
0x18002d31d  call    ?GetUrlCacheEntryInfo@CacheMetadataStorage@@AEAAJPEAVRegistryHelper@@AEAVCacheEntry@@@Z; CacheMetadataStorage::GetUrlCacheEntryInfo(RegistryHelper *,CacheEntry &)
0x18002d322  mov     edi, eax
0x18002d324  test    eax, eax
0x18002d326  jns     loc_18002D17C
0x18002d32c  mov     rcx, [rbp+88h]; this
0x18002d333  mov     r9d, eax; char *
0x18002d336  lea     r8, aOnecoreuapBase_76; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18002d33d  mov     edx, 113h; void *
0x18002d342  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002d347  lea     rax, word_180124798
0x18002d34e  mov     [rsp+180h+var_158], rax; unsigned __int16 *
0x18002d353  mov     [rsp+180h+var_160], edi; int
0x18002d357  mov     r9d, 113h; int
0x18002d35d  lea     r8, aCachemetadatas_2; "CacheMetadataStorage::FindNextUrlCacheE"...
0x18002d364  lea     rdx, aOnecoreuapBase_95; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18002d36b  call    ?WpnDebugTrace@@YAXKPEBG0HJ0@Z; WpnDebugTrace(ulong,ushort const *,ushort const *,int,long,ushort const *)
0x18002d370  jmp     loc_18002D17C
0x18002d375  mov     rcx, [rbp+88h]; this
0x18002d37c  mov     r9d, edi; char *
0x18002d37f  lea     r8, aOnecoreuapBase_64; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18002d386  mov     edx, 343h; void *
0x18002d38b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002d390  lea     rax, WPP_GLOBAL_Control
0x18002d397  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d39e  cmp     rcx, rax
0x18002d3a1  jz      loc_18002D19A
0x18002d3a7  test    byte ptr [rcx+1Ch], 80h
0x18002d3ab  jz      loc_18002D19A
0x18002d3b1  mov     edx, 27h ; '''
0x18002d3b6  mov     r9d, edi
0x18002d3b9  lea     r8, WPP_54d166b4b7773830bae608bc87214534_Traceguids
0x18002d3c0  mov     rcx, [rcx+10h]
0x18002d3c4  call    WPP_SF_d
0x18002d3c9  jmp     loc_18002D19A
```
