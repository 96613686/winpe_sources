# User::IsServiceSid(void)

- ea: `0x1800258cc`
- end: `0x180025a36`
- name: `?IsServiceSid@User@@QEBA_NXZ`
- size: `362`
- prototype: `bool __fastcall(User *__hidden this)`
- caller_count: `4`
- callee_count: `4`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180006a10`
- `0x180006a74`
- `0x180006ac0`
- `0x180025a3c`

## callees

- `0x1800258cc`
- `0x180056954`
- `0x18005a2bc`
- `0x18006acbc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025a1d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025a1d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800258e9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800258e9`
- `api-ms-win-security-base-l1-1-0!GetSidIdentifierAuthority` at `0x1800259ab`
- `api-ms-win-security-base-l1-1-0!GetSidIdentifierAuthority` at `0x1800259ab`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x1800259e1`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x1800259e1`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1800259fc`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1800259fc`

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
      v14 = &qword_1800A8718;
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
0x1800258cc  push    rbp
0x1800258ce  push    rbx
0x1800258cf  push    rsi
0x1800258d0  push    rdi
0x1800258d1  mov     rbp, rsp
0x1800258d4  sub     rsp, 68h
0x1800258d8  mov     rsi, rcx
0x1800258db  mov     rbx, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x1800258e2  mov     [rbp+arg_0], rbx
0x1800258e6  mov     rcx, rbx; lpCriticalSection
0x1800258e9  call    cs:__imp_EnterCriticalSection
0x1800258f0  nop     dword ptr [rax+rax+00h]
0x1800258f5  nop
0x1800258f6  mov     rax, [rsi]
0x1800258f9  test    rax, rax
0x1800258fc  jz      loc_180025A17
0x180025902  cmp     byte ptr [rax], 0
0x180025905  jnz     loc_180025A17
0x18002590b  cmp     qword ptr [rax+20h], 0
0x180025910  jnz     loc_1800259A1
0x180025916  mov     rcx, rsi; this
0x180025919  call    ?UpdateEntry@User@@AEBAJXZ; User::UpdateEntry(void)
0x18002591e  mov     edi, eax
0x180025920  test    eax, eax
0x180025922  jns     short loc_1800259A1
0x180025924  lea     rax, WPP_GLOBAL_Control
0x18002592b  mov     rcx, cs:WPP_GLOBAL_Control
0x180025932  cmp     rcx, rax
0x180025935  jz      short loc_18002595B
0x180025937  test    byte ptr [rcx+1Ch], 80h
0x18002593b  jz      short loc_18002595B
0x18002593d  cmp     byte ptr [rcx+19h], 2
0x180025941  jb      short loc_18002595B
0x180025943  mov     edx, 1Fh
0x180025948  mov     r9d, edi
0x18002594b  lea     r8, WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids
0x180025952  mov     rcx, [rcx+10h]
0x180025956  call    WPP_SF_d
0x18002595b  mov     [rbp+var_40], 0
0x18002595f  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180025966  mov     [rbp+pExceptionObject], rax
0x18002596a  lea     rax, qword_1800A8718
0x180025971  mov     [rbp+var_38], rax
0x180025975  mov     [rbp+var_30], 0
0x18002597d  mov     [rbp+var_28], 0
0x180025985  mov     [rbp+var_20], edi
0x180025988  mov     [rbp+var_1C], 0FFFFFFFFFFFFFFFFh
0x180025990  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180025997  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18002599b  call    _CxxThrowException_0
0x1800259a1  mov     rax, [rsi]
0x1800259a4  mov     rdi, [rax+20h]
0x1800259a8  mov     rcx, rdi; pSid
0x1800259ab  call    cs:__imp_GetSidIdentifierAuthority
0x1800259b2  nop     dword ptr [rax+rax+00h]
0x1800259b7  test    rax, rax
0x1800259ba  jz      short loc_180025A17
0x1800259bc  mov     dword ptr [rbp+arg_0], 0
0x1800259c3  mov     word ptr [rbp+arg_0+4], 500h
0x1800259c9  mov     ecx, [rax]
0x1800259cb  sub     ecx, dword ptr [rbp+arg_0]
0x1800259ce  jnz     short loc_1800259DA
0x1800259d0  movzx   ecx, word ptr [rax+4]
0x1800259d4  movzx   eax, word ptr [rbp+arg_0+4]
0x1800259d8  sub     ecx, eax
0x1800259da  test    ecx, ecx
0x1800259dc  jnz     short loc_180025A17
0x1800259de  mov     rcx, rdi; pSid
0x1800259e1  call    cs:__imp_GetSidSubAuthorityCount
0x1800259e8  nop     dword ptr [rax+rax+00h]
0x1800259ed  test    rax, rax
0x1800259f0  jz      short loc_180025A17
0x1800259f2  cmp     byte ptr [rax], 6
0x1800259f5  jnz     short loc_180025A17
0x1800259f7  xor     edx, edx; nSubAuthority
0x1800259f9  mov     rcx, rdi; pSid
0x1800259fc  call    cs:__imp_GetSidSubAuthority
0x180025a03  nop     dword ptr [rax+rax+00h]
0x180025a08  test    rax, rax
0x180025a0b  jz      short loc_180025A17
0x180025a0d  cmp     dword ptr [rax], 50h ; 'P'
0x180025a10  jnz     short loc_180025A17
0x180025a12  mov     dil, 1
0x180025a15  jmp     short loc_180025A1A
0x180025a17  xor     dil, dil
0x180025a1a  mov     rcx, rbx; lpCriticalSection
0x180025a1d  call    cs:__imp_LeaveCriticalSection
0x180025a24  nop     dword ptr [rax+rax+00h]
0x180025a29  mov     al, dil
0x180025a2c  add     rsp, 68h
0x180025a30  pop     rdi
0x180025a31  pop     rsi
0x180025a32  pop     rbx
0x180025a33  pop     rbp
0x180025a34  retn
```
