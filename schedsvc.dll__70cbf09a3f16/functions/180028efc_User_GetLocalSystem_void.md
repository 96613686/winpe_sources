# User::GetLocalSystem(void)

- ea: `0x180028efc`
- end: `0x1800290df`
- name: `?GetLocalSystem@User@@SA?AV1@XZ`
- size: `483`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18004cfb0`
- `0x18004def0`

## callees

- `0x18000b4e0`
- `0x18000dc30`
- `0x180028efc`
- `0x1800290f0`
- `0x1800291c0`
- `0x180029508`
- `0x18002d390`
- `0x180030f80`
- `0x18004e4fc`
- `0x18004e508`
- `0x18005790c`
- `0x18005b124`
- `0x18007e6d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028f63`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028f63`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028f39`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028f39`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180028fa6`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180028fa6`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
User::UserEntry **__fastcall User::GetLocalSystem(User::UserEntry **a1)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbx
  User::UserEntry *v3; // rcx
  void *v5; // rdi
  __int64 User; // r14
  LPVOID v7; // rax
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
  LPVOID v22; // [rsp+98h] [rbp-21h]
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
      v16 = &qword_1800A4718;
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
0x180028efc  mov     [rsp-8+arg_8], rbx
0x180028f01  mov     [rsp-8+arg_10], rsi
0x180028f06  push    rbp
0x180028f07  push    rdi
0x180028f08  push    r14
0x180028f0a  lea     rbp, [rsp-47h]
0x180028f0f  sub     rsp, 100h
0x180028f16  mov     rax, cs:__security_cookie
0x180028f1d  xor     rax, rsp
0x180028f20  mov     [rbp+57h+var_20], rax
0x180028f24  mov     rsi, rcx
0x180028f27  mov     [rbp+57h+var_C8], rcx
0x180028f2b  mov     rbx, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x180028f32  mov     [rbp+57h+var_80], rbx
0x180028f36  mov     rcx, rbx; lpCriticalSection
0x180028f39  call    cs:__imp_EnterCriticalSection
0x180028f3f  nop
0x180028f40  mov     rax, cs:?s_userCache@User@@0PEAVUserCache@1@EA; User::UserCache * User::s_userCache
0x180028f47  mov     rcx, [rax]
0x180028f4a  test    rcx, rcx
0x180028f4d  jz      short loc_180028F90
0x180028f4f  mov     rcx, [rcx]; this
0x180028f52  mov     [rsi], rcx
0x180028f55  test    rcx, rcx
0x180028f58  jz      short loc_180028F60
0x180028f5a  call    ?AddRef@UserEntry@User@@QEAAKXZ; User::UserEntry::AddRef(void)
0x180028f5f  nop
0x180028f60  mov     rcx, rbx; lpCriticalSection
0x180028f63  call    cs:__imp_LeaveCriticalSection
0x180028f69  mov     rax, rsi
0x180028f6c  mov     rcx, [rbp+57h+var_20]
0x180028f70  xor     rcx, rsp; StackCookie
0x180028f73  call    __security_check_cookie
0x180028f78  lea     r11, [rsp+110h+var_10]
0x180028f80  mov     rbx, [r11+28h]
0x180028f84  mov     rsi, [r11+30h]
0x180028f88  mov     rsp, r11
0x180028f8b  pop     r14
0x180028f8d  pop     rdi
0x180028f8e  pop     rbp
0x180028f8f  retn
0x180028f90  mov     [rsp+110h+cbSid], 44h ; 'D'
0x180028f98  lea     r9, [rsp+110h+cbSid]; cbSid
0x180028f9d  lea     r8, [rbp+57h+pSid]; pSid
0x180028fa1  xor     edx, edx; DomainSid
0x180028fa3  lea     ecx, [rdx+16h]; WellKnownSidType
0x180028fa6  call    cs:__imp_CreateWellKnownSid
0x180028fac  mov     rdi, cs:?s_userCache@User@@0PEAVUserCache@1@EA; User::UserCache * User::s_userCache
0x180028fb3  lea     rdx, aNtAuthority; "NT AUTHORITY"
0x180028fba  lea     rcx, [rbp+57h+var_D0]; this
0x180028fbe  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180028fc3  nop
0x180028fc4  lea     rdx, aSystem_0; "System"
0x180028fcb  lea     rcx, [rsp+110h+var_D8]; this
0x180028fd0  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180028fd5  nop
0x180028fd6  lea     rax, [rbp+57h+pSid]
0x180028fda  mov     [rsp+110h+var_F0], rax
0x180028fdf  mov     r9d, 5
0x180028fe5  lea     r8, [rbp+57h+var_D0]
0x180028fe9  lea     rdx, [rsp+110h+var_D8]
0x180028fee  lea     rcx, [rbp+57h+var_C8]
0x180028ff2  call    ?CreateUser@User@@SA?AV1@AEBV_bstr_t@@0W4_SID_NAME_USE@@PEAX@Z; User::CreateUser(_bstr_t const &,_bstr_t const &,_SID_NAME_USE,void *)
0x180028ff7  mov     r14, rax
0x180028ffa  mov     ecx, 8; dwBytes
0x180028fff  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180029004  mov     [rbp+57h+var_78], rax
0x180029008  test    rax, rax
0x18002900b  jz      short loc_180029061
0x18002900d  mov     rdx, r14
0x180029010  mov     rcx, rax
0x180029013  call    ??0User@@AEAA@AEBV?$AutoRef@UUserEntry@User@@@wmi@@@Z; User::User(wmi::AutoRef<User::UserEntry> const &)
0x180029018  test    rax, rax
0x18002901b  jz      short loc_180029061
0x18002901d  mov     rdx, rax
0x180029020  mov     rcx, rdi
0x180029023  call    ?reset@?$unique_ptr@VUser@@U?$default_delete@VUser@@@std@@@std@@QEAAXPEAVUser@@@Z; std::unique_ptr<User>::reset(User *)
0x180029028  mov     rcx, rdi
0x18002902b  call    ?get@?$unique_ptr@VUser@@U?$default_delete@VUser@@@std@@@std@@QEBAPEAVUser@@XZ; std::unique_ptr<User>::get(void)
0x180029030  mov     rdi, rax
0x180029033  lea     rcx, [rbp+57h+var_C8]
0x180029037  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x18002903c  nop
0x18002903d  lea     rcx, [rsp+110h+var_D8]; this
0x180029042  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180029047  nop
0x180029048  lea     rcx, [rbp+57h+var_D0]; this
0x18002904c  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180029051  mov     rdx, rdi
0x180029054  mov     rcx, rsi
0x180029057  call    ??0User@@AEAA@AEBV?$AutoRef@UUserEntry@User@@@wmi@@@Z; User::User(wmi::AutoRef<User::UserEntry> const &)
0x18002905c  jmp     loc_180028F60
0x180029061  lea     rax, WPP_GLOBAL_Control
0x180029068  mov     rcx, cs:WPP_GLOBAL_Control
0x18002906f  cmp     rcx, rax
0x180029072  jz      short loc_180029095
0x180029074  test    byte ptr [rcx+1Ch], 80h
0x180029078  jz      short loc_180029095
0x18002907a  cmp     byte ptr [rcx+19h], 2
0x18002907e  jb      short loc_180029095
0x180029080  mov     edx, 0Ah
0x180029085  lea     r8, WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids
0x18002908c  mov     rcx, [rcx+10h]
0x180029090  call    WPP_SF_
0x180029095  mov     [rbp+57h+var_B0], 0
0x180029099  lea     rax, qword_1800A4718
0x1800290a0  mov     [rbp+57h+var_A8], rax
0x1800290a4  mov     [rbp+57h+var_A0], 0
0x1800290ac  mov     [rbp+57h+var_98], 0
0x1800290b4  mov     [rbp+57h+var_90], 0Eh
0x1800290bb  mov     [rbp+57h+var_8C], 0FFFFFFFFFFFFFFFFh
0x1800290c3  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x1800290ca  mov     [rbp+57h+pExceptionObject], rax
0x1800290ce  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x1800290d5  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800290d9  call    _CxxThrowException_0
```
