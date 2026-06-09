# CServiceTokenInfo::RetrievePersistedServiceTokens(ushort const *,CIdentityTokenBag *)

- ea: `0x180047008`
- end: `0x180047595`
- name: `?RetrievePersistedServiceTokens@CServiceTokenInfo@@SAJPEBGPEAVCIdentityTokenBag@@@Z`
- size: `1421`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct CIdentityTokenBag *)`
- caller_count: `1`
- callee_count: `31`
- tags: `service_task, broker_com_uri`

## callers

- `0x180046f34`

## callees

- `0x18000b878`
- `0x18000c050`
- `0x18000ed04`
- `0x18000ed3c`
- `0x1800151c4`
- `0x180015980`
- `0x1800167b8`
- `0x180017af0`
- `0x1800191c0`
- `0x180019424`
- `0x180019690`
- `0x180019780`
- `0x18001a530`
- `0x18001a9c0`
- `0x18001bbb4`
- `0x180021b28`
- `0x180021bbc`
- `0x1800334f8`
- `0x1800396e8`
- `0x18003a398`
- `0x180047008`
- `0x18005a2dc`
- `0x180065110`
- `0x180067778`
- `0x1800858e0`
- `0x180086f40`
- `0x18008b4ac`
- `0x1800a3b60`
- `0x1800a4718`
- `0x1800dde38`
- `0x1800ef65c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800472bd`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800472bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047146`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047157`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047146`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047157`

## string_xrefs

- `0x1800470ca`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\singleidentity.cpp`
- `0x180047436`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\singleidentity.cpp`
- `0x18004749d`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\singleidentity.cpp`
- `0x180047125`: `WindowsLive:(token):name=`
- `0x180047239`: `Microsoft_WindowsLive:serviceticket:`
- `0x1800470b3`: `CServiceTokenInfo::RetrievePersistedServiceTokens`
- `0x1800474dc`: `CServiceTokenInfo::RetrievePersistedServiceTokens`
- `0x180047105`: `pTokenBag != nullptr`
- `0x1800474c4`: `hr = AssembleTokenBlob(pCred, PPCRL_CRED_SERVICETICKET_KEYWORD, wstrTokenBlob)`
- `0x180047210`: `Retrieve token %ls.`
- `0x1800474a6`: `hr = GetServiceName(pCred->TargetName, wstrServiceURI)`
- `0x1800474b5`: `hr = UnPack(wstrTokenBlob, dwTokenType, wstrToken, bpSessionKey, sessionKeyType, ctExpireTime)`
- `0x18004748b`: `hr = pTokenBag->AddStoredToken( strServiceURI, wstrToken, ctExpireTime, bpSessionKey, dwTokenType, sessionKeyType)`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall CServiceTokenInfo::RetrievePersistedServiceTokens(
        const unsigned __int16 *a1,
        struct CIdentityTokenBag *a2)
{
  int v4; // esi
  unsigned __int8 v5; // dl
  PPTraceStatus *v6; // rcx
  bool v7; // zf
  char v8; // cl
  char v9; // al
  const unsigned __int16 *String; // rax
  int v11; // r9d
  const char *v12; // rax
  unsigned int v13; // r8d
  unsigned int v14; // edx
  signed int LastError; // eax
  int v16; // r14d
  struct _CREDENTIALW *v17; // rbx
  unsigned __int8 v18; // dl
  PPTraceStatus *v19; // rcx
  char v20; // cl
  const unsigned __int16 *v21; // rax
  int ServiceName; // eax
  int v23; // r15d
  unsigned __int8 v24; // dl
  PPTraceStatus *v25; // rcx
  char v26; // cl
  const unsigned __int16 *v27; // rax
  __int64 v28; // rdx
  __int64 v29; // rcx
  _QWORD *v30; // rax
  __int64 v31; // rax
  int v32; // edi
  unsigned int v33; // ebx
  int v34; // eax
  int v35; // eax
  __int64 v36; // rax
  const char *v37; // rcx
  unsigned int v38; // r8d
  unsigned int v39; // ebx
  int v41; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v42; // [rsp+48h] [rbp-B8h] BYREF
  const void *v43; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v44; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v45; // [rsp+60h] [rbp-A0h] BYREF
  __int64 *v46; // [rsp+68h] [rbp-98h] BYREF
  int v47; // [rsp+70h] [rbp-90h] BYREF
  __int64 v48; // [rsp+78h] [rbp-88h] BYREF
  void **v49; // [rsp+80h] [rbp-80h] BYREF
  const unsigned __int16 *v50; // [rsp+88h] [rbp-78h]
  __int64 v51; // [rsp+90h] [rbp-70h]
  char v52; // [rsp+98h] [rbp-68h]
  LPCWSTR Filter; // [rsp+A0h] [rbp-60h] BYREF
  void **v54; // [rsp+A8h] [rbp-58h] BYREF
  struct _CREDENTIALW **v55[2]; // [rsp+B0h] [rbp-50h] BYREF
  void **v56; // [rsp+C0h] [rbp-40h] BYREF
  LPWSTR TargetName; // [rsp+C8h] [rbp-38h]
  __int64 v58; // [rsp+D0h] [rbp-30h]
  char v59; // [rsp+D8h] [rbp-28h]
  __int64 v60; // [rsp+E0h] [rbp-20h] BYREF
  char v61[8]; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v62; // [rsp+F0h] [rbp-10h] BYREF
  char v63[8]; // [rsp+F8h] [rbp-8h] BYREF
  char v64[8]; // [rsp+100h] [rbp+0h] BYREF
  const char *v65[5]; // [rsp+108h] [rbp+8h] BYREF
  void *Block; // [rsp+130h] [rbp+30h] BYREF
  char v67; // [rsp+138h] [rbp+38h] BYREF

