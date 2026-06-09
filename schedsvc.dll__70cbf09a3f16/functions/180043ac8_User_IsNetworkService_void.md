# User::IsNetworkService(void)

- ea: `0x180043ac8`
- end: `0x180043bdf`
- name: `?IsNetworkService@User@@QEBA_NXZ`
- size: `279`
- prototype: `bool __fastcall(User *__hidden this)`
- caller_count: `5`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18001233c`
- `0x18001239c`
- `0x1800123e0`
- `0x18002c1b0`
- `0x180050e14`

## callees

- `0x180042fa4`
- `0x180043ac8`
- `0x180054084`
- `0x18005790c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180043bb7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180043bc5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180043bb7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180043bc5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180043aeb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180043aeb`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x180043ba7`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x180043ba7`

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
      v8 = &qword_1800A4718;
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
0x180043ac8  mov     [rsp-8+arg_10], rbx
0x180043acd  mov     [rsp-8+arg_18], rdi
0x180043ad2  push    rbp
0x180043ad3  mov     rbp, rsp
0x180043ad6  sub     rsp, 60h
0x180043ada  mov     rdi, rcx
0x180043add  mov     rbx, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x180043ae4  mov     [rbp+arg_8], rbx
0x180043ae8  mov     rcx, rbx; lpCriticalSection
0x180043aeb  call    cs:__imp_EnterCriticalSection
0x180043af1  nop
0x180043af2  mov     rax, [rdi]
0x180043af5  test    rax, rax
0x180043af8  jz      loc_180043BC2
0x180043afe  cmp     byte ptr [rax], 0
0x180043b01  jnz     loc_180043BC2
0x180043b07  mov     [rbp+pSid], 0
0x180043b0f  lea     rdx, [rbp+pSid]; void **
0x180043b13  mov     rcx, rdi; this
0x180043b16  call    ?LookupSid@User@@QEBAJAEAPEAX@Z; User::LookupSid(void * &)
0x180043b1b  mov     edi, eax
0x180043b1d  test    eax, eax
0x180043b1f  jns     short loc_180043B9E
0x180043b21  lea     rax, WPP_GLOBAL_Control
0x180043b28  mov     rcx, cs:WPP_GLOBAL_Control
0x180043b2f  cmp     rcx, rax
0x180043b32  jz      short loc_180043B58
0x180043b34  test    byte ptr [rcx+1Ch], 80h
0x180043b38  jz      short loc_180043B58
0x180043b3a  cmp     byte ptr [rcx+19h], 2
0x180043b3e  jb      short loc_180043B58
0x180043b40  mov     edx, 1Eh
0x180043b45  mov     r9d, edi
0x180043b48  lea     r8, WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids
0x180043b4f  mov     rcx, [rcx+10h]
0x180043b53  call    WPP_SF_d
0x180043b58  mov     [rbp+var_38], 0
0x180043b5c  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180043b63  mov     [rbp+pExceptionObject], rax
0x180043b67  lea     rax, qword_1800A4718
0x180043b6e  mov     [rbp+var_30], rax
0x180043b72  mov     [rbp+var_28], 0
0x180043b7a  mov     [rbp+var_20], 0
0x180043b82  mov     [rbp+var_18], edi
0x180043b85  mov     [rbp+var_14], 0FFFFFFFFFFFFFFFFh
0x180043b8d  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180043b94  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180043b98  call    _CxxThrowException_0
0x180043b9e  mov     edx, 18h; WellKnownSidType
0x180043ba3  mov     rcx, [rbp+pSid]; pSid
0x180043ba7  call    cs:__imp_IsWellKnownSid
0x180043bad  nop
0x180043bae  test    eax, eax
0x180043bb0  setnz   dil
0x180043bb4  mov     rcx, rbx; lpCriticalSection
0x180043bb7  call    cs:__imp_LeaveCriticalSection
0x180043bbd  mov     al, dil
0x180043bc0  jmp     short loc_180043BCD
0x180043bc2  mov     rcx, rbx; lpCriticalSection
0x180043bc5  call    cs:__imp_LeaveCriticalSection
0x180043bcb  xor     al, al
0x180043bcd  lea     r11, [rsp+60h+var_s0]
0x180043bd2  mov     rbx, [r11+20h]
0x180043bd6  mov     rdi, [r11+28h]
0x180043bda  mov     rsp, r11
0x180043bdd  pop     rbp
0x180043bde  retn
```
