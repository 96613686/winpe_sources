# CINetHttpEdge::LastRequestHandleClosed(void)

- ea: `0x180094a50`
- end: `0x180094d2b`
- name: `?LastRequestHandleClosed@CINetHttpEdge@@UEAAXXZ`
- size: `731`
- prototype: `void __fastcall(CINetHttpEdge *__hidden this)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180024a3c`
- `0x180030880`
- `0x18004e3a8`
- `0x180063d8c`
- `0x18007c510`
- `0x18008a5b0`
- `0x1800923a0`
- `0x180094a50`
- `0x18011ba3e`
- `0x18011baa0`
- `0x18011bb60`
- `0x18011c010`

## import_xrefs

- `iertutil!__imp_?GetEdgeBrowsingEnvironment@@YAPEAUIEdgeBrowsingEnvironment@@XZ` at `0x180094c92`
- `iertutil!__imp_?GetEdgeBrowsingEnvironment@@YAPEAUIEdgeBrowsingEnvironment@@XZ` at `0x180094c92`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180094b64`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180094cdf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180094b64`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180094cdf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180094b51`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180094cc4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180094b51`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180094cc4`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180094c3d`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180094c3d`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180094b8c`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180094c71`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180094b8c`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180094c71`
- `WININET!HttpCloseDependencyHandle` at `0x180094adb`
- `WININET!HttpCloseDependencyHandle` at `0x180094adb`
- `WININET!AppCacheCloseHandle` at `0x180094abe`
- `WININET!AppCacheCloseHandle` at `0x180094abe`
- `WININET!GetUrlCacheEntryInfoW` at `0x180094c27`
- `WININET!GetUrlCacheEntryInfoW` at `0x180094c27`
- `WININET!DeleteUrlCacheEntryW` at `0x180094c51`
- `WININET!DeleteUrlCacheEntryW` at `0x180094c51`

## pseudocode

```c
void __fastcall CINetHttpEdge::LastRequestHandleClosed(CINetHttpEdge *this, __int64 a2, __int64 a3)
{
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 v6; // r9
  void *v7; // rcx
  void *v8; // rcx
  char v9; // cl
  bool v10; // bl
  CTransactionManager *GlobalTransactionManager; // rax
  unsigned int v12; // r8d
  struct CTransaction *v13; // rdx
  const WCHAR *v14; // rbx
  bool v15; // si
  struct IEdgeBrowsingEnvironment *EdgeBrowsingEnvironment; // rax
  __int64 v17; // rbx
  DWORD cbCacheEntryInfo[4]; // [rsp+30h] [rbp-1048h] BYREF
  struct _INTERNET_CACHE_ENTRY_INFOW CacheEntryInfo; // [rsp+40h] [rbp-1038h] BYREF

  if ( (unsigned int)dword_180159000 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180159000, 32, a3) )
  {
    *(_QWORD *)cbCacheEntryInfo = this;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
      v4,
      (unsigned __int8 *)&unk_180144DF0,
      v5,
      v6,
      (__int64)cbCacheEntryInfo);
  }
  v7 = (void *)*((_QWORD *)this + 246);
  if ( v7 )
  {
    AppCacheCloseHandle(v7);
    *((_QWORD *)this + 246) = 0;
  }
  v8 = (void *)*((_QWORD *)this + 247);
  if ( v8 )
  {
    HttpCloseDependencyHandle(v8);
    *((_QWORD *)this + 247) = 0;
  }
  v9 = *((_BYTE *)this + 1361) ^ (*((_BYTE *)this + 1361) ^ (4 * *((_BYTE *)this + 978))) & 8;
  *((_BYTE *)this + 1361) = v9;
  if ( (v9 & 8) != 0 )
    CINetHttpEdge::ResetBindStatusCallbackServices(this);
  v10 = 1;
  if ( *((_DWORD *)this + 122) == -2146697196 )
  {
    GlobalTransactionManager = GetGlobalTransactionManager();
    v13 = (struct CTransaction *)*((_QWORD *)this + 171);
    if ( v13 )
    {
      if ( GlobalTransactionManager )
        v10 = CTransactionManager::ItemExists(GlobalTransactionManager, v13, v12);
    }
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 984));
  CINetHttpEdge::ReleaseCNetObjects(this, v10);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 984));
  if ( (*((_BYTE *)this + 1361) & 2) != 0 )
  {
    (*(void (__fastcall **)(CINetHttpEdge *))(*(_QWORD *)this + 320LL))(this);
    DeleteFileW(*((LPCWSTR *)this + 160));
    operator delete(*((void **)this + 160));
    *((_BYTE *)this + 1361) &= ~2u;
    *((_QWORD *)this + 160) = 0;
  }
  if ( (*((_BYTE *)this + 1360) & 2) != 0 )
  {
    (*(void (__fastcall **)(CINetHttpEdge *))(*(_QWORD *)this + 320LL))(this);
    v14 = (const WCHAR *)*((_QWORD *)this + 43);
    if ( v14 || (v14 = (const WCHAR *)*((_QWORD *)this + 23)) != 0 )
    {
      v15 = 0;
      if ( *((_QWORD *)this + 168) )
      {
        memset_0(&CacheEntryInfo.dwStructSize + 1, 0, 0xFFCu);
        cbCacheEntryInfo[0] = 4096;
        CacheEntryInfo.dwStructSize = 112;
        v15 = !GetUrlCacheEntryInfoW(v14, &CacheEntryInfo, cbCacheEntryInfo)
           || StrCmpICW(CacheEntryInfo.lpszLocalFileName, *((LPCWSTR *)this + 168)) != 0;
      }
      if ( !DeleteUrlCacheEntryW(v14) && *((_QWORD *)this + 168) || v15 )
        DeleteFileW(*((LPCWSTR *)this + 168));
    }
  }
  if ( (*((_BYTE *)this + 1361) & 4) != 0 )
  {
    (*(void (__fastcall **)(CINetHttpEdge *))(*(_QWORD *)this + 320LL))(this);
    EdgeBrowsingEnvironment = GetEdgeBrowsingEnvironment();
    (*(void (__fastcall **)(struct IEdgeBrowsingEnvironment *, char *))(*(_QWORD *)EdgeBrowsingEnvironment + 16LL))(
      EdgeBrowsingEnvironment,
      (char *)this + 1240);
    *(_OWORD *)((char *)this + 1240) = 0;
    *((_BYTE *)this + 1361) &= ~4u;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 984));
  v17 = *((_QWORD *)this + 157);
  *((_QWORD *)this + 157) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 984));
  if ( v17 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 24LL))(v17);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  }
  *((_BYTE *)this + 1361) |= 0x10u;
}

