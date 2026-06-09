# RpcCreateChildSessionTransport

- ea: `0x18005d110`
- end: `0x18005d529`
- name: `RpcCreateChildSessionTransport`
- size: `1049`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180008b40`
- `0x18000a210`
- `0x18000bad0`
- `0x18000c2f0`
- `0x18000f080`
- `0x18000f1a0`
- `0x180012480`
- `0x180013150`
- `0x1800148d0`
- `0x1800321f0`
- `0x18004f3fc`
- `0x18005d110`
- `0x18005d530`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18005d411`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18005d423`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18005d411`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18005d423`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005d481`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005d491`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005d481`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005d491`

## string_xrefs

- `0x18005d1e4`: `CRpcUtils::GetClientToken failed: 0x%x in %s`
- `0x18005d326`: `ptrCallerUserName->GetLogonSid failed: 0x%x in %s`
- `0x18005d34c`: `ptrCallerUserName->GetUserSid failed: 0x%x in %s`
- `0x18005d3c2`: `ptrListener->GetProtocolListener failed: 0x%x in %s`
- `0x18005d466`: `ptrDebugListener->CreateDebugNamedPipe failed: 0x%x in %s`
- `0x18005d143`: `RpcCreateChildSessionTransport`
- `0x18005d45f`: `RpcCreateChildSessionTransport`

## pseudocode

```c
__int64 __fastcall RpcCreateChildSessionTransport(__int64 a1, __int64 a2, unsigned int a3)
{
  unsigned int LoopbackSessionTransport; // edi
  int ClientToken; // eax
  const char *v8; // rdx
  struct IUserName *v9; // rbx
  int v10; // eax
  __int64 v11; // r15
  unsigned int v12; // esi
  __int64 (__fastcall *v13)(__int64, PSID, _QWORD, PSID, DWORD, unsigned int, _DWORD, __int64, unsigned int); // r14
  DWORD LengthSid; // ebx
  PSID v15; // rdi
  DWORD v16; // eax
  unsigned int v18; // [rsp+50h] [rbp-B0h] BYREF
  PSID pv; // [rsp+58h] [rbp-A8h] BYREF
  PSID pSid; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v21; // [rsp+68h] [rbp-98h] BYREF
  __int64 (__fastcall ***v22)(_QWORD, GUID *, __int64 *); // [rsp+70h] [rbp-90h] BYREF
  __int64 v23; // [rsp+78h] [rbp-88h] BYREF
  __int64 v24; // [rsp+80h] [rbp-80h] BYREF
  struct IRemoteConnectionManager *v25; // [rsp+88h] [rbp-78h] BYREF
  __int64 v26; // [rsp+90h] [rbp-70h] BYREF
  struct ISessionList *v27; // [rsp+98h] [rbp-68h] BYREF
  __int64 v28; // [rsp+A0h] [rbp-60h] BYREF
  struct IUserName *v29; // [rsp+A8h] [rbp-58h] BYREF
  void *v30[2]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v31[592]; // [rsp+C0h] [rbp-40h] BYREF

  CRpcCallTrace::CRpcCallTrace((CRpcCallTrace *)v31, 0, "RpcCreateChildSessionTransport");
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56916126>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID56916126>::GetImpl'::`2'::impl) )
  {
    LoopbackSessionTransport = RpcCreateLoopbackSessionTransport(a1, 7, a2, a3);
    goto LABEL_40;
  }
  v30[0] = 0;
  v29 = 0;
  v28 = 0;
  v18 = 0;
  v27 = 0;
  v26 = 0;
  pv = 0;
  pSid = 0;
  v25 = 0;
  v24 = 0;
  v23 = 0;
  v22 = 0;
  v21 = 0;
  if ( !a2 || !a3 )
  {
    LoopbackSessionTransport = -2147024809;
    goto LABEL_35;
  }
  ClientToken = CRpcUtils::GetClientToken(v30, 0);
  LoopbackSessionTransport = ClientToken;
  if ( ClientToken >= 0 )
  {
    ClientToken = CUtils::GetInstanceOfUserName(&v29);
    LoopbackSessionTransport = ClientToken;
    if ( ClientToken >= 0 )
    {
      v9 = v29;
      ClientToken = (*(__int64 (__fastcall **)(struct IUserName *, void *, __int64))(*(_QWORD *)v29 + 24LL))(
                      v29,
                      v30[0],
                      1);
      LoopbackSessionTransport = ClientToken;
      if ( ClientToken >= 0 )
      {
        ClientToken = (*(__int64 (__fastcall **)(struct IUserName *, unsigned int *))(*(_QWORD *)v9 + 112LL))(v9, &v18);
        LoopbackSessionTransport = ClientToken;
        if ( ClientToken >= 0 )
        {
          ClientToken = CHelper::GetSessionList(&v27);
          LoopbackSessionTransport = ClientToken;
          if ( ClientToken >= 0 )
          {
            v10 = (*(__int64 (__fastcall **)(struct ISessionList *, _QWORD, __int64 *))(*(_QWORD *)v27 + 24LL))(
                    v27,
                    v18,
                    &v26);
            LoopbackSessionTransport = v10;
            if ( v10 < 0 )
            {
              _DbgPrintMessage(
                4,
                "ptrList->FindSessionById failed: 0x%x in %s",
                (unsigned int)v10,
                "RpcCreateChildSessionTransport");
              goto LABEL_35;
            }
            ClientToken = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v26 + 96LL))(v26, &v28);
            LoopbackSessionTransport = ClientToken;
            if ( ClientToken >= 0 )
            {
              if ( (*(unsigned int (__fastcall **)(__int64, struct IUserName *))(*(_QWORD *)v28 + 32LL))(v28, v9) )
              {
                _DbgPrintMessage(4, "Caller is not interactive session user.");
                LoopbackSessionTransport = -2147024891;
                goto LABEL_35;
              }
              ClientToken = (*(__int64 (__fastcall **)(struct IUserName *, PSID *))(*(_QWORD *)v9 + 120LL))(v9, &pv);
              LoopbackSessionTransport = ClientToken;
              if ( ClientToken >= 0 )
              {
                ClientToken = (*(__int64 (__fastcall **)(struct IUserName *, PSID *))(*(_QWORD *)v9 + 72LL))(v9, &pSid);
                LoopbackSessionTransport = ClientToken;
                if ( ClientToken >= 0 )
                {
                  GetInstanceOfRemoteConnectionManager(&v25);
                  (*(void (__fastcall **)(struct IRemoteConnectionManager *, __int64 *))(*(_QWORD *)v25 + 120LL))(
                    v25,
                    &v24);
                  ClientToken = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, __int64 *))(*(_QWORD *)v24 + 48LL))(
                                  v24,
                                  L"7A78855482A04FA781DC",
                                  &v23);
                  LoopbackSessionTransport = ClientToken;
                  if ( ClientToken >= 0 )
                  {
                    ClientToken = (*(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v23 + 144LL))(
                                    v23,
                                    &v22);
                    LoopbackSessionTransport = ClientToken;
                    if ( ClientToken >= 0 )
                    {
                      ClientToken = (**v22)(v22, &IID_IWRdsProtocolDebugListener, &v21);
                      LoopbackSessionTransport = ClientToken;
                      if ( ClientToken >= 0 )
                      {
                        v11 = v21;
                        v12 = v18;
                        v13 = *(__int64 (__fastcall **)(__int64, PSID, _QWORD, PSID, DWORD, unsigned int, _DWORD, __int64, unsigned int))(*(_QWORD *)v21 + 24LL);
                        LengthSid = GetLengthSid(pSid);
                        v15 = pSid;
                        v16 = GetLengthSid(pv);
                        ClientToken = v13(v11, pv, v16, v15, LengthSid, v12, 0, a2, a3);
                        LoopbackSessionTransport = ClientToken;
                        if ( ClientToken >= 0 )
                          goto LABEL_35;
                        v8 = "ptrDebugListener->CreateDebugNamedPipe failed: 0x%x in %s";
                      }
                      else
                      {
                        v8 = "Check for debug listener failed: 0x%x in %s";
                      }
                    }
                    else
                    {
                      v8 = "ptrListener->GetProtocolListener failed: 0x%x in %s";
                    }
                  }
                  else
                  {
                    v8 = "ptrListenerList->GetListenerByName failed: 0x%x in %s";
                  }
                }
                else
                {
                  v8 = "ptrCallerUserName->GetUserSid failed: 0x%x in %s";
                }
              }
              else
              {
                v8 = "ptrCallerUserName->GetLogonSid failed: 0x%x in %s";
              }
            }
            else
            {
              v8 = "ptrSession->getUserName failed: 0x%x in %s";
            }
          }
          else
          {
            v8 = "CHelper::GetSessionList failed: 0x%x in %s";
          }
        }
        else
        {
          v8 = "ptrCallerUserName->GetSessionId failed: 0x%x in %s";
        }
      }
      else
      {
        v8 = "ptrCallerUserName->Initialize failed: 0x%x in %s";
      }
    }
    else
    {
      v8 = "CUtils::GetInstanceOfUserName failed: 0x%x in %s";
    }
  }
  else
  {
    v8 = "CRpcUtils::GetClientToken failed: 0x%x in %s";
  }
  _DbgPrintMessage(8, v8, (unsigned int)ClientToken, "RpcCreateChildSessionTransport");
