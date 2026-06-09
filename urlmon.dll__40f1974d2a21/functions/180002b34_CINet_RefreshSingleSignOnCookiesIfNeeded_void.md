# CINet::RefreshSingleSignOnCookiesIfNeeded(void)

- ea: `0x180002b34`
- end: `0x180002f18`
- name: `?RefreshSingleSignOnCookiesIfNeeded@CINet@@AEAAXXZ`
- size: `996`
- prototype: `void __fastcall(CINet *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18003cb70`

## callees

- `0x180002b34`
- `0x180002f20`
- `0x1800030b8`
- `0x180003b8c`
- `0x180003c28`
- `0x180003e0c`
- `0x180003f6c`
- `0x180004df0`
- `0x1800214d0`
- `0x1800d511c`
- `0x18011606c`
- `0x18011ba3e`
- `0x18011baa0`
- `0x18011c010`

## import_xrefs

- `msvcrt!wcsstr` at `0x180002c42`
- `msvcrt!wcsstr` at `0x180002c42`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x180002e09`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x180002e09`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180002b63`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180002b72`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180002ce6`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180002de6`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180002b63`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180002b72`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180002ce6`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180002de6`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180002bcd`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180002c08`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180002bcd`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180002c08`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180002c96`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180002c96`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002c16`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002d67`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002c16`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002d67`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180002ca8`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180002ca8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180002d1d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180002d1d`
- `api-ms-win-ole32-ie-l1-1-0!CoInitialize` at `0x180002b7a`
- `api-ms-win-ole32-ie-l1-1-0!CoInitialize` at `0x180002b7a`

## pseudocode

