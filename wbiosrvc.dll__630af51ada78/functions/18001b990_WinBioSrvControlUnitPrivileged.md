# WinBioSrvControlUnitPrivileged

- ea: `0x18001b990`
- end: `0x18001bcf7`
- name: `WinBioSrvControlUnitPrivileged`
- size: `871`
- prototype: `RPC_STATUS __fastcall(__int64, __int64, int, int, int, int, __int64, int, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x18000b760`
- `0x18001b990`
- `0x18001bd00`
- `0x18001d730`
- `0x18001fb04`
- `0x180020ca4`
- `0x180020cdc`
- `0x180055928`
- `0x180058e50`
- `0x18005d3e0`
- `0x180068f60`
- `0x18006963c`
- `0x1800994d8`
- `0x180099b78`
- `0x1800d2010`

## import_xrefs

- `RPCRT4!RpcServerTestCancel` at `0x18001ba8a`
- `RPCRT4!RpcServerTestCancel` at `0x18001ba8a`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18001bceb`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18001bceb`

## string_xrefs

- `0x18001ba36`: `WinBioSrvControlUnitPrivileged`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
RPC_STATUS __fastcall WinBioSrvControlUnitPrivileged(
        __int64 a1,
        __int64 a2,
        int a3,
        int a4,
        int a5,
        int a6,
        __int64 a7,
        int a8,
        __int64 a9,
        __int64 a10,
        __int64 a11)
{
  RPC_STATUS result; // eax
  __int64 v15; // rdx
  const char *v16; // r9
  struct _RPC_ASYNC_STATE *v17; // rbx
  __int64 v18; // [rsp+60h] [rbp-D8h] BYREF
  int Reply; // [rsp+68h] [rbp-D0h] BYREF
  int v20; // [rsp+70h] [rbp-C8h] BYREF
  __int64 v21; // [rsp+78h] [rbp-C0h] BYREF
  std::_Ref_count_base *v22; // [rsp+80h] [rbp-B8h]
  __int64 v23; // [rsp+88h] [rbp-B0h] BYREF
  __int64 v24; // [rsp+90h] [rbp-A8h]
  __int64 v25; // [rsp+98h] [rbp-A0h]
  __int64 v26; // [rsp+A0h] [rbp-98h]
  void *v27; // [rsp+A8h] [rbp-90h] BYREF
  std::_Ref_count_base *v28; // [rsp+B0h] [rbp-88h]
  _BYTE v29[16]; // [rsp+B8h] [rbp-80h] BYREF
  _BYTE v30[8]; // [rsp+C8h] [rbp-70h] BYREF
  std::_Ref_count_base *v31; // [rsp+D0h] [rbp-68h]
  char v32[32]; // [rsp+D8h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+0h]

  v23 = a1;
  v26 = a9;
  v25 = a10;
  v24 = a11;
  v18 = _InterlockedExchange64(&v23, 0);
  v20 = 0;
  strcpy(v32, "WinBioSrvControlUnitPrivileged");
  lambda_afd7ee1b065516bcafbe102d67bfbf3c_::_lambda_afd7ee1b065516bcafbe102d67bfbf3c_(v29, v32, &v20);
  lambda_7db1fffdcf45fed6f59e3b674571ea02_::operator()(v29);
  v20 = 1;
  _lambda_1d8e544947e376896bbe6f02de9fb8f9_::_lambda_1d8e544947e376896bbe6f02de9fb8f9_(&Reply, v29);
  if ( !RpcServerTestCancel(0) )
  {
    CRpcAsyncStatePointer::CompleteRequest((CRpcAsyncStatePointer *)&v18, -2146861052);
    WppTraceUnwinder__lambda_7db1fffdcf45fed6f59e3b674571ea02____::_WppTraceUnwinder__lambda_7db1fffdcf45fed6f59e3b674571ea02____(&Reply);
    return CRpcAsyncStatePointer::CompleteRequest((CRpcAsyncStatePointer *)&v18, -2146861052);
  }
  CSessionManager::Find(&v21, a2);
  if ( !v21 )
  {
    CRpcAsyncStatePointer::CompleteRequest((CRpcAsyncStatePointer *)&v18, -2147024890);
    if ( v22 )
      std::_Ref_count_base::_Decref(v22);
LABEL_14:
    WppTraceUnwinder__lambda_7db1fffdcf45fed6f59e3b674571ea02____::_WppTraceUnwinder__lambda_7db1fffdcf45fed6f59e3b674571ea02____(&Reply);
    return CRpcAsyncStatePointer::CompleteRequest((CRpcAsyncStatePointer *)&v18, -2146861052);
  }
  if ( (unsigned int)(a4 - 1) > 2 )
  {
    CRpcAsyncStatePointer::CompleteRequest((CRpcAsyncStatePointer *)&v18, -2147024809);
    if ( v22 )
      std::_Ref_count_base::_Decref(v22);
    goto LABEL_14;
  }
  if ( (*(_BYTE *)(v21 + 160) & 0x40) == 0 )
  {
    CRpcAsyncStatePointer::CompleteRequest((CRpcAsyncStatePointer *)&v18, -2147024891);
    if ( v22 )
      std::_Ref_count_base::_Decref(v22);
    goto LABEL_14;
  }
  try
  {
    v27 = operator new(0x90u);
    v15 = CWinBioSrvControlUnitPrivileged::CWinBioSrvControlUnitPrivileged(
            (_DWORD)v27,
            (unsigned int)&v18,
            (unsigned int)&v21,
            a3,
            a4,
            a5,
            a6,
            a7,
            a8,
            v26,
            v25,
            v24);
    std::shared_ptr<WinBioProperty::Base>::shared_ptr<WinBioProperty::Base>(v30, v15);
    CClientSession::ParentBsp(v21, &v27);
    if ( v27 )
      (*(void (__fastcall **)(void *, __int64 *, _BYTE *))(*(_QWORD *)v27 + 56LL))(v27, &v21, v30);
    if ( v28 )
      std::_Ref_count_base::_Decref(v28);
    if ( v31 )
      std::_Ref_count_base::_Decref(v31);
    if ( v22 )
      std::_Ref_count_base::_Decref(v22);
    result = WppTraceUnwinder__lambda_7db1fffdcf45fed6f59e3b674571ea02____::_WppTraceUnwinder__lambda_7db1fffdcf45fed6f59e3b674571ea02____(&Reply);
  }
  catch ( ... )
  {
    wil::details::in1diag3::FailFast_CaughtException(
      retaddr,
      (void *)0xDD2,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\winbiosrv.cpp",
      v16);
  }
  Reply = -2146861052;
  v17 = (struct _RPC_ASYNC_STATE *)_InterlockedExchange64(&v18, 0);
  if ( v17 )
  {
    CRpcDispatcher::UnsubscribeChangeNotification(v17);
    return RpcAsyncCompleteCall(v17, &Reply);
  }
  return result;
}

