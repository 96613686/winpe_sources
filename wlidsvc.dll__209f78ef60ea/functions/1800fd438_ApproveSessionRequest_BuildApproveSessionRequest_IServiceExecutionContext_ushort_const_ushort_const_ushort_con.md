# ApproveSessionRequest::BuildApproveSessionRequest(IServiceExecutionContext *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x1800fd438`
- end: `0x1800fd94c`
- name: `?BuildApproveSessionRequest@ApproveSessionRequest@@QEAAJPEAVIServiceExecutionContext@@PEBG1111111@Z`
- size: `1300`
- prototype: `__int64 __fastcall(ApproveSessionRequest *__hidden this, struct IServiceExecutionContext *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800bdf30`

## callees

- `0x18000a354`
- `0x18000c050`
- `0x18000e008`
- `0x18000ed04`
- `0x1800151c4`
- `0x180015430`
- `0x1800160a8`
- `0x1800161e0`
- `0x180016500`
- `0x180017410`
- `0x180017830`
- `0x18001a9c0`
- `0x18001ad00`
- `0x18001b330`
- `0x180021b28`
- `0x18002eed0`
- `0x180042468`
- `0x1800fd438`
- `0x180108258`
- `0x180128010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800fd4ec`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800fd554`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800fd578`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800fd58c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800fd4ec`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800fd554`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800fd578`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800fd58c`

## string_xrefs

