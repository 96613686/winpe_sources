# DumperConfig::XmlElementReadOrModify(wchar_t const *,wchar_t const *,wchar_t *,ushort,wchar_t *,ushort,bool)

- ea: `0x100444870`
- end: `0x100444db0`
- name: `?XmlElementReadOrModify@DumperConfig@@CA_NPEB_W0PEA_WG1G_N@Z`
- size: `1344`
- prototype: `bool __usercall@<al>(const wchar_t *psz@<rcx>, const wchar_t *@<rdx>, wchar_t *@<r8>, unsigned __int16@<r9w>, wchar_t *, unsigned __int16, bool)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x100443390`

## callees

- `0x100401580`
- `0x100404a30`
- `0x100444590`
- `0x100444870`
- `0x100444df0`
- `0x100444fc0`
- `0x1004534f8`

## import_xrefs

- `ole32!CoUninitialize` at `0x100444d1d`
- `ole32!CoUninitialize` at `0x100444d1d`
- `ole32!CoCreateInstance` at `0x100444950`
- `ole32!CoCreateInstance` at `0x100444950`
- `ole32!CoInitializeEx` at `0x1004448ca`
- `ole32!CoInitializeEx` at `0x1004448ca`
- `OLEAUT32!__imp_SysAllocString` at `0x100444908`
- `OLEAUT32!__imp_SysAllocString` at `0x100444aa2`
- `OLEAUT32!__imp_SysAllocString` at `0x100444908`
- `OLEAUT32!__imp_SysAllocString` at `0x100444aa2`
- `OLEAUT32!__imp_SysFreeString` at `0x100444a12`
- `OLEAUT32!__imp_SysFreeString` at `0x100444afd`
- `OLEAUT32!__imp_SysFreeString` at `0x100444bd1`
- `OLEAUT32!__imp_SysFreeString` at `0x100444a12`
- `OLEAUT32!__imp_SysFreeString` at `0x100444afd`
- `OLEAUT32!__imp_SysFreeString` at `0x100444bd1`
- `OLEAUT32!__imp_VariantClear` at `0x1004448ee`
- `OLEAUT32!__imp_VariantClear` at `0x100444d0f`
- `OLEAUT32!__imp_VariantClear` at `0x1004448ee`
- `OLEAUT32!__imp_VariantClear` at `0x100444d0f`
- `OLEAUT32!__imp_VariantCopy` at `0x100444c35`
- `OLEAUT32!__imp_VariantCopy` at `0x100444ca0`
- `OLEAUT32!__imp_VariantCopy` at `0x100444c35`
- `OLEAUT32!__imp_VariantCopy` at `0x100444ca0`

## string_xrefs

