# User::GetLocalSystem(void)

- ea: `0x18001b27c`
- end: `0x18001b464`
- name: `?GetLocalSystem@User@@SA?AV1@XZ`
- size: `488`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18001a394`
- `0x18001b68c`

## callees

- `0x180003600`
- `0x1800050d0`
- `0x1800053bc`
- `0x180007948`
- `0x180008c4c`
- `0x180010570`
- `0x18001977c`
- `0x180019f10`
- `0x18001b27c`
- `0x18001cad8`
- `0x18001cae4`
- `0x180030700`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b2b5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b2b5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b2dd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b2dd`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18001b31f`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18001b31f`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall User::GetLocalSystem(__int64 a1)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbx
  __int64 v3; // rdx
  void *v5; // r14
  __int64 User; // r15
  void *v7; // rax
  void *v8; // rdi
  __int64 v9; // rdi
  DWORD cbSid; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v11[8]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v12[8]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v13[2]; // [rsp+48h] [rbp-B8h] BYREF
  void **pExceptionObject; // [rsp+58h] [rbp-A8h] BYREF
  char v15; // [rsp+60h] [rbp-A0h]
  char *v16; // [rsp+68h] [rbp-98h]
  __int64 v17; // [rsp+70h] [rbp-90h]
  __int64 v18; // [rsp+78h] [rbp-88h]
  int v19; // [rsp+80h] [rbp-80h]
  __int64 v20; // [rsp+84h] [rbp-7Ch]
  LPCRITICAL_SECTION v21; // [rsp+90h] [rbp-70h]
  void *v22; // [rsp+98h] [rbp-68h]
  _BYTE pSid[80]; // [rsp+A0h] [rbp-60h] BYREF

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
    v8 = v7;
    v22 = v7;
    if ( !v7 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids);
      }
      v15 = 0;
      v16 = byte_180052608;
      v17 = 0;
      v18 = 0;
      v19 = 14;
      v20 = -1;
      pExceptionObject = &wmi::GenericException::`vftable';
      throw (wmi::OutOfMemoryException *)&pExceptionObject;
    }
    wmi::AutoRef<User::UserEntry>::AutoRef<User::UserEntry>(v7, User);
    std::unique_ptr<User>::reset(v5, v8);
    v9 = std::unique_ptr<User>::get(v5);
    wmi::AutoRef<User::UserEntry>::Release(v13);
    _bstr_t::~_bstr_t((_bstr_t *)v11);
    _bstr_t::~_bstr_t((_bstr_t *)v12);
    v3 = v9;
  }
  wmi::AutoRef<User::UserEntry>::AutoRef<User::UserEntry>(a1, v3);
  LeaveCriticalSection(v2);
  return a1;
}

```

## disassembly

