# RpcCreateChildSessionTransport

- ea: `0x18005ffe0`
- end: `0x180060412`
- name: `RpcCreateChildSessionTransport`
- size: `1074`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

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
- `0x18005ffe0`
- `0x180060420`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800602e1`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800602f9`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800602e1`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800602f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006035d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180060373`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006035d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180060373`

## string_xrefs

- `0x1800600b4`: `CRpcUtils::GetClientToken failed: 0x%x in %s`
- `0x1800601f6`: `ptrCallerUserName->GetLogonSid failed: 0x%x in %s`
- `0x18006021c`: `ptrCallerUserName->GetUserSid failed: 0x%x in %s`
- `0x180060292`: `ptrListener->GetProtocolListener failed: 0x%x in %s`
- `0x180060342`: `ptrDebugListener->CreateDebugNamedPipe failed: 0x%x in %s`
- `0x180060013`: `RpcCreateChildSessionTransport`
- `0x18006033b`: `RpcCreateChildSessionTransport`

## pseudocode

```c
__int64 __fastcall RpcCreateChildSessionTransport(__int64 a1, __int64 a2, int a3)
{
  unsigned int LoopbackSessionTransport; // edi
  int ClientToken; // eax
  const char *v8; // rdx
  struct IUserName *v9; // rbx
  int v10; // eax
  __int64 v11; // r15
  unsigned int v12; // esi
  __int64 (__fastcall *v13)(__int64, PSID, _QWORD, PSID, DWORD, unsigned int, _DWORD, __int64, int); // r14
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
                        v13 = *(__int64 (__fastcall **)(__int64, PSID, _QWORD, PSID, DWORD, unsigned int, _DWORD, __int64, int))(*(_QWORD *)v21 + 24LL);
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
0x18005ffe0  mov     [rsp-8+arg_18], rbx
0x18005ffe5  push    rbp
0x18005ffe6  push    rsi
0x18005ffe7  push    rdi
0x18005ffe8  push    r12
0x18005ffea  push    r13
0x18005ffec  push    r14
0x18005ffee  push    r15
0x18005fff0  lea     rbp, [rsp-220h]
0x18005fff8  sub     rsp, 320h
0x18005ffff  mov     rax, cs:__security_cookie
0x180060006  xor     rax, rsp
0x180060009  mov     [rbp+250h+var_40], rax
0x180060010  mov     r13d, r8d
0x180060013  lea     r14, aRpccreatechild; "RpcCreateChildSessionTransport"
0x18006001a  mov     r12, rdx
0x18006001d  mov     rbx, rcx
0x180060020  mov     r8, r14; char *
0x180060023  lea     rcx, [rbp+250h+var_290]; this
0x180060027  xor     edx, edx; int
0x180060029  call    ??0CRpcCallTrace@@QEAA@HPEBD@Z; CRpcCallTrace::CRpcCallTrace(int,char const *)
0x18006002e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID56916126@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID56916126@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56916126> `wil::Feature<__WilFeatureTraits_Feature_ID56916126>::GetImpl(void)'::`2'::impl
0x180060035  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID56916126@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56916126>::__private_IsEnabled(void)
0x18006003a  xor     esi, esi
0x18006003c  test    al, al
0x18006003e  jz      short loc_180060058
0x180060040  mov     r9d, r13d
0x180060043  lea     edx, [rsi+7]
0x180060046  mov     r8, r12
0x180060049  mov     rcx, rbx
0x18006004c  call    RpcCreateLoopbackSessionTransport
0x180060051  mov     edi, eax
0x180060053  jmp     loc_1800603DC
0x180060058  mov     [rbp+250h+var_2A0], rsi
0x18006005c  mov     [rbp+250h+var_2A8], rsi
0x180060060  mov     [rbp+250h+var_2B0], rsi
0x180060064  mov     [rsp+350h+var_300], esi
0x180060068  mov     [rbp+250h+var_2B8], rsi
0x18006006c  mov     [rbp+250h+var_2C0], rsi
0x180060070  mov     [rsp+350h+pv], rsi
0x180060075  mov     [rsp+350h+pSid], rsi
0x18006007a  mov     [rbp+250h+var_2C8], rsi
0x18006007e  mov     [rbp+250h+var_2D0], rsi
0x180060082  mov     [rsp+350h+var_2D8], rsi
0x180060087  mov     [rsp+350h+var_2E0], rsi
0x18006008c  mov     [rsp+350h+var_2E8], rsi
0x180060091  test    r12, r12
0x180060094  jz      loc_18006034E
0x18006009a  test    r13d, r13d
0x18006009d  jz      loc_18006034E
0x1800600a3  xor     edx, edx; int
0x1800600a5  lea     rcx, [rbp+250h+var_2A0]; void **
0x1800600a9  call    ?GetClientToken@CRpcUtils@@SAJPEAPEAXH@Z; CRpcUtils::GetClientToken(void * *,int)
0x1800600ae  mov     edi, eax
0x1800600b0  test    eax, eax
0x1800600b2  jns     short loc_1800600D0
0x1800600b4  lea     rdx, aCrpcutilsGetcl_0; "CRpcUtils::GetClientToken failed: 0x%x "...
0x1800600bb  mov     r9, r14
0x1800600be  mov     ecx, 8; int
0x1800600c3  mov     r8d, eax
0x1800600c6  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800600cb  jmp     loc_180060353
0x1800600d0  lea     rcx, [rbp+250h+var_2A8]; struct IUserName **
0x1800600d4  call    ?GetInstanceOfUserName@CUtils@@SAJPEAPEAUIUserName@@@Z; CUtils::GetInstanceOfUserName(IUserName * *)
0x1800600d9  mov     edi, eax
0x1800600db  test    eax, eax
0x1800600dd  jns     short loc_1800600E8
0x1800600df  lea     rdx, aCutilsGetinsta; "CUtils::GetInstanceOfUserName failed: 0"...
0x1800600e6  jmp     short loc_1800600BB
0x1800600e8  mov     rbx, [rbp+250h+var_2A8]
0x1800600ec  mov     r8d, 1
0x1800600f2  mov     rdx, [rbp+250h+var_2A0]
0x1800600f6  mov     rcx, rbx
0x1800600f9  mov     rax, [rbx]
0x1800600fc  mov     rax, [rax+18h]
0x180060100  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060105  mov     edi, eax
0x180060107  test    eax, eax
0x180060109  jns     short loc_180060114
0x18006010b  lea     rdx, aPtrcallerusern_2; "ptrCallerUserName->Initialize failed: 0"...
0x180060112  jmp     short loc_1800600BB
0x180060114  mov     rax, [rbx]
0x180060117  lea     rdx, [rsp+350h+var_300]
0x18006011c  mov     rcx, rbx
0x18006011f  mov     rax, [rax+70h]
0x180060123  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060128  mov     edi, eax
0x18006012a  test    eax, eax
0x18006012c  jns     short loc_180060137
0x18006012e  lea     rdx, aPtrcallerusern_3; "ptrCallerUserName->GetSessionId failed:"...
0x180060135  jmp     short loc_1800600BB
0x180060137  lea     rcx, [rbp+250h+var_2B8]; struct ISessionList **
0x18006013b  call    ?GetSessionList@CHelper@@SAJPEAPEAUISessionList@@@Z; CHelper::GetSessionList(ISessionList * *)
0x180060140  mov     edi, eax
0x180060142  test    eax, eax
0x180060144  jns     short loc_180060152
0x180060146  lea     rdx, aChelperGetsess; "CHelper::GetSessionList failed: 0x%x in"...
0x18006014d  jmp     loc_1800600BB
0x180060152  mov     rcx, [rbp+250h+var_2B8]
0x180060156  lea     r8, [rbp+250h+var_2C0]
0x18006015a  mov     edx, [rsp+350h+var_300]
0x18006015e  mov     rax, [rcx]
0x180060161  mov     rax, [rax+18h]
0x180060165  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006016a  mov     edi, eax
0x18006016c  test    eax, eax
0x18006016e  jns     short loc_180060184
0x180060170  mov     r9, r14
0x180060173  lea     rdx, aPtrlistFindses; "ptrList->FindSessionById failed: 0x%x i"...
0x18006017a  mov     ecx, 4
0x18006017f  jmp     loc_1800600C3
0x180060184  mov     rcx, [rbp+250h+var_2C0]
0x180060188  lea     rdx, [rbp+250h+var_2B0]
0x18006018c  mov     rax, [rcx]
0x18006018f  mov     rax, [rax+60h]
0x180060193  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060198  mov     edi, eax
0x18006019a  test    eax, eax
0x18006019c  jns     short loc_1800601AA
0x18006019e  lea     rdx, aPtrsessionGetu_0; "ptrSession->getUserName failed: 0x%x in"...
0x1800601a5  jmp     loc_1800600BB
0x1800601aa  mov     rcx, [rbp+250h+var_2B0]
0x1800601ae  mov     rdx, rbx
0x1800601b1  mov     rax, [rcx]
0x1800601b4  mov     rax, [rax+20h]
0x1800601b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800601bd  test    eax, eax
0x1800601bf  jz      short loc_1800601DC
0x1800601c1  lea     rdx, aCallerIsNotInt; "Caller is not interactive session user."
0x1800601c8  mov     ecx, 4; int
0x1800601cd  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800601d2  mov     edi, 80070005h
0x1800601d7  jmp     loc_180060353
0x1800601dc  mov     rax, [rbx]
0x1800601df  lea     rdx, [rsp+350h+pv]
0x1800601e4  mov     rcx, rbx
0x1800601e7  mov     rax, [rax+78h]
0x1800601eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800601f0  mov     edi, eax
0x1800601f2  test    eax, eax
0x1800601f4  jns     short loc_180060202
0x1800601f6  lea     rdx, aPtrcallerusern; "ptrCallerUserName->GetLogonSid failed: "...
0x1800601fd  jmp     loc_1800600BB
0x180060202  mov     rax, [rbx]
0x180060205  lea     rdx, [rsp+350h+pSid]
0x18006020a  mov     rcx, rbx
0x18006020d  mov     rax, [rax+48h]
0x180060211  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060216  mov     edi, eax
0x180060218  test    eax, eax
0x18006021a  jns     short loc_180060228
0x18006021c  lea     rdx, aPtrcallerusern_1; "ptrCallerUserName->GetUserSid failed: 0"...
0x180060223  jmp     loc_1800600BB
0x180060228  lea     rcx, [rbp+250h+var_2C8]; struct IRemoteConnectionManager **
0x18006022c  call    ?GetInstanceOfRemoteConnectionManager@@YAJPEAPEAVIRemoteConnectionManager@@@Z; GetInstanceOfRemoteConnectionManager(IRemoteConnectionManager * *)
0x180060231  mov     rcx, [rbp+250h+var_2C8]
0x180060235  lea     rdx, [rbp+250h+var_2D0]
0x180060239  mov     rax, [rcx]
0x18006023c  mov     rax, [rax+78h]
0x180060240  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060245  mov     rcx, [rbp+250h+var_2D0]
0x180060249  lea     r8, [rsp+350h+var_2D8]
0x18006024e  lea     rdx, a7a78855482a04f; "7A78855482A04FA781DC"
0x180060255  mov     rax, [rcx]
0x180060258  mov     rax, [rax+30h]
0x18006025c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060261  mov     edi, eax
0x180060263  test    eax, eax
0x180060265  jns     short loc_180060273
0x180060267  lea     rdx, aPtrlistenerlis; "ptrListenerList->GetListenerByName fail"...
0x18006026e  jmp     loc_1800600BB
0x180060273  mov     rcx, [rsp+350h+var_2D8]
0x180060278  lea     rdx, [rsp+350h+var_2E0]
0x18006027d  mov     rax, [rcx]
0x180060280  mov     rax, [rax+90h]
0x180060287  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006028c  mov     edi, eax
0x18006028e  test    eax, eax
0x180060290  jns     short loc_18006029E
0x180060292  lea     rdx, aPtrlistenerGet; "ptrListener->GetProtocolListener failed"...
0x180060299  jmp     loc_1800600BB
0x18006029e  mov     rcx, [rsp+350h+var_2E0]
0x1800602a3  lea     r8, [rsp+350h+var_2E8]
0x1800602a8  lea     rdx, IID_IWRdsProtocolDebugListener
0x1800602af  mov     rax, [rcx]
0x1800602b2  mov     rax, [rax]
0x1800602b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800602ba  mov     edi, eax
0x1800602bc  test    eax, eax
0x1800602be  jns     short loc_1800602CC
0x1800602c0  lea     rdx, aCheckForDebugL; "Check for debug listener failed: 0x%x i"...
0x1800602c7  jmp     loc_1800600BB
0x1800602cc  mov     r15, [rsp+350h+var_2E8]
0x1800602d1  mov     rcx, [rsp+350h+pSid]; pSid
0x1800602d6  mov     esi, [rsp+350h+var_300]
0x1800602da  mov     rax, [r15]
0x1800602dd  mov     r14, [rax+18h]
0x1800602e1  call    cs:__imp_GetLengthSid
0x1800602e8  nop     dword ptr [rax+rax+00h]
0x1800602ed  mov     rcx, [rsp+350h+pv]; pSid
0x1800602f2  mov     ebx, eax
0x1800602f4  mov     rdi, [rsp+350h+pSid]
0x1800602f9  call    cs:__imp_GetLengthSid
0x180060300  nop     dword ptr [rax+rax+00h]
0x180060305  mov     rdx, [rsp+350h+pv]
0x18006030a  mov     r9, rdi
0x18006030d  mov     [rsp+350h+var_310], r13d
0x180060312  mov     r8d, eax
0x180060315  mov     [rsp+350h+var_318], r12
0x18006031a  mov     rax, r14
0x18006031d  mov     [rsp+350h+var_320], 0
0x180060325  mov     rcx, r15
0x180060328  mov     [rsp+350h+var_328], esi
0x18006032c  mov     [rsp+350h+var_330], ebx
0x180060330  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060335  mov     edi, eax
0x180060337  test    eax, eax
0x180060339  jns     short loc_180060353
0x18006033b  lea     r9, aRpccreatechild; "RpcCreateChildSessionTransport"
0x180060342  lea     rdx, aPtrdebuglisten; "ptrDebugListener->CreateDebugNamedPipe "...
0x180060349  jmp     loc_1800600BE
0x18006034e  mov     edi, 80070057h
0x180060353  mov     rcx, [rsp+350h+pv]; pv
0x180060358  test    rcx, rcx
0x18006035b  jz      short loc_180060369
0x18006035d  call    cs:__imp_CoTaskMemFree
0x180060364  nop     dword ptr [rax+rax+00h]
0x180060369  mov     rcx, [rsp+350h+pSid]; pv
0x18006036e  test    rcx, rcx
0x180060371  jz      short loc_18006037F
0x180060373  call    cs:__imp_CoTaskMemFree
0x18006037a  nop     dword ptr [rax+rax+00h]
0x18006037f  lea     rcx, [rsp+350h+var_2E8]; void *
0x180060384  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x180060389  lea     rcx, [rsp+350h+var_2E0]; void *
0x18006038e  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x180060393  lea     rcx, [rsp+350h+var_2D8]; void *
0x180060398  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x18006039d  lea     rcx, [rbp+250h+var_2D0]; void *
0x1800603a1  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x1800603a6  lea     rcx, [rbp+250h+var_2C8]; void *
0x1800603aa  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x1800603af  lea     rcx, [rbp+250h+var_2C0]; void *
0x1800603b3  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x1800603b8  lea     rcx, [rbp+250h+var_2B8]; void *
0x1800603bc  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x1800603c1  lea     rcx, [rbp+250h+var_2B0]; void *
0x1800603c5  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x1800603ca  lea     rcx, [rbp+250h+var_2A8]; void *
0x1800603ce  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x1800603d3  lea     rcx, [rbp+250h+var_2A0]; this
0x1800603d7  call    ??1SmartHANDLE@@QEAA@XZ; SmartHANDLE::~SmartHANDLE(void)
0x1800603dc  lea     rcx, [rbp+250h+var_290]; this
0x1800603e0  call    ??1CRpcCallTrace@@UEAA@XZ; CRpcCallTrace::~CRpcCallTrace(void)
0x1800603e5  mov     eax, edi
0x1800603e7  mov     rcx, [rbp+250h+var_40]
0x1800603ee  xor     rcx, rsp; StackCookie
0x1800603f1  call    __security_check_cookie
0x1800603f6  mov     rbx, [rsp+350h+arg_18]
0x1800603fe  add     rsp, 320h
0x180060405  pop     r15
0x180060407  pop     r14
0x180060409  pop     r13
0x18006040b  pop     r12
0x18006040d  pop     rdi
0x18006040e  pop     rsi
0x18006040f  pop     rbp
0x180060410  retn
```
