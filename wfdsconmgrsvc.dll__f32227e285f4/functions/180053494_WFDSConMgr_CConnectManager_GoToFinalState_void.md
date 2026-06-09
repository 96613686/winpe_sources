# WFDSConMgr::CConnectManager::GoToFinalState(void)

- ea: `0x180053494`
- end: `0x180053640`
- name: `?GoToFinalState@CConnectManager@WFDSConMgr@@QEAAXXZ`
- size: `428`
- prototype: `void __fastcall(WFDSConMgr::CConnectManager *__hidden this)`
- caller_count: `5`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18005a200`
- `0x18005ad80`
- `0x18005b500`
- `0x18005b5f0`
- `0x18005be40`

## callees

- `0x180004c7c`
- `0x1800067d0`
- `0x180006c60`
- `0x180008a10`
- `0x18002e734`
- `0x180039fec`
- `0x18003a1dc`
- `0x18003a684`
- `0x1800409c8`
- `0x180053494`
- `0x18005c888`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005356d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005356d`

## string_xrefs

- `0x18005359a`: `WFD token not acquired, bad state for connection complete`
- `0x1800535b3`: `WFDSConMgr::CRemoteDevice::TrySetWfdSessionResourceTokenActive`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall WFDSConMgr::CConnectManager::GoToFinalState(WFDSConMgr::CConnectManager *this)
{
  RTL_SRWLOCK *v2; // rbx
  WFDSConMgr::CWFDNotifyMiracastIEHelper *Ptr; // rcx
  RTL_SRWLOCK *v4; // rbx
  PVOID v5; // rcx
  struct WFDSConMgr::CSessionStateMachine *StateMachine; // rax
  WFDSConMgr::CRemoteDevice *v7; // rcx
  struct WFDSConMgr::INotificationManager *NotificationManager; // rax
  PSRWLOCK SRWLock; // [rsp+30h] [rbp-28h] BYREF
  char v10; // [rsp+38h] [rbp-20h]
  _BYTE v11[24]; // [rsp+40h] [rbp-18h] BYREF

  WFDSConMgr::LockSentry<WFDSConMgr::ReadersWriterLock,0>::LockSentry<WFDSConMgr::ReadersWriterLock,0>(
    (__int64)v11,
    (RTL_SRWLOCK *)this + 2);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_qDD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      13,
      &WPP_66093130bb8b3f567dd99be85dcde00d_Traceguids,
      this,
      *((_DWORD *)this + 30),
      15);
  }
  if ( (unsigned int)(*((_DWORD *)this + 30) - 15) <= 4 )
    WFDSConMgr::CException::Throw(
      159,
      "WFDSConMgr::CConnectManager::GoToFinalState",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\connectmanager.cpp",
      186,
      L"Connect Manager is in a bad state to continue execution",
      this);
  *((_DWORD *)this + 30) = 15;
  v2 = (RTL_SRWLOCK *)*((_QWORD *)this + 16);
  WFDSConMgr::LockSentry<WFDSConMgr::ReadersWriterLock,1>::LockSentry<WFDSConMgr::ReadersWriterLock,1>(
    (__int64)&SRWLock,
    v2 + 6);
  Ptr = (WFDSConMgr::CWFDNotifyMiracastIEHelper *)v2[93].Ptr;
  if ( Ptr )
    WFDSConMgr::CWFDNotifyMiracastIEHelper::SetSessionAvailable(Ptr, 0);
  if ( v10 && SRWLock )
    ReleaseSRWLockShared(SRWLock);
  v4 = (RTL_SRWLOCK *)*((_QWORD *)this + 16);
  WFDSConMgr::LockSentry<WFDSConMgr::ReadersWriterLock,0>::LockSentry<WFDSConMgr::ReadersWriterLock,0>(
    (__int64)&SRWLock,
    v4 + 6);
  v5 = v4[116].Ptr;
  if ( !v5 )
    WFDSConMgr::CException::Throw(
      159,
      "WFDSConMgr::CRemoteDevice::TrySetWfdSessionResourceTokenActive",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\remotedevice.cpp",
      1,
      L"WFD token not acquired, bad state for connection complete",
      v4);
  (*(void (__fastcall **)(PVOID))(*(_QWORD *)v5 + 16LL))(v5);
  WFDSConMgr::LockSentry<WFDSConMgr::ReadersWriterLock,0>::Unlock(&SRWLock);
  StateMachine = WFDSConMgr::CRemoteDevice::GetStateMachine(*((WFDSConMgr::CRemoteDevice **)this + 16));
  if ( (unsigned __int8)WFDSConMgr::CSessionStateMachine::UpdateWFDState(StateMachine, 3)
    && ((unsigned int)WFDSConMgr::CRemoteDevice::GetDafProviderTypeForConnection(*((_QWORD *)this + 16)) != 2
     || *((_BYTE *)v7 + 393)) )
  {
    NotificationManager = WFDSConMgr::CRemoteDevice::GetNotificationManager(v7);
    (*(void (__fastcall **)(struct WFDSConMgr::INotificationManager *))(*(_QWORD *)NotificationManager + 16LL))(NotificationManager);
  }
  WFDSConMgr::LockSentry<WFDSConMgr::ReadersWriterLock,0>::Unlock(v11);
}

