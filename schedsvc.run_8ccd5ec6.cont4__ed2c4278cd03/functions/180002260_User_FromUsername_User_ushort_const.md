# User::FromUsername(User &,ushort const *)

- ea: `0x180002260`
- end: `0x180002786`
- name: `?FromUsername@User@@SAJAEAV1@PEBG@Z`
- size: `1318`
- prototype: `__int64 __fastcall(struct User *this, LPCWSTR lpAccountName)`
- caller_count: `10`
- callee_count: `13`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800044fc`
- `0x180047ee0`
- `0x18004e9d0`
- `0x180053394`
- `0x180053d9c`
- `0x180056fe0`
- `0x180058cd0`
- `0x1800735b8`
- `0x18007f7d0`
- `0x18007ffb0`

## callees

- `0x180001f8c`
- `0x180002260`
- `0x180002790`
- `0x1800044b0`
- `0x18000fe50`
- `0x180011e40`
- `0x180017740`
- `0x180027910`
- `0x1800460dc`
- `0x1800529a0`
- `0x18005a2bc`
- `0x18005dcd4`
- `0x18006acbc`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x180002536`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180002536`
- `OLEAUT32!__imp_SysFreeString` at `0x1800024ff`
- `OLEAUT32!__imp_SysFreeString` at `0x180002714`
- `OLEAUT32!__imp_SysFreeString` at `0x1800024ff`
- `OLEAUT32!__imp_SysFreeString` at `0x180002714`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002465`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800024e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002510`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002465`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800024e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002510`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000231d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000234a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800023af`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002680`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000231d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000234a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800023af`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002680`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800022d1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800022ee`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002338`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800022d1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800022ee`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002338`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800023c7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800023c7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002481`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002481`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180002409`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180002409`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800022a2`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800022a2`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x180002459`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x1800024cd`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x180002459`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x1800024cd`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall User::FromUsername(struct User *this, LPCWSTR lpAccountName)
{
  OLECHAR *v4; // rbx
  PSID v5; // r13
  struct _RTL_CRITICAL_SECTION *v6; // rsi
  User::UserEntry *v7; // rdi
  struct _RTL_CRITICAL_SECTION *v8; // r14
  User::UserEntry ***v9; // r15
  User::UserEntry **v10; // rbx
  struct _RTL_CRITICAL_SECTION *v11; // rbx
  unsigned int updated; // edi
  void *v14; // rcx
  HLOCAL v15; // rcx
  UINT v16; // edx
  signed int v17; // eax
  signed int LastError; // eax
  User::UserEntry *v19; // rax
  char v20; // di
  __int64 v21; // rbx
  enum _SID_NAME_USE peUse; // [rsp+40h] [rbp-59h] BYREF
  __int64 v23; // [rsp+48h] [rbp-51h] BYREF
  PSID Sid; // [rsp+50h] [rbp-49h] BYREF
  User::UserEntry *v25; // [rsp+58h] [rbp-41h] BYREF
  __int64 v26; // [rsp+60h] [rbp-39h] BYREF
  __int64 v27; // [rsp+68h] [rbp-31h] BYREF
  void **pExceptionObject; // [rsp+70h] [rbp-29h] BYREF
  char v29; // [rsp+78h] [rbp-21h]
  const unsigned __int16 *v30; // [rsp+80h] [rbp-19h]
  __int64 v31; // [rsp+88h] [rbp-11h]
  __int64 v32; // [rsp+90h] [rbp-9h]
  int v33; // [rsp+98h] [rbp-1h]
  __int64 v34; // [rsp+9Ch] [rbp+3h]
  LPCRITICAL_SECTION v35; // [rsp+A8h] [rbp+Fh]
  User::UserEntry *v36; // [rsp+B0h] [rbp+17h]
  DWORD ui; // [rsp+110h] [rbp+77h] BYREF
  DWORD cbSid; // [rsp+118h] [rbp+7Fh] BYREF

  v4 = 0;
  LODWORD(v23) = 0;
  LODWORD(v25) = 0;
  ui = 0;
  cbSid = 0;
  Sid = 0;
  peUse = SidTypeUnknown;
  if ( !ConvertStringSidToSidW(lpAccountName, &Sid) )
  {
    LookupAccountNameLocalW(lpAccountName, 0, &cbSid, 0, &ui, &peUse);
    if ( GetLastError() != 122 )
    {
      LastError = GetLastError();
      updated = LastError;
      if ( LastError > 0 )
        updated = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_9;
    }
    v15 = LocalAlloc(0, cbSid + 1);
    Sid = v15;
    if ( !v15 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids);
      }
      v29 = 0;
      v30 = &qword_1800A8718;
      v31 = 0;
      v32 = 0;
      v33 = 14;
      v34 = -1;
      pExceptionObject = &wmi::GenericException::`vftable';
      throw (wmi::OutOfMemoryException *)&pExceptionObject;
    }
    v16 = ui++;
    if ( v16 )
    {
      v4 = SysAllocStringLen(0, v16);
      if ( !v4 )
        ATL::PrivateAtlThrow(0x8007000E);
      v15 = Sid;
    }
    if ( !LookupAccountNameLocalW(lpAccountName, v15, &cbSid, v4, &ui, &peUse) )
    {
      v17 = GetLastError();
      updated = v17;
      if ( v17 > 0 )
        updated = (unsigned __int16)v17 | 0x80070000;
      SysFreeString(v4);
      goto LABEL_9;
    }
    SysFreeString(v4);
    if ( peUse != SidTypeDomain && peUse > 0 && peUse < SidTypeDeletedAccount )
    {
      updated = User::FromSid(this, Sid, peUse);
      goto LABEL_9;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids);
    }
