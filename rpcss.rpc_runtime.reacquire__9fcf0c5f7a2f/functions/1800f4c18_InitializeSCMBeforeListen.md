# InitializeSCMBeforeListen

- ea: `0x1800f4c18`
- end: `0x1800f51d0`
- name: `InitializeSCMBeforeListen`
- size: `1464`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800bca54`

## callees

- `0x1800065a4`
- `0x180034260`
- `0x18005e690`
- `0x18008172c`
- `0x1800881a4`
- `0x1800b7ac0`
- `0x1800c58cc`
- `0x1800f0ed4`
- `0x1800f1008`
- `0x1800f1238`
- `0x1800f142c`
- `0x1800f1564`
- `0x1800f41ec`
- `0x1800f4c18`
- `0x180110ed8`
- `0x18011252c`

## import_xrefs

- `ntdll!RtlAllocateAndInitializeSid` at `0x1800f4cfe`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1800f4d6e`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1800f4cfe`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1800f4d6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f4c71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f4c71`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800f4e04`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800f4e41`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800f4e7e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800f4ed3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800f4f0f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800f4f54`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800f4f94`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800f4fd8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800f5025`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800f5054`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800f5092`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800f50cd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800f5110`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800f4e04`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800f4e41`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800f4e7e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800f4ed3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800f4f0f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800f4f54`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800f4f94`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800f4fd8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800f5025`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800f5054`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800f5092`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800f50cd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800f5110`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800f4c59`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800f4c59`

## string_xrefs

- `0x1800f4cba`: `onecore\com\combase\rpcss\olescm\scmsvc.cxx`

## pseudocode

