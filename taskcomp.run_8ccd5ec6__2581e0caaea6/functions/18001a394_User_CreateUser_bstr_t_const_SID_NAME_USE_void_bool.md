# User::CreateUser(_bstr_t const &,_SID_NAME_USE,void *,bool)

- ea: `0x18001a394`
- end: `0x18001a78d`
- name: `?CreateUser@User@@SA?AV1@AEBV_bstr_t@@W4_SID_NAME_USE@@PEAX_N@Z`
- size: `1017`
- prototype: `static struct User __high(const struct _bstr_t *, enum _SID_NAME_USE, void *, bool)`
- caller_count: `1`
- callee_count: `25`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180018870`

## callees

- `0x1800010c0`
- `0x180001184`
- `0x1800014d0`
- `0x1800014e0`
- `0x180003c9c`
- `0x180003cec`
- `0x180003f7c`
- `0x1800050d0`
- `0x180005184`
- `0x1800051c4`
- `0x1800053bc`
- `0x180005bc0`
- `0x180007948`
- `0x180008c4c`
- `0x18000a008`
- `0x18000edd8`
- `0x18001822c`
- `0x18001977c`
- `0x1800197c4`
- `0x1800199cc`
- `0x18001a394`
- `0x18001b124`
- `0x18001b27c`
- `0x18001b46c`
- `0x18001bee0`

## import_xrefs

- `msvcrt!wcschr` at `0x18001a4d3`
- `msvcrt!wcschr` at `0x18001a4d3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a5e8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a5e8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a69f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a69f`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001a3d6`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001a411`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001a44c`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001a3d6`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001a411`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001a44c`
- `OLEAUT32!__imp_SysFreeString` at `0x18001a5cc`
- `OLEAUT32!__imp_SysFreeString` at `0x18001a5cc`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall User::CreateUser(
        __int64 a1,
        const struct _bstr_t *a2,
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
  const wchar_t **v16; // rax
  const wchar_t *v17; // rcx
  const unsigned __int16 *v18; // r12
  unsigned __int16 *v19; // rax
  int v20; // r8d
  int v21; // r9d
  unsigned __int16 *v22; // rbx
  __int64 v23; // rcx
  User::UserEntry *v24; // rcx
  bool v25; // r8
  _bstr_t *v26; // rax
  struct _RTL_CRITICAL_SECTION *v27; // rbx
  User::UserEntry *v28; // rax
  bool v29; // dl
  User::UserEntry *v30; // rax
  __int64 v32; // rax
  __int64 v33; // rax
  __int64 v34; // rax
  __int64 v35; // rax
  __int64 v36; // r8
  __int64 v37; // r9
  __int64 v38; // r10
  bool v39; // [rsp+30h] [rbp-91h]
  unsigned __int16 *v40; // [rsp+50h] [rbp-71h] BYREF
  User::UserEntry *v41; // [rsp+58h] [rbp-69h] BYREF
  __int64 v42; // [rsp+60h] [rbp-61h] BYREF
  __int64 v43; // [rsp+68h] [rbp-59h] BYREF
  LPCRITICAL_SECTION v44; // [rsp+70h] [rbp-51h] BYREF
  _QWORD v45[2]; // [rsp+78h] [rbp-49h] BYREF
  char v46[8]; // [rsp+88h] [rbp-39h] BYREF
  char v47[8]; // [rsp+90h] [rbp-31h] BYREF
  _BYTE pExceptionObject[120]; // [rsp+98h] [rbp-29h] BYREF

  LODWORD(v9) = 0;
  v43 = 0;
  v42 = 0;
  LocalSystem = User::GetLocalSystem(&v41);
  v11 = EqualSid(*(PSID *)(*(_QWORD *)LocalSystem + 32LL), a4);
  wmi::AutoRef<User::UserEntry>::Release(&v41);
  if ( v11 )
  {
    User::GetLocalSystem(a1);
  }
  else
  {
    LocalService = User::GetLocalService(&v41);
    v13 = EqualSid(*(PSID *)(*(_QWORD *)LocalService + 32LL), a4);
    wmi::AutoRef<User::UserEntry>::Release(&v41);
    if ( v13 )
    {
      User::GetLocalService(a1);
    }
    else
    {
      NetworkService = User::GetNetworkService(&v41);
      v15 = EqualSid(*(PSID *)(*(_QWORD *)NetworkService + 32LL), a4);
      wmi::AutoRef<User::UserEntry>::Release(&v41);
      if ( v15 )
      {
        User::GetNetworkService(a1);
      }
      else
      {
        v40 = 0;
        _bstr_t::operator=(&v43, &v40);
        _bstr_t::~_bstr_t((_bstr_t *)&v40);
        v40 = 0;
        _bstr_t::operator=(&v42, &v40);
        _bstr_t::~_bstr_t((_bstr_t *)&v40);
        if ( !(unsigned __int8)_bstr_t::operator!(a2) )
        {
          v16 = *(const wchar_t ***)a2;
          if ( *(_QWORD *)a2 )
          {
            v17 = *v16;
            v18 = *v16;
          }
          else
          {
            v17 = 0;
            v18 = 0;
          }
          v19 = wcschr(v17, 0x5Cu);
          v22 = v19;
          v23 = (unsigned int)dword_18005F170;
          if ( (unsigned int)dword_18005F170 > 4 )
          {
            a5 = a3;
            v24 = 0;
            if ( *(_QWORD *)a2 )
              v24 = **(User::UserEntry ***)a2;
            v41 = v24;
            v40 = v19;
            v45[0] = v18;
            v44 = a4;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSid<_SID>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
              (_DWORD)v24,
              (unsigned int)&byte_180057C4F,
              v20,
              v21,
              (__int64)&v44,
              (__int64)v45,
              (__int64)&v40,
              (__int64)&v41,
              (__int64)&a5);
          }
          if ( !v22 || (v9 = v22 - v18, ++v22 == 0) || !*v22 )
          {
            if ( (unsigned int)dword_18005F170 > 4 )
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
                v23,
                &word_180057C1E);
          }
          _bstr_t::operator=(&v43, v22);
          if ( (_DWORD)v9 )
          {
            ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v40, v9);
            StringCchCopyNW(v40, (unsigned int)(v9 + 1), v18, (unsigned int)v9);
            v26 = _bstr_t::_bstr_t((_bstr_t *)&v44, v40, v25);
            _bstr_t::operator=(&v42, v26);
            _bstr_t::~_bstr_t((_bstr_t *)&v44);
            SysFreeString(0);
          }
        }
        v27 = User::s_cs;
        v44 = User::s_cs;
        EnterCriticalSection(User::s_cs);
        User::LookupUser(&v40, a4);
        if ( v40 )
        {
          User::UpdateEntry((User *)&v40, (const struct _bstr_t *)&v43, (const struct _bstr_t *)&v42, a2, a3, a4, v39);
          wmi::AutoRef<User::UserEntry>::AutoRef<User::UserEntry>(a1, &v40);
        }
        else
        {
          v28 = (User::UserEntry *)operator new(0x30u);
          v45[0] = v28;
          if ( v28 )
            v30 = (User::UserEntry *)User::UserEntry::UserEntry(
                                       v28,
                                       v29,
                                       (const struct _bstr_t *)&v43,
                                       (const struct _bstr_t *)&v42,
                                       a2,
                                       a3,
                                       a4);
          else
            v30 = 0;
          if ( !v30 )
          {
            if ( (unsigned int)dword_18005F170 > 2 && (unsigned __int8)tlgKeywordOn() )
            {
              a5 = a3;
              v32 = _bstr_t::operator unsigned short const *(a2);
              _tlgWrapSid<_SID>::_tlgWrapSid<_SID>(v45, v32);
              v33 = _bstr_t::operator unsigned short const *(&v42);
              _tlgWrapSid<_SID>::_tlgWrapSid<_SID>(&v41, v33);
              v34 = _bstr_t::operator unsigned short const *(&v43);
              _tlgWrapSid<_SID>::_tlgWrapSid<_SID>(v46, v34);
              v35 = _tlgWrapSid<_SID>::_tlgWrapSid<_SID>(v47, a4);
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSid<_SID>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
                (unsigned int)&a5,
                (unsigned int)&dword_180057BB4,
                v36,
                v37,
                v35,
                v36,
                v37,
                v38,
                (__int64)&a5);
            }
            wmi::OutOfMemoryException::OutOfMemoryException((wmi::OutOfMemoryException *)pExceptionObject);
            throw (wmi::OutOfMemoryException *)pExceptionObject;
          }
          v41 = v30;
          User::UserEntry::AddRef(v30);
          wmi::AutoRef<User::UserEntry>::AutoRef<User::UserEntry>(a1, &v41);
          wmi::AutoRef<User::UserEntry>::Release(&v41);
        }
        wmi::AutoRef<User::UserEntry>::Release(&v40);
        LeaveCriticalSection(v27);
      }
    }
  }
  _bstr_t::~_bstr_t((_bstr_t *)&v42);
  _bstr_t::~_bstr_t((_bstr_t *)&v43);
  return a1;
}

```

