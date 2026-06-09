# User::IsServiceSid(void)

- ea: `0x18002eeec`
- end: `0x18002f037`
- name: `?IsServiceSid@User@@QEBA_NXZ`
- size: `331`
- prototype: `bool __fastcall(User *__hidden this)`
- caller_count: `4`
- callee_count: `4`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18001233c`
- `0x18001239c`
- `0x1800123e0`
- `0x18002f040`

## callees

- `0x18002eeec`
- `0x180054084`
- `0x18005790c`
- `0x1800679e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f025`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f025`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002ef09`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002ef09`
- `api-ms-win-security-base-l1-1-0!GetSidIdentifierAuthority` at `0x18002efc5`
- `api-ms-win-security-base-l1-1-0!GetSidIdentifierAuthority` at `0x18002efc5`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002eff5`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002eff5`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002f00a`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002f00a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall User::IsServiceSid(User *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbx
  __int64 v3; // rax
  int updated; // edi
  void *v5; // rdi
  PSID_IDENTIFIER_AUTHORITY SidIdentifierAuthority; // rax
  int v7; // ecx
  PUCHAR SidSubAuthorityCount; // rax
  PDWORD SidSubAuthority; // rax
  char v10; // di
  void **pExceptionObject; // [rsp+20h] [rbp-48h] BYREF
  char v13; // [rsp+28h] [rbp-40h]
  const unsigned __int16 *v14; // [rsp+30h] [rbp-38h]
  __int64 v15; // [rsp+38h] [rbp-30h]
  __int64 v16; // [rsp+40h] [rbp-28h]
  int v17; // [rsp+48h] [rbp-20h]
  __int64 v18; // [rsp+4Ch] [rbp-1Ch]

  v2 = User::s_cs;
  EnterCriticalSection(User::s_cs);
  v3 = *(_QWORD *)this;
  if ( !*(_QWORD *)this || *(_BYTE *)v3 )
    goto LABEL_19;
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
          31,
          WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids,
          (unsigned int)updated);
      }
      v13 = 0;
      pExceptionObject = &wmi::GenericException::`vftable';
      v14 = &qword_1800A4718;
      v15 = 0;
      v16 = 0;
      v17 = updated;
      v18 = -1;
      throw (wmi::GenericException *)&pExceptionObject;
    }
  }
  v5 = *(void **)(*(_QWORD *)this + 32LL);
  SidIdentifierAuthority = GetSidIdentifierAuthority(v5);
  if ( !SidIdentifierAuthority )
    goto LABEL_19;
  v7 = *(_DWORD *)SidIdentifierAuthority->Value;
  if ( !*(_DWORD *)SidIdentifierAuthority->Value )
    v7 = *(unsigned __int16 *)&SidIdentifierAuthority->Value[4] - 1280;
  if ( !v7
    && (SidSubAuthorityCount = GetSidSubAuthorityCount(v5)) != 0
    && *SidSubAuthorityCount == 6
    && (SidSubAuthority = GetSidSubAuthority(v5, 0)) != 0
    && *SidSubAuthority == 80 )
  {
    v10 = 1;
  }
  else
  {
LABEL_19:
    v10 = 0;
  }
  LeaveCriticalSection(v2);
  return v10;
}

