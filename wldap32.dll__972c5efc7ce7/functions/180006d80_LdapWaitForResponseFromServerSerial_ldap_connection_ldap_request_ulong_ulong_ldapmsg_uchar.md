# LdapWaitForResponseFromServerSerial(ldap_connection *,ldap_request *,ulong,ulong,ldapmsg * *,uchar)

- ea: `0x180006d80`
- end: `0x180008066`
- name: `?LdapWaitForResponseFromServerSerial@@YAKPEAUldap_connection@@PEAUldap_request@@KKPEAPEAUldapmsg@@E@Z`
- size: `4838`
- prototype: `unsigned int __usercall@<eax>(struct ldap_connection *@<rcx>, struct ldap_request *@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, struct ldapmsg **, unsigned __int8)`
- caller_count: `1`
- callee_count: `22`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000cad0`

## callees

- `0x1800037a8`
- `0x1800057a0`
- `0x180006510`
- `0x180006d80`
- `0x180008070`
- `0x180009040`
- `0x1800094a0`
- `0x18000a280`
- `0x18000a358`
- `0x18000adb0`
- `0x18000b440`
- `0x18000e0d0`
- `0x1800112b0`
- `0x1800147f0`
- `0x180015bd8`
- `0x18001a730`
- `0x18001e7b0`
- `0x1800235b0`
- `0x180027a30`
- `0x1800299c0`
- `0x18002cf6c`
- `0x18003b448`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006f92`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007001`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800071c7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800072ac`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800074c8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000761d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000779c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000786c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007940`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007965`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800079ea`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007c50`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007e22`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006f92`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007001`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800071c7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800072ac`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800074c8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000761d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000779c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000786c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007940`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007965`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800079ea`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007c50`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007e22`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006fca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007046`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800071ea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007212`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800072c9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800074fe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800075f2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000763d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007673`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007735`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800077b9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007889`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000797f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800079d0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007a3a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007c9c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007cba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007d09`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007d3e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007e40`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007f71`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000800c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006fca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007046`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800071ea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007212`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800072c9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800074fe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800075f2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000763d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007673`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007735`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800077b9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007889`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000797f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800079d0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007a3a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007c9c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007cba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007d09`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007d3e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007e40`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007f71`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000800c`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180006eca`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180006eca`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180006f7f`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800070ba`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180006f7f`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800070ba`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180007079`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180007da2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180007079`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180007da2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006ef4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006ef4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000709a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000709a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800071f6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007464`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800071f6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007464`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007b11`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007b11`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180006dbe`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000712d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180006dbe`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000712d`

## string_xrefs

- `0x180007c29`: `We became the result processing thread and found results for request 0x%x on connection 0x%x BEFORE calling DrainWinsock. Another thread must have failed to finish processing results.\n`
- `0x180007473`: `ldapWaitForResponse thread 0x%x has connection 0x%x as down.\n`

## pseudocode

```c
__int64 __fastcall LdapWaitForResponseFromServerSerial(
        struct ldap_connection *a1,
        struct ldap_request *a2,
        unsigned int a3,
        unsigned int a4,
        struct ldapmsg **a5,
        unsigned __int8 a6)
{
  struct ldapmsg **v6; // r15
  unsigned int v8; // esi
  unsigned int v9; // edi
  struct ldap_request *v10; // r13
  unsigned __int64 v11; // rax
  unsigned int v12; // ecx
  char v13; // r12
  __int64 v14; // r14
  _BYTE *i; // rax
  unsigned int ResponseFromServer; // ebx
  HANDLE EventA; // rbx
  LPVOID v18; // rax
  int v19; // ecx
  unsigned int v20; // eax
  struct ldap_connection *v21; // rax
  __int64 *v22; // rax
  DWORD v23; // ebx
  DWORD v24; // eax
  unsigned int j; // ebx
  unsigned __int64 v26; // r13
  int v27; // esi
  struct ldap_connection *v28; // rdi
  char v29; // al
  DWORD CurrentThreadId; // eax
  __int64 v32; // rdx
  unsigned __int8 v33; // al
  unsigned __int8 v34; // cl
  unsigned __int16 *v35; // r8
  unsigned __int16 **v36; // rdx
  _FILETIME v37; // rdi
  unsigned int v38; // eax
  unsigned int v39; // r9d
  char v40; // al
  int v41; // eax
  struct _RTL_CRITICAL_SECTION *v42; // rcx
  struct _RTL_CRITICAL_SECTION *v43; // rcx
  DWORD v44; // ebx
  struct _RTL_CRITICAL_SECTION *v45; // rcx
  int v46; // eax
  unsigned __int16 *v47; // [rsp+20h] [rbp-B8h]
  unsigned int v48; // [rsp+30h] [rbp-A8h]
  char v49; // [rsp+50h] [rbp-88h]
  unsigned int v50; // [rsp+54h] [rbp-84h]
  _FILETIME SystemTimeAsFileTime; // [rsp+58h] [rbp-80h] BYREF
  unsigned int v52; // [rsp+60h] [rbp-78h]
  unsigned __int64 TickCount; // [rsp+68h] [rbp-70h]
  int v54; // [rsp+70h] [rbp-68h]
  struct _FILETIME v55; // [rsp+78h] [rbp-60h] BYREF
  __int64 v56; // [rsp+80h] [rbp-58h] BYREF
  int v57; // [rsp+88h] [rbp-50h]
  __int64 v58; // [rsp+90h] [rbp-48h]
  unsigned int v60; // [rsp+F0h] [rbp+18h]

  v60 = a3;
  v6 = a5;
  SystemTimeAsFileTime = 0;
  v8 = a4;
  v9 = a3;
  v10 = a2;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v11 = *(unsigned __int64 *)&SystemTimeAsFileTime / 0x2710;
  TickCount = *(unsigned __int64 *)&SystemTimeAsFileTime / 0x2710;
  if ( a5 )
    *a5 = 0;
  v12 = 1;
  if ( v8 != 2 )
    v12 = v8;
  v50 = v12;
  if ( v10 )
    v54 = *((_DWORD *)v10 + 27);
  else
    v54 = 0;
  SystemTimeAsFileTime = (_FILETIME)((char *)v10 + 274);
  v13 = 0;
  v49 = 0;
  v52 = 0;
  if ( !a5 )
  {
    SystemTimeAsFileTime = (_FILETIME)((char *)v10 + 274);
    TickCount = v11;
    goto LABEL_19;
  }
  v14 = 0;
  if ( !v10 )
    goto LABEL_11;
  for ( i = (char *)v10 + 274; ; SystemTimeAsFileTime = (_FILETIME)i )
  {
    if ( *i )
    {
      v56 = 0;
      v57 = 8;
      v58 = 0;
      ResponseFromServer = LdapBuffersToMessages(a1, v8, (struct CRequestListHolder *)&v56);
      CRequestListHolder::FreeAll((CRequestListHolder *)&v56);
      if ( ResponseFromServer )
      {
        if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x10) != 0 )
          LDAPClientPrint(16, "LdapBuffersToMessages returned error 0x%x\n", ResponseFromServer);
        if ( v58 )
          ldapFree(v58, 1718960716);
        return ResponseFromServer;
      }
      CRequestListHolder::~CRequestListHolder((CRequestListHolder *)&v56);
      v12 = v50;
    }
