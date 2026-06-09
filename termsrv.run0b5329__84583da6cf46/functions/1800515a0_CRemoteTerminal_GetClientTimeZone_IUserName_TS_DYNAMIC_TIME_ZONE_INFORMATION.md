# CRemoteTerminal::GetClientTimeZone(IUserName *,_TS_DYNAMIC_TIME_ZONE_INFORMATION *)

- ea: `0x1800515a0`
- end: `0x180051ac6`
- name: `?GetClientTimeZone@CRemoteTerminal@@UEAAJPEAUIUserName@@PEAU_TS_DYNAMIC_TIME_ZONE_INFORMATION@@@Z`
- size: `1318`
- prototype: `__int64 __fastcall(CRemoteTerminal *__hidden this, struct IUserName *, struct _TS_DYNAMIC_TIME_ZONE_INFORMATION *)`
- caller_count: `0`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180001284`
- `0x18000a210`
- `0x18000ef50`
- `0x180011f80`
- `0x180012080`
- `0x1800148f0`
- `0x180017758`
- `0x1800321f0`
- `0x18003269c`
- `0x180032700`
- `0x1800330c4`
- `0x1800515a0`
- `0x180051be0`
- `0x1800b8c8c`
- `0x1800c4e00`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051783`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051783`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800517b6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180051a7d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800517b6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180051a7d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180051a8c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180051a8c`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180051760`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180051760`
- `REGAPI!RegIsTimeZoneRedirectionEnabled` at `0x1800517c8`
- `REGAPI!RegIsTimeZoneRedirectionEnabled` at `0x1800517c8`

## string_xrefs

