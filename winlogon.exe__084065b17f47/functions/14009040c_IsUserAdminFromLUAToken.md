# IsUserAdminFromLUAToken

- ea: `0x14009040c`
- end: `0x14009052a`
- name: `IsUserAdminFromLUAToken`
- size: `286`
- prototype: `__int64 __fastcall(HANDLE hExistingToken)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14008ff64`

## callees

- `0x1400437c0`
- `0x14008ee4c`
- `0x14009040c`
- `0x1400994dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400904f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400904fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140090508`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400904f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400904fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140090508`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x140090452`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x140090452`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400904c2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400904c2`

## pseudocode

```c
__int64 __fastcall IsUserAdminFromLUAToken(HANDLE hExistingToken, _DWORD *a2)
{
  signed int LastError; // ebx
  DWORD ReturnLength; // [rsp+58h] [rbp+28h] BYREF
  HANDLE TokenInformation; // [rsp+60h] [rbp+30h] BYREF
  HANDLE TokenHandle; // [rsp+68h] [rbp+38h] BYREF

  *a2 = 0;
  TokenHandle = 0;
  CAutoPtr<void *,&void HandleClose(void *)>::Free(&TokenHandle);
  if ( DuplicateTokenEx(hExistingToken, 0xEu, 0, SecurityImpersonation, TokenImpersonation, &TokenHandle) )
  {
    ReturnLength = 0;
    LODWORD(TokenInformation) = 0;
    LastError = LUAIsElevatedToken(TokenHandle);
    if ( LastError >= 0 )
    {
      if ( ReturnLength )
      {
        *a2 = CheckAdminMembershipFromLUAToken(TokenHandle);
      }
      else
      {
        TokenInformation = 0;
        ReturnLength = 8;
        CAutoPtr<void *,&void HandleClose(void *)>::Free(&TokenInformation);
        if ( GetTokenInformation(TokenHandle, TokenLinkedToken, &TokenInformation, 8u, &ReturnLength)
          && TokenInformation )
        {
          *a2 = CheckAdminMembershipFromLUAToken(TokenInformation);
        }
        CAutoPtr<void *,&void HandleClose(void *)>::Free(&TokenInformation);
      }
    }
  }
  else if ( (int)GetLastError() > 0 )
  {
    LastError = (unsigned __int16)GetLastError() | 0xC0070000;
  }
  else
  {
    LastError = GetLastError();
  }
  CAutoPtr<void *,&void HandleClose(void *)>::Free(&TokenHandle);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x14009040c  push    rbp
0x14009040e  push    rbx
0x14009040f  push    rdi
0x140090410  mov     rbp, rsp
0x140090413  sub     rsp, 30h
0x140090417  mov     rbx, rcx
0x14009041a  mov     dword ptr [rdx], 0
0x140090420  lea     rcx, [rbp+TokenHandle]
0x140090424  mov     [rbp+TokenHandle], 0
0x14009042c  mov     rdi, rdx
0x14009042f  call    ?Free@?$CAutoPtr@PEAX$1?HandleClose@@YAXPEAX@Z@@AEAAXXZ; CAutoPtr<void *,&HandleClose(void *)>::Free(void)
0x140090434  mov     r9d, 2; ImpersonationLevel
0x14009043a  lea     rax, [rbp+TokenHandle]
0x14009043e  mov     [rsp+30h+phNewToken], rax; phNewToken
0x140090443  xor     r8d, r8d; lpTokenAttributes
0x140090446  mov     rcx, rbx; hExistingToken
0x140090449  mov     [rsp+30h+TokenType], r9d; TokenType
0x14009044e  lea     edx, [r9+0Ch]; dwDesiredAccess
0x140090452  call    cs:__imp_DuplicateTokenEx
0x140090458  test    eax, eax
0x14009045a  jz      loc_1400904F4
0x140090460  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x140090464  lea     r8, [rbp+TokenInformation]
0x140090468  lea     rdx, [rbp+ReturnLength]
0x14009046c  mov     [rbp+ReturnLength], 0
0x140090473  mov     dword ptr [rbp+TokenInformation], 0
0x14009047a  call    LUAIsElevatedToken
0x14009047f  mov     ebx, eax
0x140090481  test    eax, eax
0x140090483  js      loc_140090517
0x140090489  cmp     [rbp+ReturnLength], 0
0x14009048d  jnz     short loc_1400904E7
0x14009048f  lea     rcx, [rbp+TokenInformation]
0x140090493  mov     [rbp+TokenInformation], 0
0x14009049b  mov     [rbp+ReturnLength], 8
0x1400904a2  call    ?Free@?$CAutoPtr@PEAX$1?HandleClose@@YAXPEAX@Z@@AEAAXXZ; CAutoPtr<void *,&HandleClose(void *)>::Free(void)
0x1400904a7  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1400904ab  lea     rax, [rbp+ReturnLength]
0x1400904af  mov     r9d, 8; TokenInformationLength
0x1400904b5  mov     qword ptr [rsp+30h+TokenType], rax; ReturnLength
0x1400904ba  lea     r8, [rbp+TokenInformation]; TokenInformation
0x1400904be  lea     edx, [r9+0Bh]; TokenInformationClass
0x1400904c2  call    cs:__imp_GetTokenInformation
0x1400904c8  test    eax, eax
0x1400904ca  jz      short loc_1400904DC
0x1400904cc  mov     rcx, [rbp+TokenInformation]; ExistingTokenHandle
0x1400904d0  test    rcx, rcx
0x1400904d3  jz      short loc_1400904DC
0x1400904d5  call    CheckAdminMembershipFromLUAToken
0x1400904da  mov     [rdi], eax
0x1400904dc  lea     rcx, [rbp+TokenInformation]
0x1400904e0  call    ?Free@?$CAutoPtr@PEAX$1?HandleClose@@YAXPEAX@Z@@AEAAXXZ; CAutoPtr<void *,&HandleClose(void *)>::Free(void)
0x1400904e5  jmp     short loc_140090517
0x1400904e7  mov     rcx, [rbp+TokenHandle]; ExistingTokenHandle
0x1400904eb  call    CheckAdminMembershipFromLUAToken
0x1400904f0  mov     [rdi], eax
0x1400904f2  jmp     short loc_140090517
0x1400904f4  call    cs:__imp_GetLastError
0x1400904fa  test    eax, eax
0x1400904fc  jg      short loc_140090508
0x1400904fe  call    cs:__imp_GetLastError
0x140090504  mov     ebx, eax
0x140090506  jmp     short loc_140090517
0x140090508  call    cs:__imp_GetLastError
0x14009050e  movzx   ebx, ax
0x140090511  or      ebx, 0C0070000h
0x140090517  lea     rcx, [rbp+TokenHandle]
0x14009051b  call    ?Free@?$CAutoPtr@PEAX$1?HandleClose@@YAXPEAX@Z@@AEAAXXZ; CAutoPtr<void *,&HandleClose(void *)>::Free(void)
0x140090520  mov     eax, ebx
0x140090522  add     rsp, 30h
0x140090526  pop     rdi
0x140090527  pop     rbx
0x140090528  pop     rbp
0x140090529  retn
```
