# CRemoteTerminal::GetClientTimeZone(IUserName *,_TS_DYNAMIC_TIME_ZONE_INFORMATION *)

- ea: `0x180053cb0`
- end: `0x1800541fb`
- name: `?GetClientTimeZone@CRemoteTerminal@@UEAAJPEAUIUserName@@PEAU_TS_DYNAMIC_TIME_ZONE_INFORMATION@@@Z`
- size: `1355`
- prototype: `__int64 __fastcall(CRemoteTerminal *__hidden this, struct IUserName *, struct _TS_DYNAMIC_TIME_ZONE_INFORMATION *)`
- caller_count: `0`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180001294`
- `0x180009940`
- `0x18000f0d0`
- `0x180012750`
- `0x180012870`
- `0x180015310`
- `0x180018394`
- `0x180033f60`
- `0x18003440c`
- `0x180034470`
- `0x180034e64`
- `0x180053cb0`
- `0x180054310`
- `0x1800bf598`
- `0x1800caed0`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053e99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053e99`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180053ed2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800541a5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180053ed2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800541a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800541ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800541ba`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180053e70`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180053e70`
- `REGAPI!RegIsTimeZoneRedirectionEnabled` at `0x180053eea`
- `REGAPI!RegIsTimeZoneRedirectionEnabled` at `0x180053eea`

## string_xrefs

- `0x180053eb8`: `Failed in getting user string sid (0x%x), process machine GP only`
- `0x18005417e`: `Impersonate.StopImpersonating failed: 0x%x in %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CRemoteTerminal::GetClientTimeZone(
        CRemoteTerminal *this,
        struct IUserName *a2,
        struct _TS_DYNAMIC_TIME_ZONE_INFORMATION *a3)
{
  int ConnectionProperty; // edi
  int LicenseType; // eax
  int v8; // ecx
  int v9; // r8d
  int v10; // r9d
  __int64 *v11; // rax
  __int64 v12; // rcx
  bool v13; // r15
  signed int LastError; // eax
  bool v15; // sf
  int v16; // ecx
  int v17; // r8d
  int v18; // r9d
  void *v19; // rax
  void *v20; // rsi
  int v21; // r8d
  int v22; // r9d
  __int64 v23; // rcx
  __int64 *v24; // rax
  __int64 v25; // rcx
  int v26; // eax
  _WORD v28[2]; // [rsp+30h] [rbp-39h] BYREF
  unsigned int Size[3]; // [rsp+34h] [rbp-35h] BYREF
  LPWSTR StringSid; // [rsp+40h] [rbp-29h] BYREF
  PSID Sid; // [rsp+48h] [rbp-21h] BYREF
  struct _GUID Buf2; // [rsp+50h] [rbp-19h] BYREF
  _BYTE v33[16]; // [rsp+60h] [rbp-9h] BYREF
  struct _GUID v34; // [rsp+70h] [rbp+7h] BYREF

