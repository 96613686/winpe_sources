# CNtSid::GetInfo(ushort * *,ushort * *,ulong *)

- ea: `0x18003d030`
- end: `0x18003d1bd`
- name: `?GetInfo@CNtSid@@QEAAHPEAPEAG0PEAK@Z`
- size: `397`
- prototype: `__int64 __fastcall(CNtSid *__hidden this, unsigned __int16 **, unsigned __int16 **, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000a290`
- `0x18000ab30`
- `0x18001c4fc`
- `0x18003d030`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d0c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d16f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d0c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d16f`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18003d0bf`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18003d155`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18003d0bf`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18003d155`

## pseudocode

```c
DWORD __fastcall CNtSid::GetInfo(PSID *this, unsigned __int16 **a2, unsigned __int16 **a3, enum _SID_NAME_USE *a4)
{
  PSID v8; // rcx
  PSID v9; // rcx
  DWORD result; // eax
  void *v11; // rbx
  unsigned __int16 *v12; // r14
  DWORD cchReferencedDomainName; // [rsp+70h] [rbp+40h] BYREF
  DWORD cchName; // [rsp+78h] [rbp+48h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+80h] [rbp+50h] BYREF

  if ( a2 )
    *a2 = 0;
  if ( a3 )
    *a3 = 0;
  if ( a4 )
    *a4 = 0;
  v8 = *this;
  if ( !v8 || !(unsigned int)DLIsValidSid(v8) )
    return 13;
  v9 = *this;
  cchName = 0;
  cchReferencedDomainName = 0;
  peUse = 0;
  LookupAccountSidLocalW(v9, 0, &cchName, 0, &cchReferencedDomainName, &peUse);
  result = GetLastError();
  if ( result != 122 )
    return result;
  v11 = CWin32DefaultArena::WbemMemAlloc(saturated_mul(cchName + 1, 2u));
  if ( !v11 )
    return 14;
  v12 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(saturated_mul(cchReferencedDomainName + 1, 2u));
  if ( !v12 )
  {
    CMUILocale::_Free(v11);
    return 14;
  }
  if ( LookupAccountSidLocalW(*this, (LPWSTR)v11, &cchName, v12, &cchReferencedDomainName, &peUse) )
  {
    if ( a2 )
      *a2 = (unsigned __int16 *)v11;
    else
      CMUILocale::_Free(v11);
    if ( a3 )
      *a3 = v12;
    else
      CMUILocale::_Free(v12);
    if ( a4 )
      *a4 = peUse;
    return 0;
  }
  else
  {
    CMUILocale::_Free(v11);
    CMUILocale::_Free(v12);
    return GetLastError();
  }
}

