# CloudAPHelper::Initialize(_GUID const &)

- ea: `0x1800104b0`
- end: `0x180010841`
- name: `?Initialize@CloudAPHelper@@QEAAJAEBU_GUID@@@Z`
- size: `913`
- prototype: `int(CloudAPHelper *__hidden this, const struct _GUID *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000fce4`

## callees

- `0x1800013bc`
- `0x1800014c4`
- `0x1800104b0`
- `0x1800155c0`

## import_xrefs

- `SspiCli!LsaConnectUntrusted` at `0x180010693`
- `SspiCli!LsaConnectUntrusted` at `0x180010693`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x1800106dd`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x18001076c`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x1800106dd`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x18001076c`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180010569`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180010569`

## string_xrefs

- `0x1800105b9`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x1800107be`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x180010671`: `StringCchCopyN(m_wszCorrelationId) failed`

## pseudocode

```c
__int64 __fastcall CloudAPHelper::Initialize(CloudAPHelper *this, const struct _GUID *a2)
{
  int v3; // ecx
  int v4; // r8d
  int v5; // r9d
  unsigned int v6; // ebx
  __int64 v7; // rax
  OLECHAR *v8; // rcx
  _WORD *v9; // r8
  __int64 v10; // rdx
  _WORD *v11; // rcx
  const char *v12; // rax
  __int16 *v13; // rdx
  HANDLE *v14; // rdi
  NTSTATUS v15; // eax
  NTSTATUS v16; // eax
  int v17; // ecx
  int v18; // r8d
  int v19; // r9d
  NTSTATUS v20; // eax
  int v22; // [rsp+50h] [rbp-B0h] BYREF
  int v23; // [rsp+54h] [rbp-ACh] BYREF
  const char *v24; // [rsp+58h] [rbp-A8h] BYREF
  const char *v25; // [rsp+60h] [rbp-A0h] BYREF
  const char *v26; // [rsp+68h] [rbp-98h] BYREF
  const char *v27; // [rsp+70h] [rbp-90h] BYREF
  _LSA_STRING PackageName; // [rsp+78h] [rbp-88h] BYREF
  struct _LSA_STRING v29; // [rsp+88h] [rbp-78h] BYREF
  char v30[16]; // [rsp+98h] [rbp-68h] BYREF
  __int64 v31; // [rsp+A8h] [rbp-58h] BYREF
  OLECHAR sz[8]; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v33; // [rsp+C0h] [rbp-40h]
  __int128 v34; // [rsp+D0h] [rbp-30h]
  _OWORD v35[2]; // [rsp+E0h] [rbp-20h]

  *(_OWORD *)sz = *(_OWORD *)L"{00000000-0000-0000-0000-000000000000}";
  v31 = 0x504164756F6C43LL;
  v34 = *(_OWORD *)L"000-0000-000000000000}";
  PackageName.Buffer = (PCHAR)&v31;
  v33 = *(_OWORD *)L"0-0000-0000-0000-000000000000}";
  v35[0] = *(_OWORD *)L"-000000000000}";
  *(_OWORD *)((char *)v35 + 14) = *(_OWORD *)L"000000}";
  strcpy(v30, "Negotiate");
  *(_QWORD *)&PackageName.Length = 524295;
  *(_QWORD *)&v29.Length = 655369;
  v29.Buffer = v30;
  if ( !StringFromGUID2(a2, sz, 39) )
  {
    v6 = -2147467259;
    if ( (unsigned int)dword_18001F000 > 2 )
    {
      v23 = 109;
      v27 = "StringFromGUID2 failed";
      v22 = -2147467259;
      v24 = "Initialize";
      v25 = "onecore\\termsrv\\rdp\\win\\security\\cloudaphelper.cpp";
      v26 = "Error HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v3,
        (unsigned int)qword_18001ABF8,
        v4,
        v5,
        (__int64)&v26,
        (__int64)&v22,
        (__int64)&v25,
        (__int64)&v23,
        (__int64)&v24,
        (__int64)&v27);
    }
    return v6;
  }
  v7 = 36;
  v8 = &sz[1];
  v9 = (_WORD *)((char *)this + 72);
  v10 = 37;
  do
  {
    if ( !v7 )
      break;
    v5 = *v8;
    if ( !(_WORD)v5 )
      break;
    *v9 = v5;
    ++v8;
    ++v9;
    --v7;
    --v10;
  }
  while ( v10 );
  v11 = v9 - 1;
  v6 = v10 == 0 ? 0x8007007A : 0;
  if ( v10 )
    v11 = v9;
  *v11 = 0;
  if ( !v10 )
  {
    if ( (unsigned int)dword_18001F000 <= 2 )
      return v6;
    v12 = "StringCchCopyN(m_wszCorrelationId) failed";
    v22 = 116;
    v13 = word_18001ABAA;
    goto LABEL_25;
  }
  v14 = (HANDLE *)((char *)this + 56);
  v15 = LsaConnectUntrusted((PHANDLE)this + 7);
  if ( v15 )
  {
    v6 = v15 | 0x10000000;
    if ( v15 < 0 )
    {
      if ( (unsigned int)dword_18001F000 <= 2 )
        return v6;
      v12 = "LsaConnectUntrusted failed";
      v22 = 125;
      v13 = (__int16 *)&dword_18001AB5C;
      goto LABEL_25;
    }
  }
  v16 = LsaLookupAuthenticationPackage(*v14, &PackageName, (PULONG)this + 16);
  if ( !v16 || (v6 = v16 | 0x10000000, v16 >= 0) )
  {
    v20 = LsaLookupAuthenticationPackage(*v14, &v29, (PULONG)this + 17);
    if ( !v20 )
      return v6;
    v6 = v20 | 0x10000000;
    if ( v20 >= 0 || (unsigned int)dword_18001F000 <= 2 )
      return v6;
    v12 = "LsaLookupAuthenticationPackage(Negotiate) failed";
    v22 = 145;
    v13 = &word_18001AB0E;
LABEL_25:
    v26 = v12;
    v25 = "Initialize";
    v24 = "onecore\\termsrv\\rdp\\win\\security\\cloudaphelper.cpp";
    v27 = "Error HResult failed";
    v23 = v6;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      (_DWORD)v11,
      (_DWORD)v13,
      (_DWORD)v9,
      v5,
      (__int64)&v27,
      (__int64)&v23,
      (__int64)&v24,
      (__int64)&v22,
      (__int64)&v25,
      (__int64)&v26);
    return v6;
  }
  if ( (unsigned int)dword_18001F000 > 3 )
  {
    v22 = v16 | 0x10000000;
    v26 = "Initialize";
    v25 = "LsaLookupAuthenticationPackage(CloudAP) failed";
    v24 = "Warning HResult failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v17,
      (unsigned int)word_18001AAD2,
      v18,
      v19,
      (__int64)&v24,
      (__int64)&v25,
      (__int64)&v22,
      (__int64)&v26);
  }
  return v6;
}

```

