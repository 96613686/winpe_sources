# User::GetNetworkService(void)

- ea: `0x18001b46c`
- end: `0x18001b5bb`
- name: `?GetNetworkService@User@@SA?AV1@XZ`
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
- `0x18001b46c`
- `0x18001cad8`
- `0x18001cae4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b490`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b490`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b4b9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b4b9`

## pseudocode

```c
__int64 __fastcall User::GetNetworkService(__int64 a1)
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
  v4 = *((_QWORD *)User::s_userCache + 2);
  if ( !v4 )
  {
    WellKnownUser = User::CreateWellKnownUser((__int64)&v17, WinNetworkServiceSid);
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
    std::unique_ptr<User>::reset(v3 + 16, v8);
    v9 = std::unique_ptr<User>::get(v3 + 16);
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
0x18001b46c  mov     [rsp-28h+arg_0], rbx
0x18001b471  push    rbp
0x18001b472  push    rsi
0x18001b473  push    rdi
0x18001b474  push    r14
0x18001b476  push    r15
0x18001b478  mov     rbp, rsp
0x18001b47b  sub     rsp, 60h
0x18001b47f  mov     rsi, rcx
0x18001b482  mov     rbx, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x18001b489  mov     [rbp+arg_10], rbx
0x18001b48d  mov     rcx, rbx; lpCriticalSection
0x18001b490  call    cs:__imp_EnterCriticalSection
0x18001b497  nop     dword ptr [rax+rax+00h]
0x18001b49c  nop
0x18001b49d  mov     rdi, cs:?s_userCache@User@@0PEAVUserCache@1@EA; User::UserCache * User::s_userCache
0x18001b4a4  mov     rdx, [rdi+10h]
0x18001b4a8  test    rdx, rdx
0x18001b4ab  jz      short loc_18001B4DD
0x18001b4ad  mov     rcx, rsi
0x18001b4b0  call    ??0?$AutoRef@UUserEntry@User@@@wmi@@QEAA@AEBV01@@Z; wmi::AutoRef<User::UserEntry>::AutoRef<User::UserEntry>(wmi::AutoRef<User::UserEntry> const &)
0x18001b4b5  nop
0x18001b4b6  mov     rcx, rbx; lpCriticalSection
0x18001b4b9  call    cs:__imp_LeaveCriticalSection
0x18001b4c0  nop     dword ptr [rax+rax+00h]
0x18001b4c5  mov     rax, rsi
0x18001b4c8  mov     rbx, [rsp+60h+arg_0]
0x18001b4d0  add     rsp, 60h
0x18001b4d4  pop     r15
0x18001b4d6  pop     r14
0x18001b4d8  pop     rdi
0x18001b4d9  pop     rsi
0x18001b4da  pop     rbp
0x18001b4db  retn
0x18001b4dd  mov     edx, 18h
0x18001b4e2  lea     rcx, [rbp+arg_8]
0x18001b4e6  call    ?CreateWellKnownUser@User@@CA?AV1@W4WELL_KNOWN_SID_TYPE@@@Z; User::CreateWellKnownUser(WELL_KNOWN_SID_TYPE)
0x18001b4eb  mov     r15, rax
0x18001b4ee  mov     ecx, 8; Size
0x18001b4f3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001b4f8  mov     r14, rax
0x18001b4fb  mov     [rbp+arg_18], rax
0x18001b4ff  test    rax, rax
0x18001b502  jz      short loc_18001B53D
0x18001b504  mov     rdx, r15
0x18001b507  mov     rcx, rax
0x18001b50a  call    ??0?$AutoRef@UUserEntry@User@@@wmi@@QEAA@AEBV01@@Z; wmi::AutoRef<User::UserEntry>::AutoRef<User::UserEntry>(wmi::AutoRef<User::UserEntry> const &)
0x18001b50f  test    r14, r14
0x18001b512  jz      short loc_18001B53D
0x18001b514  mov     rdx, r14
0x18001b517  lea     rcx, [rdi+10h]
0x18001b51b  call    ?reset@?$unique_ptr@VUser@@U?$default_delete@VUser@@@std@@@std@@QEAAXPEAVUser@@@Z; std::unique_ptr<User>::reset(User *)
0x18001b520  lea     rcx, [rdi+10h]
0x18001b524  call    ?get@?$unique_ptr@VUser@@U?$default_delete@VUser@@@std@@@std@@QEBAPEAVUser@@XZ; std::unique_ptr<User>::get(void)
0x18001b529  mov     rdi, rax
0x18001b52c  lea     rcx, [rbp+arg_8]
0x18001b530  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x18001b535  mov     rdx, rdi
0x18001b538  jmp     loc_18001B4AD
0x18001b53d  lea     rax, WPP_GLOBAL_Control
0x18001b544  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b54b  cmp     rcx, rax
0x18001b54e  jz      short loc_18001B571
0x18001b550  test    byte ptr [rcx+1Ch], 80h
0x18001b554  jz      short loc_18001B571
0x18001b556  cmp     byte ptr [rcx+19h], 2
0x18001b55a  jb      short loc_18001B571
0x18001b55c  mov     edx, 0Ah
0x18001b561  lea     r8, WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids
0x18001b568  mov     rcx, [rcx+10h]
0x18001b56c  call    WPP_SF_
0x18001b571  mov     [rbp+var_30], 0
0x18001b575  lea     rax, byte_180052608
0x18001b57c  mov     [rbp+var_28], rax
0x18001b580  mov     [rbp+var_20], 0
0x18001b588  mov     [rbp+var_18], 0
0x18001b590  mov     [rbp+var_10], 0Eh
0x18001b597  mov     [rbp+var_C], 0FFFFFFFFFFFFFFFFh
0x18001b59f  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18001b5a6  mov     [rbp+pExceptionObject], rax
0x18001b5aa  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x18001b5b1  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001b5b5  call    _CxxThrowException_0
```
