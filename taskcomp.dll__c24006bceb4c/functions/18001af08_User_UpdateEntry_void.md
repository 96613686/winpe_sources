# User::UpdateEntry(void)

- ea: `0x18001af08`
- end: `0x18001b455`
- name: `?UpdateEntry@User@@AEBAJXZ`
- size: `1357`
- prototype: `__int64 __fastcall(User *__hidden this)`
- caller_count: `4`
- callee_count: `18`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180003b3c`
- `0x180005b98`
- `0x180019a10`
- `0x18001aacc`

## callees

- `0x1800013a0`
- `0x180003470`
- `0x180003dac`
- `0x180003de8`
- `0x180004e50`
- `0x180004eec`
- `0x180004f88`
- `0x1800074c8`
- `0x1800074d4`
- `0x18000878c`
- `0x180009ac0`
- `0x18000c760`
- `0x18000fbb8`
- `0x18001724c`
- `0x180019c28`
- `0x18001abac`
- `0x18001af08`
- `0x18001b45c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001af71`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b22a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b388`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001af71`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b22a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b388`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b078`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b24b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b3ca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b078`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b24b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b3ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b0d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b0db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b1a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b2d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b0d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b0db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b1a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b2d9`
- `OLEAUT32!__imp_SysFreeString` at `0x18001b1ef`
- `OLEAUT32!__imp_SysFreeString` at `0x18001b254`
- `OLEAUT32!__imp_SysFreeString` at `0x18001b33f`
- `OLEAUT32!__imp_SysFreeString` at `0x18001b1ef`
- `OLEAUT32!__imp_SysFreeString` at `0x18001b254`
- `OLEAUT32!__imp_SysFreeString` at `0x18001b33f`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x18001b0bc`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x18001b196`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x18001b0bc`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x18001b196`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall User::UpdateEntry(User *this)
{
  __int64 v2; // rcx
  void *v3; // r14
  const WCHAR **v4; // rbx
  struct _RTL_CRITICAL_SECTION *v5; // rdi
  WCHAR *ComputerNameW; // rax
  int v7; // eax
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 v11; // rax
  _QWORD *v12; // rcx
  _QWORD *v13; // rcx
  void **v14; // rcx
  void *v15; // rax
  const WCHAR **v16; // rdi
  const WCHAR *v17; // rdx
  const WCHAR *v18; // rcx
  signed int LastError; // ebx
  UINT v20; // edx
  OLECHAR *v21; // rsi
  const WCHAR *v22; // rdx
  const WCHAR *v23; // rcx
  struct _RTL_CRITICAL_SECTION *v24; // rbx
  __int64 v25; // r8
  __int64 v26; // r8
  signed int v27; // eax
  _bstr_t *v28; // rcx
  struct _RTL_CRITICAL_SECTION *v30; // rbx
  const WCHAR **v31; // [rsp+40h] [rbp-49h] BYREF
  const WCHAR **v32; // [rsp+48h] [rbp-41h] BYREF
  const struct _bstr_t::Data_t *v33; // [rsp+50h] [rbp-39h] BYREF
  void *v34; // [rsp+58h] [rbp-31h] BYREF
  _QWORD *v35; // [rsp+60h] [rbp-29h] BYREF
  _QWORD *v36; // [rsp+68h] [rbp-21h] BYREF
  _BYTE pExceptionObject[112]; // [rsp+70h] [rbp-19h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+F0h] [rbp+67h] BYREF
  DWORD cchReferencedDomainName; // [rsp+F8h] [rbp+6Fh] BYREF
  DWORD cbSid; // [rsp+100h] [rbp+77h] BYREF
  LPWSTR bstrString; // [rsp+108h] [rbp+7Fh] BYREF

  v2 = *(_QWORD *)this;
  if ( !v2 )
    return 2147549183LL;
  v3 = *(void **)(v2 + 32);
  if ( !v3 )
  {
    if ( !(unsigned __int8)_bstr_t::operator!(v2 + 8) )
    {
      peUse = SidTypeUnknown;
      cchReferencedDomainName = 0;
      cbSid = 0;
      v31 = 0;
      v4 = 0;
      v32 = 0;
      v5 = User::s_cs;
      bstrString = (LPWSTR)User::s_cs;
      EnterCriticalSection(User::s_cs);
      ComputerNameW = User::GetComputerNameW();
      _bstr_t::_bstr_t((_bstr_t *)&v33, ComputerNameW);
      v7 = _bstr_t::_Compare((_bstr_t::Data_t **)(*(_QWORD *)this + 24LL), &v33);
      v8 = *(_QWORD *)this;
      if ( v7 )
      {
        _bstr_t::operator=((_bstr_t *)&v31, v8 + 8);
      }
      else
      {
        _bstr_t::operator=((_bstr_t *)&v31, v8 + 16);
        _bstr_t::operator=((_bstr_t *)&v32, (__int64)&v33);
        v4 = v32;
      }
      if ( ((unsigned __int8)_bstr_t::operator!(*(_QWORD *)this + 24LL)
         || (unsigned __int8)_bstr_t::operator!(v9 + 16)
         || (unsigned __int8)_bstr_t::operator!(v9 + 8))
        && (unsigned int)dword_18005D170 > 4 )
      {
        LODWORD(bstrString) = peUse;
        v11 = *(_QWORD *)this;
        v12 = *(_QWORD **)(*(_QWORD *)this + 8LL);
        if ( v12 )
          v12 = (_QWORD *)*v12;
        v35 = v12;
        v13 = *(_QWORD **)(v11 + 16);
        if ( v13 )
          v13 = (_QWORD *)*v13;
        v36 = v13;
        v14 = *(void ***)(v11 + 24);
        if ( v14 )
          v15 = *v14;
        else
          v15 = 0;
        v34 = v15;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
          (__int64)v14,
          (__int64)byte_180055AA9,
          v9,
          v10,
          &v34,
          &v36,
          &v35);
      }
      _bstr_t::~_bstr_t((_bstr_t *)&v33);
      LeaveCriticalSection(v5);
      v16 = v31;
      if ( v31 )
        v17 = *v31;
      else
        v17 = 0;
      if ( v4 )
        v18 = *v4;
      else
        v18 = 0;
      if ( LookupAccountNameW(v18, v17, 0, &cbSid, 0, &cchReferencedDomainName, &peUse) )
      {
        LastError = -2147418113;
LABEL_65:
        _bstr_t::~_bstr_t((_bstr_t *)&v32);
        v28 = (_bstr_t *)&v31;
LABEL_66:
        _bstr_t::~_bstr_t(v28);
        return (unsigned int)LastError;
      }
      if ( GetLastError() != 122 )
      {
        LastError = GetLastError();
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && *((char *)WPP_GLOBAL_Control + 28) < 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            24,
            WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids,
            (unsigned int)LastError);
        }
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        goto LABEL_65;
      }
      v3 = operator new[](cbSid + 1);
      v34 = v3;
      if ( !v3 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && *((char *)WPP_GLOBAL_Control + 28) < 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids);
        }
        wmi::OutOfMemoryException::OutOfMemoryException((wmi::OutOfMemoryException *)pExceptionObject);
        throw (wmi::OutOfMemoryException *)pExceptionObject;
      }
      v20 = cchReferencedDomainName++;
      ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, v20);
      v21 = bstrString;
      if ( v16 )
        v22 = *v16;
      else
        v22 = 0;
      if ( v4 )
        v23 = *v4;
      else
        v23 = 0;
      if ( !LookupAccountNameW(v23, v22, v3, &cbSid, bstrString, &cchReferencedDomainName, &peUse) )
      {
        LastError = GetLastError();
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && *((char *)WPP_GLOBAL_Control + 28) < 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            26,
            WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids,
            (unsigned int)LastError);
        }
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        SysFreeString(v21);
        operator delete(v3);
        goto LABEL_65;
      }
      if ( peUse == SidTypeDomain || peUse <= 0 || peUse >= SidTypeDeletedAccount )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && *((char *)WPP_GLOBAL_Control + 28) < 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids);
        }
        SysFreeString(v21);
        operator delete(v3);
        LastError = -2147024809;
        goto LABEL_65;
      }
      v24 = User::s_cs;
      EnterCriticalSection(User::s_cs);
      wmi::AutoVectorPtr<unsigned char>::operator=((void **)(*(_QWORD *)this + 32LL), v3);
      *(_DWORD *)(*(_QWORD *)this + 40LL) = peUse;
      LeaveCriticalSection(v24);
      SysFreeString(v21);
      operator delete(0);
      _bstr_t::~_bstr_t((_bstr_t *)&v32);
      _bstr_t::~_bstr_t((_bstr_t *)&v31);
      goto LABEL_53;
    }
    return 2147549183LL;
  }
LABEL_53:
  if ( (unsigned __int8)_bstr_t::operator!(*(_QWORD *)this + 24LL)
    || (unsigned __int8)_bstr_t::operator!(v25 + 16)
    || *(_DWORD *)(v26 + 40) == 8 )
  {
    LODWORD(bstrString) = 8;
    v32 = 0;
    v31 = 0;
    v33 = 0;
    if ( !(unsigned int)User::LookupUserSid(
                          (struct _bstr_t *)&v32,
                          (struct _bstr_t *)&v31,
                          (enum _SID_NAME_USE *)&bstrString,
                          v3) )
    {
      v27 = GetLastError();
      LastError = v27;
      if ( v27 > 0 )
        LastError = (unsigned __int16)v27 | 0x80070000;
      _bstr_t::~_bstr_t((_bstr_t *)&v33);
      _bstr_t::~_bstr_t((_bstr_t *)&v31);
      v28 = (_bstr_t *)&v32;
      goto LABEL_66;
    }
    User::AssembleFullUserName((struct _bstr_t *)&v33, (struct _bstr_t *)&v32, (struct _bstr_t *)&v31);
    v30 = User::s_cs;
    EnterCriticalSection(User::s_cs);
    _bstr_t::operator=((_bstr_t *)(*(_QWORD *)this + 16LL), (__int64)&v31);
    _bstr_t::operator=((_bstr_t *)(*(_QWORD *)this + 24LL), (__int64)&v32);
    _bstr_t::operator=((_bstr_t *)(*(_QWORD *)this + 8LL), (__int64)&v33);
    *(_DWORD *)(*(_QWORD *)this + 40LL) = (_DWORD)bstrString;
    LeaveCriticalSection(v30);
    _bstr_t::~_bstr_t((_bstr_t *)&v33);
    _bstr_t::~_bstr_t((_bstr_t *)&v31);
    _bstr_t::~_bstr_t((_bstr_t *)&v32);
  }
  return 0;
}

```

