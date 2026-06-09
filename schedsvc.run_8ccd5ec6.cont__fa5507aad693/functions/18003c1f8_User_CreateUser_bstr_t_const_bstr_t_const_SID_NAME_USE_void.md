# User::CreateUser(_bstr_t const &,_bstr_t const &,_SID_NAME_USE,void *)

- ea: `0x18003c1f8`
- end: `0x18003c67f`
- name: `?CreateUser@User@@SA?AV1@AEBV_bstr_t@@0W4_SID_NAME_USE@@PEAX@Z`
- size: `1159`
- prototype: `static struct User __high(const struct _bstr_t *, const struct _bstr_t *, enum _SID_NAME_USE, void *)`
- caller_count: `4`
- callee_count: `25`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180025e70`
- `0x18003bb74`
- `0x18003be7c`
- `0x180053d9c`

## callees

- `0x18000131c`
- `0x180001534`
- `0x180001544`
- `0x180001d10`
- `0x180001dbc`
- `0x180001e10`
- `0x180002790`
- `0x1800044b0`
- `0x18000fe50`
- `0x180011e40`
- `0x180017740`
- `0x180017820`
- `0x180027910`
- `0x1800301f0`
- `0x180032c30`
- `0x18003be50`
- `0x18003c1f8`
- `0x18003dfb0`
- `0x1800449bc`
- `0x1800460dc`
- `0x18004658c`
- `0x180054b54`
- `0x180054bd8`
- `0x18005a2bc`
- `0x18007e258`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18003c4d3`
- `OLEAUT32!__imp_SysFreeString` at `0x18003c4d3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003c2b8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003c2b8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003c274`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003c373`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003c274`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003c373`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18003c59f`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18003c59f`

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
  unsigned int v22; // edi
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
  __int64 v34; // rax
  __int64 v35; // r8
  __int64 v36; // r9
  __int64 v37; // r10
  __int64 v38; // rax
  __int64 v39; // rax
  __int64 v40; // rax
  __int64 v41; // r8
  __int64 v42; // r9
  User::UserEntry *v43; // [rsp+50h] [rbp-71h] BYREF
  __int64 v44; // [rsp+58h] [rbp-69h] BYREF
  unsigned __int16 *v45; // [rsp+60h] [rbp-61h] BYREF
  enum _SID_NAME_USE v46; // [rsp+68h] [rbp-59h] BYREF
  int v47; // [rsp+6Ch] [rbp-55h]
  LPCRITICAL_SECTION v48; // [rsp+70h] [rbp-51h] BYREF
  LPCRITICAL_SECTION v49; // [rsp+78h] [rbp-49h] BYREF
  _BYTE v50[8]; // [rsp+80h] [rbp-41h] BYREF
  _BYTE v51[8]; // [rsp+88h] [rbp-39h] BYREF
  _BYTE v52[8]; // [rsp+90h] [rbp-31h] BYREF
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
      User::UpdateEntry((User *)&v44, a2, a3, (const struct _bstr_t *)&v43, a4, pSid, 0);
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
        v29 = (User::UserEntry *)User::UserEntry::UserEntry(v29, 0, a2, a3, (const struct _bstr_t *)&v43, a4, pSid);
      if ( !v29 )
      {
        if ( (unsigned int)dword_1800C0358 > 2 && (unsigned __int8)tlgKeywordOn(v30, 0) )
        {
          v46 = a4;
          v31 = _bstr_t::operator unsigned short const *(&v43);
          wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&v48, v31);
          v32 = _bstr_t::operator unsigned short const *(a2);
          wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(v50, v32);
          v33 = _bstr_t::operator unsigned short const *(a3);
          wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(v51, v33);
          v34 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(v52, pSid);
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSid<_SID>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
            (unsigned int)&v46,
            (unsigned int)&unk_1800B14C8,
            v35,
            v36,
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
        v19 = (User::UserEntry *)User::UserEntry::UserEntry(
                                   (User::UserEntry *)v17,
                                   0,
                                   a2,
                                   (const struct _bstr_t *)&v43,
                                   a2,
                                   a4,
                                   pSid);
      }
      else
      {
        v19 = 0;
      }
      if ( (v9 & 2) != 0 )
        _bstr_t::~_bstr_t((_bstr_t *)&v43);
      if ( !v19 )
      {
        if ( (unsigned int)dword_1800C0358 > 2 && (unsigned __int8)tlgKeywordOn(v18, 0) )
        {
          v46 = a4;
          v38 = _bstr_t::operator unsigned short const *(a2);
          wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&v45, v38);
          v39 = _bstr_t::operator unsigned short const *(a3);
          wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&v43, v39);
          v40 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
                  &v49,
                  pSid);
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSid<_SID>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
            (unsigned int)&v46,
            (unsigned int)&word_1800B1526,
            v41,
            v42,
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
0x18003c1f8  mov     [rsp-8+arg_18], r9d
0x18003c1fd  push    rbp
0x18003c1fe  push    rbx
0x18003c1ff  push    rsi
0x18003c200  push    rdi
0x18003c201  push    r12
0x18003c203  push    r13
0x18003c205  push    r14
0x18003c207  push    r15
0x18003c209  lea     rbp, [rsp-17h]
0x18003c20e  sub     rsp, 0D8h
0x18003c215  mov     edi, r9d
0x18003c218  mov     r15, r8
0x18003c21b  mov     r14, rdx
0x18003c21e  mov     rsi, rcx
0x18003c221  xor     r13d, r13d
0x18003c224  mov     [rbp+4Fh+var_A4], r13d
0x18003c228  mov     [rbp+4Fh+var_B8], r13
0x18003c22c  mov     rcx, rdx
0x18003c22f  call    ??7_bstr_t@@QEBA_NXZ; _bstr_t::operator!(void)
0x18003c234  test    al, al
0x18003c236  jnz     loc_18003C596
0x18003c23c  mov     rcx, r8
0x18003c23f  call    ??7_bstr_t@@QEBA_NXZ; _bstr_t::operator!(void)
0x18003c244  test    al, al
0x18003c246  jnz     loc_18003C596
0x18003c24c  mov     r12, [rbp+4Fh+pSid]
0x18003c250  test    r12, r12
0x18003c253  jz      loc_18003C5C7
0x18003c259  call    ?length@_bstr_t@@QEBAIXZ; _bstr_t::length(void)
0x18003c25e  mov     rbx, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x18003c265  mov     rcx, rbx; lpCriticalSection
0x18003c268  test    eax, eax
0x18003c26a  jnz     loc_18003C36F
0x18003c270  mov     [rbp+4Fh+var_A0], rbx
0x18003c274  call    cs:__imp_EnterCriticalSection
0x18003c27b  nop     dword ptr [rax+rax+00h]
0x18003c280  nop
0x18003c281  mov     rdx, r12
0x18003c284  lea     rcx, [rbp+4Fh+var_B0]
0x18003c288  call    ?LookupUser@User@@CA?AV1@PEAX@Z; User::LookupUser(void *)
0x18003c28d  mov     rdx, [rax]
0x18003c290  lea     rcx, [rbp+4Fh+var_B8]
0x18003c294  call    ??4?$AutoRef@UUserEntry@User@@@wmi@@QEAAAEAV01@PEAUUserEntry@User@@@Z; wmi::AutoRef<User::UserEntry>::operator=(User::UserEntry *)
0x18003c299  lea     rcx, [rbp+4Fh+var_B0]
0x18003c29d  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x18003c2a2  cmp     [rbp+4Fh+var_B8], r13
0x18003c2a6  jz      short loc_18003C2E6
0x18003c2a8  lea     rdx, [rbp+4Fh+var_B8]
0x18003c2ac  mov     rcx, rsi
0x18003c2af  call    ??0User@@AEAA@AEBV?$AutoRef@UUserEntry@User@@@wmi@@@Z; User::User(wmi::AutoRef<User::UserEntry> const &)
0x18003c2b4  nop
0x18003c2b5  mov     rcx, rbx; lpCriticalSection
0x18003c2b8  call    cs:__imp_LeaveCriticalSection
0x18003c2bf  nop     dword ptr [rax+rax+00h]
0x18003c2c4  nop
0x18003c2c5  lea     rcx, [rbp+4Fh+var_B8]
0x18003c2c9  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x18003c2ce  mov     rax, rsi
0x18003c2d1  add     rsp, 0D8h
0x18003c2d8  pop     r15
0x18003c2da  pop     r14
0x18003c2dc  pop     r13
0x18003c2de  pop     r12
0x18003c2e0  pop     rdi
0x18003c2e1  pop     rsi
0x18003c2e2  pop     rbx
0x18003c2e3  pop     rbp
0x18003c2e4  retn
0x18003c2e6  mov     ecx, 30h ; '0'; dwBytes
0x18003c2eb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003c2f0  mov     [rbp+4Fh+var_B0], rax
0x18003c2f4  test    rax, rax
0x18003c2f7  jz      short loc_18003C32F
0x18003c2f9  mov     [rbp+4Fh+var_C0], 0
0x18003c301  mov     r13d, 2
0x18003c307  mov     [rbp+4Fh+var_A4], r13d
0x18003c30b  mov     [rsp+110h+var_E0], r12; void *
0x18003c310  mov     [rsp+110h+var_E8], edi; enum _SID_NAME_USE
0x18003c314  mov     qword ptr [rsp+110h+var_F0], r14; struct _bstr_t *
0x18003c319  lea     r9, [rbp+4Fh+var_C0]; struct _bstr_t *
0x18003c31d  mov     r8, r14; struct _bstr_t *
0x18003c320  xor     edx, edx; bool
0x18003c322  mov     rcx, rax; this
0x18003c325  call    ??0UserEntry@User@@QEAA@_NAEBV_bstr_t@@11W4_SID_NAME_USE@@PEAX@Z; User::UserEntry::UserEntry(bool,_bstr_t const &,_bstr_t const &,_bstr_t const &,_SID_NAME_USE,void *)
0x18003c32a  mov     rdi, rax
0x18003c32d  jmp     short loc_18003C331
0x18003c32f  xor     edi, edi
0x18003c331  test    r13b, 2
0x18003c335  jz      short loc_18003C340
0x18003c337  lea     rcx, [rbp+4Fh+var_C0]; this
0x18003c33b  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18003c340  test    rdi, rdi
0x18003c343  jz      loc_18003C5EB
0x18003c349  mov     [rbp+4Fh+var_C0], rdi
0x18003c34d  mov     rcx, rdi; this
0x18003c350  call    ?AddRef@UserEntry@User@@QEAAKXZ; User::UserEntry::AddRef(void)
0x18003c355  lea     rdx, [rbp+4Fh+var_C0]
0x18003c359  mov     rcx, rsi
0x18003c35c  call    ??0User@@AEAA@AEBV?$AutoRef@UUserEntry@User@@@wmi@@@Z; User::User(wmi::AutoRef<User::UserEntry> const &)
0x18003c361  lea     rcx, [rbp+4Fh+var_C0]
0x18003c365  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x18003c36a  jmp     loc_18003C2B5
0x18003c36f  mov     [rbp+4Fh+var_98], rbx
0x18003c373  call    cs:__imp_EnterCriticalSection
0x18003c37a  nop     dword ptr [rax+rax+00h]
0x18003c37f  nop
0x18003c380  mov     rdx, r12
0x18003c383  lea     rcx, [rbp+4Fh+var_B0]
0x18003c387  call    ?LookupUser@User@@CA?AV1@PEAX@Z; User::LookupUser(void *)
0x18003c38c  mov     rdx, [rax]
0x18003c38f  lea     rcx, [rbp+4Fh+var_B8]
0x18003c393  call    ??4?$AutoRef@UUserEntry@User@@@wmi@@QEAAAEAV01@PEAUUserEntry@User@@@Z; wmi::AutoRef<User::UserEntry>::operator=(User::UserEntry *)
0x18003c398  lea     rcx, [rbp+4Fh+var_B0]
0x18003c39c  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x18003c3a1  xor     eax, eax
0x18003c3a3  cmp     [rbp+4Fh+var_B8], rax
0x18003c3a7  jz      short loc_18003C3E9
0x18003c3a9  mov     [rbp+4Fh+var_C0], rax
0x18003c3ad  mov     byte ptr [rsp+110h+var_E0], al; bool
0x18003c3b1  mov     qword ptr [rsp+110h+var_E8], r12; void *
0x18003c3b6  mov     [rsp+110h+var_F0], edi; enum _SID_NAME_USE
0x18003c3ba  lea     r9, [rbp+4Fh+var_C0]; struct _bstr_t *
0x18003c3be  mov     r8, r15; struct _bstr_t *
0x18003c3c1  mov     rdx, r14; struct _bstr_t *
0x18003c3c4  lea     rcx, [rbp+4Fh+var_B8]; this
0x18003c3c8  call    ?UpdateEntry@User@@AEBAXAEBV_bstr_t@@00W4_SID_NAME_USE@@PEAX_N@Z; User::UpdateEntry(_bstr_t const &,_bstr_t const &,_bstr_t const &,_SID_NAME_USE,void *,bool)
0x18003c3cd  nop
0x18003c3ce  lea     rcx, [rbp+4Fh+var_C0]; this
0x18003c3d2  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18003c3d7  lea     rdx, [rbp+4Fh+var_B8]
0x18003c3db  mov     rcx, rsi
0x18003c3de  call    ??0User@@AEAA@AEBV?$AutoRef@UUserEntry@User@@@wmi@@@Z; User::User(wmi::AutoRef<User::UserEntry> const &)
0x18003c3e3  nop
0x18003c3e4  jmp     loc_18003C2B5
0x18003c3e9  mov     rcx, r14; this
0x18003c3ec  call    ?length@_bstr_t@@QEBAIXZ; _bstr_t::length(void)
0x18003c3f1  lea     edi, [rax+1]
0x18003c3f4  mov     rcx, r15; this
0x18003c3f7  call    ?length@_bstr_t@@QEBAIXZ; _bstr_t::length(void)
0x18003c3fc  add     edi, eax
0x18003c3fe  mov     edx, edi; int
0x18003c400  lea     rcx, [rbp+4Fh+var_B0]; this
0x18003c404  call    ??0CComBSTR@ATL@@QEAA@H@Z; ATL::CComBSTR::CComBSTR(int)
0x18003c409  nop
0x18003c40a  mov     r13d, edi
0x18003c40d  inc     r13
0x18003c410  mov     r8, [r15]
0x18003c413  test    r8, r8
0x18003c416  jz      short loc_18003C41B
0x18003c418  mov     r8, [r8]; unsigned __int16 *
0x18003c41b  mov     rdx, r13; unsigned __int64
0x18003c41e  mov     rdi, [rbp+4Fh+var_B0]
0x18003c422  mov     rcx, rdi; unsigned __int16 *
0x18003c425  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003c42a  lea     r8, asc_1800A7EC0; "\\"
0x18003c431  mov     rdx, r13; unsigned __int64
0x18003c434  mov     rcx, rdi; unsigned __int16 *
0x18003c437  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003c43c  mov     r8, [r14]
0x18003c43f  test    r8, r8
0x18003c442  jz      short loc_18003C447
0x18003c444  mov     r8, [r8]; unsigned __int16 *
0x18003c447  mov     rdx, r13; unsigned __int64
0x18003c44a  mov     rcx, rdi; unsigned __int16 *
0x18003c44d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003c452  mov     rdx, rdi; unsigned __int16 *
0x18003c455  lea     rcx, [rbp+4Fh+var_C0]; this
0x18003c459  call    ??0_bstr_t@@QEAA@PEAG_N@Z; _bstr_t::_bstr_t(ushort *,bool)
0x18003c45e  nop
0x18003c45f  mov     [rbp+4Fh+var_B0], 0
0x18003c467  mov     ecx, 30h ; '0'; dwBytes
0x18003c46c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003c471  mov     [rbp+4Fh+var_A0], rax
0x18003c475  mov     edi, [rbp+4Fh+arg_18]
0x18003c478  test    rax, rax
0x18003c47b  jz      short loc_18003C4A0
0x18003c47d  mov     [rsp+110h+var_E0], r12; void *
0x18003c482  mov     [rsp+110h+var_E8], edi; enum _SID_NAME_USE
0x18003c486  lea     rcx, [rbp+4Fh+var_C0]
0x18003c48a  mov     qword ptr [rsp+110h+var_F0], rcx; struct _bstr_t *
0x18003c48f  mov     r9, r15; struct _bstr_t *
0x18003c492  mov     r8, r14; struct _bstr_t *
0x18003c495  xor     edx, edx; bool
0x18003c497  mov     rcx, rax; this
0x18003c49a  call    ??0UserEntry@User@@QEAA@_NAEBV_bstr_t@@11W4_SID_NAME_USE@@PEAX@Z; User::UserEntry::UserEntry(bool,_bstr_t const &,_bstr_t const &,_bstr_t const &,_SID_NAME_USE,void *)
0x18003c49f  nop
0x18003c4a0  test    rax, rax
0x18003c4a3  jz      short loc_18003C4E4
0x18003c4a5  mov     [rbp+4Fh+var_B0], rax
0x18003c4a9  mov     rcx, rax; this
0x18003c4ac  call    ?AddRef@UserEntry@User@@QEAAKXZ; User::UserEntry::AddRef(void)
0x18003c4b1  lea     rdx, [rbp+4Fh+var_B0]
0x18003c4b5  mov     rcx, rsi
0x18003c4b8  call    ??0User@@AEAA@AEBV?$AutoRef@UUserEntry@User@@@wmi@@@Z; User::User(wmi::AutoRef<User::UserEntry> const &)
0x18003c4bd  lea     rcx, [rbp+4Fh+var_B0]
0x18003c4c1  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x18003c4c6  nop
0x18003c4c7  lea     rcx, [rbp+4Fh+var_C0]; this
0x18003c4cb  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18003c4d0  nop
0x18003c4d1  xor     ecx, ecx; bstrString
0x18003c4d3  call    cs:__imp_SysFreeString
0x18003c4da  nop     dword ptr [rax+rax+00h]
0x18003c4df  jmp     loc_18003C3E4
0x18003c4e4  mov     eax, cs:dword_1800C0358
0x18003c4ea  cmp     eax, 2
0x18003c4ed  jbe     loc_18003C57C
0x18003c4f3  xor     edx, edx
0x18003c4f5  call    _tlgKeywordOn
0x18003c4fa  test    al, al
0x18003c4fc  jz      short loc_18003C57C
0x18003c4fe  mov     [rbp+4Fh+var_A8], edi
0x18003c501  lea     rcx, [rbp+4Fh+var_C0]
0x18003c505  call    ??B_bstr_t@@QEBAPEBGXZ; _bstr_t::operator ushort const *(void)
0x18003c50a  mov     rdx, rax
0x18003c50d  lea     rcx, [rbp+4Fh+var_A0]
0x18003c511  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x18003c516  mov     r10, rax
0x18003c519  mov     rcx, r14
0x18003c51c  call    ??B_bstr_t@@QEBAPEBGXZ; _bstr_t::operator ushort const *(void)
0x18003c521  mov     rdx, rax
0x18003c524  lea     rcx, [rbp+4Fh+var_90]
0x18003c528  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x18003c52d  mov     r9, rax
0x18003c530  mov     rcx, r15
0x18003c533  call    ??B_bstr_t@@QEBAPEBGXZ; _bstr_t::operator ushort const *(void)
0x18003c538  mov     rdx, rax
0x18003c53b  lea     rcx, [rbp+4Fh+var_88]
0x18003c53f  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x18003c544  mov     r8, rax
0x18003c547  mov     rdx, r12
0x18003c54a  lea     rcx, [rbp+4Fh+var_80]
0x18003c54e  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x18003c553  lea     rcx, [rbp+4Fh+var_A8]
0x18003c557  mov     [rsp+110h+var_D0], rcx
0x18003c55c  mov     [rsp+110h+var_D8], r10
0x18003c561  mov     [rsp+110h+var_E0], r9
0x18003c566  mov     qword ptr [rsp+110h+var_E8], r8
0x18003c56b  mov     qword ptr [rsp+110h+var_F0], rax
0x18003c570  lea     rdx, unk_1800B14C8
0x18003c577  call    ??$Write@U?$_tlgWrapSid@U_SID@@@@U?$_tlgWrapSz@G@@U2@U2@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSid@U_SID@@@@AEBU?$_tlgWrapSz@G@@44AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSid<_SID>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSid<_SID> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18003c57c  lea     rcx, [rbp+4Fh+pExceptionObject]; this
0x18003c580  call    ??0OutOfMemoryException@wmi@@QEAA@XZ; wmi::OutOfMemoryException::OutOfMemoryException(void)
0x18003c585  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x18003c58c  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x18003c590  call    _CxxThrowException_0
0x18003c596  mov     rcx, [rbp+4Fh+pSid]; pSid
0x18003c59a  test    rcx, rcx
0x18003c59d  jz      short loc_18003C5C7
0x18003c59f  call    cs:__imp_IsValidSid
0x18003c5a6  nop     dword ptr [rax+rax+00h]
0x18003c5ab  test    eax, eax
0x18003c5ad  jz      short loc_18003C5C7
0x18003c5af  mov     rcx, r14
0x18003c5b2  call    ??7_bstr_t@@QEBA_NXZ; _bstr_t::operator!(void)
0x18003c5b7  test    al, al
0x18003c5b9  jnz     short loc_18003C5C7
0x18003c5bb  mov     rcx, r15
0x18003c5be  call    ??7_bstr_t@@QEBA_NXZ; _bstr_t::operator!(void)
0x18003c5c3  test    al, al
0x18003c5c5  jz      short loc_18003C5CC
0x18003c5c7  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003c5cc  mov     edx, 57h ; 'W'; unsigned int
0x18003c5d1  lea     rcx, [rbp+4Fh+pExceptionObject]; this
0x18003c5d5  call    ??0GenericException@wmi@@QEAA@K@Z; wmi::GenericException::GenericException(ulong)
0x18003c5da  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18003c5e1  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x18003c5e5  call    _CxxThrowException_0
0x18003c5eb  mov     eax, cs:dword_1800C0358
0x18003c5f1  cmp     eax, 2
0x18003c5f4  jbe     short loc_18003C665
0x18003c5f6  xor     edx, edx
0x18003c5f8  call    _tlgKeywordOn
0x18003c5fd  test    al, al
0x18003c5ff  jz      short loc_18003C665
0x18003c601  mov     edi, [rbp+4Fh+arg_18]
0x18003c604  mov     [rbp+4Fh+var_A8], edi
0x18003c607  mov     rcx, r14
0x18003c60a  call    ??B_bstr_t@@QEBAPEBGXZ; _bstr_t::operator ushort const *(void)
0x18003c60f  mov     rdx, rax
0x18003c612  lea     rcx, [rbp+4Fh+var_B0]
0x18003c616  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x18003c61b  mov     r9, rax
0x18003c61e  mov     rcx, r15
0x18003c621  call    ??B_bstr_t@@QEBAPEBGXZ; _bstr_t::operator ushort const *(void)
0x18003c626  mov     rdx, rax
0x18003c629  lea     rcx, [rbp+4Fh+var_C0]
0x18003c62d  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x18003c632  mov     r8, rax
0x18003c635  mov     rdx, r12
0x18003c638  lea     rcx, [rbp+4Fh+var_98]
0x18003c63c  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x18003c641  lea     rcx, [rbp+4Fh+var_A8]
0x18003c645  mov     [rsp+110h+var_D8], rcx
0x18003c64a  mov     [rsp+110h+var_E0], r9
0x18003c64f  mov     qword ptr [rsp+110h+var_E8], r8
0x18003c654  mov     qword ptr [rsp+110h+var_F0], rax
0x18003c659  lea     rdx, word_1800B1526
0x18003c660  call    ??$Write@U?$_tlgWrapSid@U_SID@@@@U?$_tlgWrapSz@G@@U2@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSid@U_SID@@@@AEBU?$_tlgWrapSz@G@@4AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSid<_SID>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSid<_SID> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
  ... truncated ...
```