```c
void __fastcall CINet::RefreshSingleSignOnCookiesIfNeeded(CINet *this)
{
  CINet *v2; // rcx
  ProofOfPossessionTokenProvider *v3; // r14
  const wchar_t *SingleSignOnLoginUrl; // rax
  CINet *v5; // rcx
  const WCHAR *v6; // r15
  const unsigned __int16 *AadSingleSignOnLoginUrls; // rax
  const unsigned __int16 *v8; // r8
  char *AadLoginUrlMatch; // rbx
  void *v10; // rcx
  char v11; // r12
  char v12; // si
  wchar_t *v13; // r13
  HRESULT v14; // r12d
  unsigned __int16 *v15; // rax
  unsigned __int16 *v16; // r13
  void *v17; // rcx
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
    v6 = SingleSignOnLoginUrl;
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
          BrowserTelemetry::SingleSignOnGetCookiesAadStarted<unsigned short const * &>((__int64)v24);
        else
          BrowserTelemetry::SingleSignOnGetCookiesMsaStarted<unsigned short const * &>((__int64)v24);
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
        v10 = (void *)*((_QWORD *)this + 44);
        v6 = (const WCHAR *)AadLoginUrlMatch;
      }
      ProofOfPossessionTokenProvider::SetCookiesAndFreeTokens<ProofOfPossessionCookieInfo>(
        v10,
        v6,
        v20,
        *(unsigned int **)&pguid.Data1);
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
        v17 = (void *)*((_QWORD *)this + 44);
        v6 = (const WCHAR *)AadLoginUrlMatch;
      }
      ProofOfPossessionTokenProvider::SetCookiesAndFreeTokens<_IEProofOfPossessionToken>(
        v17,
        v6,
        v20,
        *(unsigned int **)&pguid.Data1);
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
0x180002b34  push    rbp
0x180002b36  push    rbx
0x180002b37  push    rsi
0x180002b38  push    rdi
0x180002b39  push    r12
0x180002b3b  push    r13
0x180002b3d  push    r14
0x180002b3f  push    r15
0x180002b41  lea     rbp, [rsp-1Fh]
0x180002b46  sub     rsp, 0F8h
0x180002b4d  mov     rax, cs:__security_cookie
0x180002b54  xor     rax, rsp
0x180002b57  mov     [rbp+57h+var_50], rax
0x180002b5b  mov     rdi, rcx
0x180002b5e  mov     ecx, 10000019h
0x180002b63  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180002b69  test    al, al
0x180002b6b  jnz     short loc_180002B78
0x180002b6d  mov     ecx, 1000001Ah
0x180002b72  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180002b78  xor     ecx, ecx; pvReserved
0x180002b7a  call    cs:__imp_CoInitialize
0x180002b80  mov     [rsp+130h+var_FC], eax
0x180002b84  test    eax, eax
0x180002b86  js      loc_180002C1C
0x180002b8c  mov     r14, [rdi+140h]
0x180002b93  mov     [rsp+130h+var_F8], 0
0x180002b9b  test    r14, r14
0x180002b9e  jz      short loc_180002BD5
0x180002ba0  call    ?GetSingleSignOnLoginUrl@CINet@@IEAAPEBGXZ; CINet::GetSingleSignOnLoginUrl(void)
0x180002ba5  mov     r15, rax
0x180002ba8  test    rax, rax
0x180002bab  jnz     loc_180002C3C
0x180002bb1  call    ?GetAadSingleSignOnLoginUrls@CINet@@IEAAPEBGXZ; CINet::GetAadSingleSignOnLoginUrls(void)
0x180002bb6  mov     rdx, rax; unsigned __int16 *
0x180002bb9  mov     rcx, r14; this
0x180002bbc  call    ?GetAadLoginUrlMatch@ProofOfPossessionTokenProvider@@YAPEAGPEBG0@Z; ProofOfPossessionTokenProvider::GetAadLoginUrlMatch(ushort const *,ushort const *)
0x180002bc1  mov     rbx, rax
0x180002bc4  test    rax, rax
0x180002bc7  jnz     loc_180002DC3
0x180002bcd  call    cs:__imp_CoUninitialize
0x180002bd3  jmp     short loc_180002C1C
0x180002bd5  mov     r14, [rdi+0A0h]
0x180002bdc  jmp     short loc_180002BA0
0x180002bde  xor     ecx, ecx
0x180002be0  mov     r9, qword ptr [rbp+57h+pguid.Data1]
0x180002be4  mov     rdx, r15
0x180002be7  call    ??$SetCookiesAndFreeTokens@UProofOfPossessionCookieInfo@@@ProofOfPossessionTokenProvider@@YAXPEAXPEBGKPEAUProofOfPossessionCookieInfo@@@Z; ProofOfPossessionTokenProvider::SetCookiesAndFreeTokens<ProofOfPossessionCookieInfo>(void *,ushort const *,ulong,ProofOfPossessionCookieInfo *)
0x180002bec  and     byte ptr [rdi+3E2h], 0BFh
0x180002bf3  shl     sil, 6
0x180002bf7  or      [rdi+3E2h], sil
0x180002bfe  lea     rcx, [rsp+130h+var_D8]; this
0x180002c03  call    ??1SingleSignonTelemetryHelper@@QEAA@XZ; SingleSignonTelemetryHelper::~SingleSignonTelemetryHelper(void)
0x180002c08  call    cs:__imp_CoUninitialize
0x180002c0e  test    rbx, rbx
0x180002c11  jz      short loc_180002C1C
0x180002c13  mov     rcx, rbx; pv
0x180002c16  call    cs:__imp_CoTaskMemFree
0x180002c1c  mov     rcx, [rbp+57h+var_50]
0x180002c20  xor     rcx, rsp; StackCookie
0x180002c23  call    __security_check_cookie
0x180002c28  add     rsp, 0F8h
0x180002c2f  pop     r15
0x180002c31  pop     r14
0x180002c33  pop     r13
0x180002c35  pop     r12
0x180002c37  pop     rdi
0x180002c38  pop     rsi
0x180002c39  pop     rbx
0x180002c3a  pop     rbp
0x180002c3b  retn
0x180002c3c  mov     rdx, rax; SubStr
0x180002c3f  mov     rcx, r14; Str
0x180002c42  call    cs:__imp_wcsstr
0x180002c48  test    rax, rax
0x180002c4b  jz      loc_180002BB1
0x180002c51  mov     r12b, 1
0x180002c54  xor     ebx, ebx
0x180002c56  mov     [rsp+130h+var_100], r12b
0x180002c5b  xor     sil, sil
0x180002c5e  xor     r13d, r13d
0x180002c61  mov     [rbp+57h+var_C0], sil
0x180002c65  lea     rax, [rsp+130h+var_F8]
0x180002c6a  mov     [rsp+130h+var_D8], r13
0x180002c6f  mov     [rbp+57h+var_D0], rax
0x180002c73  lea     rcx, [rbp+57h+sz]; void *
0x180002c77  lea     rax, [rsp+130h+var_FC]
0x180002c7c  xor     edx, edx; Val
0x180002c7e  lea     r8d, [r13+4Eh]; Size
0x180002c82  mov     [rbp+57h+var_C8], rax
0x180002c86  call    memset_0
0x180002c8b  xorps   xmm0, xmm0
0x180002c8e  lea     rcx, [rbp+57h+pguid]; pguid
0x180002c92  movups  xmmword ptr [rbp+57h+pguid.Data1], xmm0
0x180002c96  call    cs:__imp_CoCreateGuid
0x180002c9c  lea     r8d, [r13+27h]; cchMax
0x180002ca0  lea     rdx, [rbp+57h+sz]; lpsz
0x180002ca4  lea     rcx, [rbp+57h+pguid]; rguid
0x180002ca8  call    cs:__imp_StringFromGUID2
0x180002cae  test    eax, eax
0x180002cb0  jle     short loc_180002CE1
0x180002cb2  xor     eax, eax
0x180002cb4  lea     rcx, [rbp+57h+var_9E]; unsigned __int16 *
0x180002cb8  mov     [rbp+57h+var_56], ax
0x180002cbc  call    ?OLESTRDuplicate@@YAPEAGPEBG@Z; OLESTRDuplicate(ushort const *)
0x180002cc1  mov     [rsp+130h+var_D8], rax
0x180002cc6  mov     r13, rax
0x180002cc9  test    rax, rax
0x180002ccc  jz      short loc_180002CE1
0x180002cce  lea     rcx, [rsp+130h+var_D8]
0x180002cd3  test    sil, sil
0x180002cd6  jz      loc_180002DB9
0x180002cdc  call    ??$SingleSignOnGetCookiesAadStarted@AEAPEBG@BrowserTelemetry@@SAXAEAPEBG@Z; BrowserTelemetry::SingleSignOnGetCookiesAadStarted<ushort const * &>(ushort const * &)
0x180002ce1  mov     ecx, 20000004h
0x180002ce6  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180002cec  xor     ecx, ecx
0x180002cee  test    al, al
0x180002cf0  jnz     loc_180002DE1
0x180002cf6  xor     edx, edx; pUnkOuter
0x180002cf8  mov     qword ptr [rbp+57h+pguid.Data1], rcx
0x180002cfc  mov     [rsp+130h+var_F0], rcx
0x180002d01  lea     rax, [rsp+130h+var_F0]
0x180002d06  lea     r9, _GUID_cdaece56_4edf_43df_b113_88e4556fa1bb; riid
0x180002d0d  mov     [rsp+130h+ppv], rax; ppv
0x180002d12  lea     rcx, _GUID_a9927f85_a304_4390_8b23_a75f1c668600; rclsid
0x180002d19  lea     r8d, [rdx+1]; dwClsContext
0x180002d1d  call    cs:__imp_CoCreateInstance
0x180002d23  mov     r12d, eax
0x180002d26  test    eax, eax
0x180002d28  js      short loc_180002D6D
0x180002d2a  mov     rdx, r13; wchar_t *
0x180002d2d  mov     rcx, r14; Source
0x180002d30  call    ?AddCorrelationIdParameter@@YAPEAGPEBG0@Z; AddCorrelationIdParameter(ushort const *,ushort const *)
0x180002d35  mov     rcx, [rsp+130h+var_F0]
0x180002d3a  lea     r9, [rbp+57h+pguid]
0x180002d3e  mov     r13, rax
0x180002d41  lea     r8, [rsp+130h+var_F8]
0x180002d46  test    r13, r13
0x180002d49  mov     rdx, [rcx]
0x180002d4c  cmovnz  r14, r13
0x180002d50  mov     rax, [rdx+18h]
0x180002d54  mov     rdx, r14
0x180002d57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d5c  mov     r12d, eax
0x180002d5f  test    r13, r13
0x180002d62  jz      short loc_180002D6D
0x180002d64  mov     rcx, r13; pv
0x180002d67  call    cs:__imp_CoTaskMemFree
0x180002d6d  mov     rcx, [rsp+130h+var_F0]
0x180002d72  test    rcx, rcx
0x180002d75  jz      short loc_180002D83
0x180002d77  mov     rax, [rcx]
0x180002d7a  mov     rax, [rax+10h]
0x180002d7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d83  mov     [rsp+130h+var_FC], r12d
0x180002d88  test    r12d, r12d
0x180002d8b  js      loc_180002BFE
0x180002d91  mov     r8d, [rsp+130h+var_F8]
0x180002d96  test    r8d, r8d
0x180002d99  jz      loc_180002BFE
0x180002d9f  cmp     [rsp+130h+var_100], 0
0x180002da4  jnz     loc_180002BDE
0x180002daa  mov     rcx, [rdi+160h]
0x180002db1  mov     r15, rbx
0x180002db4  jmp     loc_180002BE0
0x180002db9  call    ??$SingleSignOnGetCookiesMsaStarted@AEAPEBG@BrowserTelemetry@@SAXAEAPEBG@Z; BrowserTelemetry::SingleSignOnGetCookiesMsaStarted<ushort const * &>(ushort const * &)
0x180002dbe  jmp     loc_180002CE1
0x180002dc3  xor     r12b, r12b
0x180002dc6  mov     sil, 1
0x180002dc9  cmp     qword ptr [rdi+160h], 0
0x180002dd1  mov     [rsp+130h+var_100], r12b
0x180002dd6  jz      loc_180002C08
0x180002ddc  jmp     loc_180002C5E
0x180002de1  mov     ecx, 20000001h
0x180002de6  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180002dec  xor     ecx, ecx
0x180002dee  test    al, al
0x180002df0  jnz     loc_180002CF6
0x180002df6  mov     qword ptr [rbp+57h+pguid.Data1], rcx
0x180002dfa  mov     [rsp+130h+var_F0], rcx
0x180002dff  mov     [rsp+130h+var_E0], rcx
0x180002e04  lea     rcx, [rsp+130h+var_E0]
0x180002e09  call    cs:__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z; CoCreateUserBroker(IEUserBroker * *)
0x180002e0f  mov     [rsp+130h+var_FC], eax
0x180002e13  test    eax, eax
0x180002e15  js      loc_180002BFE
0x180002e1b  mov     rcx, [rsp+130h+var_E0]
0x180002e20  lea     r9, [rsp+130h+var_E8]
0x180002e25  mov     [rsp+130h+var_E8], 0
0x180002e2e  lea     r8, IID_IUnknown
0x180002e35  lea     rdx, CLSID_CShdocvwBroker
0x180002e3c  mov     rax, [rcx]
0x180002e3f  mov     rax, [rax+30h]
0x180002e43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e48  mov     [rsp+130h+var_FC], eax
0x180002e4c  test    eax, eax
0x180002e4e  js      short loc_180002E81
0x180002e50  mov     rcx, [rsp+130h+var_E8]
0x180002e55  lea     r8, [rsp+130h+var_F0]
0x180002e5a  lea     rdx, _GUID_cd45afe8_9a64_402a_8cfd_22bb4ebd8b42
0x180002e61  mov     rax, [rcx]
0x180002e64  mov     rax, [rax]
0x180002e67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e6c  mov     rcx, [rsp+130h+var_E8]
0x180002e71  mov     [rsp+130h+var_FC], eax
0x180002e75  mov     rax, [rcx]
0x180002e78  mov     rax, [rax+10h]
0x180002e7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e81  mov     rcx, [rsp+130h+var_E0]
0x180002e86  mov     rax, [rcx]
0x180002e89  mov     rax, [rax+10h]
0x180002e8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e92  mov     eax, [rsp+130h+var_FC]
0x180002e96  test    eax, eax
0x180002e98  js      loc_180002BFE
0x180002e9e  mov     rcx, [rsp+130h+var_F0]
0x180002ea3  lea     rdx, [rbp+57h+pguid]
0x180002ea7  mov     [rsp+130h+ppv], rdx
0x180002eac  lea     r9, [rsp+130h+var_F8]
0x180002eb1  mov     r8, r13
0x180002eb4  mov     rdx, r14
0x180002eb7  mov     rax, [rcx]
0x180002eba  mov     rax, [rax+480h]
0x180002ec1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ec6  mov     rcx, [rsp+130h+var_F0]
0x180002ecb  mov     [rsp+130h+var_FC], eax
0x180002ecf  mov     rax, [rcx]
0x180002ed2  mov     rax, [rax+10h]
0x180002ed6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002edb  cmp     [rsp+130h+var_FC], 0
0x180002ee0  jl      loc_180002BFE
0x180002ee6  mov     r8d, [rsp+130h+var_F8]
0x180002eeb  test    r8d, r8d
0x180002eee  jz      loc_180002BFE
0x180002ef4  test    r12b, r12b
0x180002ef7  jz      short loc_180002EFD
0x180002ef9  xor     ecx, ecx
0x180002efb  jmp     short loc_180002F07
0x180002efd  mov     rcx, [rdi+160h]
0x180002f04  mov     r15, rbx
0x180002f07  mov     r9, qword ptr [rbp+57h+pguid.Data1]
0x180002f0b  mov     rdx, r15
0x180002f0e  call    ??$SetCookiesAndFreeTokens@U_IEProofOfPossessionToken@@@ProofOfPossessionTokenProvider@@YAXPEAXPEBGKPEAU_IEProofOfPossessionToken@@@Z; ProofOfPossessionTokenProvider::SetCookiesAndFreeTokens<_IEProofOfPossessionToken>(void *,ushort const *,ulong,_IEProofOfPossessionToken *)
0x180002f13  jmp     loc_180002BEC
```
