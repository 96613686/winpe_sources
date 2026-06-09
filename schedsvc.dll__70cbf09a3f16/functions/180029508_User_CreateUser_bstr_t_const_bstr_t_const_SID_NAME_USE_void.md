# User::CreateUser(_bstr_t const &,_bstr_t const &,_SID_NAME_USE,void *)

- ea: `0x180029508`
- end: `0x180029970`
- name: `?CreateUser@User@@SA?AV1@AEBV_bstr_t@@0W4_SID_NAME_USE@@PEAX@Z`
- size: `1128`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `25`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180028efc`
- `0x1800291e8`
- `0x18002f3e0`
- `0x1800517ec`

## callees

- `0x1800012fc`
- `0x180001510`
- `0x180001520`
- `0x18000b4e0`
- `0x18000dc30`
- `0x180019130`
- `0x1800291c0`
- `0x180029508`
- `0x18002a320`
- `0x18002a3c8`
- `0x18002a9e0`
- `0x18002ab90`
- `0x18002ac60`
- `0x18002ae80`
- `0x18002b690`
- `0x18002d390`
- `0x180030f80`
- `0x18003d3f0`
- `0x180042f40`
- `0x180043fcc`
- `0x1800444bc`
- `0x18005248c`
- `0x18005250c`
- `0x18005790c`
- `0x18007a0b0`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800297d0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800297d0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800295c2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800295c2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180029584`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180029676`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180029584`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180029676`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180029896`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180029896`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall User::CreateUser(
        __int64 a1,
        const struct _bstr_t *a2,
        const struct _bstr_t *a3,
        enum _SID_NAME_USE a4,
        _bstr_t *pSid)
{
  char v9; // r13
  __int64 v10; // rdx
  __int64 v11; // r8
  _bstr_t *v12; // rcx
  unsigned int v13; // eax
  struct _RTL_CRITICAL_SECTION *v14; // rbx
  _QWORD *v15; // rax
  unsigned __int16 *v17; // rax
  __int64 v18; // rcx
  User::UserEntry *v19; // rdi
  _QWORD *v20; // rax
  unsigned int v21; // edi
  UINT v22; // edi
  unsigned __int64 v23; // r13
  const unsigned __int16 *v24; // r8
  unsigned __int64 v25; // rdx
  unsigned __int16 *v26; // rdi
  const unsigned __int16 *v27; // r8
  bool v28; // r8
  User::UserEntry *v29; // rax
  __int64 v30; // rcx
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 v33; // rax
  __int64 *v34; // rax
  const OLECHAR **v35; // r8
  const OLECHAR **v36; // r9
  const OLECHAR **v37; // r10
  __int64 v38; // rax
  __int64 v39; // rax
  __int64 *v40; // rax
  const OLECHAR **v41; // r8
  const OLECHAR **v42; // r9
  User::UserEntry *v43; // [rsp+50h] [rbp-71h] BYREF
  User::UserEntry *v44; // [rsp+58h] [rbp-69h] BYREF
  unsigned __int16 *v45; // [rsp+60h] [rbp-61h] BYREF
  enum _SID_NAME_USE v46; // [rsp+68h] [rbp-59h] BYREF
  int v47; // [rsp+6Ch] [rbp-55h]
  LPCRITICAL_SECTION v48; // [rsp+70h] [rbp-51h] BYREF
  LPCRITICAL_SECTION v49; // [rsp+78h] [rbp-49h] BYREF
  __int64 v50; // [rsp+80h] [rbp-41h] BYREF
  __int64 v51; // [rsp+88h] [rbp-39h] BYREF
  __int64 v52; // [rsp+90h] [rbp-31h] BYREF
  _BYTE pExceptionObject[120]; // [rsp+98h] [rbp-29h] BYREF

  v9 = 0;
  v47 = 0;
  v44 = 0;
  if ( (unsigned __int8)_bstr_t::operator!(a2) || (unsigned __int8)_bstr_t::operator!(v11) )
  {
    v12 = pSid;
    if ( pSid
      && IsValidSid(pSid)
      && !(unsigned __int8)_bstr_t::operator!(a2)
      && !(unsigned __int8)_bstr_t::operator!(a3) )
    {
LABEL_34:
      wmi::GenericException::GenericException((wmi::GenericException *)pExceptionObject, 0x57u);
      throw (wmi::GenericException *)pExceptionObject;
    }
LABEL_33:
    MicrosoftTelemetryAssertTriggeredNoArgs(v12, v10, v11);
    goto LABEL_34;
  }
  if ( !pSid )
    goto LABEL_33;
  v13 = _bstr_t::length(v12);
  v14 = User::s_cs;
  if ( v13 )
  {
    v49 = User::s_cs;
    EnterCriticalSection(User::s_cs);
    v20 = (_QWORD *)User::LookupUser(&v45, pSid);
    wmi::AutoRef<User::UserEntry>::operator=(&v44, *v20);
    wmi::AutoRef<User::UserEntry>::Release(&v45);
    if ( v44 )
    {
      v43 = 0;
      User::UpdateEntry(&v44, a2, a3, (const struct _bstr_t *)&v43, a4, pSid, 0);
      _bstr_t::~_bstr_t((_bstr_t *)&v43);
      User::User(a1, &v44);
    }
    else
    {
      v21 = _bstr_t::length(a2) + 1;
      v22 = _bstr_t::length(a3) + v21;
      ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v45, v22);
      v23 = v22 + 1LL;
      v24 = *(const unsigned __int16 **)a3;
      if ( *(_QWORD *)a3 )
        v24 = *(const unsigned __int16 **)v24;
      v25 = v22 + 1LL;
      v26 = v45;
      StringCchCopyW(v45, v25, v24);
      StringCchCatW(v26, v23, L"\\");
      v27 = *(const unsigned __int16 **)a2;
      if ( *(_QWORD *)a2 )
        v27 = *(const unsigned __int16 **)v27;
      StringCchCatW(v26, v23, v27);
      _bstr_t::_bstr_t((_bstr_t *)&v43, v26, v28);
      v45 = 0;
      v29 = (User::UserEntry *)operator new(0x30u);
      v48 = (LPCRITICAL_SECTION)v29;
      if ( v29 )
        v29 = User::UserEntry::UserEntry(v29, 0, a2, a3, (const struct _bstr_t *)&v43, a4, pSid);
      if ( !v29 )
      {
        if ( (unsigned int)dword_1800BC358 > 2 && (unsigned __int8)tlgKeywordOn(v30, 0) )
        {
          v46 = a4;
          v31 = _bstr_t::operator unsigned short const *(&v43);
          wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&v48, v31);
          v32 = _bstr_t::operator unsigned short const *(a2);
          wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&v50, v32);
          v33 = _bstr_t::operator unsigned short const *(a3);
          wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&v51, v33);
          v34 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
                  &v52,
                  (__int64)pSid);
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSid<_SID>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
            (__int64)&v46,
            (unsigned __int8 *)&unk_1800AD480,
            (__int64)v35,
            (__int64)v36,
            v34,
            v35,
            v36,
            v37,
            (__int64)&v46);
        }
        wmi::OutOfMemoryException::OutOfMemoryException((wmi::OutOfMemoryException *)pExceptionObject);
        throw (wmi::OutOfMemoryException *)pExceptionObject;
      }
      v45 = (unsigned __int16 *)v29;
      User::UserEntry::AddRef(v29);
      User::User(a1, &v45);
      wmi::AutoRef<User::UserEntry>::Release(&v45);
      _bstr_t::~_bstr_t((_bstr_t *)&v43);
      SysFreeString(0);
    }
  }
  else
  {
    v48 = User::s_cs;
    EnterCriticalSection(User::s_cs);
    v15 = (_QWORD *)User::LookupUser(&v45, pSid);
    wmi::AutoRef<User::UserEntry>::operator=(&v44, *v15);
    wmi::AutoRef<User::UserEntry>::Release(&v45);
    if ( v44 )
    {
      User::User(a1, &v44);
    }
    else
    {
      v17 = (unsigned __int16 *)operator new(0x30u);
      v45 = v17;
      if ( v17 )
      {
        v43 = 0;
        v9 = 2;
        v47 = 2;
        v19 = User::UserEntry::UserEntry((User::UserEntry *)v17, 0, a2, (const struct _bstr_t *)&v43, a2, a4, pSid);
      }
      else
      {
        v19 = 0;
      }
      if ( (v9 & 2) != 0 )
        _bstr_t::~_bstr_t((_bstr_t *)&v43);
      if ( !v19 )
      {
        if ( (unsigned int)dword_1800BC358 > 2 && (unsigned __int8)tlgKeywordOn(v18, 0) )
        {
          v46 = a4;
          v38 = _bstr_t::operator unsigned short const *(a2);
          wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&v45, v38);
          v39 = _bstr_t::operator unsigned short const *(a3);
          wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&v43, v39);
          v40 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
                  &v49,
                  (__int64)pSid);
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSid<_SID>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
            (__int64)&v46,
            (__int64)&word_1800AD4DE,
            (__int64)v41,
            (__int64)v42,
            v40,
            v41,
            v42,
            (__int64)&v46);
        }
        wmi::OutOfMemoryException::OutOfMemoryException((wmi::OutOfMemoryException *)pExceptionObject);
        throw (wmi::OutOfMemoryException *)pExceptionObject;
      }
      v43 = v19;
      User::UserEntry::AddRef(v19);
      User::User(a1, &v43);
      wmi::AutoRef<User::UserEntry>::Release(&v43);
    }
  }
  LeaveCriticalSection(v14);
  wmi::AutoRef<User::UserEntry>::Release(&v44);
  return a1;
}

```