LABEL_11:
    ResponseFromServer = LdapGetResponseFromServer(a1, v10, v12, v6);
    if ( !*v6 )
    {
      if ( v10 )
      {
        if ( a1 )
        {
          if ( *((_QWORD *)a1 + 120) != -1 )
          {
            v49 = 1;
            if ( v9 == -1 || !v9 )
            {
              v9 = 1000 * *((_DWORD *)a1 + 269);
LABEL_19:
              v60 = v9;
            }
          }
        }
      }
      EventA = CreateEventA(0, 0, 0, 0);
      if ( EventA )
      {
        v18 = HeapAlloc(LdapHeap, 8u, 0x38u);
        v19 = g_fTracingOn;
        v14 = (__int64)v18;
        if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
        {
          LDAPClientPrint(
            8,
            "ldapMalloc allocated 0x%x bytes at address 0x%x of tag 0x%x.\n",
            56,
            (_DWORD)v18,
            1767987020);
          v19 = g_fTracingOn;
        }
        v20 = LdapAllocatedHeap;
        if ( v14 )
        {
          *(_DWORD *)v14 = 1767987020;
          *(_DWORD *)(v14 + 4) = 48;
          v14 += 8;
          v20 += 48;
          LdapAllocatedHeap = v20;
        }
        if ( v19 && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
        {
          LDAPClientPrint(8, "ldapMalloc 0x%08x bytes at address 0x%x of tag %x, tot=%d.\n", 48, v14, 1767987020, v20);
          v19 = g_fTracingOn;
        }
        if ( v14 )
        {
          v21 = a1;
          if ( a1 )
            v21 = (struct ldap_connection *)ReferenceLdapConnection(a1);
          *(_QWORD *)(v14 + 16) = v21;
          *(_DWORD *)(v14 + 32) = v54;
          *(_BYTE *)(v14 + 41) = v6 == 0;
          *(_QWORD *)(v14 + 24) = EventA;
          *(_BYTE *)(v14 + 40) = 0;
          *(_DWORD *)(v14 + 36) = v8;
          ResetEvent(EventA);
          EnterCriticalSection(&WaiterLock);
          v22 = (__int64 *)qword_180065B20;
          ++GlobalWaiterCount;
          *(_QWORD *)v14 = &GlobalListWaiters;
          *(_QWORD *)(v14 + 8) = v22;
          *v22 = v14;
          qword_180065B20 = v14;
          LeaveCriticalSection(&WaiterLock);
        }
        else
        {
          if ( v19 && g_fProviderEnabled && (g_ulTraceFlags & 0x4000) != 0 )
            LDAPClientPrint(
              0x4000,
              "ldap GetMessageWaitStructure connection 0x%x failed allocate of 0x%x.\n",
              (_DWORD)a1,
              48);
          CloseHandle(EventA);
          v14 = 0;
        }
      }
      else
      {
        if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x10000000) != 0 )
          LDAPClientPrint(
            0x10000000,
            "ldap GetMessageWaitStructure connection 0x%x failed allocation of event.\n",
            (_DWORD)a1);
        v14 = 0;
      }
      if ( !v6 || (ResponseFromServer = LdapGetResponseFromServer(a1, v10, v50, v6), !*v6) )
      {
        if ( !GlobalCountOfOpenRequests )
        {
          if ( !v6 || (ResponseFromServer = LdapGetResponseFromServer(a1, v10, v50, v6), !*v6) )
          {
LABEL_182:
            ResponseFromServer = 89;
            SetConnectionError(a1, 89);
          }
          goto LABEL_80;
        }
        if ( !v14 )
        {
          if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x4000) != 0 )
            LDAPClientPrint(0x4000, "ldapGetMsg connection 0x%x failed wait allocation.\n", (_DWORD)a1);
          ResponseFromServer = 90;
          SetConnectionError(a1, 90);
          goto LABEL_80;
        }
        while ( 1 )
        {
          EnterCriticalSection(&ConnectionListLock);
          v13 = 1;
          if ( a1 && *((_BYTE *)a1 + 552) != 1 )
            goto LABEL_182;
          if ( v10 )
          {
            v29 = *((_BYTE *)v10 + 188);
            if ( v29 == 1 || *((_BYTE *)v10 + 184) == 1 )
            {
              ResponseFromServer = (v29 != 0) + 88;
              SetConnectionError(a1, ResponseFromServer);
              goto LABEL_80;
            }
          }
          if ( GlobalReceiveHandlerThread )
            break;
          if ( v6 )
          {
            LeaveCriticalSection(&ConnectionListLock);
            ResponseFromServer = LdapGetResponseFromServer(a1, v10, v50, v6);
            v13 = 1;
            EnterCriticalSection(&ConnectionListLock);
            if ( *v6 )
              goto LABEL_126;
          }
          if ( !a1 || *((_BYTE *)a1 + 553) == 8 )
          {
            if ( !GlobalReceiveHandlerThread )
            {
              EnterCriticalSection(&SelectLock2);
              if ( v10 )
              {
                v40 = *((_BYTE *)v10 + 188);
                if ( v40 == 1 || *((_BYTE *)v10 + 184) == 1 )
                {
                  ResponseFromServer = (v40 != 0) + 88;
                  SetConnectionError(a1, ResponseFromServer);
                  LeaveCriticalSection(&SelectLock2);
                  goto LABEL_80;
                }
              }
              InsideSelect = 1;
              LeaveCriticalSection(&SelectLock2);
              GlobalReceiveHandlerThread = GetCurrentThreadId();
              v13 = 0;
              LeaveCriticalSection(&ConnectionListLock);
              if ( v6 )
              {
                v28 = LdapAllBuffersToMessages(a1, v8);
                LdapGetResponseFromServer(a1, v10, v50, v6);
                if ( !*v6 )
                {
                  if ( v28 )
                  {
                    EnterCriticalSection((LPCRITICAL_SECTION)((char *)v28 + 512));
                    --*(_DWORD *)v28;
                    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 4) != 0 )
                      LDAPClientPrint(4, "LDAP deref conn 0x%x, new count = 0x%x\n", (_DWORD)v28, *(_DWORD *)v28);
                    v43 = (struct _RTL_CRITICAL_SECTION *)((char *)v28 + 512);
                    if ( *(_DWORD *)v28 )
                    {
                      LeaveCriticalSection(v43);
                    }
                    else
                    {
                      LeaveCriticalSection(v43);
                      DereferenceLdapConnection2((__int64)v28, 1);
                    }
                  }
                  v9 = v60;
                  goto LABEL_63;
                }
                if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400) != 0 )
                  LDAPClientPrint(
                    1024,
                    "We became the result processing thread and found results for request 0x%x on connection 0x%x BEFORE "
                    "calling DrainWinsock. Another thread must have failed to finish processing results.\n",
                    (_DWORD)v10,
                    (_DWORD)a1);
                InsideSelect = 0;
              }
              else
              {
LABEL_63:
                if ( v9 - 1 <= 0xFFFFFFFD )
                  v9 = v60 + TickCount - LdapGetTickCount();
                if ( v9 == -1 )
                {
                  for ( j = DrainWinsock(0xFFFFFFFF); !j; j = DrainWinsock(0) )
                    ;
                  if ( j == 10055 )
                  {
                    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x100000) != 0 )
                      LDAPClientPrint(0x100000, "Drainwinsock failed with error 0x%x\n", 10055);
                    SetConnectionError(a1, 10055);
                    InsideSelect = 0;
                    ResponseFromServer = 90;
                    EnterCriticalSection(&ConnectionListLock);
                    GlobalReceiveHandlerThread = 0;
                    LeaveCriticalSection(&ConnectionListLock);
                    goto LABEL_106;
                  }
                }
                else
                {
                  j = 0;
                  v26 = TickCount;
                  v27 = 0;
                  do
                  {
                    if ( j )
                      break;
                    j = DrainWinsock(0);
                    if ( !j )
                      ++v27;
                  }
                  while ( !v60 || v60 > LdapGetTickCount() - v26 );
                  v6 = a5;
                  v10 = a2;
                  if ( j != 258 )
                    goto LABEL_69;
                  if ( v9 && !v27 )
                  {
                    for ( j = DrainWinsock(v9); !j; j = DrainWinsock(0) )
                      ;
LABEL_69:
                    if ( j == 10055 )
                    {
                      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x100000) != 0 )
                        LDAPClientPrint(0x100000, "Drainwinsock failed with error 0x%x\n", 10055);
                      SetConnectionError(a1, 10055);
                      InsideSelect = 0;
                      ResponseFromServer = 90;
                      EnterCriticalSection(&ConnectionListLock);
                      GlobalReceiveHandlerThread = 0;
                      LeaveCriticalSection(&ConnectionListLock);
                      v8 = a4;
                      goto LABEL_106;
                    }
                  }
                  v8 = a4;
                }
                if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x200000) != 0 )
                  LDAPClientPrint(0x200000, "LdapWaitForResponseFromServer DrainWinsock returned 0x%x.\n", j);
                InsideSelect = 0;
                v28 = LdapAllBuffersToMessages(a1, v8);
              }
              EnterCriticalSection(&ConnectionListLock);
              GlobalReceiveHandlerThread = 0;
              LeaveCriticalSection(&ConnectionListLock);
              if ( v28 )
              {
                if ( !a6 && (v28 == a1 || *((int *)v28 + 150) > 0) )
                {
                  EnterCriticalSection((LPCRITICAL_SECTION)v28 + 14);
                  if ( *((_BYTE *)v28 + 553) == 16 && *((_BYTE *)v28 + 555) == 1 )
                  {
                    EnterCriticalSection((LPCRITICAL_SECTION)((char *)v28 + 512));
                    *((_BYTE *)v28 + 553) = 4;
                    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v28 + 512));
                    v41 = LdapAutoReconnect(v28);
                    if ( g_fTracingOn )
                    {
                      if ( g_fProviderEnabled && (g_ulTraceFlags & 0x100000) != 0 )
                        LDAPClientPrint(
                          0x100000,
                          "LdapWaitForResponseFromServer: reconnect returned 0x%x for 0x%x\n",
                          v41,
                          (_DWORD)v28);
                    }
                  }
                  LeaveCriticalSection((LPCRITICAL_SECTION)v28 + 14);
                  v8 = a4;
                }
                EnterCriticalSection((LPCRITICAL_SECTION)((char *)v28 + 512));
                --*(_DWORD *)v28;
                if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 4) != 0 )
                  LDAPClientPrint(4, "LDAP deref conn 0x%x, new count = 0x%x\n", (_DWORD)v28, *(_DWORD *)v28);
                v42 = (struct _RTL_CRITICAL_SECTION *)((char *)v28 + 512);
                if ( *(_DWORD *)v28 )
                {
                  LeaveCriticalSection(v42);
                }
                else
                {
                  LeaveCriticalSection(v42);
                  DereferenceLdapConnection2((__int64)v28, 1);
                }
              }
              v9 = v60;
              goto LABEL_42;
            }
            _InterlockedIncrement(&GlobalWaitersCount);
            if ( a1 && !a6 )
              _InterlockedIncrement((volatile signed __int32 *)a1 + 150);
            LeaveCriticalSection(&ConnectionListLock);
            v13 = 0;
            if ( v9 - 1 > 0xFFFFFFFD )
              v44 = v9;
            else
              v44 = v9 + TickCount - LdapGetTickCount();
            if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400) != 0 )
              LDAPClientPrint(1024, "LdapWaitForResponseFromServer waiting for request 0x%x.\n", (_DWORD)v10);
            v24 = WaitForSingleObjectEx(*(HANDLE *)(v14 + 24), v44, 0);
            _InterlockedDecrement(&GlobalWaitersCount);
            if ( a1 && !a6 )
              goto LABEL_193;
