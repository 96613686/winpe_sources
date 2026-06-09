# WsiEnvironmentAccountManager::GetUserSessionIdsByType(WsiEnvironmentAccountManager::UserType,ulong *,ulong * *)

- ea: `0x1800143a8`
- end: `0x18001471d`
- name: `?GetUserSessionIdsByType@WsiEnvironmentAccountManager@@AEAAJW4UserType@1@PEAKPEAPEAK@Z`
- size: `885`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180013904`
- `0x1800d814c`

## callees

- `0x1800088e8`
- `0x180013b84`
- `0x1800143a8`
- `0x180014724`
- `0x180014e7c`
- `0x180015960`
- `0x180053cf8`
- `0x180061e1c`
- `0x18006c426`
- `0x18006da60`
- `0x18006f1c9`
- `0x1800d7434`
- `0x1800de450`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800145ce`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800145fd`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001466c`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800146a1`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800145ce`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800145fd`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001466c`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800146a1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001451a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001451a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800144f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800145be`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800144f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800145be`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsW` at `0x18001442e`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsW` at `0x18001442e`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x1800144c8`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x1800144c8`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x18001444f`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x1800146b7`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x1800146ee`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x18001444f`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x1800146b7`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x1800146ee`

## string_xrefs

- `0x18001445d`: `onecore\ds\security\umstartup\wsienvironmentaccountmanager\wsienvironmentaccountmanager.cpp`
- `0x18001459d`: `onecore\ds\security\umstartup\wsienvironmentaccountmanager\wsienvironmentaccountmanager.cpp`
- `0x180014648`: `onecore\ds\security\umstartup\wsienvironmentaccountmanager\wsienvironmentaccountmanager.cpp`
- `0x1800146cd`: `onecore\ds\security\umstartup\wsienvironmentaccountmanager\wsienvironmentaccountmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall WsiEnvironmentAccountManager::GetUserSessionIdsByType(
        WsiEnvironmentAccountManager *a1,
        int a2,
        _DWORD *a3,
        _QWORD *a4)
{
  BOOL v8; // ebx
  PWTS_SESSION_INFOW v9; // r8
  const char *v10; // r9
  void *v11; // rcx
  unsigned int LastError; // ebx
  DWORD i; // edi
  char *v14; // rbx
  BOOL v15; // eax
  unsigned int v16; // r8d
  const char *v17; // r9
  wil::details::in1diag3 *v18; // rcx
  __int64 v19; // rdx
  void *v20; // rcx
  BOOL v21; // eax
  int IsWsiEnvironmentUserInternal; // eax
  PVOID v23; // rcx
  PWTS_SESSION_INFOW v24; // rdi
  PVOID v25; // rcx
  signed __int64 v26; // rsi
  int v27; // eax
  void *v28; // rbx
  int pCount; // [rsp+20h] [rbp-99h]
  int pCounta; // [rsp+20h] [rbp-99h]
  PVOID pMemory; // [rsp+30h] [rbp-89h] BYREF
  void *phToken; // [rsp+38h] [rbp-81h] BYREF
  DWORD v34; // [rsp+40h] [rbp-79h] BYREF
  int v35; // [rsp+44h] [rbp-75h] BYREF
  PWTS_SESSION_INFOW ppSessionInfo[2]; // [rsp+48h] [rbp-71h] BYREF
  __int64 v37; // [rsp+58h] [rbp-61h]
  DWORD ReturnLength[4]; // [rsp+60h] [rbp-59h] BYREF
  void *TokenInformation[12]; // [rsp+70h] [rbp-49h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  *a3 = 0;
  *a4 = 0;
  pMemory = 0;
  v34 = 0;
  if ( !(unsigned __int8)IsWTSEnumerateSessionsWPresent() || !(unsigned __int8)IsWTSEnumerateSessionsWPresent() )
  {
    LastError = -2147467263;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7F,
      (unsigned int)"onecore\\ds\\security\\umstartup\\wsienvironmentaccountmanager\\wsienvironmentaccountmanager.cpp",
      (const char *)0x80004001LL,
      pCount);
    goto LABEL_48;
  }
  ppSessionInfo[0] = (PWTS_SESSION_INFOW)&pMemory;
  ppSessionInfo[1] = 0;
  LOBYTE(v37) = 1;
  v8 = WTSEnumerateSessionsW(0, 0, 1u, &ppSessionInfo[1], &v34);
  if ( (_BYTE)v37 )
  {
    v9 = ppSessionInfo[0];
    v11 = *(void **)ppSessionInfo[0];
    *(_QWORD *)ppSessionInfo[0] = ppSessionInfo[1];
    if ( v11 )
      WTSFreeMemory(v11);
  }
  if ( !v8 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x81,
                  (unsigned int)"onecore\\ds\\security\\umstartup\\wsienvironmentaccountmanager\\wsienvironmentaccountmanager.cpp",
                  v10);
LABEL_48:
    v23 = pMemory;
    pMemory = 0;
    goto LABEL_49;
  }
  *(_OWORD *)ppSessionInfo = 0;
  v37 = 0;
  for ( i = 0; i < v34; ++i )
  {
    v14 = 0;
    phToken = 0;
    memset_0(TokenInformation, 0, 0x54u);
    ReturnLength[0] = 0;
    if ( !*((_DWORD *)pMemory + 6 * i) )
      goto LABEL_14;
    phToken = 0;
    v15 = WTSQueryUserToken(*((_DWORD *)pMemory + 6 * i), &phToken);
    v18 = retaddr;
    if ( !v15 )
    {
      v19 = 139;
      goto LABEL_13;
    }
    v21 = GetTokenInformation(phToken, TokenUser, TokenInformation, 0x54u, ReturnLength);
    v18 = retaddr;
    if ( !v21 )
    {
      v19 = 140;
LABEL_13:
      wil::details::in1diag3::_Log_GetLastError(v18, (void *)v19, v16, v17);
      v14 = (char *)phToken;
LABEL_14:
      if ( (unsigned __int64)(v14 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
        continue;
      v20 = v14;
LABEL_16:
      CloseHandle(v20);
      continue;
    }
    v35 = 0;
    IsWsiEnvironmentUserInternal = WsiEnvironmentAccountManager::IsWsiEnvironmentUserInternal(
                                     a1,
                                     TokenInformation[0],
                                     &v35);
    LastError = IsWsiEnvironmentUserInternal;
    if ( IsWsiEnvironmentUserInternal < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x93,
        (unsigned int)"onecore\\ds\\security\\umstartup\\wsienvironmentaccountmanager\\wsienvironmentaccountmanager.cpp",
        (const char *)(unsigned int)IsWsiEnvironmentUserInternal,
        pCounta);
      if ( (char *)phToken - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(phToken);
      if ( ppSessionInfo[0] )
        operator delete(ppSessionInfo[0]);
      v23 = pMemory;
      pMemory = 0;
      goto LABEL_49;
    }
    if ( a2 == 1 && !v35 || a2 == 2 && v35 )
    {
      v20 = phToken;
      if ( (char *)phToken - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        goto LABEL_16;
    }
    else
    {
      std::vector<unsigned long>::push_back(ppSessionInfo, (char *)pMemory + 24 * i);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phToken);
    }
  }
  v24 = ppSessionInfo[0];
  if ( ppSessionInfo[0] == ppSessionInfo[1] )
  {
    if ( ppSessionInfo[0] )
      operator delete(ppSessionInfo[0]);
    v25 = pMemory;
    pMemory = 0;
    goto LABEL_44;
  }
  v26 = ((char *)ppSessionInfo[1] - (char *)ppSessionInfo[0]) >> 2;
  phToken = 0;
  v27 = CamAllocBuffer<unsigned long>(4 * v26, (char **)&phToken, (__int64)v9, v10);
  LastError = v27;
  if ( v27 >= 0 )
  {
    v28 = phToken;
    memcpy_0(phToken, v24, 4 * v26);
    *a3 = v26;
    *a4 = v28;
    if ( v24 )
      operator delete(v24);
    v25 = pMemory;
    pMemory = 0;
LABEL_44:
    if ( v25 )
      WTSFreeMemory(v25);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA5,
      (unsigned int)"onecore\\ds\\security\\umstartup\\wsienvironmentaccountmanager\\wsienvironmentaccountmanager.cpp",
      (const char *)(unsigned int)v27,
      pCounta);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&phToken);
    if ( v24 )
      operator delete(v24);
    v23 = pMemory;
    pMemory = 0;
LABEL_49:
    if ( v23 )
      WTSFreeMemory(v23);
    return LastError;
  }
}

```

