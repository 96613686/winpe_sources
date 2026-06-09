# User::CreateUser(_bstr_t const &,_bstr_t const &,_SID_NAME_USE,void *)

- ea: `0x180019f10`
- end: `0x18001a38e`
- name: `?CreateUser@User@@SA?AV1@AEBV_bstr_t@@0W4_SID_NAME_USE@@PEAX@Z`
- size: `1150`
- prototype: `static struct User __high(const struct _bstr_t *, const struct _bstr_t *, enum _SID_NAME_USE, void *)`
- caller_count: `3`
- callee_count: `25`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18001a794`
- `0x18001a8f4`
- `0x18001b27c`

## callees

- `0x180001184`
- `0x1800012b8`
- `0x1800014d0`
- `0x1800014e0`
- `0x180003320`
- `0x180003cec`
- `0x180004090`
- `0x1800040c0`
- `0x1800050d0`
- `0x180005184`
- `0x1800051c4`
- `0x1800053bc`
- `0x180005bc0`
- `0x180007948`
- `0x180008c4c`
- `0x180009c80`
- `0x18000a008`
- `0x1800181ec`
- `0x18001822c`
- `0x18001977c`
- `0x1800197c4`
- `0x1800199cc`
- `0x180019f10`
- `0x18001bee0`
- `0x18002fee8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019f8c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a089`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019f8c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a089`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019fd0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019fd0`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18001a2b0`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18001a2b0`
- `OLEAUT32!__imp_SysFreeString` at `0x18001a1e6`
- `OLEAUT32!__imp_SysFreeString` at `0x18001a1e6`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall User::CreateUser(
        __int64 a1,
        const struct _bstr_t *a2,
        const struct _bstr_t *a3,
        enum _SID_NAME_USE a4,
        PSID pSid)
{
  char v9; // r13
  __int64 v10; // r8
  _bstr_t *v11; // rcx
  unsigned int v12; // eax
  struct _RTL_CRITICAL_SECTION *v13; // rbx
  _QWORD *v14; // rax
  unsigned __int16 *v16; // rax
  bool v17; // dl
  User::UserEntry *v18; // rdi
  _QWORD *v19; // rax
  unsigned int v20; // edi
  unsigned int v21; // edi
  unsigned __int64 v22; // r13
  const unsigned __int16 *v23; // r8
  unsigned __int64 v24; // rdx
  unsigned __int16 *v25; // rdi
  const unsigned __int16 *v26; // r8
  bool v27; // r8
  User::UserEntry *v28; // rax
  bool v29; // dl
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 v33; // rax
  __int64 v34; // r8
  __int64 v35; // r9
  __int64 v36; // r10
  __int64 v37; // rax
  __int64 v38; // rax
  __int64 v39; // rax
  __int64 v40; // r8
  __int64 v41; // r9
  bool v42; // [rsp+30h] [rbp-91h]
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
  if ( (unsigned __int8)_bstr_t::operator!(a2) || (unsigned __int8)_bstr_t::operator!(v10) )
  {
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
    MicrosoftTelemetryAssertTriggeredNoArgs();
    goto LABEL_34;
  }
  if ( !pSid )
    goto LABEL_33;
  v12 = _bstr_t::length(v11);
  v13 = User::s_cs;
  if ( v12 )
  {
    v49 = User::s_cs;
    EnterCriticalSection(User::s_cs);
    v19 = (_QWORD *)User::LookupUser(&v45, pSid);
    wmi::AutoRef<User::UserEntry>::operator=(&v44, *v19);
    wmi::AutoRef<User::UserEntry>::Release(&v45);
    if ( v44 )
    {
      v43 = 0;
      User::UpdateEntry((User *)&v44, a2, a3, (const struct _bstr_t *)&v43, a4, pSid, v42);
      _bstr_t::~_bstr_t((_bstr_t *)&v43);
      wmi::AutoRef<User::UserEntry>::AutoRef<User::UserEntry>(a1, &v44);
    }
    else
    {
      v20 = _bstr_t::length(a2) + 1;
      v21 = _bstr_t::length(a3) + v20;
      ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v45, v21);
      v22 = v21 + 1LL;
      v23 = *(const unsigned __int16 **)a3;
      if ( *(_QWORD *)a3 )
        v23 = *(const unsigned __int16 **)v23;
      v24 = v21 + 1LL;
      v25 = v45;
      StringCchCopyW(v45, v24, v23);
      StringCchCatW(v25, v22, L"\\");
      v26 = *(const unsigned __int16 **)a2;
      if ( *(_QWORD *)a2 )
        v26 = *(const unsigned __int16 **)v26;
      StringCchCatW(v25, v22, v26);
      _bstr_t::_bstr_t((_bstr_t *)&v43, v25, v27);
      v45 = 0;
      v28 = (User::UserEntry *)operator new(0x30u);
      v48 = (LPCRITICAL_SECTION)v28;
      if ( v28 )
        v28 = (User::UserEntry *)User::UserEntry::UserEntry(v28, v29, a2, a3, (const struct _bstr_t *)&v43, a4, pSid);
      if ( !v28 )
      {
        if ( (unsigned int)dword_18005F170 > 2 && (unsigned __int8)tlgKeywordOn() )
        {
          v46 = a4;
          v30 = _bstr_t::operator unsigned short const *(&v43);
          _tlgWrapSid<_SID>::_tlgWrapSid<_SID>(&v48, v30);
          v31 = _bstr_t::operator unsigned short const *(a2);
          _tlgWrapSid<_SID>::_tlgWrapSid<_SID>(v50, v31);
          v32 = _bstr_t::operator unsigned short const *(a3);
          _tlgWrapSid<_SID>::_tlgWrapSid<_SID>(v51, v32);
          v33 = _tlgWrapSid<_SID>::_tlgWrapSid<_SID>(v52, pSid);
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSid<_SID>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
            (unsigned int)&v46,
            (unsigned int)&unk_180057B08,
            v34,
            v35,
            v33,
            v34,
            v35,
            v36,
            (__int64)&v46);
        }
        wmi::OutOfMemoryException::OutOfMemoryException((wmi::OutOfMemoryException *)pExceptionObject);
        throw (wmi::OutOfMemoryException *)pExceptionObject;
      }
      v45 = (unsigned __int16 *)v28;
      User::UserEntry::AddRef(v28);
      wmi::AutoRef<User::UserEntry>::AutoRef<User::UserEntry>(a1, &v45);
      wmi::AutoRef<User::UserEntry>::Release(&v45);
      _bstr_t::~_bstr_t((_bstr_t *)&v43);
      SysFreeString(0);
    }
  }
  else
  {
    v48 = User::s_cs;
    EnterCriticalSection(User::s_cs);
    v14 = (_QWORD *)User::LookupUser(&v45, pSid);
    wmi::AutoRef<User::UserEntry>::operator=(&v44, *v14);
    wmi::AutoRef<User::UserEntry>::Release(&v45);
    if ( v44 )
    {
      wmi::AutoRef<User::UserEntry>::AutoRef<User::UserEntry>(a1, &v44);
    }
    else
    {
      v16 = (unsigned __int16 *)operator new(0x30u);
      v45 = v16;
      if ( v16 )
      {
        v43 = 0;
        v9 = 2;
        v47 = 2;
        v18 = (User::UserEntry *)User::UserEntry::UserEntry(
                                   (User::UserEntry *)v16,
                                   v17,
                                   a2,
                                   (const struct _bstr_t *)&v43,
                                   a2,
                                   a4,
                                   pSid);
      }
      else
      {
        v18 = 0;
      }
      if ( (v9 & 2) != 0 )
        _bstr_t::~_bstr_t((_bstr_t *)&v43);
      if ( !v18 )
      {
        if ( (unsigned int)dword_18005F170 > 2 && (unsigned __int8)tlgKeywordOn() )
        {
          v46 = a4;
          v37 = _bstr_t::operator unsigned short const *(a2);
          _tlgWrapSid<_SID>::_tlgWrapSid<_SID>(&v45, v37);
          v38 = _bstr_t::operator unsigned short const *(a3);
          _tlgWrapSid<_SID>::_tlgWrapSid<_SID>(&v43, v38);
          v39 = _tlgWrapSid<_SID>::_tlgWrapSid<_SID>(&v49, pSid);
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSid<_SID>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
            (unsigned int)&v46,
            (unsigned int)&word_180057B66,
            v40,
            v41,
            v39,
            v40,
            v41,
            (__int64)&v46);
        }
        wmi::OutOfMemoryException::OutOfMemoryException((wmi::OutOfMemoryException *)pExceptionObject);
        throw (wmi::OutOfMemoryException *)pExceptionObject;
      }
      v43 = v18;
      User::UserEntry::AddRef(v18);
      wmi::AutoRef<User::UserEntry>::AutoRef<User::UserEntry>(a1, &v43);
      wmi::AutoRef<User::UserEntry>::Release(&v43);
    }
  }
  LeaveCriticalSection(v13);
  wmi::AutoRef<User::UserEntry>::Release(&v44);
  return a1;
}

```

