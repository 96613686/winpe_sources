# CServiceRequest::GetRequestAuthToken(ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> &,ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> &)

- ea: `0x1800ce730`
- end: `0x1800cec4d`
- name: `?GetRequestAuthToken@CServiceRequest@@MEAAJAEAV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@0@Z`
- size: `1309`
- prototype: ``
- caller_count: `0`
- callee_count: `26`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000b39c`
- `0x18000c050`
- `0x18000ed04`
- `0x180011f38`
- `0x1800151c4`
- `0x1800161e0`
- `0x180016500`
- `0x180016f3c`
- `0x180017410`
- `0x180017830`
- `0x1800179c0`
- `0x1800181bc`
- `0x180018f80`
- `0x1800191c0`
- `0x18001a9c0`
- `0x18001ad00`
- `0x1800277c0`
- `0x180029d54`
- `0x180037288`
- `0x180039be0`
- `0x180051784`
- `0x180079554`
- `0x18007c2f4`
- `0x180084374`
- `0x1800ce730`
- `0x180128010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800ce905`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800ce93c`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800ce9a6`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800ce9dd`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800ce905`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800ce93c`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800ce9a6`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800ce9dd`
- `ext-ms-win-msa-device-l1-1-0!MsaDevice_UseXTokenBasedSessionKey` at `0x1800ceb53`
- `ext-ms-win-msa-device-l1-1-0!MsaDevice_UseXTokenBasedSessionKey` at `0x1800ceb53`

## string_xrefs

