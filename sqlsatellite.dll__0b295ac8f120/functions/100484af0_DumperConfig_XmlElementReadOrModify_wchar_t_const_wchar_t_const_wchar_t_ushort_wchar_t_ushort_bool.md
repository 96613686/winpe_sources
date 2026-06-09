# DumperConfig::XmlElementReadOrModify(wchar_t const *,wchar_t const *,wchar_t *,ushort,wchar_t *,ushort,bool)

- ea: `0x100484af0`
- end: `0x100485025`
- name: `?XmlElementReadOrModify@DumperConfig@@CA_NPEB_W0PEA_WG1G_N@Z`
- size: `1333`
- prototype: `bool __usercall@<al>(const wchar_t *psz@<rcx>, const wchar_t *@<rdx>, wchar_t *@<r8>, unsigned __int16@<r9w>, wchar_t *, unsigned __int16, bool)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x100483630`

## callees

- `0x10040d8a0`
- `0x100484830`
- `0x100484af0`
- `0x100485060`
- `0x100485230`
- `0x100486af0`
- `0x100487cd6`

## import_xrefs

- `ole32!CoInitializeEx` at `0x100484b4a`
- `ole32!CoInitializeEx` at `0x100484b4a`
- `ole32!CoUninitialize` at `0x100484f9d`
- `ole32!CoUninitialize` at `0x100484f9d`
- `ole32!CoCreateInstance` at `0x100484bd0`
- `ole32!CoCreateInstance` at `0x100484bd0`
- `OLEAUT32!__imp_SysAllocString` at `0x100484b88`
- `OLEAUT32!__imp_SysAllocString` at `0x100484d22`
- `OLEAUT32!__imp_SysAllocString` at `0x100484b88`
- `OLEAUT32!__imp_SysAllocString` at `0x100484d22`
- `OLEAUT32!__imp_SysFreeString` at `0x100484c92`
- `OLEAUT32!__imp_SysFreeString` at `0x100484d7d`
- `OLEAUT32!__imp_SysFreeString` at `0x100484e51`
- `OLEAUT32!__imp_SysFreeString` at `0x100484c92`
- `OLEAUT32!__imp_SysFreeString` at `0x100484d7d`
- `OLEAUT32!__imp_SysFreeString` at `0x100484e51`
- `OLEAUT32!__imp_VariantClear` at `0x100484b6e`
- `OLEAUT32!__imp_VariantClear` at `0x100484f8f`
- `OLEAUT32!__imp_VariantClear` at `0x100484b6e`
- `OLEAUT32!__imp_VariantClear` at `0x100484f8f`
- `OLEAUT32!__imp_VariantCopy` at `0x100484eb5`
- `OLEAUT32!__imp_VariantCopy` at `0x100484f20`
- `OLEAUT32!__imp_VariantCopy` at `0x100484eb5`
- `OLEAUT32!__imp_VariantCopy` at `0x100484f20`

## string_xrefs

