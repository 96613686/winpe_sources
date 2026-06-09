# LegacyPowerEventRegistrationThread(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x140024ab0`
- end: `0x140024c22`
- name: `?LegacyPowerEventRegistrationThread@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `370`
- prototype: `void __fastcall(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_WORK *)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x140007960`
- `0x140019014`
- `0x14001c87c`
- `0x140020d84`
- `0x140024ab0`
- `0x140025830`
- `0x14002bf54`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140024b13`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140024b13`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140024ac6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140024ac6`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x140024ab9`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x140024ab9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140024acc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140024acc`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x140024b81`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x140024b81`

## pseudocode

```c
void __fastcall LegacyPowerEventRegistrationThread(struct _TP_CALLBACK_INSTANCE *a1, void *a2, struct _TP_WORK *a3)
{
  RTL_SRWLOCK *v3; // rbx
  __int64 v4; // rax
  __int64 v5; // rdi
  int v6; // ebp
  _DWORD *v7; // rsi
  int v8; // eax
  RTL_SRWLOCK **v9; // rsi
  _QWORD *v10; // rdx
  _QWORD *v11; // r8
  __int64 v12; // rax
  __int64 v13; // rcx
  _QWORD v14[7]; // [rsp+30h] [rbp-38h] BYREF
  char v15; // [rsp+88h] [rbp+20h] BYREF

  CallbackMayRunLong(a1);
  AcquireSRWLockExclusive(&g_LegacyPowerEventRegistrationLock);
  v3 = &g_LegacyPowerEventRegistrationLock;
  dword_1400BC638 = GetCurrentThreadId();
  v14[0] = &g_LegacyPowerEventRegistrationLock;
  while ( qword_1400BC650 )
  {
    v4 = g_PendingLegacyPowerEventRegistrations;
    v5 = *(_QWORD *)(g_PendingLegacyPowerEventRegistrations + 16);
    if ( v5 )
      _InterlockedIncrement((volatile signed __int32 *)(v5 + 12));
    v6 = *(_DWORD *)(v4 + 24);
    v7 = *(_DWORD **)(v4 + 32);
    if ( v3 )
    {
      LODWORD(v3[1].Ptr) = 0;
      ReleaseSRWLockExclusive(v3);
      v3 = 0;
      v14[0] = 0;
    }
    v8 = PowerRegisterLegacyEventNotification(v5, *(_QWORD *)(v5 + 56), v6 == 0);
    if ( v8
      && WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
    {
      WPP_SF_SLd(
        WPP_GLOBAL_Control->StubInfo,
        23,
        (unsigned int)WPP_3228a6eab32731dc224fad51c8996946_Traceguids,
        *(_QWORD *)(v5 + 56),
        v6,
        v8);
    }
    if ( v7 )
    {
      *v7 = 1;
      WakeByAddressAll(v7);
    }
    v9 = (RTL_SRWLOCK **)CScmLock::LockAutoExclusive(&g_LegacyPowerEventRegistrationLock, &v15);
    if ( v9 != v14 )
    {
      CScmSyncLockExclusive::InternalUnlock((CScmSyncLockExclusive *)v14);
      v3 = *v9;
      v14[0] = *v9;
      *v9 = 0;
    }
    CScmSyncLockExclusive::InternalUnlock((CScmSyncLockExclusive *)&v15);
    v10 = (_QWORD *)g_PendingLegacyPowerEventRegistrations;
    v11 = *(_QWORD **)(g_PendingLegacyPowerEventRegistrations + 8);
    v12 = *(_QWORD *)g_PendingLegacyPowerEventRegistrations;
    *v11 = *(_QWORD *)g_PendingLegacyPowerEventRegistrations;
    *(_QWORD *)(v12 + 8) = v11;
    utl::_ContainerBase<_LEGACY_POWER_EVENT_REGISTRATION_CONTEXT,utl::allocator<_LEGACY_POWER_EVENT_REGISTRATION_CONTEXT>>::_DeleteNode<utl::_DlistNode<_LEGACY_POWER_EVENT_REGISTRATION_CONTEXT>>(
      v13,
      v10);
    --qword_1400BC650;
    SmartPtrRef::Release((SmartPtrRef *)v5);
  }
  g_IsLegacyPowerEventRegistrationThreadRunning = 0;
  CScmSyncLockExclusive::InternalUnlock((CScmSyncLockExclusive *)v14);
}

```

