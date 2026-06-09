# CUtils::Destroy(void)

- ea: `0x1800a12a8`
- end: `0x1800a144f`
- name: `?Destroy@CUtils@@SAXXZ`
- size: `423`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18003c0ec`
- `0x1800a235c`

## callees

- `0x180009940`
- `0x180033f44`
- `0x1800a12a8`

## import_xrefs

- `ntdll!RtlFreeSid` at `0x1800a12be`
- `ntdll!RtlFreeSid` at `0x1800a12e1`
- `ntdll!RtlFreeSid` at `0x1800a1304`
- `ntdll!RtlFreeSid` at `0x1800a12be`
- `ntdll!RtlFreeSid` at `0x1800a12e1`
- `ntdll!RtlFreeSid` at `0x1800a1304`
- `ntdll!RtlDeleteResource` at `0x1800a13bd`
- `ntdll!RtlDeleteResource` at `0x1800a13bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1403`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1403`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a1327`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a134a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a136d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a1390`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a1327`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a134a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a136d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a1390`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueEx` at `0x1800a13f3`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueEx` at `0x1800a13f3`

## pseudocode

```c
void CUtils::Destroy(void)
{
  _DWORD *v0; // rbx
  signed int LastError; // eax

  if ( CUtils::pSystemSid )
  {
    RtlFreeSid(CUtils::pSystemSid);
    CUtils::pSystemSid = 0;
  }
  if ( CUtils::pAdminSid )
  {
    RtlFreeSid(CUtils::pAdminSid);
    CUtils::pAdminSid = 0;
  }
  if ( CUtils::pAnonymousSid )
  {
    RtlFreeSid(CUtils::pAnonymousSid);
    CUtils::pAnonymousSid = 0;
  }
  if ( CUtils::pNetworkServiceSid )
  {
    LocalFree(CUtils::pNetworkServiceSid);
    CUtils::pNetworkServiceSid = 0;
  }
  if ( CUtils::pRdsMsSid )
  {
    LocalFree(CUtils::pRdsMsSid);
    CUtils::pRdsMsSid = 0;
  }
  if ( CUtils::pAppContainerSid )
  {
    LocalFree(CUtils::pAppContainerSid);
    CUtils::pAppContainerSid = 0;
  }
  if ( CUtils::pLPACCapabilitySid )
  {
    LocalFree(CUtils::pLPACCapabilitySid);
    CUtils::pLPACCapabilitySid = 0;
  }
  v0 = g_pObjectTracker;
  if ( g_pObjectTracker )
  {
    if ( *((_DWORD *)g_pObjectTracker + 30) )
      RtlDeleteResource((PRTL_RESOURCE)((char *)g_pObjectTracker + 24));
    v0[30] = 0;
    operator delete(v0);
    g_pObjectTracker = 0;
  }
  if ( COpsMonitorBase::g_OpsMonitorTimeQueue )
  {
    if ( !DeleteTimerQueueEx(COpsMonitorBase::g_OpsMonitorTimeQueue, (HANDLE)0xFFFFFFFFFFFFFFFFLL) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      if ( (g_DebugTraceComponent & 0x40) != 0 )
        _DbgPrintMessage(2, "COpsMonitorBase::Destroy() failed with 0x%08x", LastError);
    }
    COpsMonitorBase::g_OpsMonitorTimeQueue = 0;
  }
}

```

## disassembly

