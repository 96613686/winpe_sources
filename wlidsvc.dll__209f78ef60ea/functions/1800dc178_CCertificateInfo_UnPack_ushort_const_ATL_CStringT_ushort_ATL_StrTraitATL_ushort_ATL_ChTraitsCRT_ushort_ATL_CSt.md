# CCertificateInfo::UnPack(ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ulong &,ATL::CTime &)

- ea: `0x1800dc178`
- end: `0x1800dc726`
- name: `?UnPack@CCertificateInfo@@KAJPEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@1AEAKAEAVCTime@3@@Z`
- size: `1454`
- prototype: `__int64 __usercall@<rax>(unsigned __int16 *@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800db798`

## callees

- `0x18000c050`
- `0x18000ed04`
- `0x1800151c4`
- `0x180015860`
- `0x180019690`
- `0x180019780`
- `0x18001a9c0`
- `0x18001ad00`
- `0x180021b28`
- `0x180021bbc`
- `0x1800396e8`
- `0x180039ee8`
- `0x1800406a8`
- `0x180044598`
- `0x1800838dc`
- `0x1800dc178`
- `0x180128010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1800dc567`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1800dc567`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800dc283`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800dc283`
- `OLEAUT32!__imp_SysFreeString` at `0x1800dc2ee`
- `OLEAUT32!__imp_SysFreeString` at `0x1800dc3bf`
- `OLEAUT32!__imp_SysFreeString` at `0x1800dc40e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800dc497`
- `OLEAUT32!__imp_SysFreeString` at `0x1800dc520`
- `OLEAUT32!__imp_SysFreeString` at `0x1800dc5ab`
- `OLEAUT32!__imp_SysFreeString` at `0x1800dc6d7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800dc2ee`
- `OLEAUT32!__imp_SysFreeString` at `0x1800dc3bf`
- `OLEAUT32!__imp_SysFreeString` at `0x1800dc40e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800dc497`
- `OLEAUT32!__imp_SysFreeString` at `0x1800dc520`
- `OLEAUT32!__imp_SysFreeString` at `0x1800dc5ab`
- `OLEAUT32!__imp_SysFreeString` at `0x1800dc6d7`
- `OLEAUT32!__imp_SysStringLen` at `0x1800dc442`
- `OLEAUT32!__imp_SysStringLen` at `0x1800dc4cb`
- `OLEAUT32!__imp_SysStringLen` at `0x1800dc554`
- `OLEAUT32!__imp_SysStringLen` at `0x1800dc5db`
- `OLEAUT32!__imp_SysStringLen` at `0x1800dc442`
- `OLEAUT32!__imp_SysStringLen` at `0x1800dc4cb`
- `OLEAUT32!__imp_SysStringLen` at `0x1800dc554`
- `OLEAUT32!__imp_SysStringLen` at `0x1800dc5db`

## string_xrefs

- `0x1800dc1f6`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\singleidentity.cpp`
- `0x1800dc314`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\singleidentity.cpp`
- `0x1800dc397`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\singleidentity.cpp`
- `0x1800dc6a9`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\singleidentity.cpp`
- `0x1800dc291`: `hr = pDOMXml.CoCreateInstance(CLSID_DOMDocument60)`
- `0x1800dc38a`: `XML load for text failed at %d: %ls.`
- `0x1800dc62a`: `Could not read node. HR=0x%x.`
- `0x1800dc64c`: `Could not read node. HR=0x%x.`
- `0x1800dc66e`: `Could not read node. HR=0x%x.`
- `0x1800dc689`: `Could not read node. HR=0x%x.`
- `0x1800dc69e`: `Token node not found in certificate info xml. 0x%x.`
- `0x1800dc2f8`: `hr = pDOMXml->loadXML(CComBSTR(wstrCertInfo), &bParsedOK)`
- `0x1800dc639`: `Expire time node not found in certificate info xml. 0x%x.`
- `0x1800dc65b`: `KeyGenFlags node not found in certificate info xml. 0x%x.`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall CCertificateInfo::UnPack(unsigned __int16 *a1, __int64 a2, __int64 a3, _DWORD *a4, __int64 a5)
{
  unsigned __int8 v9; // dl
  PPTraceStatus *v10; // rcx
  char v11; // cl
  const unsigned __int16 *String; // rax
  HRESULT v13; // eax
  int v14; // r9d
  unsigned int v15; // r8d
  LPVOID v16; // rdi
  __int64 (__fastcall *v17)(LPVOID, _QWORD, __int16 *); // rbx
  ATL::CComBSTR *v18; // rax
  int v19; // ebx
  int v20; // eax
  int v21; // eax
  const unsigned __int16 *v22; // r9
  unsigned int v23; // r8d
  unsigned int v24; // ebx
  LPVOID *ppv; // [rsp+20h] [rbp-A1h]
  LPVOID *ppva; // [rsp+20h] [rbp-A1h]
  const char *ppvb; // [rsp+20h] [rbp-A1h]
  int v29; // [rsp+30h] [rbp-91h] BYREF
  BSTR pbstr; // [rsp+38h] [rbp-89h] BYREF
  LPVOID v31; // [rsp+40h] [rbp-81h] BYREF
  int v32; // [rsp+48h] [rbp-79h] BYREF
  BSTR bstrString; // [rsp+50h] [rbp-71h] BYREF
  __int64 v34; // [rsp+58h] [rbp-69h] BYREF
  __int64 v35; // [rsp+60h] [rbp-61h] BYREF
  __int64 v36; // [rsp+68h] [rbp-59h] BYREF
  __int64 v37; // [rsp+70h] [rbp-51h] BYREF
  __int64 v38; // [rsp+78h] [rbp-49h] BYREF
  __int64 v39; // [rsp+80h] [rbp-41h] BYREF
  _QWORD v40[3]; // [rsp+88h] [rbp-39h] BYREF
  char v41; // [rsp+A0h] [rbp-21h]
  _QWORD v42[13]; // [rsp+A8h] [rbp-19h] BYREF
  __int16 v43; // [rsp+120h] [rbp+5Fh] BYREF

  v29 = 0;
  v31 = 0;
  v38 = 0;
  v37 = 0;
  v36 = 0;
  v35 = 0;
  pbstr = 0;
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v39);
  v43 = 0;
  v42[0] = "CCertificateInfo::UnPack";
  v42[1] = &v29;
  v42[2] = 0;
  v42[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\singleidentity.cpp",
    "CCertificateInfo::UnPack",
    (const char *)0x14BF,
    0,
    (const unsigned __int16 *)ppv);
  if ( !PPTraceShouldRedact() || (LOBYTE(v10) = 1, !PPTraceStatus::TraceOnFlag(v10, v9)) )
    v11 = 0;
  v40[0] = &PPRedactedStringW::`vftable';
  v40[1] = a1;
  v40[2] = 0;
  v41 = v11;
  String = PPRedactedStringW::GetString((PPRedactedStringW *)v40);
  TracePrintW(
    5u,
    "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\singleidentity.cpp",
    0x14C0u,
    L"wstrCertInfo %ls",
    String);
  PPRedactedStringW::~PPRedactedStringW((PPRedactedStringW *)v40);
  v13 = CoCreateInstance(&CLSID_DOMDocument60, 0, 0x17u, &GUID_2933bf95_7b36_11d2_b20e_00c04f983e60, &v31);
  v29 = v13;
  if ( v13 < 0 )
  {
    ppvb = "hr = pDOMXml.CoCreateInstance(CLSID_DOMDocument60)";
    v14 = v13;
    v15 = 5314;
LABEL_6:
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\singleidentity.cpp",
      "CCertificateInfo::UnPack",
      v15,
      v14,
      ppvb);
    goto LABEL_45;
  }
  v16 = v31;
  v17 = *(__int64 (__fastcall **)(LPVOID, _QWORD, __int16 *))(*(_QWORD *)v31 + 520LL);
  v18 = ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, a1);
  v19 = v17(v16, *(_QWORD *)v18, &v43);
  v29 = v19;
  SysFreeString(bstrString);
  if ( v19 < 0 )
  {
    ppvb = "hr = pDOMXml->loadXML(CComBSTR(wstrCertInfo), &bParsedOK)";
    v14 = v19;
    v15 = 5316;
    goto LABEL_6;
  }
  if ( v43 == -1 )
  {
    v20 = (*(__int64 (__fastcall **)(LPVOID, BSTR, __int64 *))(*(_QWORD *)v31 + 296LL))(v31, k_bstrCertTokenPath, &v36);
    v29 = v20;
    if ( v20 >= 0 && v36 )
    {
      SysFreeString(pbstr);
      pbstr = 0;
      v20 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v36 + 208LL))(v36, &pbstr);
      v29 = v20;
      if ( v20 >= 0 )
      {
        if ( SysStringLen(pbstr) )
        {
          ATL::CSimpleStringT<unsigned short,0>::SetString(a2, pbstr);
          v20 = (*(__int64 (__fastcall **)(LPVOID, BSTR, __int64 *))(*(_QWORD *)v31 + 296LL))(
                  v31,
                  k_bstrCertKeypairPath,
                  &v38);
          v29 = v20;
          if ( v20 >= 0 && v38 )
          {
            SysFreeString(pbstr);
            pbstr = 0;
            v20 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v38 + 208LL))(v38, &pbstr);
            v29 = v20;
            if ( v20 >= 0 )
            {
              if ( SysStringLen(pbstr) )
              {
                ATL::CSimpleStringT<unsigned short,0>::SetString(a3, pbstr);
                v20 = (*(__int64 (__fastcall **)(LPVOID, BSTR, __int64 *))(*(_QWORD *)v31 + 296LL))(
                        v31,
                        k_bstrCertKeyGenFlagsPath,
                        &v37);
                v29 = v20;
                if ( v20 < 0 || !v37 )
                {
                  v22 = L"KeyGenFlags node not found in certificate info xml. 0x%x.";
                  v23 = 5373;
                  goto LABEL_44;
                }
                SysFreeString(pbstr);
                pbstr = 0;
                v20 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v37 + 208LL))(v37, &pbstr);
                v29 = v20;
                if ( v20 >= 0 )
                {
                  if ( SysStringLen(pbstr) )
                  {
                    *a4 = _o__wtoi(pbstr);
                    v20 = (*(__int64 (__fastcall **)(LPVOID, BSTR, __int64 *))(*(_QWORD *)v31 + 296LL))(
                            v31,
                            k_bstrCertExpiredTimePath,
                            &v35);
                    v29 = v20;
                    if ( v20 >= 0 && v35 )
                    {
                      SysFreeString(pbstr);
                      pbstr = 0;
                      v20 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v35 + 208LL))(v35, &pbstr);
                      v29 = v20;
                      if ( v20 >= 0 )
                      {
                        if ( SysStringLen(pbstr) )
                        {
                          ATL::CSimpleStringT<unsigned short,0>::SetString(&v39, pbstr);
                          v21 = CTokenInfo::String2Time(&v39, a5);
                          v29 = v21;
                          if ( v21 >= 0 )
                            goto LABEL_45;
                          ppvb = "hr = String2Time(wstrExpireTime, ctExpireTime)";
                          v14 = v21;
                          v15 = 5402;
                          goto LABEL_6;
                        }
                        v20 = v29;
                      }
                      v22 = L"Could not read node. HR=0x%x.";
                      v23 = 5398;
                    }
                    else
                    {
                      v22 = L"Expire time node not found in certificate info xml. 0x%x.";
                      v23 = 5390;
                    }
LABEL_44:
                    LODWORD(ppva) = v20;
                    TracePrintW(
                      2u,
                      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\singleidentity.cpp",
                      v23,
                      v22,
                      ppva);
                    goto LABEL_45;
                  }
                  v20 = v29;
                }
                v22 = L"Could not read node. HR=0x%x.";
                v23 = 5381;
                goto LABEL_44;
              }
              v20 = v29;
            }
            v22 = L"Could not read node. HR=0x%x.";
            v23 = 5364;
            goto LABEL_44;
          }
          v23 = 5356;