  v4 = 0;
  LODWORD(v46) = 0;
  v41 = 0;
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&Filter);
  *(_OWORD *)v55 = 0;
  v54 = &SmartCredManArrayMem::`vftable';
  if ( !PPTraceShouldRedact() || (LOBYTE(v6) = 1, v7 = !PPTraceStatus::TraceOnFlag(v6, v5), v9 = v8, v7) )
    v9 = 0;
  v50 = a1;
  v51 = 0;
  v52 = v9;
  v49 = &PPRedactedStringW::`vftable';
  String = PPRedactedStringW::GetString((PPRedactedStringW *)&v49);
  CTraceFuncW<long>::CTraceFuncW<long>(
    v65,
    "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\singleidentity.cpp",
    5138,
    (const char *)&v41,
    "CServiceTokenInfo::RetrievePersistedServiceTokens",
    L"wstrUserName: %ls",
    String);
  PPRedactedStringW::~PPRedactedStringW((PPRedactedStringW *)&v49);
  if ( !a1 || !*a1 )
  {
    v11 = -2147188701;
    v12 = "wstrUserName != nullptr && *wstrUserName != L'\\0'";
    v13 = 5141;
    goto LABEL_46;
  }
  if ( !a2 )
  {
    v11 = -2147188475;
    v12 = "pTokenBag != nullptr";
    v13 = 5142;
LABEL_46:
    v41 = v11;
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\singleidentity.cpp",
      "CServiceTokenInfo::RetrievePersistedServiceTokens",
      v13,
      v11,
      v12);
    goto LABEL_47;
  }
  CTokenInfo::GetCredTargetName(L"WindowsLive:(token):name=", a1, "*", &Filter);
  if ( (unsigned int)CredmanUtility::CredEnumerateW(Filter, v14, (unsigned int *)v55, &v55[1]) )
  {
    v16 = 0;
    if ( LODWORD(v55[0]) )
    {
      while ( 1 )
      {
        v17 = v55[1][v16];
        ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v45);
        ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v42);
        ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v44);
        v47 = 0;
        ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v43);
        v50 = 0;
        LODWORD(v49) = 0;
        LODWORD(v51) = 0;
        LODWORD(v46) = 0;
        v48 = 0;
        if ( !PPTraceShouldRedact() || (LOBYTE(v19) = 1, !PPTraceStatus::TraceOnFlag(v19, v18)) )
          v20 = 0;
        v56 = &PPRedactedStringW::`vftable';
        TargetName = v17->TargetName;
        v58 = 0;
        v59 = v20;
        v21 = PPRedactedStringW::GetString((PPRedactedStringW *)&v56);
        TracePrintW(
          5u,
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\singleidentity.cpp",
          0x1437u,
          L"Retrieve token %ls.",
          v21);
        PPRedactedStringW::~PPRedactedStringW((PPRedactedStringW *)&v56);
        ServiceName = CTokenInfo::AssembleTokenBlob(v17, L"Microsoft_WindowsLive:serviceticket:", &v44);
        v41 = ServiceName;
        if ( ServiceName < 0 )
          break;
        ServiceName = CServiceTokenInfo::UnPack(
                        v44,
                        &v47,
                        (char *)&v43,
                        (unsigned __int8 **)&v49,
                        (enum SessionKeyTypes::Type *)&v46,
                        (__int64)&v48);
        v41 = ServiceName;
        if ( ServiceName < 0 )
        {
          v37 = "hr = UnPack(wstrTokenBlob, dwTokenType, wstrToken, bpSessionKey, sessionKeyType, ctExpireTime)";
          v38 = 5179;
          goto LABEL_43;
        }
        ServiceName = CTokenInfo::GetServiceName(v17->TargetName, &v45);
        v41 = ServiceName;
        if ( ServiceName < 0 )
        {
          v37 = "hr = GetServiceName(pCred->TargetName, wstrServiceURI)";
          v38 = 5182;
          goto LABEL_43;
        }
        v23 = v47;
        if ( (v47 != 5 || (unsigned int)_o__wcsicmp(v45, L"http://Passport.NET/purpose"))
          && CTokenInfo::IsExpired((struct ATL::CTime *)&v48, 5) )
        {
          if ( byte_1801C36C4 < 0 )
          {
            v60 = AsFileTime(&v48);
            if ( byte_1801C36C4 < 0 )
            {
              if ( !PPTraceShouldRedact() || (LOBYTE(v25) = 1, !PPTraceStatus::TraceOnFlag(v25, v24)) )
                v26 = 0;
              v56 = &PPRedactedStringW::`vftable';
              TargetName = v17->TargetName;
              v58 = 0;
              v59 = v26;
              v4 |= 1u;
              LODWORD(v46) = v4;
              v27 = PPRedactedStringW::GetString((PPRedactedStringW *)&v56);
              McTemplateU0zm_EventWriteTransfer(v29, v28, v27, &v60);
            }
            if ( (v4 & 1) != 0 )
            {
              v4 &= ~1u;
              PPRedactedStringW::~PPRedactedStringW((PPRedactedStringW *)&v56);
            }
          }
          CredmanUtility::CredDeleteW(v17->TargetName, 1u, 0);
        }
        else
        {
          v30 = (_QWORD *)ATL::CW2AEX<128>::CW2AEX<128>(&Block, v45);
          ATL::CSimpleStringT<char,0>::SetString(&v42, *v30);
          if ( Block != &v67 )
            free(Block);
          v31 = ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(
                  v61,
                  &v42);
          if ( !(unsigned int)CIdentityTokenBag::HasToken(a2, v31) )
          {
            v32 = (int)v46;
            v46 = &v62;
            v33 = (unsigned int)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                                  &v62,
                                  &v43);
            v34 = ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(
                    v63,
                    &v42);
            v35 = CIdentityTokenBag::AddStoredToken((_DWORD)a2, v34, v33, (unsigned int)&v48, (__int64)&v49, v23, v32);
            v41 = v35;
            if ( v35 < 0 )
            {
              Telemetry::IfFailExit(
                "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\singleidentity.cpp",
                "CServiceTokenInfo::RetrievePersistedServiceTokens",
                0x1460u,
                v35,
                "hr = pTokenBag->AddStoredToken( strServiceURI, wstrToken, ctExpireTime, bpSessionKey, dwTokenType, sessionKeyType)");
              goto LABEL_44;
            }
            v36 = ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(
                    v64,
                    &v42);
            CIdentityTokenBag::SetTokenCachedFlag(a2, v36);
          }
        }
        CBytePtr::Empty((CBytePtr *)&v49);
        ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v43);
        ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v44);
        ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v42);
        ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v45);
        if ( (unsigned int)++v16 >= LODWORD(v55[0]) )
          goto LABEL_47;
      }
      v37 = "hr = AssembleTokenBlob(pCred, PPCRL_CRED_SERVICETICKET_KEYWORD, wstrTokenBlob)";
      v38 = 5177;
