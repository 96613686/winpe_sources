# ComputeService::Communication::BridgeClient::BridgeClient(std::shared_ptr<Transport> const &,std::shared_ptr<ComputeService::Management::ComputeSystemManager> const &,std::shared_ptr<ComputeService::Communication::IProtocolReader> const &,std::function<void (ComputeService::Communication::BridgeNotification const &)>)

- ea: `0x14004dbe0`
- end: `0x14004e04a`
- name: `??0BridgeClient@Communication@ComputeService@@QEAA@AEBV?$shared_ptr@VTransport@@@std@@AEBV?$shared_ptr@VComputeSystemManager@Management@ComputeService@@@4@AEBV?$shared_ptr@VIProtocolReader@Communication@ComputeService@@@4@V?$function@$$A6AXAEBUBridgeNotification@Communication@ComputeService@@@Z@4@@Z`
- size: `1130`
- prototype: `char *__fastcall(char *pv, _QWORD *, _QWORD *, _QWORD *, __int64 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x140030c28`

## callees

- `0x1400056c4`
- `0x1400056fc`
- `0x140006098`
- `0x1400068e0`
- `0x14000ddac`
- `0x14002e120`
- `0x140044d1c`
- `0x14004b95c`
- `0x14004dbe0`
- `0x140055b80`
- `0x14007b860`
- `0x1400fe010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x14004dc9f`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x14004dc9f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x14004dd33`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x14004dd33`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x14004dd99`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x14004dd99`

## string_xrefs

