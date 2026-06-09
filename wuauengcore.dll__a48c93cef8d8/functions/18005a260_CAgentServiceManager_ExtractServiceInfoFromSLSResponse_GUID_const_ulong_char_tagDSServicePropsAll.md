# CAgentServiceManager::ExtractServiceInfoFromSLSResponse(_GUID const &,ulong,char *,tagDSServicePropsAll *)

- ea: `0x18005a260`
- end: `0x18005a83a`
- name: `?ExtractServiceInfoFromSLSResponse@CAgentServiceManager@@CAJAEBU_GUID@@KPEADPEAUtagDSServicePropsAll@@@Z`
- size: `1498`
- prototype: `__int64 __fastcall(const struct _GUID *, unsigned int, char *, const wchar_t **)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18005ab54`

## callees

- `0x18005a260`
- `0x180104404`
- `0x180104440`
- `0x1801044b8`
- `0x18010f18c`
- `0x180113ae8`
- `0x180113b9c`
- `0x180113c50`
- `0x18011cc6c`
- `0x18012b618`
- `0x1801342ec`
- `0x1801345ec`
- `0x18013a280`
- `0x180238960`
- `0x180240cc0`
- `0x180240d40`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005a395`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005a395`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005a56f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005a65e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005a667`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005a693`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005a56f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005a65e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005a667`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005a693`
- `OLEAUT32!__imp_SysAllocString` at `0x18005a33c`
- `OLEAUT32!__imp_SysAllocString` at `0x18005a43f`
- `OLEAUT32!__imp_SysAllocString` at `0x18005a33c`
- `OLEAUT32!__imp_SysAllocString` at `0x18005a43f`
- `OLEAUT32!__imp_SysFreeString` at `0x18005a48f`
- `OLEAUT32!__imp_SysFreeString` at `0x18005a4db`
- `OLEAUT32!__imp_SysFreeString` at `0x18005a72d`
- `OLEAUT32!__imp_SysFreeString` at `0x18005a787`
- `OLEAUT32!__imp_SysFreeString` at `0x18005a48f`
- `OLEAUT32!__imp_SysFreeString` at `0x18005a4db`
- `OLEAUT32!__imp_SysFreeString` at `0x18005a72d`
- `OLEAUT32!__imp_SysFreeString` at `0x18005a787`
- `OLEAUT32!__imp_VariantInit` at `0x18005a432`
- `OLEAUT32!__imp_VariantInit` at `0x18005a432`

## string_xrefs

- `0x18005a753`: `loadXML failed. Returning WU_E_REDIRECTOR_LOAD_XML...`
- `0x18005a3d9`: `loadXML`
- `0x18005a592`: `Update service Url property to '%ws'`
- `0x18005a672`: `Windows Update`
- `0x18005a7af`: `CAgentServiceManager::ExtractServiceInfoFromSLSResponse`

## pseudocode

