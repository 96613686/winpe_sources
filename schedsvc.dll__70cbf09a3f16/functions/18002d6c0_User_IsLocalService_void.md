# User::IsLocalService(void)

- ea: `0x18002d6c0`
- end: `0x18002d7e3`
- name: `?IsLocalService@User@@QEBA_NXZ`
- size: `291`
- prototype: `bool __fastcall(User *__hidden this)`
- caller_count: `5`
- callee_count: `4`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18001233c`
- `0x18001239c`
- `0x1800123e0`
- `0x18002c1b0`
- `0x180050e14`

## callees

- `0x18002d6c0`
- `0x180054084`
- `0x18005790c`
- `0x1800679e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002d7bb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002d7c9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002d7bb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002d7c9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002d6e1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002d6e1`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18002d7ab`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18002d7ab`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall User::IsLocalService(User *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbx
  __int64 v3; // rax
  int updated; // edi
  bool v5; // di
  void **pExceptionObject; // [rsp+20h] [rbp-48h] BYREF
  char v8; // [rsp+28h] [rbp-40h]
  const unsigned __int16 *v9; // [rsp+30h] [rbp-38h]
  __int64 v10; // [rsp+38h] [rbp-30h]
  __int64 v11; // [rsp+40h] [rbp-28h]
  int v12; // [rsp+48h] [rbp-20h]
  __int64 v13; // [rsp+4Ch] [rbp-1Ch]

  v2 = User::s_cs;
  EnterCriticalSection(User::s_cs);
  v3 = *(_QWORD *)this;
  if ( !*(_QWORD *)this || *(_BYTE *)v3 )
  {
    LeaveCriticalSection(v2);
    return 0;
  }
  else
  {
    if ( !*(_QWORD *)(v3 + 32) )
    {
      updated = User::UpdateEntry(this);
      if ( updated < 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && *((char *)WPP_GLOBAL_Control + 28) < 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            29,
            WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids,
            (unsigned int)updated);
        }
        v8 = 0;
        pExceptionObject = &wmi::GenericException::`vftable';
        v9 = &qword_1800A4718;
        v10 = 0;
        v11 = 0;
        v12 = updated;
        v13 = -1;
        throw (wmi::GenericException *)&pExceptionObject;
      }
    }
    v5 = IsWellKnownSid(*(PSID *)(*(_QWORD *)this + 32LL), WinLocalServiceSid);
    LeaveCriticalSection(v2);
    return v5;
  }
}

```

## disassembly

```asm
0x18002d6c0  mov     [rsp+arg_8], rbx
0x18002d6c5  mov     [rsp+arg_10], rsi
0x18002d6ca  push    rdi
0x18002d6cb  sub     rsp, 60h
0x18002d6cf  mov     rsi, rcx
0x18002d6d2  mov     rbx, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x18002d6d9  mov     [rsp+68h+arg_0], rbx
0x18002d6de  mov     rcx, rbx; lpCriticalSection
0x18002d6e1  call    cs:__imp_EnterCriticalSection
0x18002d6e7  nop
0x18002d6e8  mov     rax, [rsi]
0x18002d6eb  test    rax, rax
0x18002d6ee  jz      loc_18002D7C6
0x18002d6f4  cmp     byte ptr [rax], 0
0x18002d6f7  jnz     loc_18002D7C6
0x18002d6fd  cmp     qword ptr [rax+20h], 0
0x18002d702  jnz     loc_18002D79F
0x18002d708  mov     rcx, rsi; this
0x18002d70b  call    ?UpdateEntry@User@@AEBAJXZ; User::UpdateEntry(void)
0x18002d710  mov     edi, eax
0x18002d712  test    eax, eax
0x18002d714  jns     loc_18002D79F
0x18002d71a  lea     rax, WPP_GLOBAL_Control
0x18002d721  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d728  cmp     rcx, rax
0x18002d72b  jz      short loc_18002D751
0x18002d72d  test    byte ptr [rcx+1Ch], 80h
0x18002d731  jz      short loc_18002D751
0x18002d733  cmp     byte ptr [rcx+19h], 2
0x18002d737  jb      short loc_18002D751
0x18002d739  mov     edx, 1Dh
0x18002d73e  mov     r9d, edi
0x18002d741  lea     r8, WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids
0x18002d748  mov     rcx, [rcx+10h]
0x18002d74c  call    WPP_SF_d
0x18002d751  mov     [rsp+68h+var_40], 0
0x18002d756  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18002d75d  mov     [rsp+68h+pExceptionObject], rax
0x18002d762  lea     rax, qword_1800A4718
0x18002d769  mov     [rsp+68h+var_38], rax
0x18002d76e  mov     [rsp+68h+var_30], 0
0x18002d777  mov     [rsp+68h+var_28], 0
0x18002d780  mov     [rsp+68h+var_20], edi
0x18002d784  mov     [rsp+68h+var_1C], 0FFFFFFFFFFFFFFFFh
0x18002d78d  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18002d794  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18002d799  call    _CxxThrowException_0
0x18002d79f  mov     rax, [rsi]
0x18002d7a2  mov     edx, 17h; WellKnownSidType
0x18002d7a7  mov     rcx, [rax+20h]; pSid
0x18002d7ab  call    cs:__imp_IsWellKnownSid
0x18002d7b1  nop
0x18002d7b2  test    eax, eax
0x18002d7b4  setnz   dil
0x18002d7b8  mov     rcx, rbx; lpCriticalSection
0x18002d7bb  call    cs:__imp_LeaveCriticalSection
0x18002d7c1  mov     al, dil
0x18002d7c4  jmp     short loc_18002D7D1
0x18002d7c6  mov     rcx, rbx; lpCriticalSection
0x18002d7c9  call    cs:__imp_LeaveCriticalSection
0x18002d7cf  xor     al, al
0x18002d7d1  lea     r11, [rsp+68h+var_8]
0x18002d7d6  mov     rbx, [r11+18h]
0x18002d7da  mov     rsi, [r11+20h]
0x18002d7de  mov     rsp, r11
0x18002d7e1  pop     rdi
0x18002d7e2  retn
```
