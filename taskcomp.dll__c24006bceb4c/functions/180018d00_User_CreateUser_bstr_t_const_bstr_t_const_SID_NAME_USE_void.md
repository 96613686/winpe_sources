# User::CreateUser(_bstr_t const &,_bstr_t const &,_SID_NAME_USE,void *)

- ea: `0x180018d00`
- end: `0x18001915f`
- name: `?CreateUser@User@@SA?AV1@AEBV_bstr_t@@0W4_SID_NAME_USE@@PEAX@Z`
- size: `1119`
- prototype: `__int64 __fastcall(__int64, const struct _bstr_t *, const struct _bstr_t *, enum _SID_NAME_USE, PSID pSid)`
- caller_count: `3`
- callee_count: `25`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18001953c`
- `0x180019690`
- `0x180019f78`

## callees

- `0x18000116c`
- `0x1800012a0`
- `0x1800014b4`
- `0x1800014c4`
- `0x1800031a0`
- `0x180003b3c`
- `0x180003ec0`
- `0x180003ef0`
- `0x180004e50`
- `0x180004eec`
- `0x180004f28`
- `0x1800050fc`
- `0x1800058d0`
- `0x180007488`
- `0x18000878c`
- `0x18000978c`
- `0x180009ac0`
- `0x180017210`
- `0x18001724c`
- `0x180018604`
- `0x18001862c`
- `0x180018808`
- `0x180018d00`
- `0x18001ab20`
- `0x18002de50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018d7c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018e6c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018d7c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018e6c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018dba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018dba`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180019087`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180019087`
- `OLEAUT32!__imp_SysFreeString` at `0x180018fc3`
- `OLEAUT32!__imp_SysFreeString` at `0x180018fc3`

## pseudocode

```c
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
  __int64 v17; // rdx
  User::UserEntry *v18; // rdi
  _QWORD *v19; // rax
  unsigned int v20; // edi
  UINT v21; // edi
  unsigned __int64 v22; // r13
  const unsigned __int16 *v23; // r8
  unsigned __int64 v24; // rdx
  unsigned __int16 *v25; // rdi
  const unsigned __int16 *v26; // r8
  User::UserEntry *v27; // rax
  __int64 v28; // rdx
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rax
  _QWORD *v32; // rax
  _QWORD *v33; // r8
  _QWORD *v34; // r9
  _QWORD *v35; // r10
  __int64 v36; // rax
  __int64 v37; // rax
  _QWORD *v38; // rax
  _QWORD *v39; // r8
  _QWORD *v40; // r9
  bool v41; // [rsp+30h] [rbp-91h]
  User::UserEntry *v42; // [rsp+50h] [rbp-71h] BYREF
  __int64 v43; // [rsp+58h] [rbp-69h] BYREF
  unsigned __int16 *v44; // [rsp+60h] [rbp-61h] BYREF
  enum _SID_NAME_USE v45; // [rsp+68h] [rbp-59h] BYREF
  int v46; // [rsp+6Ch] [rbp-55h]
  LPCRITICAL_SECTION v47; // [rsp+70h] [rbp-51h] BYREF
  LPCRITICAL_SECTION v48; // [rsp+78h] [rbp-49h] BYREF
  __int64 v49; // [rsp+80h] [rbp-41h] BYREF
  __int64 v50; // [rsp+88h] [rbp-39h] BYREF
  __int64 v51; // [rsp+90h] [rbp-31h] BYREF
  _BYTE pExceptionObject[120]; // [rsp+98h] [rbp-29h] BYREF

  v9 = 0;
  v46 = 0;
  v43 = 0;
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
    v48 = User::s_cs;
    EnterCriticalSection(User::s_cs);
    v19 = (_QWORD *)User::LookupUser(&v44, pSid);
    wmi::AutoRef<User::UserEntry>::operator=(&v43, *v19);
    wmi::AutoRef<User::UserEntry>::Release(&v44);
    if ( v43 )
    {
      v42 = 0;
      User::UpdateEntry((User *)&v43, a2, a3, (const struct _bstr_t *)&v42, a4, pSid, v41);
      _bstr_t::~_bstr_t((_bstr_t *)&v42);
      User::User(a1, &v43);
    }
    else
    {
      v20 = _bstr_t::length(a2) + 1;
      v21 = _bstr_t::length(a3) + v20;
      ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v44, v21);
      v22 = v21 + 1LL;
      v23 = *(const unsigned __int16 **)a3;
      if ( *(_QWORD *)a3 )
        v23 = *(const unsigned __int16 **)v23;
      v24 = v21 + 1LL;
      v25 = v44;
      StringCchCopyW(v44, v24, v23);
      StringCchCatW(v25, v22, L"\\");
      v26 = *(const unsigned __int16 **)a2;
      if ( *(_QWORD *)a2 )
        v26 = *(const unsigned __int16 **)v26;
      StringCchCatW(v25, v22, v26);
      _bstr_t::_bstr_t((_bstr_t *)&v42, v25);
      v44 = 0;
      v27 = (User::UserEntry *)operator new(0x30u);
      v47 = (LPCRITICAL_SECTION)v27;
      if ( v27 )
        v27 = User::UserEntry::UserEntry(v27, v28, a2, a3, (const struct _bstr_t *)&v42, a4, pSid);
      if ( !v27 )
      {
        if ( (unsigned int)dword_18005D170 > 2 && (unsigned __int8)tlgKeywordOn() )
        {
          v45 = a4;
          v29 = _bstr_t::operator unsigned short const *(&v42);
          _tlgWrapSid<_SID>::_tlgWrapSid<_SID>(&v47, v29);
          v30 = _bstr_t::operator unsigned short const *(a2);
          _tlgWrapSid<_SID>::_tlgWrapSid<_SID>(&v49, v30);
          v31 = _bstr_t::operator unsigned short const *(a3);
          _tlgWrapSid<_SID>::_tlgWrapSid<_SID>(&v50, v31);
          v32 = _tlgWrapSid<_SID>::_tlgWrapSid<_SID>(&v51, (__int64)pSid);
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSid<_SID>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
            (__int64)&v45,
            (__int64)&unk_180055B00,
            (__int64)v33,
            (__int64)v34,
            (__int64)v32,
            v33,
            v34,
            v35);
        }
        wmi::OutOfMemoryException::OutOfMemoryException((wmi::OutOfMemoryException *)pExceptionObject);
        throw (wmi::OutOfMemoryException *)pExceptionObject;
      }
      v44 = (unsigned __int16 *)v27;
      User::UserEntry::AddRef(v27);
      User::User(a1, &v44);
      wmi::AutoRef<User::UserEntry>::Release(&v44);
      _bstr_t::~_bstr_t((_bstr_t *)&v42);
      SysFreeString(0);
    }
  }
  else
  {
    v47 = User::s_cs;
    EnterCriticalSection(User::s_cs);
    v14 = (_QWORD *)User::LookupUser(&v44, pSid);
    wmi::AutoRef<User::UserEntry>::operator=(&v43, *v14);
    wmi::AutoRef<User::UserEntry>::Release(&v44);
    if ( v43 )
    {
      User::User(a1, &v43);
    }
    else
    {
      v16 = (unsigned __int16 *)operator new(0x30u);
      v44 = v16;
      if ( v16 )
      {
        v42 = 0;
        v9 = 2;
        v46 = 2;
        v18 = User::UserEntry::UserEntry((User::UserEntry *)v16, v17, a2, (const struct _bstr_t *)&v42, a2, a4, pSid);
      }
      else
      {
        v18 = 0;
      }
      if ( (v9 & 2) != 0 )
        _bstr_t::~_bstr_t((_bstr_t *)&v42);
      if ( !v18 )
      {
        if ( (unsigned int)dword_18005D170 > 2 && (unsigned __int8)tlgKeywordOn() )
        {
          v45 = a4;
          v36 = _bstr_t::operator unsigned short const *(a2);
          _tlgWrapSid<_SID>::_tlgWrapSid<_SID>(&v44, v36);
          v37 = _bstr_t::operator unsigned short const *(a3);
          _tlgWrapSid<_SID>::_tlgWrapSid<_SID>(&v42, v37);
          v38 = _tlgWrapSid<_SID>::_tlgWrapSid<_SID>(&v48, (__int64)pSid);
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSid<_SID>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
            (__int64)&v45,
            (__int64)&word_180055B5E,
            (__int64)v39,
            (__int64)v40,
            (__int64)v38,
            v39,
            v40);
        }
        wmi::OutOfMemoryException::OutOfMemoryException((wmi::OutOfMemoryException *)pExceptionObject);
        throw (wmi::OutOfMemoryException *)pExceptionObject;
      }
      v42 = v18;
      User::UserEntry::AddRef(v18);
      User::User(a1, &v42);
      wmi::AutoRef<User::UserEntry>::Release(&v42);
    }
  }
  LeaveCriticalSection(v13);
  wmi::AutoRef<User::UserEntry>::Release(&v43);
  return a1;
}

