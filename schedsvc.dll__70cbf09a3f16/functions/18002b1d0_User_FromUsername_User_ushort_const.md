# User::FromUsername(User &,ushort const *)

- ea: `0x18002b1d0`
- end: `0x18002b67d`
- name: `?FromUsername@User@@SAJAEAV1@PEBG@Z`
- size: `1197`
- prototype: `__int64 __fastcall(struct User *this, LPCWSTR lpAccountName)`
- caller_count: `10`
- callee_count: `13`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18002d3d0`
- `0x180045df0`
- `0x18004c6d0`
- `0x180050e14`
- `0x1800517ec`
- `0x180054700`
- `0x180056350`
- `0x18006fd64`
- `0x18007b570`
- `0x18007bd50`

## callees

- `0x18000b4e0`
- `0x18000dc30`
- `0x18002ab90`
- `0x18002af2c`
- `0x18002b1d0`
- `0x18002b690`
- `0x18002d390`
- `0x180030f80`
- `0x180043fcc`
- `0x1800504b4`
- `0x18005790c`
- `0x18005b124`
- `0x1800679e0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x18002b43f`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18002b43f`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b414`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b611`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b414`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b611`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b39a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b3fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b41f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b39a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b3fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b41f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002b27d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002b29e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002b2fd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002b583`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002b27d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002b29e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002b2fd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002b583`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002b23b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002b252`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002b292`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002b23b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002b252`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002b292`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b30f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b30f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002b3ac`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002b3ac`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18002b34a`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18002b34a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18002b212`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18002b212`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x18002b394`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x18002b3ee`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x18002b394`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x18002b3ee`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
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
      v30 = &qword_1800A4718;
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
      v30 = &qword_1800A4718;
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
0x18002b1d0  mov     [rsp-8+arg_0], rbx
0x18002b1d5  push    rbp
0x18002b1d6  push    rsi
0x18002b1d7  push    rdi
0x18002b1d8  push    r12
0x18002b1da  push    r13
0x18002b1dc  push    r14
0x18002b1de  push    r15
0x18002b1e0  lea     rbp, [rsp-27h]
0x18002b1e5  sub     rsp, 0C0h
0x18002b1ec  mov     rdi, rdx
0x18002b1ef  mov     r12, rcx
0x18002b1f2  xor     ebx, ebx
0x18002b1f4  mov     dword ptr [rbp+57h+var_A8], ebx
0x18002b1f7  mov     dword ptr [rbp+57h+var_98], ebx
0x18002b1fa  mov     [rbp+57h+ui], ebx
0x18002b1fd  mov     [rbp+57h+cbSid], ebx
0x18002b200  mov     [rbp+57h+Sid], rbx
0x18002b204  mov     [rbp+57h+var_B0], 8
0x18002b20b  lea     rdx, [rbp+57h+Sid]; Sid
0x18002b20f  mov     rcx, rdi; StringSid
0x18002b212  call    cs:__imp_ConvertStringSidToSidW
0x18002b218  test    eax, eax
0x18002b21a  jz      loc_18002B376
0x18002b220  mov     r13, [rbp+57h+Sid]
0x18002b224  test    r13, r13
0x18002b227  jz      loc_18002B673
0x18002b22d  mov     rsi, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x18002b234  mov     [rbp+57h+var_48], rsi
0x18002b238  mov     rcx, rsi; lpCriticalSection
0x18002b23b  call    cs:__imp_EnterCriticalSection
0x18002b241  nop
0x18002b242  mov     edi, ebx
0x18002b244  mov     [rbp+57h+var_98], rbx
0x18002b248  mov     r14, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x18002b24f  mov     rcx, r14; lpCriticalSection
0x18002b252  call    cs:__imp_EnterCriticalSection
0x18002b258  mov     r15, cs:?s_userTable@User@@0PEAV?$vector@PEAUUserEntry@User@@V?$allocator@PEAUUserEntry@User@@@std@@@std@@EA; std::vector<User::UserEntry *> * User::s_userTable
0x18002b25f  mov     rbx, [r15]
0x18002b262  cmp     rbx, [r15+8]
0x18002b266  jz      short loc_18002B27A
0x18002b268  nop     dword ptr [rax+rax+00000000h]
0x18002b270  cmp     rbx, [r15+8]
0x18002b274  jnz     loc_18002B332
0x18002b27a  mov     rcx, r14; lpCriticalSection
0x18002b27d  call    cs:__imp_LeaveCriticalSection
0x18002b283  test    rdi, rdi
0x18002b286  jz      short loc_18002B2A4
0x18002b288  mov     rbx, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x18002b28f  mov     rcx, rbx; lpCriticalSection
0x18002b292  call    cs:__imp_EnterCriticalSection
0x18002b298  inc     dword ptr [rdi+2Ch]
0x18002b29b  mov     rcx, rbx; lpCriticalSection
0x18002b29e  call    cs:__imp_LeaveCriticalSection
0x18002b2a4  mov     rcx, r12
0x18002b2a7  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x18002b2ac  mov     [r12], rdi
0x18002b2b0  lea     rcx, [rbp+57h+var_98]
0x18002b2b4  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x18002b2b9  cmp     qword ptr [r12], 0
0x18002b2be  jz      loc_18002B45A
0x18002b2c4  xor     r14d, r14d
0x18002b2c7  mov     [rbp+57h+var_88], r14
0x18002b2cb  mov     [rbp+57h+var_90], r14
0x18002b2cf  mov     [rbp+57h+var_A8], r14
0x18002b2d3  mov     byte ptr [rsp+0F0h+var_C0], r14b; bool
0x18002b2d8  mov     [rsp+0F0h+peUse], r14; void *
0x18002b2dd  mov     dword ptr [rsp+0F0h+cchReferencedDomainName], 8; enum _SID_NAME_USE
0x18002b2e5  lea     r9, [rbp+57h+var_88]; struct _bstr_t *
0x18002b2e9  lea     r8, [rbp+57h+var_90]; struct _bstr_t *
0x18002b2ed  lea     rdx, [rbp+57h+var_A8]; struct _bstr_t *
0x18002b2f1  mov     rcx, r12; this
0x18002b2f4  call    ?UpdateEntry@User@@AEBAXAEBV_bstr_t@@00W4_SID_NAME_USE@@PEAX_N@Z; User::UpdateEntry(_bstr_t const &,_bstr_t const &,_bstr_t const &,_SID_NAME_USE,void *,bool)
0x18002b2f9  nop
0x18002b2fa  mov     rcx, rsi; lpCriticalSection
0x18002b2fd  call    cs:__imp_LeaveCriticalSection
0x18002b303  mov     edi, r14d
0x18002b306  mov     rcx, [rbp+57h+Sid]; hMem
0x18002b30a  test    rcx, rcx
0x18002b30d  jz      short loc_18002B315
0x18002b30f  call    cs:__imp_LocalFree
0x18002b315  mov     eax, edi
0x18002b317  mov     rbx, [rsp+0F0h+arg_0]
0x18002b31f  add     rsp, 0C0h
0x18002b326  pop     r15
0x18002b328  pop     r14
0x18002b32a  pop     r13
0x18002b32c  pop     r12
0x18002b32e  pop     rdi
0x18002b32f  pop     rsi
0x18002b330  pop     rbp
0x18002b331  retn
0x18002b332  mov     rcx, [rbx]
0x18002b335  mov     rcx, [rcx+20h]; pSid1
0x18002b339  test    rcx, rcx
0x18002b33c  jnz     short loc_18002B347
0x18002b33e  add     rbx, 8
0x18002b342  jmp     loc_18002B270
0x18002b347  mov     rdx, r13; pSid2
0x18002b34a  call    cs:__imp_EqualSid
0x18002b350  test    eax, eax
0x18002b352  jz      short loc_18002B33E
0x18002b354  mov     rdi, [rbx]
0x18002b357  test    rdi, rdi
0x18002b35a  jz      short loc_18002B364
0x18002b35c  mov     rcx, rdi; this
0x18002b35f  call    ?AddRef@UserEntry@User@@QEAAKXZ; User::UserEntry::AddRef(void)
0x18002b364  lea     rcx, [rbp+57h+var_98]
0x18002b368  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x18002b36d  mov     [rbp+57h+var_98], rdi
0x18002b371  jmp     loc_18002B27A
0x18002b376  lea     rax, [rbp+57h+var_B0]
0x18002b37a  mov     [rsp+0F0h+peUse], rax; peUse
0x18002b37f  lea     rax, [rbp+57h+ui]
0x18002b383  mov     [rsp+0F0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18002b388  xor     r9d, r9d; ReferencedDomainName
0x18002b38b  lea     r8, [rbp+57h+cbSid]; cbSid
0x18002b38f  xor     edx, edx; Sid
0x18002b391  mov     rcx, rdi; lpAccountName
0x18002b394  call    cs:__imp_LookupAccountNameLocalW
0x18002b39a  call    cs:__imp_GetLastError
0x18002b3a0  cmp     eax, 7Ah ; 'z'
0x18002b3a3  jnz     short loc_18002B41F
0x18002b3a5  mov     edx, [rbp+57h+cbSid]
0x18002b3a8  inc     edx; uBytes
0x18002b3aa  xor     ecx, ecx; uFlags
0x18002b3ac  call    cs:__imp_LocalAlloc
0x18002b3b2  mov     rcx, rax
0x18002b3b5  mov     [rbp+57h+Sid], rax
0x18002b3b9  test    rax, rax
0x18002b3bc  jz      loc_18002B58E
0x18002b3c2  mov     edx, [rbp+57h+ui]; ui
0x18002b3c5  lea     eax, [rdx+1]
0x18002b3c8  mov     [rbp+57h+ui], eax
0x18002b3cb  test    edx, edx
0x18002b3cd  jnz     short loc_18002B43D
0x18002b3cf  lea     rax, [rbp+57h+var_B0]
0x18002b3d3  mov     [rsp+0F0h+peUse], rax; peUse
0x18002b3d8  lea     rax, [rbp+57h+ui]
0x18002b3dc  mov     [rsp+0F0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18002b3e1  mov     r9, rbx; ReferencedDomainName
0x18002b3e4  lea     r8, [rbp+57h+cbSid]; cbSid
0x18002b3e8  mov     rdx, rcx; Sid
0x18002b3eb  mov     rcx, rdi; lpAccountName
0x18002b3ee  call    cs:__imp_LookupAccountNameLocalW
0x18002b3f4  test    eax, eax
0x18002b3f6  jnz     loc_18002B60E
0x18002b3fc  call    cs:__imp_GetLastError
0x18002b402  mov     edi, eax
0x18002b404  test    eax, eax
0x18002b406  jle     short loc_18002B411
0x18002b408  movzx   edi, ax
0x18002b40b  or      edi, 80070000h
0x18002b411  mov     rcx, rbx; bstrString
0x18002b414  call    cs:__imp_SysFreeString
0x18002b41a  jmp     loc_18002B306
0x18002b41f  call    cs:__imp_GetLastError
0x18002b425  mov     edi, eax
0x18002b427  test    eax, eax
0x18002b429  jle     loc_18002B306
0x18002b42f  movzx   edi, ax
0x18002b432  or      edi, 80070000h
0x18002b438  jmp     loc_18002B306
0x18002b43d  xor     ecx, ecx; strIn
0x18002b43f  call    cs:__imp_SysAllocStringLen
0x18002b445  mov     rbx, rax
0x18002b448  test    rax, rax
0x18002b44b  jz      loc_18002B603
0x18002b451  mov     rcx, [rbp+57h+Sid]
0x18002b455  jmp     loc_18002B3CF
0x18002b45a  mov     ecx, 30h ; '0'; dwBytes
0x18002b45f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002b464  mov     [rbp+57h+var_40], rax
0x18002b468  xor     r14d, r14d
0x18002b46b  test    rax, rax
0x18002b46e  jz      short loc_18002B4B1
0x18002b470  mov     [rbp+57h+var_88], r14
0x18002b474  mov     [rbp+57h+var_90], r14
0x18002b478  mov     [rbp+57h+var_A8], r14
0x18002b47c  mov     edi, 7
0x18002b481  mov     dword ptr [rbp+57h+var_98], edi
0x18002b484  mov     [rsp+0F0h+var_C0], r13; void *
0x18002b489  mov     dword ptr [rsp+0F0h+peUse], 8; enum _SID_NAME_USE
0x18002b491  lea     rcx, [rbp+57h+var_88]
0x18002b495  mov     [rsp+0F0h+cchReferencedDomainName], rcx; struct _bstr_t *
0x18002b49a  lea     r9, [rbp+57h+var_90]; struct _bstr_t *
0x18002b49e  lea     r8, [rbp+57h+var_A8]; struct _bstr_t *
0x18002b4a2  xor     edx, edx; bool
0x18002b4a4  mov     rcx, rax; this
0x18002b4a7  call    ??0UserEntry@User@@QEAA@_NAEBV_bstr_t@@11W4_SID_NAME_USE@@PEAX@Z; User::UserEntry::UserEntry(bool,_bstr_t const &,_bstr_t const &,_bstr_t const &,_SID_NAME_USE,void *)
0x18002b4ac  mov     rbx, rax
0x18002b4af  jmp     short loc_18002B4B7
0x18002b4b1  mov     rbx, r14
0x18002b4b4  mov     edi, dword ptr [rbp+57h+var_A8]
0x18002b4b7  test    dil, 4
0x18002b4bb  jz      short loc_18002B4CA
0x18002b4bd  and     edi, 0FFFFFFFBh
0x18002b4c0  lea     rcx, [rbp+57h+var_A8]; this
0x18002b4c4  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18002b4c9  nop
0x18002b4ca  test    dil, 2
0x18002b4ce  jz      short loc_18002B4DD
0x18002b4d0  and     edi, 0FFFFFFFDh
0x18002b4d3  lea     rcx, [rbp+57h+var_90]; this
0x18002b4d7  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18002b4dc  nop
0x18002b4dd  test    dil, 1
0x18002b4e1  jz      short loc_18002B4EC
0x18002b4e3  lea     rcx, [rbp+57h+var_88]; this
0x18002b4e7  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18002b4ec  test    rbx, rbx
0x18002b4ef  jnz     short loc_18002B56B
0x18002b4f1  lea     rax, WPP_GLOBAL_Control
0x18002b4f8  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b4ff  cmp     rcx, rax
0x18002b502  jz      short loc_18002B525
0x18002b504  test    byte ptr [rcx+1Ch], 80h
0x18002b508  jz      short loc_18002B525
0x18002b50a  cmp     byte ptr [rcx+19h], 2
0x18002b50e  jb      short loc_18002B525
0x18002b510  mov     edx, 17h
0x18002b515  lea     r8, WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids
0x18002b51c  mov     rcx, [rcx+10h]
0x18002b520  call    WPP_SF_
0x18002b525  mov     [rbp+57h+var_78], 0
0x18002b529  lea     rax, qword_1800A4718
0x18002b530  mov     [rbp+57h+var_70], rax
0x18002b534  mov     [rbp+57h+var_68], r14
0x18002b538  mov     [rbp+57h+var_60], 0
0x18002b540  mov     [rbp+57h+var_58], 0Eh
0x18002b547  mov     [rbp+57h+var_54], 0FFFFFFFFFFFFFFFFh
0x18002b54f  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18002b556  mov     [rbp+57h+pExceptionObject], rax
0x18002b55a  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x18002b561  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18002b565  call    _CxxThrowException_0
0x18002b56b  mov     rdx, rbx
0x18002b56e  mov     rcx, r12
0x18002b571  call    ??4?$AutoRef@UUserEntry@User@@@wmi@@QEAAAEAV01@PEAUUserEntry@User@@@Z; wmi::AutoRef<User::UserEntry>::operator=(User::UserEntry *)
0x18002b576  mov     rcx, r12; this
0x18002b579  call    ?UpdateEntry@User@@AEBAJXZ; User::UpdateEntry(void)
0x18002b57e  mov     edi, eax
0x18002b580  mov     rcx, rsi; lpCriticalSection
0x18002b583  call    cs:__imp_LeaveCriticalSection
0x18002b589  jmp     loc_18002B306
0x18002b58e  lea     rax, WPP_GLOBAL_Control
0x18002b595  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b59c  cmp     rcx, rax
0x18002b59f  jz      short loc_18002B5C2
0x18002b5a1  test    byte ptr [rcx+1Ch], 80h
0x18002b5a5  jz      short loc_18002B5C2
0x18002b5a7  cmp     byte ptr [rcx+19h], 2
0x18002b5ab  jb      short loc_18002B5C2
0x18002b5ad  mov     edx, 15h
0x18002b5b2  lea     r8, WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids
0x18002b5b9  mov     rcx, [rcx+10h]
0x18002b5bd  call    WPP_SF_
0x18002b5c2  mov     [rbp+57h+var_78], bl
0x18002b5c5  lea     rax, qword_1800A4718
0x18002b5cc  mov     [rbp+57h+var_70], rax
0x18002b5d0  mov     [rbp+57h+var_68], rbx
0x18002b5d4  mov     [rbp+57h+var_60], rbx
0x18002b5d8  mov     [rbp+57h+var_58], 0Eh
0x18002b5df  mov     [rbp+57h+var_54], 0FFFFFFFFFFFFFFFFh
0x18002b5e7  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18002b5ee  mov     [rbp+57h+pExceptionObject], rax
0x18002b5f2  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x18002b5f9  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18002b5fd  call    _CxxThrowException_0
0x18002b603  mov     ecx, 8007000Eh; unsigned int
0x18002b608  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x18002b60e  mov     rcx, rbx; bstrString
0x18002b611  call    cs:__imp_SysFreeString
0x18002b617  mov     r8d, [rbp+57h+var_B0]; enum _SID_NAME_USE
0x18002b61b  cmp     r8d, 3
0x18002b61f  jz      short loc_18002B63F
0x18002b621  test    r8d, r8d
0x18002b624  jle     short loc_18002B63F
0x18002b626  cmp     r8d, 6
0x18002b62a  jge     short loc_18002B63F
0x18002b62c  mov     rdx, [rbp+57h+Sid]; void *
0x18002b630  mov     rcx, r12; this
0x18002b633  call    ?FromSid@User@@SAJAEAV1@PEAXW4_SID_NAME_USE@@@Z; User::FromSid(User &,void *,_SID_NAME_USE)
0x18002b638  mov     edi, eax
0x18002b63a  jmp     loc_18002B306
0x18002b63f  lea     rax, WPP_GLOBAL_Control
0x18002b646  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b64d  cmp     rcx, rax
0x18002b650  jz      short loc_18002B673
0x18002b652  test    byte ptr [rcx+1Ch], 80h
0x18002b656  jz      short loc_18002B673
0x18002b658  cmp     byte ptr [rcx+19h], 2
0x18002b65c  jb      short loc_18002B673
0x18002b65e  mov     edx, 16h
0x18002b663  lea     r8, WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids
0x18002b66a  mov     rcx, [rcx+10h]
0x18002b66e  call    WPP_SF_
0x18002b673  mov     edi, 80070057h
0x18002b678  jmp     loc_18002B306
```