```c
__int64 InitializeSCMBeforeListen()
{
  int LastError; // ebx
  const wchar_t *v1; // rax
  int v2; // r8d
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
  __int64 SubAuthority3; // [rsp+28h] [rbp-21h]
  int v24; // [rsp+60h] [rbp+17h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+64h] [rbp+1Bh] BYREF

  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  gpClientLock.Ptr = 0;
  gpServerLock.Ptr = 0;
  g_hServiceController = OpenSCManagerW(0, 0, 1u);
  if ( !g_hServiceController )
  {
    LastError = GetLastError();
    if ( !dword_1801574B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled((unsigned int)dword_1801574B8)) )
      return (unsigned int)LastError;
    v1 = (const wchar_t *)L"%!WINERROR!";
    v2 = 474;
LABEL_6:
    LODWORD(SubAuthority3) = LastError;
    ComTraceMessageT<long>(
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\scmsvc.cxx",
      (unsigned int)"InitializeSCMBeforeListen",
      v2,
      0,
      (__int64)v1,
      SubAuthority3);
    return (unsigned int)LastError;
  }
  LastError = RtlAllocateAndInitializeSid(&IdentifierAuthority, 1u, 0x14u, 0, 0, 0, 0, 0, 0, 0, &psidStateServiceSid);
  if ( LastError < 0 )
  {
    if ( !dword_1801574B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled((unsigned int)dword_1801574B8)) )
      return (unsigned int)LastError;
    v1 = L"%!STATUS!";
    v2 = 494;
    goto LABEL_6;
  }
  LastError = RtlAllocateAndInitializeSid(&IdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &psidLaunchServiceSid);
  if ( LastError < 0 )
  {
    if ( !dword_1801574B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled((unsigned int)dword_1801574B8)) )
      return (unsigned int)LastError;
    v1 = L"%!STATUS!";
    v2 = 511;
    goto LABEL_6;
  }
  result = InitializeSystemSecurityDescriptors();
  v24 = result;
  if ( !(_DWORD)result )
  {
    ReadRemoteActivationKeys();
    ReadRemoteBindingHandleCacheKeys();
    ReadSAFERKeys();
    ReadDynamicIPChangesKeys();
    ReadEELoggingKeys();
    if ( (unsigned int)CMutexSem2::FInit((CMutexSem2 *)qword_180157AF8) )
    {
      v4 = (CSharedLock *)HeapAlloc(g_hHeap, 0, 0x48u);
      if ( v4 )
      {
        gpClassLock = (LPCRITICAL_SECTION)CSharedLock::CSharedLock(v4, &v24);
        if ( gpClassLock )
        {
          v5 = (CSharedLock *)HeapAlloc(g_hHeap, 0, 0x48u);
          if ( v5 )
          {
            gpSystemSurrogateAppIDTableLock = CSharedLock::CSharedLock(v5, &v24);
            if ( gpSystemSurrogateAppIDTableLock )
            {
              v6 = (CSharedLock *)HeapAlloc(g_hHeap, 0, 0x48u);
              if ( v6 )
              {
                gpProcessListLock = (LPCRITICAL_SECTION)CSharedLock::CSharedLock(v6, &v24);
                if ( gpProcessListLock )
                {
                  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl) )
                  {
                    v7 = HeapAlloc(g_hHeap, 0, 0x28u);
                    if ( v7 )
                    {
                      gpClassTable = (CClassicComServerTable *)CClassicComServerTable::CClassicComServerTable(
                                                                 v7,
                                                                 &v24,
                                                                 0);
                      if ( gpClassTable )
                      {
                        v8 = HeapAlloc(g_hHeap, 0, 0x28u);
                        if ( v8 )
                        {
                          v9 = (CClassicComServerTable *)CClassicComServerTable::CClassicComServerTable(v8, &v24, 1);
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
                                                                       &v24,
                                                                       0);
                      if ( gpClassTableOld )
                      {
                        v11 = HeapAlloc(g_hHeap, 0, 0x28u);
                        if ( v11 )
                        {
                          v9 = (CClassicComServerTable *)CClassicComServerTable::CClassicComServerTable(v11, &v24, 1);
                          gpProcessTableOld = v9;
LABEL_37:
                          if ( v9 )
                          {
                            v12 = (ObjexHashTable::CHashTable *)HeapAlloc(g_hHeap, 0, 0x20u);
                            v13 = v12;
                            if ( v12 )
                            {
                              ObjexHashTable::CHashTable::CHashTable(v12, &v24, 0x20u);
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
                                  gpRemoteMachineLock = (LPCRITICAL_SECTION)CSharedLock::CSharedLock(v16, &v24);
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
                                        gpNamedObjectTable = CNamedObjectTable::CNamedObjectTable(v19, &v24);
                                        if ( gpNamedObjectTable && !v24 )
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
0x1800f4c18  push    rbp
0x1800f4c1a  push    rbx
0x1800f4c1b  push    rdi
0x1800f4c1c  push    r14
0x1800f4c1e  lea     rbp, [rsp-3Fh]
0x1800f4c23  sub     rsp, 88h
0x1800f4c2a  mov     rax, cs:__security_cookie
0x1800f4c31  xor     rax, rsp
0x1800f4c34  mov     [rbp+57h+var_30], rax
0x1800f4c38  xor     edi, edi
0x1800f4c3a  mov     word ptr [rbp+57h+IdentifierAuthority.Value+4], 500h
0x1800f4c40  xor     edx, edx; lpDatabaseName
0x1800f4c42  mov     dword ptr [rbp+57h+IdentifierAuthority.Value], edi
0x1800f4c45  xor     ecx, ecx; lpMachineName
0x1800f4c47  mov     cs:?gpClientLock@@3U_RTL_SRWLOCK@@A.Ptr, rdi; _RTL_SRWLOCK gpClientLock ...
0x1800f4c4e  mov     cs:?gpServerLock@@3U_RTL_SRWLOCK@@A.Ptr, rdi; _RTL_SRWLOCK gpServerLock ...
0x1800f4c55  lea     r8d, [rdi+1]; dwDesiredAccess
0x1800f4c59  call    cs:__imp_OpenSCManagerW
0x1800f4c60  nop     dword ptr [rax+rax+00h]
0x1800f4c65  mov     cs:?g_hServiceController@@3PEAUSC_HANDLE__@@EA, rax; SC_HANDLE__ * g_hServiceController
0x1800f4c6c  test    rax, rax
0x1800f4c6f  jnz     short loc_1800F4CCD
0x1800f4c71  call    cs:__imp_GetLastError
0x1800f4c78  nop     dword ptr [rax+rax+00h]
0x1800f4c7d  mov     ecx, cs:dword_1801574B8
0x1800f4c83  mov     ebx, eax
0x1800f4c85  test    ecx, ecx
0x1800f4c87  jnz     short loc_1800F4C9A
0x1800f4c89  cmp     cs:?gfEnableTracing@@3HA, edi; int gfEnableTracing
0x1800f4c8f  jz      short loc_1800F4CC6
0x1800f4c91  call    IsWppLevelEnabled
0x1800f4c96  test    al, al
0x1800f4c98  jz      short loc_1800F4CC6
0x1800f4c9a  lea     rax, aWinerror; "%!WINERROR!"
0x1800f4ca1  mov     r8d, 1DAh
0x1800f4ca7  mov     dword ptr [rsp+0A0h+SubAuthority3], ebx
0x1800f4cab  lea     rdx, aInitializescmb; "InitializeSCMBeforeListen"
0x1800f4cb2  xor     r9d, r9d
0x1800f4cb5  mov     qword ptr [rsp+0A0h+SubAuthority2], rax
0x1800f4cba  lea     rcx, aOnecoreComComb_99; "onecore\\com\\combase\\rpcss\\olescm\\s"...
0x1800f4cc1  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x1800f4cc6  mov     eax, ebx
0x1800f4cc8  jmp     loc_1800F51B6
0x1800f4ccd  lea     rax, ?psidStateServiceSid@@3PEAXEA; void * psidStateServiceSid
0x1800f4cd4  xor     r9d, r9d; SubAuthority1
0x1800f4cd7  mov     [rsp+0A0h+Sid], rax; Sid
0x1800f4cdc  lea     rcx, [rbp+57h+IdentifierAuthority]; IdentifierAuthority
0x1800f4ce0  mov     [rsp+0A0h+SubAuthority7], edi; SubAuthority7
0x1800f4ce4  mov     dl, 1; SubAuthorityCount
0x1800f4ce6  mov     [rsp+0A0h+SubAuthority6], edi; SubAuthority6
0x1800f4cea  mov     [rsp+0A0h+SubAuthority5], edi; SubAuthority5
0x1800f4cee  lea     r8d, [r9+14h]; SubAuthority0
0x1800f4cf2  mov     [rsp+0A0h+SubAuthority4], edi; SubAuthority4
0x1800f4cf6  mov     dword ptr [rsp+0A0h+SubAuthority3], edi; SubAuthority3
0x1800f4cfa  mov     [rsp+0A0h+SubAuthority2], edi; SubAuthority2
0x1800f4cfe  call    cs:__imp_RtlAllocateAndInitializeSid
0x1800f4d05  nop     dword ptr [rax+rax+00h]
0x1800f4d0a  mov     ebx, eax
0x1800f4d0c  test    eax, eax
0x1800f4d0e  jns     short loc_1800F4D3D
0x1800f4d10  mov     ecx, cs:dword_1801574B8
0x1800f4d16  test    ecx, ecx
0x1800f4d18  jnz     short loc_1800F4D2B
0x1800f4d1a  cmp     cs:?gfEnableTracing@@3HA, edi; int gfEnableTracing
0x1800f4d20  jz      short loc_1800F4CC6
0x1800f4d22  call    IsWppLevelEnabled
0x1800f4d27  test    al, al
0x1800f4d29  jz      short loc_1800F4CC6
0x1800f4d2b  lea     rax, aStatus; "%!STATUS!"
0x1800f4d32  mov     r8d, 1EEh
0x1800f4d38  jmp     loc_1800F4CA7
0x1800f4d3d  lea     rax, ?psidLaunchServiceSid@@3PEAXEA; void * psidLaunchServiceSid
0x1800f4d44  xor     r9d, r9d; SubAuthority1
0x1800f4d47  mov     [rsp+0A0h+Sid], rax; Sid
0x1800f4d4c  lea     rcx, [rbp+57h+IdentifierAuthority]; IdentifierAuthority
0x1800f4d50  mov     [rsp+0A0h+SubAuthority7], edi; SubAuthority7
0x1800f4d54  mov     dl, 1; SubAuthorityCount
0x1800f4d56  mov     [rsp+0A0h+SubAuthority6], edi; SubAuthority6
0x1800f4d5a  mov     [rsp+0A0h+SubAuthority5], edi; SubAuthority5
0x1800f4d5e  lea     r8d, [r9+12h]; SubAuthority0
0x1800f4d62  mov     [rsp+0A0h+SubAuthority4], edi; SubAuthority4
0x1800f4d66  mov     dword ptr [rsp+0A0h+SubAuthority3], edi; SubAuthority3
0x1800f4d6a  mov     [rsp+0A0h+SubAuthority2], edi; SubAuthority2
0x1800f4d6e  call    cs:__imp_RtlAllocateAndInitializeSid
0x1800f4d75  nop     dword ptr [rax+rax+00h]
0x1800f4d7a  mov     ebx, eax
0x1800f4d7c  test    eax, eax
0x1800f4d7e  jns     short loc_1800F4DB5
0x1800f4d80  mov     ecx, cs:dword_1801574B8
0x1800f4d86  test    ecx, ecx
0x1800f4d88  jnz     short loc_1800F4DA3
0x1800f4d8a  cmp     cs:?gfEnableTracing@@3HA, edi; int gfEnableTracing
0x1800f4d90  jz      loc_1800F4CC6
0x1800f4d96  call    IsWppLevelEnabled
0x1800f4d9b  test    al, al
0x1800f4d9d  jz      loc_1800F4CC6
0x1800f4da3  lea     rax, aStatus; "%!STATUS!"
0x1800f4daa  mov     r8d, 1FFh
0x1800f4db0  jmp     loc_1800F4CA7
0x1800f4db5  call    ?InitializeSystemSecurityDescriptors@@YAKXZ; InitializeSystemSecurityDescriptors(void)
0x1800f4dba  mov     [rbp+57h+var_40], eax
0x1800f4dbd  test    eax, eax
0x1800f4dbf  jnz     loc_1800F51B6
0x1800f4dc5  call    ?ReadRemoteActivationKeys@@YAXXZ; ReadRemoteActivationKeys(void)
0x1800f4dca  call    ?ReadRemoteBindingHandleCacheKeys@@YAXXZ; ReadRemoteBindingHandleCacheKeys(void)
0x1800f4dcf  call    ?ReadSAFERKeys@@YAXXZ; ReadSAFERKeys(void)
0x1800f4dd4  call    ?ReadDynamicIPChangesKeys@@YAXXZ; ReadDynamicIPChangesKeys(void)
0x1800f4dd9  call    ?ReadEELoggingKeys@@YAXXZ; ReadEELoggingKeys(void)
0x1800f4dde  lea     rcx, qword_180157AF8; this
0x1800f4de5  call    ?FInit@CMutexSem2@@QEAAHXZ; CMutexSem2::FInit(void)
0x1800f4dea  test    eax, eax
0x1800f4dec  jz      loc_1800F51B1
0x1800f4df2  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800f4df9  mov     r14d, 48h ; 'H'
0x1800f4dff  mov     r8d, r14d; dwBytes
0x1800f4e02  xor     edx, edx; dwFlags
0x1800f4e04  call    cs:__imp_HeapAlloc
0x1800f4e0b  nop     dword ptr [rax+rax+00h]
0x1800f4e10  test    rax, rax
0x1800f4e13  jz      loc_1800F51AA
0x1800f4e19  lea     rdx, [rbp+57h+var_40]; int *
0x1800f4e1d  mov     rcx, rax; this
0x1800f4e20  call    ??0CSharedLock@@QEAA@AEAJ@Z; CSharedLock::CSharedLock(long &)
0x1800f4e25  mov     cs:?gpClassLock@@3PEAVCSharedLock@@EA, rax; CSharedLock * gpClassLock
0x1800f4e2c  test    rax, rax
0x1800f4e2f  jz      loc_1800F51B1
0x1800f4e35  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800f4e3c  mov     r8d, r14d; dwBytes
0x1800f4e3f  xor     edx, edx; dwFlags
0x1800f4e41  call    cs:__imp_HeapAlloc
0x1800f4e48  nop     dword ptr [rax+rax+00h]
0x1800f4e4d  test    rax, rax
0x1800f4e50  jz      loc_1800F51A1
0x1800f4e56  lea     rdx, [rbp+57h+var_40]; int *
0x1800f4e5a  mov     rcx, rax; this
0x1800f4e5d  call    ??0CSharedLock@@QEAA@AEAJ@Z; CSharedLock::CSharedLock(long &)
0x1800f4e62  mov     cs:?gpSystemSurrogateAppIDTableLock@@3PEAVCSharedLock@@EA, rax; CSharedLock * gpSystemSurrogateAppIDTableLock
0x1800f4e69  test    rax, rax
0x1800f4e6c  jz      loc_1800F51B1
0x1800f4e72  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800f4e79  mov     r8d, r14d; dwBytes
0x1800f4e7c  xor     edx, edx; dwFlags
0x1800f4e7e  call    cs:__imp_HeapAlloc
0x1800f4e85  nop     dword ptr [rax+rax+00h]
0x1800f4e8a  test    rax, rax
0x1800f4e8d  jz      loc_1800F5198
0x1800f4e93  lea     rdx, [rbp+57h+var_40]; int *
0x1800f4e97  mov     rcx, rax; this
0x1800f4e9a  call    ??0CSharedLock@@QEAA@AEAJ@Z; CSharedLock::CSharedLock(long &)
0x1800f4e9f  mov     cs:?gpProcessListLock@@3PEAVCSharedLock@@EA, rax; CSharedLock * gpProcessListLock
0x1800f4ea6  test    rax, rax
0x1800f4ea9  jz      loc_1800F51B1
0x1800f4eaf  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x1800f4eb6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x1800f4ebb  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800f4ec2  lea     ebx, [r14-20h]
0x1800f4ec6  xor     edx, edx; dwFlags
0x1800f4ec8  mov     r8d, ebx; dwBytes
0x1800f4ecb  test    al, al
0x1800f4ecd  jz      loc_1800F4F54
0x1800f4ed3  call    cs:__imp_HeapAlloc
0x1800f4eda  nop     dword ptr [rax+rax+00h]
0x1800f4edf  test    rax, rax
0x1800f4ee2  jz      short loc_1800F4F48
0x1800f4ee4  xor     r8d, r8d
0x1800f4ee7  lea     rdx, [rbp+57h+var_40]
0x1800f4eeb  mov     rcx, rax
0x1800f4eee  call    ??0CClassicComServerTable@@QEAA@AEAJW4EnumEntryType@@@Z; CClassicComServerTable::CClassicComServerTable(long &,EnumEntryType)
0x1800f4ef3  mov     cs:?gpClassTable@@3PEAVCClassicComServerTable@@EA, rax; CClassicComServerTable * gpClassTable
0x1800f4efa  test    rax, rax
0x1800f4efd  jz      loc_1800F51B1
0x1800f4f03  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800f4f0a  mov     r8d, ebx; dwBytes
0x1800f4f0d  xor     edx, edx; dwFlags
0x1800f4f0f  call    cs:__imp_HeapAlloc
0x1800f4f16  nop     dword ptr [rax+rax+00h]
0x1800f4f1b  test    rax, rax
0x1800f4f1e  jz      short loc_1800F4F3C
0x1800f4f20  lea     r8d, [r14-47h]
0x1800f4f24  mov     rcx, rax
0x1800f4f27  lea     rdx, [rbp+57h+var_40]
0x1800f4f2b  call    ??0CClassicComServerTable@@QEAA@AEAJW4EnumEntryType@@@Z; CClassicComServerTable::CClassicComServerTable(long &,EnumEntryType)
0x1800f4f30  mov     cs:?gpSystemSurrogateAppIDTable@@3PEAVCClassicComServerTable@@EA, rax; CClassicComServerTable * gpSystemSurrogateAppIDTable
0x1800f4f37  jmp     loc_1800F4FC2
0x1800f4f3c  mov     cs:?gpSystemSurrogateAppIDTable@@3PEAVCClassicComServerTable@@EA, rdi; CClassicComServerTable * gpSystemSurrogateAppIDTable
0x1800f4f43  jmp     loc_1800F51B1
0x1800f4f48  mov     cs:?gpClassTable@@3PEAVCClassicComServerTable@@EA, rdi; CClassicComServerTable * gpClassTable
0x1800f4f4f  jmp     loc_1800F51B1
0x1800f4f54  call    cs:__imp_HeapAlloc
0x1800f4f5b  nop     dword ptr [rax+rax+00h]
0x1800f4f60  test    rax, rax
0x1800f4f63  jz      loc_1800F518F
0x1800f4f69  xor     r8d, r8d
0x1800f4f6c  lea     rdx, [rbp+57h+var_40]
0x1800f4f70  mov     rcx, rax
0x1800f4f73  call    ??0CClassicComServerTable@@QEAA@AEAJW4EnumEntryType@@@Z; CClassicComServerTable::CClassicComServerTable(long &,EnumEntryType)
0x1800f4f78  mov     cs:?gpClassTableOld@@3PEAVCClassicComServerTableOld@@EA, rax; CClassicComServerTableOld * gpClassTableOld
0x1800f4f7f  test    rax, rax
0x1800f4f82  jz      loc_1800F51B1
0x1800f4f88  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800f4f8f  mov     r8, rbx; dwBytes
0x1800f4f92  xor     edx, edx; dwFlags
0x1800f4f94  call    cs:__imp_HeapAlloc
0x1800f4f9b  nop     dword ptr [rax+rax+00h]
0x1800f4fa0  test    rax, rax
0x1800f4fa3  jz      loc_1800F5186
0x1800f4fa9  mov     r8d, 1
0x1800f4faf  lea     rdx, [rbp+57h+var_40]
0x1800f4fb3  mov     rcx, rax
0x1800f4fb6  call    ??0CClassicComServerTable@@QEAA@AEAJW4EnumEntryType@@@Z; CClassicComServerTable::CClassicComServerTable(long &,EnumEntryType)
0x1800f4fbb  mov     cs:?gpProcessTableOld@@3PEAVCClassicComServerTableOld@@EA, rax; CClassicComServerTableOld * gpProcessTableOld
0x1800f4fc2  test    rax, rax
0x1800f4fc5  jz      loc_1800F51B1
0x1800f4fcb  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800f4fd2  xor     edx, edx; dwFlags
0x1800f4fd4  lea     r8d, [rdx+20h]; dwBytes
0x1800f4fd8  call    cs:__imp_HeapAlloc
0x1800f4fdf  nop     dword ptr [rax+rax+00h]
0x1800f4fe4  mov     rbx, rax
0x1800f4fe7  test    rax, rax
0x1800f4fea  jz      loc_1800F517D
0x1800f4ff0  mov     r8d, 20h ; ' '; unsigned int
0x1800f4ff6  lea     rdx, [rbp+57h+var_40]; int *
0x1800f4ffa  mov     rcx, rax; this
0x1800f4ffd  call    ??0CHashTable@ObjexHashTable@@QEAA@AEAJI@Z; ObjexHashTable::CHashTable::CHashTable(long &,uint)
0x1800f5002  mov     rcx, cs:?gpClassLock@@3PEAVCSharedLock@@EA; CSharedLock * gpClassLock
0x1800f5009  xor     edx, edx; dwFlags
0x1800f500b  mov     [rbx+18h], rcx
0x1800f500f  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800f5016  mov     cs:?gpActivatableClassTable@@3PEAVCWinRTServerTable@@EA, rbx; CWinRTServerTable * gpActivatableClassTable
0x1800f501d  mov     ebx, 10h
0x1800f5022  mov     r8d, ebx; dwBytes
0x1800f5025  call    cs:__imp_HeapAlloc
0x1800f502c  nop     dword ptr [rax+rax+00h]
0x1800f5031  test    rax, rax
0x1800f5034  jz      loc_1800F5174
0x1800f503a  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800f5041  mov     r8, r14; dwBytes
0x1800f5044  xor     edx, edx; dwFlags
0x1800f5046  mov     [rax], rdi
0x1800f5049  mov     [rax+8], rdi
0x1800f504d  mov     cs:?gpCustomSurrogateList@@3PEAVCSurrogateList@@EA, rax; CSurrogateList * gpCustomSurrogateList
0x1800f5054  call    cs:__imp_HeapAlloc
0x1800f505b  nop     dword ptr [rax+rax+00h]
0x1800f5060  test    rax, rax
0x1800f5063  jz      loc_1800F516B
0x1800f5069  lea     rdx, [rbp+57h+var_40]; int *
0x1800f506d  mov     rcx, rax; this
0x1800f5070  call    ??0CSharedLock@@QEAA@AEAJ@Z; CSharedLock::CSharedLock(long &)
0x1800f5075  mov     cs:?gpRemoteMachineLock@@3PEAVCSharedLock@@EA, rax; CSharedLock * gpRemoteMachineLock
0x1800f507c  test    rax, rax
0x1800f507f  jz      loc_1800F51B1
0x1800f5085  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800f508c  lea     r8d, [rbx+8]; dwBytes
0x1800f5090  xor     edx, edx; dwFlags
0x1800f5092  call    cs:__imp_HeapAlloc
0x1800f5099  nop     dword ptr [rax+rax+00h]
0x1800f509e  test    rax, rax
0x1800f50a1  jz      loc_1800F5162
0x1800f50a7  mov     ecx, cs:?gdwRemoteBindingHandleCacheMaxSize@@3KA; ulong gdwRemoteBindingHandleCacheMaxSize
0x1800f50ad  mov     r8d, ebx; dwBytes
0x1800f50b0  mov     [rax+14h], ecx
0x1800f50b3  xor     edx, edx; dwFlags
0x1800f50b5  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800f50bc  mov     [rax], rdi
0x1800f50bf  mov     [rax+8], rdi
0x1800f50c3  mov     [rax+10h], edi
0x1800f50c6  mov     cs:?gpRemoteMachineList@@3PEAVCRemoteMachineList@@EA, rax; CRemoteMachineList * gpRemoteMachineList
0x1800f50cd  call    cs:__imp_HeapAlloc
0x1800f50d4  nop     dword ptr [rax+rax+00h]
0x1800f50d9  test    rax, rax
0x1800f50dc  jz      short loc_1800F5159
0x1800f50de  lea     rdx, [rbp+57h+var_40]; int *
0x1800f50e2  mov     rcx, rax; this
0x1800f50e5  call    ??0CNamedObjectTable@@QEAA@AEAJ@Z; CNamedObjectTable::CNamedObjectTable(long &)
0x1800f50ea  mov     cs:?gpNamedObjectTable@@3PEAVCNamedObjectTable@@EA, rax; CNamedObjectTable * gpNamedObjectTable
0x1800f50f1  test    rax, rax
0x1800f50f4  jz      loc_1800F51B1
0x1800f50fa  cmp     [rbp+57h+var_40], edi
0x1800f50fd  jnz     loc_1800F51B1
0x1800f5103  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800f510a  lea     r8d, [rbx+30h]; dwBytes
0x1800f510e  xor     edx, edx; dwFlags
0x1800f5110  call    cs:__imp_HeapAlloc
0x1800f5117  nop     dword ptr [rax+rax+00h]
0x1800f511c  mov     rbx, rax
0x1800f511f  test    rax, rax
0x1800f5122  jz      short loc_1800F5150
0x1800f5124  lea     rcx, [rax+10h]; this
0x1800f5128  mov     [rax], rdi
0x1800f512b  mov     [rcx+28h], edi
0x1800f512e  mov     [rax+8], rdi
0x1800f5132  call    ?FInit@CMutexSem2@@QEAAHXZ; CMutexSem2::FInit(void)
0x1800f5137  neg     eax
0x1800f5139  mov     cs:?gActivationStateList@@3PEAVCActivationStateList@@EA, rbx; CActivationStateList * gActivationStateList
0x1800f5140  sbb     ecx, ecx
0x1800f5142  not     ecx
0x1800f5144  test    ecx, 0Eh
0x1800f514a  jnz     short loc_1800F51B1
0x1800f514c  xor     eax, eax
  ... truncated ...
```
