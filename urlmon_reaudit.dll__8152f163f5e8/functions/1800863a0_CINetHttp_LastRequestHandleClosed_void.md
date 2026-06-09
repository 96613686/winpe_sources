# CINetHttp::LastRequestHandleClosed(void)

- ea: `0x1800863a0`
- end: `0x1800866c1`
- name: `?LastRequestHandleClosed@CINetHttp@@UEAAXXZ`
- size: `801`
- prototype: `void __fastcall(CINetHttp *__hidden this)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x18002bac4`
- `0x18007883c`
- `0x1800863a0`
- `0x1800866c8`
- `0x18008f844`
- `0x1800ac8d4`
- `0x1801285fe`
- `0x180128660`
- `0x180128720`
- `0x180129010`

## import_xrefs

- `iertutil!__imp_?GetLegacyBrowsingEnvironment@@YAPEAUILegacyBrowsingEnvironment@@XZ` at `0x180086664`
- `iertutil!__imp_?GetLegacyBrowsingEnvironment@@YAPEAUILegacyBrowsingEnvironment@@XZ` at `0x180086664`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180086429`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180086480`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180086429`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180086480`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180086410`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008645f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180086410`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008645f`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1800865fd`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1800865fd`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180086548`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180086641`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180086548`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180086641`
- `WININET!HttpCloseDependencyHandle` at `0x1800864b9`
- `WININET!HttpCloseDependencyHandle` at `0x1800864b9`
- `WININET!AppCacheCloseHandle` at `0x1800864d5`
- `WININET!AppCacheCloseHandle` at `0x1800864d5`
- `WININET!GetUrlCacheEntryInfoW` at `0x1800865e1`
- `WININET!GetUrlCacheEntryInfoW` at `0x1800865e1`
- `WININET!DeleteUrlCacheEntryW` at `0x180086617`
- `WININET!DeleteUrlCacheEntryW` at `0x180086617`

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
  _INTERNET_CACHE_ENTRY_INFOW CacheEntryInfo; // [rsp+30h] [rbp-1038h] BYREF

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
0x1800863a0  push    rbx
0x1800863a2  push    rbp
0x1800863a3  push    rsi
0x1800863a4  push    rdi
0x1800863a5  mov     eax, 1048h
0x1800863aa  call    _alloca_probe
0x1800863af  sub     rsp, rax
0x1800863b2  mov     rax, cs:__security_cookie
0x1800863b9  xor     rax, rsp
0x1800863bc  mov     [rsp+1068h+var_38], rax
0x1800863c4  mov     rdi, rcx
0x1800863c7  mov     rcx, [rcx+578h]; hAppCache
0x1800863ce  test    rcx, rcx
0x1800863d1  jnz     loc_1800864D5
0x1800863d7  mov     rcx, [rdi+580h]; hDependencyHandle
0x1800863de  test    rcx, rcx
0x1800863e1  jnz     loc_1800864B9
0x1800863e7  test    byte ptr [rdi+4C1h], 4
0x1800863ee  jnz     loc_1800864F1
0x1800863f4  cmp     dword ptr [rdi+1D0h], 800C0014h
0x1800863fe  mov     bl, 1
0x180086400  jz      loc_1800864FE
0x180086406  lea     rbp, [rdi+1E8h]
0x18008640d  mov     rcx, rbp; lpCriticalSection
0x180086410  call    cs:__imp_EnterCriticalSection
0x180086417  nop     dword ptr [rax+rax+00h]
0x18008641c  mov     dl, bl; bool
0x18008641e  mov     rcx, rdi; this
0x180086421  call    ?ReleaseCNetObjects@CINetHttp@@IEAAX_N@Z; CINetHttp::ReleaseCNetObjects(bool)
0x180086426  mov     rcx, rbp; lpCriticalSection
0x180086429  call    cs:__imp_LeaveCriticalSection
0x180086430  nop     dword ptr [rax+rax+00h]
0x180086435  test    byte ptr [rdi+4C1h], 1
0x18008643c  jnz     loc_18008652F
0x180086442  test    byte ptr [rdi+4C0h], 2
0x180086449  jnz     loc_180086577
0x18008644f  test    byte ptr [rdi+4C1h], 2
0x180086456  jnz     loc_180086652
0x18008645c  mov     rcx, rbp; lpCriticalSection
0x18008645f  call    cs:__imp_EnterCriticalSection
0x180086466  nop     dword ptr [rax+rax+00h]
0x18008646b  mov     rbx, [rdi+458h]
0x180086472  mov     rcx, rbp; lpCriticalSection
0x180086475  mov     qword ptr [rdi+458h], 0
0x180086480  call    cs:__imp_LeaveCriticalSection
0x180086487  nop     dword ptr [rax+rax+00h]
0x18008648c  test    rbx, rbx
0x18008648f  jnz     loc_18008669E
0x180086495  or      byte ptr [rdi+4C1h], 8
0x18008649c  mov     rcx, [rsp+1068h+var_38]
0x1800864a4  xor     rcx, rsp; StackCookie
0x1800864a7  call    __security_check_cookie
0x1800864ac  add     rsp, 1048h
0x1800864b3  pop     rdi
0x1800864b4  pop     rsi
0x1800864b5  pop     rbp
0x1800864b6  pop     rbx
0x1800864b7  retn
0x1800864b9  call    cs:__imp_HttpCloseDependencyHandle
0x1800864c0  nop     dword ptr [rax+rax+00h]
0x1800864c5  mov     qword ptr [rdi+580h], 0
0x1800864d0  jmp     loc_1800863E7
0x1800864d5  call    cs:__imp_AppCacheCloseHandle
0x1800864dc  nop     dword ptr [rax+rax+00h]
0x1800864e1  mov     qword ptr [rdi+578h], 0
0x1800864ec  jmp     loc_1800863D7
0x1800864f1  mov     rcx, rdi; this
0x1800864f4  call    ?ResetBindStatusCallbackServices@CINetHttp@@AEAAXXZ; CINetHttp::ResetBindStatusCallbackServices(void)
0x1800864f9  jmp     loc_1800863F4
0x1800864fe  call    ?GetGlobalTransactionManager@@YAPEAVCTransactionManager@@XZ; GetGlobalTransactionManager(void)
0x180086503  mov     rdx, [rdi+4C8h]; struct CTransaction *
0x18008650a  test    rdx, rdx
0x18008650d  jz      loc_180086406
0x180086513  test    rax, rax
0x180086516  jz      loc_180086406
0x18008651c  mov     rcx, rax; this
0x18008651f  call    ?ItemExists@CTransactionManager@@QEAA_NPEAVCTransaction@@K@Z; CTransactionManager::ItemExists(CTransaction *,ulong)
0x180086524  neg     al
0x180086526  sbb     cl, cl
0x180086528  and     bl, cl
0x18008652a  jmp     loc_180086406
0x18008652f  mov     rax, [rdi]
0x180086532  mov     rcx, rdi
0x180086535  mov     rax, [rax+0D8h]
0x18008653c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086541  mov     rcx, [rdi+470h]; lpFileName
0x180086548  call    cs:__imp_DeleteFileW
0x18008654f  nop     dword ptr [rax+rax+00h]
0x180086554  mov     rcx, [rdi+470h]; void *
0x18008655b  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180086560  and     byte ptr [rdi+4C1h], 0FEh
0x180086567  mov     qword ptr [rdi+470h], 0
0x180086572  jmp     loc_180086442
0x180086577  mov     rax, [rdi]
0x18008657a  mov     rcx, rdi
0x18008657d  mov     rax, [rax+0D8h]
0x180086584  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086589  mov     rbx, [rdi+140h]
0x180086590  test    rbx, rbx
0x180086593  jnz     short loc_1800865A5
0x180086595  mov     rbx, [rdi+0A0h]
0x18008659c  test    rbx, rbx
0x18008659f  jz      loc_18008644F
0x1800865a5  xor     sil, sil
0x1800865a8  cmp     qword ptr [rdi+4B0h], 0
0x1800865b0  jz      short loc_180086614
0x1800865b2  xor     edx, edx; Val
0x1800865b4  lea     rcx, [rsp+1068h+CacheEntryInfo+4]; void *
0x1800865b9  mov     r8d, 0FFCh; Size
0x1800865bf  call    memset_0
0x1800865c4  lea     r8, [rsp+1068h+cbCacheEntryInfo]; lpcbCacheEntryInfo
0x1800865c9  mov     [rsp+1068h+cbCacheEntryInfo], 1000h
0x1800865d1  lea     rdx, [rsp+1068h+CacheEntryInfo]; lpCacheEntryInfo
0x1800865d6  mov     [rsp+1068h+CacheEntryInfo.dwStructSize], 70h ; 'p'
0x1800865de  mov     rcx, rbx; lpszUrlName
0x1800865e1  call    cs:__imp_GetUrlCacheEntryInfoW
0x1800865e8  nop     dword ptr [rax+rax+00h]
0x1800865ed  test    eax, eax
0x1800865ef  jz      short loc_180086611
0x1800865f1  mov     rdx, [rdi+4B0h]; pszStr2
0x1800865f8  mov     rcx, [rsp+1068h+CacheEntryInfo.lpszLocalFileName]; pszStr1
0x1800865fd  call    cs:__imp_StrCmpICW
0x180086604  nop     dword ptr [rax+rax+00h]
0x180086609  test    eax, eax
0x18008660b  setnz   sil
0x18008660f  jmp     short loc_180086614
0x180086611  mov     sil, 1
0x180086614  mov     rcx, rbx; lpszUrlName
0x180086617  call    cs:__imp_DeleteUrlCacheEntryW
0x18008661e  nop     dword ptr [rax+rax+00h]
0x180086623  test    eax, eax
0x180086625  jnz     short loc_180086631
0x180086627  cmp     qword ptr [rdi+4B0h], 0
0x18008662f  jnz     short loc_18008663A
0x180086631  test    sil, sil
0x180086634  jz      loc_18008644F
0x18008663a  mov     rcx, [rdi+4B0h]; lpFileName
0x180086641  call    cs:__imp_DeleteFileW
0x180086648  nop     dword ptr [rax+rax+00h]
0x18008664d  jmp     loc_18008644F
0x180086652  mov     rax, [rdi]
0x180086655  mov     rcx, rdi
0x180086658  mov     rax, [rax+0D8h]
0x18008665f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086664  call    cs:__imp_?GetLegacyBrowsingEnvironment@@YAPEAUILegacyBrowsingEnvironment@@XZ; GetLegacyBrowsingEnvironment(void)
0x18008666b  nop     dword ptr [rax+rax+00h]
0x180086670  mov     r8, rax
0x180086673  lea     rbx, [rdi+444h]
0x18008667a  mov     rdx, rbx
0x18008667d  mov     rcx, [rax]
0x180086680  mov     rax, [rcx+10h]
0x180086684  mov     rcx, r8
0x180086687  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008668c  xorps   xmm0, xmm0
0x18008668f  movups  xmmword ptr [rbx], xmm0
0x180086692  and     byte ptr [rdi+4C1h], 0FDh
0x180086699  jmp     loc_18008645C
0x18008669e  mov     rax, [rbx]
0x1800866a1  mov     rcx, rbx
0x1800866a4  mov     rax, [rax+18h]
0x1800866a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800866ad  mov     rax, [rbx]
0x1800866b0  mov     rcx, rbx
0x1800866b3  mov     rax, [rax+10h]
0x1800866b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800866bc  jmp     loc_180086495
```
