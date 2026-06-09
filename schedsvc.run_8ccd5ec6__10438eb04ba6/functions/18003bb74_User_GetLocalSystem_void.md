# User::GetLocalSystem(void)

- ea: `0x18003bb74`
- end: `0x18003bd6a`
- name: `?GetLocalSystem@User@@SA?AV1@XZ`
- size: `502`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18004f2b0`
- `0x1800502c4`

## callees

- `0x1800044b0`
- `0x18000fe50`
- `0x180011e40`
- `0x180027910`
- `0x18003bb74`
- `0x18003bd70`
- `0x18003be50`
- `0x18003c1f8`
- `0x180050908`
- `0x180050914`
- `0x18005a2bc`
- `0x18005dcd4`
- `0x180082a40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003bbe1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003bbe1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003bbb1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003bbb1`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18003bc2b`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18003bc2b`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
User::UserEntry **__fastcall User::GetLocalSystem(User::UserEntry **a1)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbx
  User::UserEntry *v3; // rcx
  void *v5; // rdi
  __int64 User; // r14
  void *v7; // rax
  __int64 v8; // rax
  __int64 v9; // rdi
  DWORD cbSid; // [rsp+30h] [rbp-89h] BYREF
  _BYTE v11[8]; // [rsp+38h] [rbp-81h] BYREF
  _BYTE v12[8]; // [rsp+40h] [rbp-79h] BYREF
  _QWORD v13[2]; // [rsp+48h] [rbp-71h] BYREF
  void **pExceptionObject; // [rsp+58h] [rbp-61h] BYREF
  char v15; // [rsp+60h] [rbp-59h]
  const unsigned __int16 *v16; // [rsp+68h] [rbp-51h]
  __int64 v17; // [rsp+70h] [rbp-49h]
  __int64 v18; // [rsp+78h] [rbp-41h]
  int v19; // [rsp+80h] [rbp-39h]
  __int64 v20; // [rsp+84h] [rbp-35h]
  LPCRITICAL_SECTION v21; // [rsp+90h] [rbp-29h]
  void *v22; // [rsp+98h] [rbp-21h]
  _BYTE pSid[80]; // [rsp+A0h] [rbp-19h] BYREF

  v13[0] = a1;
  v2 = User::s_cs;
  v21 = User::s_cs;
  EnterCriticalSection(User::s_cs);
  if ( *(_QWORD *)User::s_userCache )
  {
    v3 = **(User::UserEntry ***)User::s_userCache;
    *a1 = v3;
    if ( v3 )
      User::UserEntry::AddRef(v3);
  }
  else
  {
    cbSid = 68;
    CreateWellKnownSid(WinLocalSystemSid, 0, pSid, &cbSid);
    v5 = User::s_userCache;
    _bstr_t::_bstr_t((_bstr_t *)v12, L"NT AUTHORITY");
    _bstr_t::_bstr_t((_bstr_t *)v11, L"System");
    User = User::CreateUser(
             (__int64)v13,
             (const struct _bstr_t *)v11,
             (const struct _bstr_t *)v12,
             SidTypeWellKnownGroup,
             (_bstr_t *)pSid);
    v7 = operator new(8u);
    v22 = v7;
    if ( !v7 || (v8 = User::User(v7, User)) == 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids);
      }
      v15 = 0;
      v16 = &qword_1800A8718;
      v17 = 0;
      v18 = 0;
      v19 = 14;
      v20 = -1;
      pExceptionObject = &wmi::GenericException::`vftable';
      throw (wmi::OutOfMemoryException *)&pExceptionObject;
    }
    std::unique_ptr<User>::reset(v5, v8);
    v9 = std::unique_ptr<User>::get(v5);
    wmi::AutoRef<User::UserEntry>::Release(v13);
    _bstr_t::~_bstr_t((_bstr_t *)v11);
    _bstr_t::~_bstr_t((_bstr_t *)v12);
    User::User(a1, v9);
  }
  LeaveCriticalSection(v2);
  return a1;
}

