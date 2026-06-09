# RpcCreateLoopbackSessionTransport

- ea: `0x180060420`
- end: `0x180060873`
- name: `RpcCreateLoopbackSessionTransport`
- size: `1107`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18005ffe0`

## callees

- `0x180008110`
- `0x180009940`
- `0x18000ba50`
- `0x18000c2a0`
- `0x18000f610`
- `0x18000f760`
- `0x180012c90`
- `0x1800139c0`
- `0x180015020`
- `0x180033f60`
- `0x180051aa4`
- `0x180060420`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180060731`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180060749`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180060731`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180060749`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800607b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800607ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800607b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800607ce`

## string_xrefs

- `0x18006050a`: `CRpcUtils::GetClientToken failed: 0x%x in %s`
- `0x180060453`: `RpcCreateLoopbackSessionTransport`
- `0x180060796`: `RpcCreateLoopbackSessionTransport`
- `0x18006064c`: `ptrCallerUserName->GetLogonSid failed: 0x%x in %s`
- `0x180060672`: `ptrCallerUserName->GetUserSid failed: 0x%x in %s`
- `0x1800606e2`: `ptrListener->GetProtocolListener failed: 0x%x in %s`
- `0x180060710`: `Check for debug/agent listener failed: 0x%x in %s`
- `0x18006079d`: `ptrDebugListener->CreateDebugNamedPipe failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall RpcCreateLoopbackSessionTransport(__int64 a1, int a2, __int64 a3, int a4)
{
  unsigned int v7; // edi
  const unsigned __int16 *v8; // rsi
  int ClientToken; // eax
  const char *v10; // rdx
  struct IUserName *v11; // rbx
  int v12; // eax
  __int64 v13; // r15
  unsigned int v14; // esi
  __int64 (__fastcall *v15)(__int64, PSID, _QWORD, PSID, DWORD, unsigned int, bool, __int64, int); // r14
  DWORD LengthSid; // ebx
  PSID v17; // rdi
  DWORD v18; // eax
  unsigned int v20; // [rsp+50h] [rbp-B0h] BYREF
  PSID pv; // [rsp+58h] [rbp-A8h] BYREF
  PSID pSid; // [rsp+60h] [rbp-A0h] BYREF
  int v23; // [rsp+68h] [rbp-98h]
  __int64 v24; // [rsp+70h] [rbp-90h] BYREF
  __int64 (__fastcall ***v25)(_QWORD, GUID *, __int64 *); // [rsp+78h] [rbp-88h] BYREF
  __int64 v26; // [rsp+80h] [rbp-80h] BYREF
  __int64 v27; // [rsp+88h] [rbp-78h] BYREF
  struct IRemoteConnectionManager *v28; // [rsp+90h] [rbp-70h] BYREF
  __int64 v29; // [rsp+98h] [rbp-68h] BYREF
  struct ISessionList *v30; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v31; // [rsp+A8h] [rbp-58h] BYREF
  struct IUserName *v32; // [rsp+B0h] [rbp-50h] BYREF
  void *v33; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v34[592]; // [rsp+C0h] [rbp-40h] BYREF

  v23 = a4;
  CRpcCallTrace::CRpcCallTrace((CRpcCallTrace *)v34, 0, "RpcCreateLoopbackSessionTransport");
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56916126>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID56916126>::GetImpl'::`2'::impl) )
  {
    v7 = -2147467263;
    goto LABEL_45;
  }
  v33 = 0;
  v32 = 0;
  v31 = 0;
  v20 = 0;
  v30 = 0;
  v29 = 0;
  pv = 0;
  pSid = 0;
  v28 = 0;
  v27 = 0;
  v26 = 0;
  v25 = 0;
  v24 = 0;
  if ( !a3 || !a4 )
  {
    v7 = -2147024809;
    goto LABEL_39;
  }
  if ( a2 == 7 )
  {
    v8 = L"7A78855482A04FA781DC";
LABEL_9:
    ClientToken = CRpcUtils::GetClientToken(&v33, 0);
    v7 = ClientToken;
    if ( ClientToken >= 0 )
    {
      ClientToken = CUtils::GetInstanceOfUserName(&v32);
      v7 = ClientToken;
      if ( ClientToken >= 0 )
      {
        v11 = v32;
        ClientToken = (*(__int64 (__fastcall **)(struct IUserName *, void *, __int64))(*(_QWORD *)v32 + 24LL))(
                        v32,
                        v33,
                        1);
        v7 = ClientToken;
        if ( ClientToken >= 0 )
        {
          ClientToken = (*(__int64 (__fastcall **)(struct IUserName *, unsigned int *))(*(_QWORD *)v11 + 112LL))(
                          v11,
                          &v20);
          v7 = ClientToken;
          if ( ClientToken >= 0 )
          {
            ClientToken = CHelper::GetSessionList(&v30);
            v7 = ClientToken;
            if ( ClientToken >= 0 )
            {
              v12 = (*(__int64 (__fastcall **)(struct ISessionList *, _QWORD, __int64 *))(*(_QWORD *)v30 + 24LL))(
                      v30,
                      v20,
                      &v29);
              v7 = v12;
              if ( v12 < 0 )
              {
                _DbgPrintMessage(
                  4,
                  "ptrList->FindSessionById failed: 0x%x in %s",
                  (unsigned int)v12,
                  "RpcCreateLoopbackSessionTransport");
                goto LABEL_39;
              }
              ClientToken = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v29 + 96LL))(v29, &v31);
              v7 = ClientToken;
              if ( ClientToken >= 0 )
              {
                if ( (*(unsigned int (__fastcall **)(__int64, struct IUserName *))(*(_QWORD *)v31 + 32LL))(v31, v11) )
                {
                  _DbgPrintMessage(4, "Caller is not interactive session user.");
                  v7 = -2147024891;
                  goto LABEL_39;
                }
                ClientToken = (*(__int64 (__fastcall **)(struct IUserName *, PSID *))(*(_QWORD *)v11 + 120LL))(v11, &pv);
                v7 = ClientToken;
                if ( ClientToken >= 0 )
                {
                  ClientToken = (*(__int64 (__fastcall **)(struct IUserName *, PSID *))(*(_QWORD *)v11 + 72LL))(
                                  v11,
                                  &pSid);
                  v7 = ClientToken;
                  if ( ClientToken >= 0 )
                  {
                    GetInstanceOfRemoteConnectionManager(&v28);
                    (*(void (__fastcall **)(struct IRemoteConnectionManager *, __int64 *))(*(_QWORD *)v28 + 120LL))(
                      v28,
                      &v27);
                    ClientToken = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, __int64 *))(*(_QWORD *)v27 + 48LL))(
                                    v27,
                                    v8,
                                    &v26);
                    v7 = ClientToken;
                    if ( ClientToken >= 0 )
                    {
                      ClientToken = (*(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v26 + 144LL))(
                                      v26,
                                      &v25);
                      v7 = ClientToken;
                      if ( ClientToken >= 0 )
                      {
                        ClientToken = (**v25)(v25, &IID_IWRdsProtocolDebugListener, &v24);
                        v7 = ClientToken;
                        if ( ClientToken >= 0 )
                        {
                          v13 = v24;
                          v14 = v20;
                          v15 = *(__int64 (__fastcall **)(__int64, PSID, _QWORD, PSID, DWORD, unsigned int, bool, __int64, int))(*(_QWORD *)v24 + 24LL);
                          LengthSid = GetLengthSid(pSid);
                          v17 = pSid;
                          v18 = GetLengthSid(pv);
                          ClientToken = v15(v13, pv, v18, v17, LengthSid, v14, a2 == 9, a3, v23);
                          v7 = ClientToken;
                          if ( ClientToken >= 0 )
                            goto LABEL_39;
                          v10 = "ptrDebugListener->CreateDebugNamedPipe failed: 0x%x in %s";
                        }
                        else
                        {
                          v10 = "Check for debug/agent listener failed: 0x%x in %s";
                        }
                      }
                      else
                      {
                        v10 = "ptrListener->GetProtocolListener failed: 0x%x in %s";
                      }
                    }
                    else
                    {
                      v10 = "ptrListenerList->GetListenerByName failed: 0x%x in %s";
                    }
                  }
                  else
                  {
                    v10 = "ptrCallerUserName->GetUserSid failed: 0x%x in %s";
                  }
                }
                else
                {
                  v10 = "ptrCallerUserName->GetLogonSid failed: 0x%x in %s";
                }
              }
              else
              {
                v10 = "ptrSession->getUserName failed: 0x%x in %s";
              }
            }
            else
            {
              v10 = "CHelper::GetSessionList failed: 0x%x in %s";
            }
          }
          else
          {
            v10 = "ptrCallerUserName->GetSessionId failed: 0x%x in %s";
          }
        }
        else
        {
          v10 = "ptrCallerUserName->Initialize failed: 0x%x in %s";
        }
      }
      else
      {
        v10 = "CUtils::GetInstanceOfUserName failed: 0x%x in %s";
      }
    }
    else
    {
      v10 = "CRpcUtils::GetClientToken failed: 0x%x in %s";
    }
    _DbgPrintMessage(8, v10, (unsigned int)ClientToken, "RpcCreateLoopbackSessionTransport");