- `0x1800ce798`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\rst.cpp`
- `0x1800ce826`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\rst.cpp`
- `0x1800cea4f`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\rst.cpp`
- `0x1800ceb37`: `</wsse:UsernameToken>`
- `0x1800cea33`: `hr = AppendDeviceDaTokenToRequestXml(&serviceExecutionContext, strAuthToken, strTokenId, false )`
- `0x1800ce76c`: `CServiceRequest::GetRequestAuthToken`
- `0x1800ce81f`: `CServiceRequest::GetRequestAuthToken`
- `0x1800cea48`: `CServiceRequest::GetRequestAuthToken`
- `0x1800ce8a1`: `m_pIdentity->GetTokenBag() != nullptr && m_pIdentity->GetTokenBag()->RetrieveToken(PPCRL_DEFAULT_DA_URI, tokAuthToken) && !tokAuthToken.GetToken().IsEmpty()`
- `0x1800ceabe`: `<wsse:UsernameToken wsu:Id="user"><wsse:UsernameHint>`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall CServiceRequest::GetRequestAuthToken(__int64 a1, __int64 a2, __int64 a3)
{
  char v6; // si
  __int64 v7; // rbx
  int v8; // r9d
  const char *v9; // rax
  unsigned int v10; // r8d
  __int64 v11; // rbx
  __int64 v12; // rax
  char v13; // bl
  __int64 Token; // rax
  const WCHAR *v15; // rbx
  int v16; // eax
  int cbMultiByte; // esi
  CHAR *v18; // rax
  unsigned int v19; // eax
  __int64 TokenURI; // rax
  const WCHAR *v21; // rbx
  int v22; // eax
  int v23; // esi
  CHAR *v24; // rax
  unsigned int v25; // eax
  int v26; // eax
  _QWORD *v27; // rax
  unsigned __int8 *v28; // rsi
  int v29; // r14d
  unsigned int v30; // ebx
  unsigned int v31; // ebx
  const unsigned __int16 *lpMultiByteStr; // [rsp+20h] [rbp-E0h]
  int lpMultiByteStra; // [rsp+20h] [rbp-E0h]
  LPCWCH v35; // [rsp+40h] [rbp-C0h] BYREF
  LPCWCH lpWideCharStr; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v37; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int8 *v38; // [rsp+58h] [rbp-A8h]
  int v39; // [rsp+60h] [rbp-A0h]
  __int64 v40; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v41[4]; // [rsp+70h] [rbp-90h] BYREF
  _DWORD v42[36]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int8 *v43; // [rsp+120h] [rbp+20h]
  _BYTE v44[272]; // [rsp+140h] [rbp+40h] BYREF
  int v45; // [rsp+260h] [rbp+160h] BYREF
  __int64 v46; // [rsp+278h] [rbp+178h] BYREF

  v6 = 0;
  v45 = 0;
  v41[0] = "CServiceRequest::GetRequestAuthToken";
  v41[1] = &v45;
  v41[2] = 0;
  v41[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\rst.cpp",
    "CServiceRequest::GetRequestAuthToken",
    (const char *)0x155F,
    0,
    lpMultiByteStr);
  CPPCRLToken::CPPCRLToken((CPPCRLToken *)v42);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&lpWideCharStr);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v35);
  ATL::CSimpleStringT<char,0>::Truncate(a2, 0);
  ATL::CSimpleStringT<char,0>::Truncate(a3, 0);
  CBytePtr::Empty((CBytePtr *)(a1 + 192));
  v38 = 0;
  v37 = 0;
  v39 = 0;
  v7 = *(_QWORD *)(a1 + 24);
  if ( !v7 )
  {
    v8 = -2147418113;
    v9 = "m_pIdentity != nullptr";
    v10 = 5481;
LABEL_3:
    v45 = v8;
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\rst.cpp",
      "CServiceRequest::GetRequestAuthToken",
      v10,
      v8,
      v9);
    goto LABEL_34;
  }
  v11 = *(_QWORD *)(v7 + 88);
  if ( !v11
    || (v12 = ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(
                &v46,
                L"http://Passport.NET/tb"),
        !(unsigned int)CIdentityTokenBag::RetrieveToken(v11, v12, v42))
    || (v6 = 1, v13 = 0, !*(_DWORD *)(*(_QWORD *)CPPCRLToken::GetToken(v42, &v40) - 16LL)) )
  {
    v13 = 1;
  }
  if ( (v6 & 1) != 0 )
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v40);
  if ( v13 )
  {
    v8 = -2147186591;
    v9 = "m_pIdentity->GetTokenBag() != nullptr && m_pIdentity->GetTokenBag()->RetrieveToken(PPCRL_DEFAULT_DA_URI, tokAut"
         "hToken) && !tokAuthToken.GetToken().IsEmpty()";
    v10 = 5486;
    goto LABEL_3;
  }
  Token = CPPCRLToken::GetToken(v42, &v46);
  ATL::CSimpleStringT<unsigned short,0>::operator=(&lpWideCharStr, Token);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v46);
  v15 = lpWideCharStr;
  v16 = WideCharToMultiByte(0xFDE9u, 0, lpWideCharStr, *((_DWORD *)lpWideCharStr - 4), 0, 0, 0, 0);
  cbMultiByte = v16;
  if ( v16 > 0 )
  {
    v18 = (CHAR *)ATL::CSimpleStringT<char,0>::PrepareWrite(a2, (unsigned int)v16);
    v19 = WideCharToMultiByte(0xFDE9u, 0, v15, *((_DWORD *)v15 - 4), v18, cbMultiByte, 0, 0);
    if ( v19 != cbMultiByte )
      goto LABEL_35;
    ATL::CSimpleStringT<char,0>::ReleaseBuffer(a2, v19);
  }
  TokenURI = CPPCRLToken::GetTokenURI(v42, &v46);
  ATL::CSimpleStringT<unsigned short,0>::operator=(&v35, TokenURI);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v46);
  v21 = v35;
  v22 = WideCharToMultiByte(0xFDE9u, 0, v35, *((_DWORD *)v35 - 4), 0, 0, 0, 0);
  v23 = v22;
  if ( v22 <= 0 )
    goto LABEL_18;
  v24 = (CHAR *)ATL::CSimpleStringT<char,0>::PrepareWrite(a3, (unsigned int)v22);
  v25 = WideCharToMultiByte(0xFDE9u, 0, v21, *((_DWORD *)v21 - 4), v24, v23, 0, 0);
  if ( v25 != v23 )
LABEL_35:
    ATL::AtlThrowLastWin32();
  ATL::CSimpleStringT<char,0>::ReleaseBuffer(a3, v25);
LABEL_18:
  if ( *(_BYTE *)(a1 + 161) == 1 )
  {
    ServiceExecutionContext::ServiceExecutionContext((ServiceExecutionContext *)v44);
    LOBYTE(lpMultiByteStra) = 0;
    v26 = (*(__int64 (__fastcall **)(__int64, _BYTE *, __int64, __int64, int))(*(_QWORD *)a1 + 304LL))(
            a1,
            v44,
            a2,
            a3,
            lpMultiByteStra);
    v45 = v26;
    if ( v26 < 0 )
    {
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\rst.cpp",
        "CServiceRequest::GetRequestAuthToken",
        0x1595u,
        v26,
        "hr = AppendDeviceDaTokenToRequestXml(&serviceExecutionContext, strAuthToken, strTokenId, false )");
      ServiceExecutionContext::~ServiceExecutionContext((ServiceExecutionContext *)v44);
      goto LABEL_34;
    }
    ServiceExecutionContext::~ServiceExecutionContext((ServiceExecutionContext *)v44);
  }
  if ( (*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 24) + 80LL))(*(_QWORD *)(a1 + 24)) != 1
    && (*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 24) + 80LL))(*(_QWORD *)(a1 + 24)) != 2
    && (*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 24) + 80LL))(*(_QWORD *)(a1 + 24)) != 3 )
  {
    ATL::CSimpleStringT<char,0>::Append(a2, "<wsse:UsernameToken wsu:Id=\"user\"><wsse:UsernameHint>");
    v27 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)(a1 + 24) + 32LL))(
                      *(_QWORD *)(a1 + 24),
                      &v46);
    CPPCRLBaseRequest::AppendEscapedXML(a2, *v27);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v46);
    ATL::CSimpleStringT<char,0>::Append(a2, "</wsse:UsernameHint>");
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v46);
    CPPCRLRequest::GenerateLoginOptions(a1, &v46);
    ATL::CSimpleStringT<char,0>::Append(a2, &v46);
    ATL::CSimpleStringT<char,0>::Append(a2, "</wsse:UsernameToken>");
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v46);
  }
  if ( !(unsigned int)MsaDevice_UseXTokenBasedSessionKey() )
  {
    CBytePtr::Attach((CBytePtr *)&v37, v43, v42[34], 0);
    v28 = v38;
    if ( !v38 && !*(_QWORD *)(a1 + 200) )
    {
      v8 = -2147188722;
      v9 = "authSessionKey.GetBuffer() != nullptr || m_spAuthSessionKey.GetBuffer() != nullptr";
      v10 = 5553;
      goto LABEL_3;
    }
    v29 = v42[0];
    v30 = v37;
    if ( !*(_DWORD *)(a1 + 192) )
    {
      CBytePtr::Attach((CBytePtr *)(a1 + 192), v38, v37, 0);
      *(_DWORD *)(a1 + 216) = v29;
    }
    if ( v30 )
    {
      CBytePtr::Attach((CBytePtr *)(*(_QWORD *)(a1 + 24) + 752LL), v28, v30, 0);
      *(_DWORD *)(*(_QWORD *)(a1 + 24) + 744LL) = v29;
    }
  }
LABEL_34:
  v31 = v45;
  CBytePtr::Empty((CBytePtr *)&v37);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v35);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&lpWideCharStr);
  CPPCRLToken::~CPPCRLToken((CPPCRLToken *)v42);
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v41);
  return v31;
}

```