## disassembly

```asm
0x180019f10  mov     [rsp-8+arg_18], r9d
0x180019f15  push    rbp
0x180019f16  push    rbx
0x180019f17  push    rsi
0x180019f18  push    rdi
0x180019f19  push    r12
0x180019f1b  push    r13
0x180019f1d  push    r14
0x180019f1f  push    r15
0x180019f21  lea     rbp, [rsp-17h]
0x180019f26  sub     rsp, 0D8h
0x180019f2d  mov     edi, r9d
0x180019f30  mov     r15, r8
0x180019f33  mov     r14, rdx
0x180019f36  mov     rsi, rcx
0x180019f39  xor     r13d, r13d
0x180019f3c  mov     [rbp+4Fh+var_A4], r13d
0x180019f40  mov     [rbp+4Fh+var_B8], r13
0x180019f44  mov     rcx, rdx
0x180019f47  call    ??7_bstr_t@@QEBA_NXZ; _bstr_t::operator!(void)
0x180019f4c  test    al, al
0x180019f4e  jnz     loc_18001A2A7
0x180019f54  mov     rcx, r8
0x180019f57  call    ??7_bstr_t@@QEBA_NXZ; _bstr_t::operator!(void)
0x180019f5c  test    al, al
0x180019f5e  jnz     loc_18001A2A7
0x180019f64  mov     r12, [rbp+4Fh+pSid]
0x180019f68  test    r12, r12
0x180019f6b  jz      loc_18001A2D8
0x180019f71  call    ?length@_bstr_t@@QEBAIXZ; _bstr_t::length(void)
0x180019f76  mov     rbx, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x180019f7d  mov     rcx, rbx; lpCriticalSection
0x180019f80  test    eax, eax
0x180019f82  jnz     loc_18001A085
0x180019f88  mov     [rbp+4Fh+var_A0], rbx
0x180019f8c  call    cs:__imp_EnterCriticalSection
0x180019f93  nop     dword ptr [rax+rax+00h]
0x180019f98  nop
0x180019f99  mov     rdx, r12
0x180019f9c  lea     rcx, [rbp+4Fh+var_B0]
0x180019fa0  call    ?LookupUser@User@@CA?AV1@PEAX@Z; User::LookupUser(void *)
0x180019fa5  mov     rdx, [rax]
0x180019fa8  lea     rcx, [rbp+4Fh+var_B8]
0x180019fac  call    ??4?$AutoRef@UUserEntry@User@@@wmi@@QEAAAEAV01@PEAUUserEntry@User@@@Z; wmi::AutoRef<User::UserEntry>::operator=(User::UserEntry *)
0x180019fb1  lea     rcx, [rbp+4Fh+var_B0]
0x180019fb5  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x180019fba  cmp     [rbp+4Fh+var_B8], r13
0x180019fbe  jz      short loc_180019FFE
0x180019fc0  lea     rdx, [rbp+4Fh+var_B8]
0x180019fc4  mov     rcx, rsi
0x180019fc7  call    ??0?$AutoRef@UUserEntry@User@@@wmi@@QEAA@AEBV01@@Z; wmi::AutoRef<User::UserEntry>::AutoRef<User::UserEntry>(wmi::AutoRef<User::UserEntry> const &)
0x180019fcc  nop
0x180019fcd  mov     rcx, rbx; lpCriticalSection
0x180019fd0  call    cs:__imp_LeaveCriticalSection
0x180019fd7  nop     dword ptr [rax+rax+00h]
0x180019fdc  nop
0x180019fdd  lea     rcx, [rbp+4Fh+var_B8]
0x180019fe1  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x180019fe6  mov     rax, rsi
0x180019fe9  add     rsp, 0D8h
0x180019ff0  pop     r15
0x180019ff2  pop     r14
0x180019ff4  pop     r13
0x180019ff6  pop     r12
0x180019ff8  pop     rdi
0x180019ff9  pop     rsi
0x180019ffa  pop     rbx
0x180019ffb  pop     rbp
0x180019ffc  retn
0x180019ffe  mov     ecx, 30h ; '0'; Size
0x18001a003  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001a008  mov     [rbp+4Fh+var_B0], rax
0x18001a00c  test    rax, rax
0x18001a00f  jz      short loc_18001A045
0x18001a011  mov     [rbp+4Fh+var_C0], 0
0x18001a019  mov     r13d, 2
0x18001a01f  mov     [rbp+4Fh+var_A4], r13d
0x18001a023  mov     [rsp+110h+var_E0], r12; void *
0x18001a028  mov     [rsp+110h+var_E8], edi; enum _SID_NAME_USE
0x18001a02c  mov     qword ptr [rsp+110h+var_F0], r14; struct _bstr_t *
0x18001a031  lea     r9, [rbp+4Fh+var_C0]; struct _bstr_t *
0x18001a035  mov     r8, r14; struct _bstr_t *
0x18001a038  mov     rcx, rax; this
0x18001a03b  call    ??0UserEntry@User@@QEAA@_NAEBV_bstr_t@@11W4_SID_NAME_USE@@PEAX@Z; User::UserEntry::UserEntry(bool,_bstr_t const &,_bstr_t const &,_bstr_t const &,_SID_NAME_USE,void *)
0x18001a040  mov     rdi, rax
0x18001a043  jmp     short loc_18001A047
0x18001a045  xor     edi, edi
0x18001a047  test    r13b, 2
0x18001a04b  jz      short loc_18001A056
0x18001a04d  lea     rcx, [rbp+4Fh+var_C0]; this
0x18001a051  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18001a056  test    rdi, rdi
0x18001a059  jz      loc_18001A2FC
0x18001a05f  mov     [rbp+4Fh+var_C0], rdi
0x18001a063  mov     rcx, rdi; this
0x18001a066  call    ?AddRef@UserEntry@User@@QEAAKXZ; User::UserEntry::AddRef(void)
0x18001a06b  lea     rdx, [rbp+4Fh+var_C0]
0x18001a06f  mov     rcx, rsi
0x18001a072  call    ??0?$AutoRef@UUserEntry@User@@@wmi@@QEAA@AEBV01@@Z; wmi::AutoRef<User::UserEntry>::AutoRef<User::UserEntry>(wmi::AutoRef<User::UserEntry> const &)
0x18001a077  lea     rcx, [rbp+4Fh+var_C0]
0x18001a07b  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x18001a080  jmp     loc_180019FCD
0x18001a085  mov     [rbp+4Fh+var_98], rbx
0x18001a089  call    cs:__imp_EnterCriticalSection
0x18001a090  nop     dword ptr [rax+rax+00h]
0x18001a095  nop
0x18001a096  mov     rdx, r12
0x18001a099  lea     rcx, [rbp+4Fh+var_B0]
0x18001a09d  call    ?LookupUser@User@@CA?AV1@PEAX@Z; User::LookupUser(void *)
0x18001a0a2  mov     rdx, [rax]
0x18001a0a5  lea     rcx, [rbp+4Fh+var_B8]
0x18001a0a9  call    ??4?$AutoRef@UUserEntry@User@@@wmi@@QEAAAEAV01@PEAUUserEntry@User@@@Z; wmi::AutoRef<User::UserEntry>::operator=(User::UserEntry *)
0x18001a0ae  lea     rcx, [rbp+4Fh+var_B0]
0x18001a0b2  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x18001a0b7  cmp     [rbp+4Fh+var_B8], 0
0x18001a0bc  jz      short loc_18001A0FE
0x18001a0be  mov     [rbp+4Fh+var_C0], 0
0x18001a0c6  mov     qword ptr [rsp+110h+var_E8], r12; void *
0x18001a0cb  mov     [rsp+110h+var_F0], edi; enum _SID_NAME_USE
0x18001a0cf  lea     r9, [rbp+4Fh+var_C0]; struct _bstr_t *
0x18001a0d3  mov     r8, r15; struct _bstr_t *
0x18001a0d6  mov     rdx, r14; struct _bstr_t *
0x18001a0d9  lea     rcx, [rbp+4Fh+var_B8]; this
0x18001a0dd  call    ?UpdateEntry@User@@AEBAXAEBV_bstr_t@@00W4_SID_NAME_USE@@PEAX_N@Z; User::UpdateEntry(_bstr_t const &,_bstr_t const &,_bstr_t const &,_SID_NAME_USE,void *,bool)
0x18001a0e2  nop
0x18001a0e3  lea     rcx, [rbp+4Fh+var_C0]; this
0x18001a0e7  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18001a0ec  lea     rdx, [rbp+4Fh+var_B8]
0x18001a0f0  mov     rcx, rsi
0x18001a0f3  call    ??0?$AutoRef@UUserEntry@User@@@wmi@@QEAA@AEBV01@@Z; wmi::AutoRef<User::UserEntry>::AutoRef<User::UserEntry>(wmi::AutoRef<User::UserEntry> const &)
0x18001a0f8  nop
0x18001a0f9  jmp     loc_180019FCD
0x18001a0fe  mov     rcx, r14; this
0x18001a101  call    ?length@_bstr_t@@QEBAIXZ; _bstr_t::length(void)
0x18001a106  lea     edi, [rax+1]
0x18001a109  mov     rcx, r15; this
0x18001a10c  call    ?length@_bstr_t@@QEBAIXZ; _bstr_t::length(void)
0x18001a111  add     edi, eax
0x18001a113  mov     edx, edi; int
0x18001a115  lea     rcx, [rbp+4Fh+var_B0]; this
0x18001a119  call    ??0CComBSTR@ATL@@QEAA@H@Z; ATL::CComBSTR::CComBSTR(int)
0x18001a11e  nop
0x18001a11f  mov     r13d, edi
0x18001a122  inc     r13
0x18001a125  mov     r8, [r15]
0x18001a128  test    r8, r8
0x18001a12b  jz      short loc_18001A130
0x18001a12d  mov     r8, [r8]; unsigned __int16 *
0x18001a130  mov     rdx, r13; unsigned __int64
0x18001a133  mov     rdi, [rbp+4Fh+var_B0]
0x18001a137  mov     rcx, rdi; unsigned __int16 *
0x18001a13a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001a13f  lea     r8, asc_1800516CC; "\\"
0x18001a146  mov     rdx, r13; unsigned __int64
0x18001a149  mov     rcx, rdi; unsigned __int16 *
0x18001a14c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001a151  mov     r8, [r14]
0x18001a154  test    r8, r8
0x18001a157  jz      short loc_18001A15C
0x18001a159  mov     r8, [r8]; unsigned __int16 *
0x18001a15c  mov     rdx, r13; unsigned __int64
0x18001a15f  mov     rcx, rdi; unsigned __int16 *
0x18001a162  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001a167  mov     rdx, rdi; unsigned __int16 *
0x18001a16a  lea     rcx, [rbp+4Fh+var_C0]; this
0x18001a16e  call    ??0_bstr_t@@QEAA@PEAG_N@Z; _bstr_t::_bstr_t(ushort *,bool)
0x18001a173  nop
0x18001a174  mov     [rbp+4Fh+var_B0], 0
0x18001a17c  mov     ecx, 30h ; '0'; Size
0x18001a181  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001a186  mov     [rbp+4Fh+var_A0], rax
0x18001a18a  mov     edi, [rbp+4Fh+arg_18]
0x18001a18d  test    rax, rax
0x18001a190  jz      short loc_18001A1B3
0x18001a192  mov     [rsp+110h+var_E0], r12; void *
0x18001a197  mov     [rsp+110h+var_E8], edi; enum _SID_NAME_USE
0x18001a19b  lea     rcx, [rbp+4Fh+var_C0]
0x18001a19f  mov     qword ptr [rsp+110h+var_F0], rcx; struct _bstr_t *
0x18001a1a4  mov     r9, r15; struct _bstr_t *
0x18001a1a7  mov     r8, r14; struct _bstr_t *
0x18001a1aa  mov     rcx, rax; this
0x18001a1ad  call    ??0UserEntry@User@@QEAA@_NAEBV_bstr_t@@11W4_SID_NAME_USE@@PEAX@Z; User::UserEntry::UserEntry(bool,_bstr_t const &,_bstr_t const &,_bstr_t const &,_SID_NAME_USE,void *)
0x18001a1b2  nop
0x18001a1b3  test    rax, rax
0x18001a1b6  jz      short loc_18001A1F7
0x18001a1b8  mov     [rbp+4Fh+var_B0], rax
0x18001a1bc  mov     rcx, rax; this
0x18001a1bf  call    ?AddRef@UserEntry@User@@QEAAKXZ; User::UserEntry::AddRef(void)
0x18001a1c4  lea     rdx, [rbp+4Fh+var_B0]
0x18001a1c8  mov     rcx, rsi
0x18001a1cb  call    ??0?$AutoRef@UUserEntry@User@@@wmi@@QEAA@AEBV01@@Z; wmi::AutoRef<User::UserEntry>::AutoRef<User::UserEntry>(wmi::AutoRef<User::UserEntry> const &)
0x18001a1d0  lea     rcx, [rbp+4Fh+var_B0]
0x18001a1d4  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x18001a1d9  nop
0x18001a1da  lea     rcx, [rbp+4Fh+var_C0]; this
0x18001a1de  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18001a1e3  nop
0x18001a1e4  xor     ecx, ecx; bstrString
0x18001a1e6  call    cs:__imp_SysFreeString
0x18001a1ed  nop     dword ptr [rax+rax+00h]
0x18001a1f2  jmp     loc_18001A0F9
0x18001a1f7  mov     eax, cs:dword_18005F170
0x18001a1fd  cmp     eax, 2
0x18001a200  jbe     loc_18001A28D
0x18001a206  call    _tlgKeywordOn
0x18001a20b  test    al, al
0x18001a20d  jz      short loc_18001A28D
0x18001a20f  mov     [rbp+4Fh+var_A8], edi
0x18001a212  lea     rcx, [rbp+4Fh+var_C0]
0x18001a216  call    ??B_bstr_t@@QEBAPEBGXZ; _bstr_t::operator ushort const *(void)
0x18001a21b  mov     rdx, rax
0x18001a21e  lea     rcx, [rbp+4Fh+var_A0]
0x18001a222  call    ??0?$_tlgWrapSid@U_SID@@@@QEAA@PEBU_SID@@@Z; _tlgWrapSid<_SID>::_tlgWrapSid<_SID>(_SID const *)
0x18001a227  mov     r10, rax
0x18001a22a  mov     rcx, r14
0x18001a22d  call    ??B_bstr_t@@QEBAPEBGXZ; _bstr_t::operator ushort const *(void)
0x18001a232  mov     rdx, rax
0x18001a235  lea     rcx, [rbp+4Fh+var_90]
0x18001a239  call    ??0?$_tlgWrapSid@U_SID@@@@QEAA@PEBU_SID@@@Z; _tlgWrapSid<_SID>::_tlgWrapSid<_SID>(_SID const *)
0x18001a23e  mov     r9, rax
0x18001a241  mov     rcx, r15
0x18001a244  call    ??B_bstr_t@@QEBAPEBGXZ; _bstr_t::operator ushort const *(void)
0x18001a249  mov     rdx, rax
0x18001a24c  lea     rcx, [rbp+4Fh+var_88]
0x18001a250  call    ??0?$_tlgWrapSid@U_SID@@@@QEAA@PEBU_SID@@@Z; _tlgWrapSid<_SID>::_tlgWrapSid<_SID>(_SID const *)
0x18001a255  mov     r8, rax
0x18001a258  mov     rdx, r12
0x18001a25b  lea     rcx, [rbp+4Fh+var_80]
0x18001a25f  call    ??0?$_tlgWrapSid@U_SID@@@@QEAA@PEBU_SID@@@Z; _tlgWrapSid<_SID>::_tlgWrapSid<_SID>(_SID const *)
0x18001a264  lea     rcx, [rbp+4Fh+var_A8]
0x18001a268  mov     [rsp+110h+var_D0], rcx
0x18001a26d  mov     [rsp+110h+var_D8], r10
0x18001a272  mov     [rsp+110h+var_E0], r9
0x18001a277  mov     qword ptr [rsp+110h+var_E8], r8
0x18001a27c  mov     qword ptr [rsp+110h+var_F0], rax
0x18001a281  lea     rdx, unk_180057B08
0x18001a288  call    ??$Write@U?$_tlgWrapSid@U_SID@@@@U?$_tlgWrapSz@G@@U2@U2@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSid@U_SID@@@@AEBU?$_tlgWrapSz@G@@44AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSid<_SID>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSid<_SID> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18001a28d  lea     rcx, [rbp+4Fh+pExceptionObject]; this
0x18001a291  call    ??0OutOfMemoryException@wmi@@QEAA@XZ; wmi::OutOfMemoryException::OutOfMemoryException(void)
0x18001a296  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x18001a29d  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x18001a2a1  call    _CxxThrowException_0
0x18001a2a7  mov     rcx, [rbp+4Fh+pSid]; pSid
0x18001a2ab  test    rcx, rcx
0x18001a2ae  jz      short loc_18001A2D8
0x18001a2b0  call    cs:__imp_IsValidSid
0x18001a2b7  nop     dword ptr [rax+rax+00h]
0x18001a2bc  test    eax, eax
0x18001a2be  jz      short loc_18001A2D8
0x18001a2c0  mov     rcx, r14
0x18001a2c3  call    ??7_bstr_t@@QEBA_NXZ; _bstr_t::operator!(void)
0x18001a2c8  test    al, al
0x18001a2ca  jnz     short loc_18001A2D8
0x18001a2cc  mov     rcx, r15
0x18001a2cf  call    ??7_bstr_t@@QEBA_NXZ; _bstr_t::operator!(void)
0x18001a2d4  test    al, al
0x18001a2d6  jz      short loc_18001A2DD
0x18001a2d8  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001a2dd  mov     edx, 57h ; 'W'; unsigned int
0x18001a2e2  lea     rcx, [rbp+4Fh+pExceptionObject]; this
0x18001a2e6  call    ??0GenericException@wmi@@QEAA@K@Z; wmi::GenericException::GenericException(ulong)
0x18001a2eb  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18001a2f2  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x18001a2f6  call    _CxxThrowException_0
0x18001a2fc  mov     eax, cs:dword_18005F170
0x18001a302  cmp     eax, 2
0x18001a305  jbe     short loc_18001A374
0x18001a307  call    _tlgKeywordOn
0x18001a30c  test    al, al
0x18001a30e  jz      short loc_18001A374
0x18001a310  mov     edi, [rbp+4Fh+arg_18]
0x18001a313  mov     [rbp+4Fh+var_A8], edi
0x18001a316  mov     rcx, r14
0x18001a319  call    ??B_bstr_t@@QEBAPEBGXZ; _bstr_t::operator ushort const *(void)
0x18001a31e  mov     rdx, rax
0x18001a321  lea     rcx, [rbp+4Fh+var_B0]
0x18001a325  call    ??0?$_tlgWrapSid@U_SID@@@@QEAA@PEBU_SID@@@Z; _tlgWrapSid<_SID>::_tlgWrapSid<_SID>(_SID const *)
0x18001a32a  mov     r9, rax
0x18001a32d  mov     rcx, r15
0x18001a330  call    ??B_bstr_t@@QEBAPEBGXZ; _bstr_t::operator ushort const *(void)
0x18001a335  mov     rdx, rax
0x18001a338  lea     rcx, [rbp+4Fh+var_C0]
0x18001a33c  call    ??0?$_tlgWrapSid@U_SID@@@@QEAA@PEBU_SID@@@Z; _tlgWrapSid<_SID>::_tlgWrapSid<_SID>(_SID const *)
0x18001a341  mov     r8, rax
0x18001a344  mov     rdx, r12
0x18001a347  lea     rcx, [rbp+4Fh+var_98]
0x18001a34b  call    ??0?$_tlgWrapSid@U_SID@@@@QEAA@PEBU_SID@@@Z; _tlgWrapSid<_SID>::_tlgWrapSid<_SID>(_SID const *)
0x18001a350  lea     rcx, [rbp+4Fh+var_A8]
0x18001a354  mov     [rsp+110h+var_D8], rcx
0x18001a359  mov     [rsp+110h+var_E0], r9
0x18001a35e  mov     qword ptr [rsp+110h+var_E8], r8
0x18001a363  mov     qword ptr [rsp+110h+var_F0], rax
0x18001a368  lea     rdx, word_180057B66
0x18001a36f  call    ??$Write@U?$_tlgWrapSid@U_SID@@@@U?$_tlgWrapSz@G@@U2@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSid@U_SID@@@@AEBU?$_tlgWrapSz@G@@4AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSid<_SID>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSid<_SID> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18001a374  lea     rcx, [rbp+4Fh+pExceptionObject]; this
0x18001a378  call    ??0OutOfMemoryException@wmi@@QEAA@XZ; wmi::OutOfMemoryException::OutOfMemoryException(void)
0x18001a37d  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x18001a384  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x18001a388  call    _CxxThrowException_0
```
