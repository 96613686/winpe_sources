# CSingleIdentity::WriteCredManLogInternal(bool)

- ea: `0x180081648`
- end: `0x1800819e2`
- name: `?WriteCredManLogInternal@CSingleIdentity@@AEAA?AW4CredManLogPreviousValue@@_N@Z`
- size: `922`
- prototype: ``
- caller_count: `2`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180045af8`
- `0x1800563d0`

## callees

- `0x180006ac0`
- `0x180013510`
- `0x18001426c`
- `0x1800146f0`
- `0x1800151c4`
- `0x180015fb0`
- `0x18001cf20`
- `0x18001dfec`
- `0x18001f968`
- `0x180023d24`
- `0x1800264b0`
- `0x180043344`
- `0x180052340`
- `0x180054910`
- `0x180081648`
- `0x18008d4bc`
- `0x1800ddda4`
- `0x1800dddc0`
- `0x180128010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180081954`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180081954`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800818e4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800818e4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180081919`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180081919`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180081785`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180081785`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18008189a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18008189a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800817e3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800817e3`

## string_xrefs

- `0x180081683`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\singleidentity.cpp`
- `0x1800816cc`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\singleidentity.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CSingleIdentity::WriteCredManLogInternal(__int64 a1, unsigned __int8 a2)
{
  int v2; // edi
  int v4; // eax
  int TokenUser; // eax
  const WCHAR *v6; // rdx
  unsigned int v7; // ebx
  unsigned int v8; // r8d
  unsigned int v9; // eax
  unsigned int v10; // r8d
  int v11; // ecx
  unsigned int v12; // r8d
  const char *v13; // r9
  const WCHAR *Buffer; // rax
  unsigned int v15; // eax
  unsigned int v16; // r8d
  unsigned int v17; // eax
  unsigned int v18; // r8d
  int phkResult; // [rsp+20h] [rbp-39h]
  unsigned int phkResulta; // [rsp+20h] [rbp-39h]
  unsigned int phkResultb; // [rsp+20h] [rbp-39h]
  unsigned int phkResultc; // [rsp+20h] [rbp-39h]
  unsigned int phkResultd; // [rsp+20h] [rbp-39h]
  LPCWSTR lpSubKey; // [rsp+50h] [rbp-9h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-1h] BYREF
  __int64 v27; // [rsp+60h] [rbp+7h] BYREF
  __int64 v28; // [rsp+68h] [rbp+Fh] BYREF
  __int64 v29; // [rsp+70h] [rbp+17h] BYREF
  DWORD Type; // [rsp+78h] [rbp+1Fh] BYREF
  BYTE v31[4]; // [rsp+7Ch] [rbp+23h] BYREF
  HKEY *p_hKey; // [rsp+80h] [rbp+27h] BYREF
  HKEY v33; // [rsp+88h] [rbp+2Fh] BYREF
  char v34; // [rsp+90h] [rbp+37h]
  HKEY *v35; // [rsp+98h] [rbp+3Fh] BYREF
  HKEY v36; // [rsp+A0h] [rbp+47h] BYREF
  char v37; // [rsp+A8h] [rbp+4Fh]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]
  int Data; // [rsp+D0h] [rbp+77h] BYREF
  DWORD cbData; // [rsp+D8h] [rbp+7Fh] BYREF

  v2 = a2;
  v27 = 0;
  v4 = CAutoImpersonateClient::ImpersonateClient((CAutoImpersonateClient *)&v27, 0);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x6FB,
      (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\singleidentity.cpp",
      (const char *)(unsigned int)v4,
      phkResult);
  v28 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  TokenUser = CAutoImpersonateClient::GetTokenUser((CAutoImpersonateClient *)&v27, &v28);
  if ( TokenUser < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x6FD,
      (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\singleidentity.cpp",
      (const char *)(unsigned int)TokenUser,
      phkResult);
  (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a1 + 32LL))(a1, &v29);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64 *)&lpSubKey,
    L".Default\\Software\\Microsoft\\IdentityCRL\\CredManLog");
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator+=(&lpSubKey);
  ATL::CSimpleStringT<unsigned short,0>::Append(&lpSubKey, &v29);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator+=(&lpSubKey);
  ATL::CSimpleStringT<unsigned short,0>::Append(&lpSubKey, &v28);
  Data = -1;
  hKey = 0;
  p_hKey = &hKey;
  v33 = 0;
  v34 = 1;
  v6 = lpSubKey;
  if ( *((int *)lpSubKey - 2) > 1 )
  {
    ATL::CSimpleStringT<unsigned short,0>::Fork(&lpSubKey, *((unsigned int *)lpSubKey - 4));
    v6 = lpSubKey;
  }
  v7 = RegOpenKeyExW(HKEY_USERS, v6, 0, 0x20019u, &v33);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
  if ( v7 == 2 )
  {
    v11 = -1;
    Data = -1;
  }
  else
  {
    if ( v7 )
      wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x714, v8, (const char *)v7, phkResulta);
    Type = 4;
    cbData = 4;
    v9 = RegQueryValueExW(hKey, L"IsMissingCred", 0, &Type, (LPBYTE)&Data, &cbData);
    if ( v9 )
      wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x71F, v10, (const char *)v9, phkResultb);
    v11 = Data;
  }
  *(_DWORD *)v31 = v2;
  if ( v11 != v2 )
  {
    LODWORD(p_hKey) = 0;
    v33 = 0;
    if ( !(unsigned int)CAutoRevertToSelf::Revert((void **)&p_hKey, 0) )
      wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x72C, v12, v13);
    v35 = &hKey;
    v36 = 0;
    v37 = 1;
    Buffer = (const WCHAR *)ATL::CSimpleStringT<unsigned short,0>::GetBuffer(&lpSubKey);
    v15 = RegCreateKeyExW(HKEY_USERS, Buffer, 0, 0, 0, 0x20006u, 0, &v36, 0);
    if ( v15 )
      wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x737, v16, (const char *)v15, phkResultc);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&v35);
    v17 = RegSetValueExW(hKey, L"IsMissingCred", 0, 4u, v31, 4u);
    if ( v17 )
      wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x73F, v18, (const char *)v17, phkResultd);
    CAutoRevertToSelf::~CAutoRevertToSelf((CAutoRevertToSelf *)&p_hKey);
    v11 = Data;
  }
  if ( v11 )
  {
    if ( v11 == -1 )
    {
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&lpSubKey);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v29);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v28);
      CAutoImpersonateClient::~CAutoImpersonateClient((CAutoImpersonateClient *)&v27);
      return 2;
    }
    else
    {
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&lpSubKey);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v29);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v28);
      CAutoImpersonateClient::~CAutoImpersonateClient((CAutoImpersonateClient *)&v27);
      return 1;
    }
  }
  else
  {
    if ( hKey )
      RegCloseKey(hKey);
    ATL::CStringData::Release((ATL::CStringData *)(lpSubKey - 12));
    ATL::CStringData::Release((ATL::CStringData *)(v29 - 24));
    ATL::CStringData::Release((ATL::CStringData *)(v28 - 24));
    if ( (_DWORD)v27 )
      SetThreadToken(0, 0);
    return 0;
  }
}