LABEL_40:
            if ( v24 == -1 )
              GetLastError();
LABEL_42:
            if ( !v6 )
              goto LABEL_105;
            if ( *(_BYTE *)(v14 + 40) == 1 )
            {
              ResetEvent(*(HANDLE *)(v14 + 24));
              *(_BYTE *)(v14 + 40) = 0;
              LdapGetResponseFromServer(a1, v10, v8, v6);
            }
            if ( *v6 )
            {
LABEL_105:
              ResponseFromServer = 0;
              goto LABEL_106;
            }
            if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x100000) != 0 )
              LDAPClientPrint(
                0x100000,
                "LdapWaitForResponseFromServer: no message found for 0x%x. retrying!\n",
                (_DWORD)a1);
            if ( a1 && *((_BYTE *)a1 + 554) == 1 )
            {
              if ( *((_BYTE *)a1 + 555) )
              {
                ResponseFromServer = 52;
              }
              else
              {
                if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x80u) != 0LL )
                {
                  CurrentThreadId = GetCurrentThreadId();
                  LDAPClientPrint(
                    128,
                    "ldapWaitForResponse thread 0x%x has connection 0x%x as down.\n",
                    CurrentThreadId,
                    (_DWORD)a1);
                }
                ResponseFromServer = 81;
              }
              goto LABEL_57;
            }
            if ( GlobalLdapShuttingDown == 1 || a1 && *((_BYTE *)a1 + 552) != 1 )
              goto LABEL_132;
            if ( !GlobalCountOfOpenRequests )
            {
              if ( v8 == 2 )
              {
                LdapGetResponseFromServer(a1, v10, 2u, v6);
              }
              else
              {
                ResponseFromServer = LdapGetResponseFromServer(a1, v10, v50, v6);
                if ( *v6 )
                  goto LABEL_106;
              }
              if ( v10 && *((_BYTE *)v10 + 184) )
LABEL_132:
                ResponseFromServer = 88;
              else
LABEL_56:
                ResponseFromServer = 85;
LABEL_57:
              SetConnectionError(a1, ResponseFromServer);
              v13 = 0;
              goto LABEL_106;
            }
            v55 = 0;
            GetSystemTimeAsFileTime(&v55);
            if ( !v9 || v9 != -1 && *(unsigned __int64 *)&v55 / 0x2710 - TickCount >= v9 )
            {
              if ( v49 != 1 || v52 >= *((_DWORD *)a1 + 268) )
                goto LABEL_55;
              ++v52;
              EnterCriticalSection((LPCRITICAL_SECTION)((char *)v10 + 48));
              v45 = (struct _RTL_CRITICAL_SECTION *)((char *)v10 + 48);
              if ( *((_BYTE *)v10 + 184) )
              {
                LeaveCriticalSection(v45);
                goto LABEL_55;
              }
              LeaveCriticalSection(v45);
              v46 = LdapSendCommand(a1, v10);
              if ( v46 )
              {
                if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x100000) != 0 )
                  LDAPClientPrint(
                    0x100000,
                    "LdapWaitForResponseFromServer connection 0x%x send with error of 0x%x.\n",
                    (_DWORD)a1,
                    v46);