  v34 = 0;
  Sid = 0;
  StringSid = 0;
  v28[0] = 0;
  CAutoSharedLock::CAutoSharedLock((CAutoSharedLock *)v33, (CRemoteTerminal *)((char *)this + 5112));
  if ( !a3 )
  {
    _DbgPrintMessage(8, "Missing paramter %s in %s", "pTimeZone", "CRemoteTerminal::GetClientTimeZone");
    ConnectionProperty = -2147024809;
    goto LABEL_47;
  }
  LicenseType = CRemoteTerminal::GetLicenseType(this, &v34);
  ConnectionProperty = LicenseType;
  if ( LicenseType < 0 )
  {
    _DbgPrintMessage(8, "this->GetLicenseType failed: 0x%x in %s", LicenseType, "CRemoteTerminal::GetClientTimeZone");
    goto LABEL_47;
  }
  Buf2 = v34;
  if ( memcmp_0(&LICENSE_TYPE_APPSERVER, &Buf2, 0x10u) && !CUtils::bIsClientSKU )
  {
    if ( (unsigned int)dword_18012E170 > 4 )
    {
      *(_QWORD *)&Size[1] = "Not using timezone redirection because this is not an AppServer session.";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v8,
        (unsigned int)&word_18010E37E,
        v9,
        v10,
        (__int64)&Size[1]);
    }
    v11 = TS_INVALID_DTZ;
    v12 = 3;
    do
    {
      *(_OWORD *)a3 = *(_OWORD *)v11;
      *((_OWORD *)a3 + 1) = *((_OWORD *)v11 + 1);
      *((_OWORD *)a3 + 2) = *((_OWORD *)v11 + 2);
      *((_OWORD *)a3 + 3) = *((_OWORD *)v11 + 3);
      *((_OWORD *)a3 + 4) = *((_OWORD *)v11 + 4);
      *((_OWORD *)a3 + 5) = *((_OWORD *)v11 + 5);
      *((_OWORD *)a3 + 6) = *((_OWORD *)v11 + 6);
      *((_OWORD *)a3 + 7) = *((_OWORD *)v11 + 7);
      a3 = (struct _TS_DYNAMIC_TIME_ZONE_INFORMATION *)((char *)a3 + 128);
      v11 += 16;
      --v12;
    }
    while ( v12 );
    *(_OWORD *)a3 = *(_OWORD *)v11;
    *((_OWORD *)a3 + 1) = *((_OWORD *)v11 + 1);
    *((_OWORD *)a3 + 2) = *((_OWORD *)v11 + 2);
    ConnectionProperty = 0;
    goto LABEL_47;
  }
  v13 = 0;
  if ( a2 )
  {
    LastError = (*(__int64 (__fastcall **)(struct IUserName *, PSID *))(*(_QWORD *)a2 + 72LL))(a2, &Sid);
    if ( LastError < 0 )
    {
LABEL_20:
      _DbgPrintMessage(4, "Failed in getting user string sid (0x%x), process machine GP only", LastError);
      if ( StringSid )
        LocalFree(StringSid);
      StringSid = 0;
      goto LABEL_23;
    }
    if ( ConvertSidToStringSidW(Sid, &StringSid) )
    {
      LastError = CImpersonate::ImpersonateUser((CImpersonate *)v28, a2);
      v13 = LastError >= 0;
    }
    else
    {
      LastError = GetLastError();
      v15 = LastError < 0;
      if ( LastError <= 0 )
        goto LABEL_19;
      LastError = (unsigned __int16)LastError | 0x80070000;
    }
    v15 = LastError < 0;
LABEL_19:
    if ( !v15 )
      goto LABEL_23;
    goto LABEL_20;
  }