LABEL_43:
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\singleidentity.cpp",
        "CServiceTokenInfo::RetrievePersistedServiceTokens",
        v38,
        ServiceName,
        v37);
LABEL_44:
      CBytePtr::Empty((CBytePtr *)&v49);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v43);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v44);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v42);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v45);
    }
  }
  else if ( GetLastError() != 1168 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v41 = LastError;
  }
LABEL_47:
  v39 = v41;
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v65);
  SmartCredManArrayMem::~SmartCredManArrayMem((SmartCredManArrayMem *)&v54);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&Filter);
  return v39;
}

```

## disassembly

```asm
0x180047008  mov     [rsp-8+arg_10], rbx
0x18004700d  push    rbp
0x18004700e  push    rsi
0x18004700f  push    rdi
0x180047010  push    r12
0x180047012  push    r13
0x180047014  push    r14
0x180047016  push    r15
0x180047018  lea     rbp, [rsp-0D0h]
0x180047020  sub     rsp, 1D0h
0x180047027  mov     rax, cs:__security_cookie
0x18004702e  xor     rax, rsp
0x180047031  mov     [rbp+100h+var_40], rax
0x180047038  mov     r12, rdx
0x18004703b  mov     rbx, rcx
0x18004703e  xor     r13d, r13d
0x180047041  mov     esi, r13d
0x180047044  mov     dword ptr [rsp+200h+var_198], r13d
0x180047049  mov     [rsp+200h+var_1C0], r13d
0x18004704e  lea     rcx, [rbp+100h+Filter]
0x180047052  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180047057  nop
0x180047058  xorps   xmm0, xmm0
0x18004705b  movups  xmmword ptr [rbp+100h+var_150], xmm0
0x18004705f  lea     rax, ??_7SmartCredManArrayMem@@6B@; const SmartCredManArrayMem::`vftable'
0x180047066  mov     [rbp+100h+var_158], rax
0x18004706a  call    ?PPTraceShouldRedact@@YA_NXZ; PPTraceShouldRedact(void)
0x18004706f  test    al, al
0x180047071  jz      short loc_180047080
0x180047073  mov     cl, 1; this
0x180047075  call    ?TraceOnFlag@PPTraceStatus@@YA_NE@Z; PPTraceStatus::TraceOnFlag(uchar)
0x18004707a  test    al, al
0x18004707c  mov     al, cl
0x18004707e  jnz     short loc_180047083
0x180047080  mov     al, r13b
0x180047083  mov     [rbp+100h+var_178], rbx
0x180047087  mov     [rbp+100h+var_170], r13
0x18004708b  mov     [rbp+100h+var_168], al
0x18004708e  lea     rax, ??_7PPRedactedStringW@@6B@; const PPRedactedStringW::`vftable'
0x180047095  mov     [rbp+100h+var_180], rax
0x180047099  lea     rcx, [rbp+100h+var_180]; this
0x18004709d  call    ?GetString@PPRedactedStringW@@QEAAPEBGXZ; PPRedactedStringW::GetString(void)
0x1800470a2  mov     [rsp+200h+var_1D0], rax
0x1800470a7  lea     rax, aWstrusernameLs; "wstrUserName: %ls"
0x1800470ae  mov     [rsp+200h+var_1D8], rax
0x1800470b3  lea     r15, aCservicetokeni_3; "CServiceTokenInfo::RetrievePersistedSer"...
0x1800470ba  mov     [rsp+200h+var_1E0], r15
0x1800470bf  lea     r9, [rsp+200h+var_1C0]
0x1800470c4  mov     r8d, 1412h
0x1800470ca  lea     rdi, aOnecoreuapDsEx_24; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800470d1  mov     rdx, rdi
0x1800470d4  lea     rcx, [rbp+100h+var_F8]
0x1800470d8  call    ??0?$CTraceFuncW@J@@QEAA@PEBDKAEAJ0PEBGZZ; CTraceFuncW<long>::CTraceFuncW<long>(char const *,ulong,long &,char const *,ushort const *,...)
0x1800470dd  nop
0x1800470de  lea     rcx, [rbp+100h+var_180]; this
0x1800470e2  call    ??1PPRedactedStringW@@QEAA@XZ; PPRedactedStringW::~PPRedactedStringW(void)
0x1800470e7  test    rbx, rbx
0x1800470ea  jz      loc_180047520
0x1800470f0  cmp     [rbx], r13w
0x1800470f4  jz      loc_180047520
0x1800470fa  test    r12, r12
0x1800470fd  jnz     short loc_180047117
0x1800470ff  mov     r9d, 80048105h
0x180047105  lea     rax, aPtokenbagNullp; "pTokenBag != nullptr"
0x18004710c  mov     r8d, 1416h
0x180047112  jmp     loc_180047533
0x180047117  lea     r9, [rbp+100h+Filter]
0x18004711b  lea     r8, asc_18013D3C0; "*"
0x180047122  mov     rdx, rbx
0x180047125  lea     rcx, aWindowsliveTok; "WindowsLive:(token):name="
0x18004712c  call    ?GetCredTargetName@CTokenInfo@@KAJPEBG0PEBDAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; CTokenInfo::GetCredTargetName(ushort const *,ushort const *,char const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180047131  lea     r9, [rbp+100h+var_150+8]; struct _CREDENTIALW ***
0x180047135  lea     r8, [rbp+100h+var_150]; unsigned int *
0x180047139  mov     rcx, [rbp+100h+Filter]; Filter
0x18004713d  call    ?CredEnumerateW@CredmanUtility@@SAHPEBGKPEAKPEAPEAPEAU_CREDENTIALW@@@Z; CredmanUtility::CredEnumerateW(ushort const *,ulong,ulong *,_CREDENTIALW * * *)
0x180047142  test    eax, eax
0x180047144  jnz     short loc_180047172
0x180047146  call    cs:__imp_GetLastError
0x18004714c  cmp     eax, 490h
0x180047151  jz      loc_180047548
0x180047157  call    cs:__imp_GetLastError
0x18004715d  test    eax, eax
0x18004715f  jle     short loc_180047169
0x180047161  movzx   eax, ax
0x180047164  or      eax, 80070000h
0x180047169  mov     [rsp+200h+var_1C0], eax
0x18004716d  jmp     loc_180047548
0x180047172  mov     r14d, r13d
0x180047175  cmp     dword ptr [rbp+100h+var_150], r13d
0x180047179  jbe     loc_180047548
0x18004717f  lea     r15, ??_7PPRedactedStringW@@6B@; const PPRedactedStringW::`vftable'
0x180047186  mov     ecx, r14d
0x180047189  mov     rax, [rbp+100h+var_150+8]
0x18004718d  mov     rbx, [rax+rcx*8]
0x180047191  lea     rcx, [rsp+200h+var_1A0]
0x180047196  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18004719b  nop
0x18004719c  lea     rcx, [rsp+200h+var_1B8]
0x1800471a1  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800471a6  nop
0x1800471a7  lea     rcx, [rsp+200h+var_1A8]
0x1800471ac  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800471b1  nop
0x1800471b2  mov     [rsp+200h+var_190], r13d
0x1800471b7  lea     rcx, [rsp+200h+var_1B0]
0x1800471bc  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800471c1  nop
0x1800471c2  mov     [rbp+100h+var_178], r13
0x1800471c6  mov     dword ptr [rbp+100h+var_180], r13d
0x1800471ca  mov     dword ptr [rbp+100h+var_170], r13d
0x1800471ce  mov     dword ptr [rsp+200h+var_198], r13d
0x1800471d3  mov     [rsp+200h+var_188], r13
0x1800471d8  call    ?PPTraceShouldRedact@@YA_NXZ; PPTraceShouldRedact(void)
0x1800471dd  test    al, al
0x1800471df  jz      short loc_1800471EC
0x1800471e1  mov     cl, 1; this
0x1800471e3  call    ?TraceOnFlag@PPTraceStatus@@YA_NE@Z; PPTraceStatus::TraceOnFlag(uchar)
0x1800471e8  test    al, al
0x1800471ea  jnz     short loc_1800471EF
0x1800471ec  mov     cl, r13b
0x1800471ef  mov     [rbp+100h+var_140], r15
0x1800471f3  mov     rax, [rbx+8]
0x1800471f7  mov     [rbp+100h+var_138], rax
0x1800471fb  mov     [rbp+100h+var_130], r13
0x1800471ff  mov     [rbp+100h+var_128], cl
0x180047202  lea     rcx, [rbp+100h+var_140]; this
0x180047206  call    ?GetString@PPRedactedStringW@@QEAAPEBGXZ; PPRedactedStringW::GetString(void)
0x18004720b  mov     [rsp+200h+var_1E0], rax
0x180047210  lea     r9, aRetrieveTokenL; "Retrieve token %ls."
0x180047217  mov     r8d, 1437h; unsigned int
0x18004721d  mov     rdx, rdi; char *
0x180047220  mov     ecx, 5; unsigned __int8
0x180047225  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004722a  nop
0x18004722b  lea     rcx, [rbp+100h+var_140]; this
0x18004722f  call    ??1PPRedactedStringW@@QEAA@XZ; PPRedactedStringW::~PPRedactedStringW(void)
0x180047234  lea     r8, [rsp+200h+var_1A8]
0x180047239  lea     rdx, aMicrosoftWindo; "Microsoft_WindowsLive:serviceticket:"
0x180047240  mov     rcx, rbx
0x180047243  call    ?AssembleTokenBlob@CTokenInfo@@SAJPEAU_CREDENTIALW@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; CTokenInfo::AssembleTokenBlob(_CREDENTIALW *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180047248  mov     [rsp+200h+var_1C0], eax
0x18004724c  test    eax, eax
0x18004724e  js      loc_1800474C4
0x180047254  lea     rax, [rsp+200h+var_188]
0x180047259  mov     [rsp+200h+var_1D8], rax; __int64
0x18004725e  lea     rax, [rsp+200h+var_198]
0x180047263  mov     [rsp+200h+var_1E0], rax; enum SessionKeyTypes::Type *
0x180047268  lea     r9, [rbp+100h+var_180]
0x18004726c  lea     r8, [rsp+200h+var_1B0]
0x180047271  lea     rdx, [rsp+200h+var_190]
0x180047276  mov     rcx, [rsp+200h+var_1A8]; unsigned __int16 *
0x18004727b  call    ?UnPack@CServiceTokenInfo@@KAJPEBGAEAKAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAVCBytePtr@@AEAW4Type@SessionKeyTypes@@AEAVCTime@3@@Z; CServiceTokenInfo::UnPack(ushort const *,ulong &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,CBytePtr &,SessionKeyTypes::Type &,ATL::CTime &)
0x180047280  mov     [rsp+200h+var_1C0], eax
0x180047284  test    eax, eax
0x180047286  js      loc_1800474B5
0x18004728c  lea     rdx, [rsp+200h+var_1A0]
0x180047291  mov     rcx, [rbx+8]
0x180047295  call    ?GetServiceName@CTokenInfo@@KAJPEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; CTokenInfo::GetServiceName(ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x18004729a  mov     [rsp+200h+var_1C0], eax
0x18004729e  test    eax, eax
0x1800472a0  js      loc_1800474A6
0x1800472a6  mov     r15d, [rsp+200h+var_190]
0x1800472ab  cmp     r15d, 5
0x1800472af  jnz     short loc_1800472CB
0x1800472b1  lea     rdx, aHttpPassportNe; "http://Passport.NET/purpose"
0x1800472b8  mov     rcx, [rsp+200h+var_1A0]
0x1800472bd  call    cs:__imp__o__wcsicmp
0x1800472c3  test    eax, eax
0x1800472c5  jz      loc_180047377
0x1800472cb  mov     edx, 5; int
0x1800472d0  lea     rcx, [rsp+200h+var_188]; struct ATL::CTime *
0x1800472d5  call    ?IsExpired@CTokenInfo@@SA_NAEAVCTime@ATL@@H@Z; CTokenInfo::IsExpired(ATL::CTime &,int)
0x1800472da  test    al, al
0x1800472dc  jz      loc_180047377
0x1800472e2  cmp     cs:byte_1801C36C4, r13b
0x1800472e9  jge     short loc_180047362
0x1800472eb  lea     rcx, [rsp+200h+var_188]
0x1800472f0  call    AsFileTime
0x1800472f5  mov     [rbp+100h+var_120], rax
0x1800472f9  cmp     cs:byte_1801C36C4, r13b
0x180047300  jge     short loc_180047350
0x180047302  call    ?PPTraceShouldRedact@@YA_NXZ; PPTraceShouldRedact(void)
0x180047307  test    al, al
0x180047309  jz      short loc_180047316
0x18004730b  mov     cl, 1; this
0x18004730d  call    ?TraceOnFlag@PPTraceStatus@@YA_NE@Z; PPTraceStatus::TraceOnFlag(uchar)
0x180047312  test    al, al
0x180047314  jnz     short loc_180047319
0x180047316  mov     cl, r13b
0x180047319  lea     rax, ??_7PPRedactedStringW@@6B@; const PPRedactedStringW::`vftable'
0x180047320  mov     [rbp+100h+var_140], rax
0x180047324  mov     rax, [rbx+8]
0x180047328  mov     [rbp+100h+var_138], rax
0x18004732c  mov     [rbp+100h+var_130], r13
0x180047330  mov     [rbp+100h+var_128], cl
0x180047333  or      esi, 1
0x180047336  mov     dword ptr [rsp+200h+var_198], esi
0x18004733a  lea     rcx, [rbp+100h+var_140]; this
0x18004733e  call    ?GetString@PPRedactedStringW@@QEAAPEBGXZ; PPRedactedStringW::GetString(void)
0x180047343  mov     r8, rax
0x180047346  lea     r9, [rbp+100h+var_120]
0x18004734a  call    McTemplateU0zm_EventWriteTransfer
0x18004734f  nop
0x180047350  test    sil, 1
0x180047354  jz      short loc_180047362
0x180047356  and     esi, 0FFFFFFFEh
0x180047359  lea     rcx, [rbp+100h+var_140]; this
0x18004735d  call    ??1PPRedactedStringW@@QEAA@XZ; PPRedactedStringW::~PPRedactedStringW(void)
0x180047362  xor     r8d, r8d; Flags
0x180047365  lea     edx, [r8+1]; Type
0x180047369  mov     rcx, [rbx+8]; TargetName
0x18004736d  call    ?CredDeleteW@CredmanUtility@@SAHPEBGKK@Z; CredmanUtility::CredDeleteW(ushort const *,ulong,ulong)
0x180047372  jmp     loc_18004743D
0x180047377  mov     rdx, [rsp+200h+var_1A0]
0x18004737c  lea     rcx, [rbp+100h+Block]
0x180047380  call    ??0?$CW2AEX@$0IA@@ATL@@QEAA@PEBG@Z; ATL::CW2AEX<128>::CW2AEX<128>(ushort const *)
0x180047385  nop
0x180047386  mov     rdx, [rax]
0x180047389  lea     rcx, [rsp+200h+var_1B8]
0x18004738e  call    ?SetString@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBD@Z; ATL::CSimpleStringT<char,0>::SetString(char const *)
0x180047393  nop
0x180047394  mov     rcx, [rbp+100h+Block]; Block
0x180047398  lea     rax, [rbp+100h+var_C8]
0x18004739c  cmp     rcx, rax
0x18004739f  jz      short loc_1800473A6
0x1800473a1  call    free
0x1800473a6  lea     rdx, [rsp+200h+var_1B8]
0x1800473ab  lea     rcx, [rbp+100h+var_118]
0x1800473af  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> const &)
0x1800473b4  mov     rdx, rax
0x1800473b7  mov     rcx, r12
0x1800473ba  call    ?HasToken@CIdentityTokenBag@@QEAAHV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@@Z; CIdentityTokenBag::HasToken(ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>)
0x1800473bf  test    eax, eax
0x1800473c1  jnz     short loc_18004743D
0x1800473c3  mov     edi, dword ptr [rsp+200h+var_198]
0x1800473c7  lea     rax, [rbp+100h+var_110]
0x1800473cb  mov     [rsp+200h+var_198], rax
0x1800473d0  lea     rdx, [rsp+200h+var_1B0]
0x1800473d5  lea     rcx, [rbp+100h+var_110]
0x1800473d9  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1800473de  mov     rbx, rax
0x1800473e1  lea     rdx, [rsp+200h+var_1B8]
0x1800473e6  lea     rcx, [rbp+100h+var_108]
0x1800473ea  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> const &)
0x1800473ef  nop
0x1800473f0  mov     dword ptr [rsp+200h+var_1D0], edi
0x1800473f4  mov     dword ptr [rsp+200h+var_1D8], r15d
0x1800473f9  lea     rcx, [rbp+100h+var_180]
0x1800473fd  mov     [rsp+200h+var_1E0], rcx
0x180047402  lea     r9, [rsp+200h+var_188]
0x180047407  mov     r8, rbx
0x18004740a  mov     rdx, rax
0x18004740d  mov     rcx, r12
0x180047410  call    ?AddStoredToken@CIdentityTokenBag@@QEAAJV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@3@AEAVCTime@3@AEBVCBytePtr@@KW4Type@SessionKeyTypes@@@Z; CIdentityTokenBag::AddStoredToken(ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CTime &,CBytePtr const &,ulong,SessionKeyTypes::Type)
0x180047415  mov     [rsp+200h+var_1C0], eax
0x180047419  test    eax, eax
0x18004741b  js      short loc_18004748B
0x18004741d  lea     rdx, [rsp+200h+var_1B8]
0x180047422  lea     rcx, [rbp+100h+var_100]
0x180047426  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> const &)
0x18004742b  mov     rdx, rax
0x18004742e  mov     rcx, r12
0x180047431  call    ?SetTokenCachedFlag@CIdentityTokenBag@@QEAAHV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@@Z; CIdentityTokenBag::SetTokenCachedFlag(ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>)
0x180047436  lea     rdi, aOnecoreuapDsEx_24; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18004743d  lea     rcx, [rbp+100h+var_180]; this
0x180047441  call    ?Empty@CBytePtr@@QEAAXXZ; CBytePtr::Empty(void)
0x180047446  nop
0x180047447  lea     rcx, [rsp+200h+var_1B0]
0x18004744c  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180047451  nop
0x180047452  lea     rcx, [rsp+200h+var_1A8]
0x180047457  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18004745c  nop
0x18004745d  lea     rcx, [rsp+200h+var_1B8]
0x180047462  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180047467  nop
0x180047468  lea     rcx, [rsp+200h+var_1A0]
0x18004746d  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180047472  inc     r14d
0x180047475  cmp     r14d, dword ptr [rbp+100h+var_150]
0x180047479  lea     r15, ??_7PPRedactedStringW@@6B@; const PPRedactedStringW::`vftable'
0x180047480  jb      loc_180047186
0x180047486  jmp     loc_180047548
0x18004748b  lea     rcx, aHrPtokenbagAdd; "hr = pTokenBag->AddStoredToken( strServ"...
0x180047492  mov     [rsp+200h+var_1E0], rcx
0x180047497  mov     r8d, 1460h
0x18004749d  lea     rcx, aOnecoreuapDsEx_24; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800474a4  jmp     short loc_1800474D9
0x1800474a6  lea     rcx, aHrGetservicena_0; "hr = GetServiceName(pCred->TargetName, "...
0x1800474ad  mov     r8d, 143Eh
0x1800474b3  jmp     short loc_1800474D1
0x1800474b5  lea     rcx, aHrUnpackWstrto; "hr = UnPack(wstrTokenBlob, dwTokenType,"...
0x1800474bc  mov     r8d, 143Bh
0x1800474c2  jmp     short loc_1800474D1
0x1800474c4  lea     rcx, aHrAssembletoke_0; "hr = AssembleTokenBlob(pCred, PPCRL_CRE"...
0x1800474cb  mov     r8d, 1439h; unsigned int
0x1800474d1  mov     [rsp+200h+var_1E0], rcx; char *
0x1800474d6  mov     rcx, rdi; char *
0x1800474d9  mov     r9d, eax; int
0x1800474dc  lea     rdx, aCservicetokeni_3; "CServiceTokenInfo::RetrievePersistedSer"...
  ... truncated ...
```
