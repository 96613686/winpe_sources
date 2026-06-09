# WinBioSrvLockUnit

- ea: `0x1800204b0`
- end: `0x1800208c1`
- name: `WinBioSrvLockUnit`
- size: `1041`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x18000b760`
- `0x18000eed0`
- `0x18000f090`
- `0x1800118fc`
- `0x18001d730`
- `0x18001fb04`
- `0x1800204b0`
- `0x180020ca4`
- `0x180020cdc`
- `0x180022ba4`
- `0x180022c6c`
- `0x180055928`
- `0x18005d3e0`
- `0x180068f60`
- `0x18006963c`
- `0x180099508`
- `0x180099c4c`
- `0x1800d2010`

## import_xrefs

- `RPCRT4!RpcServerTestCancel` at `0x180020544`
- `RPCRT4!RpcServerTestCancel` at `0x180020544`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180020572`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180020625`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18002067a`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800206c0`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800208b5`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180020572`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180020625`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18002067a`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800206c0`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800208b5`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
RPC_STATUS __fastcall WinBioSrvLockUnit(__int64 a1, __int64 a2, unsigned int a3)
{
  struct _RPC_ASYNC_STATE *v5; // rbx
  struct _RPC_ASYNC_STATE *v6; // rbx
  struct _RPC_ASYNC_STATE *v7; // rbx
  RPC_STATUS result; // eax
  struct _RPC_ASYNC_STATE *v9; // rbx
  __int64 v11; // rdx
  const char *v12; // r9
  struct _RPC_ASYNC_STATE *v13; // rbx
  __int64 v14; // [rsp+20h] [rbp-88h] BYREF
  char *Reply; // [rsp+28h] [rbp-80h] BYREF
  std::_Ref_count_base *v16; // [rsp+30h] [rbp-78h]
  __int64 v17; // [rsp+38h] [rbp-70h] BYREF
  __int64 v18; // [rsp+40h] [rbp-68h] BYREF
  std::_Ref_count_base *v19; // [rsp+48h] [rbp-60h]
  int v20; // [rsp+50h] [rbp-58h] BYREF
  __int64 v21; // [rsp+58h] [rbp-50h] BYREF
  _BYTE v22[16]; // [rsp+60h] [rbp-48h] BYREF
  char v23[8]; // [rsp+70h] [rbp-38h] BYREF
  std::_Ref_count_base *v24; // [rsp+78h] [rbp-30h]
  char v25[24]; // [rsp+80h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  v21 = a1;
  v14 = _InterlockedExchange64(&v21, 0);
  v20 = 0;
  strcpy(v25, "WinBioSrvLockUnit");
  lambda_afd7ee1b065516bcafbe102d67bfbf3c_::_lambda_afd7ee1b065516bcafbe102d67bfbf3c_(v22, v25, &v20);
  lambda_80f882fb2776bdaef0a64b06c9c879ed_::operator()(v22);
  v20 = 1;
  _lambda_1d8e544947e376896bbe6f02de9fb8f9_::_lambda_1d8e544947e376896bbe6f02de9fb8f9_(&v17, (__int64)v22);
  if ( !RpcServerTestCancel(0) )
  {
    LODWORD(Reply) = -2146861052;
    v5 = (struct _RPC_ASYNC_STATE *)_InterlockedExchange64(&v14, 0);
    if ( v5 )
    {
      CRpcDispatcher::UnsubscribeChangeNotification(v5);
      RpcAsyncCompleteCall(v5, &Reply);
    }
LABEL_20:
    result = WppTraceUnwinder__lambda_80f882fb2776bdaef0a64b06c9c879ed____::_WppTraceUnwinder__lambda_80f882fb2776bdaef0a64b06c9c879ed____(&v17);
    LODWORD(Reply) = -2146861052;
    v9 = (struct _RPC_ASYNC_STATE *)_InterlockedExchange64(&v14, 0);
    if ( v9 )
    {
      CRpcDispatcher::UnsubscribeChangeNotification(v9);
      return RpcAsyncCompleteCall(v9, &Reply);
    }
    return result;
  }
  CSessionManager::Find(&v18, a2);
  if ( !v18 )
  {
    CRpcAsyncStatePointer::CompleteRequest((CRpcAsyncStatePointer *)&v14, -2147024890);
    if ( v19 )
      std::_Ref_count_base::_Decref(v19);
LABEL_38:
    WppTraceUnwinder__lambda_80f882fb2776bdaef0a64b06c9c879ed____::_WppTraceUnwinder__lambda_80f882fb2776bdaef0a64b06c9c879ed____(&v17);
    return CRpcAsyncStatePointer::CompleteRequest((CRpcAsyncStatePointer *)&v14, -2146861052);
  }
  if ( !a3 )
  {
    LODWORD(Reply) = -2147024809;
    v6 = (struct _RPC_ASYNC_STATE *)_InterlockedExchange64(&v14, 0);
    if ( v6 )
    {
      CRpcDispatcher::UnsubscribeChangeNotification(v6);
      RpcAsyncCompleteCall(v6, &Reply);
    }
    if ( v19 )
      std::_Ref_count_base::_Decref(v19);
    goto LABEL_20;
  }
  if ( BindingHelper::IsEnrolling((BindingHelper *)(v18 + 16)) )
  {
    LODWORD(Reply) = -2146861049;
    v7 = (struct _RPC_ASYNC_STATE *)_InterlockedExchange64(&v14, 0);
    if ( v7 )
    {
      CRpcDispatcher::UnsubscribeChangeNotification(v7);
      RpcAsyncCompleteCall(v7, &Reply);
    }
    if ( v19 )
      std::_Ref_count_base::_Decref(v19);
    goto LABEL_20;
  }
  if ( BindingHelper::IsLocked((BindingHelper *)(v18 + 16)) )
  {
    CRpcAsyncStatePointer::CompleteRequest((CRpcAsyncStatePointer *)&v14, -2146861014);
    if ( v19 )
      std::_Ref_count_base::_Decref(v19);
    goto LABEL_38;
  }
  CHardwareManager::FindBiometricUnit(&Reply, a3);
  if ( !Reply )
  {
    CRpcAsyncStatePointer::CompleteRequest((CRpcAsyncStatePointer *)&v14, -2146861054);
    if ( v16 )
      std::_Ref_count_base::_Decref(v16);
    if ( v19 )
      std::_Ref_count_base::_Decref(v19);
    goto LABEL_38;
  }
  if ( BindingHelper::IsEnrolling((BindingHelper *)(Reply + 16)) )
  {
    CRpcAsyncStatePointer::CompleteRequest((CRpcAsyncStatePointer *)&v14, -2146861049);
    if ( v16 )
      std::_Ref_count_base::_Decref(v16);
    if ( v19 )
      std::_Ref_count_base::_Decref(v19);
    goto LABEL_38;
  }
  if ( v16 )
    std::_Ref_count_base::_Decref(v16);
  try
  {
    Reply = (char *)operator new(0x60u);
    v11 = CWinBioSrvLockUnit::CWinBioSrvLockUnit(Reply, &v14, &v18, a3, v14);
    std::shared_ptr<CAsyncWorkItem>::shared_ptr<CAsyncWorkItem>(v23, v11);
    CClientSession::ParentBsp(v18, &Reply);
    if ( Reply )
      (*(void (__fastcall **)(char *, __int64 *, char *))(*(_QWORD *)Reply + 56LL))(Reply, &v18, v23);
    if ( v16 )
      std::_Ref_count_base::_Decref(v16);
    if ( v24 )
      std::_Ref_count_base::_Decref(v24);
    if ( v19 )
      std::_Ref_count_base::_Decref(v19);
    result = WppTraceUnwinder__lambda_80f882fb2776bdaef0a64b06c9c879ed____::_WppTraceUnwinder__lambda_80f882fb2776bdaef0a64b06c9c879ed____(&v17);
  }
  catch ( ... )
  {
    wil::details::in1diag3::FailFast_CaughtException(
      retaddr,
      (void *)0xC91,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\winbiosrv.cpp",
      v12);
  }
  LODWORD(Reply) = -2146861052;
  v13 = (struct _RPC_ASYNC_STATE *)_InterlockedExchange64(&v14, 0);
  if ( v13 )
  {
    CRpcDispatcher::UnsubscribeChangeNotification(v13);
    return RpcAsyncCompleteCall(v13, &Reply);
  }
  return result;
}

```