## disassembly

```asm
0x18001af08  push    rbp
0x18001af0a  push    rbx
0x18001af0b  push    rsi
0x18001af0c  push    rdi
0x18001af0d  push    r14
0x18001af0f  push    r15
0x18001af11  lea     rbp, [rsp-2Fh]
0x18001af16  sub     rsp, 0B8h
0x18001af1d  mov     r15, rcx
0x18001af20  mov     rcx, [rcx]
0x18001af23  test    rcx, rcx
0x18001af26  jz      loc_18001B3F2
0x18001af2c  mov     r14, [rcx+20h]
0x18001af30  test    r14, r14
0x18001af33  jnz     loc_18001B276
0x18001af39  add     rcx, 8
0x18001af3d  call    ??7_bstr_t@@QEBA_NXZ; _bstr_t::operator!(void)
0x18001af42  test    al, al
0x18001af44  jnz     loc_18001B3F2
0x18001af4a  mov     [rbp+57h+arg_0], 8
0x18001af51  mov     [rbp+57h+arg_8], r14d
0x18001af55  mov     [rbp+57h+cbSid], r14d
0x18001af59  mov     [rbp+57h+var_A0], r14
0x18001af5d  xor     ebx, ebx
0x18001af5f  mov     [rbp+57h+var_98], rbx
0x18001af63  mov     rdi, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x18001af6a  mov     [rbp+57h+bstrString], rdi
0x18001af6e  mov     rcx, rdi; lpCriticalSection
0x18001af71  call    cs:__imp_EnterCriticalSection
0x18001af77  nop
0x18001af78  call    ?GetComputerNameW@User@@CAPEBGXZ; User::GetComputerNameW(void)
0x18001af7d  mov     rdx, rax; unsigned __int16 *
0x18001af80  lea     rcx, [rbp+57h+var_90]; this
0x18001af84  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18001af89  mov     rcx, [r15]
0x18001af8c  add     rcx, 18h; this
0x18001af90  lea     rdx, [rbp+57h+var_90]; struct _bstr_t *
0x18001af94  call    ?_Compare@_bstr_t@@AEBAHAEBV1@@Z; _bstr_t::_Compare(_bstr_t const &)
0x18001af99  mov     rdx, [r15]
0x18001af9c  lea     rcx, [rbp+57h+var_A0]
0x18001afa0  test    eax, eax
0x18001afa2  jnz     short loc_18001AFC0
0x18001afa4  add     rdx, 10h
0x18001afa8  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x18001afad  lea     rdx, [rbp+57h+var_90]
0x18001afb1  lea     rcx, [rbp+57h+var_98]
0x18001afb5  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x18001afba  mov     rbx, [rbp+57h+var_98]
0x18001afbe  jmp     short loc_18001AFC9
0x18001afc0  add     rdx, 8
0x18001afc4  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x18001afc9  mov     r8, [r15]
0x18001afcc  lea     rcx, [r8+18h]
0x18001afd0  call    ??7_bstr_t@@QEBA_NXZ; _bstr_t::operator!(void)
0x18001afd5  test    al, al
0x18001afd7  jnz     short loc_18001AFF3
0x18001afd9  lea     rcx, [r8+10h]
0x18001afdd  call    ??7_bstr_t@@QEBA_NXZ; _bstr_t::operator!(void)
0x18001afe2  test    al, al
0x18001afe4  jnz     short loc_18001AFF3
0x18001afe6  lea     rcx, [r8+8]
0x18001afea  call    ??7_bstr_t@@QEBA_NXZ; _bstr_t::operator!(void)
0x18001afef  test    al, al
0x18001aff1  jz      short loc_18001B06B
0x18001aff3  mov     eax, cs:dword_18005D170
0x18001aff9  cmp     eax, 4
0x18001affc  jbe     short loc_18001B06B
0x18001affe  mov     eax, [rbp+57h+arg_0]
0x18001b001  mov     dword ptr [rbp+57h+bstrString], eax
0x18001b004  mov     rax, [r15]
0x18001b007  mov     rcx, [rax+8]
0x18001b00b  test    rcx, rcx
0x18001b00e  jz      short loc_18001B013
0x18001b010  mov     rcx, [rcx]
0x18001b013  mov     [rbp+57h+var_80], rcx
0x18001b017  mov     rcx, [rax+10h]
0x18001b01b  test    rcx, rcx
0x18001b01e  jz      short loc_18001B023
0x18001b020  mov     rcx, [rcx]
0x18001b023  mov     [rbp+57h+var_78], rcx
0x18001b027  mov     rcx, [rax+18h]
0x18001b02b  test    rcx, rcx
0x18001b02e  jz      short loc_18001B035
0x18001b030  mov     rax, [rcx]
0x18001b033  jmp     short loc_18001B037
0x18001b035  xor     eax, eax
0x18001b037  mov     [rbp+57h+var_88], rax
0x18001b03b  lea     rax, [rbp+57h+bstrString]
0x18001b03f  mov     [rsp+0E0h+var_A8], rax
0x18001b044  lea     rax, [rbp+57h+var_80]
0x18001b048  mov     [rsp+0E0h+peUse], rax
0x18001b04d  lea     rax, [rbp+57h+var_78]
0x18001b051  mov     [rsp+0E0h+cchReferencedDomainName], rax
0x18001b056  lea     rax, [rbp+57h+var_88]
0x18001b05a  mov     [rsp+0E0h+ReferencedDomainName], rax
0x18001b05f  lea     rdx, byte_180055AA9
0x18001b066  call    ??$Write@U?$_tlgWrapSz@G@@U1@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@33AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18001b06b  lea     rcx, [rbp+57h+var_90]; this
0x18001b06f  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18001b074  nop
0x18001b075  mov     rcx, rdi; lpCriticalSection
0x18001b078  call    cs:__imp_LeaveCriticalSection
0x18001b07e  mov     rdi, [rbp+57h+var_A0]
0x18001b082  test    rdi, rdi
0x18001b085  jz      short loc_18001B08C
0x18001b087  mov     rdx, [rdi]
0x18001b08a  jmp     short loc_18001B08E
0x18001b08c  xor     edx, edx; lpAccountName
0x18001b08e  test    rbx, rbx
0x18001b091  jz      short loc_18001B098
0x18001b093  mov     rcx, [rbx]
0x18001b096  jmp     short loc_18001B09A
0x18001b098  xor     ecx, ecx; lpSystemName
0x18001b09a  lea     rax, [rbp+57h+arg_0]
0x18001b09e  mov     [rsp+0E0h+peUse], rax; peUse
0x18001b0a3  lea     rax, [rbp+57h+arg_8]
0x18001b0a7  mov     [rsp+0E0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18001b0ac  mov     [rsp+0E0h+ReferencedDomainName], 0; ReferencedDomainName
0x18001b0b5  lea     r9, [rbp+57h+cbSid]; cbSid
0x18001b0b9  xor     r8d, r8d; Sid
0x18001b0bc  call    cs:__imp_LookupAccountNameW
0x18001b0c2  test    eax, eax
0x18001b0c4  jz      short loc_18001B0D0
0x18001b0c6  mov     ebx, 8000FFFFh
0x18001b0cb  jmp     loc_18001B353
0x18001b0d0  call    cs:__imp_GetLastError
0x18001b0d6  cmp     eax, 7Ah ; 'z'
0x18001b0d9  jz      short loc_18001B130
0x18001b0db  call    cs:__imp_GetLastError
0x18001b0e1  mov     ebx, eax
0x18001b0e3  lea     rax, WPP_GLOBAL_Control
0x18001b0ea  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b0f1  cmp     rcx, rax
0x18001b0f4  jz      short loc_18001B11A
0x18001b0f6  test    byte ptr [rcx+1Ch], 80h
0x18001b0fa  jz      short loc_18001B11A
0x18001b0fc  cmp     byte ptr [rcx+19h], 2
0x18001b100  jb      short loc_18001B11A
0x18001b102  mov     edx, 18h
0x18001b107  mov     r9d, ebx
0x18001b10a  lea     r8, WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids
0x18001b111  mov     rcx, [rcx+10h]
0x18001b115  call    WPP_SF_d
0x18001b11a  test    ebx, ebx
0x18001b11c  jle     loc_18001B353
0x18001b122  movzx   ebx, bx
0x18001b125  or      ebx, 80070000h
0x18001b12b  jmp     loc_18001B353
0x18001b130  mov     ecx, [rbp+57h+cbSid]
0x18001b133  inc     ecx; unsigned __int64
0x18001b135  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001b13a  mov     r14, rax
0x18001b13d  mov     [rbp+57h+var_88], rax
0x18001b141  test    rax, rax
0x18001b144  jz      loc_18001B407
0x18001b14a  mov     edx, [rbp+57h+arg_8]; int
0x18001b14d  lea     eax, [rdx+1]
0x18001b150  mov     [rbp+57h+arg_8], eax
0x18001b153  lea     rcx, [rbp+57h+bstrString]; this
0x18001b157  call    ??0CComBSTR@ATL@@QEAA@H@Z; ATL::CComBSTR::CComBSTR(int)
0x18001b15c  mov     rsi, [rbp+57h+bstrString]
0x18001b160  test    rdi, rdi
0x18001b163  jz      short loc_18001B16A
0x18001b165  mov     rdx, [rdi]
0x18001b168  jmp     short loc_18001B16C
0x18001b16a  xor     edx, edx; lpAccountName
0x18001b16c  test    rbx, rbx
0x18001b16f  jz      short loc_18001B176
0x18001b171  mov     rcx, [rbx]
0x18001b174  jmp     short loc_18001B178
0x18001b176  xor     ecx, ecx; lpSystemName
0x18001b178  lea     rax, [rbp+57h+arg_0]
0x18001b17c  mov     [rsp+0E0h+peUse], rax; peUse
0x18001b181  lea     rax, [rbp+57h+arg_8]
0x18001b185  mov     [rsp+0E0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18001b18a  mov     [rsp+0E0h+ReferencedDomainName], rsi; ReferencedDomainName
0x18001b18f  lea     r9, [rbp+57h+cbSid]; cbSid
0x18001b193  mov     r8, r14; Sid
0x18001b196  call    cs:__imp_LookupAccountNameW
0x18001b19c  test    eax, eax
0x18001b19e  jnz     short loc_18001B203
0x18001b1a0  call    cs:__imp_GetLastError
0x18001b1a6  mov     ebx, eax
0x18001b1a8  lea     rax, WPP_GLOBAL_Control
0x18001b1af  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b1b6  cmp     rcx, rax
0x18001b1b9  jz      short loc_18001B1DF
0x18001b1bb  test    byte ptr [rcx+1Ch], 80h
0x18001b1bf  jz      short loc_18001B1DF
0x18001b1c1  cmp     byte ptr [rcx+19h], 2
0x18001b1c5  jb      short loc_18001B1DF
0x18001b1c7  mov     edx, 1Ah
0x18001b1cc  mov     r9d, ebx
0x18001b1cf  lea     r8, WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids
0x18001b1d6  mov     rcx, [rcx+10h]
0x18001b1da  call    WPP_SF_d
0x18001b1df  test    ebx, ebx
0x18001b1e1  jle     short loc_18001B1EC
0x18001b1e3  movzx   ebx, bx
0x18001b1e6  or      ebx, 80070000h
0x18001b1ec  mov     rcx, rsi; bstrString
0x18001b1ef  call    cs:__imp_SysFreeString
0x18001b1f5  nop
0x18001b1f6  mov     rcx, r14; Block
0x18001b1f9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001b1fe  jmp     loc_18001B353
0x18001b203  mov     eax, [rbp+57h+arg_0]
0x18001b206  cmp     eax, 3
0x18001b209  jz      loc_18001B308
0x18001b20f  test    eax, eax
0x18001b211  jle     loc_18001B308
0x18001b217  cmp     eax, 6
0x18001b21a  jge     loc_18001B308
0x18001b220  mov     rbx, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x18001b227  mov     rcx, rbx; lpCriticalSection
0x18001b22a  call    cs:__imp_EnterCriticalSection
0x18001b230  mov     rcx, [r15]
0x18001b233  add     rcx, 20h ; ' '
0x18001b237  mov     rdx, r14
0x18001b23a  call    ??4?$AutoVectorPtr@E@wmi@@QEAAAEAV01@PEAE@Z; wmi::AutoVectorPtr<uchar>::operator=(uchar *)
0x18001b23f  mov     rcx, [r15]
0x18001b242  mov     eax, [rbp+57h+arg_0]
0x18001b245  mov     [rcx+28h], eax
0x18001b248  mov     rcx, rbx; lpCriticalSection
0x18001b24b  call    cs:__imp_LeaveCriticalSection
0x18001b251  mov     rcx, rsi; bstrString
0x18001b254  call    cs:__imp_SysFreeString
0x18001b25a  nop
0x18001b25b  xor     ecx, ecx; Block
0x18001b25d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001b262  nop
0x18001b263  lea     rcx, [rbp+57h+var_98]; this
0x18001b267  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18001b26c  nop
0x18001b26d  lea     rcx, [rbp+57h+var_A0]; this
0x18001b271  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18001b276  mov     r8, [r15]
0x18001b279  lea     rcx, [r8+18h]
0x18001b27d  call    ??7_bstr_t@@QEBA_NXZ; _bstr_t::operator!(void)
0x18001b282  test    al, al
0x18001b284  jnz     short loc_18001B29E
0x18001b286  lea     rcx, [r8+10h]
0x18001b28a  call    ??7_bstr_t@@QEBA_NXZ; _bstr_t::operator!(void)
0x18001b28f  test    al, al
0x18001b291  jnz     short loc_18001B29E
0x18001b293  cmp     dword ptr [r8+28h], 8
0x18001b298  jnz     loc_18001B3EE
0x18001b29e  mov     dword ptr [rbp+57h+bstrString], 8
0x18001b2a5  mov     [rbp+57h+var_98], 0
0x18001b2ad  mov     [rbp+57h+var_A0], 0
0x18001b2b5  mov     [rbp+57h+var_90], 0
0x18001b2bd  mov     r9, r14; void *
0x18001b2c0  lea     r8, [rbp+57h+bstrString]; enum _SID_NAME_USE *
0x18001b2c4  lea     rdx, [rbp+57h+var_A0]; struct _bstr_t *
0x18001b2c8  lea     rcx, [rbp+57h+var_98]; struct _bstr_t *
0x18001b2cc  call    ?LookupUserSid@User@@CAHAEAV_bstr_t@@0AEAW4_SID_NAME_USE@@PEAX@Z; User::LookupUserSid(_bstr_t &,_bstr_t &,_SID_NAME_USE &,void *)
0x18001b2d1  test    eax, eax
0x18001b2d3  jnz     loc_18001B36D
0x18001b2d9  call    cs:__imp_GetLastError
0x18001b2df  mov     ebx, eax
0x18001b2e1  test    eax, eax
0x18001b2e3  jle     short loc_18001B2EE
0x18001b2e5  movzx   ebx, ax
0x18001b2e8  or      ebx, 80070000h
0x18001b2ee  lea     rcx, [rbp+57h+var_90]; this
0x18001b2f2  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18001b2f7  nop
0x18001b2f8  lea     rcx, [rbp+57h+var_A0]; this
0x18001b2fc  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18001b301  nop
0x18001b302  lea     rcx, [rbp+57h+var_98]
0x18001b306  jmp     short loc_18001B361
0x18001b308  lea     rax, WPP_GLOBAL_Control
0x18001b30f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b316  cmp     rcx, rax
0x18001b319  jz      short loc_18001B33C
0x18001b31b  test    byte ptr [rcx+1Ch], 80h
0x18001b31f  jz      short loc_18001B33C
0x18001b321  cmp     byte ptr [rcx+19h], 2
0x18001b325  jb      short loc_18001B33C
0x18001b327  mov     edx, 1Bh
0x18001b32c  lea     r8, WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids
0x18001b333  mov     rcx, [rcx+10h]
0x18001b337  call    WPP_SF_
0x18001b33c  mov     rcx, rsi; bstrString
0x18001b33f  call    cs:__imp_SysFreeString
0x18001b345  nop
0x18001b346  mov     rcx, r14; Block
0x18001b349  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001b34e  mov     ebx, 80070057h
0x18001b353  lea     rcx, [rbp+57h+var_98]; this
0x18001b357  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18001b35c  nop
0x18001b35d  lea     rcx, [rbp+57h+var_A0]; this
0x18001b361  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18001b366  mov     eax, ebx
0x18001b368  jmp     loc_18001B3F7
0x18001b36d  lea     r8, [rbp+57h+var_A0]; struct _bstr_t *
0x18001b371  lea     rdx, [rbp+57h+var_98]; struct _bstr_t *
0x18001b375  lea     rcx, [rbp+57h+var_90]; struct _bstr_t *
  ... truncated ...
```
