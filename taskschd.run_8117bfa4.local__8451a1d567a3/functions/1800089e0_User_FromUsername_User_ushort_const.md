# User::FromUsername(User &,ushort const *)

- ea: `0x1800089e0`
- end: `0x18000905d`
- name: `?FromUsername@User@@SAJAEAV1@PEBG@Z`
- size: `1661`
- prototype: `__int64 __fastcall(struct User *this, LPCWSTR lpAccountName)`
- caller_count: `3`
- callee_count: `15`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18003b048`
- `0x18004fec0`
- `0x180050690`

## callees

- `0x180007e90`
- `0x180008240`
- `0x1800089e0`
- `0x180009070`
- `0x180009150`
- `0x1800091d8`
- `0x180009248`
- `0x180009280`
- `0x18000a020`
- `0x18000a148`
- `0x18000a1d0`
- `0x18003c664`
- `0x18003e88c`
- `0x18005224c`
- `0x180052284`

## import_xrefs

- `msvcrt!malloc` at `0x180008b03`
- `msvcrt!malloc` at `0x180008b03`
- `msvcrt!free` at `0x180008b74`
- `msvcrt!free` at `0x180008b74`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008ac4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008bfd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008c22`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008cab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008ac4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008bfd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008c22`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008cab`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008a4e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008a69`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008bb7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008a4e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008a69`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008bb7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008e1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008e41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008f24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008e1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008e41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008f24`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008cbf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008cbf`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008d5b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008d5b`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180008aa1`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180008aa1`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180008b95`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180008b95`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180008b53`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180008b53`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180008dfc`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180008dfc`
- `OLEAUT32!__imp_SysFreeString` at `0x180008dba`
- `OLEAUT32!__imp_SysFreeString` at `0x180008e5f`
- `OLEAUT32!__imp_SysFreeString` at `0x180008dba`
- `OLEAUT32!__imp_SysFreeString` at `0x180008e5f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180008a1f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180008a1f`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x180008d33`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x180008da3`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x180008d33`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x180008da3`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall User::FromUsername(struct User *this, LPCWSTR lpAccountName)
{
  OLECHAR *v4; // rbx
  PSID v5; // r12
  struct _RTL_CRITICAL_SECTION *v6; // rsi
  struct _RTL_CRITICAL_SECTION *v7; // rdi
  _QWORD **v8; // r13
  _QWORD *v9; // r14
  void *v10; // rcx
  _QWORD *v11; // rax
  _QWORD *v12; // r14
  unsigned __int64 LengthSid; // rdi
  void *v14; // rbx
  void *v15; // rcx
  struct _RTL_CRITICAL_SECTION *v16; // rbx
  _QWORD **v17; // rdi
  unsigned __int64 v18; // rax
  unsigned int updated; // edi
  __int64 v21; // r12
  HLOCAL v22; // rcx
  UINT v23; // edx
  signed int LastError; // eax
  signed int v25; // eax
  DWORD v26; // ebx
  __int64 v27; // r8
  bool v28; // [rsp+30h] [rbp-79h]
  enum _SID_NAME_USE peUse; // [rsp+40h] [rbp-69h] BYREF
  OLECHAR *v30; // [rsp+48h] [rbp-61h] BYREF
  PSID Sid; // [rsp+50h] [rbp-59h] BYREF
  void **pExceptionObject; // [rsp+58h] [rbp-51h] BYREF
  char v33; // [rsp+60h] [rbp-49h]
  __int64 *v34; // [rsp+68h] [rbp-41h]
  __int64 v35; // [rsp+70h] [rbp-39h]
  __int64 v36; // [rsp+78h] [rbp-31h]
  int v37; // [rsp+80h] [rbp-29h]
  __int64 v38; // [rsp+84h] [rbp-25h]
  _QWORD *v39; // [rsp+90h] [rbp-19h] BYREF
  __int64 v40; // [rsp+98h] [rbp-11h] BYREF
  _QWORD v41[12]; // [rsp+A0h] [rbp-9h] BYREF
  DWORD ui; // [rsp+120h] [rbp+77h] BYREF
  DWORD cbSid; // [rsp+128h] [rbp+7Fh] BYREF

  v4 = 0;
  LODWORD(v30) = 0;
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
      goto LABEL_22;
    }
    v22 = LocalAlloc(0, cbSid + 1);
    Sid = v22;
    if ( !v22 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21);
      }
      v33 = 0;
      v34 = &qword_18007B2F0;
      v35 = 0;
      v36 = 0;
      v37 = 14;
      v38 = -1;
      pExceptionObject = &wmi::GenericException::`vftable';
      throw (wmi::OutOfMemoryException *)&pExceptionObject;
    }
    v23 = ui++;
    if ( v23 )
    {
      v4 = SysAllocStringLen(0, v23);
      if ( !v4 )
        ATL::PrivateAtlThrow(-2147024882);
      v22 = Sid;
    }
    if ( !LookupAccountNameLocalW(lpAccountName, v22, &cbSid, v4, &ui, &peUse) )
    {
      v25 = GetLastError();
      updated = v25;
      if ( v25 > 0 )
        updated = (unsigned __int16)v25 | 0x80070000;
      SysFreeString(v4);
      goto LABEL_22;
    }
    SysFreeString(v4);
    if ( peUse != SidTypeDomain && peUse > 0 && peUse < SidTypeDeletedAccount )
    {
      updated = User::FromSid(this, Sid, peUse);
      goto LABEL_22;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22);
    }
