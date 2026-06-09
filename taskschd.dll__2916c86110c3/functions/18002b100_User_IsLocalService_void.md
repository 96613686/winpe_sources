# User::IsLocalService(void)

- ea: `0x18002b100`
- end: `0x18002b20c`
- name: `?IsLocalService@User@@QEBA_NXZ`
- size: `268`
- prototype: `bool __fastcall(User *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18002ad84`
- `0x180037fbc`

## callees

- `0x180008e40`
- `0x18002b100`
- `0x18003b51c`
- `0x18004e5c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002b138`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002b175`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002b138`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002b175`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002b121`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002b121`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18002b165`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18002b165`

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
        v10 = &qword_180077320;
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
0x18002b100  mov     [rsp+arg_8], rbx
0x18002b105  mov     [rsp+arg_10], rsi
0x18002b10a  push    rdi
0x18002b10b  sub     rsp, 60h
0x18002b10f  mov     rsi, rcx
0x18002b112  mov     rbx, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x18002b119  mov     [rsp+68h+arg_0], rbx
0x18002b11e  mov     rcx, rbx; lpCriticalSection
0x18002b121  call    cs:__imp_EnterCriticalSection
0x18002b127  nop
0x18002b128  mov     rax, [rsi]
0x18002b12b  test    rax, rax
0x18002b12e  jz      short loc_18002B135
0x18002b130  cmp     byte ptr [rax], 0
0x18002b133  jz      short loc_18002B152
0x18002b135  mov     rcx, rbx; lpCriticalSection
0x18002b138  call    cs:__imp_LeaveCriticalSection
0x18002b13e  xor     al, al
0x18002b140  lea     r11, [rsp+68h+var_8]
0x18002b145  mov     rbx, [r11+18h]
0x18002b149  mov     rsi, [r11+20h]
0x18002b14d  mov     rsp, r11
0x18002b150  pop     rdi
0x18002b151  retn
0x18002b152  cmp     qword ptr [rax+20h], 0
0x18002b157  jz      short loc_18002B180
0x18002b159  mov     rax, [rsi]
0x18002b15c  mov     edx, 17h; WellKnownSidType
0x18002b161  mov     rcx, [rax+20h]; pSid
0x18002b165  call    cs:__imp_IsWellKnownSid
0x18002b16b  nop
0x18002b16c  test    eax, eax
0x18002b16e  setnz   dil
0x18002b172  mov     rcx, rbx; lpCriticalSection
0x18002b175  call    cs:__imp_LeaveCriticalSection
0x18002b17b  mov     al, dil
0x18002b17e  jmp     short loc_18002B140
0x18002b180  mov     rcx, rsi; this
0x18002b183  call    ?UpdateEntry@User@@AEBAJXZ; User::UpdateEntry(void)
0x18002b188  mov     edi, eax
0x18002b18a  test    eax, eax
0x18002b18c  jns     short loc_18002B159
0x18002b18e  lea     rax, WPP_GLOBAL_Control
0x18002b195  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b19c  cmp     rcx, rax
0x18002b19f  jz      short loc_18002B1BE
0x18002b1a1  test    byte ptr [rcx+1Ch], 80h
0x18002b1a5  jz      short loc_18002B1BE
0x18002b1a7  cmp     byte ptr [rcx+19h], 2
0x18002b1ab  jb      short loc_18002B1BE
0x18002b1ad  mov     edx, 1Dh
0x18002b1b2  mov     r9d, edi
0x18002b1b5  mov     rcx, [rcx+10h]
0x18002b1b9  call    WPP_SF_d
0x18002b1be  mov     [rsp+68h+var_40], 0
0x18002b1c3  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18002b1ca  mov     [rsp+68h+pExceptionObject], rax
0x18002b1cf  lea     rax, qword_180077320
0x18002b1d6  mov     [rsp+68h+var_38], rax
0x18002b1db  mov     [rsp+68h+var_30], 0
0x18002b1e4  mov     [rsp+68h+var_28], 0
0x18002b1ed  mov     [rsp+68h+var_20], edi
0x18002b1f1  mov     [rsp+68h+var_1C], 0FFFFFFFFFFFFFFFFh
0x18002b1fa  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18002b201  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18002b206  call    _CxxThrowException_0
```