LABEL_55:
                if ( v8 != 1 )
                {
                  ResponseFromServer = LdapGetResponseFromServer(a1, v10, v8, v6);
                  if ( !*v6 )
                    ResponseFromServer = 85;
                  goto LABEL_57;
                }
                goto LABEL_56;
              }
              if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x20000) != 0 )
                LDAPClientPrint(0x20000, "LdapWaitForResponseFromServer rewaiting for connection 0x%x\n", (_DWORD)a1);
              TickCount = LdapGetTickCount();
            }
          }
          else
          {
            if ( a6 )
            {
              ResponseFromServer = 81;
              goto LABEL_80;
            }
            v13 = 0;
            LeaveCriticalSection(&ConnectionListLock);
            ResponseFromServer = LdapConnect(a1, 0, 0);
            if ( ResponseFromServer )
              goto LABEL_106;
          }
        }
        _InterlockedIncrement(&GlobalWaitersCount);
        if ( a1 && !a6 )
          _InterlockedIncrement((volatile signed __int32 *)a1 + 150);
        LeaveCriticalSection(&ConnectionListLock);
        v13 = 0;
        if ( v9 - 1 <= 0xFFFFFFFD )
          v23 = v9 + TickCount - LdapGetTickCount();
        else
          v23 = v9;
        if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400) != 0 )
          LDAPClientPrint(1024, "LdapWaitForResponseFromServer waiting for request 0x%x.\n", (_DWORD)v10);
        v24 = WaitForSingleObjectEx(*(HANDLE *)(v14 + 24), v23, 0);
        _InterlockedDecrement(&GlobalWaitersCount);
        if ( !a1 || a6 )
          goto LABEL_40;
