# W3WP_HOST::ShutdownProcess(int)

- ea: `0x180007398`
- end: `0x180007505`
- name: `?ShutdownProcess@W3WP_HOST@@QEAAXH@Z`
- size: `365`
- prototype: `void __fastcall(W3WP_HOST *this, unsigned int)`
- caller_count: `3`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180003540`
- `0x180004b20`
- `0x180004e50`

## callees

- `0x1800019f0`
- `0x1800020d0`
- `0x1800031b0`
- `0x180007398`
- `0x180009640`
- `0x180009d94`
- `0x180009ff0`
- `0x18000a93c`
- `0x18000bc3c`
- `0x18000cf88`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000742f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000742f`
- `iisutil!PuDbgPrint` at `0x1800073d6`
- `iisutil!PuDbgPrint` at `0x1800074a4`
- `iisutil!PuDbgPrint` at `0x1800073d6`
- `iisutil!PuDbgPrint` at `0x1800074a4`

## string_xrefs

- `0x1800073cf`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\w3wphost.cxx`
- `0x18000748b`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\w3wphost.cxx`

## pseudocode

```c
void __fastcall W3WP_HOST::ShutdownProcess(W3WP_HOST *this, unsigned int a2)
{
  WP_RECYCLER *v4; // rcx
  WP_IDLE_TIMER *v5; // rcx
  PRELOAD_MANAGER *v6; // rcx
  struct PROTOCOL_MANAGER_ENTRY *i; // rdx
  int v8; // eax
  PROTOCOL_MANAGER_ENTRY *NextProtocolManagerEntry; // rax
  unsigned int v10; // edx
  PROTOCOL_MANAGER_ENTRY *v11; // rdi
  WP_IDLE_TIMER *v12; // rcx

  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\w3wphost.cxx",
      3174,
      "W3WP_HOST::ShutdownProcess",
      "Process Model Shutdown called\n");
  v4 = (WP_RECYCLER *)*((_QWORD *)this + 13);
  if ( v4 )
    WP_RECYCLER::TerminateInstance(v4);
  v5 = (WP_IDLE_TIMER *)*((_QWORD *)this + 12);
  if ( v5 )
    WP_IDLE_TIMER::StopTimer(v5);
  v6 = (PRELOAD_MANAGER *)*((_QWORD *)this + 197);
  if ( v6 )
    PRELOAD_MANAGER::Terminate(v6);
  LISTENER_CHANNEL_LIST_MANAGER::StopAllRunningListenerChannels((W3WP_HOST *)((char *)this + 368), a2);
  _InterlockedExchange(&W3WP_HOST_WORKITEM::sm_ShutdownCalled, 1);
  while ( W3WP_HOST_WORKITEM::sm_OutstandingWorkItemCount )
    Sleep(0xC8u);
  for ( i = 0; ; i = v11 )
  {
    NextProtocolManagerEntry = PROTOCOL_MANAGER_LIST::GetNextProtocolManagerEntry((W3WP_HOST *)((char *)this + 320), i);
    v11 = NextProtocolManagerEntry;
    if ( !NextProtocolManagerEntry )
      break;
    PROTOCOL_MANAGER_ENTRY::ReleaseSecondaryInterfaces(NextProtocolManagerEntry);
    v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)v11 + 32) + 32LL))(*((_QWORD *)v11 + 32), a2);
    if ( v8 < 0 && (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\w3wphost.cxx",
        3255,
        "W3WP_HOST::ShutdownProcess",
        "Shutdown failed. Error 0x%x\n",
        v8);
  }
  if ( Source )
  {
    operator delete(Source);
    Source = 0;
  }
  v12 = (WP_IDLE_TIMER *)*((_QWORD *)this + 12);
  if ( v12 )
  {
    WP_IDLE_TIMER::`scalar deleting destructor'(v12, v10);
    *((_QWORD *)this + 12) = 0;
  }
  PROTOCOL_MANAGER_LIST::CleanupList((W3WP_HOST *)((char *)this + 320));
}

