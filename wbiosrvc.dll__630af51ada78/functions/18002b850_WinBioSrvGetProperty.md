# WinBioSrvGetProperty

- ea: `0x18002b850`
- end: `0x18002bf40`
- name: `WinBioSrvGetProperty`
- size: `1776`
- prototype: `RPC_STATUS __fastcall(__int64, __int64, int, int, unsigned int, struct _WINBIO_IDENTITY *, unsigned __int8, _DWORD *, std::_Ref_count_base **)`
- caller_count: `0`
- callee_count: `20`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x18000b760`
- `0x18000eed0`
- `0x1800118fc`
- `0x1800119c4`
- `0x18001d730`
- `0x18001fb04`
- `0x180020ca4`
- `0x180020cdc`
- `0x180022ba4`
- `0x18002b850`
- `0x18002bf48`
- `0x18002c040`
- `0x18002c420`
- `0x180055928`
- `0x18005d3e0`
- `0x180068f60`
- `0x18006963c`
- `0x180099550`
- `0x180099dd8`
- `0x1800d2010`

## import_xrefs

- `RPCRT4!RpcServerTestCancel` at `0x18002b91d`
- `RPCRT4!RpcServerTestCancel` at `0x18002b91d`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18002bc68`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18002bcaf`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18002be89`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18002bc68`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18002bcaf`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18002be89`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
RPC_STATUS __fastcall WinBioSrvGetProperty(
        __int64 a1,
        __int64 a2,
        int a3,
        int a4,
        unsigned int a5,
        struct _WINBIO_IDENTITY *a6,
        unsigned __int8 a7,
        _DWORD *a8,
        std::_Ref_count_base **a9)
{
  RPC_STATUS result; // eax
  int v13; // eax
  struct _RPC_ASYNC_STATE *v14; // rbx
  struct _RPC_ASYNC_STATE *v15; // rbx
  int v16; // eax
  __int64 Property; // rdx
  const char *v18; // r9
  struct _RPC_ASYNC_STATE *v19; // rbx
  __int64 v20; // [rsp+40h] [rbp-C8h] BYREF
  _BYTE v21[8]; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v22; // [rsp+50h] [rbp-B8h] BYREF
  std::_Ref_count_base *v23; // [rsp+58h] [rbp-B0h]
  __int128 Reply; // [rsp+60h] [rbp-A8h] BYREF
  std::_Ref_count_base *v25[2]; // [rsp+70h] [rbp-98h] BYREF
  int v26; // [rsp+80h] [rbp-88h] BYREF
  __int64 v27; // [rsp+88h] [rbp-80h] BYREF
  std::_Ref_count_base **v28; // [rsp+90h] [rbp-78h] BYREF
  std::_Ref_count_base *v29; // [rsp+98h] [rbp-70h]
  _BYTE v30[16]; // [rsp+A0h] [rbp-68h] BYREF
  char v31[24]; // [rsp+B0h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  v27 = a1;
  v20 = _InterlockedExchange64(&v27, 0);
  v26 = 0;
  strcpy(v31, "WinBioSrvGetProperty");
  lambda_afd7ee1b065516bcafbe102d67bfbf3c_::_lambda_afd7ee1b065516bcafbe102d67bfbf3c_(v30, v31, &v26);
  lambda_8fef55889fcce4085fc6cc0b1112a47c_::operator()(v30);
  v26 = 1;
  _lambda_1d8e544947e376896bbe6f02de9fb8f9_::_lambda_1d8e544947e376896bbe6f02de9fb8f9_(v21, v30);
  if ( !RpcServerTestCancel(0) )
  {
    CRpcAsyncStatePointer::CompleteRequest((CRpcAsyncStatePointer *)&v20, -2146861052);
    WppTraceUnwinder__lambda_8fef55889fcce4085fc6cc0b1112a47c____::_WppTraceUnwinder__lambda_8fef55889fcce4085fc6cc0b1112a47c____(v21);
    return CRpcAsyncStatePointer::CompleteRequest((CRpcAsyncStatePointer *)&v20, -2146861052);
  }
  CSessionManager::Find(&v22, a2);
  if ( !v22 )
  {
    CRpcAsyncStatePointer::CompleteRequest((CRpcAsyncStatePointer *)&v20, -2147024890);
    if ( v23 )
      std::_Ref_count_base::_Decref(v23);
LABEL_81:
    WppTraceUnwinder__lambda_8fef55889fcce4085fc6cc0b1112a47c____::_WppTraceUnwinder__lambda_8fef55889fcce4085fc6cc0b1112a47c____(v21);
    return CRpcAsyncStatePointer::CompleteRequest((CRpcAsyncStatePointer *)&v20, -2146861052);
  }
  if ( !a9 || !a8 )
  {
    CRpcAsyncStatePointer::CompleteRequest((CRpcAsyncStatePointer *)&v20, -2147467261);
    if ( v23 )
      std::_Ref_count_base::_Decref(v23);
    goto LABEL_81;
  }
  if ( a3 == 2 )
  {
    if ( BindingHelper::IsLocked((BindingHelper *)(v22 + 16)) )
    {
      CRpcAsyncStatePointer::CompleteRequest((CRpcAsyncStatePointer *)&v20, -2146861014);
      if ( v23 )
        std::_Ref_count_base::_Decref(v23);
      goto LABEL_81;
    }
    CHardwareManager::FindBiometricUnit(v25, a5);
    if ( !v25[0] )
    {
      CRpcAsyncStatePointer::CompleteRequest((CRpcAsyncStatePointer *)&v20, -2146861054);
      if ( v25[1] )
        std::_Ref_count_base::_Decref(v25[1]);
      if ( v23 )
        std::_Ref_count_base::_Decref(v23);
      goto LABEL_81;
    }
    if ( BindingHelper::IsLocked((std::_Ref_count_base *)((char *)v25[0] + 16)) )
    {
      CRpcAsyncStatePointer::CompleteRequest((CRpcAsyncStatePointer *)&v20, -2146861014);
      if ( v25[1] )
        std::_Ref_count_base::_Decref(v25[1]);
      if ( v23 )
        std::_Ref_count_base::_Decref(v23);
      goto LABEL_81;
    }
    if ( v25[1] )
      std::_Ref_count_base::_Decref(v25[1]);
  }
  else if ( a3 == 1 && a4 == 8 )
  {
    if ( a5 || a7 || a6 )
    {
      CRpcAsyncStatePointer::CompleteRequest((CRpcAsyncStatePointer *)&v20, -2146861012);
      if ( v23 )
        std::_Ref_count_base::_Decref(v23);
      goto LABEL_81;
    }
    v25[0] = (std::_Ref_count_base *)MIDL_user_allocate(8u);
    if ( !v25[0] )
    {
      CRpcAsyncStatePointer::CompleteRequest((CRpcAsyncStatePointer *)&v20, -2147024882);
      if ( v23 )
        std::_Ref_count_base::_Decref(v23);
      goto LABEL_81;
    }
    v28 = v25;
    LOBYTE(v29) = 1;
    LODWORD(Reply) = *((unsigned __int8 *)CHardwareManager::Instance() + 185);
    DWORD1(Reply) = *((_DWORD *)CHardwareManager::Instance() + 47);
    *(_QWORD *)v25[0] = Reply;
    *a9 = v25[0];
    *a8 = 8;
    LODWORD(Reply) = 0;
    v14 = (struct _RPC_ASYNC_STATE *)_InterlockedExchange64(&v20, 0);
    if ( v14 )
    {
      CRpcDispatcher::UnsubscribeChangeNotification(v14);
      RpcAsyncCompleteCall(v14, &Reply);
    }
    if ( v23 )
      std::_Ref_count_base::_Decref(v23);
    result = WppTraceUnwinder__lambda_8fef55889fcce4085fc6cc0b1112a47c____::_WppTraceUnwinder__lambda_8fef55889fcce4085fc6cc0b1112a47c____(v21);
    LODWORD(Reply) = -2146861052;
    v15 = (struct _RPC_ASYNC_STATE *)_InterlockedExchange64(&v20, 0);
    if ( v15 )
    {
      CRpcDispatcher::UnsubscribeChangeNotification(v15);
      return RpcAsyncCompleteCall(v15, &Reply);
    }
    return result;
  }
  Reply = 0;
  v13 = WinBioProperty::Create(a3, a4, a5, a6, a7, &Reply);
  if ( v13 < 0 )
  {
    CRpcAsyncStatePointer::CompleteRequest((CRpcAsyncStatePointer *)&v20, v13);
    if ( *((_QWORD *)&Reply + 1) )
      std::_Ref_count_base::_Decref(*((std::_Ref_count_base **)&Reply + 1));
    if ( v23 )
      std::_Ref_count_base::_Decref(v23);
    goto LABEL_81;
  }
  if ( !*(_DWORD *)(Reply + 16) )
  {
    *(_OWORD *)v25 = 0;
    v16 = (*(__int64 (__fastcall **)(_QWORD, __int64 *, std::_Ref_count_base **, std::_Ref_count_base **, _DWORD *))(*(_QWORD *)Reply + 16LL))(
            Reply,
            &v22,
            v25,
            a9,
            a8);
    CRpcAsyncStatePointer::CompleteRequest((CRpcAsyncStatePointer *)&v20, v16);
    if ( v25[1] )
      std::_Ref_count_base::_Decref(v25[1]);
    if ( *((_QWORD *)&Reply + 1) )
      std::_Ref_count_base::_Decref(*((std::_Ref_count_base **)&Reply + 1));
    if ( v23 )
      std::_Ref_count_base::_Decref(v23);
    goto LABEL_81;
  }
  if ( *(_DWORD *)(Reply + 16) != 1 )
  {
    CRpcAsyncStatePointer::CompleteRequest((CRpcAsyncStatePointer *)&v20, -2147023537);
    if ( *((_QWORD *)&Reply + 1) )
      std::_Ref_count_base::_Decref(*((std::_Ref_count_base **)&Reply + 1));
    if ( v23 )
      std::_Ref_count_base::_Decref(v23);
    goto LABEL_81;
  }
  try
  {
    v25[0] = (std::_Ref_count_base *)operator new(0x98u);
    Property = CWinBioSrvGetProperty::CWinBioSrvGetProperty(
                 v25[0],
                 (unsigned int)&v20,
                 (unsigned int)&v22,
                 a5,
                 (__int64)&Reply,
                 (__int64)a8,
                 (__int64)a9);
    std::shared_ptr<CAsyncWorkItem>::shared_ptr<CAsyncWorkItem>(&v28, Property);
    CClientSession::ParentBsp(v22, v25);
    if ( v25[0] )
      (*(void (__fastcall **)(std::_Ref_count_base *, __int64 *, std::_Ref_count_base ***))(*(_QWORD *)v25[0] + 56LL))(
        v25[0],
        &v22,
        &v28);
    if ( v25[1] )
      std::_Ref_count_base::_Decref(v25[1]);
    if ( v29 )
      std::_Ref_count_base::_Decref(v29);
    if ( *((_QWORD *)&Reply + 1) )
      std::_Ref_count_base::_Decref(*((std::_Ref_count_base **)&Reply + 1));
    if ( v23 )
      std::_Ref_count_base::_Decref(v23);
    result = WppTraceUnwinder__lambda_8fef55889fcce4085fc6cc0b1112a47c____::_WppTraceUnwinder__lambda_8fef55889fcce4085fc6cc0b1112a47c____(v21);
  }
  catch ( ... )
  {
    wil::details::in1diag3::FailFast_CaughtException(
      retaddr,
      (void *)0xE87,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\winbiosrv.cpp",
      v18);
  }
  LODWORD(Reply) = -2146861052;
  v19 = (struct _RPC_ASYNC_STATE *)_InterlockedExchange64(&v20, 0);
  if ( v19 )
  {
    CRpcDispatcher::UnsubscribeChangeNotification(v19);
    return RpcAsyncCompleteCall(v19, &Reply);
  }
  return result;
}

```