- `0x14004e026`: `onecore\vm\compute\common\bridge\bridgeclient.cpp`
- `0x14004e038`: `onecore\vm\compute\common\bridge\bridgeclient.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char *__fastcall ComputeService::Communication::BridgeClient::BridgeClient(
        char *pv,
        _QWORD *a2,
        _QWORD *a3,
        _QWORD *a4,
        __int64 *a5)
{
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  char *v9; // rcx
  __int64 (__fastcall ***v10)(_QWORD, char *); // rcx
  PTP_CLEANUP_GROUP ThreadpoolCleanupGroup; // rax
  const char *v12; // r9
  PTP_WORK ThreadpoolWork; // rax
  const char *v14; // r9
  __int64 v15; // rax
  volatile signed __int32 *v16; // rbx
  _QWORD *v17; // rsi
  __int64 v18; // rax
  _QWORD *v19; // rax
  volatile signed __int32 *v20; // rdx
  volatile signed __int32 *v21; // rcx
  volatile signed __int32 *v22; // rsi
  __int64 v23; // rax
  volatile signed __int32 *v24; // rbx
  unsigned int v25; // ebx
  void *v26; // rsi
  unsigned __int64 v27; // rdx
  char *v28; // rax
  void *v29; // rcx
  __int64 v30; // rax
  volatile signed __int32 *v31; // rbx
  __int64 *v32; // rcx
  __int64 v33; // rdx
  char *v35; // [rsp+20h] [rbp-51h] BYREF
  void *v36; // [rsp+28h] [rbp-49h] BYREF
  volatile signed __int32 *v37; // [rsp+30h] [rbp-41h]
  char *v38; // [rsp+38h] [rbp-39h]
  __int64 v39; // [rsp+40h] [rbp-31h]
  char v40; // [rsp+48h] [rbp-29h] BYREF
  _QWORD v41[14]; // [rsp+50h] [rbp-21h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+57h]

  v38 = pv;
  v39 = (__int64)a5;
  *(_QWORD *)pv = &ComputeService::Communication::BridgeClient::`vftable';
  *((_QWORD *)pv + 1) = 0;
  *((_QWORD *)pv + 2) = 0;
  v6 = a3[1];
  if ( v6 )
    _InterlockedIncrement((volatile signed __int32 *)(v6 + 8));
  *((_QWORD *)pv + 1) = *a3;
  *((_QWORD *)pv + 2) = a3[1];
  *((_QWORD *)pv + 3) = 0;
  *((_QWORD *)pv + 4) = 0;
  v7 = a2[1];
  if ( v7 )
    _InterlockedIncrement((volatile signed __int32 *)(v7 + 8));
  *((_QWORD *)pv + 3) = *a2;
  *((_QWORD *)pv + 4) = a2[1];
  *((_QWORD *)pv + 5) = 0;
  *((_QWORD *)pv + 6) = 0;
  v8 = a4[1];
  if ( v8 )
    _InterlockedIncrement((volatile signed __int32 *)(v8 + 8));
  *((_QWORD *)pv + 5) = *a4;
  *((_QWORD *)pv + 6) = a4[1];
  *((_QWORD *)pv + 7) = 0;
  *((_QWORD *)pv + 8) = 0;
  *((_QWORD *)pv + 9) = 0;
  *((_QWORD *)pv + 10) = 0;
  *((_QWORD *)pv + 11) = 0;
  *((_QWORD *)pv + 12) = 0;
  v9 = pv + 104;
  *((_DWORD *)v9 + 2) = 0;
  InitializeSRWLock((PSRWLOCK)v9);
  *((_DWORD *)pv + 30) = 0;
  v35 = pv + 128;
  *((_QWORD *)pv + 23) = 0;
  v10 = (__int64 (__fastcall ***)(_QWORD, char *))a5[7];
  if ( v10 )
    *((_QWORD *)pv + 23) = (**v10)(v10, pv + 128);
  *((_QWORD *)pv + 24) = 0;
  *((_QWORD *)pv + 25) = 0;
  *(_OWORD *)(pv + 280) = 0;
  *(_OWORD *)(pv + 296) = 0;
  *((_DWORD *)pv + 78) = 0;
  *((_DWORD *)pv + 52) = 3;
  *((_QWORD *)pv + 27) = 0;
  *((_QWORD *)pv + 28) = 0;
  *((_QWORD *)pv + 29) = 0;
  *((_QWORD *)pv + 30) = 0;
  *((_QWORD *)pv + 31) = 0;
  *((_QWORD *)pv + 32) = 0;
  *((_DWORD *)pv + 66) = 0;
  *((_DWORD *)pv + 67) = 1;
  *((_DWORD *)pv + 68) = 72;
  ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
  *((_QWORD *)pv + 25) = ThreadpoolCleanupGroup;
  if ( !ThreadpoolCleanupGroup )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x34E,
      (unsigned int)"onecore\\vm\\compute\\common\\bridge\\bridgeclient.cpp",
      v12);
  *((_QWORD *)pv + 28) = ThreadpoolCleanupGroup;
  *((_QWORD *)pv + 29) = 0;
  (*(void (__fastcall **)(_QWORD, char *))(**((_QWORD **)pv + 3) + 8LL))(*((_QWORD *)pv + 3), pv);
  v41[0] = &std::_Func_impl_no_alloc<_lambda_536524eda838714cf1ea4162ab577322_,void,std::wstring const &,ComputeService::Management::ComputeSystemNotificationInfo const &>::`vftable';
  v41[1] = pv;
  v41[7] = v41;
  ComputeService::Management::ComputeSystemManager::RegisterNotificationCallback(*((_QWORD *)pv + 1), v41);
  ThreadpoolWork = CreateThreadpoolWork(
                     lambda_00e6871b655ba3839164241ec165860f_::_lambda_invoker_cdecl_,
                     pv,
                     (PTP_CALLBACK_ENVIRON)(pv + 208));
  *((_QWORD *)pv + 24) = ThreadpoolWork;
  if ( !ThreadpoolWork )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x36A,
      (unsigned int)"onecore\\vm\\compute\\common\\bridge\\bridgeclient.cpp",
      v14);
  LODWORD(v35) = 2;
  v36 = operator new(0x40u);
  v15 = ((__int64 (__fastcall *)(void *, const unsigned int *, const unsigned int *, char **))std::_Ref_count_obj2<TransportIoContextPool>::_Ref_count_obj2<TransportIoContextPool>)(
          v36,
          &ComputeService::Communication::BridgeClient::c_SendContextPoolSize,
          &ComputeService::Communication::BridgeClient::c_SendBufferSize,
          &v35);
  v16 = (volatile signed __int32 *)v15;
  v17 = (_QWORD *)(v15 + 16);
  if ( v15 != -16 )
  {
    v18 = *(_QWORD *)(v15 + 24);
    if ( !v18 || !*(_DWORD *)(v18 + 8) )
    {
      if ( v16 )
      {
        _InterlockedIncrement(v16 + 2);
        v19 = v17;
        v20 = v16;
        _InterlockedIncrement(v16 + 3);
      }
      else
      {
        v19 = 0;
        v20 = 0;
      }
      *v17 = v19;
      v21 = (volatile signed __int32 *)v17[1];
      v17[1] = v20;
      if ( v21 && !_InterlockedDecrement(v21 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v21 + 8LL))(v21);
      if ( v16 )
      {
        if ( !_InterlockedDecrement(v16 + 2) )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v16)(v16);
          if ( !_InterlockedDecrement(v16 + 3) )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
        }
      }
    }
  }
  *((_QWORD *)pv + 11) = v17;
  v22 = (volatile signed __int32 *)*((_QWORD *)pv + 12);
  *((_QWORD *)pv + 12) = v16;
  if ( v22 )
  {
    if ( !_InterlockedDecrement(v22 + 2) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v22)(v22);
      if ( !_InterlockedDecrement(v22 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v22 + 8LL))(v22);
    }
  }
  v23 = std::make_shared<TransportIoContext,>(&v36);
  std::shared_ptr<TransportIoContext>::operator=(pv + 72, v23);
  v24 = v37;
  if ( v37 )
  {
    if ( _InterlockedExchangeAdd(v37 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v24)(v24);
      if ( _InterlockedExchangeAdd(v24 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v24 + 8LL))(v24);
    }
  }
  *(_DWORD *)(*((_QWORD *)pv + 9) + 16LL) = 3;
  *(_DWORD *)(*((_QWORD *)pv + 9) + 32LL) = 0x10000;
  v25 = *(_DWORD *)(*((_QWORD *)pv + 9) + 32LL);
  v26 = operator new[](v25);
  memset_0(v26, 0, v25);
  v28 = (char *)(*((_QWORD *)pv + 9) + 24LL);
  if ( v28 == &v40 )
  {
    if ( v26 )
    {
      v29 = v26;
LABEL_37:
      operator delete(v29, v27);
    }
  }
  else
  {
    v29 = *(void **)v28;
    *(_QWORD *)v28 = v26;
    if ( v29 )
      goto LABEL_37;
  }
  v30 = std::make_shared<TransportIoContext,>(&v36);
  std::shared_ptr<TransportIoContext>::operator=(pv + 56, v30);
  v31 = v37;
  if ( v37 )
  {
    if ( _InterlockedExchangeAdd(v37 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v31)(v31);
      if ( _InterlockedExchangeAdd(v31 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v31 + 8LL))(v31);
    }
  }
  *(_DWORD *)(*((_QWORD *)pv + 7) + 16LL) = 1;
  ComputeService::Communication::BridgeClient::StartConnect(pv, pv + 56);
  v32 = (__int64 *)a5[7];
  if ( v32 )
  {
    v33 = *v32;
    LOBYTE(v33) = v32 != a5;
    (*(void (__fastcall **)(__int64 *, __int64))(*v32 + 32))(v32, v33);
    a5[7] = 0;
  }
  return pv;
}

```

