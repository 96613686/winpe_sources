# ConnectionProviderFactoryImpl::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180013c60`
- end: `0x180013fe7`
- name: `?CreateInstance@ConnectionProviderFactoryImpl@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `903`
- prototype: `__int64 __fastcall(ConnectionProviderFactoryImpl *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `13`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180007464`
- `0x18000ba54`
- `0x18000fe0c`
- `0x18000fe2c`
- `0x18000fe54`
- `0x180011354`
- `0x180013860`
- `0x180013888`
- `0x180013ab4`
- `0x180013c60`
- `0x180066c7c`
- `0x18007fa6c`
- `0x180096010`

## string_xrefs

- `0x180013cd5`: `onecoreuap\base\diagnosis\platform\notifications\prov\dll\connectionproviderfactoryimpl.cpp`
- `0x180013d2e`: `onecoreuap\base\diagnosis\platform\notifications\prov\dll\connectionproviderfactoryimpl.cpp`
- `0x180013def`: `onecoreuap\base\diagnosis\platform\notifications\prov\dll\connectionproviderfactoryimpl.cpp`
- `0x180013e70`: `onecoreuap\base\diagnosis\platform\notifications\prov\dll\connectionproviderfactoryimpl.cpp`
- `0x180013ef1`: `onecoreuap\base\diagnosis\platform\notifications\prov\dll\connectionproviderfactoryimpl.cpp`
- `0x180013f68`: `onecoreuap\base\diagnosis\platform\notifications\prov\dll\connectionproviderfactoryimpl.cpp`

## pseudocode

```c
__int64 __fastcall ConnectionProviderFactoryImpl::CreateInstance(
        ConnectionProviderFactoryImpl *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  NetworkStateTracker *v7; // rax
  __int64 v8; // rcx
  int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // r9
  int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // r9
  int v17; // eax
  int v18; // eax
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // r9
  int v22; // ebx
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // r9
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 v28; // r9
  const char *v29; // r9
  __int64 result; // rax
  struct IConnectionProvider *v31; // [rsp+20h] [rbp-58h] BYREF
  struct INotificationService *v32; // [rsp+28h] [rbp-50h] BYREF
  struct LogCommandManager *v33; // [rsp+30h] [rbp-48h] BYREF
  _QWORD v34[2]; // [rsp+38h] [rbp-40h] BYREF
  char v35; // [rsp+48h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  unsigned int v37; // [rsp+98h] [rbp+20h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_f729e868de40343b80be061298f9fc67_Traceguids);
  }
  try
  {
    v37 = 0;
    v34[1] = &v37;
    v35 = 1;
    if ( !a4 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2D,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\dll\\connectionproviderfactoryimpl.cpp",
        (const char *)0x8000FFFFLL,
        (int)v31);
    *a4 = 0;
    if ( a2 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_f729e868de40343b80be061298f9fc67_Traceguids, 2147746064LL);
      }
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x33,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\dll\\connectionproviderfactoryimpl.cpp",
        (const char *)0x80040110LL,
        (int)v31);
    }
    g_connectionProviderShutdown = 0;
    if ( !g_networkStateTracker )
    {
      v7 = (NetworkStateTracker *)operator new(0x40u);
      v34[0] = NetworkStateTracker::NetworkStateTracker(v7);
      std::unique_ptr<NetworkStateTracker>::operator=<std::default_delete<NetworkStateTracker>,0>(v8, v34);
      std::unique_ptr<NetworkStateTracker>::~unique_ptr<NetworkStateTracker>(v34);
    }
    v33 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v33, a2, a3, a4);
    v9 = Microsoft::WRL::Details::MakeAndInitialize<LogCommandManager,LogCommandManager,>(&v33);
    v37 = v9;
    if ( v9 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        WPP_f729e868de40343b80be061298f9fc67_Traceguids,
        (unsigned int)v9);
      v9 = v37;
    }
    if ( v9 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3F,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\dll\\connectionproviderfactoryimpl.cpp",
        (const char *)(unsigned int)v9,
        (int)v31);
    v32 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32, v10, v11, v12);
    v13 = CreateNotificationService(v33, &v32);
    v37 = v13;
    if ( v13 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        WPP_f729e868de40343b80be061298f9fc67_Traceguids,
        (unsigned int)v13);
      v13 = v37;
    }
    if ( v13 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x45,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\dll\\connectionproviderfactoryimpl.cpp",
        (const char *)(unsigned int)v13,
        (int)v31);
    v31 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31, v14, v15, v16);
    v17 = ConnectionProviderImpl::CreateInstance(v32, &v31);
    v37 = v17;
    if ( v17 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        WPP_f729e868de40343b80be061298f9fc67_Traceguids,
        (unsigned int)v17);
      v17 = v37;
    }
    if ( v17 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4A,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\dll\\connectionproviderfactoryimpl.cpp",
        (const char *)(unsigned int)v17,
        (int)v31);
    v18 = (**(__int64 (__fastcall ***)(struct IConnectionProvider *, const struct _GUID *, void **))v31)(v31, a3, a4);
    v22 = v18;
    v37 = v18;
    if ( v18 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        16,
        WPP_f729e868de40343b80be061298f9fc67_Traceguids,
        (unsigned int)v18);
      v22 = v37;
    }
    if ( v22 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4E,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\dll\\connectionproviderfactoryimpl.cpp",
        (const char *)(unsigned int)v22,
        (int)v31);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31, v19, v20, v21);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32, v23, v24, v25);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v33, v26, v27, v28);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_f729e868de40343b80be061298f9fc67_Traceguids, v37);
    }
    result = (unsigned int)v22;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x52,
                           (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\dll\\connectionprov"
                                         "iderfactoryimpl.cpp",
                           v29);
  }
  return result;
}