- `0x1800fd534`: `</wsse:BinarySecurityToken>`
- `0x1800fd7c0`: `<?xml version="1.0" encoding="UTF-8"?><s:Envelope xmlns:s="http://www.w3.org/2003/05/soap-envelope" xmlns:ps="http://schemas.microsoft.com/Passport/SoapServices/PPCRL" xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd" xmlns:saml="urn:oasis:names:tc:SAML:1.0:assertion" xmlns:wsp="http://schemas.xmlsoap.org/ws/2004/09/policy" xmlns:wsu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd" xmlns:wsa="http://www.w3.org/2005/`
- `0x1800fd582`: `ApproveUSID`
- `0x1800fd7d0`: `<wsse:Security>`
- `0x1800fd633`: `</wsse:Username></wsse:UsernameToken>`
- `0x1800fd7ed`: `</wsse:Security>`
- `0x1800fd518`: `<wsse:BinarySecurityToken id="DeviceDAToken" ValueType="urn:liveid:sha1device">`
- `0x1800fd4c0`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\approvesessionrequest.cpp`
- `0x1800fd5d5`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\approvesessionrequest.cpp`
- `0x1800fd8e4`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\approvesessionrequest.cpp`
- `0x1800fd616`: `<wsse:UsernameToken Id="user"><wsse:Username>`
- `0x1800fd5b9`: `hr = AppendLoginKeyTokenToRequestXml(pExecutionContext, JWTXml, NGC_DONOT_DISPLAY_ALT_CRED_OPTION)`
- `0x1800fd650`: `<ps:OneTimeCredentials xmlns:ps="http://schemas.microsoft.com/Passport/SoapServices/PPCRL">`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall ApproveSessionRequest::BuildApproveSessionRequest(
        ApproveSessionRequest *this,
        struct IServiceExecutionContext *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        const unsigned __int16 *a6,
        const unsigned __int16 *a7,
        const unsigned __int16 *a8,
        const unsigned __int16 *a9,
        const unsigned __int16 *a10)
{
  int v14; // eax
  const unsigned __int16 *v15; // rsi
  __int64 v16; // rdx
  int v17; // eax
  __int64 v18; // rdx
  __int64 v19; // r8
  const char *v20; // rdx
  __int64 v21; // rcx
  unsigned int v22; // ebx
  char *v24; // [rsp+20h] [rbp-69h]
  __int64 v25; // [rsp+30h] [rbp-59h] BYREF
  __int64 v26; // [rsp+38h] [rbp-51h] BYREF
  __int64 v27; // [rsp+40h] [rbp-49h] BYREF
  const unsigned __int8 *v28; // [rsp+48h] [rbp-41h] BYREF
  __int64 v29; // [rsp+50h] [rbp-39h] BYREF
  _QWORD v30[3]; // [rsp+58h] [rbp-31h] BYREF
  _QWORD v31[4]; // [rsp+70h] [rbp-19h] BYREF
  int v32; // [rsp+C0h] [rbp+37h] BYREF

  v32 = 0;
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v29);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v26);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v25);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v27);
  memset(v30, 0, sizeof(v30));
  v31[0] = "ApproveSessionRequest::BuildApproveSessionRequest";
  v31[1] = &v32;
  v31[2] = 0;
  v31[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\approvesessionrequest.cpp",
    "ApproveSessionRequest::BuildApproveSessionRequest",
    (const char *)0x38,
    0,
    (const unsigned __int16 *)v24);
  ATL::CSimpleStringT<char,0>::Truncate((char *)this + 40, 0);
  *((_DWORD *)this + 61) = 0;
  v14 = _o__wcsicmp(a10, L"Device");
  v15 = a9;
  if ( v14 )
  {
    if ( (unsigned int)_o__wcsicmp(a10, L"NGC") )
    {
      v32 = -2147024809;
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\approvesessionrequest.cpp",
        "ApproveSessionRequest::BuildApproveSessionRequest",
        0x5Fu,
        -2147024809,
        "hr = E_INVALIDARG");
      goto LABEL_19;
    }
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v28);
    if ( !(unsigned int)_o__wcsicmp(v15, L"Approve") || !(unsigned int)_o__wcsicmp(v15, L"ApproveUSID") )
    {
      v17 = (*(__int64 (__fastcall **)(ApproveSessionRequest *, struct IServiceExecutionContext *, const unsigned __int8 **, _QWORD))(*(_QWORD *)this + 200LL))(
              this,
              a2,
              &v28,
              0);
      v32 = v17;
      if ( v17 < 0 )
      {
        Telemetry::IfFailExit(
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\approvesessionrequest.cpp",
          "ApproveSessionRequest::BuildApproveSessionRequest",
          0x51u,
          v17,
          "hr = AppendLoginKeyTokenToRequestXml(pExecutionContext, JWTXml, NGC_DONOT_DISPLAY_ALT_CRED_OPTION)");
        CAutoZeroMemoryStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CAutoZeroMemoryStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)&v28);
        goto LABEL_19;
      }
    }
    v18 = -1;
    do
      ++v18;
    while ( a4[v18] );
    ATL::CSimpleStringT<char,0>::PrepareWrite(&v26, (unsigned int)(*((_DWORD *)v28 - 4) + 400 + v18));
    ATL::CSimpleStringT<char,0>::Append(&v26, "<wsse:UsernameToken Id=\"user\"><wsse:Username>");
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::operator+=(&v26, a5);
    ATL::CSimpleStringT<char,0>::Append(&v26, "</wsse:Username></wsse:UsernameToken>");
    ATL::CSimpleStringT<char,0>::Append(&v26, &v28);
    ATL::CSimpleStringT<char,0>::Append(
      &v26,
      "<ps:OneTimeCredentials xmlns:ps=\"http://schemas.microsoft.com/Passport/SoapServices/PPCRL\">");
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::operator+=(&v26, a4);
    ATL::CSimpleStringT<char,0>::Append(&v26, "</ps:OneTimeCredentials>");
    CAutoZeroMemoryStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CAutoZeroMemoryStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)&v28);
  }
  else
  {
    v16 = -1;
    do
      ++v16;
    while ( a3[v16] );
    ATL::CSimpleStringT<char,0>::PrepareWrite(&v26, (unsigned int)(v16 + 200));
    ATL::CSimpleStringT<char,0>::Append(
      &v26,
      "<wsse:BinarySecurityToken id=\"DeviceDAToken\" ValueType=\"urn:liveid:sha1device\">");
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::operator+=(&v26, a3);
    ATL::CSimpleStringT<char,0>::Append(&v26, "</wsse:BinarySecurityToken>");
  }
  ATL::CSimpleStringT<char,0>::PrepareWrite(&v29, 900);
  ATL::CSimpleStringT<char,0>::Append(&v29, "<ps:ClientVersion>");
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::operator+=(&v29, a7);
  ATL::CSimpleStringT<char,0>::Append(&v29, "</ps:ClientVersion>");
  CPPCRLBaseRequest::AppendDeviceType(&v29);
  ATL::CSimpleStringT<char,0>::PrepareWrite(&v25, 900);
  ATL::CSimpleStringT<char,0>::Append(&v25, "<ps:ApproveSessionRequest>");
  ATL::CSimpleStringT<char,0>::Append(&v25, "<ps:UserPUID>");
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::operator+=(&v25, a6);
  ATL::CSimpleStringT<char,0>::Append(&v25, "</ps:UserPUID>");
  ATL::CSimpleStringT<char,0>::Append(&v25, "<ps:SessionID>");
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::operator+=(&v25, a8);
  ATL::CSimpleStringT<char,0>::Append(&v25, "</ps:SessionID>");
  ATL::CSimpleStringT<char,0>::Append(&v25, "<ps:SessionState>");
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::operator+=(&v25, v15);
  ATL::CSimpleStringT<char,0>::Append(&v25, "</ps:SessionState>");
  ATL::CSimpleStringT<char,0>::Append(&v25, "<ps:SessionType>");
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::operator+=(&v25, a10);
  ATL::CSimpleStringT<char,0>::Append(&v25, "</ps:SessionType>");
  ATL::CSimpleStringT<char,0>::Append(&v25, "</ps:ApproveSessionRequest>");
  ATL::CSimpleStringT<char,0>::PrepareWrite(&v27, (unsigned int)(*(_DWORD *)(v26 - 16) + 1800));
  ATL::CSimpleStringT<char,0>::Append(
    &v27,
    "<?xml version=\"1.0\" encoding=\"UTF-8\"?><s:Envelope xmlns:s=\"http://www.w3.org/2003/05/soap-envelope\" xmlns:ps=\""
    "http://schemas.microsoft.com/Passport/SoapServices/PPCRL\" xmlns:wsse=\"http://docs.oasis-open.org/wss/2004/01/oasis"
    "-200401-wss-wssecurity-secext-1.0.xsd\" xmlns:saml=\"urn:oasis:names:tc:SAML:1.0:assertion\" xmlns:wsp=\"http://sche"
    "mas.xmlsoap.org/ws/2004/09/policy\" xmlns:wsu=\"http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-u"
    "tility-1.0.xsd\" xmlns:wsa=\"http://www.w3.org/2005/08/addressing\" xmlns:wssc=\"http://schemas.xmlsoap.org/ws/2005/"
    "02/sc\" xmlns:wst=\"http://schemas.xmlsoap.org/ws/2005/02/trust\"><s:Header>");
  ATL::CSimpleStringT<char,0>::Append(&v27, "<wsse:Security>");
  ATL::CSimpleStringT<char,0>::Append(&v27, &v26);
  ATL::CSimpleStringT<char,0>::Append(&v27, "</wsse:Security>");
  ATL::CSimpleStringT<char,0>::Append(&v27, "<ps:AuthInfo>");
  ATL::CSimpleStringT<char,0>::Append(&v27, &v29);
  ATL::CSimpleStringT<char,0>::Append(&v27, "</ps:AuthInfo>");
  ATL::CSimpleStringT<char,0>::Append(&v27, "</s:Header><s:Body>");
  ATL::CSimpleStringT<char,0>::Append(&v27, &v25);
  ATL::CSimpleStringT<char,0>::Append(&v27, "</s:Body></s:Envelope>");
  ATL::CSimpleStringT<char,0>::operator=((char *)this + 40, &v27);
  if ( (byte_1801C36C5 & 4) != 0 )
  {
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v28);
    LOBYTE(v19) = PPTraceShouldRedact();
    if ( (int)RedactSensitiveXMLElements(&v27, &v28, v19) >= 0 )
    {
      ReduceXmlForTracing(&v28, v20);
      if ( (byte_1801C36C5 & 4) != 0 )
        McTemplateU0s_EventWriteTransfer(v21, SOAPRequest, v28);
    }
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v28);
  }
LABEL_19:
  v22 = v32;
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v31);
  Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>((__int64)v30);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v27);
  CAutoZeroMemoryStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CAutoZeroMemoryStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)&v25);
  CAutoZeroMemoryStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CAutoZeroMemoryStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)&v26);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v29);
  return v22;
}

```

