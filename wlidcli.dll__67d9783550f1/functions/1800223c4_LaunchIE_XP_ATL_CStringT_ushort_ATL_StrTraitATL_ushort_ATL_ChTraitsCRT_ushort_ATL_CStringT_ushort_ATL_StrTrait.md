# LaunchIE_XP(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)

- ea: `0x1800223c4`
- end: `0x1800224d6`
- name: `?LaunchIE_XP@@YAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0@Z`
- size: `274`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002204c`

## callees

- `0x18000a844`
- `0x18000cc9c`
- `0x18000e870`
- `0x180013638`
- `0x1800223c4`
- `0x1800224dc`
- `0x1800530e4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180022441`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180022441`

## string_xrefs

- `0x180022452`: `CoCreateInstance of CLSID_InternetExplorer failed. 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall LaunchIE_XP(_QWORD *a1, _QWORD *a2)
{
  HRESULT Instance; // eax
  unsigned int v5; // ebx
  LPVOID *ppv; // [rsp+20h] [rbp-50h]
  LPVOID *ppva; // [rsp+20h] [rbp-50h]
  __int64 v9; // [rsp+30h] [rbp-40h] BYREF
  _QWORD v10[3]; // [rsp+38h] [rbp-38h] BYREF
  _QWORD v11[4]; // [rsp+50h] [rbp-20h] BYREF
  int v12; // [rsp+90h] [rbp+20h] BYREF
  IUnknown *pUnk; // [rsp+98h] [rbp+28h] BYREF

  v12 = 1;
  pUnk = 0;
  v11[0] = "LaunchIE_XP";
  v11[1] = &v12;
  v11[2] = 0;
  v11[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"clientcore\\ds\\ext\\live\\identity\\api\\classic\\launchbrowser.cpp",
    "LaunchIE_XP",
    (const char *)0x176,
    0,
    (const unsigned __int16 *)ppv);
  Instance = CoCreateInstance(&CLSID_InternetExplorer, 0, 0x15u, &IID_IWebBrowser2, (LPVOID *)&pUnk);
  v12 = Instance;
  if ( Instance >= 0 )
  {
    v10[1] = &v9;
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &v9,
      a2);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      v10,
      a1);
    v5 = PostDataInIE(pUnk);
  }
  else
  {
    LODWORD(ppva) = Instance;
    TracePrintW(
      2u,
      "clientcore\\ds\\ext\\live\\identity\\api\\classic\\launchbrowser.cpp",
      0x17Eu,
      L"CoCreateInstance of CLSID_InternetExplorer failed. 0x%x",
      ppva);
    v5 = -2147186534;
  }
  v12 = v5;
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v11);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&pUnk);
  return v5;
}

```

## disassembly

```asm
0x1800223c4  mov     [rsp-8+arg_0], rbx
0x1800223c9  mov     [rsp-8+arg_8], rdi
0x1800223ce  push    rbp
0x1800223cf  mov     rbp, rsp
0x1800223d2  sub     rsp, 70h
0x1800223d6  mov     rbx, rdx
0x1800223d9  mov     rdi, rcx
0x1800223dc  mov     [rbp+arg_10], 1
0x1800223e3  mov     [rbp+pUnk], 0
0x1800223eb  lea     rdx, aLaunchieXp; "LaunchIE_XP"
0x1800223f2  mov     [rbp+var_20], rdx
0x1800223f6  lea     rax, [rbp+arg_10]
0x1800223fa  mov     [rbp+var_18], rax
0x1800223fe  mov     [rbp+var_10], 0
0x180022406  mov     [rbp+var_8], 0
0x18002240e  xor     r9d, r9d; unsigned int
0x180022411  mov     r8d, 176h; char *
0x180022417  lea     rcx, aClientcoreDsEx_4; "clientcore\\ds\\ext\\live\\identity\\ap"...
0x18002241e  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x180022423  nop
0x180022424  lea     rax, [rbp+pUnk]
0x180022428  mov     [rsp+70h+ppv], rax; ppv
0x18002242d  lea     r9, IID_IWebBrowser2; riid
0x180022434  xor     edx, edx; pUnkOuter
0x180022436  lea     r8d, [rdx+15h]; dwClsContext
0x18002243a  lea     rcx, CLSID_InternetExplorer; rclsid
0x180022441  call    cs:__imp_CoCreateInstance
0x180022447  mov     [rbp+arg_10], eax
0x18002244a  test    eax, eax
0x18002244c  jns     short loc_180022477
0x18002244e  mov     dword ptr [rsp+70h+ppv], eax
0x180022452  lea     r9, aCocreateinstan; "CoCreateInstance of CLSID_InternetExplo"...
0x180022459  mov     r8d, 17Eh; unsigned int
0x18002245f  lea     rdx, aClientcoreDsEx_4; "clientcore\\ds\\ext\\live\\identity\\ap"...
0x180022466  mov     ecx, 2; unsigned __int8
0x18002246b  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180022470  mov     ebx, 8004889Ah
0x180022475  jmp     short loc_1800224AC
0x180022477  lea     rax, [rbp+var_40]
0x18002247b  mov     [rbp+var_30], rax
0x18002247f  mov     rdx, rbx
0x180022482  lea     rcx, [rbp+var_40]
0x180022486  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18002248b  mov     rbx, rax
0x18002248e  mov     rdx, rdi
0x180022491  lea     rcx, [rbp+var_38]
0x180022495  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18002249a  nop
0x18002249b  mov     r8, rbx
0x18002249e  mov     rdx, rax
0x1800224a1  mov     rcx, [rbp+pUnk]; pUnk
0x1800224a5  call    ?PostDataInIE@@YAJPEAUIWebBrowser2@@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@1@Z; PostDataInIE(IWebBrowser2 *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>)
0x1800224aa  mov     ebx, eax
0x1800224ac  mov     [rbp+arg_10], ebx
0x1800224af  lea     rcx, [rbp+var_20]
0x1800224b3  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x1800224b8  nop
0x1800224b9  lea     rcx, [rbp+pUnk]
0x1800224bd  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800224c2  mov     eax, ebx
0x1800224c4  lea     r11, [rsp+70h+var_s0]
0x1800224c9  mov     rbx, [r11+10h]
0x1800224cd  mov     rdi, [r11+18h]
0x1800224d1  mov     rsp, r11
0x1800224d4  pop     rbp
0x1800224d5  retn
```