## disassembly

```asm
0x180029508  mov     [rsp-8+arg_18], r9d
0x18002950d  push    rbp
0x18002950e  push    rbx
0x18002950f  push    rsi
0x180029510  push    rdi
0x180029511  push    r12
0x180029513  push    r13
0x180029515  push    r14
0x180029517  push    r15
0x180029519  lea     rbp, [rsp-17h]
0x18002951e  sub     rsp, 0D8h
0x180029525  mov     edi, r9d
0x180029528  mov     r15, r8
0x18002952b  mov     r14, rdx
0x18002952e  mov     rsi, rcx
0x180029531  xor     r13d, r13d
0x180029534  mov     [rbp+4Fh+var_A4], r13d
0x180029538  mov     [rbp+4Fh+var_B8], r13
0x18002953c  mov     rcx, rdx
0x18002953f  call    ??7_bstr_t@@QEBA_NXZ; _bstr_t::operator!(void)
0x180029544  test    al, al
0x180029546  jnz     loc_18002988D
0x18002954c  mov     rcx, r8
0x18002954f  call    ??7_bstr_t@@QEBA_NXZ; _bstr_t::operator!(void)
0x180029554  test    al, al
0x180029556  jnz     loc_18002988D
0x18002955c  mov     r12, [rbp+4Fh+pSid]
0x180029560  test    r12, r12
0x180029563  jz      loc_1800298B8
0x180029569  call    ?length@_bstr_t@@QEBAIXZ; _bstr_t::length(void)
0x18002956e  mov     rbx, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x180029575  mov     rcx, rbx; lpCriticalSection
0x180029578  test    eax, eax
0x18002957a  jnz     loc_180029672
0x180029580  mov     [rbp+4Fh+var_A0], rbx
0x180029584  call    cs:__imp_EnterCriticalSection
0x18002958a  nop
0x18002958b  mov     rdx, r12
0x18002958e  lea     rcx, [rbp+4Fh+var_B0]
0x180029592  call    ?LookupUser@User@@CA?AV1@PEAX@Z; User::LookupUser(void *)
0x180029597  mov     rdx, [rax]
0x18002959a  lea     rcx, [rbp+4Fh+var_B8]
0x18002959e  call    ??4?$AutoRef@UUserEntry@User@@@wmi@@QEAAAEAV01@PEAUUserEntry@User@@@Z; wmi::AutoRef<User::UserEntry>::operator=(User::UserEntry *)
0x1800295a3  lea     rcx, [rbp+4Fh+var_B0]
0x1800295a7  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x1800295ac  cmp     [rbp+4Fh+var_B8], r13
0x1800295b0  jz      short loc_1800295E9
0x1800295b2  lea     rdx, [rbp+4Fh+var_B8]
0x1800295b6  mov     rcx, rsi
0x1800295b9  call    ??0User@@AEAA@AEBV?$AutoRef@UUserEntry@User@@@wmi@@@Z; User::User(wmi::AutoRef<User::UserEntry> const &)
0x1800295be  nop
0x1800295bf  mov     rcx, rbx; lpCriticalSection
0x1800295c2  call    cs:__imp_LeaveCriticalSection
0x1800295c8  nop
0x1800295c9  lea     rcx, [rbp+4Fh+var_B8]
0x1800295cd  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x1800295d2  mov     rax, rsi
0x1800295d5  add     rsp, 0D8h
0x1800295dc  pop     r15
0x1800295de  pop     r14
0x1800295e0  pop     r13
0x1800295e2  pop     r12
0x1800295e4  pop     rdi
0x1800295e5  pop     rsi
0x1800295e6  pop     rbx
0x1800295e7  pop     rbp
0x1800295e8  retn
0x1800295e9  mov     ecx, 30h ; '0'; dwBytes
0x1800295ee  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800295f3  mov     [rbp+4Fh+var_B0], rax
0x1800295f7  test    rax, rax
0x1800295fa  jz      short loc_180029632
0x1800295fc  mov     [rbp+4Fh+var_C0], 0
0x180029604  mov     r13d, 2
0x18002960a  mov     [rbp+4Fh+var_A4], r13d
0x18002960e  mov     [rsp+110h+var_E0], r12; void *
0x180029613  mov     [rsp+110h+var_E8], edi; enum _SID_NAME_USE
0x180029617  mov     qword ptr [rsp+110h+var_F0], r14; struct _bstr_t *
0x18002961c  lea     r9, [rbp+4Fh+var_C0]; struct _bstr_t *
0x180029620  mov     r8, r14; struct _bstr_t *
0x180029623  xor     edx, edx; bool
0x180029625  mov     rcx, rax; this
0x180029628  call    ??0UserEntry@User@@QEAA@_NAEBV_bstr_t@@11W4_SID_NAME_USE@@PEAX@Z; User::UserEntry::UserEntry(bool,_bstr_t const &,_bstr_t const &,_bstr_t const &,_SID_NAME_USE,void *)
0x18002962d  mov     rdi, rax
0x180029630  jmp     short loc_180029634
0x180029632  xor     edi, edi
0x180029634  test    r13b, 2
0x180029638  jz      short loc_180029643
0x18002963a  lea     rcx, [rbp+4Fh+var_C0]; this
0x18002963e  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180029643  test    rdi, rdi
0x180029646  jz      loc_1800298DC
0x18002964c  mov     [rbp+4Fh+var_C0], rdi
0x180029650  mov     rcx, rdi; this
0x180029653  call    ?AddRef@UserEntry@User@@QEAAKXZ; User::UserEntry::AddRef(void)
0x180029658  lea     rdx, [rbp+4Fh+var_C0]
0x18002965c  mov     rcx, rsi
0x18002965f  call    ??0User@@AEAA@AEBV?$AutoRef@UUserEntry@User@@@wmi@@@Z; User::User(wmi::AutoRef<User::UserEntry> const &)
0x180029664  lea     rcx, [rbp+4Fh+var_C0]
0x180029668  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x18002966d  jmp     loc_1800295BF
0x180029672  mov     [rbp+4Fh+var_98], rbx
0x180029676  call    cs:__imp_EnterCriticalSection
0x18002967c  nop
0x18002967d  mov     rdx, r12
0x180029680  lea     rcx, [rbp+4Fh+var_B0]
0x180029684  call    ?LookupUser@User@@CA?AV1@PEAX@Z; User::LookupUser(void *)
0x180029689  mov     rdx, [rax]
0x18002968c  lea     rcx, [rbp+4Fh+var_B8]
0x180029690  call    ??4?$AutoRef@UUserEntry@User@@@wmi@@QEAAAEAV01@PEAUUserEntry@User@@@Z; wmi::AutoRef<User::UserEntry>::operator=(User::UserEntry *)
0x180029695  lea     rcx, [rbp+4Fh+var_B0]
0x180029699  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x18002969e  xor     eax, eax
0x1800296a0  cmp     [rbp+4Fh+var_B8], rax
0x1800296a4  jz      short loc_1800296E6
0x1800296a6  mov     [rbp+4Fh+var_C0], rax
0x1800296aa  mov     byte ptr [rsp+110h+var_E0], al; bool
0x1800296ae  mov     qword ptr [rsp+110h+var_E8], r12; void *
0x1800296b3  mov     [rsp+110h+var_F0], edi; enum _SID_NAME_USE
0x1800296b7  lea     r9, [rbp+4Fh+var_C0]; struct _bstr_t *
0x1800296bb  mov     r8, r15; struct _bstr_t *
0x1800296be  mov     rdx, r14; struct _bstr_t *
0x1800296c1  lea     rcx, [rbp+4Fh+var_B8]; this
0x1800296c5  call    ?UpdateEntry@User@@AEBAXAEBV_bstr_t@@00W4_SID_NAME_USE@@PEAX_N@Z; User::UpdateEntry(_bstr_t const &,_bstr_t const &,_bstr_t const &,_SID_NAME_USE,void *,bool)
0x1800296ca  nop
0x1800296cb  lea     rcx, [rbp+4Fh+var_C0]; this
0x1800296cf  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x1800296d4  lea     rdx, [rbp+4Fh+var_B8]
0x1800296d8  mov     rcx, rsi
0x1800296db  call    ??0User@@AEAA@AEBV?$AutoRef@UUserEntry@User@@@wmi@@@Z; User::User(wmi::AutoRef<User::UserEntry> const &)
0x1800296e0  nop
0x1800296e1  jmp     loc_1800295BF
0x1800296e6  mov     rcx, r14; this
0x1800296e9  call    ?length@_bstr_t@@QEBAIXZ; _bstr_t::length(void)
0x1800296ee  lea     edi, [rax+1]
0x1800296f1  mov     rcx, r15; this
0x1800296f4  call    ?length@_bstr_t@@QEBAIXZ; _bstr_t::length(void)
0x1800296f9  add     edi, eax
0x1800296fb  mov     edx, edi; int
0x1800296fd  lea     rcx, [rbp+4Fh+var_B0]; this
0x180029701  call    ??0CComBSTR@ATL@@QEAA@H@Z; ATL::CComBSTR::CComBSTR(int)
0x180029706  nop
0x180029707  mov     r13d, edi
0x18002970a  inc     r13
0x18002970d  mov     r8, [r15]
0x180029710  test    r8, r8
0x180029713  jz      short loc_180029718
0x180029715  mov     r8, [r8]; unsigned __int16 *
0x180029718  mov     rdx, r13; unsigned __int64
0x18002971b  mov     rdi, [rbp+4Fh+var_B0]
0x18002971f  mov     rcx, rdi; unsigned __int16 *
0x180029722  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180029727  lea     r8, asc_1800A3DA8; "\\"
0x18002972e  mov     rdx, r13; unsigned __int64
0x180029731  mov     rcx, rdi; unsigned __int16 *
0x180029734  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180029739  mov     r8, [r14]
0x18002973c  test    r8, r8
0x18002973f  jz      short loc_180029744
0x180029741  mov     r8, [r8]; unsigned __int16 *
0x180029744  mov     rdx, r13; unsigned __int64
0x180029747  mov     rcx, rdi; unsigned __int16 *
0x18002974a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002974f  mov     rdx, rdi; unsigned __int16 *
0x180029752  lea     rcx, [rbp+4Fh+var_C0]; this
0x180029756  call    ??0_bstr_t@@QEAA@PEAG_N@Z; _bstr_t::_bstr_t(ushort *,bool)
0x18002975b  nop
0x18002975c  mov     [rbp+4Fh+var_B0], 0
0x180029764  mov     ecx, 30h ; '0'; dwBytes
0x180029769  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002976e  mov     [rbp+4Fh+var_A0], rax
0x180029772  mov     edi, [rbp+4Fh+arg_18]
0x180029775  test    rax, rax
0x180029778  jz      short loc_18002979D
0x18002977a  mov     [rsp+110h+var_E0], r12; void *
0x18002977f  mov     [rsp+110h+var_E8], edi; enum _SID_NAME_USE
0x180029783  lea     rcx, [rbp+4Fh+var_C0]
0x180029787  mov     qword ptr [rsp+110h+var_F0], rcx; struct _bstr_t *
0x18002978c  mov     r9, r15; struct _bstr_t *
0x18002978f  mov     r8, r14; struct _bstr_t *
0x180029792  xor     edx, edx; bool
0x180029794  mov     rcx, rax; this
0x180029797  call    ??0UserEntry@User@@QEAA@_NAEBV_bstr_t@@11W4_SID_NAME_USE@@PEAX@Z; User::UserEntry::UserEntry(bool,_bstr_t const &,_bstr_t const &,_bstr_t const &,_SID_NAME_USE,void *)
0x18002979c  nop
0x18002979d  test    rax, rax
0x1800297a0  jz      short loc_1800297DB
0x1800297a2  mov     [rbp+4Fh+var_B0], rax
0x1800297a6  mov     rcx, rax; this
0x1800297a9  call    ?AddRef@UserEntry@User@@QEAAKXZ; User::UserEntry::AddRef(void)
0x1800297ae  lea     rdx, [rbp+4Fh+var_B0]
0x1800297b2  mov     rcx, rsi
0x1800297b5  call    ??0User@@AEAA@AEBV?$AutoRef@UUserEntry@User@@@wmi@@@Z; User::User(wmi::AutoRef<User::UserEntry> const &)
0x1800297ba  lea     rcx, [rbp+4Fh+var_B0]
0x1800297be  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x1800297c3  nop
0x1800297c4  lea     rcx, [rbp+4Fh+var_C0]; this
0x1800297c8  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x1800297cd  nop
0x1800297ce  xor     ecx, ecx; bstrString
0x1800297d0  call    cs:__imp_SysFreeString
0x1800297d6  jmp     loc_1800296E1
0x1800297db  mov     eax, cs:dword_1800BC358
0x1800297e1  cmp     eax, 2
0x1800297e4  jbe     loc_180029873
0x1800297ea  xor     edx, edx
0x1800297ec  call    _tlgKeywordOn
0x1800297f1  test    al, al
0x1800297f3  jz      short loc_180029873
0x1800297f5  mov     [rbp+4Fh+var_A8], edi
0x1800297f8  lea     rcx, [rbp+4Fh+var_C0]
0x1800297fc  call    ??B_bstr_t@@QEBAPEBGXZ; _bstr_t::operator ushort const *(void)
0x180029801  mov     rdx, rax
0x180029804  lea     rcx, [rbp+4Fh+var_A0]
0x180029808  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x18002980d  mov     r10, rax
0x180029810  mov     rcx, r14
0x180029813  call    ??B_bstr_t@@QEBAPEBGXZ; _bstr_t::operator ushort const *(void)
0x180029818  mov     rdx, rax
0x18002981b  lea     rcx, [rbp+4Fh+var_90]
0x18002981f  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x180029824  mov     r9, rax
0x180029827  mov     rcx, r15
0x18002982a  call    ??B_bstr_t@@QEBAPEBGXZ; _bstr_t::operator ushort const *(void)
0x18002982f  mov     rdx, rax
0x180029832  lea     rcx, [rbp+4Fh+var_88]
0x180029836  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x18002983b  mov     r8, rax
0x18002983e  mov     rdx, r12
0x180029841  lea     rcx, [rbp+4Fh+var_80]
0x180029845  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x18002984a  lea     rcx, [rbp+4Fh+var_A8]
0x18002984e  mov     [rsp+110h+var_D0], rcx
0x180029853  mov     [rsp+110h+var_D8], r10
0x180029858  mov     [rsp+110h+var_E0], r9
0x18002985d  mov     qword ptr [rsp+110h+var_E8], r8
0x180029862  mov     qword ptr [rsp+110h+var_F0], rax
0x180029867  lea     rdx, unk_1800AD480
0x18002986e  call    ??$Write@U?$_tlgWrapSid@U_SID@@@@U?$_tlgWrapSz@G@@U2@U2@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSid@U_SID@@@@AEBU?$_tlgWrapSz@G@@44AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSid<_SID>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSid<_SID> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180029873  lea     rcx, [rbp+4Fh+pExceptionObject]; this
0x180029877  call    ??0OutOfMemoryException@wmi@@QEAA@XZ; wmi::OutOfMemoryException::OutOfMemoryException(void)
0x18002987c  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x180029883  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x180029887  call    _CxxThrowException_0
0x18002988d  mov     rcx, [rbp+4Fh+pSid]; pSid
0x180029891  test    rcx, rcx
0x180029894  jz      short loc_1800298B8
0x180029896  call    cs:__imp_IsValidSid
0x18002989c  test    eax, eax
0x18002989e  jz      short loc_1800298B8
0x1800298a0  mov     rcx, r14
0x1800298a3  call    ??7_bstr_t@@QEBA_NXZ; _bstr_t::operator!(void)
0x1800298a8  test    al, al
0x1800298aa  jnz     short loc_1800298B8
0x1800298ac  mov     rcx, r15
0x1800298af  call    ??7_bstr_t@@QEBA_NXZ; _bstr_t::operator!(void)
0x1800298b4  test    al, al
0x1800298b6  jz      short loc_1800298BD
0x1800298b8  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800298bd  mov     edx, 57h ; 'W'; unsigned int
0x1800298c2  lea     rcx, [rbp+4Fh+pExceptionObject]; this
0x1800298c6  call    ??0GenericException@wmi@@QEAA@K@Z; wmi::GenericException::GenericException(ulong)
0x1800298cb  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x1800298d2  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x1800298d6  call    _CxxThrowException_0
0x1800298dc  mov     eax, cs:dword_1800BC358
0x1800298e2  cmp     eax, 2
0x1800298e5  jbe     short loc_180029956
0x1800298e7  xor     edx, edx
0x1800298e9  call    _tlgKeywordOn
0x1800298ee  test    al, al
0x1800298f0  jz      short loc_180029956
0x1800298f2  mov     edi, [rbp+4Fh+arg_18]
0x1800298f5  mov     [rbp+4Fh+var_A8], edi
0x1800298f8  mov     rcx, r14
0x1800298fb  call    ??B_bstr_t@@QEBAPEBGXZ; _bstr_t::operator ushort const *(void)
0x180029900  mov     rdx, rax
0x180029903  lea     rcx, [rbp+4Fh+var_B0]
0x180029907  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x18002990c  mov     r9, rax
0x18002990f  mov     rcx, r15
0x180029912  call    ??B_bstr_t@@QEBAPEBGXZ; _bstr_t::operator ushort const *(void)
0x180029917  mov     rdx, rax
0x18002991a  lea     rcx, [rbp+4Fh+var_C0]
0x18002991e  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x180029923  mov     r8, rax
0x180029926  mov     rdx, r12
0x180029929  lea     rcx, [rbp+4Fh+var_98]
0x18002992d  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x180029932  lea     rcx, [rbp+4Fh+var_A8]
0x180029936  mov     [rsp+110h+var_D8], rcx
0x18002993b  mov     [rsp+110h+var_E0], r9
0x180029940  mov     qword ptr [rsp+110h+var_E8], r8
0x180029945  mov     qword ptr [rsp+110h+var_F0], rax
0x18002994a  lea     rdx, word_1800AD4DE
0x180029951  call    ??$Write@U?$_tlgWrapSid@U_SID@@@@U?$_tlgWrapSz@G@@U2@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSid@U_SID@@@@AEBU?$_tlgWrapSz@G@@4AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSid<_SID>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSid<_SID> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180029956  lea     rcx, [rbp+4Fh+pExceptionObject]; this
0x18002995a  call    ??0OutOfMemoryException@wmi@@QEAA@XZ; wmi::OutOfMemoryException::OutOfMemoryException(void)
0x18002995f  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x180029966  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x18002996a  call    _CxxThrowException_0
  ... truncated ...
```
