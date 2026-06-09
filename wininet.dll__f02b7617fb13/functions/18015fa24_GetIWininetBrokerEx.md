# GetIWininetBrokerEx

- ea: `0x18015fa24`
- end: `0x18015fca1`
- name: `GetIWininetBrokerEx`
- size: `637`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1801299d4`
- `0x18015f7e0`
- `0x18015f880`
- `0x18015f940`

## callees

- `0x18014a7a0`
- `0x18015f6fc`
- `0x18015fa24`
- `0x1801e1790`
- `0x1801ee010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18015fb94`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18015fbd3`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18015fb94`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18015fbd3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18015fae9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18015fb25`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18015fae9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18015fb25`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18015fa84`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18015fa93`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18015fa84`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18015fa93`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x18015fac1`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x18015fac1`
- `iertutil!__imp_?GetBrowserElevationBrokerIEUserBrokerKnownObject@@YAJAEBU_GUID@@0PEAPEAX@Z` at `0x18015fc01`
- `iertutil!__imp_?GetBrowserElevationBrokerIEUserBrokerKnownObject@@YAJAEBU_GUID@@0PEAPEAX@Z` at `0x18015fc01`

## pseudocode

```c
__int64 __fastcall GetIWininetBrokerEx(__int64 a1, IUnknown **a2)
{
  __int64 v3; // rdx
  __int64 v4; // rcx
  HRESULT IEUserBrokerKnownObject; // ebx
  DWORD v6; // r8d
  int BrowserElevationBrokerIEUserBrokerKnownObject; // eax
  IUnknown *ppv; // [rsp+48h] [rbp-18h] BYREF
  IUnknown *pProxy; // [rsp+50h] [rbp-10h] BYREF

  ppv = 0;
  pProxy = 0;
  if ( a2 )
    *a2 = 0;
  if ( GlobalSpartanContentProcess || GlobalSpartanManager )
  {
    ppv = 0;
    BrowserElevationBrokerIEUserBrokerKnownObject = GetBrowserElevationBrokerIEUserBrokerKnownObject(
                                                      &CLSID_WininetBroker,
                                                      &GUID_b55a476b_737e_41b6_bab7_f098e81ca0eb,
                                                      (void **)&ppv);
    IEUserBrokerKnownObject = BrowserElevationBrokerIEUserBrokerKnownObject;
    if ( BrowserElevationBrokerIEUserBrokerKnownObject >= 0 )
      goto LABEL_24;
    if ( (BYTE1(xmmword_180266B50) & 0x40) != 0 )
      WPP_SF_d(
        526,
        22,
        WPP_4b50d4119023394b229b3c7cf56764e6_Traceguids,
        (unsigned int)BrowserElevationBrokerIEUserBrokerKnownObject);
  }
  else
  {
    if ( GlobalIsProcessExplorer
      && (unsigned __int8)IEConfiguration_GetBool(536870914)
      && !(unsigned __int8)IEConfiguration_GetBool(536870913) )
    {
      IEUserBrokerKnownObject = GetIEUserBrokerKnownObject(v4, v3, &ppv);
      if ( IEUserBrokerKnownObject < 0 )
        goto LABEL_25;
LABEL_24:
      *a2 = ppv;
      ppv = 0;
      goto LABEL_25;
    }
    if ( (unsigned int)IEConfiguration_GetDWORD(268435501) == 2 )
    {
      IEUserBrokerKnownObject = CoCreateInstance(
                                  &CLSID_WininetBroker,
                                  0,
                                  1u,
                                  &GUID_b55a476b_737e_41b6_bab7_f098e81ca0eb,
                                  (LPVOID *)&ppv);
      if ( IEUserBrokerKnownObject >= 0 )
        goto LABEL_24;
    }
    else
    {
      v6 = 4;
      if ( GlobalIsWow64 )
        v6 = 524292;
      IEUserBrokerKnownObject = CoCreateInstance(
                                  &CLSID_WininetBroker,
                                  0,
                                  v6,
                                  &GUID_b55a476b_737e_41b6_bab7_f098e81ca0eb,
                                  (LPVOID *)&ppv);
      if ( IEUserBrokerKnownObject >= 0 )
      {
        IEUserBrokerKnownObject = ((__int64 (__fastcall *)(IUnknown *, GUID *, IUnknown **))ppv->lpVtbl->QueryInterface)(
                                    ppv,
                                    &IID_IUnknown,
                                    &pProxy);
        if ( IEUserBrokerKnownObject >= 0 )
        {
          IEUserBrokerKnownObject = CoSetProxyBlanket(
                                      pProxy,
                                      0xFFFFFFFF,
                                      0xFFFFFFFF,
                                      (OLECHAR *)0xFFFFFFFFFFFFFFFFLL,
                                      0,
                                      3u,
                                      (RPC_AUTH_IDENTITY_HANDLE)0xFFFFFFFFFFFFFFFFLL,
                                      0x800u);
          if ( IEUserBrokerKnownObject >= 0 )
          {
            IEUserBrokerKnownObject = CoSetProxyBlanket(
                                        ppv,
                                        0xFFFFFFFF,
                                        0xFFFFFFFF,
                                        (OLECHAR *)0xFFFFFFFFFFFFFFFFLL,
                                        0,
                                        3u,
                                        (RPC_AUTH_IDENTITY_HANDLE)0xFFFFFFFFFFFFFFFFLL,
                                        0x800u);
            if ( IEUserBrokerKnownObject >= 0 )
              goto LABEL_24;
          }
        }
      }
    }
  }
LABEL_25:
  if ( pProxy )
  {
    ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
    pProxy = 0;
  }
  if ( ppv )
    ((void (__fastcall *)(IUnknown *))ppv->lpVtbl->Release)(ppv);
  return (unsigned int)IEUserBrokerKnownObject;
}

