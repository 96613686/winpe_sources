# InitializeSCMBeforeListen

- ea: `0x1800ed100`
- end: `0x1800ed64a`
- name: `InitializeSCMBeforeListen`
- size: `1354`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800b74b4`

## callees

- `0x180005c40`
- `0x180034540`
- `0x1800592e0`
- `0x18007e3d4`
- `0x180083810`
- `0x1800b27e0`
- `0x1800bfddc`
- `0x1800e9694`
- `0x1800e97b4`
- `0x1800e99c0`
- `0x1800e9ba8`
- `0x1800e9cd4`
- `0x1800ec7b0`
- `0x1800ed100`
- `0x1801082a0`
- `0x18010983c`

## import_xrefs

- `ntdll!RtlAllocateAndInitializeSid` at `0x1800ed1da`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1800ed244`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1800ed1da`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1800ed244`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ed153`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ed153`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ed2d4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ed30b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ed342`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ed38d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ed3c3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ed3ff`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ed439`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ed477`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ed4be`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ed4e7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ed51f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ed554`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ed591`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ed2d4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ed30b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ed342`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ed38d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ed3c3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ed3ff`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ed439`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ed477`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ed4be`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ed4e7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ed51f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ed554`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ed591`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800ed141`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800ed141`

## string_xrefs

- `0x1800ed196`: `onecore\com\combase\rpcss\olescm\scmsvc.cxx`

## pseudocode

