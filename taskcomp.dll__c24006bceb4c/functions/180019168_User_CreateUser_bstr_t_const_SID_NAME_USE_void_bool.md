# User::CreateUser(_bstr_t const &,_SID_NAME_USE,void *,bool)

- ea: `0x180019168`
- end: `0x180019536`
- name: `?CreateUser@User@@SA?AV1@AEBV_bstr_t@@W4_SID_NAME_USE@@PEAX_N@Z`
- size: `974`
- prototype: `__int64 __fastcall(__int64, __int64 **, enum _SID_NAME_USE, struct _RTL_CRITICAL_SECTION *, enum _SID_NAME_USE)`
- caller_count: `1`
- callee_count: `25`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1800177d0`

## callees

- `0x1800010b0`
- `0x18000116c`
- `0x1800014b4`
- `0x1800014c4`
- `0x180003af0`
- `0x180003b3c`
- `0x180003dac`
- `0x180004e50`
- `0x180004eec`
- `0x180004f28`
- `0x1800050fc`
- `0x1800058d0`
- `0x180007488`
- `0x18000878c`
- `0x180009ac0`
- `0x18000e4d8`
- `0x18001724c`
- `0x180018604`
- `0x18001862c`
- `0x180018808`
- `0x180019168`
- `0x180019e44`
- `0x180019f78`
- `0x18001a154`
- `0x18001ab20`

## import_xrefs

- `msvcrt!wcschr` at `0x180019295`
- `msvcrt!wcschr` at `0x180019295`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001939e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001939e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001944f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001944f`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800191aa`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800191df`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180019214`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800191aa`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800191df`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180019214`
- `OLEAUT32!__imp_SysFreeString` at `0x180019388`
- `OLEAUT32!__imp_SysFreeString` at `0x180019388`

## pseudocode

