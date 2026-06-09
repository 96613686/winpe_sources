# AuthenticationAdapter::GetLoginProofTokenAndProperties(HWND__ *,bool,bool,ulong,ushort * *,ushort * *,ushort * *)

- ea: `0x1800389a0`
- end: `0x180038e78`
- name: `?GetLoginProofTokenAndProperties@AuthenticationAdapter@@UEAAJPEAUHWND__@@_N1KPEAPEAG22@Z`
- size: `1240`
- prototype: `__int64 __fastcall(AuthenticationAdapter *__hidden this, HWND, bool, bool, unsigned int, unsigned __int16 **, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `14`
- tags: `broker_com_uri`

## callees

- `0x180002200`
- `0x1800023b8`
- `0x180004824`
- `0x180004910`
- `0x1800061a8`
- `0x1800090c0`
- `0x180009630`
- `0x1800281c4`
- `0x180028810`
- `0x18002ae68`
- `0x180037fe0`
- `0x180038194`
- `0x1800389a0`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180038b5a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180038c39`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180038d14`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180038b5a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180038c39`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180038d14`

## string_xrefs

- `0x1800389e9`: `AuthenticationAdapter::GetLoginProofTokenAndProperties`
- `0x180038b3f`: `hr = spTicket->get_Value(loginProofToken.GetAddressOf())`
- `0x180038b9b`: `hr = DuplicateString(loginProofToken, spLoginProofToken)`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall AuthenticationAdapter::GetLoginProofTokenAndProperties(
        AuthenticationAdapter *this,
        __int64 a2,
        char a3,
        char a4,
        __int16 a5,
        unsigned __int16 **a6,
        unsigned __int16 **a7,
        unsigned __int16 **a8)
{
  int AuthenticatedIdentity; // eax
  unsigned int v12; // r8d
  unsigned __int16 *v13; // rcx
  int v14; // eax
  const char *v15; // rcx
  unsigned int v16; // r8d
  unsigned __int16 *v17; // rax
  unsigned __int16 *v18; // rax
  unsigned int v19; // ebx
  __int64 v20; // rcx
  __int64 v21; // rcx
  char *v23; // [rsp+20h] [rbp-B9h]
  char *v24; // [rsp+20h] [rbp-B9h]
  int v25; // [rsp+30h] [rbp-A9h] BYREF
  HSTRING v26; // [rsp+38h] [rbp-A1h] BYREF
  unsigned __int16 *v27; // [rsp+40h] [rbp-99h] BYREF
  __int64 v28; // [rsp+48h] [rbp-91h]
  __int64 v29; // [rsp+50h] [rbp-89h]
  __int64 v30; // [rsp+58h] [rbp-81h] BYREF
  __int64 v31; // [rsp+60h] [rbp-79h] BYREF
  __int64 v32; // [rsp+68h] [rbp-71h] BYREF
  HSTRING string; // [rsp+70h] [rbp-69h] BYREF
  int v34; // [rsp+78h] [rbp-61h] BYREF
  unsigned __int16 *v35; // [rsp+80h] [rbp-59h] BYREF
  __int64 v36; // [rsp+88h] [rbp-51h]
  __int64 v37; // [rsp+90h] [rbp-49h]
  __int64 v38; // [rsp+98h] [rbp-41h] BYREF
  int *v39[4]; // [rsp+A0h] [rbp-39h] BYREF
  _QWORD v40[10]; // [rsp+C0h] [rbp-19h] BYREF

  v25 = 0;
  string = 0;
  v34 = 0;
  v31 = 0;
  v32 = 0;
  v30 = 0;
  v35 = 0;
  v37 = 0;
  v36 = 0;
  v40[0] = "AuthenticationAdapter::GetLoginProofTokenAndProperties";
  v40[1] = &v25;
  v40[2] = 0;
  v40[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\authenticationadapter.cpp",
    "AuthenticationAdapter::GetLoginProofTokenAndProperties",
    (const char *)0x115,
    0,
    (const unsigned __int16 *)v23);
  ErrorVerifier::ErrorVerifier(
    (ErrorVerifier *)v39,
    "AuthenticationAdapter::GetLoginProofTokenAndProperties",
    &v25,
    0x17u,
    &qword_18006BA90);
  AuthenticatedIdentity = GetAuthenticatedIdentity(a2, a3, a4, a5, (__int64)&v31);
  v25 = AuthenticatedIdentity;
  if ( AuthenticatedIdentity >= 0 )
  {
    AuthenticatedIdentity = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v31 + 48LL))(v31, &v30);
    v25 = AuthenticatedIdentity;
    if ( AuthenticatedIdentity < 0 )
    {
      v24 = "hr = spUserIdentity->get_Tickets(spTickets.GetAddressOf())";
      v12 = 293;
      goto LABEL_3;
    }
    AuthenticatedIdentity = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v30 + 56LL))(v30, &v34);
    v25 = AuthenticatedIdentity;
    if ( AuthenticatedIdentity < 0 )
    {
      v24 = "hr = spTickets->get_Size(&ticketCount)";
      v12 = 294;
      goto LABEL_3;
    }
    AuthenticatedIdentity = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v30 + 48LL))(
                              v30,
                              0,
                              &v32);
    v25 = AuthenticatedIdentity;
    if ( AuthenticatedIdentity < 0 )
    {
      v24 = "hr = spTickets->GetAt(0, spTicket.GetAddressOf())";
      v12 = 296;
      goto LABEL_3;
    }
    AuthenticatedIdentity = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v32 + 48LL))(v32, &string);
    v25 = AuthenticatedIdentity;
    if ( AuthenticatedIdentity < 0 )
    {
      v24 = "hr = spTicket->get_Value(loginProofToken.GetAddressOf())";
      v12 = 297;
      goto LABEL_3;
    }
    if ( WindowsIsStringEmpty(string) )
    {
      v25 = -2147418113;
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\authenticationadapter.cpp",
        "AuthenticationAdapter::GetLoginProofTokenAndProperties",
        0x12Eu,
        -2147418113,
        "hr = E_UNEXPECTED");
      goto LABEL_34;
    }
    AuthenticatedIdentity = DuplicateString(&string, &v35);
    v25 = AuthenticatedIdentity;
    if ( AuthenticatedIdentity < 0 )
    {
      v24 = "hr = DuplicateString(loginProofToken, spLoginProofToken)";
      v12 = 305;
      goto LABEL_3;
    }
    v13 = v35;
    v35 = 0;
    v36 = 0;
    *a6 = v13;
    if ( a7 )
    {
      v26 = 0;
      v27 = 0;
      v29 = 0;
      v28 = 0;
      v14 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v31 + 64LL))(v31, &v26);
      v25 = v14;
      if ( v14 < 0 )
      {
        v15 = "hr = spUserIdentity->get_SafeCustomerId(accountId.GetAddressOf())";
        v16 = 312;
LABEL_27:
        Telemetry::IfFailExit(
          "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\authenticationadapter.cpp",
          "AuthenticationAdapter::GetLoginProofTokenAndProperties",
          v16,
          v14,
          v15);
        goto LABEL_33;
      }
      if ( WindowsIsStringEmpty(v26) )
      {
        v25 = -2147418113;
        Telemetry::IfFailExit(
          "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\authenticationadapter.cpp",
          "AuthenticationAdapter::GetLoginProofTokenAndProperties",
          0x13Cu,
          -2147418113,
          "hr = E_UNEXPECTED");
LABEL_33:
        Auto<unsigned short *,LocalMIDLPointerFunctor<unsigned short *>,DummyContext>::~Auto<unsigned short *,LocalMIDLPointerFunctor<unsigned short *>,DummyContext>(&v27);
        Windows::Internal::String::~String(&v26);
        goto LABEL_34;
      }
      v14 = DuplicateString(&v26, &v27);
      v25 = v14;
      if ( v14 < 0 )
      {
        v15 = "hr = DuplicateString(accountId, spAccountId)";
        v16 = 319;
        goto LABEL_27;
      }
      v17 = v27;
      v27 = 0;
      v28 = 0;
      *a7 = v17;
      Auto<unsigned short *,LocalMIDLPointerFunctor<unsigned short *>,DummyContext>::~Auto<unsigned short *,LocalMIDLPointerFunctor<unsigned short *>,DummyContext>(&v27);
      Windows::Internal::String::~String(&v26);
    }
    if ( !a8 )
      goto LABEL_34;
    v26 = 0;
    v27 = 0;
    v29 = 0;
    v28 = 0;
    v14 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v31 + 72LL))(v31, &v26);
    v25 = v14;
    if ( v14 >= 0 )
    {
      if ( WindowsIsStringEmpty(v26) )
      {
        v25 = -2147418113;
        Telemetry::IfFailExit(
          "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\authenticationadapter.cpp",
          "AuthenticationAdapter::GetLoginProofTokenAndProperties",
          0x14Bu,
          -2147418113,
          "hr = E_UNEXPECTED");
        goto LABEL_33;
      }
      v14 = DuplicateString(&v26, &v27);
      v25 = v14;
      if ( v14 >= 0 )
      {
        v18 = v27;
        v27 = 0;
        v28 = 0;
        *a8 = v18;
        goto LABEL_33;
      }
      v15 = "hr = DuplicateString(accountName, spAccountName)";
      v16 = 334;
    }
    else
    {
      v15 = "hr = spUserIdentity->get_SignInName(accountName.GetAddressOf())";
      v16 = 327;
    }
    goto LABEL_27;
  }
  v24 = "hr = GetAuthenticatedIdentity(hWnd, useStrongAuth, isPinReset, dwflags, spUserIdentity)";
  v12 = 291;
LABEL_3:
  Telemetry::IfFailExit(
    "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\authenticationadapter.cpp",
    "AuthenticationAdapter::GetLoginProofTokenAndProperties",
    v12,
    AuthenticatedIdentity,
    v24);
LABEL_34:
  if ( (unsigned int)dword_180084278 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180084278, 0x400000000000LL) )
  {
    LODWORD(v26) = v25;
    v38 = 50331648;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      (unsigned int)&dword_180084278,
      (unsigned int)word_180076D5A,
      0,
      0,
      (__int64)&v38,
      (__int64)&v26);
  }
  v19 = v25;
  ErrorVerifier::CheckAgainstList((const char *)v39[3], *v39[2], (unsigned __int64)v39[1], v39[0]);
  CTraceFuncW<long>::~CTraceFuncW<long>(v40);
  Auto<unsigned short *,LocalMIDLPointerFunctor<unsigned short *>,DummyContext>::~Auto<unsigned short *,LocalMIDLPointerFunctor<unsigned short *>,DummyContext>(&v35);
  v20 = v30;
  if ( v30 )
  {
    v30 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  }
  v21 = v32;
  if ( v32 )
  {
    v32 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
  Windows::Internal::String::~String(&string);
  return v19;
}

```