```c
__int64 InitializeSCMBeforeListen()
{
  unsigned int LastError; // ebx
  const wchar_t *v1; // rax
  unsigned int v2; // r8d
  __int64 result; // rax
  CSharedLock *v4; // rax
  CSharedLock *v5; // rax
  CSharedLock *v6; // rax
  LPVOID v7; // rax
  LPVOID v8; // rax
  CClassicComServerTable *v9; // rax
  LPVOID v10; // rax
  LPVOID v11; // rax
  ObjexHashTable::CHashTable *v12; // rax
  ObjexHashTable::CHashTable *v13; // rbx
  struct CSurrogateList *v14; // rax
  HANDLE v15; // rcx
  CSharedLock *v16; // rax
  _DWORD *v17; // rax
  HANDLE v18; // rcx
  CNamedObjectTable *v19; // rax
  char *v20; // rax
  struct CActivationStateList *v21; // rbx
  int v22; // eax
  int v23; // [rsp+60h] [rbp+17h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+64h] [rbp+1Bh] BYREF

  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  gpClientLock.Ptr = 0;
  gpServerLock.Ptr = 0;
  g_hServiceController = OpenSCManagerW(0, 0, 1u);
  if ( !g_hServiceController )
  {
    LastError = GetLastError();
    if ( !dword_18014E4B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled((unsigned int)dword_18014E4B8)) )
      return LastError;
    v1 = (const wchar_t *)L"%!WINERROR!";
    v2 = 474;
LABEL_6:
    ComTraceMessageT<long>(
      (__int64)"onecore\\com\\combase\\rpcss\\olescm\\scmsvc.cxx",
      (__int64)"InitializeSCMBeforeListen",
      v2,
      0,
      (__int64)v1,
      LastError);
    return LastError;
  }
  LastError = RtlAllocateAndInitializeSid(&IdentifierAuthority, 1u, 0x14u, 0, 0, 0, 0, 0, 0, 0, &psidStateServiceSid);
  if ( (LastError & 0x80000000) != 0 )
  {
    if ( !dword_18014E4B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled((unsigned int)dword_18014E4B8)) )
      return LastError;
    v1 = L"%!STATUS!";
    v2 = 494;
    goto LABEL_6;
  }
  LastError = RtlAllocateAndInitializeSid(&IdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &psidLaunchServiceSid);
  if ( (LastError & 0x80000000) != 0 )
  {
    if ( !dword_18014E4B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled((unsigned int)dword_18014E4B8)) )
      return LastError;
    v1 = L"%!STATUS!";
    v2 = 511;
    goto LABEL_6;
  }
  result = InitializeSystemSecurityDescriptors();
  v23 = result;
  if ( !(_DWORD)result )
  {
    ReadRemoteActivationKeys();
    ReadRemoteBindingHandleCacheKeys();
    ReadSAFERKeys();
    ReadDynamicIPChangesKeys();
    ReadEELoggingKeys();
    if ( (unsigned int)CMutexSem2::FInit((CMutexSem2 *)qword_18014E9F8) )
    {
      v4 = (CSharedLock *)HeapAlloc(g_hHeap, 0, 0x48u);
      if ( v4 )
      {
        gpClassLock = (LPCRITICAL_SECTION)CSharedLock::CSharedLock(v4, &v23);
        if ( gpClassLock )
        {
          v5 = (CSharedLock *)HeapAlloc(g_hHeap, 0, 0x48u);
          if ( v5 )
          {
            gpSystemSurrogateAppIDTableLock = CSharedLock::CSharedLock(v5, &v23);
            if ( gpSystemSurrogateAppIDTableLock )
            {
              v6 = (CSharedLock *)HeapAlloc(g_hHeap, 0, 0x48u);
              if ( v6 )
              {
                gpProcessListLock = (LPCRITICAL_SECTION)CSharedLock::CSharedLock(v6, &v23);
                if ( gpProcessListLock )
                {
                  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl) )
                  {
                    v7 = HeapAlloc(g_hHeap, 0, 0x28u);
                    if ( v7 )
                    {
                      gpClassTable = (CClassicComServerTable *)CClassicComServerTable::CClassicComServerTable(
                                                                 v7,
                                                                 &v23,
                                                                 0);
                      if ( gpClassTable )
                      {
                        v8 = HeapAlloc(g_hHeap, 0, 0x28u);
                        if ( v8 )
                        {
                          v9 = (CClassicComServerTable *)CClassicComServerTable::CClassicComServerTable(v8, &v23, 1);
                          gpSystemSurrogateAppIDTable = v9;
                          goto LABEL_37;
                        }
                        gpSystemSurrogateAppIDTable = 0;
                      }
                    }
                    else
                    {
                      gpClassTable = 0;
                    }
                  }
                  else
                  {
                    v10 = HeapAlloc(g_hHeap, 0, 0x28u);
                    if ( v10 )
                    {
                      gpClassTableOld = (CClassicComServerTableOld *)CClassicComServerTable::CClassicComServerTable(
                                                                       v10,
                                                                       &v23,
                                                                       0);
                      if ( gpClassTableOld )
                      {
                        v11 = HeapAlloc(g_hHeap, 0, 0x28u);
                        if ( v11 )
                        {
                          v9 = (CClassicComServerTable *)CClassicComServerTable::CClassicComServerTable(v11, &v23, 1);
                          gpProcessTableOld = v9;
LABEL_37:
                          if ( v9 )
                          {
                            v12 = (ObjexHashTable::CHashTable *)HeapAlloc(g_hHeap, 0, 0x20u);
                            v13 = v12;
                            if ( v12 )
                            {
                              ObjexHashTable::CHashTable::CHashTable(v12, &v23, 0x20u);
                              *((_QWORD *)v13 + 3) = gpClassLock;
                              gpActivatableClassTable = v13;
                              v14 = (struct CSurrogateList *)HeapAlloc(g_hHeap, 0, 0x10u);
                              if ( v14 )
                              {
                                v15 = g_hHeap;
                                *(_QWORD *)v14 = 0;
                                *((_QWORD *)v14 + 1) = 0;
                                gpCustomSurrogateList = v14;
                                v16 = (CSharedLock *)HeapAlloc(v15, 0, 0x48u);
                                if ( v16 )
                                {
                                  gpRemoteMachineLock = (LPCRITICAL_SECTION)CSharedLock::CSharedLock(v16, &v23);
                                  if ( gpRemoteMachineLock )
                                  {
                                    v17 = HeapAlloc(g_hHeap, 0, 0x18u);
                                    if ( v17 )
                                    {
                                      v17[5] = gdwRemoteBindingHandleCacheMaxSize;
                                      v18 = g_hHeap;
                                      *(_QWORD *)v17 = 0;
                                      *((_QWORD *)v17 + 1) = 0;
                                      v17[4] = 0;
                                      gpRemoteMachineList = (struct CRemoteMachineList *)v17;
                                      v19 = (CNamedObjectTable *)HeapAlloc(v18, 0, 0x10u);
                                      if ( v19 )
                                      {
                                        gpNamedObjectTable = CNamedObjectTable::CNamedObjectTable(v19, &v23);
                                        if ( gpNamedObjectTable && !v23 )
                                        {
                                          v20 = (char *)HeapAlloc(g_hHeap, 0, 0x40u);
                                          v21 = (struct CActivationStateList *)v20;
                                          if ( v20 )
                                          {
                                            *(_QWORD *)v20 = 0;
                                            *((_DWORD *)v20 + 14) = 0;
                                            *((_QWORD *)v20 + 1) = 0;
                                            v22 = CMutexSem2::FInit((CMutexSem2 *)(v20 + 16));
                                            gActivationStateList = v21;
                                            if ( (v22 == 0 ? 0xE : 0) == 0 )
                                              return 0;
                                          }
                                          else
                                          {
                                            gActivationStateList = 0;
                                          }
                                        }
                                      }
                                      else
                                      {
                                        gpNamedObjectTable = 0;
                                      }
                                    }
                                    else
                                    {
                                      gpRemoteMachineList = 0;
                                    }
                                  }
                                }
                                else
                                {
                                  gpRemoteMachineLock = 0;
                                }
                              }
                              else
                              {
                                gpCustomSurrogateList = 0;
                              }
                            }
                            else
                            {
                              gpActivatableClassTable = 0;
                            }
                          }
                          return 8;
                        }
                        gpProcessTableOld = 0;
                      }
                    }
                    else
                    {
                      gpClassTableOld = 0;
                    }
                  }
                }
              }
              else
              {
                gpProcessListLock = 0;
              }
            }
          }
          else
          {
            gpSystemSurrogateAppIDTableLock = 0;
          }
        }
      }
      else
      {
        gpClassLock = 0;
      }
    }
    return 8;
  }
  return result;
}

```

