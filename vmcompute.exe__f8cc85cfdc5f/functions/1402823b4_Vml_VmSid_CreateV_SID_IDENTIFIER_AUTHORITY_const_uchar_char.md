# Vml::VmSid::CreateV(_SID_IDENTIFIER_AUTHORITY const &,uchar,char *)

- ea: `0x1402823b4`
- end: `0x140282485`
- name: `?CreateV@VmSid@Vml@@AEAAXAEBU_SID_IDENTIFIER_AUTHORITY@@EPEAD@Z`
- size: `209`
- prototype: `void __fastcall(Vml::VmSid *__hidden this, PSID_IDENTIFIER_AUTHORITY pIdentifierAuthority, unsigned __int8, char *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14010c5f0`

## callees

- `0x140080180`
- `0x1400bc99c`
- `0x1402823b4`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x14028241a`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x14028241a`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x1402823d1`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x1402823d1`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x140282455`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x140282455`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1402823e1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1402823e1`

## string_xrefs

- `0x1402823ff`: `onecore\vm\common\vml\VmSecurity.h`
- `0x14028242f`: `onecore\vm\common\vml\VmSecurity.h`

## pseudocode

```c
void __fastcall Vml::VmSid::CreateV(
        Vml::VmSid *this,
        PSID_IDENTIFIER_AUTHORITY pIdentifierAuthority,
        UCHAR a3,
        char *a4)
{
  DWORD v5; // ebx
  DWORD SidLengthRequired; // eax
  HLOCAL v9; // rax
  const char *v10; // r9
  void *v11; // rsi
  BOOL v12; // eax
  const char *v13; // r9
  DWORD v14; // r14d
  DWORD v15; // edi
  DWORD v16; // ebx
  void *v17; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v5 = a3;
  SidLengthRequired = GetSidLengthRequired(a3);
  v9 = LocalAlloc(0, SidLengthRequired);
  v11 = v9;
  v17 = v9;
  if ( !v9 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x13CB,
      (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
      v10);
  v12 = InitializeSid(v9, pIdentifierAuthority, v5);
  try
  {
    if ( !v12 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x13D3,
        (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
        v13);
    v14 = v5;
    v15 = 0;
    if ( (_BYTE)v5 )
    {
      do
      {
        v16 = *(_DWORD *)a4;
        a4 += 8;
        *GetSidSubAuthority(v11, v15++) = v16;
      }
      while ( v15 < v14 );
    }
    Vml::VmSid::Reset(this, v11);
  }
  catch ( ... )
  {
    LocalFree(v17);
    throw;
  }
}

```

## disassembly

```asm
0x1402823b4  push    rbx
0x1402823b6  push    rsi
0x1402823b7  push    rdi
0x1402823b8  push    r12
0x1402823ba  push    r14
0x1402823bc  push    r15
0x1402823be  sub     rsp, 38h
0x1402823c2  mov     r15, r9
0x1402823c5  movzx   ebx, r8b
0x1402823c9  mov     rdi, rdx
0x1402823cc  mov     r12, rcx
0x1402823cf  mov     cl, bl; nSubAuthorityCount
0x1402823d1  call    cs:__imp_GetSidLengthRequired
0x1402823d8  nop     dword ptr [rax+rax+00h]
0x1402823dd  mov     edx, eax; uBytes
0x1402823df  xor     ecx, ecx; uFlags
0x1402823e1  call    cs:__imp_LocalAlloc
0x1402823e8  nop     dword ptr [rax+rax+00h]
0x1402823ed  mov     rsi, rax
0x1402823f0  mov     [rsp+68h+var_48], rax
0x1402823f5  test    rax, rax
0x1402823f8  jnz     short loc_140282411
0x1402823fa  mov     rcx, [rsp+68h]; this
0x1402823ff  lea     r8, aOnecoreVmCommo_54; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x140282406  mov     edx, 13CBh; void *
0x14028240b  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140282411  mov     r8b, bl; nSubAuthorityCount
0x140282414  mov     rdx, rdi; pIdentifierAuthority
0x140282417  mov     rcx, rsi; Sid
0x14028241a  call    cs:__imp_InitializeSid
0x140282421  nop     dword ptr [rax+rax+00h]
0x140282426  mov     rcx, [rsp+68h]; this
0x14028242b  test    eax, eax
0x14028242d  jnz     short loc_140282440
0x14028242f  lea     r8, aOnecoreVmCommo_54; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x140282436  mov     edx, 13D3h; void *
0x14028243b  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140282440  mov     r14d, ebx
0x140282443  xor     edi, edi
0x140282445  test    bl, bl
0x140282447  jz      short loc_14028246A
0x140282449  mov     ebx, [r15]
0x14028244c  lea     r15, [r15+8]
0x140282450  mov     edx, edi; nSubAuthority
0x140282452  mov     rcx, rsi; pSid
0x140282455  call    cs:__imp_GetSidSubAuthority
0x14028245c  nop     dword ptr [rax+rax+00h]
0x140282461  mov     [rax], ebx
0x140282463  inc     edi
0x140282465  cmp     edi, r14d
0x140282468  jb      short loc_140282449
0x14028246a  mov     rdx, rsi; void *
0x14028246d  mov     rcx, r12; this
0x140282470  call    ?Reset@VmSid@Vml@@QEAAXPEAX@Z; Vml::VmSid::Reset(void *)
0x140282475  nop
0x140282476  add     rsp, 38h
0x14028247a  pop     r15
0x14028247c  pop     r14
0x14028247e  pop     r12
0x140282480  pop     rdi
0x140282481  pop     rsi
0x140282482  pop     rbx
0x140282483  retn
```