## disassembly

```asm
0x1800104b0  mov     [rsp-8+arg_10], rbx
0x1800104b5  mov     [rsp-8+arg_18], rsi
0x1800104ba  push    rbp
0x1800104bb  push    rdi
0x1800104bc  push    r14
0x1800104be  lea     rbp, [rsp-10h]
0x1800104c3  sub     rsp, 110h
0x1800104ca  mov     rax, cs:__security_cookie
0x1800104d1  xor     rax, rsp
0x1800104d4  mov     [rbp+20h+var_20], rax
0x1800104d8  movaps  xmm0, xmmword ptr cs:a00000000000000; "{00000000-0000-0000-0000-000000000000}"
0x1800104df  mov     r9, rdx
0x1800104e2  movaps  xmm1, xmmword ptr cs:a00000000000000+10h; "0-0000-0000-0000-000000000000}"
0x1800104e9  lea     rdx, [rbp+20h+sz]; lpsz
0x1800104ed  movaps  xmmword ptr [rbp+20h+sz], xmm0
0x1800104f1  mov     rax, 504164756F6C43h
0x1800104fb  movaps  xmm0, xmmword ptr cs:a00000000000000+20h; "000-0000-000000000000}"
0x180010502  mov     rsi, rcx
0x180010505  mov     [rbp+20h+var_78], rax
0x180010509  mov     r8d, 27h ; '''; cchMax
0x18001050f  movaps  [rbp+20h+var_50], xmm0
0x180010513  lea     rax, [rbp+20h+var_78]
0x180010517  movups  xmm0, xmmword ptr cs:a00000000000000+3Eh; "000000}"
0x18001051e  mov     [rbp+20h+PackageName.Buffer], rax
0x180010522  mov     rcx, r9; rguid
0x180010525  movzx   eax, word ptr cs:aNegotiate+8; "e"
0x18001052c  movaps  [rbp+20h+var_60], xmm1
0x180010530  movaps  xmm1, xmmword ptr cs:a00000000000000+30h; "-000000000000}"
0x180010537  movaps  xmmword ptr [rbp+20h+var_40], xmm1
0x18001053b  movups  xmmword ptr [rbp+20h+var_40+0Eh], xmm0
0x18001053f  mov     word ptr [rbp+20h+var_88+8], ax
0x180010543  lea     rax, [rbp+20h+var_88]
0x180010547  movsd   xmm0, qword ptr cs:aNegotiate; "Negotiate"
0x18001054f  movsd   qword ptr [rbp+20h+var_88], xmm0
0x180010554  mov     qword ptr [rsp+120h+PackageName.Length], 80007h
0x18001055d  mov     qword ptr [rbp+20h+var_98.Length], 0A0009h
0x180010565  mov     [rbp+20h+var_98.Buffer], rax
0x180010569  call    cs:__imp_StringFromGUID2
0x18001056f  xor     r14d, r14d
0x180010572  test    eax, eax
0x180010574  jnz     loc_18001060D
0x18001057a  mov     eax, cs:dword_18001F000
0x180010580  mov     ebx, 80004005h
0x180010585  cmp     eax, 2
0x180010588  jbe     loc_18001081B
0x18001058e  lea     rax, aStringfromguid; "StringFromGUID2 failed"
0x180010595  mov     [rsp+120h+var_CC], 6Dh ; 'm'
0x18001059d  mov     [rsp+120h+var_B0], rax
0x1800105a2  lea     rdx, qword_18001ABF8
0x1800105a9  lea     rax, aInitialize; "Initialize"
0x1800105b0  mov     [rsp+120h+var_D0], ebx
0x1800105b4  mov     [rsp+120h+var_C8], rax
0x1800105b9  lea     rax, aOnecoreTermsrv_0; "onecore\\termsrv\\rdp\\win\\security\\c"...
0x1800105c0  mov     [rsp+120h+var_C0], rax
0x1800105c5  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800105cc  mov     [rsp+120h+var_B8], rax
0x1800105d1  lea     rax, [rsp+120h+var_B0]
0x1800105d6  mov     [rsp+120h+var_D8], rax
0x1800105db  lea     rax, [rsp+120h+var_C8]
0x1800105e0  mov     [rsp+120h+var_E0], rax
0x1800105e5  lea     rax, [rsp+120h+var_CC]
0x1800105ea  mov     [rsp+120h+var_E8], rax
0x1800105ef  lea     rax, [rsp+120h+var_C0]
0x1800105f4  mov     [rsp+120h+var_F0], rax
0x1800105f9  lea     rax, [rsp+120h+var_D0]
0x1800105fe  mov     [rsp+120h+var_F8], rax
0x180010603  lea     rax, [rsp+120h+var_B8]
0x180010608  jmp     loc_180010811
0x18001060d  mov     eax, 24h ; '$'
0x180010612  lea     rcx, [rbp+20h+sz+2]
0x180010616  lea     r8, [rsi+48h]
0x18001061a  lea     edx, [rax+1]
0x18001061d  test    rax, rax
0x180010620  jz      short loc_180010641
0x180010622  movzx   r9d, word ptr [rcx]
0x180010626  test    r9w, r9w
0x18001062a  jz      short loc_180010641
0x18001062c  mov     [r8], r9w
0x180010630  add     rcx, 2
0x180010634  add     r8, 2
0x180010638  dec     rax
0x18001063b  sub     rdx, 1
0x18001063f  jnz     short loc_18001061D
0x180010641  mov     rax, rdx
0x180010644  lea     rcx, [r8-2]
0x180010648  neg     rax
0x18001064b  sbb     ebx, ebx
0x18001064d  not     ebx
0x18001064f  and     ebx, 8007007Ah
0x180010655  test    rdx, rdx
0x180010658  cmovnz  rcx, r8
0x18001065c  mov     [rcx], r14w
0x180010660  jnz     short loc_18001068C
0x180010662  mov     eax, cs:dword_18001F000
0x180010668  cmp     eax, 2
0x18001066b  jbe     loc_18001081B
0x180010671  lea     rax, aStringcchcopyn; "StringCchCopyN(m_wszCorrelationId) fail"...
0x180010678  mov     [rsp+120h+var_D0], 74h ; 't'
0x180010680  lea     rdx, word_18001ABAA
0x180010687  jmp     loc_1800107AD
0x18001068c  lea     rdi, [rsi+38h]
0x180010690  mov     rcx, rdi; LsaHandle
0x180010693  call    cs:__imp_LsaConnectUntrusted
0x180010699  test    eax, eax
0x18001069b  jz      short loc_1800106D1
0x18001069d  mov     ebx, eax
0x18001069f  or      ebx, 10000000h
0x1800106a5  jge     short loc_1800106D1
0x1800106a7  mov     eax, cs:dword_18001F000
0x1800106ad  cmp     eax, 2
0x1800106b0  jbe     loc_18001081B
0x1800106b6  lea     rax, aLsaconnectuntr; "LsaConnectUntrusted failed"
0x1800106bd  mov     [rsp+120h+var_D0], 7Dh ; '}'
0x1800106c5  lea     rdx, dword_18001AB5C
0x1800106cc  jmp     loc_1800107AD
0x1800106d1  mov     rcx, [rdi]; LsaHandle
0x1800106d4  lea     r8, [rsi+40h]; AuthenticationPackage
0x1800106d8  lea     rdx, [rsp+120h+PackageName]; PackageName
0x1800106dd  call    cs:__imp_LsaLookupAuthenticationPackage
0x1800106e3  test    eax, eax
0x1800106e5  jz      short loc_180010761
0x1800106e7  mov     ebx, eax
0x1800106e9  or      ebx, 10000000h
0x1800106ef  jge     short loc_180010761
0x1800106f1  mov     eax, cs:dword_18001F000
0x1800106f7  cmp     eax, 3
0x1800106fa  jbe     loc_18001081B
0x180010700  lea     rax, aInitialize; "Initialize"
0x180010707  mov     [rsp+120h+var_D0], ebx
0x18001070b  mov     [rsp+120h+var_B8], rax
0x180010710  lea     rdx, word_18001AAD2
0x180010717  lea     rax, aLsalookupauthe_0; "LsaLookupAuthenticationPackage(CloudAP)"...
0x18001071e  mov     [rsp+120h+var_C0], rax
0x180010723  lea     rax, aWarningHresult; "Warning HResult failed"
0x18001072a  mov     [rsp+120h+var_C8], rax
0x18001072f  lea     rax, [rsp+120h+var_B8]
0x180010734  mov     [rsp+120h+var_E8], rax
0x180010739  lea     rax, [rsp+120h+var_D0]
0x18001073e  mov     [rsp+120h+var_F0], rax
0x180010743  lea     rax, [rsp+120h+var_C0]
0x180010748  mov     [rsp+120h+var_F8], rax
0x18001074d  lea     rax, [rsp+120h+var_C8]
0x180010752  mov     [rsp+120h+var_100], rax
0x180010757  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18001075c  jmp     loc_18001081B
0x180010761  mov     rcx, [rdi]; LsaHandle
0x180010764  lea     r8, [rsi+44h]; AuthenticationPackage
0x180010768  lea     rdx, [rbp+20h+var_98]; PackageName
0x18001076c  call    cs:__imp_LsaLookupAuthenticationPackage
0x180010772  test    eax, eax
0x180010774  jz      loc_18001081B
0x18001077a  mov     ebx, eax
0x18001077c  or      ebx, 10000000h
0x180010782  jge     loc_18001081B
0x180010788  mov     eax, cs:dword_18001F000
0x18001078e  cmp     eax, 2
0x180010791  jbe     loc_18001081B
0x180010797  lea     rax, aLsalookupauthe; "LsaLookupAuthenticationPackage(Negotiat"...
0x18001079e  mov     [rsp+120h+var_D0], 91h
0x1800107a6  lea     rdx, word_18001AB0E
0x1800107ad  mov     [rsp+120h+var_B8], rax
0x1800107b2  lea     rax, aInitialize; "Initialize"
0x1800107b9  mov     [rsp+120h+var_C0], rax
0x1800107be  lea     rax, aOnecoreTermsrv_0; "onecore\\termsrv\\rdp\\win\\security\\c"...
0x1800107c5  mov     [rsp+120h+var_C8], rax
0x1800107ca  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800107d1  mov     [rsp+120h+var_B0], rax
0x1800107d6  lea     rax, [rsp+120h+var_B8]
0x1800107db  mov     [rsp+120h+var_D8], rax
0x1800107e0  lea     rax, [rsp+120h+var_C0]
0x1800107e5  mov     [rsp+120h+var_E0], rax
0x1800107ea  lea     rax, [rsp+120h+var_D0]
0x1800107ef  mov     [rsp+120h+var_E8], rax
0x1800107f4  lea     rax, [rsp+120h+var_C8]
0x1800107f9  mov     [rsp+120h+var_F0], rax
0x1800107fe  lea     rax, [rsp+120h+var_CC]
0x180010803  mov     [rsp+120h+var_F8], rax
0x180010808  lea     rax, [rsp+120h+var_B0]
0x18001080d  mov     [rsp+120h+var_CC], ebx
0x180010811  mov     [rsp+120h+var_100], rax
0x180010816  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18001081b  mov     eax, ebx
0x18001081d  mov     rcx, [rbp+20h+var_20]
0x180010821  xor     rcx, rsp; StackCookie
0x180010824  call    __security_check_cookie
0x180010829  lea     r11, [rsp+120h+var_10]
0x180010831  mov     rbx, [r11+30h]
0x180010835  mov     rsi, [r11+38h]
0x180010839  mov     rsp, r11
0x18001083c  pop     r14
0x18001083e  pop     rdi
0x18001083f  pop     rbp
0x180010840  retn
```
