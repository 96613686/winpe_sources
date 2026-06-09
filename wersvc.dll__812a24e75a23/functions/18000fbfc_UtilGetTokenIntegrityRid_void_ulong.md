# UtilGetTokenIntegrityRid(void *,ulong *)

- ea: `0x18000fbfc`
- end: `0x18000fd01`
- name: `?UtilGetTokenIntegrityRid@@YAJPEAXPEAK@Z`
- size: `261`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180025568`

## callees

- `0x180002a00`
- `0x180002ff0`
- `0x18000fbfc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fc4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fc9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fcda`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fc4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fc9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fcda`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000fc3c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000fc92`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000fc3c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000fc92`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18000fcb6`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18000fcb6`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18000fcc4`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18000fcc4`

## pseudocode

```c
__int64 __fastcall UtilGetTokenIntegrityRid(HANDLE TokenHandle, unsigned int *a2)
{
  unsigned int v4; // ebx
  PSID *v5; // rdi
  signed int v6; // eax
  PUCHAR SidSubAuthorityCount; // rax
  signed int LastError; // eax
  DWORD TokenInformationLength; // [rsp+48h] [rbp+10h] BYREF

  if ( a2 )
  {
    TokenInformationLength = 0;
    if ( GetTokenInformation(TokenHandle, TokenIntegrityLevel, 0, 0, &TokenInformationLength) || GetLastError() != 122 )
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v5 = (PSID *)operator new(TokenInformationLength, (const struct std::nothrow_t *)&std::nothrow);
      if ( v5 )
      {
        if ( GetTokenInformation(TokenHandle, TokenIntegrityLevel, v5, TokenInformationLength, &TokenInformationLength) )
        {
          SidSubAuthorityCount = GetSidSubAuthorityCount(*v5);
          *a2 = *GetSidSubAuthority(*v5, (unsigned int)*SidSubAuthorityCount - 1);
          v4 = 0;
        }
        else
        {
          v6 = GetLastError();
          v4 = v6;
          if ( v6 > 0 )
            v4 = (unsigned __int16)v6 | 0x80070000;
        }
        operator delete(v5);
      }
      else
      {
        return (unsigned int)-2147024882;
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v4;
}

```

## disassembly

```asm
0x18000fbfc  mov     [rsp+arg_0], rbx
0x18000fc01  mov     [rsp+arg_10], rsi
0x18000fc06  push    rdi
0x18000fc07  sub     rsp, 30h
0x18000fc0b  mov     rbx, rdx
0x18000fc0e  mov     rsi, rcx
0x18000fc11  test    rdx, rdx
0x18000fc14  jnz     short loc_18000FC20
0x18000fc16  mov     ebx, 80070057h
0x18000fc1b  jmp     loc_18000FCEF
0x18000fc20  xor     r9d, r9d; TokenInformationLength
0x18000fc23  mov     [rsp+38h+TokenInformationLength], 0
0x18000fc2b  lea     rax, [rsp+38h+TokenInformationLength]
0x18000fc30  xor     r8d, r8d; TokenInformation
0x18000fc33  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18000fc38  lea     edx, [r9+19h]; TokenInformationClass
0x18000fc3c  call    cs:__imp_GetTokenInformation
0x18000fc42  test    eax, eax
0x18000fc44  jnz     loc_18000FCDA
0x18000fc4a  call    cs:__imp_GetLastError
0x18000fc50  cmp     eax, 7Ah ; 'z'
0x18000fc53  jnz     loc_18000FCDA
0x18000fc59  mov     ecx, [rsp+38h+TokenInformationLength]; unsigned __int64
0x18000fc5d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000fc64  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000fc69  mov     rdi, rax
0x18000fc6c  test    rax, rax
0x18000fc6f  jnz     short loc_18000FC78
0x18000fc71  mov     ebx, 8007000Eh
0x18000fc76  jmp     short loc_18000FCEF
0x18000fc78  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x18000fc7d  lea     rax, [rsp+38h+TokenInformationLength]
0x18000fc82  mov     r8, rdi; TokenInformation
0x18000fc85  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18000fc8a  mov     edx, 19h; TokenInformationClass
0x18000fc8f  mov     rcx, rsi; TokenHandle
0x18000fc92  call    cs:__imp_GetTokenInformation
0x18000fc98  test    eax, eax
0x18000fc9a  jnz     short loc_18000FCB3
0x18000fc9c  call    cs:__imp_GetLastError
0x18000fca2  mov     ebx, eax
0x18000fca4  test    eax, eax
0x18000fca6  jle     short loc_18000FCD0
0x18000fca8  movzx   ebx, ax
0x18000fcab  or      ebx, 80070000h
0x18000fcb1  jmp     short loc_18000FCD0
0x18000fcb3  mov     rcx, [rdi]; pSid
0x18000fcb6  call    cs:__imp_GetSidSubAuthorityCount
0x18000fcbc  mov     rcx, [rdi]; pSid
0x18000fcbf  movzx   edx, byte ptr [rax]
0x18000fcc2  dec     edx; nSubAuthority
0x18000fcc4  call    cs:__imp_GetSidSubAuthority
0x18000fcca  mov     edx, [rax]
0x18000fccc  mov     [rbx], edx
0x18000fcce  xor     ebx, ebx
0x18000fcd0  mov     rcx, rdi; Block
0x18000fcd3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000fcd8  jmp     short loc_18000FCEF
0x18000fcda  call    cs:__imp_GetLastError
0x18000fce0  mov     ebx, eax
0x18000fce2  test    eax, eax
0x18000fce4  jle     short loc_18000FCEF
0x18000fce6  movzx   ebx, ax
0x18000fce9  or      ebx, 80070000h
0x18000fcef  mov     rsi, [rsp+38h+arg_10]
0x18000fcf4  mov     eax, ebx
0x18000fcf6  mov     rbx, [rsp+38h+arg_0]
0x18000fcfb  add     rsp, 30h
0x18000fcff  pop     rdi
0x18000fd00  retn
```
