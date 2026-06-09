# User::GetLocalService(void)

- ea: `0x18001b124`
- end: `0x18001b273`
- name: `?GetLocalService@User@@SA?AV1@XZ`
- size: `335`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, service_task`

## callers

- `0x18001a394`
- `0x18001b68c`

## callees

- `0x1800053bc`
- `0x180007948`
- `0x180008c4c`
- `0x180010570`
- `0x18001977c`
- `0x18001a794`
- `0x18001b124`
- `0x18001cad8`
- `0x18001cae4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b148`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b148`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b171`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b171`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall User::GetLocalService(__int64 a1)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbx
  char *v3; // rdi
  __int64 v4; // rdx
  __int64 WellKnownUser; // r15
  void *v7; // rax
  void *v8; // r14
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
    v8 = v7;
    v19 = v7;
    if ( !v7 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids);
      }
      v11 = 0;
      v12 = byte_180052608;
      v13 = 0;
      v14 = 0;
      v15 = 14;
      v16 = -1;
      pExceptionObject = &wmi::GenericException::`vftable';
      throw (wmi::OutOfMemoryException *)&pExceptionObject;
    }
    wmi::AutoRef<User::UserEntry>::AutoRef<User::UserEntry>(v7, WellKnownUser);
    std::unique_ptr<User>::reset(v3 + 8, v8);
    v9 = std::unique_ptr<User>::get(v3 + 8);
    wmi::AutoRef<User::UserEntry>::Release(&v17);
    v4 = v9;
  }
  wmi::AutoRef<User::UserEntry>::AutoRef<User::UserEntry>(a1, v4);
  LeaveCriticalSection(v2);
  return a1;
}

```

## disassembly

```asm
0x18001b124  mov     [rsp-28h+arg_0], rbx
0x18001b129  push    rbp
0x18001b12a  push    rsi
0x18001b12b  push    rdi
0x18001b12c  push    r14
0x18001b12e  push    r15
0x18001b130  mov     rbp, rsp
0x18001b133  sub     rsp, 60h
0x18001b137  mov     rsi, rcx
0x18001b13a  mov     rbx, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x18001b141  mov     [rbp+arg_10], rbx
0x18001b145  mov     rcx, rbx; lpCriticalSection
0x18001b148  call    cs:__imp_EnterCriticalSection
0x18001b14f  nop     dword ptr [rax+rax+00h]
0x18001b154  nop
0x18001b155  mov     rdi, cs:?s_userCache@User@@0PEAVUserCache@1@EA; User::UserCache * User::s_userCache
0x18001b15c  mov     rdx, [rdi+8]
0x18001b160  test    rdx, rdx
0x18001b163  jz      short loc_18001B195
0x18001b165  mov     rcx, rsi
0x18001b168  call    ??0?$AutoRef@UUserEntry@User@@@wmi@@QEAA@AEBV01@@Z; wmi::AutoRef<User::UserEntry>::AutoRef<User::UserEntry>(wmi::AutoRef<User::UserEntry> const &)
0x18001b16d  nop
0x18001b16e  mov     rcx, rbx; lpCriticalSection
0x18001b171  call    cs:__imp_LeaveCriticalSection
0x18001b178  nop     dword ptr [rax+rax+00h]
0x18001b17d  mov     rax, rsi
0x18001b180  mov     rbx, [rsp+60h+arg_0]
0x18001b188  add     rsp, 60h
0x18001b18c  pop     r15
0x18001b18e  pop     r14
0x18001b190  pop     rdi
0x18001b191  pop     rsi
0x18001b192  pop     rbp
0x18001b193  retn
0x18001b195  mov     edx, 17h
0x18001b19a  lea     rcx, [rbp+arg_8]
0x18001b19e  call    ?CreateWellKnownUser@User@@CA?AV1@W4WELL_KNOWN_SID_TYPE@@@Z; User::CreateWellKnownUser(WELL_KNOWN_SID_TYPE)
0x18001b1a3  mov     r15, rax
0x18001b1a6  mov     ecx, 8; Size
0x18001b1ab  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001b1b0  mov     r14, rax
0x18001b1b3  mov     [rbp+arg_18], rax
0x18001b1b7  test    rax, rax
0x18001b1ba  jz      short loc_18001B1F5
0x18001b1bc  mov     rdx, r15
0x18001b1bf  mov     rcx, rax
0x18001b1c2  call    ??0?$AutoRef@UUserEntry@User@@@wmi@@QEAA@AEBV01@@Z; wmi::AutoRef<User::UserEntry>::AutoRef<User::UserEntry>(wmi::AutoRef<User::UserEntry> const &)
0x18001b1c7  test    r14, r14
0x18001b1ca  jz      short loc_18001B1F5
0x18001b1cc  mov     rdx, r14
0x18001b1cf  lea     rcx, [rdi+8]
0x18001b1d3  call    ?reset@?$unique_ptr@VUser@@U?$default_delete@VUser@@@std@@@std@@QEAAXPEAVUser@@@Z; std::unique_ptr<User>::reset(User *)
0x18001b1d8  lea     rcx, [rdi+8]
0x18001b1dc  call    ?get@?$unique_ptr@VUser@@U?$default_delete@VUser@@@std@@@std@@QEBAPEAVUser@@XZ; std::unique_ptr<User>::get(void)
0x18001b1e1  mov     rdi, rax
0x18001b1e4  lea     rcx, [rbp+arg_8]
0x18001b1e8  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x18001b1ed  mov     rdx, rdi
0x18001b1f0  jmp     loc_18001B165
0x18001b1f5  lea     rax, WPP_GLOBAL_Control
0x18001b1fc  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b203  cmp     rcx, rax
0x18001b206  jz      short loc_18001B229
0x18001b208  test    byte ptr [rcx+1Ch], 80h
0x18001b20c  jz      short loc_18001B229
0x18001b20e  cmp     byte ptr [rcx+19h], 2
0x18001b212  jb      short loc_18001B229
0x18001b214  mov     edx, 0Ah
0x18001b219  lea     r8, WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids
0x18001b220  mov     rcx, [rcx+10h]
0x18001b224  call    WPP_SF_
0x18001b229  mov     [rbp+var_30], 0
0x18001b22d  lea     rax, byte_180052608
0x18001b234  mov     [rbp+var_28], rax
0x18001b238  mov     [rbp+var_20], 0
0x18001b240  mov     [rbp+var_18], 0
0x18001b248  mov     [rbp+var_10], 0Eh
0x18001b24f  mov     [rbp+var_C], 0FFFFFFFFFFFFFFFFh
0x18001b257  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18001b25e  mov     [rbp+pExceptionObject], rax
0x18001b262  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x18001b269  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001b26d  call    _CxxThrowException_0
```
