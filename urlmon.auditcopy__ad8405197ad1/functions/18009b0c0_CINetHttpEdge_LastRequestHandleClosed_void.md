# CINetHttpEdge::LastRequestHandleClosed(void)

- ea: `0x18009b0c0`
- end: `0x18009b3e4`
- name: `?LastRequestHandleClosed@CINetHttpEdge@@UEAAXXZ`
- size: `804`
- prototype: `void __fastcall(CINetHttpEdge *__hidden this)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x18000f45c`
- `0x18002bac4`
- `0x18002fee0`
- `0x18006894c`
- `0x1800820a4`
- `0x18008f844`
- `0x180098850`
- `0x18009b0c0`
- `0x1801285fe`
- `0x180128660`
- `0x180128720`
- `0x180129010`

## import_xrefs

- `iertutil!__imp_?GetEdgeBrowsingEnvironment@@YAPEAUIEdgeBrowsingEnvironment@@XZ` at `0x18009b338`
- `iertutil!__imp_?GetEdgeBrowsingEnvironment@@YAPEAUIEdgeBrowsingEnvironment@@XZ` at `0x18009b338`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009b1e6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009b391`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009b1e6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009b391`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009b1cd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009b370`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009b1cd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009b370`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18009b2d1`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18009b2d1`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18009b214`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18009b311`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18009b214`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18009b311`
- `WININET!HttpCloseDependencyHandle` at `0x18009b151`
- `WININET!HttpCloseDependencyHandle` at `0x18009b151`
- `WININET!AppCacheCloseHandle` at `0x18009b12e`
- `WININET!AppCacheCloseHandle` at `0x18009b12e`
- `WININET!GetUrlCacheEntryInfoW` at `0x18009b2b5`
- `WININET!GetUrlCacheEntryInfoW` at `0x18009b2b5`
- `WININET!DeleteUrlCacheEntryW` at `0x18009b2eb`
- `WININET!DeleteUrlCacheEntryW` at `0x18009b2eb`

## pseudocode

```c
void __fastcall CINetHttpEdge::LastRequestHandleClosed(CINetHttpEdge *this)
{
  __int64 v2; // rcx
  __int64 v3; // r8
  __int64 v4; // r9
  void *v5; // rcx
  void *v6; // rcx
  char v7; // cl
  char v8; // bl
  HDSA *GlobalTransactionManager; // rax
  struct CTransaction *v10; // rdx
  const WCHAR *v11; // rbx
  bool v12; // si
  struct IEdgeBrowsingEnvironment *EdgeBrowsingEnvironment; // rax
  __int64 v14; // rbx
  DWORD cbCacheEntryInfo[4]; // [rsp+30h] [rbp-1048h] BYREF
  struct _INTERNET_CACHE_ENTRY_INFOW CacheEntryInfo; // [rsp+40h] [rbp-1038h] BYREF

  if ( (unsigned int)dword_180166000 > 5 && tlgKeywordOn((__int64)&dword_180166000, 32) )
  {
    *(_QWORD *)cbCacheEntryInfo = this;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
      v2,
      (unsigned __int8 *)&unk_180151DB8,
      v3,
      v4,
      (__int64)cbCacheEntryInfo);
  }
  v5 = (void *)*((_QWORD *)this + 246);
  if ( v5 )
  {
    AppCacheCloseHandle(v5);
    *((_QWORD *)this + 246) = 0;
  }
  v6 = (void *)*((_QWORD *)this + 247);
  if ( v6 )
  {
    HttpCloseDependencyHandle(v6);
    *((_QWORD *)this + 247) = 0;
  }
  v7 = *((_BYTE *)this + 1361) ^ (*((_BYTE *)this + 1361) ^ (4 * *((_BYTE *)this + 978))) & 8;
  *((_BYTE *)this + 1361) = v7;
  if ( (v7 & 8) != 0 )
    CINetHttpEdge::ResetBindStatusCallbackServices(this);
  v8 = 1;
  if ( *((_DWORD *)this + 122) == -2146697196 )
  {
    GlobalTransactionManager = (HDSA *)GetGlobalTransactionManager();
    v10 = (struct CTransaction *)*((_QWORD *)this + 171);
    if ( v10 )
    {
      if ( GlobalTransactionManager )
        v8 = CTransactionManager::ItemExists(GlobalTransactionManager, v10) != 0;
    }
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 984));
  CINetHttpEdge::ReleaseCNetObjects(this, v8);
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
    v11 = (const WCHAR *)*((_QWORD *)this + 43);
    if ( v11 || (v11 = (const WCHAR *)*((_QWORD *)this + 23)) != 0 )
    {
      v12 = 0;
      if ( *((_QWORD *)this + 168) )
      {
        memset_0(&CacheEntryInfo.dwStructSize + 1, 0, 0xFFCu);
        cbCacheEntryInfo[0] = 4096;
        CacheEntryInfo.dwStructSize = 112;
        v12 = !GetUrlCacheEntryInfoW(v11, &CacheEntryInfo, cbCacheEntryInfo)
           || StrCmpICW(CacheEntryInfo.lpszLocalFileName, *((LPCWSTR *)this + 168)) != 0;
      }
      if ( !DeleteUrlCacheEntryW(v11) && *((_QWORD *)this + 168) || v12 )
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
  v14 = *((_QWORD *)this + 157);
  *((_QWORD *)this + 157) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 984));
  if ( v14 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 24LL))(v14);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  }
  *((_BYTE *)this + 1361) |= 0x10u;
}

```