```

## disassembly

```asm
0x180094a50  push    rbx
0x180094a52  push    rbp
0x180094a53  push    rsi
0x180094a54  push    rdi
0x180094a55  mov     eax, 1058h
0x180094a5a  call    _alloca_probe
0x180094a5f  sub     rsp, rax
0x180094a62  mov     rax, cs:__security_cookie
0x180094a69  xor     rax, rsp
0x180094a6c  mov     [rsp+1078h+var_38], rax
0x180094a74  mov     eax, cs:dword_180159000
0x180094a7a  mov     rdi, rcx
0x180094a7d  cmp     eax, 5
0x180094a80  jbe     short loc_180094AB2
0x180094a82  mov     edx, 20h ; ' '
0x180094a87  lea     rcx, dword_180159000
0x180094a8e  call    _tlgKeywordOn
0x180094a93  test    al, al
0x180094a95  jz      short loc_180094AB2
0x180094a97  lea     rax, [rsp+1078h+cbCacheEntryInfo]
0x180094a9c  mov     qword ptr [rsp+1078h+cbCacheEntryInfo], rdi
0x180094aa1  lea     rdx, unk_180144DF0
0x180094aa8  mov     [rsp+1078h+var_1058], rax
0x180094aad  call    ??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_BrowserWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)
0x180094ab2  mov     rcx, [rdi+7B0h]; hAppCache
0x180094ab9  test    rcx, rcx
0x180094abc  jz      short loc_180094ACF
0x180094abe  call    cs:__imp_AppCacheCloseHandle
0x180094ac4  mov     qword ptr [rdi+7B0h], 0
0x180094acf  mov     rcx, [rdi+7B8h]; hDependencyHandle
0x180094ad6  test    rcx, rcx
0x180094ad9  jz      short loc_180094AEC
0x180094adb  call    cs:__imp_HttpCloseDependencyHandle
0x180094ae1  mov     qword ptr [rdi+7B8h], 0
0x180094aec  mov     al, [rdi+551h]
0x180094af2  mov     cl, [rdi+3D2h]
0x180094af8  shl     cl, 2
0x180094afb  xor     cl, al
0x180094afd  and     cl, 8
0x180094b00  xor     cl, al
0x180094b02  mov     [rdi+551h], cl
0x180094b08  test    cl, 8
0x180094b0b  jz      short loc_180094B15
0x180094b0d  mov     rcx, rdi; this
0x180094b10  call    ?ResetBindStatusCallbackServices@CINetHttpEdge@@AEAAXXZ; CINetHttpEdge::ResetBindStatusCallbackServices(void)
0x180094b15  cmp     dword ptr [rdi+1E8h], 800C0014h
0x180094b1f  mov     bl, 1
0x180094b21  jnz     short loc_180094B47
0x180094b23  call    ?GetGlobalTransactionManager@@YAPEAVCTransactionManager@@XZ; GetGlobalTransactionManager(void)
0x180094b28  mov     rdx, [rdi+558h]; struct CTransaction *
0x180094b2f  test    rdx, rdx
0x180094b32  jz      short loc_180094B47
0x180094b34  test    rax, rax
0x180094b37  jz      short loc_180094B47
0x180094b39  mov     rcx, rax; this
0x180094b3c  call    ?ItemExists@CTransactionManager@@QEAA_NPEAVCTransaction@@K@Z; CTransactionManager::ItemExists(CTransaction *,ulong)
0x180094b41  neg     al
0x180094b43  sbb     cl, cl
0x180094b45  and     bl, cl
0x180094b47  lea     rbp, [rdi+3D8h]
0x180094b4e  mov     rcx, rbp; lpCriticalSection
0x180094b51  call    cs:__imp_EnterCriticalSection
0x180094b57  mov     dl, bl; bool
0x180094b59  mov     rcx, rdi; this
0x180094b5c  call    ?ReleaseCNetObjects@CINetHttpEdge@@IEAAX_N@Z; CINetHttpEdge::ReleaseCNetObjects(bool)
0x180094b61  mov     rcx, rbp; lpCriticalSection
0x180094b64  call    cs:__imp_LeaveCriticalSection
0x180094b6a  test    byte ptr [rdi+551h], 2
0x180094b71  jz      short loc_180094BB0
0x180094b73  mov     rax, [rdi]
0x180094b76  mov     rcx, rdi
0x180094b79  mov     rax, [rax+140h]
0x180094b80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094b85  mov     rcx, [rdi+500h]; lpFileName
0x180094b8c  call    cs:__imp_DeleteFileW
0x180094b92  mov     rcx, [rdi+500h]; void *
0x180094b99  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180094b9e  and     byte ptr [rdi+551h], 0FDh
0x180094ba5  mov     qword ptr [rdi+500h], 0
0x180094bb0  test    byte ptr [rdi+550h], 2
0x180094bb7  jz      loc_180094C77
0x180094bbd  mov     rax, [rdi]
0x180094bc0  mov     rcx, rdi
0x180094bc3  mov     rax, [rax+140h]
0x180094bca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094bcf  mov     rbx, [rdi+158h]
0x180094bd6  test    rbx, rbx
0x180094bd9  jnz     short loc_180094BEB
0x180094bdb  mov     rbx, [rdi+0B8h]
0x180094be2  test    rbx, rbx
0x180094be5  jz      loc_180094C77
0x180094beb  xor     sil, sil
0x180094bee  cmp     qword ptr [rdi+540h], 0
0x180094bf6  jz      short loc_180094C4E
0x180094bf8  xor     edx, edx; Val
0x180094bfa  lea     rcx, [rsp+1078h+CacheEntryInfo+4]; void *
0x180094bff  mov     r8d, 0FFCh; Size
0x180094c05  call    memset_0
0x180094c0a  lea     r8, [rsp+1078h+cbCacheEntryInfo]; lpcbCacheEntryInfo
0x180094c0f  mov     [rsp+1078h+cbCacheEntryInfo], 1000h
0x180094c17  lea     rdx, [rsp+1078h+CacheEntryInfo]; lpCacheEntryInfo
0x180094c1c  mov     [rsp+1078h+CacheEntryInfo.dwStructSize], 70h ; 'p'
0x180094c24  mov     rcx, rbx; lpszUrlName
0x180094c27  call    cs:__imp_GetUrlCacheEntryInfoW
0x180094c2d  test    eax, eax
0x180094c2f  jz      short loc_180094C4B
0x180094c31  mov     rdx, [rdi+540h]; pszStr2
0x180094c38  mov     rcx, [rsp+1078h+CacheEntryInfo.lpszLocalFileName]; pszStr1
0x180094c3d  call    cs:__imp_StrCmpICW
0x180094c43  test    eax, eax
0x180094c45  setnz   sil
0x180094c49  jmp     short loc_180094C4E
0x180094c4b  mov     sil, 1
0x180094c4e  mov     rcx, rbx; lpszUrlName
0x180094c51  call    cs:__imp_DeleteUrlCacheEntryW
0x180094c57  test    eax, eax
0x180094c59  jnz     short loc_180094C65
0x180094c5b  cmp     qword ptr [rdi+540h], 0
0x180094c63  jnz     short loc_180094C6A
0x180094c65  test    sil, sil
0x180094c68  jz      short loc_180094C77
0x180094c6a  mov     rcx, [rdi+540h]; lpFileName
0x180094c71  call    cs:__imp_DeleteFileW
0x180094c77  test    byte ptr [rdi+551h], 4
0x180094c7e  jz      short loc_180094CC1
0x180094c80  mov     rax, [rdi]
0x180094c83  mov     rcx, rdi
0x180094c86  mov     rax, [rax+140h]
0x180094c8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094c92  call    cs:__imp_?GetEdgeBrowsingEnvironment@@YAPEAUIEdgeBrowsingEnvironment@@XZ; GetEdgeBrowsingEnvironment(void)
0x180094c98  mov     r8, rax
0x180094c9b  lea     rbx, [rdi+4D8h]
0x180094ca2  mov     rdx, rbx
0x180094ca5  mov     rcx, [rax]
0x180094ca8  mov     rax, [rcx+10h]
0x180094cac  mov     rcx, r8
0x180094caf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094cb4  xorps   xmm0, xmm0
0x180094cb7  movups  xmmword ptr [rbx], xmm0
0x180094cba  and     byte ptr [rdi+551h], 0FBh
0x180094cc1  mov     rcx, rbp; lpCriticalSection
0x180094cc4  call    cs:__imp_EnterCriticalSection
0x180094cca  mov     rbx, [rdi+4E8h]
0x180094cd1  mov     rcx, rbp; lpCriticalSection
0x180094cd4  mov     qword ptr [rdi+4E8h], 0
0x180094cdf  call    cs:__imp_LeaveCriticalSection
0x180094ce5  test    rbx, rbx
0x180094ce8  jz      short loc_180094D08
0x180094cea  mov     rax, [rbx]
0x180094ced  mov     rcx, rbx
0x180094cf0  mov     rax, [rax+18h]
0x180094cf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094cf9  mov     rax, [rbx]
0x180094cfc  mov     rcx, rbx
0x180094cff  mov     rax, [rax+10h]
0x180094d03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094d08  or      byte ptr [rdi+551h], 10h
0x180094d0f  mov     rcx, [rsp+1078h+var_38]
0x180094d17  xor     rcx, rsp; StackCookie
0x180094d1a  call    __security_check_cookie
0x180094d1f  add     rsp, 1058h
0x180094d26  pop     rdi
0x180094d27  pop     rsi
0x180094d28  pop     rbp
0x180094d29  pop     rbx
0x180094d2a  retn
```
