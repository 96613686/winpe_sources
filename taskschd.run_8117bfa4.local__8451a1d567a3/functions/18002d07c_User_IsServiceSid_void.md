# User::IsServiceSid(void)

- ea: `0x18002d07c`
- end: `0x18002d201`
- name: `?IsServiceSid@User@@QEBA_NXZ`
- size: `389`
- prototype: `bool __fastcall(User *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18002ce24`

## callees

- `0x180009280`
- `0x18002d07c`
- `0x18003c810`
- `0x18003e88c`
- `0x180052284`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002d12d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002d12d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002d099`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002d099`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002d10d`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002d10d`
- `api-ms-win-security-base-l1-1-0!GetSidIdentifierAuthority` at `0x18002d0d7`
- `api-ms-win-security-base-l1-1-0!GetSidIdentifierAuthority` at `0x18002d0d7`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002d1da`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002d1da`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall User::IsServiceSid(User *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbx
  __int64 v3; // rdx
  __int64 v4; // r8
  void *v5; // rdi
  PSID_IDENTIFIER_AUTHORITY SidIdentifierAuthority; // rax
  int v7; // ecx
  PUCHAR SidSubAuthorityCount; // rax
  char v9; // di
  int updated; // edi
  PDWORD SidSubAuthority; // rax
  void **pExceptionObject; // [rsp+20h] [rbp-48h] BYREF
  char v14; // [rsp+28h] [rbp-40h]
  __int64 *v15; // [rsp+30h] [rbp-38h]
  __int64 v16; // [rsp+38h] [rbp-30h]
  __int64 v17; // [rsp+40h] [rbp-28h]
  int v18; // [rsp+48h] [rbp-20h]
  __int64 v19; // [rsp+4Ch] [rbp-1Ch]

  v2 = User::s_cs;
  EnterCriticalSection(User::s_cs);
  if ( !*(_QWORD *)this || User::IsAlias(this) )
    goto LABEL_11;
  if ( *(_BYTE *)v3 )
  {
    updated = -2147418113;
    goto LABEL_15;
  }
  if ( !*(_QWORD *)(v3 + 32) )
  {
    updated = User::UpdateEntry(this);
    if ( updated < 0 )
    {
LABEL_15:
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, v4, (unsigned int)updated);
      }
      v14 = 0;
      pExceptionObject = &wmi::GenericException::`vftable';
      v15 = &qword_18007B2F0;
      v16 = 0;
      v17 = 0;
      v18 = updated;
      v19 = -1;
      throw (wmi::GenericException *)&pExceptionObject;
    }
  }
  v5 = *(void **)(*(_QWORD *)this + 32LL);
  SidIdentifierAuthority = GetSidIdentifierAuthority(v5);
  if ( !SidIdentifierAuthority )
    goto LABEL_11;
  v7 = *(_DWORD *)SidIdentifierAuthority->Value;
  if ( !*(_DWORD *)SidIdentifierAuthority->Value )
    v7 = *(unsigned __int16 *)&SidIdentifierAuthority->Value[4] - 1280;
  if ( !v7
    && (SidSubAuthorityCount = GetSidSubAuthorityCount(v5)) != 0
    && *SidSubAuthorityCount == 6
    && (SidSubAuthority = GetSidSubAuthority(v5, 0)) != 0
    && *SidSubAuthority == 80 )
  {
    v9 = 1;
  }
  else
  {
LABEL_11:
    v9 = 0;
  }
  LeaveCriticalSection(v2);
  return v9;
}

```

## disassembly

```asm
0x18002d07c  push    rbp
0x18002d07e  push    rbx
0x18002d07f  push    rsi
0x18002d080  push    rdi
0x18002d081  mov     rbp, rsp
0x18002d084  sub     rsp, 68h
0x18002d088  mov     rsi, rcx
0x18002d08b  mov     rbx, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x18002d092  mov     [rbp+arg_0], rbx
0x18002d096  mov     rcx, rbx; lpCriticalSection
0x18002d099  call    cs:__imp_EnterCriticalSection
0x18002d0a0  nop     dword ptr [rax+rax+00h]
0x18002d0a5  nop
0x18002d0a6  mov     rdx, [rsi]
0x18002d0a9  test    rdx, rdx
0x18002d0ac  jz      short loc_18002D127
0x18002d0ae  mov     rcx, rsi; this
0x18002d0b1  call    ?IsAlias@User@@QEBA_NXZ; User::IsAlias(void)
0x18002d0b6  test    al, al
0x18002d0b8  jnz     short loc_18002D127
0x18002d0ba  cmp     [rdx], al
0x18002d0bc  jnz     loc_18002D146
0x18002d0c2  cmp     qword ptr [rdx+20h], 0
0x18002d0c7  jz      loc_18002D14D
0x18002d0cd  mov     rax, [rsi]
0x18002d0d0  mov     rdi, [rax+20h]
0x18002d0d4  mov     rcx, rdi; pSid
0x18002d0d7  call    cs:__imp_GetSidIdentifierAuthority
0x18002d0de  nop     dword ptr [rax+rax+00h]
0x18002d0e3  test    rax, rax
0x18002d0e6  jz      short loc_18002D127
0x18002d0e8  mov     dword ptr [rbp+arg_0], 0
0x18002d0ef  mov     word ptr [rbp+arg_0+4], 500h
0x18002d0f5  mov     ecx, [rax]
0x18002d0f7  sub     ecx, dword ptr [rbp+arg_0]
0x18002d0fa  jnz     short loc_18002D106
0x18002d0fc  movzx   ecx, word ptr [rax+4]
0x18002d100  movzx   eax, word ptr [rbp+arg_0+4]
0x18002d104  sub     ecx, eax
0x18002d106  test    ecx, ecx
0x18002d108  jnz     short loc_18002D127
0x18002d10a  mov     rcx, rdi; pSid
0x18002d10d  call    cs:__imp_GetSidSubAuthorityCount
0x18002d114  nop     dword ptr [rax+rax+00h]
0x18002d119  test    rax, rax
0x18002d11c  jz      short loc_18002D127
0x18002d11e  cmp     byte ptr [rax], 6
0x18002d121  jz      loc_18002D1D5
0x18002d127  xor     dil, dil
0x18002d12a  mov     rcx, rbx; lpCriticalSection
0x18002d12d  call    cs:__imp_LeaveCriticalSection
0x18002d134  nop     dword ptr [rax+rax+00h]
0x18002d139  mov     al, dil
0x18002d13c  add     rsp, 68h
0x18002d140  pop     rdi
0x18002d141  pop     rsi
0x18002d142  pop     rbx
0x18002d143  pop     rbp
0x18002d144  retn
0x18002d146  mov     edi, 8000FFFFh
0x18002d14b  jmp     short loc_18002D15F
0x18002d14d  mov     rcx, rsi; this
0x18002d150  call    ?UpdateEntry@User@@AEBAJXZ; User::UpdateEntry(void)
0x18002d155  mov     edi, eax
0x18002d157  test    eax, eax
0x18002d159  jns     loc_18002D0CD
0x18002d15f  lea     rax, WPP_GLOBAL_Control
0x18002d166  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d16d  cmp     rcx, rax
0x18002d170  jz      short loc_18002D18F
0x18002d172  test    byte ptr [rcx+1Ch], 80h
0x18002d176  jz      short loc_18002D18F
0x18002d178  cmp     byte ptr [rcx+19h], 2
0x18002d17c  jb      short loc_18002D18F
0x18002d17e  mov     edx, 1Fh
0x18002d183  mov     r9d, edi
0x18002d186  mov     rcx, [rcx+10h]
0x18002d18a  call    WPP_SF_d
0x18002d18f  mov     [rbp+var_40], 0
0x18002d193  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18002d19a  mov     [rbp+pExceptionObject], rax
0x18002d19e  lea     rax, qword_18007B2F0
0x18002d1a5  mov     [rbp+var_38], rax
0x18002d1a9  mov     [rbp+var_30], 0
0x18002d1b1  mov     [rbp+var_28], 0
0x18002d1b9  mov     [rbp+var_20], edi
0x18002d1bc  mov     [rbp+var_1C], 0FFFFFFFFFFFFFFFFh
0x18002d1c4  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18002d1cb  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18002d1cf  call    _CxxThrowException_0
0x18002d1d5  xor     edx, edx; nSubAuthority
0x18002d1d7  mov     rcx, rdi; pSid
0x18002d1da  call    cs:__imp_GetSidSubAuthority
0x18002d1e1  nop     dword ptr [rax+rax+00h]
0x18002d1e6  test    rax, rax
0x18002d1e9  jz      loc_18002D127
0x18002d1ef  cmp     dword ptr [rax], 50h ; 'P'
0x18002d1f2  jnz     loc_18002D127
0x18002d1f8  mov     dil, 1
0x18002d1fb  jmp     loc_18002D12A
```
