# WlidsvcUtil::ParseChallengeToken(ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ulong &)

- ea: `0x1800f479c`
- end: `0x1800f4b2c`
- name: `?ParseChallengeToken@WlidsvcUtil@@SAJPEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAK@Z`
- size: `912`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180046b4c`

## callees

- `0x18000c050`
- `0x180015860`
- `0x18001a530`
- `0x18001a9c0`
- `0x18002aeb0`
- `0x18002b4ec`
- `0x180039ee8`
- `0x18003eda8`
- `0x1800406a8`
- `0x1800f479c`
- `0x180128010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x1800f4aa8`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x1800f4aa8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800f48c8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800f49aa`
- `OLEAUT32!__imp_SysFreeString` at `0x1800f4a51`
- `OLEAUT32!__imp_SysFreeString` at `0x1800f4ad2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800f4ae7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800f4af2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800f48c8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800f49aa`
- `OLEAUT32!__imp_SysFreeString` at `0x1800f4a51`
- `OLEAUT32!__imp_SysFreeString` at `0x1800f4ad2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800f4ae7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800f4af2`
- `OLEAUT32!__imp_VariantClear` at `0x1800f4842`
- `OLEAUT32!__imp_VariantClear` at `0x1800f4842`

## string_xrefs

- `0x1800f480c`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\wlidsvcutil.cpp`
- `0x1800f4867`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\wlidsvcutil.cpp`
- `0x1800f484f`: `hr = CreateDOM(pszChallenge, pDOMXml)`
- `0x1800f47f6`: `WlidsvcUtil::ParseChallengeToken`
- `0x1800f49cb`: `WlidsvcUtil::ParseChallengeToken`
- `0x1800f48dc`: `SUCCEEDED(hr = pDOMXml->selectSingleNode(CComBSTR(AUTHZ_TOKEN_XPATH_TYPE), &pMessageTypeNode)) && pMessageTypeNode != nullptr`
- `0x1800f4886`: `/WlidToken/Type`
- `0x1800f4946`: `bstrType == AUTHZ_TOKEN_TYPE_CHALLENGE`
- `0x1800f49b4`: `SUCCEEDED(hr = pDOMXml->selectSingleNode(CComBSTR(AUTHZ_TOKEN_XPATH_POLICY), &pPolicyNode)) && pPolicyNode != nullptr`
- `0x1800f4966`: `/WlidToken/ChallengeToken/Policy`
- `0x1800f4a12`: `/WlidToken/ChallengeToken/Flags`
- `0x1800f4a5c`: `SUCCEEDED(hr = pDOMXml->selectSingleNode(CComBSTR(AUTHZ_TOKEN_XPATH_FLAGS), &pFlagsNode)) && pFlagsNode != nullptr`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall WlidsvcUtil::ParseChallengeToken(unsigned __int16 *a1, __int64 a2, unsigned int *a3)
{
  int DOM; // ebx
  const char *v7; // rax
  int v8; // r9d
  unsigned int v9; // r8d
  __int64 (__fastcall *v10)(__int64, _QWORD, __int64 *); // rbx
  ATL::CComBSTR *v11; // rax
  char v12; // si
  char v13; // bl
  __int64 (__fastcall *v14)(__int64, _QWORD, __int64 *); // rbx
  ATL::CComBSTR *v15; // rax
  char v16; // bl
  __int64 (__fastcall *v17)(__int64, _QWORD, __int64 *); // rbx
  ATL::CComBSTR *v18; // rax
  unsigned int v19; // ebx
  __int64 v21; // [rsp+48h] [rbp-61h] BYREF
  BSTR bstrString; // [rsp+50h] [rbp-59h] BYREF
  __int64 v23; // [rsp+58h] [rbp-51h] BYREF
  __int64 v24; // [rsp+60h] [rbp-49h] BYREF
  __int64 v25; // [rsp+68h] [rbp-41h] BYREF
  BSTR v26; // [rsp+70h] [rbp-39h] BYREF
  wchar_t *String; // [rsp+78h] [rbp-31h] BYREF
  BSTR v28; // [rsp+80h] [rbp-29h] BYREF
  VARIANTARG pvarg; // [rsp+88h] [rbp-21h] BYREF
  const char *v30[12]; // [rsp+A0h] [rbp-9h] BYREF
  int v31; // [rsp+128h] [rbp+7Fh] BYREF

  v31 = 0;
  v21 = 0;
  v25 = 0;
  v24 = 0;
  v28 = 0;
  String = 0;
  v23 = 0;
  v26 = 0;
  CTraceFuncW<long>::CTraceFuncW<long>(
    v30,
    "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\wlidsvcutil.cpp",
    428,
    (const char *)&v31,
    "WlidsvcUtil::ParseChallengeToken",
    L"pszChallenge=%ls",
    a1);
  pvarg.vt = 0;
  ATL::CComVariant::operator=(&pvarg);
  DOM = CreateDOM(a1);
  VariantClear(&pvarg);
  v31 = DOM;
  if ( DOM >= 0 )
  {
    v10 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v21 + 296LL);
    v11 = ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, L"/WlidToken/Type");
    v12 = 1;
    v31 = v10(v21, *(_QWORD *)v11, &v23);
    if ( v31 < 0 || (v13 = 0, !v23) )
      v13 = 1;
    SysFreeString(bstrString);
    if ( v13 )
    {
      v8 = -2147024809;
      v31 = -2147024809;
      v7 = "SUCCEEDED(hr = pDOMXml->selectSingleNode(CComBSTR(AUTHZ_TOKEN_XPATH_TYPE), &pMessageTypeNode)) && pMessageTyp"
           "eNode != nullptr";
      v9 = 435;
    }
    else
    {
      v31 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v23 + 208LL))(v23, &v26);
      if ( v31 >= 0 )
      {
        if ( (unsigned __int8)ATL::CComBSTR::operator==(&v26, L"1") )
        {
          v14 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v21 + 296LL);
          v15 = ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, L"/WlidToken/ChallengeToken/Policy");
          v31 = v14(v21, *(_QWORD *)v15, &v25);
          if ( v31 < 0 || (v16 = 0, !v25) )
            v16 = 1;
          SysFreeString(bstrString);
          if ( v16 )
          {
            v7 = "SUCCEEDED(hr = pDOMXml->selectSingleNode(CComBSTR(AUTHZ_TOKEN_XPATH_POLICY), &pPolicyNode)) && pPolicyNode != nullptr";
            v9 = 441;
          }
          else
          {
            v31 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v25 + 208LL))(v25, &v28);
            if ( v31 >= 0 )
            {
              v17 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v21 + 296LL);
              v18 = ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, L"/WlidToken/ChallengeToken/Flags");
              v31 = v17(v21, *(_QWORD *)v18, &v24);
              if ( v31 >= 0 && v24 )
                v12 = 0;
              SysFreeString(bstrString);
              if ( v12 )
              {
                v7 = "SUCCEEDED(hr = pDOMXml->selectSingleNode(CComBSTR(AUTHZ_TOKEN_XPATH_FLAGS), &pFlagsNode)) && pFlagsNode != nullptr";
                v9 = 445;
              }
              else
              {
                v31 = (*(__int64 (__fastcall **)(__int64, wchar_t **))(*(_QWORD *)v24 + 208LL))(v24, &String);
                if ( v31 >= 0 )
                {
                  *a3 = wcstoul(String, 0, 10);
                  ATL::CSimpleStringT<unsigned short,0>::SetString(a2, v28);
                  v31 = 0;
                  goto LABEL_29;
                }
                v7 = "SUCCEEDED(hr = pFlagsNode->get_text(&bstrFlags))";
                v9 = 447;
              }
            }
            else
            {
              v7 = "SUCCEEDED(hr = pPolicyNode->get_text(&bstrPolicy))";
              v9 = 443;
            }
          }
          v8 = -2147024809;
          v31 = -2147024809;
        }
        else
        {
          v8 = -2147024809;
          v31 = -2147024809;
          v7 = "bstrType == AUTHZ_TOKEN_TYPE_CHALLENGE";
          v9 = 439;
        }
      }
      else
      {
        v8 = -2147024809;
        v31 = -2147024809;
        v7 = "SUCCEEDED(hr = pMessageTypeNode->get_text(&bstrType))";
        v9 = 437;
      }
    }
  }
  else
  {
    v7 = "hr = CreateDOM(pszChallenge, pDOMXml)";
    v8 = DOM;
    v9 = 430;
  }
  Telemetry::IfFailExit(
    "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\wlidsvcutil.cpp",
    "WlidsvcUtil::ParseChallengeToken",
    v9,
    v8,
    v7);
