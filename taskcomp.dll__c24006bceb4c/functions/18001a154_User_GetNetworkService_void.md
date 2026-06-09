# User::GetNetworkService(void)

- ea: `0x18001a154`
- end: `0x18001a282`
- name: `?GetNetworkService@User@@SA?AV1@XZ`
- size: `302`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, service_task`

## callers

- `0x180019168`
- `0x18001a334`

## callees

- `0x1800050fc`
- `0x180007488`
- `0x18000878c`
- `0x18000fbb8`
- `0x180018604`
- `0x18001953c`
- `0x18001a154`
- `0x18001b5d4`
- `0x18001b5e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a173`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a173`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a196`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a196`

## pseudocode

```c
__int64 __fastcall User::GetNetworkService(__int64 a1)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbx
  char *v3; // rdi
  __int64 v4; // rdx
  __int64 WellKnownUser; // r14
  void *v7; // rax
  __int64 v8; // rax
  __int64 v9; // rdi
  void **pExceptionObject; // [rsp+28h] [rbp-38h] BYREF
  char v11; // [rsp+30h] [rbp-30h]
  char *v12; // [rsp+38h] [rbp-28h]
  __int64 v13; // [rsp+40h] [rbp-20h]
  __int64 v14; // [rsp+48h] [rbp-18h]
  int v15; // [rsp+50h] [rbp-10h]
  __int64 v16; // [rsp+54h] [rbp-Ch]
  char v17; // [rsp+98h] [rbp+38h] BYREF
  LPCRITICAL_SECTION v18; // [rsp+A0h] [rbp+40h]
  void *v19; // [rsp+A8h] [rbp+48h]

  v2 = User::s_cs;
  v18 = User::s_cs;
  EnterCriticalSection(User::s_cs);
  v3 = (char *)User::s_userCache;
  v4 = *((_QWORD *)User::s_userCache + 2);
  if ( !v4 )
  {
    WellKnownUser = User::CreateWellKnownUser((__int64)&v17, WinNetworkServiceSid);
    v7 = operator new(8u);
    v19 = v7;
    if ( !v7 || (v8 = User::User(v7, WellKnownUser)) == 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids);
      }
      v11 = 0;
      v12 = byte_1800505F8;
      v13 = 0;
      v14 = 0;
      v15 = 14;
      v16 = -1;
      pExceptionObject = &wmi::GenericException::`vftable';
      throw (wmi::OutOfMemoryException *)&pExceptionObject;
    }
    std::unique_ptr<User>::reset(v3 + 16, v8);
    v9 = std::unique_ptr<User>::get((__int64)(v3 + 16));
    wmi::AutoRef<User::UserEntry>::Release(&v17);
    v4 = v9;
  }
  User::User(a1, v4);
  LeaveCriticalSection(v2);
  return a1;
}

```

## disassembly

```asm
0x18001a154  push    rbp
0x18001a156  push    rbx
0x18001a157  push    rsi
0x18001a158  push    rdi
0x18001a159  push    r14
0x18001a15b  mov     rbp, rsp
0x18001a15e  sub     rsp, 60h
0x18001a162  mov     rsi, rcx
0x18001a165  mov     rbx, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x18001a16c  mov     [rbp+arg_10], rbx
0x18001a170  mov     rcx, rbx; lpCriticalSection
0x18001a173  call    cs:__imp_EnterCriticalSection
0x18001a179  nop
0x18001a17a  mov     rdi, cs:?s_userCache@User@@0PEAVUserCache@1@EA; User::UserCache * User::s_userCache
0x18001a181  mov     rdx, [rdi+10h]
0x18001a185  test    rdx, rdx
0x18001a188  jz      short loc_18001A1AA
0x18001a18a  mov     rcx, rsi
0x18001a18d  call    ??0User@@AEAA@AEBV?$AutoRef@UUserEntry@User@@@wmi@@@Z; User::User(wmi::AutoRef<User::UserEntry> const &)
0x18001a192  nop
0x18001a193  mov     rcx, rbx; lpCriticalSection
0x18001a196  call    cs:__imp_LeaveCriticalSection
0x18001a19c  mov     rax, rsi
0x18001a19f  add     rsp, 60h
0x18001a1a3  pop     r14
0x18001a1a5  pop     rdi
0x18001a1a6  pop     rsi
0x18001a1a7  pop     rbx
0x18001a1a8  pop     rbp
0x18001a1a9  retn
0x18001a1aa  mov     edx, 18h
0x18001a1af  lea     rcx, [rbp+arg_8]
0x18001a1b3  call    ?CreateWellKnownUser@User@@CA?AV1@W4WELL_KNOWN_SID_TYPE@@@Z; User::CreateWellKnownUser(WELL_KNOWN_SID_TYPE)
0x18001a1b8  mov     r14, rax
0x18001a1bb  mov     ecx, 8; Size
0x18001a1c0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001a1c5  mov     [rbp+arg_18], rax
0x18001a1c9  test    rax, rax
0x18001a1cc  jz      short loc_18001A204
0x18001a1ce  mov     rdx, r14
0x18001a1d1  mov     rcx, rax
0x18001a1d4  call    ??0User@@AEAA@AEBV?$AutoRef@UUserEntry@User@@@wmi@@@Z; User::User(wmi::AutoRef<User::UserEntry> const &)
0x18001a1d9  test    rax, rax
0x18001a1dc  jz      short loc_18001A204
0x18001a1de  mov     rdx, rax
0x18001a1e1  lea     rcx, [rdi+10h]
0x18001a1e5  call    ?reset@?$unique_ptr@VUser@@U?$default_delete@VUser@@@std@@@std@@QEAAXPEAVUser@@@Z; std::unique_ptr<User>::reset(User *)
0x18001a1ea  lea     rcx, [rdi+10h]
0x18001a1ee  call    ?get@?$unique_ptr@VUser@@U?$default_delete@VUser@@@std@@@std@@QEBAPEAVUser@@XZ; std::unique_ptr<User>::get(void)
0x18001a1f3  mov     rdi, rax
0x18001a1f6  lea     rcx, [rbp+arg_8]
0x18001a1fa  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x18001a1ff  mov     rdx, rdi
0x18001a202  jmp     short loc_18001A18A
0x18001a204  lea     rax, WPP_GLOBAL_Control
0x18001a20b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a212  cmp     rcx, rax
0x18001a215  jz      short loc_18001A238
0x18001a217  test    byte ptr [rcx+1Ch], 80h
0x18001a21b  jz      short loc_18001A238
0x18001a21d  cmp     byte ptr [rcx+19h], 2
0x18001a221  jb      short loc_18001A238
0x18001a223  mov     edx, 0Ah
0x18001a228  lea     r8, WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids
0x18001a22f  mov     rcx, [rcx+10h]
0x18001a233  call    WPP_SF_
0x18001a238  mov     [rbp+var_30], 0
0x18001a23c  lea     rax, byte_1800505F8
0x18001a243  mov     [rbp+var_28], rax
0x18001a247  mov     [rbp+var_20], 0
0x18001a24f  mov     [rbp+var_18], 0
0x18001a257  mov     [rbp+var_10], 0Eh
0x18001a25e  mov     [rbp+var_C], 0FFFFFFFFFFFFFFFFh
0x18001a266  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18001a26d  mov     [rbp+pExceptionObject], rax
0x18001a271  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x18001a278  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001a27c  call    _CxxThrowException_0
```
