# SourceInitiatedSubscription::BookmarkCallback(WSMAN_SENDER_DETAILS_INTERNAL const *,void *)

- ea: `0x18000ada0`
- end: `0x18000b1f1`
- name: `?BookmarkCallback@SourceInitiatedSubscription@@CAPEAUWSMAN_OBJECT@@PEBVWSMAN_SENDER_DETAILS_INTERNAL@@PEAX@Z`
- size: `1105`
- prototype: `struct WSMAN_OBJECT *__fastcall(const struct WSMAN_SENDER_DETAILS_INTERNAL *, _QWORD *)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, service_task`

## callees

- `0x18000195c`
- `0x1800024b0`
- `0x180002510`
- `0x1800032dc`
- `0x180003430`
- `0x180007fc0`
- `0x18000ada0`
- `0x18000e134`
- `0x180011618`
- `0x18001fe50`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ae6f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ae6f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b113`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b13c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b113`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b13c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ae08`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000af84`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000adf5`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000adf5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000adde`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000adde`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000af7e`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000ae27`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000af7e`

## string_xrefs

- `0x18000b1c3`: `admin\wmi\events\forwarding\collector\service\submgr.cpp`

## pseudocode

```c
struct WSMAN_OBJECT *__fastcall SourceInitiatedSubscription::BookmarkCallback(
        const struct WSMAN_SENDER_DETAILS_INTERNAL *a1,
        _QWORD *a2)
{
  const struct WSMAN_SENDER_DETAILS_INTERNAL *v3; // r13
  HANDLE CurrentThread; // rax
  char v5; // si
  BOOL v6; // eax
  BOOL (__stdcall *v7)(HANDLE); // rax
  void *v8; // rcx
  __int64 v9; // r12
  SourceInitiatedSubscription *v10; // r15
  struct _RTL_CRITICAL_SECTION *v11; // rbx
  __int64 v12; // rcx
  __int128 *v13; // rax
  __int64 v14; // r14
  _BYTE *v15; // rax
  _QWORD *v16; // rax
  const wchar_t *v17; // rax
  const wchar_t *v18; // r8
  const wchar_t *v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // rax
  _QWORD *v22; // r9
  struct WSMAN_OBJECT *v23; // rdi
  struct WSMAN_OBJECT *result; // rax
  char v25; // al
  int v26; // r8d
  _QWORD *v27; // r9
  char v28; // [rsp+30h] [rbp-158h]
  void *TokenHandle; // [rsp+38h] [rbp-150h] BYREF
  __int128 v30; // [rsp+40h] [rbp-148h] BYREF
  SourceInitiatedSubscription *v31; // [rsp+50h] [rbp-138h]
  __int64 v32; // [rsp+58h] [rbp-130h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+60h] [rbp-128h]
  char v34; // [rsp+68h] [rbp-120h] BYREF
  const struct WSMAN_SENDER_DETAILS_INTERNAL *v35; // [rsp+70h] [rbp-118h]
  char v36[8]; // [rsp+78h] [rbp-110h] BYREF
  BOOL (__stdcall *v37)(HANDLE); // [rsp+80h] [rbp-108h]
  void *v38; // [rsp+88h] [rbp-100h]
  bool v39[8]; // [rsp+90h] [rbp-F8h] BYREF
  BOOL (__stdcall *v40)(PHANDLE, HANDLE); // [rsp+98h] [rbp-F0h]
  __int64 v41; // [rsp+A0h] [rbp-E8h]
  void *v42; // [rsp+A8h] [rbp-E0h]
  _BYTE v43[8]; // [rsp+B0h] [rbp-D8h] BYREF
  void (__fastcall *v44)(struct tag_EcRpcMetadataPropertyList *); // [rsp+B8h] [rbp-D0h]
  __int128 *v45; // [rsp+C0h] [rbp-C8h]
  wmi::Exception *v46; // [rsp+C8h] [rbp-C0h] BYREF
  _BYTE pExceptionObject[64]; // [rsp+D0h] [rbp-B8h] BYREF
  const wchar_t *v48; // [rsp+110h] [rbp-78h] BYREF
  int v49; // [rsp+118h] [rbp-70h]
  int v50; // [rsp+11Ch] [rbp-6Ch]
  const wchar_t *v51; // [rsp+120h] [rbp-68h]
  int v52; // [rsp+128h] [rbp-60h]
  int v53; // [rsp+12Ch] [rbp-5Ch]
  char *v54; // [rsp+130h] [rbp-58h]
  __int64 v55; // [rsp+138h] [rbp-50h]
  const wchar_t *v56; // [rsp+140h] [rbp-48h]
  __int64 v57; // [rsp+148h] [rbp-40h]

  v3 = a1;
  v35 = a1;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  v5 = 1;
  v6 = OpenThreadToken(CurrentThread, 4u, 1, &TokenHandle);
  try
  {
    if ( v6 )
    {
      SetThreadToken(0, 0);
      v7 = CloseHandle;
      v8 = TokenHandle;
      if ( TokenHandle )
      {
        v36[0] = 0;
LABEL_5:
        v37 = v7;
        v38 = v8;
        v39[0] = v8 == 0;
        v40 = SetThreadToken;
        v41 = 0;
        v42 = v8;
        v9 = *((_QWORD *)v3 + 5);
        v32 = v9;
        v10 = (SourceInitiatedSubscription *)a2[1];
        v31 = v10;
        v11 = (struct _RTL_CRITICAL_SECTION *)((char *)v10 + 16);
        lpCriticalSection = (LPCRITICAL_SECTION)((char *)v10 + 16);
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)v10 + 16));
        v28 = 1;
        v30 = 0;
        v12 = 16;
        v13 = &v30;
        do
        {
          *(_BYTE *)v13 = 0;
          v13 = (__int128 *)((char *)v13 + 1);
          --v12;
        }
        while ( v12 );
        LODWORD(v30) = 7;
        v14 = 168;
        v15 = operator new(0xA8u);
        *((_QWORD *)&v30 + 1) = v15;
        v43[0] = 0;
        v44 = CleanupMetadataPropList;
        v45 = &v30;
        do
        {
          *v15++ = 0;
          --v14;
        }
        while ( v14 );
        (*(void (__fastcall **)(SourceInitiatedSubscription *, __int64, __int128 *, _QWORD))(*(_QWORD *)v10 + 32LL))(
          v10,
          v9,
          &v30,
          0);
        if ( **((_DWORD **)&v30 + 1) == 2 )
        {
          if ( *(_DWORD *)(*((_QWORD *)&v30 + 1) + 8LL) == 1 )
          {
            v17 = (const wchar_t *)((char *)v10 + 56);
            if ( *((_QWORD *)v10 + 10) >= 8u )
              v17 = *(const wchar_t **)v17;
            v18 = &word_180026AD8;
            v19 = &word_180026AD8;
            if ( v17 )
              v19 = v17;
            v20 = -1;
            v21 = -1;
            do
              ++v21;
            while ( v19[v21] );
            v48 = v19;
            v49 = 2 * v21 + 2;
            v50 = 0;
            if ( v9 )
              v18 = (const wchar_t *)v9;
            do
              ++v20;
            while ( v18[v20] );
            v51 = v18;
            v52 = 2 * v20 + 2;
            v53 = 0;
            v54 = &v34;
            v55 = 4;
            v56 = L"\teventsource is disabled ";
            v57 = 52;
            (*(void (__fastcall **)(_QWORD, __int64 *, __int64, const wchar_t **))(**(_QWORD **)(*((_QWORD *)v10 + 13)
                                                                                               + 136LL)
                                                                                 + 8LL))(
              *(_QWORD *)(*((_QWORD *)v10 + 13) + 136LL),
              EVTCOLL_EVENT_SOURCE_UNAVAILABLE,
              4,
              &v48);
            v5 = 0;
            v28 = 0;
          }
          else if ( *(_DWORD *)(*((_QWORD *)&v30 + 1) + 8LL) == 3
                 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
                 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
          {
            v16 = (_QWORD *)((char *)v10 + 56);
            if ( *((_QWORD *)v10 + 10) >= 8u )
              v16 = (_QWORD *)*v16;
            WPP_SF_SS(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              79,
              (unsigned int)&WPP_311dc52e399f3c6238c54a9ac88e2061_Traceguids,
              v9,
              (__int64)v16);
          }
        }
        wmi::ScopeGuardImpl1<void (*)(std::vector<std::vector<unsigned short>> *),std::vector<std::vector<unsigned short>> *>::~ScopeGuardImpl1<void (*)(std::vector<std::vector<unsigned short>> *),std::vector<std::vector<unsigned short>> *>(v43);
        goto LABEL_53;
      }
    }
    else
    {
      TokenHandle = 0;
      v7 = CloseHandle;
    }
    v8 = 0;
    v36[0] = 1;
    goto LABEL_5;
  }
  catch ( ... )
  {
    v9 = v32;
    v10 = v31;
    v11 = lpCriticalSection;
    v5 = v28;
    v3 = v35;
  }
LABEL_53:
  if ( !v5 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 80, &WPP_311dc52e399f3c6238c54a9ac88e2061_Traceguids, 1168);
    }
    wmi::GenericException::GenericException(
      (wmi::GenericException *)pExceptionObject,
      0x490u,
      "admin\\wmi\\events\\forwarding\\collector\\service\\submgr.cpp",
      3236);
    throw (wmi::GenericException *)pExceptionObject;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    v22 = (_QWORD *)((char *)v10 + 56);
    if ( *((_QWORD *)v10 + 10) >= 8u )
      v22 = (_QWORD *)*v22;
    WPP_SF_SS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      81,
      (unsigned int)&WPP_311dc52e399f3c6238c54a9ac88e2061_Traceguids,
      (_DWORD)v22,
      v9);
  }
  try
  {
    v23 = SourceInitiatedSubscription::OnBookmarkCallback(v10, v3);
    LeaveCriticalSection(v11);
    wmi::ScopeGuardImpl2<int (*)(void * *,void *),void * *,void *>::~ScopeGuardImpl2<int (*)(void * *,void *),void * *,void *>(v39);
    wmi::ScopeGuardImpl1<void (*)(std::vector<std::vector<unsigned short>> *),std::vector<std::vector<unsigned short>> *>::~ScopeGuardImpl1<void (*)(std::vector<std::vector<unsigned short>> *),std::vector<std::vector<unsigned short>> *>(v36);
    result = v23;
  }
  catch ( wmi::Exception *v46 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v25 = (**(__int64 (__fastcall ***)(wmi::Exception *))v46)(v46);
      v27 = (_QWORD *)((char *)v31 + 56);
      if ( *((_QWORD *)v31 + 10) >= 8u )
        v27 = (_QWORD *)*v27;
      WPP_SF_SSD(*((_QWORD *)WPP_GLOBAL_Control + 2), 82, v26, (_DWORD)v27, v32, v25);
    }
    LeaveCriticalSection(lpCriticalSection);
    wmi::ScopeGuardImpl2<int (*)(void * *,void *),void * *,void *>::~ScopeGuardImpl2<int (*)(void * *,void *),void * *,void *>(v39);
    wmi::ScopeGuardImpl1<void (*)(std::vector<std::vector<unsigned short>> *),std::vector<std::vector<unsigned short>> *>::~ScopeGuardImpl1<void (*)(std::vector<std::vector<unsigned short>> *),std::vector<std::vector<unsigned short>> *>(v36);
    return 0;
  }
  v23 = SourceInitiatedSubscription::OnBookmarkCallback(v10, v3);
}

```