LABEL_29:
  v19 = v31;
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v30);
  SysFreeString(v26);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v23);
  SysFreeString(String);
  SysFreeString(v28);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v24);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v25);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v21);
  return v19;
}

```

## disassembly

```asm
0x1800f479c  push    rbp
0x1800f479e  push    rbx
0x1800f479f  push    rsi
0x1800f47a0  push    rdi
0x1800f47a1  push    r12
0x1800f47a3  push    r13
0x1800f47a5  push    r14
0x1800f47a7  push    r15
0x1800f47a9  lea     rbp, [rsp-1Fh]
0x1800f47ae  sub     rsp, 0C8h
0x1800f47b5  mov     r15, r8
0x1800f47b8  mov     r12, rdx
0x1800f47bb  mov     rbx, rcx
0x1800f47be  xor     r13d, r13d
0x1800f47c1  mov     [rbp+57h+var_C0], r13d
0x1800f47c5  mov     [rbp+57h+arg_18], r13d
0x1800f47c9  mov     [rbp+57h+var_B8], r13
0x1800f47cd  mov     [rbp+57h+var_98], r13
0x1800f47d1  mov     [rbp+57h+var_A0], r13
0x1800f47d5  mov     [rbp+57h+var_80], r13
0x1800f47d9  mov     [rbp+57h+String], r13
0x1800f47dd  mov     [rbp+57h+var_A8], r13
0x1800f47e1  mov     [rbp+57h+var_90], r13
0x1800f47e5  mov     [rsp+100h+var_D0], rcx
0x1800f47ea  lea     rax, aPszchallengeLs; "pszChallenge=%ls"
0x1800f47f1  mov     [rsp+100h+var_D8], rax
0x1800f47f6  lea     r14, aWlidsvcutilPar; "WlidsvcUtil::ParseChallengeToken"
0x1800f47fd  mov     [rsp+100h+var_E0], r14
0x1800f4802  lea     r9, [rbp+57h+arg_18]
0x1800f4806  mov     r8d, 1ACh
0x1800f480c  lea     rdx, aOnecoreuapDsEx_84; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800f4813  lea     rcx, [rbp+57h+var_60]
0x1800f4817  call    ??0?$CTraceFuncW@J@@QEAA@PEBDKAEAJ0PEBGZZ; CTraceFuncW<long>::CTraceFuncW<long>(char const *,ulong,long &,char const *,ushort const *,...)
0x1800f481c  nop
0x1800f481d  mov     word ptr [rbp+57h+pvarg], r13w
0x1800f4822  lea     rcx, [rbp+57h+pvarg]
0x1800f4826  call    ??4CComVariant@ATL@@QEAAAEAV01@PEBD@Z; ATL::CComVariant::operator=(char const *)
0x1800f482b  nop
0x1800f482c  lea     r8, [rbp+57h+var_B8]
0x1800f4830  lea     rdx, [rbp+57h+pvarg]
0x1800f4834  mov     rcx, rbx; unsigned __int16 *
0x1800f4837  call    ?CreateDOM@@YAJPEBGAEBVCComVariant@ATL@@AEAV?$CComPtr@UIXMLDOMDocument2@@@2@@Z; CreateDOM(ushort const *,ATL::CComVariant const &,ATL::CComPtr<IXMLDOMDocument2> &)
0x1800f483c  mov     ebx, eax
0x1800f483e  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800f4842  call    cs:__imp_VariantClear
0x1800f4848  mov     [rbp+57h+arg_18], ebx
0x1800f484b  test    ebx, ebx
0x1800f484d  jns     short loc_1800F4878
0x1800f484f  lea     rax, aHrCreatedomPsz; "hr = CreateDOM(pszChallenge, pDOMXml)"
0x1800f4856  mov     r9d, ebx; int
0x1800f4859  mov     r8d, 1AEh; unsigned int
0x1800f485f  mov     rdx, r14; char *
0x1800f4862  mov     [rsp+100h+var_E0], rax; char *
0x1800f4867  lea     rcx, aOnecoreuapDsEx_84; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800f486e  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x1800f4873  jmp     loc_1800F4AC1
0x1800f4878  mov     rdi, [rbp+57h+var_B8]
0x1800f487c  mov     rax, [rdi]
0x1800f487f  mov     rbx, [rax+128h]
0x1800f4886  lea     rdx, aWlidtokenType; "/WlidToken/Type"
0x1800f488d  lea     rcx, [rbp+57h+bstrString]; this
0x1800f4891  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x1800f4896  nop
0x1800f4897  mov     esi, 1
0x1800f489c  mov     [rbp+57h+var_C0], esi
0x1800f489f  lea     r8, [rbp+57h+var_A8]
0x1800f48a3  mov     rdx, [rax]
0x1800f48a6  mov     rcx, rdi
0x1800f48a9  mov     rax, rbx
0x1800f48ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f48b1  mov     [rbp+57h+arg_18], eax
0x1800f48b4  test    eax, eax
0x1800f48b6  js      short loc_1800F48C1
0x1800f48b8  cmp     [rbp+57h+var_A8], r13
0x1800f48bc  mov     bl, r13b
0x1800f48bf  jnz     short loc_1800F48C4
0x1800f48c1  mov     bl, sil
0x1800f48c4  mov     rcx, [rbp+57h+bstrString]; bstrString
0x1800f48c8  call    cs:__imp_SysFreeString
0x1800f48ce  test    bl, bl
0x1800f48d0  jz      short loc_1800F48EE
0x1800f48d2  mov     r9d, 80070057h
0x1800f48d8  mov     [rbp+57h+arg_18], r9d
0x1800f48dc  lea     rax, aSucceededHrPdo; "SUCCEEDED(hr = pDOMXml->selectSingleNod"...
0x1800f48e3  mov     r8d, 1B3h
0x1800f48e9  jmp     loc_1800F485F
0x1800f48ee  mov     rcx, [rbp+57h+var_A8]
0x1800f48f2  mov     rax, [rcx]
0x1800f48f5  lea     rdx, [rbp+57h+var_90]
0x1800f48f9  mov     rax, [rax+0D0h]
0x1800f4900  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f4905  mov     [rbp+57h+arg_18], eax
0x1800f4908  test    eax, eax
0x1800f490a  jns     short loc_1800F4928
0x1800f490c  mov     r9d, 80070057h
0x1800f4912  mov     [rbp+57h+arg_18], r9d
0x1800f4916  lea     rax, aSucceededHrPme; "SUCCEEDED(hr = pMessageTypeNode->get_te"...
0x1800f491d  mov     r8d, 1B5h
0x1800f4923  jmp     loc_1800F485F
0x1800f4928  lea     rdx, a1; "1"
0x1800f492f  lea     rcx, [rbp+57h+var_90]
0x1800f4933  call    ??8CComBSTR@ATL@@QEBA_NPEBG@Z; ATL::CComBSTR::operator==(ushort const *)
0x1800f4938  test    al, al
0x1800f493a  jnz     short loc_1800F4958
0x1800f493c  mov     r9d, 80070057h
0x1800f4942  mov     [rbp+57h+arg_18], r9d
0x1800f4946  lea     rax, aBstrtypeAuthzT; "bstrType == AUTHZ_TOKEN_TYPE_CHALLENGE"
0x1800f494d  mov     r8d, 1B7h
0x1800f4953  jmp     loc_1800F485F
0x1800f4958  mov     rdi, [rbp+57h+var_B8]
0x1800f495c  mov     rax, [rdi]
0x1800f495f  mov     rbx, [rax+128h]
0x1800f4966  lea     rdx, aWlidtokenChall; "/WlidToken/ChallengeToken/Policy"
0x1800f496d  lea     rcx, [rbp+57h+bstrString]; this
0x1800f4971  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x1800f4976  nop
0x1800f4977  mov     [rbp+57h+var_C0], 2
0x1800f497e  lea     r8, [rbp+57h+var_98]
0x1800f4982  mov     rdx, [rax]
0x1800f4985  mov     rcx, rdi
0x1800f4988  mov     rax, rbx
0x1800f498b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f4990  mov     [rbp+57h+arg_18], eax
0x1800f4993  test    eax, eax
0x1800f4995  js      short loc_1800F49A0
0x1800f4997  cmp     [rbp+57h+var_98], r13
0x1800f499b  mov     bl, r13b
0x1800f499e  jnz     short loc_1800F49A3
0x1800f49a0  mov     bl, sil
0x1800f49a3  mov     r14d, r13d
0x1800f49a6  mov     rcx, [rbp+57h+bstrString]; bstrString
0x1800f49aa  call    cs:__imp_SysFreeString
0x1800f49b0  test    bl, bl
0x1800f49b2  jz      short loc_1800F49D7
0x1800f49b4  lea     rax, aSucceededHrPdo_1; "SUCCEEDED(hr = pDOMXml->selectSingleNod"...
0x1800f49bb  mov     r8d, 1B9h
0x1800f49c1  mov     r9d, 80070057h
0x1800f49c7  mov     [rbp+57h+arg_18], r9d
0x1800f49cb  lea     rdx, aWlidsvcutilPar; "WlidsvcUtil::ParseChallengeToken"
0x1800f49d2  jmp     loc_1800F4862
0x1800f49d7  mov     rcx, [rbp+57h+var_98]
0x1800f49db  mov     rax, [rcx]
0x1800f49de  lea     rdx, [rbp+57h+var_80]
0x1800f49e2  mov     rax, [rax+0D0h]
0x1800f49e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f49ee  mov     [rbp+57h+arg_18], eax
0x1800f49f1  test    eax, eax
0x1800f49f3  jns     short loc_1800F4A04
0x1800f49f5  lea     rax, aSucceededHrPpo; "SUCCEEDED(hr = pPolicyNode->get_text(&b"...
0x1800f49fc  mov     r8d, 1BBh
0x1800f4a02  jmp     short loc_1800F49C1
0x1800f4a04  mov     rdi, [rbp+57h+var_B8]
0x1800f4a08  mov     rax, [rdi]
0x1800f4a0b  mov     rbx, [rax+128h]
0x1800f4a12  lea     rdx, aWlidtokenChall_0; "/WlidToken/ChallengeToken/Flags"
0x1800f4a19  lea     rcx, [rbp+57h+bstrString]; this
0x1800f4a1d  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x1800f4a22  nop
0x1800f4a23  or      r14d, 4
0x1800f4a27  mov     [rbp+57h+var_C0], r14d
0x1800f4a2b  lea     r8, [rbp+57h+var_A0]
0x1800f4a2f  mov     rdx, [rax]
0x1800f4a32  mov     rcx, rdi
0x1800f4a35  mov     rax, rbx
0x1800f4a38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f4a3d  mov     [rbp+57h+arg_18], eax
0x1800f4a40  test    eax, eax
0x1800f4a42  js      short loc_1800F4A4D
0x1800f4a44  cmp     [rbp+57h+var_A0], r13
0x1800f4a48  jz      short loc_1800F4A4D
0x1800f4a4a  mov     sil, r13b
0x1800f4a4d  mov     rcx, [rbp+57h+bstrString]; bstrString
0x1800f4a51  call    cs:__imp_SysFreeString
0x1800f4a57  test    sil, sil
0x1800f4a5a  jz      short loc_1800F4A6E
0x1800f4a5c  lea     rax, aSucceededHrPdo_0; "SUCCEEDED(hr = pDOMXml->selectSingleNod"...
0x1800f4a63  mov     r8d, 1BDh
0x1800f4a69  jmp     loc_1800F49C1
0x1800f4a6e  mov     rcx, [rbp+57h+var_A0]
0x1800f4a72  mov     rax, [rcx]
0x1800f4a75  lea     rdx, [rbp+57h+String]
0x1800f4a79  mov     rax, [rax+0D0h]
0x1800f4a80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f4a85  mov     [rbp+57h+arg_18], eax
0x1800f4a88  test    eax, eax
0x1800f4a8a  jns     short loc_1800F4A9E
0x1800f4a8c  lea     rax, aSucceededHrPfl; "SUCCEEDED(hr = pFlagsNode->get_text(&bs"...
0x1800f4a93  mov     r8d, 1BFh
0x1800f4a99  jmp     loc_1800F49C1
0x1800f4a9e  xor     edx, edx; EndPtr
0x1800f4aa0  lea     r8d, [rdx+0Ah]; Radix
0x1800f4aa4  mov     rcx, [rbp+57h+String]; String
0x1800f4aa8  call    cs:__imp_wcstoul
0x1800f4aae  mov     [r15], eax
0x1800f4ab1  mov     rdx, [rbp+57h+var_80]
0x1800f4ab5  mov     rcx, r12
0x1800f4ab8  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x1800f4abd  mov     [rbp+57h+arg_18], r13d
0x1800f4ac1  mov     ebx, [rbp+57h+arg_18]
0x1800f4ac4  lea     rcx, [rbp+57h+var_60]
0x1800f4ac8  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x1800f4acd  nop
0x1800f4ace  mov     rcx, [rbp+57h+var_90]; bstrString
0x1800f4ad2  call    cs:__imp_SysFreeString
0x1800f4ad8  nop
0x1800f4ad9  lea     rcx, [rbp+57h+var_A8]
0x1800f4add  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x1800f4ae2  nop
0x1800f4ae3  mov     rcx, [rbp+57h+String]; bstrString
0x1800f4ae7  call    cs:__imp_SysFreeString
0x1800f4aed  nop
0x1800f4aee  mov     rcx, [rbp+57h+var_80]; bstrString
0x1800f4af2  call    cs:__imp_SysFreeString
0x1800f4af8  nop
0x1800f4af9  lea     rcx, [rbp+57h+var_A0]
0x1800f4afd  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x1800f4b02  nop
0x1800f4b03  lea     rcx, [rbp+57h+var_98]
0x1800f4b07  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x1800f4b0c  nop
0x1800f4b0d  lea     rcx, [rbp+57h+var_B8]
0x1800f4b11  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x1800f4b16  mov     eax, ebx
0x1800f4b18  add     rsp, 0C8h
0x1800f4b1f  pop     r15
0x1800f4b21  pop     r14
0x1800f4b23  pop     r13
0x1800f4b25  pop     r12
0x1800f4b27  pop     rdi
0x1800f4b28  pop     rsi
0x1800f4b29  pop     rbx
0x1800f4b2a  pop     rbp
0x1800f4b2b  retn
```