## disassembly

```asm
0x14004dbe0  push    rbp
0x14004dbe2  push    rbx
0x14004dbe3  push    rsi
0x14004dbe4  push    rdi
0x14004dbe5  push    r12
0x14004dbe7  push    r14
0x14004dbe9  push    r15
0x14004dbeb  lea     rbp, [rsp-1Fh]
0x14004dbf0  sub     rsp, 90h
0x14004dbf7  mov     rdi, rcx
0x14004dbfa  mov     [rbp+4Fh+var_88], rcx
0x14004dbfe  mov     r14, [rbp+4Fh+arg_20]
0x14004dc02  mov     [rbp+4Fh+var_80], r14
0x14004dc06  xor     r15d, r15d
0x14004dc09  lea     rax, ??_7BridgeClient@Communication@ComputeService@@6B@; const ComputeService::Communication::BridgeClient::`vftable'
0x14004dc10  mov     [rcx], rax
0x14004dc13  mov     [rcx+8], r15
0x14004dc17  mov     [rcx+10h], r15
0x14004dc1b  mov     rax, [r8+8]
0x14004dc1f  test    rax, rax
0x14004dc22  jz      short loc_14004DC28
0x14004dc24  lock inc dword ptr [rax+8]
0x14004dc28  mov     rax, [r8]
0x14004dc2b  mov     [rcx+8], rax
0x14004dc2f  mov     rax, [r8+8]
0x14004dc33  mov     [rcx+10h], rax
0x14004dc37  mov     [rcx+18h], r15
0x14004dc3b  mov     [rcx+20h], r15
0x14004dc3f  mov     rax, [rdx+8]
0x14004dc43  test    rax, rax
0x14004dc46  jz      short loc_14004DC4C
0x14004dc48  lock inc dword ptr [rax+8]
0x14004dc4c  mov     rax, [rdx]
0x14004dc4f  mov     [rcx+18h], rax
0x14004dc53  mov     rax, [rdx+8]
0x14004dc57  mov     [rcx+20h], rax
0x14004dc5b  mov     [rcx+28h], r15
0x14004dc5f  mov     [rcx+30h], r15
0x14004dc63  mov     rax, [r9+8]
0x14004dc67  test    rax, rax
0x14004dc6a  jz      short loc_14004DC70
0x14004dc6c  lock inc dword ptr [rax+8]
0x14004dc70  mov     rax, [r9]
0x14004dc73  mov     [rcx+28h], rax
0x14004dc77  mov     rax, [r9+8]
0x14004dc7b  mov     [rcx+30h], rax
0x14004dc7f  mov     [rcx+38h], r15
0x14004dc83  mov     [rcx+40h], r15
0x14004dc87  mov     [rcx+48h], r15
0x14004dc8b  mov     [rcx+50h], r15
0x14004dc8f  mov     [rcx+58h], r15
0x14004dc93  mov     [rcx+60h], r15
0x14004dc97  add     rcx, 68h ; 'h'; SRWLock
0x14004dc9b  mov     [rcx+8], r15d
0x14004dc9f  call    cs:__imp_InitializeSRWLock
0x14004dca5  mov     [rdi+78h], r15d
0x14004dca9  lea     rbx, [rdi+80h]
0x14004dcb0  mov     [rbp+4Fh+var_A0], rbx
0x14004dcb4  mov     [rbx+38h], r15
0x14004dcb8  mov     rcx, [r14+38h]
0x14004dcbc  test    rcx, rcx
0x14004dcbf  jz      short loc_14004DCD3
0x14004dcc1  mov     rax, [rcx]
0x14004dcc4  mov     rdx, rbx
0x14004dcc7  mov     rax, [rax]
0x14004dcca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004dccf  mov     [rbx+38h], rax
0x14004dcd3  mov     [rdi+0C0h], r15
0x14004dcda  mov     [rdi+0C8h], r15
0x14004dce1  xorps   xmm0, xmm0
0x14004dce4  movups  xmmword ptr [rdi+118h], xmm0
0x14004dceb  xorps   xmm1, xmm1
0x14004dcee  movups  xmmword ptr [rdi+128h], xmm1
0x14004dcf5  mov     [rdi+138h], r15d
0x14004dcfc  lea     rbx, [rdi+0D0h]
0x14004dd03  mov     dword ptr [rbx], 3
0x14004dd09  mov     [rbx+8], r15
0x14004dd0d  mov     [rbx+10h], r15
0x14004dd11  mov     [rbx+18h], r15
0x14004dd15  mov     [rbx+20h], r15
0x14004dd19  mov     [rbx+28h], r15
0x14004dd1d  mov     [rbx+30h], r15
0x14004dd21  mov     [rbx+38h], r15d
0x14004dd25  mov     dword ptr [rbx+3Ch], 1
0x14004dd2c  mov     dword ptr [rbx+40h], 48h ; 'H'
0x14004dd33  call    cs:__imp_CreateThreadpoolCleanupGroup
0x14004dd39  mov     [rdi+0C8h], rax
0x14004dd40  mov     rcx, [rbp+57h]; this
0x14004dd44  test    rax, rax
0x14004dd47  jz      loc_14004E038
0x14004dd4d  mov     [rbx+10h], rax
0x14004dd51  mov     [rbx+18h], r15
0x14004dd55  mov     rcx, [rdi+18h]
0x14004dd59  mov     rax, [rcx]
0x14004dd5c  mov     rdx, rdi
0x14004dd5f  mov     rax, [rax+8]
0x14004dd63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004dd68  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_536524eda838714cf1ea4162ab577322_@@XAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBUComputeSystemNotificationInfo@Management@ComputeService@@@std@@6B@; const std::_Func_impl_no_alloc<_lambda_536524eda838714cf1ea4162ab577322_,void,std::wstring const &,ComputeService::Management::ComputeSystemNotificationInfo const &>::`vftable'
0x14004dd6f  mov     [rbp+4Fh+var_70], rax
0x14004dd73  mov     [rbp+4Fh+var_68], rdi
0x14004dd77  lea     rax, [rbp+4Fh+var_70]
0x14004dd7b  mov     [rbp+4Fh+var_38], rax
0x14004dd7f  lea     rdx, [rbp+4Fh+var_70]
0x14004dd83  mov     rcx, [rdi+8]
0x14004dd87  call    ?RegisterNotificationCallback@ComputeSystemManager@Management@ComputeService@@QEAAXV?$function@$$A6AXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBUComputeSystemNotificationInfo@Management@ComputeService@@@Z@std@@@Z; ComputeService::Management::ComputeSystemManager::RegisterNotificationCallback(std::function<void (std::wstring const &,ComputeService::Management::ComputeSystemNotificationInfo const &)>)
0x14004dd8c  mov     r8, rbx; pcbe
0x14004dd8f  mov     rdx, rdi; pv
0x14004dd92  lea     rcx, _lambda_00e6871b655ba3839164241ec165860f____lambda_invoker_cdecl_; pfnwk
0x14004dd99  call    cs:__imp_CreateThreadpoolWork
0x14004dd9f  mov     [rdi+0C0h], rax
0x14004dda6  mov     rcx, [rbp+57h]; this
0x14004ddaa  test    rax, rax
0x14004ddad  jz      loc_14004E026
0x14004ddb3  mov     dword ptr [rbp+4Fh+var_A0], 2
0x14004ddba  mov     ecx, 40h ; '@'; Size
0x14004ddbf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14004ddc4  mov     [rbp+4Fh+var_98], rax
0x14004ddc8  lea     r9, [rbp+4Fh+var_A0]
0x14004ddcc  lea     r8, ?c_SendBufferSize@BridgeClient@Communication@ComputeService@@0KB; ulong const ComputeService::Communication::BridgeClient::c_SendBufferSize
0x14004ddd3  lea     rdx, ?c_SendContextPoolSize@BridgeClient@Communication@ComputeService@@0KB; ulong const ComputeService::Communication::BridgeClient::c_SendContextPoolSize
0x14004ddda  mov     rcx, rax
0x14004dddd  call    ??$?0AEBKAEBKW4TransportIoContextType@@@?$_Ref_count_obj2@VTransportIoContextPool@@@std@@QEAA@AEBK0$$QEAW4TransportIoContextType@@@Z; std::_Ref_count_obj2<TransportIoContextPool>::_Ref_count_obj2<TransportIoContextPool>(ulong const &,ulong const &,TransportIoContextType &&)
0x14004dde2  mov     rbx, rax
0x14004dde5  lea     rsi, [rax+10h]
0x14004dde9  or      r12d, 0FFFFFFFFh
0x14004dded  test    rsi, rsi
0x14004ddf0  jz      loc_14004DE89
0x14004ddf6  mov     rax, [rsi+8]
0x14004ddfa  test    rax, rax
0x14004ddfd  jz      short loc_14004DE09
0x14004ddff  cmp     [rax+8], r15d
0x14004de03  jnz     loc_14004DE89
0x14004de09  test    rbx, rbx
0x14004de0c  jz      short loc_14004DE1E
0x14004de0e  lock inc dword ptr [rbx+8]
0x14004de12  mov     rax, rsi
0x14004de15  mov     rdx, rbx
0x14004de18  lock inc dword ptr [rbx+0Ch]
0x14004de1c  jmp     short loc_14004DE24
0x14004de1e  mov     rax, r15
0x14004de21  mov     rdx, r15
0x14004de24  mov     [rsi], rax
0x14004de27  mov     rcx, [rsi+8]
0x14004de2b  mov     [rsi+8], rdx
0x14004de2f  test    rcx, rcx
0x14004de32  jz      short loc_14004DE4D
0x14004de34  mov     eax, r12d
0x14004de37  lock xadd [rcx+0Ch], eax
0x14004de3c  add     eax, r12d
0x14004de3f  jnz     short loc_14004DE4D
0x14004de41  mov     rax, [rcx]
0x14004de44  mov     rax, [rax+8]
0x14004de48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004de4d  test    rbx, rbx
0x14004de50  jz      short loc_14004DE89
0x14004de52  mov     eax, r12d
0x14004de55  lock xadd [rbx+8], eax
0x14004de5a  add     eax, r12d
0x14004de5d  jnz     short loc_14004DE89
0x14004de5f  mov     rax, [rbx]
0x14004de62  mov     rcx, rbx
0x14004de65  mov     rax, [rax]
0x14004de68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004de6d  mov     eax, r12d
0x14004de70  lock xadd [rbx+0Ch], eax
0x14004de75  add     eax, r12d
0x14004de78  jnz     short loc_14004DE89
0x14004de7a  mov     rax, [rbx]
0x14004de7d  mov     rcx, rbx
0x14004de80  mov     rax, [rax+8]
0x14004de84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004de89  mov     [rdi+58h], rsi
0x14004de8d  mov     rsi, [rdi+60h]
0x14004de91  mov     [rdi+60h], rbx
0x14004de95  test    rsi, rsi
0x14004de98  jz      short loc_14004DED1
0x14004de9a  mov     eax, r12d
0x14004de9d  lock xadd [rsi+8], eax
0x14004dea2  add     eax, r12d
0x14004dea5  jnz     short loc_14004DED1
0x14004dea7  mov     rax, [rsi]
0x14004deaa  mov     rcx, rsi
0x14004dead  mov     rax, [rax]
0x14004deb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004deb5  mov     eax, r12d
0x14004deb8  lock xadd [rsi+0Ch], eax
0x14004debd  add     eax, r12d
0x14004dec0  jnz     short loc_14004DED1
0x14004dec2  mov     rax, [rsi]
0x14004dec5  mov     rcx, rsi
0x14004dec8  mov     rax, [rax+8]
0x14004decc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004ded1  lea     rcx, [rbp+4Fh+var_98]
0x14004ded5  call    ??$make_shared@VTransportIoContext@@$$V@std@@YA?AV?$shared_ptr@VTransportIoContext@@@0@XZ; std::make_shared<TransportIoContext,>(void)
0x14004deda  lea     rcx, [rdi+48h]
0x14004dede  mov     rdx, rax
0x14004dee1  call    ??4?$shared_ptr@VTransportIoContext@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<TransportIoContext>::operator=(std::shared_ptr<TransportIoContext> &&)
0x14004dee6  mov     rbx, [rbp+4Fh+var_90]
0x14004deea  test    rbx, rbx
0x14004deed  jz      short loc_14004DF26
0x14004deef  mov     eax, r12d
0x14004def2  lock xadd [rbx+8], eax
0x14004def7  add     eax, r12d
0x14004defa  jnz     short loc_14004DF26
0x14004defc  mov     rax, [rbx]
0x14004deff  mov     rcx, rbx
0x14004df02  mov     rax, [rax]
0x14004df05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004df0a  mov     eax, r12d
0x14004df0d  lock xadd [rbx+0Ch], eax
0x14004df12  add     eax, r12d
0x14004df15  jnz     short loc_14004DF26
0x14004df17  mov     rax, [rbx]
0x14004df1a  mov     rcx, rbx
0x14004df1d  mov     rax, [rax+8]
0x14004df21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004df26  mov     rax, [rdi+48h]
0x14004df2a  mov     dword ptr [rax+10h], 3
0x14004df31  mov     rax, [rdi+48h]
0x14004df35  mov     dword ptr [rax+20h], 10000h
0x14004df3c  mov     rax, [rdi+48h]
0x14004df40  mov     ebx, [rax+20h]
0x14004df43  mov     ecx, ebx; unsigned __int64
0x14004df45  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x14004df4a  mov     rsi, rax
0x14004df4d  mov     r8d, ebx; Size
0x14004df50  xor     edx, edx; Val
0x14004df52  mov     rcx, rax; void *
0x14004df55  call    memset_0
0x14004df5a  mov     rax, [rdi+48h]
0x14004df5e  add     rax, 18h
0x14004df62  lea     rcx, [rbp+4Fh+var_78]
0x14004df66  cmp     rax, rcx
0x14004df69  jz      short loc_14004DF78
0x14004df6b  mov     rcx, [rax]
0x14004df6e  mov     [rax], rsi
0x14004df71  test    rcx, rcx
0x14004df74  jz      short loc_14004DF85
0x14004df76  jmp     short loc_14004DF80
0x14004df78  test    rsi, rsi
0x14004df7b  jz      short loc_14004DF85
0x14004df7d  mov     rcx, rsi; void *
0x14004df80  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14004df85  lea     rcx, [rbp+4Fh+var_98]
0x14004df89  call    ??$make_shared@VTransportIoContext@@$$V@std@@YA?AV?$shared_ptr@VTransportIoContext@@@0@XZ; std::make_shared<TransportIoContext,>(void)
0x14004df8e  lea     rcx, [rdi+38h]
0x14004df92  mov     rdx, rax
0x14004df95  call    ??4?$shared_ptr@VTransportIoContext@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<TransportIoContext>::operator=(std::shared_ptr<TransportIoContext> &&)
0x14004df9a  mov     rbx, [rbp+4Fh+var_90]
0x14004df9e  test    rbx, rbx
0x14004dfa1  jz      short loc_14004DFDA
0x14004dfa3  mov     eax, r12d
0x14004dfa6  lock xadd [rbx+8], eax
0x14004dfab  add     eax, r12d
0x14004dfae  jnz     short loc_14004DFDA
0x14004dfb0  mov     rax, [rbx]
0x14004dfb3  mov     rcx, rbx
0x14004dfb6  mov     rax, [rax]
0x14004dfb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004dfbe  mov     eax, r12d
0x14004dfc1  lock xadd [rbx+0Ch], eax
0x14004dfc6  add     eax, r12d
0x14004dfc9  jnz     short loc_14004DFDA
0x14004dfcb  mov     rax, [rbx]
0x14004dfce  mov     rcx, rbx
0x14004dfd1  mov     rax, [rax+8]
0x14004dfd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004dfda  mov     rax, [rdi+38h]
0x14004dfde  mov     dword ptr [rax+10h], 1
0x14004dfe5  lea     rdx, [rdi+38h]
0x14004dfe9  mov     rcx, rdi
0x14004dfec  call    ?StartConnect@BridgeClient@Communication@ComputeService@@AEAAXAEBV?$shared_ptr@VTransportIoContext@@@std@@@Z; ComputeService::Communication::BridgeClient::StartConnect(std::shared_ptr<TransportIoContext> const &)
0x14004dff1  nop
0x14004dff2  mov     rcx, [r14+38h]
0x14004dff6  test    rcx, rcx
0x14004dff9  jz      short loc_14004E011
0x14004dffb  mov     rdx, [rcx]
0x14004dffe  mov     rax, [rdx+20h]
0x14004e002  cmp     rcx, r14
0x14004e005  setnz   dl
0x14004e008  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004e00d  mov     [r14+38h], r15
0x14004e011  mov     rax, rdi
0x14004e014  add     rsp, 90h
0x14004e01b  pop     r15
0x14004e01d  pop     r14
0x14004e01f  pop     r12
0x14004e021  pop     rdi
0x14004e022  pop     rsi
0x14004e023  pop     rbx
0x14004e024  pop     rbp
0x14004e025  retn
0x14004e026  lea     r8, aOnecoreVmCompu_21; "onecore\\vm\\compute\\common\\bridge\\b"...
0x14004e02d  mov     edx, 36Ah; void *
0x14004e032  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14004e038  lea     r8, aOnecoreVmCompu_21; "onecore\\vm\\compute\\common\\bridge\\b"...
0x14004e03f  mov     edx, 34Eh; void *
0x14004e044  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
