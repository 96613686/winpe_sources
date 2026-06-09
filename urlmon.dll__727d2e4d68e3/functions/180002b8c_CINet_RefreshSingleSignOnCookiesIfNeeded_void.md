# CINet::RefreshSingleSignOnCookiesIfNeeded(void)

- ea: `0x180002b8c`
- end: `0x180002fc5`
- name: `?RefreshSingleSignOnCookiesIfNeeded@CINet@@AEAAXXZ`
- size: `1081`
- prototype: `void __fastcall(CINet *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800053e0`

## callees

- `0x180002b8c`
- `0x180002fcc`
- `0x180003190`
- `0x180003d8c`
- `0x180003e28`
- `0x180004040`
- `0x1800041d4`
- `0x18000523c`
- `0x180028410`
- `0x1800de218`
- `0x18012250c`
- `0x1801285fe`
- `0x180128660`
- `0x180129010`

## import_xrefs

- `msvcrt!wcsstr` at `0x180002cbf`
- `msvcrt!wcsstr` at `0x180002cbf`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x180002eb0`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x180002eb0`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180002bbb`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180002bd0`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180002d75`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180002e87`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180002bbb`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180002bd0`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180002d75`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180002e87`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180002c37`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180002c78`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180002c37`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180002c78`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180002d19`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180002d19`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002c8c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002e02`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002c8c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002e02`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180002d31`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180002d31`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180002db2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180002db2`
- `api-ms-win-ole32-ie-l1-1-0!CoInitialize` at `0x180002bde`
- `api-ms-win-ole32-ie-l1-1-0!CoInitialize` at `0x180002bde`

## pseudocode

```c
void __fastcall CINet::RefreshSingleSignOnCookiesIfNeeded(CINet *this)
{
  CINet *v2; // rcx
  ProofOfPossessionTokenProvider *v3; // r14
  const wchar_t *SingleSignOnLoginUrl; // rax
  CINet *v5; // rcx
  void *v6; // r15
  const unsigned __int16 *AadSingleSignOnLoginUrls; // rax
  const unsigned __int16 *v8; // r8
  char *AadLoginUrlMatch; // rbx
  __int64 v10; // rcx
  char v11; // r12
  char v12; // si
  wchar_t *v13; // r13
  HRESULT v14; // r12d
  unsigned __int16 *v15; // rax
  unsigned __int16 *v16; // r13
  __int64 v17; // rcx
  char v18; // [rsp+30h] [rbp-A9h]
  HRESULT v19; // [rsp+34h] [rbp-A5h] BYREF
  unsigned int v20; // [rsp+38h] [rbp-A1h] BYREF
  LPVOID ppv; // [rsp+40h] [rbp-99h] BYREF
  __int64 v22; // [rsp+48h] [rbp-91h] BYREF
  struct IEUserBroker *v23; // [rsp+50h] [rbp-89h] BYREF
  _QWORD v24[3]; // [rsp+58h] [rbp-81h] BYREF
  char v25; // [rsp+70h] [rbp-69h]
  GUID pguid; // [rsp+78h] [rbp-61h] BYREF
  OLECHAR sz; // [rsp+90h] [rbp-49h] BYREF
  unsigned __int16 v28[39]; // [rsp+92h] [rbp-47h] BYREF

  if ( !(unsigned __int8)IEConfiguration_GetBool(268435481) )
    IEConfiguration_GetBool(268435482);
  v19 = CoInitialize(0);
  if ( v19 >= 0 )
  {
    v3 = (ProofOfPossessionTokenProvider *)*((_QWORD *)this + 40);
    v20 = 0;
    if ( !v3 )
      v3 = (ProofOfPossessionTokenProvider *)*((_QWORD *)this + 20);
    SingleSignOnLoginUrl = CINet::GetSingleSignOnLoginUrl(v2);
    v6 = (void *)SingleSignOnLoginUrl;
    if ( SingleSignOnLoginUrl && wcsstr((const wchar_t *)v3, SingleSignOnLoginUrl) )
    {
      v11 = 1;
      AadLoginUrlMatch = 0;
      v18 = 1;
      v12 = 0;
    }
    else
    {
      AadSingleSignOnLoginUrls = CINet::GetAadSingleSignOnLoginUrls(v5);
      AadLoginUrlMatch = ProofOfPossessionTokenProvider::GetAadLoginUrlMatch(v3, AadSingleSignOnLoginUrls, v8);
      if ( !AadLoginUrlMatch )
      {
        CoUninitialize();
        return;
      }
      v11 = 0;
      v12 = 1;
      v18 = 0;
      if ( !*((_QWORD *)this + 44) )
        goto LABEL_13;
    }
    v13 = 0;
    v25 = v12;
    v24[0] = 0;
    v24[1] = &v20;
    v24[2] = &v19;
    memset_0(&sz, 0, 0x4Eu);
    pguid = 0;
    CoCreateGuid(&pguid);
    if ( StringFromGUID2(&pguid, &sz, 39) > 0 )
    {
      v28[36] = 0;
      v24[0] = OLESTRDuplicate(v28);
      v13 = (wchar_t *)v24[0];
      if ( v24[0] )
      {
        if ( v12 )
          BrowserTelemetry::SingleSignOnGetCookiesAadStarted<unsigned short const * &>(v24);
        else
          BrowserTelemetry::SingleSignOnGetCookiesMsaStarted<unsigned short const * &>(v24);
      }
    }
    if ( !(unsigned __int8)IEConfiguration_GetBool(536870916) || (unsigned __int8)IEConfiguration_GetBool(536870913) )
    {
      *(_QWORD *)&pguid.Data1 = 0;
      ppv = 0;
      v14 = CoCreateInstance(
              &GUID_a9927f85_a304_4390_8b23_a75f1c668600,
              0,
              1u,
              &GUID_cdaece56_4edf_43df_b113_88e4556fa1bb,
              &ppv);
      if ( v14 >= 0 )
      {
        v15 = AddCorrelationIdParameter((const unsigned __int16 *)v3, v13);
        v16 = v15;
        if ( v15 )
          v3 = (ProofOfPossessionTokenProvider *)v15;
        v14 = (*(__int64 (__fastcall **)(LPVOID, ProofOfPossessionTokenProvider *, unsigned int *, GUID *))(*(_QWORD *)ppv + 24LL))(
                ppv,
                v3,
                &v20,
                &pguid);
        if ( v16 )
          CoTaskMemFree(v16);
      }
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      v19 = v14;
      if ( v14 < 0 || !v20 )
        goto LABEL_12;
      if ( v18 )
      {
        v10 = 0;
      }
      else
      {
        v10 = *((_QWORD *)this + 44);
        v6 = AadLoginUrlMatch;
      }
      ProofOfPossessionTokenProvider::SetCookiesAndFreeTokens<ProofOfPossessionCookieInfo>(
        v10,
        v6,
        v20,
        *(_QWORD *)&pguid.Data1);
    }
    else
    {
      *(_QWORD *)&pguid.Data1 = 0;
      ppv = 0;
      v23 = 0;
      v19 = CoCreateUserBroker(&v23);
      if ( v19 < 0 )
        goto LABEL_12;
      v22 = 0;
      v19 = (*(__int64 (__fastcall **)(struct IEUserBroker *, GUID *, GUID *, __int64 *))(*(_QWORD *)v23 + 48LL))(
              v23,
              &CLSID_CShdocvwBroker,
              &IID_IUnknown,
              &v22);
      if ( v19 >= 0 )
      {
        v19 = (**(__int64 (__fastcall ***)(__int64, GUID *, LPVOID *))v22)(
                v22,
                &GUID_cd45afe8_9a64_402a_8cfd_22bb4ebd8b42,
                &ppv);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
      }
      (*(void (__fastcall **)(struct IEUserBroker *))(*(_QWORD *)v23 + 16LL))(v23);
      if ( v19 < 0 )
        goto LABEL_12;
      v19 = (*(__int64 (__fastcall **)(LPVOID, ProofOfPossessionTokenProvider *, wchar_t *, unsigned int *, GUID *))(*(_QWORD *)ppv + 1152LL))(
              ppv,
              v3,
              v13,
              &v20,
              &pguid);
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      if ( v19 < 0 || !v20 )
        goto LABEL_12;
      if ( v11 )
      {
        v17 = 0;
      }
      else
      {
        v17 = *((_QWORD *)this + 44);
        v6 = AadLoginUrlMatch;
      }
      ProofOfPossessionTokenProvider::SetCookiesAndFreeTokens<_IEProofOfPossessionToken>(
        v17,
        v6,
        v20,
        *(_QWORD *)&pguid.Data1);
    }
    *((_BYTE *)this + 994) &= ~0x40u;
    *((_BYTE *)this + 994) |= v12 << 6;
LABEL_12:
    SingleSignonTelemetryHelper::~SingleSignonTelemetryHelper((SingleSignonTelemetryHelper *)v24);
LABEL_13:
    CoUninitialize();
    if ( AadLoginUrlMatch )
      CoTaskMemFree(AadLoginUrlMatch);
  }
}