```

## disassembly

```asm
0x180018d00  mov     [rsp-8+arg_18], r9d
0x180018d05  push    rbp
0x180018d06  push    rbx
0x180018d07  push    rsi
0x180018d08  push    rdi
0x180018d09  push    r12
0x180018d0b  push    r13
0x180018d0d  push    r14
0x180018d0f  push    r15
0x180018d11  lea     rbp, [rsp-17h]
0x180018d16  sub     rsp, 0D8h
0x180018d1d  mov     edi, r9d
0x180018d20  mov     r15, r8
0x180018d23  mov     r14, rdx
0x180018d26  mov     rsi, rcx
0x180018d29  xor     r13d, r13d
0x180018d2c  mov     [rbp+4Fh+var_A4], r13d
0x180018d30  mov     [rbp+4Fh+var_B8], r13
0x180018d34  mov     rcx, rdx
0x180018d37  call    ??7_bstr_t@@QEBA_NXZ; _bstr_t::operator!(void)
0x180018d3c  test    al, al
0x180018d3e  jnz     loc_18001907E
0x180018d44  mov     rcx, r8
0x180018d47  call    ??7_bstr_t@@QEBA_NXZ; _bstr_t::operator!(void)
0x180018d4c  test    al, al
0x180018d4e  jnz     loc_18001907E
0x180018d54  mov     r12, [rbp+4Fh+pSid]
0x180018d58  test    r12, r12
0x180018d5b  jz      loc_1800190A9
0x180018d61  call    ?length@_bstr_t@@QEBAIXZ; _bstr_t::length(void)
0x180018d66  mov     rbx, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x180018d6d  mov     rcx, rbx; lpCriticalSection
0x180018d70  test    eax, eax
0x180018d72  jnz     loc_180018E68
0x180018d78  mov     [rbp+4Fh+var_A0], rbx
0x180018d7c  call    cs:__imp_EnterCriticalSection
0x180018d82  nop
0x180018d83  mov     rdx, r12
0x180018d86  lea     rcx, [rbp+4Fh+var_B0]
0x180018d8a  call    ?LookupUser@User@@CA?AV1@PEAX@Z; User::LookupUser(void *)
0x180018d8f  mov     rdx, [rax]
0x180018d92  lea     rcx, [rbp+4Fh+var_B8]
0x180018d96  call    ??4?$AutoRef@UUserEntry@User@@@wmi@@QEAAAEAV01@PEAUUserEntry@User@@@Z; wmi::AutoRef<User::UserEntry>::operator=(User::UserEntry *)
0x180018d9b  lea     rcx, [rbp+4Fh+var_B0]
0x180018d9f  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x180018da4  cmp     [rbp+4Fh+var_B8], r13
0x180018da8  jz      short loc_180018DE1
0x180018daa  lea     rdx, [rbp+4Fh+var_B8]
0x180018dae  mov     rcx, rsi
0x180018db1  call    ??0User@@AEAA@AEBV?$AutoRef@UUserEntry@User@@@wmi@@@Z; User::User(wmi::AutoRef<User::UserEntry> const &)
0x180018db6  nop
0x180018db7  mov     rcx, rbx; lpCriticalSection
0x180018dba  call    cs:__imp_LeaveCriticalSection
0x180018dc0  nop
0x180018dc1  lea     rcx, [rbp+4Fh+var_B8]
0x180018dc5  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x180018dca  mov     rax, rsi
0x180018dcd  add     rsp, 0D8h
0x180018dd4  pop     r15
0x180018dd6  pop     r14
0x180018dd8  pop     r13
0x180018dda  pop     r12
0x180018ddc  pop     rdi
0x180018ddd  pop     rsi
0x180018dde  pop     rbx
0x180018ddf  pop     rbp
0x180018de0  retn
0x180018de1  mov     ecx, 30h ; '0'; Size
0x180018de6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180018deb  mov     [rbp+4Fh+var_B0], rax
0x180018def  test    rax, rax
0x180018df2  jz      short loc_180018E28
0x180018df4  mov     [rbp+4Fh+var_C0], 0
0x180018dfc  mov     r13d, 2
0x180018e02  mov     [rbp+4Fh+var_A4], r13d
0x180018e06  mov     [rsp+110h+var_E0], r12; void *
0x180018e0b  mov     [rsp+110h+var_E8], edi; enum _SID_NAME_USE
0x180018e0f  mov     qword ptr [rsp+110h+var_F0], r14; struct _bstr_t *
0x180018e14  lea     r9, [rbp+4Fh+var_C0]; struct _bstr_t *
0x180018e18  mov     r8, r14; struct _bstr_t *
0x180018e1b  mov     rcx, rax; this
0x180018e1e  call    ??0UserEntry@User@@QEAA@_NAEBV_bstr_t@@11W4_SID_NAME_USE@@PEAX@Z; User::UserEntry::UserEntry(bool,_bstr_t const &,_bstr_t const &,_bstr_t const &,_SID_NAME_USE,void *)
0x180018e23  mov     rdi, rax
0x180018e26  jmp     short loc_180018E2A
0x180018e28  xor     edi, edi
0x180018e2a  test    r13b, 2
0x180018e2e  jz      short loc_180018E39
0x180018e30  lea     rcx, [rbp+4Fh+var_C0]; this
0x180018e34  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180018e39  test    rdi, rdi
0x180018e3c  jz      loc_1800190CD
0x180018e42  mov     [rbp+4Fh+var_C0], rdi
0x180018e46  mov     rcx, rdi; this
0x180018e49  call    ?AddRef@UserEntry@User@@QEAAKXZ; User::UserEntry::AddRef(void)
0x180018e4e  lea     rdx, [rbp+4Fh+var_C0]
0x180018e52  mov     rcx, rsi
0x180018e55  call    ??0User@@AEAA@AEBV?$AutoRef@UUserEntry@User@@@wmi@@@Z; User::User(wmi::AutoRef<User::UserEntry> const &)
0x180018e5a  lea     rcx, [rbp+4Fh+var_C0]
0x180018e5e  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x180018e63  jmp     loc_180018DB7
0x180018e68  mov     [rbp+4Fh+var_98], rbx
0x180018e6c  call    cs:__imp_EnterCriticalSection
0x180018e72  nop
0x180018e73  mov     rdx, r12
0x180018e76  lea     rcx, [rbp+4Fh+var_B0]
0x180018e7a  call    ?LookupUser@User@@CA?AV1@PEAX@Z; User::LookupUser(void *)
0x180018e7f  mov     rdx, [rax]
0x180018e82  lea     rcx, [rbp+4Fh+var_B8]
0x180018e86  call    ??4?$AutoRef@UUserEntry@User@@@wmi@@QEAAAEAV01@PEAUUserEntry@User@@@Z; wmi::AutoRef<User::UserEntry>::operator=(User::UserEntry *)
0x180018e8b  lea     rcx, [rbp+4Fh+var_B0]
0x180018e8f  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x180018e94  cmp     [rbp+4Fh+var_B8], 0
0x180018e99  jz      short loc_180018EDB
0x180018e9b  mov     [rbp+4Fh+var_C0], 0
0x180018ea3  mov     qword ptr [rsp+110h+var_E8], r12; void *
0x180018ea8  mov     [rsp+110h+var_F0], edi; enum _SID_NAME_USE
0x180018eac  lea     r9, [rbp+4Fh+var_C0]; struct _bstr_t *
0x180018eb0  mov     r8, r15; struct _bstr_t *
0x180018eb3  mov     rdx, r14; struct _bstr_t *
0x180018eb6  lea     rcx, [rbp+4Fh+var_B8]; this
0x180018eba  call    ?UpdateEntry@User@@AEBAXAEBV_bstr_t@@00W4_SID_NAME_USE@@PEAX_N@Z; User::UpdateEntry(_bstr_t const &,_bstr_t const &,_bstr_t const &,_SID_NAME_USE,void *,bool)
0x180018ebf  nop
0x180018ec0  lea     rcx, [rbp+4Fh+var_C0]; this
0x180018ec4  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180018ec9  lea     rdx, [rbp+4Fh+var_B8]
0x180018ecd  mov     rcx, rsi
0x180018ed0  call    ??0User@@AEAA@AEBV?$AutoRef@UUserEntry@User@@@wmi@@@Z; User::User(wmi::AutoRef<User::UserEntry> const &)
0x180018ed5  nop
0x180018ed6  jmp     loc_180018DB7
0x180018edb  mov     rcx, r14; this
0x180018ede  call    ?length@_bstr_t@@QEBAIXZ; _bstr_t::length(void)
0x180018ee3  lea     edi, [rax+1]
0x180018ee6  mov     rcx, r15; this
0x180018ee9  call    ?length@_bstr_t@@QEBAIXZ; _bstr_t::length(void)
0x180018eee  add     edi, eax
0x180018ef0  mov     edx, edi; int
0x180018ef2  lea     rcx, [rbp+4Fh+var_B0]; this
0x180018ef6  call    ??0CComBSTR@ATL@@QEAA@H@Z; ATL::CComBSTR::CComBSTR(int)
0x180018efb  nop
0x180018efc  mov     r13d, edi
0x180018eff  inc     r13
0x180018f02  mov     r8, [r15]
0x180018f05  test    r8, r8
0x180018f08  jz      short loc_180018F0D
0x180018f0a  mov     r8, [r8]; unsigned __int16 *
0x180018f0d  mov     rdx, r13; unsigned __int64
0x180018f10  mov     rdi, [rbp+4Fh+var_B0]
0x180018f14  mov     rcx, rdi; unsigned __int16 *
0x180018f17  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180018f1c  lea     r8, asc_18004F6BC; "\\"
0x180018f23  mov     rdx, r13; unsigned __int64
0x180018f26  mov     rcx, rdi; unsigned __int16 *
0x180018f29  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180018f2e  mov     r8, [r14]
0x180018f31  test    r8, r8
0x180018f34  jz      short loc_180018F39
0x180018f36  mov     r8, [r8]; unsigned __int16 *
0x180018f39  mov     rdx, r13; unsigned __int64
0x180018f3c  mov     rcx, rdi; unsigned __int16 *
0x180018f3f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180018f44  mov     rdx, rdi; unsigned __int16 *
0x180018f47  lea     rcx, [rbp+4Fh+var_C0]; this
0x180018f4b  call    ??0_bstr_t@@QEAA@PEAG_N@Z; _bstr_t::_bstr_t(ushort *,bool)
0x180018f50  nop
0x180018f51  mov     [rbp+4Fh+var_B0], 0
0x180018f59  mov     ecx, 30h ; '0'; Size
0x180018f5e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180018f63  mov     [rbp+4Fh+var_A0], rax
0x180018f67  mov     edi, [rbp+4Fh+arg_18]
0x180018f6a  test    rax, rax
0x180018f6d  jz      short loc_180018F90
0x180018f6f  mov     [rsp+110h+var_E0], r12; void *
0x180018f74  mov     [rsp+110h+var_E8], edi; enum _SID_NAME_USE
0x180018f78  lea     rcx, [rbp+4Fh+var_C0]
0x180018f7c  mov     qword ptr [rsp+110h+var_F0], rcx; struct _bstr_t *
0x180018f81  mov     r9, r15; struct _bstr_t *
0x180018f84  mov     r8, r14; struct _bstr_t *
0x180018f87  mov     rcx, rax; this
0x180018f8a  call    ??0UserEntry@User@@QEAA@_NAEBV_bstr_t@@11W4_SID_NAME_USE@@PEAX@Z; User::UserEntry::UserEntry(bool,_bstr_t const &,_bstr_t const &,_bstr_t const &,_SID_NAME_USE,void *)
0x180018f8f  nop
0x180018f90  test    rax, rax
0x180018f93  jz      short loc_180018FCE
0x180018f95  mov     [rbp+4Fh+var_B0], rax
0x180018f99  mov     rcx, rax; this
0x180018f9c  call    ?AddRef@UserEntry@User@@QEAAKXZ; User::UserEntry::AddRef(void)
0x180018fa1  lea     rdx, [rbp+4Fh+var_B0]
0x180018fa5  mov     rcx, rsi
0x180018fa8  call    ??0User@@AEAA@AEBV?$AutoRef@UUserEntry@User@@@wmi@@@Z; User::User(wmi::AutoRef<User::UserEntry> const &)
0x180018fad  lea     rcx, [rbp+4Fh+var_B0]
0x180018fb1  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x180018fb6  nop
0x180018fb7  lea     rcx, [rbp+4Fh+var_C0]; this
0x180018fbb  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180018fc0  nop
0x180018fc1  xor     ecx, ecx; bstrString
0x180018fc3  call    cs:__imp_SysFreeString
0x180018fc9  jmp     loc_180018ED6
0x180018fce  mov     eax, cs:dword_18005D170
0x180018fd4  cmp     eax, 2
0x180018fd7  jbe     loc_180019064
0x180018fdd  call    _tlgKeywordOn
0x180018fe2  test    al, al
0x180018fe4  jz      short loc_180019064
0x180018fe6  mov     [rbp+4Fh+var_A8], edi
0x180018fe9  lea     rcx, [rbp+4Fh+var_C0]
0x180018fed  call    ??B_bstr_t@@QEBAPEBGXZ; _bstr_t::operator ushort const *(void)
0x180018ff2  mov     rdx, rax
0x180018ff5  lea     rcx, [rbp+4Fh+var_A0]
0x180018ff9  call    ??0?$_tlgWrapSid@U_SID@@@@QEAA@PEBU_SID@@@Z; _tlgWrapSid<_SID>::_tlgWrapSid<_SID>(_SID const *)
0x180018ffe  mov     r10, rax
0x180019001  mov     rcx, r14
0x180019004  call    ??B_bstr_t@@QEBAPEBGXZ; _bstr_t::operator ushort const *(void)
0x180019009  mov     rdx, rax
0x18001900c  lea     rcx, [rbp+4Fh+var_90]
0x180019010  call    ??0?$_tlgWrapSid@U_SID@@@@QEAA@PEBU_SID@@@Z; _tlgWrapSid<_SID>::_tlgWrapSid<_SID>(_SID const *)
0x180019015  mov     r9, rax
0x180019018  mov     rcx, r15
0x18001901b  call    ??B_bstr_t@@QEBAPEBGXZ; _bstr_t::operator ushort const *(void)
0x180019020  mov     rdx, rax
0x180019023  lea     rcx, [rbp+4Fh+var_88]
0x180019027  call    ??0?$_tlgWrapSid@U_SID@@@@QEAA@PEBU_SID@@@Z; _tlgWrapSid<_SID>::_tlgWrapSid<_SID>(_SID const *)
0x18001902c  mov     r8, rax
0x18001902f  mov     rdx, r12
0x180019032  lea     rcx, [rbp+4Fh+var_80]
0x180019036  call    ??0?$_tlgWrapSid@U_SID@@@@QEAA@PEBU_SID@@@Z; _tlgWrapSid<_SID>::_tlgWrapSid<_SID>(_SID const *)
0x18001903b  lea     rcx, [rbp+4Fh+var_A8]
0x18001903f  mov     [rsp+110h+var_D0], rcx
0x180019044  mov     [rsp+110h+var_D8], r10
0x180019049  mov     [rsp+110h+var_E0], r9
0x18001904e  mov     qword ptr [rsp+110h+var_E8], r8
0x180019053  mov     qword ptr [rsp+110h+var_F0], rax
0x180019058  lea     rdx, unk_180055B00
0x18001905f  call    ??$Write@U?$_tlgWrapSid@U_SID@@@@U?$_tlgWrapSz@G@@U2@U2@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSid@U_SID@@@@AEBU?$_tlgWrapSz@G@@44AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSid<_SID>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSid<_SID> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180019064  lea     rcx, [rbp+4Fh+pExceptionObject]; this
0x180019068  call    ??0OutOfMemoryException@wmi@@QEAA@XZ; wmi::OutOfMemoryException::OutOfMemoryException(void)
0x18001906d  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x180019074  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x180019078  call    _CxxThrowException_0
0x18001907e  mov     rcx, [rbp+4Fh+pSid]; pSid
0x180019082  test    rcx, rcx
0x180019085  jz      short loc_1800190A9
0x180019087  call    cs:__imp_IsValidSid
0x18001908d  test    eax, eax
0x18001908f  jz      short loc_1800190A9
0x180019091  mov     rcx, r14
0x180019094  call    ??7_bstr_t@@QEBA_NXZ; _bstr_t::operator!(void)
0x180019099  test    al, al
0x18001909b  jnz     short loc_1800190A9
0x18001909d  mov     rcx, r15
0x1800190a0  call    ??7_bstr_t@@QEBA_NXZ; _bstr_t::operator!(void)
0x1800190a5  test    al, al
0x1800190a7  jz      short loc_1800190AE
0x1800190a9  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800190ae  mov     edx, 57h ; 'W'; unsigned int
0x1800190b3  lea     rcx, [rbp+4Fh+pExceptionObject]; this
0x1800190b7  call    ??0GenericException@wmi@@QEAA@K@Z; wmi::GenericException::GenericException(ulong)
0x1800190bc  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x1800190c3  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x1800190c7  call    _CxxThrowException_0
0x1800190cd  mov     eax, cs:dword_18005D170
0x1800190d3  cmp     eax, 2
0x1800190d6  jbe     short loc_180019145
0x1800190d8  call    _tlgKeywordOn
0x1800190dd  test    al, al
0x1800190df  jz      short loc_180019145
0x1800190e1  mov     edi, [rbp+4Fh+arg_18]
0x1800190e4  mov     [rbp+4Fh+var_A8], edi
0x1800190e7  mov     rcx, r14
0x1800190ea  call    ??B_bstr_t@@QEBAPEBGXZ; _bstr_t::operator ushort const *(void)
0x1800190ef  mov     rdx, rax
0x1800190f2  lea     rcx, [rbp+4Fh+var_B0]
0x1800190f6  call    ??0?$_tlgWrapSid@U_SID@@@@QEAA@PEBU_SID@@@Z; _tlgWrapSid<_SID>::_tlgWrapSid<_SID>(_SID const *)
0x1800190fb  mov     r9, rax
0x1800190fe  mov     rcx, r15
0x180019101  call    ??B_bstr_t@@QEBAPEBGXZ; _bstr_t::operator ushort const *(void)
0x180019106  mov     rdx, rax
0x180019109  lea     rcx, [rbp+4Fh+var_C0]
0x18001910d  call    ??0?$_tlgWrapSid@U_SID@@@@QEAA@PEBU_SID@@@Z; _tlgWrapSid<_SID>::_tlgWrapSid<_SID>(_SID const *)
0x180019112  mov     r8, rax
0x180019115  mov     rdx, r12
0x180019118  lea     rcx, [rbp+4Fh+var_98]
0x18001911c  call    ??0?$_tlgWrapSid@U_SID@@@@QEAA@PEBU_SID@@@Z; _tlgWrapSid<_SID>::_tlgWrapSid<_SID>(_SID const *)
0x180019121  lea     rcx, [rbp+4Fh+var_A8]
0x180019125  mov     [rsp+110h+var_D8], rcx
0x18001912a  mov     [rsp+110h+var_E0], r9
0x18001912f  mov     qword ptr [rsp+110h+var_E8], r8
0x180019134  mov     qword ptr [rsp+110h+var_F0], rax
0x180019139  lea     rdx, word_180055B5E
0x180019140  call    ??$Write@U?$_tlgWrapSid@U_SID@@@@U?$_tlgWrapSz@G@@U2@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSid@U_SID@@@@AEBU?$_tlgWrapSz@G@@4AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSid<_SID>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSid<_SID> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180019145  lea     rcx, [rbp+4Fh+pExceptionObject]; this
0x180019149  call    ??0OutOfMemoryException@wmi@@QEAA@XZ; wmi::OutOfMemoryException::OutOfMemoryException(void)
0x18001914e  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x180019155  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x180019159  call    _CxxThrowException_0
```