```c
__int64 __fastcall User::CreateUser(
        __int64 a1,
        __int64 **a2,
        enum _SID_NAME_USE a3,
        struct _RTL_CRITICAL_SECTION *a4,
        enum _SID_NAME_USE a5)
{
  __int64 v9; // rsi
  __int64 LocalSystem; // rax
  BOOL v11; // ebx
  __int64 LocalService; // rax
  BOOL v13; // ebx
  __int64 NetworkService; // rax
  BOOL v15; // ebx
  __int64 *v16; // rax
  const wchar_t *v17; // rcx
  const unsigned __int16 *v18; // r12
  unsigned __int16 *v19; // rax
  __int64 v20; // r8
  __int64 v21; // r9
  unsigned __int16 *v22; // rbx
  __int64 v23; // rcx
  __int64 v24; // rcx
  _bstr_t *v25; // rax
  struct _RTL_CRITICAL_SECTION *v26; // rbx
  User::UserEntry *v27; // rax
  __int64 v28; // rdx
  User::UserEntry *v29; // rax
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 v33; // rax
  _QWORD *v34; // rax
  _QWORD *v35; // r8
  _QWORD *v36; // r9
  _QWORD *v37; // r10
  bool v38; // [rsp+30h] [rbp-91h]
  unsigned __int16 *v39; // [rsp+50h] [rbp-71h] BYREF
  __int64 v40; // [rsp+58h] [rbp-69h] BYREF
  __int64 v41; // [rsp+60h] [rbp-61h] BYREF
  __int64 v42; // [rsp+68h] [rbp-59h] BYREF
  LPCRITICAL_SECTION v43; // [rsp+70h] [rbp-51h] BYREF
  _QWORD v44[2]; // [rsp+78h] [rbp-49h] BYREF
  __int64 v45; // [rsp+88h] [rbp-39h] BYREF
  __int64 v46; // [rsp+90h] [rbp-31h] BYREF
  _BYTE pExceptionObject[120]; // [rsp+98h] [rbp-29h] BYREF

  LODWORD(v9) = 0;
  v42 = 0;
  v41 = 0;
  LocalSystem = User::GetLocalSystem(&v40);
  v11 = EqualSid(*(PSID *)(*(_QWORD *)LocalSystem + 32LL), a4);
  wmi::AutoRef<User::UserEntry>::Release(&v40);
  if ( v11 )
  {
    User::GetLocalSystem(a1);
  }
  else
  {
    LocalService = User::GetLocalService(&v40);
    v13 = EqualSid(*(PSID *)(*(_QWORD *)LocalService + 32LL), a4);
    wmi::AutoRef<User::UserEntry>::Release(&v40);
    if ( v13 )
    {
      User::GetLocalService(a1);
    }
    else
    {
      NetworkService = User::GetNetworkService(&v40);
      v15 = EqualSid(*(PSID *)(*(_QWORD *)NetworkService + 32LL), a4);
      wmi::AutoRef<User::UserEntry>::Release(&v40);
      if ( v15 )
      {
        User::GetNetworkService(a1);
      }
      else
      {
        v39 = 0;
        _bstr_t::operator=((_bstr_t *)&v42, (__int64)&v39);
        _bstr_t::~_bstr_t((_bstr_t *)&v39);
        v39 = 0;
        _bstr_t::operator=((_bstr_t *)&v41, (__int64)&v39);
        _bstr_t::~_bstr_t((_bstr_t *)&v39);
        if ( !(unsigned __int8)_bstr_t::operator!(a2) )
        {
          v16 = *a2;
          if ( *a2 )
          {
            v17 = (const wchar_t *)*v16;
            v18 = (const unsigned __int16 *)*v16;
          }
          else
          {
            v17 = 0;
            v18 = 0;
          }
          v19 = wcschr(v17, 0x5Cu);
          v22 = v19;
          v23 = (unsigned int)dword_18005D170;
          if ( (unsigned int)dword_18005D170 > 4 )
          {
            a5 = a3;
            v24 = 0;
            if ( *a2 )
              v24 = **a2;
            v40 = v24;
            v39 = v19;
            v44[0] = v18;
            v43 = a4;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSid<_SID>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
              v24,
              (__int64)&byte_180055C47,
              v20,
              v21,
              (__int64)&v43,
              v44,
              &v39,
              &v40);
          }
          if ( !v22 || (v9 = v22 - v18, ++v22 == 0) || !*v22 )
          {
            if ( (unsigned int)dword_18005D170 > 4 )
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
                v23,
                (unsigned __int8 *)&word_180055C16);
          }
          _bstr_t::operator=(&v42, v22);
          if ( (_DWORD)v9 )
          {
            ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v39, v9);
            StringCchCopyNW(v39, (unsigned int)(v9 + 1), v18, (unsigned int)v9);
            v25 = _bstr_t::_bstr_t((_bstr_t *)&v43, v39);
            _bstr_t::operator=((_bstr_t *)&v41, (__int64)v25);
            _bstr_t::~_bstr_t((_bstr_t *)&v43);
            SysFreeString(0);
          }
        }
        v26 = User::s_cs;
        v43 = User::s_cs;
        EnterCriticalSection(User::s_cs);
        User::LookupUser(&v39, a4);
        if ( v39 )
        {
          User::UpdateEntry(
            (User *)&v39,
            (const struct _bstr_t *)&v42,
            (const struct _bstr_t *)&v41,
            (const struct _bstr_t *)a2,
            a3,
            a4,
            v38);
          User::User(a1, &v39);
        }
        else
        {
          v27 = (User::UserEntry *)operator new(0x30u);
          v44[0] = v27;
          if ( v27 )
            v29 = User::UserEntry::UserEntry(
                    v27,
                    v28,
                    (const struct _bstr_t *)&v42,
                    (const struct _bstr_t *)&v41,
                    (const struct _bstr_t *)a2,
                    a3,
                    a4);
          else
            v29 = 0;
          if ( !v29 )
          {
            if ( (unsigned int)dword_18005D170 > 2 && (unsigned __int8)tlgKeywordOn() )
            {
              a5 = a3;
              v31 = _bstr_t::operator unsigned short const *(a2);
              _tlgWrapSid<_SID>::_tlgWrapSid<_SID>(v44, v31);
              v32 = _bstr_t::operator unsigned short const *(&v41);
              _tlgWrapSid<_SID>::_tlgWrapSid<_SID>(&v40, v32);
              v33 = _bstr_t::operator unsigned short const *(&v42);
              _tlgWrapSid<_SID>::_tlgWrapSid<_SID>(&v45, v33);
              v34 = _tlgWrapSid<_SID>::_tlgWrapSid<_SID>(&v46, (__int64)a4);
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSid<_SID>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
                (__int64)&a5,
                (__int64)&dword_180055BAC,
                (__int64)v35,
                (__int64)v36,
                (__int64)v34,
                v35,
                v36,
                v37);
            }
            wmi::OutOfMemoryException::OutOfMemoryException((wmi::OutOfMemoryException *)pExceptionObject);
            throw (wmi::OutOfMemoryException *)pExceptionObject;
          }
          v40 = (__int64)v29;
          User::UserEntry::AddRef(v29);
          User::User(a1, &v40);
          wmi::AutoRef<User::UserEntry>::Release(&v40);
        }
        wmi::AutoRef<User::UserEntry>::Release(&v39);
        LeaveCriticalSection(v26);
      }
    }
  }
  _bstr_t::~_bstr_t((_bstr_t *)&v41);
  _bstr_t::~_bstr_t((_bstr_t *)&v42);
  return a1;
}

```