## disassembly

```asm
0x18002b850  mov     r11, rsp
0x18002b853  push    rbx
0x18002b854  push    rsi
0x18002b855  push    rdi
0x18002b856  push    r12
0x18002b858  push    r13
0x18002b85a  push    r14
0x18002b85c  push    r15
0x18002b85e  sub     rsp, 0D0h
0x18002b865  mov     rax, cs:__security_cookie
0x18002b86c  xor     rax, rsp
0x18002b86f  mov     [rsp+108h+var_40], rax
0x18002b877  mov     r12d, r9d
0x18002b87a  mov     r14d, r8d
0x18002b87d  mov     r13, rdx
0x18002b880  mov     [r11-80h], rcx
0x18002b884  mov     ebx, [rsp+108h+arg_20]
0x18002b88b  mov     r15, [rsp+108h+arg_28]
0x18002b893  mov     rdi, [rsp+108h+arg_38]
0x18002b89b  mov     rsi, [rsp+108h+arg_40]
0x18002b8a3  mov     [rsp+108h+var_C8], 0
0x18002b8ac  xor     eax, eax
0x18002b8ae  xchg    rax, [r11-80h]
0x18002b8b2  mov     [rsp+108h+var_C8], rax
0x18002b8b7  mov     [rsp+108h+var_88], 0
0x18002b8c2  movups  xmm0, xmmword ptr cs:aWinbiosrvgetpr; "WinBioSrvGetProperty"
0x18002b8c9  movups  xmmword ptr [r11-58h], xmm0
0x18002b8ce  movsd   xmm1, qword ptr cs:aWinbiosrvgetpr+0Dh; "roperty"
0x18002b8d6  movsd   qword ptr [r11-4Bh], xmm1
0x18002b8dc  lea     r8, [r11-88h]
0x18002b8e3  lea     rdx, [r11-58h]
0x18002b8e7  lea     rcx, [r11-68h]
0x18002b8eb  call    _lambda_afd7ee1b065516bcafbe102d67bfbf3c____lambda_afd7ee1b065516bcafbe102d67bfbf3c_
0x18002b8f0  lea     rcx, [rsp+108h+var_68]
0x18002b8f8  call    _lambda_8fef55889fcce4085fc6cc0b1112a47c___operator__
0x18002b8fd  mov     [rsp+108h+var_88], 1
0x18002b908  lea     rdx, [rsp+108h+var_68]
0x18002b910  lea     rcx, [rsp+108h+var_C0]
0x18002b915  call    ??0_lambda_1d8e544947e376896bbe6f02de9fb8f9_@@QEAA@PEAV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@Z; _lambda_1d8e544947e376896bbe6f02de9fb8f9_::_lambda_1d8e544947e376896bbe6f02de9fb8f9_(nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>> *)
0x18002b91a  nop
0x18002b91b  xor     ecx, ecx; BindingHandle
0x18002b91d  call    cs:__imp_RpcServerTestCancel
0x18002b923  test    eax, eax
0x18002b925  jnz     short loc_18002B957
0x18002b927  mov     edx, 80098004h; int
0x18002b92c  lea     rcx, [rsp+108h+var_C8]; this
0x18002b931  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x18002b936  nop
0x18002b937  lea     rcx, [rsp+108h+var_C0]
0x18002b93c  call    WppTraceUnwinder__lambda_8fef55889fcce4085fc6cc0b1112a47c_______WppTraceUnwinder__lambda_8fef55889fcce4085fc6cc0b1112a47c____
0x18002b941  nop
0x18002b942  mov     edx, 80098004h; int
0x18002b947  lea     rcx, [rsp+108h+var_C8]; this
0x18002b94c  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x18002b951  nop
0x18002b952  jmp     loc_18002BF1D
0x18002b957  mov     rdx, r13
0x18002b95a  lea     rcx, [rsp+108h+var_B8]
0x18002b95f  call    ?Find@CSessionManager@@SA?AV?$shared_ptr@VCClientSession@@@std@@PEAX@Z; CSessionManager::Find(void *)
0x18002b964  nop
0x18002b965  mov     rcx, [rsp+108h+var_B8]
0x18002b96a  xor     r13d, r13d
0x18002b96d  test    rcx, rcx
0x18002b970  jnz     short loc_18002B9B2
0x18002b972  mov     edx, 80070006h; int
0x18002b977  lea     rcx, [rsp+108h+var_C8]; this
0x18002b97c  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x18002b981  nop
0x18002b982  mov     rcx, [rsp+108h+var_B0]; this
0x18002b987  test    rcx, rcx
0x18002b98a  jz      short loc_18002B992
0x18002b98c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002b991  nop
0x18002b992  lea     rcx, [rsp+108h+var_C0]
0x18002b997  call    WppTraceUnwinder__lambda_8fef55889fcce4085fc6cc0b1112a47c_______WppTraceUnwinder__lambda_8fef55889fcce4085fc6cc0b1112a47c____
0x18002b99c  nop
0x18002b99d  mov     edx, 80098004h; int
0x18002b9a2  lea     rcx, [rsp+108h+var_C8]; this
0x18002b9a7  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x18002b9ac  nop
0x18002b9ad  jmp     loc_18002BF1D
0x18002b9b2  test    rsi, rsi
0x18002b9b5  jz      loc_18002BEE2
0x18002b9bb  test    rdi, rdi
0x18002b9be  jz      loc_18002BEE2
0x18002b9c4  cmp     r14d, 2
0x18002b9c8  jnz     loc_18002BB72
0x18002b9ce  add     rcx, 10h; this
0x18002b9d2  call    ?IsLocked@BindingHelper@@QEAA_NXZ; BindingHelper::IsLocked(void)
0x18002b9d7  test    al, al
0x18002b9d9  jz      short loc_18002BA1B
0x18002b9db  mov     edx, 8009802Ah; int
0x18002b9e0  lea     rcx, [rsp+108h+var_C8]; this
0x18002b9e5  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x18002b9ea  nop
0x18002b9eb  mov     rcx, [rsp+108h+var_B0]; this
0x18002b9f0  test    rcx, rcx
0x18002b9f3  jz      short loc_18002B9FB
0x18002b9f5  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002b9fa  nop
0x18002b9fb  lea     rcx, [rsp+108h+var_C0]
0x18002ba00  call    WppTraceUnwinder__lambda_8fef55889fcce4085fc6cc0b1112a47c_______WppTraceUnwinder__lambda_8fef55889fcce4085fc6cc0b1112a47c____
0x18002ba05  nop
0x18002ba06  mov     edx, 80098004h; int
0x18002ba0b  lea     rcx, [rsp+108h+var_C8]; this
0x18002ba10  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x18002ba15  nop
0x18002ba16  jmp     loc_18002BF1D
0x18002ba1b  mov     edx, ebx
0x18002ba1d  lea     rcx, [rsp+108h+var_98]
0x18002ba22  call    ?FindBiometricUnit@CHardwareManager@@SA?AV?$shared_ptr@VCBiometricUnit@@@std@@K@Z; CHardwareManager::FindBiometricUnit(ulong)
0x18002ba27  nop
0x18002ba28  mov     rcx, [rsp+108h+var_98]
0x18002ba2d  test    rcx, rcx
0x18002ba30  jnz     short loc_18002BA82
0x18002ba32  mov     edx, 80098002h; int
0x18002ba37  lea     rcx, [rsp+108h+var_C8]; this
0x18002ba3c  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x18002ba41  nop
0x18002ba42  mov     rcx, [rsp+108h+var_98+8]; this
0x18002ba47  test    rcx, rcx
0x18002ba4a  jz      short loc_18002BA52
0x18002ba4c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002ba51  nop
0x18002ba52  mov     rcx, [rsp+108h+var_B0]; this
0x18002ba57  test    rcx, rcx
0x18002ba5a  jz      short loc_18002BA62
0x18002ba5c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002ba61  nop
0x18002ba62  lea     rcx, [rsp+108h+var_C0]
0x18002ba67  call    WppTraceUnwinder__lambda_8fef55889fcce4085fc6cc0b1112a47c_______WppTraceUnwinder__lambda_8fef55889fcce4085fc6cc0b1112a47c____
0x18002ba6c  nop
0x18002ba6d  mov     edx, 80098004h; int
0x18002ba72  lea     rcx, [rsp+108h+var_C8]; this
0x18002ba77  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x18002ba7c  nop
0x18002ba7d  jmp     loc_18002BF1D
0x18002ba82  add     rcx, 10h; this
0x18002ba86  call    ?IsLocked@BindingHelper@@QEAA_NXZ; BindingHelper::IsLocked(void)
0x18002ba8b  test    al, al
0x18002ba8d  jz      short loc_18002BADF
0x18002ba8f  mov     edx, 8009802Ah; int
0x18002ba94  lea     rcx, [rsp+108h+var_C8]; this
0x18002ba99  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x18002ba9e  nop
0x18002ba9f  mov     rcx, [rsp+108h+var_98+8]; this
0x18002baa4  test    rcx, rcx
0x18002baa7  jz      short loc_18002BAAF
0x18002baa9  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002baae  nop
0x18002baaf  mov     rcx, [rsp+108h+var_B0]; this
0x18002bab4  test    rcx, rcx
0x18002bab7  jz      short loc_18002BABF
0x18002bab9  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002babe  nop
0x18002babf  lea     rcx, [rsp+108h+var_C0]
0x18002bac4  call    WppTraceUnwinder__lambda_8fef55889fcce4085fc6cc0b1112a47c_______WppTraceUnwinder__lambda_8fef55889fcce4085fc6cc0b1112a47c____
0x18002bac9  nop
0x18002baca  mov     edx, 80098004h; int
0x18002bacf  lea     rcx, [rsp+108h+var_C8]; this
0x18002bad4  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x18002bad9  nop
0x18002bada  jmp     loc_18002BF1D
0x18002badf  mov     rcx, [rsp+108h+var_98+8]; this
0x18002bae4  test    rcx, rcx
0x18002bae7  jz      short loc_18002BAEE
0x18002bae9  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002baee  xorps   xmm0, xmm0
0x18002baf1  movdqu  [rsp+108h+Reply], xmm0
0x18002baf7  lea     rax, [rsp+108h+Reply]
0x18002bafc  mov     [rsp+108h+var_E0], rax
0x18002bb01  mov     al, [rsp+108h+arg_30]
0x18002bb08  mov     byte ptr [rsp+108h+var_E8], al
0x18002bb0c  mov     r9, r15
0x18002bb0f  mov     r8d, ebx
0x18002bb12  mov     edx, r12d
0x18002bb15  mov     ecx, r14d
0x18002bb18  call    ?Create@WinBioProperty@@YAJIIKPEAU_WINBIO_IDENTITY@@EAEAV?$shared_ptr@VBase@WinBioProperty@@@std@@@Z; WinBioProperty::Create(uint,uint,ulong,_WINBIO_IDENTITY *,uchar,std::shared_ptr<WinBioProperty::Base> &)
0x18002bb1d  test    eax, eax
0x18002bb1f  jns     loc_18002BCFB
0x18002bb25  mov     edx, eax; int
0x18002bb27  lea     rcx, [rsp+108h+var_C8]; this
0x18002bb2c  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x18002bb31  nop
0x18002bb32  mov     rcx, qword ptr [rsp+108h+Reply+8]; this
0x18002bb37  test    rcx, rcx
0x18002bb3a  jz      short loc_18002BB42
0x18002bb3c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002bb41  nop
0x18002bb42  mov     rcx, [rsp+108h+var_B0]; this
0x18002bb47  test    rcx, rcx
0x18002bb4a  jz      short loc_18002BB52
0x18002bb4c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002bb51  nop
0x18002bb52  lea     rcx, [rsp+108h+var_C0]
0x18002bb57  call    WppTraceUnwinder__lambda_8fef55889fcce4085fc6cc0b1112a47c_______WppTraceUnwinder__lambda_8fef55889fcce4085fc6cc0b1112a47c____
0x18002bb5c  nop
0x18002bb5d  mov     edx, 80098004h; int
0x18002bb62  lea     rcx, [rsp+108h+var_C8]; this
0x18002bb67  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x18002bb6c  nop
0x18002bb6d  jmp     loc_18002BF1D
0x18002bb72  cmp     r14d, 1
0x18002bb76  jnz     loc_18002BAEE
0x18002bb7c  cmp     r12d, 8
0x18002bb80  jnz     loc_18002BAEE
0x18002bb86  test    ebx, ebx
0x18002bb88  jnz     loc_18002BCBB
0x18002bb8e  cmp     [rsp+108h+arg_30], r13b
0x18002bb96  jnz     loc_18002BCBB
0x18002bb9c  test    r15, r15
0x18002bb9f  jnz     loc_18002BCBB
0x18002bba5  mov     ecx, r12d; size
0x18002bba8  call    MIDL_user_allocate
0x18002bbad  mov     [rsp+108h+var_98], rax
0x18002bbb2  test    rax, rax
0x18002bbb5  jnz     short loc_18002BBF7
0x18002bbb7  mov     edx, 8007000Eh; int
0x18002bbbc  lea     rcx, [rsp+108h+var_C8]; this
0x18002bbc1  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x18002bbc6  nop
0x18002bbc7  mov     rcx, [rsp+108h+var_B0]; this
0x18002bbcc  test    rcx, rcx
0x18002bbcf  jz      short loc_18002BBD7
0x18002bbd1  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002bbd6  nop
0x18002bbd7  lea     rcx, [rsp+108h+var_C0]
0x18002bbdc  call    WppTraceUnwinder__lambda_8fef55889fcce4085fc6cc0b1112a47c_______WppTraceUnwinder__lambda_8fef55889fcce4085fc6cc0b1112a47c____
0x18002bbe1  nop
0x18002bbe2  mov     edx, 80098004h; int
0x18002bbe7  lea     rcx, [rsp+108h+var_C8]; this
0x18002bbec  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x18002bbf1  nop
0x18002bbf2  jmp     loc_18002BF1D
0x18002bbf7  lea     rax, [rsp+108h+var_98]
0x18002bbfc  mov     [rsp+108h+var_78], rax
0x18002bc04  mov     byte ptr [rsp+108h+var_70], 1
0x18002bc0c  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x18002bc11  movzx   ecx, byte ptr [rax+0B9h]
0x18002bc18  mov     dword ptr [rsp+108h+Reply], ecx
0x18002bc1c  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x18002bc21  mov     ecx, [rax+0BCh]
0x18002bc27  mov     dword ptr [rsp+108h+Reply+4], ecx
0x18002bc2b  mov     rcx, [rsp+108h+var_98]
0x18002bc30  mov     rax, qword ptr [rsp+108h+Reply]
0x18002bc35  mov     [rcx], rax
0x18002bc38  mov     rax, [rsp+108h+var_98]
0x18002bc3d  mov     [rsi], rax
0x18002bc40  mov     dword ptr [rdi], 8
0x18002bc46  mov     dword ptr [rsp+108h+Reply], r13d
0x18002bc4b  mov     rbx, r13
0x18002bc4e  xchg    rbx, [rsp+108h+var_C8]
0x18002bc53  test    rbx, rbx
0x18002bc56  jz      short loc_18002BC6F
0x18002bc58  mov     rcx, rbx; struct _RPC_ASYNC_STATE *
0x18002bc5b  call    ?UnsubscribeChangeNotification@CRpcDispatcher@@SAXPEAU_RPC_ASYNC_STATE@@@Z; CRpcDispatcher::UnsubscribeChangeNotification(_RPC_ASYNC_STATE *)
0x18002bc60  lea     rdx, [rsp+108h+Reply]; Reply
0x18002bc65  mov     rcx, rbx; pAsync
0x18002bc68  call    cs:__imp_RpcAsyncCompleteCall
0x18002bc6e  nop
0x18002bc6f  mov     rcx, [rsp+108h+var_B0]; this
0x18002bc74  test    rcx, rcx
0x18002bc77  jz      short loc_18002BC7F
0x18002bc79  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002bc7e  nop
0x18002bc7f  lea     rcx, [rsp+108h+var_C0]
0x18002bc84  call    WppTraceUnwinder__lambda_8fef55889fcce4085fc6cc0b1112a47c_______WppTraceUnwinder__lambda_8fef55889fcce4085fc6cc0b1112a47c____
0x18002bc89  nop
0x18002bc8a  mov     dword ptr [rsp+108h+Reply], 80098004h
0x18002bc92  mov     rbx, r13
0x18002bc95  xchg    rbx, [rsp+108h+var_C8]
0x18002bc9a  test    rbx, rbx
0x18002bc9d  jz      short loc_18002BCB6
0x18002bc9f  mov     rcx, rbx; struct _RPC_ASYNC_STATE *
0x18002bca2  call    ?UnsubscribeChangeNotification@CRpcDispatcher@@SAXPEAU_RPC_ASYNC_STATE@@@Z; CRpcDispatcher::UnsubscribeChangeNotification(_RPC_ASYNC_STATE *)
0x18002bca7  lea     rdx, [rsp+108h+Reply]; Reply
0x18002bcac  mov     rcx, rbx; pAsync
0x18002bcaf  call    cs:__imp_RpcAsyncCompleteCall
0x18002bcb5  nop
0x18002bcb6  jmp     loc_18002BF1D
0x18002bcbb  mov     edx, 8009802Ch; int
0x18002bcc0  lea     rcx, [rsp+108h+var_C8]; this
0x18002bcc5  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x18002bcca  nop
0x18002bccb  mov     rcx, [rsp+108h+var_B0]; this
0x18002bcd0  test    rcx, rcx
0x18002bcd3  jz      short loc_18002BCDB
0x18002bcd5  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002bcda  nop
0x18002bcdb  lea     rcx, [rsp+108h+var_C0]
0x18002bce0  call    WppTraceUnwinder__lambda_8fef55889fcce4085fc6cc0b1112a47c_______WppTraceUnwinder__lambda_8fef55889fcce4085fc6cc0b1112a47c____
0x18002bce5  nop
0x18002bce6  mov     edx, 80098004h; int
0x18002bceb  lea     rcx, [rsp+108h+var_C8]; this
0x18002bcf0  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x18002bcf5  nop
0x18002bcf6  jmp     loc_18002BF1D
0x18002bcfb  mov     rcx, qword ptr [rsp+108h+Reply]
0x18002bd00  cmp     [rcx+10h], r13d
0x18002bd04  jnz     loc_18002BD8E
  ... truncated ...
```
