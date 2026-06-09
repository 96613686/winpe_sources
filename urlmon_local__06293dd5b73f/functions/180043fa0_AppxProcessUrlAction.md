# AppxProcessUrlAction

- ea: `0x180043fa0`
- end: `0x180044785`
- name: `AppxProcessUrlAction`
- size: `2021`
- prototype: `__int64 __usercall@<rax>(struct IWebPlatformAppContext *@<rcx>, STRSAFE_PCNZWCH psz, unsigned __int8 *, int, struct IUri *, __int64, AppProtocolsCommon *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180043d70`

## callees

- `0x180008b2c`
- `0x180043370`
- `0x180043958`
- `0x180043fa0`
- `0x180044790`
- `0x180044e38`
- `0x180044f18`
- `0x180045310`
- `0x180045354`
- `0x180064f50`
- `0x180065f44`
- `0x18006cf6c`
- `0x18006d168`
- `0x18008c33c`
- `0x1800a25dc`
- `0x180115220`
- `0x180129010`

## import_xrefs

- `iertutil!CreateUri` at `0x180044409`
- `iertutil!CreateUri` at `0x1800446a3`
- `iertutil!CreateUri` at `0x180044409`
- `iertutil!CreateUri` at `0x1800446a3`
- `OLEAUT32!__imp_SysFreeString` at `0x1800441a1`
- `OLEAUT32!__imp_SysFreeString` at `0x180044217`
- `OLEAUT32!__imp_SysFreeString` at `0x1800443ad`
- `OLEAUT32!__imp_SysFreeString` at `0x1800441a1`
- `OLEAUT32!__imp_SysFreeString` at `0x180044217`
- `OLEAUT32!__imp_SysFreeString` at `0x1800443ad`

## string_xrefs

- `0x180044068`: `onecoreuap\inetcore\lib\appprotocols\appxprocessurlaction.cpp`
- `0x180044087`: `onecoreuap\inetcore\lib\appprotocols\appxprocessurlaction.cpp`
- `0x1800440f9`: `onecoreuap\inetcore\lib\appprotocols\appxprocessurlaction.cpp`
- `0x180044134`: `onecoreuap\inetcore\lib\appprotocols\appxprocessurlaction.cpp`
- `0x180044455`: `onecoreuap\inetcore\lib\appprotocols\appxprocessurlaction.cpp`
- `0x1800444ef`: `onecoreuap\inetcore\lib\appprotocols\appxprocessurlaction.cpp`
- `0x180044532`: `onecoreuap\inetcore\lib\appprotocols\appxprocessurlaction.cpp`
- `0x1800445ab`: `onecoreuap\inetcore\lib\appprotocols\appxprocessurlaction.cpp`
- `0x180044602`: `onecoreuap\inetcore\lib\appprotocols\appxprocessurlaction.cpp`
- `0x180044638`: `onecoreuap\inetcore\lib\appprotocols\appxprocessurlaction.cpp`
- `0x180044725`: `onecoreuap\inetcore\lib\appprotocols\appxprocessurlaction.cpp`
- `0x180044765`: `onecoreuap\inetcore\lib\appprotocols\appxprocessurlaction.cpp`
- `0x180044425`: `This UrlAction should only be called on the default security manager`
- `0x18004443d`: `This UrlAction should never be called on the default security manager`

## pseudocode

