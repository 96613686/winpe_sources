# User::IsLocalService(void)

- ea: `0x18001a6e8`
- end: `0x18001a7ff`
- name: `?IsLocalService@User@@QEBA_NXZ`
- size: `279`
- prototype: `bool __fastcall(User *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18001a928`
- `0x18001ad80`

## callees

- `0x18000878c`
- `0x18000c760`
- `0x18001a6e8`
- `0x18001aacc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a70b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a70b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a7d7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a7e5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a7d7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a7e5`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18001a7c7`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18001a7c7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall User::IsLocalService(User *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbx
  int v3; // edi
  bool v4; // di
  void **pExceptionObject; // [rsp+20h] [rbp-40h] BYREF
  char v7; // [rsp+28h] [rbp-38h]
  char *v8; // [rsp+30h] [rbp-30h]
  __int64 v9; // [rsp+38h] [rbp-28h]
  __int64 v10; // [rsp+40h] [rbp-20h]
  int v11; // [rsp+48h] [rbp-18h]
  __int64 v12; // [rsp+4Ch] [rbp-14h]
  PSID pSid; // [rsp+70h] [rbp+10h] BYREF
  LPCRITICAL_SECTION v14; // [rsp+78h] [rbp+18h]

  v2 = User::s_cs;
  v14 = User::s_cs;
  EnterCriticalSection(User::s_cs);
  if ( !*(_QWORD *)this || **(_BYTE **)this )
  {
    LeaveCriticalSection(v2);
    return 0;
  }
  else
  {
    pSid = 0;
    v3 = User::LookupSid(this, &pSid);
    if ( v3 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          29,
          WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids,
          (unsigned int)v3);
      }
      v7 = 0;
      pExceptionObject = &wmi::GenericException::`vftable';
      v8 = byte_1800505F8;
      v9 = 0;
      v10 = 0;
      v11 = v3;
      v12 = -1;
      throw (wmi::GenericException *)&pExceptionObject;
    }
    v4 = IsWellKnownSid(pSid, WinLocalServiceSid);
    LeaveCriticalSection(v2);
    return v4;
  }
}

```

## disassembly

```asm
0x18001a6e8  mov     [rsp-8+arg_10], rbx
0x18001a6ed  mov     [rsp-8+arg_18], rdi
0x18001a6f2  push    rbp
0x18001a6f3  mov     rbp, rsp
0x18001a6f6  sub     rsp, 60h
0x18001a6fa  mov     rdi, rcx
0x18001a6fd  mov     rbx, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x18001a704  mov     [rbp+arg_8], rbx
0x18001a708  mov     rcx, rbx; lpCriticalSection
0x18001a70b  call    cs:__imp_EnterCriticalSection
0x18001a711  nop
0x18001a712  mov     rax, [rdi]
0x18001a715  test    rax, rax
0x18001a718  jz      loc_18001A7E2
0x18001a71e  cmp     byte ptr [rax], 0
0x18001a721  jnz     loc_18001A7E2
0x18001a727  mov     [rbp+pSid], 0
0x18001a72f  lea     rdx, [rbp+pSid]; void **
0x18001a733  mov     rcx, rdi; this
0x18001a736  call    ?LookupSid@User@@QEBAJAEAPEAX@Z; User::LookupSid(void * &)
0x18001a73b  mov     edi, eax
0x18001a73d  test    eax, eax
0x18001a73f  jns     short loc_18001A7BE
0x18001a741  lea     rax, WPP_GLOBAL_Control
0x18001a748  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a74f  cmp     rcx, rax
0x18001a752  jz      short loc_18001A778
0x18001a754  test    byte ptr [rcx+1Ch], 80h
0x18001a758  jz      short loc_18001A778
0x18001a75a  cmp     byte ptr [rcx+19h], 2
0x18001a75e  jb      short loc_18001A778
0x18001a760  mov     edx, 1Dh
0x18001a765  mov     r9d, edi
0x18001a768  lea     r8, WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids
0x18001a76f  mov     rcx, [rcx+10h]
0x18001a773  call    WPP_SF_d
0x18001a778  mov     [rbp+var_38], 0
0x18001a77c  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18001a783  mov     [rbp+pExceptionObject], rax
0x18001a787  lea     rax, byte_1800505F8
0x18001a78e  mov     [rbp+var_30], rax
0x18001a792  mov     [rbp+var_28], 0
0x18001a79a  mov     [rbp+var_20], 0
0x18001a7a2  mov     [rbp+var_18], edi
0x18001a7a5  mov     [rbp+var_14], 0FFFFFFFFFFFFFFFFh
0x18001a7ad  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18001a7b4  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001a7b8  call    _CxxThrowException_0
0x18001a7be  mov     edx, 17h; WellKnownSidType
0x18001a7c3  mov     rcx, [rbp+pSid]; pSid
0x18001a7c7  call    cs:__imp_IsWellKnownSid
0x18001a7cd  nop
0x18001a7ce  test    eax, eax
0x18001a7d0  setnz   dil
0x18001a7d4  mov     rcx, rbx; lpCriticalSection
0x18001a7d7  call    cs:__imp_LeaveCriticalSection
0x18001a7dd  mov     al, dil
0x18001a7e0  jmp     short loc_18001A7ED
0x18001a7e2  mov     rcx, rbx; lpCriticalSection
0x18001a7e5  call    cs:__imp_LeaveCriticalSection
0x18001a7eb  xor     al, al
0x18001a7ed  lea     r11, [rsp+60h+var_s0]
0x18001a7f2  mov     rbx, [r11+20h]
0x18001a7f6  mov     rdi, [r11+28h]
0x18001a7fa  mov     rsp, r11
0x18001a7fd  pop     rbp
0x18001a7fe  retn
```