```

## disassembly

```asm
0x180007398  push    rbx
0x18000739a  push    rbp
0x18000739b  push    rsi
0x18000739c  push    rdi
0x18000739d  sub     rsp, 38h
0x1800073a1  test    byte ptr cs:g_dwDebugFlags, 3
0x1800073a8  mov     ebp, edx
0x1800073aa  mov     rbx, rcx
0x1800073ad  jz      short loc_1800073E2
0x1800073af  mov     rcx, cs:g_pDebug
0x1800073b6  lea     rax, aProcessModelSh; "Process Model Shutdown called\n"
0x1800073bd  lea     r9, aW3wpHostShutdo; "W3WP_HOST::ShutdownProcess"
0x1800073c4  mov     [rsp+58h+var_38], rax
0x1800073c9  mov     r8d, 0C66h
0x1800073cf  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800073d6  call    cs:__imp_PuDbgPrint
0x1800073dd  nop     dword ptr [rax+rax+00h]
0x1800073e2  mov     rcx, [rbx+68h]; this
0x1800073e6  test    rcx, rcx
0x1800073e9  jz      short loc_1800073F0
0x1800073eb  call    ?TerminateInstance@WP_RECYCLER@@QEAAXXZ; WP_RECYCLER::TerminateInstance(void)
0x1800073f0  mov     rcx, [rbx+60h]; this
0x1800073f4  test    rcx, rcx
0x1800073f7  jz      short loc_1800073FE
0x1800073f9  call    ?StopTimer@WP_IDLE_TIMER@@QEAAXXZ; WP_IDLE_TIMER::StopTimer(void)
0x1800073fe  mov     rcx, [rbx+628h]; this
0x180007405  test    rcx, rcx
0x180007408  jz      short loc_18000740F
0x18000740a  call    ?Terminate@PRELOAD_MANAGER@@QEAAJXZ; PRELOAD_MANAGER::Terminate(void)
0x18000740f  lea     rcx, [rbx+170h]; this
0x180007416  mov     edx, ebp; int
0x180007418  call    ?StopAllRunningListenerChannels@LISTENER_CHANNEL_LIST_MANAGER@@QEAAXH@Z; LISTENER_CHANNEL_LIST_MANAGER::StopAllRunningListenerChannels(int)
0x18000741d  mov     eax, 1
0x180007422  xchg    eax, cs:?sm_ShutdownCalled@W3WP_HOST_WORKITEM@@0HA; int W3WP_HOST_WORKITEM::sm_ShutdownCalled
0x180007428  jmp     short loc_18000743B
0x18000742a  mov     ecx, 0C8h; dwMilliseconds
0x18000742f  call    cs:__imp_Sleep
0x180007436  nop     dword ptr [rax+rax+00h]
0x18000743b  cmp     cs:?sm_OutstandingWorkItemCount@W3WP_HOST_WORKITEM@@0JA, 0; long W3WP_HOST_WORKITEM::sm_OutstandingWorkItemCount
0x180007442  jnz     short loc_18000742A
0x180007444  lea     rsi, [rbx+140h]
0x18000744b  xor     edx, edx
0x18000744d  jmp     short loc_1800074B3
0x18000744f  mov     rcx, rdi; this
0x180007452  call    ?ReleaseSecondaryInterfaces@PROTOCOL_MANAGER_ENTRY@@QEAAXXZ; PROTOCOL_MANAGER_ENTRY::ReleaseSecondaryInterfaces(void)
0x180007457  mov     rcx, [rdi+100h]
0x18000745e  mov     rdx, [rcx]
0x180007461  mov     rax, [rdx+20h]
0x180007465  mov     edx, ebp
0x180007467  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000746c  test    eax, eax
0x18000746e  jns     short loc_1800074B0
0x180007470  test    byte ptr cs:g_dwDebugFlags, 3
0x180007477  jz      short loc_1800074B0
0x180007479  mov     rcx, cs:g_pDebug
0x180007480  lea     r9, aW3wpHostShutdo; "W3WP_HOST::ShutdownProcess"
0x180007487  mov     [rsp+58h+var_30], eax
0x18000748b  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180007492  lea     rax, aShutdownFailed; "Shutdown failed. Error 0x%x\n"
0x180007499  mov     r8d, 0CB7h
0x18000749f  mov     [rsp+58h+var_38], rax
0x1800074a4  call    cs:__imp_PuDbgPrint
0x1800074ab  nop     dword ptr [rax+rax+00h]
0x1800074b0  mov     rdx, rdi; struct PROTOCOL_MANAGER_ENTRY *
0x1800074b3  mov     rcx, rsi; this
0x1800074b6  call    ?GetNextProtocolManagerEntry@PROTOCOL_MANAGER_LIST@@QEAAPEAVPROTOCOL_MANAGER_ENTRY@@PEAV2@@Z; PROTOCOL_MANAGER_LIST::GetNextProtocolManagerEntry(PROTOCOL_MANAGER_ENTRY *)
0x1800074bb  mov     rdi, rax
0x1800074be  test    rax, rax
0x1800074c1  jnz     short loc_18000744F
0x1800074c3  mov     rcx, cs:Source; Block
0x1800074ca  test    rcx, rcx
0x1800074cd  jz      short loc_1800074DF
0x1800074cf  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800074d4  mov     cs:Source, 0
0x1800074df  mov     rcx, [rbx+60h]; this
0x1800074e3  test    rcx, rcx
0x1800074e6  jz      short loc_1800074F5
0x1800074e8  call    ??_GWP_IDLE_TIMER@@QEAAPEAXI@Z; WP_IDLE_TIMER::`scalar deleting destructor'(uint)
0x1800074ed  mov     qword ptr [rbx+60h], 0
0x1800074f5  mov     rcx, rsi; this
0x1800074f8  add     rsp, 38h
0x1800074fc  pop     rdi
0x1800074fd  pop     rsi
0x1800074fe  pop     rbp
0x1800074ff  pop     rbx
0x180007500  jmp     ?CleanupList@PROTOCOL_MANAGER_LIST@@QEAAXXZ; PROTOCOL_MANAGER_LIST::CleanupList(void)
```