LABEL_23:
  if ( (unsigned __int8)RegIsTimeZoneRedirectionEnabled() )
  {
    if ( (unsigned int)dword_18012E170 > 4 )
    {
      *(_QWORD *)&Size[1] = "Timezone redirection is enabled";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v16,
        (unsigned int)byte_18010E35D,
        v17,
        v18,
        (__int64)&Size[1]);
    }
    Size[0] = 456;
    v19 = operator new[](0x1C8u, (const struct std::nothrow_t *)std::nothrow);
    v20 = v19;
    if ( !v19 )
    {
      ConnectionProperty = -2147024882;
      goto LABEL_47;
    }
    memset_0(v19, 0, Size[0]);
    ConnectionProperty = CRemoteTerminal::GetConnectionProperty(
                           this,
                           &PROPERTY_DYNAMIC_TIME_ZONE_INFORMATION,
                           Size,
                           (struct __PROPERTY_VALUE *)v20);
    v23 = 3;
    if ( ConnectionProperty < 0
      || *(_WORD *)v20 != 3
      || *((_DWORD *)v20 + 2) < 0x1B0u
      || (v24 = (__int64 *)*((_QWORD *)v20 + 2)) == 0 )
    {
      if ( (unsigned int)dword_18012E170 > 3 )
      {
        Size[1] = ConnectionProperty;
        *(_QWORD *)&Buf2.Data1 = "Unable to get dynamic time zone information. Falling back to legacy time zone.";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          3,
          (unsigned int)&byte_18010E337,
          v21,
          v22,
          (__int64)&Buf2,
          (__int64)&Size[1]);
      }
      *(_OWORD *)a3 = *((_OWORD *)this + 304);
      *((_OWORD *)a3 + 1) = *((_OWORD *)this + 305);
      *((_OWORD *)a3 + 2) = *((_OWORD *)this + 306);
      *((_OWORD *)a3 + 3) = *((_OWORD *)this + 307);
      *((_OWORD *)a3 + 4) = *((_OWORD *)this + 308);
      *((_OWORD *)a3 + 5) = *((_OWORD *)this + 309);
      *((_OWORD *)a3 + 6) = *((_OWORD *)this + 310);
      *((_OWORD *)a3 + 7) = *((_OWORD *)this + 311);
      *((_OWORD *)a3 + 8) = *((_OWORD *)this + 312);
      *((_OWORD *)a3 + 9) = *((_OWORD *)this + 313);
      *(_OWORD *)((char *)a3 + 156) = *(_OWORD *)((char *)this + 5020);
      memset_0((char *)a3 + 172, 0, 0x100u);
      *((_WORD *)a3 + 214) = 1;
      ConnectionProperty = 0;
      goto LABEL_42;
    }
    do
    {
      *(_OWORD *)a3 = *(_OWORD *)v24;
      *((_OWORD *)a3 + 1) = *((_OWORD *)v24 + 1);
      *((_OWORD *)a3 + 2) = *((_OWORD *)v24 + 2);
      *((_OWORD *)a3 + 3) = *((_OWORD *)v24 + 3);
      *((_OWORD *)a3 + 4) = *((_OWORD *)v24 + 4);
      *((_OWORD *)a3 + 5) = *((_OWORD *)v24 + 5);
      *((_OWORD *)a3 + 6) = *((_OWORD *)v24 + 6);
      *((_OWORD *)a3 + 7) = *((_OWORD *)v24 + 7);
      a3 = (struct _TS_DYNAMIC_TIME_ZONE_INFORMATION *)((char *)a3 + 128);
      v24 += 16;
      --v23;
    }
    while ( v23 );
  }
  else
  {
    v20 = 0;
    if ( (unsigned int)dword_18012E170 > 4 )
    {
      *(_QWORD *)&Buf2.Data1 = "Timezone redirection is disabled";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v16,
        (unsigned int)&word_18010E316,
        v17,
        v18,
        (__int64)&Buf2);
    }
    v24 = TS_INVALID_DTZ;
    v25 = 3;
    do
    {
      *(_OWORD *)a3 = *(_OWORD *)v24;
      *((_OWORD *)a3 + 1) = *((_OWORD *)v24 + 1);
      *((_OWORD *)a3 + 2) = *((_OWORD *)v24 + 2);
      *((_OWORD *)a3 + 3) = *((_OWORD *)v24 + 3);
      *((_OWORD *)a3 + 4) = *((_OWORD *)v24 + 4);
      *((_OWORD *)a3 + 5) = *((_OWORD *)v24 + 5);
      *((_OWORD *)a3 + 6) = *((_OWORD *)v24 + 6);
      *((_OWORD *)a3 + 7) = *((_OWORD *)v24 + 7);
      a3 = (struct _TS_DYNAMIC_TIME_ZONE_INFORMATION *)((char *)a3 + 128);
      v24 += 16;
      --v25;
    }
    while ( v25 );
  }
  *(_OWORD *)a3 = *(_OWORD *)v24;
  *((_OWORD *)a3 + 1) = *((_OWORD *)v24 + 1);
  *((_OWORD *)a3 + 2) = *((_OWORD *)v24 + 2);
