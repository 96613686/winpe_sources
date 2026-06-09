# TestShutdownPrivilege(void *)

- ea: `0x18006081c`
- end: `0x18006091a`
- name: `?TestShutdownPrivilege@@YAHPEAX@Z`
- size: `254`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800695a0`

## callees

- `0x18006081c`
- `0x180060920`
- `0x180096e00`

## import_xrefs

- `ntdll!RtlFreeSid` at `0x180060912`
- `ntdll!RtlFreeSid` at `0x180060912`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180060892`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180060892`
- `ntdll!NtClose` at `0x1800a0d36`
- `ntdll!NtClose` at `0x1800a0d36`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800a0ce0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800a0d16`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800a0ce0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800a0d16`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800608ab`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800608ab`

## pseudocode

```c
__int64 __fastcall TestShutdownPrivilege(HANDLE TokenHandle)
{
  struct _LUID v2; // rbx
  unsigned int v3; // edi
  HANDLE Handle; // [rsp+68h] [rbp+17h] BYREF
  WINBOOL IsMember; // [rsp+70h] [rbp+1Fh] BYREF
  int TokenInformation; // [rsp+74h] [rbp+23h] BYREF
  DWORD ReturnLength; // [rsp+78h] [rbp+27h] BYREF
  PSID SidToCheck; // [rsp+80h] [rbp+2Fh] BYREF
  _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+88h] [rbp+37h] BYREF

  Handle = HANDLE_FLAG_PROTECT_FROM_CLOSE|HANDLE_FLAG_INHERIT|0x10;
  IsMember = 0;
  SidToCheck = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  if ( RtlAllocateAndInitializeSid(&IdentifierAuthority, 1u, 2u, 0, 0, 0, 0, 0, 0, 0, &SidToCheck) < 0 )
  {
    return 0;
  }
  else
  {
    v2 = (struct _LUID)Handle;
    if ( CheckTokenMembership(TokenHandle, SidToCheck, &IsMember) && IsMember )
    {
      Handle = (HANDLE)24;
      v2 = (struct _LUID)24LL;
    }
    v3 = IsPrivilegePresentOnToken(TokenHandle, v2);
    if ( !v3 )
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
            v3 = IsPrivilegePresentOnToken(Handle, v2);
            NtClose(Handle);
          }
        }
      }
    }
    if ( SidToCheck )
      RtlFreeSid(SidToCheck);
  }
  return v3;
}