```

## disassembly

```asm
0x180053494  mov     [rsp+arg_0], rbx
0x180053499  push    rdi
0x18005349a  sub     rsp, 50h
0x18005349e  mov     rdi, rcx
0x1800534a1  lea     rdx, [rcx+10h]
0x1800534a5  lea     rcx, [rsp+58h+var_18]
0x1800534aa  call    ??0?$LockSentry@VReadersWriterLock@WFDSConMgr@@$0A@@WFDSConMgr@@QEAA@AEAVReadersWriterLock@1@@Z; WFDSConMgr::LockSentry<WFDSConMgr::ReadersWriterLock,0>::LockSentry<WFDSConMgr::ReadersWriterLock,0>(WFDSConMgr::ReadersWriterLock &)
0x1800534af  nop
0x1800534b0  lea     rax, WPP_GLOBAL_Control
0x1800534b7  mov     ebx, 0Fh
0x1800534bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800534c3  cmp     rcx, rax
0x1800534c6  jz      short loc_1800534F5
0x1800534c8  cmp     byte ptr [rcx+19h], 4
0x1800534cc  jb      short loc_1800534F5
0x1800534ce  test    byte ptr [rcx+1Ch], 1
0x1800534d2  jz      short loc_1800534F5
0x1800534d4  lea     edx, [rbx-2]
0x1800534d7  mov     dword ptr [rsp+58h+var_30], ebx
0x1800534db  mov     eax, [rdi+78h]
0x1800534de  mov     dword ptr [rsp+58h+var_38], eax
0x1800534e2  mov     r9, rdi
0x1800534e5  lea     r8, WPP_66093130bb8b3f567dd99be85dcde00d_Traceguids
0x1800534ec  mov     rcx, [rcx+10h]
0x1800534f0  call    WPP_SF_qDD
0x1800534f5  mov     eax, [rdi+78h]
0x1800534f8  sub     eax, ebx
0x1800534fa  cmp     eax, 4
0x1800534fd  ja      short loc_18005352F
0x1800534ff  mov     [rsp+58h+var_30], rdi; void *
0x180053504  lea     rax, aConnectManager_0; "Connect Manager is in a bad state to co"...
0x18005350b  mov     [rsp+58h+var_38], rax; unsigned __int16 *
0x180053510  mov     r9d, 0BAh; char
0x180053516  lea     r8, aOnecoreuapNetW_4; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x18005351d  lea     rdx, aWfdsconmgrCcon_5; "WFDSConMgr::CConnectManager::GoToFinalS"...
0x180053524  mov     ecx, 8007139Fh; char
0x180053529  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x18005352f  mov     [rdi+78h], ebx
0x180053532  mov     rbx, [rdi+80h]
0x180053539  lea     rdx, [rbx+30h]
0x18005353d  lea     rcx, [rsp+58h+SRWLock]
0x180053542  call    ??0?$LockSentry@VReadersWriterLock@WFDSConMgr@@$00@WFDSConMgr@@QEAA@AEAVReadersWriterLock@1@@Z; WFDSConMgr::LockSentry<WFDSConMgr::ReadersWriterLock,1>::LockSentry<WFDSConMgr::ReadersWriterLock,1>(WFDSConMgr::ReadersWriterLock &)
0x180053547  nop
0x180053548  mov     rcx, [rbx+2E8h]; this
0x18005354f  test    rcx, rcx
0x180053552  jz      short loc_18005355C
0x180053554  xor     edx, edx; bool
0x180053556  call    ?SetSessionAvailable@CWFDNotifyMiracastIEHelper@WFDSConMgr@@QEAAX_N@Z; WFDSConMgr::CWFDNotifyMiracastIEHelper::SetSessionAvailable(bool)
0x18005355b  nop
0x18005355c  cmp     [rsp+58h+var_20], 0
0x180053561  jz      short loc_180053573
0x180053563  mov     rcx, [rsp+58h+SRWLock]; SRWLock
0x180053568  test    rcx, rcx
0x18005356b  jz      short loc_180053573
0x18005356d  call    cs:__imp_ReleaseSRWLockShared
0x180053573  mov     rbx, [rdi+80h]
0x18005357a  lea     rdx, [rbx+30h]
0x18005357e  lea     rcx, [rsp+58h+SRWLock]
0x180053583  call    ??0?$LockSentry@VReadersWriterLock@WFDSConMgr@@$0A@@WFDSConMgr@@QEAA@AEAVReadersWriterLock@1@@Z; WFDSConMgr::LockSentry<WFDSConMgr::ReadersWriterLock,0>::LockSentry<WFDSConMgr::ReadersWriterLock,0>(WFDSConMgr::ReadersWriterLock &)
0x180053588  nop
0x180053589  mov     rcx, [rbx+3A0h]
0x180053590  test    rcx, rcx
0x180053593  jnz     short loc_1800535C5
0x180053595  mov     [rsp+58h+var_30], rbx; void *
0x18005359a  lea     rax, aWfdTokenNotAcq; "WFD token not acquired, bad state for c"...
0x1800535a1  mov     [rsp+58h+var_38], rax; unsigned __int16 *
0x1800535a6  mov     r9d, 201h; char
0x1800535ac  lea     r8, aOnecoreuapNetW_17; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x1800535b3  lea     rdx, aWfdsconmgrCrem_7; "WFDSConMgr::CRemoteDevice::TrySetWfdSes"...
0x1800535ba  mov     ecx, 8007139Fh; char
0x1800535bf  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x1800535c5  mov     rax, [rcx]
0x1800535c8  mov     rax, [rax+10h]
0x1800535cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800535d1  nop
0x1800535d2  lea     rcx, [rsp+58h+SRWLock]
0x1800535d7  call    ?Unlock@?$LockSentry@VReadersWriterLock@WFDSConMgr@@$0A@@WFDSConMgr@@QEAAXXZ; WFDSConMgr::LockSentry<WFDSConMgr::ReadersWriterLock,0>::Unlock(void)
0x1800535dc  mov     rcx, [rdi+80h]; this
0x1800535e3  call    ?GetStateMachine@CRemoteDevice@WFDSConMgr@@QEAAAEAVCSessionStateMachine@2@XZ; WFDSConMgr::CRemoteDevice::GetStateMachine(void)
0x1800535e8  mov     edx, 3
0x1800535ed  mov     rcx, rax
0x1800535f0  call    ?UpdateWFDState@CSessionStateMachine@WFDSConMgr@@QEAA_NW4_WFDSConMgrWFDStatus@@@Z; WFDSConMgr::CSessionStateMachine::UpdateWFDState(_WFDSConMgrWFDStatus)
0x1800535f5  test    al, al
0x1800535f7  jz      short loc_18005362B
0x1800535f9  mov     rcx, [rdi+80h]
0x180053600  call    ?GetDafProviderTypeForConnection@CRemoteDevice@WFDSConMgr@@QEBA?AW4DafProvider@2@XZ; WFDSConMgr::CRemoteDevice::GetDafProviderTypeForConnection(void)
0x180053605  cmp     eax, 2
0x180053608  jnz     short loc_180053613
0x18005360a  cmp     byte ptr [rcx+189h], 0
0x180053611  jz      short loc_18005362B
0x180053613  call    ?GetNotificationManager@CRemoteDevice@WFDSConMgr@@QEAAAEAVINotificationManager@2@XZ; WFDSConMgr::CRemoteDevice::GetNotificationManager(void)
0x180053618  mov     rdx, rax
0x18005361b  mov     rcx, [rax]
0x18005361e  mov     rax, [rcx+10h]
0x180053622  mov     rcx, rdx
0x180053625  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005362a  nop
0x18005362b  lea     rcx, [rsp+58h+var_18]
0x180053630  call    ?Unlock@?$LockSentry@VReadersWriterLock@WFDSConMgr@@$0A@@WFDSConMgr@@QEAAXXZ; WFDSConMgr::LockSentry<WFDSConMgr::ReadersWriterLock,0>::Unlock(void)
0x180053635  mov     rbx, [rsp+58h+arg_0]
0x18005363a  add     rsp, 50h
0x18005363e  pop     rdi
0x18005363f  retn
```