## disassembly

```asm
0x180019168  push    rbp
0x18001916a  push    rbx
0x18001916b  push    rsi
0x18001916c  push    rdi
0x18001916d  push    r12
0x18001916f  push    r13
0x180019171  push    r14
0x180019173  push    r15
0x180019175  lea     rbp, [rsp-17h]
0x18001917a  sub     rsp, 0D8h
0x180019181  mov     r14, r9
0x180019184  mov     r13d, r8d
0x180019187  mov     r15, rdx
0x18001918a  mov     rdi, rcx
0x18001918d  xor     esi, esi
0x18001918f  mov     [rbp+4Fh+var_A8], rsi
0x180019193  mov     [rbp+4Fh+var_B0], rsi
0x180019197  lea     rcx, [rbp+4Fh+var_B8]
0x18001919b  call    ?GetLocalSystem@User@@SA?AV1@XZ; User::GetLocalSystem(void)
0x1800191a0  mov     rcx, [rax]
0x1800191a3  mov     rdx, r14; pSid2
0x1800191a6  mov     rcx, [rcx+20h]; pSid1
0x1800191aa  call    cs:__imp_EqualSid
0x1800191b0  mov     ebx, eax
0x1800191b2  lea     rcx, [rbp+4Fh+var_B8]
0x1800191b6  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x1800191bb  test    ebx, ebx
0x1800191bd  jz      short loc_1800191CC
0x1800191bf  mov     rcx, rdi
0x1800191c2  call    ?GetLocalSystem@User@@SA?AV1@XZ; User::GetLocalSystem(void)
0x1800191c7  jmp     loc_180019456
0x1800191cc  lea     rcx, [rbp+4Fh+var_B8]
0x1800191d0  call    ?GetLocalService@User@@SA?AV1@XZ; User::GetLocalService(void)
0x1800191d5  mov     rcx, [rax]
0x1800191d8  mov     rdx, r14; pSid2
0x1800191db  mov     rcx, [rcx+20h]; pSid1
0x1800191df  call    cs:__imp_EqualSid
0x1800191e5  mov     ebx, eax
0x1800191e7  lea     rcx, [rbp+4Fh+var_B8]
0x1800191eb  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x1800191f0  test    ebx, ebx
0x1800191f2  jz      short loc_180019201
0x1800191f4  mov     rcx, rdi
0x1800191f7  call    ?GetLocalService@User@@SA?AV1@XZ; User::GetLocalService(void)
0x1800191fc  jmp     loc_180019456
0x180019201  lea     rcx, [rbp+4Fh+var_B8]
0x180019205  call    ?GetNetworkService@User@@SA?AV1@XZ; User::GetNetworkService(void)
0x18001920a  mov     rcx, [rax]
0x18001920d  mov     rdx, r14; pSid2
0x180019210  mov     rcx, [rcx+20h]; pSid1
0x180019214  call    cs:__imp_EqualSid
0x18001921a  mov     ebx, eax
0x18001921c  lea     rcx, [rbp+4Fh+var_B8]
0x180019220  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x180019225  test    ebx, ebx
0x180019227  jz      short loc_180019236
0x180019229  mov     rcx, rdi
0x18001922c  call    ?GetNetworkService@User@@SA?AV1@XZ; User::GetNetworkService(void)
0x180019231  jmp     loc_180019456
0x180019236  mov     [rbp+4Fh+var_C0], rsi
0x18001923a  lea     rdx, [rbp+4Fh+var_C0]
0x18001923e  lea     rcx, [rbp+4Fh+var_A8]
0x180019242  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x180019247  lea     rcx, [rbp+4Fh+var_C0]; this
0x18001924b  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180019250  mov     [rbp+4Fh+var_C0], rsi
0x180019254  lea     rdx, [rbp+4Fh+var_C0]
0x180019258  lea     rcx, [rbp+4Fh+var_B0]
0x18001925c  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x180019261  lea     rcx, [rbp+4Fh+var_C0]; this
0x180019265  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18001926a  mov     rcx, r15
0x18001926d  call    ??7_bstr_t@@QEBA_NXZ; _bstr_t::operator!(void)
0x180019272  test    al, al
0x180019274  jnz     loc_180019390
0x18001927a  mov     rax, [r15]
0x18001927d  test    rax, rax
0x180019280  jz      short loc_18001928A
0x180019282  mov     rcx, [rax]
0x180019285  mov     r12, rcx
0x180019288  jmp     short loc_180019290
0x18001928a  mov     rcx, rsi; Str
0x18001928d  mov     r12, rsi
0x180019290  mov     edx, 5Ch ; '\'; Ch
0x180019295  call    cs:__imp_wcschr
0x18001929b  mov     rbx, rax
0x18001929e  mov     ecx, cs:dword_18005D170
0x1800192a4  cmp     ecx, 4
0x1800192a7  jbe     short loc_180019303
0x1800192a9  mov     [rbp+4Fh+arg_20], r13d
0x1800192ad  mov     rax, [r15]
0x1800192b0  xor     ecx, ecx
0x1800192b2  test    rax, rax
0x1800192b5  jz      short loc_1800192BA
0x1800192b7  mov     rcx, [rax]
0x1800192ba  mov     [rbp+4Fh+var_B8], rcx
0x1800192be  mov     [rbp+4Fh+var_C0], rbx
0x1800192c2  mov     [rbp+4Fh+var_98], r12
0x1800192c6  mov     [rbp+4Fh+var_A0], r14
0x1800192ca  lea     rax, [rbp+4Fh+arg_20]
0x1800192ce  mov     [rsp+110h+var_D0], rax
0x1800192d3  lea     rax, [rbp+4Fh+var_B8]
0x1800192d7  mov     [rsp+110h+var_D8], rax
0x1800192dc  lea     rax, [rbp+4Fh+var_C0]
0x1800192e0  mov     [rsp+110h+var_E0], rax; bool
0x1800192e5  lea     rax, [rbp+4Fh+var_98]
0x1800192e9  mov     qword ptr [rsp+110h+var_E8], rax
0x1800192ee  lea     rax, [rbp+4Fh+var_A0]
0x1800192f2  mov     qword ptr [rsp+110h+var_F0], rax
0x1800192f7  lea     rdx, byte_180055C47
0x1800192fe  call    ??$Write@U?$_tlgWrapSid@U_SID@@@@U?$_tlgWrapSz@G@@U2@U2@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSid@U_SID@@@@AEBU?$_tlgWrapSz@G@@44AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSid<_SID>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSid<_SID> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180019303  xor     eax, eax
0x180019305  test    rbx, rbx
0x180019308  jz      short loc_18001931E
0x18001930a  mov     rsi, rbx
0x18001930d  sub     rsi, r12
0x180019310  sar     rsi, 1
0x180019313  add     rbx, 2
0x180019317  jz      short loc_18001931E
0x180019319  cmp     [rbx], ax
0x18001931c  jnz     short loc_180019335
0x18001931e  mov     eax, cs:dword_18005D170
0x180019324  cmp     eax, 4
0x180019327  jbe     short loc_180019335
0x180019329  lea     rdx, word_180055C16
0x180019330  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180019335  mov     rdx, rbx
0x180019338  lea     rcx, [rbp+4Fh+var_A8]
0x18001933c  call    ??4_bstr_t@@QEAAAEAV0@PEBG@Z; _bstr_t::operator=(ushort const *)
0x180019341  test    esi, esi
0x180019343  jz      short loc_18001938E
0x180019345  mov     edx, esi; int
0x180019347  lea     rcx, [rbp+4Fh+var_C0]; this
0x18001934b  call    ??0CComBSTR@ATL@@QEAA@H@Z; ATL::CComBSTR::CComBSTR(int)
0x180019350  nop
0x180019351  mov     r9d, esi; unsigned __int64
0x180019354  lea     edx, [rsi+1]; unsigned __int64
0x180019357  mov     r8, r12; unsigned __int16 *
0x18001935a  mov     rcx, [rbp+4Fh+var_C0]; unsigned __int16 *
0x18001935e  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180019363  mov     rdx, [rbp+4Fh+var_C0]; unsigned __int16 *
0x180019367  lea     rcx, [rbp+4Fh+var_A0]; this
0x18001936b  call    ??0_bstr_t@@QEAA@PEAG_N@Z; _bstr_t::_bstr_t(ushort *,bool)
0x180019370  mov     rdx, rax
0x180019373  lea     rcx, [rbp+4Fh+var_B0]
0x180019377  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x18001937c  lea     rcx, [rbp+4Fh+var_A0]; this
0x180019380  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180019385  nop
0x180019386  xor     ecx, ecx; bstrString
0x180019388  call    cs:__imp_SysFreeString
0x18001938e  xor     esi, esi
0x180019390  mov     rbx, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x180019397  mov     [rbp+4Fh+var_A0], rbx
0x18001939b  mov     rcx, rbx; lpCriticalSection
0x18001939e  call    cs:__imp_EnterCriticalSection
0x1800193a4  nop
0x1800193a5  mov     rdx, r14
0x1800193a8  lea     rcx, [rbp+4Fh+var_C0]
0x1800193ac  call    ?LookupUser@User@@CA?AV1@PEAX@Z; User::LookupUser(void *)
0x1800193b1  nop
0x1800193b2  cmp     [rbp+4Fh+var_C0], rsi
0x1800193b6  jz      short loc_1800193E4
0x1800193b8  mov     qword ptr [rsp+110h+var_E8], r14; void *
0x1800193bd  mov     [rsp+110h+var_F0], r13d; enum _SID_NAME_USE
0x1800193c2  mov     r9, r15; struct _bstr_t *
0x1800193c5  lea     r8, [rbp+4Fh+var_B0]; struct _bstr_t *
0x1800193c9  lea     rdx, [rbp+4Fh+var_A8]; struct _bstr_t *
0x1800193cd  lea     rcx, [rbp+4Fh+var_C0]; this
0x1800193d1  call    ?UpdateEntry@User@@AEBAXAEBV_bstr_t@@00W4_SID_NAME_USE@@PEAX_N@Z; User::UpdateEntry(_bstr_t const &,_bstr_t const &,_bstr_t const &,_SID_NAME_USE,void *,bool)
0x1800193d6  lea     rdx, [rbp+4Fh+var_C0]
0x1800193da  mov     rcx, rdi
0x1800193dd  call    ??0User@@AEAA@AEBV?$AutoRef@UUserEntry@User@@@wmi@@@Z; User::User(wmi::AutoRef<User::UserEntry> const &)
0x1800193e2  jmp     short loc_180019442
0x1800193e4  mov     ecx, 30h ; '0'; Size
0x1800193e9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800193ee  mov     [rbp+4Fh+var_98], rax
0x1800193f2  test    rax, rax
0x1800193f5  jz      short loc_180019418
0x1800193f7  mov     [rsp+110h+var_E0], r14; void *
0x1800193fc  mov     [rsp+110h+var_E8], r13d; enum _SID_NAME_USE
0x180019401  mov     qword ptr [rsp+110h+var_F0], r15; struct _bstr_t *
0x180019406  lea     r9, [rbp+4Fh+var_B0]; struct _bstr_t *
0x18001940a  lea     r8, [rbp+4Fh+var_A8]; struct _bstr_t *
0x18001940e  mov     rcx, rax; this
0x180019411  call    ??0UserEntry@User@@QEAA@_NAEBV_bstr_t@@11W4_SID_NAME_USE@@PEAX@Z; User::UserEntry::UserEntry(bool,_bstr_t const &,_bstr_t const &,_bstr_t const &,_SID_NAME_USE,void *)
0x180019416  jmp     short loc_18001941B
0x180019418  mov     rax, rsi
0x18001941b  test    rax, rax
0x18001941e  jz      short loc_180019480
0x180019420  mov     [rbp+4Fh+var_B8], rax
0x180019424  mov     rcx, rax; this
0x180019427  call    ?AddRef@UserEntry@User@@QEAAKXZ; User::UserEntry::AddRef(void)
0x18001942c  lea     rdx, [rbp+4Fh+var_B8]
0x180019430  mov     rcx, rdi
0x180019433  call    ??0User@@AEAA@AEBV?$AutoRef@UUserEntry@User@@@wmi@@@Z; User::User(wmi::AutoRef<User::UserEntry> const &)
0x180019438  lea     rcx, [rbp+4Fh+var_B8]
0x18001943c  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x180019441  nop
0x180019442  lea     rcx, [rbp+4Fh+var_C0]
0x180019446  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x18001944b  nop
0x18001944c  mov     rcx, rbx; lpCriticalSection
0x18001944f  call    cs:__imp_LeaveCriticalSection
0x180019455  nop
0x180019456  lea     rcx, [rbp+4Fh+var_B0]; this
0x18001945a  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18001945f  nop
0x180019460  lea     rcx, [rbp+4Fh+var_A8]; this
0x180019464  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180019469  mov     rax, rdi
0x18001946c  add     rsp, 0D8h
0x180019473  pop     r15
0x180019475  pop     r14
0x180019477  pop     r13
0x180019479  pop     r12
0x18001947b  pop     rdi
0x18001947c  pop     rsi
0x18001947d  pop     rbx
0x18001947e  pop     rbp
0x18001947f  retn
0x180019480  mov     eax, cs:dword_18005D170
0x180019486  cmp     eax, 2
0x180019489  jbe     loc_18001951C
0x18001948f  call    _tlgKeywordOn
0x180019494  test    al, al
0x180019496  jz      loc_18001951C
0x18001949c  mov     [rbp+4Fh+arg_20], r13d
0x1800194a0  mov     rcx, r15
0x1800194a3  call    ??B_bstr_t@@QEBAPEBGXZ; _bstr_t::operator ushort const *(void)
0x1800194a8  mov     rdx, rax
0x1800194ab  lea     rcx, [rbp+4Fh+var_98]
0x1800194af  call    ??0?$_tlgWrapSid@U_SID@@@@QEAA@PEBU_SID@@@Z; _tlgWrapSid<_SID>::_tlgWrapSid<_SID>(_SID const *)
0x1800194b4  mov     r10, rax
0x1800194b7  lea     rcx, [rbp+4Fh+var_B0]
0x1800194bb  call    ??B_bstr_t@@QEBAPEBGXZ; _bstr_t::operator ushort const *(void)
0x1800194c0  mov     rdx, rax
0x1800194c3  lea     rcx, [rbp+4Fh+var_B8]
0x1800194c7  call    ??0?$_tlgWrapSid@U_SID@@@@QEAA@PEBU_SID@@@Z; _tlgWrapSid<_SID>::_tlgWrapSid<_SID>(_SID const *)
0x1800194cc  mov     r9, rax
0x1800194cf  lea     rcx, [rbp+4Fh+var_A8]
0x1800194d3  call    ??B_bstr_t@@QEBAPEBGXZ; _bstr_t::operator ushort const *(void)
0x1800194d8  mov     rdx, rax
0x1800194db  lea     rcx, [rbp+4Fh+var_88]
0x1800194df  call    ??0?$_tlgWrapSid@U_SID@@@@QEAA@PEBU_SID@@@Z; _tlgWrapSid<_SID>::_tlgWrapSid<_SID>(_SID const *)
0x1800194e4  mov     r8, rax
0x1800194e7  mov     rdx, r14
0x1800194ea  lea     rcx, [rbp+4Fh+var_80]
0x1800194ee  call    ??0?$_tlgWrapSid@U_SID@@@@QEAA@PEBU_SID@@@Z; _tlgWrapSid<_SID>::_tlgWrapSid<_SID>(_SID const *)
0x1800194f3  lea     rcx, [rbp+4Fh+arg_20]
0x1800194f7  mov     [rsp+110h+var_D0], rcx
0x1800194fc  mov     [rsp+110h+var_D8], r10
0x180019501  mov     [rsp+110h+var_E0], r9
0x180019506  mov     qword ptr [rsp+110h+var_E8], r8
0x18001950b  mov     qword ptr [rsp+110h+var_F0], rax
0x180019510  lea     rdx, dword_180055BAC
0x180019517  call    ??$Write@U?$_tlgWrapSid@U_SID@@@@U?$_tlgWrapSz@G@@U2@U2@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSid@U_SID@@@@AEBU?$_tlgWrapSz@G@@44AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSid<_SID>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSid<_SID> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18001951c  lea     rcx, [rbp+4Fh+pExceptionObject]; this
0x180019520  call    ??0OutOfMemoryException@wmi@@QEAA@XZ; wmi::OutOfMemoryException::OutOfMemoryException(void)
0x180019525  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x18001952c  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x180019530  call    _CxxThrowException_0
```