## disassembly

```asm
0x1800204b0  mov     r11, rsp
0x1800204b3  mov     [r11+10h], rbx
0x1800204b7  push    rdi
0x1800204b8  sub     rsp, 0A0h
0x1800204bf  mov     rax, cs:__security_cookie
0x1800204c6  xor     rax, rsp
0x1800204c9  mov     [rsp+0A8h+var_10], rax
0x1800204d1  mov     ebx, r8d
0x1800204d4  mov     rdi, rdx
0x1800204d7  mov     [r11-50h], rcx
0x1800204db  mov     [rsp+0A8h+var_88], 0
0x1800204e4  xor     eax, eax
0x1800204e6  xchg    rax, [r11-50h]
0x1800204ea  mov     [rsp+0A8h+var_88], rax
0x1800204ef  mov     [rsp+0A8h+var_58], 0
0x1800204f7  movups  xmm0, xmmword ptr cs:aWinbiosrvlocku; "WinBioSrvLockUnit"
0x1800204fe  movups  xmmword ptr [r11-28h], xmm0
0x180020503  movzx   eax, word ptr cs:aWinbiosrvlocku+10h; "t"
0x18002050a  mov     [r11-18h], ax
0x18002050f  lea     r8, [r11-58h]
0x180020513  lea     rdx, [r11-28h]
0x180020517  lea     rcx, [r11-48h]
0x18002051b  call    _lambda_afd7ee1b065516bcafbe102d67bfbf3c____lambda_afd7ee1b065516bcafbe102d67bfbf3c_
0x180020520  lea     rcx, [rsp+0A8h+var_48]
0x180020525  call    _lambda_80f882fb2776bdaef0a64b06c9c879ed___operator__
0x18002052a  mov     [rsp+0A8h+var_58], 1
0x180020532  lea     rdx, [rsp+0A8h+var_48]
0x180020537  lea     rcx, [rsp+0A8h+var_70]
0x18002053c  call    ??0_lambda_1d8e544947e376896bbe6f02de9fb8f9_@@QEAA@PEAV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@Z; _lambda_1d8e544947e376896bbe6f02de9fb8f9_::_lambda_1d8e544947e376896bbe6f02de9fb8f9_(nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>> *)
0x180020541  nop
0x180020542  xor     ecx, ecx; BindingHandle
0x180020544  call    cs:__imp_RpcServerTestCancel
0x18002054a  test    eax, eax
0x18002054c  jnz     short loc_180020589
0x18002054e  mov     dword ptr [rsp+0A8h+Reply], 80098004h
0x180020556  xor     ebx, ebx
0x180020558  xchg    rbx, [rsp+0A8h+var_88]
0x18002055d  test    rbx, rbx
0x180020560  jz      short loc_180020579
0x180020562  mov     rcx, rbx; struct _RPC_ASYNC_STATE *
0x180020565  call    ?UnsubscribeChangeNotification@CRpcDispatcher@@SAXPEAU_RPC_ASYNC_STATE@@@Z; CRpcDispatcher::UnsubscribeChangeNotification(_RPC_ASYNC_STATE *)
0x18002056a  lea     rdx, [rsp+0A8h+Reply]; Reply
0x18002056f  mov     rcx, rbx; pAsync
0x180020572  call    cs:__imp_RpcAsyncCompleteCall
0x180020578  nop
0x180020579  lea     rcx, [rsp+0A8h+var_70]
0x18002057e  call    WppTraceUnwinder__lambda_80f882fb2776bdaef0a64b06c9c879ed_______WppTraceUnwinder__lambda_80f882fb2776bdaef0a64b06c9c879ed____
0x180020583  nop
0x180020584  jmp     loc_18002069C
0x180020589  mov     rdx, rdi
0x18002058c  lea     rcx, [rsp+0A8h+var_68]
0x180020591  call    ?Find@CSessionManager@@SA?AV?$shared_ptr@VCClientSession@@@std@@PEAX@Z; CSessionManager::Find(void *)
0x180020596  nop
0x180020597  mov     rcx, [rsp+0A8h+var_68]
0x18002059c  test    rcx, rcx
0x18002059f  jnz     short loc_1800205FD
0x1800205a1  mov     edx, 80070006h; int
0x1800205a6  lea     rcx, [rsp+0A8h+var_88]; this
0x1800205ab  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x1800205b0  nop
0x1800205b1  mov     rcx, [rsp+0A8h+var_60]; this
0x1800205b6  test    rcx, rcx
0x1800205b9  jz      short loc_1800205C1
0x1800205bb  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800205c0  nop
0x1800205c1  lea     rcx, [rsp+0A8h+var_70]
0x1800205c6  call    WppTraceUnwinder__lambda_80f882fb2776bdaef0a64b06c9c879ed_______WppTraceUnwinder__lambda_80f882fb2776bdaef0a64b06c9c879ed____
0x1800205cb  nop
0x1800205cc  mov     edx, 80098004h; int
0x1800205d1  lea     rcx, [rsp+0A8h+var_88]; this
0x1800205d6  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x1800205db  nop
0x1800205dc  mov     rcx, [rsp+0A8h+var_10]
0x1800205e4  xor     rcx, rsp; StackCookie
0x1800205e7  call    __security_check_cookie
0x1800205ec  mov     rbx, [rsp+0A8h+arg_8]
0x1800205f4  add     rsp, 0A0h
0x1800205fb  pop     rdi
0x1800205fc  retn
0x1800205fd  test    ebx, ebx
0x1800205ff  jnz     short loc_180020649
0x180020601  mov     dword ptr [rsp+0A8h+Reply], 80070057h
0x180020609  xor     ebx, ebx
0x18002060b  xchg    rbx, [rsp+0A8h+var_88]
0x180020610  test    rbx, rbx
0x180020613  jz      short loc_18002062C
0x180020615  mov     rcx, rbx; struct _RPC_ASYNC_STATE *
0x180020618  call    ?UnsubscribeChangeNotification@CRpcDispatcher@@SAXPEAU_RPC_ASYNC_STATE@@@Z; CRpcDispatcher::UnsubscribeChangeNotification(_RPC_ASYNC_STATE *)
0x18002061d  lea     rdx, [rsp+0A8h+Reply]; Reply
0x180020622  mov     rcx, rbx; pAsync
0x180020625  call    cs:__imp_RpcAsyncCompleteCall
0x18002062b  nop
0x18002062c  mov     rcx, [rsp+0A8h+var_60]; this
0x180020631  test    rcx, rcx
0x180020634  jz      short loc_18002063C
0x180020636  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002063b  nop
0x18002063c  lea     rcx, [rsp+0A8h+var_70]
0x180020641  call    WppTraceUnwinder__lambda_80f882fb2776bdaef0a64b06c9c879ed_______WppTraceUnwinder__lambda_80f882fb2776bdaef0a64b06c9c879ed____
0x180020646  nop
0x180020647  jmp     short loc_18002069C
0x180020649  add     rcx, 10h; this
0x18002064d  call    ?IsEnrolling@BindingHelper@@QEAA_NXZ; BindingHelper::IsEnrolling(void)
0x180020652  test    al, al
0x180020654  jz      short loc_1800206CC
0x180020656  mov     dword ptr [rsp+0A8h+Reply], 80098007h
0x18002065e  xor     ebx, ebx
0x180020660  xchg    rbx, [rsp+0A8h+var_88]
0x180020665  test    rbx, rbx
0x180020668  jz      short loc_180020681
0x18002066a  mov     rcx, rbx; struct _RPC_ASYNC_STATE *
0x18002066d  call    ?UnsubscribeChangeNotification@CRpcDispatcher@@SAXPEAU_RPC_ASYNC_STATE@@@Z; CRpcDispatcher::UnsubscribeChangeNotification(_RPC_ASYNC_STATE *)
0x180020672  lea     rdx, [rsp+0A8h+Reply]; Reply
0x180020677  mov     rcx, rbx; pAsync
0x18002067a  call    cs:__imp_RpcAsyncCompleteCall
0x180020680  nop
0x180020681  mov     rcx, [rsp+0A8h+var_60]; this
0x180020686  test    rcx, rcx
0x180020689  jz      short loc_180020691
0x18002068b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180020690  nop
0x180020691  lea     rcx, [rsp+0A8h+var_70]
0x180020696  call    WppTraceUnwinder__lambda_80f882fb2776bdaef0a64b06c9c879ed_______WppTraceUnwinder__lambda_80f882fb2776bdaef0a64b06c9c879ed____
0x18002069b  nop
0x18002069c  mov     dword ptr [rsp+0A8h+Reply], 80098004h
0x1800206a4  xor     ebx, ebx
0x1800206a6  xchg    rbx, [rsp+0A8h+var_88]
0x1800206ab  test    rbx, rbx
0x1800206ae  jz      short loc_1800206C7
0x1800206b0  mov     rcx, rbx; struct _RPC_ASYNC_STATE *
0x1800206b3  call    ?UnsubscribeChangeNotification@CRpcDispatcher@@SAXPEAU_RPC_ASYNC_STATE@@@Z; CRpcDispatcher::UnsubscribeChangeNotification(_RPC_ASYNC_STATE *)
0x1800206b8  lea     rdx, [rsp+0A8h+Reply]; Reply
0x1800206bd  mov     rcx, rbx; pAsync
0x1800206c0  call    cs:__imp_RpcAsyncCompleteCall
0x1800206c6  nop
0x1800206c7  jmp     loc_1800205DC
0x1800206cc  mov     rcx, [rsp+0A8h+var_68]
0x1800206d1  add     rcx, 10h; this
0x1800206d5  call    ?IsLocked@BindingHelper@@QEAA_NXZ; BindingHelper::IsLocked(void)
0x1800206da  test    al, al
0x1800206dc  jz      short loc_18002071E
0x1800206de  mov     edx, 8009802Ah; int
0x1800206e3  lea     rcx, [rsp+0A8h+var_88]; this
0x1800206e8  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x1800206ed  nop
0x1800206ee  mov     rcx, [rsp+0A8h+var_60]; this
0x1800206f3  test    rcx, rcx
0x1800206f6  jz      short loc_1800206FE
0x1800206f8  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800206fd  nop
0x1800206fe  lea     rcx, [rsp+0A8h+var_70]
0x180020703  call    WppTraceUnwinder__lambda_80f882fb2776bdaef0a64b06c9c879ed_______WppTraceUnwinder__lambda_80f882fb2776bdaef0a64b06c9c879ed____
0x180020708  nop
0x180020709  mov     edx, 80098004h; int
0x18002070e  lea     rcx, [rsp+0A8h+var_88]; this
0x180020713  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x180020718  nop
0x180020719  jmp     loc_1800205DC
0x18002071e  mov     edx, ebx
0x180020720  lea     rcx, [rsp+0A8h+Reply]
0x180020725  call    ?FindBiometricUnit@CHardwareManager@@SA?AV?$shared_ptr@VCBiometricUnit@@@std@@K@Z; CHardwareManager::FindBiometricUnit(ulong)
0x18002072a  nop
0x18002072b  mov     rcx, [rsp+0A8h+Reply]
0x180020730  test    rcx, rcx
0x180020733  jnz     short loc_180020785
0x180020735  mov     edx, 80098002h; int
0x18002073a  lea     rcx, [rsp+0A8h+var_88]; this
0x18002073f  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x180020744  nop
0x180020745  mov     rcx, [rsp+0A8h+var_78]; this
0x18002074a  test    rcx, rcx
0x18002074d  jz      short loc_180020755
0x18002074f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180020754  nop
0x180020755  mov     rcx, [rsp+0A8h+var_60]; this
0x18002075a  test    rcx, rcx
0x18002075d  jz      short loc_180020765
0x18002075f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180020764  nop
0x180020765  lea     rcx, [rsp+0A8h+var_70]
0x18002076a  call    WppTraceUnwinder__lambda_80f882fb2776bdaef0a64b06c9c879ed_______WppTraceUnwinder__lambda_80f882fb2776bdaef0a64b06c9c879ed____
0x18002076f  nop
0x180020770  mov     edx, 80098004h; int
0x180020775  lea     rcx, [rsp+0A8h+var_88]; this
0x18002077a  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x18002077f  nop
0x180020780  jmp     loc_1800205DC
0x180020785  add     rcx, 10h; this
0x180020789  call    ?IsEnrolling@BindingHelper@@QEAA_NXZ; BindingHelper::IsEnrolling(void)
0x18002078e  test    al, al
0x180020790  jz      short loc_1800207E2
0x180020792  mov     edx, 80098007h; int
0x180020797  lea     rcx, [rsp+0A8h+var_88]; this
0x18002079c  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x1800207a1  nop
0x1800207a2  mov     rcx, [rsp+0A8h+var_78]; this
0x1800207a7  test    rcx, rcx
0x1800207aa  jz      short loc_1800207B2
0x1800207ac  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800207b1  nop
0x1800207b2  mov     rcx, [rsp+0A8h+var_60]; this
0x1800207b7  test    rcx, rcx
0x1800207ba  jz      short loc_1800207C2
0x1800207bc  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800207c1  nop
0x1800207c2  lea     rcx, [rsp+0A8h+var_70]
0x1800207c7  call    WppTraceUnwinder__lambda_80f882fb2776bdaef0a64b06c9c879ed_______WppTraceUnwinder__lambda_80f882fb2776bdaef0a64b06c9c879ed____
0x1800207cc  nop
0x1800207cd  mov     edx, 80098004h; int
0x1800207d2  lea     rcx, [rsp+0A8h+var_88]; this
0x1800207d7  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x1800207dc  nop
0x1800207dd  jmp     loc_1800205DC
0x1800207e2  mov     rcx, [rsp+0A8h+var_78]; this
0x1800207e7  test    rcx, rcx
0x1800207ea  jz      short loc_1800207F2
0x1800207ec  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800207f1  nop
0x1800207f2  mov     ecx, 60h ; '`'; Size
0x1800207f7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800207fc  mov     [rsp+0A8h+Reply], rax
0x180020801  mov     r9d, ebx
0x180020804  lea     r8, [rsp+0A8h+var_68]
0x180020809  lea     rdx, [rsp+0A8h+var_88]
0x18002080e  mov     rcx, rax
0x180020811  call    ??0CWinBioSrvLockUnit@@QEAA@AEAVCRpcAsyncStatePointer@@AEAV?$shared_ptr@VCClientSession@@@std@@K@Z; CWinBioSrvLockUnit::CWinBioSrvLockUnit(CRpcAsyncStatePointer &,std::shared_ptr<CClientSession> &,ulong)
0x180020816  nop
0x180020817  mov     rdx, rax
0x18002081a  lea     rcx, [rsp+0A8h+var_38]
0x18002081f  call    ??$?0VCWinBioSrvGetProperty@@$0A@@?$shared_ptr@VCAsyncWorkItem@@@std@@QEAA@PEAVCWinBioSrvGetProperty@@@Z; std::shared_ptr<CAsyncWorkItem>::shared_ptr<CAsyncWorkItem>(CWinBioSrvGetProperty *)
0x180020824  nop
0x180020825  lea     rdx, [rsp+0A8h+Reply]
0x18002082a  mov     rcx, [rsp+0A8h+var_68]
0x18002082f  call    ?ParentBsp@CClientSession@@QEAA?AV?$shared_ptr@VCBiometricServiceProvider@@@std@@XZ; CClientSession::ParentBsp(void)
0x180020834  nop
0x180020835  mov     rcx, [rsp+0A8h+Reply]
0x18002083a  test    rcx, rcx
0x18002083d  jz      short loc_180020856
0x18002083f  mov     rax, [rcx]
0x180020842  lea     r8, [rsp+0A8h+var_38]
0x180020847  lea     rdx, [rsp+0A8h+var_68]
0x18002084c  mov     rax, [rax+38h]
0x180020850  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020855  nop
0x180020856  mov     rcx, [rsp+0A8h+var_78]; this
0x18002085b  test    rcx, rcx
0x18002085e  jz      short loc_180020866
0x180020860  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180020865  nop
0x180020866  mov     rcx, [rsp+0A8h+var_30]; this
0x18002086b  test    rcx, rcx
0x18002086e  jz      short loc_180020876
0x180020870  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180020875  nop
0x180020876  mov     rcx, [rsp+0A8h+var_60]; this
0x18002087b  test    rcx, rcx
0x18002087e  jz      short loc_180020886
0x180020880  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180020885  nop
0x180020886  lea     rcx, [rsp+0A8h+var_70]
0x18002088b  call    WppTraceUnwinder__lambda_80f882fb2776bdaef0a64b06c9c879ed_______WppTraceUnwinder__lambda_80f882fb2776bdaef0a64b06c9c879ed____
0x180020890  nop
0x180020891  mov     dword ptr [rsp+0A8h+Reply], 80098004h
0x180020899  xor     ebx, ebx
0x18002089b  xchg    rbx, [rsp+0A8h+var_88]
0x1800208a0  test    rbx, rbx
0x1800208a3  jz      short loc_1800208BC
0x1800208a5  mov     rcx, rbx; struct _RPC_ASYNC_STATE *
0x1800208a8  call    ?UnsubscribeChangeNotification@CRpcDispatcher@@SAXPEAU_RPC_ASYNC_STATE@@@Z; CRpcDispatcher::UnsubscribeChangeNotification(_RPC_ASYNC_STATE *)
0x1800208ad  lea     rdx, [rsp+0A8h+Reply]; Reply
0x1800208b2  mov     rcx, rbx; pAsync
0x1800208b5  call    cs:__imp_RpcAsyncCompleteCall
0x1800208bb  nop
0x1800208bc  jmp     loc_1800205DC
```
