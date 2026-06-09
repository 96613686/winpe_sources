# User::IsServiceSid(void)

- ea: `0x18001bd08`
- end: `0x18001be81`
- name: `?IsServiceSid@User@@QEBA_NXZ`
- size: `377`
- prototype: `bool __fastcall(User *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18001bcc0`

## callees

- `0x180008c4c`
- `0x18000cf80`
- `0x180018534`
- `0x18001bd08`
- `0x18001be88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001bd33`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001bd33`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001be5f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001be5f`
- `api-ms-win-security-base-l1-1-0!GetSidIdentifierAuthority` at `0x18001bded`
- `api-ms-win-security-base-l1-1-0!GetSidIdentifierAuthority` at `0x18001bded`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18001be23`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18001be23`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18001be3e`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18001be3e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall User::IsServiceSid(User *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbx
  User *v3; // rcx
  int v4; // edi
  PSID v5; // rdi
  PSID_IDENTIFIER_AUTHORITY SidIdentifierAuthority; // rax
  int v7; // ecx
  PUCHAR SidSubAuthorityCount; // rax
  PDWORD SidSubAuthority; // rax
  char v10; // di
  void **pExceptionObject; // [rsp+20h] [rbp-40h] BYREF
  char v13; // [rsp+28h] [rbp-38h]
  char *v14; // [rsp+30h] [rbp-30h]
  __int64 v15; // [rsp+38h] [rbp-28h]
  __int64 v16; // [rsp+40h] [rbp-20h]
  int v17; // [rsp+48h] [rbp-18h]
  __int64 v18; // [rsp+4Ch] [rbp-14h]
  PSID pSid; // [rsp+70h] [rbp+10h] BYREF
  LPCRITICAL_SECTION v20; // [rsp+78h] [rbp+18h]

  pSid = 0;
  v2 = User::s_cs;
  v20 = User::s_cs;
  EnterCriticalSection(User::s_cs);
  if ( !*(_QWORD *)this || User::IsAlias(this) )
    goto LABEL_18;
  v4 = User::LookupSid(v3, &pSid);
  if ( v4 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        31,
        WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids,
        (unsigned int)v4);
    }
    v13 = 0;
    pExceptionObject = &wmi::GenericException::`vftable';
    v14 = byte_180052608;
    v15 = 0;
    v16 = 0;
    v17 = v4;
    v18 = -1;
    throw (wmi::GenericException *)&pExceptionObject;
  }
  v5 = pSid;
  SidIdentifierAuthority = GetSidIdentifierAuthority(pSid);
  if ( !SidIdentifierAuthority )
    goto LABEL_18;
  LODWORD(pSid) = 0;
  WORD2(pSid) = 1280;
  v7 = *(_DWORD *)SidIdentifierAuthority->Value;
  if ( !*(_DWORD *)SidIdentifierAuthority->Value )
    v7 = *(unsigned __int16 *)&SidIdentifierAuthority->Value[4] - WORD2(pSid);
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
LABEL_18:
    v10 = 0;
  }
  LeaveCriticalSection(v2);
  return v10;
}