## disassembly

```asm
0x18001a394  push    rbp
0x18001a396  push    rbx
0x18001a397  push    rsi
0x18001a398  push    rdi
0x18001a399  push    r12
0x18001a39b  push    r13
0x18001a39d  push    r14
0x18001a39f  push    r15
0x18001a3a1  lea     rbp, [rsp-17h]
0x18001a3a6  sub     rsp, 0D8h
0x18001a3ad  mov     r14, r9
0x18001a3b0  mov     r13d, r8d
0x18001a3b3  mov     r15, rdx
0x18001a3b6  mov     rdi, rcx
0x18001a3b9  xor     esi, esi
0x18001a3bb  mov     [rbp+4Fh+var_A8], rsi
0x18001a3bf  mov     [rbp+4Fh+var_B0], rsi
0x18001a3c3  lea     rcx, [rbp+4Fh+var_B8]
0x18001a3c7  call    ?GetLocalSystem@User@@SA?AV1@XZ; User::GetLocalSystem(void)
0x18001a3cc  mov     rcx, [rax]
0x18001a3cf  mov     rdx, r14; pSid2
0x18001a3d2  mov     rcx, [rcx+20h]; pSid1
0x18001a3d6  call    cs:__imp_EqualSid
0x18001a3dd  nop     dword ptr [rax+rax+00h]
0x18001a3e2  mov     ebx, eax
0x18001a3e4  lea     rcx, [rbp+4Fh+var_B8]
0x18001a3e8  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x18001a3ed  test    ebx, ebx
0x18001a3ef  jz      short loc_18001A3FE
0x18001a3f1  mov     rcx, rdi
0x18001a3f4  call    ?GetLocalSystem@User@@SA?AV1@XZ; User::GetLocalSystem(void)
0x18001a3f9  jmp     loc_18001A6AC
0x18001a3fe  lea     rcx, [rbp+4Fh+var_B8]
0x18001a402  call    ?GetLocalService@User@@SA?AV1@XZ; User::GetLocalService(void)
0x18001a407  mov     rcx, [rax]
0x18001a40a  mov     rdx, r14; pSid2
0x18001a40d  mov     rcx, [rcx+20h]; pSid1
0x18001a411  call    cs:__imp_EqualSid
0x18001a418  nop     dword ptr [rax+rax+00h]
0x18001a41d  mov     ebx, eax
0x18001a41f  lea     rcx, [rbp+4Fh+var_B8]
0x18001a423  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x18001a428  test    ebx, ebx
0x18001a42a  jz      short loc_18001A439
0x18001a42c  mov     rcx, rdi
0x18001a42f  call    ?GetLocalService@User@@SA?AV1@XZ; User::GetLocalService(void)
0x18001a434  jmp     loc_18001A6AC
0x18001a439  lea     rcx, [rbp+4Fh+var_B8]
0x18001a43d  call    ?GetNetworkService@User@@SA?AV1@XZ; User::GetNetworkService(void)
0x18001a442  mov     rcx, [rax]
0x18001a445  mov     rdx, r14; pSid2
0x18001a448  mov     rcx, [rcx+20h]; pSid1
0x18001a44c  call    cs:__imp_EqualSid
0x18001a453  nop     dword ptr [rax+rax+00h]
0x18001a458  mov     ebx, eax
0x18001a45a  lea     rcx, [rbp+4Fh+var_B8]
0x18001a45e  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x18001a463  test    ebx, ebx
0x18001a465  jz      short loc_18001A474
0x18001a467  mov     rcx, rdi
0x18001a46a  call    ?GetNetworkService@User@@SA?AV1@XZ; User::GetNetworkService(void)
0x18001a46f  jmp     loc_18001A6AC
0x18001a474  mov     [rbp+4Fh+var_C0], rsi
0x18001a478  lea     rdx, [rbp+4Fh+var_C0]
0x18001a47c  lea     rcx, [rbp+4Fh+var_A8]
0x18001a480  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x18001a485  lea     rcx, [rbp+4Fh+var_C0]; this
0x18001a489  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18001a48e  mov     [rbp+4Fh+var_C0], rsi
0x18001a492  lea     rdx, [rbp+4Fh+var_C0]
0x18001a496  lea     rcx, [rbp+4Fh+var_B0]
0x18001a49a  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x18001a49f  lea     rcx, [rbp+4Fh+var_C0]; this
0x18001a4a3  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18001a4a8  mov     rcx, r15
0x18001a4ab  call    ??7_bstr_t@@QEBA_NXZ; _bstr_t::operator!(void)
0x18001a4b0  test    al, al
0x18001a4b2  jnz     loc_18001A5DA
0x18001a4b8  mov     rax, [r15]
0x18001a4bb  test    rax, rax
0x18001a4be  jz      short loc_18001A4C8
0x18001a4c0  mov     rcx, [rax]
0x18001a4c3  mov     r12, rcx
0x18001a4c6  jmp     short loc_18001A4CE
0x18001a4c8  mov     rcx, rsi; Str
0x18001a4cb  mov     r12, rsi
0x18001a4ce  mov     edx, 5Ch ; '\'; Ch
0x18001a4d3  call    cs:__imp_wcschr
0x18001a4da  nop     dword ptr [rax+rax+00h]
0x18001a4df  mov     rbx, rax
0x18001a4e2  mov     ecx, cs:dword_18005F170
0x18001a4e8  cmp     ecx, 4
0x18001a4eb  jbe     short loc_18001A547
0x18001a4ed  mov     [rbp+4Fh+arg_20], r13d
0x18001a4f1  mov     rax, [r15]
0x18001a4f4  xor     ecx, ecx
0x18001a4f6  test    rax, rax
0x18001a4f9  jz      short loc_18001A4FE
0x18001a4fb  mov     rcx, [rax]
0x18001a4fe  mov     [rbp+4Fh+var_B8], rcx
0x18001a502  mov     [rbp+4Fh+var_C0], rbx
0x18001a506  mov     [rbp+4Fh+var_98], r12
0x18001a50a  mov     [rbp+4Fh+var_A0], r14
0x18001a50e  lea     rax, [rbp+4Fh+arg_20]
0x18001a512  mov     [rsp+110h+var_D0], rax
0x18001a517  lea     rax, [rbp+4Fh+var_B8]
0x18001a51b  mov     [rsp+110h+var_D8], rax
0x18001a520  lea     rax, [rbp+4Fh+var_C0]
0x18001a524  mov     [rsp+110h+var_E0], rax; bool
0x18001a529  lea     rax, [rbp+4Fh+var_98]
0x18001a52d  mov     qword ptr [rsp+110h+var_E8], rax
0x18001a532  lea     rax, [rbp+4Fh+var_A0]
0x18001a536  mov     qword ptr [rsp+110h+var_F0], rax
0x18001a53b  lea     rdx, byte_180057C4F
0x18001a542  call    ??$Write@U?$_tlgWrapSid@U_SID@@@@U?$_tlgWrapSz@G@@U2@U2@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSid@U_SID@@@@AEBU?$_tlgWrapSz@G@@44AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSid<_SID>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSid<_SID> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18001a547  xor     eax, eax
0x18001a549  test    rbx, rbx
0x18001a54c  jz      short loc_18001A562
0x18001a54e  mov     rsi, rbx
0x18001a551  sub     rsi, r12
0x18001a554  sar     rsi, 1
0x18001a557  add     rbx, 2
0x18001a55b  jz      short loc_18001A562
0x18001a55d  cmp     [rbx], ax
0x18001a560  jnz     short loc_18001A579
0x18001a562  mov     eax, cs:dword_18005F170
0x18001a568  cmp     eax, 4
0x18001a56b  jbe     short loc_18001A579
0x18001a56d  lea     rdx, word_180057C1E
0x18001a574  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18001a579  mov     rdx, rbx
0x18001a57c  lea     rcx, [rbp+4Fh+var_A8]
0x18001a580  call    ??4_bstr_t@@QEAAAEAV0@PEBG@Z; _bstr_t::operator=(ushort const *)
0x18001a585  test    esi, esi
0x18001a587  jz      short loc_18001A5D8
0x18001a589  mov     edx, esi; int
0x18001a58b  lea     rcx, [rbp+4Fh+var_C0]; this
0x18001a58f  call    ??0CComBSTR@ATL@@QEAA@H@Z; ATL::CComBSTR::CComBSTR(int)
0x18001a594  nop
0x18001a595  mov     r9d, esi; unsigned __int64
0x18001a598  lea     edx, [rsi+1]; unsigned __int64
0x18001a59b  mov     r8, r12; unsigned __int16 *
0x18001a59e  mov     rcx, [rbp+4Fh+var_C0]; unsigned __int16 *
0x18001a5a2  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18001a5a7  mov     rdx, [rbp+4Fh+var_C0]; unsigned __int16 *
0x18001a5ab  lea     rcx, [rbp+4Fh+var_A0]; this
0x18001a5af  call    ??0_bstr_t@@QEAA@PEAG_N@Z; _bstr_t::_bstr_t(ushort *,bool)
0x18001a5b4  mov     rdx, rax
0x18001a5b7  lea     rcx, [rbp+4Fh+var_B0]
0x18001a5bb  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x18001a5c0  lea     rcx, [rbp+4Fh+var_A0]; this
0x18001a5c4  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18001a5c9  nop
0x18001a5ca  xor     ecx, ecx; bstrString
0x18001a5cc  call    cs:__imp_SysFreeString
0x18001a5d3  nop     dword ptr [rax+rax+00h]
0x18001a5d8  xor     esi, esi
0x18001a5da  mov     rbx, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x18001a5e1  mov     [rbp+4Fh+var_A0], rbx
0x18001a5e5  mov     rcx, rbx; lpCriticalSection
0x18001a5e8  call    cs:__imp_EnterCriticalSection
0x18001a5ef  nop     dword ptr [rax+rax+00h]
0x18001a5f4  nop
0x18001a5f5  mov     rdx, r14
0x18001a5f8  lea     rcx, [rbp+4Fh+var_C0]
0x18001a5fc  call    ?LookupUser@User@@CA?AV1@PEAX@Z; User::LookupUser(void *)
0x18001a601  nop
0x18001a602  cmp     [rbp+4Fh+var_C0], rsi
0x18001a606  jz      short loc_18001A634
0x18001a608  mov     qword ptr [rsp+110h+var_E8], r14; void *
0x18001a60d  mov     [rsp+110h+var_F0], r13d; enum _SID_NAME_USE
0x18001a612  mov     r9, r15; struct _bstr_t *
0x18001a615  lea     r8, [rbp+4Fh+var_B0]; struct _bstr_t *
0x18001a619  lea     rdx, [rbp+4Fh+var_A8]; struct _bstr_t *
0x18001a61d  lea     rcx, [rbp+4Fh+var_C0]; this
0x18001a621  call    ?UpdateEntry@User@@AEBAXAEBV_bstr_t@@00W4_SID_NAME_USE@@PEAX_N@Z; User::UpdateEntry(_bstr_t const &,_bstr_t const &,_bstr_t const &,_SID_NAME_USE,void *,bool)
0x18001a626  lea     rdx, [rbp+4Fh+var_C0]
0x18001a62a  mov     rcx, rdi
0x18001a62d  call    ??0?$AutoRef@UUserEntry@User@@@wmi@@QEAA@AEBV01@@Z; wmi::AutoRef<User::UserEntry>::AutoRef<User::UserEntry>(wmi::AutoRef<User::UserEntry> const &)
0x18001a632  jmp     short loc_18001A692
0x18001a634  mov     ecx, 30h ; '0'; Size
0x18001a639  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001a63e  mov     [rbp+4Fh+var_98], rax
0x18001a642  test    rax, rax
0x18001a645  jz      short loc_18001A668
0x18001a647  mov     [rsp+110h+var_E0], r14; void *
0x18001a64c  mov     [rsp+110h+var_E8], r13d; enum _SID_NAME_USE
0x18001a651  mov     qword ptr [rsp+110h+var_F0], r15; struct _bstr_t *
0x18001a656  lea     r9, [rbp+4Fh+var_B0]; struct _bstr_t *
0x18001a65a  lea     r8, [rbp+4Fh+var_A8]; struct _bstr_t *
0x18001a65e  mov     rcx, rax; this
0x18001a661  call    ??0UserEntry@User@@QEAA@_NAEBV_bstr_t@@11W4_SID_NAME_USE@@PEAX@Z; User::UserEntry::UserEntry(bool,_bstr_t const &,_bstr_t const &,_bstr_t const &,_SID_NAME_USE,void *)
0x18001a666  jmp     short loc_18001A66B
0x18001a668  mov     rax, rsi
0x18001a66b  test    rax, rax
0x18001a66e  jz      short loc_18001A6D7
0x18001a670  mov     [rbp+4Fh+var_B8], rax
0x18001a674  mov     rcx, rax; this
0x18001a677  call    ?AddRef@UserEntry@User@@QEAAKXZ; User::UserEntry::AddRef(void)
0x18001a67c  lea     rdx, [rbp+4Fh+var_B8]
0x18001a680  mov     rcx, rdi
0x18001a683  call    ??0?$AutoRef@UUserEntry@User@@@wmi@@QEAA@AEBV01@@Z; wmi::AutoRef<User::UserEntry>::AutoRef<User::UserEntry>(wmi::AutoRef<User::UserEntry> const &)
0x18001a688  lea     rcx, [rbp+4Fh+var_B8]
0x18001a68c  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x18001a691  nop
0x18001a692  lea     rcx, [rbp+4Fh+var_C0]
0x18001a696  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x18001a69b  nop
0x18001a69c  mov     rcx, rbx; lpCriticalSection
0x18001a69f  call    cs:__imp_LeaveCriticalSection
0x18001a6a6  nop     dword ptr [rax+rax+00h]
0x18001a6ab  nop
0x18001a6ac  lea     rcx, [rbp+4Fh+var_B0]; this
0x18001a6b0  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18001a6b5  nop
0x18001a6b6  lea     rcx, [rbp+4Fh+var_A8]; this
0x18001a6ba  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18001a6bf  mov     rax, rdi
0x18001a6c2  add     rsp, 0D8h
0x18001a6c9  pop     r15
0x18001a6cb  pop     r14
0x18001a6cd  pop     r13
0x18001a6cf  pop     r12
0x18001a6d1  pop     rdi
0x18001a6d2  pop     rsi
0x18001a6d3  pop     rbx
0x18001a6d4  pop     rbp
0x18001a6d5  retn
0x18001a6d7  mov     eax, cs:dword_18005F170
0x18001a6dd  cmp     eax, 2
0x18001a6e0  jbe     loc_18001A773
0x18001a6e6  call    _tlgKeywordOn
0x18001a6eb  test    al, al
0x18001a6ed  jz      loc_18001A773
0x18001a6f3  mov     [rbp+4Fh+arg_20], r13d
0x18001a6f7  mov     rcx, r15
0x18001a6fa  call    ??B_bstr_t@@QEBAPEBGXZ; _bstr_t::operator ushort const *(void)
0x18001a6ff  mov     rdx, rax
0x18001a702  lea     rcx, [rbp+4Fh+var_98]
0x18001a706  call    ??0?$_tlgWrapSid@U_SID@@@@QEAA@PEBU_SID@@@Z; _tlgWrapSid<_SID>::_tlgWrapSid<_SID>(_SID const *)
0x18001a70b  mov     r10, rax
0x18001a70e  lea     rcx, [rbp+4Fh+var_B0]
0x18001a712  call    ??B_bstr_t@@QEBAPEBGXZ; _bstr_t::operator ushort const *(void)
0x18001a717  mov     rdx, rax
0x18001a71a  lea     rcx, [rbp+4Fh+var_B8]
0x18001a71e  call    ??0?$_tlgWrapSid@U_SID@@@@QEAA@PEBU_SID@@@Z; _tlgWrapSid<_SID>::_tlgWrapSid<_SID>(_SID const *)
0x18001a723  mov     r9, rax
0x18001a726  lea     rcx, [rbp+4Fh+var_A8]
0x18001a72a  call    ??B_bstr_t@@QEBAPEBGXZ; _bstr_t::operator ushort const *(void)
0x18001a72f  mov     rdx, rax
0x18001a732  lea     rcx, [rbp+4Fh+var_88]
0x18001a736  call    ??0?$_tlgWrapSid@U_SID@@@@QEAA@PEBU_SID@@@Z; _tlgWrapSid<_SID>::_tlgWrapSid<_SID>(_SID const *)
0x18001a73b  mov     r8, rax
0x18001a73e  mov     rdx, r14
0x18001a741  lea     rcx, [rbp+4Fh+var_80]
0x18001a745  call    ??0?$_tlgWrapSid@U_SID@@@@QEAA@PEBU_SID@@@Z; _tlgWrapSid<_SID>::_tlgWrapSid<_SID>(_SID const *)
0x18001a74a  lea     rcx, [rbp+4Fh+arg_20]
0x18001a74e  mov     [rsp+110h+var_D0], rcx
0x18001a753  mov     [rsp+110h+var_D8], r10
0x18001a758  mov     [rsp+110h+var_E0], r9
0x18001a75d  mov     qword ptr [rsp+110h+var_E8], r8
0x18001a762  mov     qword ptr [rsp+110h+var_F0], rax
0x18001a767  lea     rdx, dword_180057BB4
0x18001a76e  call    ??$Write@U?$_tlgWrapSid@U_SID@@@@U?$_tlgWrapSz@G@@U2@U2@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSid@U_SID@@@@AEBU?$_tlgWrapSz@G@@44AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSid<_SID>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSid<_SID> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18001a773  lea     rcx, [rbp+4Fh+pExceptionObject]; this
0x18001a777  call    ??0OutOfMemoryException@wmi@@QEAA@XZ; wmi::OutOfMemoryException::OutOfMemoryException(void)
0x18001a77c  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x18001a783  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x18001a787  call    _CxxThrowException_0
```
