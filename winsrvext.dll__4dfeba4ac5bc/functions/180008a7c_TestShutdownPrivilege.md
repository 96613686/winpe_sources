# TestShutdownPrivilege

- ea: `0x180008a7c`
- end: `0x180008c09`
- name: `TestShutdownPrivilege`
- size: `397`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800080b0`

## callees

- `0x180006fd4`
- `0x180008a7c`
- `0x1800138f0`

## import_xrefs

- `ntdll!RtlFreeSid` at `0x180008bd6`
- `ntdll!RtlFreeSid` at `0x180008bd6`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180008af5`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180008af5`
- `ntdll!NtClose` at `0x180008bc1`
- `ntdll!NtClose` at `0x180008bc1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180008b6e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180008b9f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180008b6e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180008b9f`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180008b14`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180008b14`

## pseudocode

```c
__int64 __fastcall TestShutdownPrivilege(HANDLE TokenHandle)
{
  unsigned int v2; // edi
  HANDLE Handle; // [rsp+68h] [rbp+17h] BYREF
  WINBOOL IsMember; // [rsp+70h] [rbp+1Fh] BYREF
  int TokenInformation; // [rsp+74h] [rbp+23h] BYREF
  DWORD ReturnLength; // [rsp+78h] [rbp+27h] BYREF
  PSID SidToCheck; // [rsp+80h] [rbp+2Fh] BYREF
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+88h] [rbp+37h] BYREF

  Handle = HANDLE_FLAG_PROTECT_FROM_CLOSE|HANDLE_FLAG_INHERIT|0x10;
  IsMember = 0;
  v2 = 0;
  SidToCheck = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  if ( RtlAllocateAndInitializeSid(&IdentifierAuthority, 1u, 2u, 0, 0, 0, 0, 0, 0, 0, &SidToCheck) >= 0 )
  {
    if ( CheckTokenMembership(TokenHandle, SidToCheck, &IsMember) )
    {
      if ( IsMember )
        Handle = (HANDLE)24;
      v2 = IsPrivilegePresentOnToken(TokenHandle);
      if ( !v2 )
      {
        TokenInformation = 0;
        ReturnLength = 0;
        if ( GetTokenInformation(TokenHandle, TokenElevationType, &TokenInformation, 4u, &ReturnLength) )
        {
          if ( TokenInformation == 3 )
          {
            Handle = 0;
            if ( GetTokenInformation(TokenHandle, TokenLinkedToken, &Handle, 8u, &ReturnLength) )
            {
              v2 = IsPrivilegePresentOnToken(Handle);
              NtClose(Handle);
            }
          }
        }
      }
    }
    if ( SidToCheck )
      RtlFreeSid(SidToCheck);
  }
  return v2;
}

