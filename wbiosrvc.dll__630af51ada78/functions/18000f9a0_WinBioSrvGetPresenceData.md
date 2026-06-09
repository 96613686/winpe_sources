# WinBioSrvGetPresenceData

- ea: `0x18000f9a0`
- end: `0x18000fdbb`
- name: `WinBioSrvGetPresenceData`
- size: `1051`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x18000b760`
- `0x18000f090`
- `0x18000f9a0`
- `0x1800118fc`
- `0x18001d730`
- `0x18001fb04`
- `0x180020ca4`
- `0x180020cdc`
- `0x18002274c`
- `0x180022ba4`
- `0x180055928`
- `0x18005d3e0`
- `0x180068f60`
- `0x18006963c`
- `0x180099430`
- `0x180099730`
- `0x1800d2010`

## import_xrefs

- `RPCRT4!RpcServerTestCancel` at `0x18000fa5d`
- `RPCRT4!RpcServerTestCancel` at `0x18000fa5d`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18000fd4f`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18000fd4f`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
RPC_STATUS __fastcall WinBioSrvGetPresenceData(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        char a4,
        __int64 a5,
        __int64 a6,
        __int64 a7)
{
  RPC_STATUS result; // eax
  __int64 PresenceData; // rdx
  const char *v13; // r9
  struct _RPC_ASYNC_STATE *v14; // rbx
  __int64 v15; // [rsp+40h] [rbp-B8h] BYREF
  __int64 Reply; // [rsp+48h] [rbp-B0h] BYREF
  int v17; // [rsp+50h] [rbp-A8h] BYREF
  __int64 v18; // [rsp+58h] [rbp-A0h] BYREF
  std::_Ref_count_base *v19; // [rsp+60h] [rbp-98h]
  char *v20; // [rsp+68h] [rbp-90h] BYREF
  std::_Ref_count_base *v21; // [rsp+70h] [rbp-88h]
  __int64 v22; // [rsp+78h] [rbp-80h] BYREF
  _BYTE v23[16]; // [rsp+80h] [rbp-78h] BYREF
  char v24[8]; // [rsp+90h] [rbp-68h] BYREF
  std::_Ref_count_base *v25; // [rsp+98h] [rbp-60h]
  char v26[32]; // [rsp+A0h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  v22 = a1;
  v15 = _InterlockedExchange64(&v22, 0);
  v17 = 0;
  strcpy(v26, "WinBioSrvGetPresenceData");
  lambda_afd7ee1b065516bcafbe102d67bfbf3c_::_lambda_afd7ee1b065516bcafbe102d67bfbf3c_(v23, v26, &v17);
  lambda_0631559adf4bf52f9fcb36dd9cc3c2fe_::operator()(v23);
  v17 = 1;
  _lambda_1d8e544947e376896bbe6f02de9fb8f9_::_lambda_1d8e544947e376896bbe6f02de9fb8f9_(&Reply, (__int64)v23);
  if ( !RpcServerTestCancel(0) )
  {
    CRpcAsyncStatePointer::CompleteRequest((CRpcAsyncStatePointer *)&v15, -2146861052);
    WppTraceUnwinder__lambda_0631559adf4bf52f9fcb36dd9cc3c2fe____::_WppTraceUnwinder__lambda_0631559adf4bf52f9fcb36dd9cc3c2fe____(&Reply);
    return CRpcAsyncStatePointer::CompleteRequest((CRpcAsyncStatePointer *)&v15, -2146861052);
  }
  CSessionManager::Find(&v18, a2);
  if ( !v18 )
  {
    CRpcAsyncStatePointer::CompleteRequest((CRpcAsyncStatePointer *)&v15, -2147024890);
    if ( v19 )
      std::_Ref_count_base::_Decref(v19);
LABEL_29:
    WppTraceUnwinder__lambda_0631559adf4bf52f9fcb36dd9cc3c2fe____::_WppTraceUnwinder__lambda_0631559adf4bf52f9fcb36dd9cc3c2fe____(&Reply);
    return CRpcAsyncStatePointer::CompleteRequest((CRpcAsyncStatePointer *)&v15, -2146861052);
  }
  if ( !a3 )
  {
    CRpcAsyncStatePointer::CompleteRequest((CRpcAsyncStatePointer *)&v15, -2146861054);
    if ( v19 )
      std::_Ref_count_base::_Decref(v19);
    goto LABEL_29;
  }
  if ( !a5 || !a6 || !a7 )
  {
    CRpcAsyncStatePointer::CompleteRequest((CRpcAsyncStatePointer *)&v15, -2147467261);
    if ( v19 )
      std::_Ref_count_base::_Decref(v19);
    goto LABEL_29;
  }
  if ( BindingHelper::IsEnrolling((BindingHelper *)(v18 + 16)) )
  {
    CRpcAsyncStatePointer::CompleteRequest((CRpcAsyncStatePointer *)&v15, -2146861049);
    if ( v19 )
      std::_Ref_count_base::_Decref(v19);
    goto LABEL_29;
  }
  CHardwareManager::FindBiometricUnit(&v20, a3);
  if ( !v20 )
  {
    CRpcAsyncStatePointer::CompleteRequest((CRpcAsyncStatePointer *)&v15, -2146861054);
    if ( v21 )
      std::_Ref_count_base::_Decref(v21);
    if ( v19 )
      std::_Ref_count_base::_Decref(v19);
    goto LABEL_29;
  }
  if ( BindingHelper::IsEnrolling((BindingHelper *)(v20 + 16)) )
  {
    CRpcAsyncStatePointer::CompleteRequest((CRpcAsyncStatePointer *)&v15, -2146861049);
    if ( v21 )
      std::_Ref_count_base::_Decref(v21);
    if ( v19 )
      std::_Ref_count_base::_Decref(v19);
    goto LABEL_29;
  }
  if ( v21 )
    std::_Ref_count_base::_Decref(v21);
  try
  {
    v20 = (char *)operator new(0x78u);
    PresenceData = CWinBioSrvGetPresenceData::CWinBioSrvGetPresenceData(
                     (_DWORD)v20,
                     (unsigned int)&v15,
                     (unsigned int)&v18,
                     a3,
                     a4,
                     a5,
                     a6,
                     a7);
    std::shared_ptr<CAsyncWorkItem>::shared_ptr<CAsyncWorkItem>(v24, PresenceData);
    CClientSession::ParentBsp(v18, &v20);
    if ( v20 )
      (*(void (__fastcall **)(char *, __int64 *, char *))(*(_QWORD *)v20 + 56LL))(v20, &v18, v24);
    if ( v21 )
      std::_Ref_count_base::_Decref(v21);
    if ( v25 )
      std::_Ref_count_base::_Decref(v25);
    if ( v19 )
      std::_Ref_count_base::_Decref(v19);
    result = WppTraceUnwinder__lambda_0631559adf4bf52f9fcb36dd9cc3c2fe____::_WppTraceUnwinder__lambda_0631559adf4bf52f9fcb36dd9cc3c2fe____(&Reply);
  }
  catch ( ... )
  {
    wil::details::in1diag3::FailFast_CaughtException(
      retaddr,
      (void *)0xAE5,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\winbiosrv.cpp",
      v13);
  }
  LODWORD(Reply) = -2146861052;
  v14 = (struct _RPC_ASYNC_STATE *)_InterlockedExchange64(&v15, 0);
  if ( v14 )
  {
    CRpcDispatcher::UnsubscribeChangeNotification(v14);
    return RpcAsyncCompleteCall(v14, &Reply);
  }
  return result;
}

```

