# User::IsLocalService(void)

- ea: `0x18002d208`
- end: `0x18002d32d`
- name: `?IsLocalService@User@@QEBA_NXZ`
- size: `293`
- prototype: `bool __fastcall(User *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18002ce24`
- `0x18003b048`

## callees

- `0x180009280`
- `0x18002d208`
- `0x18003e88c`
- `0x180052284`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002d246`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002d290`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002d246`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002d290`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002d229`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002d229`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18002d27a`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18002d27a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall User::IsLocalService(User *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbx
  __int64 v3; // rax
  bool v5; // di
  int updated; // edi
  __int64 v7; // r8
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
  if ( *(_QWORD *)this && !*(_BYTE *)v3 )
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
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, v7, (unsigned int)updated);
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
    v5 = IsWellKnownSid(*(PSID *)(*(_QWORD *)this + 32LL), WinLocalServiceSid);
    LeaveCriticalSection(v2);
    return v5;
  }
  else
  {
    LeaveCriticalSection(v2);
    return 0;
  }
}

```

## disassembly

```asm
0x18002d208  mov     [rsp+arg_8], rbx
0x18002d20d  mov     [rsp+arg_10], rsi
0x18002d212  push    rdi
0x18002d213  sub     rsp, 60h
0x18002d217  mov     rsi, rcx
0x18002d21a  mov     rbx, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x18002d221  mov     [rsp+68h+arg_0], rbx
0x18002d226  mov     rcx, rbx; lpCriticalSection
0x18002d229  call    cs:__imp_EnterCriticalSection
0x18002d230  nop     dword ptr [rax+rax+00h]
0x18002d235  nop
0x18002d236  mov     rax, [rsi]
0x18002d239  test    rax, rax
0x18002d23c  jz      short loc_18002D243
0x18002d23e  cmp     byte ptr [rax], 0
0x18002d241  jz      short loc_18002D267
0x18002d243  mov     rcx, rbx; lpCriticalSection
0x18002d246  call    cs:__imp_LeaveCriticalSection
0x18002d24d  nop     dword ptr [rax+rax+00h]
0x18002d252  xor     al, al
0x18002d254  lea     r11, [rsp+68h+var_8]
0x18002d259  mov     rbx, [r11+18h]
0x18002d25d  mov     rsi, [r11+20h]
0x18002d261  mov     rsp, r11
0x18002d264  pop     rdi
0x18002d265  retn
0x18002d267  cmp     qword ptr [rax+20h], 0
0x18002d26c  jz      short loc_18002D2A1
0x18002d26e  mov     rax, [rsi]
0x18002d271  mov     edx, 17h; WellKnownSidType
0x18002d276  mov     rcx, [rax+20h]; pSid
0x18002d27a  call    cs:__imp_IsWellKnownSid
0x18002d281  nop     dword ptr [rax+rax+00h]
0x18002d286  nop
0x18002d287  test    eax, eax
0x18002d289  setnz   dil
0x18002d28d  mov     rcx, rbx; lpCriticalSection
0x18002d290  call    cs:__imp_LeaveCriticalSection
0x18002d297  nop     dword ptr [rax+rax+00h]
0x18002d29c  mov     al, dil
0x18002d29f  jmp     short loc_18002D254
0x18002d2a1  mov     rcx, rsi; this
0x18002d2a4  call    ?UpdateEntry@User@@AEBAJXZ; User::UpdateEntry(void)
0x18002d2a9  mov     edi, eax
0x18002d2ab  test    eax, eax
0x18002d2ad  jns     short loc_18002D26E
0x18002d2af  lea     rax, WPP_GLOBAL_Control
0x18002d2b6  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d2bd  cmp     rcx, rax
0x18002d2c0  jz      short loc_18002D2DF
0x18002d2c2  test    byte ptr [rcx+1Ch], 80h
0x18002d2c6  jz      short loc_18002D2DF
0x18002d2c8  cmp     byte ptr [rcx+19h], 2
0x18002d2cc  jb      short loc_18002D2DF
0x18002d2ce  mov     edx, 1Dh
0x18002d2d3  mov     r9d, edi
0x18002d2d6  mov     rcx, [rcx+10h]
0x18002d2da  call    WPP_SF_d
0x18002d2df  mov     [rsp+68h+var_40], 0
0x18002d2e4  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18002d2eb  mov     [rsp+68h+pExceptionObject], rax
0x18002d2f0  lea     rax, qword_18007B2F0
0x18002d2f7  mov     [rsp+68h+var_38], rax
0x18002d2fc  mov     [rsp+68h+var_30], 0
0x18002d305  mov     [rsp+68h+var_28], 0
0x18002d30e  mov     [rsp+68h+var_20], edi
0x18002d312  mov     [rsp+68h+var_1C], 0FFFFFFFFFFFFFFFFh
0x18002d31b  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18002d322  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18002d327  call    _CxxThrowException_0
```
