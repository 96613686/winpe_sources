# W3WP_HOST::ShutdownProcess(int)

- ea: `0x180006cd8`
- end: `0x180006e33`
- name: `?ShutdownProcess@W3WP_HOST@@QEAAXH@Z`
- size: `347`
- prototype: `void(W3WP_HOST *__hidden this, int)`
- caller_count: `3`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180003340`
- `0x180004750`
- `0x180004a40`

## callees

- `0x180001970`
- `0x180001fa8`
- `0x180002fd8`
- `0x180006cd8`
- `0x180008c60`
- `0x180009328`
- `0x180009548`
- `0x180009d60`
- `0x18000aea8`
- `0x18000c0a8`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180006d69`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180006d69`
- `iisutil!PuDbgPrint` at `0x180006d16`
- `iisutil!PuDbgPrint` at `0x180006dd8`
- `iisutil!PuDbgPrint` at `0x180006d16`
- `iisutil!PuDbgPrint` at `0x180006dd8`

## string_xrefs

- `0x180006d0f`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\w3wphost.cxx`
- `0x180006dbf`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\w3wphost.cxx`

## pseudocode

```c
void __fastcall W3WP_HOST::ShutdownProcess(W3WP_HOST *this, unsigned int a2)
{
  WP_RECYCLER *v4; // rcx
  HANDLE *v5; // rcx
  PRELOAD_MANAGER *v6; // rcx
  PROTOCOL_MANAGER_ENTRY **i; // rdx
  PROTOCOL_MANAGER_ENTRY **NextProtocolManagerEntry; // rax
  unsigned int v9; // edx
  PROTOCOL_MANAGER_ENTRY **v10; // rdi
  WP_IDLE_TIMER *v11; // rcx

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
  v5 = (HANDLE *)*((_QWORD *)this + 12);
  if ( v5 )
    WP_IDLE_TIMER::StopTimer(v5);
  v6 = (PRELOAD_MANAGER *)*((_QWORD *)this + 197);
  if ( v6 )
    PRELOAD_MANAGER::Terminate(v6);
  LISTENER_CHANNEL_LIST_MANAGER::StopAllRunningListenerChannels((W3WP_HOST *)((char *)this + 368), a2);
  _InterlockedExchange(&W3WP_HOST_WORKITEM::sm_ShutdownCalled, 1);
  while ( W3WP_HOST_WORKITEM::sm_OutstandingWorkItemCount )
    Sleep(0xC8u);
  for ( i = 0; ; i = v10 )
  {
    NextProtocolManagerEntry = PROTOCOL_MANAGER_LIST::GetNextProtocolManagerEntry((W3WP_HOST *)((char *)this + 320), i);
    v10 = NextProtocolManagerEntry;
    if ( !NextProtocolManagerEntry )
      break;
    PROTOCOL_MANAGER_ENTRY::ReleaseSecondaryInterfaces((PROTOCOL_MANAGER_ENTRY *)NextProtocolManagerEntry);
    if ( (*(int (__fastcall **)(PROTOCOL_MANAGER_ENTRY *, _QWORD))(*(_QWORD *)v10[32] + 32LL))(v10[32], a2) < 0
      && (g_dwDebugFlags & 3) != 0 )
    {
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\w3wphost.cxx",
        3255,
        "W3WP_HOST::ShutdownProcess",
        "Shutdown failed. Error 0x%x\n");
    }
  }
  if ( Source )
  {
    operator delete(Source);
    Source = 0;
  }
  v11 = (WP_IDLE_TIMER *)*((_QWORD *)this + 12);
  if ( v11 )
  {
    WP_IDLE_TIMER::`scalar deleting destructor'(v11, v9);
    *((_QWORD *)this + 12) = 0;
  }
  PROTOCOL_MANAGER_LIST::CleanupList((PROTOCOL_MANAGER_ENTRY **)this + 40);
}

```

## disassembly

```asm
0x180006cd8  push    rbx
0x180006cda  push    rbp
0x180006cdb  push    rsi
0x180006cdc  push    rdi
0x180006cdd  sub     rsp, 38h
0x180006ce1  test    byte ptr cs:g_dwDebugFlags, 3
0x180006ce8  mov     ebp, edx
0x180006cea  mov     rbx, rcx
0x180006ced  jz      short loc_180006D1C
0x180006cef  mov     rcx, cs:g_pDebug
0x180006cf6  lea     rax, aProcessModelSh; "Process Model Shutdown called\n"
0x180006cfd  lea     r9, aW3wpHostShutdo; "W3WP_HOST::ShutdownProcess"
0x180006d04  mov     [rsp+58h+var_38], rax
0x180006d09  mov     r8d, 0C66h
0x180006d0f  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180006d16  call    cs:__imp_PuDbgPrint
0x180006d1c  mov     rcx, [rbx+68h]; this
0x180006d20  test    rcx, rcx
0x180006d23  jz      short loc_180006D2A
0x180006d25  call    ?TerminateInstance@WP_RECYCLER@@QEAAXXZ; WP_RECYCLER::TerminateInstance(void)
0x180006d2a  mov     rcx, [rbx+60h]; this
0x180006d2e  test    rcx, rcx
0x180006d31  jz      short loc_180006D38
0x180006d33  call    ?StopTimer@WP_IDLE_TIMER@@QEAAXXZ; WP_IDLE_TIMER::StopTimer(void)
0x180006d38  mov     rcx, [rbx+628h]; this
0x180006d3f  test    rcx, rcx
0x180006d42  jz      short loc_180006D49
0x180006d44  call    ?Terminate@PRELOAD_MANAGER@@QEAAJXZ; PRELOAD_MANAGER::Terminate(void)
0x180006d49  lea     rcx, [rbx+170h]; this
0x180006d50  mov     edx, ebp; int
0x180006d52  call    ?StopAllRunningListenerChannels@LISTENER_CHANNEL_LIST_MANAGER@@QEAAXH@Z; LISTENER_CHANNEL_LIST_MANAGER::StopAllRunningListenerChannels(int)
0x180006d57  mov     eax, 1
0x180006d5c  xchg    eax, cs:?sm_ShutdownCalled@W3WP_HOST_WORKITEM@@0HA; int W3WP_HOST_WORKITEM::sm_ShutdownCalled
0x180006d62  jmp     short loc_180006D6F
0x180006d64  mov     ecx, 0C8h; dwMilliseconds
0x180006d69  call    cs:__imp_Sleep
0x180006d6f  cmp     cs:?sm_OutstandingWorkItemCount@W3WP_HOST_WORKITEM@@0JA, 0; long W3WP_HOST_WORKITEM::sm_OutstandingWorkItemCount
0x180006d76  jnz     short loc_180006D64
0x180006d78  lea     rsi, [rbx+140h]
0x180006d7f  xor     edx, edx
0x180006d81  jmp     short loc_180006DE1
0x180006d83  mov     rcx, rdi; this
0x180006d86  call    ?ReleaseSecondaryInterfaces@PROTOCOL_MANAGER_ENTRY@@QEAAXXZ; PROTOCOL_MANAGER_ENTRY::ReleaseSecondaryInterfaces(void)
0x180006d8b  mov     rcx, [rdi+100h]
0x180006d92  mov     rdx, [rcx]
0x180006d95  mov     rax, [rdx+20h]
0x180006d99  mov     edx, ebp
0x180006d9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006da0  test    eax, eax
0x180006da2  jns     short loc_180006DDE
0x180006da4  test    byte ptr cs:g_dwDebugFlags, 3
0x180006dab  jz      short loc_180006DDE
0x180006dad  mov     rcx, cs:g_pDebug
0x180006db4  lea     r9, aW3wpHostShutdo; "W3WP_HOST::ShutdownProcess"
0x180006dbb  mov     [rsp+58h+var_30], eax
0x180006dbf  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180006dc6  lea     rax, aShutdownFailed; "Shutdown failed. Error 0x%x\n"
0x180006dcd  mov     r8d, 0CB7h
0x180006dd3  mov     [rsp+58h+var_38], rax
0x180006dd8  call    cs:__imp_PuDbgPrint
0x180006dde  mov     rdx, rdi; struct PROTOCOL_MANAGER_ENTRY *
0x180006de1  mov     rcx, rsi; this
0x180006de4  call    ?GetNextProtocolManagerEntry@PROTOCOL_MANAGER_LIST@@QEAAPEAVPROTOCOL_MANAGER_ENTRY@@PEAV2@@Z; PROTOCOL_MANAGER_LIST::GetNextProtocolManagerEntry(PROTOCOL_MANAGER_ENTRY *)
0x180006de9  mov     rdi, rax
0x180006dec  test    rax, rax
0x180006def  jnz     short loc_180006D83
0x180006df1  mov     rcx, cs:Source; Block
0x180006df8  test    rcx, rcx
0x180006dfb  jz      short loc_180006E0D
0x180006dfd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180006e02  mov     cs:Source, 0
0x180006e0d  mov     rcx, [rbx+60h]; this
0x180006e11  test    rcx, rcx
0x180006e14  jz      short loc_180006E23
0x180006e16  call    ??_GWP_IDLE_TIMER@@QEAAPEAXI@Z; WP_IDLE_TIMER::`scalar deleting destructor'(uint)
0x180006e1b  mov     qword ptr [rbx+60h], 0
0x180006e23  mov     rcx, rsi; this
0x180006e26  add     rsp, 38h
0x180006e2a  pop     rdi
0x180006e2b  pop     rsi
0x180006e2c  pop     rbp
0x180006e2d  pop     rbx
0x180006e2e  jmp     ?CleanupList@PROTOCOL_MANAGER_LIST@@QEAAXXZ; PROTOCOL_MANAGER_LIST::CleanupList(void)
```
