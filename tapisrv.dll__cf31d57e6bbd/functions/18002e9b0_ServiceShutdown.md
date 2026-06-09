# ServiceShutdown

- ea: `0x18002e9b0`
- end: `0x18002ef9f`
- name: `ServiceShutdown`
- size: `1519`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18002d6d0`

## callees

- `0x18001c7c0`
- `0x180026730`
- `0x180026c54`
- `0x18002c448`
- `0x18002c8d4`
- `0x18002d27c`
- `0x18002e9b0`
- `0x18003dc84`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18002eedb`
- `KERNEL32!GetProcessHeap` at `0x18002eedb`
- `KERNEL32!DeleteCriticalSection` at `0x18002ecbf`
- `KERNEL32!DeleteCriticalSection` at `0x18002ecfa`
- `KERNEL32!DeleteCriticalSection` at `0x18002ed0f`
- `KERNEL32!DeleteCriticalSection` at `0x18002ed28`
- `KERNEL32!DeleteCriticalSection` at `0x18002ed41`
- `KERNEL32!DeleteCriticalSection` at `0x18002ed5a`
- `KERNEL32!DeleteCriticalSection` at `0x18002ed70`
- `KERNEL32!DeleteCriticalSection` at `0x18002ed86`
- `KERNEL32!DeleteCriticalSection` at `0x18002ed9c`
- `KERNEL32!DeleteCriticalSection` at `0x18002edb2`
- `KERNEL32!DeleteCriticalSection` at `0x18002edc8`
- `KERNEL32!DeleteCriticalSection` at `0x18002ede1`
- `KERNEL32!DeleteCriticalSection` at `0x18002edfa`
- `KERNEL32!DeleteCriticalSection` at `0x18002ee68`
- `KERNEL32!DeleteCriticalSection` at `0x18002eec0`
- `KERNEL32!DeleteCriticalSection` at `0x18002ecbf`
- `KERNEL32!DeleteCriticalSection` at `0x18002ecfa`
- `KERNEL32!DeleteCriticalSection` at `0x18002ed0f`
- `KERNEL32!DeleteCriticalSection` at `0x18002ed28`
- `KERNEL32!DeleteCriticalSection` at `0x18002ed41`
- `KERNEL32!DeleteCriticalSection` at `0x18002ed5a`
- `KERNEL32!DeleteCriticalSection` at `0x18002ed70`
- `KERNEL32!DeleteCriticalSection` at `0x18002ed86`
- `KERNEL32!DeleteCriticalSection` at `0x18002ed9c`
- `KERNEL32!DeleteCriticalSection` at `0x18002edb2`
- `KERNEL32!DeleteCriticalSection` at `0x18002edc8`
- `KERNEL32!DeleteCriticalSection` at `0x18002ede1`
- `KERNEL32!DeleteCriticalSection` at `0x18002edfa`
- `KERNEL32!DeleteCriticalSection` at `0x18002ee68`
- `KERNEL32!DeleteCriticalSection` at `0x18002eec0`
- `KERNEL32!HeapDestroy` at `0x18002eeed`
- `KERNEL32!HeapDestroy` at `0x18002eeed`
- `KERNEL32!UnregisterWait` at `0x18002ef25`
- `KERNEL32!UnregisterWait` at `0x18002ef25`
- `KERNEL32!HeapFree` at `0x18002eeb6`
- `KERNEL32!HeapFree` at `0x18002eece`
- `KERNEL32!HeapFree` at `0x18002eeb6`
- `KERNEL32!HeapFree` at `0x18002eece`
- `KERNEL32!CloseHandle` at `0x18002e9ec`
- `KERNEL32!CloseHandle` at `0x18002ec3f`
- `KERNEL32!CloseHandle` at `0x18002ecab`
- `KERNEL32!CloseHandle` at `0x18002ee0c`
- `KERNEL32!CloseHandle` at `0x18002eeff`
- `KERNEL32!CloseHandle` at `0x18002ef18`
- `KERNEL32!CloseHandle` at `0x18002e9ec`
- `KERNEL32!CloseHandle` at `0x18002ec3f`
- `KERNEL32!CloseHandle` at `0x18002ecab`
- `KERNEL32!CloseHandle` at `0x18002ee0c`
- `KERNEL32!CloseHandle` at `0x18002eeff`
- `KERNEL32!CloseHandle` at `0x18002ef18`
- `KERNEL32!SetEvent` at `0x18002eba3`
- `KERNEL32!SetEvent` at `0x18002ec1f`
- `KERNEL32!SetEvent` at `0x18002eba3`
- `KERNEL32!SetEvent` at `0x18002ec1f`
- `KERNEL32!Sleep` at `0x18002eae4`
- `KERNEL32!Sleep` at `0x18002ebd0`
- `KERNEL32!Sleep` at `0x18002ebf4`
- `KERNEL32!Sleep` at `0x18002ec2a`
- `KERNEL32!Sleep` at `0x18002ec81`
- `KERNEL32!Sleep` at `0x18002eae4`
- `KERNEL32!Sleep` at `0x18002ebd0`
- `KERNEL32!Sleep` at `0x18002ebf4`
- `KERNEL32!Sleep` at `0x18002ec2a`
- `KERNEL32!Sleep` at `0x18002ec81`
- `KERNEL32!GetCurrentThreadId` at `0x18002ea28`
- `KERNEL32!GetCurrentThreadId` at `0x18002ea6e`
- `KERNEL32!GetCurrentThreadId` at `0x18002eb0d`
- `KERNEL32!GetCurrentThreadId` at `0x18002eb4b`
- `KERNEL32!GetCurrentThreadId` at `0x18002ea28`
- `KERNEL32!GetCurrentThreadId` at `0x18002ea6e`
- `KERNEL32!GetCurrentThreadId` at `0x18002eb0d`
- `KERNEL32!GetCurrentThreadId` at `0x18002eb4b`
- `KERNEL32!WaitForSingleObject` at `0x18002e9e3`
- `KERNEL32!WaitForSingleObject` at `0x18002e9e3`
- `KERNEL32!LeaveCriticalSection` at `0x18002ea90`
- `KERNEL32!LeaveCriticalSection` at `0x18002eb6d`
- `KERNEL32!LeaveCriticalSection` at `0x18002ebb7`
- `KERNEL32!LeaveCriticalSection` at `0x18002ea90`
- `KERNEL32!LeaveCriticalSection` at `0x18002eb6d`
- `KERNEL32!LeaveCriticalSection` at `0x18002ebb7`
- `KERNEL32!EnterCriticalSection` at `0x18002ea18`
- `KERNEL32!EnterCriticalSection` at `0x18002eafd`
- `KERNEL32!EnterCriticalSection` at `0x18002eb91`
- `KERNEL32!EnterCriticalSection` at `0x18002ea18`
- `KERNEL32!EnterCriticalSection` at `0x18002eafd`
- `KERNEL32!EnterCriticalSection` at `0x18002eb91`
- `USER32!DestroyIcon` at `0x18002ee1e`
- `USER32!DestroyIcon` at `0x18002ee37`
- `USER32!DestroyIcon` at `0x18002ee1e`
- `USER32!DestroyIcon` at `0x18002ee37`
- `rtutils!TraceDeregisterW` at `0x18002ef80`
- `rtutils!TraceDeregisterW` at `0x18002ef80`

