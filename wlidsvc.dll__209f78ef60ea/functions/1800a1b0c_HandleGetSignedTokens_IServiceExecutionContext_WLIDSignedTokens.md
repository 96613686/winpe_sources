# HandleGetSignedTokens(IServiceExecutionContext *,_WLIDSignedTokens * *)

- ea: `0x1800a1b0c`
- end: `0x1800a1f71`
- name: `?HandleGetSignedTokens@@YAJPEAVIServiceExecutionContext@@PEAPEAU_WLIDSignedTokens@@@Z`
- size: `1125`
- prototype: `__int64 __fastcall(struct IServiceExecutionContext *, struct _WLIDSignedTokens **)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800a19d0`

## callees

- `0x180009e98`
- `0x18000a36c`
- `0x18000c050`
- `0x18000ed04`
- `0x18000fd04`
- `0x1800151c4`
- `0x180019690`
- `0x18001a9c0`
- `0x18001ad00`
- `0x180030120`
- `0x180043344`
- `0x18007a2e0`
- `0x18008a50c`
- `0x1800a1b0c`
- `0x1800b3670`
- `0x180128010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800a1d85`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800a1db7`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800a1e2b`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800a1d85`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800a1db7`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800a1e2b`

## string_xrefs

- `0x1800a1ba9`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x1800a1c0d`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x1800a1d16`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x1800a1e07`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x1800a1ee6`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x1800a1b82`: `HandleGetSignedTokens`
- `0x1800a1d48`: `HandleGetSignedTokens`
- `0x1800a1e00`: `HandleGetSignedTokens`
- `0x1800a1bf5`: `hr = pServiceWrapper->Impersonate(&client)`
- `0x1800a1c3d`: `hr = pServiceWrapper->GetLogonId(&client, logonId)`
- `0x1800a1d09`: `Error generating signed tokens: userTokenHr=0x%x deviceTokenHr=0x%x`
- `0x1800a1d33`: `hr = userTokenHr`
- `0x1800a1deb`: `hr = StringCchCopyW(pAutoUserToken, userTokenBufferSizeChars, (LPCWSTR)userToken)`
- `0x1800a1e5d`: `hr = StringCchCopyW(pAutoDeviceToken, deviceTokenBufferSizeChars, (LPCWSTR)deviceToken)`
- `0x1800a1ed9`: `Error being collapsed to common error code. Original error: 0x%x.`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall HandleGetSignedTokens(struct IServiceExecutionContext *a1, struct _WLIDSignedTokens **a2)
{
  __int64 v4; // rsi
  __int64 v5; // r15
  int v6; // eax
  const char *v7; // rcx
  unsigned int v8; // r8d
  int LocalSignedUserToken; // edi
  __int64 (__fastcall *v10)(__int64, const unsigned __int16 *, __int64, __int64, _QWORD, _QWORD, _QWORD, __int64 *); // rbx
  int v11; // r14d
  unsigned __int16 *v12; // rsi
  unsigned __int16 *v13; // rbx
  struct _WLIDSignedTokens *v14; // r15
  __int64 v15; // rdi
  int v16; // eax
  const char *v17; // rcx
  unsigned int v18; // r8d
  unsigned int v19; // edi
  unsigned int v20; // ebx
  char *v22; // [rsp+20h] [rbp-E0h]
  char *v23; // [rsp+20h] [rbp-E0h]
  __int64 v24; // [rsp+28h] [rbp-D8h]
  __int64 v25; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v26; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 *v27; // [rsp+70h] [rbp-90h] BYREF
  __int64 v28; // [rsp+78h] [rbp-88h]
  __int64 v29; // [rsp+80h] [rbp-80h]
  unsigned __int16 *v30; // [rsp+88h] [rbp-78h] BYREF
  __int64 v31; // [rsp+90h] [rbp-70h]
  __int64 v32; // [rsp+98h] [rbp-68h]
  struct _WLIDSignedTokens *v33; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v34; // [rsp+A8h] [rbp-58h]
  __int64 v35; // [rsp+B0h] [rbp-50h]
  __int64 v36; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v37; // [rsp+C0h] [rbp-40h] BYREF
  int *v38[4]; // [rsp+C8h] [rbp-38h] BYREF
  _QWORD v39[11]; // [rsp+E8h] [rbp-18h] BYREF
  int v40; // [rsp+150h] [rbp+50h] BYREF
  unsigned __int16 *v41; // [rsp+160h] [rbp+60h] BYREF
  unsigned __int16 *v42; // [rsp+168h] [rbp+68h] BYREF

  v40 = 0;
  v4 = (*(__int64 (__fastcall **)(struct IServiceExecutionContext *))(*(_QWORD *)a1 + 80LL))(a1);
  v5 = (*(__int64 (__fastcall **)(struct IServiceExecutionContext *))(*(_QWORD *)a1 + 56LL))(a1);
  v26 = 0;
  v25 = 0;
  v36 = 0;
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v37);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v42);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v41);
  v39[0] = "HandleGetSignedTokens";
  v39[1] = &v40;
  v39[2] = 0;
  v39[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
    "HandleGetSignedTokens",
    (const char *)0x2ACB,
    0,
    (const unsigned __int16 *)v22);
  ErrorVerifier::ErrorVerifier((ErrorVerifier *)v38, "HandleGetSignedTokens", &v40, 0xBu, &qword_18014A0F0);
  v6 = (*(__int64 (__fastcall **)(__int64, __int64 *, _QWORD))(*(_QWORD *)v4 + 32LL))(v4, &v25, 0);
  v40 = v6;
  if ( v6 < 0 )
  {
    v7 = "hr = pServiceWrapper->Impersonate(&client)";
    v8 = 10964;
LABEL_3:
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
      "HandleGetSignedTokens",
      v8,
      v6,
      v7);
    goto LABEL_27;
  }
  v6 = (*(__int64 (__fastcall **)(__int64, __int64 *, __int64 *))(*(_QWORD *)v4 + 40LL))(v4, &v25, &v36);
  v40 = v6;
  if ( v6 < 0 )
  {
    v7 = "hr = pServiceWrapper->GetLogonId(&client, logonId)";
    v8 = 10965;
    goto LABEL_3;
  }
  LocalSignedUserToken = GetLocalSignedUserToken(a1, &v36, &v42);
  v10 = *(__int64 (__fastcall **)(__int64, const unsigned __int16 *, __int64, __int64, _QWORD, _QWORD, _QWORD, __int64 *))(*(_QWORD *)v4 + 128LL);
  CAutoRefPtr<CSingleIdentity>::Deinit(&v26);
  v11 = v10(v4, L"{AFDA72BF-3409-413a-B54E-2AB8D66A7826}", 16, 0x4000, 0, 0, 0, &v26);
  if ( v11 >= 0 )
    v11 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, const wchar_t *, _QWORD, _QWORD, _QWORD, __int64 *, unsigned __int16 **, _QWORD))(*(_QWORD *)v5 + 96LL))(
            v5,
            v26,
            0,
            L"Default",
            0,
            0,
            0,
            &v37,
            &v41,
            0);
  if ( LocalSignedUserToken >= 0 && v11 >= 0
    || (LODWORD(v24) = v11,
        LODWORD(v23) = LocalSignedUserToken,
        TracePrintW(
          2u,
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
          0x2AECu,
          L"Error generating signed tokens: userTokenHr=0x%x deviceTokenHr=0x%x",
          v23,
          v24),
        LocalSignedUserToken >= 0)
    || v11 >= 0 )
  {
    v33 = 0;
    v35 = 0;
    v34 = 0;
    v12 = 0;
    v30 = 0;
    v32 = 0;
    v31 = 0;
    v13 = 0;
    v27 = 0;
    v29 = 0;
    v28 = 0;
    v14 = (struct _WLIDSignedTokens *)malloc(0x10u);
    Auto<_WLIDSignedTokens *,LocalMIDLPointerFunctor<_WLIDSignedTokens *>,DummyContext>::Clear(&v33);
    v33 = v14;
    if ( v14 )
    {
      if ( LocalSignedUserToken >= 0 )
      {
        v15 = (unsigned int)(*((_DWORD *)v42 - 4) + 1);
        v12 = (unsigned __int16 *)malloc(2 * v15);
        Auto<_WLIDSignedTokens *,LocalMIDLPointerFunctor<_WLIDSignedTokens *>,DummyContext>::Clear(&v30);
        v30 = v12;
        if ( !v12 )
          goto LABEL_25;
        v16 = StringCchCopyW(v12, (unsigned int)v15, v42);
        v40 = v16;
        if ( v16 < 0 )
        {
          v17 = "hr = StringCchCopyW(pAutoUserToken, userTokenBufferSizeChars, (LPCWSTR)userToken)";
          v18 = 11010;
LABEL_19:
          Telemetry::IfFailExit(
            "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
            "HandleGetSignedTokens",
            v18,
            v16,
            v17);
LABEL_26:
          Auto<unsigned short *,LocalMIDLPointerFunctor<unsigned short *>,DummyContext>::~Auto<unsigned short *,LocalMIDLPointerFunctor<unsigned short *>,DummyContext>(&v27);
          Auto<unsigned short *,LocalMIDLPointerFunctor<unsigned short *>,DummyContext>::~Auto<unsigned short *,LocalMIDLPointerFunctor<unsigned short *>,DummyContext>(&v30);
          Auto<unsigned short *,LocalMIDLPointerFunctor<unsigned short *>,DummyContext>::~Auto<unsigned short *,LocalMIDLPointerFunctor<unsigned short *>,DummyContext>(&v33);
          goto LABEL_27;
        }
      }
      if ( v11 < 0 )
        goto LABEL_24;
      v19 = *((_DWORD *)v41 - 4) + 1;
      v13 = (unsigned __int16 *)malloc(2LL * v19);
      Auto<_WLIDSignedTokens *,LocalMIDLPointerFunctor<_WLIDSignedTokens *>,DummyContext>::Clear(&v27);
      v27 = v13;
      if ( v13 )
      {
        v16 = StringCchCopyW(v13, v19, v41);
        v40 = v16;
        if ( v16 < 0 )
        {
          v17 = "hr = StringCchCopyW(pAutoDeviceToken, deviceTokenBufferSizeChars, (LPCWSTR)deviceToken)";
          v18 = 11019;
          goto LABEL_19;
        }
LABEL_24:
        v33 = 0;
        v34 = 0;
        *a2 = v14;
        v27 = 0;
        v28 = 0;
        *((_QWORD *)v14 + 1) = v13;
        v30 = 0;
        v31 = 0;
        *(_QWORD *)*a2 = v12;
        goto LABEL_26;
      }
    }
LABEL_25:
    v40 = -2147024882;
    goto LABEL_26;
  }
  v40 = LocalSignedUserToken;
  Telemetry::IfFailExit(
    "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
    "HandleGetSignedTokens",
    0x2AF0u,
    LocalSignedUserToken,
    "hr = userTokenHr");