LABEL_67:
    updated = -2147024809;
    goto LABEL_22;
  }
  v5 = Sid;
  if ( !Sid )
    goto LABEL_67;
  v6 = User::s_cs;
  v41[1] = User::s_cs;
  EnterCriticalSection(User::s_cs);
  v30 = 0;
  v7 = User::s_cs;
  EnterCriticalSection(User::s_cs);
  v8 = (_QWORD **)User::s_userTable;
  v9 = *(_QWORD **)User::s_userTable;
  if ( *(_QWORD *)User::s_userTable != *((_QWORD *)User::s_userTable + 1) )
  {
    while ( v9 != v8[1] )
    {
      v10 = *(void **)(*v9 + 32LL);
      if ( v10 && EqualSid(v10, v5) )
      {
        wmi::AutoRef<User::UserEntry>::operator=(&v30, *v9);
        v4 = v30;
        break;
      }
      ++v9;
    }
  }
  LeaveCriticalSection(v7);
  if ( v4 )
  {
    User::UserEntry::AddRef((User::UserEntry *)v4);
    User::~User(this);
    *(_QWORD *)this = v4;
    User::UserEntry::Release((User::UserEntry *)v4);
  }
  else
  {
    User::~User(this);
    *(_QWORD *)this = 0;
  }
  if ( *(_QWORD *)this )
  {
    v41[0] = 0;
    v40 = 0;
    v30 = 0;
    User::UpdateEntry(
      this,
      (const struct _bstr_t *)&v30,
      (const struct _bstr_t *)&v40,
      (const struct _bstr_t *)v41,
      SidTypeUnknown,
      0,
      v28);
    _bstr_t::_Free((_bstr_t *)&v30);
    _bstr_t::_Free((_bstr_t *)&v40);
    _bstr_t::_Free((_bstr_t *)v41);
    LeaveCriticalSection(v6);
    updated = 0;
  }
  else
  {
    v11 = malloc(0x30u);
    v12 = v11;
    if ( !v11 )
    {
      v33 = 0;
      v34 = &qword_18007B2F0;
      v35 = 0;
      v36 = 0;
      v37 = 14;
      v38 = -1;
      pExceptionObject = &wmi::GenericException::`vftable';
      throw (wmi::OutOfMemoryException *)&pExceptionObject;
    }
    v41[0] = v11;
    v40 = 0;
    v41[2] = 0;
    v41[3] = 0;
    LODWORD(v30) = 7;
    *(_BYTE *)v11 = 0;
    v11[1] = 0;
    v11[2] = 0;
    v11[3] = 0;
    v11[4] = 0;
    v11[5] = 8;
    LengthSid = GetLengthSid(v5);
    v14 = operator new(LengthSid);
    v15 = (void *)v12[4];
    if ( v15 )
      free(v15);
    v12[4] = v14;
    if ( !v14 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17);
      }
      v33 = 0;
      v34 = &qword_18007B2F0;
      v35 = 0;
      v36 = 0;
      v37 = 14;
      v38 = -1;
      pExceptionObject = &wmi::GenericException::`vftable';
      throw (wmi::OutOfMemoryException *)&pExceptionObject;
    }
    if ( !CopySid(LengthSid, v14, v5) )
    {
      v26 = GetLastError();
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, v27, v26);
      }
      v33 = 0;
      pExceptionObject = &wmi::GenericException::`vftable';
      v34 = &qword_18007B2F0;
      v35 = 0;
      v36 = 0;
      v37 = v26;
      v38 = -1;
      throw (wmi::GenericException *)&pExceptionObject;
    }
    v16 = User::s_cs;
    v41[4] = User::s_cs;
    EnterCriticalSection(User::s_cs);
    v17 = (_QWORD **)User::s_userTable;
    v39 = v12;
    v18 = *((_QWORD *)User::s_userTable + 1);
    if ( (unsigned __int64)&v39 >= v18 || *(_QWORD *)User::s_userTable > (unsigned __int64)&v39 )
    {
      if ( v18 == *((_QWORD *)User::s_userTable + 2) )
        std::vector<User::UserEntry *>::_Reserve(User::s_userTable);
      *v17[1] = v12;
    }
    else
    {
      v21 = ((__int64)&v39 - *(_QWORD *)User::s_userTable) >> 3;
      if ( v18 == *((_QWORD *)User::s_userTable + 2) )
        std::vector<User::UserEntry *>::_Reserve(User::s_userTable);
      *v17[1] = (*v17)[v21];
    }
    ++v17[1];
    LeaveCriticalSection(v16);
    wmi::AutoRef<User::UserEntry>::operator=(this, v12);
    updated = User::UpdateEntry(this);
    LeaveCriticalSection(v6);
  }
LABEL_22:
  if ( Sid )
    LocalFree(Sid);
  return updated;
}

```