## disassembly

```asm
0x1800ce730  mov     [rsp-8+arg_8], rbx
0x1800ce735  push    rbp
0x1800ce736  push    rsi
0x1800ce737  push    rdi
0x1800ce738  push    r12
0x1800ce73a  push    r13
0x1800ce73c  push    r14
0x1800ce73e  push    r15
0x1800ce740  lea     rbp, [rsp-120h]
0x1800ce748  sub     rsp, 220h
0x1800ce74f  mov     r15, r8
0x1800ce752  mov     r14, rdx
0x1800ce755  mov     rdi, rcx
0x1800ce758  xor     r13d, r13d
0x1800ce75b  mov     esi, r13d
0x1800ce75e  mov     [rbp+150h+arg_0], r13d
0x1800ce765  mov     [rbp+150h+arg_0], r13d
0x1800ce76c  lea     rcx, aCservicereques; "CServiceRequest::GetRequestAuthToken"
0x1800ce773  mov     [rsp+250h+var_1E0], rcx
0x1800ce778  lea     rax, [rbp+150h+arg_0]
0x1800ce77f  mov     [rsp+250h+var_1D8], rax
0x1800ce784  mov     [rbp+150h+var_1D0], r13
0x1800ce788  mov     [rbp+150h+var_1C8], r13
0x1800ce78c  xor     r9d, r9d; unsigned int
0x1800ce78f  mov     r8d, 155Fh; char *
0x1800ce795  mov     rdx, rcx; char *
0x1800ce798  lea     rcx, aOnecoreuapDsEx_94; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800ce79f  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x1800ce7a4  nop
0x1800ce7a5  lea     rcx, [rbp+150h+var_1C0]; this
0x1800ce7a9  call    ??0CPPCRLToken@@QEAA@XZ; CPPCRLToken::CPPCRLToken(void)
0x1800ce7ae  nop
0x1800ce7af  lea     rcx, [rsp+250h+lpWideCharStr]
0x1800ce7b4  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800ce7b9  nop
0x1800ce7ba  lea     rcx, [rsp+250h+var_210]
0x1800ce7bf  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800ce7c4  nop
0x1800ce7c5  xor     edx, edx
0x1800ce7c7  mov     rcx, r14
0x1800ce7ca  call    ?Truncate@?$CSimpleStringT@D$0A@@ATL@@QEAAXH@Z; ATL::CSimpleStringT<char,0>::Truncate(int)
0x1800ce7cf  xor     edx, edx
0x1800ce7d1  mov     rcx, r15
0x1800ce7d4  call    ?Truncate@?$CSimpleStringT@D$0A@@ATL@@QEAAXH@Z; ATL::CSimpleStringT<char,0>::Truncate(int)
0x1800ce7d9  lea     r12, [rdi+0C0h]
0x1800ce7e0  mov     rcx, r12; this
0x1800ce7e3  call    ?Empty@CBytePtr@@QEAAXXZ; CBytePtr::Empty(void)
0x1800ce7e8  mov     [rsp+250h+var_1F8], r13
0x1800ce7ed  mov     [rsp+250h+var_200], r13d
0x1800ce7f2  mov     [rsp+250h+var_1F0], r13d
0x1800ce7f7  mov     rbx, [rdi+18h]
0x1800ce7fb  test    rbx, rbx
0x1800ce7fe  jnz     short loc_1800CE837
0x1800ce800  mov     r9d, 8000FFFFh; int
0x1800ce806  lea     rax, aMPidentityNull; "m_pIdentity != nullptr"
0x1800ce80d  mov     r8d, 1569h; unsigned int
0x1800ce813  mov     [rbp+150h+arg_0], r9d
0x1800ce81a  mov     [rsp+250h+lpMultiByteStr], rax; char *
0x1800ce81f  lea     rdx, aCservicereques; "CServiceRequest::GetRequestAuthToken"
0x1800ce826  lea     rcx, aOnecoreuapDsEx_94; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800ce82d  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x1800ce832  jmp     loc_1800CEBEF
0x1800ce837  mov     rbx, [rbx+58h]
0x1800ce83b  test    rbx, rbx
0x1800ce83e  jz      short loc_1800CE885
0x1800ce840  lea     rdx, aHttpPassportNe_2; "http://Passport.NET/tb"
0x1800ce847  lea     rcx, [rbp+150h+arg_18]
0x1800ce84e  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(ushort const *)
0x1800ce853  lea     r8, [rbp+150h+var_1C0]
0x1800ce857  mov     rdx, rax
0x1800ce85a  mov     rcx, rbx
0x1800ce85d  call    ?RetrieveToken@CIdentityTokenBag@@QEAAHV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@AEAVCPPCRLToken@@@Z; CIdentityTokenBag::RetrieveToken(ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>,CPPCRLToken &)
0x1800ce862  test    eax, eax
0x1800ce864  jz      short loc_1800CE885
0x1800ce866  lea     rdx, [rsp+250h+var_1E8]
0x1800ce86b  lea     rcx, [rbp+150h+var_1C0]
0x1800ce86f  call    ?GetToken@CPPCRLToken@@QEBA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@XZ; CPPCRLToken::GetToken(void)
0x1800ce874  mov     esi, 1
0x1800ce879  mov     rax, [rax]
0x1800ce87c  cmp     [rax-10h], r13d
0x1800ce880  mov     bl, r13b
0x1800ce883  jnz     short loc_1800CE887
0x1800ce885  mov     bl, 1
0x1800ce887  test    sil, 1
0x1800ce88b  jz      short loc_1800CE897
0x1800ce88d  lea     rcx, [rsp+250h+var_1E8]
0x1800ce892  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800ce897  test    bl, bl
0x1800ce899  jz      short loc_1800CE8B3
0x1800ce89b  mov     r9d, 80048861h
0x1800ce8a1  lea     rax, aMPidentityGett; "m_pIdentity->GetTokenBag() != nullptr &"...
0x1800ce8a8  mov     r8d, 156Eh
0x1800ce8ae  jmp     loc_1800CE813
0x1800ce8b3  lea     rdx, [rbp+150h+arg_18]
0x1800ce8ba  lea     rcx, [rbp+150h+var_1C0]
0x1800ce8be  call    ?GetToken@CPPCRLToken@@QEBA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@XZ; CPPCRLToken::GetToken(void)
0x1800ce8c3  nop
0x1800ce8c4  mov     rdx, rax
0x1800ce8c7  lea     rcx, [rsp+250h+lpWideCharStr]
0x1800ce8cc  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x1800ce8d1  nop
0x1800ce8d2  lea     rcx, [rbp+150h+arg_18]
0x1800ce8d9  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800ce8de  mov     rbx, [rsp+250h+lpWideCharStr]
0x1800ce8e3  mov     [rsp+250h+lpUsedDefaultChar], r13; lpUsedDefaultChar
0x1800ce8e8  mov     [rsp+250h+lpDefaultChar], r13; lpDefaultChar
0x1800ce8ed  mov     [rsp+250h+cbMultiByte], r13d; cbMultiByte
0x1800ce8f2  mov     [rsp+250h+lpMultiByteStr], r13; lpMultiByteStr
0x1800ce8f7  mov     r9d, [rbx-10h]; cchWideChar
0x1800ce8fb  mov     r8, rbx; lpWideCharStr
0x1800ce8fe  xor     edx, edx; dwFlags
0x1800ce900  mov     ecx, 0FDE9h; CodePage
0x1800ce905  call    cs:__imp_WideCharToMultiByte
0x1800ce90b  mov     esi, eax
0x1800ce90d  test    eax, eax
0x1800ce90f  jle     short loc_1800CE954
0x1800ce911  mov     edx, eax
0x1800ce913  mov     rcx, r14
0x1800ce916  call    ?PrepareWrite@?$CSimpleStringT@D$0A@@ATL@@AEAAPEADH@Z; ATL::CSimpleStringT<char,0>::PrepareWrite(int)
0x1800ce91b  mov     [rsp+250h+lpUsedDefaultChar], r13; lpUsedDefaultChar
0x1800ce920  mov     [rsp+250h+lpDefaultChar], r13; lpDefaultChar
0x1800ce925  mov     [rsp+250h+cbMultiByte], esi; cbMultiByte
0x1800ce929  mov     [rsp+250h+lpMultiByteStr], rax; lpMultiByteStr
0x1800ce92e  mov     r9d, [rbx-10h]; cchWideChar
0x1800ce932  mov     r8, rbx; lpWideCharStr
0x1800ce935  xor     edx, edx; dwFlags
0x1800ce937  mov     ecx, 0FDE9h; CodePage
0x1800ce93c  call    cs:__imp_WideCharToMultiByte
0x1800ce942  cmp     eax, esi
0x1800ce944  jnz     loc_1800CEC47
0x1800ce94a  mov     edx, eax
0x1800ce94c  mov     rcx, r14
0x1800ce94f  call    ?ReleaseBuffer@?$CSimpleStringT@D$0A@@ATL@@QEAAXH@Z; ATL::CSimpleStringT<char,0>::ReleaseBuffer(int)
0x1800ce954  lea     rdx, [rbp+150h+arg_18]
0x1800ce95b  lea     rcx, [rbp+150h+var_1C0]
0x1800ce95f  call    ?GetTokenURI@CPPCRLToken@@QEBA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@XZ; CPPCRLToken::GetTokenURI(void)
0x1800ce964  nop
0x1800ce965  mov     rdx, rax
0x1800ce968  lea     rcx, [rsp+250h+var_210]
0x1800ce96d  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x1800ce972  nop
0x1800ce973  lea     rcx, [rbp+150h+arg_18]
0x1800ce97a  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800ce97f  mov     rbx, [rsp+250h+var_210]
0x1800ce984  mov     [rsp+250h+lpUsedDefaultChar], r13; lpUsedDefaultChar
0x1800ce989  mov     [rsp+250h+lpDefaultChar], r13; lpDefaultChar
0x1800ce98e  mov     [rsp+250h+cbMultiByte], r13d; cbMultiByte
0x1800ce993  mov     [rsp+250h+lpMultiByteStr], r13; lpMultiByteStr
0x1800ce998  mov     r9d, [rbx-10h]; cchWideChar
0x1800ce99c  mov     r8, rbx; lpWideCharStr
0x1800ce99f  xor     edx, edx; dwFlags
0x1800ce9a1  mov     ecx, 0FDE9h; CodePage
0x1800ce9a6  call    cs:__imp_WideCharToMultiByte
0x1800ce9ac  mov     esi, eax
0x1800ce9ae  test    eax, eax
0x1800ce9b0  jle     short loc_1800CE9F5
0x1800ce9b2  mov     edx, eax
0x1800ce9b4  mov     rcx, r15
0x1800ce9b7  call    ?PrepareWrite@?$CSimpleStringT@D$0A@@ATL@@AEAAPEADH@Z; ATL::CSimpleStringT<char,0>::PrepareWrite(int)
0x1800ce9bc  mov     [rsp+250h+lpUsedDefaultChar], r13; lpUsedDefaultChar
0x1800ce9c1  mov     [rsp+250h+lpDefaultChar], r13; lpDefaultChar
0x1800ce9c6  mov     [rsp+250h+cbMultiByte], esi; cbMultiByte
0x1800ce9ca  mov     [rsp+250h+lpMultiByteStr], rax; lpMultiByteStr
0x1800ce9cf  mov     r9d, [rbx-10h]; cchWideChar
0x1800ce9d3  mov     r8, rbx; lpWideCharStr
0x1800ce9d6  xor     edx, edx; dwFlags
0x1800ce9d8  mov     ecx, 0FDE9h; CodePage
0x1800ce9dd  call    cs:__imp_WideCharToMultiByte
0x1800ce9e3  cmp     eax, esi
0x1800ce9e5  jnz     loc_1800CEC47
0x1800ce9eb  mov     edx, eax
0x1800ce9ed  mov     rcx, r15
0x1800ce9f0  call    ?ReleaseBuffer@?$CSimpleStringT@D$0A@@ATL@@QEAAXH@Z; ATL::CSimpleStringT<char,0>::ReleaseBuffer(int)
0x1800ce9f5  cmp     byte ptr [rdi+0A1h], 1
0x1800ce9fc  jnz     short loc_1800CEA73
0x1800ce9fe  lea     rcx, [rbp+150h+var_110]; this
0x1800cea02  call    ??0ServiceExecutionContext@@QEAA@XZ; ServiceExecutionContext::ServiceExecutionContext(void)
0x1800cea07  nop
0x1800cea08  mov     rax, [rdi]
0x1800cea0b  mov     byte ptr [rsp+250h+lpMultiByteStr], r13b
0x1800cea10  mov     r9, r15
0x1800cea13  mov     r8, r14
0x1800cea16  lea     rdx, [rbp+150h+var_110]
0x1800cea1a  mov     rcx, rdi
0x1800cea1d  mov     rax, [rax+130h]
0x1800cea24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cea29  mov     [rbp+150h+arg_0], eax
0x1800cea2f  test    eax, eax
0x1800cea31  jns     short loc_1800CEA6A
0x1800cea33  lea     rcx, aHrAppenddevice; "hr = AppendDeviceDaTokenToRequestXml(&s"...
0x1800cea3a  mov     [rsp+250h+lpMultiByteStr], rcx; char *
0x1800cea3f  mov     r9d, eax; int
0x1800cea42  mov     r8d, 1595h; unsigned int
0x1800cea48  lea     rdx, aCservicereques; "CServiceRequest::GetRequestAuthToken"
0x1800cea4f  lea     rcx, aOnecoreuapDsEx_94; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800cea56  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x1800cea5b  nop
0x1800cea5c  lea     rcx, [rbp+150h+var_110]; this
0x1800cea60  call    ??1ServiceExecutionContext@@UEAA@XZ; ServiceExecutionContext::~ServiceExecutionContext(void)
0x1800cea65  jmp     loc_1800CEBEF
0x1800cea6a  lea     rcx, [rbp+150h+var_110]; this
0x1800cea6e  call    ??1ServiceExecutionContext@@UEAA@XZ; ServiceExecutionContext::~ServiceExecutionContext(void)
0x1800cea73  mov     rcx, [rdi+18h]
0x1800cea77  mov     rax, [rcx]
0x1800cea7a  mov     rax, [rax+50h]
0x1800cea7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cea83  cmp     eax, 1
0x1800cea86  jz      loc_1800CEB53
0x1800cea8c  mov     rcx, [rdi+18h]
0x1800cea90  mov     rax, [rcx]
0x1800cea93  mov     rax, [rax+50h]
0x1800cea97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cea9c  cmp     eax, 2
0x1800cea9f  jz      loc_1800CEB53
0x1800ceaa5  mov     rcx, [rdi+18h]
0x1800ceaa9  mov     rax, [rcx]
0x1800ceaac  mov     rax, [rax+50h]
0x1800ceab0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ceab5  cmp     eax, 3
0x1800ceab8  jz      loc_1800CEB53
0x1800ceabe  lea     rdx, aWsseUsernameto_2; "<wsse:UsernameToken wsu:Id=\"user\"><ws"...
0x1800ceac5  mov     rcx, r14
0x1800ceac8  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBD@Z; ATL::CSimpleStringT<char,0>::Append(char const *)
0x1800ceacd  mov     rcx, [rdi+18h]
0x1800cead1  mov     rax, [rcx]
0x1800cead4  lea     rdx, [rbp+150h+arg_18]
0x1800ceadb  mov     rax, [rax+20h]
0x1800ceadf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ceae4  nop
0x1800ceae5  mov     rdx, [rax]
0x1800ceae8  mov     rcx, r14
0x1800ceaeb  call    ?AppendEscapedXML@CPPCRLBaseRequest@@SAJAEAV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@PEBG@Z; CPPCRLBaseRequest::AppendEscapedXML(ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> &,ushort const *)
0x1800ceaf0  nop
0x1800ceaf1  lea     rcx, [rbp+150h+arg_18]
0x1800ceaf8  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800ceafd  lea     rdx, aWsseUsernamehi; "</wsse:UsernameHint>"
0x1800ceb04  mov     rcx, r14
0x1800ceb07  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBD@Z; ATL::CSimpleStringT<char,0>::Append(char const *)
0x1800ceb0c  lea     rcx, [rbp+150h+arg_18]
0x1800ceb13  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800ceb18  nop
0x1800ceb19  lea     rdx, [rbp+150h+arg_18]
0x1800ceb20  mov     rcx, rdi
0x1800ceb23  call    ?GenerateLoginOptions@CPPCRLRequest@@IEAAXAEAV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@@Z; CPPCRLRequest::GenerateLoginOptions(ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> &)
0x1800ceb28  lea     rdx, [rbp+150h+arg_18]
0x1800ceb2f  mov     rcx, r14
0x1800ceb32  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXAEBV12@@Z; ATL::CSimpleStringT<char,0>::Append(ATL::CSimpleStringT<char,0> const &)
0x1800ceb37  lea     rdx, aWsseUsernameto_3; "</wsse:UsernameToken>"
0x1800ceb3e  mov     rcx, r14
0x1800ceb41  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBD@Z; ATL::CSimpleStringT<char,0>::Append(char const *)
0x1800ceb46  nop
0x1800ceb47  lea     rcx, [rbp+150h+arg_18]
0x1800ceb4e  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800ceb53  call    cs:__imp_MsaDevice_UseXTokenBasedSessionKey
0x1800ceb59  test    eax, eax
0x1800ceb5b  jnz     loc_1800CEBEF
0x1800ceb61  xor     r9d, r9d; bool
0x1800ceb64  mov     r8d, [rbp+150h+var_138]; unsigned int
0x1800ceb68  mov     rdx, [rbp+150h+var_130]; unsigned __int8 *
0x1800ceb6c  lea     rcx, [rsp+250h+var_200]; this
0x1800ceb71  call    ?Attach@CBytePtr@@QEAAXPEAEK_N@Z; CBytePtr::Attach(uchar *,ulong,bool)
0x1800ceb76  mov     rsi, [rsp+250h+var_1F8]
0x1800ceb7b  test    rsi, rsi
0x1800ceb7e  jnz     short loc_1800CEBA1
0x1800ceb80  cmp     [rdi+0C8h], r13
0x1800ceb87  jnz     short loc_1800CEBA1
0x1800ceb89  mov     r9d, 8004800Eh
0x1800ceb8f  lea     rax, aAuthsessionkey; "authSessionKey.GetBuffer() != nullptr |"...
0x1800ceb96  mov     r8d, 15B1h
0x1800ceb9c  jmp     loc_1800CE813
0x1800ceba1  mov     r14d, [rbp+150h+var_1C0]
0x1800ceba5  mov     ebx, [rsp+250h+var_200]
0x1800ceba9  cmp     [r12], r13d
0x1800cebad  jnz     short loc_1800CEBC7
0x1800cebaf  xor     r9d, r9d; bool
0x1800cebb2  mov     r8d, ebx; unsigned int
0x1800cebb5  mov     rdx, rsi; unsigned __int8 *
0x1800cebb8  mov     rcx, r12; this
0x1800cebbb  call    ?Attach@CBytePtr@@QEAAXPEAEK_N@Z; CBytePtr::Attach(uchar *,ulong,bool)
0x1800cebc0  mov     [rdi+0D8h], r14d
0x1800cebc7  test    ebx, ebx
0x1800cebc9  jz      short loc_1800CEBEF
0x1800cebcb  mov     rcx, [rdi+18h]
0x1800cebcf  add     rcx, 2F0h; this
0x1800cebd6  xor     r9d, r9d; bool
0x1800cebd9  mov     r8d, ebx; unsigned int
0x1800cebdc  mov     rdx, rsi; unsigned __int8 *
0x1800cebdf  call    ?Attach@CBytePtr@@QEAAXPEAEK_N@Z; CBytePtr::Attach(uchar *,ulong,bool)
0x1800cebe4  mov     rax, [rdi+18h]
0x1800cebe8  mov     [rax+2E8h], r14d
0x1800cebef  mov     ebx, [rbp+150h+arg_0]
0x1800cebf5  lea     rcx, [rsp+250h+var_200]; this
0x1800cebfa  call    ?Empty@CBytePtr@@QEAAXXZ; CBytePtr::Empty(void)
0x1800cebff  nop
0x1800cec00  lea     rcx, [rsp+250h+var_210]
0x1800cec05  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800cec0a  nop
0x1800cec0b  lea     rcx, [rsp+250h+lpWideCharStr]
0x1800cec10  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800cec15  nop
  ... truncated ...
```
