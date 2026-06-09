# P2pTerminate

- ea: `0x1800438c0`
- end: `0x180043980`
- name: `P2pTerminate`
- size: `192`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800435fc`

## callees

- `0x180042b64`
- `0x1800438c0`
- `0x180043988`
- `0x180043a00`
- `0x18006a070`
- `0x180098010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004393b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004393b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800438df`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800438df`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800438fe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800438fe`

## pseudocode

```c
void P2pTerminate()
{
  if ( P2pEnabled )
  {
    CleanupQueuedHashRequests();
    EnterCriticalSection(&P2pGlobalLock);
    if ( P2pThreadPool )
    {
      P2P_THREAD_POOL::Terminate(P2pThreadPool);
      P2pThreadPool = 0;
    }
    LeaveCriticalSection(&P2pGlobalLock);
    ((void (__fastcall *)(void *))qword_1800AE618)(P2pPeerDistHandle);
    P2pPeerDistHandle = 0;
    P2P_PEER_DIST_API::UnloadPeerDist((P2P_PEER_DIST_API *)&P2pPeerDist);
    DeleteCriticalSection(&P2pGlobalLock);
    P2pEnabled = 0;
    P2pIntegrationEnabled = 0;
    P2PDeleteHeaderList(&P2PHeaderListToCopy);
  }
}

```

## disassembly

```asm
0x1800438c0  sub     rsp, 28h
0x1800438c4  cmp     cs:?P2pEnabled@@3HA, 0; int P2pEnabled
0x1800438cb  jnz     short loc_1800438D3
0x1800438cd  add     rsp, 28h
0x1800438d1  retn
0x1800438d3  call    ?CleanupQueuedHashRequests@@YAXXZ; CleanupQueuedHashRequests(void)
0x1800438d8  lea     rcx, ?P2pGlobalLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800438df  call    cs:__imp_EnterCriticalSection
0x1800438e6  nop     dword ptr [rax+rax+00h]
0x1800438eb  mov     rcx, cs:?P2pThreadPool@@3PEAVP2P_THREAD_POOL@@EA; this
0x1800438f2  test    rcx, rcx
0x1800438f5  jnz     short loc_18004396B
0x1800438f7  lea     rcx, ?P2pGlobalLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800438fe  call    cs:__imp_LeaveCriticalSection
0x180043905  nop     dword ptr [rax+rax+00h]
0x18004390a  mov     rcx, cs:?P2pPeerDistHandle@@3PEAXEA; void * P2pPeerDistHandle
0x180043911  mov     rax, cs:qword_1800AE618
0x180043918  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004391d  lea     rcx, ?P2pPeerDist@@3VP2P_PEER_DIST_API@@A; this
0x180043924  mov     cs:?P2pPeerDistHandle@@3PEAXEA, 0; void * P2pPeerDistHandle
0x18004392f  call    ?UnloadPeerDist@P2P_PEER_DIST_API@@QEAAXXZ; P2P_PEER_DIST_API::UnloadPeerDist(void)
0x180043934  lea     rcx, ?P2pGlobalLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18004393b  call    cs:__imp_DeleteCriticalSection
0x180043942  nop     dword ptr [rax+rax+00h]
0x180043947  lea     rcx, ?P2PHeaderListToCopy@@3PEAPEADEA; char ***
0x18004394e  mov     cs:?P2pEnabled@@3HA, 0; int P2pEnabled
0x180043958  mov     cs:?P2pIntegrationEnabled@@3HA, 0; int P2pIntegrationEnabled
0x180043962  add     rsp, 28h
0x180043966  jmp     ?P2PDeleteHeaderList@@YAXAEAPEAPEAD@Z; P2PDeleteHeaderList(char * * &)
0x18004396b  call    ?Terminate@P2P_THREAD_POOL@@QEAAXXZ; P2P_THREAD_POOL::Terminate(void)
0x180043970  mov     cs:?P2pThreadPool@@3PEAVP2P_THREAD_POOL@@EA, 0; P2P_THREAD_POOL * P2pThreadPool
0x18004397b  jmp     loc_1800438F7
```