## disassembly

```asm
0x1800fd438  mov     [rsp-8+arg_8], rbx
0x1800fd43d  mov     [rsp-8+arg_10], rsi
0x1800fd442  push    rbp
0x1800fd443  push    rdi
0x1800fd444  push    r12
0x1800fd446  push    r13
0x1800fd448  push    r14
0x1800fd44a  lea     rbp, [rsp-7]
0x1800fd44f  sub     rsp, 90h
0x1800fd456  mov     r14, r9
0x1800fd459  mov     rdi, r8
0x1800fd45c  mov     r12, rdx
0x1800fd45f  mov     rbx, rcx
0x1800fd462  xor     esi, esi
0x1800fd464  mov     [rbp+27h+arg_0], esi
0x1800fd467  lea     rcx, [rbp+27h+var_60]
0x1800fd46b  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800fd470  nop
0x1800fd471  lea     rcx, [rbp+27h+var_78]
0x1800fd475  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800fd47a  nop
0x1800fd47b  lea     rcx, [rbp+27h+var_80]
0x1800fd47f  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800fd484  nop
0x1800fd485  lea     rcx, [rbp+27h+var_70]
0x1800fd489  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800fd48e  nop
0x1800fd48f  mov     [rbp+27h+var_58], rsi
0x1800fd493  mov     [rbp+27h+var_48], rsi
0x1800fd497  mov     [rbp+27h+var_50], rsi
0x1800fd49b  lea     rcx, aApprovesession_1; "ApproveSessionRequest::BuildApproveSess"...
0x1800fd4a2  mov     [rbp+27h+var_40], rcx
0x1800fd4a6  lea     rax, [rbp+27h+arg_0]
0x1800fd4aa  mov     [rbp+27h+var_38], rax
0x1800fd4ae  mov     [rbp+27h+var_30], rsi
0x1800fd4b2  mov     [rbp+27h+var_28], rsi
0x1800fd4b6  xor     r9d, r9d; unsigned int
0x1800fd4b9  lea     r8d, [rsi+38h]; char *
0x1800fd4bd  mov     rdx, rcx; char *
0x1800fd4c0  lea     rcx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800fd4c7  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x1800fd4cc  nop
0x1800fd4cd  lea     r13, [rbx+28h]
0x1800fd4d1  xor     edx, edx
0x1800fd4d3  mov     rcx, r13
0x1800fd4d6  call    ?Truncate@?$CSimpleStringT@D$0A@@ATL@@QEAAXH@Z; ATL::CSimpleStringT<char,0>::Truncate(int)
0x1800fd4db  mov     [rbx+0F4h], esi
0x1800fd4e1  lea     rdx, aDevice; "Device"
0x1800fd4e8  mov     rcx, [rbp+27h+arg_48]
0x1800fd4ec  call    cs:__imp__o__wcsicmp
0x1800fd4f2  mov     rsi, [rbp+27h+arg_40]
0x1800fd4f6  xor     ecx, ecx
0x1800fd4f8  test    eax, eax
0x1800fd4fa  jnz     short loc_1800FD549
0x1800fd4fc  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800fd500  inc     rdx
0x1800fd503  cmp     [rdi+rdx*2], cx
0x1800fd507  jnz     short loc_1800FD500
0x1800fd509  add     edx, 0C8h
0x1800fd50f  lea     rcx, [rbp+27h+var_78]
0x1800fd513  call    ?PrepareWrite@?$CSimpleStringT@D$0A@@ATL@@AEAAPEADH@Z; ATL::CSimpleStringT<char,0>::PrepareWrite(int)
0x1800fd518  lea     rdx, aWsseBinarysecu_11; "<wsse:BinarySecurityToken id=\"DeviceDA"...
0x1800fd51f  lea     rcx, [rbp+27h+var_78]
0x1800fd523  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBD@Z; ATL::CSimpleStringT<char,0>::Append(char const *)
0x1800fd528  mov     rdx, rdi
0x1800fd52b  lea     rcx, [rbp+27h+var_78]
0x1800fd52f  call    ??Y?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBG@Z; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::operator+=(ushort const *)
0x1800fd534  lea     rdx, aWsseBinarysecu_1; "</wsse:BinarySecurityToken>"
0x1800fd53b  lea     rcx, [rbp+27h+var_78]
0x1800fd53f  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBD@Z; ATL::CSimpleStringT<char,0>::Append(char const *)
0x1800fd544  jmp     loc_1800FD686
0x1800fd549  lea     rdx, aNgc; "NGC"
0x1800fd550  mov     rcx, [rbp+27h+arg_48]
0x1800fd554  call    cs:__imp__o__wcsicmp
0x1800fd55a  xor     edi, edi
0x1800fd55c  test    eax, eax
0x1800fd55e  jnz     loc_1800FD8C1
0x1800fd564  lea     rcx, [rbp+27h+var_68]
0x1800fd568  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800fd56d  nop
0x1800fd56e  lea     rdx, aApprove; "Approve"
0x1800fd575  mov     rcx, rsi
0x1800fd578  call    cs:__imp__o__wcsicmp
0x1800fd57e  test    eax, eax
0x1800fd580  jz      short loc_1800FD596
0x1800fd582  lea     rdx, aApproveusid; "ApproveUSID"
0x1800fd589  mov     rcx, rsi
0x1800fd58c  call    cs:__imp__o__wcsicmp
0x1800fd592  test    eax, eax
0x1800fd594  jnz     short loc_1800FD5F0
0x1800fd596  mov     rax, [rbx]
0x1800fd599  xor     r9d, r9d
0x1800fd59c  lea     r8, [rbp+27h+var_68]
0x1800fd5a0  mov     rdx, r12
0x1800fd5a3  mov     rcx, rbx
0x1800fd5a6  mov     rax, [rax+0C8h]
0x1800fd5ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fd5b2  mov     [rbp+27h+arg_0], eax
0x1800fd5b5  test    eax, eax
0x1800fd5b7  jns     short loc_1800FD5F0
0x1800fd5b9  lea     r8, aHrAppendlogink_0; "hr = AppendLoginKeyTokenToRequestXml(pE"...
0x1800fd5c0  mov     [rsp+0B0h+var_90], r8; char *
0x1800fd5c5  mov     r9d, eax; int
0x1800fd5c8  mov     r8d, 51h ; 'Q'; unsigned int
0x1800fd5ce  lea     rdx, aApprovesession_1; "ApproveSessionRequest::BuildApproveSess"...
0x1800fd5d5  lea     rcx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800fd5dc  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x1800fd5e1  nop
0x1800fd5e2  lea     rcx, [rbp+27h+var_68]
0x1800fd5e6  call    ??1?$CAutoZeroMemoryStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@@QEAA@XZ; CAutoZeroMemoryStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CAutoZeroMemoryStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800fd5eb  jmp     loc_1800FD8F0
0x1800fd5f0  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800fd5f4  inc     rdx
0x1800fd5f7  cmp     [r14+rdx*2], di
0x1800fd5fc  jnz     short loc_1800FD5F4
0x1800fd5fe  mov     rax, [rbp+27h+var_68]
0x1800fd602  mov     ecx, [rax-10h]
0x1800fd605  add     ecx, 190h
0x1800fd60b  add     edx, ecx
0x1800fd60d  lea     rcx, [rbp+27h+var_78]
0x1800fd611  call    ?PrepareWrite@?$CSimpleStringT@D$0A@@ATL@@AEAAPEADH@Z; ATL::CSimpleStringT<char,0>::PrepareWrite(int)
0x1800fd616  lea     rdx, aWsseUsernameto_0; "<wsse:UsernameToken Id=\"user\"><wsse:U"...
0x1800fd61d  lea     rcx, [rbp+27h+var_78]
0x1800fd621  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBD@Z; ATL::CSimpleStringT<char,0>::Append(char const *)
0x1800fd626  mov     rdx, [rbp+27h+arg_20]
0x1800fd62a  lea     rcx, [rbp+27h+var_78]
0x1800fd62e  call    ??Y?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBG@Z; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::operator+=(ushort const *)
0x1800fd633  lea     rdx, aWsseUsernameWs_0; "</wsse:Username></wsse:UsernameToken>"
0x1800fd63a  lea     rcx, [rbp+27h+var_78]
0x1800fd63e  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBD@Z; ATL::CSimpleStringT<char,0>::Append(char const *)
0x1800fd643  lea     rdx, [rbp+27h+var_68]
0x1800fd647  lea     rcx, [rbp+27h+var_78]
0x1800fd64b  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXAEBV12@@Z; ATL::CSimpleStringT<char,0>::Append(ATL::CSimpleStringT<char,0> const &)
0x1800fd650  lea     rdx, aPsOnetimecrede_2; "<ps:OneTimeCredentials xmlns:ps=\"http:"...
0x1800fd657  lea     rcx, [rbp+27h+var_78]
0x1800fd65b  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBD@Z; ATL::CSimpleStringT<char,0>::Append(char const *)
0x1800fd660  mov     rdx, r14
0x1800fd663  lea     rcx, [rbp+27h+var_78]
0x1800fd667  call    ??Y?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBG@Z; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::operator+=(ushort const *)
0x1800fd66c  lea     rdx, aPsOnetimecrede_0; "</ps:OneTimeCredentials>"
0x1800fd673  lea     rcx, [rbp+27h+var_78]
0x1800fd677  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBD@Z; ATL::CSimpleStringT<char,0>::Append(char const *)
0x1800fd67c  nop
0x1800fd67d  lea     rcx, [rbp+27h+var_68]
0x1800fd681  call    ??1?$CAutoZeroMemoryStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@@QEAA@XZ; CAutoZeroMemoryStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CAutoZeroMemoryStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800fd686  mov     ebx, 384h
0x1800fd68b  mov     edx, ebx
0x1800fd68d  lea     rcx, [rbp+27h+var_60]
0x1800fd691  call    ?PrepareWrite@?$CSimpleStringT@D$0A@@ATL@@AEAAPEADH@Z; ATL::CSimpleStringT<char,0>::PrepareWrite(int)
0x1800fd696  lea     rdx, aPsClientversio_0; "<ps:ClientVersion>"
0x1800fd69d  lea     rcx, [rbp+27h+var_60]
0x1800fd6a1  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBD@Z; ATL::CSimpleStringT<char,0>::Append(char const *)
0x1800fd6a6  mov     rdx, [rbp+27h+arg_30]
0x1800fd6aa  lea     rcx, [rbp+27h+var_60]
0x1800fd6ae  call    ??Y?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBG@Z; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::operator+=(ushort const *)
0x1800fd6b3  lea     rdx, aPsClientversio; "</ps:ClientVersion>"
0x1800fd6ba  lea     rcx, [rbp+27h+var_60]
0x1800fd6be  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBD@Z; ATL::CSimpleStringT<char,0>::Append(char const *)
0x1800fd6c3  lea     rcx, [rbp+27h+var_60]
0x1800fd6c7  call    ?AppendDeviceType@CPPCRLBaseRequest@@SAJAEAV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@@Z; CPPCRLBaseRequest::AppendDeviceType(ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> &)
0x1800fd6cc  mov     edx, ebx
0x1800fd6ce  lea     rcx, [rbp+27h+var_80]
0x1800fd6d2  call    ?PrepareWrite@?$CSimpleStringT@D$0A@@ATL@@AEAAPEADH@Z; ATL::CSimpleStringT<char,0>::PrepareWrite(int)
0x1800fd6d7  lea     rdx, aPsApprovesessi; "<ps:ApproveSessionRequest>"
0x1800fd6de  lea     rcx, [rbp+27h+var_80]
0x1800fd6e2  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBD@Z; ATL::CSimpleStringT<char,0>::Append(char const *)
0x1800fd6e7  lea     rdx, aPsUserpuid; "<ps:UserPUID>"
0x1800fd6ee  lea     rcx, [rbp+27h+var_80]
0x1800fd6f2  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBD@Z; ATL::CSimpleStringT<char,0>::Append(char const *)
0x1800fd6f7  mov     rdx, [rbp+27h+arg_28]
0x1800fd6fb  lea     rcx, [rbp+27h+var_80]
0x1800fd6ff  call    ??Y?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBG@Z; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::operator+=(ushort const *)
0x1800fd704  lea     rdx, aPsUserpuid_0; "</ps:UserPUID>"
0x1800fd70b  lea     rcx, [rbp+27h+var_80]
0x1800fd70f  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBD@Z; ATL::CSimpleStringT<char,0>::Append(char const *)
0x1800fd714  lea     rdx, aPsSessionid_0; "<ps:SessionID>"
0x1800fd71b  lea     rcx, [rbp+27h+var_80]
0x1800fd71f  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBD@Z; ATL::CSimpleStringT<char,0>::Append(char const *)
0x1800fd724  mov     rdx, [rbp+27h+arg_38]
0x1800fd728  lea     rcx, [rbp+27h+var_80]
0x1800fd72c  call    ??Y?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBG@Z; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::operator+=(ushort const *)
0x1800fd731  lea     rdx, aPsSessionid_2; "</ps:SessionID>"
0x1800fd738  lea     rcx, [rbp+27h+var_80]
0x1800fd73c  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBD@Z; ATL::CSimpleStringT<char,0>::Append(char const *)
0x1800fd741  lea     rdx, aPsSessionstate; "<ps:SessionState>"
0x1800fd748  lea     rcx, [rbp+27h+var_80]
0x1800fd74c  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBD@Z; ATL::CSimpleStringT<char,0>::Append(char const *)
0x1800fd751  mov     rdx, rsi
0x1800fd754  lea     rcx, [rbp+27h+var_80]
0x1800fd758  call    ??Y?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBG@Z; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::operator+=(ushort const *)
0x1800fd75d  lea     rdx, aPsSessionstate_0; "</ps:SessionState>"
0x1800fd764  lea     rcx, [rbp+27h+var_80]
0x1800fd768  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBD@Z; ATL::CSimpleStringT<char,0>::Append(char const *)
0x1800fd76d  lea     rdx, aPsSessiontype_1; "<ps:SessionType>"
0x1800fd774  lea     rcx, [rbp+27h+var_80]
0x1800fd778  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBD@Z; ATL::CSimpleStringT<char,0>::Append(char const *)
0x1800fd77d  mov     rdx, [rbp+27h+arg_48]
0x1800fd781  lea     rcx, [rbp+27h+var_80]
0x1800fd785  call    ??Y?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBG@Z; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::operator+=(ushort const *)
0x1800fd78a  lea     rdx, aPsSessiontype_0; "</ps:SessionType>"
0x1800fd791  lea     rcx, [rbp+27h+var_80]
0x1800fd795  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBD@Z; ATL::CSimpleStringT<char,0>::Append(char const *)
0x1800fd79a  lea     rdx, aPsApprovesessi_0; "</ps:ApproveSessionRequest>"
0x1800fd7a1  lea     rcx, [rbp+27h+var_80]
0x1800fd7a5  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBD@Z; ATL::CSimpleStringT<char,0>::Append(char const *)
0x1800fd7aa  mov     rax, [rbp+27h+var_78]
0x1800fd7ae  mov     edx, [rax-10h]
0x1800fd7b1  add     edx, 708h
0x1800fd7b7  lea     rcx, [rbp+27h+var_70]
0x1800fd7bb  call    ?PrepareWrite@?$CSimpleStringT@D$0A@@ATL@@AEAAPEADH@Z; ATL::CSimpleStringT<char,0>::PrepareWrite(int)
0x1800fd7c0  lea     rdx, aXmlVersion10En; "<?xml version=\"1.0\" encoding=\"UTF-8"...
0x1800fd7c7  lea     rcx, [rbp+27h+var_70]
0x1800fd7cb  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBD@Z; ATL::CSimpleStringT<char,0>::Append(char const *)
0x1800fd7d0  lea     rdx, aWsseSecurity_0; "<wsse:Security>"
0x1800fd7d7  lea     rcx, [rbp+27h+var_70]
0x1800fd7db  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBD@Z; ATL::CSimpleStringT<char,0>::Append(char const *)
0x1800fd7e0  lea     rdx, [rbp+27h+var_78]
0x1800fd7e4  lea     rcx, [rbp+27h+var_70]
0x1800fd7e8  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXAEBV12@@Z; ATL::CSimpleStringT<char,0>::Append(ATL::CSimpleStringT<char,0> const &)
0x1800fd7ed  lea     rdx, aWsseSecurity; "</wsse:Security>"
0x1800fd7f4  lea     rcx, [rbp+27h+var_70]
0x1800fd7f8  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBD@Z; ATL::CSimpleStringT<char,0>::Append(char const *)
0x1800fd7fd  lea     rdx, aPsAuthinfo_0; "<ps:AuthInfo>"
0x1800fd804  lea     rcx, [rbp+27h+var_70]
0x1800fd808  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBD@Z; ATL::CSimpleStringT<char,0>::Append(char const *)
0x1800fd80d  lea     rdx, [rbp+27h+var_60]
0x1800fd811  lea     rcx, [rbp+27h+var_70]
0x1800fd815  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXAEBV12@@Z; ATL::CSimpleStringT<char,0>::Append(ATL::CSimpleStringT<char,0> const &)
0x1800fd81a  lea     rdx, aPsAuthinfo; "</ps:AuthInfo>"
0x1800fd821  lea     rcx, [rbp+27h+var_70]
0x1800fd825  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBD@Z; ATL::CSimpleStringT<char,0>::Append(char const *)
0x1800fd82a  lea     rdx, aSHeaderSBody; "</s:Header><s:Body>"
0x1800fd831  lea     rcx, [rbp+27h+var_70]
0x1800fd835  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBD@Z; ATL::CSimpleStringT<char,0>::Append(char const *)
0x1800fd83a  lea     rdx, [rbp+27h+var_80]
0x1800fd83e  lea     rcx, [rbp+27h+var_70]
0x1800fd842  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXAEBV12@@Z; ATL::CSimpleStringT<char,0>::Append(ATL::CSimpleStringT<char,0> const &)
0x1800fd847  lea     rdx, aSBodySEnvelope; "</s:Body></s:Envelope>"
0x1800fd84e  lea     rcx, [rbp+27h+var_70]
0x1800fd852  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBD@Z; ATL::CSimpleStringT<char,0>::Append(char const *)
0x1800fd857  lea     rdx, [rbp+27h+var_70]
0x1800fd85b  mov     rcx, r13
0x1800fd85e  call    ??4?$CSimpleStringT@D$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<char,0>::operator=(ATL::CSimpleStringT<char,0> const &)
0x1800fd863  test    cs:byte_1801C36C5, 4
0x1800fd86a  jz      loc_1800FD8F0
0x1800fd870  lea     rcx, [rbp+27h+var_68]
0x1800fd874  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800fd879  nop
0x1800fd87a  call    ?PPTraceShouldRedact@@YA_NXZ; PPTraceShouldRedact(void)
0x1800fd87f  mov     r8b, al
0x1800fd882  lea     rdx, [rbp+27h+var_68]
0x1800fd886  lea     rcx, [rbp+27h+var_70]
0x1800fd88a  call    ?RedactSensitiveXMLElements@@YAJAEBV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@AEAV12@_N@Z; RedactSensitiveXMLElements(ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> const &,ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> &,bool)
0x1800fd88f  test    eax, eax
0x1800fd891  js      short loc_1800FD8B6
0x1800fd893  lea     rcx, [rbp+27h+var_68]
0x1800fd897  call    ?ReduceXmlForTracing@@YAJAEAV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@@Z; ReduceXmlForTracing(ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> &)
0x1800fd89c  test    cs:byte_1801C36C5, 4
0x1800fd8a3  jz      short loc_1800FD8B6
0x1800fd8a5  mov     r8, [rbp+27h+var_68]
0x1800fd8a9  lea     rdx, SOAPRequest
0x1800fd8b0  call    McTemplateU0s_EventWriteTransfer
0x1800fd8b5  nop
0x1800fd8b6  lea     rcx, [rbp+27h+var_68]
0x1800fd8ba  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800fd8bf  jmp     short loc_1800FD8F0
0x1800fd8c1  mov     r9d, 80070057h; int
0x1800fd8c7  mov     [rbp+27h+arg_0], r9d
0x1800fd8cb  lea     rax, aHrEInvalidarg; "hr = E_INVALIDARG"
0x1800fd8d2  mov     [rsp+0B0h+var_90], rax; char *
0x1800fd8d7  mov     r8d, 5Fh ; '_'; unsigned int
0x1800fd8dd  lea     rdx, aApprovesession_1; "ApproveSessionRequest::BuildApproveSess"...
0x1800fd8e4  lea     rcx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800fd8eb  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x1800fd8f0  mov     ebx, [rbp+27h+arg_0]
0x1800fd8f3  lea     rcx, [rbp+27h+var_40]
0x1800fd8f7  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x1800fd8fc  nop
0x1800fd8fd  lea     rcx, [rbp+27h+var_58]
0x1800fd901  call    ??1?$Auto@PEAU_TOKEN_USER@@V?$LocalAllocFunctor@PEAU_TOKEN_USER@@@@VDummyContext@@@@QEAA@XZ; Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>(void)
0x1800fd906  nop
0x1800fd907  lea     rcx, [rbp+27h+var_70]
0x1800fd90b  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800fd910  nop
0x1800fd911  lea     rcx, [rbp+27h+var_80]
0x1800fd915  call    ??1?$CAutoZeroMemoryStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@@QEAA@XZ; CAutoZeroMemoryStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CAutoZeroMemoryStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800fd91a  nop
0x1800fd91b  lea     rcx, [rbp+27h+var_78]
0x1800fd91f  call    ??1?$CAutoZeroMemoryStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@@QEAA@XZ; CAutoZeroMemoryStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CAutoZeroMemoryStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800fd924  nop
0x1800fd925  lea     rcx, [rbp+27h+var_60]
0x1800fd929  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800fd92e  mov     eax, ebx
0x1800fd930  lea     r11, [rsp+0B0h+var_20]
0x1800fd938  mov     rbx, [r11+38h]
0x1800fd93c  mov     rsi, [r11+40h]
0x1800fd940  mov     rsp, r11
0x1800fd943  pop     r14
0x1800fd945  pop     r13
0x1800fd947  pop     r12
  ... truncated ...
```
