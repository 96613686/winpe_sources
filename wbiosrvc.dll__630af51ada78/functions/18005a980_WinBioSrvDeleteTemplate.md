# WinBioSrvDeleteTemplate

- ea: `0x18005a980`
- end: `0x18005af21`
- name: `WinBioSrvDeleteTemplate`
- size: `1441`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, _DWORD *, char)`
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x18000b760`
- `0x18000f090`
- `0x1800118fc`
- `0x18001d730`
- `0x18001fb04`
- `0x180020ca4`
- `0x180055928`
- `0x1800594ec`
- `0x18005a980`
- `0x18005af28`
- `0x18005af40`
- `0x18005d3e0`
- `0x180068f60`
- `0x18006963c`
- `0x18009a558`
- `0x1800d2010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18005ac50`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18005ac50`
- `RPCRT4!RpcServerTestCancel` at `0x18005aa23`
- `RPCRT4!RpcServerTestCancel` at `0x18005aa23`

## string_xrefs

- `0x18005a9ce`: `WinBioSrvDeleteTemplate`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall WinBioSrvDeleteTemplate(__int64 a1, __int64 a2, unsigned int a3, _DWORD *a4, char a5)
{
  __int64 v9; // rcx
  int v10; // eax
  std::_Ref_count_base *v11; // rbx
  _DWORD *v12; // rax
  const char *v13; // r9
  __int64 v14; // [rsp+30h] [rbp-88h] BYREF
  _BYTE v15[8]; // [rsp+38h] [rbp-80h] BYREF
  __int64 v16; // [rsp+40h] [rbp-78h] BYREF
  std::_Ref_count_base *v17; // [rsp+48h] [rbp-70h]
  std::_Ref_count_base *v18; // [rsp+50h] [rbp-68h] BYREF
  std::_Ref_count_base *v19; // [rsp+58h] [rbp-60h]
  int v20; // [rsp+60h] [rbp-58h] BYREF
  __int64 v21; // [rsp+68h] [rbp-50h] BYREF
  std::_Ref_count_base *v22[2]; // [rsp+70h] [rbp-48h] BYREF
  _BYTE v23[16]; // [rsp+80h] [rbp-38h] BYREF
  char v24[24]; // [rsp+90h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  v21 = a1;
  v14 = _InterlockedExchange64(&v21, 0);
  v20 = 0;
  strcpy(v24, "WinBioSrvDeleteTemplate");
  lambda_afd7ee1b065516bcafbe102d67bfbf3c_::_lambda_afd7ee1b065516bcafbe102d67bfbf3c_(v23, v24, &v20);
  lambda_e4ad96ccc5af864a8a03c3a97d2f1418_::operator()(v23);
  v20 = 1;
  _lambda_1d8e544947e376896bbe6f02de9fb8f9_::_lambda_1d8e544947e376896bbe6f02de9fb8f9_(v15, v23);
  if ( !RpcServerTestCancel(0) )
  {
    CRpcAsyncStatePointer::CompleteRequest((CRpcAsyncStatePointer *)&v14, -2146861052);
    WppTraceUnwinder__lambda_e4ad96ccc5af864a8a03c3a97d2f1418____::_WppTraceUnwinder__lambda_e4ad96ccc5af864a8a03c3a97d2f1418____(v15);
    return CRpcAsyncStatePointer::CompleteRequest((CRpcAsyncStatePointer *)&v14, -2146861052);
  }
  CSessionManager::Find(&v16, a2);
  v9 = v16;
  if ( !v16 )
  {
    CRpcAsyncStatePointer::CompleteRequest((CRpcAsyncStatePointer *)&v14, -2147024890);
    if ( v17 )
      std::_Ref_count_base::_Decref(v17);
LABEL_53:
    WppTraceUnwinder__lambda_e4ad96ccc5af864a8a03c3a97d2f1418____::_WppTraceUnwinder__lambda_e4ad96ccc5af864a8a03c3a97d2f1418____(v15);
    return CRpcAsyncStatePointer::CompleteRequest((CRpcAsyncStatePointer *)&v14, -2146861052);
  }
  if ( !a5 || !a3 )
  {
    CRpcAsyncStatePointer::CompleteRequest((CRpcAsyncStatePointer *)&v14, -2147024809);
    if ( v17 )
      std::_Ref_count_base::_Decref(v17);
    goto LABEL_53;
  }
  if ( !a4 )
  {
    CRpcAsyncStatePointer::CompleteRequest((CRpcAsyncStatePointer *)&v14, -2147467261);
    if ( v17 )
      std::_Ref_count_base::_Decref(v17);
    goto LABEL_53;
  }
  if ( !*a4 )
  {
    CRpcAsyncStatePointer::CompleteRequest((CRpcAsyncStatePointer *)&v14, -2147024809);
    if ( v17 )
      std::_Ref_count_base::_Decref(v17);
    goto LABEL_53;
  }
  if ( *a4 == 1 && (a4[1] != 621175426 || a5 != -1) )
  {
    CRpcAsyncStatePointer::CompleteRequest((CRpcAsyncStatePointer *)&v14, -2147024809);
    if ( v17 )
      std::_Ref_count_base::_Decref(v17);
    goto LABEL_53;
  }
  v10 = *(_DWORD *)(v16 + 160);
  if ( (v10 & 0x20) == 0 )
  {
    CRpcAsyncStatePointer::CompleteRequest((CRpcAsyncStatePointer *)&v14, -2147024891);
    if ( v17 )
      std::_Ref_count_base::_Decref(v17);
    goto LABEL_53;
  }
  if ( (v10 & 8) == 0 )
  {
    if ( *a4 == 1 )
    {
      CRpcAsyncStatePointer::CompleteRequest((CRpcAsyncStatePointer *)&v14, -2147024891);
      if ( v17 )
        std::_Ref_count_base::_Decref(v17);
      goto LABEL_53;
    }
    if ( *a4 == 3 )
    {
      if ( !EqualSid(a4 + 2, (PSID)(v16 + 56)) )
      {
        CRpcAsyncStatePointer::CompleteRequest((CRpcAsyncStatePointer *)&v14, -2147024891);
        if ( v17 )
          std::_Ref_count_base::_Decref(v17);
        goto LABEL_53;
      }
      v9 = v16;
    }
  }
  if ( BindingHelper::IsEnrolling((BindingHelper *)(v9 + 16)) )
  {
    CRpcAsyncStatePointer::CompleteRequest((CRpcAsyncStatePointer *)&v14, -2146861049);
    if ( v17 )
      std::_Ref_count_base::_Decref(v17);
    goto LABEL_53;
  }
  CHardwareManager::FindBiometricUnit(&v18, a3);
  if ( !v18 )
  {
    CRpcAsyncStatePointer::CompleteRequest((CRpcAsyncStatePointer *)&v14, -2146861054);
    if ( v19 )
      std::_Ref_count_base::_Decref(v19);
    if ( v17 )
      std::_Ref_count_base::_Decref(v17);
    goto LABEL_53;
  }
  if ( BindingHelper::IsEnrolling((std::_Ref_count_base *)((char *)v18 + 16)) )
  {
    CRpcAsyncStatePointer::CompleteRequest((CRpcAsyncStatePointer *)&v14, -2146861049);
    if ( v19 )
      std::_Ref_count_base::_Decref(v19);
    if ( v17 )
      std::_Ref_count_base::_Decref(v17);
    goto LABEL_53;
  }
  if ( v19 )
    std::_Ref_count_base::_Decref(v19);
  try
  {
    v18 = (std::_Ref_count_base *)operator new(0x70u);
    v11 = (std::_Ref_count_base *)CWinBioSrvDeleteTemplate::CWinBioSrvDeleteTemplate(
                                    (_DWORD)v18,
                                    (unsigned int)&v14,
                                    (unsigned int)&v16,
                                    a3,
                                    (__int64)a4,
                                    a5);
    *(_OWORD *)v22 = 0;
    v18 = v11;
    v12 = operator new(0x18u);
    v12[2] = 1;
    v12[3] = 1;
    *(_QWORD *)v12 = &std::_Ref_count<CWinBioSrvEnrollBegin>::`vftable';
    *((_QWORD *)v12 + 2) = v11;
    v22[0] = v11;
    v22[1] = (std::_Ref_count_base *)v12;
    v18 = 0;
    std::_Temporary_owner<CBootstrapBsp>::~_Temporary_owner<CBootstrapBsp>(&v18);
    CClientSession::ParentBsp(v16, &v18);
    if ( v18 )
      (*(void (__fastcall **)(std::_Ref_count_base *, __int64 *, std::_Ref_count_base **))(*(_QWORD *)v18 + 56LL))(
        v18,
        &v16,
        v22);
    if ( v19 )
      std::_Ref_count_base::_Decref(v19);
    if ( v22[1] )
      std::_Ref_count_base::_Decref(v22[1]);
    if ( v17 )
      std::_Ref_count_base::_Decref(v17);
    WppTraceUnwinder__lambda_e4ad96ccc5af864a8a03c3a97d2f1418____::_WppTraceUnwinder__lambda_e4ad96ccc5af864a8a03c3a97d2f1418____(v15);
  }
  catch ( ... )
  {
    wil::details::in1diag3::FailFast_CaughtException(
      retaddr,
      (void *)0xC15,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\winbiosrv.cpp",
      v13);
  }
  return CRpcAsyncStatePointer::CompleteRequest((CRpcAsyncStatePointer *)&v14, -2146861052);
}