## string_xrefs

- `0x18002ef50`: `ServiceMain: exit`

## pseudocode

```c
void __fastcall ServiceShutdown(__int64 a1)
{
  HANDLE v1; // rbx
  void *v2; // rdi
  void *v3; // rsi
  size_t v4; // rdx
  __int64 v5; // rcx
  size_t v6; // rdx
  __int64 v7; // rdi
  unsigned int v8; // ebx
  size_t v9; // rdx
  __int64 v10; // rcx
  size_t v11; // rdx
  unsigned int i; // edi
  unsigned __int64 v13; // rbx
  unsigned int j; // edi
  unsigned __int64 v15; // rbx
  unsigned int k; // ebx
  char *v17; // rbx
  __int64 v18; // rdx
  bool v19; // zf

  if ( a1 )
  {
    v1 = *(HANDLE *)a1;
    v2 = *(void **)(a1 + 8);
    v3 = *(void **)(a1 + 16);
    if ( *(_QWORD *)a1 )
    {
      WaitForSingleObject(*(HANDLE *)a1, 0xFFFFFFFF);
      CloseHandle(v1);
    }
    if ( gbNTServer && (gdwServiceInitFlags & 0x800) != 0 )
    {
      EnterCriticalSection(&CriticalSection);
      dword_1800519E0 = 2092;
      dword_1800519E4 = GetCurrentThreadId();
      StringCbCopyA(pszDest, v4, "server\\server.c");
      if ( !dword_180051918 && !dword_180051928 && gbServerInited )
        ServerShutdown(v5);
      dword_1800519F8 = 2100;
      dword_1800519FC = GetCurrentThreadId();
      StringCbCopyA(byte_1800519E8, v6, "server\\server.c");
      LeaveCriticalSection(&CriticalSection);
    }
    ServerFree(v2);
    ServerFree(v3);
    gbSPEventHandlerThreadExit = 1;
LABEL_12:
    while ( 1 )
    {
      v7 = qword_180051908;
      if ( !qword_180051908 )
        break;
      if ( !(unsigned int)CleanUpClient(qword_180051908, 1) )
      {
        v8 = 0;
        if ( v7 == qword_180051908 )
        {
          while ( v8 < 0xA )
          {
            Sleep(0x64u);
            ++v8;
            if ( v7 != qword_180051908 )
            {
              if ( v8 < 0xA )
                goto LABEL_12;
              break;
            }
          }
          EnterCriticalSection(&CriticalSection);
          dword_1800519E0 = 2138;
          dword_1800519E4 = GetCurrentThreadId();
          StringCbCopyA(pszDest, v9, "server\\server.c");
          if ( dword_180051918 || dword_180051928 )
            ServerShutdown(v10);
          dword_1800519F8 = 2146;
          dword_1800519FC = GetCurrentThreadId();
          StringCbCopyA(byte_1800519E8, v11, "server\\server.c");
          LeaveCriticalSection(&CriticalSection);
          break;
        }
      }
    }
    for ( i = 0; i < gdwNumSPEventHandlerThreads; ++i )
    {
      v13 = (unsigned __int64)i << 6;
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)aSPEventHandlerThreadInfo + v13 + 24));
      SetEvent(*(HANDLE *)((char *)aSPEventHandlerThreadInfo + v13 + 16));
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)aSPEventHandlerThreadInfo + v13 + 24));
    }
    while ( _InterlockedExchange((volatile __int32 *)&gRundownLock, 1) == 1 )
      Sleep(0x32u);
    dword_180051D48 = 1;
    _InterlockedExchange((volatile __int32 *)&gRundownLock, 0);
    while ( HIDWORD(gRundownLock) )
      Sleep(0x32u);
    if ( (dword_180051900 & 2) != 0 && (gdwServiceInitFlags & 0x10000) != 0 )
    {
      dword_180051D20 = 1;
      while ( dword_180051D08 )
      {
        SetEvent(hEvent);
        Sleep(0x64u);
      }
      CloseHandle(hEvent);
      ServerFree(gEventNotificationThreadParams);
      ServerFree(qword_180051D10);
    }
    if ( (gdwServiceInitFlags & 0x8000) != 0 )
      CleanUpManagementMemory();
    ServerFree((LPVOID)lpString);
    while ( glNumActiveSPEventHandlerThreads )
      Sleep(0x64u);
    for ( j = 0; j < gdwNumSPEventHandlerThreads; ++j )
    {
      v15 = (unsigned __int64)j << 6;
      CloseHandle(*(HANDLE *)((char *)aSPEventHandlerThreadInfo + v15 + 16));
      DeleteCriticalSection((LPCRITICAL_SECTION)((char *)aSPEventHandlerThreadInfo + v15 + 24));
    }
    if ( aSPEventHandlerThreadInfo != gSPEventHandlerThreadInfo )
      ServerFree(aSPEventHandlerThreadInfo);
    if ( (gdwServiceInitFlags & 0x2000) != 0 )
      DeleteCriticalSection(&gMgmtCritSec);
    if ( (gdwServiceInitFlags & 0x800) != 0 )
      DeleteCriticalSection(&CriticalSection);
    if ( (gdwServiceInitFlags & 0x1000) != 0 )
      DeleteCriticalSection(&stru_180051A00);
    if ( (gdwServiceInitFlags & 0x200) != 0 )
      DeleteCriticalSection(&gCnClientMsgPendingCritSec);
    if ( (gdwServiceInitFlags & 0x400) != 0 )
      DeleteCriticalSection(&gDgClientMsgPendingCritSec);
    if ( (gdwServiceInitFlags & 8) != 0 )
      DeleteCriticalSection(&gSafeMutexCritSec);
    if ( (gdwServiceInitFlags & 0x10) != 0 )
      DeleteCriticalSection(&gRemoteCliEventBufCritSec);
    if ( (gdwServiceInitFlags & 0x20) != 0 )
      DeleteCriticalSection(&gPriorityListCritSec);
    if ( (gdwServiceInitFlags & 0x40) != 0 )
      DeleteCriticalSection(&gManagementDllsCritSec);
    if ( (gdwServiceInitFlags & 0x80u) != 0 )
      DeleteCriticalSection(&gDllListCritSec);
    if ( (gdwServiceInitFlags & 0x40000) != 0 )
      DeleteCriticalSection(&gSCPCritSec);
    if ( (gdwServiceInitFlags & 0x100) != 0 )
      DeleteCriticalSection(&gClientHandleCritSec);
    if ( ghProvRegistryMutex )
      CloseHandle(ghProvRegistryMutex);
    if ( hIcon )
    {
      DestroyIcon(hIcon);
      hIcon = 0;
    }
    if ( qword_1800518F0 )
    {
      DestroyIcon(qword_1800518F0);
      qword_1800518F0 = 0;
    }
    if ( (gdwServiceInitFlags & 4) != 0 )
    {
      for ( k = 0; k < gdwNumLockTableEntries; ++k )
        DeleteCriticalSection((LPCRITICAL_SECTION)gLockTable + k);
      if ( gLockTable != gLockTableCritSecs )
        ServerFree(gLockTable);
    }
    if ( Src )
      ServerFree(Src);
    v17 = (char *)ghHandleTable;
    if ( ghHandleTable )
    {
      HeapFree(*(HANDLE *)ghHandleTable, 0, *((LPVOID *)ghHandleTable + 1));
      DeleteCriticalSection((LPCRITICAL_SECTION)(v17 + 48));
      HeapFree(*(HANDLE *)v17, 0, v17);
      ghHandleTable = 0;
    }
    if ( ghTapisrvHeap != GetProcessHeap() )
      HeapDestroy(ghTapisrvHeap);
    if ( ghEventService )
    {
      CloseHandle(ghEventService);
      ghEventService = 0;
    }
    if ( ghSCMAutostartEvent )
      CloseHandle(ghSCMAutostartEvent);
    UnregisterWait(g_hWaitSvcShutdown);
    v19 = (gdwServiceInitFlags & 2) == 0;
    gdwServiceInitFlags = 0;
    if ( !v19 )
    {
      gdwServiceState = 1;
      ReportStatusToSCMgr(1, v18, 0, 0);
    }
    TRACELogPrint(524290, "ServiceMain: exit");
    *(_DWORD *)&sg_dwTracingToDebugger = 0;
    *(_DWORD *)&sg_dwTracingToConsole = 0;
    *(_DWORD *)&sg_dwTracingToFile = 0;
    if ( sg_dwTraceID != -1 )
    {
      TraceDeregisterW(sg_dwTraceID);
      sg_dwTraceID = -1;
    }
  }
}

```

