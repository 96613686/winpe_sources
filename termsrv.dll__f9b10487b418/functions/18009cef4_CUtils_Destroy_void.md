# CUtils::Destroy(void)

- ea: `0x18009cef4`
- end: `0x18009d05e`
- name: `?Destroy@CUtils@@SAXXZ`
- size: `362`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180039ff0`
- `0x18009d4cc`

## callees

- `0x18000a210`
- `0x1800321d4`
- `0x18009cef4`

## import_xrefs

- `ntdll!RtlFreeSid` at `0x18009cf0a`
- `ntdll!RtlFreeSid` at `0x18009cf27`
- `ntdll!RtlFreeSid` at `0x18009cf44`
- `ntdll!RtlFreeSid` at `0x18009cf0a`
- `ntdll!RtlFreeSid` at `0x18009cf27`
- `ntdll!RtlFreeSid` at `0x18009cf44`
- `ntdll!RtlDeleteResource` at `0x18009cfdf`
- `ntdll!RtlDeleteResource` at `0x18009cfdf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d019`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d019`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009cf61`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009cf7e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009cf9b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009cfb8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009cf61`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009cf7e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009cf9b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009cfb8`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueEx` at `0x18009d00f`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueEx` at `0x18009d00f`

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
0x18009cef4  mov     [rsp+arg_0], rbx
0x18009cef9  push    rdi
0x18009cefa  sub     rsp, 20h
0x18009cefe  mov     rcx, cs:?pSystemSid@CUtils@@0PEAXEA; Sid
0x18009cf05  test    rcx, rcx
0x18009cf08  jz      short loc_18009CF1B
0x18009cf0a  call    cs:__imp_RtlFreeSid
0x18009cf10  mov     cs:?pSystemSid@CUtils@@0PEAXEA, 0; void * CUtils::pSystemSid
0x18009cf1b  mov     rcx, cs:?pAdminSid@CUtils@@0PEAXEA; Sid
0x18009cf22  test    rcx, rcx
0x18009cf25  jz      short loc_18009CF38
0x18009cf27  call    cs:__imp_RtlFreeSid
0x18009cf2d  mov     cs:?pAdminSid@CUtils@@0PEAXEA, 0; void * CUtils::pAdminSid
0x18009cf38  mov     rcx, cs:?pAnonymousSid@CUtils@@0PEAXEA; Sid
0x18009cf3f  test    rcx, rcx
0x18009cf42  jz      short loc_18009CF55
0x18009cf44  call    cs:__imp_RtlFreeSid
0x18009cf4a  mov     cs:?pAnonymousSid@CUtils@@0PEAXEA, 0; void * CUtils::pAnonymousSid
0x18009cf55  mov     rcx, cs:?pNetworkServiceSid@CUtils@@0PEAXEA; hMem
0x18009cf5c  test    rcx, rcx
0x18009cf5f  jz      short loc_18009CF72
0x18009cf61  call    cs:__imp_LocalFree
0x18009cf67  mov     cs:?pNetworkServiceSid@CUtils@@0PEAXEA, 0; void * CUtils::pNetworkServiceSid
0x18009cf72  mov     rcx, cs:?pRdsMsSid@CUtils@@0PEAXEA; hMem
0x18009cf79  test    rcx, rcx
0x18009cf7c  jz      short loc_18009CF8F
0x18009cf7e  call    cs:__imp_LocalFree
0x18009cf84  mov     cs:?pRdsMsSid@CUtils@@0PEAXEA, 0; void * CUtils::pRdsMsSid
0x18009cf8f  mov     rcx, cs:?pAppContainerSid@CUtils@@0PEAXEA; hMem
0x18009cf96  test    rcx, rcx
0x18009cf99  jz      short loc_18009CFAC
0x18009cf9b  call    cs:__imp_LocalFree
0x18009cfa1  mov     cs:?pAppContainerSid@CUtils@@0PEAXEA, 0; void * CUtils::pAppContainerSid
0x18009cfac  mov     rcx, cs:?pLPACCapabilitySid@CUtils@@0PEAXEA; hMem
0x18009cfb3  test    rcx, rcx
0x18009cfb6  jz      short loc_18009CFC9
0x18009cfb8  call    cs:__imp_LocalFree
0x18009cfbe  mov     cs:?pLPACCapabilitySid@CUtils@@0PEAXEA, 0; void * CUtils::pLPACCapabilitySid
0x18009cfc9  mov     rbx, cs:?g_pObjectTracker@@3PEAVCObjectTracker@@EA; CObjectTracker * g_pObjectTracker
0x18009cfd0  test    rbx, rbx
0x18009cfd3  jz      short loc_18009CFFF
0x18009cfd5  cmp     dword ptr [rbx+78h], 0
0x18009cfd9  jz      short loc_18009CFE5
0x18009cfdb  lea     rcx, [rbx+18h]; Resource
0x18009cfdf  call    cs:__imp_RtlDeleteResource
0x18009cfe5  mov     rcx, rbx; Block
0x18009cfe8  mov     dword ptr [rbx+78h], 0
0x18009cfef  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18009cff4  mov     cs:?g_pObjectTracker@@3PEAVCObjectTracker@@EA, 0; CObjectTracker * g_pObjectTracker
0x18009cfff  mov     rcx, cs:?g_OpsMonitorTimeQueue@COpsMonitorBase@@0PEAXEA; TimerQueue
0x18009d006  test    rcx, rcx
0x18009d009  jz      short loc_18009D053
0x18009d00b  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18009d00f  call    cs:__imp_DeleteTimerQueueEx
0x18009d015  test    eax, eax
0x18009d017  jnz     short loc_18009D048
0x18009d019  call    cs:__imp_GetLastError
0x18009d01f  test    eax, eax
0x18009d021  jle     short loc_18009D02B
0x18009d023  movzx   eax, ax
0x18009d026  or      eax, 80070000h
0x18009d02b  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 40h; ulong g_DebugTraceComponent
0x18009d032  jz      short loc_18009D048
0x18009d034  mov     r8d, eax
0x18009d037  lea     rdx, aCopsmonitorbas_0; "COpsMonitorBase::Destroy() failed with "...
0x18009d03e  mov     ecx, 2; int
0x18009d043  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18009d048  mov     cs:?g_OpsMonitorTimeQueue@COpsMonitorBase@@0PEAXEA, 0; void * COpsMonitorBase::g_OpsMonitorTimeQueue
0x18009d053  mov     rbx, [rsp+28h+arg_0]
0x18009d058  add     rsp, 20h
0x18009d05c  pop     rdi
0x18009d05d  retn
```