LABEL_43:
          v22 = L"Token node not found in certificate info xml. 0x%x.";
          goto LABEL_44;
        }
        v20 = v29;
      }
      v22 = L"Could not read node. HR=0x%x.";
      v23 = 5347;
      goto LABEL_44;
    }
    v23 = 5340;
    goto LABEL_43;
  }
  v34 = 0;
  bstrString = 0;
  v32 = -1;
  (*(void (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)v31 + 480LL))(v31, &v34);
  if ( v34 )
  {
    (*(void (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v34 + 72LL))(v34, &bstrString);
    (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v34 + 88LL))(v34, &v32);
    LODWORD(ppva) = v32;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\singleidentity.cpp",
      0x14D1u,
      L"XML load for text failed at %d: %ls.",
      ppva,
      bstrString);
  }
  v29 = -2147186552;
  ATL::CComPtrBase<IXMLDOMNodeList>::Release(&v31);
  SysFreeString(bstrString);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v34);
LABEL_45:
  v24 = v29;
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v42);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v39);
  SysFreeString(pbstr);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v35);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v36);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v37);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v38);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>((__int64 *)&v31);
  return v24;
}

```

## disassembly

```asm
0x1800dc178  push    rbp
0x1800dc17a  push    rbx
0x1800dc17b  push    rsi
0x1800dc17c  push    rdi
0x1800dc17d  push    r12
0x1800dc17f  push    r13
0x1800dc181  push    r14
0x1800dc183  push    r15
0x1800dc185  lea     rbp, [rsp-17h]
0x1800dc18a  sub     rsp, 0D8h
0x1800dc191  mov     r12, r9
0x1800dc194  mov     r15, r8
0x1800dc197  mov     r14, rdx
0x1800dc19a  mov     rsi, rcx
0x1800dc19d  xor     r13d, r13d
0x1800dc1a0  mov     [rsp+110h+var_E0], r13d
0x1800dc1a5  mov     [rsp+110h+var_D0], r13
0x1800dc1aa  mov     [rbp+4Fh+var_98], r13
0x1800dc1ae  mov     [rbp+4Fh+var_A0], r13
0x1800dc1b2  mov     [rbp+4Fh+var_A8], r13
0x1800dc1b6  mov     [rbp+4Fh+var_B0], r13
0x1800dc1ba  mov     [rsp+110h+pbstr], r13
0x1800dc1bf  lea     rcx, [rbp+4Fh+var_90]
0x1800dc1c3  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800dc1c8  nop
0x1800dc1c9  mov     [rbp+4Fh+arg_0], r13w
0x1800dc1ce  lea     rdi, aCcertificatein_6; "CCertificateInfo::UnPack"
0x1800dc1d5  mov     [rbp+4Fh+var_68], rdi
0x1800dc1d9  lea     rax, [rsp+110h+var_E0]
0x1800dc1de  mov     [rbp+4Fh+var_60], rax
0x1800dc1e2  mov     [rbp+4Fh+var_58], r13
0x1800dc1e6  mov     [rbp+4Fh+var_50], r13
0x1800dc1ea  xor     r9d, r9d; unsigned int
0x1800dc1ed  mov     r8d, 14BFh; char *
0x1800dc1f3  mov     rdx, rdi; char *
0x1800dc1f6  lea     rbx, aOnecoreuapDsEx_24; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800dc1fd  mov     rcx, rbx; this
0x1800dc200  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x1800dc205  nop
0x1800dc206  call    ?PPTraceShouldRedact@@YA_NXZ; PPTraceShouldRedact(void)
0x1800dc20b  test    al, al
0x1800dc20d  jz      short loc_1800DC21A
0x1800dc20f  mov     cl, 1; this
0x1800dc211  call    ?TraceOnFlag@PPTraceStatus@@YA_NE@Z; PPTraceStatus::TraceOnFlag(uchar)
0x1800dc216  test    al, al
0x1800dc218  jnz     short loc_1800DC21D
0x1800dc21a  mov     cl, r13b
0x1800dc21d  lea     rax, ??_7PPRedactedStringW@@6B@; const PPRedactedStringW::`vftable'
0x1800dc224  mov     [rbp+4Fh+var_88], rax
0x1800dc228  mov     [rbp+4Fh+var_80], rsi
0x1800dc22c  mov     [rbp+4Fh+var_78], r13
0x1800dc230  mov     [rbp+4Fh+var_70], cl
0x1800dc233  lea     rcx, [rbp+4Fh+var_88]; this
0x1800dc237  call    ?GetString@PPRedactedStringW@@QEAAPEBGXZ; PPRedactedStringW::GetString(void)
0x1800dc23c  mov     [rsp+110h+ppv], rax
0x1800dc241  lea     r9, aWstrcertinfoLs; "wstrCertInfo %ls"
0x1800dc248  mov     r8d, 14C0h; unsigned int
0x1800dc24e  mov     rdx, rbx; char *
0x1800dc251  mov     ecx, 5; unsigned __int8
0x1800dc256  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800dc25b  nop
0x1800dc25c  lea     rcx, [rbp+4Fh+var_88]; this
0x1800dc260  call    ??1PPRedactedStringW@@QEAA@XZ; PPRedactedStringW::~PPRedactedStringW(void)
0x1800dc265  lea     rax, [rsp+110h+var_D0]
0x1800dc26a  mov     [rsp+110h+ppv], rax; ppv
0x1800dc26f  lea     r9, _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60; riid
0x1800dc276  xor     edx, edx; pUnkOuter
0x1800dc278  lea     r8d, [rdx+17h]; dwClsContext
0x1800dc27c  lea     rcx, CLSID_DOMDocument60; rclsid
0x1800dc283  call    cs:__imp_CoCreateInstance
0x1800dc289  mov     [rsp+110h+var_E0], eax
0x1800dc28d  test    eax, eax
0x1800dc28f  jns     short loc_1800DC2B6
0x1800dc291  lea     r8, aHrPdomxmlCocre; "hr = pDOMXml.CoCreateInstance(CLSID_DOM"...
0x1800dc298  mov     [rsp+110h+ppv], r8; char *
0x1800dc29d  mov     r9d, eax; int
0x1800dc2a0  mov     r8d, 14C2h; unsigned int
0x1800dc2a6  mov     rdx, rdi; char *
0x1800dc2a9  mov     rcx, rbx; char *
0x1800dc2ac  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x1800dc2b1  jmp     loc_1800DC6BA
0x1800dc2b6  mov     rdi, [rsp+110h+var_D0]
0x1800dc2bb  mov     rax, [rdi]
0x1800dc2be  mov     rbx, [rax+208h]
0x1800dc2c5  mov     rdx, rsi; unsigned __int16 *
0x1800dc2c8  lea     rcx, [rbp+4Fh+bstrString]; this
0x1800dc2cc  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x1800dc2d1  nop
0x1800dc2d2  lea     r8, [rbp+4Fh+arg_0]
0x1800dc2d6  mov     rdx, [rax]
0x1800dc2d9  mov     rcx, rdi
0x1800dc2dc  mov     rax, rbx
0x1800dc2df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dc2e4  mov     ebx, eax
0x1800dc2e6  mov     [rsp+110h+var_E0], eax
0x1800dc2ea  mov     rcx, [rbp+4Fh+bstrString]; bstrString
0x1800dc2ee  call    cs:__imp_SysFreeString
0x1800dc2f4  test    ebx, ebx
0x1800dc2f6  jns     short loc_1800DC31D
0x1800dc2f8  lea     rax, aHrPdomxmlLoadx_0; "hr = pDOMXml->loadXML(CComBSTR(wstrCert"...
0x1800dc2ff  mov     [rsp+110h+ppv], rax
0x1800dc304  mov     r9d, ebx
0x1800dc307  mov     r8d, 14C4h
0x1800dc30d  lea     rdx, aCcertificatein_6; "CCertificateInfo::UnPack"
0x1800dc314  lea     rcx, aOnecoreuapDsEx_24; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800dc31b  jmp     short loc_1800DC2AC
0x1800dc31d  or      eax, 0FFFFFFFFh
0x1800dc320  cmp     ax, [rbp+4Fh+arg_0]
0x1800dc324  jz      loc_1800DC3D4
0x1800dc32a  mov     [rbp+4Fh+var_B8], r13
0x1800dc32e  mov     [rbp+4Fh+bstrString], r13
0x1800dc332  mov     [rbp+4Fh+var_C8], eax
0x1800dc335  mov     rcx, [rsp+110h+var_D0]
0x1800dc33a  mov     rax, [rcx]
0x1800dc33d  lea     rdx, [rbp+4Fh+var_B8]
0x1800dc341  mov     rax, [rax+1E0h]
0x1800dc348  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dc34d  mov     rcx, [rbp+4Fh+var_B8]
0x1800dc351  test    rcx, rcx
0x1800dc354  jz      short loc_1800DC3A8
0x1800dc356  mov     rax, [rcx]
0x1800dc359  lea     rdx, [rbp+4Fh+bstrString]
0x1800dc35d  mov     rax, [rax+48h]
0x1800dc361  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dc366  mov     rcx, [rbp+4Fh+var_B8]
0x1800dc36a  mov     rax, [rcx]
0x1800dc36d  lea     rdx, [rbp+4Fh+var_C8]
0x1800dc371  mov     rax, [rax+58h]
0x1800dc375  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dc37a  mov     rax, [rbp+4Fh+bstrString]
0x1800dc37e  mov     [rsp+110h+var_E8], rax
0x1800dc383  mov     eax, [rbp+4Fh+var_C8]
0x1800dc386  mov     dword ptr [rsp+110h+ppv], eax
0x1800dc38a  lea     r9, aXmlLoadForText; "XML load for text failed at %d: %ls."
0x1800dc391  mov     r8d, 14D1h; unsigned int
0x1800dc397  lea     rdx, aOnecoreuapDsEx_24; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800dc39e  mov     ecx, 2; unsigned __int8
0x1800dc3a3  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800dc3a8  mov     [rsp+110h+var_E0], 80048888h
0x1800dc3b0  lea     rcx, [rsp+110h+var_D0]
0x1800dc3b5  call    ?Release@?$CComPtrBase@UIXMLDOMNodeList@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IXMLDOMNodeList>::Release(void)
0x1800dc3ba  nop
0x1800dc3bb  mov     rcx, [rbp+4Fh+bstrString]; bstrString
0x1800dc3bf  call    cs:__imp_SysFreeString
0x1800dc3c5  nop
0x1800dc3c6  lea     rcx, [rbp+4Fh+var_B8]
0x1800dc3ca  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x1800dc3cf  jmp     loc_1800DC6BA
0x1800dc3d4  mov     rcx, [rsp+110h+var_D0]
0x1800dc3d9  mov     rax, [rcx]
0x1800dc3dc  lea     r8, [rbp+4Fh+var_A8]
0x1800dc3e0  mov     rdx, cs:?k_bstrCertTokenPath@@3VCComBSTR@ATL@@A; ATL::CComBSTR k_bstrCertTokenPath
0x1800dc3e7  mov     rax, [rax+128h]
0x1800dc3ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dc3f3  mov     [rsp+110h+var_E0], eax
0x1800dc3f7  test    eax, eax
0x1800dc3f9  js      loc_1800DC698
0x1800dc3ff  cmp     [rbp+4Fh+var_A8], r13
0x1800dc403  jz      loc_1800DC698
0x1800dc409  mov     rcx, [rsp+110h+pbstr]; bstrString
0x1800dc40e  call    cs:__imp_SysFreeString
0x1800dc414  mov     [rsp+110h+pbstr], r13
0x1800dc419  mov     rcx, [rbp+4Fh+var_A8]
0x1800dc41d  mov     rax, [rcx]
0x1800dc420  lea     rdx, [rsp+110h+pbstr]
0x1800dc425  mov     rax, [rax+0D0h]
0x1800dc42c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dc431  mov     [rsp+110h+var_E0], eax
0x1800dc435  test    eax, eax
0x1800dc437  js      loc_1800DC689
0x1800dc43d  mov     rcx, [rsp+110h+pbstr]; pbstr
0x1800dc442  call    cs:__imp_SysStringLen
0x1800dc448  test    eax, eax
0x1800dc44a  jz      loc_1800DC685
0x1800dc450  mov     rdx, [rsp+110h+pbstr]
0x1800dc455  mov     rcx, r14
0x1800dc458  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x1800dc45d  mov     rcx, [rsp+110h+var_D0]
0x1800dc462  mov     rax, [rcx]
0x1800dc465  lea     r8, [rbp+4Fh+var_98]
0x1800dc469  mov     rdx, cs:?k_bstrCertKeypairPath@@3VCComBSTR@ATL@@A; ATL::CComBSTR k_bstrCertKeypairPath
0x1800dc470  mov     rax, [rax+128h]
0x1800dc477  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dc47c  mov     [rsp+110h+var_E0], eax
0x1800dc480  test    eax, eax
0x1800dc482  js      loc_1800DC67D
0x1800dc488  cmp     [rbp+4Fh+var_98], r13
0x1800dc48c  jz      loc_1800DC67D
0x1800dc492  mov     rcx, [rsp+110h+pbstr]; bstrString
0x1800dc497  call    cs:__imp_SysFreeString
0x1800dc49d  mov     [rsp+110h+pbstr], r13
0x1800dc4a2  mov     rcx, [rbp+4Fh+var_98]
0x1800dc4a6  mov     rax, [rcx]
0x1800dc4a9  lea     rdx, [rsp+110h+pbstr]
0x1800dc4ae  mov     rax, [rax+0D0h]
0x1800dc4b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dc4ba  mov     [rsp+110h+var_E0], eax
0x1800dc4be  test    eax, eax
0x1800dc4c0  js      loc_1800DC66E
0x1800dc4c6  mov     rcx, [rsp+110h+pbstr]; pbstr
0x1800dc4cb  call    cs:__imp_SysStringLen
0x1800dc4d1  test    eax, eax
0x1800dc4d3  jz      loc_1800DC66A
0x1800dc4d9  mov     rdx, [rsp+110h+pbstr]
0x1800dc4de  mov     rcx, r15
0x1800dc4e1  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x1800dc4e6  mov     rcx, [rsp+110h+var_D0]
0x1800dc4eb  mov     rax, [rcx]
0x1800dc4ee  lea     r8, [rbp+4Fh+var_A0]
0x1800dc4f2  mov     rdx, cs:?k_bstrCertKeyGenFlagsPath@@3VCComBSTR@ATL@@A; ATL::CComBSTR k_bstrCertKeyGenFlagsPath
0x1800dc4f9  mov     rax, [rax+128h]
0x1800dc500  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dc505  mov     [rsp+110h+var_E0], eax
0x1800dc509  test    eax, eax
0x1800dc50b  js      loc_1800DC65B
0x1800dc511  cmp     [rbp+4Fh+var_A0], r13
0x1800dc515  jz      loc_1800DC65B
0x1800dc51b  mov     rcx, [rsp+110h+pbstr]; bstrString
0x1800dc520  call    cs:__imp_SysFreeString
0x1800dc526  mov     [rsp+110h+pbstr], r13
0x1800dc52b  mov     rcx, [rbp+4Fh+var_A0]
0x1800dc52f  mov     rax, [rcx]
0x1800dc532  lea     rdx, [rsp+110h+pbstr]
0x1800dc537  mov     rax, [rax+0D0h]
0x1800dc53e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dc543  mov     [rsp+110h+var_E0], eax
0x1800dc547  test    eax, eax
0x1800dc549  js      loc_1800DC64C
0x1800dc54f  mov     rcx, [rsp+110h+pbstr]; pbstr
0x1800dc554  call    cs:__imp_SysStringLen
0x1800dc55a  test    eax, eax
0x1800dc55c  jz      loc_1800DC648
0x1800dc562  mov     rcx, [rsp+110h+pbstr]
0x1800dc567  call    cs:__imp__o__wtoi
0x1800dc56d  mov     [r12], eax
0x1800dc571  mov     rcx, [rsp+110h+var_D0]
0x1800dc576  mov     rax, [rcx]
0x1800dc579  lea     r8, [rbp+4Fh+var_B0]
0x1800dc57d  mov     rdx, cs:?k_bstrCertExpiredTimePath@@3VCComBSTR@ATL@@A; ATL::CComBSTR k_bstrCertExpiredTimePath
0x1800dc584  mov     rax, [rax+128h]
0x1800dc58b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dc590  mov     [rsp+110h+var_E0], eax
0x1800dc594  test    eax, eax
0x1800dc596  js      loc_1800DC639
0x1800dc59c  cmp     [rbp+4Fh+var_B0], r13
0x1800dc5a0  jz      loc_1800DC639
0x1800dc5a6  mov     rcx, [rsp+110h+pbstr]; bstrString
0x1800dc5ab  call    cs:__imp_SysFreeString
0x1800dc5b1  mov     [rsp+110h+pbstr], r13
0x1800dc5b6  mov     rcx, [rbp+4Fh+var_B0]
0x1800dc5ba  mov     rax, [rcx]
0x1800dc5bd  lea     rdx, [rsp+110h+pbstr]
0x1800dc5c2  mov     rax, [rax+0D0h]
0x1800dc5c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dc5ce  mov     [rsp+110h+var_E0], eax
0x1800dc5d2  test    eax, eax
0x1800dc5d4  js      short loc_1800DC62A
0x1800dc5d6  mov     rcx, [rsp+110h+pbstr]; pbstr
0x1800dc5db  call    cs:__imp_SysStringLen
0x1800dc5e1  test    eax, eax
0x1800dc5e3  jz      short loc_1800DC626
0x1800dc5e5  mov     rdx, [rsp+110h+pbstr]
0x1800dc5ea  lea     rcx, [rbp+4Fh+var_90]
0x1800dc5ee  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x1800dc5f3  mov     rdx, [rbp+4Fh+arg_20]
0x1800dc5f7  lea     rcx, [rbp+4Fh+var_90]
0x1800dc5fb  call    ?String2Time@CTokenInfo@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAVCTime@3@@Z; CTokenInfo::String2Time(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CTime &)
0x1800dc600  mov     [rsp+110h+var_E0], eax
0x1800dc604  test    eax, eax
0x1800dc606  jns     loc_1800DC6BA
0x1800dc60c  lea     rcx, aHrString2timeW; "hr = String2Time(wstrExpireTime, ctExpi"...
0x1800dc613  mov     [rsp+110h+ppv], rcx
0x1800dc618  mov     r9d, eax
0x1800dc61b  mov     r8d, 151Ah
0x1800dc621  jmp     loc_1800DC30D
0x1800dc626  mov     eax, [rsp+110h+var_E0]
0x1800dc62a  lea     r9, aCouldNotReadNo; "Could not read node. HR=0x%x."
0x1800dc631  mov     r8d, 1516h
0x1800dc637  jmp     short loc_1800DC6A5
0x1800dc639  lea     r9, aExpireTimeNode_0; "Expire time node not found in certifica"...
0x1800dc640  mov     r8d, 150Eh
0x1800dc646  jmp     short loc_1800DC6A5
0x1800dc648  mov     eax, [rsp+110h+var_E0]
0x1800dc64c  lea     r9, aCouldNotReadNo; "Could not read node. HR=0x%x."
0x1800dc653  mov     r8d, 1505h
0x1800dc659  jmp     short loc_1800DC6A5
0x1800dc65b  lea     r9, aKeygenflagsNod; "KeyGenFlags node not found in certifica"...
0x1800dc662  mov     r8d, 14FDh
0x1800dc668  jmp     short loc_1800DC6A5
0x1800dc66a  mov     eax, [rsp+110h+var_E0]
0x1800dc66e  lea     r9, aCouldNotReadNo; "Could not read node. HR=0x%x."
0x1800dc675  mov     r8d, 14F4h
0x1800dc67b  jmp     short loc_1800DC6A5
0x1800dc67d  mov     r8d, 14ECh
0x1800dc683  jmp     short loc_1800DC69E
0x1800dc685  mov     eax, [rsp+110h+var_E0]
0x1800dc689  lea     r9, aCouldNotReadNo; "Could not read node. HR=0x%x."
0x1800dc690  mov     r8d, 14E3h
0x1800dc696  jmp     short loc_1800DC6A5
0x1800dc698  mov     r8d, 14DCh; unsigned int
  ... truncated ...
```
