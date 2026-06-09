# WinBioSrvEnumEnrollments

- ea: `0x180021560`
- end: `0x180021996`
- name: `WinBioSrvEnumEnrollments`
- size: `1078`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x18000b760`
- `0x18000f090`
- `0x1800118fc`
- `0x18001d730`
- `0x18001fb04`
- `0x180020ca4`
- `0x180020cdc`
- `0x180021560`
- `0x180022abc`
- `0x180022ba4`
- `0x180055928`
- `0x18005d3e0`
- `0x180068f60`
- `0x18006963c`
- `0x180099490`
- `0x180099a2c`
- `0x1800d2010`

## import_xrefs

- `RPCRT4!RpcServerTestCancel` at `0x180021610`
- `RPCRT4!RpcServerTestCancel` at `0x180021610`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180021686`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800216cc`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180021933`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180021686`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800216cc`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180021933`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
RPC_STATUS __fastcall WinBioSrvEnumEnrollments(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  RPC_STATUS result; // eax
  struct _RPC_ASYNC_STATE *v10; // rbx
  struct _RPC_ASYNC_STATE *v11; // rbx
  __int64 v13; // rdx
  const char *v14; // r9
  struct _RPC_ASYNC_STATE *v15; // rbx
  __int64 v16; // [rsp+40h] [rbp-B8h] BYREF
  __int64 v17; // [rsp+48h] [rbp-B0h] BYREF
  char *Reply; // [rsp+50h] [rbp-A8h] BYREF
  std::_Ref_count_base *v19; // [rsp+58h] [rbp-A0h]
  int v20; // [rsp+60h] [rbp-98h] BYREF
  __int64 v21; // [rsp+68h] [rbp-90h] BYREF
  std::_Ref_count_base *v22; // [rsp+70h] [rbp-88h]
  __int64 v23; // [rsp+78h] [rbp-80h] BYREF
  _BYTE v24[16]; // [rsp+80h] [rbp-78h] BYREF
  char v25[8]; // [rsp+90h] [rbp-68h] BYREF
  std::_Ref_count_base *v26; // [rsp+98h] [rbp-60h]
  char v27[32]; // [rsp+A0h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  v23 = a1;
  v16 = _InterlockedExchange64(&v23, 0);
  v20 = 0;
  strcpy(v27, "WinBioSrvEnumEnrollments");
  lambda_afd7ee1b065516bcafbe102d67bfbf3c_::_lambda_afd7ee1b065516bcafbe102d67bfbf3c_(v24, v27, &v20);
  lambda_6d91521182124b45a8169f375e81ecb0_::operator()(v24);
  v20 = 1;
  _lambda_1d8e544947e376896bbe6f02de9fb8f9_::_lambda_1d8e544947e376896bbe6f02de9fb8f9_(&v17, (__int64)v24);
  if ( !RpcServerTestCancel(0) )
  {
    CRpcAsyncStatePointer::CompleteRequest((CRpcAsyncStatePointer *)&v16, -2146861052);
    WppTraceUnwinder__lambda_6d91521182124b45a8169f375e81ecb0____::_WppTraceUnwinder__lambda_6d91521182124b45a8169f375e81ecb0____(&v17);
    return CRpcAsyncStatePointer::CompleteRequest((CRpcAsyncStatePointer *)&v16, -2146861052);
  }
  CSessionManager::Find(&v21, a2);
  if ( !v21 )
  {
    LODWORD(Reply) = -2147024890;
    v10 = (struct _RPC_ASYNC_STATE *)_InterlockedExchange64(&v16, 0);
    if ( v10 )
    {
      CRpcDispatcher::UnsubscribeChangeNotification(v10);
      RpcAsyncCompleteCall(v10, &Reply);
    }
    if ( v22 )
      std::_Ref_count_base::_Decref(v22);
    result = WppTraceUnwinder__lambda_6d91521182124b45a8169f375e81ecb0____::_WppTraceUnwinder__lambda_6d91521182124b45a8169f375e81ecb0____(&v17);
    LODWORD(Reply) = -2146861052;
    v11 = (struct _RPC_ASYNC_STATE *)_InterlockedExchange64(&v16, 0);
    if ( v11 )
    {
      CRpcDispatcher::UnsubscribeChangeNotification(v11);
      return RpcAsyncCompleteCall(v11, &Reply);
    }
    return result;
  }
  if ( !a3 )
  {
    CRpcAsyncStatePointer::CompleteRequest((CRpcAsyncStatePointer *)&v16, -2147024809);
    if ( v22 )
      std::_Ref_count_base::_Decref(v22);
LABEL_33:
    WppTraceUnwinder__lambda_6d91521182124b45a8169f375e81ecb0____::_WppTraceUnwinder__lambda_6d91521182124b45a8169f375e81ecb0____(&v17);
    return CRpcAsyncStatePointer::CompleteRequest((CRpcAsyncStatePointer *)&v16, -2146861052);
  }
  if ( !a4 || !a6 || !a5 )
  {
    CRpcAsyncStatePointer::CompleteRequest((CRpcAsyncStatePointer *)&v16, -2147467261);
    if ( v22 )
      std::_Ref_count_base::_Decref(v22);
    goto LABEL_33;
  }
  if ( BindingHelper::IsEnrolling((BindingHelper *)(v21 + 16)) )
  {
    CRpcAsyncStatePointer::CompleteRequest((CRpcAsyncStatePointer *)&v16, -2146861049);
    if ( v22 )
      std::_Ref_count_base::_Decref(v22);
    goto LABEL_33;
  }
  CHardwareManager::FindBiometricUnit(&Reply, a3);
  if ( !Reply )
  {
    CRpcAsyncStatePointer::CompleteRequest((CRpcAsyncStatePointer *)&v16, -2146861054);
    if ( v19 )
      std::_Ref_count_base::_Decref(v19);
    if ( v22 )
      std::_Ref_count_base::_Decref(v22);
    goto LABEL_33;
  }
  if ( BindingHelper::IsEnrolling((BindingHelper *)(Reply + 16)) )
  {
    CRpcAsyncStatePointer::CompleteRequest((CRpcAsyncStatePointer *)&v16, -2146861049);
    if ( v19 )
      std::_Ref_count_base::_Decref(v19);
    if ( v22 )
      std::_Ref_count_base::_Decref(v22);
    goto LABEL_33;
  }
  if ( v19 )
    std::_Ref_count_base::_Decref(v19);
  try
  {
    Reply = (char *)operator new(0x78u);
    v13 = CWinBioSrvEnumEnrollments::CWinBioSrvEnumEnrollments(
            (_DWORD)Reply,
            (unsigned int)&v16,
            (unsigned int)&v21,
            a3,
            a4,
            a5,
            a6);
    std::shared_ptr<CAsyncWorkItem>::shared_ptr<CAsyncWorkItem>(v25, v13);
    CClientSession::ParentBsp(v21, &Reply);
    if ( Reply )
      (*(void (__fastcall **)(char *, __int64 *, char *))(*(_QWORD *)Reply + 56LL))(Reply, &v21, v25);
    if ( v19 )
      std::_Ref_count_base::_Decref(v19);
    if ( v26 )
      std::_Ref_count_base::_Decref(v26);
    if ( v22 )
      std::_Ref_count_base::_Decref(v22);
    result = WppTraceUnwinder__lambda_6d91521182124b45a8169f375e81ecb0____::_WppTraceUnwinder__lambda_6d91521182124b45a8169f375e81ecb0____(&v17);
  }
  catch ( ... )
  {
    wil::details::in1diag3::FailFast_CaughtException(
      retaddr,
      (void *)0x96C,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\winbiosrv.cpp",
      v14);
  }
  LODWORD(Reply) = -2146861052;
  v15 = (struct _RPC_ASYNC_STATE *)_InterlockedExchange64(&v16, 0);
  if ( v15 )
  {
    CRpcDispatcher::UnsubscribeChangeNotification(v15);
    return RpcAsyncCompleteCall(v15, &Reply);
  }
  return result;
}

```