```

## disassembly

```asm
0x180081648  mov     [rsp-8+arg_0], rbx
0x18008164d  mov     [rsp-8+arg_8], rdi
0x180081652  push    rbp
0x180081653  lea     rbp, [rsp-57h]
0x180081658  sub     rsp, 0B0h
0x18008165f  movzx   edi, dl
0x180081662  mov     rbx, rcx
0x180081665  mov     [rbp+57h+var_50], 0
0x18008166d  xor     edx, edx; struct ATL::CAccessToken *
0x18008166f  lea     rcx, [rbp+57h+var_50]; this
0x180081673  call    ?ImpersonateClient@CAutoImpersonateClient@@QEAAJPEAVCAccessToken@ATL@@@Z; CAutoImpersonateClient::ImpersonateClient(ATL::CAccessToken *)
0x180081678  mov     rcx, [rbp+5Fh]; this
0x18008167c  test    eax, eax
0x18008167e  jns     short loc_180081695
0x180081680  mov     r9d, eax; char *
0x180081683  lea     r8, aOnecoreuapDsEx_24; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18008168a  mov     edx, 6FBh; void *
0x18008168f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180081695  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18008169c  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800816a3  mov     rax, [rax+18h]
0x1800816a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800816ac  add     rax, 18h
0x1800816b0  mov     [rbp+57h+var_48], rax
0x1800816b4  lea     rdx, [rbp+57h+var_48]
0x1800816b8  lea     rcx, [rbp+57h+var_50]; this
0x1800816bc  call    ?GetTokenUser@CAutoImpersonateClient@@QEAAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; CAutoImpersonateClient::GetTokenUser(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x1800816c1  mov     rcx, [rbp+5Fh]; this
0x1800816c5  test    eax, eax
0x1800816c7  jns     short loc_1800816DE
0x1800816c9  mov     r9d, eax; char *
0x1800816cc  lea     r8, aOnecoreuapDsEx_24; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800816d3  mov     edx, 6FDh; void *
0x1800816d8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800816de  mov     rax, [rbx]
0x1800816e1  lea     rdx, [rbp+57h+var_40]
0x1800816e5  mov     rcx, rbx
0x1800816e8  mov     rax, [rax+20h]
0x1800816ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800816f1  nop
0x1800816f2  lea     rdx, aDefaultSoftwar_1; ".Default\\Software\\Microsoft\\Identity"...
0x1800816f9  lea     rcx, [rbp+57h+lpSubKey]
0x1800816fd  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180081702  nop
0x180081703  lea     rcx, [rbp+57h+lpSubKey]
0x180081707  call    ??Y?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator+=(char const *)
0x18008170c  lea     rdx, [rbp+57h+var_40]
0x180081710  lea     rcx, [rbp+57h+lpSubKey]
0x180081714  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXAEBV12@@Z; ATL::CSimpleStringT<ushort,0>::Append(ATL::CSimpleStringT<ushort,0> const &)
0x180081719  lea     rcx, [rbp+57h+lpSubKey]
0x18008171d  call    ??Y?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator+=(char const *)
0x180081722  lea     rdx, [rbp+57h+var_48]
0x180081726  lea     rcx, [rbp+57h+lpSubKey]
0x18008172a  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXAEBV12@@Z; ATL::CSimpleStringT<ushort,0>::Append(ATL::CSimpleStringT<ushort,0> const &)
0x18008172f  mov     [rbp+57h+Data], 0FFFFFFFFh
0x180081736  mov     [rbp+57h+hKey], 0
0x18008173e  lea     rax, [rbp+57h+hKey]
0x180081742  mov     [rbp+57h+var_30], rax
0x180081746  mov     [rbp+57h+var_28], 0
0x18008174e  mov     [rbp+57h+var_20], 1
0x180081752  mov     rdx, [rbp+57h+lpSubKey]
0x180081756  cmp     dword ptr [rdx-8], 1
0x18008175a  jle     short loc_18008176C
0x18008175c  mov     edx, [rdx-10h]
0x18008175f  lea     rcx, [rbp+57h+lpSubKey]
0x180081763  call    ?Fork@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Fork(int)
0x180081768  mov     rdx, [rbp+57h+lpSubKey]; lpSubKey
0x18008176c  lea     rax, [rbp+57h+var_28]
0x180081770  mov     [rsp+0B0h+phkResult], rax; unsigned int
0x180081775  mov     r9d, 20019h; samDesired
0x18008177b  xor     r8d, r8d; ulOptions
0x18008177e  mov     rcx, 0FFFFFFFF80000003h; hKey
0x180081785  call    cs:__imp_RegOpenKeyExW
0x18008178b  mov     ebx, eax
0x18008178d  lea     rcx, [rbp+57h+var_30]
0x180081791  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x180081796  cmp     ebx, 2
0x180081799  jz      short loc_180081804
0x18008179b  mov     rcx, [rbp+5Fh]; this
0x18008179f  test    ebx, ebx
0x1800817a1  jz      short loc_1800817B1
0x1800817a3  mov     r9d, ebx; char *
0x1800817a6  mov     edx, 714h; void *
0x1800817ab  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800817b1  mov     [rbp+57h+Type], 4
0x1800817b8  mov     [rbp+57h+cbData], 4
0x1800817bf  lea     rax, [rbp+57h+cbData]
0x1800817c3  mov     [rsp+0B0h+lpcbData], rax; lpcbData
0x1800817c8  lea     rax, [rbp+57h+Data]
0x1800817cc  mov     [rsp+0B0h+phkResult], rax; unsigned int
0x1800817d1  lea     r9, [rbp+57h+Type]; lpType
0x1800817d5  xor     r8d, r8d; lpReserved
0x1800817d8  lea     rdx, aIsmissingcred; "IsMissingCred"
0x1800817df  mov     rcx, [rbp+57h+hKey]; hKey
0x1800817e3  call    cs:__imp_RegQueryValueExW
0x1800817e9  mov     rcx, [rbp+5Fh]; this
0x1800817ed  test    eax, eax
0x1800817ef  jz      short loc_1800817FF
0x1800817f1  mov     r9d, eax; char *
0x1800817f4  mov     edx, 71Fh; void *
0x1800817f9  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800817ff  mov     ecx, [rbp+57h+Data]
0x180081802  jmp     short loc_18008180A
0x180081804  or      ecx, 0FFFFFFFFh
0x180081807  mov     [rbp+57h+Data], ecx
0x18008180a  mov     dword ptr [rbp+57h+var_34], edi
0x18008180d  cmp     ecx, edi
0x18008180f  jz      loc_18008190C
0x180081815  mov     dword ptr [rbp+57h+var_30], 0
0x18008181c  mov     [rbp+57h+var_28], 0
0x180081824  xor     edx, edx; int
0x180081826  lea     rcx, [rbp+57h+var_30]; this
0x18008182a  call    ?Revert@CAutoRevertToSelf@@QEAAHH@Z; CAutoRevertToSelf::Revert(int)
0x18008182f  mov     rcx, [rbp+5Fh]; this
0x180081833  test    eax, eax
0x180081835  jnz     short loc_180081842
0x180081837  mov     edx, 72Ch; void *
0x18008183c  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180081842  lea     rax, [rbp+57h+hKey]
0x180081846  mov     [rbp+57h+var_18], rax
0x18008184a  mov     [rbp+57h+var_10], 0
0x180081852  mov     [rbp+57h+var_8], 1
0x180081856  lea     rcx, [rbp+57h+lpSubKey]
0x18008185a  call    ?GetBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAPEAGXZ; ATL::CSimpleStringT<ushort,0>::GetBuffer(void)
0x18008185f  mov     [rsp+0B0h+lpdwDisposition], 0; lpdwDisposition
0x180081868  lea     rdx, [rbp+57h+var_10]
0x18008186c  mov     [rsp+0B0h+var_78], rdx; phkResult
0x180081871  mov     [rsp+0B0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18008187a  mov     dword ptr [rsp+0B0h+lpcbData], 20006h; samDesired
0x180081882  mov     dword ptr [rsp+0B0h+phkResult], 0; unsigned int
0x18008188a  xor     r9d, r9d; lpClass
0x18008188d  xor     r8d, r8d; Reserved
0x180081890  mov     rdx, rax; lpSubKey
0x180081893  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18008189a  call    cs:__imp_RegCreateKeyExW
0x1800818a0  mov     rcx, [rbp+5Fh]; this
0x1800818a4  test    eax, eax
0x1800818a6  jz      short loc_1800818B6
0x1800818a8  mov     r9d, eax; char *
0x1800818ab  mov     edx, 737h; void *
0x1800818b0  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800818b6  lea     rcx, [rbp+57h+var_18]
0x1800818ba  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x1800818bf  mov     dword ptr [rsp+0B0h+lpcbData], 4; cbData
0x1800818c7  lea     rax, [rbp+57h+var_34]
0x1800818cb  mov     [rsp+0B0h+phkResult], rax; unsigned int
0x1800818d0  mov     r9d, 4; dwType
0x1800818d6  xor     r8d, r8d; Reserved
0x1800818d9  lea     rdx, aIsmissingcred; "IsMissingCred"
0x1800818e0  mov     rcx, [rbp+57h+hKey]; hKey
0x1800818e4  call    cs:__imp_RegSetValueExW
0x1800818ea  mov     rcx, [rbp+5Fh]; this
0x1800818ee  test    eax, eax
0x1800818f0  jz      short loc_180081900
0x1800818f2  mov     r9d, eax; char *
0x1800818f5  mov     edx, 73Fh; void *
0x1800818fa  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180081900  lea     rcx, [rbp+57h+var_30]; this
0x180081904  call    ??1CAutoRevertToSelf@@QEAA@XZ; CAutoRevertToSelf::~CAutoRevertToSelf(void)
0x180081909  mov     ecx, [rbp+57h+Data]
0x18008190c  test    ecx, ecx
0x18008190e  jnz     short loc_18008195E
0x180081910  mov     rcx, [rbp+57h+hKey]; hKey
0x180081914  test    rcx, rcx
0x180081917  jz      short loc_180081920
0x180081919  call    cs:__imp_RegCloseKey
0x18008191f  nop
0x180081920  mov     rcx, [rbp+57h+lpSubKey]
0x180081924  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180081928  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18008192d  nop
0x18008192e  mov     rcx, [rbp+57h+var_40]
0x180081932  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180081936  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18008193b  nop
0x18008193c  mov     rcx, [rbp+57h+var_48]
0x180081940  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180081944  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180081949  nop
0x18008194a  cmp     dword ptr [rbp+57h+var_50], 0
0x18008194e  jz      short loc_18008195A
0x180081950  xor     edx, edx; Token
0x180081952  xor     ecx, ecx; Thread
0x180081954  call    cs:__imp_SetThreadToken
0x18008195a  xor     eax, eax
0x18008195c  jmp     short loc_1800819CD
0x18008195e  cmp     ecx, 0FFFFFFFFh
0x180081961  lea     rcx, [rbp+57h+hKey]
0x180081965  jnz     short loc_18008199B
0x180081967  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18008196c  nop
0x18008196d  lea     rcx, [rbp+57h+lpSubKey]
0x180081971  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180081976  nop
0x180081977  lea     rcx, [rbp+57h+var_40]
0x18008197b  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180081980  nop
0x180081981  lea     rcx, [rbp+57h+var_48]
0x180081985  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18008198a  nop
0x18008198b  lea     rcx, [rbp+57h+var_50]; this
0x18008198f  call    ??1CAutoImpersonateClient@@QEAA@XZ; CAutoImpersonateClient::~CAutoImpersonateClient(void)
0x180081994  mov     eax, 2
0x180081999  jmp     short loc_1800819CD
0x18008199b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800819a0  nop
0x1800819a1  lea     rcx, [rbp+57h+lpSubKey]
0x1800819a5  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800819aa  nop
0x1800819ab  lea     rcx, [rbp+57h+var_40]
0x1800819af  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800819b4  nop
0x1800819b5  lea     rcx, [rbp+57h+var_48]
0x1800819b9  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800819be  nop
0x1800819bf  lea     rcx, [rbp+57h+var_50]; this
0x1800819c3  call    ??1CAutoImpersonateClient@@QEAA@XZ; CAutoImpersonateClient::~CAutoImpersonateClient(void)
0x1800819c8  mov     eax, 1
0x1800819cd  lea     r11, [rsp+0B0h+var_s0]
0x1800819d5  mov     rbx, [r11+10h]
0x1800819d9  mov     rdi, [r11+18h]
0x1800819dd  mov     rsp, r11
0x1800819e0  pop     rbp
0x1800819e1  retn
```
