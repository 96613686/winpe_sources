# User::UpdateEntry(void)

- ea: `0x18001c3ac`
- end: `0x18001c954`
- name: `?UpdateEntry@User@@AEBAJXZ`
- size: `1448`
- prototype: `__int64 __fastcall(User *__hidden this)`
- caller_count: `4`
- callee_count: `18`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180003cec`
- `0x180005efc`
- `0x18001acc4`
- `0x18001be88`

## callees

- `0x1800013b8`
- `0x180003600`
- `0x180003f7c`
- `0x180003fb8`
- `0x1800050d0`
- `0x180005184`
- `0x180005224`
- `0x180007988`
- `0x180007994`
- `0x180008c4c`
- `0x18000a008`
- `0x18000cf80`
- `0x180010570`
- `0x18001822c`
- `0x18001aeec`
- `0x18001bf80`
- `0x18001c3ac`
- `0x18001c95c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c415`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c6fe`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c87a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c415`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c6fe`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c87a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c522`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c725`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c8c2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c522`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c725`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c8c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c586`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c597`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c668`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c7bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c586`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c597`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c668`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c7bf`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c6bd`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c734`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c82b`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c6bd`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c734`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c82b`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x18001c56c`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x18001c658`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x18001c56c`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x18001c658`

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
  int v10; // r9d
  __int64 v11; // rax
  _QWORD *v12; // rcx
  _QWORD *v13; // rcx
  void **v14; // rcx
  void *v15; // rax
  const WCHAR **v16; // rdi
  const WCHAR *v17; // rdx
  const WCHAR *v18; // rcx
  signed int LastError; // ebx
  int v20; // edx
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
  __int64 v33; // [rsp+50h] [rbp-39h] BYREF
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
      v7 = _bstr_t::_Compare((_bstr_t *)(*(_QWORD *)this + 24LL), (const struct _bstr_t *)&v33);
      v8 = *(_QWORD *)this;
      if ( v7 )
      {
        _bstr_t::operator=(&v31, v8 + 8);
      }
      else
      {
        _bstr_t::operator=(&v31, v8 + 16);
        _bstr_t::operator=(&v32, &v33);
        v4 = v32;
      }
      if ( ((unsigned __int8)_bstr_t::operator!(*(_QWORD *)this + 24LL)
         || (unsigned __int8)_bstr_t::operator!(v9 + 16)
         || (unsigned __int8)_bstr_t::operator!(v9 + 8))
        && (unsigned int)dword_18005F170 > 4 )
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
          (_DWORD)v14,
          (unsigned int)byte_180057AB1,
          v9,
          v10,
          (__int64)&v34,
          (__int64)&v36,
          (__int64)&v35,
          (__int64)&bstrString);
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
      wmi::AutoVectorPtr<unsigned char>::operator=(*(_QWORD *)this + 32LL, v3);
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
    _bstr_t::operator=(*(_QWORD *)this + 16LL, &v31);
    _bstr_t::operator=(*(_QWORD *)this + 24LL, &v32);
    _bstr_t::operator=(*(_QWORD *)this + 8LL, &v33);
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
0x18001c3ac  push    rbp
0x18001c3ae  push    rbx
0x18001c3af  push    rsi
0x18001c3b0  push    rdi
0x18001c3b1  push    r14
0x18001c3b3  push    r15
0x18001c3b5  lea     rbp, [rsp-2Fh]
0x18001c3ba  sub     rsp, 0B8h
0x18001c3c1  mov     r15, rcx
0x18001c3c4  mov     rcx, [rcx]
0x18001c3c7  test    rcx, rcx
0x18001c3ca  jz      loc_18001C8F0
0x18001c3d0  mov     r14, [rcx+20h]
0x18001c3d4  test    r14, r14
0x18001c3d7  jnz     loc_18001C75C
0x18001c3dd  add     rcx, 8
0x18001c3e1  call    ??7_bstr_t@@QEBA_NXZ; _bstr_t::operator!(void)
0x18001c3e6  test    al, al
0x18001c3e8  jnz     loc_18001C8F0
0x18001c3ee  mov     [rbp+57h+arg_0], 8
0x18001c3f5  mov     [rbp+57h+arg_8], r14d
0x18001c3f9  mov     [rbp+57h+cbSid], r14d
0x18001c3fd  mov     [rbp+57h+var_A0], r14
0x18001c401  xor     ebx, ebx
0x18001c403  mov     [rbp+57h+var_98], rbx
0x18001c407  mov     rdi, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x18001c40e  mov     [rbp+57h+bstrString], rdi
0x18001c412  mov     rcx, rdi; lpCriticalSection
0x18001c415  call    cs:__imp_EnterCriticalSection
0x18001c41c  nop     dword ptr [rax+rax+00h]
0x18001c421  nop
0x18001c422  call    ?GetComputerNameW@User@@CAPEBGXZ; User::GetComputerNameW(void)
0x18001c427  mov     rdx, rax; unsigned __int16 *
0x18001c42a  lea     rcx, [rbp+57h+var_90]; this
0x18001c42e  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18001c433  mov     rcx, [r15]
0x18001c436  add     rcx, 18h; this
0x18001c43a  lea     rdx, [rbp+57h+var_90]; struct _bstr_t *
0x18001c43e  call    ?_Compare@_bstr_t@@AEBAHAEBV1@@Z; _bstr_t::_Compare(_bstr_t const &)
0x18001c443  mov     rdx, [r15]
0x18001c446  lea     rcx, [rbp+57h+var_A0]
0x18001c44a  test    eax, eax
0x18001c44c  jnz     short loc_18001C46A
0x18001c44e  add     rdx, 10h
0x18001c452  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x18001c457  lea     rdx, [rbp+57h+var_90]
0x18001c45b  lea     rcx, [rbp+57h+var_98]
0x18001c45f  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x18001c464  mov     rbx, [rbp+57h+var_98]
0x18001c468  jmp     short loc_18001C473
0x18001c46a  add     rdx, 8
0x18001c46e  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x18001c473  mov     r8, [r15]
0x18001c476  lea     rcx, [r8+18h]
0x18001c47a  call    ??7_bstr_t@@QEBA_NXZ; _bstr_t::operator!(void)
0x18001c47f  test    al, al
0x18001c481  jnz     short loc_18001C49D
0x18001c483  lea     rcx, [r8+10h]
0x18001c487  call    ??7_bstr_t@@QEBA_NXZ; _bstr_t::operator!(void)
0x18001c48c  test    al, al
0x18001c48e  jnz     short loc_18001C49D
0x18001c490  lea     rcx, [r8+8]
0x18001c494  call    ??7_bstr_t@@QEBA_NXZ; _bstr_t::operator!(void)
0x18001c499  test    al, al
0x18001c49b  jz      short loc_18001C515
0x18001c49d  mov     eax, cs:dword_18005F170
0x18001c4a3  cmp     eax, 4
0x18001c4a6  jbe     short loc_18001C515
0x18001c4a8  mov     eax, [rbp+57h+arg_0]
0x18001c4ab  mov     dword ptr [rbp+57h+bstrString], eax
0x18001c4ae  mov     rax, [r15]
0x18001c4b1  mov     rcx, [rax+8]
0x18001c4b5  test    rcx, rcx
0x18001c4b8  jz      short loc_18001C4BD
0x18001c4ba  mov     rcx, [rcx]
0x18001c4bd  mov     [rbp+57h+var_80], rcx
0x18001c4c1  mov     rcx, [rax+10h]
0x18001c4c5  test    rcx, rcx
0x18001c4c8  jz      short loc_18001C4CD
0x18001c4ca  mov     rcx, [rcx]
0x18001c4cd  mov     [rbp+57h+var_78], rcx
0x18001c4d1  mov     rcx, [rax+18h]
0x18001c4d5  test    rcx, rcx
0x18001c4d8  jz      short loc_18001C4DF
0x18001c4da  mov     rax, [rcx]
0x18001c4dd  jmp     short loc_18001C4E1
0x18001c4df  xor     eax, eax
0x18001c4e1  mov     [rbp+57h+var_88], rax
0x18001c4e5  lea     rax, [rbp+57h+bstrString]
0x18001c4e9  mov     [rsp+0E0h+var_A8], rax
0x18001c4ee  lea     rax, [rbp+57h+var_80]
0x18001c4f2  mov     [rsp+0E0h+peUse], rax
0x18001c4f7  lea     rax, [rbp+57h+var_78]
0x18001c4fb  mov     [rsp+0E0h+cchReferencedDomainName], rax
0x18001c500  lea     rax, [rbp+57h+var_88]
0x18001c504  mov     [rsp+0E0h+ReferencedDomainName], rax
0x18001c509  lea     rdx, byte_180057AB1
0x18001c510  call    ??$Write@U?$_tlgWrapSz@G@@U1@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@33AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18001c515  lea     rcx, [rbp+57h+var_90]; this
0x18001c519  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18001c51e  nop
0x18001c51f  mov     rcx, rdi; lpCriticalSection
0x18001c522  call    cs:__imp_LeaveCriticalSection
0x18001c529  nop     dword ptr [rax+rax+00h]
0x18001c52e  mov     rdi, [rbp+57h+var_A0]
0x18001c532  test    rdi, rdi
0x18001c535  jz      short loc_18001C53C
0x18001c537  mov     rdx, [rdi]
0x18001c53a  jmp     short loc_18001C53E
0x18001c53c  xor     edx, edx; lpAccountName
0x18001c53e  test    rbx, rbx
0x18001c541  jz      short loc_18001C548
0x18001c543  mov     rcx, [rbx]
0x18001c546  jmp     short loc_18001C54A
0x18001c548  xor     ecx, ecx; lpSystemName
0x18001c54a  lea     rax, [rbp+57h+arg_0]
0x18001c54e  mov     [rsp+0E0h+peUse], rax; peUse
0x18001c553  lea     rax, [rbp+57h+arg_8]
0x18001c557  mov     [rsp+0E0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18001c55c  mov     [rsp+0E0h+ReferencedDomainName], 0; ReferencedDomainName
0x18001c565  lea     r9, [rbp+57h+cbSid]; cbSid
0x18001c569  xor     r8d, r8d; Sid
0x18001c56c  call    cs:__imp_LookupAccountNameW
0x18001c573  nop     dword ptr [rax+rax+00h]
0x18001c578  test    eax, eax
0x18001c57a  jz      short loc_18001C586
0x18001c57c  mov     ebx, 8000FFFFh
0x18001c581  jmp     loc_18001C845
0x18001c586  call    cs:__imp_GetLastError
0x18001c58d  nop     dword ptr [rax+rax+00h]
0x18001c592  cmp     eax, 7Ah ; 'z'
0x18001c595  jz      short loc_18001C5F2
0x18001c597  call    cs:__imp_GetLastError
0x18001c59e  nop     dword ptr [rax+rax+00h]
0x18001c5a3  mov     ebx, eax
0x18001c5a5  lea     rax, WPP_GLOBAL_Control
0x18001c5ac  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c5b3  cmp     rcx, rax
0x18001c5b6  jz      short loc_18001C5DC
0x18001c5b8  test    byte ptr [rcx+1Ch], 80h
0x18001c5bc  jz      short loc_18001C5DC
0x18001c5be  cmp     byte ptr [rcx+19h], 2
0x18001c5c2  jb      short loc_18001C5DC
0x18001c5c4  mov     edx, 18h
0x18001c5c9  mov     r9d, ebx
0x18001c5cc  lea     r8, WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids
0x18001c5d3  mov     rcx, [rcx+10h]
0x18001c5d7  call    WPP_SF_d
0x18001c5dc  test    ebx, ebx
0x18001c5de  jle     loc_18001C845
0x18001c5e4  movzx   ebx, bx
0x18001c5e7  or      ebx, 80070000h
0x18001c5ed  jmp     loc_18001C845
0x18001c5f2  mov     ecx, [rbp+57h+cbSid]
0x18001c5f5  inc     ecx; unsigned __int64
0x18001c5f7  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001c5fc  mov     r14, rax
0x18001c5ff  mov     [rbp+57h+var_88], rax
0x18001c603  test    rax, rax
0x18001c606  jz      loc_18001C906
0x18001c60c  mov     edx, [rbp+57h+arg_8]; int
0x18001c60f  lea     eax, [rdx+1]
0x18001c612  mov     [rbp+57h+arg_8], eax
0x18001c615  lea     rcx, [rbp+57h+bstrString]; this
0x18001c619  call    ??0CComBSTR@ATL@@QEAA@H@Z; ATL::CComBSTR::CComBSTR(int)
0x18001c61e  mov     rsi, [rbp+57h+bstrString]
0x18001c622  test    rdi, rdi
0x18001c625  jz      short loc_18001C62C
0x18001c627  mov     rdx, [rdi]
0x18001c62a  jmp     short loc_18001C62E
0x18001c62c  xor     edx, edx; lpAccountName
0x18001c62e  test    rbx, rbx
0x18001c631  jz      short loc_18001C638
0x18001c633  mov     rcx, [rbx]
0x18001c636  jmp     short loc_18001C63A
0x18001c638  xor     ecx, ecx; lpSystemName
0x18001c63a  lea     rax, [rbp+57h+arg_0]
0x18001c63e  mov     [rsp+0E0h+peUse], rax; peUse
0x18001c643  lea     rax, [rbp+57h+arg_8]
0x18001c647  mov     [rsp+0E0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18001c64c  mov     [rsp+0E0h+ReferencedDomainName], rsi; ReferencedDomainName
0x18001c651  lea     r9, [rbp+57h+cbSid]; cbSid
0x18001c655  mov     r8, r14; Sid
0x18001c658  call    cs:__imp_LookupAccountNameW
0x18001c65f  nop     dword ptr [rax+rax+00h]
0x18001c664  test    eax, eax
0x18001c666  jnz     short loc_18001C6D7
0x18001c668  call    cs:__imp_GetLastError
0x18001c66f  nop     dword ptr [rax+rax+00h]
0x18001c674  mov     ebx, eax
0x18001c676  lea     rax, WPP_GLOBAL_Control
0x18001c67d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c684  cmp     rcx, rax
0x18001c687  jz      short loc_18001C6AD
0x18001c689  test    byte ptr [rcx+1Ch], 80h
0x18001c68d  jz      short loc_18001C6AD
0x18001c68f  cmp     byte ptr [rcx+19h], 2
0x18001c693  jb      short loc_18001C6AD
0x18001c695  mov     edx, 1Ah
0x18001c69a  mov     r9d, ebx
0x18001c69d  lea     r8, WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids
0x18001c6a4  mov     rcx, [rcx+10h]
0x18001c6a8  call    WPP_SF_d
0x18001c6ad  test    ebx, ebx
0x18001c6af  jle     short loc_18001C6BA
0x18001c6b1  movzx   ebx, bx
0x18001c6b4  or      ebx, 80070000h
0x18001c6ba  mov     rcx, rsi; bstrString
0x18001c6bd  call    cs:__imp_SysFreeString
0x18001c6c4  nop     dword ptr [rax+rax+00h]
0x18001c6c9  nop
0x18001c6ca  mov     rcx, r14; Block
0x18001c6cd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001c6d2  jmp     loc_18001C845
0x18001c6d7  mov     eax, [rbp+57h+arg_0]
0x18001c6da  cmp     eax, 3
0x18001c6dd  jz      loc_18001C7F4
0x18001c6e3  test    eax, eax
0x18001c6e5  jle     loc_18001C7F4
0x18001c6eb  cmp     eax, 6
0x18001c6ee  jge     loc_18001C7F4
0x18001c6f4  mov     rbx, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x18001c6fb  mov     rcx, rbx; lpCriticalSection
0x18001c6fe  call    cs:__imp_EnterCriticalSection
0x18001c705  nop     dword ptr [rax+rax+00h]
0x18001c70a  mov     rcx, [r15]
0x18001c70d  add     rcx, 20h ; ' '
0x18001c711  mov     rdx, r14
0x18001c714  call    ??4?$AutoVectorPtr@E@wmi@@QEAAAEAV01@PEAE@Z; wmi::AutoVectorPtr<uchar>::operator=(uchar *)
0x18001c719  mov     rcx, [r15]
0x18001c71c  mov     eax, [rbp+57h+arg_0]
0x18001c71f  mov     [rcx+28h], eax
0x18001c722  mov     rcx, rbx; lpCriticalSection
0x18001c725  call    cs:__imp_LeaveCriticalSection
0x18001c72c  nop     dword ptr [rax+rax+00h]
0x18001c731  mov     rcx, rsi; bstrString
0x18001c734  call    cs:__imp_SysFreeString
0x18001c73b  nop     dword ptr [rax+rax+00h]
0x18001c740  nop
0x18001c741  xor     ecx, ecx; Block
0x18001c743  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001c748  nop
0x18001c749  lea     rcx, [rbp+57h+var_98]; this
0x18001c74d  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18001c752  nop
0x18001c753  lea     rcx, [rbp+57h+var_A0]; this
0x18001c757  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18001c75c  mov     r8, [r15]
0x18001c75f  lea     rcx, [r8+18h]
0x18001c763  call    ??7_bstr_t@@QEBA_NXZ; _bstr_t::operator!(void)
0x18001c768  test    al, al
0x18001c76a  jnz     short loc_18001C784
0x18001c76c  lea     rcx, [r8+10h]
0x18001c770  call    ??7_bstr_t@@QEBA_NXZ; _bstr_t::operator!(void)
0x18001c775  test    al, al
0x18001c777  jnz     short loc_18001C784
0x18001c779  cmp     dword ptr [r8+28h], 8
0x18001c77e  jnz     loc_18001C8EC
0x18001c784  mov     dword ptr [rbp+57h+bstrString], 8
0x18001c78b  mov     [rbp+57h+var_98], 0
0x18001c793  mov     [rbp+57h+var_A0], 0
0x18001c79b  mov     [rbp+57h+var_90], 0
0x18001c7a3  mov     r9, r14; void *
0x18001c7a6  lea     r8, [rbp+57h+bstrString]; enum _SID_NAME_USE *
0x18001c7aa  lea     rdx, [rbp+57h+var_A0]; struct _bstr_t *
0x18001c7ae  lea     rcx, [rbp+57h+var_98]; struct _bstr_t *
0x18001c7b2  call    ?LookupUserSid@User@@CAHAEAV_bstr_t@@0AEAW4_SID_NAME_USE@@PEAX@Z; User::LookupUserSid(_bstr_t &,_bstr_t &,_SID_NAME_USE &,void *)
0x18001c7b7  test    eax, eax
0x18001c7b9  jnz     loc_18001C85F
0x18001c7bf  call    cs:__imp_GetLastError
0x18001c7c6  nop     dword ptr [rax+rax+00h]
0x18001c7cb  mov     ebx, eax
0x18001c7cd  test    eax, eax
0x18001c7cf  jle     short loc_18001C7DA
0x18001c7d1  movzx   ebx, ax
0x18001c7d4  or      ebx, 80070000h
0x18001c7da  lea     rcx, [rbp+57h+var_90]; this
0x18001c7de  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18001c7e3  nop
0x18001c7e4  lea     rcx, [rbp+57h+var_A0]; this
0x18001c7e8  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18001c7ed  nop
0x18001c7ee  lea     rcx, [rbp+57h+var_98]
0x18001c7f2  jmp     short loc_18001C853
0x18001c7f4  lea     rax, WPP_GLOBAL_Control
0x18001c7fb  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c802  cmp     rcx, rax
0x18001c805  jz      short loc_18001C828
0x18001c807  test    byte ptr [rcx+1Ch], 80h
0x18001c80b  jz      short loc_18001C828
0x18001c80d  cmp     byte ptr [rcx+19h], 2
0x18001c811  jb      short loc_18001C828
0x18001c813  mov     edx, 1Bh
0x18001c818  lea     r8, WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids
0x18001c81f  mov     rcx, [rcx+10h]
0x18001c823  call    WPP_SF_
0x18001c828  mov     rcx, rsi; bstrString
0x18001c82b  call    cs:__imp_SysFreeString
0x18001c832  nop     dword ptr [rax+rax+00h]
0x18001c837  nop
  ... truncated ...
```