LABEL_35:
  if ( pv )
    CoTaskMemFree(pv);
  if ( pSid )
    CoTaskMemFree(pSid);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v21);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v22);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v23);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v24);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v25);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v26);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v27);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v28);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v29);
  SmartHANDLE::~SmartHANDLE((SmartHANDLE *)v30);
LABEL_40:
  CRpcCallTrace::~CRpcCallTrace((CRpcCallTrace *)v31);
  return LoopbackSessionTransport;
}

```

## disassembly

```asm
0x18005d110  mov     [rsp-8+arg_18], rbx
0x18005d115  push    rbp
0x18005d116  push    rsi
0x18005d117  push    rdi
0x18005d118  push    r12
0x18005d11a  push    r13
0x18005d11c  push    r14
0x18005d11e  push    r15
0x18005d120  lea     rbp, [rsp-220h]
0x18005d128  sub     rsp, 320h
0x18005d12f  mov     rax, cs:__security_cookie
0x18005d136  xor     rax, rsp
0x18005d139  mov     [rbp+250h+var_40], rax
0x18005d140  mov     r13d, r8d
0x18005d143  lea     r14, aRpccreatechild; "RpcCreateChildSessionTransport"
0x18005d14a  mov     r12, rdx
0x18005d14d  mov     rbx, rcx
0x18005d150  mov     r8, r14; char *
0x18005d153  lea     rcx, [rbp+250h+var_290]; this
0x18005d157  xor     edx, edx; int
0x18005d159  call    ??0CRpcCallTrace@@QEAA@HPEBD@Z; CRpcCallTrace::CRpcCallTrace(int,char const *)
0x18005d15e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID56916126@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID56916126@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56916126> `wil::Feature<__WilFeatureTraits_Feature_ID56916126>::GetImpl(void)'::`2'::impl
0x18005d165  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID56916126@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56916126>::__private_IsEnabled(void)
0x18005d16a  xor     esi, esi
0x18005d16c  test    al, al
0x18005d16e  jz      short loc_18005D188
0x18005d170  mov     r9d, r13d
0x18005d173  lea     edx, [rsi+7]
0x18005d176  mov     r8, r12
0x18005d179  mov     rcx, rbx
0x18005d17c  call    RpcCreateLoopbackSessionTransport
0x18005d181  mov     edi, eax
0x18005d183  jmp     loc_18005D4F4
0x18005d188  mov     [rbp+250h+var_2A0], rsi
0x18005d18c  mov     [rbp+250h+var_2A8], rsi
0x18005d190  mov     [rbp+250h+var_2B0], rsi
0x18005d194  mov     [rsp+350h+var_300], esi
0x18005d198  mov     [rbp+250h+var_2B8], rsi
0x18005d19c  mov     [rbp+250h+var_2C0], rsi
0x18005d1a0  mov     [rsp+350h+pv], rsi
0x18005d1a5  mov     [rsp+350h+pSid], rsi
0x18005d1aa  mov     [rbp+250h+var_2C8], rsi
0x18005d1ae  mov     [rbp+250h+var_2D0], rsi
0x18005d1b2  mov     [rsp+350h+var_2D8], rsi
0x18005d1b7  mov     [rsp+350h+var_2E0], rsi
0x18005d1bc  mov     [rsp+350h+var_2E8], rsi
0x18005d1c1  test    r12, r12
0x18005d1c4  jz      loc_18005D472
0x18005d1ca  test    r13d, r13d
0x18005d1cd  jz      loc_18005D472
0x18005d1d3  xor     edx, edx; int
0x18005d1d5  lea     rcx, [rbp+250h+var_2A0]; void **
0x18005d1d9  call    ?GetClientToken@CRpcUtils@@SAJPEAPEAXH@Z; CRpcUtils::GetClientToken(void * *,int)
0x18005d1de  mov     edi, eax
0x18005d1e0  test    eax, eax
0x18005d1e2  jns     short loc_18005D200
0x18005d1e4  lea     rdx, aCrpcutilsGetcl_0; "CRpcUtils::GetClientToken failed: 0x%x "...
0x18005d1eb  mov     r9, r14
0x18005d1ee  mov     ecx, 8; int
0x18005d1f3  mov     r8d, eax
0x18005d1f6  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005d1fb  jmp     loc_18005D477
0x18005d200  lea     rcx, [rbp+250h+var_2A8]; struct IUserName **
0x18005d204  call    ?GetInstanceOfUserName@CUtils@@SAJPEAPEAUIUserName@@@Z; CUtils::GetInstanceOfUserName(IUserName * *)
0x18005d209  mov     edi, eax
0x18005d20b  test    eax, eax
0x18005d20d  jns     short loc_18005D218
0x18005d20f  lea     rdx, aCutilsGetinsta; "CUtils::GetInstanceOfUserName failed: 0"...
0x18005d216  jmp     short loc_18005D1EB
0x18005d218  mov     rbx, [rbp+250h+var_2A8]
0x18005d21c  mov     r8d, 1
0x18005d222  mov     rdx, [rbp+250h+var_2A0]
0x18005d226  mov     rcx, rbx
0x18005d229  mov     rax, [rbx]
0x18005d22c  mov     rax, [rax+18h]
0x18005d230  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d235  mov     edi, eax
0x18005d237  test    eax, eax
0x18005d239  jns     short loc_18005D244
0x18005d23b  lea     rdx, aPtrcallerusern_2; "ptrCallerUserName->Initialize failed: 0"...
0x18005d242  jmp     short loc_18005D1EB
0x18005d244  mov     rax, [rbx]
0x18005d247  lea     rdx, [rsp+350h+var_300]
0x18005d24c  mov     rcx, rbx
0x18005d24f  mov     rax, [rax+70h]
0x18005d253  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d258  mov     edi, eax
0x18005d25a  test    eax, eax
0x18005d25c  jns     short loc_18005D267
0x18005d25e  lea     rdx, aPtrcallerusern_3; "ptrCallerUserName->GetSessionId failed:"...
0x18005d265  jmp     short loc_18005D1EB
0x18005d267  lea     rcx, [rbp+250h+var_2B8]; struct ISessionList **
0x18005d26b  call    ?GetSessionList@CHelper@@SAJPEAPEAUISessionList@@@Z; CHelper::GetSessionList(ISessionList * *)
0x18005d270  mov     edi, eax
0x18005d272  test    eax, eax
0x18005d274  jns     short loc_18005D282
0x18005d276  lea     rdx, aChelperGetsess; "CHelper::GetSessionList failed: 0x%x in"...
0x18005d27d  jmp     loc_18005D1EB
0x18005d282  mov     rcx, [rbp+250h+var_2B8]
0x18005d286  lea     r8, [rbp+250h+var_2C0]
0x18005d28a  mov     edx, [rsp+350h+var_300]
0x18005d28e  mov     rax, [rcx]
0x18005d291  mov     rax, [rax+18h]
0x18005d295  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d29a  mov     edi, eax
0x18005d29c  test    eax, eax
0x18005d29e  jns     short loc_18005D2B4
0x18005d2a0  mov     r9, r14
0x18005d2a3  lea     rdx, aPtrlistFindses; "ptrList->FindSessionById failed: 0x%x i"...
0x18005d2aa  mov     ecx, 4
0x18005d2af  jmp     loc_18005D1F3
0x18005d2b4  mov     rcx, [rbp+250h+var_2C0]
0x18005d2b8  lea     rdx, [rbp+250h+var_2B0]
0x18005d2bc  mov     rax, [rcx]
0x18005d2bf  mov     rax, [rax+60h]
0x18005d2c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d2c8  mov     edi, eax
0x18005d2ca  test    eax, eax
0x18005d2cc  jns     short loc_18005D2DA
0x18005d2ce  lea     rdx, aPtrsessionGetu_0; "ptrSession->getUserName failed: 0x%x in"...
0x18005d2d5  jmp     loc_18005D1EB
0x18005d2da  mov     rcx, [rbp+250h+var_2B0]
0x18005d2de  mov     rdx, rbx
0x18005d2e1  mov     rax, [rcx]
0x18005d2e4  mov     rax, [rax+20h]
0x18005d2e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d2ed  test    eax, eax
0x18005d2ef  jz      short loc_18005D30C
0x18005d2f1  lea     rdx, aCallerIsNotInt; "Caller is not interactive session user."
0x18005d2f8  mov     ecx, 4; int
0x18005d2fd  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005d302  mov     edi, 80070005h
0x18005d307  jmp     loc_18005D477
0x18005d30c  mov     rax, [rbx]
0x18005d30f  lea     rdx, [rsp+350h+pv]
0x18005d314  mov     rcx, rbx
0x18005d317  mov     rax, [rax+78h]
0x18005d31b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d320  mov     edi, eax
0x18005d322  test    eax, eax
0x18005d324  jns     short loc_18005D332
0x18005d326  lea     rdx, aPtrcallerusern; "ptrCallerUserName->GetLogonSid failed: "...
0x18005d32d  jmp     loc_18005D1EB
0x18005d332  mov     rax, [rbx]
0x18005d335  lea     rdx, [rsp+350h+pSid]
0x18005d33a  mov     rcx, rbx
0x18005d33d  mov     rax, [rax+48h]
0x18005d341  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d346  mov     edi, eax
0x18005d348  test    eax, eax
0x18005d34a  jns     short loc_18005D358
0x18005d34c  lea     rdx, aPtrcallerusern_1; "ptrCallerUserName->GetUserSid failed: 0"...
0x18005d353  jmp     loc_18005D1EB
0x18005d358  lea     rcx, [rbp+250h+var_2C8]; struct IRemoteConnectionManager **
0x18005d35c  call    ?GetInstanceOfRemoteConnectionManager@@YAJPEAPEAVIRemoteConnectionManager@@@Z; GetInstanceOfRemoteConnectionManager(IRemoteConnectionManager * *)
0x18005d361  mov     rcx, [rbp+250h+var_2C8]
0x18005d365  lea     rdx, [rbp+250h+var_2D0]
0x18005d369  mov     rax, [rcx]
0x18005d36c  mov     rax, [rax+78h]
0x18005d370  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d375  mov     rcx, [rbp+250h+var_2D0]
0x18005d379  lea     r8, [rsp+350h+var_2D8]
0x18005d37e  lea     rdx, a7a78855482a04f; "7A78855482A04FA781DC"
0x18005d385  mov     rax, [rcx]
0x18005d388  mov     rax, [rax+30h]
0x18005d38c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d391  mov     edi, eax
0x18005d393  test    eax, eax
0x18005d395  jns     short loc_18005D3A3
0x18005d397  lea     rdx, aPtrlistenerlis; "ptrListenerList->GetListenerByName fail"...
0x18005d39e  jmp     loc_18005D1EB
0x18005d3a3  mov     rcx, [rsp+350h+var_2D8]
0x18005d3a8  lea     rdx, [rsp+350h+var_2E0]
0x18005d3ad  mov     rax, [rcx]
0x18005d3b0  mov     rax, [rax+90h]
0x18005d3b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d3bc  mov     edi, eax
0x18005d3be  test    eax, eax
0x18005d3c0  jns     short loc_18005D3CE
0x18005d3c2  lea     rdx, aPtrlistenerGet; "ptrListener->GetProtocolListener failed"...
0x18005d3c9  jmp     loc_18005D1EB
0x18005d3ce  mov     rcx, [rsp+350h+var_2E0]
0x18005d3d3  lea     r8, [rsp+350h+var_2E8]
0x18005d3d8  lea     rdx, IID_IWRdsProtocolDebugListener
0x18005d3df  mov     rax, [rcx]
0x18005d3e2  mov     rax, [rax]
0x18005d3e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d3ea  mov     edi, eax
0x18005d3ec  test    eax, eax
0x18005d3ee  jns     short loc_18005D3FC
0x18005d3f0  lea     rdx, aCheckForDebugL; "Check for debug listener failed: 0x%x i"...
0x18005d3f7  jmp     loc_18005D1EB
0x18005d3fc  mov     r15, [rsp+350h+var_2E8]
0x18005d401  mov     rcx, [rsp+350h+pSid]; pSid
0x18005d406  mov     esi, [rsp+350h+var_300]
0x18005d40a  mov     rax, [r15]
0x18005d40d  mov     r14, [rax+18h]
0x18005d411  call    cs:__imp_GetLengthSid
0x18005d417  mov     rcx, [rsp+350h+pv]; pSid
0x18005d41c  mov     ebx, eax
0x18005d41e  mov     rdi, [rsp+350h+pSid]
0x18005d423  call    cs:__imp_GetLengthSid
0x18005d429  mov     rdx, [rsp+350h+pv]
0x18005d42e  mov     r9, rdi
0x18005d431  mov     [rsp+350h+var_310], r13d
0x18005d436  mov     r8d, eax
0x18005d439  mov     [rsp+350h+var_318], r12
0x18005d43e  mov     rax, r14
0x18005d441  mov     [rsp+350h+var_320], 0
0x18005d449  mov     rcx, r15
0x18005d44c  mov     [rsp+350h+var_328], esi
0x18005d450  mov     [rsp+350h+var_330], ebx
0x18005d454  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d459  mov     edi, eax
0x18005d45b  test    eax, eax
0x18005d45d  jns     short loc_18005D477
0x18005d45f  lea     r9, aRpccreatechild; "RpcCreateChildSessionTransport"
0x18005d466  lea     rdx, aPtrdebuglisten; "ptrDebugListener->CreateDebugNamedPipe "...
0x18005d46d  jmp     loc_18005D1EE
0x18005d472  mov     edi, 80070057h
0x18005d477  mov     rcx, [rsp+350h+pv]; pv
0x18005d47c  test    rcx, rcx
0x18005d47f  jz      short loc_18005D487
0x18005d481  call    cs:__imp_CoTaskMemFree
0x18005d487  mov     rcx, [rsp+350h+pSid]; pv
0x18005d48c  test    rcx, rcx
0x18005d48f  jz      short loc_18005D497
0x18005d491  call    cs:__imp_CoTaskMemFree
0x18005d497  lea     rcx, [rsp+350h+var_2E8]; void *
0x18005d49c  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x18005d4a1  lea     rcx, [rsp+350h+var_2E0]; void *
0x18005d4a6  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x18005d4ab  lea     rcx, [rsp+350h+var_2D8]; void *
0x18005d4b0  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x18005d4b5  lea     rcx, [rbp+250h+var_2D0]; void *
0x18005d4b9  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x18005d4be  lea     rcx, [rbp+250h+var_2C8]; void *
0x18005d4c2  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x18005d4c7  lea     rcx, [rbp+250h+var_2C0]; void *
0x18005d4cb  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x18005d4d0  lea     rcx, [rbp+250h+var_2B8]; void *
0x18005d4d4  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x18005d4d9  lea     rcx, [rbp+250h+var_2B0]; void *
0x18005d4dd  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x18005d4e2  lea     rcx, [rbp+250h+var_2A8]; void *
0x18005d4e6  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x18005d4eb  lea     rcx, [rbp+250h+var_2A0]; this
0x18005d4ef  call    ??1SmartHANDLE@@QEAA@XZ; SmartHANDLE::~SmartHANDLE(void)
0x18005d4f4  lea     rcx, [rbp+250h+var_290]; this
0x18005d4f8  call    ??1CRpcCallTrace@@UEAA@XZ; CRpcCallTrace::~CRpcCallTrace(void)
0x18005d4fd  mov     eax, edi
0x18005d4ff  mov     rcx, [rbp+250h+var_40]
0x18005d506  xor     rcx, rsp; StackCookie
0x18005d509  call    __security_check_cookie
0x18005d50e  mov     rbx, [rsp+350h+arg_18]
0x18005d516  add     rsp, 320h
0x18005d51d  pop     r15
0x18005d51f  pop     r14
0x18005d521  pop     r13
0x18005d523  pop     r12
0x18005d525  pop     rdi
0x18005d526  pop     rsi
0x18005d527  pop     rbp
0x18005d528  retn
```
