# NSecurityLibrary::TSidUserContext::Initialize(void *,_TOKEN_USER * *)

- ea: `0x140012c80`
- end: `0x140012d45`
- name: `?Initialize@TSidUserContext@NSecurityLibrary@@CAJPEAXPEAPEAU_TOKEN_USER@@@Z`
- size: `197`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, struct _TOKEN_USER **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14001293c`

## callees

- `0x140002174`
- `0x1400112c8`
- `0x140012c80`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140012cc1`
- `KERNEL32!GetLastError` at `0x140012cc1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140012cb7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140012d1b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140012cb7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140012d1b`

## pseudocode

```c
__int64 __fastcall NSecurityLibrary::TSidUserContext::Initialize(HANDLE TokenHandle, LPVOID *a2)
{
  signed int LastError; // eax
  signed int v5; // ebx
  struct _TOKEN_USER *v6; // rax
  NCoreLibrary *v7; // rcx
  DWORD TokenInformationLength; // [rsp+50h] [rbp+18h] BYREF
  DWORD ReturnLength; // [rsp+58h] [rbp+20h] BYREF

  ReturnLength = 0;
  TokenInformationLength = 0;
  if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) )
  {
    return (unsigned int)-2147467259;
  }
  else
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError == 122 )
    {
      v6 = (struct _TOKEN_USER *)operator new[](
                                   TokenInformationLength,
                                   (const struct std::nothrow_t *)&NCoreLibrary::nothrow);
      *a2 = v6;
      v5 = v6 == 0 ? 0x8007000E : 0;
    }
    else if ( LastError > 0 )
    {
      v5 = (unsigned __int16)LastError | 0x80070000;
    }
    if ( v5 >= 0 && !GetTokenInformation(TokenHandle, TokenUser, *a2, TokenInformationLength, &ReturnLength) )
      return (unsigned int)NCoreLibrary::GetLastErrorAsFailHR(v7);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140012c80  mov     rax, rsp
0x140012c83  mov     [rax+8], rbx
0x140012c87  mov     [rax+10h], rsi
0x140012c8b  push    rdi
0x140012c8c  sub     rsp, 30h
0x140012c90  xor     r9d, r9d; TokenInformationLength
0x140012c93  mov     dword ptr [rax+20h], 0
0x140012c9a  mov     dword ptr [rax+18h], 0
0x140012ca1  lea     rax, [rax+18h]
0x140012ca5  mov     rdi, rdx
0x140012ca8  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x140012cad  xor     r8d, r8d; TokenInformation
0x140012cb0  mov     rsi, rcx
0x140012cb3  lea     edx, [r9+1]; TokenInformationClass
0x140012cb7  call    cs:__imp_GetTokenInformation
0x140012cbd  test    eax, eax
0x140012cbf  jnz     short loc_140012D2E
0x140012cc1  call    cs:__imp_GetLastError
0x140012cc7  mov     ebx, eax
0x140012cc9  cmp     eax, 7Ah ; 'z'
0x140012ccc  jnz     short loc_140012CF0
0x140012cce  mov     ecx, [rsp+38h+TokenInformationLength]; unsigned __int64
0x140012cd2  lea     rdx, ?nothrow@NCoreLibrary@@3Unothrow_t@std@@B; struct std::nothrow_t *
0x140012cd9  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x140012cde  mov     [rdi], rax
0x140012ce1  neg     rax
0x140012ce4  sbb     ebx, ebx
0x140012ce6  not     ebx
0x140012ce8  and     ebx, 8007000Eh
0x140012cee  jmp     short loc_140012CFD
0x140012cf0  test    eax, eax
0x140012cf2  jle     short loc_140012CFD
0x140012cf4  movzx   ebx, ax
0x140012cf7  or      ebx, 80070000h
0x140012cfd  test    ebx, ebx
0x140012cff  js      short loc_140012D33
0x140012d01  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x140012d06  lea     rax, [rsp+38h+arg_18]
0x140012d0b  mov     r8, [rdi]; TokenInformation
0x140012d0e  mov     edx, 1; TokenInformationClass
0x140012d13  mov     rcx, rsi; TokenHandle
0x140012d16  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x140012d1b  call    cs:__imp_GetTokenInformation
0x140012d21  test    eax, eax
0x140012d23  jnz     short loc_140012D33
0x140012d25  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x140012d2a  mov     ebx, eax
0x140012d2c  jmp     short loc_140012D33
0x140012d2e  mov     ebx, 80004005h
0x140012d33  mov     rsi, [rsp+38h+arg_8]
0x140012d38  mov     eax, ebx
0x140012d3a  mov     rbx, [rsp+38h+arg_0]
0x140012d3f  add     rsp, 30h
0x140012d43  pop     rdi
0x140012d44  retn
```