## disassembly

```asm
0x1800143a8  mov     [rsp-8+arg_8], rbx
0x1800143ad  push    rbp
0x1800143ae  push    rsi
0x1800143af  push    rdi
0x1800143b0  push    r12
0x1800143b2  push    r13
0x1800143b4  push    r14
0x1800143b6  push    r15
0x1800143b8  lea     rbp, [rsp-27h]
0x1800143bd  sub     rsp, 0E0h
0x1800143c4  mov     rax, cs:__security_cookie
0x1800143cb  xor     rax, rsp
0x1800143ce  mov     [rbp+57h+var_40], rax
0x1800143d2  mov     r12, r9
0x1800143d5  mov     r15, r8
0x1800143d8  mov     r14d, edx
0x1800143db  mov     r13, rcx
0x1800143de  xor     esi, esi
0x1800143e0  mov     [r8], esi
0x1800143e3  mov     [r9], rsi
0x1800143e6  mov     [rsp+110h+pMemory], rsi
0x1800143eb  mov     [rbp+57h+var_D0], esi
0x1800143ee  call    IsWTSEnumerateSessionsWPresent
0x1800143f3  test    al, al
0x1800143f5  jz      loc_1800146C1
0x1800143fb  call    IsWTSEnumerateSessionsWPresent
0x180014400  test    al, al
0x180014402  jz      loc_1800146C1
0x180014408  lea     rax, [rsp+110h+pMemory]
0x18001440d  mov     [rbp+57h+ppSessionInfo], rax
0x180014411  mov     [rbp+57h+ppSessionInfo+8], rsi
0x180014415  mov     byte ptr [rbp+57h+var_B8], 1
0x180014419  lea     rax, [rbp+57h+var_D0]
0x18001441d  mov     qword ptr [rsp+110h+pCount], rax; int
0x180014422  lea     r9, [rbp+57h+ppSessionInfo+8]; ppSessionInfo
0x180014426  xor     edx, edx; Reserved
0x180014428  xor     ecx, ecx; hServer
0x18001442a  lea     r8d, [rsi+1]; Version
0x18001442e  call    cs:__imp_WTSEnumerateSessionsW
0x180014434  mov     ebx, eax
0x180014436  cmp     byte ptr [rbp+57h+var_B8], sil
0x18001443a  jz      short loc_180014455
0x18001443c  mov     r8, [rbp+57h+ppSessionInfo]
0x180014440  mov     rcx, [r8]; pMemory
0x180014443  mov     rdx, [rbp+57h+ppSessionInfo+8]
0x180014447  mov     [r8], rdx
0x18001444a  test    rcx, rcx
0x18001444d  jz      short loc_180014455
0x18001444f  call    cs:__imp_WTSFreeMemory
0x180014455  test    ebx, ebx
0x180014457  jnz     short loc_180014475
0x180014459  mov     rcx, [rbp+5Fh]; this
0x18001445d  lea     r8, aOnecoreDsSecur_42; "onecore\\ds\\security\\umstartup\\wsien"...
0x180014464  mov     edx, 81h; void *
0x180014469  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001446e  mov     ebx, eax
0x180014470  jmp     loc_1800146DF
0x180014475  xorps   xmm0, xmm0
0x180014478  movdqu  xmmword ptr [rbp+57h+ppSessionInfo], xmm0
0x18001447d  mov     [rbp+57h+var_B8], rsi
0x180014481  mov     edi, esi
0x180014483  cmp     edi, [rbp+57h+var_D0]
0x180014486  jnb     loc_1800145E8
0x18001448c  mov     rbx, rsi
0x18001448f  mov     [rsp+110h+phToken], rbx
0x180014494  xor     edx, edx; Val
0x180014496  lea     r8d, [rdx+54h]; Size
0x18001449a  lea     rcx, [rbp+57h+TokenInformation]; void *
0x18001449e  call    memset_0
0x1800144a3  mov     [rbp+57h+ReturnLength], esi
0x1800144a6  mov     eax, edi
0x1800144a8  lea     rsi, [rax+rax*2]
0x1800144ac  mov     rcx, [rsp+110h+pMemory]
0x1800144b1  cmp     dword ptr [rcx+rsi*8], 0
0x1800144b5  jz      short loc_1800144E5
0x1800144b7  mov     [rsp+110h+phToken], 0
0x1800144c0  lea     rdx, [rsp+110h+phToken]; phToken
0x1800144c5  mov     ecx, [rcx+rsi*8]; SessionId
0x1800144c8  call    cs:__imp_WTSQueryUserToken
0x1800144ce  mov     rcx, [rbp+5Fh]; this
0x1800144d2  test    eax, eax
0x1800144d4  jnz     short loc_1800144FE
0x1800144d6  mov     edx, 8Bh; void *
0x1800144db  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x1800144e0  mov     rbx, [rsp+110h+phToken]
0x1800144e5  lea     rax, [rbx-1]
0x1800144e9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800144ed  ja      short loc_1800144F8
0x1800144ef  mov     rcx, rbx; hObject
0x1800144f2  call    cs:__imp_CloseHandle
0x1800144f8  inc     edi
0x1800144fa  xor     esi, esi
0x1800144fc  jmp     short loc_180014483
0x1800144fe  lea     rax, [rbp+57h+ReturnLength]
0x180014502  mov     qword ptr [rsp+110h+pCount], rax; int
0x180014507  mov     r9d, 54h ; 'T'; TokenInformationLength
0x18001450d  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x180014511  lea     edx, [r9-53h]; TokenInformationClass
0x180014515  mov     rcx, [rsp+110h+phToken]; TokenHandle
0x18001451a  call    cs:__imp_GetTokenInformation
0x180014520  mov     rcx, [rbp+5Fh]
0x180014524  test    eax, eax
0x180014526  jnz     short loc_18001452F
0x180014528  mov     edx, 8Ch
0x18001452d  jmp     short loc_1800144DB
0x18001452f  mov     [rbp+57h+var_CC], 0
0x180014536  lea     r8, [rbp+57h+var_CC]; int *
0x18001453a  mov     rdx, [rbp+57h+TokenInformation]; void *
0x18001453e  mov     rcx, r13; this
0x180014541  call    ?IsWsiEnvironmentUserInternal@WsiEnvironmentAccountManager@@AEAAJQEAXPEAH@Z; WsiEnvironmentAccountManager::IsWsiEnvironmentUserInternal(void * const,int *)
0x180014546  mov     ebx, eax
0x180014548  test    eax, eax
0x18001454a  js      short loc_180014596
0x18001454c  mov     eax, [rbp+57h+var_CC]
0x18001454f  cmp     r14d, 1
0x180014553  jnz     short loc_180014559
0x180014555  test    eax, eax
0x180014557  jz      short loc_180014563
0x180014559  cmp     r14d, 2
0x18001455d  jnz     short loc_180014574
0x18001455f  test    eax, eax
0x180014561  jz      short loc_180014574
0x180014563  mov     rcx, [rsp+110h+phToken]
0x180014568  lea     rax, [rcx-1]
0x18001456c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180014570  jbe     short loc_1800144F2
0x180014572  jmp     short loc_1800144F8
0x180014574  mov     rax, [rsp+110h+pMemory]
0x180014579  lea     rdx, [rax+rsi*8]
0x18001457d  lea     rcx, [rbp+57h+ppSessionInfo]
0x180014581  call    ?push_back@?$vector@KV?$allocator@K@std@@@std@@QEAAXAEBK@Z; std::vector<ulong>::push_back(ulong const &)
0x180014586  nop
0x180014587  lea     rcx, [rsp+110h+phToken]
0x18001458c  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180014591  jmp     loc_1800144F8
0x180014596  mov     rcx, [rbp+5Fh]; this
0x18001459a  mov     r9d, ebx; char *
0x18001459d  lea     r8, aOnecoreDsSecur_42; "onecore\\ds\\security\\umstartup\\wsien"...
0x1800145a4  mov     edx, 93h; void *
0x1800145a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800145ae  nop
0x1800145af  mov     rcx, [rsp+110h+phToken]; hObject
0x1800145b4  lea     rax, [rcx-1]
0x1800145b8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800145bc  ja      short loc_1800145C5
0x1800145be  call    cs:__imp_CloseHandle
0x1800145c4  nop
0x1800145c5  mov     rcx, [rbp+57h+ppSessionInfo]
0x1800145c9  test    rcx, rcx
0x1800145cc  jz      short loc_1800145D5
0x1800145ce  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800145d4  nop
0x1800145d5  mov     rcx, [rsp+110h+pMemory]
0x1800145da  mov     [rsp+110h+pMemory], 0
0x1800145e3  jmp     loc_1800146E9
0x1800145e8  mov     rdi, [rbp+57h+ppSessionInfo]
0x1800145ec  mov     rsi, [rbp+57h+ppSessionInfo+8]
0x1800145f0  cmp     rdi, rsi
0x1800145f3  jnz     short loc_180014617
0x1800145f5  test    rdi, rdi
0x1800145f8  jz      short loc_180014604
0x1800145fa  mov     rcx, rdi
0x1800145fd  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180014603  nop
0x180014604  mov     rcx, [rsp+110h+pMemory]
0x180014609  mov     [rsp+110h+pMemory], 0
0x180014612  jmp     loc_1800146B2
0x180014617  sub     rsi, rdi
0x18001461a  sar     rsi, 2
0x18001461e  lea     r14, ds:0[rsi*4]
0x180014626  xor     r13d, r13d
0x180014629  mov     [rsp+110h+phToken], r13
0x18001462e  lea     rdx, [rsp+110h+phToken]
0x180014633  mov     rcx, r14
0x180014636  call    ??$CamAllocBuffer@K@@YAJ_KPEAPEAK@Z; CamAllocBuffer<ulong>(unsigned __int64,ulong * *)
0x18001463b  mov     ebx, eax
0x18001463d  test    eax, eax
0x18001463f  jns     short loc_18001467F
0x180014641  mov     rcx, [rbp+5Fh]; this
0x180014645  mov     r9d, eax; char *
0x180014648  lea     r8, aOnecoreDsSecur_42; "onecore\\ds\\security\\umstartup\\wsien"...
0x18001464f  mov     edx, 0A5h; void *
0x180014654  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014659  lea     rcx, [rsp+110h+phToken]
0x18001465e  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AJPEAX@Z$1?CamFreeBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180014663  nop
0x180014664  test    rdi, rdi
0x180014667  jz      short loc_180014673
0x180014669  mov     rcx, rdi
0x18001466c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180014672  nop
0x180014673  mov     rcx, [rsp+110h+pMemory]
0x180014678  mov     [rsp+110h+pMemory], r13
0x18001467d  jmp     short loc_1800146E9
0x18001467f  mov     r8, r14; Size
0x180014682  mov     rdx, rdi; Src
0x180014685  mov     rbx, [rsp+110h+phToken]
0x18001468a  mov     rcx, rbx; void *
0x18001468d  call    memcpy_0
0x180014692  mov     [r15], esi
0x180014695  mov     [r12], rbx
0x180014699  test    rdi, rdi
0x18001469c  jz      short loc_1800146A8
0x18001469e  mov     rcx, rdi
0x1800146a1  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800146a7  nop
0x1800146a8  mov     rcx, [rsp+110h+pMemory]; pMemory
0x1800146ad  mov     [rsp+110h+pMemory], r13
0x1800146b2  test    rcx, rcx
0x1800146b5  jz      short loc_1800146BD
0x1800146b7  call    cs:__imp_WTSFreeMemory
0x1800146bd  xor     eax, eax
0x1800146bf  jmp     short loc_1800146F6
0x1800146c1  mov     rcx, [rbp+5Fh]; this
0x1800146c5  mov     ebx, 80004001h
0x1800146ca  mov     r9d, ebx; char *
0x1800146cd  lea     r8, aOnecoreDsSecur_42; "onecore\\ds\\security\\umstartup\\wsien"...
0x1800146d4  mov     edx, 7Fh; void *
0x1800146d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800146de  nop
0x1800146df  mov     rcx, [rsp+110h+pMemory]; pMemory
0x1800146e4  mov     [rsp+110h+pMemory], rsi
0x1800146e9  test    rcx, rcx
0x1800146ec  jz      short loc_1800146F4
0x1800146ee  call    cs:__imp_WTSFreeMemory
0x1800146f4  mov     eax, ebx
0x1800146f6  mov     rcx, [rbp+57h+var_40]
0x1800146fa  xor     rcx, rsp; StackCookie
0x1800146fd  call    __security_check_cookie
0x180014702  mov     rbx, [rsp+110h+arg_8]
0x18001470a  add     rsp, 0E0h
0x180014711  pop     r15
0x180014713  pop     r14
0x180014715  pop     r13
0x180014717  pop     r12
0x180014719  pop     rdi
0x18001471a  pop     rsi
0x18001471b  pop     rbp
0x18001471c  retn
```