```

## disassembly

```asm
0x18005a980  mov     r11, rsp
0x18005a983  mov     [r11+10h], rbx
0x18005a987  mov     [r11+18h], rsi
0x18005a98b  push    rdi
0x18005a98c  sub     rsp, 0B0h
0x18005a993  mov     rax, cs:__security_cookie
0x18005a99a  xor     rax, rsp
0x18005a99d  mov     [rsp+0B8h+var_10], rax
0x18005a9a5  mov     rbx, r9
0x18005a9a8  mov     esi, r8d
0x18005a9ab  mov     rdi, rdx
0x18005a9ae  mov     [r11-50h], rcx
0x18005a9b2  mov     [rsp+0B8h+var_88], 0
0x18005a9bb  xor     eax, eax
0x18005a9bd  xchg    rax, [r11-50h]
0x18005a9c1  mov     [rsp+0B8h+var_88], rax
0x18005a9c6  mov     [rsp+0B8h+var_58], 0
0x18005a9ce  movups  xmm0, xmmword ptr cs:aWinbiosrvdelet; "WinBioSrvDeleteTemplate"
0x18005a9d5  movups  xmmword ptr [r11-28h], xmm0
0x18005a9da  movsd   xmm1, qword ptr cs:aWinbiosrvdelet+10h; "emplate"
0x18005a9e2  movsd   qword ptr [r11-18h], xmm1
0x18005a9e8  lea     r8, [r11-58h]
0x18005a9ec  lea     rdx, [r11-28h]
0x18005a9f0  lea     rcx, [r11-38h]
0x18005a9f4  call    _lambda_afd7ee1b065516bcafbe102d67bfbf3c____lambda_afd7ee1b065516bcafbe102d67bfbf3c_
0x18005a9f9  lea     rcx, [rsp+0B8h+var_38]
0x18005aa01  call    _lambda_e4ad96ccc5af864a8a03c3a97d2f1418___operator__
0x18005aa06  mov     [rsp+0B8h+var_58], 1
0x18005aa0e  lea     rdx, [rsp+0B8h+var_38]
0x18005aa16  lea     rcx, [rsp+0B8h+var_80]
0x18005aa1b  call    ??0_lambda_1d8e544947e376896bbe6f02de9fb8f9_@@QEAA@PEAV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@Z; _lambda_1d8e544947e376896bbe6f02de9fb8f9_::_lambda_1d8e544947e376896bbe6f02de9fb8f9_(nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>> *)
0x18005aa20  nop
0x18005aa21  xor     ecx, ecx; BindingHandle
0x18005aa23  call    cs:__imp_RpcServerTestCancel
0x18005aa29  test    eax, eax
0x18005aa2b  jnz     short loc_18005AA5D
0x18005aa2d  mov     edx, 80098004h; int
0x18005aa32  lea     rcx, [rsp+0B8h+var_88]; this
0x18005aa37  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x18005aa3c  nop
0x18005aa3d  lea     rcx, [rsp+0B8h+var_80]
0x18005aa42  call    WppTraceUnwinder__lambda_e4ad96ccc5af864a8a03c3a97d2f1418_______WppTraceUnwinder__lambda_e4ad96ccc5af864a8a03c3a97d2f1418____
0x18005aa47  nop
0x18005aa48  mov     edx, 80098004h; int
0x18005aa4d  lea     rcx, [rsp+0B8h+var_88]; this
0x18005aa52  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x18005aa57  nop
0x18005aa58  jmp     loc_18005AEFC
0x18005aa5d  mov     rdx, rdi
0x18005aa60  lea     rcx, [rsp+0B8h+var_78]
0x18005aa65  call    ?Find@CSessionManager@@SA?AV?$shared_ptr@VCClientSession@@@std@@PEAX@Z; CSessionManager::Find(void *)
0x18005aa6a  nop
0x18005aa6b  mov     rcx, [rsp+0B8h+var_78]
0x18005aa70  test    rcx, rcx
0x18005aa73  jnz     short loc_18005AAB5
0x18005aa75  mov     edx, 80070006h; int
0x18005aa7a  lea     rcx, [rsp+0B8h+var_88]; this
0x18005aa7f  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x18005aa84  nop
0x18005aa85  mov     rcx, [rsp+0B8h+var_70]; this
0x18005aa8a  test    rcx, rcx
0x18005aa8d  jz      short loc_18005AA95
0x18005aa8f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005aa94  nop
0x18005aa95  lea     rcx, [rsp+0B8h+var_80]
0x18005aa9a  call    WppTraceUnwinder__lambda_e4ad96ccc5af864a8a03c3a97d2f1418_______WppTraceUnwinder__lambda_e4ad96ccc5af864a8a03c3a97d2f1418____
0x18005aa9f  nop
0x18005aaa0  mov     edx, 80098004h; int
0x18005aaa5  lea     rcx, [rsp+0B8h+var_88]; this
0x18005aaaa  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x18005aaaf  nop
0x18005aab0  jmp     loc_18005AEFC
0x18005aab5  mov     dil, [rsp+0B8h+arg_20]
0x18005aabd  test    dil, dil
0x18005aac0  jz      loc_18005AEC1
0x18005aac6  test    esi, esi
0x18005aac8  jz      loc_18005AEC1
0x18005aace  test    rbx, rbx
0x18005aad1  jnz     short loc_18005AB13
0x18005aad3  mov     edx, 80004003h; int
0x18005aad8  lea     rcx, [rsp+0B8h+var_88]; this
0x18005aadd  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x18005aae2  nop
0x18005aae3  mov     rcx, [rsp+0B8h+var_70]; this
0x18005aae8  test    rcx, rcx
0x18005aaeb  jz      short loc_18005AAF3
0x18005aaed  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005aaf2  nop
0x18005aaf3  lea     rcx, [rsp+0B8h+var_80]
0x18005aaf8  call    WppTraceUnwinder__lambda_e4ad96ccc5af864a8a03c3a97d2f1418_______WppTraceUnwinder__lambda_e4ad96ccc5af864a8a03c3a97d2f1418____
0x18005aafd  nop
0x18005aafe  mov     edx, 80098004h; int
0x18005ab03  lea     rcx, [rsp+0B8h+var_88]; this
0x18005ab08  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x18005ab0d  nop
0x18005ab0e  jmp     loc_18005AEFC
0x18005ab13  cmp     dword ptr [rbx], 0
0x18005ab16  jnz     short loc_18005AB58
0x18005ab18  mov     edx, 80070057h; int
0x18005ab1d  lea     rcx, [rsp+0B8h+var_88]; this
0x18005ab22  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x18005ab27  nop
0x18005ab28  mov     rcx, [rsp+0B8h+var_70]; this
0x18005ab2d  test    rcx, rcx
0x18005ab30  jz      short loc_18005AB38
0x18005ab32  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005ab37  nop
0x18005ab38  lea     rcx, [rsp+0B8h+var_80]
0x18005ab3d  call    WppTraceUnwinder__lambda_e4ad96ccc5af864a8a03c3a97d2f1418_______WppTraceUnwinder__lambda_e4ad96ccc5af864a8a03c3a97d2f1418____
0x18005ab42  nop
0x18005ab43  mov     edx, 80098004h; int
0x18005ab48  lea     rcx, [rsp+0B8h+var_88]; this
0x18005ab4d  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x18005ab52  nop
0x18005ab53  jmp     loc_18005AEFC
0x18005ab58  cmp     dword ptr [rbx], 1
0x18005ab5b  jnz     short loc_18005ABAC
0x18005ab5d  cmp     dword ptr [rbx+4], 25066282h
0x18005ab64  jnz     short loc_18005AB6C
0x18005ab66  cmp     dil, 0FFh
0x18005ab6a  jz      short loc_18005ABAC
0x18005ab6c  mov     edx, 80070057h; int
0x18005ab71  lea     rcx, [rsp+0B8h+var_88]; this
0x18005ab76  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x18005ab7b  nop
0x18005ab7c  mov     rcx, [rsp+0B8h+var_70]; this
0x18005ab81  test    rcx, rcx
0x18005ab84  jz      short loc_18005AB8C
0x18005ab86  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005ab8b  nop
0x18005ab8c  lea     rcx, [rsp+0B8h+var_80]
0x18005ab91  call    WppTraceUnwinder__lambda_e4ad96ccc5af864a8a03c3a97d2f1418_______WppTraceUnwinder__lambda_e4ad96ccc5af864a8a03c3a97d2f1418____
0x18005ab96  nop
0x18005ab97  mov     edx, 80098004h; int
0x18005ab9c  lea     rcx, [rsp+0B8h+var_88]; this
0x18005aba1  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x18005aba6  nop
0x18005aba7  jmp     loc_18005AEFC
0x18005abac  mov     eax, [rcx+0A0h]
0x18005abb2  test    al, 20h
0x18005abb4  jnz     short loc_18005ABF6
0x18005abb6  mov     edx, 80070005h; int
0x18005abbb  lea     rcx, [rsp+0B8h+var_88]; this
0x18005abc0  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x18005abc5  nop
0x18005abc6  mov     rcx, [rsp+0B8h+var_70]; this
0x18005abcb  test    rcx, rcx
0x18005abce  jz      short loc_18005ABD6
0x18005abd0  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005abd5  nop
0x18005abd6  lea     rcx, [rsp+0B8h+var_80]
0x18005abdb  call    WppTraceUnwinder__lambda_e4ad96ccc5af864a8a03c3a97d2f1418_______WppTraceUnwinder__lambda_e4ad96ccc5af864a8a03c3a97d2f1418____
0x18005abe0  nop
0x18005abe1  mov     edx, 80098004h; int
0x18005abe6  lea     rcx, [rsp+0B8h+var_88]; this
0x18005abeb  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x18005abf0  nop
0x18005abf1  jmp     loc_18005AEFC
0x18005abf6  test    al, 8
0x18005abf8  jnz     loc_18005AC9F
0x18005abfe  cmp     dword ptr [rbx], 1
0x18005ac01  jnz     short loc_18005AC43
0x18005ac03  mov     edx, 80070005h; int
0x18005ac08  lea     rcx, [rsp+0B8h+var_88]; this
0x18005ac0d  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x18005ac12  nop
0x18005ac13  mov     rcx, [rsp+0B8h+var_70]; this
0x18005ac18  test    rcx, rcx
0x18005ac1b  jz      short loc_18005AC23
0x18005ac1d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005ac22  nop
0x18005ac23  lea     rcx, [rsp+0B8h+var_80]
0x18005ac28  call    WppTraceUnwinder__lambda_e4ad96ccc5af864a8a03c3a97d2f1418_______WppTraceUnwinder__lambda_e4ad96ccc5af864a8a03c3a97d2f1418____
0x18005ac2d  nop
0x18005ac2e  mov     edx, 80098004h; int
0x18005ac33  lea     rcx, [rsp+0B8h+var_88]; this
0x18005ac38  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x18005ac3d  nop
0x18005ac3e  jmp     loc_18005AEFC
0x18005ac43  cmp     dword ptr [rbx], 3
0x18005ac46  jnz     short loc_18005AC9F
0x18005ac48  lea     rdx, [rcx+38h]; pSid2
0x18005ac4c  lea     rcx, [rbx+8]; pSid1
0x18005ac50  call    cs:__imp_EqualSid
0x18005ac56  test    eax, eax
0x18005ac58  jnz     short loc_18005AC9A
0x18005ac5a  mov     edx, 80070005h; int
0x18005ac5f  lea     rcx, [rsp+0B8h+var_88]; this
0x18005ac64  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x18005ac69  nop
0x18005ac6a  mov     rcx, [rsp+0B8h+var_70]; this
0x18005ac6f  test    rcx, rcx
0x18005ac72  jz      short loc_18005AC7A
0x18005ac74  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005ac79  nop
0x18005ac7a  lea     rcx, [rsp+0B8h+var_80]
0x18005ac7f  call    WppTraceUnwinder__lambda_e4ad96ccc5af864a8a03c3a97d2f1418_______WppTraceUnwinder__lambda_e4ad96ccc5af864a8a03c3a97d2f1418____
0x18005ac84  nop
0x18005ac85  mov     edx, 80098004h; int
0x18005ac8a  lea     rcx, [rsp+0B8h+var_88]; this
0x18005ac8f  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x18005ac94  nop
0x18005ac95  jmp     loc_18005AEFC
0x18005ac9a  mov     rcx, [rsp+0B8h+var_78]
0x18005ac9f  add     rcx, 10h; this
0x18005aca3  call    ?IsEnrolling@BindingHelper@@QEAA_NXZ; BindingHelper::IsEnrolling(void)
0x18005aca8  test    al, al
0x18005acaa  jz      short loc_18005ACEC
0x18005acac  mov     edx, 80098007h; int
0x18005acb1  lea     rcx, [rsp+0B8h+var_88]; this
0x18005acb6  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x18005acbb  nop
0x18005acbc  mov     rcx, [rsp+0B8h+var_70]; this
0x18005acc1  test    rcx, rcx
0x18005acc4  jz      short loc_18005ACCC
0x18005acc6  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005accb  nop
0x18005accc  lea     rcx, [rsp+0B8h+var_80]
0x18005acd1  call    WppTraceUnwinder__lambda_e4ad96ccc5af864a8a03c3a97d2f1418_______WppTraceUnwinder__lambda_e4ad96ccc5af864a8a03c3a97d2f1418____
0x18005acd6  nop
0x18005acd7  mov     edx, 80098004h; int
0x18005acdc  lea     rcx, [rsp+0B8h+var_88]; this
0x18005ace1  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x18005ace6  nop
0x18005ace7  jmp     loc_18005AEFC
0x18005acec  mov     edx, esi
0x18005acee  lea     rcx, [rsp+0B8h+var_68]
0x18005acf3  call    ?FindBiometricUnit@CHardwareManager@@SA?AV?$shared_ptr@VCBiometricUnit@@@std@@K@Z; CHardwareManager::FindBiometricUnit(ulong)
0x18005acf8  nop
0x18005acf9  mov     rcx, [rsp+0B8h+var_68]
0x18005acfe  test    rcx, rcx
0x18005ad01  jnz     short loc_18005AD53
0x18005ad03  mov     edx, 80098002h; int
0x18005ad08  lea     rcx, [rsp+0B8h+var_88]; this
0x18005ad0d  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x18005ad12  nop
0x18005ad13  mov     rcx, [rsp+0B8h+var_60]; this
0x18005ad18  test    rcx, rcx
0x18005ad1b  jz      short loc_18005AD23
0x18005ad1d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005ad22  nop
0x18005ad23  mov     rcx, [rsp+0B8h+var_70]; this
0x18005ad28  test    rcx, rcx
0x18005ad2b  jz      short loc_18005AD33
0x18005ad2d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005ad32  nop
0x18005ad33  lea     rcx, [rsp+0B8h+var_80]
0x18005ad38  call    WppTraceUnwinder__lambda_e4ad96ccc5af864a8a03c3a97d2f1418_______WppTraceUnwinder__lambda_e4ad96ccc5af864a8a03c3a97d2f1418____
0x18005ad3d  nop
0x18005ad3e  mov     edx, 80098004h; int
0x18005ad43  lea     rcx, [rsp+0B8h+var_88]; this
0x18005ad48  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x18005ad4d  nop
0x18005ad4e  jmp     loc_18005AEFC
0x18005ad53  add     rcx, 10h; this
0x18005ad57  call    ?IsEnrolling@BindingHelper@@QEAA_NXZ; BindingHelper::IsEnrolling(void)
0x18005ad5c  test    al, al
0x18005ad5e  jz      short loc_18005ADB0
0x18005ad60  mov     edx, 80098007h; int
0x18005ad65  lea     rcx, [rsp+0B8h+var_88]; this
0x18005ad6a  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x18005ad6f  nop
0x18005ad70  mov     rcx, [rsp+0B8h+var_60]; this
0x18005ad75  test    rcx, rcx
0x18005ad78  jz      short loc_18005AD80
0x18005ad7a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005ad7f  nop
0x18005ad80  mov     rcx, [rsp+0B8h+var_70]; this
0x18005ad85  test    rcx, rcx
0x18005ad88  jz      short loc_18005AD90
0x18005ad8a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005ad8f  nop
0x18005ad90  lea     rcx, [rsp+0B8h+var_80]
0x18005ad95  call    WppTraceUnwinder__lambda_e4ad96ccc5af864a8a03c3a97d2f1418_______WppTraceUnwinder__lambda_e4ad96ccc5af864a8a03c3a97d2f1418____
0x18005ad9a  nop
0x18005ad9b  mov     edx, 80098004h; int
0x18005ada0  lea     rcx, [rsp+0B8h+var_88]; this
0x18005ada5  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x18005adaa  nop
0x18005adab  jmp     loc_18005AEFC
0x18005adb0  mov     rcx, [rsp+0B8h+var_60]; this
0x18005adb5  test    rcx, rcx
0x18005adb8  jz      short loc_18005ADC0
0x18005adba  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005adbf  nop
0x18005adc0  mov     ecx, 70h ; 'p'; Size
0x18005adc5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005adca  mov     [rsp+0B8h+var_68], rax
0x18005adcf  mov     [rsp+0B8h+var_90], dil
0x18005add4  mov     [rsp+0B8h+var_98], rbx
0x18005add9  mov     r9d, esi
0x18005addc  lea     r8, [rsp+0B8h+var_78]
0x18005ade1  lea     rdx, [rsp+0B8h+var_88]
0x18005ade6  mov     rcx, rax
0x18005ade9  call    ??0CWinBioSrvDeleteTemplate@@QEAA@AEAVCRpcAsyncStatePointer@@AEAV?$shared_ptr@VCClientSession@@@std@@KPEAU_WINBIO_IDENTITY@@E@Z; CWinBioSrvDeleteTemplate::CWinBioSrvDeleteTemplate(CRpcAsyncStatePointer &,std::shared_ptr<CClientSession> &,ulong,_WINBIO_IDENTITY *,uchar)
0x18005adee  mov     rbx, rax
0x18005adf1  xorps   xmm0, xmm0
0x18005adf4  movdqu  xmmword ptr [rsp+0B8h+var_48], xmm0
0x18005adfa  mov     [rsp+0B8h+var_68], rax
0x18005adff  mov     ecx, 18h; Size
  ... truncated ...
```
