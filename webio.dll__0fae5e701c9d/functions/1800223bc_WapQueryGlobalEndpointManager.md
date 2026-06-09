# WapQueryGlobalEndpointManager

- ea: `0x1800223bc`
- end: `0x18002252e`
- name: `WapQueryGlobalEndpointManager`
- size: `370`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180025860`

## callees

- `0x18001f410`
- `0x18001ff40`
- `0x1800223bc`
- `0x180023324`
- `0x18002e460`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002244c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002244c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180022520`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180022520`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800223e2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800223e2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180022416`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180022416`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180022485`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180022485`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800224c6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800224c6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800224e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800224e6`

## pseudocode

```c
__int64 __fastcall WapQueryGlobalEndpointManager(__int64 *a1)
{
  __int64 v1; // rbx
  __int64 v3; // rdi
  unsigned int EndpointManager; // esi
  __int64 v6; // rcx
  HANDLE EventW; // rdi
  __int64 v8; // r8
  __int64 v9; // r9
  __int64 v10; // rax
  __int64 v11; // rbp
  __int64 v12; // rbx
  __int64 v13; // [rsp+50h] [rbp+8h] BYREF

  v1 = 0;
  *a1 = 0;
  v13 = 0;
  AcquireSRWLockShared(&WaGlobalEpMgrLock);
  v3 = 0;
  if ( WaGlobalEpMgr )
  {
    _InterlockedIncrement((volatile signed __int32 *)(WaGlobalEpMgr + 28));
    v1 = WaGlobalEpMgr;
    v13 = WaGlobalEpMgr;
    v3 = WaGlobalEpMgr;
  }
  ReleaseSRWLockShared(&WaGlobalEpMgrLock);
  if ( v3 )
  {
    EndpointManager = 0;
    *a1 = v1;
  }
  else
  {
    EventW = CreateEventW(0, 0, 0, 0);
    if ( EventW )
    {
      EndpointManager = WaCreateEndpointManager(0, (__int64)EventW, v8, v9, (struct _FILETIME *)&v13);
      if ( EndpointManager )
        goto LABEL_13;
      AcquireSRWLockExclusive(&WaGlobalEpMgrLock);
      v10 = WaGlobalEpMgr;
      if ( WaGlobalEpMgr )
      {
        v11 = v13;
      }
      else
      {
        v10 = v13;
        v11 = 0;
        WaEpMgrTerminateEvent = EventW;
        EventW = 0;
        WaGlobalEpMgr = v13;
      }
      _InterlockedIncrement((volatile signed __int32 *)(v10 + 28));
      v12 = WaGlobalEpMgr;
      ReleaseSRWLockExclusive(&WaGlobalEpMgrLock);
      *a1 = v12;
      if ( v11 )
      {
        WaShutdownEndpointManager(v11);
        WaDereferenceEndpointManager(v11);
        WaitForSingleObject(EventW, 0xFFFFFFFF);
      }
      if ( EventW )
LABEL_13:
        CloseHandle(EventW);
    }
    else
    {
      return (unsigned int)WaGetLastError(v6);
    }
  }
  return EndpointManager;
}

```

## disassembly