## disassembly

```asm
0x18000f9a0  mov     r11, rsp
0x18000f9a3  mov     [r11+10h], rbx
0x18000f9a7  push    rsi
0x18000f9a8  push    rdi
0x18000f9a9  push    r12
0x18000f9ab  push    r14
0x18000f9ad  push    r15
0x18000f9af  sub     rsp, 0D0h
0x18000f9b6  mov     rax, cs:__security_cookie
0x18000f9bd  xor     rax, rsp
0x18000f9c0  mov     [rsp+0F8h+var_38], rax
0x18000f9c8  mov     r12b, r9b
0x18000f9cb  mov     ebx, r8d
0x18000f9ce  mov     r15, rdx
0x18000f9d1  mov     [r11-80h], rcx
0x18000f9d5  mov     rdi, [rsp+0F8h+arg_20]
0x18000f9dd  mov     rsi, [rsp+0F8h+arg_28]
0x18000f9e5  mov     r14, [rsp+0F8h+arg_30]
0x18000f9ed  mov     [rsp+0F8h+var_B8], 0
0x18000f9f6  xor     eax, eax
0x18000f9f8  xchg    rax, [r11-80h]
0x18000f9fc  mov     [rsp+0F8h+var_B8], rax
0x18000fa01  mov     [rsp+0F8h+var_A8], 0
0x18000fa09  movups  xmm0, xmmword ptr cs:aWinbiosrvgetpr_0; "WinBioSrvGetPresenceData"
0x18000fa10  movups  xmmword ptr [r11-58h], xmm0
0x18000fa15  movups  xmm1, xmmword ptr cs:aWinbiosrvgetpr_0+9; "GetPresenceData"
0x18000fa1c  movups  xmmword ptr [r11-4Fh], xmm1
0x18000fa21  lea     r8, [rsp+0F8h+var_A8]
0x18000fa26  lea     rdx, [r11-58h]
0x18000fa2a  lea     rcx, [r11-78h]
0x18000fa2e  call    _lambda_afd7ee1b065516bcafbe102d67bfbf3c____lambda_afd7ee1b065516bcafbe102d67bfbf3c_
0x18000fa33  lea     rcx, [rsp+0F8h+var_78]
0x18000fa3b  call    _lambda_0631559adf4bf52f9fcb36dd9cc3c2fe___operator__
0x18000fa40  mov     [rsp+0F8h+var_A8], 1
0x18000fa48  lea     rdx, [rsp+0F8h+var_78]
0x18000fa50  lea     rcx, [rsp+0F8h+Reply]
0x18000fa55  call    ??0_lambda_1d8e544947e376896bbe6f02de9fb8f9_@@QEAA@PEAV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@Z; _lambda_1d8e544947e376896bbe6f02de9fb8f9_::_lambda_1d8e544947e376896bbe6f02de9fb8f9_(nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>> *)
0x18000fa5a  nop
0x18000fa5b  xor     ecx, ecx; BindingHandle
0x18000fa5d  call    cs:__imp_RpcServerTestCancel
0x18000fa63  test    eax, eax
0x18000fa65  jnz     short loc_18000FA97
0x18000fa67  mov     edx, 80098004h; int
0x18000fa6c  lea     rcx, [rsp+0F8h+var_B8]; this
0x18000fa71  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x18000fa76  nop
0x18000fa77  lea     rcx, [rsp+0F8h+Reply]
0x18000fa7c  call    WppTraceUnwinder__lambda_0631559adf4bf52f9fcb36dd9cc3c2fe_______WppTraceUnwinder__lambda_0631559adf4bf52f9fcb36dd9cc3c2fe____
0x18000fa81  nop
0x18000fa82  mov     edx, 80098004h; int
0x18000fa87  lea     rcx, [rsp+0F8h+var_B8]; this
0x18000fa8c  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x18000fa91  nop
0x18000fa92  jmp     loc_18000FD93
0x18000fa97  mov     rdx, r15
0x18000fa9a  lea     rcx, [rsp+0F8h+var_A0]
0x18000fa9f  call    ?Find@CSessionManager@@SA?AV?$shared_ptr@VCClientSession@@@std@@PEAX@Z; CSessionManager::Find(void *)
0x18000faa4  nop
0x18000faa5  mov     rcx, [rsp+0F8h+var_A0]
0x18000faaa  test    rcx, rcx
0x18000faad  jnz     short loc_18000FAEF
0x18000faaf  mov     edx, 80070006h; int
0x18000fab4  lea     rcx, [rsp+0F8h+var_B8]; this
0x18000fab9  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x18000fabe  nop
0x18000fabf  mov     rcx, [rsp+0F8h+var_98]; this
0x18000fac4  test    rcx, rcx
0x18000fac7  jz      short loc_18000FACF
0x18000fac9  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000face  nop
0x18000facf  lea     rcx, [rsp+0F8h+Reply]
0x18000fad4  call    WppTraceUnwinder__lambda_0631559adf4bf52f9fcb36dd9cc3c2fe_______WppTraceUnwinder__lambda_0631559adf4bf52f9fcb36dd9cc3c2fe____
0x18000fad9  nop
0x18000fada  mov     edx, 80098004h; int
0x18000fadf  lea     rcx, [rsp+0F8h+var_B8]; this
0x18000fae4  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x18000fae9  nop
0x18000faea  jmp     loc_18000FD93
0x18000faef  test    ebx, ebx
0x18000faf1  jnz     short loc_18000FB33
0x18000faf3  mov     edx, 80098002h; int
0x18000faf8  lea     rcx, [rsp+0F8h+var_B8]; this
0x18000fafd  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x18000fb02  nop
0x18000fb03  mov     rcx, [rsp+0F8h+var_98]; this
0x18000fb08  test    rcx, rcx
0x18000fb0b  jz      short loc_18000FB13
0x18000fb0d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000fb12  nop
0x18000fb13  lea     rcx, [rsp+0F8h+Reply]
0x18000fb18  call    WppTraceUnwinder__lambda_0631559adf4bf52f9fcb36dd9cc3c2fe_______WppTraceUnwinder__lambda_0631559adf4bf52f9fcb36dd9cc3c2fe____
0x18000fb1d  nop
0x18000fb1e  mov     edx, 80098004h; int
0x18000fb23  lea     rcx, [rsp+0F8h+var_B8]; this
0x18000fb28  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x18000fb2d  nop
0x18000fb2e  jmp     loc_18000FD93
0x18000fb33  test    rdi, rdi
0x18000fb36  jz      loc_18000FD58
0x18000fb3c  test    rsi, rsi
0x18000fb3f  jz      loc_18000FD58
0x18000fb45  test    r14, r14
0x18000fb48  jz      loc_18000FD58
0x18000fb4e  add     rcx, 10h; this
0x18000fb52  call    ?IsEnrolling@BindingHelper@@QEAA_NXZ; BindingHelper::IsEnrolling(void)
0x18000fb57  test    al, al
0x18000fb59  jz      short loc_18000FB9B
0x18000fb5b  mov     edx, 80098007h; int
0x18000fb60  lea     rcx, [rsp+0F8h+var_B8]; this
0x18000fb65  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x18000fb6a  nop
0x18000fb6b  mov     rcx, [rsp+0F8h+var_98]; this
0x18000fb70  test    rcx, rcx
0x18000fb73  jz      short loc_18000FB7B
0x18000fb75  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000fb7a  nop
0x18000fb7b  lea     rcx, [rsp+0F8h+Reply]
0x18000fb80  call    WppTraceUnwinder__lambda_0631559adf4bf52f9fcb36dd9cc3c2fe_______WppTraceUnwinder__lambda_0631559adf4bf52f9fcb36dd9cc3c2fe____
0x18000fb85  nop
0x18000fb86  mov     edx, 80098004h; int
0x18000fb8b  lea     rcx, [rsp+0F8h+var_B8]; this
0x18000fb90  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x18000fb95  nop
0x18000fb96  jmp     loc_18000FD93
0x18000fb9b  mov     edx, ebx
0x18000fb9d  lea     rcx, [rsp+0F8h+var_90]
0x18000fba2  call    ?FindBiometricUnit@CHardwareManager@@SA?AV?$shared_ptr@VCBiometricUnit@@@std@@K@Z; CHardwareManager::FindBiometricUnit(ulong)
0x18000fba7  nop
0x18000fba8  mov     rcx, [rsp+0F8h+var_90]
0x18000fbad  test    rcx, rcx
0x18000fbb0  jnz     short loc_18000FC02
0x18000fbb2  mov     edx, 80098002h; int
0x18000fbb7  lea     rcx, [rsp+0F8h+var_B8]; this
0x18000fbbc  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x18000fbc1  nop
0x18000fbc2  mov     rcx, [rsp+0F8h+var_88]; this
0x18000fbc7  test    rcx, rcx
0x18000fbca  jz      short loc_18000FBD2
0x18000fbcc  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000fbd1  nop
0x18000fbd2  mov     rcx, [rsp+0F8h+var_98]; this
0x18000fbd7  test    rcx, rcx
0x18000fbda  jz      short loc_18000FBE2
0x18000fbdc  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000fbe1  nop
0x18000fbe2  lea     rcx, [rsp+0F8h+Reply]
0x18000fbe7  call    WppTraceUnwinder__lambda_0631559adf4bf52f9fcb36dd9cc3c2fe_______WppTraceUnwinder__lambda_0631559adf4bf52f9fcb36dd9cc3c2fe____
0x18000fbec  nop
0x18000fbed  mov     edx, 80098004h; int
0x18000fbf2  lea     rcx, [rsp+0F8h+var_B8]; this
0x18000fbf7  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x18000fbfc  nop
0x18000fbfd  jmp     loc_18000FD93
0x18000fc02  add     rcx, 10h; this
0x18000fc06  call    ?IsEnrolling@BindingHelper@@QEAA_NXZ; BindingHelper::IsEnrolling(void)
0x18000fc0b  test    al, al
0x18000fc0d  jz      short loc_18000FC5F
0x18000fc0f  mov     edx, 80098007h; int
0x18000fc14  lea     rcx, [rsp+0F8h+var_B8]; this
0x18000fc19  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x18000fc1e  nop
0x18000fc1f  mov     rcx, [rsp+0F8h+var_88]; this
0x18000fc24  test    rcx, rcx
0x18000fc27  jz      short loc_18000FC2F
0x18000fc29  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000fc2e  nop
0x18000fc2f  mov     rcx, [rsp+0F8h+var_98]; this
0x18000fc34  test    rcx, rcx
0x18000fc37  jz      short loc_18000FC3F
0x18000fc39  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000fc3e  nop
0x18000fc3f  lea     rcx, [rsp+0F8h+Reply]
0x18000fc44  call    WppTraceUnwinder__lambda_0631559adf4bf52f9fcb36dd9cc3c2fe_______WppTraceUnwinder__lambda_0631559adf4bf52f9fcb36dd9cc3c2fe____
0x18000fc49  nop
0x18000fc4a  mov     edx, 80098004h; int
0x18000fc4f  lea     rcx, [rsp+0F8h+var_B8]; this
0x18000fc54  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x18000fc59  nop
0x18000fc5a  jmp     loc_18000FD93
0x18000fc5f  mov     rcx, [rsp+0F8h+var_88]; this
0x18000fc64  test    rcx, rcx
0x18000fc67  jz      short loc_18000FC6F
0x18000fc69  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000fc6e  nop
0x18000fc6f  mov     ecx, 78h ; 'x'; Size
0x18000fc74  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000fc79  mov     [rsp+0F8h+var_90], rax
0x18000fc7e  mov     [rsp+0F8h+var_C0], r14
0x18000fc83  mov     [rsp+0F8h+var_C8], rsi
0x18000fc88  mov     [rsp+0F8h+var_D0], rdi
0x18000fc8d  mov     [rsp+0F8h+var_D8], r12b
0x18000fc92  mov     r9d, ebx
0x18000fc95  lea     r8, [rsp+0F8h+var_A0]
0x18000fc9a  lea     rdx, [rsp+0F8h+var_B8]
0x18000fc9f  mov     rcx, rax
0x18000fca2  call    ??0CWinBioSrvGetPresenceData@@QEAA@AEAVCRpcAsyncStatePointer@@AEAV?$shared_ptr@VCClientSession@@@std@@KEPEAK2PEAPEAU_WINBIO_PRESENCE@@@Z; CWinBioSrvGetPresenceData::CWinBioSrvGetPresenceData(CRpcAsyncStatePointer &,std::shared_ptr<CClientSession> &,ulong,uchar,ulong *,ulong *,_WINBIO_PRESENCE * *)
0x18000fca7  nop
0x18000fca8  mov     rdx, rax
0x18000fcab  lea     rcx, [rsp+0F8h+var_68]
0x18000fcb3  call    ??$?0VCWinBioSrvGetProperty@@$0A@@?$shared_ptr@VCAsyncWorkItem@@@std@@QEAA@PEAVCWinBioSrvGetProperty@@@Z; std::shared_ptr<CAsyncWorkItem>::shared_ptr<CAsyncWorkItem>(CWinBioSrvGetProperty *)
0x18000fcb8  nop
0x18000fcb9  lea     rdx, [rsp+0F8h+var_90]
0x18000fcbe  mov     rcx, [rsp+0F8h+var_A0]
0x18000fcc3  call    ?ParentBsp@CClientSession@@QEAA?AV?$shared_ptr@VCBiometricServiceProvider@@@std@@XZ; CClientSession::ParentBsp(void)
0x18000fcc8  nop
0x18000fcc9  mov     rcx, [rsp+0F8h+var_90]
0x18000fcce  test    rcx, rcx
0x18000fcd1  jz      short loc_18000FCED
0x18000fcd3  mov     rax, [rcx]
0x18000fcd6  lea     r8, [rsp+0F8h+var_68]
0x18000fcde  lea     rdx, [rsp+0F8h+var_A0]
0x18000fce3  mov     rax, [rax+38h]
0x18000fce7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fcec  nop
0x18000fced  mov     rcx, [rsp+0F8h+var_88]; this
0x18000fcf2  test    rcx, rcx
0x18000fcf5  jz      short loc_18000FCFD
0x18000fcf7  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000fcfc  nop
0x18000fcfd  mov     rcx, [rsp+0F8h+var_60]; this
0x18000fd05  test    rcx, rcx
0x18000fd08  jz      short loc_18000FD10
0x18000fd0a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000fd0f  nop
0x18000fd10  mov     rcx, [rsp+0F8h+var_98]; this
0x18000fd15  test    rcx, rcx
0x18000fd18  jz      short loc_18000FD20
0x18000fd1a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000fd1f  nop
0x18000fd20  lea     rcx, [rsp+0F8h+Reply]
0x18000fd25  call    WppTraceUnwinder__lambda_0631559adf4bf52f9fcb36dd9cc3c2fe_______WppTraceUnwinder__lambda_0631559adf4bf52f9fcb36dd9cc3c2fe____
0x18000fd2a  nop
0x18000fd2b  mov     dword ptr [rsp+0F8h+Reply], 80098004h
0x18000fd33  xor     ebx, ebx
0x18000fd35  xchg    rbx, [rsp+0F8h+var_B8]
0x18000fd3a  test    rbx, rbx
0x18000fd3d  jz      short loc_18000FD56
0x18000fd3f  mov     rcx, rbx; struct _RPC_ASYNC_STATE *
0x18000fd42  call    ?UnsubscribeChangeNotification@CRpcDispatcher@@SAXPEAU_RPC_ASYNC_STATE@@@Z; CRpcDispatcher::UnsubscribeChangeNotification(_RPC_ASYNC_STATE *)
0x18000fd47  lea     rdx, [rsp+0F8h+Reply]; Reply
0x18000fd4c  mov     rcx, rbx; pAsync
0x18000fd4f  call    cs:__imp_RpcAsyncCompleteCall
0x18000fd55  nop
0x18000fd56  jmp     short loc_18000FD93
0x18000fd58  mov     edx, 80004003h; int
0x18000fd5d  lea     rcx, [rsp+0F8h+var_B8]; this
0x18000fd62  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x18000fd67  nop
0x18000fd68  mov     rcx, [rsp+0F8h+var_98]; this
0x18000fd6d  test    rcx, rcx
0x18000fd70  jz      short loc_18000FD78
0x18000fd72  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000fd77  nop
0x18000fd78  lea     rcx, [rsp+0F8h+Reply]
0x18000fd7d  call    WppTraceUnwinder__lambda_0631559adf4bf52f9fcb36dd9cc3c2fe_______WppTraceUnwinder__lambda_0631559adf4bf52f9fcb36dd9cc3c2fe____
0x18000fd82  nop
0x18000fd83  mov     edx, 80098004h; int
0x18000fd88  lea     rcx, [rsp+0F8h+var_B8]; this
0x18000fd8d  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x18000fd92  nop
0x18000fd93  mov     rcx, [rsp+0F8h+var_38]
0x18000fd9b  xor     rcx, rsp; StackCookie
0x18000fd9e  call    __security_check_cookie
0x18000fda3  mov     rbx, [rsp+0F8h+arg_8]
0x18000fdab  add     rsp, 0D0h
0x18000fdb2  pop     r15
0x18000fdb4  pop     r14
0x18000fdb6  pop     r12
0x18000fdb8  pop     rdi
0x18000fdb9  pop     rsi
0x18000fdba  retn
```