## disassembly

```asm
0x1800ed100  push    rbp
0x1800ed102  push    rbx
0x1800ed103  push    rdi
0x1800ed104  push    r14
0x1800ed106  lea     rbp, [rsp-3Fh]
0x1800ed10b  sub     rsp, 88h
0x1800ed112  mov     rax, cs:__security_cookie
0x1800ed119  xor     rax, rsp
0x1800ed11c  mov     [rbp+57h+var_30], rax
0x1800ed120  xor     edi, edi
0x1800ed122  mov     word ptr [rbp+57h+IdentifierAuthority.Value+4], 500h
0x1800ed128  xor     edx, edx; lpDatabaseName
0x1800ed12a  mov     dword ptr [rbp+57h+IdentifierAuthority.Value], edi
0x1800ed12d  xor     ecx, ecx; lpMachineName
0x1800ed12f  mov     cs:?gpClientLock@@3U_RTL_SRWLOCK@@A.Ptr, rdi; _RTL_SRWLOCK gpClientLock ...
0x1800ed136  mov     cs:?gpServerLock@@3U_RTL_SRWLOCK@@A.Ptr, rdi; _RTL_SRWLOCK gpServerLock ...
0x1800ed13d  lea     r8d, [rdi+1]; dwDesiredAccess
0x1800ed141  call    cs:__imp_OpenSCManagerW
0x1800ed147  mov     cs:?g_hServiceController@@3PEAUSC_HANDLE__@@EA, rax; SC_HANDLE__ * g_hServiceController
0x1800ed14e  test    rax, rax
0x1800ed151  jnz     short loc_1800ED1A9
0x1800ed153  call    cs:__imp_GetLastError
0x1800ed159  mov     ecx, cs:dword_18014E4B8
0x1800ed15f  mov     ebx, eax
0x1800ed161  test    ecx, ecx
0x1800ed163  jnz     short loc_1800ED176
0x1800ed165  cmp     cs:?gfEnableTracing@@3HA, edi; int gfEnableTracing
0x1800ed16b  jz      short loc_1800ED1A2
0x1800ed16d  call    IsWppLevelEnabled
0x1800ed172  test    al, al
0x1800ed174  jz      short loc_1800ED1A2
0x1800ed176  lea     rax, aWinerror; "%!WINERROR!"
0x1800ed17d  mov     r8d, 1DAh
0x1800ed183  mov     [rsp+0A0h+SubAuthority3], ebx
0x1800ed187  lea     rdx, aInitializescmb; "InitializeSCMBeforeListen"
0x1800ed18e  xor     r9d, r9d
0x1800ed191  mov     qword ptr [rsp+0A0h+SubAuthority2], rax
0x1800ed196  lea     rcx, aOnecoreComComb_99; "onecore\\com\\combase\\rpcss\\olescm\\s"...
0x1800ed19d  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x1800ed1a2  mov     eax, ebx
0x1800ed1a4  jmp     loc_1800ED631
0x1800ed1a9  lea     rax, ?psidStateServiceSid@@3PEAXEA; void * psidStateServiceSid
0x1800ed1b0  xor     r9d, r9d; SubAuthority1
0x1800ed1b3  mov     [rsp+0A0h+Sid], rax; Sid
0x1800ed1b8  lea     rcx, [rbp+57h+IdentifierAuthority]; IdentifierAuthority
0x1800ed1bc  mov     [rsp+0A0h+SubAuthority7], edi; SubAuthority7
0x1800ed1c0  mov     dl, 1; SubAuthorityCount
0x1800ed1c2  mov     [rsp+0A0h+SubAuthority6], edi; SubAuthority6
0x1800ed1c6  mov     [rsp+0A0h+SubAuthority5], edi; SubAuthority5
0x1800ed1ca  lea     r8d, [r9+14h]; SubAuthority0
0x1800ed1ce  mov     [rsp+0A0h+SubAuthority4], edi; SubAuthority4
0x1800ed1d2  mov     [rsp+0A0h+SubAuthority3], edi; SubAuthority3
0x1800ed1d6  mov     [rsp+0A0h+SubAuthority2], edi; SubAuthority2
0x1800ed1da  call    cs:__imp_RtlAllocateAndInitializeSid
0x1800ed1e0  mov     ebx, eax
0x1800ed1e2  test    eax, eax
0x1800ed1e4  jns     short loc_1800ED213
0x1800ed1e6  mov     ecx, cs:dword_18014E4B8
0x1800ed1ec  test    ecx, ecx
0x1800ed1ee  jnz     short loc_1800ED201
0x1800ed1f0  cmp     cs:?gfEnableTracing@@3HA, edi; int gfEnableTracing
0x1800ed1f6  jz      short loc_1800ED1A2
0x1800ed1f8  call    IsWppLevelEnabled
0x1800ed1fd  test    al, al
0x1800ed1ff  jz      short loc_1800ED1A2
0x1800ed201  lea     rax, aStatus; "%!STATUS!"
0x1800ed208  mov     r8d, 1EEh
0x1800ed20e  jmp     loc_1800ED183
0x1800ed213  lea     rax, ?psidLaunchServiceSid@@3PEAXEA; void * psidLaunchServiceSid
0x1800ed21a  xor     r9d, r9d; SubAuthority1
0x1800ed21d  mov     [rsp+0A0h+Sid], rax; Sid
0x1800ed222  lea     rcx, [rbp+57h+IdentifierAuthority]; IdentifierAuthority
0x1800ed226  mov     [rsp+0A0h+SubAuthority7], edi; SubAuthority7
0x1800ed22a  mov     dl, 1; SubAuthorityCount
0x1800ed22c  mov     [rsp+0A0h+SubAuthority6], edi; SubAuthority6
0x1800ed230  mov     [rsp+0A0h+SubAuthority5], edi; SubAuthority5
0x1800ed234  lea     r8d, [r9+12h]; SubAuthority0
0x1800ed238  mov     [rsp+0A0h+SubAuthority4], edi; SubAuthority4
0x1800ed23c  mov     [rsp+0A0h+SubAuthority3], edi; SubAuthority3
0x1800ed240  mov     [rsp+0A0h+SubAuthority2], edi; SubAuthority2
0x1800ed244  call    cs:__imp_RtlAllocateAndInitializeSid
0x1800ed24a  mov     ebx, eax
0x1800ed24c  test    eax, eax
0x1800ed24e  jns     short loc_1800ED285
0x1800ed250  mov     ecx, cs:dword_18014E4B8
0x1800ed256  test    ecx, ecx
0x1800ed258  jnz     short loc_1800ED273
0x1800ed25a  cmp     cs:?gfEnableTracing@@3HA, edi; int gfEnableTracing
0x1800ed260  jz      loc_1800ED1A2
0x1800ed266  call    IsWppLevelEnabled
0x1800ed26b  test    al, al
0x1800ed26d  jz      loc_1800ED1A2
0x1800ed273  lea     rax, aStatus; "%!STATUS!"
0x1800ed27a  mov     r8d, 1FFh
0x1800ed280  jmp     loc_1800ED183
0x1800ed285  call    ?InitializeSystemSecurityDescriptors@@YAKXZ; InitializeSystemSecurityDescriptors(void)
0x1800ed28a  mov     [rbp+57h+var_40], eax
0x1800ed28d  test    eax, eax
0x1800ed28f  jnz     loc_1800ED631
0x1800ed295  call    ?ReadRemoteActivationKeys@@YAXXZ; ReadRemoteActivationKeys(void)
0x1800ed29a  call    ?ReadRemoteBindingHandleCacheKeys@@YAXXZ; ReadRemoteBindingHandleCacheKeys(void)
0x1800ed29f  call    ?ReadSAFERKeys@@YAXXZ; ReadSAFERKeys(void)
0x1800ed2a4  call    ?ReadDynamicIPChangesKeys@@YAXXZ; ReadDynamicIPChangesKeys(void)
0x1800ed2a9  call    ?ReadEELoggingKeys@@YAXXZ; ReadEELoggingKeys(void)
0x1800ed2ae  lea     rcx, qword_18014E9F8; this
0x1800ed2b5  call    ?FInit@CMutexSem2@@QEAAHXZ; CMutexSem2::FInit(void)
0x1800ed2ba  test    eax, eax
0x1800ed2bc  jz      loc_1800ED62C
0x1800ed2c2  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800ed2c9  mov     r14d, 48h ; 'H'
0x1800ed2cf  mov     r8d, r14d; dwBytes
0x1800ed2d2  xor     edx, edx; dwFlags
0x1800ed2d4  call    cs:__imp_HeapAlloc
0x1800ed2da  test    rax, rax
0x1800ed2dd  jz      loc_1800ED625
0x1800ed2e3  lea     rdx, [rbp+57h+var_40]; int *
0x1800ed2e7  mov     rcx, rax; this
0x1800ed2ea  call    ??0CSharedLock@@QEAA@AEAJ@Z; CSharedLock::CSharedLock(long &)
0x1800ed2ef  mov     cs:?gpClassLock@@3PEAVCSharedLock@@EA, rax; CSharedLock * gpClassLock
0x1800ed2f6  test    rax, rax
0x1800ed2f9  jz      loc_1800ED62C
0x1800ed2ff  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800ed306  mov     r8d, r14d; dwBytes
0x1800ed309  xor     edx, edx; dwFlags
0x1800ed30b  call    cs:__imp_HeapAlloc
0x1800ed311  test    rax, rax
0x1800ed314  jz      loc_1800ED61C
0x1800ed31a  lea     rdx, [rbp+57h+var_40]; int *
0x1800ed31e  mov     rcx, rax; this
0x1800ed321  call    ??0CSharedLock@@QEAA@AEAJ@Z; CSharedLock::CSharedLock(long &)
0x1800ed326  mov     cs:?gpSystemSurrogateAppIDTableLock@@3PEAVCSharedLock@@EA, rax; CSharedLock * gpSystemSurrogateAppIDTableLock
0x1800ed32d  test    rax, rax
0x1800ed330  jz      loc_1800ED62C
0x1800ed336  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800ed33d  mov     r8d, r14d; dwBytes
0x1800ed340  xor     edx, edx; dwFlags
0x1800ed342  call    cs:__imp_HeapAlloc
0x1800ed348  test    rax, rax
0x1800ed34b  jz      loc_1800ED613
0x1800ed351  lea     rdx, [rbp+57h+var_40]; int *
0x1800ed355  mov     rcx, rax; this
0x1800ed358  call    ??0CSharedLock@@QEAA@AEAJ@Z; CSharedLock::CSharedLock(long &)
0x1800ed35d  mov     cs:?gpProcessListLock@@3PEAVCSharedLock@@EA, rax; CSharedLock * gpProcessListLock
0x1800ed364  test    rax, rax
0x1800ed367  jz      loc_1800ED62C
0x1800ed36d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x1800ed374  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x1800ed379  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800ed380  lea     ebx, [r14-20h]
0x1800ed384  xor     edx, edx; dwFlags
0x1800ed386  mov     r8d, ebx; dwBytes
0x1800ed389  test    al, al
0x1800ed38b  jz      short loc_1800ED3FF
0x1800ed38d  call    cs:__imp_HeapAlloc
0x1800ed393  test    rax, rax
0x1800ed396  jz      short loc_1800ED3F3
0x1800ed398  xor     r8d, r8d
0x1800ed39b  lea     rdx, [rbp+57h+var_40]
0x1800ed39f  mov     rcx, rax
0x1800ed3a2  call    ??0CClassicComServerTable@@QEAA@AEAJW4EnumEntryType@@@Z; CClassicComServerTable::CClassicComServerTable(long &,EnumEntryType)
0x1800ed3a7  mov     cs:?gpClassTable@@3PEAVCClassicComServerTable@@EA, rax; CClassicComServerTable * gpClassTable
0x1800ed3ae  test    rax, rax
0x1800ed3b1  jz      loc_1800ED62C
0x1800ed3b7  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800ed3be  mov     r8d, ebx; dwBytes
0x1800ed3c1  xor     edx, edx; dwFlags
0x1800ed3c3  call    cs:__imp_HeapAlloc
0x1800ed3c9  test    rax, rax
0x1800ed3cc  jz      short loc_1800ED3E7
0x1800ed3ce  lea     r8d, [r14-47h]
0x1800ed3d2  mov     rcx, rax
0x1800ed3d5  lea     rdx, [rbp+57h+var_40]
0x1800ed3d9  call    ??0CClassicComServerTable@@QEAA@AEAJW4EnumEntryType@@@Z; CClassicComServerTable::CClassicComServerTable(long &,EnumEntryType)
0x1800ed3de  mov     cs:?gpSystemSurrogateAppIDTable@@3PEAVCClassicComServerTable@@EA, rax; CClassicComServerTable * gpSystemSurrogateAppIDTable
0x1800ed3e5  jmp     short loc_1800ED461
0x1800ed3e7  mov     cs:?gpSystemSurrogateAppIDTable@@3PEAVCClassicComServerTable@@EA, rdi; CClassicComServerTable * gpSystemSurrogateAppIDTable
0x1800ed3ee  jmp     loc_1800ED62C
0x1800ed3f3  mov     cs:?gpClassTable@@3PEAVCClassicComServerTable@@EA, rdi; CClassicComServerTable * gpClassTable
0x1800ed3fa  jmp     loc_1800ED62C
0x1800ed3ff  call    cs:__imp_HeapAlloc
0x1800ed405  test    rax, rax
0x1800ed408  jz      loc_1800ED60A
0x1800ed40e  xor     r8d, r8d
0x1800ed411  lea     rdx, [rbp+57h+var_40]
0x1800ed415  mov     rcx, rax
0x1800ed418  call    ??0CClassicComServerTable@@QEAA@AEAJW4EnumEntryType@@@Z; CClassicComServerTable::CClassicComServerTable(long &,EnumEntryType)
0x1800ed41d  mov     cs:?gpClassTableOld@@3PEAVCClassicComServerTableOld@@EA, rax; CClassicComServerTableOld * gpClassTableOld
0x1800ed424  test    rax, rax
0x1800ed427  jz      loc_1800ED62C
0x1800ed42d  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800ed434  mov     r8, rbx; dwBytes
0x1800ed437  xor     edx, edx; dwFlags
0x1800ed439  call    cs:__imp_HeapAlloc
0x1800ed43f  test    rax, rax
0x1800ed442  jz      loc_1800ED601
0x1800ed448  mov     r8d, 1
0x1800ed44e  lea     rdx, [rbp+57h+var_40]
0x1800ed452  mov     rcx, rax
0x1800ed455  call    ??0CClassicComServerTable@@QEAA@AEAJW4EnumEntryType@@@Z; CClassicComServerTable::CClassicComServerTable(long &,EnumEntryType)
0x1800ed45a  mov     cs:?gpProcessTableOld@@3PEAVCClassicComServerTableOld@@EA, rax; CClassicComServerTableOld * gpProcessTableOld
0x1800ed461  test    rax, rax
0x1800ed464  jz      loc_1800ED62C
0x1800ed46a  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800ed471  xor     edx, edx; dwFlags
0x1800ed473  lea     r8d, [rdx+20h]; dwBytes
0x1800ed477  call    cs:__imp_HeapAlloc
0x1800ed47d  mov     rbx, rax
0x1800ed480  test    rax, rax
0x1800ed483  jz      loc_1800ED5F8
0x1800ed489  mov     r8d, 20h ; ' '; unsigned int
0x1800ed48f  lea     rdx, [rbp+57h+var_40]; int *
0x1800ed493  mov     rcx, rax; this
0x1800ed496  call    ??0CHashTable@ObjexHashTable@@QEAA@AEAJI@Z; ObjexHashTable::CHashTable::CHashTable(long &,uint)
0x1800ed49b  mov     rcx, cs:?gpClassLock@@3PEAVCSharedLock@@EA; CSharedLock * gpClassLock
0x1800ed4a2  xor     edx, edx; dwFlags
0x1800ed4a4  mov     [rbx+18h], rcx
0x1800ed4a8  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800ed4af  mov     cs:?gpActivatableClassTable@@3PEAVCWinRTServerTable@@EA, rbx; CWinRTServerTable * gpActivatableClassTable
0x1800ed4b6  mov     ebx, 10h
0x1800ed4bb  mov     r8d, ebx; dwBytes
0x1800ed4be  call    cs:__imp_HeapAlloc
0x1800ed4c4  test    rax, rax
0x1800ed4c7  jz      loc_1800ED5EF
0x1800ed4cd  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800ed4d4  mov     r8, r14; dwBytes
0x1800ed4d7  xor     edx, edx; dwFlags
0x1800ed4d9  mov     [rax], rdi
0x1800ed4dc  mov     [rax+8], rdi
0x1800ed4e0  mov     cs:?gpCustomSurrogateList@@3PEAVCSurrogateList@@EA, rax; CSurrogateList * gpCustomSurrogateList
0x1800ed4e7  call    cs:__imp_HeapAlloc
0x1800ed4ed  test    rax, rax
0x1800ed4f0  jz      loc_1800ED5E6
0x1800ed4f6  lea     rdx, [rbp+57h+var_40]; int *
0x1800ed4fa  mov     rcx, rax; this
0x1800ed4fd  call    ??0CSharedLock@@QEAA@AEAJ@Z; CSharedLock::CSharedLock(long &)
0x1800ed502  mov     cs:?gpRemoteMachineLock@@3PEAVCSharedLock@@EA, rax; CSharedLock * gpRemoteMachineLock
0x1800ed509  test    rax, rax
0x1800ed50c  jz      loc_1800ED62C
0x1800ed512  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800ed519  lea     r8d, [rbx+8]; dwBytes
0x1800ed51d  xor     edx, edx; dwFlags
0x1800ed51f  call    cs:__imp_HeapAlloc
0x1800ed525  test    rax, rax
0x1800ed528  jz      loc_1800ED5DD
0x1800ed52e  mov     ecx, cs:?gdwRemoteBindingHandleCacheMaxSize@@3KA; ulong gdwRemoteBindingHandleCacheMaxSize
0x1800ed534  mov     r8d, ebx; dwBytes
0x1800ed537  mov     [rax+14h], ecx
0x1800ed53a  xor     edx, edx; dwFlags
0x1800ed53c  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800ed543  mov     [rax], rdi
0x1800ed546  mov     [rax+8], rdi
0x1800ed54a  mov     [rax+10h], edi
0x1800ed54d  mov     cs:?gpRemoteMachineList@@3PEAVCRemoteMachineList@@EA, rax; CRemoteMachineList * gpRemoteMachineList
0x1800ed554  call    cs:__imp_HeapAlloc
0x1800ed55a  test    rax, rax
0x1800ed55d  jz      short loc_1800ED5D4
0x1800ed55f  lea     rdx, [rbp+57h+var_40]; int *
0x1800ed563  mov     rcx, rax; this
0x1800ed566  call    ??0CNamedObjectTable@@QEAA@AEAJ@Z; CNamedObjectTable::CNamedObjectTable(long &)
0x1800ed56b  mov     cs:?gpNamedObjectTable@@3PEAVCNamedObjectTable@@EA, rax; CNamedObjectTable * gpNamedObjectTable
0x1800ed572  test    rax, rax
0x1800ed575  jz      loc_1800ED62C
0x1800ed57b  cmp     [rbp+57h+var_40], edi
0x1800ed57e  jnz     loc_1800ED62C
0x1800ed584  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800ed58b  lea     r8d, [rbx+30h]; dwBytes
0x1800ed58f  xor     edx, edx; dwFlags
0x1800ed591  call    cs:__imp_HeapAlloc
0x1800ed597  mov     rbx, rax
0x1800ed59a  test    rax, rax
0x1800ed59d  jz      short loc_1800ED5CB
0x1800ed59f  lea     rcx, [rax+10h]; this
0x1800ed5a3  mov     [rax], rdi
0x1800ed5a6  mov     [rcx+28h], edi
0x1800ed5a9  mov     [rax+8], rdi
0x1800ed5ad  call    ?FInit@CMutexSem2@@QEAAHXZ; CMutexSem2::FInit(void)
0x1800ed5b2  neg     eax
0x1800ed5b4  mov     cs:?gActivationStateList@@3PEAVCActivationStateList@@EA, rbx; CActivationStateList * gActivationStateList
0x1800ed5bb  sbb     ecx, ecx
0x1800ed5bd  not     ecx
0x1800ed5bf  test    ecx, 0Eh
0x1800ed5c5  jnz     short loc_1800ED62C
0x1800ed5c7  xor     eax, eax
0x1800ed5c9  jmp     short loc_1800ED631
0x1800ed5cb  mov     cs:?gActivationStateList@@3PEAVCActivationStateList@@EA, rdi; CActivationStateList * gActivationStateList
0x1800ed5d2  jmp     short loc_1800ED62C
0x1800ed5d4  mov     cs:?gpNamedObjectTable@@3PEAVCNamedObjectTable@@EA, rdi; CNamedObjectTable * gpNamedObjectTable
0x1800ed5db  jmp     short loc_1800ED62C
0x1800ed5dd  mov     cs:?gpRemoteMachineList@@3PEAVCRemoteMachineList@@EA, rdi; CRemoteMachineList * gpRemoteMachineList
0x1800ed5e4  jmp     short loc_1800ED62C
0x1800ed5e6  mov     cs:?gpRemoteMachineLock@@3PEAVCSharedLock@@EA, rdi; CSharedLock * gpRemoteMachineLock
0x1800ed5ed  jmp     short loc_1800ED62C
0x1800ed5ef  mov     cs:?gpCustomSurrogateList@@3PEAVCSurrogateList@@EA, rdi; CSurrogateList * gpCustomSurrogateList
0x1800ed5f6  jmp     short loc_1800ED62C
0x1800ed5f8  mov     cs:?gpActivatableClassTable@@3PEAVCWinRTServerTable@@EA, rdi; CWinRTServerTable * gpActivatableClassTable
0x1800ed5ff  jmp     short loc_1800ED62C
0x1800ed601  mov     cs:?gpProcessTableOld@@3PEAVCClassicComServerTableOld@@EA, rdi; CClassicComServerTableOld * gpProcessTableOld
0x1800ed608  jmp     short loc_1800ED62C
0x1800ed60a  mov     cs:?gpClassTableOld@@3PEAVCClassicComServerTableOld@@EA, rdi; CClassicComServerTableOld * gpClassTableOld
0x1800ed611  jmp     short loc_1800ED62C
  ... truncated ...
```