```

## disassembly

```asm
0x18015fa24  mov     [rsp-18h+arg_0], rbx
0x18015fa29  mov     [rsp-18h+arg_10], rsi
0x18015fa2e  push    rbp
0x18015fa2f  push    rdi
0x18015fa30  push    r14
0x18015fa32  mov     rbp, rsp
0x18015fa35  sub     rsp, 60h
0x18015fa39  mov     rax, cs:__security_cookie
0x18015fa40  xor     rax, rsp
0x18015fa43  mov     [rbp+var_8], rax
0x18015fa47  xor     esi, esi
0x18015fa49  mov     rdi, rdx
0x18015fa4c  mov     [rbp+var_1C], esi
0x18015fa4f  mov     [rbp+var_18], rsi
0x18015fa53  mov     [rbp+pProxy], rsi
0x18015fa57  test    rdx, rdx
0x18015fa5a  jz      short loc_18015FA5F
0x18015fa5c  mov     [rdx], rsi
0x18015fa5f  cmp     cs:GlobalSpartanContentProcess, esi
0x18015fa65  jnz     loc_18015FBE8
0x18015fa6b  cmp     cs:GlobalSpartanManager, esi
0x18015fa71  jnz     loc_18015FBE8
0x18015fa77  cmp     cs:GlobalIsProcessExplorer, esi
0x18015fa7d  jz      short loc_18015FABC
0x18015fa7f  mov     ecx, 20000002h
0x18015fa84  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18015fa8a  test    al, al
0x18015fa8c  jz      short loc_18015FABC
0x18015fa8e  mov     ecx, 20000001h
0x18015fa93  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18015fa99  test    al, al
0x18015fa9b  jnz     short loc_18015FABC
0x18015fa9d  lea     r8, [rbp+var_18]
0x18015faa1  call    GetIEUserBrokerKnownObject
0x18015faa6  mov     ebx, eax
0x18015faa8  test    eax, eax
0x18015faaa  jns     loc_18015FC45
0x18015fab0  mov     [rbp+var_1C], 1F5h
0x18015fab7  jmp     loc_18015FC50
0x18015fabc  mov     ecx, 1000002Dh
0x18015fac1  call    cs:__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z; IEConfiguration_GetDWORD(IEConfigurationID)
0x18015fac7  lea     r9, _GUID_b55a476b_737e_41b6_bab7_f098e81ca0eb; riid
0x18015face  lea     rcx, CLSID_WininetBroker; rclsid
0x18015fad5  cmp     eax, 2
0x18015fad8  jnz     short loc_18015FB05
0x18015fada  xor     edx, edx; pUnkOuter
0x18015fadc  lea     rax, [rbp+var_18]
0x18015fae0  mov     [rsp+60h+ppv], rax; ppv
0x18015fae5  lea     r8d, [rdx+1]; dwClsContext
0x18015fae9  call    cs:__imp_CoCreateInstance
0x18015faef  mov     ebx, eax
0x18015faf1  test    eax, eax
0x18015faf3  jns     loc_18015FC45
0x18015faf9  mov     [rbp+var_1C], 1FFh
0x18015fb00  jmp     loc_18015FC50
0x18015fb05  cmp     cs:GlobalIsWow64, esi
0x18015fb0b  mov     eax, 80004h
0x18015fb10  mov     r8d, 4
0x18015fb16  cmovnz  r8d, eax; dwClsContext
0x18015fb1a  lea     rax, [rbp+var_18]
0x18015fb1e  xor     edx, edx; pUnkOuter
0x18015fb20  mov     [rsp+60h+ppv], rax; ppv
0x18015fb25  call    cs:__imp_CoCreateInstance
0x18015fb2b  mov     ebx, eax
0x18015fb2d  test    eax, eax
0x18015fb2f  jns     short loc_18015FB3D
0x18015fb31  mov     [rbp+var_1C], 208h
0x18015fb38  jmp     loc_18015FC50
0x18015fb3d  mov     rcx, [rbp+var_18]
0x18015fb41  lea     r8, [rbp+pProxy]
0x18015fb45  lea     rdx, IID_IUnknown
0x18015fb4c  mov     rax, [rcx]
0x18015fb4f  mov     rax, [rax]
0x18015fb52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015fb57  mov     ebx, eax
0x18015fb59  test    eax, eax
0x18015fb5b  jns     short loc_18015FB69
0x18015fb5d  mov     [rbp+var_1C], 20Eh
0x18015fb64  jmp     loc_18015FC50
0x18015fb69  mov     rcx, [rbp+pProxy]; pProxy
0x18015fb6d  or      r14, 0FFFFFFFFFFFFFFFFh
0x18015fb71  mov     [rsp+60h+dwCapabilities], 800h; dwCapabilities
0x18015fb79  or      r8d, 0FFFFFFFFh; dwAuthzSvc
0x18015fb7d  mov     [rsp+60h+pAuthInfo], r14; pAuthInfo
0x18015fb82  mov     r9, r14; pServerPrincName
0x18015fb85  mov     [rsp+60h+dwImpLevel], 3; dwImpLevel
0x18015fb8d  or      edx, r8d; dwAuthnSvc
0x18015fb90  mov     dword ptr [rsp+60h+ppv], esi; dwAuthnLevel
0x18015fb94  call    cs:__imp_CoSetProxyBlanket
0x18015fb9a  mov     ebx, eax
0x18015fb9c  test    eax, eax
0x18015fb9e  jns     short loc_18015FBAC
0x18015fba0  mov     [rbp+var_1C], 217h
0x18015fba7  jmp     loc_18015FC50
0x18015fbac  mov     rcx, [rbp+var_18]; pProxy
0x18015fbb0  or      r8d, 0FFFFFFFFh; dwAuthzSvc
0x18015fbb4  mov     [rsp+60h+dwCapabilities], 800h; dwCapabilities
0x18015fbbc  or      edx, r8d; dwAuthnSvc
0x18015fbbf  mov     [rsp+60h+pAuthInfo], r14; pAuthInfo
0x18015fbc4  mov     r9, r14; pServerPrincName
0x18015fbc7  mov     [rsp+60h+dwImpLevel], 3; dwImpLevel
0x18015fbcf  mov     dword ptr [rsp+60h+ppv], esi; dwAuthnLevel
0x18015fbd3  call    cs:__imp_CoSetProxyBlanket
0x18015fbd9  mov     ebx, eax
0x18015fbdb  test    eax, eax
0x18015fbdd  jns     short loc_18015FC45
0x18015fbdf  mov     [rbp+var_1C], 220h
0x18015fbe6  jmp     short loc_18015FC50
0x18015fbe8  lea     r8, [rbp+var_18]
0x18015fbec  mov     [rbp+var_1C], esi
0x18015fbef  lea     rdx, _GUID_b55a476b_737e_41b6_bab7_f098e81ca0eb
0x18015fbf6  mov     [rbp+var_18], rsi
0x18015fbfa  lea     rcx, CLSID_WininetBroker
0x18015fc01  call    cs:__imp_?GetBrowserElevationBrokerIEUserBrokerKnownObject@@YAJAEBU_GUID@@0PEAPEAX@Z; GetBrowserElevationBrokerIEUserBrokerKnownObject(_GUID const &,_GUID const &,void * *)
0x18015fc07  mov     ebx, eax
0x18015fc09  test    eax, eax
0x18015fc0b  jns     short loc_18015FC45
0x18015fc0d  mov     [rbp+var_1C], 1CCh
0x18015fc14  test    byte ptr cs:xmmword_180266B50+1, 40h
0x18015fc1b  jz      short loc_18015FC38
0x18015fc1d  mov     edx, 16h
0x18015fc22  lea     r8, WPP_4b50d4119023394b229b3c7cf56764e6_Traceguids
0x18015fc29  mov     ecx, 20Eh
0x18015fc2e  mov     r9d, eax
0x18015fc31  call    WPP_SF_d
0x18015fc36  jmp     short loc_18015FC3C
0x18015fc38  test    eax, eax
0x18015fc3a  jns     short loc_18015FC45
0x18015fc3c  mov     [rbp+var_1C], 1EFh
0x18015fc43  jmp     short loc_18015FC50
0x18015fc45  mov     rax, [rbp+var_18]
0x18015fc49  mov     [rdi], rax
0x18015fc4c  mov     [rbp+var_18], rsi
0x18015fc50  mov     rcx, [rbp+pProxy]
0x18015fc54  test    rcx, rcx
0x18015fc57  jz      short loc_18015FC69
0x18015fc59  mov     rax, [rcx]
0x18015fc5c  mov     rax, [rax+10h]
0x18015fc60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015fc65  mov     [rbp+pProxy], rsi
0x18015fc69  mov     rcx, [rbp+var_18]
0x18015fc6d  test    rcx, rcx
0x18015fc70  jz      short loc_18015FC7E
0x18015fc72  mov     rdx, [rcx]
0x18015fc75  mov     rax, [rdx+10h]
0x18015fc79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015fc7e  mov     eax, ebx
0x18015fc80  mov     rcx, [rbp+var_8]
0x18015fc84  xor     rcx, rsp; StackCookie
0x18015fc87  call    __security_check_cookie
0x18015fc8c  lea     r11, [rsp+60h+var_s0]
0x18015fc91  mov     rbx, [r11+20h]
0x18015fc95  mov     rsi, [r11+30h]
0x18015fc99  mov     rsp, r11
0x18015fc9c  pop     r14
0x18015fc9e  pop     rdi
0x18015fc9f  pop     rbp
0x18015fca0  retn
```
