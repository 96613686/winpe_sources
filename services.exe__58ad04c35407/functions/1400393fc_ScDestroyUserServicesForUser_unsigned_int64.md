# ScDestroyUserServicesForUser(unsigned __int64)

- ea: `0x1400393fc`
- end: `0x140039902`
- name: `?ScDestroyUserServicesForUser@@YAX_K@Z`
- size: `1286`
- prototype: `void __fastcall(unsigned __int64)`
- caller_count: `3`
- callee_count: `23`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140029340`
- `0x140030e34`
- `0x1400707d0`

## callees

- `0x1400013f0`
- `0x140003310`
- `0x140003e54`
- `0x140004c58`
- `0x140004c98`
- `0x14000512c`
- `0x1400070d0`
- `0x140007130`
- `0x1400188fc`
- `0x14001c87c`
- `0x14001f99c`
- `0x14001f9c4`
- `0x140020cbc`
- `0x140020d84`
- `0x140020f3c`
- `0x1400222b4`
- `0x14002303c`
- `0x1400255a4`
- `0x14002a54c`
- `0x140038698`
- `0x1400393fc`
- `0x1400575b0`
- `0x140094020`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140039701`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140039701`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x14003947f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1400396cc`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x140039888`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x14003947f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1400396cc`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x140039888`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x140039491`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1400394a7`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1400398cb`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x140039491`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1400394a7`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1400398cb`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1400397a7`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1400397a7`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1400396fb`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1400396fb`
- `ntdll!RtlReleaseResource` at `0x14003961b`
- `ntdll!RtlReleaseResource` at `0x14003961b`
- `ntdll!RtlAcquireResourceShared` at `0x140039500`
- `ntdll!RtlAcquireResourceShared` at `0x140039500`

## string_xrefs

- `0x140039646`: `Service user Log off`

## pseudocode

```c
void __fastcall ScDestroyUserServicesForUser(CServiceRecord *a1)
{
  ULONGLONG TickCount64; // r14
  __int64 v3; // r8
  __int64 v4; // rcx
  CServiceRecord *v5; // rcx
  CServiceRecord *v6; // rbx
  __int64 v7; // rcx
  _QWORD *i; // rbx
  _DWORD *v9; // rcx
  void (__fastcall *v10)(_DWORD *, _QWORD, __int64, _QWORD, _QWORD, _DWORD, CServiceRecord **, _DWORD, _DWORD, _DWORD, const wchar_t *, _QWORD, _QWORD, int); // rax
  ULONGLONG v11; // rax
  _QWORD *j; // rbx
  __int64 v13; // rdi
  __int64 v14; // rdx
  int v15; // eax
  unsigned int v16; // eax
  __int64 v17; // r8
  PRPC_ASYNC_STATE v18; // rcx
  _QWORD *k; // rbx
  struct CWin32ServiceRecord *v20; // rdi
  DEFER_LIST *v21; // rcx
  ULONGLONG v22; // rax
  CServiceRecord **v23; // [rsp+20h] [rbp-89h]
  CServiceRecord *v24; // [rsp+80h] [rbp-29h] BYREF
  _QWORD v25[3]; // [rsp+88h] [rbp-21h] BYREF
  ULONGLONG v26; // [rsp+A0h] [rbp-9h] BYREF
  __int128 v27; // [rsp+A8h] [rbp-1h] BYREF
  __int64 v28; // [rsp+B8h] [rbp+Fh]
  GUID ActivityId; // [rsp+C0h] [rbp+17h] BYREF

  v25[2] = 0;
  v25[0] = v25;
  v25[1] = v25;
  ActivityId = 0;
  if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->UserInfo) & 0x100000) != 0 )
  {
    WPP_SF_q(WPP_GLOBAL_Control->StubInfo, 76, WPP_036c406685683e02631f01bfa4d71e7e_Traceguids, a1);
  }
  TickCount64 = GetTickCount64();
  EventActivityIdControl(5u, &ActivityId);
  EventActivityIdControl(1u, &g_ActivityId);
  if ( (unsigned int)dword_1400BA2A0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1400BA2A0, 0x200000000000LL, v3) )
  {
    v24 = a1;
    v23 = &v24;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>();
  }
  RtlAcquireResourceShared(&ScServiceRecordLock, 1u);
  CServiceDatabase::GetFirst(v4, &v24);
  while ( 1 )
  {
    v5 = v24;
    if ( !v24 )
      break;
    if ( (*((_DWORD *)v24 + 13) & 0x80000) != 0
      && (*((_DWORD *)v24 + 13) & 0x100000) == 0
      && (CServiceRecord *)(*(__int64 (__fastcall **)(CServiceRecord *))(*(_QWORD *)v24 + 80LL))(v24) == a1 )
    {
      if ( (unsigned __int8)utl::list<Microsoft::WRL::ComPtr<CServiceRecord>,utl::allocator<Microsoft::WRL::ComPtr<CServiceRecord>>>::push_back(
                              v25,
                              &v24) )
      {
        v6 = v24;
        CScmLock::LockAutoExclusive((char *)v24 + 312, &v26);
        CServiceRecord::SetStatusFlag(v6, 1u);
        if ( (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 160LL))(v7) )
        {
          if ( *(_QWORD *)((*(__int64 (__fastcall **)(CServiceRecord *))(*(_QWORD *)v6 + 160LL))(v6) + 96) )
            *(_BYTE *)(*(_QWORD *)((*(__int64 (__fastcall **)(CServiceRecord *))(*(_QWORD *)v6 + 160LL))(v6) + 96)
                     + 140LL) = 10;
        }
        CScmSyncLockExclusive::InternalUnlock((CScmSyncLockExclusive *)&v26);
      }
      else
      {
        v5 = (CServiceRecord *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        {
          WPP_SF_S(
            WPP_GLOBAL_Control->StubInfo,
            77,
            WPP_036c406685683e02631f01bfa4d71e7e_Traceguids,
            *((_QWORD *)v24 + 7));
        }
      }
    }
    CServiceDatabase::GetNext((__int64)v5, &v24);
  }
  Microsoft::WRL::ComPtr<CServiceRecord>::InternalRelease(&v24);
  RtlReleaseResource(&ScServiceRecordLock);
  for ( i = (_QWORD *)v25[0]; i != v25; i = (_QWORD *)*i )
  {
    v9 = (_DWORD *)i[2];
    if ( ((v9[21] - 2) & 0xFFFFFFFD) == 0 )
    {
      v10 = *(void (__fastcall **)(_DWORD *, _QWORD, __int64, _QWORD, _QWORD, _DWORD, CServiceRecord **, _DWORD, _DWORD, _DWORD, const wchar_t *, _QWORD, _QWORD, int))(*(_QWORD *)v9 + 64LL);
      LODWORD(v24) = 0;
      v10(v9, 0, 1, 0, 0, 0, &v24, 0, 0, 0, L"Service user Log off", 0, 0, 1);
    }
  }
  if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->UserInfo) & 0x100000) != 0 )
  {
    v11 = GetTickCount64();
    WPP_SF_q(WPP_GLOBAL_Control->StubInfo, 78, WPP_036c406685683e02631f01bfa4d71e7e_Traceguids, v11 - TickCount64);
  }
  RtlAcquireSRWLockExclusive(&g_TriggerRegistrationLock);
  GetCurrentThreadId();
  for ( j = (_QWORD *)v25[0]; j != v25; j = (_QWORD *)*j )
  {
    v13 = j[2];
    if ( (*(_DWORD *)(v13 + 52) & 0x400) != 0 )
    {
      v14 = *(_QWORD *)(v13 + 56);
      LODWORD(v23) = 32;
      v28 = 0;
      v27 = 0;
      v15 = ((__int64 (__fastcall *)(__int128 *, __int64, _QWORD, _QWORD, CServiceRecord **))g_pScExtFunctionPointers[10])(
              &v27,
              v14,
              0,
              0,
              v23);
      if ( v15
        && WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      {
        WPP_SF_Sd(
          WPP_GLOBAL_Control->StubInfo,
          79,
          (unsigned int)WPP_036c406685683e02631f01bfa4d71e7e_Traceguids,
          *(_QWORD *)(v13 + 56),
          v15);
      }
      CServiceRecord::ClearStatusFlag((CServiceRecord *)v13, 1024);
    }
  }
  RtlReleaseSRWLockExclusive(&g_TriggerRegistrationLock);
  v16 = ScWaitForUserServiceShutdown(v25);
  if ( !v16 )
    goto LABEL_42;
  v18 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control )
    goto LABEL_46;
  if ( (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 80, WPP_036c406685683e02631f01bfa4d71e7e_Traceguids, v16);
LABEL_42:
    v18 = WPP_GLOBAL_Control;
  }
  if ( v18 != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (HIDWORD(v18->UserInfo) & 0x100000) != 0 )
    WPP_SF_(v18->StubInfo, 81, WPP_036c406685683e02631f01bfa4d71e7e_Traceguids);