```

## disassembly

```asm
0x18006081c  mov     r11, rsp
0x18006081f  mov     [r11+10h], rbx
0x180060823  mov     [r11+18h], rsi
0x180060827  push    rbp
0x180060828  push    rdi
0x180060829  push    r14
0x18006082b  lea     rbp, [r11-5Fh]
0x18006082f  sub     rsp, 90h
0x180060836  mov     rax, cs:__security_cookie
0x18006083d  xor     rax, rsp
0x180060840  mov     [rbp+57h+var_18], rax
0x180060844  xor     r14d, r14d
0x180060847  mov     [rbp+57h+Handle], 13h
0x18006084f  lea     rax, [rbp+57h+SidToCheck]
0x180060853  mov     [rbp+57h+IsMember], r14d
0x180060857  mov     [r11-58h], rax
0x18006085b  mov     rsi, rcx
0x18006085e  mov     [r11-60h], r14d
0x180060862  lea     rcx, [rbp+57h+IdentifierAuthority]; IdentifierAuthority
0x180060866  mov     [r11-68h], r14d
0x18006086a  lea     r8d, [r14+2]; SubAuthority0
0x18006086e  mov     [r11-70h], r14d
0x180060872  xor     r9d, r9d; SubAuthority1
0x180060875  mov     [r11-78h], r14d
0x180060879  mov     dl, 1; SubAuthorityCount
0x18006087b  mov     [r11-80h], r14d
0x18006087f  mov     [rsp+0A0h+SubAuthority2], r14d; SubAuthority2
0x180060884  mov     [rbp+57h+SidToCheck], r14
0x180060888  mov     dword ptr [rbp+57h+IdentifierAuthority.Value], r14d
0x18006088c  mov     word ptr [rbp+57h+IdentifierAuthority.Value+4], 500h
0x180060892  call    cs:__imp_RtlAllocateAndInitializeSid
0x180060898  test    eax, eax
0x18006089a  js      short loc_1800608F9
0x18006089c  mov     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x1800608a0  lea     r8, [rbp+57h+IsMember]; IsMember
0x1800608a4  mov     rbx, [rbp+57h+Handle]
0x1800608a8  mov     rcx, rsi; TokenHandle
0x1800608ab  call    cs:__imp_CheckTokenMembership
0x1800608b1  test    eax, eax
0x1800608b3  jnz     short loc_1800608FE
0x1800608b5  mov     rdx, rbx; struct _LUID
0x1800608b8  mov     rcx, rsi; TokenHandle
0x1800608bb  call    ?IsPrivilegePresentOnToken@@YAHPEAXU_LUID@@@Z; IsPrivilegePresentOnToken(void *,_LUID)
0x1800608c0  mov     edi, eax
0x1800608c2  test    eax, eax
0x1800608c4  jz      loc_1800A0CBE
0x1800608ca  mov     rcx, [rbp+57h+SidToCheck]; Sid
0x1800608ce  test    rcx, rcx
0x1800608d1  jnz     short loc_180060912
0x1800608d3  mov     eax, edi
0x1800608d5  mov     rcx, [rbp+57h+var_18]
0x1800608d9  xor     rcx, rsp; StackCookie
0x1800608dc  call    __security_check_cookie
0x1800608e1  lea     r11, [rsp+0A0h+var_10]
0x1800608e9  mov     rbx, [r11+28h]
0x1800608ed  mov     rsi, [r11+30h]
0x1800608f1  mov     rsp, r11
0x1800608f4  pop     r14
0x1800608f6  pop     rdi
0x1800608f7  pop     rbp
0x1800608f8  retn
0x1800608f9  mov     edi, r14d
0x1800608fc  jmp     short loc_1800608D3
0x1800608fe  cmp     [rbp+57h+IsMember], r14d
0x180060902  jz      short loc_1800608B5
0x180060904  mov     [rbp+57h+Handle], 18h
0x18006090c  mov     rbx, [rbp+57h+Handle]
0x180060910  jmp     short loc_1800608B5
0x180060912  call    cs:__imp_RtlFreeSid
0x180060918  jmp     short loc_1800608D3
0x1800a0cbe  mov     r9d, 4; TokenInformationLength
0x1800a0cc4  mov     [rbp+57h+TokenInformation], r14d
0x1800a0cc8  lea     rax, [rbp+57h+ReturnLength]
0x1800a0ccc  mov     [rbp+57h+ReturnLength], r14d
0x1800a0cd0  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x1800a0cd4  mov     qword ptr [rsp+0A0h+SubAuthority2], rax; ReturnLength
0x1800a0cd9  mov     rcx, rsi; TokenHandle
0x1800a0cdc  lea     edx, [r9+0Eh]; TokenInformationClass
0x1800a0ce0  call    cs:__imp_GetTokenInformation
0x1800a0ce6  test    eax, eax
0x1800a0ce8  jz      loc_1800608CA
0x1800a0cee  cmp     [rbp+57h+TokenInformation], 3
0x1800a0cf2  jnz     loc_1800608CA
0x1800a0cf8  mov     r9d, 8; TokenInformationLength
0x1800a0cfe  mov     [rbp+57h+Handle], r14
0x1800a0d02  lea     rax, [rbp+57h+ReturnLength]
0x1800a0d06  mov     rcx, rsi; TokenHandle
0x1800a0d09  lea     r8, [rbp+57h+Handle]; TokenInformation
0x1800a0d0d  mov     qword ptr [rsp+0A0h+SubAuthority2], rax; ReturnLength
0x1800a0d12  lea     edx, [r9+0Bh]; TokenInformationClass
0x1800a0d16  call    cs:__imp_GetTokenInformation
0x1800a0d1c  test    eax, eax
0x1800a0d1e  jz      loc_1800608CA
0x1800a0d24  mov     rcx, [rbp+57h+Handle]; TokenHandle
0x1800a0d28  mov     rdx, rbx; struct _LUID
0x1800a0d2b  call    ?IsPrivilegePresentOnToken@@YAHPEAXU_LUID@@@Z; IsPrivilegePresentOnToken(void *,_LUID)
0x1800a0d30  mov     rcx, [rbp+57h+Handle]; Handle
0x1800a0d34  mov     edi, eax
0x1800a0d36  call    cs:__imp_NtClose
0x1800a0d3c  nop
0x1800a0d3d  jmp     loc_1800608CA
```