- `0x100484d67`: `spXMLDoc->selectSingleNode failed to get element of [%ls] in configuration file. hr=0x%x`
- `0x100484be9`: `CoCreateInstance failed. hr=0x%x`
- `0x100484c7a`: `spXMLDoc->load dumper configuration xml failed. hr=0x%x. Reason: %ls`

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
0x100484af0  push    rbp
0x100484af2  push    rbx
0x100484af3  push    rsi
0x100484af4  push    rdi
0x100484af5  push    r12
0x100484af7  push    r13
0x100484af9  push    r14
0x100484afb  push    r15
0x100484afd  lea     rbp, [rsp-258h]
0x100484b05  sub     rsp, 358h
0x100484b0c  mov     [rbp+290h+var_290], 0FFFFFFFFFFFFFFFEh
0x100484b14  mov     rax, cs:__security_cookie
0x100484b1b  xor     rax, rsp
0x100484b1e  mov     [rbp+290h+var_50], rax
0x100484b25  mov     [rsp+390h+var_340], r9w
0x100484b2b  mov     r13, r8
0x100484b2e  mov     r12, rdx
0x100484b31  mov     [rsp+390h+var_348], rdx
0x100484b36  mov     rsi, rcx
0x100484b39  mov     rdi, [rbp+290h+Buffer]
0x100484b40  xor     bl, bl
0x100484b42  mov     [rsp+390h+var_350], bl
0x100484b46  xor     edx, edx; dwCoInit
0x100484b48  xor     ecx, ecx; pvReserved
0x100484b4a  call    cs:__imp_CoInitializeEx
0x100484b50  movzx   ecx, bl
0x100484b53  mov     edx, 1
0x100484b58  test    eax, eax
0x100484b5a  cmovns  ecx, edx
0x100484b5d  mov     [rsp+390h+var_350], cl
0x100484b61  xor     r14b, r14b
0x100484b64  xor     ebx, ebx
0x100484b66  mov     word ptr [rbp+290h+pvarg], bx
0x100484b6a  lea     rcx, [rbp+290h+pvarg]; pvarg
0x100484b6e  call    cs:__imp_VariantClear
0x100484b74  test    eax, eax
0x100484b76  js      loc_100484FDF
0x100484b7c  mov     eax, 8
0x100484b81  mov     word ptr [rbp+290h+pvarg], ax
0x100484b85  mov     rcx, rsi; psz
0x100484b88  call    cs:__imp_SysAllocString
0x100484b8e  mov     qword ptr [rbp+290h+pvarg+8], rax
0x100484b92  test    rax, rax
0x100484b95  jnz     short loc_100484BA0
0x100484b97  test    rsi, rsi
0x100484b9a  jnz     loc_100484FEA
0x100484ba0  mov     [rsp+390h+var_338], rbx
0x100484ba5  mov     [rsp+390h+var_34C], bx
0x100484baa  xor     r15b, r15b
0x100484bad  mov     [rsp+390h+var_330], rbx
0x100484bb2  lea     rax, [rsp+390h+var_338]
0x100484bb7  mov     [rsp+390h+ppv], rax; ppv
0x100484bbc  lea     r9, IID_IXMLDOMDocument2; riid
0x100484bc3  xor     edx, edx; pUnkOuter
0x100484bc5  lea     r8d, [rdx+1]; dwClsContext
0x100484bc9  lea     rcx, CLSID_FreeThreadedDOMDocument60; rclsid
0x100484bd0  call    cs:__imp_CoCreateInstance
0x100484bd6  movzx   esi, [rbp+290h+arg_28]
0x100484bdd  mov     ebx, esi
0x100484bdf  test    eax, eax
0x100484be1  jns     short loc_100484BFF
0x100484be3  lfence
0x100484be6  mov     r9d, eax
0x100484be9  lea     r8, aCocreateinstan; "CoCreateInstance failed. hr=0x%x"
0x100484bf0  mov     edx, ebx; unsigned __int64
0x100484bf2  mov     rcx, rdi; Buffer
0x100484bf5  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x100484bfa  jmp     loc_100484D94
0x100484bff  movups  xmm0, xmmword ptr [rbp+290h+pvarg]
0x100484c03  movaps  [rbp+290h+var_280], xmm0
0x100484c07  movsd   xmm1, qword ptr [rbp+290h+pvarg+10h]
0x100484c0c  movsd   [rbp+290h+var_270], xmm1
0x100484c11  mov     rcx, [rsp+390h+var_338]
0x100484c16  mov     rax, [rcx]
0x100484c19  lea     r8, [rsp+390h+var_34C]
0x100484c1e  lea     rdx, [rbp+290h+var_280]
0x100484c22  call    qword ptr [rax+1D0h]
0x100484c28  mov     r12d, eax
0x100484c2b  test    eax, eax
0x100484c2d  js      short loc_100484C39
0x100484c2f  movzx   ecx, [rsp+390h+var_34C]
0x100484c34  test    cx, cx
0x100484c37  jnz     short loc_100484CB7
0x100484c39  xor     eax, eax
0x100484c3b  mov     [rsp+390h+var_320], rax
0x100484c40  mov     [rsp+390h+bstrString], rax
0x100484c45  mov     rcx, [rsp+390h+var_338]
0x100484c4a  mov     rax, [rcx]
0x100484c4d  lea     rdx, [rsp+390h+var_320]
0x100484c52  call    qword ptr [rax+1E0h]
0x100484c58  mov     rcx, [rsp+390h+var_320]
0x100484c5d  test    rcx, rcx
0x100484c60  jz      short loc_100484C6D
0x100484c62  mov     rax, [rcx]
0x100484c65  lea     rdx, [rsp+390h+bstrString]
0x100484c6a  call    qword ptr [rax+48h]
0x100484c6d  mov     rax, [rsp+390h+bstrString]
0x100484c72  mov     [rsp+390h+ppv], rax
0x100484c77  mov     r9d, r12d
0x100484c7a  lea     r8, aSpxmldocLoadDu; "spXMLDoc->load dumper configuration xml"...
0x100484c81  mov     rdx, rbx; unsigned __int64
0x100484c84  mov     rcx, rdi; Buffer
0x100484c87  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x100484c8c  nop
0x100484c8d  mov     rcx, [rsp+390h+bstrString]; bstrString
0x100484c92  call    cs:__imp_SysFreeString
0x100484c98  nop
0x100484c99  mov     rcx, [rsp+390h+var_320]
0x100484c9e  test    rcx, rcx
0x100484ca1  jz      short loc_100484CA9
0x100484ca3  mov     rax, [rcx]
0x100484ca6  call    qword ptr [rax+10h]
0x100484ca9  test    r12d, r12d
0x100484cac  js      loc_100484D88
0x100484cb2  movzx   ecx, [rsp+390h+var_34C]
0x100484cb7  mov     rbx, rsi
0x100484cba  cmp     cx, 0FFFFh
0x100484cbe  jnz     loc_100484D88
0x100484cc4  xor     edx, edx; Val
0x100484cc6  mov     r8d, 208h; Size
0x100484ccc  lea     rcx, [rbp+290h+psz]; void *
0x100484cd0  call    memset_0
0x100484cd5  mov     r12, [rsp+390h+var_348]
0x100484cda  mov     [rsp+390h+ppv], r12
0x100484cdf  lea     r9, aSqldumper_0; "SqlDumper"
0x100484ce6  lea     r8, aLsLs; "./%ls/%ls"
0x100484ced  mov     edx, 104h; unsigned __int64
0x100484cf2  lea     rcx, [rbp+290h+psz]; Buffer
0x100484cf6  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x100484cfb  test    eax, eax
0x100484cfd  jns     short loc_100484D1E
0x100484cff  lfence
0x100484d02  mov     dword ptr [rsp+390h+ppv], eax
0x100484d06  lea     r9, [rbp+290h+psz]
0x100484d0a  lea     r8, aStringcchprint_0; "StringCchPrintfW failed to construct el"...
0x100484d11  mov     rdx, rsi; unsigned __int64
0x100484d14  mov     rcx, rdi; Buffer
0x100484d17  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x100484d1c  jmp     short loc_100484D8D
0x100484d1e  lea     rcx, [rbp+290h+psz]; psz
0x100484d22  call    cs:__imp_SysAllocString
0x100484d28  mov     rbx, rax
0x100484d2b  mov     [rbp+290h+var_2E0], rax
0x100484d2f  test    rax, rax
0x100484d32  jz      loc_100485005
0x100484d38  mov     rcx, [rsp+390h+var_338]
0x100484d3d  mov     rax, [rcx]
0x100484d40  lea     r8, [rsp+390h+var_330]
0x100484d45  mov     rdx, rbx
0x100484d48  call    qword ptr [rax+128h]
0x100484d4e  test    eax, eax
0x100484d50  js      short loc_100484D5F
0x100484d52  cmp     [rsp+390h+var_330], 0
0x100484d58  jz      short loc_100484D5F
0x100484d5a  mov     r15b, 1
0x100484d5d  jmp     short loc_100484D7A
0x100484d5f  mov     dword ptr [rsp+390h+ppv], eax
0x100484d63  lea     r9, [rbp+290h+psz]
0x100484d67  lea     r8, aSpxmldocSelect_0; "spXMLDoc->selectSingleNode failed to ge"...
0x100484d6e  mov     rdx, rsi; unsigned __int64
0x100484d71  mov     rcx, rdi; Buffer
0x100484d74  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x100484d79  nop
0x100484d7a  mov     rcx, rbx; bstrString
0x100484d7d  call    cs:__imp_SysFreeString
0x100484d83  mov     rbx, rsi
0x100484d86  jmp     short loc_100484D8D
0x100484d88  mov     r12, [rsp+390h+var_348]
0x100484d8d  movzx   esi, [rbp+290h+arg_28]
0x100484d94  cmp     [rbp+290h+arg_30], 0
0x100484d9b  jnz     loc_100484E71
0x100484da1  test    r15b, r15b
0x100484da4  jz      loc_100484F69
0x100484daa  lea     rax, [rsp+390h+var_348]
0x100484daf  mov     [rbp+290h+var_2E0], rax
0x100484db3  mov     rcx, [rsp+390h+var_330]
0x100484db8  mov     [rsp+390h+var_348], rcx
0x100484dbd  test    rcx, rcx
0x100484dc0  jz      short loc_100484DC9
0x100484dc2  mov     rax, [rcx]
0x100484dc5  call    qword ptr [rax+8]
0x100484dc8  nop
0x100484dc9  lea     rax, [rsp+390h+var_348]
0x100484dce  mov     [rbp+290h+var_2D8], rax
0x100484dd2  xor     r14b, r14b
0x100484dd5  xor     eax, eax
0x100484dd7  mov     [rsp+390h+var_318], rax
0x100484ddc  mov     rcx, [rsp+390h+var_348]
0x100484de1  mov     rax, [rcx]
0x100484de4  lea     rdx, [rsp+390h+var_318]
0x100484de9  call    qword ptr [rax+0D0h]
0x100484def  test    eax, eax
0x100484df1  jns     short loc_100484E0D
0x100484df3  lfence
0x100484df6  mov     r9d, eax
0x100484df9  lea     r8, aNodeGetTextFai; "node->get_text failed. hr=0x%x"
0x100484e00  mov     rdx, rbx; unsigned __int64
0x100484e03  mov     rcx, rdi; Buffer
0x100484e06  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x100484e0b  jmp     short loc_100484E4C
0x100484e0d  movzx   edx, [rsp+390h+var_340]; unsigned __int64
0x100484e12  mov     r9, [rsp+390h+var_318]
0x100484e17  lea     r8, aLs_0; "%ls"
0x100484e1e  mov     rcx, r13; Buffer
0x100484e21  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x100484e26  test    eax, eax
0x100484e28  jns     short loc_100484E49
0x100484e2a  lfence
0x100484e2d  mov     [rsp+390h+ppv], r13
0x100484e32  mov     r9d, eax
0x100484e35  lea     r8, aStringcchprint_1; "StringCchPrintfW failed to save element"...
0x100484e3c  mov     rdx, rbx; unsigned __int64
0x100484e3f  mov     rcx, rdi; Buffer
0x100484e42  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x100484e47  jmp     short loc_100484E4C
0x100484e49  mov     r14b, 1
0x100484e4c  mov     rcx, [rsp+390h+var_318]; bstrString
0x100484e51  call    cs:__imp_SysFreeString
0x100484e57  nop
0x100484e58  mov     rcx, [rsp+390h+var_348]
0x100484e5d  test    rcx, rcx
0x100484e60  jz      loc_100484F69
0x100484e66  mov     rax, [rcx]
0x100484e69  call    qword ptr [rax+10h]
0x100484e6c  jmp     loc_100484F69
0x100484e71  test    r15b, r15b
0x100484e74  jz      loc_100484F02
0x100484e7a  lea     rax, [rbp+290h+var_2F8]
0x100484e7e  mov     [rbp+290h+var_2D8], rax
0x100484e82  lea     rax, [rbp+290h+pvargDest]
0x100484e86  mov     [rbp+290h+var_2D0], rax
0x100484e8a  lea     rax, [rbp+290h+var_2F0]
0x100484e8e  mov     [rbp+290h+var_2C8], rax
0x100484e92  mov     rcx, [rsp+390h+var_330]
0x100484e97  mov     [rbp+290h+var_2F8], rcx
0x100484e9b  test    rcx, rcx
0x100484e9e  jz      short loc_100484EA7
0x100484ea0  mov     rax, [rcx]
0x100484ea3  call    qword ptr [rax+8]
0x100484ea6  nop
0x100484ea7  xor     eax, eax
0x100484ea9  mov     word ptr [rbp+290h+pvargDest], ax
0x100484ead  lea     rdx, [rbp+290h+pvarg]; pvargSrc
0x100484eb1  lea     rcx, [rbp+290h+pvargDest]; pvargDest
0x100484eb5  call    cs:__imp_VariantCopy
0x100484ebb  mov     ecx, eax; int
0x100484ebd  test    eax, eax
0x100484ebf  js      loc_100485010
0x100484ec5  lfence
0x100484ec8  mov     rcx, [rsp+390h+var_338]
0x100484ecd  mov     [rbp+290h+var_2F0], rcx
0x100484ed1  test    rcx, rcx
0x100484ed4  jz      short loc_100484EDD
0x100484ed6  mov     rax, [rcx]
0x100484ed9  call    qword ptr [rax+8]
0x100484edc  nop
0x100484edd  mov     [rsp+390h+var_360], si
0x100484ee2  mov     [rsp+390h+var_368], rdi
0x100484ee7  mov     [rsp+390h+ppv], r13
0x100484eec  mov     r9, r12
0x100484eef  lea     r8, [rbp+290h+var_2F8]
0x100484ef3  lea     rdx, [rbp+290h+pvargDest]
0x100484ef7  lea     rcx, [rbp+290h+var_2F0]
0x100484efb  call    ?UpdateXmlElement@DumperConfig@@CA_NV?$CComPtr@UIXMLDOMDocument2@@@ATL@@VCComVariant@3@V?$CComPtr@UIXMLDOMNode@@@3@PEB_W3PEA_WG@Z; DumperConfig::UpdateXmlElement(ATL::CComPtr<IXMLDOMDocument2>,ATL::CComVariant,ATL::CComPtr<IXMLDOMNode>,wchar_t const *,wchar_t const *,wchar_t *,ushort)
0x100484f00  jmp     short loc_100484F65
0x100484f02  lea     rax, [rbp+290h+var_2A8]
0x100484f06  mov     [rbp+290h+var_2C8], rax
0x100484f0a  lea     rax, [rbp+290h+var_2E8]
0x100484f0e  mov     [rbp+290h+var_2D0], rax
0x100484f12  xor     eax, eax
0x100484f14  mov     word ptr [rbp+290h+var_2A8], ax
0x100484f18  lea     rdx, [rbp+290h+pvarg]; pvargSrc
0x100484f1c  lea     rcx, [rbp+290h+var_2A8]; pvargDest
0x100484f20  call    cs:__imp_VariantCopy
0x100484f26  mov     ecx, eax; int
0x100484f28  test    eax, eax
0x100484f2a  js      loc_100484FCA
0x100484f30  lfence
0x100484f33  mov     rcx, [rsp+390h+var_338]
0x100484f38  mov     [rbp+290h+var_2E8], rcx
0x100484f3c  test    rcx, rcx
0x100484f3f  jz      short loc_100484F48
0x100484f41  mov     rax, [rcx]
0x100484f44  call    qword ptr [rax+8]
0x100484f47  nop
0x100484f48  mov     word ptr [rsp+390h+var_368], si
0x100484f4d  mov     [rsp+390h+ppv], rdi
0x100484f52  mov     r9, r13
0x100484f55  mov     r8, r12
0x100484f58  lea     rdx, [rbp+290h+var_2A8]
0x100484f5c  lea     rcx, [rbp+290h+var_2E8]
0x100484f60  call    ?InsertXmlElement@DumperConfig@@CA_NV?$CComPtr@UIXMLDOMDocument2@@@ATL@@VCComVariant@3@PEB_W2PEA_WG@Z; DumperConfig::InsertXmlElement(ATL::CComPtr<IXMLDOMDocument2>,ATL::CComVariant,wchar_t const *,wchar_t const *,wchar_t *,ushort)
0x100484f65  movzx   r14d, al
0x100484f69  mov     rcx, [rsp+390h+var_330]
0x100484f6e  test    rcx, rcx
0x100484f71  jz      short loc_100484F7A
0x100484f73  mov     rax, [rcx]
0x100484f76  call    qword ptr [rax+10h]
0x100484f79  nop
0x100484f7a  mov     rcx, [rsp+390h+var_338]
  ... truncated ...
```