```c
char __fastcall AppxProcessUrlAction(
        struct IWebPlatformAppContext *a1,
        int a2,
        int *a3,
        unsigned int a4,
        struct IUri *psz,
        unsigned __int8 *a6,
        int a7,
        struct IUri *a8,
        __int64 a9,
        AppProtocolsCommon *a10)
{
  char *v13; // rbx
  unsigned int i; // edx
  int v15; // ecx
  char result; // al
  bool v17; // zf
  int v18; // r12d
  int v19; // esi
  const char *v20; // r9
  __int64 v21; // rax
  int v22; // eax
  int v23; // edi
  int v24; // ebx
  LPCWSTR v25; // rax
  int v26; // edx
  int v27; // r9d
  int v28; // eax
  int v29; // edi
  LPCWSTR v30; // rax
  int v31; // r8d
  int v32; // edx
  __int64 v33; // rax
  const WCHAR *v34; // r10
  char v35; // di
  IUri *v36; // rcx
  HRESULT Uri; // ebx
  AppProtocolsCommon *v38; // rbx
  int *v39; // r9
  __int64 v40; // rax
  int v41; // edi
  int v42; // eax
  unsigned __int16 *v43; // rax
  int v44; // r8d
  int v45; // edx
  int IsLocalCompartmentUri; // eax
  struct IUri *v47; // r8
  int v48; // edx
  char v49; // di
  bool v50; // zf
  int IsLocalXhrAllowed; // eax
  int szMethod; // edx
  int v53; // edx
  int v54; // ebx
  int v55; // r12d
  char v56; // bl
  int *v57; // r9
  struct IUri *v58; // rdx
  struct tag_APPX_PROCESS_URL_ACTION_TELEMETRY *v59; // r9
  char v60; // dl
  char v61; // bl
  struct tag_APPX_PROCESS_URL_ACTION_TELEMETRY *v62; // r9
  int IsTelemetryCollectionAllowed; // r8d
  unsigned int v64; // r13d
  const char *v65; // r9
  const unsigned __int16 *v66; // r12
  int IsCrossDomainWebWorkerAllowed; // eax
  __int64 v68; // r8
  char *v69; // r9
  int *v70; // [rsp+20h] [rbp-28h]
  int *v71; // [rsp+20h] [rbp-28h]
  const char *v72; // [rsp+28h] [rbp-20h]
  const char *v73; // [rsp+28h] [rbp-20h]
  const char *v74; // [rsp+28h] [rbp-20h]
  size_t pcchLength; // [rsp+30h] [rbp-18h] BYREF
  IUri *ppURI[2]; // [rsp+38h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+40h]
  struct _tagPROTOCOL_ARGUMENT bstrString; // [rsp+A0h] [rbp+58h] BYREF

  if ( !a3 || a4 < 4 )
    return 87;
  switch ( a2 )
  {
    case 5126:
      goto LABEL_24;
    case 5131:
      LODWORD(bstrString.szMethod) = 0;
      wil::details::in1diag3::FailFast_IfFalseMsg(
        retaddr,
        (void *)0x192,
        (unsigned int)"onecoreuap\\inetcore\\lib\\appprotocols\\appxprocessurlaction.cpp",
        (const char *)((unsigned int)(a7 - 3) <= 1),
        (bool)"UrlAction is called out of context",
        v72);
      if ( !a8 )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x194,
          (unsigned int)"onecoreuap\\inetcore\\lib\\appprotocols\\appxprocessurlaction.cpp",
          v69);
      IsLocalXhrAllowed = AppProtocolsCommon::IsLocalXhrAllowed(a1, psz, &bstrString, (int *)v69);
      szMethod = (int)bstrString.szMethod;
      if ( IsLocalXhrAllowed < 0 )
        szMethod = 0;
      v53 = -szMethod;
      v50 = (v53 == 0 ? 3 : 0) == 0;
      *(_BYTE *)a3 = v53 == 0 ? 3 : 0;
      return !v50;
    case 5645:
      goto LABEL_24;
    case 5647:
      v64 = a7;
      wil::details::in1diag3::FailFast_IfFalseMsg(
        retaddr,
        (void *)0x1A6,
        (unsigned int)"onecoreuap\\inetcore\\lib\\appprotocols\\appxprocessurlaction.cpp",
        (const char *)((unsigned int)(a7 - 3) <= 1),
        (bool)"UrlAction is called out of context",
        v72);
      if ( !a8 )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x1A8,
          (unsigned int)"onecoreuap\\inetcore\\lib\\appprotocols\\appxprocessurlaction.cpp",
          v65);
      v66 = (const unsigned __int16 *)psz;
      *(_BYTE *)a3 = 3;
      LOBYTE(Uri) = 1;
      if ( v66 )
      {
        if ( (unsigned __int64)(unsigned int)a6 >> 1 )
        {
          Uri = StringCchLengthW(v66, (unsigned __int64)(unsigned int)a6 >> 1, (unsigned __int64 *)&bstrString);
          if ( Uri >= 0 )
          {
            ppURI[0] = 0;
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(ppURI);
            Uri = CreateUri(v66, 0x2081u, 0, ppURI);
            if ( Uri >= 0 )
            {
              LODWORD(bstrString.szMethod) = 0;
              IsCrossDomainWebWorkerAllowed = AppProtocolsCommon::IsCrossDomainWebWorkerAllowed(
                                                a1,
                                                ppURI[0],
                                                a8,
                                                (struct IAppxUrlHelper *)&bstrString,
                                                v71);
              LOBYTE(Uri) = IsCrossDomainWebWorkerAllowed;
              if ( IsCrossDomainWebWorkerAllowed < 0 )
              {
                if ( IsCrossDomainWebWorkerAllowed == -2146697199 && v64 != 3 )
                  LOBYTE(Uri) = AppxProcessUrlActionFromTemplate(5647, a3, v68, v64);
              }
              else if ( LODWORD(bstrString.szMethod) )
              {
                *(_BYTE *)a3 = 0;
                LOBYTE(Uri) = 0;
              }
              else
              {
                LOBYTE(Uri) = 1;
              }
            }
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(ppURI);
          }
        }
      }
      return Uri;
    case 5648:
    case 6161:
LABEL_24:
      v18 = 0;
      ppURI[0] = 0;
      v19 = 1;
      wil::details::in1diag3::FailFast_IfFalseMsg(
        retaddr,
        (void *)0x153,
        (unsigned int)"onecoreuap\\inetcore\\lib\\appprotocols\\appxprocessurlaction.cpp",
        (const char *)((unsigned int)(a7 - 3) <= 1),
        (bool)"UrlAction is called out of context",
        v72);
      if ( !a8 )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x155,
          (unsigned int)"onecoreuap\\inetcore\\lib\\appprotocols\\appxprocessurlaction.cpp",
          v20);
      v21 = *(_QWORD *)a1;
      bstrString.szMethod = 0;
      v22 = (*(__int64 (__fastcall **)(struct IWebPlatformAppContext *, struct _tagPROTOCOL_ARGUMENT *))(v21 + 152))(
              a1,
              &bstrString);
      v23 = v22;
      v24 = -2147024809;
      if ( v22 == 1 )
      {
        v23 = -2147024809;
      }
      else if ( v22 >= 0 )
      {
        v25 = bstrString.szMethod;
        do
        {
          v26 = *(unsigned __int16 *)((char *)v25 + (char *)L"ms-appx" - (char *)bstrString.szMethod);
          v27 = *v25 - v26;
          if ( v27 )
            break;
          ++v25;
        }
        while ( v26 );
        LOBYTE(v18) = v27 == 0;
      }
      SysFreeString((BSTR)bstrString.szMethod);
      if ( v23 < 0 )
        v18 = 0;
      if ( v18 )
        goto LABEL_72;
      bstrString.szMethod = 0;
      v28 = (*(__int64 (__fastcall **)(struct IWebPlatformAppContext *, struct _tagPROTOCOL_ARGUMENT *))(*(_QWORD *)a1 + 152LL))(
              a1,
              &bstrString);
      v29 = v28;
      if ( v28 == 1 )
      {
        v29 = -2147024809;
      }
      else if ( v28 >= 0 )
      {
        v30 = bstrString.szMethod;
        do
        {
          v31 = *(unsigned __int16 *)((char *)v30 + (char *)L"ms-appx-web" - (char *)bstrString.szMethod);
          v32 = *v30 - v31;
          if ( v32 )
            break;
          ++v30;
        }
        while ( v31 );
        if ( !v32 )
          v18 = 1;
      }
      SysFreeString((BSTR)bstrString.szMethod);
      if ( v29 >= 0 && v18 )
      {
        if ( a10 )
        {
          v33 = *(_QWORD *)a10;
          LODWORD(bstrString.szMethod) = 0;
          if ( (*(int (__fastcall **)(AppProtocolsCommon *, struct IWebPlatformAppContext *, struct _tagPROTOCOL_ARGUMENT *))(v33 + 24))(
                 a10,
                 a1,
                 &bstrString) >= 0
            && ((__int64)bstrString.szMethod & 4) != 0 )
          {
LABEL_71:
            if ( v19 )
            {
LABEL_72:
              v35 = 0;
LABEL_51:
              v36 = ppURI[0];
              *(_BYTE *)a3 = v35;
              LOBYTE(Uri) = v35 != 0;
              if ( v36 )
              {
                ppURI[0] = 0;
                ((void (__fastcall *)(IUri *))v36->lpVtbl->Release)(v36);
              }
              return Uri;
            }
LABEL_50:
            v35 = 3;
            goto LABEL_51;
          }
        }
        LODWORD(bstrString.szMethod) = 0;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(ppURI);
        if ( !psz
          || (unsigned int)a6 < 2
          || StringLengthWorkerW((STRSAFE_PCNZWCH)psz, (unsigned __int64)(unsigned int)a6 >> 1, &pcchLength) < 0
          || CreateUri(v34, 0x2080u, 0, ppURI) < 0 )
        {
          goto LABEL_50;
        }
        v41 = 0;
        pcchLength = 0;
        v42 = ((__int64 (__fastcall *)(IUri *, size_t *))ppURI[0]->lpVtbl->GetSchemeName)(ppURI[0], &pcchLength);
        if ( v42 != 1 )
        {
          v24 = v42;
          if ( v42 >= 0 )
          {
            v43 = (unsigned __int16 *)pcchLength;
            do
            {
              v44 = *(unsigned __int16 *)((char *)L"ms-appx-web" + (_QWORD)v43 - pcchLength);
              v45 = *v43 - v44;
              if ( v45 )
                break;
              ++v43;
            }
            while ( v44 );
            if ( !v45 )
              v41 = 1;
          }
        }
        SysFreeString((BSTR)pcchLength);
        if ( v24 < 0 || !v41 )
          goto LABEL_50;
        if ( (int)AppProtocolsCommon::IsPackagedWebCompartmentXhrAllowed(
                    a1,
                    ppURI[0],
                    a8,
                    (struct IAppxUrlHelper *)&bstrString,
                    v70) < 0 )
        {
          v19 = 0;
          goto LABEL_71;
        }
      }
      else
      {
        v38 = a10;
        if ( !a10 )
          goto LABEL_50;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(ppURI);
        if ( AppProtocolsCommon::GetUriFromContext(
               (AppProtocolsCommon *)psz,
               (const unsigned __int8 *)(unsigned int)a6,
               4u,
               (unsigned int)ppURI,
               (struct IUri **)v70) < 0 )
          goto LABEL_50;
        LODWORD(bstrString.szMethod) = 0;
        LODWORD(pcchLength) = 0;
        if ( (int)AppProtocolsCommon::IsPackageUri(
                    (AppProtocolsCommon *)ppURI[0],
                    (struct IUri *)&bstrString,
                    (int *)&pcchLength,
                    v39) < 0 )
          goto LABEL_50;
        if ( !LODWORD(bstrString.szMethod) )
          goto LABEL_50;
        v40 = *(_QWORD *)v38;
        LODWORD(bstrString.szMethod) = 0;
        if ( (*(int (__fastcall **)(AppProtocolsCommon *, struct IWebPlatformAppContext *, struct _tagPROTOCOL_ARGUMENT *))(v40 + 40))(
               v38,
               a1,
               &bstrString) < 0 )
          goto LABEL_50;
      }
      v19 = (int)bstrString.szMethod;
      goto LABEL_71;
    case 8961:
      v61 = a9;
      wil::details::in1diag3::FailFast_IfFalseMsg(
        retaddr,
        (void *)0x1DE,
        (unsigned int)"onecoreuap\\inetcore\\lib\\appprotocols\\appxprocessurlaction.cpp",
        (const char *)(a9 != 0),
        (bool)"Telemetry info is required for this url action",
        v72);
      IsTelemetryCollectionAllowed = AppProtocolsCommon::IsTelemetryCollectionAllowed(a1, 0, v61, v62);
      v60 = IsTelemetryCollectionAllowed == 0 ? 3 : 0;
      v17 = IsTelemetryCollectionAllowed == 0;
LABEL_95:
      *(_BYTE *)a3 = v60;
      return v17;
    case 8962:
      v54 = a7;
      v55 = 0;
      wil::details::in1diag3::FailFast_IfFalseMsg(
        retaddr,
        (void *)0x1EA,
        (unsigned int)"onecoreuap\\inetcore\\lib\\appprotocols\\appxprocessurlaction.cpp",
        (const char *)((unsigned int)(a7 - 3) <= 1),
        (bool)"UrlAction is called out of context",
        v72);
      if ( v54 == 3 )
      {
        v56 = a9;
        wil::details::in1diag3::FailFast_IfFalseMsg(
          retaddr,
          (void *)0x1F5,
          (unsigned int)"onecoreuap\\inetcore\\lib\\appprotocols\\appxprocessurlaction.cpp",
          (const char *)(a9 != 0),
          (bool)"Telemetry info is required for this url action",
          v74);
        LODWORD(bstrString.szMethod) = 0;
        LODWORD(pcchLength) = 0;
        if ( (int)AppProtocolsCommon::IsPackageUri(a1, (struct IUri *)&bstrString, (int *)&pcchLength, v57) >= 0 )
        {
          if ( LODWORD(bstrString.szMethod) )
          {
            LOBYTE(v58) = 1;
            v55 = AppProtocolsCommon::IsTelemetryCollectionAllowed((AppProtocolsCommon *)psz, v58, v56, v59);
          }
        }
      }
      v60 = v55 == 0 ? 3 : 0;
      v17 = v55 == 0;
      goto LABEL_95;
    case 9988:
      LODWORD(bstrString.szMethod) = 0;
      IsLocalCompartmentUri = AppProtocolsCommon::IsLocalCompartmentUri(a1, (struct IUri *)&bstrString, a3);
      v48 = (int)bstrString.szMethod;
      if ( IsLocalCompartmentUri < 0 )
        v48 = 0;
      if ( v48 || (unsigned int)AppProtocolsCommon::UriHasFullWinRTAccess(a10, a1, v47) )
        v49 = 0;
      else
        v49 = 3;
      *(_BYTE *)a3 = v49;
      v50 = v49 == 0;
      return !v50;
  }
  v13 = 0;
  for ( i = 0; i < 0x74; ++i )
  {
    if ( *((_DWORD *)qword_180139C50 + 3 * (int)i) == a2 )
    {
      v13 = (char *)qword_180139C50 + 12 * (int)i;
      break;
    }
  }
  wil::details::in1diag3::FailFast_IfNullMsg<APPXURLACTIONPOLICY const *,0>(
    (_DWORD)retaddr,
    244,
    (unsigned int)"onecoreuap\\inetcore\\lib\\appprotocols\\appxprocessurlaction.cpp",
    (_DWORD)v13,
    "UrlAction was not found in our table");
  wil::details::in1diag3::FailFast_IfFalseMsg(
    retaddr,
    (void *)0xF6,
    (unsigned int)"onecoreuap\\inetcore\\lib\\appprotocols\\appxprocessurlaction.cpp",
    (const char *)((v13[8] & 1) == 0),
    (bool)"UrlAction is unexpected",
    v72);
  if ( (v13[8] & 2) != 0 )
  {
    wil::details::in1diag3::FailFast_IfFalseMsg(
      retaddr,
      (void *)0xFB,
      (unsigned int)"onecoreuap\\inetcore\\lib\\appprotocols\\appxprocessurlaction.cpp",
      (const char *)((unsigned int)(a7 - 1) <= 1),
      (bool)"This UrlAction should only be called on the default security manager",
      v73);
  }
  else if ( (v13[8] & 4) != 0 )
  {
    wil::details::in1diag3::FailFast_IfFalseMsg(
      retaddr,
      (void *)0x100,
      (unsigned int)"onecoreuap\\inetcore\\lib\\appprotocols\\appxprocessurlaction.cpp",
      (const char *)((unsigned int)(a7 - 3) <= 1),
      (bool)"This UrlAction should never be called on the default security manager",
      v73);
  }
  v15 = *((_DWORD *)v13 + 1);
  result = 0;
  *a3 = v15;
  if ( a2 != 8454 )
    return v15 == 3;
  return result;
}

```

