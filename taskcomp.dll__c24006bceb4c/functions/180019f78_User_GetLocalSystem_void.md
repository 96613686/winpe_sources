# User::GetLocalSystem(void)

- ea: `0x180019f78`
- end: `0x18001a14b`
- name: `?GetLocalSystem@User@@SA?AV1@XZ`
- size: `467`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180019168`
- `0x18001a334`

## callees

- `0x180003470`
- `0x180004e50`
- `0x1800050fc`
- `0x180007488`
- `0x18000878c`
- `0x18000fbb8`
- `0x180018604`
- `0x180018d00`
- `0x180019f78`
- `0x18001b5d4`
- `0x18001b5e0`
- `0x18002e5b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019fb5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019fb5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019fd7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019fd7`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18001a01a`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18001a01a`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall User::GetLocalSystem(__int64 a1)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbx
  __int64 v3; // rdx
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
  char *v16; // [rsp+68h] [rbp-51h]
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
  v3 = *(_QWORD *)User::s_userCache;
  if ( !*(_QWORD *)User::s_userCache )
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
             pSid);
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
      v16 = byte_1800505F8;
      v17 = 0;
      v18 = 0;
      v19 = 14;
      v20 = -1;
      pExceptionObject = &wmi::GenericException::`vftable';
      throw (wmi::OutOfMemoryException *)&pExceptionObject;
    }
    std::unique_ptr<User>::reset(v5, v8);
    v9 = std::unique_ptr<User>::get((__int64)v5);
    wmi::AutoRef<User::UserEntry>::Release(v13);
    _bstr_t::~_bstr_t((_bstr_t *)v11);
    _bstr_t::~_bstr_t((_bstr_t *)v12);
    v3 = v9;
  }
  User::User(a1, v3);
  LeaveCriticalSection(v2);
  return a1;
}

