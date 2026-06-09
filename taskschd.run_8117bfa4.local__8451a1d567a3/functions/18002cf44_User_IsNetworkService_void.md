# User::IsNetworkService(void)

- ea: `0x18002cf44`
- end: `0x18002d075`
- name: `?IsNetworkService@User@@QEBA_NXZ`
- size: `305`
- prototype: `bool __fastcall(User *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18002ce24`
- `0x18003b048`

## callees

- `0x180009280`
- `0x18002cf44`
- `0x18003e88c`
- `0x180052284`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002d040`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002d054`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002d040`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002d054`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002cf65`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002cf65`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18002d02a`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18002d02a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall User::IsNetworkService(User *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbx
  __int64 v3; // rax
  int updated; // edi
  __int64 v5; // r8
  bool v6; // di
  void **pExceptionObject; // [rsp+20h] [rbp-48h] BYREF
  char v9; // [rsp+28h] [rbp-40h]
  __int64 *v10; // [rsp+30h] [rbp-38h]
  __int64 v11; // [rsp+38h] [rbp-30h]
  __int64 v12; // [rsp+40h] [rbp-28h]
  int v13; // [rsp+48h] [rbp-20h]
  __int64 v14; // [rsp+4Ch] [rbp-1Ch]

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
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, v5, (unsigned int)updated);
        }
        v9 = 0;
        pExceptionObject = &wmi::GenericException::`vftable';
        v10 = &qword_18007B2F0;
        v11 = 0;
        v12 = 0;
        v13 = updated;
        v14 = -1;
        throw (wmi::GenericException *)&pExceptionObject;
      }
    }
    v6 = IsWellKnownSid(*(PSID *)(*(_QWORD *)this + 32LL), WinNetworkServiceSid);
    LeaveCriticalSection(v2);
    return v6;
  }
}

```

## disassembly

```asm
0x18002cf44  mov     [rsp+arg_8], rbx
0x18002cf49  mov     [rsp+arg_10], rsi
0x18002cf4e  push    rdi
0x18002cf4f  sub     rsp, 60h
0x18002cf53  mov     rsi, rcx
0x18002cf56  mov     rbx, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x18002cf5d  mov     [rsp+68h+arg_0], rbx
0x18002cf62  mov     rcx, rbx; lpCriticalSection
0x18002cf65  call    cs:__imp_EnterCriticalSection
0x18002cf6c  nop     dword ptr [rax+rax+00h]
0x18002cf71  nop
0x18002cf72  mov     rax, [rsi]
0x18002cf75  test    rax, rax
0x18002cf78  jz      loc_18002D051
0x18002cf7e  cmp     byte ptr [rax], 0
0x18002cf81  jnz     loc_18002D051
0x18002cf87  cmp     qword ptr [rax+20h], 0
0x18002cf8c  jnz     loc_18002D01E
0x18002cf92  mov     rcx, rsi; this
0x18002cf95  call    ?UpdateEntry@User@@AEBAJXZ; User::UpdateEntry(void)
0x18002cf9a  mov     edi, eax
0x18002cf9c  test    eax, eax
0x18002cf9e  jns     short loc_18002D01E
0x18002cfa0  lea     rax, WPP_GLOBAL_Control
0x18002cfa7  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cfae  cmp     rcx, rax
0x18002cfb1  jz      short loc_18002CFD0
0x18002cfb3  test    byte ptr [rcx+1Ch], 80h
0x18002cfb7  jz      short loc_18002CFD0
0x18002cfb9  cmp     byte ptr [rcx+19h], 2
0x18002cfbd  jb      short loc_18002CFD0
0x18002cfbf  mov     edx, 1Eh
0x18002cfc4  mov     r9d, edi
0x18002cfc7  mov     rcx, [rcx+10h]
0x18002cfcb  call    WPP_SF_d
0x18002cfd0  mov     [rsp+68h+var_40], 0
0x18002cfd5  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18002cfdc  mov     [rsp+68h+pExceptionObject], rax
0x18002cfe1  lea     rax, qword_18007B2F0
0x18002cfe8  mov     [rsp+68h+var_38], rax
0x18002cfed  mov     [rsp+68h+var_30], 0
0x18002cff6  mov     [rsp+68h+var_28], 0
0x18002cfff  mov     [rsp+68h+var_20], edi
0x18002d003  mov     [rsp+68h+var_1C], 0FFFFFFFFFFFFFFFFh
0x18002d00c  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18002d013  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18002d018  call    _CxxThrowException_0
0x18002d01e  mov     rax, [rsi]
0x18002d021  mov     edx, 18h; WellKnownSidType
0x18002d026  mov     rcx, [rax+20h]; pSid
0x18002d02a  call    cs:__imp_IsWellKnownSid
0x18002d031  nop     dword ptr [rax+rax+00h]
0x18002d036  nop
0x18002d037  test    eax, eax
0x18002d039  setnz   dil
0x18002d03d  mov     rcx, rbx; lpCriticalSection
0x18002d040  call    cs:__imp_LeaveCriticalSection
0x18002d047  nop     dword ptr [rax+rax+00h]
0x18002d04c  mov     al, dil
0x18002d04f  jmp     short loc_18002D062
0x18002d051  mov     rcx, rbx; lpCriticalSection
0x18002d054  call    cs:__imp_LeaveCriticalSection
0x18002d05b  nop     dword ptr [rax+rax+00h]
0x18002d060  xor     al, al
0x18002d062  lea     r11, [rsp+68h+var_8]
0x18002d067  mov     rbx, [r11+18h]
0x18002d06b  mov     rsi, [r11+20h]
0x18002d06f  mov     rsp, r11
0x18002d072  pop     rdi
0x18002d073  retn
```