## disassembly

```asm
0x180043fa0  push    rbp
0x180043fa2  push    rbx
0x180043fa3  push    rsi
0x180043fa4  push    rdi
0x180043fa5  push    r12
0x180043fa7  push    r13
0x180043fa9  push    r14
0x180043fab  push    r15
0x180043fad  mov     rbp, rsp
0x180043fb0  sub     rsp, 48h
0x180043fb4  mov     r15, r8
0x180043fb7  mov     edi, edx
0x180043fb9  mov     r14, rcx
0x180043fbc  test    r8, r8
0x180043fbf  jz      loc_1800440E4
0x180043fc5  cmp     r9d, 4
0x180043fc9  jb      loc_1800440E4
0x180043fcf  mov     eax, edx
0x180043fd1  sub     eax, 1406h
0x180043fd6  jz      loc_1800440EB
0x180043fdc  sub     eax, 5
0x180043fdf  jz      loc_180044717
0x180043fe5  sub     eax, 202h
0x180043fea  jz      loc_1800440EB
0x180043ff0  sub     eax, 2
0x180043ff3  jz      loc_1800445F3
0x180043ff9  sub     eax, 1
0x180043ffc  jz      loc_1800440EB
0x180044002  sub     eax, 201h
0x180044007  jz      loc_1800440EB
0x18004400d  sub     eax, 0AF0h
0x180044012  jz      loc_180044599
0x180044018  sub     eax, 1
0x18004401b  jz      loc_1800444E1
0x180044021  cmp     eax, 402h
0x180044026  jz      loc_18004446F
0x18004402c  xor     ebx, ebx
0x18004402e  xor     edx, edx
0x180044030  lea     esi, [rbx+1]
0x180044033  cmp     edx, 74h ; 't'
0x180044036  jnb     short loc_180044055
0x180044038  movsxd  rax, edx
0x18004403b  lea     rcx, [rax+rax*2]
0x18004403f  lea     rax, qword_180139C50
0x180044046  lea     rax, [rax+rcx*4]
0x18004404a  cmp     [rax], edi
0x18004404c  jz      short loc_180044052
0x18004404e  add     edx, esi
0x180044050  jmp     short loc_180044033
0x180044052  mov     rbx, rax
0x180044055  mov     rcx, [rbp+40h]
0x180044059  lea     rax, aUrlactionWasNo; "UrlAction was not found in our table"
0x180044060  mov     r9, rbx
0x180044063  mov     [rsp+48h+var_28], rax
0x180044068  lea     r8, aOnecoreuapInet_8; "onecoreuap\\inetcore\\lib\\appprotocols"...
0x18004406f  mov     edx, 0F4h
0x180044074  call    ??$FailFast_IfNullMsg@PEBUAPPXURLACTIONPOLICY@@$0A@@in1diag3@details@wil@@YAPEBUAPPXURLACTIONPOLICY@@PEAXIPEBDPEBU3@1ZZ; wil::details::in1diag3::FailFast_IfNullMsg<APPXURLACTIONPOLICY const *,0>(void *,uint,char const *,APPXURLACTIONPOLICY const *,char const *,...)
0x180044079  mov     al, [rbx+8]
0x18004407c  lea     rdx, aUrlactionIsUne; "UrlAction is unexpected"
0x180044083  mov     rcx, [rbp+40h]; this
0x180044087  lea     r8, aOnecoreuapInet_8; "onecoreuap\\inetcore\\lib\\appprotocols"...
0x18004408e  not     al
0x180044090  mov     [rsp+48h+var_28], rdx; bool
0x180044095  and     al, sil
0x180044098  mov     edx, 0F6h; void *
0x18004409d  movzx   r9d, al; char *
0x1800440a1  call    ?FailFast_IfFalseMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::FailFast_IfFalseMsg(void *,uint,char const *,bool,char const *,...)
0x1800440a6  test    byte ptr [rbx+8], 2
0x1800440aa  jnz     loc_180044422
0x1800440b0  test    byte ptr [rbx+8], 4
0x1800440b4  jnz     loc_18004443A
0x1800440ba  mov     ecx, [rbx+4]
0x1800440bd  xor     eax, eax
0x1800440bf  mov     [r15], ecx
0x1800440c2  cmp     edi, 2106h
0x1800440c8  jz      short loc_1800440D2
0x1800440ca  lea     edi, [rax+3]
0x1800440cd  cmp     ecx, edi
0x1800440cf  setz    al
0x1800440d2  add     rsp, 48h
0x1800440d6  pop     r15
0x1800440d8  pop     r14
0x1800440da  pop     r13
0x1800440dc  pop     r12
0x1800440de  pop     rdi
0x1800440df  pop     rsi
0x1800440e0  pop     rbx
0x1800440e1  pop     rbp
0x1800440e2  retn
0x1800440e4  mov     eax, 80070057h
0x1800440e9  jmp     short loc_1800440D2
0x1800440eb  mov     eax, [rbp+arg_30]
0x1800440ee  lea     rdx, aUrlactionIsCal; "UrlAction is called out of context"
0x1800440f5  mov     rcx, [rbp+40h]; this
0x1800440f9  lea     r8, aOnecoreuapInet_8; "onecoreuap\\inetcore\\lib\\appprotocols"...
0x180044100  xor     r12d, r12d
0x180044103  mov     [rsp+48h+var_28], rdx; int *
0x180044108  add     eax, 0FFFFFFFDh
0x18004410b  mov     [rbp+ppURI], r12
0x18004410f  mov     edx, 153h; void *
0x180044114  lea     esi, [r12+1]
0x180044119  cmp     eax, esi
0x18004411b  setbe   al
0x18004411e  movzx   r9d, al; char *
0x180044122  call    ?FailFast_IfFalseMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::FailFast_IfFalseMsg(void *,uint,char const *,bool,char const *,...)
0x180044127  cmp     [rbp+arg_38], r12
0x18004412e  jnz     short loc_180044146
0x180044130  mov     rcx, [rbp+40h]; this
0x180044134  lea     r8, aOnecoreuapInet_8; "onecoreuap\\inetcore\\lib\\appprotocols"...
0x18004413b  mov     edx, 155h; void *
0x180044140  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180044146  mov     rax, [r14]
0x180044149  lea     rdx, [rbp+bstrString]
0x18004414d  mov     rcx, r14
0x180044150  mov     qword ptr [rbp+bstrString], r12
0x180044154  mov     rax, [rax+98h]
0x18004415b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044160  mov     rcx, qword ptr [rbp+bstrString]; bstrString
0x180044164  mov     edi, eax
0x180044166  mov     ebx, 80070057h
0x18004416b  cmp     eax, esi
0x18004416d  jz      loc_180044777
0x180044173  test    eax, eax
0x180044175  js      short loc_1800441A1
0x180044177  lea     r8, ?Package@Protocols@@3QBGB; "ms-appx"
0x18004417e  mov     rax, rcx
0x180044181  sub     r8, rcx
0x180044184  movzx   r9d, word ptr [rax]
0x180044188  movzx   edx, word ptr [rax+r8]
0x18004418d  sub     r9d, edx
0x180044190  jnz     short loc_18004419A
0x180044192  add     rax, 2
0x180044196  test    edx, edx
0x180044198  jnz     short loc_180044184
0x18004419a  test    r9d, r9d
0x18004419d  setz    r12b
0x1800441a1  call    cs:__imp_SysFreeString
0x1800441a8  nop     dword ptr [rax+rax+00h]
0x1800441ad  xor     eax, eax
0x1800441af  test    edi, edi
0x1800441b1  cmovs   r12d, eax
0x1800441b5  test    r12d, r12d
0x1800441b8  jnz     loc_1800443F2
0x1800441be  mov     qword ptr [rbp+bstrString], rax
0x1800441c2  lea     rdx, [rbp+bstrString]
0x1800441c6  mov     rax, [r14]
0x1800441c9  mov     rcx, r14
0x1800441cc  mov     rax, [rax+98h]
0x1800441d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800441d8  mov     rcx, qword ptr [rbp+bstrString]; bstrString
0x1800441dc  mov     edi, eax
0x1800441de  lea     r13, ?PackageUntrusted@Protocols@@3QBGB; "ms-appx-web"
0x1800441e5  cmp     eax, esi
0x1800441e7  jz      loc_18004477E
0x1800441ed  test    eax, eax
0x1800441ef  js      short loc_180044217
0x1800441f1  mov     r9, r13
0x1800441f4  mov     rax, rcx
0x1800441f7  sub     r9, rcx
0x1800441fa  movzx   edx, word ptr [rax]
0x1800441fd  movzx   r8d, word ptr [rax+r9]
0x180044202  sub     edx, r8d
0x180044205  jnz     short loc_180044210
0x180044207  add     rax, 2
0x18004420b  test    r8d, r8d
0x18004420e  jnz     short loc_1800441FA
0x180044210  test    edx, edx
0x180044212  jnz     short loc_180044217
0x180044214  mov     r12d, esi
0x180044217  call    cs:__imp_SysFreeString
0x18004421e  nop     dword ptr [rax+rax+00h]
0x180044223  test    edi, edi
0x180044225  js      loc_1800442D2
0x18004422b  test    r12d, r12d
0x18004422e  jz      loc_1800442D2
0x180044234  mov     rcx, [rbp+arg_48]
0x18004423b  xor     r12d, r12d
0x18004423e  test    rcx, rcx
0x180044241  jz      short loc_180044268
0x180044243  mov     rax, [rcx]
0x180044246  lea     r8, [rbp+bstrString]
0x18004424a  mov     rdx, r14
0x18004424d  mov     dword ptr [rbp+bstrString], r12d
0x180044251  mov     rax, [rax+18h]
0x180044255  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004425a  test    eax, eax
0x18004425c  js      short loc_180044268
0x18004425e  test    byte ptr [rbp+bstrString], 4
0x180044262  jnz     loc_1800443EA
0x180044268  lea     rcx, [rbp+ppURI]
0x18004426c  mov     dword ptr [rbp+bstrString], r12d
0x180044270  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180044275  mov     r10, [rbp+psz]
0x180044279  test    r10, r10
0x18004427c  jz      short loc_18004429E
0x18004427e  cmp     dword ptr [rbp+arg_28], 2
0x180044282  jb      short loc_18004429E
0x180044284  mov     edx, dword ptr [rbp+arg_28]
0x180044287  lea     r8, [rbp+pcchLength]; pcchLength
0x18004428b  shr     rdx, 1; cchMax
0x18004428e  mov     rcx, r10; psz
0x180044291  call    StringLengthWorkerW
0x180044296  test    eax, eax
0x180044298  jns     loc_1800443FA
0x18004429e  mov     edi, 3
0x1800442a3  mov     rcx, [rbp+ppURI]
0x1800442a7  xor     ebx, ebx
0x1800442a9  test    dil, dil
0x1800442ac  mov     [r15], dil
0x1800442af  setnz   bl
0x1800442b2  test    rcx, rcx
0x1800442b5  jz      short loc_1800442CB
0x1800442b7  mov     [rbp+ppURI], 0
0x1800442bf  mov     rdx, [rcx]
0x1800442c2  mov     rax, [rdx+10h]
0x1800442c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800442cb  mov     eax, ebx
0x1800442cd  jmp     loc_1800440D2
0x1800442d2  mov     rbx, [rbp+arg_48]
0x1800442d9  test    rbx, rbx
0x1800442dc  jz      short loc_18004429E
0x1800442de  lea     rcx, [rbp+ppURI]
0x1800442e2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800442e7  mov     edx, dword ptr [rbp+arg_28]; unsigned __int8 *
0x1800442ea  lea     r9, [rbp+ppURI]; unsigned int
0x1800442ee  mov     rcx, [rbp+psz]; this
0x1800442f2  mov     r8d, 4; unsigned int
0x1800442f8  call    ?GetUriFromContext@AppProtocolsCommon@@YAJPEBEKKPEAPEAUIUri@@@Z; AppProtocolsCommon::GetUriFromContext(uchar const *,ulong,ulong,IUri * *)
0x1800442fd  test    eax, eax
0x1800442ff  js      short loc_18004429E
0x180044301  mov     rcx, [rbp+ppURI]; this
0x180044305  lea     r8, [rbp+pcchLength]; int *
0x180044309  lea     rdx, [rbp+bstrString]; struct IUri *
0x18004430d  mov     dword ptr [rbp+bstrString], 0
0x180044314  mov     dword ptr [rbp+pcchLength], 0
0x18004431b  call    ?IsPackageUri@AppProtocolsCommon@@YAJPEAUIUri@@PEAH1@Z; AppProtocolsCommon::IsPackageUri(IUri *,int *,int *)
0x180044320  test    eax, eax
0x180044322  js      loc_18004429E
0x180044328  cmp     dword ptr [rbp+bstrString], 0
0x18004432c  jz      loc_18004429E
0x180044332  mov     rax, [rbx]
0x180044335  lea     r8, [rbp+bstrString]
0x180044339  mov     rdx, r14
0x18004433c  mov     dword ptr [rbp+bstrString], 0
0x180044343  mov     rcx, rbx
0x180044346  mov     rax, [rax+28h]
0x18004434a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004434f  test    eax, eax
0x180044351  js      loc_18004429E
0x180044357  mov     esi, dword ptr [rbp+bstrString]
0x18004435a  jmp     loc_1800443EA
0x18004435f  mov     rcx, [rbp+ppURI]
0x180044363  lea     rdx, [rbp+pcchLength]
0x180044367  mov     edi, r12d
0x18004436a  mov     [rbp+pcchLength], r12
0x18004436e  mov     rax, [rcx]
0x180044371  mov     rax, [rax+98h]
0x180044378  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004437d  mov     rcx, [rbp+pcchLength]; bstrString
0x180044381  cmp     eax, esi
0x180044383  jz      short loc_1800443AD
0x180044385  mov     ebx, eax
0x180044387  test    eax, eax
0x180044389  js      short loc_1800443AD
0x18004438b  mov     rax, rcx
0x18004438e  sub     r13, rcx
0x180044391  movzx   edx, word ptr [rax]
0x180044394  movzx   r8d, word ptr [rax+r13]
0x180044399  sub     edx, r8d
0x18004439c  jnz     short loc_1800443A7
0x18004439e  add     rax, 2
0x1800443a2  test    r8d, r8d
0x1800443a5  jnz     short loc_180044391
0x1800443a7  test    edx, edx
0x1800443a9  jnz     short loc_1800443AD
0x1800443ab  mov     edi, esi
0x1800443ad  call    cs:__imp_SysFreeString
0x1800443b4  nop     dword ptr [rax+rax+00h]
0x1800443b9  test    ebx, ebx
0x1800443bb  js      loc_18004429E
0x1800443c1  test    edi, edi
0x1800443c3  jz      loc_18004429E
0x1800443c9  mov     r8, [rbp+arg_38]; struct IUri *
0x1800443d0  lea     r9, [rbp+bstrString]; struct IAppxUrlHelper *
0x1800443d4  mov     rdx, [rbp+ppURI]; struct IUri *
0x1800443d8  mov     rcx, r14; this
0x1800443db  call    ?IsPackagedWebCompartmentXhrAllowed@AppProtocolsCommon@@YAJPEAUIUri@@0PEAVIAppxUrlHelper@@PEAH@Z; AppProtocolsCommon::IsPackagedWebCompartmentXhrAllowed(IUri *,IUri *,IAppxUrlHelper *,int *)
0x1800443e0  test    eax, eax
0x1800443e2  jns     loc_180044357
0x1800443e8  xor     esi, esi
0x1800443ea  test    esi, esi
0x1800443ec  jz      loc_18004429E
0x1800443f2  xor     dil, dil
0x1800443f5  jmp     loc_1800442A3
0x1800443fa  lea     r9, [rbp+ppURI]; ppURI
0x1800443fe  xor     r8d, r8d; dwReserved
0x180044401  mov     edx, 2080h; dwFlags
0x180044406  mov     rcx, r10; pwzURI
0x180044409  call    cs:__imp_CreateUri
0x180044410  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