- `0x1004449fa`: `spXMLDoc->load dumper configuration xml failed. hr=0x%x. Reason: %ls`
- `0x100444969`: `CoCreateInstance failed. hr=0x%x`
- `0x100444ae7`: `spXMLDoc->selectSingleNode failed to get element of [%ls] in configuration file. hr=0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=25
__int64 __fastcall DumperConfig::XmlElementReadOrModify(
        const wchar_t *psz,
        const wchar_t *a2,
        wchar_t *a3,
        unsigned __int16 a4,
        wchar_t *Buffer,
        unsigned __int16 a6,
        bool a7)
{
  const wchar_t *v8; // r12
  unsigned __int8 v10; // r14
  HRESULT v11; // eax
  char v12; // r15
  HRESULT v13; // eax
  unsigned __int16 v14; // si
  unsigned __int64 v15; // rbx
  int v16; // r12d
  __int16 v17; // cx
  int v18; // eax
  OLECHAR *v19; // rbx
  int v20; // eax
  int v21; // eax
  int v22; // eax
  HRESULT v23; // ecx
  unsigned __int8 updated; // al
  HRESULT v25; // ecx
  LPVOID *ppv; // [rsp+20h] [rbp-E0h]
  bool v28; // [rsp+40h] [rbp-C0h]
  __int16 v29; // [rsp+44h] [rbp-BCh] BYREF
  const wchar_t *v30; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 v31; // [rsp+50h] [rbp-B0h]
  LPVOID v32; // [rsp+58h] [rbp-A8h] BYREF
  const wchar_t *v33; // [rsp+60h] [rbp-A0h] BYREF
  BSTR bstrString; // [rsp+68h] [rbp-98h] BYREF
  __int64 v35; // [rsp+70h] [rbp-90h] BYREF
  BSTR v36; // [rsp+78h] [rbp-88h] BYREF
  VARIANTARG pvarg; // [rsp+80h] [rbp-80h] BYREF
  const wchar_t *v38; // [rsp+98h] [rbp-68h] BYREF
  LPVOID v39; // [rsp+A0h] [rbp-60h] BYREF
  LPVOID v40; // [rsp+A8h] [rbp-58h] BYREF
  const wchar_t **v41; // [rsp+B0h] [rbp-50h]
  const wchar_t **v42; // [rsp+B8h] [rbp-48h]
  VARIANTARG *p_pvargDest; // [rsp+C0h] [rbp-40h]
  VARIANTARG *v44; // [rsp+C8h] [rbp-38h]
  VARIANTARG pvargDest; // [rsp+D0h] [rbp-30h] BYREF
  VARIANTARG v46; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v47; // [rsp+100h] [rbp+0h]
  VARIANTARG v48; // [rsp+110h] [rbp+10h] BYREF
  OLECHAR psza[264]; // [rsp+130h] [rbp+30h] BYREF

  v47 = -2;
  v31 = a4;
  v8 = a2;
  v30 = a2;
  v28 = CoInitializeEx(0, 0) >= 0;
  v10 = 0;
  pvarg.vt = 0;
  v11 = VariantClear(&pvarg);
  if ( v11 < 0 )
  {
    _mm_lfence();
    ATL::AtlThrowImpl(v11);
  }
  pvarg.vt = 8;
  pvarg.llVal = (LONGLONG)SysAllocString(psz);
  if ( !pvarg.llVal && psz )
  {
    pvarg.vt = 10;
    pvarg.lVal = -2147024882;
    ATL::AtlThrowImpl(-2147024882);
  }
  v32 = 0;
  v29 = 0;
  v12 = 0;
  v33 = 0;
  v13 = CoCreateInstance(&CLSID_FreeThreadedDOMDocument60, 0, 1u, &IID_IXMLDOMDocument2, &v32);
  v14 = a6;
  v15 = a6;
  if ( v13 < 0 )
  {
    _mm_lfence();
    StringCchPrintfW(Buffer, a6, L"CoCreateInstance failed. hr=0x%x", (unsigned int)v13);
    goto LABEL_25;
  }
  v48 = pvarg;
  v16 = (*(__int64 (__fastcall **)(LPVOID, VARIANTARG *, __int16 *))(*(_QWORD *)v32 + 464LL))(v32, &v48, &v29);
  if ( v16 < 0 || (v17 = v29) == 0 )
  {
    v35 = 0;
    bstrString = 0;
    (*(void (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)v32 + 480LL))(v32, &v35);
    if ( v35 )
      (*(void (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v35 + 72LL))(v35, &bstrString);
    StringCchPrintfW(
      Buffer,
      a6,
      L"spXMLDoc->load dumper configuration xml failed. hr=0x%x. Reason: %ls",
      (unsigned int)v16,
      bstrString);
    SysFreeString(bstrString);
    if ( v35 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
    if ( v16 < 0 )
      goto LABEL_23;
    v17 = v29;
  }
  v15 = a6;
  if ( v17 == -1 )
  {
    memset_0(psza, 0, 0x208u);
    v8 = v30;
    v18 = StringCchPrintfW(psza, 0x104u, L"./%ls/%ls", L"SqlDumper", v30);
    if ( v18 >= 0 )
    {
      v19 = SysAllocString(psza);
      v41 = (const wchar_t **)v19;
      if ( !v19 )
        ATL::AtlThrowImpl(-2147024882);
      v20 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *, const wchar_t **))(*(_QWORD *)v32 + 296LL))(v32, v19, &v33);
      if ( v20 >= 0 && v33 )
      {
        v12 = 1;
      }
      else
      {
        LODWORD(ppv) = v20;
        StringCchPrintfW(
          Buffer,
          a6,
          L"spXMLDoc->selectSingleNode failed to get element of [%ls] in configuration file. hr=0x%x",
          psza,
          ppv);
      }
      SysFreeString(v19);
      v15 = a6;
    }
    else
    {
      _mm_lfence();
      LODWORD(ppv) = v18;
      StringCchPrintfW(Buffer, a6, L"StringCchPrintfW failed to construct element node name of %ls. hr=0x%x", psza, ppv);
    }
    goto LABEL_24;
  }
LABEL_23:
  v8 = v30;
LABEL_24:
  v14 = a6;
LABEL_25:
  if ( a7 )
  {
    if ( v12 )
    {
      v42 = &v38;
      p_pvargDest = &pvargDest;
      v44 = (VARIANTARG *)&v39;
      v38 = v33;
      if ( v33 )
        (*(void (__fastcall **)(const wchar_t *))(*(_QWORD *)v33 + 8LL))(v33);
      pvargDest.vt = 0;
      v23 = VariantCopy(&pvargDest, &pvarg);
      if ( v23 < 0 )
      {
        _mm_lfence();
        pvargDest.vt = 10;
        pvargDest.lVal = v23;
        ATL::AtlThrowImpl(v23);
      }
      _mm_lfence();
      v39 = v32;
      if ( v32 )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v32 + 8LL))(v32);
      updated = DumperConfig::UpdateXmlElement(&v39, &pvargDest, &v38, v8, a3, Buffer, v14);
    }
    else
    {
      v44 = &v46;
      p_pvargDest = (VARIANTARG *)&v40;
      v46.vt = 0;
      v25 = VariantCopy(&v46, &pvarg);
      if ( v25 < 0 )
      {
        _mm_lfence();
        v46.vt = 10;
        v46.lVal = v25;
        ATL::AtlThrowImpl(v25);
      }
      _mm_lfence();
      v40 = v32;
      if ( v32 )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v32 + 8LL))(v32);
      updated = DumperConfig::InsertXmlElement(&v40, &v46, v8, a3, Buffer, v14);
    }
    v10 = updated;
  }
  else if ( v12 )
  {
    v41 = &v30;
    v30 = v33;
    if ( v33 )
      (*(void (__fastcall **)(const wchar_t *))(*(_QWORD *)v33 + 8LL))(v33);
    v42 = &v30;
    v10 = 0;
    v36 = 0;
    v21 = (*(__int64 (__fastcall **)(const wchar_t *, BSTR *))(*(_QWORD *)v30 + 208LL))(v30, &v36);
    if ( v21 >= 0 )
    {
      v22 = StringCchPrintfW(a3, v31, L"%ls", v36);
      if ( v22 >= 0 )
      {
        v10 = 1;
      }
      else
      {
        _mm_lfence();
        StringCchPrintfW(
          Buffer,
          v15,
          L"StringCchPrintfW failed to save element value text . hr=0x%x. element value text:%ls",
          (unsigned int)v22,
          a3);
      }
    }
    else
    {
      _mm_lfence();
      StringCchPrintfW(Buffer, v15, L"node->get_text failed. hr=0x%x", (unsigned int)v21);
    }
    SysFreeString(v36);
    if ( v30 )
      (*(void (__fastcall **)(const wchar_t *))(*(_QWORD *)v30 + 16LL))(v30);
  }
  if ( v33 )
    (*(void (__fastcall **)(const wchar_t *))(*(_QWORD *)v33 + 16LL))(v33);
  if ( v32 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v32 + 16LL))(v32);
  VariantClear(&pvarg);
  if ( v28 )
    CoUninitialize();
  return v10;
}

```