```

## disassembly

```asm
0x180019f78  mov     [rsp-8+arg_8], rbx
0x180019f7d  mov     [rsp-8+arg_10], rsi
0x180019f82  push    rbp
0x180019f83  push    rdi
0x180019f84  push    r14
0x180019f86  lea     rbp, [rsp-47h]
0x180019f8b  sub     rsp, 100h
0x180019f92  mov     rax, cs:__security_cookie
0x180019f99  xor     rax, rsp
0x180019f9c  mov     [rbp+57h+var_20], rax
0x180019fa0  mov     rsi, rcx
0x180019fa3  mov     [rbp+57h+var_C8], rcx
0x180019fa7  mov     rbx, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x180019fae  mov     [rbp+57h+var_80], rbx
0x180019fb2  mov     rcx, rbx; lpCriticalSection
0x180019fb5  call    cs:__imp_EnterCriticalSection
0x180019fbb  nop
0x180019fbc  mov     rcx, cs:?s_userCache@User@@0PEAVUserCache@1@EA; User::UserCache * User::s_userCache
0x180019fc3  mov     rdx, [rcx]
0x180019fc6  test    rdx, rdx
0x180019fc9  jz      short loc_18001A004
0x180019fcb  mov     rcx, rsi
0x180019fce  call    ??0User@@AEAA@AEBV?$AutoRef@UUserEntry@User@@@wmi@@@Z; User::User(wmi::AutoRef<User::UserEntry> const &)
0x180019fd3  nop
0x180019fd4  mov     rcx, rbx; lpCriticalSection
0x180019fd7  call    cs:__imp_LeaveCriticalSection
0x180019fdd  mov     rax, rsi
0x180019fe0  mov     rcx, [rbp+57h+var_20]
0x180019fe4  xor     rcx, rsp; StackCookie
0x180019fe7  call    __security_check_cookie
0x180019fec  lea     r11, [rsp+110h+var_10]
0x180019ff4  mov     rbx, [r11+28h]
0x180019ff8  mov     rsi, [r11+30h]
0x180019ffc  mov     rsp, r11
0x180019fff  pop     r14
0x18001a001  pop     rdi
0x18001a002  pop     rbp
0x18001a003  retn
0x18001a004  mov     [rsp+110h+cbSid], 44h ; 'D'
0x18001a00c  lea     r9, [rsp+110h+cbSid]; cbSid
0x18001a011  lea     r8, [rbp+57h+pSid]; pSid
0x18001a015  xor     edx, edx; DomainSid
0x18001a017  lea     ecx, [rdx+16h]; WellKnownSidType
0x18001a01a  call    cs:__imp_CreateWellKnownSid
0x18001a020  mov     rdi, cs:?s_userCache@User@@0PEAVUserCache@1@EA; User::UserCache * User::s_userCache
0x18001a027  lea     rdx, aNtAuthority; "NT AUTHORITY"
0x18001a02e  lea     rcx, [rbp+57h+var_D0]; this
0x18001a032  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18001a037  nop
0x18001a038  lea     rdx, aSystem; "System"
0x18001a03f  lea     rcx, [rsp+110h+var_D8]; this
0x18001a044  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18001a049  nop
0x18001a04a  lea     rax, [rbp+57h+pSid]
0x18001a04e  mov     [rsp+110h+var_F0], rax
0x18001a053  mov     r9d, 5
0x18001a059  lea     r8, [rbp+57h+var_D0]
0x18001a05d  lea     rdx, [rsp+110h+var_D8]
0x18001a062  lea     rcx, [rbp+57h+var_C8]
0x18001a066  call    ?CreateUser@User@@SA?AV1@AEBV_bstr_t@@0W4_SID_NAME_USE@@PEAX@Z; User::CreateUser(_bstr_t const &,_bstr_t const &,_SID_NAME_USE,void *)
0x18001a06b  mov     r14, rax
0x18001a06e  mov     ecx, 8; Size
0x18001a073  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001a078  mov     [rbp+57h+var_78], rax
0x18001a07c  test    rax, rax
0x18001a07f  jz      short loc_18001A0CD
0x18001a081  mov     rdx, r14
0x18001a084  mov     rcx, rax
0x18001a087  call    ??0User@@AEAA@AEBV?$AutoRef@UUserEntry@User@@@wmi@@@Z; User::User(wmi::AutoRef<User::UserEntry> const &)
0x18001a08c  test    rax, rax
0x18001a08f  jz      short loc_18001A0CD
0x18001a091  mov     rdx, rax
0x18001a094  mov     rcx, rdi
0x18001a097  call    ?reset@?$unique_ptr@VUser@@U?$default_delete@VUser@@@std@@@std@@QEAAXPEAVUser@@@Z; std::unique_ptr<User>::reset(User *)
0x18001a09c  mov     rcx, rdi
0x18001a09f  call    ?get@?$unique_ptr@VUser@@U?$default_delete@VUser@@@std@@@std@@QEBAPEAVUser@@XZ; std::unique_ptr<User>::get(void)
0x18001a0a4  mov     rdi, rax
0x18001a0a7  lea     rcx, [rbp+57h+var_C8]
0x18001a0ab  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x18001a0b0  nop
0x18001a0b1  lea     rcx, [rsp+110h+var_D8]; this
0x18001a0b6  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18001a0bb  nop
0x18001a0bc  lea     rcx, [rbp+57h+var_D0]; this
0x18001a0c0  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18001a0c5  mov     rdx, rdi
0x18001a0c8  jmp     loc_180019FCB
0x18001a0cd  lea     rax, WPP_GLOBAL_Control
0x18001a0d4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a0db  cmp     rcx, rax
0x18001a0de  jz      short loc_18001A101
0x18001a0e0  test    byte ptr [rcx+1Ch], 80h
0x18001a0e4  jz      short loc_18001A101
0x18001a0e6  cmp     byte ptr [rcx+19h], 2
0x18001a0ea  jb      short loc_18001A101
0x18001a0ec  mov     edx, 0Ah
0x18001a0f1  lea     r8, WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids
0x18001a0f8  mov     rcx, [rcx+10h]
0x18001a0fc  call    WPP_SF_
0x18001a101  mov     [rbp+57h+var_B0], 0
0x18001a105  lea     rax, byte_1800505F8
0x18001a10c  mov     [rbp+57h+var_A8], rax
0x18001a110  mov     [rbp+57h+var_A0], 0
0x18001a118  mov     [rbp+57h+var_98], 0
0x18001a120  mov     [rbp+57h+var_90], 0Eh
0x18001a127  mov     [rbp+57h+var_8C], 0FFFFFFFFFFFFFFFFh
0x18001a12f  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18001a136  mov     [rbp+57h+pExceptionObject], rax
0x18001a13a  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x18001a141  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18001a145  call    _CxxThrowException_0
```