LABEL_27:
  v20 = v40;
  if ( v40 == -2147188724 || v40 == -2147186687 || v40 == -2147186548 )
  {
    LODWORD(v23) = v40;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
      0x2B1Bu,
      L"Error being collapsed to common error code. Original error: 0x%x.",
      v23);
    v20 = -2147186591;
    v40 = -2147186591;
  }
  ErrorVerifier::CheckAgainstList((const char *)v38[3], *v38[2], (unsigned __int64)v38[1], v38[0]);
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v39);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v41);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v42);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v37);
  CAutoImpersonateClient::~CAutoImpersonateClient((CAutoImpersonateClient *)&v25);
  CAutoRefPtr<CSingleIdentity>::Deinit(&v26);
  return v20;
}

```

## disassembly

```asm
0x1800a1b0c  mov     [rsp-8+arg_8], rbx
0x1800a1b11  push    rbp
0x1800a1b12  push    rsi
0x1800a1b13  push    rdi
0x1800a1b14  push    r12
0x1800a1b16  push    r13
0x1800a1b18  push    r14
0x1800a1b1a  push    r15
0x1800a1b1c  lea     rbp, [rsp-10h]
0x1800a1b21  sub     rsp, 110h
0x1800a1b28  mov     r12, rdx
0x1800a1b2b  mov     rbx, rcx
0x1800a1b2e  xor     r13d, r13d
0x1800a1b31  mov     [rbp+40h+arg_0], r13d
0x1800a1b35  mov     rax, [rcx]
0x1800a1b38  mov     rax, [rax+50h]
0x1800a1b3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1b41  mov     rsi, rax
0x1800a1b44  mov     r8, [rbx]
0x1800a1b47  mov     rcx, rbx
0x1800a1b4a  mov     rax, [r8+38h]
0x1800a1b4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1b53  mov     r15, rax
0x1800a1b56  mov     [rsp+140h+var_D8], r13
0x1800a1b5b  mov     [rsp+140h+var_E0], r13
0x1800a1b60  mov     [rbp+40h+var_88], r13
0x1800a1b64  lea     rcx, [rbp+40h+var_80]
0x1800a1b68  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800a1b6d  nop
0x1800a1b6e  lea     rcx, [rbp+40h+arg_18]
0x1800a1b72  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800a1b77  nop
0x1800a1b78  lea     rcx, [rbp+40h+arg_10]
0x1800a1b7c  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800a1b81  nop
0x1800a1b82  lea     rdi, aHandlegetsigne; "HandleGetSignedTokens"
0x1800a1b89  mov     [rbp+40h+var_58], rdi
0x1800a1b8d  lea     rax, [rbp+40h+arg_0]
0x1800a1b91  mov     [rbp+40h+var_50], rax
0x1800a1b95  mov     [rbp+40h+var_48], r13
0x1800a1b99  mov     [rbp+40h+var_40], r13
0x1800a1b9d  xor     r9d, r9d; unsigned int
0x1800a1ba0  mov     r8d, 2ACBh; char *
0x1800a1ba6  mov     rdx, rdi; char *
0x1800a1ba9  lea     rcx, aOnecoreuapDsEx_11; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800a1bb0  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x1800a1bb5  nop
0x1800a1bb6  lea     rax, qword_18014A0F0
0x1800a1bbd  mov     [rsp+140h+var_120], rax; int *
0x1800a1bc2  lea     r9d, [r13+0Bh]; unsigned __int64
0x1800a1bc6  lea     r8, [rbp+40h+arg_0]; int *
0x1800a1bca  mov     rdx, rdi; char *
0x1800a1bcd  lea     rcx, [rbp+40h+var_78]; this
0x1800a1bd1  call    ??0ErrorVerifier@@QEAA@PEBDPEAJ_KPEBJ@Z; ErrorVerifier::ErrorVerifier(char const *,long *,unsigned __int64,long const *)
0x1800a1bd6  nop
0x1800a1bd7  mov     rax, [rsi]
0x1800a1bda  xor     r8d, r8d
0x1800a1bdd  lea     rdx, [rsp+140h+var_E0]
0x1800a1be2  mov     rcx, rsi
0x1800a1be5  mov     rax, [rax+20h]
0x1800a1be9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1bee  mov     [rbp+40h+arg_0], eax
0x1800a1bf1  test    eax, eax
0x1800a1bf3  jns     short loc_1800A1C1E
0x1800a1bf5  lea     rcx, aHrPservicewrap_25; "hr = pServiceWrapper->Impersonate(&clie"...
0x1800a1bfc  mov     r8d, 2AD4h; unsigned int
0x1800a1c02  mov     r9d, eax; int
0x1800a1c05  mov     [rsp+140h+var_120], rcx; char *
0x1800a1c0a  mov     rdx, rdi; char *
0x1800a1c0d  lea     rcx, aOnecoreuapDsEx_11; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800a1c14  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x1800a1c19  jmp     loc_1800A1EBA
0x1800a1c1e  mov     rax, [rsi]
0x1800a1c21  lea     r8, [rbp+40h+var_88]
0x1800a1c25  lea     rdx, [rsp+140h+var_E0]
0x1800a1c2a  mov     rcx, rsi
0x1800a1c2d  mov     rax, [rax+28h]
0x1800a1c31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1c36  mov     [rbp+40h+arg_0], eax
0x1800a1c39  test    eax, eax
0x1800a1c3b  jns     short loc_1800A1C4C
0x1800a1c3d  lea     rcx, aHrPservicewrap_16; "hr = pServiceWrapper->GetLogonId(&clien"...
0x1800a1c44  mov     r8d, 2AD5h
0x1800a1c4a  jmp     short loc_1800A1C02
0x1800a1c4c  lea     r8, [rbp+40h+arg_18]
0x1800a1c50  lea     rdx, [rbp+40h+var_88]
0x1800a1c54  mov     rcx, rbx
0x1800a1c57  call    ?GetLocalSignedUserToken@@YAJPEAVIServiceExecutionContext@@PEAU_LUID@@AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; GetLocalSignedUserToken(IServiceExecutionContext *,_LUID *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x1800a1c5c  mov     edi, eax
0x1800a1c5e  mov     rcx, [rsi]
0x1800a1c61  mov     rbx, [rcx+80h]
0x1800a1c68  lea     rcx, [rsp+140h+var_D8]
0x1800a1c6d  call    ?Deinit@?$CAutoRefPtr@VCSingleIdentity@@@@IEAAXXZ; CAutoRefPtr<CSingleIdentity>::Deinit(void)
0x1800a1c72  lea     rax, [rsp+140h+var_D8]
0x1800a1c77  mov     [rsp+140h+var_108], rax
0x1800a1c7c  mov     [rsp+140h+var_110], r13
0x1800a1c81  mov     [rsp+140h+var_118], r13
0x1800a1c86  mov     [rsp+140h+var_120], r13
0x1800a1c8b  mov     r9d, 4000h
0x1800a1c91  mov     r8d, 10h
0x1800a1c97  lea     rdx, aAfda72bf340941; "{AFDA72BF-3409-413a-B54E-2AB8D66A7826}"
0x1800a1c9e  mov     rcx, rsi
0x1800a1ca1  mov     rax, rbx
0x1800a1ca4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1ca9  mov     r14d, eax
0x1800a1cac  test    eax, eax
0x1800a1cae  js      short loc_1800A1CF7
0x1800a1cb0  mov     rax, [r15]
0x1800a1cb3  mov     [rsp+140h+var_F8], r13
0x1800a1cb8  lea     rcx, [rbp+40h+arg_10]
0x1800a1cbc  mov     [rsp+140h+var_100], rcx
0x1800a1cc1  lea     rcx, [rbp+40h+var_80]
0x1800a1cc5  mov     [rsp+140h+var_108], rcx
0x1800a1cca  mov     [rsp+140h+var_110], r13
0x1800a1ccf  mov     [rsp+140h+var_118], r13
0x1800a1cd4  mov     [rsp+140h+var_120], r13
0x1800a1cd9  lea     r9, aDefault; "Default"
0x1800a1ce0  xor     r8d, r8d
0x1800a1ce3  mov     rdx, [rsp+140h+var_D8]
0x1800a1ce8  mov     rcx, r15
0x1800a1ceb  mov     rax, [rax+60h]
0x1800a1cef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1cf4  mov     r14d, eax
0x1800a1cf7  test    edi, edi
0x1800a1cf9  js      short loc_1800A1D00
0x1800a1cfb  test    r14d, r14d
0x1800a1cfe  jns     short loc_1800A1D54
0x1800a1d00  mov     dword ptr [rsp+140h+var_118], r14d
0x1800a1d05  mov     dword ptr [rsp+140h+var_120], edi
0x1800a1d09  lea     r9, aErrorGeneratin; "Error generating signed tokens: userTok"...
0x1800a1d10  mov     r8d, 2AECh; unsigned int
0x1800a1d16  lea     rdx, aOnecoreuapDsEx_11; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800a1d1d  mov     ecx, 2; unsigned __int8
0x1800a1d22  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800a1d27  test    edi, edi
0x1800a1d29  jns     short loc_1800A1D54
0x1800a1d2b  test    r14d, r14d
0x1800a1d2e  jns     short loc_1800A1D54
0x1800a1d30  mov     [rbp+40h+arg_0], edi
0x1800a1d33  lea     rax, aHrUsertokenhr; "hr = userTokenHr"
0x1800a1d3a  mov     [rsp+140h+var_120], rax
0x1800a1d3f  mov     r9d, edi
0x1800a1d42  mov     r8d, 2AF0h
0x1800a1d48  lea     rdx, aHandlegetsigne; "HandleGetSignedTokens"
0x1800a1d4f  jmp     loc_1800A1C0D
0x1800a1d54  mov     [rbp+40h+var_A0], r13
0x1800a1d58  mov     [rbp+40h+var_90], r13
0x1800a1d5c  mov     [rbp+40h+var_98], r13
0x1800a1d60  mov     rsi, r13
0x1800a1d63  mov     [rbp+40h+var_B8], r13
0x1800a1d67  mov     [rbp+40h+var_A8], r13
0x1800a1d6b  mov     [rbp+40h+var_B0], r13
0x1800a1d6f  mov     rbx, r13
0x1800a1d72  mov     [rsp+140h+var_D0], rbx
0x1800a1d77  mov     [rbp+40h+var_C0], r13
0x1800a1d7b  mov     [rsp+140h+var_C8], r13
0x1800a1d80  mov     ecx, 10h; Size
0x1800a1d85  call    cs:__imp_malloc
0x1800a1d8b  mov     r15, rax
0x1800a1d8e  lea     rcx, [rbp+40h+var_A0]
0x1800a1d92  call    ?Clear@?$Auto@PEAU_WLIDSignedTokens@@V?$LocalMIDLPointerFunctor@PEAU_WLIDSignedTokens@@@@VDummyContext@@@@QEAAXXZ; Auto<_WLIDSignedTokens *,LocalMIDLPointerFunctor<_WLIDSignedTokens *>,DummyContext>::Clear(void)
0x1800a1d97  mov     [rbp+40h+var_A0], r15
0x1800a1d9b  test    r15, r15
0x1800a1d9e  jz      loc_1800A1E97
0x1800a1da4  test    edi, edi
0x1800a1da6  js      short loc_1800A1E18
0x1800a1da8  mov     rcx, [rbp+40h+arg_18]
0x1800a1dac  mov     edx, [rcx-10h]
0x1800a1daf  inc     edx
0x1800a1db1  mov     edi, edx
0x1800a1db3  lea     rcx, [rdx+rdx]; Size
0x1800a1db7  call    cs:__imp_malloc
0x1800a1dbd  mov     rsi, rax
0x1800a1dc0  lea     rcx, [rbp+40h+var_B8]
0x1800a1dc4  call    ?Clear@?$Auto@PEAU_WLIDSignedTokens@@V?$LocalMIDLPointerFunctor@PEAU_WLIDSignedTokens@@@@VDummyContext@@@@QEAAXXZ; Auto<_WLIDSignedTokens *,LocalMIDLPointerFunctor<_WLIDSignedTokens *>,DummyContext>::Clear(void)
0x1800a1dc9  mov     [rbp+40h+var_B8], rsi
0x1800a1dcd  test    rsi, rsi
0x1800a1dd0  jz      loc_1800A1E97
0x1800a1dd6  mov     r8, [rbp+40h+arg_18]; unsigned __int16 *
0x1800a1dda  mov     edx, edi; unsigned __int64
0x1800a1ddc  mov     rcx, rsi; unsigned __int16 *
0x1800a1ddf  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800a1de4  mov     [rbp+40h+arg_0], eax
0x1800a1de7  test    eax, eax
0x1800a1de9  jns     short loc_1800A1E18
0x1800a1deb  lea     rcx, aHrStringcchcop_15; "hr = StringCchCopyW(pAutoUserToken, use"...
0x1800a1df2  mov     r8d, 2B02h; unsigned int
0x1800a1df8  mov     r9d, eax; int
0x1800a1dfb  mov     [rsp+140h+var_120], rcx; char *
0x1800a1e00  lea     rdx, aHandlegetsigne; "HandleGetSignedTokens"
0x1800a1e07  lea     rcx, aOnecoreuapDsEx_11; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800a1e0e  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x1800a1e13  jmp     loc_1800A1E9E
0x1800a1e18  test    r14d, r14d
0x1800a1e1b  js      short loc_1800A1E6C
0x1800a1e1d  mov     rax, [rbp+40h+arg_10]
0x1800a1e21  mov     ecx, [rax-10h]
0x1800a1e24  inc     ecx
0x1800a1e26  mov     edi, ecx
0x1800a1e28  add     rcx, rcx; Size
0x1800a1e2b  call    cs:__imp_malloc
0x1800a1e31  mov     rbx, rax
0x1800a1e34  lea     rcx, [rsp+140h+var_D0]
0x1800a1e39  call    ?Clear@?$Auto@PEAU_WLIDSignedTokens@@V?$LocalMIDLPointerFunctor@PEAU_WLIDSignedTokens@@@@VDummyContext@@@@QEAAXXZ; Auto<_WLIDSignedTokens *,LocalMIDLPointerFunctor<_WLIDSignedTokens *>,DummyContext>::Clear(void)
0x1800a1e3e  mov     [rsp+140h+var_D0], rbx
0x1800a1e43  test    rbx, rbx
0x1800a1e46  jz      short loc_1800A1E97
0x1800a1e48  mov     r8, [rbp+40h+arg_10]; unsigned __int16 *
0x1800a1e4c  mov     edx, edi; unsigned __int64
0x1800a1e4e  mov     rcx, rbx; unsigned __int16 *
0x1800a1e51  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800a1e56  mov     [rbp+40h+arg_0], eax
0x1800a1e59  test    eax, eax
0x1800a1e5b  jns     short loc_1800A1E6C
0x1800a1e5d  lea     rcx, aHrStringcchcop_4; "hr = StringCchCopyW(pAutoDeviceToken, d"...
0x1800a1e64  mov     r8d, 2B0Bh
0x1800a1e6a  jmp     short loc_1800A1DF8
0x1800a1e6c  mov     [rbp+40h+var_A0], r13
0x1800a1e70  mov     [rbp+40h+var_98], r13
0x1800a1e74  mov     [r12], r15
0x1800a1e78  mov     [rsp+140h+var_D0], r13
0x1800a1e7d  mov     [rsp+140h+var_C8], r13
0x1800a1e82  mov     [r15+8], rbx
0x1800a1e86  mov     [rbp+40h+var_B8], r13
0x1800a1e8a  mov     [rbp+40h+var_B0], r13
0x1800a1e8e  mov     rax, [r12]
0x1800a1e92  mov     [rax], rsi
0x1800a1e95  jmp     short loc_1800A1E9E
0x1800a1e97  mov     [rbp+40h+arg_0], 8007000Eh
0x1800a1e9e  lea     rcx, [rsp+140h+var_D0]; void *
0x1800a1ea3  call    ??1?$Auto@PEAGV?$LocalMIDLPointerFunctor@PEAG@@VDummyContext@@@@QEAA@XZ; Auto<ushort *,LocalMIDLPointerFunctor<ushort *>,DummyContext>::~Auto<ushort *,LocalMIDLPointerFunctor<ushort *>,DummyContext>(void)
0x1800a1ea8  lea     rcx, [rbp+40h+var_B8]; void *
0x1800a1eac  call    ??1?$Auto@PEAGV?$LocalMIDLPointerFunctor@PEAG@@VDummyContext@@@@QEAA@XZ; Auto<ushort *,LocalMIDLPointerFunctor<ushort *>,DummyContext>::~Auto<ushort *,LocalMIDLPointerFunctor<ushort *>,DummyContext>(void)
0x1800a1eb1  lea     rcx, [rbp+40h+var_A0]; void *
0x1800a1eb5  call    ??1?$Auto@PEAGV?$LocalMIDLPointerFunctor@PEAG@@VDummyContext@@@@QEAA@XZ; Auto<ushort *,LocalMIDLPointerFunctor<ushort *>,DummyContext>::~Auto<ushort *,LocalMIDLPointerFunctor<ushort *>,DummyContext>(void)
0x1800a1eba  mov     ebx, [rbp+40h+arg_0]
0x1800a1ebd  cmp     ebx, 8004800Ch
0x1800a1ec3  jz      short loc_1800A1ED5
0x1800a1ec5  cmp     ebx, 80048801h
0x1800a1ecb  jz      short loc_1800A1ED5
0x1800a1ecd  cmp     ebx, 8004888Ch
0x1800a1ed3  jnz     short loc_1800A1EFF
0x1800a1ed5  mov     dword ptr [rsp+140h+var_120], ebx
0x1800a1ed9  lea     r9, aErrorBeingColl; "Error being collapsed to common error c"...
0x1800a1ee0  mov     r8d, 2B1Bh; unsigned int
0x1800a1ee6  lea     rdx, aOnecoreuapDsEx_11; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800a1eed  mov     ecx, 2; unsigned __int8
0x1800a1ef2  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800a1ef7  mov     ebx, 80048861h
0x1800a1efc  mov     [rbp+40h+arg_0], ebx
0x1800a1eff  mov     r9, [rbp+40h+var_78]; int *
0x1800a1f03  mov     r8, [rbp+40h+var_70]; unsigned __int64
0x1800a1f07  mov     rdx, [rbp+40h+var_68]
0x1800a1f0b  mov     edx, [rdx]; int
0x1800a1f0d  mov     rcx, [rbp+40h+var_60]; char *
0x1800a1f11  call    ?CheckAgainstList@ErrorVerifier@@SAXPEBDJ_KPEBJ@Z; ErrorVerifier::CheckAgainstList(char const *,long,unsigned __int64,long const *)
0x1800a1f16  nop
0x1800a1f17  lea     rcx, [rbp+40h+var_58]
0x1800a1f1b  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x1800a1f20  nop
0x1800a1f21  lea     rcx, [rbp+40h+arg_10]
0x1800a1f25  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800a1f2a  nop
0x1800a1f2b  lea     rcx, [rbp+40h+arg_18]
0x1800a1f2f  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800a1f34  nop
0x1800a1f35  lea     rcx, [rbp+40h+var_80]
0x1800a1f39  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800a1f3e  nop
0x1800a1f3f  lea     rcx, [rsp+140h+var_E0]; this
0x1800a1f44  call    ??1CAutoImpersonateClient@@QEAA@XZ; CAutoImpersonateClient::~CAutoImpersonateClient(void)
0x1800a1f49  nop
0x1800a1f4a  lea     rcx, [rsp+140h+var_D8]
0x1800a1f4f  call    ?Deinit@?$CAutoRefPtr@VCSingleIdentity@@@@IEAAXXZ; CAutoRefPtr<CSingleIdentity>::Deinit(void)
0x1800a1f54  mov     eax, ebx
0x1800a1f56  mov     rbx, [rsp+140h+arg_8]
0x1800a1f5e  add     rsp, 110h
0x1800a1f65  pop     r15
0x1800a1f67  pop     r14
0x1800a1f69  pop     r13
0x1800a1f6b  pop     r12
0x1800a1f6d  pop     rdi
0x1800a1f6e  pop     rsi
0x1800a1f6f  pop     rbp
0x1800a1f70  retn
```