```

## disassembly

```asm
0x180002b8c  push    rbp
0x180002b8e  push    rbx
0x180002b8f  push    rsi
0x180002b90  push    rdi
0x180002b91  push    r12
0x180002b93  push    r13
0x180002b95  push    r14
0x180002b97  push    r15
0x180002b99  lea     rbp, [rsp-1Fh]
0x180002b9e  sub     rsp, 0F8h
0x180002ba5  mov     rax, cs:__security_cookie
0x180002bac  xor     rax, rsp
0x180002baf  mov     [rbp+57h+var_50], rax
0x180002bb3  mov     rdi, rcx
0x180002bb6  mov     ecx, 10000019h
0x180002bbb  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180002bc2  nop     dword ptr [rax+rax+00h]
0x180002bc7  test    al, al
0x180002bc9  jnz     short loc_180002BDC
0x180002bcb  mov     ecx, 1000001Ah
0x180002bd0  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180002bd7  nop     dword ptr [rax+rax+00h]
0x180002bdc  xor     ecx, ecx; pvReserved
0x180002bde  call    cs:__imp_CoInitialize
0x180002be5  nop     dword ptr [rax+rax+00h]
0x180002bea  mov     [rsp+130h+var_FC], eax
0x180002bee  test    eax, eax
0x180002bf0  js      loc_180002C98
0x180002bf6  mov     r14, [rdi+140h]
0x180002bfd  mov     [rsp+130h+var_F8], 0
0x180002c05  test    r14, r14
0x180002c08  jz      short loc_180002C45
0x180002c0a  call    ?GetSingleSignOnLoginUrl@CINet@@IEAAPEBGXZ; CINet::GetSingleSignOnLoginUrl(void)
0x180002c0f  mov     r15, rax
0x180002c12  test    rax, rax
0x180002c15  jnz     loc_180002CB9
0x180002c1b  call    ?GetAadSingleSignOnLoginUrls@CINet@@IEAAPEBGXZ; CINet::GetAadSingleSignOnLoginUrls(void)
0x180002c20  mov     rdx, rax; unsigned __int16 *
0x180002c23  mov     rcx, r14; this
0x180002c26  call    ?GetAadLoginUrlMatch@ProofOfPossessionTokenProvider@@YAPEAGPEBG0@Z; ProofOfPossessionTokenProvider::GetAadLoginUrlMatch(ushort const *,ushort const *)
0x180002c2b  mov     rbx, rax
0x180002c2e  test    rax, rax
0x180002c31  jnz     loc_180002E64
0x180002c37  call    cs:__imp_CoUninitialize
0x180002c3e  nop     dword ptr [rax+rax+00h]
0x180002c43  jmp     short loc_180002C98
0x180002c45  mov     r14, [rdi+0A0h]
0x180002c4c  jmp     short loc_180002C0A
0x180002c4e  xor     ecx, ecx
0x180002c50  mov     r9, qword ptr [rbp+57h+pguid.Data1]
0x180002c54  mov     rdx, r15
0x180002c57  call    ??$SetCookiesAndFreeTokens@UProofOfPossessionCookieInfo@@@ProofOfPossessionTokenProvider@@YAXPEAXPEBGKPEAUProofOfPossessionCookieInfo@@@Z; ProofOfPossessionTokenProvider::SetCookiesAndFreeTokens<ProofOfPossessionCookieInfo>(void *,ushort const *,ulong,ProofOfPossessionCookieInfo *)
0x180002c5c  and     byte ptr [rdi+3E2h], 0BFh
0x180002c63  shl     sil, 6
0x180002c67  or      [rdi+3E2h], sil
0x180002c6e  lea     rcx, [rsp+130h+var_D8]; this
0x180002c73  call    ??1SingleSignonTelemetryHelper@@QEAA@XZ; SingleSignonTelemetryHelper::~SingleSignonTelemetryHelper(void)
0x180002c78  call    cs:__imp_CoUninitialize
0x180002c7f  nop     dword ptr [rax+rax+00h]
0x180002c84  test    rbx, rbx
0x180002c87  jz      short loc_180002C98
0x180002c89  mov     rcx, rbx; pv
0x180002c8c  call    cs:__imp_CoTaskMemFree
0x180002c93  nop     dword ptr [rax+rax+00h]
0x180002c98  mov     rcx, [rbp+57h+var_50]
0x180002c9c  xor     rcx, rsp; StackCookie
0x180002c9f  call    __security_check_cookie
0x180002ca4  add     rsp, 0F8h
0x180002cab  pop     r15
0x180002cad  pop     r14
0x180002caf  pop     r13
0x180002cb1  pop     r12
0x180002cb3  pop     rdi
0x180002cb4  pop     rsi
0x180002cb5  pop     rbx
0x180002cb6  pop     rbp
0x180002cb7  retn
0x180002cb9  mov     rdx, rax; SubStr
0x180002cbc  mov     rcx, r14; Str
0x180002cbf  call    cs:__imp_wcsstr
0x180002cc6  nop     dword ptr [rax+rax+00h]
0x180002ccb  test    rax, rax
0x180002cce  jz      loc_180002C1B
0x180002cd4  mov     r12b, 1
0x180002cd7  xor     ebx, ebx
0x180002cd9  mov     [rsp+130h+var_100], r12b
0x180002cde  xor     sil, sil
0x180002ce1  xor     r13d, r13d
0x180002ce4  mov     [rbp+57h+var_C0], sil
0x180002ce8  lea     rax, [rsp+130h+var_F8]
0x180002ced  mov     [rsp+130h+var_D8], r13
0x180002cf2  mov     [rbp+57h+var_D0], rax
0x180002cf6  lea     rcx, [rbp+57h+sz]; void *
0x180002cfa  lea     rax, [rsp+130h+var_FC]
0x180002cff  xor     edx, edx; Val
0x180002d01  lea     r8d, [r13+4Eh]; Size
0x180002d05  mov     [rbp+57h+var_C8], rax
0x180002d09  call    memset_0
0x180002d0e  xorps   xmm0, xmm0
0x180002d11  lea     rcx, [rbp+57h+pguid]; pguid
0x180002d15  movups  xmmword ptr [rbp+57h+pguid.Data1], xmm0
0x180002d19  call    cs:__imp_CoCreateGuid
0x180002d20  nop     dword ptr [rax+rax+00h]
0x180002d25  lea     r8d, [r13+27h]; cchMax
0x180002d29  lea     rdx, [rbp+57h+sz]; lpsz
0x180002d2d  lea     rcx, [rbp+57h+pguid]; rguid
0x180002d31  call    cs:__imp_StringFromGUID2
0x180002d38  nop     dword ptr [rax+rax+00h]
0x180002d3d  test    eax, eax
0x180002d3f  jle     short loc_180002D70
0x180002d41  xor     eax, eax
0x180002d43  lea     rcx, [rbp+57h+var_9E]; unsigned __int16 *
0x180002d47  mov     [rbp+57h+var_56], ax
0x180002d4b  call    ?OLESTRDuplicate@@YAPEAGPEBG@Z; OLESTRDuplicate(ushort const *)
0x180002d50  mov     [rsp+130h+var_D8], rax
0x180002d55  mov     r13, rax
0x180002d58  test    rax, rax
0x180002d5b  jz      short loc_180002D70
0x180002d5d  lea     rcx, [rsp+130h+var_D8]
0x180002d62  test    sil, sil
0x180002d65  jz      loc_180002E5A
0x180002d6b  call    ??$SingleSignOnGetCookiesAadStarted@AEAPEBG@BrowserTelemetry@@SAXAEAPEBG@Z; BrowserTelemetry::SingleSignOnGetCookiesAadStarted<ushort const * &>(ushort const * &)
0x180002d70  mov     ecx, 20000004h
0x180002d75  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180002d7c  nop     dword ptr [rax+rax+00h]
0x180002d81  xor     ecx, ecx
0x180002d83  test    al, al
0x180002d85  jnz     loc_180002E82
0x180002d8b  xor     edx, edx; pUnkOuter
0x180002d8d  mov     qword ptr [rbp+57h+pguid.Data1], rcx
0x180002d91  mov     [rsp+130h+var_F0], rcx
0x180002d96  lea     rax, [rsp+130h+var_F0]
0x180002d9b  lea     r9, _GUID_cdaece56_4edf_43df_b113_88e4556fa1bb; riid
0x180002da2  mov     [rsp+130h+ppv], rax; ppv
0x180002da7  lea     rcx, _GUID_a9927f85_a304_4390_8b23_a75f1c668600; rclsid
0x180002dae  lea     r8d, [rdx+1]; dwClsContext
0x180002db2  call    cs:__imp_CoCreateInstance
0x180002db9  nop     dword ptr [rax+rax+00h]
0x180002dbe  mov     r12d, eax
0x180002dc1  test    eax, eax
0x180002dc3  js      short loc_180002E0E
0x180002dc5  mov     rdx, r13; wchar_t *
0x180002dc8  mov     rcx, r14; Source
0x180002dcb  call    ?AddCorrelationIdParameter@@YAPEAGPEBG0@Z; AddCorrelationIdParameter(ushort const *,ushort const *)
0x180002dd0  mov     rcx, [rsp+130h+var_F0]
0x180002dd5  lea     r9, [rbp+57h+pguid]
0x180002dd9  mov     r13, rax
0x180002ddc  lea     r8, [rsp+130h+var_F8]
0x180002de1  test    r13, r13
0x180002de4  mov     rdx, [rcx]
0x180002de7  cmovnz  r14, r13
0x180002deb  mov     rax, [rdx+18h]
0x180002def  mov     rdx, r14
0x180002df2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002df7  mov     r12d, eax
0x180002dfa  test    r13, r13
0x180002dfd  jz      short loc_180002E0E
0x180002dff  mov     rcx, r13; pv
0x180002e02  call    cs:__imp_CoTaskMemFree
0x180002e09  nop     dword ptr [rax+rax+00h]
0x180002e0e  mov     rcx, [rsp+130h+var_F0]
0x180002e13  test    rcx, rcx
0x180002e16  jz      short loc_180002E24
0x180002e18  mov     rax, [rcx]
0x180002e1b  mov     rax, [rax+10h]
0x180002e1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e24  mov     [rsp+130h+var_FC], r12d
0x180002e29  test    r12d, r12d
0x180002e2c  js      loc_180002C6E
0x180002e32  mov     r8d, [rsp+130h+var_F8]
0x180002e37  test    r8d, r8d
0x180002e3a  jz      loc_180002C6E
0x180002e40  cmp     [rsp+130h+var_100], 0
0x180002e45  jnz     loc_180002C4E
0x180002e4b  mov     rcx, [rdi+160h]
0x180002e52  mov     r15, rbx
0x180002e55  jmp     loc_180002C50
0x180002e5a  call    ??$SingleSignOnGetCookiesMsaStarted@AEAPEBG@BrowserTelemetry@@SAXAEAPEBG@Z; BrowserTelemetry::SingleSignOnGetCookiesMsaStarted<ushort const * &>(ushort const * &)
0x180002e5f  jmp     loc_180002D70
0x180002e64  xor     r12b, r12b
0x180002e67  mov     sil, 1
0x180002e6a  cmp     qword ptr [rdi+160h], 0
0x180002e72  mov     [rsp+130h+var_100], r12b
0x180002e77  jz      loc_180002C78
0x180002e7d  jmp     loc_180002CE1
0x180002e82  mov     ecx, 20000001h
0x180002e87  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180002e8e  nop     dword ptr [rax+rax+00h]
0x180002e93  xor     ecx, ecx
0x180002e95  test    al, al
0x180002e97  jnz     loc_180002D8B
0x180002e9d  mov     qword ptr [rbp+57h+pguid.Data1], rcx
0x180002ea1  mov     [rsp+130h+var_F0], rcx
0x180002ea6  mov     [rsp+130h+var_E0], rcx
0x180002eab  lea     rcx, [rsp+130h+var_E0]
0x180002eb0  call    cs:__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z; CoCreateUserBroker(IEUserBroker * *)
0x180002eb7  nop     dword ptr [rax+rax+00h]
0x180002ebc  mov     [rsp+130h+var_FC], eax
0x180002ec0  test    eax, eax
0x180002ec2  js      loc_180002C6E
0x180002ec8  mov     rcx, [rsp+130h+var_E0]
0x180002ecd  lea     r9, [rsp+130h+var_E8]
0x180002ed2  mov     [rsp+130h+var_E8], 0
0x180002edb  lea     r8, IID_IUnknown
0x180002ee2  lea     rdx, CLSID_CShdocvwBroker
0x180002ee9  mov     rax, [rcx]
0x180002eec  mov     rax, [rax+30h]
0x180002ef0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ef5  mov     [rsp+130h+var_FC], eax
0x180002ef9  test    eax, eax
0x180002efb  js      short loc_180002F2E
0x180002efd  mov     rcx, [rsp+130h+var_E8]
0x180002f02  lea     r8, [rsp+130h+var_F0]
0x180002f07  lea     rdx, _GUID_cd45afe8_9a64_402a_8cfd_22bb4ebd8b42
0x180002f0e  mov     rax, [rcx]
0x180002f11  mov     rax, [rax]
0x180002f14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f19  mov     rcx, [rsp+130h+var_E8]
0x180002f1e  mov     [rsp+130h+var_FC], eax
0x180002f22  mov     rax, [rcx]
0x180002f25  mov     rax, [rax+10h]
0x180002f29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f2e  mov     rcx, [rsp+130h+var_E0]
0x180002f33  mov     rax, [rcx]
0x180002f36  mov     rax, [rax+10h]
0x180002f3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f3f  mov     eax, [rsp+130h+var_FC]
0x180002f43  test    eax, eax
0x180002f45  js      loc_180002C6E
0x180002f4b  mov     rcx, [rsp+130h+var_F0]
0x180002f50  lea     rdx, [rbp+57h+pguid]
0x180002f54  mov     [rsp+130h+ppv], rdx
0x180002f59  lea     r9, [rsp+130h+var_F8]
0x180002f5e  mov     r8, r13
0x180002f61  mov     rdx, r14
0x180002f64  mov     rax, [rcx]
0x180002f67  mov     rax, [rax+480h]
0x180002f6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f73  mov     rcx, [rsp+130h+var_F0]
0x180002f78  mov     [rsp+130h+var_FC], eax
0x180002f7c  mov     rax, [rcx]
0x180002f7f  mov     rax, [rax+10h]
0x180002f83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f88  cmp     [rsp+130h+var_FC], 0
0x180002f8d  jl      loc_180002C6E
0x180002f93  mov     r8d, [rsp+130h+var_F8]
0x180002f98  test    r8d, r8d
0x180002f9b  jz      loc_180002C6E
0x180002fa1  test    r12b, r12b
0x180002fa4  jz      short loc_180002FAA
0x180002fa6  xor     ecx, ecx
0x180002fa8  jmp     short loc_180002FB4
0x180002faa  mov     rcx, [rdi+160h]
0x180002fb1  mov     r15, rbx
0x180002fb4  mov     r9, qword ptr [rbp+57h+pguid.Data1]
0x180002fb8  mov     rdx, r15
0x180002fbb  call    ??$SetCookiesAndFreeTokens@U_IEProofOfPossessionToken@@@ProofOfPossessionTokenProvider@@YAXPEAXPEBGKPEAU_IEProofOfPossessionToken@@@Z; ProofOfPossessionTokenProvider::SetCookiesAndFreeTokens<_IEProofOfPossessionToken>(void *,ushort const *,ulong,_IEProofOfPossessionToken *)
0x180002fc0  jmp     loc_180002C5C
```
