# CINetHttp::LastRequestHandleClosed(void)

- ea: `0x18004e010`
- end: `0x18004e2e8`
- name: `?LastRequestHandleClosed@CINetHttp@@UEAAXXZ`
- size: `728`
- prototype: `void __fastcall(CINetHttp *__hidden this)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180024a3c`
- `0x18003d390`
- `0x18004e010`
- `0x18004e2f0`
- `0x18008a5b0`
- `0x1800a5a94`
- `0x18011ba3e`
- `0x18011baa0`
- `0x18011bb60`
- `0x18011c010`

## import_xrefs

- `iertutil!__imp_?GetLegacyBrowsingEnvironment@@YAPEAUILegacyBrowsingEnvironment@@XZ` at `0x18004e291`
- `iertutil!__imp_?GetLegacyBrowsingEnvironment@@YAPEAUILegacyBrowsingEnvironment@@XZ` at `0x18004e291`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004e093`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004e0de`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004e093`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004e0de`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004e080`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004e0c3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004e080`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004e0c3`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18004e23c`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18004e23c`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18004e193`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18004e274`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18004e193`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18004e274`
- `WININET!HttpCloseDependencyHandle` at `0x18004e110`
- `WININET!HttpCloseDependencyHandle` at `0x18004e110`
- `WININET!AppCacheCloseHandle` at `0x18004e126`
- `WININET!AppCacheCloseHandle` at `0x18004e126`
- `WININET!GetUrlCacheEntryInfoW` at `0x18004e226`
- `WININET!GetUrlCacheEntryInfoW` at `0x18004e226`
- `WININET!DeleteUrlCacheEntryW` at `0x18004e250`
- `WININET!DeleteUrlCacheEntryW` at `0x18004e250`

## pseudocode

```c
void __fastcall CINetHttp::LastRequestHandleClosed(CINetHttp *this)
{
  void *v2; // rcx
  void *v3; // rcx
  bool v4; // bl
  __int64 v5; // rbx
  CTransactionManager *GlobalTransactionManager; // rax
  unsigned int v7; // r8d
  struct CTransaction *v8; // rdx
  const WCHAR *v9; // rbx
  bool v10; // si
  struct ILegacyBrowsingEnvironment *LegacyBrowsingEnvironment; // rax
  DWORD cbCacheEntryInfo[4]; // [rsp+20h] [rbp-1048h] BYREF
  struct _INTERNET_CACHE_ENTRY_INFOW CacheEntryInfo; // [rsp+30h] [rbp-1038h] BYREF

  v2 = (void *)*((_QWORD *)this + 175);
  if ( v2 )
  {
    AppCacheCloseHandle(v2);
    *((_QWORD *)this + 175) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 176);
  if ( v3 )
  {
    HttpCloseDependencyHandle(v3);
    *((_QWORD *)this + 176) = 0;
  }
  if ( (*((_BYTE *)this + 1217) & 4) != 0 )
    CINetHttp::ResetBindStatusCallbackServices(this);
  v4 = 1;
  if ( *((_DWORD *)this + 116) == -2146697196 )
  {
    GlobalTransactionManager = GetGlobalTransactionManager();
    v8 = (struct CTransaction *)*((_QWORD *)this + 153);
    if ( v8 )
    {
      if ( GlobalTransactionManager )
        v4 = CTransactionManager::ItemExists(GlobalTransactionManager, v8, v7);
    }
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 488));
  CINetHttp::ReleaseCNetObjects(this, v4);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 488));
  if ( (*((_BYTE *)this + 1217) & 1) != 0 )
  {
    (*(void (__fastcall **)(CINetHttp *))(*(_QWORD *)this + 216LL))(this);
    DeleteFileW(*((LPCWSTR *)this + 142));
    operator delete[](*((void **)this + 142));
    *((_BYTE *)this + 1217) &= ~1u;
    *((_QWORD *)this + 142) = 0;
  }
  if ( (*((_BYTE *)this + 1216) & 2) != 0 )
  {
    (*(void (__fastcall **)(CINetHttp *))(*(_QWORD *)this + 216LL))(this);
    v9 = (const WCHAR *)*((_QWORD *)this + 40);
    if ( v9 || (v9 = (const WCHAR *)*((_QWORD *)this + 20)) != 0 )
    {
      v10 = 0;
      if ( *((_QWORD *)this + 150) )
      {
        memset_0(&CacheEntryInfo.dwStructSize + 1, 0, 0xFFCu);
        cbCacheEntryInfo[0] = 4096;
        CacheEntryInfo.dwStructSize = 112;
        v10 = !GetUrlCacheEntryInfoW(v9, &CacheEntryInfo, cbCacheEntryInfo)
           || StrCmpICW(CacheEntryInfo.lpszLocalFileName, *((LPCWSTR *)this + 150)) != 0;
      }
      if ( !DeleteUrlCacheEntryW(v9) && *((_QWORD *)this + 150) || v10 )
        DeleteFileW(*((LPCWSTR *)this + 150));
    }
  }
  if ( (*((_BYTE *)this + 1217) & 2) != 0 )
  {
    (*(void (__fastcall **)(CINetHttp *))(*(_QWORD *)this + 216LL))(this);
    LegacyBrowsingEnvironment = GetLegacyBrowsingEnvironment();
    (*(void (__fastcall **)(struct ILegacyBrowsingEnvironment *, char *))(*(_QWORD *)LegacyBrowsingEnvironment + 16LL))(
      LegacyBrowsingEnvironment,
      (char *)this + 1092);
    *(_OWORD *)((char *)this + 1092) = 0;
    *((_BYTE *)this + 1217) &= ~2u;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 488));
  v5 = *((_QWORD *)this + 139);
  *((_QWORD *)this + 139) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 488));
  if ( v5 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 24LL))(v5);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  }
  *((_BYTE *)this + 1217) |= 8u;
}