## disassembly

```asm
0x18002e9b0  test    rcx, rcx
0x18002e9b3  jz      locret_18002EF9E
0x18002e9b9  mov     [rsp+arg_8], rbx
0x18002e9be  mov     [rsp+arg_10], rbp
0x18002e9c3  push    rsi
0x18002e9c4  push    rdi
0x18002e9c5  push    r12
0x18002e9c7  sub     rsp, 20h
0x18002e9cb  mov     rbx, [rcx]
0x18002e9ce  xor     ebp, ebp
0x18002e9d0  mov     rdi, [rcx+8]
0x18002e9d4  mov     rsi, [rcx+10h]
0x18002e9d8  test    rbx, rbx
0x18002e9db  jz      short loc_18002E9F2
0x18002e9dd  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18002e9e0  mov     rcx, rbx; hHandle
0x18002e9e3  call    cs:__imp_WaitForSingleObject
0x18002e9e9  mov     rcx, rbx; hObject
0x18002e9ec  call    cs:__imp_CloseHandle
0x18002e9f2  cmp     cs:gbNTServer, ebp
0x18002e9f8  lea     r12, CriticalSection
0x18002e9ff  jz      loc_18002EA96
0x18002ea05  test    cs:gdwServiceInitFlags, 800h
0x18002ea0f  jz      loc_18002EA96
0x18002ea15  mov     rcx, r12; lpCriticalSection
0x18002ea18  call    cs:__imp_EnterCriticalSection
0x18002ea1e  mov     cs:dword_1800519E0, 82Ch
0x18002ea28  call    cs:__imp_GetCurrentThreadId
0x18002ea2e  lea     r8, aPrintscanTapiS_3+0Fh; pszSrc
0x18002ea35  mov     cs:dword_1800519E4, eax
0x18002ea3b  lea     rcx, pszDest; pszDest
0x18002ea42  call    StringCbCopyA
0x18002ea47  cmp     cs:dword_180051918, ebp
0x18002ea4d  jnz     short loc_18002EA64
0x18002ea4f  cmp     cs:dword_180051928, ebp
0x18002ea55  jnz     short loc_18002EA64
0x18002ea57  cmp     cs:gbServerInited, ebp
0x18002ea5d  jz      short loc_18002EA64
0x18002ea5f  call    ServerShutdown
0x18002ea64  mov     cs:dword_1800519F8, 834h
0x18002ea6e  call    cs:__imp_GetCurrentThreadId
0x18002ea74  lea     r8, aPrintscanTapiS_3+0Fh; pszSrc
0x18002ea7b  mov     cs:dword_1800519FC, eax
0x18002ea81  lea     rcx, byte_1800519E8; pszDest
0x18002ea88  call    StringCbCopyA
0x18002ea8d  mov     rcx, r12; lpCriticalSection
0x18002ea90  call    cs:__imp_LeaveCriticalSection
0x18002ea96  mov     rcx, rdi; lpMem
0x18002ea99  call    ServerFree
0x18002ea9e  mov     rcx, rsi; lpMem
0x18002eaa1  call    ServerFree
0x18002eaa6  mov     esi, 1
0x18002eaab  mov     cs:gbSPEventHandlerThreadExit, esi
0x18002eab1  mov     rdi, cs:qword_180051908
0x18002eab8  test    rdi, rdi
0x18002eabb  jz      loc_18002EB73
0x18002eac1  mov     edx, esi
0x18002eac3  mov     rcx, rdi
0x18002eac6  call    CleanUpClient
0x18002eacb  test    eax, eax
0x18002eacd  jnz     short loc_18002EAB1
0x18002eacf  cmp     rdi, cs:qword_180051908
0x18002ead6  mov     ebx, ebp
0x18002ead8  jnz     short loc_18002EAB1
0x18002eada  cmp     ebx, 0Ah
0x18002eadd  jnb     short loc_18002EAFA
0x18002eadf  mov     ecx, 64h ; 'd'; dwMilliseconds
0x18002eae4  call    cs:__imp_Sleep
0x18002eaea  add     ebx, esi
0x18002eaec  cmp     rdi, cs:qword_180051908
0x18002eaf3  jz      short loc_18002EADA
0x18002eaf5  cmp     ebx, 0Ah
0x18002eaf8  jb      short loc_18002EAB1
0x18002eafa  mov     rcx, r12; lpCriticalSection
0x18002eafd  call    cs:__imp_EnterCriticalSection
0x18002eb03  mov     cs:dword_1800519E0, 85Ah
0x18002eb0d  call    cs:__imp_GetCurrentThreadId
0x18002eb13  lea     r8, aPrintscanTapiS_3+0Fh; pszSrc
0x18002eb1a  mov     cs:dword_1800519E4, eax
0x18002eb20  lea     rcx, pszDest; pszDest
0x18002eb27  call    StringCbCopyA
0x18002eb2c  cmp     cs:dword_180051918, ebp
0x18002eb32  jnz     short loc_18002EB3C
0x18002eb34  cmp     cs:dword_180051928, ebp
0x18002eb3a  jz      short loc_18002EB41
0x18002eb3c  call    ServerShutdown
0x18002eb41  mov     cs:dword_1800519F8, 862h
0x18002eb4b  call    cs:__imp_GetCurrentThreadId
0x18002eb51  lea     r8, aPrintscanTapiS_3+0Fh; pszSrc
0x18002eb58  mov     cs:dword_1800519FC, eax
0x18002eb5e  lea     rcx, byte_1800519E8; pszDest
0x18002eb65  call    StringCbCopyA
0x18002eb6a  mov     rcx, r12; lpCriticalSection
0x18002eb6d  call    cs:__imp_LeaveCriticalSection
0x18002eb73  cmp     cs:gdwNumSPEventHandlerThreads, ebp
0x18002eb79  mov     edi, ebp
0x18002eb7b  jbe     short loc_18002EBC7
0x18002eb7d  mov     rcx, cs:aSPEventHandlerThreadInfo
0x18002eb84  add     rcx, 18h
0x18002eb88  mov     ebx, edi
0x18002eb8a  shl     rbx, 6
0x18002eb8e  add     rcx, rbx; lpCriticalSection
0x18002eb91  call    cs:__imp_EnterCriticalSection
0x18002eb97  mov     rcx, cs:aSPEventHandlerThreadInfo
0x18002eb9e  mov     rcx, [rbx+rcx+10h]; hEvent
0x18002eba3  call    cs:__imp_SetEvent
0x18002eba9  mov     rcx, cs:aSPEventHandlerThreadInfo
0x18002ebb0  add     rcx, 18h
0x18002ebb4  add     rcx, rbx; lpCriticalSection
0x18002ebb7  call    cs:__imp_LeaveCriticalSection
0x18002ebbd  add     edi, esi
0x18002ebbf  cmp     edi, cs:gdwNumSPEventHandlerThreads
0x18002ebc5  jb      short loc_18002EB7D
0x18002ebc7  mov     ebx, 32h ; '2'
0x18002ebcc  jmp     short loc_18002EBD6
0x18002ebce  mov     ecx, ebx; dwMilliseconds
0x18002ebd0  call    cs:__imp_Sleep
0x18002ebd6  mov     eax, esi
0x18002ebd8  xchg    eax, dword ptr cs:gRundownLock
0x18002ebde  cmp     eax, esi
0x18002ebe0  jz      short loc_18002EBCE
0x18002ebe2  mov     eax, ebp
0x18002ebe4  mov     cs:dword_180051D48, esi
0x18002ebea  xchg    eax, dword ptr cs:gRundownLock
0x18002ebf0  jmp     short loc_18002EBFA
0x18002ebf2  mov     ecx, ebx; dwMilliseconds
0x18002ebf4  call    cs:__imp_Sleep
0x18002ebfa  cmp     dword ptr cs:gRundownLock+4, ebp
0x18002ec00  jnz     short loc_18002EBF2
0x18002ec02  test    byte ptr cs:dword_180051900, 2
0x18002ec09  jz      short loc_18002EC5D
0x18002ec0b  test    cs:gdwServiceInitFlags, 10000h
0x18002ec15  jz      short loc_18002EC5D
0x18002ec17  mov     cs:dword_180051D20, esi
0x18002ec1d  jmp     short loc_18002EC30
0x18002ec1f  call    cs:__imp_SetEvent
0x18002ec25  mov     ecx, 64h ; 'd'; dwMilliseconds
0x18002ec2a  call    cs:__imp_Sleep
0x18002ec30  cmp     cs:dword_180051D08, ebp
0x18002ec36  mov     rcx, cs:hEvent; hObject
0x18002ec3d  jnz     short loc_18002EC1F
0x18002ec3f  call    cs:__imp_CloseHandle
0x18002ec45  mov     rcx, cs:gEventNotificationThreadParams; lpMem
0x18002ec4c  call    ServerFree
0x18002ec51  mov     rcx, cs:qword_180051D10; lpMem
0x18002ec58  call    ServerFree
0x18002ec5d  test    cs:gdwServiceInitFlags, 8000h
0x18002ec67  jz      short loc_18002EC6E
0x18002ec69  call    CleanUpManagementMemory
0x18002ec6e  mov     rcx, cs:lpString; lpMem
0x18002ec75  call    ServerFree
0x18002ec7a  jmp     short loc_18002EC87
0x18002ec7c  mov     ecx, 64h ; 'd'; dwMilliseconds
0x18002ec81  call    cs:__imp_Sleep
0x18002ec87  cmp     cs:glNumActiveSPEventHandlerThreads, ebp
0x18002ec8d  jnz     short loc_18002EC7C
0x18002ec8f  cmp     cs:gdwNumSPEventHandlerThreads, ebp
0x18002ec95  mov     edi, ebp
0x18002ec97  jbe     short loc_18002ECCF
0x18002ec99  mov     rcx, cs:aSPEventHandlerThreadInfo
0x18002eca0  mov     ebx, edi
0x18002eca2  shl     rbx, 6
0x18002eca6  mov     rcx, [rbx+rcx+10h]; hObject
0x18002ecab  call    cs:__imp_CloseHandle
0x18002ecb1  mov     rcx, cs:aSPEventHandlerThreadInfo
0x18002ecb8  add     rcx, 18h
0x18002ecbc  add     rcx, rbx; lpCriticalSection
0x18002ecbf  call    cs:__imp_DeleteCriticalSection
0x18002ecc5  add     edi, esi
0x18002ecc7  cmp     edi, cs:gdwNumSPEventHandlerThreads
0x18002eccd  jb      short loc_18002EC99
0x18002eccf  mov     rcx, cs:aSPEventHandlerThreadInfo; lpMem
0x18002ecd6  lea     rax, gSPEventHandlerThreadInfo
0x18002ecdd  cmp     rcx, rax
0x18002ece0  jz      short loc_18002ECE7
0x18002ece2  call    ServerFree
0x18002ece7  test    cs:gdwServiceInitFlags, 2000h
0x18002ecf1  jz      short loc_18002ED00
0x18002ecf3  lea     rcx, gMgmtCritSec; lpCriticalSection
0x18002ecfa  call    cs:__imp_DeleteCriticalSection
0x18002ed00  test    cs:gdwServiceInitFlags, 800h
0x18002ed0a  jz      short loc_18002ED15
0x18002ed0c  mov     rcx, r12; lpCriticalSection
0x18002ed0f  call    cs:__imp_DeleteCriticalSection
0x18002ed15  test    cs:gdwServiceInitFlags, 1000h
0x18002ed1f  jz      short loc_18002ED2E
0x18002ed21  lea     rcx, stru_180051A00; lpCriticalSection
0x18002ed28  call    cs:__imp_DeleteCriticalSection
0x18002ed2e  test    cs:gdwServiceInitFlags, 200h
0x18002ed38  jz      short loc_18002ED47
0x18002ed3a  lea     rcx, gCnClientMsgPendingCritSec; lpCriticalSection
0x18002ed41  call    cs:__imp_DeleteCriticalSection
0x18002ed47  test    cs:gdwServiceInitFlags, 400h
0x18002ed51  jz      short loc_18002ED60
0x18002ed53  lea     rcx, gDgClientMsgPendingCritSec; lpCriticalSection
0x18002ed5a  call    cs:__imp_DeleteCriticalSection
0x18002ed60  test    byte ptr cs:gdwServiceInitFlags, 8
0x18002ed67  jz      short loc_18002ED76
0x18002ed69  lea     rcx, gSafeMutexCritSec; lpCriticalSection
0x18002ed70  call    cs:__imp_DeleteCriticalSection
0x18002ed76  test    byte ptr cs:gdwServiceInitFlags, 10h
0x18002ed7d  jz      short loc_18002ED8C
0x18002ed7f  lea     rcx, gRemoteCliEventBufCritSec; lpCriticalSection
0x18002ed86  call    cs:__imp_DeleteCriticalSection
0x18002ed8c  test    byte ptr cs:gdwServiceInitFlags, 20h
0x18002ed93  jz      short loc_18002EDA2
0x18002ed95  lea     rcx, gPriorityListCritSec; lpCriticalSection
0x18002ed9c  call    cs:__imp_DeleteCriticalSection
0x18002eda2  test    byte ptr cs:gdwServiceInitFlags, 40h
0x18002eda9  jz      short loc_18002EDB8
0x18002edab  lea     rcx, gManagementDllsCritSec; lpCriticalSection
0x18002edb2  call    cs:__imp_DeleteCriticalSection
0x18002edb8  test    byte ptr cs:gdwServiceInitFlags, 80h
0x18002edbf  jz      short loc_18002EDCE
0x18002edc1  lea     rcx, gDllListCritSec; lpCriticalSection
0x18002edc8  call    cs:__imp_DeleteCriticalSection
0x18002edce  test    cs:gdwServiceInitFlags, 40000h
0x18002edd8  jz      short loc_18002EDE7
0x18002edda  lea     rcx, gSCPCritSec; lpCriticalSection
0x18002ede1  call    cs:__imp_DeleteCriticalSection
0x18002ede7  test    cs:gdwServiceInitFlags, 100h
0x18002edf1  jz      short loc_18002EE00
0x18002edf3  lea     rcx, gClientHandleCritSec; lpCriticalSection
0x18002edfa  call    cs:__imp_DeleteCriticalSection
0x18002ee00  mov     rcx, cs:ghProvRegistryMutex; hObject
0x18002ee07  test    rcx, rcx
0x18002ee0a  jz      short loc_18002EE12
0x18002ee0c  call    cs:__imp_CloseHandle
0x18002ee12  mov     rcx, cs:hIcon; hIcon
0x18002ee19  test    rcx, rcx
0x18002ee1c  jz      short loc_18002EE2B
0x18002ee1e  call    cs:__imp_DestroyIcon
0x18002ee24  mov     cs:hIcon, rbp
0x18002ee2b  mov     rcx, cs:qword_1800518F0; hIcon
0x18002ee32  test    rcx, rcx
0x18002ee35  jz      short loc_18002EE44
0x18002ee37  call    cs:__imp_DestroyIcon
0x18002ee3d  mov     cs:qword_1800518F0, rbp
0x18002ee44  test    byte ptr cs:gdwServiceInitFlags, 4
0x18002ee4b  jz      short loc_18002EE90
0x18002ee4d  cmp     cs:gdwNumLockTableEntries, ebp
0x18002ee53  mov     ebx, ebp
0x18002ee55  jbe     short loc_18002EE78
0x18002ee57  mov     eax, ebx
0x18002ee59  lea     rcx, [rax+rax*4]
0x18002ee5d  mov     rax, cs:gLockTable
0x18002ee64  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x18002ee68  call    cs:__imp_DeleteCriticalSection
0x18002ee6e  add     ebx, esi
0x18002ee70  cmp     ebx, cs:gdwNumLockTableEntries
0x18002ee76  jb      short loc_18002EE57
0x18002ee78  mov     rcx, cs:gLockTable; lpMem
0x18002ee7f  lea     rax, gLockTableCritSecs
0x18002ee86  cmp     rcx, rax
0x18002ee89  jz      short loc_18002EE90
0x18002ee8b  call    ServerFree
0x18002ee90  mov     rcx, cs:Src; lpMem
0x18002ee97  test    rcx, rcx
0x18002ee9a  jz      short loc_18002EEA1
0x18002ee9c  call    ServerFree
0x18002eea1  mov     rbx, cs:ghHandleTable
0x18002eea8  test    rbx, rbx
0x18002eeab  jz      short loc_18002EEDB
0x18002eead  mov     r8, [rbx+8]; lpMem
0x18002eeb1  xor     edx, edx; dwFlags
0x18002eeb3  mov     rcx, [rbx]; hHeap
0x18002eeb6  call    cs:__imp_HeapFree
0x18002eebc  lea     rcx, [rbx+30h]; lpCriticalSection
0x18002eec0  call    cs:__imp_DeleteCriticalSection
0x18002eec6  mov     rcx, [rbx]; hHeap
0x18002eec9  mov     r8, rbx; lpMem
0x18002eecc  xor     edx, edx; dwFlags
0x18002eece  call    cs:__imp_HeapFree
0x18002eed4  mov     cs:ghHandleTable, rbp
0x18002eedb  call    cs:__imp_GetProcessHeap
0x18002eee1  mov     rcx, cs:ghTapisrvHeap; hHeap
0x18002eee8  cmp     rcx, rax
0x18002eeeb  jz      short loc_18002EEF3
0x18002eeed  call    cs:__imp_HeapDestroy
0x18002eef3  mov     rcx, cs:ghEventService; hObject
0x18002eefa  test    rcx, rcx
0x18002eefd  jz      short loc_18002EF0C
0x18002eeff  call    cs:__imp_CloseHandle
0x18002ef05  mov     cs:ghEventService, rbp
0x18002ef0c  mov     rcx, cs:ghSCMAutostartEvent; hObject
0x18002ef13  test    rcx, rcx
0x18002ef16  jz      short loc_18002EF1E
0x18002ef18  call    cs:__imp_CloseHandle
0x18002ef1e  mov     rcx, cs:g_hWaitSvcShutdown; WaitHandle
0x18002ef25  call    cs:__imp_UnregisterWait
0x18002ef2b  test    cs:gdwServiceInitFlags, 2
0x18002ef35  mov     cs:gdwServiceInitFlags, ebp
0x18002ef3b  jz      short loc_18002EF50
0x18002ef3d  xor     r9d, r9d
0x18002ef40  mov     cs:gdwServiceState, esi
0x18002ef46  xor     r8d, r8d
0x18002ef49  mov     ecx, esi
0x18002ef4b  call    ReportStatusToSCMgr
0x18002ef50  lea     rdx, aServicemainExi; "ServiceMain: exit"
0x18002ef57  mov     ecx, 80002h
  ... truncated ...
```