## disassembly

```asm
0x100444870  push    rbp
0x100444872  push    rbx
0x100444873  push    rsi
0x100444874  push    rdi
0x100444875  push    r12
0x100444877  push    r13
0x100444879  push    r14
0x10044487b  push    r15
0x10044487d  lea     rbp, [rsp-258h]
0x100444885  sub     rsp, 358h
0x10044488c  mov     [rbp+290h+var_290], 0FFFFFFFFFFFFFFFEh
0x100444894  mov     rax, cs:__security_cookie
0x10044489b  xor     rax, rsp
0x10044489e  mov     [rbp+290h+var_50], rax
0x1004448a5  mov     [rsp+390h+var_340], r9w
0x1004448ab  mov     r13, r8
0x1004448ae  mov     r12, rdx
0x1004448b1  mov     [rsp+390h+var_348], rdx
0x1004448b6  mov     rsi, rcx
0x1004448b9  mov     rdi, [rbp+290h+Buffer]
0x1004448c0  xor     bl, bl
0x1004448c2  mov     [rsp+390h+var_350], bl
0x1004448c6  xor     edx, edx; dwCoInit
0x1004448c8  xor     ecx, ecx; pvReserved
0x1004448ca  call    cs:__imp_CoInitializeEx
0x1004448d0  movzx   ecx, bl
0x1004448d3  mov     edx, 1
0x1004448d8  test    eax, eax
0x1004448da  cmovns  ecx, edx
0x1004448dd  mov     [rsp+390h+var_350], cl
0x1004448e1  xor     r14b, r14b
0x1004448e4  xor     ebx, ebx
0x1004448e6  mov     word ptr [rbp+290h+pvarg], bx
0x1004448ea  lea     rcx, [rbp+290h+pvarg]; pvarg
0x1004448ee  call    cs:__imp_VariantClear
0x1004448f4  test    eax, eax
0x1004448f6  js      loc_100444D63
0x1004448fc  mov     eax, 8
0x100444901  mov     word ptr [rbp+290h+pvarg], ax
0x100444905  mov     rcx, rsi; psz
0x100444908  call    cs:__imp_SysAllocString
0x10044490e  mov     qword ptr [rbp+290h+pvarg+8], rax
0x100444912  test    rax, rax
0x100444915  jnz     short loc_100444920
0x100444917  test    rsi, rsi
0x10044491a  jnz     loc_100444D6E
0x100444920  mov     [rsp+390h+var_338], rbx
0x100444925  mov     [rsp+390h+var_34C], bx
0x10044492a  xor     r15b, r15b
0x10044492d  mov     [rsp+390h+var_330], rbx
0x100444932  lea     rax, [rsp+390h+var_338]
0x100444937  mov     [rsp+390h+ppv], rax; ppv
0x10044493c  lea     r9, IID_IXMLDOMDocument2; riid
0x100444943  xor     edx, edx; pUnkOuter
0x100444945  lea     r8d, [rdx+1]; dwClsContext
0x100444949  lea     rcx, CLSID_FreeThreadedDOMDocument60; rclsid
0x100444950  call    cs:__imp_CoCreateInstance
0x100444956  movzx   esi, [rbp+290h+arg_28]
0x10044495d  mov     ebx, esi
0x10044495f  test    eax, eax
0x100444961  jns     short loc_10044497F
0x100444963  lfence
0x100444966  mov     r9d, eax
0x100444969  lea     r8, aCocreateinstan; "CoCreateInstance failed. hr=0x%x"
0x100444970  mov     edx, ebx; unsigned __int64
0x100444972  mov     rcx, rdi; Buffer
0x100444975  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x10044497a  jmp     loc_100444B14
0x10044497f  movups  xmm0, xmmword ptr [rbp+290h+pvarg]
0x100444983  movaps  [rbp+290h+var_280], xmm0
0x100444987  movsd   xmm1, qword ptr [rbp+290h+pvarg+10h]
0x10044498c  movsd   [rbp+290h+var_270], xmm1
0x100444991  mov     rcx, [rsp+390h+var_338]
0x100444996  mov     rax, [rcx]
0x100444999  lea     r8, [rsp+390h+var_34C]
0x10044499e  lea     rdx, [rbp+290h+var_280]
0x1004449a2  call    qword ptr [rax+1D0h]
0x1004449a8  mov     r12d, eax
0x1004449ab  test    eax, eax
0x1004449ad  js      short loc_1004449B9
0x1004449af  movzx   ecx, [rsp+390h+var_34C]
0x1004449b4  test    cx, cx
0x1004449b7  jnz     short loc_100444A37
0x1004449b9  xor     eax, eax
0x1004449bb  mov     [rsp+390h+var_320], rax
0x1004449c0  mov     [rsp+390h+bstrString], rax
0x1004449c5  mov     rcx, [rsp+390h+var_338]
0x1004449ca  mov     rax, [rcx]
0x1004449cd  lea     rdx, [rsp+390h+var_320]
0x1004449d2  call    qword ptr [rax+1E0h]
0x1004449d8  mov     rcx, [rsp+390h+var_320]
0x1004449dd  test    rcx, rcx
0x1004449e0  jz      short loc_1004449ED
0x1004449e2  mov     rax, [rcx]
0x1004449e5  lea     rdx, [rsp+390h+bstrString]
0x1004449ea  call    qword ptr [rax+48h]
0x1004449ed  mov     rax, [rsp+390h+bstrString]
0x1004449f2  mov     [rsp+390h+ppv], rax
0x1004449f7  mov     r9d, r12d
0x1004449fa  lea     r8, aSpxmldocLoadDu; "spXMLDoc->load dumper configuration xml"...
0x100444a01  mov     rdx, rbx; unsigned __int64
0x100444a04  mov     rcx, rdi; Buffer
0x100444a07  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x100444a0c  nop
0x100444a0d  mov     rcx, [rsp+390h+bstrString]; bstrString
0x100444a12  call    cs:__imp_SysFreeString
0x100444a18  nop
0x100444a19  mov     rcx, [rsp+390h+var_320]
0x100444a1e  test    rcx, rcx
0x100444a21  jz      short loc_100444A29
0x100444a23  mov     rax, [rcx]
0x100444a26  call    qword ptr [rax+10h]
0x100444a29  test    r12d, r12d
0x100444a2c  js      loc_100444B08
0x100444a32  movzx   ecx, [rsp+390h+var_34C]
0x100444a37  mov     rbx, rsi
0x100444a3a  cmp     cx, 0FFFFh
0x100444a3e  jnz     loc_100444B08
0x100444a44  xor     edx, edx; Val
0x100444a46  mov     r8d, 208h; Size
0x100444a4c  lea     rcx, [rbp+290h+psz]; void *
0x100444a50  call    memset_0
0x100444a55  mov     r12, [rsp+390h+var_348]
0x100444a5a  mov     [rsp+390h+ppv], r12
0x100444a5f  lea     r9, aSqldumper_0; "SqlDumper"
0x100444a66  lea     r8, aLsLs_0; "./%ls/%ls"
0x100444a6d  mov     edx, 104h; unsigned __int64
0x100444a72  lea     rcx, [rbp+290h+psz]; Buffer
0x100444a76  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x100444a7b  test    eax, eax
0x100444a7d  jns     short loc_100444A9E
0x100444a7f  lfence
0x100444a82  mov     dword ptr [rsp+390h+ppv], eax
0x100444a86  lea     r9, [rbp+290h+psz]
0x100444a8a  lea     r8, aStringcchprint_0; "StringCchPrintfW failed to construct el"...
0x100444a91  mov     rdx, rsi; unsigned __int64
0x100444a94  mov     rcx, rdi; Buffer
0x100444a97  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x100444a9c  jmp     short loc_100444B0D
0x100444a9e  lea     rcx, [rbp+290h+psz]; psz
0x100444aa2  call    cs:__imp_SysAllocString
0x100444aa8  mov     rbx, rax
0x100444aab  mov     [rbp+290h+var_2E0], rax
0x100444aaf  test    rax, rax
0x100444ab2  jz      loc_100444D8D
0x100444ab8  mov     rcx, [rsp+390h+var_338]
0x100444abd  mov     rax, [rcx]
0x100444ac0  lea     r8, [rsp+390h+var_330]
0x100444ac5  mov     rdx, rbx
0x100444ac8  call    qword ptr [rax+128h]
0x100444ace  test    eax, eax
0x100444ad0  js      short loc_100444ADF
0x100444ad2  cmp     [rsp+390h+var_330], 0
0x100444ad8  jz      short loc_100444ADF
0x100444ada  mov     r15b, 1
0x100444add  jmp     short loc_100444AFA
0x100444adf  mov     dword ptr [rsp+390h+ppv], eax
0x100444ae3  lea     r9, [rbp+290h+psz]
0x100444ae7  lea     r8, aSpxmldocSelect_0; "spXMLDoc->selectSingleNode failed to ge"...
0x100444aee  mov     rdx, rsi; unsigned __int64
0x100444af1  mov     rcx, rdi; Buffer
0x100444af4  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x100444af9  nop
0x100444afa  mov     rcx, rbx; bstrString
0x100444afd  call    cs:__imp_SysFreeString
0x100444b03  mov     rbx, rsi
0x100444b06  jmp     short loc_100444B0D
0x100444b08  mov     r12, [rsp+390h+var_348]
0x100444b0d  movzx   esi, [rbp+290h+arg_28]
0x100444b14  cmp     [rbp+290h+arg_30], 0
0x100444b1b  jnz     loc_100444BF1
0x100444b21  test    r15b, r15b
0x100444b24  jz      loc_100444CE9
0x100444b2a  lea     rax, [rsp+390h+var_348]
0x100444b2f  mov     [rbp+290h+var_2E0], rax
0x100444b33  mov     rcx, [rsp+390h+var_330]
0x100444b38  mov     [rsp+390h+var_348], rcx
0x100444b3d  test    rcx, rcx
0x100444b40  jz      short loc_100444B49
0x100444b42  mov     rax, [rcx]
0x100444b45  call    qword ptr [rax+8]
0x100444b48  nop
0x100444b49  lea     rax, [rsp+390h+var_348]
0x100444b4e  mov     [rbp+290h+var_2D8], rax
0x100444b52  xor     r14b, r14b
0x100444b55  xor     eax, eax
0x100444b57  mov     [rsp+390h+var_318], rax
0x100444b5c  mov     rcx, [rsp+390h+var_348]
0x100444b61  mov     rax, [rcx]
0x100444b64  lea     rdx, [rsp+390h+var_318]
0x100444b69  call    qword ptr [rax+0D0h]
0x100444b6f  test    eax, eax
0x100444b71  jns     short loc_100444B8D
0x100444b73  lfence
0x100444b76  mov     r9d, eax
0x100444b79  lea     r8, aNodeGetTextFai; "node->get_text failed. hr=0x%x"
0x100444b80  mov     rdx, rbx; unsigned __int64
0x100444b83  mov     rcx, rdi; Buffer
0x100444b86  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x100444b8b  jmp     short loc_100444BCC
0x100444b8d  movzx   edx, [rsp+390h+var_340]; unsigned __int64
0x100444b92  mov     r9, [rsp+390h+var_318]
0x100444b97  lea     r8, aLs; "%ls"
0x100444b9e  mov     rcx, r13; Buffer
0x100444ba1  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x100444ba6  test    eax, eax
0x100444ba8  jns     short loc_100444BC9
0x100444baa  lfence
0x100444bad  mov     [rsp+390h+ppv], r13
0x100444bb2  mov     r9d, eax
0x100444bb5  lea     r8, aStringcchprint_1; "StringCchPrintfW failed to save element"...
0x100444bbc  mov     rdx, rbx; unsigned __int64
0x100444bbf  mov     rcx, rdi; Buffer
0x100444bc2  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x100444bc7  jmp     short loc_100444BCC
0x100444bc9  mov     r14b, 1
0x100444bcc  mov     rcx, [rsp+390h+var_318]; bstrString
0x100444bd1  call    cs:__imp_SysFreeString
0x100444bd7  nop
0x100444bd8  mov     rcx, [rsp+390h+var_348]
0x100444bdd  test    rcx, rcx
0x100444be0  jz      loc_100444CE9
0x100444be6  mov     rax, [rcx]
0x100444be9  call    qword ptr [rax+10h]
0x100444bec  jmp     loc_100444CE9
0x100444bf1  test    r15b, r15b
0x100444bf4  jz      loc_100444C82
0x100444bfa  lea     rax, [rbp+290h+var_2F8]
0x100444bfe  mov     [rbp+290h+var_2D8], rax
0x100444c02  lea     rax, [rbp+290h+pvargDest]
0x100444c06  mov     [rbp+290h+var_2D0], rax
0x100444c0a  lea     rax, [rbp+290h+var_2F0]
0x100444c0e  mov     [rbp+290h+var_2C8], rax
0x100444c12  mov     rcx, [rsp+390h+var_330]
0x100444c17  mov     [rbp+290h+var_2F8], rcx
0x100444c1b  test    rcx, rcx
0x100444c1e  jz      short loc_100444C27
0x100444c20  mov     rax, [rcx]
0x100444c23  call    qword ptr [rax+8]
0x100444c26  nop
0x100444c27  xor     eax, eax
0x100444c29  mov     word ptr [rbp+290h+pvargDest], ax
0x100444c2d  lea     rdx, [rbp+290h+pvarg]; pvargSrc
0x100444c31  lea     rcx, [rbp+290h+pvargDest]; pvargDest
0x100444c35  call    cs:__imp_VariantCopy
0x100444c3b  mov     ecx, eax
0x100444c3d  test    eax, eax
0x100444c3f  js      loc_100444D9B
0x100444c45  lfence
0x100444c48  mov     rcx, [rsp+390h+var_338]
0x100444c4d  mov     [rbp+290h+var_2F0], rcx
0x100444c51  test    rcx, rcx
0x100444c54  jz      short loc_100444C5D
0x100444c56  mov     rax, [rcx]
0x100444c59  call    qword ptr [rax+8]
0x100444c5c  nop
0x100444c5d  mov     [rsp+390h+var_360], si
0x100444c62  mov     [rsp+390h+var_368], rdi
0x100444c67  mov     [rsp+390h+ppv], r13
0x100444c6c  mov     r9, r12
0x100444c6f  lea     r8, [rbp+290h+var_2F8]
0x100444c73  lea     rdx, [rbp+290h+pvargDest]
0x100444c77  lea     rcx, [rbp+290h+var_2F0]
0x100444c7b  call    ?UpdateXmlElement@DumperConfig@@CA_NV?$CComPtr@UIXMLDOMDocument2@@@ATL@@VCComVariant@3@V?$CComPtr@UIXMLDOMNode@@@3@PEB_W3PEA_WG@Z; DumperConfig::UpdateXmlElement(ATL::CComPtr<IXMLDOMDocument2>,ATL::CComVariant,ATL::CComPtr<IXMLDOMNode>,wchar_t const *,wchar_t const *,wchar_t *,ushort)
0x100444c80  jmp     short loc_100444CE5
0x100444c82  lea     rax, [rbp+290h+var_2A8]
0x100444c86  mov     [rbp+290h+var_2C8], rax
0x100444c8a  lea     rax, [rbp+290h+var_2E8]
0x100444c8e  mov     [rbp+290h+var_2D0], rax
0x100444c92  xor     eax, eax
0x100444c94  mov     word ptr [rbp+290h+var_2A8], ax
0x100444c98  lea     rdx, [rbp+290h+pvarg]; pvargSrc
0x100444c9c  lea     rcx, [rbp+290h+var_2A8]; pvargDest
0x100444ca0  call    cs:__imp_VariantCopy
0x100444ca6  mov     ecx, eax; int
0x100444ca8  test    eax, eax
0x100444caa  js      loc_100444D4A
0x100444cb0  lfence
0x100444cb3  mov     rcx, [rsp+390h+var_338]
0x100444cb8  mov     [rbp+290h+var_2E8], rcx
0x100444cbc  test    rcx, rcx
0x100444cbf  jz      short loc_100444CC8
0x100444cc1  mov     rax, [rcx]
0x100444cc4  call    qword ptr [rax+8]
0x100444cc7  nop
0x100444cc8  mov     word ptr [rsp+390h+var_368], si
0x100444ccd  mov     [rsp+390h+ppv], rdi
0x100444cd2  mov     r9, r13
0x100444cd5  mov     r8, r12
0x100444cd8  lea     rdx, [rbp+290h+var_2A8]
0x100444cdc  lea     rcx, [rbp+290h+var_2E8]
0x100444ce0  call    ?InsertXmlElement@DumperConfig@@CA_NV?$CComPtr@UIXMLDOMDocument2@@@ATL@@VCComVariant@3@PEB_W2PEA_WG@Z; DumperConfig::InsertXmlElement(ATL::CComPtr<IXMLDOMDocument2>,ATL::CComVariant,wchar_t const *,wchar_t const *,wchar_t *,ushort)
0x100444ce5  movzx   r14d, al
0x100444ce9  mov     rcx, [rsp+390h+var_330]
0x100444cee  test    rcx, rcx
0x100444cf1  jz      short loc_100444CFA
0x100444cf3  mov     rax, [rcx]
0x100444cf6  call    qword ptr [rax+10h]
0x100444cf9  nop
0x100444cfa  mov     rcx, [rsp+390h+var_338]
  ... truncated ...
```
