# User::IsNetworkService(void)

- ea: `0x180045a14`
- end: `0x180045b44`
- name: `?IsNetworkService@User@@QEBA_NXZ`
- size: `304`
- prototype: `bool __fastcall(User *__hidden this)`
- caller_count: `5`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180003310`
- `0x180006a10`
- `0x180006a74`
- `0x180006ac0`
- `0x180053394`

## callees

- `0x180045120`
- `0x180045a14`
- `0x180056954`
- `0x18005a2bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045b0f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045b23`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045b0f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045b23`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180045a37`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180045a37`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x180045af9`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x180045af9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall User::IsNetworkService(User *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbx
  int v3; // edi
  bool v4; // di
  void **pExceptionObject; // [rsp+20h] [rbp-40h] BYREF
  char v7; // [rsp+28h] [rbp-38h]
  const unsigned __int16 *v8; // [rsp+30h] [rbp-30h]
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
          30,
          WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids,
          (unsigned int)v3);
      }
      v7 = 0;
      pExceptionObject = &wmi::GenericException::`vftable';
      v8 = &qword_1800A8718;
      v9 = 0;
      v10 = 0;
      v11 = v3;
      v12 = -1;
      throw (wmi::GenericException *)&pExceptionObject;
    }
    v4 = IsWellKnownSid(pSid, WinNetworkServiceSid);
    LeaveCriticalSection(v2);
    return v4;
  }
}

```

## disassembly

```asm
0x180045a14  mov     [rsp-8+arg_10], rbx
0x180045a19  mov     [rsp-8+arg_18], rdi
0x180045a1e  push    rbp
0x180045a1f  mov     rbp, rsp
0x180045a22  sub     rsp, 60h
0x180045a26  mov     rdi, rcx
0x180045a29  mov     rbx, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x180045a30  mov     [rbp+arg_8], rbx
0x180045a34  mov     rcx, rbx; lpCriticalSection
0x180045a37  call    cs:__imp_EnterCriticalSection
0x180045a3e  nop     dword ptr [rax+rax+00h]
0x180045a43  nop
0x180045a44  mov     rax, [rdi]
0x180045a47  test    rax, rax
0x180045a4a  jz      loc_180045B20
0x180045a50  cmp     byte ptr [rax], 0
0x180045a53  jnz     loc_180045B20
0x180045a59  mov     [rbp+pSid], 0
0x180045a61  lea     rdx, [rbp+pSid]; void **
0x180045a65  mov     rcx, rdi; this
0x180045a68  call    ?LookupSid@User@@QEBAJAEAPEAX@Z; User::LookupSid(void * &)
0x180045a6d  mov     edi, eax
0x180045a6f  test    eax, eax
0x180045a71  jns     short loc_180045AF0
0x180045a73  lea     rax, WPP_GLOBAL_Control
0x180045a7a  mov     rcx, cs:WPP_GLOBAL_Control
0x180045a81  cmp     rcx, rax
0x180045a84  jz      short loc_180045AAA
0x180045a86  test    byte ptr [rcx+1Ch], 80h
0x180045a8a  jz      short loc_180045AAA
0x180045a8c  cmp     byte ptr [rcx+19h], 2
0x180045a90  jb      short loc_180045AAA
0x180045a92  mov     edx, 1Eh
0x180045a97  mov     r9d, edi
0x180045a9a  lea     r8, WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids
0x180045aa1  mov     rcx, [rcx+10h]
0x180045aa5  call    WPP_SF_d
0x180045aaa  mov     [rbp+var_38], 0
0x180045aae  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180045ab5  mov     [rbp+pExceptionObject], rax
0x180045ab9  lea     rax, qword_1800A8718
0x180045ac0  mov     [rbp+var_30], rax
0x180045ac4  mov     [rbp+var_28], 0
0x180045acc  mov     [rbp+var_20], 0
0x180045ad4  mov     [rbp+var_18], edi
0x180045ad7  mov     [rbp+var_14], 0FFFFFFFFFFFFFFFFh
0x180045adf  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180045ae6  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180045aea  call    _CxxThrowException_0
0x180045af0  mov     edx, 18h; WellKnownSidType
0x180045af5  mov     rcx, [rbp+pSid]; pSid
0x180045af9  call    cs:__imp_IsWellKnownSid
0x180045b00  nop     dword ptr [rax+rax+00h]
0x180045b05  nop
0x180045b06  test    eax, eax
0x180045b08  setnz   dil
0x180045b0c  mov     rcx, rbx; lpCriticalSection
0x180045b0f  call    cs:__imp_LeaveCriticalSection
0x180045b16  nop     dword ptr [rax+rax+00h]
0x180045b1b  mov     al, dil
0x180045b1e  jmp     short loc_180045B31
0x180045b20  mov     rcx, rbx; lpCriticalSection
0x180045b23  call    cs:__imp_LeaveCriticalSection
0x180045b2a  nop     dword ptr [rax+rax+00h]
0x180045b2f  xor     al, al
0x180045b31  lea     r11, [rsp+60h+var_s0]
0x180045b36  mov     rbx, [r11+20h]
0x180045b3a  mov     rdi, [r11+28h]
0x180045b3e  mov     rsp, r11
0x180045b41  pop     rbp
0x180045b42  retn
```