```asm
0x18001b27c  push    rbp
0x18001b27e  push    rbx
0x18001b27f  push    rsi
0x18001b280  push    rdi
0x18001b281  push    r14
0x18001b283  push    r15
0x18001b285  lea     rbp, [rsp-8]
0x18001b28a  sub     rsp, 108h
0x18001b291  mov     rax, cs:__security_cookie
0x18001b298  xor     rax, rsp
0x18001b29b  mov     [rbp+30h+var_40], rax
0x18001b29f  mov     rsi, rcx
0x18001b2a2  mov     [rsp+130h+var_E8], rcx
0x18001b2a7  mov     rbx, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x18001b2ae  mov     [rbp+30h+var_A0], rbx
0x18001b2b2  mov     rcx, rbx; lpCriticalSection
0x18001b2b5  call    cs:__imp_EnterCriticalSection
0x18001b2bc  nop     dword ptr [rax+rax+00h]
0x18001b2c1  nop
0x18001b2c2  mov     rcx, cs:?s_userCache@User@@0PEAVUserCache@1@EA; User::UserCache * User::s_userCache
0x18001b2c9  mov     rdx, [rcx]
0x18001b2cc  test    rdx, rdx
0x18001b2cf  jz      short loc_18001B309
0x18001b2d1  mov     rcx, rsi
0x18001b2d4  call    ??0?$AutoRef@UUserEntry@User@@@wmi@@QEAA@AEBV01@@Z; wmi::AutoRef<User::UserEntry>::AutoRef<User::UserEntry>(wmi::AutoRef<User::UserEntry> const &)
0x18001b2d9  nop
0x18001b2da  mov     rcx, rbx; lpCriticalSection
0x18001b2dd  call    cs:__imp_LeaveCriticalSection
0x18001b2e4  nop     dword ptr [rax+rax+00h]
0x18001b2e9  mov     rax, rsi
0x18001b2ec  mov     rcx, [rbp+30h+var_40]
0x18001b2f0  xor     rcx, rsp; StackCookie
0x18001b2f3  call    __security_check_cookie
0x18001b2f8  add     rsp, 108h
0x18001b2ff  pop     r15
0x18001b301  pop     r14
0x18001b303  pop     rdi
0x18001b304  pop     rsi
0x18001b305  pop     rbx
0x18001b306  pop     rbp
0x18001b307  retn
0x18001b309  mov     [rsp+130h+cbSid], 44h ; 'D'
0x18001b311  lea     r9, [rsp+130h+cbSid]; cbSid
0x18001b316  lea     r8, [rbp+30h+pSid]; pSid
0x18001b31a  xor     edx, edx; DomainSid
0x18001b31c  lea     ecx, [rdx+16h]; WellKnownSidType
0x18001b31f  call    cs:__imp_CreateWellKnownSid
0x18001b326  nop     dword ptr [rax+rax+00h]
0x18001b32b  mov     r14, cs:?s_userCache@User@@0PEAVUserCache@1@EA; User::UserCache * User::s_userCache
0x18001b332  lea     rdx, aNtAuthority; "NT AUTHORITY"
0x18001b339  lea     rcx, [rsp+130h+var_F0]; this
0x18001b33e  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18001b343  nop
0x18001b344  lea     rdx, aSystem; "System"
0x18001b34b  lea     rcx, [rsp+130h+var_F8]; this
0x18001b350  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18001b355  nop
0x18001b356  lea     rax, [rbp+30h+pSid]
0x18001b35a  mov     [rsp+130h+var_110], rax
0x18001b35f  mov     r9d, 5
0x18001b365  lea     r8, [rsp+130h+var_F0]
0x18001b36a  lea     rdx, [rsp+130h+var_F8]
0x18001b36f  lea     rcx, [rsp+130h+var_E8]
0x18001b374  call    ?CreateUser@User@@SA?AV1@AEBV_bstr_t@@0W4_SID_NAME_USE@@PEAX@Z; User::CreateUser(_bstr_t const &,_bstr_t const &,_SID_NAME_USE,void *)
0x18001b379  mov     r15, rax
0x18001b37c  mov     ecx, 8; Size
0x18001b381  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001b386  mov     rdi, rax
0x18001b389  mov     [rbp+30h+var_98], rax
0x18001b38d  test    rax, rax
0x18001b390  jz      short loc_18001B3E0
0x18001b392  mov     rdx, r15
0x18001b395  mov     rcx, rax
0x18001b398  call    ??0?$AutoRef@UUserEntry@User@@@wmi@@QEAA@AEBV01@@Z; wmi::AutoRef<User::UserEntry>::AutoRef<User::UserEntry>(wmi::AutoRef<User::UserEntry> const &)
0x18001b39d  test    rdi, rdi
0x18001b3a0  jz      short loc_18001B3E0
0x18001b3a2  mov     rdx, rdi
0x18001b3a5  mov     rcx, r14
0x18001b3a8  call    ?reset@?$unique_ptr@VUser@@U?$default_delete@VUser@@@std@@@std@@QEAAXPEAVUser@@@Z; std::unique_ptr<User>::reset(User *)
0x18001b3ad  mov     rcx, r14
0x18001b3b0  call    ?get@?$unique_ptr@VUser@@U?$default_delete@VUser@@@std@@@std@@QEBAPEAVUser@@XZ; std::unique_ptr<User>::get(void)
0x18001b3b5  mov     rdi, rax
0x18001b3b8  lea     rcx, [rsp+130h+var_E8]
0x18001b3bd  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x18001b3c2  nop
0x18001b3c3  lea     rcx, [rsp+130h+var_F8]; this
0x18001b3c8  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18001b3cd  nop
0x18001b3ce  lea     rcx, [rsp+130h+var_F0]; this
0x18001b3d3  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18001b3d8  mov     rdx, rdi
0x18001b3db  jmp     loc_18001B2D1
0x18001b3e0  lea     rax, WPP_GLOBAL_Control
0x18001b3e7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b3ee  cmp     rcx, rax
0x18001b3f1  jz      short loc_18001B414
0x18001b3f3  test    byte ptr [rcx+1Ch], 80h
0x18001b3f7  jz      short loc_18001B414
0x18001b3f9  cmp     byte ptr [rcx+19h], 2
0x18001b3fd  jb      short loc_18001B414
0x18001b3ff  mov     edx, 0Ah
0x18001b404  lea     r8, WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids
0x18001b40b  mov     rcx, [rcx+10h]
0x18001b40f  call    WPP_SF_
0x18001b414  mov     [rsp+130h+var_D0], 0
0x18001b419  lea     rax, byte_180052608
0x18001b420  mov     [rsp+130h+var_C8], rax
0x18001b425  mov     [rsp+130h+var_C0], 0
0x18001b42e  mov     [rsp+130h+var_B8], 0
0x18001b437  mov     [rbp+30h+var_B0], 0Eh
0x18001b43e  mov     [rbp+30h+var_AC], 0FFFFFFFFFFFFFFFFh
0x18001b446  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18001b44d  mov     [rsp+130h+pExceptionObject], rax
0x18001b452  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x18001b459  lea     rcx, [rsp+130h+pExceptionObject]; pExceptionObject
0x18001b45e  call    _CxxThrowException_0
```