## disassembly

```asm
0x1800089e0  mov     [rsp-8+arg_0], rbx
0x1800089e5  push    rbp
0x1800089e6  push    rsi
0x1800089e7  push    rdi
0x1800089e8  push    r12
0x1800089ea  push    r13
0x1800089ec  push    r14
0x1800089ee  push    r15
0x1800089f0  lea     rbp, [rsp-27h]
0x1800089f5  sub     rsp, 0D0h
0x1800089fc  mov     rdi, rdx
0x1800089ff  mov     r15, rcx
0x180008a02  xor     ebx, ebx
0x180008a04  mov     dword ptr [rbp+57h+var_B8], ebx
0x180008a07  mov     [rbp+57h+ui], ebx
0x180008a0a  mov     [rbp+57h+cbSid], ebx
0x180008a0d  mov     [rbp+57h+Sid], rbx
0x180008a11  mov     [rbp+57h+var_C0], 8
0x180008a18  lea     rdx, [rbp+57h+Sid]; Sid
0x180008a1c  mov     rcx, rdi; StringSid
0x180008a1f  call    cs:__imp_ConvertStringSidToSidW
0x180008a26  nop     dword ptr [rax+rax+00h]
0x180008a2b  test    eax, eax
0x180008a2d  jz      loc_180008D15
0x180008a33  mov     r12, [rbp+57h+Sid]
0x180008a37  test    r12, r12
0x180008a3a  jz      loc_180009053
0x180008a40  mov     rsi, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x180008a47  mov     [rbp+57h+var_58], rsi
0x180008a4b  mov     rcx, rsi; lpCriticalSection
0x180008a4e  call    cs:__imp_EnterCriticalSection
0x180008a55  nop     dword ptr [rax+rax+00h]
0x180008a5a  nop
0x180008a5b  mov     [rbp+57h+var_B8], rbx
0x180008a5f  mov     rdi, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x180008a66  mov     rcx, rdi; lpCriticalSection
0x180008a69  call    cs:__imp_EnterCriticalSection
0x180008a70  nop     dword ptr [rax+rax+00h]
0x180008a75  mov     r13, cs:?s_userTable@User@@0PEAV?$vector@PEAUUserEntry@User@@V?$allocator@PEAUUserEntry@User@@@std@@@std@@EA; std::vector<User::UserEntry *> * User::s_userTable
0x180008a7c  mov     r14, [r13+0]
0x180008a80  cmp     r14, [r13+8]
0x180008a84  jz      short loc_180008AC1
0x180008a86  cmp     r14, [r13+8]
0x180008a8a  jz      short loc_180008AC1
0x180008a8c  mov     rax, [r14]
0x180008a8f  mov     rcx, [rax+20h]; pSid1
0x180008a93  test    rcx, rcx
0x180008a96  jnz     short loc_180008A9E
0x180008a98  add     r14, 8
0x180008a9c  jmp     short loc_180008A86
0x180008a9e  mov     rdx, r12; pSid2
0x180008aa1  call    cs:__imp_EqualSid
0x180008aa8  nop     dword ptr [rax+rax+00h]
0x180008aad  test    eax, eax
0x180008aaf  jz      short loc_180008A98
0x180008ab1  mov     rdx, [r14]
0x180008ab4  lea     rcx, [rbp+57h+var_B8]
0x180008ab8  call    ??4?$AutoRef@UUserEntry@User@@@wmi@@QEAAAEAV01@PEAUUserEntry@User@@@Z; wmi::AutoRef<User::UserEntry>::operator=(User::UserEntry *)
0x180008abd  mov     rbx, [rbp+57h+var_B8]
0x180008ac1  mov     rcx, rdi; lpCriticalSection
0x180008ac4  call    cs:__imp_LeaveCriticalSection
0x180008acb  nop     dword ptr [rax+rax+00h]
0x180008ad0  test    rbx, rbx
0x180008ad3  jz      loc_180008D05
0x180008ad9  mov     rcx, rbx; this
0x180008adc  call    ?AddRef@UserEntry@User@@QEAAKXZ; User::UserEntry::AddRef(void)
0x180008ae1  mov     rcx, r15; this
0x180008ae4  call    ??1User@@QEAA@XZ; User::~User(void)
0x180008ae9  mov     [r15], rbx
0x180008aec  mov     rcx, rbx; this
0x180008aef  call    ?Release@UserEntry@User@@QEAAKXZ; User::UserEntry::Release(void)
0x180008af4  cmp     qword ptr [r15], 0
0x180008af8  jnz     loc_180008C59
0x180008afe  mov     ecx, 30h ; '0'; Size
0x180008b03  call    cs:__imp_malloc
0x180008b0a  nop     dword ptr [rax+rax+00h]
0x180008b0f  mov     r14, rax
0x180008b12  test    rax, rax
0x180008b15  jz      loc_180008E70
0x180008b1b  mov     [rbp+57h+var_60], rax
0x180008b1f  xor     r13d, r13d
0x180008b22  mov     [rbp+57h+var_68], r13
0x180008b26  mov     [rbp+57h+var_50], r13
0x180008b2a  mov     [rbp+57h+var_48], r13
0x180008b2e  mov     dword ptr [rbp+57h+var_B8], 7
0x180008b35  mov     [rax], r13b
0x180008b38  mov     [rax+8], r13
0x180008b3c  mov     [rax+10h], r13
0x180008b40  mov     [rax+18h], r13
0x180008b44  mov     [rax+20h], r13
0x180008b48  mov     qword ptr [rax+28h], 8
0x180008b50  mov     rcx, r12; pSid
0x180008b53  call    cs:__imp_GetLengthSid
0x180008b5a  nop     dword ptr [rax+rax+00h]
0x180008b5f  mov     edi, eax
0x180008b61  mov     ecx, eax; unsigned __int64
0x180008b63  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180008b68  mov     rbx, rax
0x180008b6b  mov     rcx, [r14+20h]; Block
0x180008b6f  test    rcx, rcx
0x180008b72  jz      short loc_180008B80
0x180008b74  call    cs:__imp_free
0x180008b7b  nop     dword ptr [rax+rax+00h]
0x180008b80  mov     [r14+20h], rbx
0x180008b84  test    rbx, rbx
0x180008b87  jz      loc_180008EB5
0x180008b8d  mov     r8, r12; pSourceSid
0x180008b90  mov     rdx, rbx; pDestinationSid
0x180008b93  mov     ecx, edi; nDestinationSidLength
0x180008b95  call    cs:__imp_CopySid
0x180008b9c  nop     dword ptr [rax+rax+00h]
0x180008ba1  test    eax, eax
0x180008ba3  jz      loc_180008F24
0x180008ba9  mov     rbx, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x180008bb0  mov     [rbp+57h+var_40], rbx
0x180008bb4  mov     rcx, rbx; lpCriticalSection
0x180008bb7  call    cs:__imp_EnterCriticalSection
0x180008bbe  nop     dword ptr [rax+rax+00h]
0x180008bc3  nop
0x180008bc4  mov     rdi, cs:?s_userTable@User@@0PEAV?$vector@PEAUUserEntry@User@@V?$allocator@PEAUUserEntry@User@@@std@@@std@@EA; std::vector<User::UserEntry *> * User::s_userTable
0x180008bcb  mov     [rbp+57h+var_70], r14
0x180008bcf  mov     rax, [rdi+8]
0x180008bd3  lea     rcx, [rbp+57h+var_70]
0x180008bd7  cmp     rcx, rax
0x180008bda  jb      loc_180008CD0
0x180008be0  cmp     rax, [rdi+10h]
0x180008be4  jnz     short loc_180008BEE
0x180008be6  mov     rcx, rdi
0x180008be9  call    ?_Reserve@?$vector@PEAUUserEntry@User@@V?$allocator@PEAUUserEntry@User@@@std@@@std@@IEAAX_K@Z; std::vector<User::UserEntry *>::_Reserve(unsigned __int64)
0x180008bee  mov     rax, [rdi+8]
0x180008bf2  mov     [rax], r14
0x180008bf5  add     qword ptr [rdi+8], 8
0x180008bfa  mov     rcx, rbx; lpCriticalSection
0x180008bfd  call    cs:__imp_LeaveCriticalSection
0x180008c04  nop     dword ptr [rax+rax+00h]
0x180008c09  nop
0x180008c0a  mov     rdx, r14
0x180008c0d  mov     rcx, r15
0x180008c10  call    ??4?$AutoRef@UUserEntry@User@@@wmi@@QEAAAEAV01@PEAUUserEntry@User@@@Z; wmi::AutoRef<User::UserEntry>::operator=(User::UserEntry *)
0x180008c15  mov     rcx, r15; this
0x180008c18  call    ?UpdateEntry@User@@AEBAJXZ; User::UpdateEntry(void)
0x180008c1d  mov     edi, eax
0x180008c1f  mov     rcx, rsi; lpCriticalSection
0x180008c22  call    cs:__imp_LeaveCriticalSection
0x180008c29  nop     dword ptr [rax+rax+00h]
0x180008c2e  mov     rcx, [rbp+57h+Sid]; hMem
0x180008c32  test    rcx, rcx
0x180008c35  jnz     loc_180008CBF
0x180008c3b  mov     eax, edi
0x180008c3d  mov     rbx, [rsp+100h+arg_0]
0x180008c45  add     rsp, 0D0h
0x180008c4c  pop     r15
0x180008c4e  pop     r14
0x180008c50  pop     r13
0x180008c52  pop     r12
0x180008c54  pop     rdi
0x180008c55  pop     rsi
0x180008c56  pop     rbp
0x180008c57  retn
0x180008c59  xor     r13d, r13d
0x180008c5c  mov     [rbp+57h+var_60], r13
0x180008c60  mov     [rbp+57h+var_68], r13
0x180008c64  mov     [rbp+57h+var_B8], r13
0x180008c68  mov     [rsp+100h+peUse], r13; void *
0x180008c6d  mov     dword ptr [rsp+100h+cchReferencedDomainName], 8; enum _SID_NAME_USE
0x180008c75  lea     r9, [rbp+57h+var_60]; struct _bstr_t *
0x180008c79  lea     r8, [rbp+57h+var_68]; struct _bstr_t *
0x180008c7d  lea     rdx, [rbp+57h+var_B8]; struct _bstr_t *
0x180008c81  mov     rcx, r15; this
0x180008c84  call    ?UpdateEntry@User@@AEBAXAEBV_bstr_t@@00W4_SID_NAME_USE@@PEAX_N@Z; User::UpdateEntry(_bstr_t const &,_bstr_t const &,_bstr_t const &,_SID_NAME_USE,void *,bool)
0x180008c89  nop
0x180008c8a  lea     rcx, [rbp+57h+var_B8]; this
0x180008c8e  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180008c93  nop
0x180008c94  lea     rcx, [rbp+57h+var_68]; this
0x180008c98  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180008c9d  nop
0x180008c9e  lea     rcx, [rbp+57h+var_60]; this
0x180008ca2  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180008ca7  nop
0x180008ca8  mov     rcx, rsi; lpCriticalSection
0x180008cab  call    cs:__imp_LeaveCriticalSection
0x180008cb2  nop     dword ptr [rax+rax+00h]
0x180008cb7  mov     edi, r13d
0x180008cba  jmp     loc_180008C2E
0x180008cbf  call    cs:__imp_LocalFree
0x180008cc6  nop     dword ptr [rax+rax+00h]
0x180008ccb  jmp     loc_180008C3B
0x180008cd0  lea     rcx, [rbp+57h+var_70]
0x180008cd4  cmp     [rdi], rcx
0x180008cd7  ja      loc_180008BE0
0x180008cdd  lea     r12, [rbp+57h+var_70]
0x180008ce1  sub     r12, [rdi]
0x180008ce4  sar     r12, 3
0x180008ce8  cmp     rax, [rdi+10h]
0x180008cec  jz      loc_180008FA0
0x180008cf2  mov     rax, [rdi]
0x180008cf5  mov     rcx, [rdi+8]
0x180008cf9  mov     rax, [rax+r12*8]
0x180008cfd  mov     [rcx], rax
0x180008d00  jmp     loc_180008BF5
0x180008d05  mov     rcx, r15; this
0x180008d08  call    ??1User@@QEAA@XZ; User::~User(void)
0x180008d0d  mov     [r15], rbx
0x180008d10  jmp     loc_180008AF4
0x180008d15  lea     rax, [rbp+57h+var_C0]
0x180008d19  mov     [rsp+100h+peUse], rax; peUse
0x180008d1e  lea     rax, [rbp+57h+ui]
0x180008d22  mov     [rsp+100h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180008d27  xor     r9d, r9d; ReferencedDomainName
0x180008d2a  lea     r8, [rbp+57h+cbSid]; cbSid
0x180008d2e  xor     edx, edx; Sid
0x180008d30  mov     rcx, rdi; lpAccountName
0x180008d33  call    cs:__imp_LookupAccountNameLocalW
0x180008d3a  nop     dword ptr [rax+rax+00h]
0x180008d3f  call    cs:__imp_GetLastError
0x180008d46  nop     dword ptr [rax+rax+00h]
0x180008d4b  cmp     eax, 7Ah ; 'z'
0x180008d4e  jnz     loc_180008E1D
0x180008d54  mov     edx, [rbp+57h+cbSid]
0x180008d57  inc     edx; uBytes
0x180008d59  xor     ecx, ecx; uFlags
0x180008d5b  call    cs:__imp_LocalAlloc
0x180008d62  nop     dword ptr [rax+rax+00h]
0x180008d67  mov     rcx, rax
0x180008d6a  mov     [rbp+57h+Sid], rax
0x180008d6e  test    rax, rax
0x180008d71  jz      loc_180008FAD
0x180008d77  mov     edx, [rbp+57h+ui]; ui
0x180008d7a  lea     eax, [rdx+1]
0x180008d7d  mov     [rbp+57h+ui], eax
0x180008d80  test    edx, edx
0x180008d82  jnz     short loc_180008DFA
0x180008d84  lea     rax, [rbp+57h+var_C0]
0x180008d88  mov     [rsp+100h+peUse], rax; peUse
0x180008d8d  lea     rax, [rbp+57h+ui]
0x180008d91  mov     [rsp+100h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180008d96  mov     r9, rbx; ReferencedDomainName
0x180008d99  lea     r8, [rbp+57h+cbSid]; cbSid
0x180008d9d  mov     rdx, rcx; Sid
0x180008da0  mov     rcx, rdi; lpAccountName
0x180008da3  call    cs:__imp_LookupAccountNameLocalW
0x180008daa  nop     dword ptr [rax+rax+00h]
0x180008daf  test    eax, eax
0x180008db1  jz      loc_180008E41
0x180008db7  mov     rcx, rbx; bstrString
0x180008dba  call    cs:__imp_SysFreeString
0x180008dc1  nop     dword ptr [rax+rax+00h]
0x180008dc6  mov     r8d, [rbp+57h+var_C0]; enum _SID_NAME_USE
0x180008dca  cmp     r8d, 3
0x180008dce  jz      loc_180009026
0x180008dd4  test    r8d, r8d
0x180008dd7  jle     loc_180009026
0x180008ddd  cmp     r8d, 6
0x180008de1  jge     loc_180009026
0x180008de7  mov     rdx, [rbp+57h+Sid]; pSourceSid
0x180008deb  mov     rcx, r15; this
0x180008dee  call    ?FromSid@User@@SAJAEAV1@PEAXW4_SID_NAME_USE@@@Z; User::FromSid(User &,void *,_SID_NAME_USE)
0x180008df3  mov     edi, eax
0x180008df5  jmp     loc_180008C2E
0x180008dfa  xor     ecx, ecx; strIn
0x180008dfc  call    cs:__imp_SysAllocStringLen
0x180008e03  nop     dword ptr [rax+rax+00h]
0x180008e08  mov     rbx, rax
0x180008e0b  test    rax, rax
0x180008e0e  jz      loc_18000901B
0x180008e14  mov     rcx, [rbp+57h+Sid]
0x180008e18  jmp     loc_180008D84
0x180008e1d  call    cs:__imp_GetLastError
0x180008e24  nop     dword ptr [rax+rax+00h]
0x180008e29  mov     edi, eax
0x180008e2b  test    eax, eax
0x180008e2d  jle     loc_180008C2E
0x180008e33  movzx   edi, ax
0x180008e36  or      edi, 80070000h
0x180008e3c  jmp     loc_180008C2E
0x180008e41  call    cs:__imp_GetLastError
0x180008e48  nop     dword ptr [rax+rax+00h]
0x180008e4d  mov     edi, eax
0x180008e4f  test    eax, eax
0x180008e51  jle     short loc_180008E5C
0x180008e53  movzx   edi, ax
0x180008e56  or      edi, 80070000h
0x180008e5c  mov     rcx, rbx; bstrString
0x180008e5f  call    cs:__imp_SysFreeString
0x180008e66  nop     dword ptr [rax+rax+00h]
0x180008e6b  jmp     loc_180008C2E
0x180008e70  mov     [rbp+57h+var_A0], 0
0x180008e74  lea     rax, qword_18007B2F0
0x180008e7b  mov     [rbp+57h+var_98], rax
0x180008e7f  xor     r13d, r13d
0x180008e82  mov     [rbp+57h+var_90], r13
0x180008e86  mov     [rbp+57h+var_88], r13
0x180008e8a  mov     [rbp+57h+var_80], 0Eh
0x180008e91  mov     [rbp+57h+var_7C], 0FFFFFFFFFFFFFFFFh
0x180008e99  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180008ea0  mov     [rbp+57h+pExceptionObject], rax
0x180008ea4  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x180008eab  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180008eaf  call    _CxxThrowException_0
  ... truncated ...
```
