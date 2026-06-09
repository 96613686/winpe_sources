# CKeyCache::ProcessKeyXml(IServiceExecutionContext *,IXMLDOMNode *)

- ea: `0x180014a20`
- end: `0x180015132`
- name: `?ProcessKeyXml@CKeyCache@@QEAAJPEAVIServiceExecutionContext@@PEAUIXMLDOMNode@@@Z`
- size: `1810`
- prototype: `__int64 __fastcall(CKeyCache *__hidden this, struct IServiceExecutionContext *, struct IXMLDOMNode *)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18002b068`
- `0x180079174`

## callees

- `0x18000c050`
- `0x18000d12c`
- `0x180014a20`
- `0x1800151c4`
- `0x180015fb0`
- `0x1800171f0`
- `0x18001a9c0`
- `0x18001ad00`
- `0x1800406a8`
- `0x18007e2fc`
- `0x180108d20`
- `0x180128010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__mbscmp` at `0x180014d77`
- `api-ms-win-crt-private-l1-1-0!_o__mbscmp` at `0x180014db3`
- `api-ms-win-crt-private-l1-1-0!_o__mbscmp` at `0x180014d77`
- `api-ms-win-crt-private-l1-1-0!_o__mbscmp` at `0x180014db3`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001507f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800150e3`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001507f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800150e3`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180014afa`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180014b04`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180014afa`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180014b04`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015088`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800150ec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015088`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800150ec`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180014b1b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180014b1b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014af0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014af0`
- `OLEAUT32!__imp_SysFreeString` at `0x180014d4a`
- `OLEAUT32!__imp_SysFreeString` at `0x180014df1`
- `OLEAUT32!__imp_SysFreeString` at `0x180014e20`
- `OLEAUT32!__imp_SysFreeString` at `0x180014f9f`
- `OLEAUT32!__imp_SysFreeString` at `0x180014d4a`
- `OLEAUT32!__imp_SysFreeString` at `0x180014df1`
- `OLEAUT32!__imp_SysFreeString` at `0x180014e20`
- `OLEAUT32!__imp_SysFreeString` at `0x180014f9f`

## string_xrefs

- `0x180014a7d`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\keycache.cpp`
- `0x180014ac6`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\keycache.cpp`
- `0x180014f8e`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\keycache.cpp`
- `0x18001500a`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\keycache.cpp`
- `0x1800150b0`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\keycache.cpp`
- `0x180014a56`: `CKeyCache::ProcessKeyXml`
- `0x180014f87`: `CKeyCache::ProcessKeyXml`
- `0x180015003`: `CKeyCache::ProcessKeyXml`
- `0x1800150a9`: `CKeyCache::ProcessKeyXml`
- `0x180014aae`: `hr = pXMLNode->selectNodes(c_bstrKeyPurpose, &pPurposeList)`
- `0x180014fee`: `hr = UpdateKeyCache(pExecutionContext, strPurpose, strVersion, strMaterial)`

## pseudocode

```c
// Hidden C++ exception states: #wind=23
__int64 __fastcall CKeyCache::ProcessKeyXml(
        CKeyCache *this,
        struct IServiceExecutionContext *a2,
        struct IXMLDOMNode *a3)
{
  int v6; // eax
  const unsigned __int8 *v7; // rbx
  int v8; // eax
  int v9; // eax
  const unsigned __int8 *v10; // rbx
  ATL::CStringData *v11; // rsi
  __int64 v12; // rcx
  unsigned __int8 *v13; // rbx
  ATL::CStringData *v14; // rsi
  int updated; // eax
  ATL::CStringData *v16; // rbx
  int v17; // eax
  char *v18; // rbx
  unsigned __int8 **v19; // rcx
  unsigned int v20; // r8d
  const char *v21; // rcx
  const char *v22; // rcx
  unsigned int v23; // r8d
  const char *v24; // rcx
  unsigned int v25; // r8d
  unsigned int v26; // ebx
  char *v28; // [rsp+20h] [rbp-69h]
  __int64 v29; // [rsp+30h] [rbp-59h] BYREF
  __int64 v30; // [rsp+38h] [rbp-51h] BYREF
  const unsigned __int8 *v31; // [rsp+40h] [rbp-49h] BYREF
  __int64 v32; // [rsp+48h] [rbp-41h] BYREF
  __int64 v33; // [rsp+50h] [rbp-39h] BYREF
  BSTR bstrString; // [rsp+58h] [rbp-31h] BYREF
  char *v35; // [rsp+60h] [rbp-29h] BYREF
  unsigned __int8 *v36; // [rsp+68h] [rbp-21h] BYREF
  char *v37; // [rsp+70h] [rbp-19h] BYREF
  __int64 v38; // [rsp+78h] [rbp-11h] BYREF
  _QWORD v39[12]; // [rsp+80h] [rbp-9h] BYREF
  int v40; // [rsp+100h] [rbp+77h] BYREF
  __int64 v41; // [rsp+108h] [rbp+7Fh] BYREF