```

## disassembly

```asm
0x180008a7c  mov     r11, rsp
0x180008a7f  mov     [r11+10h], rbx
0x180008a83  mov     [r11+18h], rsi
0x180008a87  push    rbp
0x180008a88  push    rdi
0x180008a89  push    r14
0x180008a8b  lea     rbp, [r11-5Fh]
0x180008a8f  sub     rsp, 90h
0x180008a96  mov     rax, cs:__security_cookie
0x180008a9d  xor     rax, rsp
0x180008aa0  mov     [rbp+57h+var_18], rax
0x180008aa4  xor     r14d, r14d
0x180008aa7  mov     [rbp+57h+Handle], 13h
0x180008aaf  lea     rax, [rbp+57h+SidToCheck]
0x180008ab3  mov     [rbp+57h+IsMember], r14d
0x180008ab7  mov     [r11-58h], rax
0x180008abb  mov     rsi, rcx
0x180008abe  mov     [r11-60h], r14d
0x180008ac2  lea     rcx, [rbp+57h+IdentifierAuthority]; IdentifierAuthority
0x180008ac6  mov     [r11-68h], r14d
0x180008aca  lea     r8d, [r14+2]; SubAuthority0
0x180008ace  mov     [r11-70h], r14d
0x180008ad2  xor     r9d, r9d; SubAuthority1
0x180008ad5  mov     [r11-78h], r14d
0x180008ad9  mov     dl, 1; SubAuthorityCount
0x180008adb  mov     [r11-80h], r14d
0x180008adf  mov     edi, r14d
0x180008ae2  mov     [rsp+0A0h+SubAuthority2], r14d; SubAuthority2
0x180008ae7  mov     [rbp+57h+SidToCheck], r14
0x180008aeb  mov     dword ptr [rbp+57h+IdentifierAuthority.Value], r14d
0x180008aef  mov     word ptr [rbp+57h+IdentifierAuthority.Value+4], 500h
0x180008af5  call    cs:__imp_RtlAllocateAndInitializeSid
0x180008afc  nop     dword ptr [rax+rax+00h]
0x180008b01  test    eax, eax
0x180008b03  js      loc_180008BE2
0x180008b09  mov     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x180008b0d  lea     r8, [rbp+57h+IsMember]; IsMember
0x180008b11  mov     rcx, rsi; TokenHandle
0x180008b14  call    cs:__imp_CheckTokenMembership
0x180008b1b  nop     dword ptr [rax+rax+00h]
0x180008b20  test    eax, eax
0x180008b22  jz      loc_180008BCD
0x180008b28  mov     rbx, [rbp+57h+Handle]
0x180008b2c  cmp     [rbp+57h+IsMember], r14d
0x180008b30  jz      short loc_180008B3E
0x180008b32  mov     [rbp+57h+Handle], 18h
0x180008b3a  mov     rbx, [rbp+57h+Handle]
0x180008b3e  mov     rdx, rbx
0x180008b41  mov     rcx, rsi; TokenHandle
0x180008b44  call    IsPrivilegePresentOnToken
0x180008b49  mov     edi, eax
0x180008b4b  test    eax, eax
0x180008b4d  jnz     short loc_180008BCD
0x180008b4f  lea     rax, [rbp+57h+ReturnLength]
0x180008b53  mov     [rbp+57h+TokenInformation], r14d
0x180008b57  lea     r9d, [rdi+4]; TokenInformationLength
0x180008b5b  mov     qword ptr [rsp+0A0h+SubAuthority2], rax; ReturnLength
0x180008b60  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x180008b64  mov     [rbp+57h+ReturnLength], r14d
0x180008b68  lea     edx, [rdi+12h]; TokenInformationClass
0x180008b6b  mov     rcx, rsi; TokenHandle
0x180008b6e  call    cs:__imp_GetTokenInformation
0x180008b75  nop     dword ptr [rax+rax+00h]
0x180008b7a  test    eax, eax
0x180008b7c  jz      short loc_180008BCD
0x180008b7e  cmp     [rbp+57h+TokenInformation], 3
0x180008b82  jnz     short loc_180008BCD
0x180008b84  lea     rax, [rbp+57h+ReturnLength]
0x180008b88  mov     [rbp+57h+Handle], r14
0x180008b8c  lea     r9d, [rdi+8]; TokenInformationLength
0x180008b90  mov     qword ptr [rsp+0A0h+SubAuthority2], rax; ReturnLength
0x180008b95  lea     r8, [rbp+57h+Handle]; TokenInformation
0x180008b99  mov     rcx, rsi; TokenHandle
0x180008b9c  lea     edx, [rdi+13h]; TokenInformationClass
0x180008b9f  call    cs:__imp_GetTokenInformation
0x180008ba6  nop     dword ptr [rax+rax+00h]
0x180008bab  test    eax, eax
0x180008bad  jz      short loc_180008BCD
0x180008baf  mov     rcx, [rbp+57h+Handle]; TokenHandle
0x180008bb3  mov     rdx, rbx
0x180008bb6  call    IsPrivilegePresentOnToken
0x180008bbb  mov     rcx, [rbp+57h+Handle]; Handle
0x180008bbf  mov     edi, eax
0x180008bc1  call    cs:__imp_NtClose
0x180008bc8  nop     dword ptr [rax+rax+00h]
0x180008bcd  mov     rcx, [rbp+57h+SidToCheck]; Sid
0x180008bd1  test    rcx, rcx
0x180008bd4  jz      short loc_180008BE2
0x180008bd6  call    cs:__imp_RtlFreeSid
0x180008bdd  nop     dword ptr [rax+rax+00h]
0x180008be2  mov     eax, edi
0x180008be4  mov     rcx, [rbp+57h+var_18]
0x180008be8  xor     rcx, rsp; StackCookie
0x180008beb  call    __security_check_cookie
0x180008bf0  lea     r11, [rsp+0A0h+var_10]
0x180008bf8  mov     rbx, [r11+28h]
0x180008bfc  mov     rsi, [r11+30h]
0x180008c00  mov     rsp, r11
0x180008c03  pop     r14
0x180008c05  pop     rdi
0x180008c06  pop     rbp
0x180008c07  retn
```
