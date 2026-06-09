# User::GetLocalService(void)

- ea: `0x180019e44`
- end: `0x180019f72`
- name: `?GetLocalService@User@@SA?AV1@XZ`
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
- `0x180019e44`
- `0x18001b5d4`
- `0x18001b5e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019e63`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019e63`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019e86`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019e86`

## pseudocode

```c
__int64 __fastcall User::GetLocalService(__int64 a1)
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
  v4 = *((_QWORD *)User::s_userCache + 1);
  if ( !v4 )
  {
    WellKnownUser = User::CreateWellKnownUser((__int64)&v17, WinLocalServiceSid);
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
    std::unique_ptr<User>::reset(v3 + 8, v8);
    v9 = std::unique_ptr<User>::get((__int64)(v3 + 8));
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
0x180019e44  push    rbp
0x180019e46  push    rbx
0x180019e47  push    rsi
0x180019e48  push    rdi
0x180019e49  push    r14
0x180019e4b  mov     rbp, rsp
0x180019e4e  sub     rsp, 60h
0x180019e52  mov     rsi, rcx
0x180019e55  mov     rbx, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x180019e5c  mov     [rbp+arg_10], rbx
0x180019e60  mov     rcx, rbx; lpCriticalSection
0x180019e63  call    cs:__imp_EnterCriticalSection
0x180019e69  nop
0x180019e6a  mov     rdi, cs:?s_userCache@User@@0PEAVUserCache@1@EA; User::UserCache * User::s_userCache
0x180019e71  mov     rdx, [rdi+8]
0x180019e75  test    rdx, rdx
0x180019e78  jz      short loc_180019E9A
0x180019e7a  mov     rcx, rsi
0x180019e7d  call    ??0User@@AEAA@AEBV?$AutoRef@UUserEntry@User@@@wmi@@@Z; User::User(wmi::AutoRef<User::UserEntry> const &)
0x180019e82  nop
0x180019e83  mov     rcx, rbx; lpCriticalSection
0x180019e86  call    cs:__imp_LeaveCriticalSection
0x180019e8c  mov     rax, rsi
0x180019e8f  add     rsp, 60h
0x180019e93  pop     r14
0x180019e95  pop     rdi
0x180019e96  pop     rsi
0x180019e97  pop     rbx
0x180019e98  pop     rbp
0x180019e99  retn
0x180019e9a  mov     edx, 17h
0x180019e9f  lea     rcx, [rbp+arg_8]
0x180019ea3  call    ?CreateWellKnownUser@User@@CA?AV1@W4WELL_KNOWN_SID_TYPE@@@Z; User::CreateWellKnownUser(WELL_KNOWN_SID_TYPE)
0x180019ea8  mov     r14, rax
0x180019eab  mov     ecx, 8; Size
0x180019eb0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180019eb5  mov     [rbp+arg_18], rax
0x180019eb9  test    rax, rax
0x180019ebc  jz      short loc_180019EF4
0x180019ebe  mov     rdx, r14
0x180019ec1  mov     rcx, rax
0x180019ec4  call    ??0User@@AEAA@AEBV?$AutoRef@UUserEntry@User@@@wmi@@@Z; User::User(wmi::AutoRef<User::UserEntry> const &)
0x180019ec9  test    rax, rax
0x180019ecc  jz      short loc_180019EF4
0x180019ece  mov     rdx, rax
0x180019ed1  lea     rcx, [rdi+8]
0x180019ed5  call    ?reset@?$unique_ptr@VUser@@U?$default_delete@VUser@@@std@@@std@@QEAAXPEAVUser@@@Z; std::unique_ptr<User>::reset(User *)
0x180019eda  lea     rcx, [rdi+8]
0x180019ede  call    ?get@?$unique_ptr@VUser@@U?$default_delete@VUser@@@std@@@std@@QEBAPEAVUser@@XZ; std::unique_ptr<User>::get(void)
0x180019ee3  mov     rdi, rax
0x180019ee6  lea     rcx, [rbp+arg_8]
0x180019eea  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x180019eef  mov     rdx, rdi
0x180019ef2  jmp     short loc_180019E7A
0x180019ef4  lea     rax, WPP_GLOBAL_Control
0x180019efb  mov     rcx, cs:WPP_GLOBAL_Control
0x180019f02  cmp     rcx, rax
0x180019f05  jz      short loc_180019F28
0x180019f07  test    byte ptr [rcx+1Ch], 80h
0x180019f0b  jz      short loc_180019F28
0x180019f0d  cmp     byte ptr [rcx+19h], 2
0x180019f11  jb      short loc_180019F28
0x180019f13  mov     edx, 0Ah
0x180019f18  lea     r8, WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids
0x180019f1f  mov     rcx, [rcx+10h]
0x180019f23  call    WPP_SF_
0x180019f28  mov     [rbp+var_30], 0
0x180019f2c  lea     rax, byte_1800505F8
0x180019f33  mov     [rbp+var_28], rax
0x180019f37  mov     [rbp+var_20], 0
0x180019f3f  mov     [rbp+var_18], 0
0x180019f47  mov     [rbp+var_10], 0Eh
0x180019f4e  mov     [rbp+var_C], 0FFFFFFFFFFFFFFFFh
0x180019f56  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180019f5d  mov     [rbp+pExceptionObject], rax
0x180019f61  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x180019f68  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180019f6c  call    _CxxThrowException_0
```