  v40 = 0;
  ATL::CComPtr<IXMLDOMDocument2>::CComPtr<IXMLDOMDocument2>(&v38);
  v39[0] = "CKeyCache::ProcessKeyXml";
  v39[1] = &v40;
  v39[2] = 0;
  v39[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\keycache.cpp",
    "CKeyCache::ProcessKeyXml",
    (const char *)0x38C,
    0,
    (const unsigned __int16 *)v28);
  v6 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, BSTR, __int64 *))a3->lpVtbl->selectNodes)(
         a3,
         c_bstrKeyPurpose,
         &v38);
  v40 = v6;
  if ( v6 < 0 )
  {
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\keycache.cpp",
      "CKeyCache::ProcessKeyXml",
      0x391u,
      v6,
      "hr = pXMLNode->selectNodes(c_bstrKeyPurpose, &pPurposeList)");
    goto LABEL_78;
  }
  if ( v38 )
  {
    v39[4] = (char *)this + 96;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 128));
    ResetEvent(*((HANDLE *)this + 15));
    ResetEvent(*((HANDLE *)this + 14));
    _InterlockedIncrement((volatile signed __int32 *)this + 26);
    if ( *((int *)this + 27) > 0 )
      WaitForSingleObject(*((HANDLE *)this + 14), 0xFFFFFFFF);
    while ( 1 )
    {
      v7 = (const unsigned __int8 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
      v31 = v7;
      v29 = 0;
      v41 = 0;
      v8 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v38 + 72LL))(v38, &v41);
      v40 = v8;
      if ( v8 < 0 )
        break;
      if ( !v41 )
      {
        if ( v29 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
        ATL::CStringData::Release((ATL::CStringData *)(v7 - 24));
        _InterlockedDecrement((volatile signed __int32 *)this + 26);
        SetEvent(*((HANDLE *)this + 15));
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 128));
        v40 = 0;
        goto LABEL_78;
      }
      v9 = WlidsvcUtil::XMLGetNodeAttribute(&c_bstrKeyNameAttr, &v41, &v31);
      v10 = v31;
      if ( v9 >= 0 )
      {
        v11 = (ATL::CStringData *)(v31 - 24);
        if ( *((_DWORD *)v31 - 4) )
        {
          v8 = (*(__int64 (__fastcall **)(__int64, BSTR, __int64 *))(*(_QWORD *)v41 + 288LL))(v41, c_bstrKeyData, &v29);
          v40 = v8;
          if ( v8 >= 0 )
          {
            v12 = v29;
            if ( !v29 )
            {
              if ( v41 )
              {
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
                v12 = v29;
              }
              if ( v12 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
              goto LABEL_60;
            }
LABEL_17:
            v33 = 0;
            v30 = 0;
            v13 = (unsigned __int8 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
            v36 = v13;
            v14 = (ATL::CStringData *)((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr);
            v35 = (char *)v14 + 24;
            updated = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v29 + 72LL))(v29, &v33);
            v40 = updated;
            if ( updated < 0 )
            {
              v22 = "hr = pKeyList->nextNode(&pKey)";
              v23 = 965;
LABEL_67:
              Telemetry::IfFailExit(
                "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\keycache.cpp",
                "CKeyCache::ProcessKeyXml",
                v23,
                updated,
                v22);
LABEL_64:
              ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v35);
              ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v36);
              ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v30);
              ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v33);
LABEL_77:
              ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v41);
              ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v29);
              ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v31);
              _InterlockedDecrement((volatile signed __int32 *)this + 26);
              SetEvent(*((HANDLE *)this + 15));
              LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 128));
              goto LABEL_78;
            }
            if ( !v33 )
            {
              ATL::CStringData::Release(v14);
              ATL::CStringData::Release((ATL::CStringData *)(v13 - 24));
              if ( v30 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
              if ( v33 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
              if ( v41 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
              if ( v29 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
              v11 = (ATL::CStringData *)(v31 - 24);
              goto LABEL_60;
            }
            updated = (*(__int64 (__fastcall **)(__int64, BSTR, __int64 *))(*(_QWORD *)v33 + 288LL))(
                        v33,
                        c_bstrKeyProperty,
                        &v30);
            v40 = updated;
            if ( updated < 0 )
            {
              v22 = "hr = pKey->selectNodes(c_bstrKeyProperty, &pKeyPropList)";
              v23 = 973;
              goto LABEL_67;
            }
            if ( !v30 )
            {
              ATL::CStringData::Release(v14);
              ATL::CStringData::Release((ATL::CStringData *)(v13 - 24));
              if ( v30 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
              goto LABEL_43;
            }
            while ( 1 )
            {
              while ( 1 )
              {
                v16 = (ATL::CStringData *)((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr);
                v37 = (char *)v16 + 24;
                v32 = 0;
                bstrString = 0;
                v17 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v30 + 72LL))(v30, &v32);
                v40 = v17;
                if ( v17 < 0 )
                {
                  v21 = "hr = pKeyPropList->nextNode(&pKeyProp)";
                  v20 = 986;
                  goto LABEL_63;
                }
                if ( !v32 )
                {
                  SysFreeString(bstrString);
                  if ( v32 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
                  ATL::CStringData::Release(v16);
                  updated = CKeyCache::UpdateKeyCache((__int64)this, (__int64)a2, &v31, &v36, &v35);
                  v40 = updated;
                  if ( updated < 0 )
                  {
                    v22 = "hr = UpdateKeyCache(pExecutionContext, strPurpose, strVersion, strMaterial)";
                    v23 = 1011;
                    goto LABEL_67;
                  }
                  ATL::CStringData::Release((ATL::CStringData *)(v35 - 24));
                  ATL::CStringData::Release((ATL::CStringData *)(v36 - 24));
                  if ( v30 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
LABEL_43:
                  if ( v33 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
                  goto LABEL_17;
                }
                if ( (int)WlidsvcUtil::XMLGetNodeAttribute(&c_bstrKeyNameAttr, &v32, &v37) >= 0 )
                  break;
                SysFreeString(bstrString);
                ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v32);
                ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v37);
              }
              v18 = v37;
              if ( (unsigned int)_o__mbscmp(v37, "KeyMaterial") )
              {
                if ( (unsigned int)_o__mbscmp(v18, "TimeStamp") )
                  goto LABEL_35;
                v17 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v32 + 208LL))(v32, &bstrString);
                v40 = v17;
                if ( v17 < 0 )
                {
                  v20 = 1005;
LABEL_62:
                  v21 = "hr = pKeyProp->get_text(&bstrText)";
LABEL_63:
                  Telemetry::IfFailExit(
                    "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\keycache.cpp",
                    "CKeyCache::ProcessKeyXml",
                    v20,
                    v17,
                    v21);
                  SysFreeString(bstrString);
                  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v32);
                  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v37);
                  goto LABEL_64;
                }
                v19 = &v36;
              }
              else
              {
                v17 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v32 + 208LL))(v32, &bstrString);
                v40 = v17;
                if ( v17 < 0 )
                {
                  v20 = 1000;
                  goto LABEL_62;
                }
                v19 = (unsigned __int8 **)&v35;
              }
              ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::operator=(v19, bstrString);