- `0x18005179c`: `Failed in getting user string sid (0x%x), process machine GP only`
- `0x180051a56`: `Impersonate.StopImpersonating failed: 0x%x in %s`

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
    if ( (unsigned int)dword_180128170 > 4 )
    {
      *(_QWORD *)&Size[1] = "Not using timezone redirection because this is not an AppServer session.";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v8,
        (unsigned int)&word_1801082FE,
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
    if ( (unsigned int)dword_180128170 > 4 )
    {
      *(_QWORD *)&Size[1] = "Timezone redirection is enabled";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v16,
        (unsigned int)byte_1801082DD,
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
      if ( (unsigned int)dword_180128170 > 3 )
      {
        Size[1] = ConnectionProperty;
        *(_QWORD *)&Buf2.Data1 = "Unable to get dynamic time zone information. Falling back to legacy time zone.";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          3,
          (unsigned int)&byte_1801082B7,
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
    if ( (unsigned int)dword_180128170 > 4 )
    {
      *(_QWORD *)&Buf2.Data1 = "Timezone redirection is disabled";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v16,
        (unsigned int)&word_180108296,
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
0x1800515a0  push    rbp
0x1800515a2  push    rbx
0x1800515a3  push    rsi
0x1800515a4  push    rdi
0x1800515a5  push    r13
0x1800515a7  push    r14
0x1800515a9  push    r15
0x1800515ab  lea     rbp, [rsp-27h]
0x1800515b0  sub     rsp, 90h
0x1800515b7  mov     rax, cs:__security_cookie
0x1800515be  xor     rax, rsp
0x1800515c1  mov     [rbp+57h+var_40], rax
0x1800515c5  mov     rbx, r8
0x1800515c8  mov     rsi, rdx
0x1800515cb  mov     r14, rcx
0x1800515ce  xorps   xmm0, xmm0
0x1800515d1  movups  xmmword ptr [rbp+57h+var_50.Data1], xmm0
0x1800515d5  mov     [rbp+57h+Sid], 0
0x1800515dd  mov     [rbp+57h+StringSid], 0
0x1800515e5  mov     [rbp+57h+var_90], 0
0x1800515eb  lea     rdx, [rcx+13F8h]; struct CResource *
0x1800515f2  lea     rcx, [rbp+57h+var_60]; this
0x1800515f6  call    ??0CAutoSharedLock@@QEAA@AEAVCResource@@@Z; CAutoSharedLock::CAutoSharedLock(CResource &)
0x1800515fb  nop
0x1800515fc  test    rbx, rbx
0x1800515ff  jnz     short loc_180051628
0x180051601  lea     r9, aCremotetermina_16; "CRemoteTerminal::GetClientTimeZone"
0x180051608  lea     r8, aPtimezone; "pTimeZone"
0x18005160f  lea     rdx, aMissingParamte; "Missing paramter %s in %s"
0x180051616  lea     ecx, [rbx+8]; int
0x180051619  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005161e  mov     edi, 80070057h
0x180051623  jmp     loc_180051A74
0x180051628  lea     rdx, [rbp+57h+var_50]; struct _GUID *
0x18005162c  mov     rcx, r14; this
0x18005162f  call    ?GetLicenseType@CRemoteTerminal@@UEAAJPEAU_GUID@@@Z; CRemoteTerminal::GetLicenseType(_GUID *)
0x180051634  mov     edi, eax
0x180051636  test    eax, eax
0x180051638  jns     short loc_18005165A
0x18005163a  lea     r9, aCremotetermina_16; "CRemoteTerminal::GetClientTimeZone"
0x180051641  mov     r8d, eax
0x180051644  lea     rdx, aThisGetlicense; "this->GetLicenseType failed: 0x%x in %s"
0x18005164b  mov     ecx, 8; int
0x180051650  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180051655  jmp     loc_180051A74
0x18005165a  movaps  xmm0, xmmword ptr [rbp+57h+var_50.Data1]
0x18005165e  movdqa  [rbp+57h+Buf2], xmm0
0x180051663  mov     r8d, 10h; Size
0x180051669  lea     rdx, [rbp+57h+Buf2]; Buf2
0x18005166d  lea     rcx, LICENSE_TYPE_APPSERVER; Buf1
0x180051674  call    memcmp_0
0x180051679  test    eax, eax
0x18005167b  jz      loc_18005172F
0x180051681  cmp     cs:?bIsClientSKU@CUtils@@0HA, 0; int CUtils::bIsClientSKU
0x180051688  jnz     loc_18005172F
0x18005168e  mov     eax, cs:dword_180128170
0x180051694  cmp     eax, 4
0x180051697  jbe     short loc_1800516B9
0x180051699  lea     rax, aNotUsingTimezo; "Not using timezone redirection because "...
0x1800516a0  mov     qword ptr [rbp+57h+Size+4], rax
0x1800516a4  lea     rax, [rbp+57h+Size+4]
0x1800516a8  mov     [rsp+0C0h+var_A0], rax
0x1800516ad  lea     rdx, word_1801082FE
0x1800516b4  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800516b9  lea     rax, TS_INVALID_DTZ
0x1800516c0  mov     ecx, 3
0x1800516c5  lea     edx, [rcx+7Dh]
0x1800516c8  movups  xmm0, xmmword ptr [rax]
0x1800516cb  movups  xmmword ptr [rbx], xmm0
0x1800516ce  movups  xmm1, xmmword ptr [rax+10h]
0x1800516d2  movups  xmmword ptr [rbx+10h], xmm1
0x1800516d6  movups  xmm0, xmmword ptr [rax+20h]
0x1800516da  movups  xmmword ptr [rbx+20h], xmm0
0x1800516de  movups  xmm1, xmmword ptr [rax+30h]
0x1800516e2  movups  xmmword ptr [rbx+30h], xmm1
0x1800516e6  movups  xmm0, xmmword ptr [rax+40h]
0x1800516ea  movups  xmmword ptr [rbx+40h], xmm0
0x1800516ee  movups  xmm1, xmmword ptr [rax+50h]
0x1800516f2  movups  xmmword ptr [rbx+50h], xmm1
0x1800516f6  movups  xmm0, xmmword ptr [rax+60h]
0x1800516fa  movups  xmmword ptr [rbx+60h], xmm0
0x1800516fe  movups  xmm1, xmmword ptr [rax+70h]
0x180051702  movups  xmmword ptr [rbx+70h], xmm1
0x180051706  add     rbx, rdx
0x180051709  add     rax, rdx
0x18005170c  sub     rcx, 1
0x180051710  jnz     short loc_1800516C8
0x180051712  movups  xmm0, xmmword ptr [rax]
0x180051715  movups  xmmword ptr [rbx], xmm0
0x180051718  movups  xmm1, xmmword ptr [rax+10h]
0x18005171c  movups  xmmword ptr [rbx+10h], xmm1
0x180051720  movups  xmm0, xmmword ptr [rax+20h]
0x180051724  movups  xmmword ptr [rbx+20h], xmm0
0x180051728  xor     edi, edi
0x18005172a  jmp     loc_180051A74
0x18005172f  xor     r15b, r15b
0x180051732  mov     r13d, 1
0x180051738  test    rsi, rsi
0x18005173b  jz      loc_1800517C4
0x180051741  mov     rax, [rsi]
0x180051744  lea     rdx, [rbp+57h+Sid]
0x180051748  mov     rcx, rsi
0x18005174b  mov     rax, [rax+48h]
0x18005174f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051754  test    eax, eax
0x180051756  js      short loc_180051799
0x180051758  lea     rdx, [rbp+57h+StringSid]; StringSid
0x18005175c  mov     rcx, [rbp+57h+Sid]; Sid
0x180051760  call    cs:__imp_ConvertSidToStringSidW
0x180051766  cmp     eax, r13d
0x180051769  jnz     short loc_180051783
0x18005176b  mov     rdx, rsi; struct IUserName *
0x18005176e  lea     rcx, [rbp+57h+var_90]; this
0x180051772  call    ?ImpersonateUser@CImpersonate@@QEAAJPEAUIUserName@@@Z; CImpersonate::ImpersonateUser(IUserName *)
0x180051777  mov     r15d, eax
0x18005177a  shr     r15d, 1Fh
0x18005177e  xor     r15b, r13b
0x180051781  jmp     short loc_180051795
0x180051783  call    cs:__imp_GetLastError
0x180051789  test    eax, eax
0x18005178b  jle     short loc_180051797
0x18005178d  movzx   eax, ax
0x180051790  or      eax, 80070000h
0x180051795  test    eax, eax
0x180051797  jns     short loc_1800517C4
0x180051799  mov     r8d, eax
0x18005179c  lea     rdx, aFailedInGettin; "Failed in getting user string sid (0x%x"...
0x1800517a3  mov     ecx, 4; int
0x1800517a8  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800517ad  mov     rcx, [rbp+57h+StringSid]; hMem
0x1800517b1  test    rcx, rcx
0x1800517b4  jz      short loc_1800517BC
0x1800517b6  call    cs:__imp_LocalFree
0x1800517bc  xor     ecx, ecx
0x1800517be  mov     [rbp+57h+StringSid], rcx
0x1800517c2  jmp     short loc_1800517C8
0x1800517c4  mov     rcx, [rbp+57h+StringSid]
0x1800517c8  call    cs:__imp_RegIsTimeZoneRedirectionEnabled
0x1800517ce  test    al, al
0x1800517d0  mov     eax, cs:dword_180128170
0x1800517d6  jz      loc_1800519A3
0x1800517dc  cmp     eax, 4
0x1800517df  jbe     short loc_180051801
0x1800517e1  lea     rax, aTimezoneRedire; "Timezone redirection is enabled"
0x1800517e8  mov     qword ptr [rbp+57h+Size+4], rax
0x1800517ec  lea     rax, [rbp+57h+Size+4]
0x1800517f0  mov     [rsp+0C0h+var_A0], rax
0x1800517f5  lea     rdx, byte_1801082DD
0x1800517fc  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180051801  mov     ecx, 1C8h; unsigned __int64
0x180051806  mov     dword ptr [rbp+57h+Size], ecx
0x180051809  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180051810  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180051815  mov     rsi, rax
0x180051818  test    rax, rax
0x18005181b  jnz     short loc_180051827
0x18005181d  mov     edi, 8007000Eh
0x180051822  jmp     loc_180051A74
0x180051827  mov     r8d, dword ptr [rbp+57h+Size]; Size
0x18005182b  xor     edx, edx; Val
0x18005182d  mov     rcx, rsi; void *
0x180051830  call    memset_0
0x180051835  mov     r9, rsi; struct __PROPERTY_VALUE *
0x180051838  lea     r8, [rbp+57h+Size]; unsigned int *
0x18005183c  lea     rdx, PROPERTY_DYNAMIC_TIME_ZONE_INFORMATION; struct _GUID *
0x180051843  mov     rcx, r14; this
0x180051846  call    ?GetConnectionProperty@CRemoteTerminal@@UEAAJAEBU_GUID@@PEAKPEAU__PROPERTY_VALUE@@@Z; CRemoteTerminal::GetConnectionProperty(_GUID const &,ulong *,__PROPERTY_VALUE *)
0x18005184b  mov     edi, eax
0x18005184d  mov     ecx, 3
0x180051852  test    eax, eax
0x180051854  js      short loc_1800518BE
0x180051856  cmp     [rsi], cx
0x180051859  jnz     short loc_1800518BE
0x18005185b  cmp     dword ptr [rsi+8], 1B0h
0x180051862  jb      short loc_1800518BE
0x180051864  mov     rax, [rsi+10h]
0x180051868  test    rax, rax
0x18005186b  jz      short loc_1800518BE
0x18005186d  lea     edx, [rcx+7Dh]
0x180051870  movups  xmm0, xmmword ptr [rax]
0x180051873  movups  xmmword ptr [rbx], xmm0
0x180051876  movups  xmm1, xmmword ptr [rax+10h]
0x18005187a  movups  xmmword ptr [rbx+10h], xmm1
0x18005187e  movups  xmm0, xmmword ptr [rax+20h]
0x180051882  movups  xmmword ptr [rbx+20h], xmm0
0x180051886  movups  xmm1, xmmword ptr [rax+30h]
0x18005188a  movups  xmmword ptr [rbx+30h], xmm1
0x18005188e  movups  xmm0, xmmword ptr [rax+40h]
0x180051892  movups  xmmword ptr [rbx+40h], xmm0
0x180051896  movups  xmm1, xmmword ptr [rax+50h]
0x18005189a  movups  xmmword ptr [rbx+50h], xmm1
0x18005189e  movups  xmm0, xmmword ptr [rax+60h]
0x1800518a2  movups  xmmword ptr [rbx+60h], xmm0
0x1800518a6  movups  xmm1, xmmword ptr [rax+70h]
0x1800518aa  movups  xmmword ptr [rbx+70h], xmm1
0x1800518ae  add     rbx, rdx
0x1800518b1  add     rax, rdx
0x1800518b4  sub     rcx, r13
0x1800518b7  jnz     short loc_180051870
0x1800518b9  jmp     loc_180051A22
0x1800518be  mov     eax, cs:dword_180128170
0x1800518c4  cmp     eax, ecx
0x1800518c6  jbe     short loc_1800518F4
0x1800518c8  mov     dword ptr [rbp+57h+Size+4], edi
0x1800518cb  lea     rax, aUnableToGetDyn; "Unable to get dynamic time zone informa"...
0x1800518d2  mov     qword ptr [rbp+57h+Buf2], rax
0x1800518d6  lea     rax, [rbp+57h+Size+4]
0x1800518da  mov     [rsp+0C0h+var_98], rax
0x1800518df  lea     rax, [rbp+57h+Buf2]
0x1800518e3  mov     [rsp+0C0h+var_A0], rax
0x1800518e8  lea     rdx, byte_1801082B7
0x1800518ef  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800518f4  movups  xmm0, xmmword ptr [r14+1300h]
0x1800518fc  movups  xmmword ptr [rbx], xmm0
0x1800518ff  movups  xmm1, xmmword ptr [r14+1310h]
0x180051907  movups  xmmword ptr [rbx+10h], xmm1
0x18005190b  movups  xmm0, xmmword ptr [r14+1320h]
0x180051913  movups  xmmword ptr [rbx+20h], xmm0
0x180051917  movups  xmm1, xmmword ptr [r14+1330h]
0x18005191f  movups  xmmword ptr [rbx+30h], xmm1
0x180051923  movups  xmm0, xmmword ptr [r14+1340h]
0x18005192b  movups  xmmword ptr [rbx+40h], xmm0
0x18005192f  movups  xmm1, xmmword ptr [r14+1350h]
0x180051937  movups  xmmword ptr [rbx+50h], xmm1
0x18005193b  movups  xmm0, xmmword ptr [r14+1360h]
0x180051943  movups  xmmword ptr [rbx+60h], xmm0
0x180051947  movups  xmm1, xmmword ptr [r14+1370h]
0x18005194f  movups  xmmword ptr [rbx+70h], xmm1
0x180051953  movups  xmm0, xmmword ptr [r14+1380h]
0x18005195b  movups  xmmword ptr [rbx+80h], xmm0
0x180051962  movups  xmm1, xmmword ptr [r14+1390h]
0x18005196a  movups  xmmword ptr [rbx+90h], xmm1
0x180051971  movups  xmm0, xmmword ptr [r14+139Ch]
0x180051979  movups  xmmword ptr [rbx+9Ch], xmm0
0x180051980  lea     rcx, [rbx+0ACh]; void *
0x180051987  xor     edx, edx; Val
0x180051989  mov     r8d, 100h; Size
0x18005198f  call    memset_0
0x180051994  mov     [rbx+1ACh], r13w
0x18005199c  xor     edi, edi
0x18005199e  jmp     loc_180051A38
0x1800519a3  xor     esi, esi
0x1800519a5  cmp     eax, 4
0x1800519a8  jbe     short loc_1800519CA
0x1800519aa  lea     rax, aTimezoneRedire_0; "Timezone redirection is disabled"
0x1800519b1  mov     qword ptr [rbp+57h+Buf2], rax
0x1800519b5  lea     rax, [rbp+57h+Buf2]
0x1800519b9  mov     [rsp+0C0h+var_A0], rax
0x1800519be  lea     rdx, word_180108296
0x1800519c5  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800519ca  lea     rax, TS_INVALID_DTZ
0x1800519d1  mov     ecx, 3
0x1800519d6  lea     edx, [rcx+7Dh]
0x1800519d9  movups  xmm0, xmmword ptr [rax]
0x1800519dc  movups  xmmword ptr [rbx], xmm0
0x1800519df  movups  xmm1, xmmword ptr [rax+10h]
0x1800519e3  movups  xmmword ptr [rbx+10h], xmm1
0x1800519e7  movups  xmm0, xmmword ptr [rax+20h]
0x1800519eb  movups  xmmword ptr [rbx+20h], xmm0
0x1800519ef  movups  xmm1, xmmword ptr [rax+30h]
0x1800519f3  movups  xmmword ptr [rbx+30h], xmm1
0x1800519f7  movups  xmm0, xmmword ptr [rax+40h]
0x1800519fb  movups  xmmword ptr [rbx+40h], xmm0
0x1800519ff  movups  xmm1, xmmword ptr [rax+50h]
0x180051a03  movups  xmmword ptr [rbx+50h], xmm1
0x180051a07  movups  xmm0, xmmword ptr [rax+60h]
0x180051a0b  movups  xmmword ptr [rbx+60h], xmm0
0x180051a0f  movups  xmm1, xmmword ptr [rax+70h]
0x180051a13  movups  xmmword ptr [rbx+70h], xmm1
0x180051a17  add     rbx, rdx
0x180051a1a  add     rax, rdx
0x180051a1d  sub     rcx, r13
0x180051a20  jnz     short loc_1800519D9
0x180051a22  movups  xmm0, xmmword ptr [rax]
0x180051a25  movups  xmmword ptr [rbx], xmm0
0x180051a28  movups  xmm1, xmmword ptr [rax+10h]
0x180051a2c  movups  xmmword ptr [rbx+10h], xmm1
0x180051a30  movups  xmm0, xmmword ptr [rax+20h]
0x180051a34  movups  xmmword ptr [rbx+20h], xmm0
0x180051a38  test    r15b, r15b
0x180051a3b  jz      short loc_180051A67
0x180051a3d  lea     rcx, [rbp+57h+var_90]; this
0x180051a41  call    ?StopImpersonating@CImpersonate@@QEAAJXZ; CImpersonate::StopImpersonating(void)
0x180051a46  mov     edi, eax
0x180051a48  test    eax, eax
0x180051a4a  jns     short loc_180051A67
0x180051a4c  lea     r9, aCremotetermina_16; "CRemoteTerminal::GetClientTimeZone"
0x180051a53  mov     r8d, eax
0x180051a56  lea     rdx, aImpersonateSto_0; "Impersonate.StopImpersonating failed: 0"...
0x180051a5d  mov     ecx, 8; int
0x180051a62  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180051a67  test    rsi, rsi
0x180051a6a  jz      short loc_180051A74
0x180051a6c  mov     rcx, rsi; Block
0x180051a6f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180051a74  mov     rcx, [rbp+57h+StringSid]; hMem
0x180051a78  test    rcx, rcx
0x180051a7b  jz      short loc_180051A83
0x180051a7d  call    cs:__imp_LocalFree
0x180051a83  mov     rcx, [rbp+57h+Sid]; pv
  ... truncated ...
```
