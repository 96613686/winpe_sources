# Vml::VmSid::CreateV(_SID_IDENTIFIER_AUTHORITY const &,uchar,char *)

- ea: `0x1400e0430`
- end: `0x1400e0530`
- name: `?CreateV@VmSid@Vml@@AEAAXAEBU_SID_IDENTIFIER_AUTHORITY@@EPEAD@Z`
- size: `256`
- prototype: `void(Vml::VmSid *__hidden this, const struct _SID_IDENTIFIER_AUTHORITY *, unsigned __int8, char *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400dfa0c`

## callees

- `0x14000ddac`
- `0x1400e0430`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x1400e044d`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x1400e044d`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1400e04a1`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1400e04a1`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x1400e0477`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x1400e0477`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1400e0457`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1400e0457`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400e04bb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400e04bb`

## string_xrefs

- `0x1400e050b`: `onecore\vm\common\vml\VmSecurity.h`
- `0x1400e051d`: `onecore\vm\common\vml\VmSecurity.h`

## pseudocode

```c
void __fastcall Vml::VmSid::CreateV(Vml::VmSid *this, struct _SID_IDENTIFIER_AUTHORITY *a2, UCHAR a3, char *a4)
{
  DWORD v5; // ebx
  DWORD SidLengthRequired; // eax
  HLOCAL v9; // rax
  const char *v10; // r9
  void *v11; // r14
  const char *v12; // r9
  DWORD v13; // r15d
  DWORD v14; // esi
  DWORD v15; // ebx
  void *v16; // rcx
  _QWORD *v17; // rcx
  _QWORD *v18; // rcx
  HLOCAL v19; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v5 = a3;
  SidLengthRequired = GetSidLengthRequired(a3);
  v9 = LocalAlloc(0, SidLengthRequired);
  v11 = v9;
  v19 = v9;
  if ( !v9 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x13CB,
      (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
      v10);
  if ( !InitializeSid(v9, a2, v5) )
  {
    try
    {
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x13D3,
        (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
        v12);
    }
    catch ( ... )
    {
      LocalFree(v19);
      throw;
    }
  }
  v13 = v5;
  v14 = 0;
  if ( (_BYTE)v5 )
  {
    do
    {
      v15 = *(_DWORD *)a4;
      a4 += 8;
      *GetSidSubAuthority(v11, v14++) = v15;
    }
    while ( v14 < v13 );
  }
  v16 = *(void **)this;
  *(_QWORD *)this = v11;
  if ( v16 )
    LocalFree(v16);
  *((_DWORD *)this + 2) = 7;
  v17 = (_QWORD *)((char *)this + 48);
  *((_QWORD *)this + 8) = 0;
  if ( *((_QWORD *)this + 9) > 7u )
    v17 = (_QWORD *)*v17;
  *(_WORD *)v17 = 0;
  v18 = (_QWORD *)((char *)this + 16);
  *((_QWORD *)this + 4) = 0;
  if ( *((_QWORD *)this + 5) > 7u )
    v18 = (_QWORD *)*v18;
  *(_WORD *)v18 = 0;
}

```

## disassembly

```asm
0x1400e0430  push    rbx
0x1400e0432  push    rsi
0x1400e0433  push    rdi
0x1400e0434  push    r12
0x1400e0436  push    r14
0x1400e0438  push    r15
0x1400e043a  sub     rsp, 38h
0x1400e043e  mov     r12, r9
0x1400e0441  movzx   ebx, r8b
0x1400e0445  mov     rsi, rdx
0x1400e0448  mov     rdi, rcx
0x1400e044b  mov     cl, bl; nSubAuthorityCount
0x1400e044d  call    cs:__imp_GetSidLengthRequired
0x1400e0453  mov     edx, eax; uBytes
0x1400e0455  xor     ecx, ecx; uFlags
0x1400e0457  call    cs:__imp_LocalAlloc
0x1400e045d  mov     r14, rax
0x1400e0460  mov     [rsp+68h+var_48], rax
0x1400e0465  test    rax, rax
0x1400e0468  jz      loc_1400E0506
0x1400e046e  mov     r8b, bl; nSubAuthorityCount
0x1400e0471  mov     rdx, rsi; pIdentifierAuthority
0x1400e0474  mov     rcx, r14; Sid
0x1400e0477  call    cs:__imp_InitializeSid
0x1400e047d  mov     rcx, [rsp+68h]; this
0x1400e0482  test    eax, eax
0x1400e0484  jz      loc_1400E051D
0x1400e048a  mov     r15d, ebx
0x1400e048d  xor     esi, esi
0x1400e048f  test    bl, bl
0x1400e0491  jz      short loc_1400E04B0
0x1400e0493  mov     ebx, [r12]
0x1400e0497  lea     r12, [r12+8]
0x1400e049c  mov     edx, esi; nSubAuthority
0x1400e049e  mov     rcx, r14; pSid
0x1400e04a1  call    cs:__imp_GetSidSubAuthority
0x1400e04a7  mov     [rax], ebx
0x1400e04a9  inc     esi
0x1400e04ab  cmp     esi, r15d
0x1400e04ae  jb      short loc_1400E0493
0x1400e04b0  mov     rcx, [rdi]; hMem
0x1400e04b3  mov     [rdi], r14
0x1400e04b6  test    rcx, rcx
0x1400e04b9  jz      short loc_1400E04C1
0x1400e04bb  call    cs:__imp_LocalFree
0x1400e04c1  mov     dword ptr [rdi+8], 7
0x1400e04c8  lea     rcx, [rdi+30h]
0x1400e04cc  mov     qword ptr [rcx+10h], 0
0x1400e04d4  cmp     qword ptr [rcx+18h], 7
0x1400e04d9  jbe     short loc_1400E04DE
0x1400e04db  mov     rcx, [rcx]
0x1400e04de  xor     eax, eax
0x1400e04e0  mov     [rcx], ax
0x1400e04e3  lea     rcx, [rdi+10h]
0x1400e04e7  mov     [rcx+10h], rax
0x1400e04eb  cmp     qword ptr [rcx+18h], 7
0x1400e04f0  jbe     short loc_1400E04F5
0x1400e04f2  mov     rcx, [rcx]
0x1400e04f5  mov     [rcx], ax
0x1400e04f8  add     rsp, 38h
0x1400e04fc  pop     r15
0x1400e04fe  pop     r14
0x1400e0500  pop     r12
0x1400e0502  pop     rdi
0x1400e0503  pop     rsi
0x1400e0504  pop     rbx
0x1400e0505  retn
0x1400e0506  mov     rcx, [rsp+68h]; this
0x1400e050b  lea     r8, aOnecoreVmCommo_12; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x1400e0512  mov     edx, 13CBh; void *
0x1400e0517  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400e051d  lea     r8, aOnecoreVmCommo_12; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x1400e0524  mov     edx, 13D3h; void *
0x1400e0529  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