LABEL_35:
              SysFreeString(bstrString);
              if ( v32 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
              ATL::CStringData::Release((ATL::CStringData *)(v18 - 24));
            }
          }
          v24 = "hr = pPurposeNode->selectNodes(c_bstrKeyData, &pKeyList)";
          v25 = 951;
LABEL_76:
          Telemetry::IfFailExit(
            "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\keycache.cpp",
            "CKeyCache::ProcessKeyXml",
            v25,
            v8,
            v24);
          goto LABEL_77;
        }
      }
      v40 = 0;
      if ( v41 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
      if ( v29 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
      v11 = (ATL::CStringData *)(v10 - 24);
LABEL_60:
      ATL::CStringData::Release(v11);
    }
    v24 = "hr = pPurposeList->nextNode(&pPurposeNode)";
    v25 = 933;
    goto LABEL_76;
  }
LABEL_78:
  v26 = v40;
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v39);
  if ( v38 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
  return v26;
}

```

## disassembly

```asm
0x180014a20  mov     [rsp-8+arg_0], rbx
0x180014a25  push    rbp
0x180014a26  push    rsi
0x180014a27  push    rdi
0x180014a28  push    r12
0x180014a2a  push    r13
0x180014a2c  push    r14
0x180014a2e  push    r15
0x180014a30  lea     rbp, [rsp-27h]
0x180014a35  sub     rsp, 0B0h
0x180014a3c  mov     rbx, r8
0x180014a3f  mov     r12, rdx
0x180014a42  mov     r13, rcx
0x180014a45  xor     r15d, r15d
0x180014a48  mov     [rbp+57h+arg_10], r15d
0x180014a4c  lea     rcx, [rbp+57h+var_68]
0x180014a50  call    ??0?$CComPtr@UIXMLDOMDocument2@@@ATL@@QEAA@PEAUIXMLDOMDocument2@@@Z; ATL::CComPtr<IXMLDOMDocument2>::CComPtr<IXMLDOMDocument2>(IXMLDOMDocument2 *)
0x180014a55  nop
0x180014a56  lea     rsi, aCkeycacheProce; "CKeyCache::ProcessKeyXml"
0x180014a5d  mov     [rbp+57h+var_60], rsi
0x180014a61  lea     rax, [rbp+57h+arg_10]
0x180014a65  mov     [rbp+57h+var_58], rax
0x180014a69  mov     [rbp+57h+var_50], r15
0x180014a6d  mov     [rbp+57h+var_48], r15
0x180014a71  xor     r9d, r9d; unsigned int
0x180014a74  mov     r8d, 38Ch; char *
0x180014a7a  mov     rdx, rsi; char *
0x180014a7d  lea     rcx, aOnecoreuapDsEx_53; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180014a84  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x180014a89  nop
0x180014a8a  mov     rax, [rbx]
0x180014a8d  lea     r8, [rbp+57h+var_68]
0x180014a91  mov     rdx, cs:?c_bstrKeyPurpose@@3VCComBSTR@ATL@@A; ATL::CComBSTR c_bstrKeyPurpose
0x180014a98  mov     rcx, rbx
0x180014a9b  mov     rax, [rax+120h]
0x180014aa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014aa7  mov     [rbp+57h+arg_10], eax
0x180014aaa  test    eax, eax
0x180014aac  jns     short loc_180014AD7
0x180014aae  lea     r8, aHrPxmlnodeSele; "hr = pXMLNode->selectNodes(c_bstrKeyPur"...
0x180014ab5  mov     [rsp+0E0h+var_C0], r8; char *
0x180014aba  mov     r9d, eax; int
0x180014abd  mov     r8d, 391h; unsigned int
0x180014ac3  mov     rdx, rsi; char *
0x180014ac6  lea     rcx, aOnecoreuapDsEx_53; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180014acd  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180014ad2  jmp     loc_1800150F2
0x180014ad7  cmp     [rbp+57h+var_68], r15
0x180014adb  jz      loc_1800150F2
0x180014ae1  lea     rdi, [r13+60h]
0x180014ae5  mov     [rbp+57h+var_40], rdi
0x180014ae9  lea     r14, [rdi+20h]
0x180014aed  mov     rcx, r14; lpCriticalSection
0x180014af0  call    cs:__imp_EnterCriticalSection
0x180014af6  mov     rcx, [rdi+18h]; hEvent
0x180014afa  call    cs:__imp_ResetEvent
0x180014b00  mov     rcx, [rdi+10h]; hEvent
0x180014b04  call    cs:__imp_ResetEvent
0x180014b0a  lock inc dword ptr [rdi+8]
0x180014b0e  cmp     [rdi+0Ch], r15d
0x180014b12  jle     short loc_180014B22
0x180014b14  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180014b17  mov     rcx, [rdi+10h]; hHandle
0x180014b1b  call    cs:__imp_WaitForSingleObject
0x180014b21  nop
0x180014b22  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180014b29  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180014b30  mov     rax, [rax+18h]
0x180014b34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b39  lea     rbx, [rax+18h]
0x180014b3d  mov     [rbp+57h+var_A0], rbx
0x180014b41  mov     [rbp+57h+var_B0], r15
0x180014b45  mov     [rbp+57h+arg_18], r15
0x180014b49  mov     rcx, [rbp+57h+var_68]
0x180014b4d  mov     rax, [rcx]
0x180014b50  lea     rdx, [rbp+57h+arg_18]
0x180014b54  mov     rax, [rax+48h]
0x180014b58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b5d  mov     [rbp+57h+arg_10], eax
0x180014b60  test    eax, eax
0x180014b62  js      loc_180015094
0x180014b68  cmp     [rbp+57h+arg_18], r15
0x180014b6c  jz      loc_180015057
0x180014b72  lea     r8, [rbp+57h+var_A0]
0x180014b76  lea     rdx, [rbp+57h+arg_18]
0x180014b7a  lea     rcx, ?c_bstrKeyNameAttr@@3VCComBSTR@ATL@@A; ATL::CComBSTR c_bstrKeyNameAttr
0x180014b81  call    ?XMLGetNodeAttribute@WlidsvcUtil@@SAJAEBVCComBSTR@ATL@@AEBV?$CComPtr@UIXMLDOMNode@@@3@AEAV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@3@@Z; WlidsvcUtil::XMLGetNodeAttribute(ATL::CComBSTR const &,ATL::CComPtr<IXMLDOMNode> const &,ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> &)
0x180014b86  mov     rbx, [rbp+57h+var_A0]
0x180014b8a  test    eax, eax
0x180014b8c  js      loc_180014F31
0x180014b92  lea     rsi, [rbx-18h]
0x180014b96  cmp     [rsi+8], r15d
0x180014b9a  jz      loc_180014F31
0x180014ba0  mov     rcx, [rbp+57h+arg_18]
0x180014ba4  mov     rax, [rcx]
0x180014ba7  lea     r8, [rbp+57h+var_B0]
0x180014bab  mov     rdx, cs:?c_bstrKeyData@@3VCComBSTR@ATL@@A; ATL::CComBSTR c_bstrKeyData
0x180014bb2  mov     rax, [rax+120h]
0x180014bb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014bbe  mov     [rbp+57h+arg_10], eax
0x180014bc1  test    eax, eax
0x180014bc3  js      loc_180015048
0x180014bc9  mov     rcx, [rbp+57h+var_B0]
0x180014bcd  test    rcx, rcx
0x180014bd0  jnz     short loc_180014C05
0x180014bd2  mov     rdx, [rbp+57h+arg_18]
0x180014bd6  test    rdx, rdx
0x180014bd9  jz      short loc_180014BEE
0x180014bdb  mov     rax, [rdx]
0x180014bde  mov     rcx, rdx
0x180014be1  mov     rax, [rax+10h]
0x180014be5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014bea  mov     rcx, [rbp+57h+var_B0]
0x180014bee  test    rcx, rcx
0x180014bf1  jz      short loc_180014C00
0x180014bf3  mov     rax, [rcx]
0x180014bf6  mov     rax, [rax+10h]
0x180014bfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014bff  nop
0x180014c00  jmp     loc_180014F65
0x180014c05  mov     [rbp+57h+var_90], r15
0x180014c09  mov     [rbp+57h+var_A8], r15
0x180014c0d  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180014c14  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180014c1b  mov     rax, [rax+18h]
0x180014c1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014c24  lea     rbx, [rax+18h]
0x180014c28  mov     [rbp+57h+var_78], rbx
0x180014c2c  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180014c33  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180014c3a  mov     rax, [rax+18h]
0x180014c3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014c43  mov     rsi, rax
0x180014c46  lea     r15, [rax+18h]
0x180014c4a  mov     [rbp+57h+var_80], r15
0x180014c4e  mov     rcx, [rbp+57h+var_B0]
0x180014c52  mov     rdx, [rcx]
0x180014c55  mov     rax, [rdx+48h]
0x180014c59  lea     rdx, [rbp+57h+var_90]
0x180014c5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014c62  mov     [rbp+57h+arg_10], eax
0x180014c65  test    eax, eax
0x180014c67  js      loc_180015039
0x180014c6d  mov     rcx, [rbp+57h+var_90]
0x180014c71  test    rcx, rcx
0x180014c74  jz      loc_180014EB9
0x180014c7a  mov     rax, [rcx]
0x180014c7d  lea     r8, [rbp+57h+var_A8]
0x180014c81  mov     rdx, cs:?c_bstrKeyProperty@@3VCComBSTR@ATL@@A; ATL::CComBSTR c_bstrKeyProperty
0x180014c88  mov     rax, [rax+120h]
0x180014c8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014c94  mov     [rbp+57h+arg_10], eax
0x180014c97  test    eax, eax
0x180014c99  js      loc_18001502A
0x180014c9f  cmp     [rbp+57h+var_A8], 0
0x180014ca4  jnz     short loc_180014CD8
0x180014ca6  lea     rcx, [r15-18h]; this
0x180014caa  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180014caf  nop
0x180014cb0  lea     rcx, [rbx-18h]; this
0x180014cb4  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180014cb9  nop
0x180014cba  mov     rcx, [rbp+57h+var_A8]
0x180014cbe  xor     r15d, r15d
0x180014cc1  test    rcx, rcx
0x180014cc4  jz      short loc_180014CD3
0x180014cc6  mov     rax, [rcx]
0x180014cc9  mov     rax, [rax+10h]
0x180014ccd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014cd2  nop
0x180014cd3  jmp     loc_180014E9E
0x180014cd8  xor     r15d, r15d
0x180014cdb  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180014ce2  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180014ce9  mov     rax, [rax+18h]
0x180014ced  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014cf2  mov     rbx, rax
0x180014cf5  lea     rcx, [rax+18h]
0x180014cf9  mov     [rbp+57h+var_70], rcx
0x180014cfd  mov     [rbp+57h+var_98], r15
0x180014d01  mov     [rbp+57h+bstrString], r15
0x180014d05  mov     rcx, [rbp+57h+var_A8]
0x180014d09  mov     rdx, [rcx]
0x180014d0c  mov     rax, [rdx+48h]
0x180014d10  lea     rdx, [rbp+57h+var_98]
0x180014d14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d19  mov     [rbp+57h+arg_10], eax
0x180014d1c  test    eax, eax
0x180014d1e  js      loc_180015018
0x180014d24  cmp     [rbp+57h+var_98], r15
0x180014d28  jz      loc_180014E1C
0x180014d2e  lea     r8, [rbp+57h+var_70]
0x180014d32  lea     rdx, [rbp+57h+var_98]
0x180014d36  lea     rcx, ?c_bstrKeyNameAttr@@3VCComBSTR@ATL@@A; ATL::CComBSTR c_bstrKeyNameAttr
0x180014d3d  call    ?XMLGetNodeAttribute@WlidsvcUtil@@SAJAEBVCComBSTR@ATL@@AEBV?$CComPtr@UIXMLDOMNode@@@3@AEAV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@3@@Z; WlidsvcUtil::XMLGetNodeAttribute(ATL::CComBSTR const &,ATL::CComPtr<IXMLDOMNode> const &,ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> &)
0x180014d42  test    eax, eax
0x180014d44  jns     short loc_180014D69
0x180014d46  mov     rcx, [rbp+57h+bstrString]; bstrString
0x180014d4a  call    cs:__imp_SysFreeString
0x180014d50  nop
0x180014d51  lea     rcx, [rbp+57h+var_98]
0x180014d55  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x180014d5a  nop
0x180014d5b  lea     rcx, [rbp+57h+var_70]
0x180014d5f  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180014d64  jmp     loc_180014CDB
0x180014d69  lea     rdx, aKeymaterial_0; "KeyMaterial"
0x180014d70  mov     rbx, [rbp+57h+var_70]
0x180014d74  mov     rcx, rbx
0x180014d77  call    cs:__imp__o__mbscmp
0x180014d7d  test    eax, eax
0x180014d7f  jnz     short loc_180014DA9
0x180014d81  mov     rcx, [rbp+57h+var_98]
0x180014d85  mov     rax, [rcx]
0x180014d88  lea     rdx, [rbp+57h+bstrString]
0x180014d8c  mov     rax, [rax+0D0h]
0x180014d93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d98  mov     [rbp+57h+arg_10], eax
0x180014d9b  test    eax, eax
0x180014d9d  js      loc_180014F72
0x180014da3  lea     rcx, [rbp+57h+var_80]
0x180014da7  jmp     short loc_180014DE3
0x180014da9  lea     rdx, aTimestamp; "TimeStamp"
0x180014db0  mov     rcx, rbx
0x180014db3  call    cs:__imp__o__mbscmp
0x180014db9  test    eax, eax
0x180014dbb  jnz     short loc_180014DED
0x180014dbd  mov     rcx, [rbp+57h+var_98]
0x180014dc1  mov     rax, [rcx]
0x180014dc4  lea     rdx, [rbp+57h+bstrString]
0x180014dc8  mov     rax, [rax+0D0h]
0x180014dcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014dd4  mov     [rbp+57h+arg_10], eax
0x180014dd7  test    eax, eax
0x180014dd9  js      loc_180014FE6
0x180014ddf  lea     rcx, [rbp+57h+var_78]
0x180014de3  mov     rdx, [rbp+57h+bstrString]
0x180014de7  call    ??4?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBG@Z; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::operator=(ushort const *)
0x180014dec  nop
0x180014ded  mov     rcx, [rbp+57h+bstrString]; bstrString
0x180014df1  call    cs:__imp_SysFreeString
0x180014df7  nop
0x180014df8  mov     rcx, [rbp+57h+var_98]
0x180014dfc  test    rcx, rcx
0x180014dff  jz      short loc_180014E0E
0x180014e01  mov     rax, [rcx]
0x180014e04  mov     rax, [rax+10h]
0x180014e08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014e0d  nop
0x180014e0e  lea     rcx, [rbx-18h]; this
0x180014e12  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180014e17  jmp     loc_180014CDB
0x180014e1c  mov     rcx, [rbp+57h+bstrString]; bstrString
0x180014e20  call    cs:__imp_SysFreeString
0x180014e26  nop
0x180014e27  mov     rcx, [rbp+57h+var_98]
0x180014e2b  test    rcx, rcx
0x180014e2e  jz      short loc_180014E3D
0x180014e30  mov     rax, [rcx]
0x180014e33  mov     rax, [rax+10h]
0x180014e37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014e3c  nop
0x180014e3d  mov     rcx, rbx; this
0x180014e40  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180014e45  lea     rax, [rbp+57h+var_80]
0x180014e49  mov     [rsp+0E0h+var_C0], rax
0x180014e4e  lea     r9, [rbp+57h+var_78]
0x180014e52  lea     r8, [rbp+57h+var_A0]
0x180014e56  mov     rdx, r12
0x180014e59  mov     rcx, r13
0x180014e5c  call    ?UpdateKeyCache@CKeyCache@@IEAAJPEAVIServiceExecutionContext@@AEBV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@11@Z; CKeyCache::UpdateKeyCache(IServiceExecutionContext *,ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> const &,ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> const &,ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> const &)
0x180014e61  mov     [rbp+57h+arg_10], eax
0x180014e64  test    eax, eax
0x180014e66  js      loc_180014FEE
0x180014e6c  mov     rcx, [rbp+57h+var_80]
0x180014e70  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180014e74  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180014e79  nop
0x180014e7a  mov     rcx, [rbp+57h+var_78]
0x180014e7e  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180014e82  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180014e87  nop
0x180014e88  mov     rcx, [rbp+57h+var_A8]
0x180014e8c  test    rcx, rcx
0x180014e8f  jz      short loc_180014E9E
0x180014e91  mov     rax, [rcx]
0x180014e94  mov     rax, [rax+10h]
0x180014e98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014e9d  nop
0x180014e9e  mov     rcx, [rbp+57h+var_90]
0x180014ea2  test    rcx, rcx
0x180014ea5  jz      short loc_180014EB4
0x180014ea7  mov     rax, [rcx]
0x180014eaa  mov     rax, [rax+10h]
0x180014eae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014eb3  nop
0x180014eb4  jmp     loc_180014C05
0x180014eb9  mov     rcx, rsi; this
0x180014ebc  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180014ec1  nop
  ... truncated ...
```