LABEL_46:
  for ( k = (_QWORD *)v25[0]; k != v25; k = (_QWORD *)*k )
  {
    v20 = (struct CWin32ServiceRecord *)k[2];
    ScRemoveService(v20, 0, 0);
    DEFER_LIST::Add(v21, v20);
  }
  if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->UserInfo) & 0x100000) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->StubInfo, 82, WPP_036c406685683e02631f01bfa4d71e7e_Traceguids);
  }
  if ( (unsigned int)dword_1400BA2A0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1400BA2A0, 0x400000000000LL, v17) )
  {
    v22 = GetTickCount64();
    v24 = a1;
    v26 = v22 - TickCount64;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>();
  }
  EventActivityIdControl(2u, &ActivityId);
  utl::list<Microsoft::WRL::ComPtr<CServiceRecord>,utl::allocator<Microsoft::WRL::ComPtr<CServiceRecord>>>::clear((__int64)v25);
}

```

## disassembly

```asm
0x1400393fc  mov     [rsp-8+arg_8], rbx
0x140039401  mov     [rsp-8+arg_10], rsi
0x140039406  push    rbp
0x140039407  push    rdi
0x140039408  push    r12
0x14003940a  push    r13
0x14003940c  push    r14
0x14003940e  lea     rbp, [rsp-37h]
0x140039413  sub     rsp, 0E0h
0x14003941a  mov     rax, cs:__security_cookie
0x140039421  xor     rax, rsp
0x140039424  mov     [rbp+57h+var_30], rax
0x140039428  lea     rax, [rbp+57h+var_78]
0x14003942c  mov     [rbp+57h+var_68], 0
0x140039434  mov     [rbp+57h+var_78], rax
0x140039438  xorps   xmm0, xmm0
0x14003943b  lea     rax, [rbp+57h+var_78]
0x14003943f  mov     rsi, rcx
0x140039442  mov     [rbp+57h+var_70], rax
0x140039446  movups  xmmword ptr [rbp+57h+ActivityId.Data1], xmm0
0x14003944a  mov     rcx, cs:WPP_GLOBAL_Control
0x140039451  lea     r13, WPP_GLOBAL_Control
0x140039458  mov     edi, 100000h
0x14003945d  cmp     rcx, r13
0x140039460  jz      short loc_14003947F
0x140039462  test    [rcx+1Ch], edi
0x140039465  jz      short loc_14003947F
0x140039467  mov     rcx, [rcx+10h]
0x14003946b  lea     r8, WPP_036c406685683e02631f01bfa4d71e7e_Traceguids
0x140039472  mov     edx, 4Ch ; 'L'
0x140039477  mov     r9, rsi
0x14003947a  call    WPP_SF_q
0x14003947f  call    cs:__imp_GetTickCount64
0x140039485  lea     rdx, [rbp+57h+ActivityId]; ActivityId
0x140039489  mov     ecx, 5; ControlCode
0x14003948e  mov     r14, rax
0x140039491  call    cs:__imp_EventActivityIdControl
0x140039497  mov     r12d, 1
0x14003949d  lea     rdx, ?g_ActivityId@@3U_GUID@@A; ActivityId
0x1400394a4  mov     ecx, r12d; ControlCode
0x1400394a7  call    cs:__imp_EventActivityIdControl
0x1400394ad  mov     ecx, cs:dword_1400BA2A0
0x1400394b3  cmp     ecx, 5
0x1400394b6  jbe     short loc_1400394F6
0x1400394b8  mov     rdx, 200000000000h
0x1400394c2  lea     rcx, dword_1400BA2A0
0x1400394c9  call    _tlgKeywordOn
0x1400394ce  test    al, al
0x1400394d0  jz      short loc_1400394F6
0x1400394d2  lea     rax, [rbp+57h+var_80]
0x1400394d6  mov     [rbp+57h+var_80], rsi
0x1400394da  lea     r9, [rbp+57h+ActivityId]
0x1400394de  mov     [rsp+100h+var_E0], rax
0x1400394e3  lea     r8, ?g_ActivityId@@3U_GUID@@A; _GUID g_ActivityId
0x1400394ea  lea     rdx, byte_1400AE953
0x1400394f1  call    ??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)
0x1400394f6  mov     dl, r12b; Wait
0x1400394f9  lea     rcx, ?ScServiceRecordLock@@3VCServiceRecordLock@@A; Resource
0x140039500  call    cs:__imp_RtlAcquireResourceShared
0x140039506  lea     rdx, [rbp+57h+var_80]
0x14003950a  call    ?GetFirst@CServiceDatabase@@QEAA?AV?$ComPtr@VCServiceRecord@@@WRL@Microsoft@@XZ; CServiceDatabase::GetFirst(void)
0x14003950f  mov     rcx, [rbp+57h+var_80]
0x140039513  test    rcx, rcx
0x140039516  jz      loc_14003960B
0x14003951c  mov     eax, [rcx+34h]
0x14003951f  bt      eax, 13h
0x140039523  jnb     loc_1400395FD
0x140039529  mov     eax, [rcx+34h]
0x14003952c  test    edi, eax
0x14003952e  jnz     loc_1400395FD
0x140039534  mov     rax, [rcx]
0x140039537  mov     rax, [rax+50h]
0x14003953b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140039540  cmp     rax, rsi
0x140039543  jnz     loc_1400395FD
0x140039549  lea     rdx, [rbp+57h+var_80]
0x14003954d  lea     rcx, [rbp+57h+var_78]
0x140039551  call    ?push_back@?$list@V?$ComPtr@VCServiceRecord@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VCServiceRecord@@@WRL@Microsoft@@@utl@@@utl@@QEAA_NAEBV?$ComPtr@VCServiceRecord@@@WRL@Microsoft@@@Z; utl::list<Microsoft::WRL::ComPtr<CServiceRecord>,utl::allocator<Microsoft::WRL::ComPtr<CServiceRecord>>>::push_back(Microsoft::WRL::ComPtr<CServiceRecord> const &)
0x140039556  test    al, al
0x140039558  jz      short loc_1400395CE
0x14003955a  mov     rbx, [rbp+57h+var_80]
0x14003955e  lea     rdx, [rbp+57h+var_60]
0x140039562  lea     rcx, [rbx+138h]
0x140039569  call    ?LockAutoExclusive@CScmLock@@QEAA?AVCScmSyncLockExclusive@@XZ; CScmLock::LockAutoExclusive(void)
0x14003956e  mov     edx, r12d; unsigned int
0x140039571  mov     rcx, rbx; this
0x140039574  call    ?SetStatusFlag@CServiceRecord@@QEAAXK@Z; CServiceRecord::SetStatusFlag(ulong)
0x140039579  mov     rax, [rbx]
0x14003957c  mov     rax, [rax+0A0h]
0x140039583  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140039588  test    rax, rax
0x14003958b  jz      short loc_1400395C3
0x14003958d  mov     rax, [rbx]
0x140039590  mov     rcx, rbx
0x140039593  mov     rax, [rax+0A0h]
0x14003959a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003959f  cmp     qword ptr [rax+60h], 0
0x1400395a4  jz      short loc_1400395C3
0x1400395a6  mov     rax, [rbx]
0x1400395a9  mov     rcx, rbx
0x1400395ac  mov     rax, [rax+0A0h]
0x1400395b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400395b8  mov     rcx, [rax+60h]
0x1400395bc  mov     byte ptr [rcx+8Ch], 0Ah
0x1400395c3  lea     rcx, [rbp+57h+var_60]; this
0x1400395c7  call    ?InternalUnlock@CScmSyncLockExclusive@@IEAAXXZ; CScmSyncLockExclusive::InternalUnlock(void)
0x1400395cc  jmp     short loc_1400395FD
0x1400395ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1400395d5  cmp     rcx, r13
0x1400395d8  jz      short loc_1400395FD
0x1400395da  test    [rcx+1Ch], r12b
0x1400395de  jz      short loc_1400395FD
0x1400395e0  mov     r9, [rbp+57h+var_80]
0x1400395e4  lea     r8, WPP_036c406685683e02631f01bfa4d71e7e_Traceguids
0x1400395eb  mov     rcx, [rcx+10h]
0x1400395ef  mov     edx, 4Dh ; 'M'
0x1400395f4  mov     r9, [r9+38h]
0x1400395f8  call    WPP_SF_S
0x1400395fd  lea     rdx, [rbp+57h+var_80]
0x140039601  call    ?GetNext@CServiceDatabase@@QEAAXAEAV?$ComPtr@VCServiceRecord@@@WRL@Microsoft@@@Z; CServiceDatabase::GetNext(Microsoft::WRL::ComPtr<CServiceRecord> &)
0x140039606  jmp     loc_14003950F
0x14003960b  lea     rcx, [rbp+57h+var_80]
0x14003960f  call    ?InternalRelease@?$ComPtr@VCServiceRecord@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CServiceRecord>::InternalRelease(void)
0x140039614  lea     rcx, ?ScServiceRecordLock@@3VCServiceRecordLock@@A; Resource
0x14003961b  call    cs:__imp_RtlReleaseResource
0x140039621  mov     rbx, [rbp+57h+var_78]
0x140039625  lea     rax, [rbp+57h+var_78]
0x140039629  cmp     rbx, rax
0x14003962c  jz      loc_1400396BB
0x140039632  mov     rcx, [rbx+10h]
0x140039636  mov     eax, [rcx+54h]
0x140039639  sub     eax, 2
0x14003963c  test    eax, 0FFFFFFFDh
0x140039641  jnz     short loc_1400396B3
0x140039643  mov     rax, [rcx]
0x140039646  lea     rdx, aServiceUserLog; "Service user Log off"
0x14003964d  mov     [rsp+100h+var_98], r12d
0x140039652  xor     r9d, r9d
0x140039655  mov     [rsp+100h+var_A0], 0
0x14003965e  mov     r8d, r12d
0x140039661  mov     [rsp+100h+var_A8], 0
0x14003966a  mov     rax, [rax+40h]
0x14003966e  mov     [rsp+100h+var_B0], rdx
0x140039673  lea     rdx, [rbp+57h+var_80]
0x140039677  mov     [rsp+100h+var_B8], 0
0x14003967f  mov     [rsp+100h+var_C0], 0
0x140039687  mov     [rsp+100h+var_C8], 0
0x14003968f  mov     [rsp+100h+var_D0], rdx
0x140039694  xor     edx, edx
0x140039696  mov     dword ptr [rsp+100h+var_D8], 0
0x14003969e  mov     [rsp+100h+var_E0], 0
0x1400396a7  mov     dword ptr [rbp+57h+var_80], 0
0x1400396ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400396b3  mov     rbx, [rbx]
0x1400396b6  jmp     loc_140039625
0x1400396bb  mov     rax, cs:WPP_GLOBAL_Control
0x1400396c2  cmp     rax, r13
0x1400396c5  jz      short loc_1400396F4
0x1400396c7  test    [rax+1Ch], edi
0x1400396ca  jz      short loc_1400396F4
0x1400396cc  call    cs:__imp_GetTickCount64
0x1400396d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400396d9  lea     r8, WPP_036c406685683e02631f01bfa4d71e7e_Traceguids
0x1400396e0  sub     rax, r14
0x1400396e3  mov     edx, 4Eh ; 'N'
0x1400396e8  mov     r9, rax
0x1400396eb  mov     rcx, [rcx+10h]
0x1400396ef  call    WPP_SF_q
0x1400396f4  lea     rcx, g_TriggerRegistrationLock
0x1400396fb  call    cs:__imp_RtlAcquireSRWLockExclusive
0x140039701  call    cs:__imp_GetCurrentThreadId
0x140039707  mov     rbx, [rbp+57h+var_78]
0x14003970b  lea     rax, [rbp+57h+var_78]
0x14003970f  cmp     rbx, rax
0x140039712  jz      loc_1400397A0
0x140039718  mov     rdi, [rbx+10h]
0x14003971c  mov     eax, [rdi+34h]
0x14003971f  bt      eax, 0Ah
0x140039723  jnb     short loc_140039798
0x140039725  mov     rdx, [rdi+38h]
0x140039729  lea     rcx, [rbp+57h+var_58]
0x14003972d  xor     eax, eax
0x14003972f  mov     dword ptr [rsp+100h+var_E0], 20h ; ' '
0x140039737  mov     [rbp+57h+var_48], rax
0x14003973b  xorps   xmm0, xmm0
0x14003973e  mov     rax, cs:?g_pScExtFunctionPointers@@3PEAPEAXEA; void * * g_pScExtFunctionPointers
0x140039745  xor     r9d, r9d
0x140039748  movups  [rbp+57h+var_58], xmm0
0x14003974c  xor     r8d, r8d
0x14003974f  mov     rax, [rax+50h]
0x140039753  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140039758  test    eax, eax
0x14003975a  jz      short loc_14003978B
0x14003975c  mov     rcx, cs:WPP_GLOBAL_Control
0x140039763  cmp     rcx, r13
0x140039766  jz      short loc_14003978B
0x140039768  test    [rcx+1Ch], r12b
0x14003976c  jz      short loc_14003978B
0x14003976e  mov     r9, [rdi+38h]
0x140039772  lea     r8, WPP_036c406685683e02631f01bfa4d71e7e_Traceguids
0x140039779  mov     rcx, [rcx+10h]
0x14003977d  mov     edx, 4Fh ; 'O'
0x140039782  mov     dword ptr [rsp+100h+var_E0], eax
0x140039786  call    WPP_SF_Sd
0x14003978b  mov     edx, 400h; unsigned int
0x140039790  mov     rcx, rdi; this
0x140039793  call    ?ClearStatusFlag@CServiceRecord@@QEAAXK@Z; CServiceRecord::ClearStatusFlag(ulong)
0x140039798  mov     rbx, [rbx]
0x14003979b  jmp     loc_14003970B
0x1400397a0  lea     rcx, g_TriggerRegistrationLock
0x1400397a7  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1400397ad  lea     rcx, [rbp+57h+var_78]
0x1400397b1  call    ?ScWaitForUserServiceShutdown@@YAKAEAV?$list@V?$ComPtr@VCServiceRecord@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VCServiceRecord@@@WRL@Microsoft@@@utl@@@utl@@@Z; ScWaitForUserServiceShutdown(utl::list<Microsoft::WRL::ComPtr<CServiceRecord>,utl::allocator<Microsoft::WRL::ComPtr<CServiceRecord>>> &)
0x1400397b6  test    eax, eax
0x1400397b8  jz      short loc_1400397E4
0x1400397ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1400397c1  cmp     rcx, r13
0x1400397c4  jz      short loc_14003980E
0x1400397c6  test    [rcx+1Ch], r12b
0x1400397ca  jz      short loc_1400397EB
0x1400397cc  mov     rcx, [rcx+10h]
0x1400397d0  lea     r8, WPP_036c406685683e02631f01bfa4d71e7e_Traceguids
0x1400397d7  mov     edx, 50h ; 'P'
0x1400397dc  mov     r9d, eax
0x1400397df  call    WPP_SF_d
0x1400397e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400397eb  cmp     rcx, r13
0x1400397ee  jz      short loc_14003980E
0x1400397f0  test    dword ptr [rcx+1Ch], 100000h
0x1400397f7  jz      short loc_14003980E
0x1400397f9  mov     rcx, [rcx+10h]
0x1400397fd  lea     r8, WPP_036c406685683e02631f01bfa4d71e7e_Traceguids
0x140039804  mov     edx, 51h ; 'Q'
0x140039809  call    WPP_SF_
0x14003980e  mov     rbx, [rbp+57h+var_78]
0x140039812  lea     rax, [rbp+57h+var_78]
0x140039816  cmp     rbx, rax
0x140039819  jz      short loc_140039839
0x14003981b  mov     rdi, [rbx+10h]
0x14003981f  xor     r8d, r8d; int
0x140039822  mov     rcx, rdi; struct CWin32ServiceRecord *
0x140039825  xor     edx, edx; int
0x140039827  call    ?ScRemoveService@@YAKPEAVCWin32ServiceRecord@@HH@Z; ScRemoveService(CWin32ServiceRecord *,int,int)
0x14003982c  mov     rdx, rdi; struct CServiceRecord *
0x14003982f  call    ?Add@DEFER_LIST@@QEAAXPEAVCServiceRecord@@@Z; DEFER_LIST::Add(CServiceRecord *)
0x140039834  mov     rbx, [rbx]
0x140039837  jmp     short loc_140039812
0x140039839  mov     rcx, cs:WPP_GLOBAL_Control
0x140039840  cmp     rcx, r13
0x140039843  jz      short loc_140039863
0x140039845  test    dword ptr [rcx+1Ch], 100000h
0x14003984c  jz      short loc_140039863
0x14003984e  mov     rcx, [rcx+10h]
0x140039852  lea     r8, WPP_036c406685683e02631f01bfa4d71e7e_Traceguids
0x140039859  mov     edx, 52h ; 'R'
0x14003985e  call    WPP_SF_
0x140039863  mov     eax, cs:dword_1400BA2A0
0x140039869  cmp     eax, 5
0x14003986c  jbe     short loc_1400398C2
0x14003986e  mov     rdx, 400000000000h
0x140039878  lea     rcx, dword_1400BA2A0
0x14003987f  call    _tlgKeywordOn
0x140039884  test    al, al
0x140039886  jz      short loc_1400398C2
0x140039888  call    cs:__imp_GetTickCount64
0x14003988e  lea     r9, [rbp+57h+ActivityId]
0x140039892  mov     [rbp+57h+var_80], rsi
0x140039896  sub     rax, r14
0x140039899  lea     r8, ?g_ActivityId@@3U_GUID@@A; _GUID g_ActivityId
0x1400398a0  mov     [rbp+57h+var_60], rax
0x1400398a4  lea     rdx, byte_1400AE911
0x1400398ab  lea     rax, [rbp+57h+var_60]
0x1400398af  mov     [rsp+100h+var_D8], rax
0x1400398b4  lea     rax, [rbp+57h+var_80]
0x1400398b8  mov     [rsp+100h+var_E0], rax
0x1400398bd  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x1400398c2  lea     rdx, [rbp+57h+ActivityId]; ActivityId
0x1400398c6  mov     ecx, 2; ControlCode
0x1400398cb  call    cs:__imp_EventActivityIdControl
0x1400398d1  lea     rcx, [rbp+57h+var_78]
0x1400398d5  call    ?clear@?$list@V?$ComPtr@VCServiceRecord@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VCServiceRecord@@@WRL@Microsoft@@@utl@@@utl@@QEAAXXZ; utl::list<Microsoft::WRL::ComPtr<CServiceRecord>,utl::allocator<Microsoft::WRL::ComPtr<CServiceRecord>>>::clear(void)
0x1400398da  mov     rcx, [rbp+57h+var_30]
0x1400398de  xor     rcx, rsp; StackCookie
0x1400398e1  call    __security_check_cookie
0x1400398e6  lea     r11, [rsp+100h+var_20]
0x1400398ee  mov     rbx, [r11+38h]
0x1400398f2  mov     rsi, [r11+40h]
0x1400398f6  mov     rsp, r11
0x1400398f9  pop     r14
0x1400398fb  pop     r13
0x1400398fd  pop     r12
0x1400398ff  pop     rdi
0x140039900  pop     rbp
0x140039901  retn
```