LABEL_193:
        _InterlockedDecrement((volatile signed __int32 *)a1 + 150);
        goto LABEL_40;
      }
    }
LABEL_80:
    if ( v13 )
    {
LABEL_126:
      v13 = 0;
      LeaveCriticalSection(&ConnectionListLock);
    }
    if ( v14 )
    {
LABEL_106:
      if ( *(_BYTE *)(v14 + 40) )
        CheckForWaiters(*(unsigned int *)(v14 + 32), 0, 0);
      LdapFreeMessageWaitStructure(v14);
      v14 = 0;
    }
    if ( !GlobalReceiveHandlerThread && GlobalWaitersCount > 0 )
    {
      EnterCriticalSection(&ConnectionListLock);
      if ( GlobalReceiveHandlerThread || GlobalWaitersCount <= 0 )
      {
        v13 = 0;
        LeaveCriticalSection(&ConnectionListLock);
      }
      else
      {
        LeaveCriticalSection(&ConnectionListLock);
        v13 = 0;
        LOBYTE(v32) = 1;
        CheckForWaiters(0, v32, 0);
      }
    }
    if ( ResponseFromServer || !v6 || !v10 || *((_BYTE *)v10 + 273) != 1 )
      break;
    v33 = CopyResultToCache(a1, *v6);
    *((_BYTE *)v10 + 273) = 0;
    v34 = *((_BYTE *)v10 + 260);
    v35 = (unsigned __int16 *)*((_QWORD *)v10 + 24);
    v36 = (unsigned __int16 **)*((_QWORD *)v10 + 31);
    v37 = SystemTimeAsFileTime;
    if ( v33 == 1 )
    {
      *(_BYTE *)SystemTimeAsFileTime.dwLowDateTime = 1;
      v38 = FabricateLdapResult(v10, a1, v35, v36, v34);
    }
    else
    {
      v39 = *((_DWORD *)v10 + 58);
      v48 = *((_DWORD *)v10 + 64);
      v47 = (unsigned __int16 *)*((_QWORD *)v10 + 30);
      *(_BYTE *)SystemTimeAsFileTime.dwLowDateTime = 0;
      v38 = SendLdapSearch(v10, a1, v35, v39, v47, v36, v48, v34, (struct CLdapBer **)v10 + 20, 0);
    }
    ResponseFromServer = v38;
    if ( v38 )
      break;
    ldap_msgfree(*v6);
    v12 = v50;
    i = (_BYTE *)v37;
    v9 = v60;
    *v6 = 0;
  }
  return ResponseFromServer;
}

