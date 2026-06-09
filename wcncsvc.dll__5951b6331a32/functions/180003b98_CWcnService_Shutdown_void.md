# CWcnService::Shutdown(void)

- ea: `0x180003b98`
- end: `0x180003de4`
- name: `?Shutdown@CWcnService@@QEAAXXZ`
- size: `588`
- prototype: `void __fastcall(CWcnService *this, int)`
- caller_count: `3`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x180003288`
- `0x180004630`
- `0x1800054a0`

## callees

- `0x180003b98`
- `0x180004efc`
- `0x180004fb8`
- `0x18000f7a0`
- `0x18001103c`
- `0x18002c55c`
- `0x180038d7c`
- `0x180039dac`
- `0x18003b38c`
- `0x18003d378`
- `0x180053004`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003c5f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003c5f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003ca9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003ca9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x180003d68`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x180003d68`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x180003d5b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x180003d5b`

## pseudocode

```c
void __fastcall CWcnService::Shutdown(CWcnService *this, int a2)
{
  _BYTE *v3; // r10
  const char *Indent; // rax
  __int64 v5; // r10
  __int64 v6; // rax
  const char *v7; // rax
  __int64 v8; // r10
  __int64 v9; // rsi
  _QWORD *v10; // rax
  CWcnMessageSinkSession *v11; // rbx
  CWcnTransportManager *v12; // rsi
  const char *v13; // rax
  __int64 v14; // r10
  __int64 i; // rbx
  __int64 v16; // rcx
  __int64 v17; // rbx
  struct _TP_CLEANUP_GROUP *v18; // rcx
  const char *v19; // rax
  __int64 v20; // r10

  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v5 + 16), 21, WPP_ac811424b605344d9cc8b73f32b92b60_Traceguids, Indent);
    v3 = WPP_GLOBAL_Control;
  }
  v6 = *((_QWORD *)this + 7);
  if ( v6 )
  {
    *(_BYTE *)(v6 + 1400) = 0;
    _InterlockedExchange((volatile __int32 *)(*((_QWORD *)this + 7) + 1472LL), 0);
    CWcnEventManager::CompleteAllAsyncRpcCallsWithStatus((CWcnEventManager *)(*((_QWORD *)this + 7) + 1312LL), a2);
    v9 = *((_QWORD *)this + 7);
    byte_1800759B8 = 0;
    EnterCriticalSection((LPCRITICAL_SECTION)(v9 + 512));
    v10 = *(_QWORD **)(v9 + 504);
    if ( v10 )
    {
      while ( v10[1] )
      {
        v11 = *(CWcnMessageSinkSession **)(*(_QWORD *)*v10 + 16LL);
        CWcnMessageSinkSession::CancelPendingCall(v11);
        CWcnMessageSinkManager::RemoveSession((CWcnMessageSinkManager *)(v9 + 432), v11);
        v10 = *(_QWORD **)(v9 + 504);
      }
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(v9 + 512));
    CWcnRpcManager::Shutdown((CWcnRpcManager *)(*((_QWORD *)this + 7) + 408LL));
    CWcnTransportManager::SetAdvertiseMode(*((CWcnTransportManager **)this + 7), 0);
    v12 = (CWcnTransportManager *)*((_QWORD *)this + 7);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
    {
      v13 = GetIndent(1);
      WPP_SF_s(*(_QWORD *)(v14 + 16), 36, WPP_42bc82e352e534be2eccdc7b34788c4d_Traceguids, v13);
    }
    CWcnTransportManager::SetAdvertiseMode(v12, 0);
    for ( i = 0; i != 7; ++i )
    {
      v16 = *((_QWORD *)v12 + 2 * i + 2);
      if ( v16 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    }
    CWcnPeerCache::Shutdown((CWcnPeerCache *)(*((_QWORD *)this + 7) + 192LL));
    v17 = *((_QWORD *)this + 7);
    v18 = *(struct _TP_CLEANUP_GROUP **)(v17 + 400);
    if ( v18 )
    {
      CloseThreadpoolCleanupGroupMembers(v18, 1, 0);
      CloseThreadpoolCleanupGroup(*(PTP_CLEANUP_GROUP *)(v17 + 400));
      *(_QWORD *)(v17 + 400) = 0;
    }
    if ( *(_BYTE *)(v17 + 320) )
      *(_BYTE *)(v17 + 320) = 0;
    CWcnAttributeRules::Cleanup();
    McGenEventUnregister_EtwEventUnregister(WCN_ETW_EVENT_GUID_Context);
    McGenEventUnregister_EtwEventUnregister(WCN_ETW_SECURE_EVENT_GUID_Context);
    goto LABEL_24;
  }
  if ( v3 == (_BYTE *)&WPP_GLOBAL_Control )
    return;
  if ( v3[25] >= 3u )
  {
    v7 = GetIndent(0);
    WPP_SF_s(*(_QWORD *)(v8 + 16), 22, WPP_ac811424b605344d9cc8b73f32b92b60_Traceguids, v7);
LABEL_24:
    v3 = WPP_GLOBAL_Control;
  }
  if ( v3 != (_BYTE *)&WPP_GLOBAL_Control && v3[25] >= 6u )
  {
    v19 = GetIndent(-1);
    WPP_SF_s(*(_QWORD *)(v20 + 16), 24, WPP_ac811424b605344d9cc8b73f32b92b60_Traceguids, v19);
  }
}

```