```

## disassembly

```asm
0x18002eeec  push    rbp
0x18002eeee  push    rbx
0x18002eeef  push    rsi
0x18002eef0  push    rdi
0x18002eef1  mov     rbp, rsp
0x18002eef4  sub     rsp, 68h
0x18002eef8  mov     rsi, rcx
0x18002eefb  mov     rbx, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x18002ef02  mov     [rbp+arg_0], rbx
0x18002ef06  mov     rcx, rbx; lpCriticalSection
0x18002ef09  call    cs:__imp_EnterCriticalSection
0x18002ef0f  nop
0x18002ef10  mov     rax, [rsi]
0x18002ef13  test    rax, rax
0x18002ef16  jz      loc_18002F01F
0x18002ef1c  cmp     byte ptr [rax], 0
0x18002ef1f  jnz     loc_18002F01F
0x18002ef25  cmp     qword ptr [rax+20h], 0
0x18002ef2a  jnz     loc_18002EFBB
0x18002ef30  mov     rcx, rsi; this
0x18002ef33  call    ?UpdateEntry@User@@AEBAJXZ; User::UpdateEntry(void)
0x18002ef38  mov     edi, eax
0x18002ef3a  test    eax, eax
0x18002ef3c  jns     short loc_18002EFBB
0x18002ef3e  lea     rax, WPP_GLOBAL_Control
0x18002ef45  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ef4c  cmp     rcx, rax
0x18002ef4f  jz      short loc_18002EF75
0x18002ef51  test    byte ptr [rcx+1Ch], 80h
0x18002ef55  jz      short loc_18002EF75
0x18002ef57  cmp     byte ptr [rcx+19h], 2
0x18002ef5b  jb      short loc_18002EF75
0x18002ef5d  mov     edx, 1Fh
0x18002ef62  mov     r9d, edi
0x18002ef65  lea     r8, WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids
0x18002ef6c  mov     rcx, [rcx+10h]
0x18002ef70  call    WPP_SF_d
0x18002ef75  mov     [rbp+var_40], 0
0x18002ef79  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18002ef80  mov     [rbp+pExceptionObject], rax
0x18002ef84  lea     rax, qword_1800A4718
0x18002ef8b  mov     [rbp+var_38], rax
0x18002ef8f  mov     [rbp+var_30], 0
0x18002ef97  mov     [rbp+var_28], 0
0x18002ef9f  mov     [rbp+var_20], edi
0x18002efa2  mov     [rbp+var_1C], 0FFFFFFFFFFFFFFFFh
0x18002efaa  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18002efb1  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18002efb5  call    _CxxThrowException_0
0x18002efbb  mov     rax, [rsi]
0x18002efbe  mov     rdi, [rax+20h]
0x18002efc2  mov     rcx, rdi; pSid
0x18002efc5  call    cs:__imp_GetSidIdentifierAuthority
0x18002efcb  test    rax, rax
0x18002efce  jz      short loc_18002F01F
0x18002efd0  mov     dword ptr [rbp+arg_0], 0
0x18002efd7  mov     word ptr [rbp+arg_0+4], 500h
0x18002efdd  mov     ecx, [rax]
0x18002efdf  sub     ecx, dword ptr [rbp+arg_0]
0x18002efe2  jnz     short loc_18002EFEE
0x18002efe4  movzx   ecx, word ptr [rax+4]
0x18002efe8  movzx   eax, word ptr [rbp+arg_0+4]
0x18002efec  sub     ecx, eax
0x18002efee  test    ecx, ecx
0x18002eff0  jnz     short loc_18002F01F
0x18002eff2  mov     rcx, rdi; pSid
0x18002eff5  call    cs:__imp_GetSidSubAuthorityCount
0x18002effb  test    rax, rax
0x18002effe  jz      short loc_18002F01F
0x18002f000  cmp     byte ptr [rax], 6
0x18002f003  jnz     short loc_18002F01F
0x18002f005  xor     edx, edx; nSubAuthority
0x18002f007  mov     rcx, rdi; pSid
0x18002f00a  call    cs:__imp_GetSidSubAuthority
0x18002f010  test    rax, rax
0x18002f013  jz      short loc_18002F01F
0x18002f015  cmp     dword ptr [rax], 50h ; 'P'
0x18002f018  jnz     short loc_18002F01F
0x18002f01a  mov     dil, 1
0x18002f01d  jmp     short loc_18002F022
0x18002f01f  xor     dil, dil
0x18002f022  mov     rcx, rbx; lpCriticalSection
0x18002f025  call    cs:__imp_LeaveCriticalSection
0x18002f02b  mov     al, dil
0x18002f02e  add     rsp, 68h
0x18002f032  pop     rdi
0x18002f033  pop     rsi
0x18002f034  pop     rbx
0x18002f035  pop     rbp
0x18002f036  retn
```
