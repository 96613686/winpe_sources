# CloudAPHelper::LogonUserW(uchar *,ulong,void * *,long *)

- ea: `0x180010870`
- end: `0x180010bf2`
- name: `?LogonUserW@CloudAPHelper@@UEAAJPEAEKPEAPEAXPEAJ@Z`
- size: `898`
- prototype: `int(CloudAPHelper *__hidden this, unsigned __int8 *, unsigned int, void **, int *)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800013bc`
- `0x1800014c4`
- `0x180001608`
- `0x180010870`
- `0x180011f48`
- `0x180014c74`
- `0x1800155c0`

## import_xrefs

- `SspiCli!LsaLogonUser` at `0x180010a86`
- `SspiCli!LsaLogonUser` at `0x180010a86`
- `SspiCli!LsaFreeReturnBuffer` at `0x180010bd3`
- `SspiCli!LsaFreeReturnBuffer` at `0x180010bd3`

## string_xrefs

- `0x180010937`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x1800109d7`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x180010ad4`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x1800108cc`: `Terminal Services API`
- `0x1800109ae`: `Missing paramter phToken`

## pseudocode

```c
__int64 __fastcall CloudAPHelper::LogonUserW(
        CloudAPHelper *this,
        unsigned __int8 *AuthenticationInformation,
        ULONG AuthenticationInformationLength,
        void **Token,
        int *a5)
{
  unsigned int v6; // ebx
  NTSTATUS v7; // eax
  int v8; // r8d
  int v9; // r9d
  int v10; // ebx
  void *v11; // rdx
  int v12; // ecx
  int v13; // r8d
  int v14; // r9d
  int v16; // [rsp+70h] [rbp-90h] BYREF
  int v17; // [rsp+74h] [rbp-8Ch] BYREF
  int SubStatus; // [rsp+78h] [rbp-88h] BYREF
  const char *v19; // [rsp+80h] [rbp-80h] BYREF
  const char *v20; // [rsp+88h] [rbp-78h] BYREF
  const char *v21; // [rsp+90h] [rbp-70h] BYREF
  const char *v22; // [rsp+98h] [rbp-68h] BYREF
  ULONG ProfileBufferLength; // [rsp+A0h] [rbp-60h] BYREF
  const char *v24; // [rsp+A8h] [rbp-58h] BYREF
  PVOID Buffer; // [rsp+B0h] [rbp-50h] BYREF
  struct _LSA_STRING OriginName; // [rsp+B8h] [rbp-48h] BYREF
  struct _LUID LogonId; // [rsp+C8h] [rbp-38h] BYREF
  struct _TOKEN_SOURCE SourceContext; // [rsp+D0h] [rbp-30h] BYREF
  struct _QUOTA_LIMITS Quotas; // [rsp+E0h] [rbp-20h] BYREF
  char v30[24]; // [rsp+110h] [rbp+10h] BYREF

  SubStatus = 0;
  *(_QWORD *)&OriginName.Length = 1441813;
  OriginName.Buffer = v30;
  Buffer = 0;
  ProfileBufferLength = 0;
  LogonId = 0;
  strcpy(v30, "Terminal Services API");
  SourceContext = 0;
  memset(&Quotas, 0, sizeof(Quotas));
  if ( AuthenticationInformation )
  {
    if ( Token )
    {
      v7 = LsaLogonUser(
             *((HANDLE *)this + 7),
             &OriginName,
             Network,
             *((_DWORD *)this + 17),
             AuthenticationInformation,
             AuthenticationInformationLength,
             0,
             &SourceContext,
             &Buffer,
             &ProfileBufferLength,
             &LogonId,
             Token,
             &Quotas,
             &SubStatus);
      if ( v7 >= 0 )
      {
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AuthenticationPackageUtilizationTelemetry>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AuthenticationPackageUtilizationTelemetry>::GetImpl'::`2'::impl) )
        {
          v12 = SecUtils::TraceAuthenticationPackageInfo(*Token, v11);
          if ( v12 < 0 && (unsigned int)dword_18001F000 > 3 )
          {
            LODWORD(v19) = v12;
            v24 = "LogonUserW";
            v21 = "Failed to log authentication package info";
            v20 = "HResult failed but continue";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
              v12,
              (unsigned int)qword_18001A230,
              v13,
              v14,
              (__int64)&v20,
              (__int64)&v21,
              (__int64)&v19,
              (__int64)&v24);
          }
        }
        v6 = 0;
      }
      else
      {
        if ( v7 != -1073741714 || (v10 = SubStatus) == 0 )
          v10 = v7;
        v6 = v10 | 0x10000000;
        if ( (unsigned int)dword_18001F000 > 2 )
        {
          v17 = SubStatus;
          v21 = "LogonUserW";
          v20 = "onecore\\termsrv\\rdp\\win\\security\\cloudaphelper.cpp";
          v24 = "LsaLogonUser failed.";
          v16 = v7;
          LODWORD(v22) = 392;
          LODWORD(v19) = v6;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v7,
            (unsigned int)&byte_18001A1D7,
            v8,
            v9,
            (__int64)&v24,
            (__int64)&v19,
            (__int64)&v20,
            (__int64)&v22,
            (__int64)&v21,
            (__int64)&v16,
            (__int64)&v17);
        }
      }
      if ( a5 )
        *a5 = SubStatus;
    }
    else
    {
      v6 = -2147024809;
      if ( (unsigned int)dword_18001F000 > 2 )
      {
        v17 = 362;
        v21 = "Missing paramter phToken";
        v16 = -2147024809;
        v20 = "LogonUserW";
        v19 = "onecore\\termsrv\\rdp\\win\\security\\cloudaphelper.cpp";
        v22 = "Error condition failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          -2147024809,
          (unsigned int)&dword_18001A26C,
          AuthenticationInformationLength,
          0,
          (__int64)&v22,
          (__int64)&v16,
          (__int64)&v19,
          (__int64)&v17,
          (__int64)&v20,
          (__int64)&v21);
      }
    }
  }
  else
  {
    v6 = -2147024809;
    if ( (unsigned int)dword_18001F000 > 2 )
    {
      v16 = 361;
      v19 = "Missing paramter pAuthBlob";
      v17 = -2147024809;
      v22 = "LogonUserW";
      v20 = "onecore\\termsrv\\rdp\\win\\security\\cloudaphelper.cpp";
      v21 = "Error condition failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        -2147024809,
        (unsigned int)word_18001A2BA,
        AuthenticationInformationLength,
        (_DWORD)Token,
        (__int64)&v21,
        (__int64)&v17,
        (__int64)&v20,
        (__int64)&v16,
        (__int64)&v22,
        (__int64)&v19);
    }
  }
  if ( Buffer )
    LsaFreeReturnBuffer(Buffer);
  return v6;
}

