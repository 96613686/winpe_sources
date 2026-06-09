# User::IsServiceSid(void)

- ea: `0x18001a96c`
- end: `0x18001aac4`
- name: `?IsServiceSid@User@@QEBA_NXZ`
- size: `344`
- prototype: `bool __fastcall(User *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18001a928`

## callees

- `0x18000878c`
- `0x18000c760`
- `0x18001a96c`
- `0x18001aacc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a997`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a997`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001aaa9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001aaa9`
- `api-ms-win-security-base-l1-1-0!GetSidIdentifierAuthority` at `0x18001aa49`
- `api-ms-win-security-base-l1-1-0!GetSidIdentifierAuthority` at `0x18001aa49`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18001aa79`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18001aa79`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18001aa8e`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18001aa8e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall User::IsServiceSid(User *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbx
  int v3; // edi
  PSID v4; // rdi
  PSID_IDENTIFIER_AUTHORITY SidIdentifierAuthority; // rax
  int v6; // ecx
  PUCHAR SidSubAuthorityCount; // rax
  PDWORD SidSubAuthority; // rax
  char v9; // di
  void **pExceptionObject; // [rsp+20h] [rbp-40h] BYREF
  char v12; // [rsp+28h] [rbp-38h]
  char *v13; // [rsp+30h] [rbp-30h]
  __int64 v14; // [rsp+38h] [rbp-28h]
  __int64 v15; // [rsp+40h] [rbp-20h]
  int v16; // [rsp+48h] [rbp-18h]
  __int64 v17; // [rsp+4Ch] [rbp-14h]
  PSID pSid; // [rsp+70h] [rbp+10h] BYREF
  LPCRITICAL_SECTION v19; // [rsp+78h] [rbp+18h]

  pSid = 0;
  v2 = User::s_cs;
  v19 = User::s_cs;
  EnterCriticalSection(User::s_cs);
  if ( !*(_QWORD *)this || **(_BYTE **)this )
    goto LABEL_18;
  v3 = User::LookupSid(this, &pSid);
  if ( v3 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        31,
        WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids,
        (unsigned int)v3);
    }
    v12 = 0;
    pExceptionObject = &wmi::GenericException::`vftable';
    v13 = byte_1800505F8;
    v14 = 0;
    v15 = 0;
    v16 = v3;
    v17 = -1;
    throw (wmi::GenericException *)&pExceptionObject;
  }
  v4 = pSid;
  SidIdentifierAuthority = GetSidIdentifierAuthority(pSid);
  if ( !SidIdentifierAuthority )
    goto LABEL_18;
  LODWORD(pSid) = 0;
  WORD2(pSid) = 1280;
  v6 = *(_DWORD *)SidIdentifierAuthority->Value;
  if ( !*(_DWORD *)SidIdentifierAuthority->Value )
    v6 = *(unsigned __int16 *)&SidIdentifierAuthority->Value[4] - WORD2(pSid);
  if ( !v6
    && (SidSubAuthorityCount = GetSidSubAuthorityCount(v4)) != 0
    && *SidSubAuthorityCount == 6
    && (SidSubAuthority = GetSidSubAuthority(v4, 0)) != 0
    && *SidSubAuthority == 80 )
  {
    v9 = 1;
  }
  else
  {
LABEL_18:
    v9 = 0;
  }
  LeaveCriticalSection(v2);
  return v9;
}