```

## disassembly

```asm
0x18003bb74  mov     [rsp-8+arg_8], rbx
0x18003bb79  mov     [rsp-8+arg_10], rsi
0x18003bb7e  push    rbp
0x18003bb7f  push    rdi
0x18003bb80  push    r14
0x18003bb82  lea     rbp, [rsp-47h]
0x18003bb87  sub     rsp, 100h
0x18003bb8e  mov     rax, cs:__security_cookie
0x18003bb95  xor     rax, rsp
0x18003bb98  mov     [rbp+57h+var_20], rax
0x18003bb9c  mov     rsi, rcx
0x18003bb9f  mov     [rbp+57h+var_C8], rcx
0x18003bba3  mov     rbx, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x18003bbaa  mov     [rbp+57h+var_80], rbx
0x18003bbae  mov     rcx, rbx; lpCriticalSection
0x18003bbb1  call    cs:__imp_EnterCriticalSection
0x18003bbb8  nop     dword ptr [rax+rax+00h]
0x18003bbbd  nop
0x18003bbbe  mov     rax, cs:?s_userCache@User@@0PEAVUserCache@1@EA; User::UserCache * User::s_userCache
0x18003bbc5  mov     rcx, [rax]
0x18003bbc8  test    rcx, rcx
0x18003bbcb  jz      short loc_18003BC15
0x18003bbcd  mov     rcx, [rcx]; this
0x18003bbd0  mov     [rsi], rcx
0x18003bbd3  test    rcx, rcx
0x18003bbd6  jz      short loc_18003BBDE
0x18003bbd8  call    ?AddRef@UserEntry@User@@QEAAKXZ; User::UserEntry::AddRef(void)
0x18003bbdd  nop
0x18003bbde  mov     rcx, rbx; lpCriticalSection
0x18003bbe1  call    cs:__imp_LeaveCriticalSection
0x18003bbe8  nop     dword ptr [rax+rax+00h]
0x18003bbed  mov     rax, rsi
0x18003bbf0  mov     rcx, [rbp+57h+var_20]
0x18003bbf4  xor     rcx, rsp; StackCookie
0x18003bbf7  call    __security_check_cookie
0x18003bbfc  lea     r11, [rsp+110h+var_10]
0x18003bc04  mov     rbx, [r11+28h]
0x18003bc08  mov     rsi, [r11+30h]
0x18003bc0c  mov     rsp, r11
0x18003bc0f  pop     r14
0x18003bc11  pop     rdi
0x18003bc12  pop     rbp
0x18003bc13  retn
0x18003bc15  mov     [rsp+110h+cbSid], 44h ; 'D'
0x18003bc1d  lea     r9, [rsp+110h+cbSid]; cbSid
0x18003bc22  lea     r8, [rbp+57h+pSid]; pSid
0x18003bc26  xor     edx, edx; DomainSid
0x18003bc28  lea     ecx, [rdx+16h]; WellKnownSidType
0x18003bc2b  call    cs:__imp_CreateWellKnownSid
0x18003bc32  nop     dword ptr [rax+rax+00h]
0x18003bc37  mov     rdi, cs:?s_userCache@User@@0PEAVUserCache@1@EA; User::UserCache * User::s_userCache
0x18003bc3e  lea     rdx, aNtAuthority; "NT AUTHORITY"
0x18003bc45  lea     rcx, [rbp+57h+var_D0]; this
0x18003bc49  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18003bc4e  nop
0x18003bc4f  lea     rdx, aSystem_0; "System"
0x18003bc56  lea     rcx, [rsp+110h+var_D8]; this
0x18003bc5b  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18003bc60  nop
0x18003bc61  lea     rax, [rbp+57h+pSid]
0x18003bc65  mov     [rsp+110h+var_F0], rax
0x18003bc6a  mov     r9d, 5
0x18003bc70  lea     r8, [rbp+57h+var_D0]
0x18003bc74  lea     rdx, [rsp+110h+var_D8]
0x18003bc79  lea     rcx, [rbp+57h+var_C8]
0x18003bc7d  call    ?CreateUser@User@@SA?AV1@AEBV_bstr_t@@0W4_SID_NAME_USE@@PEAX@Z; User::CreateUser(_bstr_t const &,_bstr_t const &,_SID_NAME_USE,void *)
0x18003bc82  mov     r14, rax
0x18003bc85  mov     ecx, 8; dwBytes
0x18003bc8a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003bc8f  mov     [rbp+57h+var_78], rax
0x18003bc93  test    rax, rax
0x18003bc96  jz      short loc_18003BCEC
0x18003bc98  mov     rdx, r14
0x18003bc9b  mov     rcx, rax
0x18003bc9e  call    ??0User@@AEAA@AEBV?$AutoRef@UUserEntry@User@@@wmi@@@Z; User::User(wmi::AutoRef<User::UserEntry> const &)
0x18003bca3  test    rax, rax
0x18003bca6  jz      short loc_18003BCEC
0x18003bca8  mov     rdx, rax
0x18003bcab  mov     rcx, rdi
0x18003bcae  call    ?reset@?$unique_ptr@VUser@@U?$default_delete@VUser@@@std@@@std@@QEAAXPEAVUser@@@Z; std::unique_ptr<User>::reset(User *)
0x18003bcb3  mov     rcx, rdi
0x18003bcb6  call    ?get@?$unique_ptr@VUser@@U?$default_delete@VUser@@@std@@@std@@QEBAPEAVUser@@XZ; std::unique_ptr<User>::get(void)
0x18003bcbb  mov     rdi, rax
0x18003bcbe  lea     rcx, [rbp+57h+var_C8]
0x18003bcc2  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x18003bcc7  nop
0x18003bcc8  lea     rcx, [rsp+110h+var_D8]; this
0x18003bccd  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18003bcd2  nop
0x18003bcd3  lea     rcx, [rbp+57h+var_D0]; this
0x18003bcd7  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18003bcdc  mov     rdx, rdi
0x18003bcdf  mov     rcx, rsi
0x18003bce2  call    ??0User@@AEAA@AEBV?$AutoRef@UUserEntry@User@@@wmi@@@Z; User::User(wmi::AutoRef<User::UserEntry> const &)
0x18003bce7  jmp     loc_18003BBDE
0x18003bcec  lea     rax, WPP_GLOBAL_Control
0x18003bcf3  mov     rcx, cs:WPP_GLOBAL_Control
0x18003bcfa  cmp     rcx, rax
0x18003bcfd  jz      short loc_18003BD20
0x18003bcff  test    byte ptr [rcx+1Ch], 80h
0x18003bd03  jz      short loc_18003BD20
0x18003bd05  cmp     byte ptr [rcx+19h], 2
0x18003bd09  jb      short loc_18003BD20
0x18003bd0b  mov     edx, 0Ah
0x18003bd10  lea     r8, WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids
0x18003bd17  mov     rcx, [rcx+10h]
0x18003bd1b  call    WPP_SF_
0x18003bd20  mov     [rbp+57h+var_B0], 0
0x18003bd24  lea     rax, qword_1800A8718
0x18003bd2b  mov     [rbp+57h+var_A8], rax
0x18003bd2f  mov     [rbp+57h+var_A0], 0
0x18003bd37  mov     [rbp+57h+var_98], 0
0x18003bd3f  mov     [rbp+57h+var_90], 0Eh
0x18003bd46  mov     [rbp+57h+var_8C], 0FFFFFFFFFFFFFFFFh
0x18003bd4e  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18003bd55  mov     [rbp+57h+pExceptionObject], rax
0x18003bd59  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x18003bd60  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18003bd64  call    _CxxThrowException_0
```