LABEL_39:
    if ( pv )
      CoTaskMemFree(pv);
    if ( pSid )
      CoTaskMemFree(pSid);
    goto LABEL_43;
  }
  if ( a2 == 9 )
  {
    v8 = L"D8D584DCE21F4BD4B923";
    goto LABEL_9;
  }
  v7 = -2147024809;
LABEL_43:
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v24);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v25);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v26);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v27);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v28);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v29);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v30);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v31);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v32);
  SmartHANDLE::~SmartHANDLE((SmartHANDLE *)&v33);
LABEL_45:
  CRpcCallTrace::~CRpcCallTrace((CRpcCallTrace *)v34);
  return v7;
}

```

## disassembly

```asm
0x180060420  mov     [rsp-8+arg_0], rbx
0x180060425  push    rbp
0x180060426  push    rsi
0x180060427  push    rdi
0x180060428  push    r12
0x18006042a  push    r13
0x18006042c  push    r14
0x18006042e  push    r15
0x180060430  lea     rbp, [rsp-220h]
0x180060438  sub     rsp, 320h
0x18006043f  mov     rax, cs:__security_cookie
0x180060446  xor     rax, rsp
0x180060449  mov     [rbp+250h+var_40], rax
0x180060450  mov     ebx, r9d
0x180060453  lea     r15, aRpccreateloopb; "RpcCreateLoopbackSessionTransport"
0x18006045a  mov     r13, r8
0x18006045d  mov     [rsp+350h+var_2E8], ebx
0x180060461  mov     r12d, edx
0x180060464  lea     rcx, [rbp+250h+var_290]; this
0x180060468  mov     r8, r15; char *
0x18006046b  xor     edx, edx; int
0x18006046d  call    ??0CRpcCallTrace@@QEAA@HPEBD@Z; CRpcCallTrace::CRpcCallTrace(int,char const *)
0x180060472  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID56916126@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID56916126@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56916126> `wil::Feature<__WilFeatureTraits_Feature_ID56916126>::GetImpl(void)'::`2'::impl
0x180060479  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID56916126@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56916126>::__private_IsEnabled(void)
0x18006047e  xor     r14d, r14d
0x180060481  test    al, al
0x180060483  jz      loc_180060838
0x180060489  mov     [rbp+250h+var_298], r14
0x18006048d  mov     [rbp+250h+var_2A0], r14
0x180060491  mov     [rbp+250h+var_2A8], r14
0x180060495  mov     [rsp+350h+var_300], r14d
0x18006049a  mov     [rbp+250h+var_2B0], r14
0x18006049e  mov     [rbp+250h+var_2B8], r14
0x1800604a2  mov     [rsp+350h+pv], r14
0x1800604a7  mov     [rsp+350h+pSid], r14
0x1800604ac  mov     [rbp+250h+var_2C0], r14
0x1800604b0  mov     [rbp+250h+var_2C8], r14
0x1800604b4  mov     [rbp+250h+var_2D0], r14
0x1800604b8  mov     [rsp+350h+var_2D8], r14
0x1800604bd  mov     [rsp+350h+var_2E0], r14
0x1800604c2  test    r13, r13
0x1800604c5  jz      loc_1800607A9
0x1800604cb  test    ebx, ebx
0x1800604cd  jz      loc_1800607A9
0x1800604d3  cmp     r12d, 7
0x1800604d7  jz      short loc_1800604F2
0x1800604d9  cmp     r12d, 9
0x1800604dd  jz      short loc_1800604E9
0x1800604df  mov     edi, 80070057h
0x1800604e4  jmp     loc_1800607DA
0x1800604e9  lea     rsi, aD8d584dce21f4b; "D8D584DCE21F4BD4B923"
0x1800604f0  jmp     short loc_1800604F9
0x1800604f2  lea     rsi, a7a78855482a04f; "7A78855482A04FA781DC"
0x1800604f9  xor     edx, edx; int
0x1800604fb  lea     rcx, [rbp+250h+var_298]; void **
0x1800604ff  call    ?GetClientToken@CRpcUtils@@SAJPEAPEAXH@Z; CRpcUtils::GetClientToken(void * *,int)
0x180060504  mov     edi, eax
0x180060506  test    eax, eax
0x180060508  jns     short loc_180060526
0x18006050a  lea     rdx, aCrpcutilsGetcl_0; "CRpcUtils::GetClientToken failed: 0x%x "...
0x180060511  mov     r9, r15
0x180060514  mov     ecx, 8; int
0x180060519  mov     r8d, eax
0x18006051c  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180060521  jmp     loc_1800607AE
0x180060526  lea     rcx, [rbp+250h+var_2A0]; struct IUserName **
0x18006052a  call    ?GetInstanceOfUserName@CUtils@@SAJPEAPEAUIUserName@@@Z; CUtils::GetInstanceOfUserName(IUserName * *)
0x18006052f  mov     edi, eax
0x180060531  test    eax, eax
0x180060533  jns     short loc_18006053E
0x180060535  lea     rdx, aCutilsGetinsta; "CUtils::GetInstanceOfUserName failed: 0"...
0x18006053c  jmp     short loc_180060511
0x18006053e  mov     rbx, [rbp+250h+var_2A0]
0x180060542  mov     r8d, 1
0x180060548  mov     rdx, [rbp+250h+var_298]
0x18006054c  mov     rcx, rbx
0x18006054f  mov     rax, [rbx]
0x180060552  mov     rax, [rax+18h]
0x180060556  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006055b  mov     edi, eax
0x18006055d  test    eax, eax
0x18006055f  jns     short loc_18006056A
0x180060561  lea     rdx, aPtrcallerusern_2; "ptrCallerUserName->Initialize failed: 0"...
0x180060568  jmp     short loc_180060511
0x18006056a  mov     rax, [rbx]
0x18006056d  lea     rdx, [rsp+350h+var_300]
0x180060572  mov     rcx, rbx
0x180060575  mov     rax, [rax+70h]
0x180060579  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006057e  mov     edi, eax
0x180060580  test    eax, eax
0x180060582  jns     short loc_18006058D
0x180060584  lea     rdx, aPtrcallerusern_3; "ptrCallerUserName->GetSessionId failed:"...
0x18006058b  jmp     short loc_180060511
0x18006058d  lea     rcx, [rbp+250h+var_2B0]; struct ISessionList **
0x180060591  call    ?GetSessionList@CHelper@@SAJPEAPEAUISessionList@@@Z; CHelper::GetSessionList(ISessionList * *)
0x180060596  mov     edi, eax
0x180060598  test    eax, eax
0x18006059a  jns     short loc_1800605A8
0x18006059c  lea     rdx, aChelperGetsess; "CHelper::GetSessionList failed: 0x%x in"...
0x1800605a3  jmp     loc_180060511
0x1800605a8  mov     rcx, [rbp+250h+var_2B0]
0x1800605ac  lea     r8, [rbp+250h+var_2B8]
0x1800605b0  mov     edx, [rsp+350h+var_300]
0x1800605b4  mov     rax, [rcx]
0x1800605b7  mov     rax, [rax+18h]
0x1800605bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800605c0  mov     edi, eax
0x1800605c2  test    eax, eax
0x1800605c4  jns     short loc_1800605DA
0x1800605c6  mov     r9, r15
0x1800605c9  lea     rdx, aPtrlistFindses; "ptrList->FindSessionById failed: 0x%x i"...
0x1800605d0  mov     ecx, 4
0x1800605d5  jmp     loc_180060519
0x1800605da  mov     rcx, [rbp+250h+var_2B8]
0x1800605de  lea     rdx, [rbp+250h+var_2A8]
0x1800605e2  mov     rax, [rcx]
0x1800605e5  mov     rax, [rax+60h]
0x1800605e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800605ee  mov     edi, eax
0x1800605f0  test    eax, eax
0x1800605f2  jns     short loc_180060600
0x1800605f4  lea     rdx, aPtrsessionGetu_0; "ptrSession->getUserName failed: 0x%x in"...
0x1800605fb  jmp     loc_180060511
0x180060600  mov     rcx, [rbp+250h+var_2A8]
0x180060604  mov     rdx, rbx
0x180060607  mov     rax, [rcx]
0x18006060a  mov     rax, [rax+20h]
0x18006060e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060613  test    eax, eax
0x180060615  jz      short loc_180060632
0x180060617  lea     rdx, aCallerIsNotInt; "Caller is not interactive session user."
0x18006061e  mov     ecx, 4; int
0x180060623  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180060628  mov     edi, 80070005h
0x18006062d  jmp     loc_1800607AE
0x180060632  mov     rax, [rbx]
0x180060635  lea     rdx, [rsp+350h+pv]
0x18006063a  mov     rcx, rbx
0x18006063d  mov     rax, [rax+78h]
0x180060641  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060646  mov     edi, eax
0x180060648  test    eax, eax
0x18006064a  jns     short loc_180060658
0x18006064c  lea     rdx, aPtrcallerusern; "ptrCallerUserName->GetLogonSid failed: "...
0x180060653  jmp     loc_180060511
0x180060658  mov     rax, [rbx]
0x18006065b  lea     rdx, [rsp+350h+pSid]
0x180060660  mov     rcx, rbx
0x180060663  mov     rax, [rax+48h]
0x180060667  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006066c  mov     edi, eax
0x18006066e  test    eax, eax
0x180060670  jns     short loc_18006067E
0x180060672  lea     rdx, aPtrcallerusern_1; "ptrCallerUserName->GetUserSid failed: 0"...
0x180060679  jmp     loc_180060511
0x18006067e  lea     rcx, [rbp+250h+var_2C0]; struct IRemoteConnectionManager **
0x180060682  call    ?GetInstanceOfRemoteConnectionManager@@YAJPEAPEAVIRemoteConnectionManager@@@Z; GetInstanceOfRemoteConnectionManager(IRemoteConnectionManager * *)
0x180060687  mov     rcx, [rbp+250h+var_2C0]
0x18006068b  lea     rdx, [rbp+250h+var_2C8]
0x18006068f  mov     rax, [rcx]
0x180060692  mov     rax, [rax+78h]
0x180060696  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006069b  mov     rcx, [rbp+250h+var_2C8]
0x18006069f  lea     r8, [rbp+250h+var_2D0]
0x1800606a3  mov     rdx, rsi
0x1800606a6  mov     rax, [rcx]
0x1800606a9  mov     rax, [rax+30h]
0x1800606ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800606b2  mov     edi, eax
0x1800606b4  test    eax, eax
0x1800606b6  jns     short loc_1800606C4
0x1800606b8  lea     rdx, aPtrlistenerlis; "ptrListenerList->GetListenerByName fail"...
0x1800606bf  jmp     loc_180060511
0x1800606c4  mov     rcx, [rbp+250h+var_2D0]
0x1800606c8  lea     rdx, [rsp+350h+var_2D8]
0x1800606cd  mov     rax, [rcx]
0x1800606d0  mov     rax, [rax+90h]
0x1800606d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800606dc  mov     edi, eax
0x1800606de  test    eax, eax
0x1800606e0  jns     short loc_1800606EE
0x1800606e2  lea     rdx, aPtrlistenerGet; "ptrListener->GetProtocolListener failed"...
0x1800606e9  jmp     loc_180060511
0x1800606ee  mov     rcx, [rsp+350h+var_2D8]
0x1800606f3  lea     r8, [rsp+350h+var_2E0]
0x1800606f8  lea     rdx, IID_IWRdsProtocolDebugListener
0x1800606ff  mov     rax, [rcx]
0x180060702  mov     rax, [rax]
0x180060705  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006070a  mov     edi, eax
0x18006070c  test    eax, eax
0x18006070e  jns     short loc_18006071C
0x180060710  lea     rdx, aCheckForDebugA; "Check for debug/agent listener failed: "...
0x180060717  jmp     loc_180060511
0x18006071c  mov     r15, [rsp+350h+var_2E0]
0x180060721  mov     rcx, [rsp+350h+pSid]; pSid
0x180060726  mov     esi, [rsp+350h+var_300]
0x18006072a  mov     rax, [r15]
0x18006072d  mov     r14, [rax+18h]
0x180060731  call    cs:__imp_GetLengthSid
0x180060738  nop     dword ptr [rax+rax+00h]
0x18006073d  mov     rcx, [rsp+350h+pv]; pSid
0x180060742  mov     ebx, eax
0x180060744  mov     rdi, [rsp+350h+pSid]
0x180060749  call    cs:__imp_GetLengthSid
0x180060750  nop     dword ptr [rax+rax+00h]
0x180060755  mov     ecx, [rsp+350h+var_2E8]
0x180060759  xor     r8d, r8d
0x18006075c  mov     rdx, [rsp+350h+pv]
0x180060761  cmp     r12d, 9
0x180060765  mov     [rsp+350h+var_310], ecx
0x180060769  mov     r9, rdi
0x18006076c  setz    r8b
0x180060770  mov     [rsp+350h+var_318], r13
0x180060775  mov     [rsp+350h+var_320], r8d
0x18006077a  mov     rcx, r15
0x18006077d  mov     r8d, eax
0x180060780  mov     [rsp+350h+var_328], esi
0x180060784  mov     rax, r14
0x180060787  mov     [rsp+350h+var_330], ebx
0x18006078b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060790  mov     edi, eax
0x180060792  test    eax, eax
0x180060794  jns     short loc_1800607AE
0x180060796  lea     r9, aRpccreateloopb; "RpcCreateLoopbackSessionTransport"
0x18006079d  lea     rdx, aPtrdebuglisten; "ptrDebugListener->CreateDebugNamedPipe "...
0x1800607a4  jmp     loc_180060514
0x1800607a9  mov     edi, 80070057h
0x1800607ae  mov     rcx, [rsp+350h+pv]; pv
0x1800607b3  test    rcx, rcx
0x1800607b6  jz      short loc_1800607C4
0x1800607b8  call    cs:__imp_CoTaskMemFree
0x1800607bf  nop     dword ptr [rax+rax+00h]
0x1800607c4  mov     rcx, [rsp+350h+pSid]; pv
0x1800607c9  test    rcx, rcx
0x1800607cc  jz      short loc_1800607DA
0x1800607ce  call    cs:__imp_CoTaskMemFree
0x1800607d5  nop     dword ptr [rax+rax+00h]
0x1800607da  lea     rcx, [rsp+350h+var_2E0]; void *
0x1800607df  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x1800607e4  lea     rcx, [rsp+350h+var_2D8]; void *
0x1800607e9  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x1800607ee  lea     rcx, [rbp+250h+var_2D0]; void *
0x1800607f2  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x1800607f7  lea     rcx, [rbp+250h+var_2C8]; void *
0x1800607fb  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x180060800  lea     rcx, [rbp+250h+var_2C0]; void *
0x180060804  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x180060809  lea     rcx, [rbp+250h+var_2B8]; void *
0x18006080d  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x180060812  lea     rcx, [rbp+250h+var_2B0]; void *
0x180060816  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x18006081b  lea     rcx, [rbp+250h+var_2A8]; void *
0x18006081f  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x180060824  lea     rcx, [rbp+250h+var_2A0]; void *
0x180060828  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x18006082d  lea     rcx, [rbp+250h+var_298]; this
0x180060831  call    ??1SmartHANDLE@@QEAA@XZ; SmartHANDLE::~SmartHANDLE(void)
0x180060836  jmp     short loc_18006083D
0x180060838  mov     edi, 80004001h
0x18006083d  lea     rcx, [rbp+250h+var_290]; this
0x180060841  call    ??1CRpcCallTrace@@UEAA@XZ; CRpcCallTrace::~CRpcCallTrace(void)
0x180060846  mov     eax, edi
0x180060848  mov     rcx, [rbp+250h+var_40]
0x18006084f  xor     rcx, rsp; StackCookie
0x180060852  call    __security_check_cookie
0x180060857  mov     rbx, [rsp+350h+arg_0]
0x18006085f  add     rsp, 320h
0x180060866  pop     r15
0x180060868  pop     r14
0x18006086a  pop     r13
0x18006086c  pop     r12
0x18006086e  pop     rdi
0x18006086f  pop     rsi
0x180060870  pop     rbp
0x180060871  retn
```
