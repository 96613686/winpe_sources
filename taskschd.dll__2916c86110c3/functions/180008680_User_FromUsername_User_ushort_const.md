# User::FromUsername(User &,ushort const *)

- ea: `0x180008680`
- end: `0x180008c61`
- name: `?FromUsername@User@@SAJAEAV1@PEBG@Z`
- size: `1505`
- prototype: `__int64 __fastcall(struct User *this, LPCWSTR lpAccountName)`
- caller_count: `3`
- callee_count: `15`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180037fbc`
- `0x18004c280`
- `0x18004ca50`

## callees

- `0x180007aa0`
- `0x180007da0`
- `0x180008680`
- `0x180008c70`
- `0x180008d30`
- `0x180008da8`
- `0x180008e0c`
- `0x180008e40`
- `0x180009958`
- `0x180009a94`
- `0x180009b1c`
- `0x180039524`
- `0x18003b51c`
- `0x18004e590`
- `0x18004e5c0`

## import_xrefs

- `msvcrt!malloc` at `0x180008785`
- `msvcrt!malloc` at `0x180008785`
- `msvcrt!free` at `0x1800087ea`
- `msvcrt!free` at `0x1800087ea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000874c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008861`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008880`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800088fe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000874c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008861`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008880`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800088fe`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800086e8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800086fd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008821`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800086e8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800086fd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008821`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008980`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008a39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008a57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008b2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008980`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008a39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008a57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008b2e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000890c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000890c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008996`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008996`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000872f`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000872f`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180008805`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180008805`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800087cf`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800087cf`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180008a21`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180008a21`
- `OLEAUT32!__imp_SysFreeString` at `0x1800089e5`
- `OLEAUT32!__imp_SysFreeString` at `0x180008a6f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800089e5`
- `OLEAUT32!__imp_SysFreeString` at `0x180008a6f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800086bf`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800086bf`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x18000897a`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x1800089d8`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x18000897a`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x1800089d8`

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
      v34 = &qword_180077320;
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
      v34 = &qword_180077320;
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
      v34 = &qword_180077320;
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
      v34 = &qword_180077320;
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
0x180008680  mov     [rsp-8+arg_0], rbx
0x180008685  push    rbp
0x180008686  push    rsi
0x180008687  push    rdi
0x180008688  push    r12
0x18000868a  push    r13
0x18000868c  push    r14
0x18000868e  push    r15
0x180008690  lea     rbp, [rsp-27h]
0x180008695  sub     rsp, 0D0h
0x18000869c  mov     rdi, rdx
0x18000869f  mov     r15, rcx
0x1800086a2  xor     ebx, ebx
0x1800086a4  mov     dword ptr [rbp+57h+var_B8], ebx
0x1800086a7  mov     [rbp+57h+ui], ebx
0x1800086aa  mov     [rbp+57h+cbSid], ebx
0x1800086ad  mov     [rbp+57h+Sid], rbx
0x1800086b1  mov     [rbp+57h+var_C0], 8
0x1800086b8  lea     rdx, [rbp+57h+Sid]; Sid
0x1800086bc  mov     rcx, rdi; StringSid
0x1800086bf  call    cs:__imp_ConvertStringSidToSidW
0x1800086c5  test    eax, eax
0x1800086c7  jz      loc_18000895C
0x1800086cd  mov     r12, [rbp+57h+Sid]
0x1800086d1  test    r12, r12
0x1800086d4  jz      loc_180008C57
0x1800086da  mov     rsi, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x1800086e1  mov     [rbp+57h+var_58], rsi
0x1800086e5  mov     rcx, rsi; lpCriticalSection
0x1800086e8  call    cs:__imp_EnterCriticalSection
0x1800086ee  nop
0x1800086ef  mov     [rbp+57h+var_B8], rbx
0x1800086f3  mov     rdi, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x1800086fa  mov     rcx, rdi; lpCriticalSection
0x1800086fd  call    cs:__imp_EnterCriticalSection
0x180008703  mov     r13, cs:?s_userTable@User@@0PEAV?$vector@PEAUUserEntry@User@@V?$allocator@PEAUUserEntry@User@@@std@@@std@@EA; std::vector<User::UserEntry *> * User::s_userTable
0x18000870a  mov     r14, [r13+0]
0x18000870e  cmp     r14, [r13+8]
0x180008712  jz      short loc_180008749
0x180008714  cmp     r14, [r13+8]
0x180008718  jz      short loc_180008749
0x18000871a  mov     rax, [r14]
0x18000871d  mov     rcx, [rax+20h]; pSid1
0x180008721  test    rcx, rcx
0x180008724  jnz     short loc_18000872C
0x180008726  add     r14, 8
0x18000872a  jmp     short loc_180008714
0x18000872c  mov     rdx, r12; pSid2
0x18000872f  call    cs:__imp_EqualSid
0x180008735  test    eax, eax
0x180008737  jz      short loc_180008726
0x180008739  mov     rdx, [r14]
0x18000873c  lea     rcx, [rbp+57h+var_B8]
0x180008740  call    ??4?$AutoRef@UUserEntry@User@@@wmi@@QEAAAEAV01@PEAUUserEntry@User@@@Z; wmi::AutoRef<User::UserEntry>::operator=(User::UserEntry *)
0x180008745  mov     rbx, [rbp+57h+var_B8]
0x180008749  mov     rcx, rdi; lpCriticalSection
0x18000874c  call    cs:__imp_LeaveCriticalSection
0x180008752  test    rbx, rbx
0x180008755  jz      loc_18000894C
0x18000875b  mov     rcx, rbx; this
0x18000875e  call    ?AddRef@UserEntry@User@@QEAAKXZ; User::UserEntry::AddRef(void)
0x180008763  mov     rcx, r15; this
0x180008766  call    ??1User@@QEAA@XZ; User::~User(void)
0x18000876b  mov     [r15], rbx
0x18000876e  mov     rcx, rbx; this
0x180008771  call    ?Release@UserEntry@User@@QEAAKXZ; User::UserEntry::Release(void)
0x180008776  cmp     qword ptr [r15], 0
0x18000877a  jnz     loc_1800088AC
0x180008780  mov     ecx, 30h ; '0'; Size
0x180008785  call    cs:__imp_malloc
0x18000878b  mov     r14, rax
0x18000878e  test    rax, rax
0x180008791  jz      loc_180008A7A
0x180008797  mov     [rbp+57h+var_60], rax
0x18000879b  xor     r13d, r13d
0x18000879e  mov     [rbp+57h+var_68], r13
0x1800087a2  mov     [rbp+57h+var_50], r13
0x1800087a6  mov     [rbp+57h+var_48], r13
0x1800087aa  mov     dword ptr [rbp+57h+var_B8], 7
0x1800087b1  mov     [rax], r13b
0x1800087b4  mov     [rax+8], r13
0x1800087b8  mov     [rax+10h], r13
0x1800087bc  mov     [rax+18h], r13
0x1800087c0  mov     [rax+20h], r13
0x1800087c4  mov     qword ptr [rax+28h], 8
0x1800087cc  mov     rcx, r12; pSid
0x1800087cf  call    cs:__imp_GetLengthSid
0x1800087d5  mov     edi, eax
0x1800087d7  mov     ecx, eax; unsigned __int64
0x1800087d9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800087de  mov     rbx, rax
0x1800087e1  mov     rcx, [r14+20h]; Block
0x1800087e5  test    rcx, rcx
0x1800087e8  jz      short loc_1800087F0
0x1800087ea  call    cs:__imp_free
0x1800087f0  mov     [r14+20h], rbx
0x1800087f4  test    rbx, rbx
0x1800087f7  jz      loc_180008ABF
0x1800087fd  mov     r8, r12; pSourceSid
0x180008800  mov     rdx, rbx; pDestinationSid
0x180008803  mov     ecx, edi; nDestinationSidLength
0x180008805  call    cs:__imp_CopySid
0x18000880b  test    eax, eax
0x18000880d  jz      loc_180008B2E
0x180008813  mov     rbx, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x18000881a  mov     [rbp+57h+var_40], rbx
0x18000881e  mov     rcx, rbx; lpCriticalSection
0x180008821  call    cs:__imp_EnterCriticalSection
0x180008827  nop
0x180008828  mov     rdi, cs:?s_userTable@User@@0PEAV?$vector@PEAUUserEntry@User@@V?$allocator@PEAUUserEntry@User@@@std@@@std@@EA; std::vector<User::UserEntry *> * User::s_userTable
0x18000882f  mov     [rbp+57h+var_70], r14
0x180008833  mov     rax, [rdi+8]
0x180008837  lea     rcx, [rbp+57h+var_70]
0x18000883b  cmp     rcx, rax
0x18000883e  jb      loc_180008917
0x180008844  cmp     rax, [rdi+10h]
0x180008848  jnz     short loc_180008852
0x18000884a  mov     rcx, rdi
0x18000884d  call    ?_Reserve@?$vector@PEAUUserEntry@User@@V?$allocator@PEAUUserEntry@User@@@std@@@std@@IEAAX_K@Z; std::vector<User::UserEntry *>::_Reserve(unsigned __int64)
0x180008852  mov     rax, [rdi+8]
0x180008856  mov     [rax], r14
0x180008859  add     qword ptr [rdi+8], 8
0x18000885e  mov     rcx, rbx; lpCriticalSection
0x180008861  call    cs:__imp_LeaveCriticalSection
0x180008867  nop
0x180008868  mov     rdx, r14
0x18000886b  mov     rcx, r15
0x18000886e  call    ??4?$AutoRef@UUserEntry@User@@@wmi@@QEAAAEAV01@PEAUUserEntry@User@@@Z; wmi::AutoRef<User::UserEntry>::operator=(User::UserEntry *)
0x180008873  mov     rcx, r15; this
0x180008876  call    ?UpdateEntry@User@@AEBAJXZ; User::UpdateEntry(void)
0x18000887b  mov     edi, eax
0x18000887d  mov     rcx, rsi; lpCriticalSection
0x180008880  call    cs:__imp_LeaveCriticalSection
0x180008886  mov     rcx, [rbp+57h+Sid]; hMem
0x18000888a  test    rcx, rcx
0x18000888d  jnz     short loc_18000890C
0x18000888f  mov     eax, edi
0x180008891  mov     rbx, [rsp+100h+arg_0]
0x180008899  add     rsp, 0D0h
0x1800088a0  pop     r15
0x1800088a2  pop     r14
0x1800088a4  pop     r13
0x1800088a6  pop     r12
0x1800088a8  pop     rdi
0x1800088a9  pop     rsi
0x1800088aa  pop     rbp
0x1800088ab  retn
0x1800088ac  xor     r13d, r13d
0x1800088af  mov     [rbp+57h+var_60], r13
0x1800088b3  mov     [rbp+57h+var_68], r13
0x1800088b7  mov     [rbp+57h+var_B8], r13
0x1800088bb  mov     [rsp+100h+peUse], r13; void *
0x1800088c0  mov     dword ptr [rsp+100h+cchReferencedDomainName], 8; enum _SID_NAME_USE
0x1800088c8  lea     r9, [rbp+57h+var_60]; struct _bstr_t *
0x1800088cc  lea     r8, [rbp+57h+var_68]; struct _bstr_t *
0x1800088d0  lea     rdx, [rbp+57h+var_B8]; struct _bstr_t *
0x1800088d4  mov     rcx, r15; this
0x1800088d7  call    ?UpdateEntry@User@@AEBAXAEBV_bstr_t@@00W4_SID_NAME_USE@@PEAX_N@Z; User::UpdateEntry(_bstr_t const &,_bstr_t const &,_bstr_t const &,_SID_NAME_USE,void *,bool)
0x1800088dc  nop
0x1800088dd  lea     rcx, [rbp+57h+var_B8]; this
0x1800088e1  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x1800088e6  nop
0x1800088e7  lea     rcx, [rbp+57h+var_68]; this
0x1800088eb  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x1800088f0  nop
0x1800088f1  lea     rcx, [rbp+57h+var_60]; this
0x1800088f5  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x1800088fa  nop
0x1800088fb  mov     rcx, rsi; lpCriticalSection
0x1800088fe  call    cs:__imp_LeaveCriticalSection
0x180008904  mov     edi, r13d
0x180008907  jmp     loc_180008886
0x18000890c  call    cs:__imp_LocalFree
0x180008912  jmp     loc_18000888F
0x180008917  lea     rcx, [rbp+57h+var_70]
0x18000891b  cmp     [rdi], rcx
0x18000891e  ja      loc_180008844
0x180008924  lea     r12, [rbp+57h+var_70]
0x180008928  sub     r12, [rdi]
0x18000892b  sar     r12, 3
0x18000892f  cmp     rax, [rdi+10h]
0x180008933  jz      loc_180008BA4
0x180008939  mov     rax, [rdi]
0x18000893c  mov     rcx, [rdi+8]
0x180008940  mov     rax, [rax+r12*8]
0x180008944  mov     [rcx], rax
0x180008947  jmp     loc_180008859
0x18000894c  mov     rcx, r15; this
0x18000894f  call    ??1User@@QEAA@XZ; User::~User(void)
0x180008954  mov     [r15], rbx
0x180008957  jmp     loc_180008776
0x18000895c  lea     rax, [rbp+57h+var_C0]
0x180008960  mov     [rsp+100h+peUse], rax; peUse
0x180008965  lea     rax, [rbp+57h+ui]
0x180008969  mov     [rsp+100h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18000896e  xor     r9d, r9d; ReferencedDomainName
0x180008971  lea     r8, [rbp+57h+cbSid]; cbSid
0x180008975  xor     edx, edx; Sid
0x180008977  mov     rcx, rdi; lpAccountName
0x18000897a  call    cs:__imp_LookupAccountNameLocalW
0x180008980  call    cs:__imp_GetLastError
0x180008986  cmp     eax, 7Ah ; 'z'
0x180008989  jnz     loc_180008A39
0x18000898f  mov     edx, [rbp+57h+cbSid]
0x180008992  inc     edx; uBytes
0x180008994  xor     ecx, ecx; uFlags
0x180008996  call    cs:__imp_LocalAlloc
0x18000899c  mov     rcx, rax
0x18000899f  mov     [rbp+57h+Sid], rax
0x1800089a3  test    rax, rax
0x1800089a6  jz      loc_180008BB1
0x1800089ac  mov     edx, [rbp+57h+ui]; ui
0x1800089af  lea     eax, [rdx+1]
0x1800089b2  mov     [rbp+57h+ui], eax
0x1800089b5  test    edx, edx
0x1800089b7  jnz     short loc_180008A1F
0x1800089b9  lea     rax, [rbp+57h+var_C0]
0x1800089bd  mov     [rsp+100h+peUse], rax; peUse
0x1800089c2  lea     rax, [rbp+57h+ui]
0x1800089c6  mov     [rsp+100h+cchReferencedDomainName], rax; cchReferencedDomainName
0x1800089cb  mov     r9, rbx; ReferencedDomainName
0x1800089ce  lea     r8, [rbp+57h+cbSid]; cbSid
0x1800089d2  mov     rdx, rcx; Sid
0x1800089d5  mov     rcx, rdi; lpAccountName
0x1800089d8  call    cs:__imp_LookupAccountNameLocalW
0x1800089de  test    eax, eax
0x1800089e0  jz      short loc_180008A57
0x1800089e2  mov     rcx, rbx; bstrString
0x1800089e5  call    cs:__imp_SysFreeString
0x1800089eb  mov     r8d, [rbp+57h+var_C0]; enum _SID_NAME_USE
0x1800089ef  cmp     r8d, 3
0x1800089f3  jz      loc_180008C2A
0x1800089f9  test    r8d, r8d
0x1800089fc  jle     loc_180008C2A
0x180008a02  cmp     r8d, 6
0x180008a06  jge     loc_180008C2A
0x180008a0c  mov     rdx, [rbp+57h+Sid]; pSourceSid
0x180008a10  mov     rcx, r15; this
0x180008a13  call    ?FromSid@User@@SAJAEAV1@PEAXW4_SID_NAME_USE@@@Z; User::FromSid(User &,void *,_SID_NAME_USE)
0x180008a18  mov     edi, eax
0x180008a1a  jmp     loc_180008886
0x180008a1f  xor     ecx, ecx; strIn
0x180008a21  call    cs:__imp_SysAllocStringLen
0x180008a27  mov     rbx, rax
0x180008a2a  test    rax, rax
0x180008a2d  jz      loc_180008C1F
0x180008a33  mov     rcx, [rbp+57h+Sid]
0x180008a37  jmp     short loc_1800089B9
0x180008a39  call    cs:__imp_GetLastError
0x180008a3f  mov     edi, eax
0x180008a41  test    eax, eax
0x180008a43  jle     loc_180008886
0x180008a49  movzx   edi, ax
0x180008a4c  or      edi, 80070000h
0x180008a52  jmp     loc_180008886
0x180008a57  call    cs:__imp_GetLastError
0x180008a5d  mov     edi, eax
0x180008a5f  test    eax, eax
0x180008a61  jle     short loc_180008A6C
0x180008a63  movzx   edi, ax
0x180008a66  or      edi, 80070000h
0x180008a6c  mov     rcx, rbx; bstrString
0x180008a6f  call    cs:__imp_SysFreeString
0x180008a75  jmp     loc_180008886
0x180008a7a  mov     [rbp+57h+var_A0], 0
0x180008a7e  lea     rax, qword_180077320
0x180008a85  mov     [rbp+57h+var_98], rax
0x180008a89  xor     r13d, r13d
0x180008a8c  mov     [rbp+57h+var_90], r13
0x180008a90  mov     [rbp+57h+var_88], r13
0x180008a94  mov     [rbp+57h+var_80], 0Eh
0x180008a9b  mov     [rbp+57h+var_7C], 0FFFFFFFFFFFFFFFFh
0x180008aa3  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180008aaa  mov     [rbp+57h+pExceptionObject], rax
0x180008aae  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x180008ab5  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180008ab9  call    _CxxThrowException_0
0x180008abf  lea     rax, WPP_GLOBAL_Control
0x180008ac6  mov     rcx, cs:WPP_GLOBAL_Control
0x180008acd  cmp     rcx, rax
0x180008ad0  jz      short loc_180008AEC
0x180008ad2  test    byte ptr [rcx+1Ch], 80h
0x180008ad6  jz      short loc_180008AEC
0x180008ad8  cmp     byte ptr [rcx+19h], 2
0x180008adc  jb      short loc_180008AEC
0x180008ade  mov     edx, 11h
0x180008ae3  mov     rcx, [rcx+10h]
0x180008ae7  call    WPP_SF_
0x180008aec  mov     [rbp+57h+var_A0], 0
0x180008af0  lea     rax, qword_180077320
0x180008af7  mov     [rbp+57h+var_98], rax
0x180008afb  mov     [rbp+57h+var_90], r13
0x180008aff  mov     [rbp+57h+var_88], r13
0x180008b03  mov     [rbp+57h+var_80], 0Eh
0x180008b0a  mov     [rbp+57h+var_7C], 0FFFFFFFFFFFFFFFFh
0x180008b12  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180008b19  mov     [rbp+57h+pExceptionObject], rax
0x180008b1d  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x180008b24  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180008b28  call    _CxxThrowException_0
  ... truncated ...
```