```asm
0x1800a12a8  mov     [rsp+arg_0], rbx
0x1800a12ad  push    rdi
0x1800a12ae  sub     rsp, 20h
0x1800a12b2  mov     rcx, cs:?pSystemSid@CUtils@@0PEAXEA; Sid
0x1800a12b9  test    rcx, rcx
0x1800a12bc  jz      short loc_1800A12D5
0x1800a12be  call    cs:__imp_RtlFreeSid
0x1800a12c5  nop     dword ptr [rax+rax+00h]
0x1800a12ca  mov     cs:?pSystemSid@CUtils@@0PEAXEA, 0; void * CUtils::pSystemSid
0x1800a12d5  mov     rcx, cs:?pAdminSid@CUtils@@0PEAXEA; Sid
0x1800a12dc  test    rcx, rcx
0x1800a12df  jz      short loc_1800A12F8
0x1800a12e1  call    cs:__imp_RtlFreeSid
0x1800a12e8  nop     dword ptr [rax+rax+00h]
0x1800a12ed  mov     cs:?pAdminSid@CUtils@@0PEAXEA, 0; void * CUtils::pAdminSid
0x1800a12f8  mov     rcx, cs:?pAnonymousSid@CUtils@@0PEAXEA; Sid
0x1800a12ff  test    rcx, rcx
0x1800a1302  jz      short loc_1800A131B
0x1800a1304  call    cs:__imp_RtlFreeSid
0x1800a130b  nop     dword ptr [rax+rax+00h]
0x1800a1310  mov     cs:?pAnonymousSid@CUtils@@0PEAXEA, 0; void * CUtils::pAnonymousSid
0x1800a131b  mov     rcx, cs:?pNetworkServiceSid@CUtils@@0PEAXEA; hMem
0x1800a1322  test    rcx, rcx
0x1800a1325  jz      short loc_1800A133E
0x1800a1327  call    cs:__imp_LocalFree
0x1800a132e  nop     dword ptr [rax+rax+00h]
0x1800a1333  mov     cs:?pNetworkServiceSid@CUtils@@0PEAXEA, 0; void * CUtils::pNetworkServiceSid
0x1800a133e  mov     rcx, cs:?pRdsMsSid@CUtils@@0PEAXEA; hMem
0x1800a1345  test    rcx, rcx
0x1800a1348  jz      short loc_1800A1361
0x1800a134a  call    cs:__imp_LocalFree
0x1800a1351  nop     dword ptr [rax+rax+00h]
0x1800a1356  mov     cs:?pRdsMsSid@CUtils@@0PEAXEA, 0; void * CUtils::pRdsMsSid
0x1800a1361  mov     rcx, cs:?pAppContainerSid@CUtils@@0PEAXEA; hMem
0x1800a1368  test    rcx, rcx
0x1800a136b  jz      short loc_1800A1384
0x1800a136d  call    cs:__imp_LocalFree
0x1800a1374  nop     dword ptr [rax+rax+00h]
0x1800a1379  mov     cs:?pAppContainerSid@CUtils@@0PEAXEA, 0; void * CUtils::pAppContainerSid
0x1800a1384  mov     rcx, cs:?pLPACCapabilitySid@CUtils@@0PEAXEA; hMem
0x1800a138b  test    rcx, rcx
0x1800a138e  jz      short loc_1800A13A7
0x1800a1390  call    cs:__imp_LocalFree
0x1800a1397  nop     dword ptr [rax+rax+00h]
0x1800a139c  mov     cs:?pLPACCapabilitySid@CUtils@@0PEAXEA, 0; void * CUtils::pLPACCapabilitySid
0x1800a13a7  mov     rbx, cs:?g_pObjectTracker@@3PEAVCObjectTracker@@EA; CObjectTracker * g_pObjectTracker
0x1800a13ae  test    rbx, rbx
0x1800a13b1  jz      short loc_1800A13E3
0x1800a13b3  cmp     dword ptr [rbx+78h], 0
0x1800a13b7  jz      short loc_1800A13C9
0x1800a13b9  lea     rcx, [rbx+18h]; Resource
0x1800a13bd  call    cs:__imp_RtlDeleteResource
0x1800a13c4  nop     dword ptr [rax+rax+00h]
0x1800a13c9  mov     rcx, rbx; Block
0x1800a13cc  mov     dword ptr [rbx+78h], 0
0x1800a13d3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800a13d8  mov     cs:?g_pObjectTracker@@3PEAVCObjectTracker@@EA, 0; CObjectTracker * g_pObjectTracker
0x1800a13e3  mov     rcx, cs:?g_OpsMonitorTimeQueue@COpsMonitorBase@@0PEAXEA; TimerQueue
0x1800a13ea  test    rcx, rcx
0x1800a13ed  jz      short loc_1800A1443
0x1800a13ef  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x1800a13f3  call    cs:__imp_DeleteTimerQueueEx
0x1800a13fa  nop     dword ptr [rax+rax+00h]
0x1800a13ff  test    eax, eax
0x1800a1401  jnz     short loc_1800A1438
0x1800a1403  call    cs:__imp_GetLastError
0x1800a140a  nop     dword ptr [rax+rax+00h]
0x1800a140f  test    eax, eax
0x1800a1411  jle     short loc_1800A141B
0x1800a1413  movzx   eax, ax
0x1800a1416  or      eax, 80070000h
0x1800a141b  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 40h; ulong g_DebugTraceComponent
0x1800a1422  jz      short loc_1800A1438
0x1800a1424  mov     r8d, eax
0x1800a1427  lea     rdx, aCopsmonitorbas_0; "COpsMonitorBase::Destroy() failed with "...
0x1800a142e  mov     ecx, 2; int
0x1800a1433  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800a1438  mov     cs:?g_OpsMonitorTimeQueue@COpsMonitorBase@@0PEAXEA, 0; void * COpsMonitorBase::g_OpsMonitorTimeQueue
0x1800a1443  mov     rbx, [rsp+28h+arg_0]
0x1800a1448  add     rsp, 20h
0x1800a144c  pop     rdi
0x1800a144d  retn
```
