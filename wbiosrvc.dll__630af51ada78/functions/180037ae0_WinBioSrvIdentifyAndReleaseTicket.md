# WinBioSrvIdentifyAndReleaseTicket

- ea: `0x180037ae0`
- end: `0x180037db4`
- name: `WinBioSrvIdentifyAndReleaseTicket`
- size: `724`
- prototype: `RPC_STATUS __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `15`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x18000b760`
- `0x18001d730`
- `0x18001fb04`
- `0x180020ca4`
- `0x180020cdc`
- `0x180022ba4`
- `0x180037ae0`
- `0x180037dbc`
- `0x180055928`
- `0x18005d3e0`
- `0x180068f60`
- `0x18006963c`
- `0x1800995b0`
- `0x180099ff8`
- `0x1800d2010`

## import_xrefs

- `RPCRT4!RpcServerTestCancel` at `0x180037bab`
- `RPCRT4!RpcServerTestCancel` at `0x180037bab`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180037d48`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180037d48`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
RPC_STATUS __fastcall WinBioSrvIdentifyAndReleaseTicket(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7)
{
  RPC_STATUS result; // eax
  __int64 v11; // rdx
  const char *v12; // r9
  struct _RPC_ASYNC_STATE *v13; // rbx
  __int64 v14; // [rsp+40h] [rbp-B8h] BYREF
  int Reply; // [rsp+48h] [rbp-B0h] BYREF
  int v16; // [rsp+50h] [rbp-A8h] BYREF
  __int64 v17; // [rsp+58h] [rbp-A0h] BYREF
  std::_Ref_count_base *v18; // [rsp+60h] [rbp-98h]
  __int64 v19; // [rsp+68h] [rbp-90h] BYREF
  void *v20; // [rsp+70h] [rbp-88h] BYREF
  std::_Ref_count_base *v21; // [rsp+78h] [rbp-80h]
  _BYTE v22[16]; // [rsp+80h] [rbp-78h] BYREF
  _BYTE v23[8]; // [rsp+90h] [rbp-68h] BYREF
  std::_Ref_count_base *v24; // [rsp+98h] [rbp-60h]
  char v25[40]; // [rsp+A0h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  v19 = a1;
  v14 = _InterlockedExchange64(&v19, 0);
  v16 = 0;
  strcpy(v25, "WinBioSrvIdentifyAndReleaseTicket");
  lambda_afd7ee1b065516bcafbe102d67bfbf3c_::_lambda_afd7ee1b065516bcafbe102d67bfbf3c_(v22, v25, &v16);
  lambda_caddad0820a9a9da3f791abf569c0e3e_::operator()(v22);
  v16 = 1;
  _lambda_1d8e544947e376896bbe6f02de9fb8f9_::_lambda_1d8e544947e376896bbe6f02de9fb8f9_(&Reply, v22);
  if ( !RpcServerTestCancel(0) )
  {
    CRpcAsyncStatePointer::CompleteRequest((CRpcAsyncStatePointer *)&v14, -2146861052);
    WppTraceUnwinder__lambda_caddad0820a9a9da3f791abf569c0e3e____::_WppTraceUnwinder__lambda_caddad0820a9a9da3f791abf569c0e3e____(&Reply);
    return CRpcAsyncStatePointer::CompleteRequest((CRpcAsyncStatePointer *)&v14, -2146861052);
  }
  CSessionManager::Find(&v17, a2);
  if ( !v17 )
  {
    CRpcAsyncStatePointer::CompleteRequest((CRpcAsyncStatePointer *)&v14, -2147024890);
    if ( v18 )
      std::_Ref_count_base::_Decref(v18);
LABEL_27:
    WppTraceUnwinder__lambda_caddad0820a9a9da3f791abf569c0e3e____::_WppTraceUnwinder__lambda_caddad0820a9a9da3f791abf569c0e3e____(&Reply);
    return CRpcAsyncStatePointer::CompleteRequest((CRpcAsyncStatePointer *)&v14, -2146861052);
  }
  if ( !a3 || !a4 || !a5 || !a6 || !a7 )
  {
    CRpcAsyncStatePointer::CompleteRequest((CRpcAsyncStatePointer *)&v14, -2147467261);
    if ( v18 )
      std::_Ref_count_base::_Decref(v18);
    goto LABEL_27;
  }
  try
  {
    v20 = operator new(0x80u);
    v11 = CWinBioSrvIdentify::CWinBioSrvIdentify(
            (_DWORD)v20,
            (unsigned int)&v14,
            (unsigned int)&v17,
            a3,
            a4,
            a5,
            a6,
            a7);
    std::shared_ptr<CAsyncWorkItem>::shared_ptr<CAsyncWorkItem>(v23, v11);
    CClientSession::ParentBsp(v17, &v20);
    if ( v20 )
      (*(void (__fastcall **)(void *, __int64 *, _BYTE *))(*(_QWORD *)v20 + 56LL))(v20, &v17, v23);
    if ( v21 )
      std::_Ref_count_base::_Decref(v21);
    if ( v24 )
      std::_Ref_count_base::_Decref(v24);
    if ( v18 )
      std::_Ref_count_base::_Decref(v18);
    result = WppTraceUnwinder__lambda_caddad0820a9a9da3f791abf569c0e3e____::_WppTraceUnwinder__lambda_caddad0820a9a9da3f791abf569c0e3e____(&Reply);
  }
  catch ( ... )
  {
    wil::details::in1diag3::FailFast_CaughtException(
      retaddr,
      (void *)0x5A1,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\winbiosrv.cpp",
      v12);
  }
  Reply = -2146861052;
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
0x180037ae0  mov     r11, rsp
0x180037ae3  mov     [r11+10h], rbx
0x180037ae7  push    rsi
0x180037ae8  push    rdi
0x180037ae9  push    r12
0x180037aeb  push    r14
0x180037aed  push    r15
0x180037aef  sub     rsp, 0D0h
0x180037af6  mov     rax, cs:__security_cookie
0x180037afd  xor     rax, rsp
0x180037b00  mov     [rsp+0F8h+var_30], rax
0x180037b08  mov     rdi, r9
0x180037b0b  mov     rbx, r8
0x180037b0e  mov     r12, rdx
0x180037b11  mov     [rsp+0F8h+var_90], rcx
0x180037b16  mov     rsi, [rsp+0F8h+arg_20]
0x180037b1e  mov     r14, [rsp+0F8h+arg_28]
0x180037b26  mov     r15, [rsp+0F8h+arg_30]
0x180037b2e  mov     [rsp+0F8h+var_B8], 0
0x180037b37  xor     eax, eax
0x180037b39  xchg    rax, [rsp+0F8h+var_90]
0x180037b3e  mov     [rsp+0F8h+var_B8], rax
0x180037b43  mov     [rsp+0F8h+var_A8], 0
0x180037b4b  movups  xmm0, xmmword ptr cs:aWinbiosrvident_0; "WinBioSrvIdentifyAndReleaseTicket"
0x180037b52  movups  xmmword ptr [r11-58h], xmm0
0x180037b57  movups  xmm1, xmmword ptr cs:aWinbiosrvident_0+10h; "yAndReleaseTicket"
0x180037b5e  movups  xmmword ptr [r11-48h], xmm1
0x180037b63  movzx   eax, word ptr cs:aWinbiosrvident_0+20h; "t"
0x180037b6a  mov     [r11-38h], ax
0x180037b6f  lea     r8, [rsp+0F8h+var_A8]
0x180037b74  lea     rdx, [r11-58h]
0x180037b78  lea     rcx, [r11-78h]
0x180037b7c  call    _lambda_afd7ee1b065516bcafbe102d67bfbf3c____lambda_afd7ee1b065516bcafbe102d67bfbf3c_
0x180037b81  lea     rcx, [rsp+0F8h+var_78]
0x180037b89  call    _lambda_caddad0820a9a9da3f791abf569c0e3e___operator__
0x180037b8e  mov     [rsp+0F8h+var_A8], 1
0x180037b96  lea     rdx, [rsp+0F8h+var_78]
0x180037b9e  lea     rcx, [rsp+0F8h+Reply]
0x180037ba3  call    ??0_lambda_1d8e544947e376896bbe6f02de9fb8f9_@@QEAA@PEAV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@Z; _lambda_1d8e544947e376896bbe6f02de9fb8f9_::_lambda_1d8e544947e376896bbe6f02de9fb8f9_(nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>> *)
0x180037ba8  nop
0x180037ba9  xor     ecx, ecx; BindingHandle
0x180037bab  call    cs:__imp_RpcServerTestCancel
0x180037bb1  test    eax, eax
0x180037bb3  jnz     short loc_180037BE5
0x180037bb5  mov     edx, 80098004h; int
0x180037bba  lea     rcx, [rsp+0F8h+var_B8]; this
0x180037bbf  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x180037bc4  nop
0x180037bc5  lea     rcx, [rsp+0F8h+Reply]
0x180037bca  call    WppTraceUnwinder__lambda_caddad0820a9a9da3f791abf569c0e3e_______WppTraceUnwinder__lambda_caddad0820a9a9da3f791abf569c0e3e____
0x180037bcf  nop
0x180037bd0  mov     edx, 80098004h; int
0x180037bd5  lea     rcx, [rsp+0F8h+var_B8]; this
0x180037bda  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x180037bdf  nop
0x180037be0  jmp     loc_180037D8C
0x180037be5  mov     rdx, r12
0x180037be8  lea     rcx, [rsp+0F8h+var_A0]
0x180037bed  call    ?Find@CSessionManager@@SA?AV?$shared_ptr@VCClientSession@@@std@@PEAX@Z; CSessionManager::Find(void *)
0x180037bf2  nop
0x180037bf3  cmp     [rsp+0F8h+var_A0], 0
0x180037bf9  jnz     short loc_180037C3B
0x180037bfb  mov     edx, 80070006h; int
0x180037c00  lea     rcx, [rsp+0F8h+var_B8]; this
0x180037c05  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x180037c0a  nop
0x180037c0b  mov     rcx, [rsp+0F8h+var_98]; this
0x180037c10  test    rcx, rcx
0x180037c13  jz      short loc_180037C1B
0x180037c15  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180037c1a  nop
0x180037c1b  lea     rcx, [rsp+0F8h+Reply]
0x180037c20  call    WppTraceUnwinder__lambda_caddad0820a9a9da3f791abf569c0e3e_______WppTraceUnwinder__lambda_caddad0820a9a9da3f791abf569c0e3e____
0x180037c25  nop
0x180037c26  mov     edx, 80098004h; int
0x180037c2b  lea     rcx, [rsp+0F8h+var_B8]; this
0x180037c30  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x180037c35  nop
0x180037c36  jmp     loc_180037D8C
0x180037c3b  test    rbx, rbx
0x180037c3e  jz      loc_180037D51
0x180037c44  test    rdi, rdi
0x180037c47  jz      loc_180037D51
0x180037c4d  test    rsi, rsi
0x180037c50  jz      loc_180037D51
0x180037c56  test    r14, r14
0x180037c59  jz      loc_180037D51
0x180037c5f  test    r15, r15
0x180037c62  jz      loc_180037D51
0x180037c68  mov     ecx, 80h; Size
0x180037c6d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180037c72  mov     [rsp+0F8h+var_88], rax
0x180037c77  mov     [rsp+0F8h+var_C0], r15
0x180037c7c  mov     [rsp+0F8h+var_C8], r14
0x180037c81  mov     [rsp+0F8h+var_D0], rsi
0x180037c86  mov     [rsp+0F8h+var_D8], rdi
0x180037c8b  mov     r9, rbx
0x180037c8e  lea     r8, [rsp+0F8h+var_A0]
0x180037c93  lea     rdx, [rsp+0F8h+var_B8]
0x180037c98  mov     rcx, rax
0x180037c9b  call    ??0CWinBioSrvIdentify@@QEAA@AEAVCRpcAsyncStatePointer@@AEAV?$shared_ptr@VCClientSession@@@std@@PEAKPEAU_WINBIO_IDENTITY@@PEAE2PEA_K@Z; CWinBioSrvIdentify::CWinBioSrvIdentify(CRpcAsyncStatePointer &,std::shared_ptr<CClientSession> &,ulong *,_WINBIO_IDENTITY *,uchar *,ulong *,unsigned __int64 *)
0x180037ca0  nop
0x180037ca1  mov     rdx, rax
0x180037ca4  lea     rcx, [rsp+0F8h+var_68]
0x180037cac  call    ??$?0VCWinBioSrvGetProperty@@$0A@@?$shared_ptr@VCAsyncWorkItem@@@std@@QEAA@PEAVCWinBioSrvGetProperty@@@Z; std::shared_ptr<CAsyncWorkItem>::shared_ptr<CAsyncWorkItem>(CWinBioSrvGetProperty *)
0x180037cb1  nop
0x180037cb2  lea     rdx, [rsp+0F8h+var_88]
0x180037cb7  mov     rcx, [rsp+0F8h+var_A0]
0x180037cbc  call    ?ParentBsp@CClientSession@@QEAA?AV?$shared_ptr@VCBiometricServiceProvider@@@std@@XZ; CClientSession::ParentBsp(void)
0x180037cc1  nop
0x180037cc2  mov     rcx, [rsp+0F8h+var_88]
0x180037cc7  test    rcx, rcx
0x180037cca  jz      short loc_180037CE6
0x180037ccc  mov     rax, [rcx]
0x180037ccf  lea     r8, [rsp+0F8h+var_68]
0x180037cd7  lea     rdx, [rsp+0F8h+var_A0]
0x180037cdc  mov     rax, [rax+38h]
0x180037ce0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037ce5  nop
0x180037ce6  mov     rcx, [rsp+0F8h+var_80]; this
0x180037ceb  test    rcx, rcx
0x180037cee  jz      short loc_180037CF6
0x180037cf0  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180037cf5  nop
0x180037cf6  mov     rcx, [rsp+0F8h+var_60]; this
0x180037cfe  test    rcx, rcx
0x180037d01  jz      short loc_180037D09
0x180037d03  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180037d08  nop
0x180037d09  mov     rcx, [rsp+0F8h+var_98]; this
0x180037d0e  test    rcx, rcx
0x180037d11  jz      short loc_180037D19
0x180037d13  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180037d18  nop
0x180037d19  lea     rcx, [rsp+0F8h+Reply]
0x180037d1e  call    WppTraceUnwinder__lambda_caddad0820a9a9da3f791abf569c0e3e_______WppTraceUnwinder__lambda_caddad0820a9a9da3f791abf569c0e3e____
0x180037d23  nop
0x180037d24  mov     [rsp+0F8h+Reply], 80098004h
0x180037d2c  xor     ebx, ebx
0x180037d2e  xchg    rbx, [rsp+0F8h+var_B8]
0x180037d33  test    rbx, rbx
0x180037d36  jz      short loc_180037D4F
0x180037d38  mov     rcx, rbx; struct _RPC_ASYNC_STATE *
0x180037d3b  call    ?UnsubscribeChangeNotification@CRpcDispatcher@@SAXPEAU_RPC_ASYNC_STATE@@@Z; CRpcDispatcher::UnsubscribeChangeNotification(_RPC_ASYNC_STATE *)
0x180037d40  lea     rdx, [rsp+0F8h+Reply]; Reply
0x180037d45  mov     rcx, rbx; pAsync
0x180037d48  call    cs:__imp_RpcAsyncCompleteCall
0x180037d4e  nop
0x180037d4f  jmp     short loc_180037D8C
0x180037d51  mov     edx, 80004003h; int
0x180037d56  lea     rcx, [rsp+0F8h+var_B8]; this
0x180037d5b  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x180037d60  nop
0x180037d61  mov     rcx, [rsp+0F8h+var_98]; this
0x180037d66  test    rcx, rcx
0x180037d69  jz      short loc_180037D71
0x180037d6b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180037d70  nop
0x180037d71  lea     rcx, [rsp+0F8h+Reply]
0x180037d76  call    WppTraceUnwinder__lambda_caddad0820a9a9da3f791abf569c0e3e_______WppTraceUnwinder__lambda_caddad0820a9a9da3f791abf569c0e3e____
0x180037d7b  nop
0x180037d7c  mov     edx, 80098004h; int
0x180037d81  lea     rcx, [rsp+0F8h+var_B8]; this
0x180037d86  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x180037d8b  nop
0x180037d8c  mov     rcx, [rsp+0F8h+var_30]
0x180037d94  xor     rcx, rsp; StackCookie
0x180037d97  call    __security_check_cookie
0x180037d9c  mov     rbx, [rsp+0F8h+arg_8]
0x180037da4  add     rsp, 0D0h
0x180037dab  pop     r15
0x180037dad  pop     r14
0x180037daf  pop     r12
0x180037db1  pop     rdi
0x180037db2  pop     rsi
0x180037db3  retn
```