## disassembly

```asm
0x18000ada0  mov     [rsp+arg_10], rbx
0x18000ada5  mov     [rsp+arg_18], rsi
0x18000adaa  push    rdi
0x18000adab  push    r12
0x18000adad  push    r13
0x18000adaf  push    r14
0x18000adb1  push    r15
0x18000adb3  sub     rsp, 160h
0x18000adba  mov     rax, cs:__security_cookie
0x18000adc1  xor     rax, rsp
0x18000adc4  mov     [rsp+188h+var_38], rax
0x18000adcc  mov     r15, rdx
0x18000adcf  mov     r13, rcx
0x18000add2  mov     [rsp+188h+var_118], rcx
0x18000add7  xor     edi, edi
0x18000add9  mov     [rsp+188h+TokenHandle], rdi
0x18000adde  call    cs:__imp_GetCurrentThread
0x18000ade4  mov     rcx, rax; ThreadHandle
0x18000ade7  lea     r9, [rsp+188h+TokenHandle]; TokenHandle
0x18000adec  lea     esi, [rdi+1]
0x18000adef  mov     r8d, esi; OpenAsSelf
0x18000adf2  lea     edx, [rdi+4]; DesiredAccess
0x18000adf5  call    cs:__imp_OpenThreadToken
0x18000adfb  test    eax, eax
0x18000adfd  jnz     loc_18000AF7A
0x18000ae03  mov     [rsp+188h+TokenHandle], rdi
0x18000ae08  mov     rax, cs:__imp_CloseHandle
0x18000ae0f  mov     rcx, rdi
0x18000ae12  mov     [rsp+188h+var_110], sil
0x18000ae17  mov     [rsp+188h+var_108], rax
0x18000ae1f  mov     [rsp+188h+var_100], rcx
0x18000ae27  mov     rax, cs:__imp_SetThreadToken
0x18000ae2e  test    rcx, rcx
0x18000ae31  setz    [rsp+188h+var_F8]
0x18000ae39  mov     [rsp+188h+var_F0], rax
0x18000ae41  mov     [rsp+188h+var_E8], rdi
0x18000ae49  mov     [rsp+188h+var_E0], rcx
0x18000ae51  mov     r12, [r13+28h]
0x18000ae55  mov     [rsp+188h+var_130], r12
0x18000ae5a  mov     r15, [r15+8]
0x18000ae5e  mov     [rsp+188h+var_138], r15
0x18000ae63  lea     rbx, [r15+10h]
0x18000ae67  mov     [rsp+188h+lpCriticalSection], rbx
0x18000ae6c  mov     rcx, rbx; lpCriticalSection
0x18000ae6f  call    cs:__imp_EnterCriticalSection
0x18000ae75  nop
0x18000ae76  mov     [rsp+188h+var_158], sil
0x18000ae7b  xorps   xmm0, xmm0
0x18000ae7e  movups  [rsp+188h+var_148], xmm0
0x18000ae83  mov     ecx, 10h
0x18000ae88  lea     rax, [rsp+188h+var_148]
0x18000ae8d  mov     [rax], dil
0x18000ae90  add     rax, rsi
0x18000ae93  sub     rcx, rsi
0x18000ae96  jnz     short loc_18000AE8D
0x18000ae98  mov     dword ptr [rsp+188h+var_148], 7
0x18000aea0  mov     r14d, 0A8h
0x18000aea6  mov     ecx, r14d; dwBytes
0x18000aea9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000aeae  mov     qword ptr [rsp+188h+var_148+8], rax
0x18000aeb3  mov     [rsp+188h+var_D8], dil
0x18000aebb  lea     rcx, ?CleanupMetadataPropList@@YAXPEAUtag_EcRpcMetadataPropertyList@@@Z; CleanupMetadataPropList(tag_EcRpcMetadataPropertyList *)
0x18000aec2  mov     [rsp+188h+var_D0], rcx
0x18000aeca  lea     rcx, [rsp+188h+var_148]
0x18000aecf  mov     [rsp+188h+var_C8], rcx
0x18000aed7  mov     [rax], dil
0x18000aeda  add     rax, rsi
0x18000aedd  sub     r14, rsi
0x18000aee0  jnz     short loc_18000AED7
0x18000aee2  mov     rax, [r15]
0x18000aee5  xor     r9d, r9d
0x18000aee8  lea     r8, [rsp+188h+var_148]
0x18000aeed  mov     rdx, r12
0x18000aef0  mov     rcx, r15
0x18000aef3  mov     rax, [rax+20h]
0x18000aef7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aefc  mov     rcx, qword ptr [rsp+188h+var_148+8]
0x18000af01  cmp     dword ptr [rcx], 2
0x18000af04  jnz     loc_18000B081
0x18000af0a  mov     ecx, [rcx+8]
0x18000af0d  sub     ecx, 1
0x18000af10  jz      loc_18000AFA3
0x18000af16  cmp     ecx, 2
0x18000af19  jnz     loc_18000B081
0x18000af1f  lea     r14, WPP_GLOBAL_Control
0x18000af26  mov     rcx, cs:WPP_GLOBAL_Control
0x18000af2d  cmp     rcx, r14
0x18000af30  jz      loc_18000B088
0x18000af36  test    byte ptr [rcx+1Ch], 10h
0x18000af3a  jz      loc_18000B088
0x18000af40  cmp     byte ptr [rcx+19h], 3
0x18000af44  jb      loc_18000B088
0x18000af4a  lea     rax, [r15+38h]
0x18000af4e  cmp     qword ptr [rax+18h], 8
0x18000af53  jb      short loc_18000AF58
0x18000af55  mov     rax, [rax]
0x18000af58  mov     edx, 4Fh ; 'O'
0x18000af5d  mov     [rsp+188h+var_168], rax
0x18000af62  mov     r9, r12
0x18000af65  lea     r8, WPP_311dc52e399f3c6238c54a9ac88e2061_Traceguids
0x18000af6c  mov     rcx, [rcx+10h]
0x18000af70  call    WPP_SF_SS
0x18000af75  jmp     loc_18000B088
0x18000af7a  xor     edx, edx; Token
0x18000af7c  xor     ecx, ecx; Thread
0x18000af7e  call    cs:__imp_SetThreadToken
0x18000af84  mov     rax, cs:__imp_CloseHandle
0x18000af8b  mov     rcx, [rsp+188h+TokenHandle]
0x18000af90  test    rcx, rcx
0x18000af93  jz      loc_18000AE0F
0x18000af99  mov     [rsp+188h+var_110], dil
0x18000af9e  jmp     loc_18000AE17
0x18000afa3  lea     rax, [r15+38h]
0x18000afa7  cmp     qword ptr [rax+18h], 8
0x18000afac  jb      short loc_18000AFB1
0x18000afae  mov     rax, [rax]
0x18000afb1  lea     r8, word_180026AD8
0x18000afb8  mov     rdx, r8
0x18000afbb  test    rax, rax
0x18000afbe  cmovnz  rdx, rax
0x18000afc2  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000afc6  mov     rax, rcx
0x18000afc9  inc     rax
0x18000afcc  cmp     [rdx+rax*2], di
0x18000afd0  jnz     short loc_18000AFC9
0x18000afd2  mov     [rsp+188h+var_78], rdx
0x18000afda  lea     eax, ds:2[rax*2]
0x18000afe1  mov     [rsp+188h+var_70], eax
0x18000afe8  mov     [rsp+188h+var_6C], edi
0x18000afef  test    r12, r12
0x18000aff2  cmovnz  r8, r12
0x18000aff6  inc     rcx
0x18000aff9  cmp     [r8+rcx*2], di
0x18000affe  jnz     short loc_18000AFF6
0x18000b000  mov     [rsp+188h+var_68], r8
0x18000b008  lea     eax, ds:2[rcx*2]
0x18000b00f  mov     [rsp+188h+var_60], eax
0x18000b016  mov     [rsp+188h+var_5C], edi
0x18000b01d  lea     rax, [rsp+188h+var_120]
0x18000b022  mov     [rsp+188h+var_58], rax
0x18000b02a  mov     r8d, 4
0x18000b030  mov     [rsp+188h+var_50], r8
0x18000b038  lea     rax, aEventsourceIsD; "\teventsource is disabled "
0x18000b03f  mov     [rsp+188h+var_48], rax
0x18000b047  mov     [rsp+188h+var_40], 34h ; '4'
0x18000b053  mov     rax, [r15+68h]
0x18000b057  mov     rcx, [rax+88h]
0x18000b05e  mov     rax, [rcx]
0x18000b061  lea     r9, [rsp+188h+var_78]
0x18000b069  lea     rdx, EVTCOLL_EVENT_SOURCE_UNAVAILABLE
0x18000b070  mov     rax, [rax+8]
0x18000b074  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b079  mov     sil, dil
0x18000b07c  mov     [rsp+188h+var_158], dil
0x18000b081  lea     r14, WPP_GLOBAL_Control
0x18000b088  lea     rcx, [rsp+188h+var_D8]
0x18000b090  call    ??1?$ScopeGuardImpl1@P6AXPEAV?$vector@V?$vector@GV?$allocator@G@std@@@std@@V?$allocator@V?$vector@GV?$allocator@G@std@@@std@@@2@@std@@@ZPEAV12@@wmi@@QEAA@XZ; wmi::ScopeGuardImpl1<void (*)(std::vector<std::vector<ushort>> *),std::vector<std::vector<ushort>> *>::~ScopeGuardImpl1<void (*)(std::vector<std::vector<ushort>> *),std::vector<std::vector<ushort>> *>(void)
0x18000b095  nop
0x18000b096  jmp     short loc_18000B0B8
0x18000b098  lea     r14, WPP_GLOBAL_Control
0x18000b09f  mov     r12, [rsp+188h+var_130]
0x18000b0a4  mov     r15, [rsp+188h+var_138]
0x18000b0a9  mov     rbx, [rsp+188h+lpCriticalSection]
0x18000b0ae  mov     sil, [rsp+188h+var_158]
0x18000b0b3  mov     r13, [rsp+188h+var_118]
0x18000b0b8  test    sil, sil
0x18000b0bb  jz      loc_18000B18A
0x18000b0c1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b0c8  cmp     rcx, r14
0x18000b0cb  jz      short loc_18000B102
0x18000b0cd  test    byte ptr [rcx+1Ch], 10h
0x18000b0d1  jz      short loc_18000B102
0x18000b0d3  cmp     byte ptr [rcx+19h], 5
0x18000b0d7  jb      short loc_18000B102
0x18000b0d9  lea     r9, [r15+38h]
0x18000b0dd  cmp     qword ptr [r9+18h], 8
0x18000b0e2  jb      short loc_18000B0E7
0x18000b0e4  mov     r9, [r9]
0x18000b0e7  mov     edx, 51h ; 'Q'
0x18000b0ec  mov     [rsp+188h+var_168], r12
0x18000b0f1  lea     r8, WPP_311dc52e399f3c6238c54a9ac88e2061_Traceguids
0x18000b0f8  mov     rcx, [rcx+10h]
0x18000b0fc  call    WPP_SF_SS
0x18000b101  nop
0x18000b102  mov     rdx, r13; struct WSMAN_SENDER_DETAILS_INTERNAL *
0x18000b105  mov     rcx, r15; this
0x18000b108  call    ?OnBookmarkCallback@SourceInitiatedSubscription@@AEAAPEAUWSMAN_OBJECT@@PEBVWSMAN_SENDER_DETAILS_INTERNAL@@@Z; SourceInitiatedSubscription::OnBookmarkCallback(WSMAN_SENDER_DETAILS_INTERNAL const *)
0x18000b10d  mov     rdi, rax
0x18000b110  mov     rcx, rbx; lpCriticalSection
0x18000b113  call    cs:__imp_LeaveCriticalSection
0x18000b119  nop
0x18000b11a  lea     rcx, [rsp+188h+var_F8]
0x18000b122  call    ??1?$ScopeGuardImpl2@P6AHPEAPEAXPEAX@ZPEAPEAXPEAX@wmi@@QEAA@XZ; wmi::ScopeGuardImpl2<int (*)(void * *,void *),void * *,void *>::~ScopeGuardImpl2<int (*)(void * *,void *),void * *,void *>(void)
0x18000b127  nop
0x18000b128  lea     rcx, [rsp+188h+var_110]
0x18000b12d  call    ??1?$ScopeGuardImpl1@P6AXPEAV?$vector@V?$vector@GV?$allocator@G@std@@@std@@V?$allocator@V?$vector@GV?$allocator@G@std@@@std@@@2@@std@@@ZPEAV12@@wmi@@QEAA@XZ; wmi::ScopeGuardImpl1<void (*)(std::vector<std::vector<ushort>> *),std::vector<std::vector<ushort>> *>::~ScopeGuardImpl1<void (*)(std::vector<std::vector<ushort>> *),std::vector<std::vector<ushort>> *>(void)
0x18000b132  mov     rax, rdi
0x18000b135  jmp     short loc_18000B15D
0x18000b137  mov     rcx, [rsp+188h+lpCriticalSection]; lpCriticalSection
0x18000b13c  call    cs:__imp_LeaveCriticalSection
0x18000b142  nop
0x18000b143  lea     rcx, [rsp+188h+var_F8]
0x18000b14b  call    ??1?$ScopeGuardImpl2@P6AHPEAPEAXPEAX@ZPEAPEAXPEAX@wmi@@QEAA@XZ; wmi::ScopeGuardImpl2<int (*)(void * *,void *),void * *,void *>::~ScopeGuardImpl2<int (*)(void * *,void *),void * *,void *>(void)
0x18000b150  nop
0x18000b151  lea     rcx, [rsp+188h+var_110]
0x18000b156  call    ??1?$ScopeGuardImpl1@P6AXPEAV?$vector@V?$vector@GV?$allocator@G@std@@@std@@V?$allocator@V?$vector@GV?$allocator@G@std@@@std@@@2@@std@@@ZPEAV12@@wmi@@QEAA@XZ; wmi::ScopeGuardImpl1<void (*)(std::vector<std::vector<ushort>> *),std::vector<std::vector<ushort>> *>::~ScopeGuardImpl1<void (*)(std::vector<std::vector<ushort>> *),std::vector<std::vector<ushort>> *>(void)
0x18000b15b  xor     eax, eax
0x18000b15d  mov     rcx, [rsp+188h+var_38]
0x18000b165  xor     rcx, rsp; StackCookie
0x18000b168  call    __security_check_cookie
0x18000b16d  lea     r11, [rsp+188h+var_28]
0x18000b175  mov     rbx, [r11+40h]
0x18000b179  mov     rsi, [r11+48h]
0x18000b17d  mov     rsp, r11
0x18000b180  pop     r15
0x18000b182  pop     r14
0x18000b184  pop     r13
0x18000b186  pop     r12
0x18000b188  pop     rdi
0x18000b189  retn
0x18000b18a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b191  cmp     rcx, r14
0x18000b194  jz      short loc_18000B1BD
0x18000b196  test    byte ptr [rcx+1Ch], 10h
0x18000b19a  jz      short loc_18000B1BD
0x18000b19c  cmp     byte ptr [rcx+19h], 2
0x18000b1a0  jb      short loc_18000B1BD
0x18000b1a2  mov     edx, 50h ; 'P'
0x18000b1a7  mov     r9d, 490h
0x18000b1ad  lea     r8, WPP_311dc52e399f3c6238c54a9ac88e2061_Traceguids
0x18000b1b4  mov     rcx, [rcx+10h]
0x18000b1b8  call    WPP_SF_D
0x18000b1bd  mov     r9d, 0CA4h; int
0x18000b1c3  lea     r8, aAdminWmiEvents_8; "admin\\wmi\\events\\forwarding\\collect"...
0x18000b1ca  mov     edx, 490h; unsigned int
0x18000b1cf  lea     rcx, [rsp+188h+pExceptionObject]; this
0x18000b1d7  call    ??0GenericException@wmi@@QEAA@KPEBDH@Z; wmi::GenericException::GenericException(ulong,char const *,int)
0x18000b1dc  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18000b1e3  lea     rcx, [rsp+188h+pExceptionObject]; pExceptionObject
0x18000b1eb  call    _CxxThrowException_0
```