LABEL_59:
    updated = -2147024809;
    goto LABEL_9;
  }
  v5 = Sid;
  if ( !Sid )
    goto LABEL_59;
  v6 = User::s_cs;
  v35 = User::s_cs;
  EnterCriticalSection(User::s_cs);
  v7 = 0;
  v25 = 0;
  v8 = User::s_cs;
  EnterCriticalSection(User::s_cs);
  v9 = (User::UserEntry ***)User::s_userTable;
  v10 = *(User::UserEntry ***)User::s_userTable;
  if ( *(_QWORD *)User::s_userTable != *((_QWORD *)User::s_userTable + 1) )
  {
    while ( v10 != v9[1] )
    {
      v14 = (void *)*((_QWORD *)*v10 + 4);
      if ( v14 && EqualSid(v14, v5) )
      {
        v7 = *v10;
        if ( *v10 )
          User::UserEntry::AddRef(*v10);
        wmi::AutoRef<User::UserEntry>::Release(&v25);
        v25 = v7;
        break;
      }
      ++v10;
    }
  }
  LeaveCriticalSection(v8);
  if ( v7 )
  {
    v11 = User::s_cs;
    EnterCriticalSection(User::s_cs);
    ++*((_DWORD *)v7 + 11);
    LeaveCriticalSection(v11);
  }
  wmi::AutoRef<User::UserEntry>::Release(this);
  *(_QWORD *)this = v7;
  wmi::AutoRef<User::UserEntry>::Release(&v25);
  if ( *(_QWORD *)this )
  {
    v27 = 0;
    v26 = 0;
    v23 = 0;
    User::UpdateEntry(
      this,
      (const struct _bstr_t *)&v23,
      (const struct _bstr_t *)&v26,
      (const struct _bstr_t *)&v27,
      SidTypeUnknown,
      0,
      0);
    LeaveCriticalSection(v6);
    updated = 0;
  }
  else
  {
    v19 = (User::UserEntry *)operator new(0x30u);
    v36 = v19;
    if ( v19 )
    {
      v27 = 0;
      v26 = 0;
      v23 = 0;
      v20 = 7;
      LODWORD(v25) = 7;
      v21 = User::UserEntry::UserEntry(
              v19,
              0,
              (const struct _bstr_t *)&v23,
              (const struct _bstr_t *)&v26,
              (const struct _bstr_t *)&v27,
              SidTypeUnknown,
              v5);
    }
    else
    {
      v21 = 0;
      v20 = v23;
    }
    if ( (v20 & 4) != 0 )
    {
      v20 &= ~4u;
      _bstr_t::~_bstr_t((_bstr_t *)&v23);
    }
    if ( (v20 & 2) != 0 )
    {
      v20 &= ~2u;
      _bstr_t::~_bstr_t((_bstr_t *)&v26);
    }
    if ( (v20 & 1) != 0 )
      _bstr_t::~_bstr_t((_bstr_t *)&v27);
    if ( !v21 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids);
      }
      v29 = 0;
      v30 = &qword_1800A8718;
      v31 = 0;
      v32 = 0;
      v33 = 14;
      v34 = -1;
      pExceptionObject = &wmi::GenericException::`vftable';
      throw (wmi::OutOfMemoryException *)&pExceptionObject;
    }
    wmi::AutoRef<User::UserEntry>::operator=(this, v21);
    updated = User::UpdateEntry(this);
    LeaveCriticalSection(v6);
  }
LABEL_9:
  if ( Sid )
    LocalFree(Sid);
  return updated;
}

```

