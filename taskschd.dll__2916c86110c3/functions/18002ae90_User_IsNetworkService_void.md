# User::IsNetworkService(void)

- ea: `0x18002ae90`
- end: `0x18002afa8`
- name: `?IsNetworkService@User@@QEBA_NXZ`
- size: `280`
- prototype: `bool __fastcall(User *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18002ad84`
- `0x180037fbc`

## callees

- `0x180008e40`
- `0x18002ae90`
- `0x18003b51c`
- `0x18004e5c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002af80`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002af8e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002af80`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002af8e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002aeb1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002aeb1`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18002af70`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18002af70`

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
        v10 = &qword_180077320;
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
0x18002ae90  mov     [rsp+arg_8], rbx
0x18002ae95  mov     [rsp+arg_10], rsi
0x18002ae9a  push    rdi
0x18002ae9b  sub     rsp, 60h
0x18002ae9f  mov     rsi, rcx
0x18002aea2  mov     rbx, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x18002aea9  mov     [rsp+68h+arg_0], rbx
0x18002aeae  mov     rcx, rbx; lpCriticalSection
0x18002aeb1  call    cs:__imp_EnterCriticalSection
0x18002aeb7  nop
0x18002aeb8  mov     rax, [rsi]
0x18002aebb  test    rax, rax
0x18002aebe  jz      loc_18002AF8B
0x18002aec4  cmp     byte ptr [rax], 0
0x18002aec7  jnz     loc_18002AF8B
0x18002aecd  cmp     qword ptr [rax+20h], 0
0x18002aed2  jnz     loc_18002AF64
0x18002aed8  mov     rcx, rsi; this
0x18002aedb  call    ?UpdateEntry@User@@AEBAJXZ; User::UpdateEntry(void)
0x18002aee0  mov     edi, eax
0x18002aee2  test    eax, eax
0x18002aee4  jns     short loc_18002AF64
0x18002aee6  lea     rax, WPP_GLOBAL_Control
0x18002aeed  mov     rcx, cs:WPP_GLOBAL_Control
0x18002aef4  cmp     rcx, rax
0x18002aef7  jz      short loc_18002AF16
0x18002aef9  test    byte ptr [rcx+1Ch], 80h
0x18002aefd  jz      short loc_18002AF16
0x18002aeff  cmp     byte ptr [rcx+19h], 2
0x18002af03  jb      short loc_18002AF16
0x18002af05  mov     edx, 1Eh
0x18002af0a  mov     r9d, edi
0x18002af0d  mov     rcx, [rcx+10h]
0x18002af11  call    WPP_SF_d
0x18002af16  mov     [rsp+68h+var_40], 0
0x18002af1b  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18002af22  mov     [rsp+68h+pExceptionObject], rax
0x18002af27  lea     rax, qword_180077320
0x18002af2e  mov     [rsp+68h+var_38], rax
0x18002af33  mov     [rsp+68h+var_30], 0
0x18002af3c  mov     [rsp+68h+var_28], 0
0x18002af45  mov     [rsp+68h+var_20], edi
0x18002af49  mov     [rsp+68h+var_1C], 0FFFFFFFFFFFFFFFFh
0x18002af52  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18002af59  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18002af5e  call    _CxxThrowException_0
0x18002af64  mov     rax, [rsi]
0x18002af67  mov     edx, 18h; WellKnownSidType
0x18002af6c  mov     rcx, [rax+20h]; pSid
0x18002af70  call    cs:__imp_IsWellKnownSid
0x18002af76  nop
0x18002af77  test    eax, eax
0x18002af79  setnz   dil
0x18002af7d  mov     rcx, rbx; lpCriticalSection
0x18002af80  call    cs:__imp_LeaveCriticalSection
0x18002af86  mov     al, dil
0x18002af89  jmp     short loc_18002AF96
0x18002af8b  mov     rcx, rbx; lpCriticalSection
0x18002af8e  call    cs:__imp_LeaveCriticalSection
0x18002af94  xor     al, al
0x18002af96  lea     r11, [rsp+68h+var_8]
0x18002af9b  mov     rbx, [r11+18h]
0x18002af9f  mov     rsi, [r11+20h]
0x18002afa3  mov     rsp, r11
0x18002afa6  pop     rdi
0x18002afa7  retn
```
