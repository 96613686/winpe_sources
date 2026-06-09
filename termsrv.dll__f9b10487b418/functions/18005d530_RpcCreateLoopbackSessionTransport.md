# RpcCreateLoopbackSessionTransport

- ea: `0x18005d530`
- end: `0x18005d96a`
- name: `RpcCreateLoopbackSessionTransport`
- size: `1082`
- prototype: `__int64 __fastcall(__int64, int, __int64, int)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18005d110`

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
- `0x18005d530`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18005d841`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18005d853`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18005d841`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18005d853`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005d8bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005d8cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005d8bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005d8cc`

## string_xrefs

- `0x18005d61a`: `CRpcUtils::GetClientToken failed: 0x%x in %s`
- `0x18005d563`: `RpcCreateLoopbackSessionTransport`
- `0x18005d89a`: `RpcCreateLoopbackSessionTransport`
- `0x18005d75c`: `ptrCallerUserName->GetLogonSid failed: 0x%x in %s`
- `0x18005d782`: `ptrCallerUserName->GetUserSid failed: 0x%x in %s`
- `0x18005d7f2`: `ptrListener->GetProtocolListener failed: 0x%x in %s`
- `0x18005d820`: `Check for debug/agent listener failed: 0x%x in %s`
- `0x18005d8a1`: `ptrDebugListener->CreateDebugNamedPipe failed: 0x%x in %s`

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
0x18005d530  mov     [rsp-8+arg_0], rbx
0x18005d535  push    rbp
0x18005d536  push    rsi
0x18005d537  push    rdi
0x18005d538  push    r12
0x18005d53a  push    r13
0x18005d53c  push    r14
0x18005d53e  push    r15
0x18005d540  lea     rbp, [rsp-220h]
0x18005d548  sub     rsp, 320h
0x18005d54f  mov     rax, cs:__security_cookie
0x18005d556  xor     rax, rsp
0x18005d559  mov     [rbp+250h+var_40], rax
0x18005d560  mov     ebx, r9d
0x18005d563  lea     r15, aRpccreateloopb; "RpcCreateLoopbackSessionTransport"
0x18005d56a  mov     r13, r8
0x18005d56d  mov     [rsp+350h+var_2E8], ebx
0x18005d571  mov     r12d, edx
0x18005d574  lea     rcx, [rbp+250h+var_290]; this
0x18005d578  mov     r8, r15; char *
0x18005d57b  xor     edx, edx; int
0x18005d57d  call    ??0CRpcCallTrace@@QEAA@HPEBD@Z; CRpcCallTrace::CRpcCallTrace(int,char const *)
0x18005d582  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID56916126@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID56916126@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56916126> `wil::Feature<__WilFeatureTraits_Feature_ID56916126>::GetImpl(void)'::`2'::impl
0x18005d589  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID56916126@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56916126>::__private_IsEnabled(void)
0x18005d58e  xor     r14d, r14d
0x18005d591  test    al, al
0x18005d593  jz      loc_18005D930
0x18005d599  mov     [rbp+250h+var_298], r14
0x18005d59d  mov     [rbp+250h+var_2A0], r14
0x18005d5a1  mov     [rbp+250h+var_2A8], r14
0x18005d5a5  mov     [rsp+350h+var_300], r14d
0x18005d5aa  mov     [rbp+250h+var_2B0], r14
0x18005d5ae  mov     [rbp+250h+var_2B8], r14
0x18005d5b2  mov     [rsp+350h+pv], r14
0x18005d5b7  mov     [rsp+350h+pSid], r14
0x18005d5bc  mov     [rbp+250h+var_2C0], r14
0x18005d5c0  mov     [rbp+250h+var_2C8], r14
0x18005d5c4  mov     [rbp+250h+var_2D0], r14
0x18005d5c8  mov     [rsp+350h+var_2D8], r14
0x18005d5cd  mov     [rsp+350h+var_2E0], r14
0x18005d5d2  test    r13, r13
0x18005d5d5  jz      loc_18005D8AD
0x18005d5db  test    ebx, ebx
0x18005d5dd  jz      loc_18005D8AD
0x18005d5e3  cmp     r12d, 7
0x18005d5e7  jz      short loc_18005D602
0x18005d5e9  cmp     r12d, 9
0x18005d5ed  jz      short loc_18005D5F9
0x18005d5ef  mov     edi, 80070057h
0x18005d5f4  jmp     loc_18005D8D2
0x18005d5f9  lea     rsi, aD8d584dce21f4b; "D8D584DCE21F4BD4B923"
0x18005d600  jmp     short loc_18005D609
0x18005d602  lea     rsi, a7a78855482a04f; "7A78855482A04FA781DC"
0x18005d609  xor     edx, edx; int
0x18005d60b  lea     rcx, [rbp+250h+var_298]; void **
0x18005d60f  call    ?GetClientToken@CRpcUtils@@SAJPEAPEAXH@Z; CRpcUtils::GetClientToken(void * *,int)
0x18005d614  mov     edi, eax
0x18005d616  test    eax, eax
0x18005d618  jns     short loc_18005D636
0x18005d61a  lea     rdx, aCrpcutilsGetcl_0; "CRpcUtils::GetClientToken failed: 0x%x "...
0x18005d621  mov     r9, r15
0x18005d624  mov     ecx, 8; int
0x18005d629  mov     r8d, eax
0x18005d62c  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005d631  jmp     loc_18005D8B2
0x18005d636  lea     rcx, [rbp+250h+var_2A0]; struct IUserName **
0x18005d63a  call    ?GetInstanceOfUserName@CUtils@@SAJPEAPEAUIUserName@@@Z; CUtils::GetInstanceOfUserName(IUserName * *)
0x18005d63f  mov     edi, eax
0x18005d641  test    eax, eax
0x18005d643  jns     short loc_18005D64E
0x18005d645  lea     rdx, aCutilsGetinsta; "CUtils::GetInstanceOfUserName failed: 0"...
0x18005d64c  jmp     short loc_18005D621
0x18005d64e  mov     rbx, [rbp+250h+var_2A0]
0x18005d652  mov     r8d, 1
0x18005d658  mov     rdx, [rbp+250h+var_298]
0x18005d65c  mov     rcx, rbx
0x18005d65f  mov     rax, [rbx]
0x18005d662  mov     rax, [rax+18h]
0x18005d666  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d66b  mov     edi, eax
0x18005d66d  test    eax, eax
0x18005d66f  jns     short loc_18005D67A
0x18005d671  lea     rdx, aPtrcallerusern_2; "ptrCallerUserName->Initialize failed: 0"...
0x18005d678  jmp     short loc_18005D621
0x18005d67a  mov     rax, [rbx]
0x18005d67d  lea     rdx, [rsp+350h+var_300]
0x18005d682  mov     rcx, rbx
0x18005d685  mov     rax, [rax+70h]
0x18005d689  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d68e  mov     edi, eax
0x18005d690  test    eax, eax
0x18005d692  jns     short loc_18005D69D
0x18005d694  lea     rdx, aPtrcallerusern_3; "ptrCallerUserName->GetSessionId failed:"...
0x18005d69b  jmp     short loc_18005D621
0x18005d69d  lea     rcx, [rbp+250h+var_2B0]; struct ISessionList **
0x18005d6a1  call    ?GetSessionList@CHelper@@SAJPEAPEAUISessionList@@@Z; CHelper::GetSessionList(ISessionList * *)
0x18005d6a6  mov     edi, eax
0x18005d6a8  test    eax, eax
0x18005d6aa  jns     short loc_18005D6B8
0x18005d6ac  lea     rdx, aChelperGetsess; "CHelper::GetSessionList failed: 0x%x in"...
0x18005d6b3  jmp     loc_18005D621
0x18005d6b8  mov     rcx, [rbp+250h+var_2B0]
0x18005d6bc  lea     r8, [rbp+250h+var_2B8]
0x18005d6c0  mov     edx, [rsp+350h+var_300]
0x18005d6c4  mov     rax, [rcx]
0x18005d6c7  mov     rax, [rax+18h]
0x18005d6cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d6d0  mov     edi, eax
0x18005d6d2  test    eax, eax
0x18005d6d4  jns     short loc_18005D6EA
0x18005d6d6  mov     r9, r15
0x18005d6d9  lea     rdx, aPtrlistFindses; "ptrList->FindSessionById failed: 0x%x i"...
0x18005d6e0  mov     ecx, 4
0x18005d6e5  jmp     loc_18005D629
0x18005d6ea  mov     rcx, [rbp+250h+var_2B8]
0x18005d6ee  lea     rdx, [rbp+250h+var_2A8]
0x18005d6f2  mov     rax, [rcx]
0x18005d6f5  mov     rax, [rax+60h]
0x18005d6f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d6fe  mov     edi, eax
0x18005d700  test    eax, eax
0x18005d702  jns     short loc_18005D710
0x18005d704  lea     rdx, aPtrsessionGetu_0; "ptrSession->getUserName failed: 0x%x in"...
0x18005d70b  jmp     loc_18005D621
0x18005d710  mov     rcx, [rbp+250h+var_2A8]
0x18005d714  mov     rdx, rbx
0x18005d717  mov     rax, [rcx]
0x18005d71a  mov     rax, [rax+20h]
0x18005d71e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d723  test    eax, eax
0x18005d725  jz      short loc_18005D742
0x18005d727  lea     rdx, aCallerIsNotInt; "Caller is not interactive session user."
0x18005d72e  mov     ecx, 4; int
0x18005d733  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005d738  mov     edi, 80070005h
0x18005d73d  jmp     loc_18005D8B2
0x18005d742  mov     rax, [rbx]
0x18005d745  lea     rdx, [rsp+350h+pv]
0x18005d74a  mov     rcx, rbx
0x18005d74d  mov     rax, [rax+78h]
0x18005d751  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d756  mov     edi, eax
0x18005d758  test    eax, eax
0x18005d75a  jns     short loc_18005D768
0x18005d75c  lea     rdx, aPtrcallerusern; "ptrCallerUserName->GetLogonSid failed: "...
0x18005d763  jmp     loc_18005D621
0x18005d768  mov     rax, [rbx]
0x18005d76b  lea     rdx, [rsp+350h+pSid]
0x18005d770  mov     rcx, rbx
0x18005d773  mov     rax, [rax+48h]
0x18005d777  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d77c  mov     edi, eax
0x18005d77e  test    eax, eax
0x18005d780  jns     short loc_18005D78E
0x18005d782  lea     rdx, aPtrcallerusern_1; "ptrCallerUserName->GetUserSid failed: 0"...
0x18005d789  jmp     loc_18005D621
0x18005d78e  lea     rcx, [rbp+250h+var_2C0]; struct IRemoteConnectionManager **
0x18005d792  call    ?GetInstanceOfRemoteConnectionManager@@YAJPEAPEAVIRemoteConnectionManager@@@Z; GetInstanceOfRemoteConnectionManager(IRemoteConnectionManager * *)
0x18005d797  mov     rcx, [rbp+250h+var_2C0]
0x18005d79b  lea     rdx, [rbp+250h+var_2C8]
0x18005d79f  mov     rax, [rcx]
0x18005d7a2  mov     rax, [rax+78h]
0x18005d7a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d7ab  mov     rcx, [rbp+250h+var_2C8]
0x18005d7af  lea     r8, [rbp+250h+var_2D0]
0x18005d7b3  mov     rdx, rsi
0x18005d7b6  mov     rax, [rcx]
0x18005d7b9  mov     rax, [rax+30h]
0x18005d7bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d7c2  mov     edi, eax
0x18005d7c4  test    eax, eax
0x18005d7c6  jns     short loc_18005D7D4
0x18005d7c8  lea     rdx, aPtrlistenerlis; "ptrListenerList->GetListenerByName fail"...
0x18005d7cf  jmp     loc_18005D621
0x18005d7d4  mov     rcx, [rbp+250h+var_2D0]
0x18005d7d8  lea     rdx, [rsp+350h+var_2D8]
0x18005d7dd  mov     rax, [rcx]
0x18005d7e0  mov     rax, [rax+90h]
0x18005d7e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d7ec  mov     edi, eax
0x18005d7ee  test    eax, eax
0x18005d7f0  jns     short loc_18005D7FE
0x18005d7f2  lea     rdx, aPtrlistenerGet; "ptrListener->GetProtocolListener failed"...
0x18005d7f9  jmp     loc_18005D621
0x18005d7fe  mov     rcx, [rsp+350h+var_2D8]
0x18005d803  lea     r8, [rsp+350h+var_2E0]
0x18005d808  lea     rdx, IID_IWRdsProtocolDebugListener
0x18005d80f  mov     rax, [rcx]
0x18005d812  mov     rax, [rax]
0x18005d815  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d81a  mov     edi, eax
0x18005d81c  test    eax, eax
0x18005d81e  jns     short loc_18005D82C
0x18005d820  lea     rdx, aCheckForDebugA; "Check for debug/agent listener failed: "...
0x18005d827  jmp     loc_18005D621
0x18005d82c  mov     r15, [rsp+350h+var_2E0]
0x18005d831  mov     rcx, [rsp+350h+pSid]; pSid
0x18005d836  mov     esi, [rsp+350h+var_300]
0x18005d83a  mov     rax, [r15]
0x18005d83d  mov     r14, [rax+18h]
0x18005d841  call    cs:__imp_GetLengthSid
0x18005d847  mov     rcx, [rsp+350h+pv]; pSid
0x18005d84c  mov     ebx, eax
0x18005d84e  mov     rdi, [rsp+350h+pSid]
0x18005d853  call    cs:__imp_GetLengthSid
0x18005d859  mov     ecx, [rsp+350h+var_2E8]
0x18005d85d  xor     r8d, r8d
0x18005d860  mov     rdx, [rsp+350h+pv]
0x18005d865  cmp     r12d, 9
0x18005d869  mov     [rsp+350h+var_310], ecx
0x18005d86d  mov     r9, rdi
0x18005d870  setz    r8b
0x18005d874  mov     [rsp+350h+var_318], r13
0x18005d879  mov     [rsp+350h+var_320], r8d
0x18005d87e  mov     rcx, r15
0x18005d881  mov     r8d, eax
0x18005d884  mov     [rsp+350h+var_328], esi
0x18005d888  mov     rax, r14
0x18005d88b  mov     [rsp+350h+var_330], ebx
0x18005d88f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d894  mov     edi, eax
0x18005d896  test    eax, eax
0x18005d898  jns     short loc_18005D8B2
0x18005d89a  lea     r9, aRpccreateloopb; "RpcCreateLoopbackSessionTransport"
0x18005d8a1  lea     rdx, aPtrdebuglisten; "ptrDebugListener->CreateDebugNamedPipe "...
0x18005d8a8  jmp     loc_18005D624
0x18005d8ad  mov     edi, 80070057h
0x18005d8b2  mov     rcx, [rsp+350h+pv]; pv
0x18005d8b7  test    rcx, rcx
0x18005d8ba  jz      short loc_18005D8C2
0x18005d8bc  call    cs:__imp_CoTaskMemFree
0x18005d8c2  mov     rcx, [rsp+350h+pSid]; pv
0x18005d8c7  test    rcx, rcx
0x18005d8ca  jz      short loc_18005D8D2
0x18005d8cc  call    cs:__imp_CoTaskMemFree
0x18005d8d2  lea     rcx, [rsp+350h+var_2E0]; void *
0x18005d8d7  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x18005d8dc  lea     rcx, [rsp+350h+var_2D8]; void *
0x18005d8e1  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x18005d8e6  lea     rcx, [rbp+250h+var_2D0]; void *
0x18005d8ea  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x18005d8ef  lea     rcx, [rbp+250h+var_2C8]; void *
0x18005d8f3  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x18005d8f8  lea     rcx, [rbp+250h+var_2C0]; void *
0x18005d8fc  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x18005d901  lea     rcx, [rbp+250h+var_2B8]; void *
0x18005d905  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x18005d90a  lea     rcx, [rbp+250h+var_2B0]; void *
0x18005d90e  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x18005d913  lea     rcx, [rbp+250h+var_2A8]; void *
0x18005d917  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x18005d91c  lea     rcx, [rbp+250h+var_2A0]; void *
0x18005d920  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x18005d925  lea     rcx, [rbp+250h+var_298]; this
0x18005d929  call    ??1SmartHANDLE@@QEAA@XZ; SmartHANDLE::~SmartHANDLE(void)
0x18005d92e  jmp     short loc_18005D935
0x18005d930  mov     edi, 80004001h
0x18005d935  lea     rcx, [rbp+250h+var_290]; this
0x18005d939  call    ??1CRpcCallTrace@@UEAA@XZ; CRpcCallTrace::~CRpcCallTrace(void)
0x18005d93e  mov     eax, edi
0x18005d940  mov     rcx, [rbp+250h+var_40]
0x18005d947  xor     rcx, rsp; StackCookie
0x18005d94a  call    __security_check_cookie
0x18005d94f  mov     rbx, [rsp+350h+arg_0]
0x18005d957  add     rsp, 320h
0x18005d95e  pop     r15
0x18005d960  pop     r14
0x18005d962  pop     r13
0x18005d964  pop     r12
0x18005d966  pop     rdi
0x18005d967  pop     rsi
0x18005d968  pop     rbp
0x18005d969  retn
```