## disassembly

```asm
0x180002260  mov     [rsp-8+arg_0], rbx
0x180002265  push    rbp
0x180002266  push    rsi
0x180002267  push    rdi
0x180002268  push    r12
0x18000226a  push    r13
0x18000226c  push    r14
0x18000226e  push    r15
0x180002270  lea     rbp, [rsp-27h]
0x180002275  sub     rsp, 0C0h
0x18000227c  mov     rdi, rdx
0x18000227f  mov     r12, rcx
0x180002282  xor     ebx, ebx
0x180002284  mov     dword ptr [rbp+57h+var_A8], ebx
0x180002287  mov     dword ptr [rbp+57h+var_98], ebx
0x18000228a  mov     [rbp+57h+ui], ebx
0x18000228d  mov     [rbp+57h+cbSid], ebx
0x180002290  mov     [rbp+57h+Sid], rbx
0x180002294  mov     [rbp+57h+var_B0], 8
0x18000229b  lea     rdx, [rbp+57h+Sid]; Sid
0x18000229f  mov     rcx, rdi; StringSid
0x1800022a2  call    cs:__imp_ConvertStringSidToSidW
0x1800022a9  nop     dword ptr [rax+rax+00h]
0x1800022ae  test    eax, eax
0x1800022b0  jz      loc_18000243B
0x1800022b6  mov     r13, [rbp+57h+Sid]
0x1800022ba  test    r13, r13
0x1800022bd  jz      loc_18000277C
0x1800022c3  mov     rsi, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x1800022ca  mov     [rbp+57h+var_48], rsi
0x1800022ce  mov     rcx, rsi; lpCriticalSection
0x1800022d1  call    cs:__imp_EnterCriticalSection
0x1800022d8  nop     dword ptr [rax+rax+00h]
0x1800022dd  nop
0x1800022de  mov     edi, ebx
0x1800022e0  mov     [rbp+57h+var_98], rbx
0x1800022e4  mov     r14, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x1800022eb  mov     rcx, r14; lpCriticalSection
0x1800022ee  call    cs:__imp_EnterCriticalSection
0x1800022f5  nop     dword ptr [rax+rax+00h]
0x1800022fa  mov     r15, cs:?s_userTable@User@@0PEAV?$vector@PEAUUserEntry@User@@V?$allocator@PEAUUserEntry@User@@@std@@@std@@EA; std::vector<User::UserEntry *> * User::s_userTable
0x180002301  mov     rbx, [r15]
0x180002304  cmp     rbx, [r15+8]
0x180002308  jz      short loc_18000231A
0x18000230a  nop     word ptr [rax+rax+00h]
0x180002310  cmp     rbx, [r15+8]
0x180002314  jnz     loc_1800023F1
0x18000231a  mov     rcx, r14; lpCriticalSection
0x18000231d  call    cs:__imp_LeaveCriticalSection
0x180002324  nop     dword ptr [rax+rax+00h]
0x180002329  test    rdi, rdi
0x18000232c  jz      short loc_180002356
0x18000232e  mov     rbx, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x180002335  mov     rcx, rbx; lpCriticalSection
0x180002338  call    cs:__imp_EnterCriticalSection
0x18000233f  nop     dword ptr [rax+rax+00h]
0x180002344  inc     dword ptr [rdi+2Ch]
0x180002347  mov     rcx, rbx; lpCriticalSection
0x18000234a  call    cs:__imp_LeaveCriticalSection
0x180002351  nop     dword ptr [rax+rax+00h]
0x180002356  mov     rcx, r12
0x180002359  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x18000235e  mov     [r12], rdi
0x180002362  lea     rcx, [rbp+57h+var_98]
0x180002366  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x18000236b  cmp     qword ptr [r12], 0
0x180002370  jz      loc_180002557
0x180002376  xor     r14d, r14d
0x180002379  mov     [rbp+57h+var_88], r14
0x18000237d  mov     [rbp+57h+var_90], r14
0x180002381  mov     [rbp+57h+var_A8], r14
0x180002385  mov     byte ptr [rsp+0F0h+var_C0], r14b; bool
0x18000238a  mov     [rsp+0F0h+peUse], r14; void *
0x18000238f  mov     dword ptr [rsp+0F0h+cchReferencedDomainName], 8; enum _SID_NAME_USE
0x180002397  lea     r9, [rbp+57h+var_88]; struct _bstr_t *
0x18000239b  lea     r8, [rbp+57h+var_90]; struct _bstr_t *
0x18000239f  lea     rdx, [rbp+57h+var_A8]; struct _bstr_t *
0x1800023a3  mov     rcx, r12; this
0x1800023a6  call    ?UpdateEntry@User@@AEBAXAEBV_bstr_t@@00W4_SID_NAME_USE@@PEAX_N@Z; User::UpdateEntry(_bstr_t const &,_bstr_t const &,_bstr_t const &,_SID_NAME_USE,void *,bool)
0x1800023ab  nop
0x1800023ac  mov     rcx, rsi; lpCriticalSection
0x1800023af  call    cs:__imp_LeaveCriticalSection
0x1800023b6  nop     dword ptr [rax+rax+00h]
0x1800023bb  mov     edi, r14d
0x1800023be  mov     rcx, [rbp+57h+Sid]; hMem
0x1800023c2  test    rcx, rcx
0x1800023c5  jz      short loc_1800023D3
0x1800023c7  call    cs:__imp_LocalFree
0x1800023ce  nop     dword ptr [rax+rax+00h]
0x1800023d3  mov     eax, edi
0x1800023d5  mov     rbx, [rsp+0F0h+arg_0]
0x1800023dd  add     rsp, 0C0h
0x1800023e4  pop     r15
0x1800023e6  pop     r14
0x1800023e8  pop     r13
0x1800023ea  pop     r12
0x1800023ec  pop     rdi
0x1800023ed  pop     rsi
0x1800023ee  pop     rbp
0x1800023ef  retn
0x1800023f1  mov     rcx, [rbx]
0x1800023f4  mov     rcx, [rcx+20h]; pSid1
0x1800023f8  test    rcx, rcx
0x1800023fb  jnz     short loc_180002406
0x1800023fd  add     rbx, 8
0x180002401  jmp     loc_180002310
0x180002406  mov     rdx, r13; pSid2
0x180002409  call    cs:__imp_EqualSid
0x180002410  nop     dword ptr [rax+rax+00h]
0x180002415  test    eax, eax
0x180002417  jz      short loc_1800023FD
0x180002419  mov     rdi, [rbx]
0x18000241c  test    rdi, rdi
0x18000241f  jz      short loc_180002429
0x180002421  mov     rcx, rdi; this
0x180002424  call    ?AddRef@UserEntry@User@@QEAAKXZ; User::UserEntry::AddRef(void)
0x180002429  lea     rcx, [rbp+57h+var_98]
0x18000242d  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x180002432  mov     [rbp+57h+var_98], rdi
0x180002436  jmp     loc_18000231A
0x18000243b  lea     rax, [rbp+57h+var_B0]
0x18000243f  mov     [rsp+0F0h+peUse], rax; peUse
0x180002444  lea     rax, [rbp+57h+ui]
0x180002448  mov     [rsp+0F0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18000244d  xor     r9d, r9d; ReferencedDomainName
0x180002450  lea     r8, [rbp+57h+cbSid]; cbSid
0x180002454  xor     edx, edx; Sid
0x180002456  mov     rcx, rdi; lpAccountName
0x180002459  call    cs:__imp_LookupAccountNameLocalW
0x180002460  nop     dword ptr [rax+rax+00h]
0x180002465  call    cs:__imp_GetLastError
0x18000246c  nop     dword ptr [rax+rax+00h]
0x180002471  cmp     eax, 7Ah ; 'z'
0x180002474  jnz     loc_180002510
0x18000247a  mov     edx, [rbp+57h+cbSid]
0x18000247d  inc     edx; uBytes
0x18000247f  xor     ecx, ecx; uFlags
0x180002481  call    cs:__imp_LocalAlloc
0x180002488  nop     dword ptr [rax+rax+00h]
0x18000248d  mov     rcx, rax
0x180002490  mov     [rbp+57h+Sid], rax
0x180002494  test    rax, rax
0x180002497  jz      loc_180002691
0x18000249d  mov     edx, [rbp+57h+ui]; ui
0x1800024a0  lea     eax, [rdx+1]
0x1800024a3  mov     [rbp+57h+ui], eax
0x1800024a6  test    edx, edx
0x1800024a8  jnz     loc_180002534
0x1800024ae  lea     rax, [rbp+57h+var_B0]
0x1800024b2  mov     [rsp+0F0h+peUse], rax; peUse
0x1800024b7  lea     rax, [rbp+57h+ui]
0x1800024bb  mov     [rsp+0F0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x1800024c0  mov     r9, rbx; ReferencedDomainName
0x1800024c3  lea     r8, [rbp+57h+cbSid]; cbSid
0x1800024c7  mov     rdx, rcx; Sid
0x1800024ca  mov     rcx, rdi; lpAccountName
0x1800024cd  call    cs:__imp_LookupAccountNameLocalW
0x1800024d4  nop     dword ptr [rax+rax+00h]
0x1800024d9  test    eax, eax
0x1800024db  jnz     loc_180002711
0x1800024e1  call    cs:__imp_GetLastError
0x1800024e8  nop     dword ptr [rax+rax+00h]
0x1800024ed  mov     edi, eax
0x1800024ef  test    eax, eax
0x1800024f1  jle     short loc_1800024FC
0x1800024f3  movzx   edi, ax
0x1800024f6  or      edi, 80070000h
0x1800024fc  mov     rcx, rbx; bstrString
0x1800024ff  call    cs:__imp_SysFreeString
0x180002506  nop     dword ptr [rax+rax+00h]
0x18000250b  jmp     loc_1800023BE
0x180002510  call    cs:__imp_GetLastError
0x180002517  nop     dword ptr [rax+rax+00h]
0x18000251c  mov     edi, eax
0x18000251e  test    eax, eax
0x180002520  jle     loc_1800023BE
0x180002526  movzx   edi, ax
0x180002529  or      edi, 80070000h
0x18000252f  jmp     loc_1800023BE
0x180002534  xor     ecx, ecx; strIn
0x180002536  call    cs:__imp_SysAllocStringLen
0x18000253d  nop     dword ptr [rax+rax+00h]
0x180002542  mov     rbx, rax
0x180002545  test    rax, rax
0x180002548  jz      loc_180002706
0x18000254e  mov     rcx, [rbp+57h+Sid]
0x180002552  jmp     loc_1800024AE
0x180002557  mov     ecx, 30h ; '0'; dwBytes
0x18000255c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002561  mov     [rbp+57h+var_40], rax
0x180002565  xor     r14d, r14d
0x180002568  test    rax, rax
0x18000256b  jz      short loc_1800025AE
0x18000256d  mov     [rbp+57h+var_88], r14
0x180002571  mov     [rbp+57h+var_90], r14
0x180002575  mov     [rbp+57h+var_A8], r14
0x180002579  mov     edi, 7
0x18000257e  mov     dword ptr [rbp+57h+var_98], edi
0x180002581  mov     [rsp+0F0h+var_C0], r13; void *
0x180002586  mov     dword ptr [rsp+0F0h+peUse], 8; enum _SID_NAME_USE
0x18000258e  lea     rcx, [rbp+57h+var_88]
0x180002592  mov     [rsp+0F0h+cchReferencedDomainName], rcx; struct _bstr_t *
0x180002597  lea     r9, [rbp+57h+var_90]; struct _bstr_t *
0x18000259b  lea     r8, [rbp+57h+var_A8]; struct _bstr_t *
0x18000259f  xor     edx, edx; bool
0x1800025a1  mov     rcx, rax; this
0x1800025a4  call    ??0UserEntry@User@@QEAA@_NAEBV_bstr_t@@11W4_SID_NAME_USE@@PEAX@Z; User::UserEntry::UserEntry(bool,_bstr_t const &,_bstr_t const &,_bstr_t const &,_SID_NAME_USE,void *)
0x1800025a9  mov     rbx, rax
0x1800025ac  jmp     short loc_1800025B4
0x1800025ae  mov     rbx, r14
0x1800025b1  mov     edi, dword ptr [rbp+57h+var_A8]
0x1800025b4  test    dil, 4
0x1800025b8  jz      short loc_1800025C7
0x1800025ba  and     edi, 0FFFFFFFBh
0x1800025bd  lea     rcx, [rbp+57h+var_A8]; this
0x1800025c1  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x1800025c6  nop
0x1800025c7  test    dil, 2
0x1800025cb  jz      short loc_1800025DA
0x1800025cd  and     edi, 0FFFFFFFDh
0x1800025d0  lea     rcx, [rbp+57h+var_90]; this
0x1800025d4  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x1800025d9  nop
0x1800025da  test    dil, 1
0x1800025de  jz      short loc_1800025E9
0x1800025e0  lea     rcx, [rbp+57h+var_88]; this
0x1800025e4  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x1800025e9  test    rbx, rbx
0x1800025ec  jnz     short loc_180002668
0x1800025ee  lea     rax, WPP_GLOBAL_Control
0x1800025f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800025fc  cmp     rcx, rax
0x1800025ff  jz      short loc_180002622
0x180002601  test    byte ptr [rcx+1Ch], 80h
0x180002605  jz      short loc_180002622
0x180002607  cmp     byte ptr [rcx+19h], 2
0x18000260b  jb      short loc_180002622
0x18000260d  mov     edx, 17h
0x180002612  lea     r8, WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids
0x180002619  mov     rcx, [rcx+10h]
0x18000261d  call    WPP_SF_
0x180002622  mov     [rbp+57h+var_78], 0
0x180002626  lea     rax, qword_1800A8718
0x18000262d  mov     [rbp+57h+var_70], rax
0x180002631  mov     [rbp+57h+var_68], r14
0x180002635  mov     [rbp+57h+var_60], 0
0x18000263d  mov     [rbp+57h+var_58], 0Eh
0x180002644  mov     [rbp+57h+var_54], 0FFFFFFFFFFFFFFFFh
0x18000264c  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180002653  mov     [rbp+57h+pExceptionObject], rax
0x180002657  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x18000265e  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180002662  call    _CxxThrowException_0
0x180002668  mov     rdx, rbx
0x18000266b  mov     rcx, r12
0x18000266e  call    ??4?$AutoRef@UUserEntry@User@@@wmi@@QEAAAEAV01@PEAUUserEntry@User@@@Z; wmi::AutoRef<User::UserEntry>::operator=(User::UserEntry *)
0x180002673  mov     rcx, r12; this
0x180002676  call    ?UpdateEntry@User@@AEBAJXZ; User::UpdateEntry(void)
0x18000267b  mov     edi, eax
0x18000267d  mov     rcx, rsi; lpCriticalSection
0x180002680  call    cs:__imp_LeaveCriticalSection
0x180002687  nop     dword ptr [rax+rax+00h]
0x18000268c  jmp     loc_1800023BE
0x180002691  lea     rax, WPP_GLOBAL_Control
0x180002698  mov     rcx, cs:WPP_GLOBAL_Control
0x18000269f  cmp     rcx, rax
0x1800026a2  jz      short loc_1800026C5
0x1800026a4  test    byte ptr [rcx+1Ch], 80h
0x1800026a8  jz      short loc_1800026C5
0x1800026aa  cmp     byte ptr [rcx+19h], 2
0x1800026ae  jb      short loc_1800026C5
0x1800026b0  mov     edx, 15h
0x1800026b5  lea     r8, WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids
0x1800026bc  mov     rcx, [rcx+10h]
0x1800026c0  call    WPP_SF_
0x1800026c5  mov     [rbp+57h+var_78], bl
0x1800026c8  lea     rax, qword_1800A8718
0x1800026cf  mov     [rbp+57h+var_70], rax
0x1800026d3  mov     [rbp+57h+var_68], rbx
0x1800026d7  mov     [rbp+57h+var_60], rbx
0x1800026db  mov     [rbp+57h+var_58], 0Eh
0x1800026e2  mov     [rbp+57h+var_54], 0FFFFFFFFFFFFFFFFh
0x1800026ea  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x1800026f1  mov     [rbp+57h+pExceptionObject], rax
0x1800026f5  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x1800026fc  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180002700  call    _CxxThrowException_0
0x180002706  mov     ecx, 8007000Eh; unsigned int
0x18000270b  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x180002711  mov     rcx, rbx; bstrString
0x180002714  call    cs:__imp_SysFreeString
0x18000271b  nop     dword ptr [rax+rax+00h]
0x180002720  mov     r8d, [rbp+57h+var_B0]; enum _SID_NAME_USE
0x180002724  cmp     r8d, 3
0x180002728  jz      short loc_180002748
0x18000272a  test    r8d, r8d
0x18000272d  jle     short loc_180002748
0x18000272f  cmp     r8d, 6
0x180002733  jge     short loc_180002748
0x180002735  mov     rdx, [rbp+57h+Sid]; void *
  ... truncated ...
```