```

## disassembly

```asm
0x180010870  push    rbp
0x180010872  push    rbx
0x180010873  push    rdi
0x180010874  lea     rbp, [rsp-30h]
0x180010879  sub     rsp, 130h
0x180010880  mov     rax, cs:__security_cookie
0x180010887  xor     rax, rsp
0x18001088a  mov     [rbp+40h+var_18], rax
0x18001088e  movsd   xmm1, qword ptr cs:aTerminalServic+0Eh; "ces API"
0x180010896  lea     rax, [rbp+40h+var_30]
0x18001089a  mov     rdi, [rbp+40h+arg_20]
0x18001089e  mov     rbx, r9
0x1800108a1  mov     [rsp+140h+var_C8], 0
0x1800108a9  mov     qword ptr [rbp+40h+OriginName.Length], 160015h
0x1800108b1  mov     [rbp+40h+OriginName.Buffer], rax
0x1800108b5  mov     [rbp+40h+Buffer], 0
0x1800108bd  mov     [rbp+40h+var_A0], 0
0x1800108c4  mov     qword ptr [rbp+40h+var_78.LowPart], 0
0x1800108cc  movups  xmm0, xmmword ptr cs:aTerminalServic; "Terminal Services API"
0x1800108d3  movups  xmmword ptr [rbp+40h+var_30], xmm0
0x1800108d7  movsd   qword ptr [rbp+40h+var_30+0Eh], xmm1
0x1800108dc  xorps   xmm0, xmm0
0x1800108df  movups  xmmword ptr [rbp+40h+var_70.SourceName], xmm0
0x1800108e3  movups  xmmword ptr [rbp+40h+var_60.PagedPoolLimit], xmm0
0x1800108e7  movups  xmmword ptr [rbp+40h+var_60.MinimumWorkingSetSize], xmm0
0x1800108eb  movups  xmmword ptr [rbp+40h+var_60.PagefileLimit], xmm0
0x1800108ef  test    rdx, rdx
0x1800108f2  jnz     loc_18001098F
0x1800108f8  mov     eax, cs:dword_18001F000
0x1800108fe  mov     ecx, 80070057h
0x180010903  mov     ebx, ecx
0x180010905  cmp     eax, 2
0x180010908  jbe     loc_180010BCA
0x18001090e  lea     rax, aMissingParamte_0; "Missing paramter pAuthBlob"
0x180010915  mov     [rsp+140h+var_D0], 169h
0x18001091d  mov     [rbp+40h+var_C0], rax
0x180010921  lea     rdx, word_18001A2BA
0x180010928  lea     rax, aLogonuserw; "LogonUserW"
0x18001092f  mov     [rsp+140h+var_CC], ecx
0x180010933  mov     [rbp+40h+var_A8], rax
0x180010937  lea     rax, aOnecoreTermsrv_0; "onecore\\termsrv\\rdp\\win\\security\\c"...
0x18001093e  mov     [rbp+40h+var_B8], rax
0x180010942  lea     rax, aErrorCondition; "Error condition failed"
0x180010949  mov     [rbp+40h+var_B0], rax
0x18001094d  lea     rax, [rbp+40h+var_C0]
0x180010951  mov     [rsp+140h+ProfileBufferLength], rax
0x180010956  lea     rax, [rbp+40h+var_A8]
0x18001095a  mov     [rsp+140h+ProfileBuffer], rax
0x18001095f  lea     rax, [rsp+140h+var_D0]
0x180010964  mov     [rsp+140h+SourceContext], rax
0x180010969  lea     rax, [rbp+40h+var_B8]
0x18001096d  mov     [rsp+140h+LocalGroups], rax
0x180010972  lea     rax, [rsp+140h+var_CC]
0x180010977  mov     qword ptr [rsp+140h+AuthenticationInformationLength], rax
0x18001097c  lea     rax, [rbp+40h+var_B0]
0x180010980  mov     [rsp+140h+AuthenticationInformation], rax
0x180010985  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18001098a  jmp     loc_180010BCA
0x18001098f  test    rbx, rbx
0x180010992  jnz     loc_180010A25
0x180010998  mov     eax, cs:dword_18001F000
0x18001099e  mov     ecx, 80070057h
0x1800109a3  mov     ebx, ecx
0x1800109a5  cmp     eax, 2
0x1800109a8  jbe     loc_180010BCA
0x1800109ae  lea     rax, aMissingParamte_2; "Missing paramter phToken"
0x1800109b5  mov     [rsp+140h+var_CC], 16Ah
0x1800109bd  mov     [rbp+40h+var_B0], rax
0x1800109c1  lea     rdx, dword_18001A26C
0x1800109c8  lea     rax, aLogonuserw; "LogonUserW"
0x1800109cf  mov     [rsp+140h+var_D0], ecx
0x1800109d3  mov     [rbp+40h+var_B8], rax
0x1800109d7  lea     rax, aOnecoreTermsrv_0; "onecore\\termsrv\\rdp\\win\\security\\c"...
0x1800109de  mov     [rbp+40h+var_C0], rax
0x1800109e2  lea     rax, aErrorCondition; "Error condition failed"
0x1800109e9  mov     [rbp+40h+var_A8], rax
0x1800109ed  lea     rax, [rbp+40h+var_B0]
0x1800109f1  mov     [rsp+140h+ProfileBufferLength], rax
0x1800109f6  lea     rax, [rbp+40h+var_B8]
0x1800109fa  mov     [rsp+140h+ProfileBuffer], rax
0x1800109ff  lea     rax, [rsp+140h+var_CC]
0x180010a04  mov     [rsp+140h+SourceContext], rax
0x180010a09  lea     rax, [rbp+40h+var_C0]
0x180010a0d  mov     [rsp+140h+LocalGroups], rax
0x180010a12  lea     rax, [rsp+140h+var_D0]
0x180010a17  mov     qword ptr [rsp+140h+AuthenticationInformationLength], rax
0x180010a1c  lea     rax, [rbp+40h+var_A8]
0x180010a20  jmp     loc_180010980
0x180010a25  mov     r9d, [rcx+44h]; AuthenticationPackage
0x180010a29  lea     rax, [rsp+140h+var_C8]
0x180010a2e  mov     rcx, [rcx+38h]; LsaHandle
0x180010a32  mov     [rsp+140h+SubStatus], rax; SubStatus
0x180010a37  lea     rax, [rbp+40h+var_60]
0x180010a3b  mov     [rsp+140h+Quotas], rax; Quotas
0x180010a40  lea     rax, [rbp+40h+var_78]
0x180010a44  mov     [rsp+140h+Token], rbx; Token
0x180010a49  mov     [rsp+140h+LogonId], rax; LogonId
0x180010a4e  lea     rax, [rbp+40h+var_A0]
0x180010a52  mov     [rsp+140h+ProfileBufferLength], rax; ProfileBufferLength
0x180010a57  lea     rax, [rbp+40h+Buffer]
0x180010a5b  mov     [rsp+140h+ProfileBuffer], rax; ProfileBuffer
0x180010a60  lea     rax, [rbp+40h+var_70]
0x180010a64  mov     [rsp+140h+SourceContext], rax; SourceContext
0x180010a69  mov     [rsp+140h+LocalGroups], 0; LocalGroups
0x180010a72  mov     [rsp+140h+AuthenticationInformationLength], r8d; AuthenticationInformationLength
0x180010a77  mov     r8d, 3; LogonType
0x180010a7d  mov     [rsp+140h+AuthenticationInformation], rdx; AuthenticationInformation
0x180010a82  lea     rdx, [rbp+40h+OriginName]; OriginName
0x180010a86  call    cs:__imp_LsaLogonUser
0x180010a8c  mov     ecx, eax
0x180010a8e  test    eax, eax
0x180010a90  jns     loc_180010B40
0x180010a96  cmp     eax, 0C000006Eh
0x180010a9b  jnz     short loc_180010AA5
0x180010a9d  mov     ebx, [rsp+140h+var_C8]
0x180010aa1  test    ebx, ebx
0x180010aa3  jnz     short loc_180010AA7
0x180010aa5  mov     ebx, ecx
0x180010aa7  mov     eax, cs:dword_18001F000
0x180010aad  bts     ebx, 1Ch
0x180010ab1  cmp     eax, 2
0x180010ab4  jbe     loc_180010BBF
0x180010aba  mov     eax, [rsp+140h+var_C8]
0x180010abe  lea     rdx, byte_18001A1D7
0x180010ac5  mov     [rsp+140h+var_CC], eax
0x180010ac9  lea     rax, aLogonuserw; "LogonUserW"
0x180010ad0  mov     [rbp+40h+var_B0], rax
0x180010ad4  lea     rax, aOnecoreTermsrv_0; "onecore\\termsrv\\rdp\\win\\security\\c"...
0x180010adb  mov     [rbp+40h+var_B8], rax
0x180010adf  lea     rax, aLsalogonuserFa; "LsaLogonUser failed."
0x180010ae6  mov     [rbp+40h+var_98], rax
0x180010aea  lea     rax, [rsp+140h+var_CC]
0x180010aef  mov     [rsp+140h+LogonId], rax
0x180010af4  lea     rax, [rsp+140h+var_D0]
0x180010af9  mov     [rsp+140h+ProfileBufferLength], rax
0x180010afe  lea     rax, [rbp+40h+var_B0]
0x180010b02  mov     [rsp+140h+ProfileBuffer], rax
0x180010b07  lea     rax, [rbp+40h+var_A8]
0x180010b0b  mov     [rsp+140h+SourceContext], rax
0x180010b10  lea     rax, [rbp+40h+var_B8]
0x180010b14  mov     [rsp+140h+LocalGroups], rax
0x180010b19  lea     rax, [rbp+40h+var_C0]
0x180010b1d  mov     qword ptr [rsp+140h+AuthenticationInformationLength], rax
0x180010b22  lea     rax, [rbp+40h+var_98]
0x180010b26  mov     [rsp+140h+AuthenticationInformation], rax
0x180010b2b  mov     [rsp+140h+var_D0], ecx
0x180010b2f  mov     dword ptr [rbp+40h+var_A8], 188h
0x180010b36  mov     dword ptr [rbp+40h+var_C0], ebx
0x180010b39  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@34344@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180010b3e  jmp     short loc_180010BBF
0x180010b40  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AuthenticationPackageUtilizationTelemetry@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AuthenticationPackageUtilizationTelemetry@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AuthenticationPackageUtilizationTelemetry> `wil::Feature<__WilFeatureTraits_Feature_AuthenticationPackageUtilizationTelemetry>::GetImpl(void)'::`2'::impl
0x180010b47  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AuthenticationPackageUtilizationTelemetry@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AuthenticationPackageUtilizationTelemetry>::__private_IsEnabled(void)
0x180010b4c  test    al, al
0x180010b4e  jz      short loc_180010BBD
0x180010b50  mov     rcx, [rbx]; TokenHandle
0x180010b53  call    ?TraceAuthenticationPackageInfo@SecUtils@@YAJPEAX@Z; SecUtils::TraceAuthenticationPackageInfo(void *)
0x180010b58  mov     ecx, eax
0x180010b5a  test    eax, eax
0x180010b5c  jns     short loc_180010BBD
0x180010b5e  mov     eax, cs:dword_18001F000
0x180010b64  cmp     eax, 3
0x180010b67  jbe     short loc_180010BBD
0x180010b69  lea     rax, aLogonuserw; "LogonUserW"
0x180010b70  mov     dword ptr [rbp+40h+var_C0], ecx
0x180010b73  mov     [rbp+40h+var_98], rax
0x180010b77  lea     rdx, qword_18001A230
0x180010b7e  lea     rax, aFailedToLogAut; "Failed to log authentication package in"...
0x180010b85  mov     [rbp+40h+var_B0], rax
0x180010b89  lea     rax, aHresultFailedB; "HResult failed but continue"
0x180010b90  mov     [rbp+40h+var_B8], rax
0x180010b94  lea     rax, [rbp+40h+var_98]
0x180010b98  mov     [rsp+140h+SourceContext], rax
0x180010b9d  lea     rax, [rbp+40h+var_C0]
0x180010ba1  mov     [rsp+140h+LocalGroups], rax
0x180010ba6  lea     rax, [rbp+40h+var_B0]
0x180010baa  mov     qword ptr [rsp+140h+AuthenticationInformationLength], rax
0x180010baf  lea     rax, [rbp+40h+var_B8]
0x180010bb3  mov     [rsp+140h+AuthenticationInformation], rax
0x180010bb8  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180010bbd  xor     ebx, ebx
0x180010bbf  test    rdi, rdi
0x180010bc2  jz      short loc_180010BCA
0x180010bc4  mov     ecx, [rsp+140h+var_C8]
0x180010bc8  mov     [rdi], ecx
0x180010bca  mov     rcx, [rbp+40h+Buffer]; Buffer
0x180010bce  test    rcx, rcx
0x180010bd1  jz      short loc_180010BD9
0x180010bd3  call    cs:__imp_LsaFreeReturnBuffer
0x180010bd9  mov     eax, ebx
0x180010bdb  mov     rcx, [rbp+40h+var_18]
0x180010bdf  xor     rcx, rsp; StackCookie
0x180010be2  call    __security_check_cookie
0x180010be7  add     rsp, 130h
0x180010bee  pop     rdi
0x180010bef  pop     rbx
0x180010bf0  pop     rbp
0x180010bf1  retn
```
