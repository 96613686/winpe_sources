# CWmiEventManager::Initialize(IWbemObjectSink *)

- ea: `0x18002067c`
- end: `0x180020a25`
- name: `?Initialize@CWmiEventManager@@QEAAJPEAUIWbemObjectSink@@@Z`
- size: `937`
- prototype: `__int64 __fastcall(CWmiEventManager *__hidden this, struct IWbemObjectSink *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18001d9e0`

## callees

- `0x180005220`
- `0x18001a21c`
- `0x18002067c`
- `0x180036198`
- `0x180042010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800208b2`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800208b2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800206dc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180020705`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180020761`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800206dc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180020705`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180020761`
- `OLEAUT32!__imp_SysFreeString` at `0x18002087d`
- `OLEAUT32!__imp_SysFreeString` at `0x18002098b`
- `OLEAUT32!__imp_SysFreeString` at `0x18002087d`
- `OLEAUT32!__imp_SysFreeString` at `0x18002098b`

## pseudocode

```c
__int64 __fastcall CWmiEventManager::Initialize(CWmiEventManager *this, struct IWbemObjectSink *a2)
{
  struct CWmiEventSinkAvFw *v2; // rsi
  struct CWmiEventManagerAvFw *v3; // rdi
  _QWORD *v5; // r15
  HRESULT Instance; // ebx
  OLECHAR *v7; // rbp
  struct IWbemServices **v8; // rsi
  __int64 v9; // rdx
  OLECHAR *v10; // rsi
  __int64 v11; // rcx
  _QWORD v12[2]; // [rsp+50h] [rbp-38h] BYREF
  LPVOID ppv; // [rsp+98h] [rbp+10h] BYREF

  ppv = a2;
  v2 = g_pWmiEventSinkAvFw;
  v3 = g_pWmiEventManagerAvFw;
  v12[0] = 0;
  v12[1] = g_pWmiEventManagerAvFw;
  if ( !g_pWmiEventSinkAvFw )
    return 2147942487LL;
  v5 = (_QWORD *)((char *)g_pWmiEventManagerAvFw + 24);
  Instance = CoCreateInstance(
               &CLSID_ContextSwitcher,
               0,
               1u,
               &IID_IContextCallback,
               (LPVOID *)g_pWmiEventManagerAvFw + 3);
  if ( Instance >= 0 )
  {
    Instance = CoCreateInstance(&CLSID_StdGlobalInterfaceTable, 0, 1u, &IID_IGlobalInterfaceTable, (LPVOID *)v3 + 2);
    if ( Instance >= 0 )
      Instance = (*(__int64 (__fastcall **)(_QWORD, struct CWmiEventSinkAvFw *, GUID *, __int64))(**((_QWORD **)v3 + 2)
                                                                                                + 24LL))(
                   *((_QWORD *)v3 + 2),
                   v2,
                   &IID_IWbemObjectSink,
                   (__int64)v3 + 8);
  }
  ppv = 0;
  if ( Instance >= 0 )
  {
    Instance = CoCreateInstance(&CLSID_WbemLocator, 0, 1u, &IID_IWbemLocator, &ppv);
    if ( Instance >= 0 )
    {
      v7 = (OLECHAR *)(*(__int64 (__fastcall **)(struct CWmiEventManagerAvFw *, __int64))(*(_QWORD *)v3 + 8LL))(v3, 1);
      if ( v7 )
      {
        v8 = (struct IWbemServices **)((char *)v3 + 64);
        Instance = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, __int64))(*(_QWORD *)ppv + 24LL))(
                     ppv,
                     v7,
                     0,
                     0,
                     0,
                     0,
                     0,
                     0,
                     (__int64)v3 + 64);
        LOBYTE(v9) = 1;
        wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WSCPersistAMPPLDataToWmi>::ReportUsage(
          `wil::Feature<__WilFeatureTraits_Feature_Servicing_WSCPersistAMPPLDataToWmi>::GetImpl'::`2'::impl,
          v9);
        if ( Instance == -2147217394
          || Instance >= 0
          && (!CheckClassExists(*v8, L"AntiVirusProduct")
           || !CheckClassExists(*v8, L"FirewallProduct")
           || !CheckClassExists(*v8, L"AntiSpywareProduct")
           || !CheckClassExists(*v8, L"WSC_CallerAMPPLData")) )
        {
          Instance = CWmiEventManager::CompileMofFile();
          if ( Instance >= 0 )
            Instance = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, __int64))(*(_QWORD *)ppv + 24LL))(
                         ppv,
                         v7,
                         0,
                         0,
                         0,
                         0,
                         0,
                         0,
                         (__int64)v3 + 64);
        }
        SysFreeString(v7);
        if ( Instance >= 0 )
        {
          Instance = CoSetProxyBlanket(
                       (IUnknown *)*v8,
                       0xFFFFFFFF,
                       0xFFFFFFFF,
                       (OLECHAR *)0xFFFFFFFFFFFFFFFFLL,
                       0,
                       3u,
                       0,
                       0x40u);
          if ( Instance >= 0 )
          {
            v10 = (OLECHAR *)(*(__int64 (__fastcall **)(struct CWmiEventManagerAvFw *, _QWORD))(*(_QWORD *)v3 + 8LL))(
                               v3,
                               0);
            if ( v10 )
            {
              Instance = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, __int64))(*(_QWORD *)ppv + 24LL))(
                           ppv,
                           v10,
                           0,
                           0,
                           0,
                           0,
                           0,
                           0,
                           (__int64)v3 + 56);
              if ( Instance >= 0 )
              {
                Instance = (*(__int64 (__fastcall **)(_QWORD, __int64 (__fastcall *)(struct tagComCallData *), _QWORD *, GUID *, int, _QWORD))(*(_QWORD *)*v5 + 24LL))(
                             *v5,
                             CWmiEventManager::ChainProxyInDisconnectContext,
                             v12,
                             &IID_IContextCallback,
                             5,
                             0);
                if ( Instance >= 0 )
                {
                  Instance = (*(__int64 (__fastcall **)(_QWORD, _QWORD, GUID *, __int64))(**((_QWORD **)v3 + 2) + 40LL))(
                               *((_QWORD *)v3 + 2),
                               *((unsigned int *)v3 + 3),
                               &IID_IWbemObjectSink,
                               (__int64)v3 + 48);
                  if ( Instance >= 0 )
                    Instance = (**(__int64 (__fastcall ***)(struct CWmiEventManagerAvFw *))v3)(v3);
                }
              }
              SysFreeString(v10);
            }
            else
            {
              Instance = -2147024882;
            }
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
            ppv = 0;
          }
        }
      }
      else
      {
        Instance = -2147024882;
      }
    }
  }
  v11 = *((_QWORD *)v3 + 2);
  if ( v11 )
  {
    if ( *((_DWORD *)v3 + 3) )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 32LL))(v11);
      *((_DWORD *)v3 + 3) = 0;
    }
    if ( *((_DWORD *)v3 + 2) )
    {
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v3 + 2) + 32LL))(*((_QWORD *)v3 + 2));
      *((_DWORD *)v3 + 2) = 0;
    }
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v3 + 2) + 16LL))(*((_QWORD *)v3 + 2));
    *((_QWORD *)v3 + 2) = 0;
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18002067c  mov     rax, rsp
0x18002067f  mov     [rax+8], rbx
0x180020683  mov     [rax+18h], rbp
0x180020687  mov     [rax+10h], rdx
0x18002068b  push    rsi
0x18002068c  push    rdi
0x18002068d  push    r12
0x18002068f  push    r14
0x180020691  push    r15
0x180020693  sub     rsp, 60h
0x180020697  mov     rsi, cs:?g_pWmiEventSinkAvFw@@3PEAVCWmiEventSinkAvFw@@EA; CWmiEventSinkAvFw * g_pWmiEventSinkAvFw
0x18002069e  xor     r12d, r12d
0x1800206a1  mov     rdi, cs:?g_pWmiEventManagerAvFw@@3PEAVCWmiEventManagerAvFw@@EA; CWmiEventManagerAvFw * g_pWmiEventManagerAvFw
0x1800206a8  mov     [rax-38h], r12
0x1800206ac  mov     [rax-30h], rdi
0x1800206b0  test    rsi, rsi
0x1800206b3  jnz     short loc_1800206BF
0x1800206b5  mov     eax, 80070057h
0x1800206ba  jmp     loc_180020A0C
0x1800206bf  xor     edx, edx; pUnkOuter
0x1800206c1  lea     r15, [rdi+18h]
0x1800206c5  lea     r9, IID_IContextCallback; riid
0x1800206cc  mov     [rsp+88h+ppv], r15; ppv
0x1800206d1  lea     rcx, CLSID_ContextSwitcher; rclsid
0x1800206d8  lea     r8d, [rdx+1]; dwClsContext
0x1800206dc  call    cs:__imp_CoCreateInstance
0x1800206e2  mov     ebx, eax
0x1800206e4  test    eax, eax
0x1800206e6  js      short loc_180020730
0x1800206e8  xor     edx, edx; pUnkOuter
0x1800206ea  lea     r14, [rdi+10h]
0x1800206ee  lea     r9, IID_IGlobalInterfaceTable; riid
0x1800206f5  mov     [rsp+88h+ppv], r14; ppv
0x1800206fa  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180020701  lea     r8d, [rdx+1]; dwClsContext
0x180020705  call    cs:__imp_CoCreateInstance
0x18002070b  mov     ebx, eax
0x18002070d  test    eax, eax
0x18002070f  js      short loc_180020730
0x180020711  mov     rcx, [r14]
0x180020714  lea     r9, [rdi+8]
0x180020718  lea     r8, IID_IWbemObjectSink
0x18002071f  mov     rdx, rsi
0x180020722  mov     rax, [rcx]
0x180020725  mov     rax, [rax+18h]
0x180020729  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002072e  mov     ebx, eax
0x180020730  mov     [rsp+88h+arg_8], r12
0x180020738  test    ebx, ebx
0x18002073a  js      loc_1800209BB
0x180020740  xor     edx, edx; pUnkOuter
0x180020742  lea     rax, [rsp+88h+arg_8]
0x18002074a  lea     r9, IID_IWbemLocator; riid
0x180020751  mov     [rsp+88h+ppv], rax; ppv
0x180020756  lea     rcx, CLSID_WbemLocator; rclsid
0x18002075d  lea     r8d, [rdx+1]; dwClsContext
0x180020761  call    cs:__imp_CoCreateInstance
0x180020767  mov     ebx, eax
0x180020769  test    eax, eax
0x18002076b  js      loc_1800209BB
0x180020771  mov     rax, [rdi]
0x180020774  mov     edx, 1
0x180020779  mov     rcx, rdi
0x18002077c  mov     rax, [rax+8]
0x180020780  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020785  mov     rbp, rax
0x180020788  test    rax, rax
0x18002078b  jz      loc_1800209B6
0x180020791  mov     rcx, [rsp+88h+arg_8]
0x180020799  lea     rsi, [rdi+40h]
0x18002079d  mov     [rsp+88h+var_48], rsi
0x1800207a2  xor     r9d, r9d
0x1800207a5  mov     qword ptr [rsp+88h+dwCapabilities], r12
0x1800207aa  xor     r8d, r8d
0x1800207ad  mov     [rsp+88h+pAuthInfo], r12
0x1800207b2  mov     rdx, [rcx]
0x1800207b5  mov     [rsp+88h+dwImpLevel], r12d
0x1800207ba  mov     [rsp+88h+ppv], r12
0x1800207bf  mov     rax, [rdx+18h]
0x1800207c3  mov     rdx, rbp
0x1800207c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800207cb  mov     ebx, eax
0x1800207cd  mov     dl, 1
0x1800207cf  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_WSCPersistAMPPLDataToWmi@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WSCPersistAMPPLDataToWmi@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WSCPersistAMPPLDataToWmi> `wil::Feature<__WilFeatureTraits_Feature_Servicing_WSCPersistAMPPLDataToWmi>::GetImpl(void)'::`2'::impl
0x1800207d6  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WSCPersistAMPPLDataToWmi@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WSCPersistAMPPLDataToWmi>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800207db  cmp     ebx, 8004100Eh
0x1800207e1  jz      short loc_180020837
0x1800207e3  test    ebx, ebx
0x1800207e5  js      loc_18002087A
0x1800207eb  mov     rcx, [rsi]; struct IWbemServices *
0x1800207ee  lea     rdx, aAntivirusprodu; "AntiVirusProduct"
0x1800207f5  call    ?CheckClassExists@@YA_NPEAUIWbemServices@@PEBG@Z; CheckClassExists(IWbemServices *,ushort const *)
0x1800207fa  test    al, al
0x1800207fc  jz      short loc_180020837
0x1800207fe  mov     rcx, [rsi]; struct IWbemServices *
0x180020801  lea     rdx, aFirewallproduc_1; "FirewallProduct"
0x180020808  call    ?CheckClassExists@@YA_NPEAUIWbemServices@@PEBG@Z; CheckClassExists(IWbemServices *,ushort const *)
0x18002080d  test    al, al
0x18002080f  jz      short loc_180020837
0x180020811  mov     rcx, [rsi]; struct IWbemServices *
0x180020814  lea     rdx, aAntispywarepro; "AntiSpywareProduct"
0x18002081b  call    ?CheckClassExists@@YA_NPEAUIWbemServices@@PEBG@Z; CheckClassExists(IWbemServices *,ushort const *)
0x180020820  test    al, al
0x180020822  jz      short loc_180020837
0x180020824  mov     rcx, [rsi]; struct IWbemServices *
0x180020827  lea     rdx, psz; "WSC_CallerAMPPLData"
0x18002082e  call    ?CheckClassExists@@YA_NPEAUIWbemServices@@PEBG@Z; CheckClassExists(IWbemServices *,ushort const *)
0x180020833  test    al, al
0x180020835  jnz     short loc_18002087A
0x180020837  call    ?CompileMofFile@CWmiEventManager@@CAJXZ; CWmiEventManager::CompileMofFile(void)
0x18002083c  mov     ebx, eax
0x18002083e  test    eax, eax
0x180020840  js      short loc_18002087A
0x180020842  mov     rcx, [rsp+88h+arg_8]
0x18002084a  xor     r9d, r9d
0x18002084d  mov     [rsp+88h+var_48], rsi
0x180020852  xor     r8d, r8d
0x180020855  mov     qword ptr [rsp+88h+dwCapabilities], r12
0x18002085a  mov     rdx, rbp
0x18002085d  mov     [rsp+88h+pAuthInfo], r12
0x180020862  mov     rax, [rcx]
0x180020865  mov     [rsp+88h+dwImpLevel], r12d
0x18002086a  mov     [rsp+88h+ppv], r12
0x18002086f  mov     rax, [rax+18h]
0x180020873  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020878  mov     ebx, eax
0x18002087a  mov     rcx, rbp; bstrString
0x18002087d  call    cs:__imp_SysFreeString
0x180020883  test    ebx, ebx
0x180020885  js      loc_1800209BB
0x18002088b  mov     rcx, [rsi]; pProxy
0x18002088e  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x180020891  mov     [rsp+88h+dwCapabilities], 40h ; '@'; dwCapabilities
0x180020899  mov     r8d, edx; dwAuthzSvc
0x18002089c  mov     [rsp+88h+pAuthInfo], r12; pAuthInfo
0x1800208a1  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x1800208a5  mov     [rsp+88h+dwImpLevel], 3; dwImpLevel
0x1800208ad  mov     dword ptr [rsp+88h+ppv], r12d; dwAuthnLevel
0x1800208b2  call    cs:__imp_CoSetProxyBlanket
0x1800208b8  mov     ebx, eax
0x1800208ba  test    eax, eax
0x1800208bc  js      loc_1800209BB
0x1800208c2  mov     rax, [rdi]
0x1800208c5  xor     edx, edx
0x1800208c7  mov     rcx, rdi
0x1800208ca  mov     rax, [rax+8]
0x1800208ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800208d3  mov     rsi, rax
0x1800208d6  test    rax, rax
0x1800208d9  jz      loc_180020993
0x1800208df  mov     rcx, [rsp+88h+arg_8]
0x1800208e7  lea     r8, [rdi+38h]
0x1800208eb  mov     [rsp+88h+var_48], r8
0x1800208f0  xor     r9d, r9d
0x1800208f3  mov     qword ptr [rsp+88h+dwCapabilities], r12
0x1800208f8  xor     r8d, r8d
0x1800208fb  mov     [rsp+88h+pAuthInfo], r12
0x180020900  mov     rdx, [rcx]
0x180020903  mov     [rsp+88h+dwImpLevel], r12d
0x180020908  mov     [rsp+88h+ppv], r12
0x18002090d  mov     rax, [rdx+18h]
0x180020911  mov     rdx, rsi
0x180020914  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020919  mov     ebx, eax
0x18002091b  test    eax, eax
0x18002091d  js      short loc_180020988
0x18002091f  mov     rcx, [r15]
0x180020922  lea     r9, IID_IContextCallback
0x180020929  mov     qword ptr [rsp+88h+dwImpLevel], r12
0x18002092e  lea     r8, [rsp+88h+var_38]
0x180020933  lea     rdx, ?ChainProxyInDisconnectContext@CWmiEventManager@@CAJPEAUtagComCallData@@@Z; CWmiEventManager::ChainProxyInDisconnectContext(tagComCallData *)
0x18002093a  mov     dword ptr [rsp+88h+ppv], 5
0x180020942  mov     rax, [rcx]
0x180020945  mov     rax, [rax+18h]
0x180020949  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002094e  mov     ebx, eax
0x180020950  test    eax, eax
0x180020952  js      short loc_180020988
0x180020954  mov     rcx, [rdi+10h]
0x180020958  lea     r9, [rdi+30h]
0x18002095c  mov     edx, [rdi+0Ch]
0x18002095f  lea     r8, IID_IWbemObjectSink
0x180020966  mov     rax, [rcx]
0x180020969  mov     rax, [rax+28h]
0x18002096d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020972  mov     ebx, eax
0x180020974  test    eax, eax
0x180020976  js      short loc_180020988
0x180020978  mov     rax, [rdi]
0x18002097b  mov     rcx, rdi
0x18002097e  mov     rax, [rax]
0x180020981  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020986  mov     ebx, eax
0x180020988  mov     rcx, rsi; bstrString
0x18002098b  call    cs:__imp_SysFreeString
0x180020991  jmp     short loc_180020998
0x180020993  mov     ebx, 8007000Eh
0x180020998  mov     rcx, [rsp+88h+arg_8]
0x1800209a0  mov     rax, [rcx]
0x1800209a3  mov     rax, [rax+10h]
0x1800209a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800209ac  mov     [rsp+88h+arg_8], r12
0x1800209b4  jmp     short loc_1800209BB
0x1800209b6  mov     ebx, 8007000Eh
0x1800209bb  mov     rcx, [rdi+10h]
0x1800209bf  test    rcx, rcx
0x1800209c2  jz      short loc_180020A0A
0x1800209c4  mov     edx, [rdi+0Ch]
0x1800209c7  test    edx, edx
0x1800209c9  jz      short loc_1800209DB
0x1800209cb  mov     rax, [rcx]
0x1800209ce  mov     rax, [rax+20h]
0x1800209d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800209d7  mov     [rdi+0Ch], r12d
0x1800209db  mov     edx, [rdi+8]
0x1800209de  test    edx, edx
0x1800209e0  jz      short loc_1800209F6
0x1800209e2  mov     rcx, [rdi+10h]
0x1800209e6  mov     rax, [rcx]
0x1800209e9  mov     rax, [rax+20h]
0x1800209ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800209f2  mov     [rdi+8], r12d
0x1800209f6  mov     rcx, [rdi+10h]
0x1800209fa  mov     rax, [rcx]
0x1800209fd  mov     rax, [rax+10h]
0x180020a01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020a06  mov     [rdi+10h], r12
0x180020a0a  mov     eax, ebx
0x180020a0c  lea     r11, [rsp+88h+var_28]
0x180020a11  mov     rbx, [r11+30h]
0x180020a15  mov     rbp, [r11+40h]
0x180020a19  mov     rsp, r11
0x180020a1c  pop     r15
0x180020a1e  pop     r14
0x180020a20  pop     r12
0x180020a22  pop     rdi
0x180020a23  pop     rsi
0x180020a24  retn
```