```

## disassembly

```asm
0x180006d80  mov     [rsp+arg_18], r9d
0x180006d85  mov     [rsp+arg_10], r8d
0x180006d8a  mov     [rsp+arg_8], rdx
0x180006d8f  push    rbx
0x180006d90  push    rbp
0x180006d91  push    rsi
0x180006d92  push    rdi
0x180006d93  push    r13
0x180006d95  push    r15
0x180006d97  sub     rsp, 0A8h
0x180006d9e  mov     r15, [rsp+0D8h+arg_20]
0x180006da6  mov     rbp, rcx
0x180006da9  xor     ebx, ebx
0x180006dab  lea     rcx, [rsp+0D8h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180006db0  mov     qword ptr [rsp+0D8h+SystemTimeAsFileTime.dwLowDateTime], rbx
0x180006db5  mov     esi, r9d
0x180006db8  mov     edi, r8d
0x180006dbb  mov     r13, rdx
0x180006dbe  call    cs:__imp_GetSystemTimeAsFileTime
0x180006dc5  nop     dword ptr [rax+rax+00h]
0x180006dca  mov     eax, [rsp+0D8h+SystemTimeAsFileTime.dwLowDateTime]
0x180006dce  mov     ecx, [rsp+0D8h+SystemTimeAsFileTime.dwHighDateTime]
0x180006dd2  shl     rcx, 20h
0x180006dd6  or      rcx, rax
0x180006dd9  mov     rax, 346DC5D63886594Bh
0x180006de3  mul     rcx
0x180006de6  mov     rax, rdx
0x180006de9  shr     rax, 0Bh
0x180006ded  mov     [rsp+0D8h+var_70], rax
0x180006df2  test    r15, r15
0x180006df5  jz      short loc_180006DFA
0x180006df7  mov     [r15], rbx
0x180006dfa  cmp     esi, 2
0x180006dfd  mov     ecx, 1
0x180006e02  cmovnz  ecx, esi
0x180006e05  mov     [rsp+0D8h+var_84], ecx
0x180006e09  test    r13, r13
0x180006e0c  jnz     loc_1800073E3
0x180006e12  mov     [rsp+0D8h+var_68], ebx
0x180006e16  lea     rdx, [r13+112h]
0x180006e1d  mov     [rsp+0D8h+arg_0], r12
0x180006e25  mov     qword ptr [rsp+0D8h+SystemTimeAsFileTime.dwLowDateTime], rdx
0x180006e2a  mov     [rsp+0D8h+var_38], r14
0x180006e32  nop     dword ptr [rax+00h]
0x180006e36  nop     word ptr [rax+rax+00000000h]
0x180006e40  xor     r12b, r12b
0x180006e43  mov     [rsp+0D8h+var_88], bl
0x180006e47  mov     [rsp+0D8h+var_78], ebx
0x180006e4b  test    r15, r15
0x180006e4e  jz      short loc_180006EAF
0x180006e50  mov     r14, rbx
0x180006e53  test    r13, r13
0x180006e56  jz      short loc_180006E64
0x180006e58  mov     rax, rdx
0x180006e5b  cmp     byte ptr [rax], 0
0x180006e5e  jnz     loc_1800077CA
0x180006e64  mov     r8d, ecx; unsigned int
0x180006e67  mov     r9, r15; struct ldapmsg **
0x180006e6a  mov     rcx, rbp; struct ldap_connection *
0x180006e6d  mov     rdx, r13; struct ldap_request *
0x180006e70  call    ?LdapGetResponseFromServer@@YAKPEAUldap_connection@@PEAUldap_request@@KPEAPEAUldapmsg@@@Z; LdapGetResponseFromServer(ldap_connection *,ldap_request *,ulong,ldapmsg * *)
0x180006e75  cmp     qword ptr [r15], 0
0x180006e79  mov     ebx, eax
0x180006e7b  jnz     loc_18000732A
0x180006e81  test    r13, r13
0x180006e84  jz      short loc_180006EC0
0x180006e86  test    rbp, rbp
0x180006e89  jz      short loc_180006EC0
0x180006e8b  cmp     qword ptr [rbp+3C0h], 0FFFFFFFFFFFFFFFFh
0x180006e93  jz      short loc_180006EC0
0x180006e95  mov     [rsp+0D8h+var_88], 1
0x180006e9a  cmp     edi, 0FFFFFFFFh
0x180006e9d  jz      short loc_180006EA3
0x180006e9f  test    edi, edi
0x180006ea1  jnz     short loc_180006EC0
0x180006ea3  imul    edi, [rbp+434h], 3E8h
0x180006ead  jmp     short loc_180006EB9
0x180006eaf  mov     qword ptr [rsp+0D8h+SystemTimeAsFileTime.dwLowDateTime], rdx
0x180006eb4  mov     [rsp+0D8h+var_70], rax
0x180006eb9  mov     [rsp+0D8h+arg_10], edi
0x180006ec0  xor     r9d, r9d; lpName
0x180006ec3  xor     r8d, r8d; bInitialState
0x180006ec6  xor     edx, edx; bManualReset
0x180006ec8  xor     ecx, ecx; lpEventAttributes
0x180006eca  call    cs:__imp_CreateEventA
0x180006ed1  nop     dword ptr [rax+rax+00h]
0x180006ed6  mov     rbx, rax
0x180006ed9  test    rax, rax
0x180006edc  jz      loc_18000739E
0x180006ee2  mov     rcx, cs:LdapHeap; hHeap
0x180006ee9  mov     edx, 8; dwFlags
0x180006eee  mov     r8d, 38h ; '8'; dwBytes
0x180006ef4  call    cs:__imp_HeapAlloc
0x180006efb  nop     dword ptr [rax+rax+00h]
0x180006f00  mov     ecx, cs:g_fTracingOn
0x180006f06  mov     r14, rax
0x180006f09  test    ecx, ecx
0x180006f0b  jnz     loc_1800078D2
0x180006f11  mov     eax, cs:?LdapAllocatedHeap@@3KA; ulong LdapAllocatedHeap
0x180006f17  test    r14, r14
0x180006f1a  jz      short loc_180006F38
0x180006f1c  mov     dword ptr [r14], 6961574Ch
0x180006f23  mov     dword ptr [r14+4], 30h ; '0'
0x180006f2b  add     r14, 8
0x180006f2f  add     eax, 30h ; '0'
0x180006f32  mov     cs:?LdapAllocatedHeap@@3KA, eax; ulong LdapAllocatedHeap
0x180006f38  test    ecx, ecx
0x180006f3a  jnz     loc_180007A8F
0x180006f40  test    r14, r14
0x180006f43  jz      loc_180007ADA
0x180006f49  mov     rax, rbp
0x180006f4c  test    rbp, rbp
0x180006f4f  jz      short loc_180006F59
0x180006f51  mov     rcx, rbp
0x180006f54  call    ReferenceLdapConnection
0x180006f59  mov     [r14+10h], rax
0x180006f5d  test    r15, r15
0x180006f60  mov     eax, [rsp+0D8h+var_68]
0x180006f64  mov     rcx, rbx; hEvent
0x180006f67  mov     [r14+20h], eax
0x180006f6b  setz    al
0x180006f6e  mov     [r14+29h], al
0x180006f72  mov     [r14+18h], rbx
0x180006f76  mov     byte ptr [r14+28h], 0
0x180006f7b  mov     [r14+24h], esi
0x180006f7f  call    cs:__imp_ResetEvent
0x180006f86  nop     dword ptr [rax+rax+00h]
0x180006f8b  lea     rcx, WaiterLock; lpCriticalSection
0x180006f92  call    cs:__imp_EnterCriticalSection
0x180006f99  nop     dword ptr [rax+rax+00h]
0x180006f9e  mov     rax, cs:qword_180065B20
0x180006fa5  lea     rcx, GlobalListWaiters
0x180006fac  inc     cs:GlobalWaiterCount
0x180006fb2  mov     [r14], rcx
0x180006fb5  lea     rcx, WaiterLock; lpCriticalSection
0x180006fbc  mov     [r14+8], rax
0x180006fc0  mov     [rax], r14
0x180006fc3  mov     cs:qword_180065B20, r14
0x180006fca  call    cs:__imp_LeaveCriticalSection
0x180006fd1  nop     dword ptr [rax+rax+00h]
0x180006fd6  test    r15, r15
0x180006fd9  jnz     loc_18000737D
0x180006fdf  cmp     cs:GlobalCountOfOpenRequests, 0
0x180006fe6  jz      loc_180007B25
0x180006fec  test    r14, r14
0x180006fef  jz      loc_180007B5D
0x180006ff5  test    r12b, r12b
0x180006ff8  jnz     short loc_180007010
0x180006ffa  lea     rcx, ConnectionListLock; lpCriticalSection
0x180007001  call    cs:__imp_EnterCriticalSection
0x180007008  nop     dword ptr [rax+rax+00h]
0x18000700d  mov     r12b, 1
0x180007010  test    rbp, rbp
0x180007013  jnz     loc_1800072EA
0x180007019  test    r13, r13
0x18000701c  jnz     loc_1800072FC
0x180007022  cmp     cs:GlobalReceiveHandlerThread, 0
0x180007029  jz      loc_1800071A1
0x18000702f  lock inc cs:?GlobalWaitersCount@@3JA; long GlobalWaitersCount
0x180007036  test    rbp, rbp
0x180007039  jnz     loc_1800078B8
0x18000703f  lea     rcx, ConnectionListLock; lpCriticalSection
0x180007046  call    cs:__imp_LeaveCriticalSection
0x18000704d  nop     dword ptr [rax+rax+00h]
0x180007052  lea     eax, [rdi-1]
0x180007055  xor     r12b, r12b
0x180007058  cmp     eax, 0FFFFFFFDh
0x18000705b  jbe     loc_180007BA4
0x180007061  mov     ebx, edi
0x180007063  cmp     cs:g_fTracingOn, 0
0x18000706a  jnz     loc_180007BB6
0x180007070  mov     rcx, [r14+18h]; hHandle
0x180007074  xor     r8d, r8d; bAlertable
0x180007077  mov     edx, ebx; dwMilliseconds
0x180007079  call    cs:__imp_WaitForSingleObjectEx
0x180007080  nop     dword ptr [rax+rax+00h]
0x180007085  lock dec cs:?GlobalWaitersCount@@3JA; long GlobalWaitersCount
0x18000708c  test    rbp, rbp
0x18000708f  jnz     loc_180007BED
0x180007095  cmp     eax, 0FFFFFFFFh
0x180007098  jnz     short loc_1800070A6
0x18000709a  call    cs:__imp_GetLastError
0x1800070a1  nop     dword ptr [rax+rax+00h]
0x1800070a6  test    r15, r15
0x1800070a9  jz      loc_180007491
0x1800070af  cmp     byte ptr [r14+28h], 1
0x1800070b4  jnz     short loc_1800070DC
0x1800070b6  mov     rcx, [r14+18h]; hEvent
0x1800070ba  call    cs:__imp_ResetEvent
0x1800070c1  nop     dword ptr [rax+rax+00h]
0x1800070c6  mov     r9, r15; struct ldapmsg **
0x1800070c9  mov     byte ptr [r14+28h], 0
0x1800070ce  mov     r8d, esi; unsigned int
0x1800070d1  mov     rdx, r13; struct ldap_request *
0x1800070d4  mov     rcx, rbp; struct ldap_connection *
0x1800070d7  call    ?LdapGetResponseFromServer@@YAKPEAUldap_connection@@PEAUldap_request@@KPEAPEAUldapmsg@@@Z; LdapGetResponseFromServer(ldap_connection *,ldap_request *,ulong,ldapmsg * *)
0x1800070dc  cmp     qword ptr [r15], 0
0x1800070e0  jnz     loc_180007491
0x1800070e6  cmp     cs:g_fTracingOn, 0
0x1800070ed  jnz     loc_180007DD1
0x1800070f3  test    rbp, rbp
0x1800070f6  jnz     loc_18000742F
0x1800070fc  cmp     cs:GlobalLdapShuttingDown, 1
0x180007103  jz      loc_1800076A8
0x180007109  test    rbp, rbp
0x18000710c  jnz     loc_18000769B
0x180007112  cmp     cs:GlobalCountOfOpenRequests, 0
0x180007119  jz      loc_180007FA6
0x18000711f  lea     rcx, [rsp+0D8h+var_60]; lpSystemTimeAsFileTime
0x180007124  mov     qword ptr [rsp+0D8h+var_60.dwLowDateTime], 0
0x18000712d  call    cs:__imp_GetSystemTimeAsFileTime
0x180007134  nop     dword ptr [rax+rax+00h]
0x180007139  test    edi, edi
0x18000713b  jz      short loc_180007176
0x18000713d  cmp     edi, 0FFFFFFFFh
0x180007140  jz      loc_180006FF5
0x180007146  mov     eax, [rsp+0D8h+var_60.dwLowDateTime]
0x18000714a  mov     ecx, [rsp+0D8h+var_60.dwHighDateTime]
0x18000714e  shl     rcx, 20h
0x180007152  or      rcx, rax
0x180007155  mov     rax, 346DC5D63886594Bh
0x18000715f  mul     rcx
0x180007162  mov     eax, edi
0x180007164  shr     rdx, 0Bh
0x180007168  sub     rdx, [rsp+0D8h+var_70]
0x18000716d  cmp     rdx, rax
0x180007170  jb      loc_180006FF5
0x180007176  cmp     [rsp+0D8h+var_88], 1
0x18000717b  jz      loc_180007E08
0x180007181  cmp     esi, 1
0x180007184  jnz     loc_180007F82
0x18000718a  mov     ebx, 55h ; 'U'
0x18000718f  mov     edx, ebx
0x180007191  mov     rcx, rbp
0x180007194  call    SetConnectionError
0x180007199  xor     r12b, r12b
0x18000719c  jmp     loc_180007493
0x1800071a1  test    r15, r15
0x1800071a4  jnz     loc_1800075EB
0x1800071aa  test    rbp, rbp
0x1800071ad  jnz     loc_18000764E
0x1800071b3  cmp     cs:GlobalReceiveHandlerThread, 0
0x1800071ba  jnz     loc_180007D1A
0x1800071c0  lea     rcx, SelectLock2; lpCriticalSection
0x1800071c7  call    cs:__imp_EnterCriticalSection
0x1800071ce  nop     dword ptr [rax+rax+00h]
0x1800071d3  test    r13, r13
0x1800071d6  jnz     loc_180007700
0x1800071dc  lea     rcx, SelectLock2; lpCriticalSection
0x1800071e3  mov     cs:InsideSelect, 1
0x1800071ea  call    cs:__imp_LeaveCriticalSection
0x1800071f1  nop     dword ptr [rax+rax+00h]
0x1800071f6  call    cs:__imp_GetCurrentThreadId
0x1800071fd  nop     dword ptr [rax+rax+00h]
0x180007202  lea     rcx, ConnectionListLock; lpCriticalSection
0x180007209  mov     cs:GlobalReceiveHandlerThread, eax
0x18000720f  xor     r12b, r12b
0x180007212  call    cs:__imp_LeaveCriticalSection
0x180007219  nop     dword ptr [rax+rax+00h]
0x18000721e  test    r15, r15
0x180007221  jnz     loc_1800073F0
0x180007227  lea     eax, [rdi-1]
0x18000722a  cmp     eax, 0FFFFFFFDh
0x18000722d  jbe     loc_1800078A1
0x180007233  cmp     edi, 0FFFFFFFFh
0x180007236  jz      loc_180007746
0x18000723c  mov     r15d, [rsp+0D8h+arg_10]
0x180007244  xor     ebx, ebx
0x180007246  mov     r13, [rsp+0D8h+var_70]
0x18000724b  xor     esi, esi
0x18000724d  test    ebx, ebx
0x18000724f  jz      loc_1800073B3
0x180007255  mov     r15, [rsp+0D8h+arg_20]
0x18000725d  mov     r13, [rsp+0D8h+arg_8]
0x180007265  cmp     ebx, 102h
0x18000726b  jz      loc_18000751E
0x180007271  cmp     ebx, 2747h
0x180007277  jz      loc_18000783F
0x18000727d  mov     esi, [rsp+0D8h+arg_18]
0x180007284  cmp     cs:g_fTracingOn, 0
0x18000728b  jnz     loc_180007CD2
0x180007291  mov     edx, esi; unsigned int
0x180007293  mov     cs:InsideSelect, r12b
0x18000729a  mov     rcx, rbp; struct ldap_connection *
0x18000729d  call    ?LdapAllBuffersToMessages@@YAPEAUldap_connection@@PEAU1@K@Z; LdapAllBuffersToMessages(ldap_connection *,ulong)
0x1800072a2  mov     rdi, rax
0x1800072a5  lea     rcx, ConnectionListLock; lpCriticalSection
0x1800072ac  call    cs:__imp_EnterCriticalSection
0x1800072b3  nop     dword ptr [rax+rax+00h]
0x1800072b8  lea     rcx, ConnectionListLock; lpCriticalSection
0x1800072bf  mov     cs:GlobalReceiveHandlerThread, 0
0x1800072c9  call    cs:__imp_LeaveCriticalSection
0x1800072d0  nop     dword ptr [rax+rax+00h]
0x1800072d5  test    rdi, rdi
0x1800072d8  jnz     loc_180007919
0x1800072de  mov     edi, [rsp+0D8h+arg_10]
0x1800072e5  jmp     loc_1800070A6
0x1800072ea  cmp     byte ptr [rbp+228h], 1
0x1800072f1  jz      loc_180007019
0x1800072f7  jmp     loc_180007B49
  ... truncated ...
```
