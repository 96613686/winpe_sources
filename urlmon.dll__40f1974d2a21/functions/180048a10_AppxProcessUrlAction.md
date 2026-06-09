# AppxProcessUrlAction

- ea: `0x180048a10`
- end: `0x1800491d6`
- name: `AppxProcessUrlAction`
- size: `1990`
- prototype: `__int64 __usercall@<rax>(struct IWebPlatformAppContext *@<rcx>, STRSAFE_PCNZWCH psz, unsigned __int8 *, int, struct IUri *, __int64, AppProtocolsCommon *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800487e0`

## callees

- `0x180008300`
- `0x180047e20`
- `0x1800483e8`
- `0x180048a10`
- `0x1800491e0`
- `0x180049870`
- `0x180049940`
- `0x180049d20`
- `0x180049d60`
- `0x180061440`
- `0x1800616d8`
- `0x1800685e8`
- `0x1800687d0`
- `0x180086d34`
- `0x18009b9dc`
- `0x180109b20`
- `0x18011c010`

## import_xrefs

- `iertutil!CreateUri` at `0x180048e66`
- `iertutil!CreateUri` at `0x1800490fa`
- `iertutil!CreateUri` at `0x180048e66`
- `iertutil!CreateUri` at `0x1800490fa`
- `OLEAUT32!__imp_SysFreeString` at `0x180048c10`
- `OLEAUT32!__imp_SysFreeString` at `0x180048c80`
- `OLEAUT32!__imp_SysFreeString` at `0x180048e10`
- `OLEAUT32!__imp_SysFreeString` at `0x180048c10`
- `OLEAUT32!__imp_SysFreeString` at `0x180048c80`
- `OLEAUT32!__imp_SysFreeString` at `0x180048e10`

## string_xrefs