LABEL_42:
  if ( v13 )
  {
    v26 = CImpersonate::StopImpersonating((CImpersonate *)v28);
    ConnectionProperty = v26;
    if ( v26 < 0 )
      _DbgPrintMessage(8, "Impersonate.StopImpersonating failed: 0x%x in %s", v26, "CRemoteTerminal::GetClientTimeZone");
  }
  if ( v20 )
    operator delete(v20);
LABEL_47:
  if ( StringSid )
    LocalFree(StringSid);
  if ( Sid )
    CoTaskMemFree(Sid);
  CAutoLock::Unlock((CAutoLock *)v33);
  CImpersonate::StopImpersonating((CImpersonate *)v28);
  return (unsigned int)ConnectionProperty;
}

```

## disassembly

```asm
0x180053cb0  push    rbp
0x180053cb2  push    rbx
0x180053cb3  push    rsi
0x180053cb4  push    rdi
0x180053cb5  push    r13
0x180053cb7  push    r14
0x180053cb9  push    r15
0x180053cbb  lea     rbp, [rsp-27h]
0x180053cc0  sub     rsp, 90h
0x180053cc7  mov     rax, cs:__security_cookie
0x180053cce  xor     rax, rsp
0x180053cd1  mov     [rbp+57h+var_40], rax
0x180053cd5  mov     rbx, r8
0x180053cd8  mov     rsi, rdx
0x180053cdb  mov     r14, rcx
0x180053cde  xorps   xmm0, xmm0
0x180053ce1  movups  xmmword ptr [rbp+57h+var_50.Data1], xmm0
0x180053ce5  mov     [rbp+57h+Sid], 0
0x180053ced  mov     [rbp+57h+StringSid], 0
0x180053cf5  mov     [rbp+57h+var_90], 0
0x180053cfb  lea     rdx, [rcx+13F8h]; struct CResource *
0x180053d02  lea     rcx, [rbp+57h+var_60]; this
0x180053d06  call    ??0CAutoSharedLock@@QEAA@AEAVCResource@@@Z; CAutoSharedLock::CAutoSharedLock(CResource &)
0x180053d0b  nop
0x180053d0c  test    rbx, rbx
0x180053d0f  jnz     short loc_180053D38
0x180053d11  lea     r9, aCremotetermina_16; "CRemoteTerminal::GetClientTimeZone"
0x180053d18  lea     r8, aPtimezone; "pTimeZone"
0x180053d1f  lea     rdx, aMissingParamte; "Missing paramter %s in %s"
0x180053d26  lea     ecx, [rbx+8]; int
0x180053d29  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180053d2e  mov     edi, 80070057h
0x180053d33  jmp     loc_18005419C
0x180053d38  lea     rdx, [rbp+57h+var_50]; struct _GUID *
0x180053d3c  mov     rcx, r14; this
0x180053d3f  call    ?GetLicenseType@CRemoteTerminal@@UEAAJPEAU_GUID@@@Z; CRemoteTerminal::GetLicenseType(_GUID *)
0x180053d44  mov     edi, eax
0x180053d46  test    eax, eax
0x180053d48  jns     short loc_180053D6A
0x180053d4a  lea     r9, aCremotetermina_16; "CRemoteTerminal::GetClientTimeZone"
0x180053d51  mov     r8d, eax
0x180053d54  lea     rdx, aThisGetlicense; "this->GetLicenseType failed: 0x%x in %s"
0x180053d5b  mov     ecx, 8; int
0x180053d60  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180053d65  jmp     loc_18005419C
0x180053d6a  movaps  xmm0, xmmword ptr [rbp+57h+var_50.Data1]
0x180053d6e  movdqa  [rbp+57h+Buf2], xmm0
0x180053d73  mov     r8d, 10h; Size
0x180053d79  lea     rdx, [rbp+57h+Buf2]; Buf2
0x180053d7d  lea     rcx, LICENSE_TYPE_APPSERVER; Buf1
0x180053d84  call    memcmp_0
0x180053d89  test    eax, eax
0x180053d8b  jz      loc_180053E3F
0x180053d91  cmp     cs:?bIsClientSKU@CUtils@@0HA, 0; int CUtils::bIsClientSKU
0x180053d98  jnz     loc_180053E3F
0x180053d9e  mov     eax, cs:dword_18012E170
0x180053da4  cmp     eax, 4
0x180053da7  jbe     short loc_180053DC9
0x180053da9  lea     rax, aNotUsingTimezo; "Not using timezone redirection because "...
0x180053db0  mov     qword ptr [rbp+57h+Size+4], rax
0x180053db4  lea     rax, [rbp+57h+Size+4]
0x180053db8  mov     [rsp+0C0h+var_A0], rax
0x180053dbd  lea     rdx, word_18010E37E
0x180053dc4  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180053dc9  lea     rax, TS_INVALID_DTZ
0x180053dd0  mov     ecx, 3
0x180053dd5  lea     edx, [rcx+7Dh]
0x180053dd8  movups  xmm0, xmmword ptr [rax]
0x180053ddb  movups  xmmword ptr [rbx], xmm0
0x180053dde  movups  xmm1, xmmword ptr [rax+10h]
0x180053de2  movups  xmmword ptr [rbx+10h], xmm1
0x180053de6  movups  xmm0, xmmword ptr [rax+20h]
0x180053dea  movups  xmmword ptr [rbx+20h], xmm0
0x180053dee  movups  xmm1, xmmword ptr [rax+30h]
0x180053df2  movups  xmmword ptr [rbx+30h], xmm1
0x180053df6  movups  xmm0, xmmword ptr [rax+40h]
0x180053dfa  movups  xmmword ptr [rbx+40h], xmm0
0x180053dfe  movups  xmm1, xmmword ptr [rax+50h]
0x180053e02  movups  xmmword ptr [rbx+50h], xmm1
0x180053e06  movups  xmm0, xmmword ptr [rax+60h]
0x180053e0a  movups  xmmword ptr [rbx+60h], xmm0
0x180053e0e  movups  xmm1, xmmword ptr [rax+70h]
0x180053e12  movups  xmmword ptr [rbx+70h], xmm1
0x180053e16  add     rbx, rdx
0x180053e19  add     rax, rdx
0x180053e1c  sub     rcx, 1
0x180053e20  jnz     short loc_180053DD8
0x180053e22  movups  xmm0, xmmword ptr [rax]
0x180053e25  movups  xmmword ptr [rbx], xmm0
0x180053e28  movups  xmm1, xmmword ptr [rax+10h]
0x180053e2c  movups  xmmword ptr [rbx+10h], xmm1
0x180053e30  movups  xmm0, xmmword ptr [rax+20h]
0x180053e34  movups  xmmword ptr [rbx+20h], xmm0
0x180053e38  xor     edi, edi
0x180053e3a  jmp     loc_18005419C
0x180053e3f  xor     r15b, r15b
0x180053e42  mov     r13d, 1
0x180053e48  test    rsi, rsi
0x180053e4b  jz      loc_180053EE6
0x180053e51  mov     rax, [rsi]
0x180053e54  lea     rdx, [rbp+57h+Sid]
0x180053e58  mov     rcx, rsi
0x180053e5b  mov     rax, [rax+48h]
0x180053e5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053e64  test    eax, eax
0x180053e66  js      short loc_180053EB5
0x180053e68  lea     rdx, [rbp+57h+StringSid]; StringSid
0x180053e6c  mov     rcx, [rbp+57h+Sid]; Sid
0x180053e70  call    cs:__imp_ConvertSidToStringSidW
0x180053e77  nop     dword ptr [rax+rax+00h]
0x180053e7c  cmp     eax, r13d
0x180053e7f  jnz     short loc_180053E99
0x180053e81  mov     rdx, rsi; struct IUserName *
0x180053e84  lea     rcx, [rbp+57h+var_90]; this
0x180053e88  call    ?ImpersonateUser@CImpersonate@@QEAAJPEAUIUserName@@@Z; CImpersonate::ImpersonateUser(IUserName *)
0x180053e8d  mov     r15d, eax
0x180053e90  shr     r15d, 1Fh
0x180053e94  xor     r15b, r13b
0x180053e97  jmp     short loc_180053EB1
0x180053e99  call    cs:__imp_GetLastError
0x180053ea0  nop     dword ptr [rax+rax+00h]
0x180053ea5  test    eax, eax
0x180053ea7  jle     short loc_180053EB3
0x180053ea9  movzx   eax, ax
0x180053eac  or      eax, 80070000h
0x180053eb1  test    eax, eax
0x180053eb3  jns     short loc_180053EE6
0x180053eb5  mov     r8d, eax
0x180053eb8  lea     rdx, aFailedInGettin; "Failed in getting user string sid (0x%x"...
0x180053ebf  mov     ecx, 4; int
0x180053ec4  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180053ec9  mov     rcx, [rbp+57h+StringSid]; hMem
0x180053ecd  test    rcx, rcx
0x180053ed0  jz      short loc_180053EDE
0x180053ed2  call    cs:__imp_LocalFree
0x180053ed9  nop     dword ptr [rax+rax+00h]
0x180053ede  xor     ecx, ecx
0x180053ee0  mov     [rbp+57h+StringSid], rcx
0x180053ee4  jmp     short loc_180053EEA
0x180053ee6  mov     rcx, [rbp+57h+StringSid]
0x180053eea  call    cs:__imp_RegIsTimeZoneRedirectionEnabled
0x180053ef1  nop     dword ptr [rax+rax+00h]
0x180053ef6  test    al, al
0x180053ef8  mov     eax, cs:dword_18012E170
0x180053efe  jz      loc_1800540CB
0x180053f04  cmp     eax, 4
0x180053f07  jbe     short loc_180053F29
0x180053f09  lea     rax, aTimezoneRedire; "Timezone redirection is enabled"
0x180053f10  mov     qword ptr [rbp+57h+Size+4], rax
0x180053f14  lea     rax, [rbp+57h+Size+4]
0x180053f18  mov     [rsp+0C0h+var_A0], rax
0x180053f1d  lea     rdx, byte_18010E35D
0x180053f24  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180053f29  mov     ecx, 1C8h; unsigned __int64
0x180053f2e  mov     dword ptr [rbp+57h+Size], ecx
0x180053f31  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180053f38  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180053f3d  mov     rsi, rax
0x180053f40  test    rax, rax
0x180053f43  jnz     short loc_180053F4F
0x180053f45  mov     edi, 8007000Eh
0x180053f4a  jmp     loc_18005419C
0x180053f4f  mov     r8d, dword ptr [rbp+57h+Size]; Size
0x180053f53  xor     edx, edx; Val
0x180053f55  mov     rcx, rsi; void *
0x180053f58  call    memset_0
0x180053f5d  mov     r9, rsi; struct __PROPERTY_VALUE *
0x180053f60  lea     r8, [rbp+57h+Size]; unsigned int *
0x180053f64  lea     rdx, PROPERTY_DYNAMIC_TIME_ZONE_INFORMATION; struct _GUID *
0x180053f6b  mov     rcx, r14; this
0x180053f6e  call    ?GetConnectionProperty@CRemoteTerminal@@UEAAJAEBU_GUID@@PEAKPEAU__PROPERTY_VALUE@@@Z; CRemoteTerminal::GetConnectionProperty(_GUID const &,ulong *,__PROPERTY_VALUE *)
0x180053f73  mov     edi, eax
0x180053f75  mov     ecx, 3
0x180053f7a  test    eax, eax
0x180053f7c  js      short loc_180053FE6
0x180053f7e  cmp     [rsi], cx
0x180053f81  jnz     short loc_180053FE6
0x180053f83  cmp     dword ptr [rsi+8], 1B0h
0x180053f8a  jb      short loc_180053FE6
0x180053f8c  mov     rax, [rsi+10h]
0x180053f90  test    rax, rax
0x180053f93  jz      short loc_180053FE6
0x180053f95  lea     edx, [rcx+7Dh]
0x180053f98  movups  xmm0, xmmword ptr [rax]
0x180053f9b  movups  xmmword ptr [rbx], xmm0
0x180053f9e  movups  xmm1, xmmword ptr [rax+10h]
0x180053fa2  movups  xmmword ptr [rbx+10h], xmm1
0x180053fa6  movups  xmm0, xmmword ptr [rax+20h]
0x180053faa  movups  xmmword ptr [rbx+20h], xmm0
0x180053fae  movups  xmm1, xmmword ptr [rax+30h]
0x180053fb2  movups  xmmword ptr [rbx+30h], xmm1
0x180053fb6  movups  xmm0, xmmword ptr [rax+40h]
0x180053fba  movups  xmmword ptr [rbx+40h], xmm0
0x180053fbe  movups  xmm1, xmmword ptr [rax+50h]
0x180053fc2  movups  xmmword ptr [rbx+50h], xmm1
0x180053fc6  movups  xmm0, xmmword ptr [rax+60h]
0x180053fca  movups  xmmword ptr [rbx+60h], xmm0
0x180053fce  movups  xmm1, xmmword ptr [rax+70h]
0x180053fd2  movups  xmmword ptr [rbx+70h], xmm1
0x180053fd6  add     rbx, rdx
0x180053fd9  add     rax, rdx
0x180053fdc  sub     rcx, r13
0x180053fdf  jnz     short loc_180053F98
0x180053fe1  jmp     loc_18005414A
0x180053fe6  mov     eax, cs:dword_18012E170
0x180053fec  cmp     eax, ecx
0x180053fee  jbe     short loc_18005401C
0x180053ff0  mov     dword ptr [rbp+57h+Size+4], edi
0x180053ff3  lea     rax, aUnableToGetDyn; "Unable to get dynamic time zone informa"...
0x180053ffa  mov     qword ptr [rbp+57h+Buf2], rax
0x180053ffe  lea     rax, [rbp+57h+Size+4]
0x180054002  mov     [rsp+0C0h+var_98], rax
0x180054007  lea     rax, [rbp+57h+Buf2]
0x18005400b  mov     [rsp+0C0h+var_A0], rax
0x180054010  lea     rdx, byte_18010E337
0x180054017  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18005401c  movups  xmm0, xmmword ptr [r14+1300h]
0x180054024  movups  xmmword ptr [rbx], xmm0
0x180054027  movups  xmm1, xmmword ptr [r14+1310h]
0x18005402f  movups  xmmword ptr [rbx+10h], xmm1
0x180054033  movups  xmm0, xmmword ptr [r14+1320h]
0x18005403b  movups  xmmword ptr [rbx+20h], xmm0
0x18005403f  movups  xmm1, xmmword ptr [r14+1330h]
0x180054047  movups  xmmword ptr [rbx+30h], xmm1
0x18005404b  movups  xmm0, xmmword ptr [r14+1340h]
0x180054053  movups  xmmword ptr [rbx+40h], xmm0
0x180054057  movups  xmm1, xmmword ptr [r14+1350h]
0x18005405f  movups  xmmword ptr [rbx+50h], xmm1
0x180054063  movups  xmm0, xmmword ptr [r14+1360h]
0x18005406b  movups  xmmword ptr [rbx+60h], xmm0
0x18005406f  movups  xmm1, xmmword ptr [r14+1370h]
0x180054077  movups  xmmword ptr [rbx+70h], xmm1
0x18005407b  movups  xmm0, xmmword ptr [r14+1380h]
0x180054083  movups  xmmword ptr [rbx+80h], xmm0
0x18005408a  movups  xmm1, xmmword ptr [r14+1390h]
0x180054092  movups  xmmword ptr [rbx+90h], xmm1
0x180054099  movups  xmm0, xmmword ptr [r14+139Ch]
0x1800540a1  movups  xmmword ptr [rbx+9Ch], xmm0
0x1800540a8  lea     rcx, [rbx+0ACh]; void *
0x1800540af  xor     edx, edx; Val
0x1800540b1  mov     r8d, 100h; Size
0x1800540b7  call    memset_0
0x1800540bc  mov     [rbx+1ACh], r13w
0x1800540c4  xor     edi, edi
0x1800540c6  jmp     loc_180054160
0x1800540cb  xor     esi, esi
0x1800540cd  cmp     eax, 4
0x1800540d0  jbe     short loc_1800540F2
0x1800540d2  lea     rax, aTimezoneRedire_0; "Timezone redirection is disabled"
0x1800540d9  mov     qword ptr [rbp+57h+Buf2], rax
0x1800540dd  lea     rax, [rbp+57h+Buf2]
0x1800540e1  mov     [rsp+0C0h+var_A0], rax
0x1800540e6  lea     rdx, word_18010E316
0x1800540ed  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800540f2  lea     rax, TS_INVALID_DTZ
0x1800540f9  mov     ecx, 3
0x1800540fe  lea     edx, [rcx+7Dh]
0x180054101  movups  xmm0, xmmword ptr [rax]
0x180054104  movups  xmmword ptr [rbx], xmm0
0x180054107  movups  xmm1, xmmword ptr [rax+10h]
0x18005410b  movups  xmmword ptr [rbx+10h], xmm1
0x18005410f  movups  xmm0, xmmword ptr [rax+20h]
0x180054113  movups  xmmword ptr [rbx+20h], xmm0
0x180054117  movups  xmm1, xmmword ptr [rax+30h]
0x18005411b  movups  xmmword ptr [rbx+30h], xmm1
0x18005411f  movups  xmm0, xmmword ptr [rax+40h]
0x180054123  movups  xmmword ptr [rbx+40h], xmm0
0x180054127  movups  xmm1, xmmword ptr [rax+50h]
0x18005412b  movups  xmmword ptr [rbx+50h], xmm1
0x18005412f  movups  xmm0, xmmword ptr [rax+60h]
0x180054133  movups  xmmword ptr [rbx+60h], xmm0
0x180054137  movups  xmm1, xmmword ptr [rax+70h]
0x18005413b  movups  xmmword ptr [rbx+70h], xmm1
0x18005413f  add     rbx, rdx
0x180054142  add     rax, rdx
0x180054145  sub     rcx, r13
0x180054148  jnz     short loc_180054101
0x18005414a  movups  xmm0, xmmword ptr [rax]
0x18005414d  movups  xmmword ptr [rbx], xmm0
0x180054150  movups  xmm1, xmmword ptr [rax+10h]
0x180054154  movups  xmmword ptr [rbx+10h], xmm1
0x180054158  movups  xmm0, xmmword ptr [rax+20h]
0x18005415c  movups  xmmword ptr [rbx+20h], xmm0
0x180054160  test    r15b, r15b
0x180054163  jz      short loc_18005418F
0x180054165  lea     rcx, [rbp+57h+var_90]; this
0x180054169  call    ?StopImpersonating@CImpersonate@@QEAAJXZ; CImpersonate::StopImpersonating(void)
0x18005416e  mov     edi, eax
0x180054170  test    eax, eax
0x180054172  jns     short loc_18005418F
0x180054174  lea     r9, aCremotetermina_16; "CRemoteTerminal::GetClientTimeZone"
0x18005417b  mov     r8d, eax
0x18005417e  lea     rdx, aImpersonateSto_0; "Impersonate.StopImpersonating failed: 0"...
0x180054185  mov     ecx, 8; int
0x18005418a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005418f  test    rsi, rsi
0x180054192  jz      short loc_18005419C
0x180054194  mov     rcx, rsi; Block
0x180054197  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18005419c  mov     rcx, [rbp+57h+StringSid]; hMem
  ... truncated ...
```