## disassembly

```asm
0x18009b0c0  push    rbx
0x18009b0c2  push    rbp
0x18009b0c3  push    rsi
0x18009b0c4  push    rdi
0x18009b0c5  mov     eax, 1058h
0x18009b0ca  call    _alloca_probe
0x18009b0cf  sub     rsp, rax
0x18009b0d2  mov     rax, cs:__security_cookie
0x18009b0d9  xor     rax, rsp
0x18009b0dc  mov     [rsp+1078h+var_38], rax
0x18009b0e4  mov     eax, cs:dword_180166000
0x18009b0ea  mov     rdi, rcx
0x18009b0ed  cmp     eax, 5
0x18009b0f0  jbe     short loc_18009B122
0x18009b0f2  mov     edx, 20h ; ' '
0x18009b0f7  lea     rcx, dword_180166000
0x18009b0fe  call    _tlgKeywordOn
0x18009b103  test    al, al
0x18009b105  jz      short loc_18009B122
0x18009b107  lea     rax, [rsp+1078h+cbCacheEntryInfo]
0x18009b10c  mov     qword ptr [rsp+1078h+cbCacheEntryInfo], rdi
0x18009b111  lea     rdx, unk_180151DB8
0x18009b118  mov     [rsp+1078h+var_1058], rax
0x18009b11d  call    ??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_BrowserWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)
0x18009b122  mov     rcx, [rdi+7B0h]; hAppCache
0x18009b129  test    rcx, rcx
0x18009b12c  jz      short loc_18009B145
0x18009b12e  call    cs:__imp_AppCacheCloseHandle
0x18009b135  nop     dword ptr [rax+rax+00h]
0x18009b13a  mov     qword ptr [rdi+7B0h], 0
0x18009b145  mov     rcx, [rdi+7B8h]; hDependencyHandle
0x18009b14c  test    rcx, rcx
0x18009b14f  jz      short loc_18009B168
0x18009b151  call    cs:__imp_HttpCloseDependencyHandle
0x18009b158  nop     dword ptr [rax+rax+00h]
0x18009b15d  mov     qword ptr [rdi+7B8h], 0
0x18009b168  mov     al, [rdi+551h]
0x18009b16e  mov     cl, [rdi+3D2h]
0x18009b174  shl     cl, 2
0x18009b177  xor     cl, al
0x18009b179  and     cl, 8
0x18009b17c  xor     cl, al
0x18009b17e  mov     [rdi+551h], cl
0x18009b184  test    cl, 8
0x18009b187  jz      short loc_18009B191
0x18009b189  mov     rcx, rdi; this
0x18009b18c  call    ?ResetBindStatusCallbackServices@CINetHttpEdge@@AEAAXXZ; CINetHttpEdge::ResetBindStatusCallbackServices(void)
0x18009b191  cmp     dword ptr [rdi+1E8h], 800C0014h
0x18009b19b  mov     bl, 1
0x18009b19d  jnz     short loc_18009B1C3
0x18009b19f  call    ?GetGlobalTransactionManager@@YAPEAVCTransactionManager@@XZ; GetGlobalTransactionManager(void)
0x18009b1a4  mov     rdx, [rdi+558h]; struct CTransaction *
0x18009b1ab  test    rdx, rdx
0x18009b1ae  jz      short loc_18009B1C3
0x18009b1b0  test    rax, rax
0x18009b1b3  jz      short loc_18009B1C3
0x18009b1b5  mov     rcx, rax; this
0x18009b1b8  call    ?ItemExists@CTransactionManager@@QEAA_NPEAVCTransaction@@K@Z; CTransactionManager::ItemExists(CTransaction *,ulong)
0x18009b1bd  neg     al
0x18009b1bf  sbb     cl, cl
0x18009b1c1  and     bl, cl
0x18009b1c3  lea     rbp, [rdi+3D8h]
0x18009b1ca  mov     rcx, rbp; lpCriticalSection
0x18009b1cd  call    cs:__imp_EnterCriticalSection
0x18009b1d4  nop     dword ptr [rax+rax+00h]
0x18009b1d9  mov     dl, bl; bool
0x18009b1db  mov     rcx, rdi; this
0x18009b1de  call    ?ReleaseCNetObjects@CINetHttpEdge@@IEAAX_N@Z; CINetHttpEdge::ReleaseCNetObjects(bool)
0x18009b1e3  mov     rcx, rbp; lpCriticalSection
0x18009b1e6  call    cs:__imp_LeaveCriticalSection
0x18009b1ed  nop     dword ptr [rax+rax+00h]
0x18009b1f2  test    byte ptr [rdi+551h], 2
0x18009b1f9  jz      short loc_18009B23E
0x18009b1fb  mov     rax, [rdi]
0x18009b1fe  mov     rcx, rdi
0x18009b201  mov     rax, [rax+140h]
0x18009b208  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b20d  mov     rcx, [rdi+500h]; lpFileName
0x18009b214  call    cs:__imp_DeleteFileW
0x18009b21b  nop     dword ptr [rax+rax+00h]
0x18009b220  mov     rcx, [rdi+500h]; void *
0x18009b227  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18009b22c  and     byte ptr [rdi+551h], 0FDh
0x18009b233  mov     qword ptr [rdi+500h], 0
0x18009b23e  test    byte ptr [rdi+550h], 2
0x18009b245  jz      loc_18009B31D
0x18009b24b  mov     rax, [rdi]
0x18009b24e  mov     rcx, rdi
0x18009b251  mov     rax, [rax+140h]
0x18009b258  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b25d  mov     rbx, [rdi+158h]
0x18009b264  test    rbx, rbx
0x18009b267  jnz     short loc_18009B279
0x18009b269  mov     rbx, [rdi+0B8h]
0x18009b270  test    rbx, rbx
0x18009b273  jz      loc_18009B31D
0x18009b279  xor     sil, sil
0x18009b27c  cmp     qword ptr [rdi+540h], 0
0x18009b284  jz      short loc_18009B2E8
0x18009b286  xor     edx, edx; Val
0x18009b288  lea     rcx, [rsp+1078h+CacheEntryInfo+4]; void *
0x18009b28d  mov     r8d, 0FFCh; Size
0x18009b293  call    memset_0
0x18009b298  lea     r8, [rsp+1078h+cbCacheEntryInfo]; lpcbCacheEntryInfo
0x18009b29d  mov     [rsp+1078h+cbCacheEntryInfo], 1000h
0x18009b2a5  lea     rdx, [rsp+1078h+CacheEntryInfo]; lpCacheEntryInfo
0x18009b2aa  mov     [rsp+1078h+CacheEntryInfo.dwStructSize], 70h ; 'p'
0x18009b2b2  mov     rcx, rbx; lpszUrlName
0x18009b2b5  call    cs:__imp_GetUrlCacheEntryInfoW
0x18009b2bc  nop     dword ptr [rax+rax+00h]
0x18009b2c1  test    eax, eax
0x18009b2c3  jz      short loc_18009B2E5
0x18009b2c5  mov     rdx, [rdi+540h]; pszStr2
0x18009b2cc  mov     rcx, [rsp+1078h+CacheEntryInfo.lpszLocalFileName]; pszStr1
0x18009b2d1  call    cs:__imp_StrCmpICW
0x18009b2d8  nop     dword ptr [rax+rax+00h]
0x18009b2dd  test    eax, eax
0x18009b2df  setnz   sil
0x18009b2e3  jmp     short loc_18009B2E8
0x18009b2e5  mov     sil, 1
0x18009b2e8  mov     rcx, rbx; lpszUrlName
0x18009b2eb  call    cs:__imp_DeleteUrlCacheEntryW
0x18009b2f2  nop     dword ptr [rax+rax+00h]
0x18009b2f7  test    eax, eax
0x18009b2f9  jnz     short loc_18009B305
0x18009b2fb  cmp     qword ptr [rdi+540h], 0
0x18009b303  jnz     short loc_18009B30A
0x18009b305  test    sil, sil
0x18009b308  jz      short loc_18009B31D
0x18009b30a  mov     rcx, [rdi+540h]; lpFileName
0x18009b311  call    cs:__imp_DeleteFileW
0x18009b318  nop     dword ptr [rax+rax+00h]
0x18009b31d  test    byte ptr [rdi+551h], 4
0x18009b324  jz      short loc_18009B36D
0x18009b326  mov     rax, [rdi]
0x18009b329  mov     rcx, rdi
0x18009b32c  mov     rax, [rax+140h]
0x18009b333  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b338  call    cs:__imp_?GetEdgeBrowsingEnvironment@@YAPEAUIEdgeBrowsingEnvironment@@XZ; GetEdgeBrowsingEnvironment(void)
0x18009b33f  nop     dword ptr [rax+rax+00h]
0x18009b344  mov     r8, rax
0x18009b347  lea     rbx, [rdi+4D8h]
0x18009b34e  mov     rdx, rbx
0x18009b351  mov     rcx, [rax]
0x18009b354  mov     rax, [rcx+10h]
0x18009b358  mov     rcx, r8
0x18009b35b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b360  xorps   xmm0, xmm0
0x18009b363  movups  xmmword ptr [rbx], xmm0
0x18009b366  and     byte ptr [rdi+551h], 0FBh
0x18009b36d  mov     rcx, rbp; lpCriticalSection
0x18009b370  call    cs:__imp_EnterCriticalSection
0x18009b377  nop     dword ptr [rax+rax+00h]
0x18009b37c  mov     rbx, [rdi+4E8h]
0x18009b383  mov     rcx, rbp; lpCriticalSection
0x18009b386  mov     qword ptr [rdi+4E8h], 0
0x18009b391  call    cs:__imp_LeaveCriticalSection
0x18009b398  nop     dword ptr [rax+rax+00h]
0x18009b39d  test    rbx, rbx
0x18009b3a0  jz      short loc_18009B3C0
0x18009b3a2  mov     rax, [rbx]
0x18009b3a5  mov     rcx, rbx
0x18009b3a8  mov     rax, [rax+18h]
0x18009b3ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b3b1  mov     rax, [rbx]
0x18009b3b4  mov     rcx, rbx
0x18009b3b7  mov     rax, [rax+10h]
0x18009b3bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b3c0  or      byte ptr [rdi+551h], 10h
0x18009b3c7  mov     rcx, [rsp+1078h+var_38]
0x18009b3cf  xor     rcx, rsp; StackCookie
0x18009b3d2  call    __security_check_cookie
0x18009b3d7  add     rsp, 1058h
0x18009b3de  pop     rdi
0x18009b3df  pop     rsi
0x18009b3e0  pop     rbp
0x18009b3e1  pop     rbx
0x18009b3e2  retn
```