```

## disassembly

```asm
0x18001b990  mov     r11, rsp
0x18001b993  push    rbx
0x18001b994  push    rsi
0x18001b995  push    rdi
0x18001b996  push    r12
0x18001b998  push    r13
0x18001b99a  push    r14
0x18001b99c  push    r15
0x18001b99e  sub     rsp, 100h
0x18001b9a5  mov     rax, cs:__security_cookie
0x18001b9ac  xor     rax, rsp
0x18001b9af  mov     [rsp+138h+var_40], rax
0x18001b9b7  mov     ebx, r9d
0x18001b9ba  mov     esi, r8d
0x18001b9bd  mov     rdi, rdx
0x18001b9c0  mov     [r11-0B0h], rcx
0x18001b9c7  mov     r14d, [rsp+138h+arg_20]
0x18001b9cf  mov     r15d, [rsp+138h+arg_28]
0x18001b9d7  mov     r12, [rsp+138h+arg_30]
0x18001b9df  mov     r13d, [rsp+138h+arg_38]
0x18001b9e7  mov     rax, [rsp+138h+arg_40]
0x18001b9ef  mov     [rsp+138h+var_98], rax
0x18001b9f7  mov     rax, [rsp+138h+arg_48]
0x18001b9ff  mov     [rsp+138h+var_A0], rax
0x18001ba07  mov     rax, [rsp+138h+arg_50]
0x18001ba0f  mov     [rsp+138h+var_A8], rax
0x18001ba17  mov     [rsp+138h+var_D8], 0
0x18001ba20  xor     eax, eax
0x18001ba22  xchg    rax, [r11-0B0h]
0x18001ba29  mov     [rsp+138h+var_D8], rax
0x18001ba2e  mov     [rsp+138h+var_C8], 0
0x18001ba36  movups  xmm0, xmmword ptr cs:aWinbiosrvcontr; "WinBioSrvControlUnitPrivileged"
0x18001ba3d  movups  xmmword ptr [r11-60h], xmm0
0x18001ba42  movups  xmm1, xmmword ptr cs:aWinbiosrvcontr+0Fh; "lUnitPrivileged"
0x18001ba49  movups  xmmword ptr [r11-51h], xmm1
0x18001ba4e  lea     r8, [rsp+138h+var_C8]
0x18001ba53  lea     rdx, [r11-60h]
0x18001ba57  lea     rcx, [r11-80h]
0x18001ba5b  call    _lambda_afd7ee1b065516bcafbe102d67bfbf3c____lambda_afd7ee1b065516bcafbe102d67bfbf3c_
0x18001ba60  lea     rcx, [rsp+138h+var_80]
0x18001ba68  call    _lambda_7db1fffdcf45fed6f59e3b674571ea02___operator__
0x18001ba6d  mov     [rsp+138h+var_C8], 1
0x18001ba75  lea     rdx, [rsp+138h+var_80]
0x18001ba7d  lea     rcx, [rsp+138h+Reply]
0x18001ba82  call    ??0_lambda_1d8e544947e376896bbe6f02de9fb8f9_@@QEAA@PEAV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@Z; _lambda_1d8e544947e376896bbe6f02de9fb8f9_::_lambda_1d8e544947e376896bbe6f02de9fb8f9_(nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>> *)
0x18001ba87  nop
0x18001ba88  xor     ecx, ecx; BindingHandle
0x18001ba8a  call    cs:__imp_RpcServerTestCancel
0x18001ba90  test    eax, eax
0x18001ba92  jnz     short loc_18001BAE2
0x18001ba94  mov     edx, 80098004h; int
0x18001ba99  lea     rcx, [rsp+138h+var_D8]; this
0x18001ba9e  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x18001baa3  nop
0x18001baa4  lea     rcx, [rsp+138h+Reply]
0x18001baa9  call    WppTraceUnwinder__lambda_7db1fffdcf45fed6f59e3b674571ea02_______WppTraceUnwinder__lambda_7db1fffdcf45fed6f59e3b674571ea02____
0x18001baae  nop
0x18001baaf  mov     edx, 80098004h; int
0x18001bab4  lea     rcx, [rsp+138h+var_D8]; this
0x18001bab9  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x18001babe  nop
0x18001babf  mov     rcx, [rsp+138h+var_40]
0x18001bac7  xor     rcx, rsp; StackCookie
0x18001baca  call    __security_check_cookie
0x18001bacf  add     rsp, 100h
0x18001bad6  pop     r15
0x18001bad8  pop     r14
0x18001bada  pop     r13
0x18001badc  pop     r12
0x18001bade  pop     rdi
0x18001badf  pop     rsi
0x18001bae0  pop     rbx
0x18001bae1  retn
0x18001bae2  mov     rdx, rdi
0x18001bae5  lea     rcx, [rsp+138h+var_C0]
0x18001baea  call    ?Find@CSessionManager@@SA?AV?$shared_ptr@VCClientSession@@@std@@PEAX@Z; CSessionManager::Find(void *)
0x18001baef  nop
0x18001baf0  mov     rcx, [rsp+138h+var_C0]
0x18001baf5  test    rcx, rcx
0x18001baf8  jnz     short loc_18001BB3A
0x18001bafa  mov     edx, 80070006h; int
0x18001baff  lea     rcx, [rsp+138h+var_D8]; this
0x18001bb04  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x18001bb09  nop
0x18001bb0a  mov     rcx, [rsp+138h+var_B8]; this
0x18001bb12  test    rcx, rcx
0x18001bb15  jz      short loc_18001BB1D
0x18001bb17  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001bb1c  nop
0x18001bb1d  lea     rcx, [rsp+138h+Reply]
0x18001bb22  call    WppTraceUnwinder__lambda_7db1fffdcf45fed6f59e3b674571ea02_______WppTraceUnwinder__lambda_7db1fffdcf45fed6f59e3b674571ea02____
0x18001bb27  nop
0x18001bb28  mov     edx, 80098004h; int
0x18001bb2d  lea     rcx, [rsp+138h+var_D8]; this
0x18001bb32  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x18001bb37  nop
0x18001bb38  jmp     short loc_18001BABF
0x18001bb3a  lea     eax, [rbx-1]
0x18001bb3d  cmp     eax, 2
0x18001bb40  jbe     short loc_18001BB85
0x18001bb42  mov     edx, 80070057h; int
0x18001bb47  lea     rcx, [rsp+138h+var_D8]; this
0x18001bb4c  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x18001bb51  nop
0x18001bb52  mov     rcx, [rsp+138h+var_B8]; this
0x18001bb5a  test    rcx, rcx
0x18001bb5d  jz      short loc_18001BB65
0x18001bb5f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001bb64  nop
0x18001bb65  lea     rcx, [rsp+138h+Reply]
0x18001bb6a  call    WppTraceUnwinder__lambda_7db1fffdcf45fed6f59e3b674571ea02_______WppTraceUnwinder__lambda_7db1fffdcf45fed6f59e3b674571ea02____
0x18001bb6f  nop
0x18001bb70  mov     edx, 80098004h; int
0x18001bb75  lea     rcx, [rsp+138h+var_D8]; this
0x18001bb7a  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x18001bb7f  nop
0x18001bb80  jmp     loc_18001BABF
0x18001bb85  test    byte ptr [rcx+0A0h], 40h
0x18001bb8c  jnz     short loc_18001BBD1
0x18001bb8e  mov     edx, 80070005h; int
0x18001bb93  lea     rcx, [rsp+138h+var_D8]; this
0x18001bb98  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x18001bb9d  nop
0x18001bb9e  mov     rcx, [rsp+138h+var_B8]; this
0x18001bba6  test    rcx, rcx
0x18001bba9  jz      short loc_18001BBB1
0x18001bbab  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001bbb0  nop
0x18001bbb1  lea     rcx, [rsp+138h+Reply]
0x18001bbb6  call    WppTraceUnwinder__lambda_7db1fffdcf45fed6f59e3b674571ea02_______WppTraceUnwinder__lambda_7db1fffdcf45fed6f59e3b674571ea02____
0x18001bbbb  nop
0x18001bbbc  mov     edx, 80098004h; int
0x18001bbc1  lea     rcx, [rsp+138h+var_D8]; this
0x18001bbc6  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x18001bbcb  nop
0x18001bbcc  jmp     loc_18001BABF
0x18001bbd1  mov     ecx, 90h; Size
0x18001bbd6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001bbdb  mov     [rsp+138h+var_90], rax
0x18001bbe3  mov     rcx, [rsp+138h+var_A8]
0x18001bbeb  mov     [rsp+138h+var_E0], rcx
0x18001bbf0  mov     rcx, [rsp+138h+var_A0]
0x18001bbf8  mov     [rsp+138h+var_E8], rcx
0x18001bbfd  mov     rcx, [rsp+138h+var_98]
0x18001bc05  mov     [rsp+138h+var_F0], rcx
0x18001bc0a  mov     [rsp+138h+var_F8], r13d
0x18001bc0f  mov     [rsp+138h+var_100], r12
0x18001bc14  mov     [rsp+138h+var_108], r15d
0x18001bc19  mov     [rsp+138h+var_110], r14d
0x18001bc1e  mov     [rsp+138h+var_118], ebx
0x18001bc22  mov     r9d, esi
0x18001bc25  lea     r8, [rsp+138h+var_C0]
0x18001bc2a  lea     rdx, [rsp+138h+var_D8]
0x18001bc2f  mov     rcx, rax
0x18001bc32  call    ??0CWinBioSrvControlUnitPrivileged@@QEAA@AEAVCRpcAsyncStatePointer@@AEAV?$shared_ptr@VCClientSession@@@std@@KKKKPEAEKPEAK23@Z; CWinBioSrvControlUnitPrivileged::CWinBioSrvControlUnitPrivileged(CRpcAsyncStatePointer &,std::shared_ptr<CClientSession> &,ulong,ulong,ulong,ulong,uchar *,ulong,ulong *,uchar *,ulong *)
0x18001bc37  nop
0x18001bc38  mov     rdx, rax
0x18001bc3b  lea     rcx, [rsp+138h+var_70]
0x18001bc43  call    ??$?0VUnitExtendedEnrollmentStatus@WinBioProperty@@$0A@@?$shared_ptr@VBase@WinBioProperty@@@std@@QEAA@PEAVUnitExtendedEnrollmentStatus@WinBioProperty@@@Z; std::shared_ptr<WinBioProperty::Base>::shared_ptr<WinBioProperty::Base>(WinBioProperty::UnitExtendedEnrollmentStatus *)
0x18001bc48  nop
0x18001bc49  lea     rdx, [rsp+138h+var_90]
0x18001bc51  mov     rcx, [rsp+138h+var_C0]
0x18001bc56  call    ?ParentBsp@CClientSession@@QEAA?AV?$shared_ptr@VCBiometricServiceProvider@@@std@@XZ; CClientSession::ParentBsp(void)
0x18001bc5b  nop
0x18001bc5c  mov     rcx, [rsp+138h+var_90]
0x18001bc64  test    rcx, rcx
0x18001bc67  jz      short loc_18001BC83
0x18001bc69  mov     rax, [rcx]
0x18001bc6c  lea     r8, [rsp+138h+var_70]
0x18001bc74  lea     rdx, [rsp+138h+var_C0]
0x18001bc79  mov     rax, [rax+38h]
0x18001bc7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bc82  nop
0x18001bc83  mov     rcx, [rsp+138h+var_88]; this
0x18001bc8b  test    rcx, rcx
0x18001bc8e  jz      short loc_18001BC96
0x18001bc90  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001bc95  nop
0x18001bc96  mov     rcx, [rsp+138h+var_68]; this
0x18001bc9e  test    rcx, rcx
0x18001bca1  jz      short loc_18001BCA9
0x18001bca3  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001bca8  nop
0x18001bca9  mov     rcx, [rsp+138h+var_B8]; this
0x18001bcb1  test    rcx, rcx
0x18001bcb4  jz      short loc_18001BCBC
0x18001bcb6  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001bcbb  nop
0x18001bcbc  lea     rcx, [rsp+138h+Reply]
0x18001bcc1  call    WppTraceUnwinder__lambda_7db1fffdcf45fed6f59e3b674571ea02_______WppTraceUnwinder__lambda_7db1fffdcf45fed6f59e3b674571ea02____
0x18001bcc6  nop
0x18001bcc7  mov     [rsp+138h+Reply], 80098004h
0x18001bccf  xor     ebx, ebx
0x18001bcd1  xchg    rbx, [rsp+138h+var_D8]
0x18001bcd6  test    rbx, rbx
0x18001bcd9  jz      short loc_18001BCF2
0x18001bcdb  mov     rcx, rbx; struct _RPC_ASYNC_STATE *
0x18001bcde  call    ?UnsubscribeChangeNotification@CRpcDispatcher@@SAXPEAU_RPC_ASYNC_STATE@@@Z; CRpcDispatcher::UnsubscribeChangeNotification(_RPC_ASYNC_STATE *)
0x18001bce3  lea     rdx, [rsp+138h+Reply]; Reply
0x18001bce8  mov     rcx, rbx; pAsync
0x18001bceb  call    cs:__imp_RpcAsyncCompleteCall
0x18001bcf1  nop
0x18001bcf2  jmp     loc_18001BABF
```