```

## disassembly

```asm
0x18004e010  push    rbx
0x18004e012  push    rbp
0x18004e013  push    rsi
0x18004e014  push    rdi
0x18004e015  mov     eax, 1048h
0x18004e01a  call    _alloca_probe
0x18004e01f  sub     rsp, rax
0x18004e022  mov     rax, cs:__security_cookie
0x18004e029  xor     rax, rsp
0x18004e02c  mov     [rsp+1068h+var_38], rax
0x18004e034  mov     rdi, rcx
0x18004e037  mov     rcx, [rcx+578h]; hAppCache
0x18004e03e  test    rcx, rcx
0x18004e041  jnz     loc_18004E126
0x18004e047  mov     rcx, [rdi+580h]; hDependencyHandle
0x18004e04e  test    rcx, rcx
0x18004e051  jnz     loc_18004E110
0x18004e057  test    byte ptr [rdi+4C1h], 4
0x18004e05e  jnz     loc_18004E13C
0x18004e064  cmp     dword ptr [rdi+1D0h], 800C0014h
0x18004e06e  mov     bl, 1
0x18004e070  jz      loc_18004E149
0x18004e076  lea     rbp, [rdi+1E8h]
0x18004e07d  mov     rcx, rbp; lpCriticalSection
0x18004e080  call    cs:__imp_EnterCriticalSection
0x18004e086  mov     dl, bl; bool
0x18004e088  mov     rcx, rdi; this
0x18004e08b  call    ?ReleaseCNetObjects@CINetHttp@@IEAAX_N@Z; CINetHttp::ReleaseCNetObjects(bool)
0x18004e090  mov     rcx, rbp; lpCriticalSection
0x18004e093  call    cs:__imp_LeaveCriticalSection
0x18004e099  test    byte ptr [rdi+4C1h], 1
0x18004e0a0  jnz     loc_18004E17A
0x18004e0a6  test    byte ptr [rdi+4C0h], 2
0x18004e0ad  jnz     loc_18004E1BC
0x18004e0b3  test    byte ptr [rdi+4C1h], 2
0x18004e0ba  jnz     loc_18004E27F
0x18004e0c0  mov     rcx, rbp; lpCriticalSection
0x18004e0c3  call    cs:__imp_EnterCriticalSection
0x18004e0c9  mov     rbx, [rdi+458h]
0x18004e0d0  mov     rcx, rbp; lpCriticalSection
0x18004e0d3  mov     qword ptr [rdi+458h], 0
0x18004e0de  call    cs:__imp_LeaveCriticalSection
0x18004e0e4  test    rbx, rbx
0x18004e0e7  jnz     loc_18004E2C5
0x18004e0ed  or      byte ptr [rdi+4C1h], 8
0x18004e0f4  mov     rcx, [rsp+1068h+var_38]
0x18004e0fc  xor     rcx, rsp; StackCookie
0x18004e0ff  call    __security_check_cookie
0x18004e104  add     rsp, 1048h
0x18004e10b  pop     rdi
0x18004e10c  pop     rsi
0x18004e10d  pop     rbp
0x18004e10e  pop     rbx
0x18004e10f  retn
0x18004e110  call    cs:__imp_HttpCloseDependencyHandle
0x18004e116  mov     qword ptr [rdi+580h], 0
0x18004e121  jmp     loc_18004E057
0x18004e126  call    cs:__imp_AppCacheCloseHandle
0x18004e12c  mov     qword ptr [rdi+578h], 0
0x18004e137  jmp     loc_18004E047
0x18004e13c  mov     rcx, rdi; this
0x18004e13f  call    ?ResetBindStatusCallbackServices@CINetHttp@@AEAAXXZ; CINetHttp::ResetBindStatusCallbackServices(void)
0x18004e144  jmp     loc_18004E064
0x18004e149  call    ?GetGlobalTransactionManager@@YAPEAVCTransactionManager@@XZ; GetGlobalTransactionManager(void)
0x18004e14e  mov     rdx, [rdi+4C8h]; struct CTransaction *
0x18004e155  test    rdx, rdx
0x18004e158  jz      loc_18004E076
0x18004e15e  test    rax, rax
0x18004e161  jz      loc_18004E076
0x18004e167  mov     rcx, rax; this
0x18004e16a  call    ?ItemExists@CTransactionManager@@QEAA_NPEAVCTransaction@@K@Z; CTransactionManager::ItemExists(CTransaction *,ulong)
0x18004e16f  neg     al
0x18004e171  sbb     cl, cl
0x18004e173  and     bl, cl
0x18004e175  jmp     loc_18004E076
0x18004e17a  mov     rax, [rdi]
0x18004e17d  mov     rcx, rdi
0x18004e180  mov     rax, [rax+0D8h]
0x18004e187  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e18c  mov     rcx, [rdi+470h]; lpFileName
0x18004e193  call    cs:__imp_DeleteFileW
0x18004e199  mov     rcx, [rdi+470h]; void *
0x18004e1a0  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x18004e1a5  and     byte ptr [rdi+4C1h], 0FEh
0x18004e1ac  mov     qword ptr [rdi+470h], 0
0x18004e1b7  jmp     loc_18004E0A6
0x18004e1bc  mov     rax, [rdi]
0x18004e1bf  mov     rcx, rdi
0x18004e1c2  mov     rax, [rax+0D8h]
0x18004e1c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e1ce  mov     rbx, [rdi+140h]
0x18004e1d5  test    rbx, rbx
0x18004e1d8  jnz     short loc_18004E1EA
0x18004e1da  mov     rbx, [rdi+0A0h]
0x18004e1e1  test    rbx, rbx
0x18004e1e4  jz      loc_18004E0B3
0x18004e1ea  xor     sil, sil
0x18004e1ed  cmp     qword ptr [rdi+4B0h], 0
0x18004e1f5  jz      short loc_18004E24D
0x18004e1f7  xor     edx, edx; Val
0x18004e1f9  lea     rcx, [rsp+1068h+CacheEntryInfo+4]; void *
0x18004e1fe  mov     r8d, 0FFCh; Size
0x18004e204  call    memset_0
0x18004e209  lea     r8, [rsp+1068h+cbCacheEntryInfo]; lpcbCacheEntryInfo
0x18004e20e  mov     [rsp+1068h+cbCacheEntryInfo], 1000h
0x18004e216  lea     rdx, [rsp+1068h+CacheEntryInfo]; lpCacheEntryInfo
0x18004e21b  mov     [rsp+1068h+CacheEntryInfo.dwStructSize], 70h ; 'p'
0x18004e223  mov     rcx, rbx; lpszUrlName
0x18004e226  call    cs:__imp_GetUrlCacheEntryInfoW
0x18004e22c  test    eax, eax
0x18004e22e  jz      short loc_18004E24A
0x18004e230  mov     rdx, [rdi+4B0h]; pszStr2
0x18004e237  mov     rcx, [rsp+1068h+CacheEntryInfo.lpszLocalFileName]; pszStr1
0x18004e23c  call    cs:__imp_StrCmpICW
0x18004e242  test    eax, eax
0x18004e244  setnz   sil
0x18004e248  jmp     short loc_18004E24D
0x18004e24a  mov     sil, 1
0x18004e24d  mov     rcx, rbx; lpszUrlName
0x18004e250  call    cs:__imp_DeleteUrlCacheEntryW
0x18004e256  test    eax, eax
0x18004e258  jnz     short loc_18004E264
0x18004e25a  cmp     qword ptr [rdi+4B0h], 0
0x18004e262  jnz     short loc_18004E26D
0x18004e264  test    sil, sil
0x18004e267  jz      loc_18004E0B3
0x18004e26d  mov     rcx, [rdi+4B0h]; lpFileName
0x18004e274  call    cs:__imp_DeleteFileW
0x18004e27a  jmp     loc_18004E0B3
0x18004e27f  mov     rax, [rdi]
0x18004e282  mov     rcx, rdi
0x18004e285  mov     rax, [rax+0D8h]
0x18004e28c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e291  call    cs:__imp_?GetLegacyBrowsingEnvironment@@YAPEAUILegacyBrowsingEnvironment@@XZ; GetLegacyBrowsingEnvironment(void)
0x18004e297  mov     r8, rax
0x18004e29a  lea     rbx, [rdi+444h]
0x18004e2a1  mov     rdx, rbx
0x18004e2a4  mov     rcx, [rax]
0x18004e2a7  mov     rax, [rcx+10h]
0x18004e2ab  mov     rcx, r8
0x18004e2ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e2b3  xorps   xmm0, xmm0
0x18004e2b6  movups  xmmword ptr [rbx], xmm0
0x18004e2b9  and     byte ptr [rdi+4C1h], 0FDh
0x18004e2c0  jmp     loc_18004E0C0
0x18004e2c5  mov     rax, [rbx]
0x18004e2c8  mov     rcx, rbx
0x18004e2cb  mov     rax, [rax+18h]
0x18004e2cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e2d4  mov     rax, [rbx]
0x18004e2d7  mov     rcx, rbx
0x18004e2da  mov     rax, [rax+10h]
0x18004e2de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e2e3  jmp     loc_18004E0ED
```