## disassembly

```asm
0x180003b98  push    rbx
0x180003b9a  push    rbp
0x180003b9b  push    rsi
0x180003b9c  push    rdi
0x180003b9d  push    r15
0x180003b9f  sub     rsp, 20h
0x180003ba3  mov     rdi, rcx
0x180003ba6  mov     r10, cs:WPP_GLOBAL_Control
0x180003bad  lea     r15, WPP_GLOBAL_Control
0x180003bb4  cmp     r10, r15
0x180003bb7  jz      short loc_180003BE9
0x180003bb9  cmp     byte ptr [r10+19h], 6
0x180003bbe  jb      short loc_180003BE9
0x180003bc0  mov     ecx, 1; int
0x180003bc5  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180003bca  mov     rcx, [r10+10h]
0x180003bce  lea     r8, WPP_ac811424b605344d9cc8b73f32b92b60_Traceguids
0x180003bd5  mov     edx, 15h
0x180003bda  mov     r9, rax
0x180003bdd  call    WPP_SF_s
0x180003be2  mov     r10, cs:WPP_GLOBAL_Control
0x180003be9  mov     rax, [rdi+38h]
0x180003bed  test    rax, rax
0x180003bf0  jnz     short loc_180003C2A
0x180003bf2  cmp     r10, r15
0x180003bf5  jz      loc_180003DD9
0x180003bfb  cmp     byte ptr [r10+19h], 3
0x180003c00  jb      loc_180003DAD
0x180003c06  xor     ecx, ecx; int
0x180003c08  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180003c0d  mov     rcx, [r10+10h]
0x180003c11  lea     r8, WPP_ac811424b605344d9cc8b73f32b92b60_Traceguids
0x180003c18  mov     edx, 16h
0x180003c1d  mov     r9, rax
0x180003c20  call    WPP_SF_s
0x180003c25  jmp     loc_180003DA6
0x180003c2a  mov     byte ptr [rax+578h], 0
0x180003c31  xor     eax, eax
0x180003c33  mov     rcx, [rdi+38h]
0x180003c37  xchg    eax, [rcx+5C0h]
0x180003c3d  mov     rcx, [rdi+38h]
0x180003c41  add     rcx, 520h; this
0x180003c48  call    ?CompleteAllAsyncRpcCallsWithStatus@CWcnEventManager@@QEAAXJ@Z; CWcnEventManager::CompleteAllAsyncRpcCallsWithStatus(long)
0x180003c4d  mov     rsi, [rdi+38h]
0x180003c51  mov     cs:byte_1800759B8, 0
0x180003c58  lea     rcx, [rsi+200h]; lpCriticalSection
0x180003c5f  call    cs:__imp_EnterCriticalSection
0x180003c65  mov     rax, [rsi+1F8h]
0x180003c6c  test    rax, rax
0x180003c6f  jz      short loc_180003CA2
0x180003c71  jmp     short loc_180003C9B
0x180003c73  mov     rax, [rax]
0x180003c76  mov     rdx, [rax]
0x180003c79  mov     rbx, [rdx+10h]
0x180003c7d  mov     rcx, rbx; this
0x180003c80  call    ?CancelPendingCall@CWcnMessageSinkSession@@QEAAXXZ; CWcnMessageSinkSession::CancelPendingCall(void)
0x180003c85  mov     rdx, rbx; struct CWcnMessageSinkSession *
0x180003c88  lea     rcx, [rsi+1B0h]; this
0x180003c8f  call    ?RemoveSession@CWcnMessageSinkManager@@QEAAXPEAVCWcnMessageSinkSession@@@Z; CWcnMessageSinkManager::RemoveSession(CWcnMessageSinkSession *)
0x180003c94  mov     rax, [rsi+1F8h]
0x180003c9b  cmp     qword ptr [rax+8], 0
0x180003ca0  ja      short loc_180003C73
0x180003ca2  lea     rcx, [rsi+200h]; lpCriticalSection
0x180003ca9  call    cs:__imp_LeaveCriticalSection
0x180003caf  mov     rcx, [rdi+38h]
0x180003cb3  add     rcx, 198h; this
0x180003cba  call    ?Shutdown@CWcnRpcManager@@QEAAXXZ; CWcnRpcManager::Shutdown(void)
0x180003cbf  mov     rcx, [rdi+38h]; this
0x180003cc3  xor     edx, edx; bool
0x180003cc5  call    ?SetAdvertiseMode@CWcnTransportManager@@QEAAJ_N@Z; CWcnTransportManager::SetAdvertiseMode(bool)
0x180003cca  mov     rsi, [rdi+38h]
0x180003cce  mov     r10, cs:WPP_GLOBAL_Control
0x180003cd5  cmp     r10, r15
0x180003cd8  jz      short loc_180003D03
0x180003cda  cmp     byte ptr [r10+19h], 6
0x180003cdf  jb      short loc_180003D03
0x180003ce1  mov     ecx, 1; int
0x180003ce6  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180003ceb  mov     rcx, [r10+10h]
0x180003cef  lea     r8, WPP_42bc82e352e534be2eccdc7b34788c4d_Traceguids
0x180003cf6  mov     edx, 24h ; '$'
0x180003cfb  mov     r9, rax
0x180003cfe  call    WPP_SF_s
0x180003d03  xor     edx, edx; bool
0x180003d05  mov     rcx, rsi; this
0x180003d08  call    ?SetAdvertiseMode@CWcnTransportManager@@QEAAJ_N@Z; CWcnTransportManager::SetAdvertiseMode(bool)
0x180003d0d  xor     ebx, ebx
0x180003d0f  lea     rax, [rbx+1]
0x180003d13  add     rax, rax
0x180003d16  mov     rcx, [rsi+rax*8]
0x180003d1a  test    rcx, rcx
0x180003d1d  jz      short loc_180003D2B
0x180003d1f  mov     rax, [rcx]
0x180003d22  mov     rax, [rax+10h]
0x180003d26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d2b  inc     rbx
0x180003d2e  cmp     rbx, 7
0x180003d32  jnz     short loc_180003D0F
0x180003d34  mov     rcx, [rdi+38h]
0x180003d38  add     rcx, 0C0h; this
0x180003d3f  call    ?Shutdown@CWcnPeerCache@@QEAAXXZ; CWcnPeerCache::Shutdown(void)
0x180003d44  mov     rbx, [rdi+38h]
0x180003d48  mov     rcx, [rbx+190h]; ptpcg
0x180003d4f  test    rcx, rcx
0x180003d52  jz      short loc_180003D79
0x180003d54  xor     r8d, r8d; pvCleanupContext
0x180003d57  lea     edx, [r8+1]; fCancelPendingCallbacks
0x180003d5b  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x180003d61  mov     rcx, [rbx+190h]; ptpcg
0x180003d68  call    cs:__imp_CloseThreadpoolCleanupGroup
0x180003d6e  mov     qword ptr [rbx+190h], 0
0x180003d79  cmp     byte ptr [rbx+140h], 0
0x180003d80  jz      short loc_180003D89
0x180003d82  mov     byte ptr [rbx+140h], 0
0x180003d89  call    ?Cleanup@CWcnAttributeRules@@SAJXZ; CWcnAttributeRules::Cleanup(void)
0x180003d8e  lea     rcx, WCN_ETW_EVENT_GUID_Context
0x180003d95  call    McGenEventUnregister_EtwEventUnregister
0x180003d9a  lea     rcx, WCN_ETW_SECURE_EVENT_GUID_Context
0x180003da1  call    McGenEventUnregister_EtwEventUnregister
0x180003da6  mov     r10, cs:WPP_GLOBAL_Control
0x180003dad  cmp     r10, r15
0x180003db0  jz      short loc_180003DD9
0x180003db2  cmp     byte ptr [r10+19h], 6
0x180003db7  jb      short loc_180003DD9
0x180003db9  or      ecx, 0FFFFFFFFh; int
0x180003dbc  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180003dc1  mov     rcx, [r10+10h]
0x180003dc5  lea     r8, WPP_ac811424b605344d9cc8b73f32b92b60_Traceguids
0x180003dcc  mov     edx, 18h
0x180003dd1  mov     r9, rax
0x180003dd4  call    WPP_SF_s
0x180003dd9  add     rsp, 20h
0x180003ddd  pop     r15
0x180003ddf  pop     rdi
0x180003de0  pop     rsi
0x180003de1  pop     rbp
0x180003de2  pop     rbx
0x180003de3  retn
```