```

## disassembly

```asm
0x18001bd08  mov     [rsp-8+arg_10], rbx
0x18001bd0d  mov     [rsp-8+arg_18], rdi
0x18001bd12  push    rbp
0x18001bd13  mov     rbp, rsp
0x18001bd16  sub     rsp, 60h
0x18001bd1a  mov     rdi, rcx
0x18001bd1d  mov     [rbp+pSid], 0
0x18001bd25  mov     rbx, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x18001bd2c  mov     [rbp+arg_8], rbx
0x18001bd30  mov     rcx, rbx; lpCriticalSection
0x18001bd33  call    cs:__imp_EnterCriticalSection
0x18001bd3a  nop     dword ptr [rax+rax+00h]
0x18001bd3f  nop
0x18001bd40  cmp     qword ptr [rdi], 0
0x18001bd44  jz      loc_18001BE59
0x18001bd4a  mov     rcx, rdi; this
0x18001bd4d  call    ?IsAlias@User@@QEBA_NXZ; User::IsAlias(void)
0x18001bd52  test    al, al
0x18001bd54  jnz     loc_18001BE59
0x18001bd5a  lea     rdx, [rbp+pSid]; void **
0x18001bd5e  call    ?LookupSid@User@@QEBAJAEAPEAX@Z; User::LookupSid(void * &)
0x18001bd63  mov     edi, eax
0x18001bd65  test    eax, eax
0x18001bd67  jns     short loc_18001BDE6
0x18001bd69  lea     rax, WPP_GLOBAL_Control
0x18001bd70  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bd77  cmp     rcx, rax
0x18001bd7a  jz      short loc_18001BDA0
0x18001bd7c  test    byte ptr [rcx+1Ch], 80h
0x18001bd80  jz      short loc_18001BDA0
0x18001bd82  cmp     byte ptr [rcx+19h], 2
0x18001bd86  jb      short loc_18001BDA0
0x18001bd88  mov     edx, 1Fh
0x18001bd8d  mov     r9d, edi
0x18001bd90  lea     r8, WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids
0x18001bd97  mov     rcx, [rcx+10h]
0x18001bd9b  call    WPP_SF_d
0x18001bda0  mov     [rbp+var_38], 0
0x18001bda4  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18001bdab  mov     [rbp+pExceptionObject], rax
0x18001bdaf  lea     rax, byte_180052608
0x18001bdb6  mov     [rbp+var_30], rax
0x18001bdba  mov     [rbp+var_28], 0
0x18001bdc2  mov     [rbp+var_20], 0
0x18001bdca  mov     [rbp+var_18], edi
0x18001bdcd  mov     [rbp+var_14], 0FFFFFFFFFFFFFFFFh
0x18001bdd5  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18001bddc  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001bde0  call    _CxxThrowException_0
0x18001bde6  mov     rdi, [rbp+pSid]
0x18001bdea  mov     rcx, rdi; pSid
0x18001bded  call    cs:__imp_GetSidIdentifierAuthority
0x18001bdf4  nop     dword ptr [rax+rax+00h]
0x18001bdf9  test    rax, rax
0x18001bdfc  jz      short loc_18001BE59
0x18001bdfe  mov     dword ptr [rbp+pSid], 0
0x18001be05  mov     word ptr [rbp+pSid+4], 500h
0x18001be0b  mov     ecx, [rax]
0x18001be0d  sub     ecx, dword ptr [rbp+pSid]
0x18001be10  jnz     short loc_18001BE1C
0x18001be12  movzx   ecx, word ptr [rax+4]
0x18001be16  movzx   eax, word ptr [rbp+pSid+4]
0x18001be1a  sub     ecx, eax
0x18001be1c  test    ecx, ecx
0x18001be1e  jnz     short loc_18001BE59
0x18001be20  mov     rcx, rdi; pSid
0x18001be23  call    cs:__imp_GetSidSubAuthorityCount
0x18001be2a  nop     dword ptr [rax+rax+00h]
0x18001be2f  test    rax, rax
0x18001be32  jz      short loc_18001BE59
0x18001be34  cmp     byte ptr [rax], 6
0x18001be37  jnz     short loc_18001BE59
0x18001be39  xor     edx, edx; nSubAuthority
0x18001be3b  mov     rcx, rdi; pSid
0x18001be3e  call    cs:__imp_GetSidSubAuthority
0x18001be45  nop     dword ptr [rax+rax+00h]
0x18001be4a  test    rax, rax
0x18001be4d  jz      short loc_18001BE59
0x18001be4f  cmp     dword ptr [rax], 50h ; 'P'
0x18001be52  jnz     short loc_18001BE59
0x18001be54  mov     dil, 1
0x18001be57  jmp     short loc_18001BE5C
0x18001be59  xor     dil, dil
0x18001be5c  mov     rcx, rbx; lpCriticalSection
0x18001be5f  call    cs:__imp_LeaveCriticalSection
0x18001be66  nop     dword ptr [rax+rax+00h]
0x18001be6b  mov     al, dil
0x18001be6e  lea     r11, [rsp+60h+var_s0]
0x18001be73  mov     rbx, [r11+20h]
0x18001be77  mov     rdi, [r11+28h]
0x18001be7b  mov     rsp, r11
0x18001be7e  pop     rbp
0x18001be7f  retn
```