- `0x180048ad8`: `onecoreuap\inetcore\lib\appprotocols\appxprocessurlaction.cpp`
- `0x180048af7`: `onecoreuap\inetcore\lib\appprotocols\appxprocessurlaction.cpp`
- `0x180048b68`: `onecoreuap\inetcore\lib\appprotocols\appxprocessurlaction.cpp`
- `0x180048ba3`: `onecoreuap\inetcore\lib\appprotocols\appxprocessurlaction.cpp`
- `0x180048eac`: `onecoreuap\inetcore\lib\appprotocols\appxprocessurlaction.cpp`
- `0x180048f46`: `onecoreuap\inetcore\lib\appprotocols\appxprocessurlaction.cpp`
- `0x180048f89`: `onecoreuap\inetcore\lib\appprotocols\appxprocessurlaction.cpp`
- `0x180049002`: `onecoreuap\inetcore\lib\appprotocols\appxprocessurlaction.cpp`
- `0x180049059`: `onecoreuap\inetcore\lib\appprotocols\appxprocessurlaction.cpp`
- `0x18004908f`: `onecoreuap\inetcore\lib\appprotocols\appxprocessurlaction.cpp`
- `0x180049176`: `onecoreuap\inetcore\lib\appprotocols\appxprocessurlaction.cpp`
- `0x1800491b6`: `onecoreuap\inetcore\lib\appprotocols\appxprocessurlaction.cpp`
- `0x180048e7c`: `This UrlAction should only be called on the default security manager`
- `0x180048e94`: `This UrlAction should never be called on the default security manager`

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
  const char *v69; // r9
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
      IsLocalXhrAllowed = AppProtocolsCommon::IsLocalXhrAllowed(a1, psz, &bstrString, v69);
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
        if ( (int)AppProtocolsCommon::GetUriFromContext(
                    (const wchar_t *)psz,
                    (const unsigned __int8 *)(unsigned int)a6,
                    4,
                    ppURI) < 0 )
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
    if ( *((_DWORD *)qword_18012CF20 + 3 * (int)i) == a2 )
    {
      v13 = (char *)qword_18012CF20 + 12 * (int)i;
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
0x180048a10  push    rbp
0x180048a12  push    rbx
0x180048a13  push    rsi
0x180048a14  push    rdi
0x180048a15  push    r12
0x180048a17  push    r13
0x180048a19  push    r14
0x180048a1b  push    r15
0x180048a1d  mov     rbp, rsp
0x180048a20  sub     rsp, 48h
0x180048a24  mov     r15, r8
0x180048a27  mov     edi, edx
0x180048a29  mov     r14, rcx
0x180048a2c  test    r8, r8
0x180048a2f  jz      loc_180048B53
0x180048a35  cmp     r9d, 4
0x180048a39  jb      loc_180048B53
0x180048a3f  mov     eax, edx
0x180048a41  sub     eax, 1406h
0x180048a46  jz      loc_180048B5A
0x180048a4c  sub     eax, 5
0x180048a4f  jz      loc_180049168
0x180048a55  sub     eax, 202h
0x180048a5a  jz      loc_180048B5A
0x180048a60  sub     eax, 2
0x180048a63  jz      loc_18004904A
0x180048a69  sub     eax, 1
0x180048a6c  jz      loc_180048B5A
0x180048a72  sub     eax, 201h
0x180048a77  jz      loc_180048B5A
0x180048a7d  sub     eax, 0AF0h
0x180048a82  jz      loc_180048FF0
0x180048a88  sub     eax, 1
0x180048a8b  jz      loc_180048F38
0x180048a91  cmp     eax, 402h
0x180048a96  jz      loc_180048EC6
0x180048a9c  xor     ebx, ebx
0x180048a9e  xor     edx, edx
0x180048aa0  lea     esi, [rbx+1]
0x180048aa3  cmp     edx, 74h ; 't'
0x180048aa6  jnb     short loc_180048AC5
0x180048aa8  movsxd  rax, edx
0x180048aab  lea     rcx, [rax+rax*2]
0x180048aaf  lea     rax, qword_18012CF20
0x180048ab6  lea     rax, [rax+rcx*4]
0x180048aba  cmp     [rax], edi
0x180048abc  jz      short loc_180048AC2
0x180048abe  add     edx, esi
0x180048ac0  jmp     short loc_180048AA3
0x180048ac2  mov     rbx, rax
0x180048ac5  mov     rcx, [rbp+40h]
0x180048ac9  lea     rax, aUrlactionWasNo; "UrlAction was not found in our table"
0x180048ad0  mov     r9, rbx
0x180048ad3  mov     [rsp+48h+var_28], rax
0x180048ad8  lea     r8, aOnecoreuapInet_8; "onecoreuap\\inetcore\\lib\\appprotocols"...
0x180048adf  mov     edx, 0F4h
0x180048ae4  call    ??$FailFast_IfNullMsg@PEBUAPPXURLACTIONPOLICY@@$0A@@in1diag3@details@wil@@YAPEBUAPPXURLACTIONPOLICY@@PEAXIPEBDPEBU3@1ZZ; wil::details::in1diag3::FailFast_IfNullMsg<APPXURLACTIONPOLICY const *,0>(void *,uint,char const *,APPXURLACTIONPOLICY const *,char const *,...)
0x180048ae9  mov     al, [rbx+8]
0x180048aec  lea     rdx, aUrlactionIsUne; "UrlAction is unexpected"
0x180048af3  mov     rcx, [rbp+40h]; this
0x180048af7  lea     r8, aOnecoreuapInet_8; "onecoreuap\\inetcore\\lib\\appprotocols"...
0x180048afe  not     al
0x180048b00  mov     [rsp+48h+var_28], rdx; bool
0x180048b05  and     al, sil
0x180048b08  mov     edx, 0F6h; void *
0x180048b0d  movzx   r9d, al; char *
0x180048b11  call    ?FailFast_IfFalseMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::FailFast_IfFalseMsg(void *,uint,char const *,bool,char const *,...)
0x180048b16  test    byte ptr [rbx+8], 2
0x180048b1a  jnz     loc_180048E79
0x180048b20  test    byte ptr [rbx+8], 4
0x180048b24  jnz     loc_180048E91
0x180048b2a  mov     ecx, [rbx+4]
0x180048b2d  xor     eax, eax
0x180048b2f  mov     [r15], ecx
0x180048b32  cmp     edi, 2106h
0x180048b38  jz      short loc_180048B42
0x180048b3a  lea     edi, [rax+3]
0x180048b3d  cmp     ecx, edi
0x180048b3f  setz    al
0x180048b42  add     rsp, 48h
0x180048b46  pop     r15
0x180048b48  pop     r14
0x180048b4a  pop     r13
0x180048b4c  pop     r12
0x180048b4e  pop     rdi
0x180048b4f  pop     rsi
0x180048b50  pop     rbx
0x180048b51  pop     rbp
0x180048b52  retn
0x180048b53  mov     eax, 80070057h
0x180048b58  jmp     short loc_180048B42
0x180048b5a  mov     eax, [rbp+arg_30]
0x180048b5d  lea     rdx, aUrlactionIsCal; "UrlAction is called out of context"
0x180048b64  mov     rcx, [rbp+40h]; this
0x180048b68  lea     r8, aOnecoreuapInet_8; "onecoreuap\\inetcore\\lib\\appprotocols"...
0x180048b6f  xor     r12d, r12d
0x180048b72  mov     [rsp+48h+var_28], rdx; int *
0x180048b77  add     eax, 0FFFFFFFDh
0x180048b7a  mov     [rbp+ppURI], r12
0x180048b7e  mov     edx, 153h; void *
0x180048b83  lea     esi, [r12+1]
0x180048b88  cmp     eax, esi
0x180048b8a  setbe   al
0x180048b8d  movzx   r9d, al; char *
0x180048b91  call    ?FailFast_IfFalseMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::FailFast_IfFalseMsg(void *,uint,char const *,bool,char const *,...)
0x180048b96  cmp     [rbp+arg_38], r12
0x180048b9d  jnz     short loc_180048BB5
0x180048b9f  mov     rcx, [rbp+40h]; this
0x180048ba3  lea     r8, aOnecoreuapInet_8; "onecoreuap\\inetcore\\lib\\appprotocols"...
0x180048baa  mov     edx, 155h; void *
0x180048baf  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180048bb5  mov     rax, [r14]
0x180048bb8  lea     rdx, [rbp+bstrString]
0x180048bbc  mov     rcx, r14
0x180048bbf  mov     qword ptr [rbp+bstrString], r12
0x180048bc3  mov     rax, [rax+98h]
0x180048bca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048bcf  mov     rcx, qword ptr [rbp+bstrString]; bstrString
0x180048bd3  mov     edi, eax
0x180048bd5  mov     ebx, 80070057h
0x180048bda  cmp     eax, esi
0x180048bdc  jz      loc_1800491C8
0x180048be2  test    eax, eax
0x180048be4  js      short loc_180048C10
0x180048be6  lea     r8, ?Package@Protocols@@3QBGB; "ms-appx"
0x180048bed  mov     rax, rcx
0x180048bf0  sub     r8, rcx
0x180048bf3  movzx   r9d, word ptr [rax]
0x180048bf7  movzx   edx, word ptr [rax+r8]
0x180048bfc  sub     r9d, edx
0x180048bff  jnz     short loc_180048C09
0x180048c01  add     rax, 2
0x180048c05  test    edx, edx
0x180048c07  jnz     short loc_180048BF3
0x180048c09  test    r9d, r9d
0x180048c0c  setz    r12b
0x180048c10  call    cs:__imp_SysFreeString
0x180048c16  xor     eax, eax
0x180048c18  test    edi, edi
0x180048c1a  cmovs   r12d, eax
0x180048c1e  test    r12d, r12d
0x180048c21  jnz     loc_180048E4F
0x180048c27  mov     qword ptr [rbp+bstrString], rax
0x180048c2b  lea     rdx, [rbp+bstrString]
0x180048c2f  mov     rax, [r14]
0x180048c32  mov     rcx, r14
0x180048c35  mov     rax, [rax+98h]
0x180048c3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048c41  mov     rcx, qword ptr [rbp+bstrString]; bstrString
0x180048c45  mov     edi, eax
0x180048c47  lea     r13, ?PackageUntrusted@Protocols@@3QBGB; "ms-appx-web"
0x180048c4e  cmp     eax, esi
0x180048c50  jz      loc_1800491CF
0x180048c56  test    eax, eax
0x180048c58  js      short loc_180048C80
0x180048c5a  mov     r9, r13
0x180048c5d  mov     rax, rcx
0x180048c60  sub     r9, rcx
0x180048c63  movzx   edx, word ptr [rax]
0x180048c66  movzx   r8d, word ptr [rax+r9]
0x180048c6b  sub     edx, r8d
0x180048c6e  jnz     short loc_180048C79
0x180048c70  add     rax, 2
0x180048c74  test    r8d, r8d
0x180048c77  jnz     short loc_180048C63
0x180048c79  test    edx, edx
0x180048c7b  jnz     short loc_180048C80
0x180048c7d  mov     r12d, esi
0x180048c80  call    cs:__imp_SysFreeString
0x180048c86  test    edi, edi
0x180048c88  js      loc_180048D35
0x180048c8e  test    r12d, r12d
0x180048c91  jz      loc_180048D35
0x180048c97  mov     rcx, [rbp+arg_48]
0x180048c9e  xor     r12d, r12d
0x180048ca1  test    rcx, rcx
0x180048ca4  jz      short loc_180048CCB
0x180048ca6  mov     rax, [rcx]
0x180048ca9  lea     r8, [rbp+bstrString]
0x180048cad  mov     rdx, r14
0x180048cb0  mov     dword ptr [rbp+bstrString], r12d
0x180048cb4  mov     rax, [rax+18h]
0x180048cb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048cbd  test    eax, eax
0x180048cbf  js      short loc_180048CCB
0x180048cc1  test    byte ptr [rbp+bstrString], 4
0x180048cc5  jnz     loc_180048E47
0x180048ccb  lea     rcx, [rbp+ppURI]
0x180048ccf  mov     dword ptr [rbp+bstrString], r12d
0x180048cd3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180048cd8  mov     r10, [rbp+psz]
0x180048cdc  test    r10, r10
0x180048cdf  jz      short loc_180048D01
0x180048ce1  cmp     dword ptr [rbp+arg_28], 2
0x180048ce5  jb      short loc_180048D01
0x180048ce7  mov     edx, dword ptr [rbp+arg_28]
0x180048cea  lea     r8, [rbp+pcchLength]; pcchLength
0x180048cee  shr     rdx, 1; cchMax
0x180048cf1  mov     rcx, r10; psz
0x180048cf4  call    StringLengthWorkerW
0x180048cf9  test    eax, eax
0x180048cfb  jns     loc_180048E57
0x180048d01  mov     edi, 3
0x180048d06  mov     rcx, [rbp+ppURI]
0x180048d0a  xor     ebx, ebx
0x180048d0c  test    dil, dil
0x180048d0f  mov     [r15], dil
0x180048d12  setnz   bl
0x180048d15  test    rcx, rcx
0x180048d18  jz      short loc_180048D2E
0x180048d1a  mov     [rbp+ppURI], 0
0x180048d22  mov     rdx, [rcx]
0x180048d25  mov     rax, [rdx+10h]
0x180048d29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048d2e  mov     eax, ebx
0x180048d30  jmp     loc_180048B42
0x180048d35  mov     rbx, [rbp+arg_48]
0x180048d3c  test    rbx, rbx
0x180048d3f  jz      short loc_180048D01
0x180048d41  lea     rcx, [rbp+ppURI]
0x180048d45  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180048d4a  mov     edx, dword ptr [rbp+arg_28]; unsigned __int8 *
0x180048d4d  lea     r9, [rbp+ppURI]; unsigned int
0x180048d51  mov     rcx, [rbp+psz]; this
0x180048d55  mov     r8d, 4; unsigned int
0x180048d5b  call    ?GetUriFromContext@AppProtocolsCommon@@YAJPEBEKKPEAPEAUIUri@@@Z; AppProtocolsCommon::GetUriFromContext(uchar const *,ulong,ulong,IUri * *)
0x180048d60  test    eax, eax
0x180048d62  js      short loc_180048D01
0x180048d64  mov     rcx, [rbp+ppURI]; this
0x180048d68  lea     r8, [rbp+pcchLength]; int *
0x180048d6c  lea     rdx, [rbp+bstrString]; struct IUri *
0x180048d70  mov     dword ptr [rbp+bstrString], 0
0x180048d77  mov     dword ptr [rbp+pcchLength], 0
0x180048d7e  call    ?IsPackageUri@AppProtocolsCommon@@YAJPEAUIUri@@PEAH1@Z; AppProtocolsCommon::IsPackageUri(IUri *,int *,int *)
0x180048d83  test    eax, eax
0x180048d85  js      loc_180048D01
0x180048d8b  cmp     dword ptr [rbp+bstrString], 0
0x180048d8f  jz      loc_180048D01
0x180048d95  mov     rax, [rbx]
0x180048d98  lea     r8, [rbp+bstrString]
0x180048d9c  mov     rdx, r14
0x180048d9f  mov     dword ptr [rbp+bstrString], 0
0x180048da6  mov     rcx, rbx
0x180048da9  mov     rax, [rax+28h]
0x180048dad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048db2  test    eax, eax
0x180048db4  js      loc_180048D01
0x180048dba  mov     esi, dword ptr [rbp+bstrString]
0x180048dbd  jmp     loc_180048E47
0x180048dc2  mov     rcx, [rbp+ppURI]
0x180048dc6  lea     rdx, [rbp+pcchLength]
0x180048dca  mov     edi, r12d
0x180048dcd  mov     [rbp+pcchLength], r12
0x180048dd1  mov     rax, [rcx]
0x180048dd4  mov     rax, [rax+98h]
0x180048ddb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048de0  mov     rcx, [rbp+pcchLength]; bstrString
0x180048de4  cmp     eax, esi
0x180048de6  jz      short loc_180048E10
0x180048de8  mov     ebx, eax
0x180048dea  test    eax, eax
0x180048dec  js      short loc_180048E10
0x180048dee  mov     rax, rcx
0x180048df1  sub     r13, rcx
0x180048df4  movzx   edx, word ptr [rax]
0x180048df7  movzx   r8d, word ptr [rax+r13]
0x180048dfc  sub     edx, r8d
0x180048dff  jnz     short loc_180048E0A
0x180048e01  add     rax, 2
0x180048e05  test    r8d, r8d
0x180048e08  jnz     short loc_180048DF4
0x180048e0a  test    edx, edx
0x180048e0c  jnz     short loc_180048E10
0x180048e0e  mov     edi, esi
0x180048e10  call    cs:__imp_SysFreeString
0x180048e16  test    ebx, ebx
0x180048e18  js      loc_180048D01
0x180048e1e  test    edi, edi
0x180048e20  jz      loc_180048D01
0x180048e26  mov     r8, [rbp+arg_38]; struct IUri *
0x180048e2d  lea     r9, [rbp+bstrString]; struct IAppxUrlHelper *
0x180048e31  mov     rdx, [rbp+ppURI]; struct IUri *
0x180048e35  mov     rcx, r14; this
0x180048e38  call    ?IsPackagedWebCompartmentXhrAllowed@AppProtocolsCommon@@YAJPEAUIUri@@0PEAVIAppxUrlHelper@@PEAH@Z; AppProtocolsCommon::IsPackagedWebCompartmentXhrAllowed(IUri *,IUri *,IAppxUrlHelper *,int *)
0x180048e3d  test    eax, eax
0x180048e3f  jns     loc_180048DBA
0x180048e45  xor     esi, esi
0x180048e47  test    esi, esi
0x180048e49  jz      loc_180048D01
0x180048e4f  xor     dil, dil
0x180048e52  jmp     loc_180048D06
0x180048e57  lea     r9, [rbp+ppURI]; ppURI
0x180048e5b  xor     r8d, r8d; dwReserved
0x180048e5e  mov     edx, 2080h; dwFlags
0x180048e63  mov     rcx, r10; pwzURI
0x180048e66  call    cs:__imp_CreateUri
0x180048e6c  test    eax, eax
0x180048e6e  js      loc_180048D01
0x180048e74  jmp     loc_180048DC2
0x180048e79  mov     eax, [rbp+arg_30]
  ... truncated ...
```