## disassembly

```asm
0x140024ab0  push    rbx
0x140024ab2  push    rbp
0x140024ab3  push    rsi
0x140024ab4  push    rdi
0x140024ab5  sub     rsp, 48h
0x140024ab9  call    cs:__imp_CallbackMayRunLong
0x140024abf  lea     rcx, ?g_LegacyPowerEventRegistrationLock@@3VCScmLock@@A; SRWLock
0x140024ac6  call    cs:__imp_AcquireSRWLockExclusive
0x140024acc  call    cs:__imp_GetCurrentThreadId
0x140024ad2  lea     rbx, ?g_LegacyPowerEventRegistrationLock@@3VCScmLock@@A; CScmLock g_LegacyPowerEventRegistrationLock
0x140024ad9  mov     cs:dword_1400BC638, eax
0x140024adf  mov     [rsp+68h+var_38], rbx
0x140024ae4  jmp     loc_140024BF7
0x140024ae9  mov     rax, cs:?g_PendingLegacyPowerEventRegistrations@@3V?$list@U_LEGACY_POWER_EVENT_REGISTRATION_CONTEXT@@V?$allocator@U_LEGACY_POWER_EVENT_REGISTRATION_CONTEXT@@@utl@@@utl@@A; utl::list<_LEGACY_POWER_EVENT_REGISTRATION_CONTEXT,utl::allocator<_LEGACY_POWER_EVENT_REGISTRATION_CONTEXT>> g_PendingLegacyPowerEventRegistrations
0x140024af0  mov     rdi, [rax+10h]
0x140024af4  test    rdi, rdi
0x140024af7  jz      short loc_140024AFD
0x140024af9  lock inc dword ptr [rdi+0Ch]
0x140024afd  mov     ebp, [rax+18h]
0x140024b00  mov     rsi, [rax+20h]
0x140024b04  test    rbx, rbx
0x140024b07  jz      short loc_140024B20
0x140024b09  mov     rcx, rbx; SRWLock
0x140024b0c  mov     dword ptr [rbx+8], 0
0x140024b13  call    cs:__imp_ReleaseSRWLockExclusive
0x140024b19  xor     ebx, ebx
0x140024b1b  mov     [rsp+68h+var_38], rbx
0x140024b20  mov     rdx, [rdi+38h]
0x140024b24  xor     r8d, r8d
0x140024b27  test    ebp, ebp
0x140024b29  mov     rcx, rdi
0x140024b2c  setz    r8b
0x140024b30  call    PowerRegisterLegacyEventNotification
0x140024b35  test    eax, eax
0x140024b37  jz      short loc_140024B73
0x140024b39  mov     rcx, cs:WPP_GLOBAL_Control
0x140024b40  lea     rdx, WPP_GLOBAL_Control
0x140024b47  cmp     rcx, rdx
0x140024b4a  jz      short loc_140024B73
0x140024b4c  test    byte ptr [rcx+1Ch], 1
0x140024b50  jz      short loc_140024B73
0x140024b52  mov     r9, [rdi+38h]
0x140024b56  lea     r8, WPP_3228a6eab32731dc224fad51c8996946_Traceguids
0x140024b5d  mov     rcx, [rcx+10h]
0x140024b61  mov     edx, 17h
0x140024b66  mov     [rsp+68h+var_40], eax
0x140024b6a  mov     [rsp+68h+var_48], ebp
0x140024b6e  call    WPP_SF_SLd
0x140024b73  test    rsi, rsi
0x140024b76  jz      short loc_140024B87
0x140024b78  mov     rcx, rsi; Address
0x140024b7b  mov     dword ptr [rsi], 1
0x140024b81  call    cs:__imp_WakeByAddressAll
0x140024b87  lea     rdx, [rsp+68h+arg_18]
0x140024b8f  lea     rcx, ?g_LegacyPowerEventRegistrationLock@@3VCScmLock@@A; CScmLock g_LegacyPowerEventRegistrationLock
0x140024b96  call    ?LockAutoExclusive@CScmLock@@QEAA?AVCScmSyncLockExclusive@@XZ; CScmLock::LockAutoExclusive(void)
0x140024b9b  mov     rsi, rax
0x140024b9e  lea     rax, [rsp+68h+var_38]
0x140024ba3  cmp     rsi, rax
0x140024ba6  jz      short loc_140024BC1
0x140024ba8  lea     rcx, [rsp+68h+var_38]; this
0x140024bad  call    ?InternalUnlock@CScmSyncLockExclusive@@IEAAXXZ; CScmSyncLockExclusive::InternalUnlock(void)
0x140024bb2  mov     rbx, [rsi]
0x140024bb5  mov     [rsp+68h+var_38], rbx
0x140024bba  mov     qword ptr [rsi], 0
0x140024bc1  lea     rcx, [rsp+68h+arg_18]; this
0x140024bc9  call    ?InternalUnlock@CScmSyncLockExclusive@@IEAAXXZ; CScmSyncLockExclusive::InternalUnlock(void)
0x140024bce  mov     rdx, cs:?g_PendingLegacyPowerEventRegistrations@@3V?$list@U_LEGACY_POWER_EVENT_REGISTRATION_CONTEXT@@V?$allocator@U_LEGACY_POWER_EVENT_REGISTRATION_CONTEXT@@@utl@@@utl@@A; utl::list<_LEGACY_POWER_EVENT_REGISTRATION_CONTEXT,utl::allocator<_LEGACY_POWER_EVENT_REGISTRATION_CONTEXT>> g_PendingLegacyPowerEventRegistrations
0x140024bd5  mov     r8, [rdx+8]
0x140024bd9  mov     rax, [rdx]
0x140024bdc  mov     [r8], rax
0x140024bdf  mov     [rax+8], r8
0x140024be3  call    ??$_DeleteNode@U?$_DlistNode@U_LEGACY_POWER_EVENT_REGISTRATION_CONTEXT@@@utl@@@?$_ContainerBase@U_LEGACY_POWER_EVENT_REGISTRATION_CONTEXT@@V?$allocator@U_LEGACY_POWER_EVENT_REGISTRATION_CONTEXT@@@utl@@@utl@@IEAAXPEAU?$_DlistNode@U_LEGACY_POWER_EVENT_REGISTRATION_CONTEXT@@@1@@Z; utl::_ContainerBase<_LEGACY_POWER_EVENT_REGISTRATION_CONTEXT,utl::allocator<_LEGACY_POWER_EVENT_REGISTRATION_CONTEXT>>::_DeleteNode<utl::_DlistNode<_LEGACY_POWER_EVENT_REGISTRATION_CONTEXT>>(utl::_DlistNode<_LEGACY_POWER_EVENT_REGISTRATION_CONTEXT> *)
0x140024be8  dec     cs:qword_1400BC650
0x140024bef  mov     rcx, rdi; this
0x140024bf2  call    ?Release@SmartPtrRef@@QEAAJXZ; SmartPtrRef::Release(void)
0x140024bf7  cmp     cs:qword_1400BC650, 0
0x140024bff  jnz     loc_140024AE9
0x140024c05  lea     rcx, [rsp+68h+var_38]; this
0x140024c0a  mov     cs:?g_IsLegacyPowerEventRegistrationThreadRunning@@3HA, 0; int g_IsLegacyPowerEventRegistrationThreadRunning
0x140024c14  call    ?InternalUnlock@CScmSyncLockExclusive@@IEAAXXZ; CScmSyncLockExclusive::InternalUnlock(void)
0x140024c19  add     rsp, 48h
0x140024c1d  pop     rdi
0x140024c1e  pop     rsi
0x140024c1f  pop     rbp
0x140024c20  pop     rbx
0x140024c21  retn
```