```asm
0x1800223bc  mov     [rsp+arg_8], rbx
0x1800223c1  mov     [rsp+arg_10], rbp
0x1800223c6  push    rsi
0x1800223c7  push    rdi
0x1800223c8  push    r14
0x1800223ca  sub     rsp, 30h
0x1800223ce  xor     ebx, ebx
0x1800223d0  mov     r14, rcx
0x1800223d3  mov     [rcx], rbx
0x1800223d6  lea     rcx, WaGlobalEpMgrLock; SRWLock
0x1800223dd  mov     [rsp+48h+arg_0], rbx
0x1800223e2  call    cs:__imp_AcquireSRWLockShared
0x1800223e9  nop     dword ptr [rax+rax+00h]
0x1800223ee  mov     rax, cs:WaGlobalEpMgr
0x1800223f5  xor     edi, edi
0x1800223f7  test    rax, rax
0x1800223fa  jz      short loc_18002240F
0x1800223fc  lock inc dword ptr [rax+1Ch]
0x180022400  mov     rbx, cs:WaGlobalEpMgr
0x180022407  mov     [rsp+48h+arg_0], rbx
0x18002240c  mov     rdi, rbx
0x18002240f  lea     rcx, WaGlobalEpMgrLock; SRWLock
0x180022416  call    cs:__imp_ReleaseSRWLockShared
0x18002241d  nop     dword ptr [rax+rax+00h]
0x180022422  test    rdi, rdi
0x180022425  jz      short loc_180022442
0x180022427  xor     esi, esi
0x180022429  mov     [r14], rbx
0x18002242c  mov     rbx, [rsp+48h+arg_8]
0x180022431  mov     eax, esi
0x180022433  mov     rbp, [rsp+48h+arg_10]
0x180022438  add     rsp, 30h
0x18002243c  pop     r14
0x18002243e  pop     rdi
0x18002243f  pop     rsi
0x180022440  retn
0x180022442  xor     r9d, r9d; lpName
0x180022445  xor     r8d, r8d; bInitialState
0x180022448  xor     edx, edx; bManualReset
0x18002244a  xor     ecx, ecx; lpEventAttributes
0x18002244c  call    cs:__imp_CreateEventW
0x180022453  nop     dword ptr [rax+rax+00h]
0x180022458  mov     rdi, rax
0x18002245b  test    rax, rax
0x18002245e  jz      loc_1800224FE
0x180022464  lea     rax, [rsp+48h+arg_0]
0x180022469  mov     rdx, rdi
0x18002246c  xor     ecx, ecx
0x18002246e  mov     [rsp+48h+var_28], rax
0x180022473  call    WaCreateEndpointManager
0x180022478  mov     esi, eax
0x18002247a  test    eax, eax
0x18002247c  jnz     short loc_1800224E3
0x18002247e  lea     rcx, WaGlobalEpMgrLock; SRWLock
0x180022485  call    cs:__imp_AcquireSRWLockExclusive
0x18002248c  nop     dword ptr [rax+rax+00h]
0x180022491  mov     rax, cs:WaGlobalEpMgr
0x180022498  test    rax, rax
0x18002249b  jnz     short loc_1800224F7
0x18002249d  mov     rax, [rsp+48h+arg_0]
0x1800224a2  xor     ebp, ebp
0x1800224a4  mov     cs:WaEpMgrTerminateEvent, rdi
0x1800224ab  xor     edi, edi
0x1800224ad  mov     cs:WaGlobalEpMgr, rax
0x1800224b4  lock inc dword ptr [rax+1Ch]
0x1800224b8  mov     rbx, cs:WaGlobalEpMgr
0x1800224bf  lea     rcx, WaGlobalEpMgrLock; SRWLock
0x1800224c6  call    cs:__imp_ReleaseSRWLockExclusive
0x1800224cd  nop     dword ptr [rax+rax+00h]
0x1800224d2  mov     [r14], rbx
0x1800224d5  test    rbp, rbp
0x1800224d8  jnz     short loc_18002250A
0x1800224da  test    rdi, rdi
0x1800224dd  jz      loc_18002242C
0x1800224e3  mov     rcx, rdi; hObject
0x1800224e6  call    cs:__imp_CloseHandle
0x1800224ed  nop     dword ptr [rax+rax+00h]
0x1800224f2  jmp     loc_18002242C
0x1800224f7  mov     rbp, [rsp+48h+arg_0]
0x1800224fc  jmp     short loc_1800224B4
0x1800224fe  call    WaGetLastError
0x180022503  mov     esi, eax
0x180022505  jmp     loc_18002242C
0x18002250a  mov     rcx, rbp
0x18002250d  call    WaShutdownEndpointManager
0x180022512  mov     rcx, rbp
0x180022515  call    WaDereferenceEndpointManager
0x18002251a  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18002251d  mov     rcx, rdi; hHandle
0x180022520  call    cs:__imp_WaitForSingleObject
0x180022527  nop     dword ptr [rax+rax+00h]
0x18002252c  jmp     short loc_1800224DA
```