## disassembly

```asm
0x1800389a0  push    rbp
0x1800389a2  push    rbx
0x1800389a3  push    rsi
0x1800389a4  push    rdi
0x1800389a5  push    r12
0x1800389a7  push    r14
0x1800389a9  push    r15
0x1800389ab  lea     rbp, [rsp-7]
0x1800389b0  sub     rsp, 0E0h
0x1800389b7  mov     bl, r9b
0x1800389ba  mov     dil, r8b
0x1800389bd  mov     rsi, rdx
0x1800389c0  xor     r14d, r14d
0x1800389c3  mov     [rsp+110h+var_E0], r14d
0x1800389c8  mov     [rbp+37h+string], r14
0x1800389cc  mov     [rbp+37h+var_98], r14d
0x1800389d0  mov     [rbp+37h+var_B0], r14
0x1800389d4  mov     [rbp+37h+var_A8], r14
0x1800389d8  mov     [rsp+110h+var_B8], r14
0x1800389dd  mov     [rbp+37h+var_90], r14
0x1800389e1  mov     [rbp+37h+var_80], r14
0x1800389e5  mov     [rbp+37h+var_88], r14
0x1800389e9  lea     r15, aAuthentication; "AuthenticationAdapter::GetLoginProofTok"...
0x1800389f0  mov     [rbp+37h+var_50], r15
0x1800389f4  lea     rax, [rsp+110h+var_E0]
0x1800389f9  mov     [rbp+37h+var_48], rax
0x1800389fd  mov     [rbp+37h+var_40], r14
0x180038a01  mov     [rbp+37h+var_38], r14
0x180038a05  xor     r9d, r9d; unsigned int
0x180038a08  mov     r8d, 115h; char *
0x180038a0e  mov     rdx, r15; char *
0x180038a11  lea     r12, aOnecoreuapDsEx_24; "onecoreuap\\ds\\ext\\live\\identity\\id"...
0x180038a18  mov     rcx, r12; this
0x180038a1b  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x180038a20  nop
0x180038a21  lea     rax, qword_18006BA90
0x180038a28  mov     [rsp+110h+var_F0], rax; int *
0x180038a2d  lea     r9d, [r14+17h]; unsigned __int64
0x180038a31  lea     r8, [rsp+110h+var_E0]; int *
0x180038a36  mov     rdx, r15; char *
0x180038a39  lea     rcx, [rbp+37h+var_70]; this
0x180038a3d  call    ??0ErrorVerifier@@QEAA@PEBDPEAJ_KPEBJ@Z; ErrorVerifier::ErrorVerifier(char const *,long *,unsigned __int64,long const *)
0x180038a42  nop
0x180038a43  lea     rax, [rbp+37h+var_B0]
0x180038a47  mov     [rsp+110h+var_F0], rax
0x180038a4c  mov     r9d, dword ptr [rbp+37h+arg_20]
0x180038a50  mov     r8b, bl
0x180038a53  mov     dl, dil
0x180038a56  mov     rcx, rsi
0x180038a59  call    ?GetAuthenticatedIdentity@@YAJPEAUHWND__@@_N1KAEAV?$ComPtr@UIUserIdentity@OnlineId@Authentication@Security@Windows@@@WRL@Microsoft@@@Z; GetAuthenticatedIdentity(HWND__ *,bool,bool,ulong,Microsoft::WRL::ComPtr<Windows::Security::Authentication::OnlineId::IUserIdentity> &)
0x180038a5e  mov     [rsp+110h+var_E0], eax
0x180038a62  test    eax, eax
0x180038a64  jns     short loc_180038A8B
0x180038a66  lea     r8, aHrGetauthentic_0; "hr = GetAuthenticatedIdentity(hWnd, use"...
0x180038a6d  mov     [rsp+110h+var_F0], r8; char *
0x180038a72  mov     r8d, 123h; unsigned int
0x180038a78  mov     r9d, eax; int
0x180038a7b  mov     rdx, r15; char *
0x180038a7e  mov     rcx, r12; char *
0x180038a81  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180038a86  jmp     loc_180038D8A
0x180038a8b  mov     rcx, [rbp+37h+var_B0]
0x180038a8f  mov     rax, [rcx]
0x180038a92  lea     rdx, [rsp+110h+var_B8]
0x180038a97  mov     rax, [rax+30h]
0x180038a9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038aa0  mov     [rsp+110h+var_E0], eax
0x180038aa4  test    eax, eax
0x180038aa6  jns     short loc_180038ABC
0x180038aa8  lea     rcx, aHrSpuseridenti_1; "hr = spUserIdentity->get_Tickets(spTick"...
0x180038aaf  mov     [rsp+110h+var_F0], rcx
0x180038ab4  mov     r8d, 125h
0x180038aba  jmp     short loc_180038A78
0x180038abc  mov     rcx, [rsp+110h+var_B8]
0x180038ac1  mov     rax, [rcx]
0x180038ac4  lea     rdx, [rbp+37h+var_98]
0x180038ac8  mov     rax, [rax+38h]
0x180038acc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038ad1  mov     [rsp+110h+var_E0], eax
0x180038ad5  test    eax, eax
0x180038ad7  jns     short loc_180038AED
0x180038ad9  lea     rcx, aHrSpticketsGet; "hr = spTickets->get_Size(&ticketCount)"
0x180038ae0  mov     [rsp+110h+var_F0], rcx
0x180038ae5  mov     r8d, 126h
0x180038aeb  jmp     short loc_180038A78
0x180038aed  mov     rcx, [rsp+110h+var_B8]
0x180038af2  mov     rax, [rcx]
0x180038af5  lea     r8, [rbp+37h+var_A8]
0x180038af9  xor     edx, edx
0x180038afb  mov     rax, [rax+30h]
0x180038aff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038b04  mov     [rsp+110h+var_E0], eax
0x180038b08  test    eax, eax
0x180038b0a  jns     short loc_180038B23
0x180038b0c  lea     rcx, aHrSpticketsGet_0; "hr = spTickets->GetAt(0, spTicket.GetAd"...
0x180038b13  mov     [rsp+110h+var_F0], rcx
0x180038b18  mov     r8d, 128h
0x180038b1e  jmp     loc_180038A78
0x180038b23  mov     rcx, [rbp+37h+var_A8]
0x180038b27  mov     rax, [rcx]
0x180038b2a  lea     rdx, [rbp+37h+string]
0x180038b2e  mov     rax, [rax+30h]
0x180038b32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038b37  mov     [rsp+110h+var_E0], eax
0x180038b3b  test    eax, eax
0x180038b3d  jns     short loc_180038B56
0x180038b3f  lea     rcx, aHrSpticketGetV; "hr = spTicket->get_Value(loginProofToke"...
0x180038b46  mov     [rsp+110h+var_F0], rcx
0x180038b4b  mov     r8d, 129h
0x180038b51  jmp     loc_180038A78
0x180038b56  mov     rcx, [rbp+37h+string]; string
0x180038b5a  call    cs:__imp_WindowsIsStringEmpty
0x180038b60  test    eax, eax
0x180038b62  jz      short loc_180038B86
0x180038b64  mov     r9d, 8000FFFFh
0x180038b6a  mov     [rsp+110h+var_E0], r9d
0x180038b6f  lea     rax, aHrEUnexpected; "hr = E_UNEXPECTED"
0x180038b76  mov     [rsp+110h+var_F0], rax
0x180038b7b  mov     r8d, 12Eh
0x180038b81  jmp     loc_180038A7B
0x180038b86  lea     rdx, [rbp+37h+var_90]
0x180038b8a  lea     rcx, [rbp+37h+string]
0x180038b8e  call    ?DuplicateString@@YAJAEBVString@Internal@Windows@@AEAV?$Auto@PEAGV?$LocalMIDLPointerFunctor@PEAG@@VDummyContext@@@@@Z; DuplicateString(Windows::Internal::String const &,Auto<ushort *,LocalMIDLPointerFunctor<ushort *>,DummyContext> &)
0x180038b93  mov     [rsp+110h+var_E0], eax
0x180038b97  test    eax, eax
0x180038b99  jns     short loc_180038BB2
0x180038b9b  lea     rcx, aHrDuplicatestr_0; "hr = DuplicateString(loginProofToken, s"...
0x180038ba2  mov     [rsp+110h+var_F0], rcx
0x180038ba7  mov     r8d, 131h
0x180038bad  jmp     loc_180038A78
0x180038bb2  mov     rcx, [rbp+37h+var_90]
0x180038bb6  mov     [rbp+37h+var_90], r14
0x180038bba  mov     [rbp+37h+var_88], r14
0x180038bbe  mov     rax, [rbp+37h+arg_28]
0x180038bc2  mov     [rax], rcx
0x180038bc5  mov     rbx, [rbp+37h+arg_30]
0x180038bc9  test    rbx, rbx
0x180038bcc  jz      loc_180038CAF
0x180038bd2  mov     [rsp+110h+var_D8], r14
0x180038bd7  mov     [rsp+110h+var_D0], r14
0x180038bdc  mov     [rsp+110h+var_C0], r14
0x180038be1  mov     [rsp+110h+var_C8], r14
0x180038be6  mov     rcx, [rbp+37h+var_B0]
0x180038bea  mov     rax, [rcx]
0x180038bed  lea     rdx, [rsp+110h+var_D8]
0x180038bf2  mov     rax, [rax+40h]
0x180038bf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038bfb  mov     [rsp+110h+var_E0], eax
0x180038bff  test    eax, eax
0x180038c01  jns     short loc_180038C34
0x180038c03  lea     rcx, aHrSpuseridenti; "hr = spUserIdentity->get_SafeCustomerId"...
0x180038c0a  mov     r8d, 138h; unsigned int
0x180038c10  mov     r9d, eax; int
0x180038c13  mov     [rsp+110h+var_F0], rcx; char *
0x180038c18  mov     rdx, r15; char *
0x180038c1b  mov     rcx, r12; char *
0x180038c1e  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180038c23  nop
0x180038c24  lea     rcx, [rsp+110h+var_D0]
0x180038c29  call    ??1?$Auto@PEAGV?$LocalMIDLPointerFunctor@PEAG@@VDummyContext@@@@QEAA@XZ; Auto<ushort *,LocalMIDLPointerFunctor<ushort *>,DummyContext>::~Auto<ushort *,LocalMIDLPointerFunctor<ushort *>,DummyContext>(void)
0x180038c2e  nop
0x180038c2f  jmp     loc_180038D80
0x180038c34  mov     rcx, [rsp+110h+var_D8]; string
0x180038c39  call    cs:__imp_WindowsIsStringEmpty
0x180038c3f  test    eax, eax
0x180038c41  jz      short loc_180038C62
0x180038c43  mov     r9d, 8000FFFFh
0x180038c49  mov     [rsp+110h+var_E0], r9d
0x180038c4e  lea     rax, aHrEUnexpected; "hr = E_UNEXPECTED"
0x180038c55  mov     [rsp+110h+var_F0], rax
0x180038c5a  mov     r8d, 13Ch
0x180038c60  jmp     short loc_180038C18
0x180038c62  lea     rdx, [rsp+110h+var_D0]
0x180038c67  lea     rcx, [rsp+110h+var_D8]
0x180038c6c  call    ?DuplicateString@@YAJAEBVString@Internal@Windows@@AEAV?$Auto@PEAGV?$LocalMIDLPointerFunctor@PEAG@@VDummyContext@@@@@Z; DuplicateString(Windows::Internal::String const &,Auto<ushort *,LocalMIDLPointerFunctor<ushort *>,DummyContext> &)
0x180038c71  mov     [rsp+110h+var_E0], eax
0x180038c75  test    eax, eax
0x180038c77  jns     short loc_180038C88
0x180038c79  lea     rcx, aHrDuplicatestr_1; "hr = DuplicateString(accountId, spAccou"...
0x180038c80  mov     r8d, 13Fh
0x180038c86  jmp     short loc_180038C10
0x180038c88  mov     rax, [rsp+110h+var_D0]
0x180038c8d  mov     [rsp+110h+var_D0], r14
0x180038c92  mov     [rsp+110h+var_C8], r14
0x180038c97  mov     [rbx], rax
0x180038c9a  lea     rcx, [rsp+110h+var_D0]
0x180038c9f  call    ??1?$Auto@PEAGV?$LocalMIDLPointerFunctor@PEAG@@VDummyContext@@@@QEAA@XZ; Auto<ushort *,LocalMIDLPointerFunctor<ushort *>,DummyContext>::~Auto<ushort *,LocalMIDLPointerFunctor<ushort *>,DummyContext>(void)
0x180038ca4  nop
0x180038ca5  lea     rcx, [rsp+110h+var_D8]; this
0x180038caa  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180038caf  mov     rbx, [rbp+37h+arg_38]
0x180038cb3  test    rbx, rbx
0x180038cb6  jz      loc_180038D8A
0x180038cbc  mov     [rsp+110h+var_D8], r14
0x180038cc1  mov     [rsp+110h+var_D0], r14
0x180038cc6  mov     [rsp+110h+var_C0], r14
0x180038ccb  mov     [rsp+110h+var_C8], r14
0x180038cd0  mov     rcx, [rbp+37h+var_B0]
0x180038cd4  mov     rax, [rcx]
0x180038cd7  lea     rdx, [rsp+110h+var_D8]
0x180038cdc  mov     rax, [rax+48h]
0x180038ce0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038ce5  mov     [rsp+110h+var_E0], eax
0x180038ce9  test    eax, eax
0x180038ceb  jns     short loc_180038D0F
0x180038ced  lea     rcx, aHrSpuseridenti_0; "hr = spUserIdentity->get_SignInName(acc"...
0x180038cf4  mov     r8d, 147h; unsigned int
0x180038cfa  mov     r9d, eax; int
0x180038cfd  mov     [rsp+110h+var_F0], rcx; char *
0x180038d02  mov     rdx, r15; char *
0x180038d05  mov     rcx, r12; char *
0x180038d08  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180038d0d  jmp     short loc_180038D75
0x180038d0f  mov     rcx, [rsp+110h+var_D8]; string
0x180038d14  call    cs:__imp_WindowsIsStringEmpty
0x180038d1a  test    eax, eax
0x180038d1c  jz      short loc_180038D3D
0x180038d1e  mov     r9d, 8000FFFFh
0x180038d24  mov     [rsp+110h+var_E0], r9d
0x180038d29  lea     rax, aHrEUnexpected; "hr = E_UNEXPECTED"
0x180038d30  mov     [rsp+110h+var_F0], rax
0x180038d35  mov     r8d, 14Bh
0x180038d3b  jmp     short loc_180038D02
0x180038d3d  lea     rdx, [rsp+110h+var_D0]
0x180038d42  lea     rcx, [rsp+110h+var_D8]
0x180038d47  call    ?DuplicateString@@YAJAEBVString@Internal@Windows@@AEAV?$Auto@PEAGV?$LocalMIDLPointerFunctor@PEAG@@VDummyContext@@@@@Z; DuplicateString(Windows::Internal::String const &,Auto<ushort *,LocalMIDLPointerFunctor<ushort *>,DummyContext> &)
0x180038d4c  mov     [rsp+110h+var_E0], eax
0x180038d50  test    eax, eax
0x180038d52  jns     short loc_180038D63
0x180038d54  lea     rcx, aHrDuplicatestr; "hr = DuplicateString(accountName, spAcc"...
0x180038d5b  mov     r8d, 14Eh
0x180038d61  jmp     short loc_180038CFA
0x180038d63  mov     rax, [rsp+110h+var_D0]
0x180038d68  mov     [rsp+110h+var_D0], r14
0x180038d6d  mov     [rsp+110h+var_C8], r14
0x180038d72  mov     [rbx], rax
0x180038d75  lea     rcx, [rsp+110h+var_D0]
0x180038d7a  call    ??1?$Auto@PEAGV?$LocalMIDLPointerFunctor@PEAG@@VDummyContext@@@@QEAA@XZ; Auto<ushort *,LocalMIDLPointerFunctor<ushort *>,DummyContext>::~Auto<ushort *,LocalMIDLPointerFunctor<ushort *>,DummyContext>(void)
0x180038d7f  nop
0x180038d80  lea     rcx, [rsp+110h+var_D8]; this
0x180038d85  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180038d8a  mov     eax, cs:dword_180084278
0x180038d90  cmp     eax, 5
0x180038d93  jbe     short loc_180038DEB
0x180038d95  mov     rdx, 400000000000h
0x180038d9f  lea     rcx, dword_180084278
0x180038da6  call    _tlgKeywordOn
0x180038dab  test    al, al
0x180038dad  jz      short loc_180038DEB
0x180038daf  mov     eax, [rsp+110h+var_E0]
0x180038db3  mov     dword ptr [rsp+110h+var_D8], eax
0x180038db7  mov     [rbp+37h+var_78], 3000000h
0x180038dbf  lea     rax, [rsp+110h+var_D8]
0x180038dc4  mov     [rsp+110h+var_E8], rax
0x180038dc9  lea     rax, [rbp+37h+var_78]
0x180038dcd  mov     [rsp+110h+var_F0], rax
0x180038dd2  xor     r9d, r9d
0x180038dd5  xor     r8d, r8d
0x180038dd8  lea     rdx, word_180076D5A
0x180038ddf  lea     rcx, dword_180084278
0x180038de6  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180038deb  mov     ebx, [rsp+110h+var_E0]
0x180038def  mov     r9, [rbp+37h+var_70]; int *
0x180038df3  mov     r8, [rbp+37h+var_68]; unsigned __int64
0x180038df7  mov     rdx, [rbp+37h+var_60]
0x180038dfb  mov     edx, [rdx]; int
0x180038dfd  mov     rcx, [rbp+37h+var_58]; char *
0x180038e01  call    ?CheckAgainstList@ErrorVerifier@@SAXPEBDJ_KPEBJ@Z; ErrorVerifier::CheckAgainstList(char const *,long,unsigned __int64,long const *)
0x180038e06  nop
0x180038e07  lea     rcx, [rbp+37h+var_50]
0x180038e0b  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180038e10  nop
0x180038e11  lea     rcx, [rbp+37h+var_90]
0x180038e15  call    ??1?$Auto@PEAGV?$LocalMIDLPointerFunctor@PEAG@@VDummyContext@@@@QEAA@XZ; Auto<ushort *,LocalMIDLPointerFunctor<ushort *>,DummyContext>::~Auto<ushort *,LocalMIDLPointerFunctor<ushort *>,DummyContext>(void)
0x180038e1a  nop
0x180038e1b  mov     rcx, [rsp+110h+var_B8]
0x180038e20  test    rcx, rcx
0x180038e23  jz      short loc_180038E37
0x180038e25  mov     [rsp+110h+var_B8], r14
0x180038e2a  mov     rax, [rcx]
0x180038e2d  mov     rax, [rax+10h]
0x180038e31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038e36  nop
0x180038e37  mov     rcx, [rbp+37h+var_A8]
0x180038e3b  test    rcx, rcx
0x180038e3e  jz      short loc_180038E51
0x180038e40  mov     [rbp+37h+var_A8], r14
0x180038e44  mov     rdx, [rcx]
0x180038e47  mov     rax, [rdx+10h]
0x180038e4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038e50  nop
0x180038e51  lea     rcx, [rbp+37h+var_B0]
0x180038e55  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180038e5a  nop
0x180038e5b  lea     rcx, [rbp+37h+string]; this
0x180038e5f  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180038e64  mov     eax, ebx
0x180038e66  add     rsp, 0E0h
0x180038e6d  pop     r15
0x180038e6f  pop     r14
  ... truncated ...
```