```

## disassembly

```asm
0x18001a96c  mov     [rsp-8+arg_10], rbx
0x18001a971  mov     [rsp-8+arg_18], rdi
0x18001a976  push    rbp
0x18001a977  mov     rbp, rsp
0x18001a97a  sub     rsp, 60h
0x18001a97e  mov     rdi, rcx
0x18001a981  mov     [rbp+pSid], 0
0x18001a989  mov     rbx, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x18001a990  mov     [rbp+arg_8], rbx
0x18001a994  mov     rcx, rbx; lpCriticalSection
0x18001a997  call    cs:__imp_EnterCriticalSection
0x18001a99d  nop
0x18001a99e  mov     rax, [rdi]
0x18001a9a1  test    rax, rax
0x18001a9a4  jz      loc_18001AAA3
0x18001a9aa  cmp     byte ptr [rax], 0
0x18001a9ad  jnz     loc_18001AAA3
0x18001a9b3  lea     rdx, [rbp+pSid]; void **
0x18001a9b7  mov     rcx, rdi; this
0x18001a9ba  call    ?LookupSid@User@@QEBAJAEAPEAX@Z; User::LookupSid(void * &)
0x18001a9bf  mov     edi, eax
0x18001a9c1  test    eax, eax
0x18001a9c3  jns     short loc_18001AA42
0x18001a9c5  lea     rax, WPP_GLOBAL_Control
0x18001a9cc  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a9d3  cmp     rcx, rax
0x18001a9d6  jz      short loc_18001A9FC
0x18001a9d8  test    byte ptr [rcx+1Ch], 80h
0x18001a9dc  jz      short loc_18001A9FC
0x18001a9de  cmp     byte ptr [rcx+19h], 2
0x18001a9e2  jb      short loc_18001A9FC
0x18001a9e4  mov     edx, 1Fh
0x18001a9e9  mov     r9d, edi
0x18001a9ec  lea     r8, WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids
0x18001a9f3  mov     rcx, [rcx+10h]
0x18001a9f7  call    WPP_SF_d
0x18001a9fc  mov     [rbp+var_38], 0
0x18001aa00  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18001aa07  mov     [rbp+pExceptionObject], rax
0x18001aa0b  lea     rax, byte_1800505F8
0x18001aa12  mov     [rbp+var_30], rax
0x18001aa16  mov     [rbp+var_28], 0
0x18001aa1e  mov     [rbp+var_20], 0
0x18001aa26  mov     [rbp+var_18], edi
0x18001aa29  mov     [rbp+var_14], 0FFFFFFFFFFFFFFFFh
0x18001aa31  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18001aa38  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001aa3c  call    _CxxThrowException_0
0x18001aa42  mov     rdi, [rbp+pSid]
0x18001aa46  mov     rcx, rdi; pSid
0x18001aa49  call    cs:__imp_GetSidIdentifierAuthority
0x18001aa4f  test    rax, rax
0x18001aa52  jz      short loc_18001AAA3
0x18001aa54  mov     dword ptr [rbp+pSid], 0
0x18001aa5b  mov     word ptr [rbp+pSid+4], 500h
0x18001aa61  mov     ecx, [rax]
0x18001aa63  sub     ecx, dword ptr [rbp+pSid]
0x18001aa66  jnz     short loc_18001AA72
0x18001aa68  movzx   ecx, word ptr [rax+4]
0x18001aa6c  movzx   eax, word ptr [rbp+pSid+4]
0x18001aa70  sub     ecx, eax
0x18001aa72  test    ecx, ecx
0x18001aa74  jnz     short loc_18001AAA3
0x18001aa76  mov     rcx, rdi; pSid
0x18001aa79  call    cs:__imp_GetSidSubAuthorityCount
0x18001aa7f  test    rax, rax
0x18001aa82  jz      short loc_18001AAA3
0x18001aa84  cmp     byte ptr [rax], 6
0x18001aa87  jnz     short loc_18001AAA3
0x18001aa89  xor     edx, edx; nSubAuthority
0x18001aa8b  mov     rcx, rdi; pSid
0x18001aa8e  call    cs:__imp_GetSidSubAuthority
0x18001aa94  test    rax, rax
0x18001aa97  jz      short loc_18001AAA3
0x18001aa99  cmp     dword ptr [rax], 50h ; 'P'
0x18001aa9c  jnz     short loc_18001AAA3
0x18001aa9e  mov     dil, 1
0x18001aaa1  jmp     short loc_18001AAA6
0x18001aaa3  xor     dil, dil
0x18001aaa6  mov     rcx, rbx; lpCriticalSection
0x18001aaa9  call    cs:__imp_LeaveCriticalSection
0x18001aaaf  mov     al, dil
0x18001aab2  lea     r11, [rsp+60h+var_s0]
0x18001aab7  mov     rbx, [r11+20h]
0x18001aabb  mov     rdi, [r11+28h]
0x18001aabf  mov     rsp, r11
0x18001aac2  pop     rbp
0x18001aac3  retn
```