```

## disassembly

```asm
0x180013c60  push    rbx
0x180013c62  push    rsi
0x180013c63  push    r12
0x180013c65  push    r14
0x180013c67  sub     rsp, 58h
0x180013c6b  mov     rsi, r9
0x180013c6e  mov     r14, r8
0x180013c71  mov     rbx, rdx
0x180013c74  lea     r12, WPP_GLOBAL_Control
0x180013c7b  mov     rcx, cs:WPP_GLOBAL_Control
0x180013c82  cmp     rcx, r12
0x180013c85  jz      short loc_180013CA8
0x180013c87  test    byte ptr [rcx+1Ch], 1
0x180013c8b  jz      short loc_180013CA8
0x180013c8d  cmp     byte ptr [rcx+19h], 6
0x180013c91  jb      short loc_180013CA8
0x180013c93  mov     edx, 0Ah
0x180013c98  lea     r8, WPP_f729e868de40343b80be061298f9fc67_Traceguids
0x180013c9f  mov     rcx, [rcx+10h]
0x180013ca3  call    WPP_SF_
0x180013ca8  mov     [rsp+78h+arg_18], 0
0x180013cb3  lea     rax, [rsp+78h+arg_18]
0x180013cbb  mov     [rsp+78h+var_38], rax
0x180013cc0  mov     [rsp+78h+var_30], 1
0x180013cc5  mov     rcx, [rsp+78h]; this
0x180013cca  test    rsi, rsi
0x180013ccd  jnz     short loc_180013CE4
0x180013ccf  mov     r9d, 8000FFFFh; char *
0x180013cd5  lea     r8, aOnecoreuapBase_21; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180013cdc  lea     edx, [rsi+2Dh]; void *
0x180013cdf  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180013ce4  mov     qword ptr [rsi], 0
0x180013ceb  test    rbx, rbx
0x180013cee  jz      short loc_180013D3F
0x180013cf0  mov     rcx, cs:WPP_GLOBAL_Control
0x180013cf7  cmp     rcx, r12
0x180013cfa  jz      short loc_180013D23
0x180013cfc  test    byte ptr [rcx+1Ch], 1
0x180013d00  jz      short loc_180013D23
0x180013d02  cmp     byte ptr [rcx+19h], 2
0x180013d06  jb      short loc_180013D23
0x180013d08  mov     edx, 0Ch
0x180013d0d  mov     r9d, 80040110h
0x180013d13  lea     r8, WPP_f729e868de40343b80be061298f9fc67_Traceguids
0x180013d1a  mov     rcx, [rcx+10h]
0x180013d1e  call    WPP_SF_d
0x180013d23  mov     rcx, [rsp+78h]; this
0x180013d28  mov     r9d, 80040110h; char *
0x180013d2e  lea     r8, aOnecoreuapBase_21; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180013d35  mov     edx, 33h ; '3'; void *
0x180013d3a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180013d3f  mov     cs:?g_connectionProviderShutdown@@3HA, 0; int g_connectionProviderShutdown
0x180013d49  cmp     cs:?g_networkStateTracker@@3V?$unique_ptr@VNetworkStateTracker@@U?$default_delete@VNetworkStateTracker@@@std@@@std@@A, 0; std::unique_ptr<NetworkStateTracker> g_networkStateTracker
0x180013d51  jnz     short loc_180013D84
0x180013d53  mov     ecx, 40h ; '@'; Size
0x180013d58  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180013d5d  mov     [rsp+78h+var_40], rax
0x180013d62  mov     rcx, rax; this
0x180013d65  call    ??0NetworkStateTracker@@QEAA@XZ; NetworkStateTracker::NetworkStateTracker(void)
0x180013d6a  nop
0x180013d6b  mov     [rsp+78h+var_40], rax
0x180013d70  lea     rdx, [rsp+78h+var_40]
0x180013d75  call    ??$?4U?$default_delete@VNetworkStateTracker@@@std@@$0A@@?$unique_ptr@VNetworkStateTracker@@U?$default_delete@VNetworkStateTracker@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<NetworkStateTracker>::operator=<std::default_delete<NetworkStateTracker>,0>(std::unique_ptr<NetworkStateTracker> &&)
0x180013d7a  lea     rcx, [rsp+78h+var_40]
0x180013d7f  call    ??1?$unique_ptr@VNetworkStateTracker@@U?$default_delete@VNetworkStateTracker@@@std@@@std@@QEAA@XZ; std::unique_ptr<NetworkStateTracker>::~unique_ptr<NetworkStateTracker>(void)
0x180013d84  mov     [rsp+78h+var_48], 0
0x180013d8d  lea     rcx, [rsp+78h+var_48]
0x180013d92  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180013d97  lea     rcx, [rsp+78h+var_48]
0x180013d9c  call    ??$MakeAndInitialize@VLogCommandManager@@V1@$$V@Details@WRL@Microsoft@@YAJPEAPEAVLogCommandManager@@@Z; Microsoft::WRL::Details::MakeAndInitialize<LogCommandManager,LogCommandManager,>(LogCommandManager * *)
0x180013da1  mov     [rsp+78h+arg_18], eax
0x180013da8  test    eax, eax
0x180013daa  jns     short loc_180013DE3
0x180013dac  mov     rcx, cs:WPP_GLOBAL_Control
0x180013db3  cmp     rcx, r12
0x180013db6  jz      short loc_180013DE3
0x180013db8  test    byte ptr [rcx+1Ch], 1
0x180013dbc  jz      short loc_180013DE3
0x180013dbe  cmp     byte ptr [rcx+19h], 2
0x180013dc2  jb      short loc_180013DE3
0x180013dc4  mov     edx, 0Dh
0x180013dc9  mov     r9d, eax
0x180013dcc  lea     r8, WPP_f729e868de40343b80be061298f9fc67_Traceguids
0x180013dd3  mov     rcx, [rcx+10h]
0x180013dd7  call    WPP_SF_d
0x180013ddc  mov     eax, [rsp+78h+arg_18]
0x180013de3  mov     rcx, [rsp+78h]; this
0x180013de8  test    eax, eax
0x180013dea  jns     short loc_180013E00
0x180013dec  mov     r9d, eax; char *
0x180013def  lea     r8, aOnecoreuapBase_21; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180013df6  mov     edx, 3Fh ; '?'; void *
0x180013dfb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180013e00  mov     [rsp+78h+var_50], 0
0x180013e09  lea     rcx, [rsp+78h+var_50]
0x180013e0e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180013e13  lea     rdx, [rsp+78h+var_50]; struct INotificationService **
0x180013e18  mov     rcx, [rsp+78h+var_48]; struct LogCommandManager *
0x180013e1d  call    ?CreateNotificationService@@YAJPEAVLogCommandManager@@PEAPEAVINotificationService@@@Z; CreateNotificationService(LogCommandManager *,INotificationService * *)
0x180013e22  mov     [rsp+78h+arg_18], eax
0x180013e29  test    eax, eax
0x180013e2b  jns     short loc_180013E64
0x180013e2d  mov     rcx, cs:WPP_GLOBAL_Control
0x180013e34  cmp     rcx, r12
0x180013e37  jz      short loc_180013E64
0x180013e39  test    byte ptr [rcx+1Ch], 1
0x180013e3d  jz      short loc_180013E64
0x180013e3f  cmp     byte ptr [rcx+19h], 2
0x180013e43  jb      short loc_180013E64
0x180013e45  mov     edx, 0Eh
0x180013e4a  mov     r9d, eax
0x180013e4d  lea     r8, WPP_f729e868de40343b80be061298f9fc67_Traceguids
0x180013e54  mov     rcx, [rcx+10h]
0x180013e58  call    WPP_SF_d
0x180013e5d  mov     eax, [rsp+78h+arg_18]
0x180013e64  mov     rcx, [rsp+78h]; this
0x180013e69  test    eax, eax
0x180013e6b  jns     short loc_180013E81
0x180013e6d  mov     r9d, eax; char *
0x180013e70  lea     r8, aOnecoreuapBase_21; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180013e77  mov     edx, 45h ; 'E'; void *
0x180013e7c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180013e81  mov     [rsp+78h+var_58], 0; int
0x180013e8a  lea     rcx, [rsp+78h+var_58]
0x180013e8f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180013e94  lea     rdx, [rsp+78h+var_58]; struct IConnectionProvider **
0x180013e99  mov     rcx, [rsp+78h+var_50]; struct INotificationService *
0x180013e9e  call    ?CreateInstance@ConnectionProviderImpl@@SAJPEAVINotificationService@@PEAPEAUIConnectionProvider@@@Z; ConnectionProviderImpl::CreateInstance(INotificationService *,IConnectionProvider * *)
0x180013ea3  mov     [rsp+78h+arg_18], eax
0x180013eaa  test    eax, eax
0x180013eac  jns     short loc_180013EE5
0x180013eae  mov     rcx, cs:WPP_GLOBAL_Control
0x180013eb5  cmp     rcx, r12
0x180013eb8  jz      short loc_180013EE5
0x180013eba  test    byte ptr [rcx+1Ch], 1
0x180013ebe  jz      short loc_180013EE5
0x180013ec0  cmp     byte ptr [rcx+19h], 2
0x180013ec4  jb      short loc_180013EE5
0x180013ec6  mov     edx, 0Fh
0x180013ecb  mov     r9d, eax
0x180013ece  lea     r8, WPP_f729e868de40343b80be061298f9fc67_Traceguids
0x180013ed5  mov     rcx, [rcx+10h]
0x180013ed9  call    WPP_SF_d
0x180013ede  mov     eax, [rsp+78h+arg_18]
0x180013ee5  mov     rcx, [rsp+78h]; this
0x180013eea  test    eax, eax
0x180013eec  jns     short loc_180013F02
0x180013eee  mov     r9d, eax; char *
0x180013ef1  lea     r8, aOnecoreuapBase_21; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180013ef8  mov     edx, 4Ah ; 'J'; void *
0x180013efd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180013f02  mov     rcx, [rsp+78h+var_58]
0x180013f07  mov     rax, [rcx]
0x180013f0a  mov     r8, rsi
0x180013f0d  mov     rdx, r14
0x180013f10  mov     rax, [rax]
0x180013f13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f18  mov     ebx, eax
0x180013f1a  mov     [rsp+78h+arg_18], eax
0x180013f21  test    eax, eax
0x180013f23  jns     short loc_180013F5C
0x180013f25  mov     rcx, cs:WPP_GLOBAL_Control
0x180013f2c  cmp     rcx, r12
0x180013f2f  jz      short loc_180013F5C
0x180013f31  test    byte ptr [rcx+1Ch], 1
0x180013f35  jz      short loc_180013F5C
0x180013f37  cmp     byte ptr [rcx+19h], 2
0x180013f3b  jb      short loc_180013F5C
0x180013f3d  mov     edx, 10h
0x180013f42  mov     r9d, eax
0x180013f45  lea     r8, WPP_f729e868de40343b80be061298f9fc67_Traceguids
0x180013f4c  mov     rcx, [rcx+10h]
0x180013f50  call    WPP_SF_d
0x180013f55  mov     ebx, [rsp+78h+arg_18]
0x180013f5c  mov     rcx, [rsp+78h]; this
0x180013f61  test    ebx, ebx
0x180013f63  jns     short loc_180013F7A
0x180013f65  mov     r9d, ebx; char *
0x180013f68  lea     r8, aOnecoreuapBase_21; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180013f6f  mov     edx, 4Eh ; 'N'; void *
0x180013f74  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180013f7a  lea     rcx, [rsp+78h+var_58]
0x180013f7f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180013f84  nop
0x180013f85  lea     rcx, [rsp+78h+var_50]
0x180013f8a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180013f8f  nop
0x180013f90  lea     rcx, [rsp+78h+var_48]
0x180013f95  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180013f9a  nop
0x180013f9b  mov     rcx, cs:WPP_GLOBAL_Control
0x180013fa2  cmp     rcx, r12
0x180013fa5  jz      short loc_180013FD0
0x180013fa7  test    byte ptr [rcx+1Ch], 1
0x180013fab  jz      short loc_180013FD0
0x180013fad  cmp     byte ptr [rcx+19h], 6
0x180013fb1  jb      short loc_180013FD0
0x180013fb3  mov     edx, 0Bh
0x180013fb8  mov     r9d, [rsp+78h+arg_18]
0x180013fc0  lea     r8, WPP_f729e868de40343b80be061298f9fc67_Traceguids
0x180013fc7  mov     rcx, [rcx+10h]
0x180013fcb  call    WPP_SF_d
0x180013fd0  mov     eax, ebx
0x180013fd2  jmp     short loc_180013FDB
0x180013fd4  mov     eax, [rsp+78h+arg_18]
0x180013fdb  add     rsp, 58h
0x180013fdf  pop     r14
0x180013fe1  pop     r12
0x180013fe3  pop     rsi
0x180013fe4  pop     rbx
0x180013fe5  retn
```
