# User::IsLocalService(void)

- ea: `0x18001ba50`
- end: `0x18001bb82`
- name: `?IsLocalService@User@@QEBA_NXZ`
- size: `306`
- prototype: `bool __fastcall(User *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18001bcc0`
- `0x18001c21c`

## callees

- `0x180008c4c`
- `0x18000cf80`
- `0x180018534`
- `0x18001ba50`
- `0x18001be88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ba73`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ba73`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001bb4d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001bb61`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001bb4d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001bb61`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18001bb37`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18001bb37`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall User::IsLocalService(User *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbx
  User *v3; // rcx
  int v4; // edi
  bool v5; // di
  void **pExceptionObject; // [rsp+20h] [rbp-40h] BYREF
  char v8; // [rsp+28h] [rbp-38h]
  char *v9; // [rsp+30h] [rbp-30h]
  __int64 v10; // [rsp+38h] [rbp-28h]
  __int64 v11; // [rsp+40h] [rbp-20h]
  int v12; // [rsp+48h] [rbp-18h]
  __int64 v13; // [rsp+4Ch] [rbp-14h]
  PSID pSid; // [rsp+70h] [rbp+10h] BYREF
  LPCRITICAL_SECTION v15; // [rsp+78h] [rbp+18h]

  v2 = User::s_cs;
  v15 = User::s_cs;
  EnterCriticalSection(User::s_cs);
  if ( !*(_QWORD *)this || User::IsAlias(this) )
  {
    LeaveCriticalSection(v2);
    return 0;
  }
  else
  {
    pSid = 0;
    v4 = User::LookupSid(v3, &pSid);
    if ( v4 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          29,
          WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids,
          (unsigned int)v4);
      }
      v8 = 0;
      pExceptionObject = &wmi::GenericException::`vftable';
      v9 = byte_180052608;
      v10 = 0;
      v11 = 0;
      v12 = v4;
      v13 = -1;
      throw (wmi::GenericException *)&pExceptionObject;
    }
    v5 = IsWellKnownSid(pSid, WinLocalServiceSid);
    LeaveCriticalSection(v2);
    return v5;
  }
}

```

## disassembly

```asm
0x18001ba50  mov     [rsp-8+arg_10], rbx
0x18001ba55  mov     [rsp-8+arg_18], rdi
0x18001ba5a  push    rbp
0x18001ba5b  mov     rbp, rsp
0x18001ba5e  sub     rsp, 60h
0x18001ba62  mov     rdi, rcx
0x18001ba65  mov     rbx, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x18001ba6c  mov     [rbp+arg_8], rbx
0x18001ba70  mov     rcx, rbx; lpCriticalSection
0x18001ba73  call    cs:__imp_EnterCriticalSection
0x18001ba7a  nop     dword ptr [rax+rax+00h]
0x18001ba7f  nop
0x18001ba80  cmp     qword ptr [rdi], 0
0x18001ba84  jz      loc_18001BB5E
0x18001ba8a  mov     rcx, rdi; this
0x18001ba8d  call    ?IsAlias@User@@QEBA_NXZ; User::IsAlias(void)
0x18001ba92  test    al, al
0x18001ba94  jnz     loc_18001BB5E
0x18001ba9a  mov     [rbp+pSid], 0
0x18001baa2  lea     rdx, [rbp+pSid]; void **
0x18001baa6  call    ?LookupSid@User@@QEBAJAEAPEAX@Z; User::LookupSid(void * &)
0x18001baab  mov     edi, eax
0x18001baad  test    eax, eax
0x18001baaf  jns     short loc_18001BB2E
0x18001bab1  lea     rax, WPP_GLOBAL_Control
0x18001bab8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001babf  cmp     rcx, rax
0x18001bac2  jz      short loc_18001BAE8
0x18001bac4  test    byte ptr [rcx+1Ch], 80h
0x18001bac8  jz      short loc_18001BAE8
0x18001baca  cmp     byte ptr [rcx+19h], 2
0x18001bace  jb      short loc_18001BAE8
0x18001bad0  mov     edx, 1Dh
0x18001bad5  mov     r9d, edi
0x18001bad8  lea     r8, WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids
0x18001badf  mov     rcx, [rcx+10h]
0x18001bae3  call    WPP_SF_d
0x18001bae8  mov     [rbp+var_38], 0
0x18001baec  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18001baf3  mov     [rbp+pExceptionObject], rax
0x18001baf7  lea     rax, byte_180052608
0x18001bafe  mov     [rbp+var_30], rax
0x18001bb02  mov     [rbp+var_28], 0
0x18001bb0a  mov     [rbp+var_20], 0
0x18001bb12  mov     [rbp+var_18], edi
0x18001bb15  mov     [rbp+var_14], 0FFFFFFFFFFFFFFFFh
0x18001bb1d  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18001bb24  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001bb28  call    _CxxThrowException_0
0x18001bb2e  mov     edx, 17h; WellKnownSidType
0x18001bb33  mov     rcx, [rbp+pSid]; pSid
0x18001bb37  call    cs:__imp_IsWellKnownSid
0x18001bb3e  nop     dword ptr [rax+rax+00h]
0x18001bb43  nop
0x18001bb44  test    eax, eax
0x18001bb46  setnz   dil
0x18001bb4a  mov     rcx, rbx; lpCriticalSection
0x18001bb4d  call    cs:__imp_LeaveCriticalSection
0x18001bb54  nop     dword ptr [rax+rax+00h]
0x18001bb59  mov     al, dil
0x18001bb5c  jmp     short loc_18001BB6F
0x18001bb5e  mov     rcx, rbx; lpCriticalSection
0x18001bb61  call    cs:__imp_LeaveCriticalSection
0x18001bb68  nop     dword ptr [rax+rax+00h]
0x18001bb6d  xor     al, al
0x18001bb6f  lea     r11, [rsp+60h+var_s0]
0x18001bb74  mov     rbx, [r11+20h]
0x18001bb78  mov     rdi, [r11+28h]
0x18001bb7c  mov     rsp, r11
0x18001bb7f  pop     rbp
0x18001bb80  retn
```