## disassembly

```asm
0x180021560  mov     r11, rsp
0x180021563  push    rbx
0x180021564  push    rsi
0x180021565  push    rdi
0x180021566  push    r14
0x180021568  push    r15
0x18002156a  sub     rsp, 0D0h
0x180021571  mov     rax, cs:__security_cookie
0x180021578  xor     rax, rsp
0x18002157b  mov     [rsp+0F8h+var_38], rax
0x180021583  mov     rdi, r9
0x180021586  mov     ebx, r8d
0x180021589  mov     r15, rdx
0x18002158c  mov     [r11-80h], rcx
0x180021590  mov     rsi, [rsp+0F8h+arg_20]
0x180021598  mov     r14, [rsp+0F8h+arg_28]
0x1800215a0  mov     [rsp+0F8h+var_B8], 0
0x1800215a9  xor     eax, eax
0x1800215ab  xchg    rax, [r11-80h]
0x1800215af  mov     [rsp+0F8h+var_B8], rax
0x1800215b4  mov     [rsp+0F8h+var_98], 0
0x1800215bc  movups  xmm0, xmmword ptr cs:aWinbiosrvenume; "WinBioSrvEnumEnrollments"
0x1800215c3  movups  xmmword ptr [r11-58h], xmm0
0x1800215c8  movups  xmm1, xmmword ptr cs:aWinbiosrvenume+9; "EnumEnrollments"
0x1800215cf  movups  xmmword ptr [r11-4Fh], xmm1
0x1800215d4  lea     r8, [rsp+0F8h+var_98]
0x1800215d9  lea     rdx, [r11-58h]
0x1800215dd  lea     rcx, [r11-78h]
0x1800215e1  call    _lambda_afd7ee1b065516bcafbe102d67bfbf3c____lambda_afd7ee1b065516bcafbe102d67bfbf3c_
0x1800215e6  lea     rcx, [rsp+0F8h+var_78]
0x1800215ee  call    _lambda_6d91521182124b45a8169f375e81ecb0___operator__
0x1800215f3  mov     [rsp+0F8h+var_98], 1
0x1800215fb  lea     rdx, [rsp+0F8h+var_78]
0x180021603  lea     rcx, [rsp+0F8h+var_B0]
0x180021608  call    ??0_lambda_1d8e544947e376896bbe6f02de9fb8f9_@@QEAA@PEAV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@Z; _lambda_1d8e544947e376896bbe6f02de9fb8f9_::_lambda_1d8e544947e376896bbe6f02de9fb8f9_(nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>> *)
0x18002160d  nop
0x18002160e  xor     ecx, ecx; BindingHandle
0x180021610  call    cs:__imp_RpcServerTestCancel
0x180021616  test    eax, eax
0x180021618  jnz     short loc_18002164A
0x18002161a  mov     edx, 80098004h; int
0x18002161f  lea     rcx, [rsp+0F8h+var_B8]; this
0x180021624  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x180021629  nop
0x18002162a  lea     rcx, [rsp+0F8h+var_B0]
0x18002162f  call    WppTraceUnwinder__lambda_6d91521182124b45a8169f375e81ecb0_______WppTraceUnwinder__lambda_6d91521182124b45a8169f375e81ecb0____
0x180021634  nop
0x180021635  mov     edx, 80098004h; int
0x18002163a  lea     rcx, [rsp+0F8h+var_B8]; this
0x18002163f  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x180021644  nop
0x180021645  jmp     loc_180021977
0x18002164a  mov     rdx, r15
0x18002164d  lea     rcx, [rsp+0F8h+var_90]
0x180021652  call    ?Find@CSessionManager@@SA?AV?$shared_ptr@VCClientSession@@@std@@PEAX@Z; CSessionManager::Find(void *)
0x180021657  nop
0x180021658  mov     rcx, [rsp+0F8h+var_90]
0x18002165d  test    rcx, rcx
0x180021660  jnz     short loc_1800216D8
0x180021662  mov     dword ptr [rsp+0F8h+Reply], 80070006h
0x18002166a  xor     ebx, ebx
0x18002166c  xchg    rbx, [rsp+0F8h+var_B8]
0x180021671  test    rbx, rbx
0x180021674  jz      short loc_18002168D
0x180021676  mov     rcx, rbx; struct _RPC_ASYNC_STATE *
0x180021679  call    ?UnsubscribeChangeNotification@CRpcDispatcher@@SAXPEAU_RPC_ASYNC_STATE@@@Z; CRpcDispatcher::UnsubscribeChangeNotification(_RPC_ASYNC_STATE *)
0x18002167e  lea     rdx, [rsp+0F8h+Reply]; Reply
0x180021683  mov     rcx, rbx; pAsync
0x180021686  call    cs:__imp_RpcAsyncCompleteCall
0x18002168c  nop
0x18002168d  mov     rcx, [rsp+0F8h+var_88]; this
0x180021692  test    rcx, rcx
0x180021695  jz      short loc_18002169D
0x180021697  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002169c  nop
0x18002169d  lea     rcx, [rsp+0F8h+var_B0]
0x1800216a2  call    WppTraceUnwinder__lambda_6d91521182124b45a8169f375e81ecb0_______WppTraceUnwinder__lambda_6d91521182124b45a8169f375e81ecb0____
0x1800216a7  nop
0x1800216a8  mov     dword ptr [rsp+0F8h+Reply], 80098004h
0x1800216b0  xor     ebx, ebx
0x1800216b2  xchg    rbx, [rsp+0F8h+var_B8]
0x1800216b7  test    rbx, rbx
0x1800216ba  jz      short loc_1800216D3
0x1800216bc  mov     rcx, rbx; struct _RPC_ASYNC_STATE *
0x1800216bf  call    ?UnsubscribeChangeNotification@CRpcDispatcher@@SAXPEAU_RPC_ASYNC_STATE@@@Z; CRpcDispatcher::UnsubscribeChangeNotification(_RPC_ASYNC_STATE *)
0x1800216c4  lea     rdx, [rsp+0F8h+Reply]; Reply
0x1800216c9  mov     rcx, rbx; pAsync
0x1800216cc  call    cs:__imp_RpcAsyncCompleteCall
0x1800216d2  nop
0x1800216d3  jmp     loc_180021977
0x1800216d8  test    ebx, ebx
0x1800216da  jnz     short loc_18002171C
0x1800216dc  mov     edx, 80070057h; int
0x1800216e1  lea     rcx, [rsp+0F8h+var_B8]; this
0x1800216e6  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x1800216eb  nop
0x1800216ec  mov     rcx, [rsp+0F8h+var_88]; this
0x1800216f1  test    rcx, rcx
0x1800216f4  jz      short loc_1800216FC
0x1800216f6  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800216fb  nop
0x1800216fc  lea     rcx, [rsp+0F8h+var_B0]
0x180021701  call    WppTraceUnwinder__lambda_6d91521182124b45a8169f375e81ecb0_______WppTraceUnwinder__lambda_6d91521182124b45a8169f375e81ecb0____
0x180021706  nop
0x180021707  mov     edx, 80098004h; int
0x18002170c  lea     rcx, [rsp+0F8h+var_B8]; this
0x180021711  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x180021716  nop
0x180021717  jmp     loc_180021977
0x18002171c  test    rdi, rdi
0x18002171f  jz      loc_18002193C
0x180021725  test    r14, r14
0x180021728  jz      loc_18002193C
0x18002172e  test    rsi, rsi
0x180021731  jz      loc_18002193C
0x180021737  add     rcx, 10h; this
0x18002173b  call    ?IsEnrolling@BindingHelper@@QEAA_NXZ; BindingHelper::IsEnrolling(void)
0x180021740  test    al, al
0x180021742  jz      short loc_180021784
0x180021744  mov     edx, 80098007h; int
0x180021749  lea     rcx, [rsp+0F8h+var_B8]; this
0x18002174e  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x180021753  nop
0x180021754  mov     rcx, [rsp+0F8h+var_88]; this
0x180021759  test    rcx, rcx
0x18002175c  jz      short loc_180021764
0x18002175e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180021763  nop
0x180021764  lea     rcx, [rsp+0F8h+var_B0]
0x180021769  call    WppTraceUnwinder__lambda_6d91521182124b45a8169f375e81ecb0_______WppTraceUnwinder__lambda_6d91521182124b45a8169f375e81ecb0____
0x18002176e  nop
0x18002176f  mov     edx, 80098004h; int
0x180021774  lea     rcx, [rsp+0F8h+var_B8]; this
0x180021779  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x18002177e  nop
0x18002177f  jmp     loc_180021977
0x180021784  mov     edx, ebx
0x180021786  lea     rcx, [rsp+0F8h+Reply]
0x18002178b  call    ?FindBiometricUnit@CHardwareManager@@SA?AV?$shared_ptr@VCBiometricUnit@@@std@@K@Z; CHardwareManager::FindBiometricUnit(ulong)
0x180021790  nop
0x180021791  mov     rcx, [rsp+0F8h+Reply]
0x180021796  test    rcx, rcx
0x180021799  jnz     short loc_1800217EB
0x18002179b  mov     edx, 80098002h; int
0x1800217a0  lea     rcx, [rsp+0F8h+var_B8]; this
0x1800217a5  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x1800217aa  nop
0x1800217ab  mov     rcx, [rsp+0F8h+var_A0]; this
0x1800217b0  test    rcx, rcx
0x1800217b3  jz      short loc_1800217BB
0x1800217b5  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800217ba  nop
0x1800217bb  mov     rcx, [rsp+0F8h+var_88]; this
0x1800217c0  test    rcx, rcx
0x1800217c3  jz      short loc_1800217CB
0x1800217c5  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800217ca  nop
0x1800217cb  lea     rcx, [rsp+0F8h+var_B0]
0x1800217d0  call    WppTraceUnwinder__lambda_6d91521182124b45a8169f375e81ecb0_______WppTraceUnwinder__lambda_6d91521182124b45a8169f375e81ecb0____
0x1800217d5  nop
0x1800217d6  mov     edx, 80098004h; int
0x1800217db  lea     rcx, [rsp+0F8h+var_B8]; this
0x1800217e0  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x1800217e5  nop
0x1800217e6  jmp     loc_180021977
0x1800217eb  add     rcx, 10h; this
0x1800217ef  call    ?IsEnrolling@BindingHelper@@QEAA_NXZ; BindingHelper::IsEnrolling(void)
0x1800217f4  test    al, al
0x1800217f6  jz      short loc_180021848
0x1800217f8  mov     edx, 80098007h; int
0x1800217fd  lea     rcx, [rsp+0F8h+var_B8]; this
0x180021802  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x180021807  nop
0x180021808  mov     rcx, [rsp+0F8h+var_A0]; this
0x18002180d  test    rcx, rcx
0x180021810  jz      short loc_180021818
0x180021812  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180021817  nop
0x180021818  mov     rcx, [rsp+0F8h+var_88]; this
0x18002181d  test    rcx, rcx
0x180021820  jz      short loc_180021828
0x180021822  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180021827  nop
0x180021828  lea     rcx, [rsp+0F8h+var_B0]
0x18002182d  call    WppTraceUnwinder__lambda_6d91521182124b45a8169f375e81ecb0_______WppTraceUnwinder__lambda_6d91521182124b45a8169f375e81ecb0____
0x180021832  nop
0x180021833  mov     edx, 80098004h; int
0x180021838  lea     rcx, [rsp+0F8h+var_B8]; this
0x18002183d  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x180021842  nop
0x180021843  jmp     loc_180021977
0x180021848  mov     rcx, [rsp+0F8h+var_A0]; this
0x18002184d  test    rcx, rcx
0x180021850  jz      short loc_180021858
0x180021852  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180021857  nop
0x180021858  mov     ecx, 78h ; 'x'; Size
0x18002185d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180021862  mov     [rsp+0F8h+Reply], rax
0x180021867  mov     [rsp+0F8h+var_C8], r14
0x18002186c  mov     [rsp+0F8h+var_D0], rsi
0x180021871  mov     [rsp+0F8h+var_D8], rdi
0x180021876  mov     r9d, ebx
0x180021879  lea     r8, [rsp+0F8h+var_90]
0x18002187e  lea     rdx, [rsp+0F8h+var_B8]
0x180021883  mov     rcx, rax
0x180021886  call    ??0CWinBioSrvEnumEnrollments@@QEAA@AEAVCRpcAsyncStatePointer@@AEAV?$shared_ptr@VCClientSession@@@std@@KPEAU_WINBIO_IDENTITY@@PEAKPEAPEAE@Z; CWinBioSrvEnumEnrollments::CWinBioSrvEnumEnrollments(CRpcAsyncStatePointer &,std::shared_ptr<CClientSession> &,ulong,_WINBIO_IDENTITY *,ulong *,uchar * *)
0x18002188b  nop
0x18002188c  mov     rdx, rax
0x18002188f  lea     rcx, [rsp+0F8h+var_68]
0x180021897  call    ??$?0VCWinBioSrvGetProperty@@$0A@@?$shared_ptr@VCAsyncWorkItem@@@std@@QEAA@PEAVCWinBioSrvGetProperty@@@Z; std::shared_ptr<CAsyncWorkItem>::shared_ptr<CAsyncWorkItem>(CWinBioSrvGetProperty *)
0x18002189c  nop
0x18002189d  lea     rdx, [rsp+0F8h+Reply]
0x1800218a2  mov     rcx, [rsp+0F8h+var_90]
0x1800218a7  call    ?ParentBsp@CClientSession@@QEAA?AV?$shared_ptr@VCBiometricServiceProvider@@@std@@XZ; CClientSession::ParentBsp(void)
0x1800218ac  nop
0x1800218ad  mov     rcx, [rsp+0F8h+Reply]
0x1800218b2  test    rcx, rcx
0x1800218b5  jz      short loc_1800218D1
0x1800218b7  mov     rax, [rcx]
0x1800218ba  lea     r8, [rsp+0F8h+var_68]
0x1800218c2  lea     rdx, [rsp+0F8h+var_90]
0x1800218c7  mov     rax, [rax+38h]
0x1800218cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800218d0  nop
0x1800218d1  mov     rcx, [rsp+0F8h+var_A0]; this
0x1800218d6  test    rcx, rcx
0x1800218d9  jz      short loc_1800218E1
0x1800218db  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800218e0  nop
0x1800218e1  mov     rcx, [rsp+0F8h+var_60]; this
0x1800218e9  test    rcx, rcx
0x1800218ec  jz      short loc_1800218F4
0x1800218ee  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800218f3  nop
0x1800218f4  mov     rcx, [rsp+0F8h+var_88]; this
0x1800218f9  test    rcx, rcx
0x1800218fc  jz      short loc_180021904
0x1800218fe  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180021903  nop
0x180021904  lea     rcx, [rsp+0F8h+var_B0]
0x180021909  call    WppTraceUnwinder__lambda_6d91521182124b45a8169f375e81ecb0_______WppTraceUnwinder__lambda_6d91521182124b45a8169f375e81ecb0____
0x18002190e  nop
0x18002190f  mov     dword ptr [rsp+0F8h+Reply], 80098004h
0x180021917  xor     ebx, ebx
0x180021919  xchg    rbx, [rsp+0F8h+var_B8]
0x18002191e  test    rbx, rbx
0x180021921  jz      short loc_18002193A
0x180021923  mov     rcx, rbx; struct _RPC_ASYNC_STATE *
0x180021926  call    ?UnsubscribeChangeNotification@CRpcDispatcher@@SAXPEAU_RPC_ASYNC_STATE@@@Z; CRpcDispatcher::UnsubscribeChangeNotification(_RPC_ASYNC_STATE *)
0x18002192b  lea     rdx, [rsp+0F8h+Reply]; Reply
0x180021930  mov     rcx, rbx; pAsync
0x180021933  call    cs:__imp_RpcAsyncCompleteCall
0x180021939  nop
0x18002193a  jmp     short loc_180021977
0x18002193c  mov     edx, 80004003h; int
0x180021941  lea     rcx, [rsp+0F8h+var_B8]; this
0x180021946  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x18002194b  nop
0x18002194c  mov     rcx, [rsp+0F8h+var_88]; this
0x180021951  test    rcx, rcx
0x180021954  jz      short loc_18002195C
0x180021956  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002195b  nop
0x18002195c  lea     rcx, [rsp+0F8h+var_B0]
0x180021961  call    WppTraceUnwinder__lambda_6d91521182124b45a8169f375e81ecb0_______WppTraceUnwinder__lambda_6d91521182124b45a8169f375e81ecb0____
0x180021966  nop
0x180021967  mov     edx, 80098004h; int
0x18002196c  lea     rcx, [rsp+0F8h+var_B8]; this
0x180021971  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x180021976  nop
0x180021977  mov     rcx, [rsp+0F8h+var_38]
0x18002197f  xor     rcx, rsp; StackCookie
0x180021982  call    __security_check_cookie
0x180021987  add     rsp, 0D0h
0x18002198e  pop     r15
0x180021990  pop     r14
0x180021992  pop     rdi
0x180021993  pop     rsi
0x180021994  pop     rbx
0x180021995  retn
```