```

## disassembly

```asm
0x18003d030  push    rbp
0x18003d032  push    rbx
0x18003d033  push    rsi
0x18003d034  push    rdi
0x18003d035  push    r12
0x18003d037  push    r14
0x18003d039  push    r15
0x18003d03b  mov     rbp, rsp
0x18003d03e  sub     rsp, 30h
0x18003d042  mov     rdi, r9
0x18003d045  mov     rsi, r8
0x18003d048  mov     r15, rdx
0x18003d04b  mov     r12, rcx
0x18003d04e  test    rdx, rdx
0x18003d051  jz      short loc_18003D05A
0x18003d053  mov     qword ptr [rdx], 0
0x18003d05a  test    rsi, rsi
0x18003d05d  jz      short loc_18003D066
0x18003d05f  mov     qword ptr [r8], 0
0x18003d066  test    rdi, rdi
0x18003d069  jz      short loc_18003D072
0x18003d06b  mov     dword ptr [r9], 0
0x18003d072  mov     rcx, [rcx]; void *
0x18003d075  test    rcx, rcx
0x18003d078  jz      loc_18003D1A9
0x18003d07e  call    ?DLIsValidSid@@YAHPEAX@Z; DLIsValidSid(void *)
0x18003d083  test    eax, eax
0x18003d085  jz      loc_18003D1A9
0x18003d08b  mov     rcx, [r12]; Sid
0x18003d08f  lea     rax, [rbp+arg_10]
0x18003d093  mov     [rsp+30h+peUse], rax; peUse
0x18003d098  lea     r8, [rbp+cchName]; cchName
0x18003d09c  lea     rax, [rbp+arg_0]
0x18003d0a0  mov     [rbp+cchName], 0
0x18003d0a7  xor     r9d, r9d; ReferencedDomainName
0x18003d0aa  mov     [rsp+30h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18003d0af  xor     edx, edx; Name
0x18003d0b1  mov     [rbp+arg_0], 0
0x18003d0b8  mov     [rbp+arg_10], 0
0x18003d0bf  call    cs:__imp_LookupAccountSidLocalW
0x18003d0c5  call    cs:__imp_GetLastError
0x18003d0cb  cmp     eax, 7Ah ; 'z'
0x18003d0ce  jnz     loc_18003D1AE
0x18003d0d4  mov     ecx, [rbp+cchName]
0x18003d0d7  lea     r14d, [rax-78h]
0x18003d0db  inc     ecx
0x18003d0dd  mov     eax, r14d
0x18003d0e0  mul     rcx
0x18003d0e3  lea     rcx, [r14-3]
0x18003d0e7  cmovb   rax, rcx
0x18003d0eb  mov     rcx, rax; unsigned __int64
0x18003d0ee  call    ?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18003d0f3  mov     rbx, rax
0x18003d0f6  test    rax, rax
0x18003d0f9  jnz     short loc_18003D105
0x18003d0fb  mov     eax, 0Eh
0x18003d100  jmp     loc_18003D1AE
0x18003d105  mov     edx, [rbp+arg_0]
0x18003d108  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18003d10f  inc     edx
0x18003d111  mov     rax, r14
0x18003d114  mul     rdx
0x18003d117  cmovb   rax, rcx
0x18003d11b  mov     rcx, rax; unsigned __int64
0x18003d11e  call    ?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18003d123  mov     r14, rax
0x18003d126  test    rax, rax
0x18003d129  jnz     short loc_18003D135
0x18003d12b  mov     rcx, rbx; void *
0x18003d12e  call    ?_Free@CMUILocale@@SAHPEAX@Z; CMUILocale::_Free(void *)
0x18003d133  jmp     short loc_18003D0FB
0x18003d135  mov     rcx, [r12]; Sid
0x18003d139  lea     rax, [rbp+arg_10]
0x18003d13d  mov     [rsp+30h+peUse], rax; peUse
0x18003d142  lea     r8, [rbp+cchName]; cchName
0x18003d146  lea     rax, [rbp+arg_0]
0x18003d14a  mov     r9, r14; ReferencedDomainName
0x18003d14d  mov     rdx, rbx; Name
0x18003d150  mov     [rsp+30h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18003d155  call    cs:__imp_LookupAccountSidLocalW
0x18003d15b  test    eax, eax
0x18003d15d  jnz     short loc_18003D177
0x18003d15f  mov     rcx, rbx; void *
0x18003d162  call    ?_Free@CMUILocale@@SAHPEAX@Z; CMUILocale::_Free(void *)
0x18003d167  mov     rcx, r14; void *
0x18003d16a  call    ?_Free@CMUILocale@@SAHPEAX@Z; CMUILocale::_Free(void *)
0x18003d16f  call    cs:__imp_GetLastError
0x18003d175  jmp     short loc_18003D1AE
0x18003d177  test    r15, r15
0x18003d17a  jz      short loc_18003D181
0x18003d17c  mov     [r15], rbx
0x18003d17f  jmp     short loc_18003D189
0x18003d181  mov     rcx, rbx; void *
0x18003d184  call    ?_Free@CMUILocale@@SAHPEAX@Z; CMUILocale::_Free(void *)
0x18003d189  test    rsi, rsi
0x18003d18c  jz      short loc_18003D193
0x18003d18e  mov     [rsi], r14
0x18003d191  jmp     short loc_18003D19B
0x18003d193  mov     rcx, r14; void *
0x18003d196  call    ?_Free@CMUILocale@@SAHPEAX@Z; CMUILocale::_Free(void *)
0x18003d19b  test    rdi, rdi
0x18003d19e  jz      short loc_18003D1A5
0x18003d1a0  mov     eax, [rbp+arg_10]
0x18003d1a3  mov     [rdi], eax
0x18003d1a5  xor     eax, eax
0x18003d1a7  jmp     short loc_18003D1AE
0x18003d1a9  mov     eax, 0Dh
0x18003d1ae  add     rsp, 30h
0x18003d1b2  pop     r15
0x18003d1b4  pop     r14
0x18003d1b6  pop     r12
0x18003d1b8  pop     rdi
0x18003d1b9  pop     rsi
0x18003d1ba  pop     rbx
0x18003d1bb  pop     rbp
0x18003d1bc  retn
```