```c
__int64 __fastcall CAgentServiceManager::ExtractServiceInfoFromSLSResponse(
        const struct _GUID *a1,
        unsigned int a2,
        char *a3,
        const wchar_t **a4)
{
  unsigned __int64 v6; // r14
  OLECHAR *v7; // rbx
  OLECHAR *v8; // r12
  HRESULT v9; // edi
  wchar_t *v10; // rax
  int v11; // eax
  OLECHAR *v12; // rdi
  LPVOID v13; // rdi
  __int64 (__fastcall *v14)(LPVOID, GUID *, struct IUnknown **); // r14
  const wchar_t *v15; // rdi
  unsigned int v16; // ecx
  int v17; // edx
  int v18; // edx
  unsigned int v19; // ecx
  LPVOID *v20; // r14
  VARIANTARG v22; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t *v23; // [rsp+70h] [rbp-90h] BYREF
  LPVOID pv; // [rsp+78h] [rbp-88h] BYREF
  __int16 v25; // [rsp+80h] [rbp-80h] BYREF
  LPVOID ppv; // [rsp+88h] [rbp-78h] BYREF
  struct IUnknown *v27; // [rsp+90h] [rbp-70h] BYREF
  VARIANTARG pvarg; // [rsp+98h] [rbp-68h] BYREF
  _OWORD v29[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v30; // [rsp+D0h] [rbp-30h]
  _DWORD v31[16]; // [rsp+E0h] [rbp-20h] BYREF

  v6 = a2;
  ppv = 0;
  v27 = 0;
  memset(v29, 0, sizeof(v29));
  v30 = 0;
  v25 = 0;
  v7 = 0;
  v8 = 0;
  memset(v31, 0, sizeof(v31));
  CNetworkListManagerHelper::CNetworkListManagerHelper((CNetworkListManagerHelper *)v31);
  if ( !a4 )
  {
    v9 = -2147467261;
    goto LABEL_61;
  }
  memset(a4, 0, 0xF0u);
  if ( v6 + 1 < v6 )
  {
    v9 = -2147024362;
    goto LABEL_59;
  }
  v10 = (wchar_t *)SafeSusAllocArray(v6 + 1, 2u);
  v7 = v10;
  if ( !v10 )
  {
LABEL_5:
    v9 = -2147024882;
    goto LABEL_59;
  }
  v9 = ConvertAnsiToWide(a3, v6, v10, (int)v6 + 1);
  if ( v9 >= 0 )
  {
    v8 = SysAllocString(v7);
    if ( !v8 )
      goto LABEL_5;
    SusFree(v7);
    v7 = 0;
    v9 = CoCreateInstance(&CLSID_DOMDocument60, 0, 1u, &GUID_2933bf95_7b36_11d2_b20e_00c04f983e60, &ppv);
    if ( v9 >= 0 )
    {
      v11 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *, __int16 *))(*(_QWORD *)ppv + 520LL))(ppv, v8, &v25);
      v9 = v11;
      if ( !v25 || v11 == 1 )
      {
        v23 = 0;
        pv = 0;
        if ( !(*(unsigned int (__fastcall **)(LPVOID, wchar_t **))(*(_QWORD *)ppv + 480LL))(ppv, &v23)
          && !(*(unsigned int (__fastcall **)(wchar_t *, LPVOID *))(*(_QWORD *)v23 + 72LL))(v23, &pv) )
        {
          WUTrace(0, 0, 4, 3, 0, L"Parse error reason %ws", pv);
        }
        SysFreeString((BSTR)pv);
        pv = 0;
        if ( v23 )
          (*(void (__fastcall **)(wchar_t *))(*(_QWORD *)v23 + 16LL))(v23);
        v23 = 0;
        WUTrace(0, 0, 1, 1, v9, L"loadXML failed. Returning WU_E_REDIRECTOR_LOAD_XML...");
        v9 = -2145103871;
        goto LABEL_59;
      }
      if ( v11 < 0 )
      {
        WUTrace(0, 0, 1, 1, v11, L"loadXML");
        goto LABEL_59;
      }
      v9 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 544LL))(ppv, 0);
      if ( v9 < 0 )
      {
        WUTrace(0, 0, 1, 1, v9, L"put_validateOnParse");
        goto LABEL_59;
      }
      memset(&pvarg, 0, sizeof(pvarg));
      VariantInit(&pvarg);
      v12 = SysAllocString(L"NewParser");
      if ( v12 )
      {
        pvarg.vt = 11;
        pvarg.iVal = -1;
        v22 = pvarg;
        (*(void (__fastcall **)(LPVOID, OLECHAR *, VARIANTARG *))(*(_QWORD *)ppv + 640LL))(ppv, v12, &v22);
        SysFreeString(v12);
      }
      v13 = ppv;
      v14 = **(__int64 (__fastcall ***)(LPVOID, GUID *, struct IUnknown **))ppv;
      if ( v27 )
      {
        ((void (__fastcall *)(struct IUnknown *))v27->lpVtbl->Release)(v27);
        v27 = 0;
      }
      v9 = v14(v13, &IID_IXMLDOMNode, &v27);
      if ( v9 < 0 )
        goto LABEL_59;
      SysFreeString(v8);
      v8 = 0;
      v9 = DspParseElementSet(
             v27,
             (unsigned __int8 *)a4,
             (struct SusXmlNode *)&qword_180334470,
             (struct tagSusXmlState *)v29);
      if ( v9 < 0 )
      {
        WUTrace(0, 0, 1, 1, v9, L"DspParseElementSet");
        goto LABEL_59;
      }
      v31[0] = 1;
      if ( (a4[27] || a4[26])
        && !(unsigned int)CNetworkListManagerHelper::IsInternetConnectionAvailable(v31, 1)
        && (unsigned int)CNetworkListManagerHelper::IsInternetConnectionAvailable(v31, 2)
        && ((v15 = a4[27]) != 0 || (v15 = a4[26]) != 0)
        || (v15 = a4[25]) != 0 )
      {
        if ( *a4 )
          CoTaskMemFree((LPVOID)*a4);
        v9 = CoDuplicateString(v15, (wchar_t **)a4);
        if ( v9 < 0 )
          goto LABEL_59;
        WUTrace(0, 0, 1, 5, 0, L"Update service Url property to '%ws'", *a4);
      }
      *((_DWORD *)a4 + 6) = 0;
      v16 = (_DWORD)a4[12] & 0xFFFFFFDB;
      *((_DWORD *)a4 + 24) = v16;
      v17 = *((_DWORD *)a4 + 46);
      if ( v17 )
      {
        v18 = v17 - 1;
        if ( v18 )
        {
          if ( v18 != 1 )
          {
LABEL_40:
            v23 = 0;
            a4[9] = (const wchar_t *)0x7FFFFFFFFFFFFFFFLL;
            a4[8] = 0;
            if ( !*((_DWORD *)a4 + 27) )
            {
              pv = 0;
              v23 = 0;
              v20 = (LPVOID *)SafeSusComAllocArray(1u, 0x10u);
              if ( !v20 )
              {
                v9 = -2147024882;
                goto LABEL_59;
              }
              v9 = DSCopyString((wchar_t **)&pv, L"en");
              if ( v9 < 0 )
              {
LABEL_44:
                if ( pv )
                  CoTaskMemFree(pv);
                CoTaskMemFree(v20);
                goto LABEL_59;
              }
              v9 = DSCopyString(&v23, L"Windows Update");
              if ( v9 < 0 )
              {
                if ( v23 )
                  CoTaskMemFree(v23);
                goto LABEL_44;
              }
              *v20 = pv;
              v20[1] = v23;
              a4[14] = (const wchar_t *)v20;
              *((_DWORD *)a4 + 27) = 1;
            }
            v9 = 0;
            goto LABEL_59;
          }
          v19 = v16 & 0xFFFFF9FF | 0x400;
        }
        else
        {
          v19 = v16 & 0xFFFFF9FF | 0x200;
        }
      }
      else
      {
        v19 = v16 & 0xFFFFF9FF;
      }
      *((_DWORD *)a4 + 24) = v19;
      goto LABEL_40;
    }
  }
LABEL_59:
  SysFreeString(v8);
  if ( v9 < 0 )
  {
    WUTrace("CAgentServiceManager::ExtractServiceInfoFromSLSResponse", 558, 1, 3, v9, L"Method failed");
    DsqFreeObject((struct tagDSServicePropsAll *)a4, 1u, 1);
  }
LABEL_61:
  CNetworkListManagerHelper::~CNetworkListManagerHelper((CNetworkListManagerHelper *)v31);
  if ( v7 )
    SusFree(v7);
  if ( v27 )
  {
    ((void (__fastcall *)(struct IUnknown *))v27->lpVtbl->Release)(v27);
    v27 = 0;
  }
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18005a260  mov     [rsp-8+arg_0], rbx
0x18005a265  push    rbp
0x18005a266  push    rsi
0x18005a267  push    rdi
0x18005a268  push    r12
0x18005a26a  push    r13
0x18005a26c  push    r14
0x18005a26e  push    r15
0x18005a270  lea     rbp, [rsp-30h]
0x18005a275  sub     rsp, 130h
0x18005a27c  mov     rax, cs:__security_cookie
0x18005a283  xor     rax, rsp
0x18005a286  mov     [rbp+60h+var_40], rax
0x18005a28a  mov     rsi, r9
0x18005a28d  mov     r15, r8
0x18005a290  mov     r14d, edx
0x18005a293  xor     r13d, r13d
0x18005a296  mov     [rbp+60h+var_D8], r13
0x18005a29a  mov     [rbp+60h+var_D0], r13
0x18005a29e  xorps   xmm0, xmm0
0x18005a2a1  xor     eax, eax
0x18005a2a3  movups  [rbp+60h+var_B0], xmm0
0x18005a2a7  movups  [rbp+60h+var_A0], xmm0
0x18005a2ab  mov     [rbp+60h+var_90], rax
0x18005a2af  mov     [rbp+60h+var_E0], r13w
0x18005a2b4  mov     ebx, r13d
0x18005a2b7  mov     r12d, r13d
0x18005a2ba  xor     edx, edx; Val
0x18005a2bc  lea     r8d, [r13+40h]; Size
0x18005a2c0  lea     rcx, [rbp+60h+var_80]; void *
0x18005a2c4  call    memset
0x18005a2c9  lea     rcx, [rbp+60h+var_80]; this
0x18005a2cd  call    ??0CNetworkListManagerHelper@@QEAA@XZ; CNetworkListManagerHelper::CNetworkListManagerHelper(void)
0x18005a2d2  nop
0x18005a2d3  test    rsi, rsi
0x18005a2d6  jnz     short loc_18005A2E2
0x18005a2d8  mov     edi, 80004003h
0x18005a2dd  jmp     loc_18005A7CA
0x18005a2e2  xor     edx, edx; Val
0x18005a2e4  mov     r8d, 0F0h; Size
0x18005a2ea  mov     rcx, rsi; void *
0x18005a2ed  call    memset
0x18005a2f2  lea     rdi, [r14+1]
0x18005a2f6  cmp     rdi, r14
0x18005a2f9  jb      loc_18005A779
0x18005a2ff  mov     edx, 2; unsigned __int64
0x18005a304  mov     rcx, rdi; unsigned __int64
0x18005a307  call    ?SafeSusAllocArray@@YAPEAX_K0@Z; SafeSusAllocArray(unsigned __int64,unsigned __int64)
0x18005a30c  mov     rbx, rax
0x18005a30f  test    rax, rax
0x18005a312  jnz     short loc_18005A31E
0x18005a314  mov     edi, 8007000Eh
0x18005a319  jmp     loc_18005A77E
0x18005a31e  mov     r9d, edi; cchWideChar
0x18005a321  mov     r8, rbx; wchar_t *
0x18005a324  mov     edx, r14d; cbMultiByte
0x18005a327  mov     rcx, r15; lpMultiByteStr
0x18005a32a  call    ?ConvertAnsiToWide@@YAJPEBDIPEA_WI@Z; ConvertAnsiToWide(char const *,uint,wchar_t *,uint)
0x18005a32f  mov     edi, eax
0x18005a331  test    eax, eax
0x18005a333  js      loc_18005A77E
0x18005a339  mov     rcx, rbx; psz
0x18005a33c  call    cs:__imp_SysAllocString
0x18005a342  mov     r12, rax
0x18005a345  test    rax, rax
0x18005a348  jz      short loc_18005A314
0x18005a34a  mov     rcx, rbx; lpMem
0x18005a34d  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18005a352  mov     rbx, r13
0x18005a355  mov     [rsp+160h+var_120], rbx
0x18005a35a  mov     rcx, [rbp+60h+var_D8]
0x18005a35e  test    rcx, rcx
0x18005a361  jz      short loc_18005A373
0x18005a363  mov     rax, [rcx]
0x18005a366  mov     rax, [rax+10h]
0x18005a36a  call    _guard_dispatch_icall
0x18005a36f  mov     [rbp+60h+var_D8], r13
0x18005a373  lea     rax, [rbp+60h+var_D8]
0x18005a377  mov     [rsp+160h+ppv], rax; ppv
0x18005a37c  lea     r9, _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60; riid
0x18005a383  mov     r15d, 1
0x18005a389  mov     r8d, r15d; dwClsContext
0x18005a38c  xor     edx, edx; pUnkOuter
0x18005a38e  lea     rcx, CLSID_DOMDocument60; rclsid
0x18005a395  call    cs:__imp_CoCreateInstance
0x18005a39b  mov     edi, eax
0x18005a39d  test    eax, eax
0x18005a39f  js      loc_18005A784
0x18005a3a5  mov     rcx, [rbp+60h+var_D8]
0x18005a3a9  mov     rax, [rcx]
0x18005a3ac  lea     r8, [rbp+60h+var_E0]
0x18005a3b0  mov     rdx, r12
0x18005a3b3  mov     rax, [rax+208h]
0x18005a3ba  call    _guard_dispatch_icall
0x18005a3bf  mov     edi, eax
0x18005a3c1  cmp     r13w, [rbp+60h+var_E0]
0x18005a3c6  jz      loc_18005A6BC
0x18005a3cc  cmp     eax, r15d
0x18005a3cf  jz      loc_18005A6BC
0x18005a3d5  test    eax, eax
0x18005a3d7  jns     short loc_18005A3FD
0x18005a3d9  lea     rax, aLoadxml; "loadXML"
0x18005a3e0  mov     [rsp+160h+var_138], rax
0x18005a3e5  mov     dword ptr [rsp+160h+ppv], edi
0x18005a3e9  mov     r9d, r15d
0x18005a3ec  mov     r8d, r15d
0x18005a3ef  xor     edx, edx
0x18005a3f1  xor     ecx, ecx
0x18005a3f3  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18005a3f8  jmp     loc_18005A784
0x18005a3fd  xor     edx, edx
0x18005a3ff  mov     rcx, [rbp+60h+var_D8]
0x18005a403  mov     rax, [rcx]
0x18005a406  mov     rax, [rax+220h]
0x18005a40d  call    _guard_dispatch_icall
0x18005a412  mov     edi, eax
0x18005a414  test    eax, eax
0x18005a416  jns     short loc_18005A421
0x18005a418  lea     rax, aPutValidateonp; "put_validateOnParse"
0x18005a41f  jmp     short loc_18005A3E0
0x18005a421  xorps   xmm0, xmm0
0x18005a424  xor     eax, eax
0x18005a426  movups  xmmword ptr [rbp+60h+pvarg], xmm0
0x18005a42a  mov     qword ptr [rbp+60h+pvarg+10h], rax
0x18005a42e  lea     rcx, [rbp+60h+pvarg]; pvarg
0x18005a432  call    cs:__imp_VariantInit
0x18005a438  lea     rcx, aNewparser; "NewParser"
0x18005a43f  call    cs:__imp_SysAllocString
0x18005a445  mov     rdi, rax
0x18005a448  test    rax, rax
0x18005a44b  jz      short loc_18005A495
0x18005a44d  mov     eax, 0Bh
0x18005a452  mov     word ptr [rbp+60h+pvarg], ax
0x18005a456  or      eax, 0FFFFFFFFh
0x18005a459  mov     word ptr [rbp+60h+pvarg+8], ax
0x18005a45d  movups  xmm0, xmmword ptr [rbp+60h+pvarg]
0x18005a461  movaps  [rsp+160h+var_110], xmm0
0x18005a466  movsd   xmm1, qword ptr [rbp+60h+pvarg+10h]
0x18005a46b  movsd   [rsp+160h+var_100], xmm1
0x18005a471  mov     rcx, [rbp+60h+var_D8]
0x18005a475  mov     rdx, [rcx]
0x18005a478  mov     rax, [rdx+280h]
0x18005a47f  lea     r8, [rsp+160h+var_110]
0x18005a484  mov     rdx, rdi
0x18005a487  call    _guard_dispatch_icall
0x18005a48c  mov     rcx, rdi; bstrString
0x18005a48f  call    cs:__imp_SysFreeString
0x18005a495  mov     rdi, [rbp+60h+var_D8]
0x18005a499  mov     rax, [rdi]
0x18005a49c  mov     r14, [rax]
0x18005a49f  mov     rcx, [rbp+60h+var_D0]
0x18005a4a3  test    rcx, rcx
0x18005a4a6  jz      short loc_18005A4B8
0x18005a4a8  mov     rdx, [rcx]
0x18005a4ab  mov     rax, [rdx+10h]
0x18005a4af  call    _guard_dispatch_icall
0x18005a4b4  mov     [rbp+60h+var_D0], r13
0x18005a4b8  lea     r8, [rbp+60h+var_D0]
0x18005a4bc  lea     rdx, IID_IXMLDOMNode
0x18005a4c3  mov     rcx, rdi
0x18005a4c6  mov     rax, r14
0x18005a4c9  call    _guard_dispatch_icall
0x18005a4ce  mov     edi, eax
0x18005a4d0  test    eax, eax
0x18005a4d2  js      loc_18005A784
0x18005a4d8  mov     rcx, r12; bstrString
0x18005a4db  call    cs:__imp_SysFreeString
0x18005a4e1  mov     r12, r13
0x18005a4e4  lea     r9, [rbp+60h+var_B0]; struct tagSusXmlState *
0x18005a4e8  lea     r8, qword_180334470; struct SusXmlNode *
0x18005a4ef  mov     rdx, rsi; unsigned __int8 *
0x18005a4f2  mov     rcx, [rbp+60h+var_D0]; struct IUnknown *
0x18005a4f6  call    ?DspParseElementSet@@YAJPEAUIUnknown@@PEAEPEAUSusXmlNode@@AEAUtagSusXmlState@@@Z; DspParseElementSet(IUnknown *,uchar *,SusXmlNode *,tagSusXmlState &)
0x18005a4fb  mov     edi, eax
0x18005a4fd  test    eax, eax
0x18005a4ff  jns     short loc_18005A50D
0x18005a501  lea     rax, aDspparseelemen; "DspParseElementSet"
0x18005a508  jmp     loc_18005A3E0
0x18005a50d  mov     [rbp+60h+var_80], r15d
0x18005a511  cmp     [rsi+0D8h], r13
0x18005a518  jnz     short loc_18005A523
0x18005a51a  cmp     [rsi+0D0h], r13
0x18005a521  jz      short loc_18005A55B
0x18005a523  mov     edx, r15d
0x18005a526  lea     rcx, [rbp+60h+var_80]
0x18005a52a  call    ?IsInternetConnectionAvailable@CNetworkListManagerHelper@@QEAAHW4_tagInternetConnectionState@@@Z; CNetworkListManagerHelper::IsInternetConnectionAvailable(_tagInternetConnectionState)
0x18005a52f  test    eax, eax
0x18005a531  jnz     short loc_18005A55B
0x18005a533  lea     edx, [rax+2]
0x18005a536  lea     rcx, [rbp+60h+var_80]
0x18005a53a  call    ?IsInternetConnectionAvailable@CNetworkListManagerHelper@@QEAAHW4_tagInternetConnectionState@@@Z; CNetworkListManagerHelper::IsInternetConnectionAvailable(_tagInternetConnectionState)
0x18005a53f  test    eax, eax
0x18005a541  jz      short loc_18005A55B
0x18005a543  mov     rdi, [rsi+0D8h]
0x18005a54a  test    rdi, rdi
0x18005a54d  jnz     short loc_18005A567
0x18005a54f  mov     rdi, [rsi+0D0h]
0x18005a556  test    rdi, rdi
0x18005a559  jnz     short loc_18005A567
0x18005a55b  mov     rdi, [rsi+0C8h]
0x18005a562  test    rdi, rdi
0x18005a565  jz      short loc_18005A5B5
0x18005a567  mov     rcx, [rsi]; pv
0x18005a56a  test    rcx, rcx
0x18005a56d  jz      short loc_18005A575
0x18005a56f  call    cs:__imp_CoTaskMemFree
0x18005a575  mov     rdx, rsi; wchar_t **
0x18005a578  mov     rcx, rdi; wchar_t *
0x18005a57b  call    ?CoDuplicateString@@YAJPEB_WPEAPEA_W@Z; CoDuplicateString(wchar_t const *,wchar_t * *)
0x18005a580  mov     edi, eax
0x18005a582  test    eax, eax
0x18005a584  js      loc_18005A784
0x18005a58a  mov     rax, [rsi]
0x18005a58d  mov     [rsp+160h+var_130], rax
0x18005a592  lea     rax, aUpdateServiceU; "Update service Url property to '%ws'"
0x18005a599  mov     [rsp+160h+var_138], rax
0x18005a59e  mov     [rsp+160h+ppv], r13
0x18005a5a3  mov     r9d, 5
0x18005a5a9  mov     r8d, r15d
0x18005a5ac  xor     edx, edx
0x18005a5ae  xor     ecx, ecx
0x18005a5b0  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18005a5b5  mov     [rsi+18h], r13d
0x18005a5b9  mov     ecx, [rsi+60h]
0x18005a5bc  and     ecx, 0FFFFFFDBh
0x18005a5bf  mov     [rsi+60h], ecx
0x18005a5c2  mov     edx, [rsi+0B8h]
0x18005a5c8  test    edx, edx
0x18005a5ca  jz      short loc_18005A5EA
0x18005a5cc  sub     edx, r15d
0x18005a5cf  jz      short loc_18005A5E0
0x18005a5d1  cmp     edx, r15d
0x18005a5d4  jnz     short loc_18005A5F3
0x18005a5d6  btr     ecx, 9
0x18005a5da  bts     ecx, 0Ah
0x18005a5de  jmp     short loc_18005A5F0
0x18005a5e0  btr     ecx, 0Ah
0x18005a5e4  bts     ecx, 9
0x18005a5e8  jmp     short loc_18005A5F0
0x18005a5ea  and     ecx, 0FFFFF9FFh
0x18005a5f0  mov     [rsi+60h], ecx
0x18005a5f3  mov     [rsp+160h+var_F0], r13
0x18005a5f8  mov     rax, cs:qword_180266F90
0x18005a5ff  mov     [rsi+48h], rax
0x18005a603  mov     rax, r13
0x18005a606  mov     [rsi+40h], rax
0x18005a60a  cmp     [rsi+6Ch], r13d
0x18005a60e  jnz     loc_18005A6B4
0x18005a614  mov     [rsp+160h+pv], r13
0x18005a619  mov     [rsp+160h+var_F0], r13
0x18005a61e  mov     edx, 10h; unsigned __int64
0x18005a623  mov     rcx, r15; unsigned __int64
0x18005a626  call    ?SafeSusComAllocArray@@YAPEAX_K0@Z; SafeSusComAllocArray(unsigned __int64,unsigned __int64)
0x18005a62b  mov     r14, rax
0x18005a62e  test    rax, rax
0x18005a631  jnz     short loc_18005A63D
0x18005a633  mov     edi, 8007000Eh
0x18005a638  jmp     loc_18005A784
0x18005a63d  lea     rdx, aEn; "en"
0x18005a644  lea     rcx, [rsp+160h+pv]; wchar_t **
0x18005a649  call    ?DSCopyString@@YAJPEAPEA_WPEB_W@Z; DSCopyString(wchar_t * *,wchar_t const *)
0x18005a64e  mov     edi, eax
0x18005a650  test    eax, eax
0x18005a652  jns     short loc_18005A672
0x18005a654  mov     rcx, [rsp+160h+pv]; pv
0x18005a659  test    rcx, rcx
0x18005a65c  jz      short loc_18005A664
0x18005a65e  call    cs:__imp_CoTaskMemFree
0x18005a664  mov     rcx, r14; pv
0x18005a667  call    cs:__imp_CoTaskMemFree
0x18005a66d  jmp     loc_18005A784
0x18005a672  lea     rdx, aWindowsUpdate; "Windows Update"
0x18005a679  lea     rcx, [rsp+160h+var_F0]; wchar_t **
0x18005a67e  call    ?DSCopyString@@YAJPEAPEA_WPEB_W@Z; DSCopyString(wchar_t * *,wchar_t const *)
0x18005a683  mov     edi, eax
0x18005a685  test    eax, eax
0x18005a687  jns     short loc_18005A69B
0x18005a689  mov     rcx, [rsp+160h+var_F0]; pv
0x18005a68e  test    rcx, rcx
0x18005a691  jz      short loc_18005A654
0x18005a693  call    cs:__imp_CoTaskMemFree
0x18005a699  jmp     short loc_18005A654
0x18005a69b  mov     rax, [rsp+160h+pv]
0x18005a6a0  mov     [r14], rax
0x18005a6a3  mov     rax, [rsp+160h+var_F0]
0x18005a6a8  mov     [r14+8], rax
0x18005a6ac  mov     [rsi+70h], r14
0x18005a6b0  mov     [rsi+6Ch], r15d
0x18005a6b4  mov     edi, r13d
0x18005a6b7  jmp     loc_18005A784
0x18005a6bc  mov     [rsp+160h+var_F0], r13
0x18005a6c1  mov     [rsp+160h+pv], r13
0x18005a6c6  mov     rcx, [rbp+60h+var_D8]
0x18005a6ca  mov     rax, [rcx]
0x18005a6cd  lea     rdx, [rsp+160h+var_F0]
0x18005a6d2  mov     rax, [rax+1E0h]
0x18005a6d9  call    _guard_dispatch_icall
0x18005a6de  test    eax, eax
0x18005a6e0  jnz     short loc_18005A728
0x18005a6e2  mov     rcx, [rsp+160h+var_F0]
  ... truncated ...
```
