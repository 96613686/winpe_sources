# IsAdmin(void *)

- ea: `0x14008abcc`
- end: `0x14008aeb3`
- name: `?IsAdmin@@YA_NPEAX@Z`
- size: `743`
- prototype: `bool __fastcall(HANDLE hExistingToken)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14004f0b4`

## callees

- `0x1400057f4`
- `0x14003ddec`
- `0x14004bb00`
- `0x140053720`
- `0x14008abcc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14008ac5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14008acb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14008ad66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14008adf6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14008ae3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14008ac5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14008acb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14008ad66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14008adf6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14008ae3b`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x14008ac27`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x14008adca`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x14008ac27`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x14008adca`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x14008acf5`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x14008ae0f`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x14008acf5`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x14008ae0f`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x14008ac80`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x14008ac80`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14008ad3a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14008ad3a`

## pseudocode

```c
bool __fastcall IsAdmin(HANDLE hExistingToken)
{
  DWORD LastError; // eax
  __int64 v3; // rdx
  bool v4; // bl
  DWORD v5; // eax
  DWORD v6; // eax
  __int64 v7; // rdx
  WINBOOL IsMember; // [rsp+30h] [rbp-39h] BYREF
  HANDLE TokenInformation; // [rsp+38h] [rbp-31h] BYREF
  DWORD cbSid; // [rsp+40h] [rbp-29h] BYREF
  HANDLE phNewToken; // [rsp+48h] [rbp-21h] BYREF
  HANDLE TokenHandle[2]; // [rsp+50h] [rbp-19h] BYREF
  _BYTE pSid[80]; // [rsp+60h] [rbp-9h] BYREF

  TokenHandle[0] = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    TokenHandle,
    0);
  if ( !DuplicateTokenEx(hExistingToken, 0x2000Cu, 0, SecurityImpersonation, TokenImpersonation, TokenHandle) )
  {
    if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_21;
    }
    LastError = GetLastError();
    v3 = 132;
    goto LABEL_11;
  }
  cbSid = 68;
  if ( !CreateWellKnownSid(WinBuiltinAdministratorsSid, 0, pSid, &cbSid) )
  {
    if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_21;
    }
    LastError = GetLastError();
    v3 = 133;
LABEL_11:
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v3, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids, LastError);
LABEL_21:
    v4 = 0;
    goto LABEL_35;
  }
  IsMember = 0;
  if ( !CheckTokenMembership(TokenHandle[0], pSid, &IsMember) || !IsMember )
  {
    TokenInformation = 0;
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &TokenInformation,
      0);
    if ( !GetTokenInformation(TokenHandle[0], TokenLinkedToken, &TokenInformation, 8u, &cbSid) )
    {
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v5 = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 134, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids, v5);
      }
      goto LABEL_20;
    }
    phNewToken = 0;
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &phNewToken,
      0);
    if ( DuplicateTokenEx(TokenInformation, 0x2000Cu, 0, SecurityImpersonation, TokenImpersonation, &phNewToken) )
    {
      if ( CheckTokenMembership(phNewToken, pSid, &IsMember) )
      {
        v4 = IsMember != 0;
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenInformation);
        goto LABEL_35;
      }
      if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_33;
      }
      v6 = GetLastError();
      v7 = 136;
    }
    else
    {
      if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_33;
      }
      v6 = GetLastError();
      v7 = 135;
    }
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids, v6);
LABEL_33:
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
LABEL_20:
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenInformation);
    goto LABEL_21;
  }
  v4 = 1;
LABEL_35:
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(TokenHandle);
  return v4;
}

```

## disassembly

```asm
0x14008abcc  mov     [rsp-8+arg_8], rbx
0x14008abd1  mov     [rsp-8+arg_10], rsi
0x14008abd6  push    rbp
0x14008abd7  lea     rbp, [rsp-57h]
0x14008abdc  sub     rsp, 0C0h
0x14008abe3  mov     rax, cs:__security_cookie
0x14008abea  xor     rax, rsp
0x14008abed  mov     [rbp+57h+var_10], rax
0x14008abf1  mov     rbx, rcx
0x14008abf4  mov     [rbp+57h+TokenHandle], 0
0x14008abfc  lea     rcx, [rbp+57h+TokenHandle]
0x14008ac00  xor     edx, edx
0x14008ac02  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x14008ac07  lea     rax, [rbp+57h+TokenHandle]
0x14008ac0b  mov     esi, 2
0x14008ac10  mov     [rsp+0C0h+phNewToken], rax; phNewToken
0x14008ac15  mov     r9d, esi; ImpersonationLevel
0x14008ac18  xor     r8d, r8d; lpTokenAttributes
0x14008ac1b  mov     [rsp+0C0h+TokenType], esi; TokenType
0x14008ac1f  mov     edx, 2000Ch; dwDesiredAccess
0x14008ac24  mov     rcx, rbx; hExistingToken
0x14008ac27  call    cs:__imp_DuplicateTokenEx
0x14008ac2d  test    eax, eax
0x14008ac2f  jnz     short loc_14008AC6C
0x14008ac31  mov     rcx, cs:WPP_GLOBAL_Control
0x14008ac38  lea     rax, WPP_GLOBAL_Control
0x14008ac3f  cmp     rcx, rax
0x14008ac42  jz      loc_14008AD94
0x14008ac48  test    dword ptr [rcx+1Ch], 1000h
0x14008ac4f  jz      loc_14008AD94
0x14008ac55  cmp     [rcx+19h], sil
0x14008ac59  jb      loc_14008AD94
0x14008ac5f  call    cs:__imp_GetLastError
0x14008ac65  mov     edx, 84h
0x14008ac6a  jmp     short loc_14008ACC3
0x14008ac6c  xor     edx, edx; DomainSid
0x14008ac6e  mov     [rbp+57h+cbSid], 44h ; 'D'
0x14008ac75  lea     r9, [rbp+57h+cbSid]; cbSid
0x14008ac79  lea     r8, [rbp+57h+pSid]; pSid
0x14008ac7d  lea     ecx, [rdx+1Ah]; WellKnownSidType
0x14008ac80  call    cs:__imp_CreateWellKnownSid
0x14008ac86  test    eax, eax
0x14008ac88  jnz     short loc_14008ACE2
0x14008ac8a  mov     rcx, cs:WPP_GLOBAL_Control
0x14008ac91  lea     rax, WPP_GLOBAL_Control
0x14008ac98  cmp     rcx, rax
0x14008ac9b  jz      loc_14008AD94
0x14008aca1  test    dword ptr [rcx+1Ch], 1000h
0x14008aca8  jz      loc_14008AD94
0x14008acae  cmp     [rcx+19h], sil
0x14008acb2  jb      loc_14008AD94
0x14008acb8  call    cs:__imp_GetLastError
0x14008acbe  mov     edx, 85h
0x14008acc3  mov     rcx, cs:WPP_GLOBAL_Control
0x14008acca  lea     r8, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids
0x14008acd1  mov     r9d, eax
0x14008acd4  mov     rcx, [rcx+10h]
0x14008acd8  call    WPP_SF_d
0x14008acdd  jmp     loc_14008AD94
0x14008ace2  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x14008ace6  lea     r8, [rbp+57h+IsMember]; IsMember
0x14008acea  lea     rdx, [rbp+57h+pSid]; SidToCheck
0x14008acee  mov     [rbp+57h+IsMember], 0
0x14008acf5  call    cs:__imp_CheckTokenMembership
0x14008acfb  test    eax, eax
0x14008acfd  jz      short loc_14008AD0C
0x14008acff  cmp     [rbp+57h+IsMember], 0
0x14008ad03  jz      short loc_14008AD0C
0x14008ad05  mov     bl, 1
0x14008ad07  jmp     loc_14008AE87
0x14008ad0c  xor     edx, edx
0x14008ad0e  mov     [rbp+57h+TokenInformation], 0
0x14008ad16  lea     rcx, [rbp+57h+TokenInformation]
0x14008ad1a  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x14008ad1f  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x14008ad23  lea     rax, [rbp+57h+cbSid]
0x14008ad27  mov     r9d, 8; TokenInformationLength
0x14008ad2d  mov     qword ptr [rsp+0C0h+TokenType], rax; ReturnLength
0x14008ad32  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x14008ad36  lea     edx, [r9+0Bh]; TokenInformationClass
0x14008ad3a  call    cs:__imp_GetTokenInformation
0x14008ad40  test    eax, eax
0x14008ad42  jnz     short loc_14008AD9B
0x14008ad44  mov     rcx, cs:WPP_GLOBAL_Control
0x14008ad4b  lea     rax, WPP_GLOBAL_Control
0x14008ad52  cmp     rcx, rax
0x14008ad55  jz      short loc_14008AD8B
0x14008ad57  test    dword ptr [rcx+1Ch], 1000h
0x14008ad5e  jz      short loc_14008AD8B
0x14008ad60  cmp     [rcx+19h], sil
0x14008ad64  jb      short loc_14008AD8B
0x14008ad66  call    cs:__imp_GetLastError
0x14008ad6c  mov     rcx, cs:WPP_GLOBAL_Control
0x14008ad73  lea     r8, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids
0x14008ad7a  mov     edx, 86h
0x14008ad7f  mov     r9d, eax
0x14008ad82  mov     rcx, [rcx+10h]
0x14008ad86  call    WPP_SF_d
0x14008ad8b  lea     rcx, [rbp+57h+TokenInformation]
0x14008ad8f  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x14008ad94  xor     bl, bl
0x14008ad96  jmp     loc_14008AE87
0x14008ad9b  xor     edx, edx
0x14008ad9d  mov     [rbp+57h+var_78], 0
0x14008ada5  lea     rcx, [rbp+57h+var_78]
0x14008ada9  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x14008adae  mov     rcx, [rbp+57h+TokenInformation]; hExistingToken
0x14008adb2  lea     rax, [rbp+57h+var_78]
0x14008adb6  mov     [rsp+0C0h+phNewToken], rax; phNewToken
0x14008adbb  mov     r9d, esi; ImpersonationLevel
0x14008adbe  xor     r8d, r8d; lpTokenAttributes
0x14008adc1  mov     [rsp+0C0h+TokenType], esi; TokenType
0x14008adc5  mov     edx, 2000Ch; dwDesiredAccess
0x14008adca  call    cs:__imp_DuplicateTokenEx
0x14008add0  test    eax, eax
0x14008add2  jnz     short loc_14008AE03
0x14008add4  mov     rcx, cs:WPP_GLOBAL_Control
0x14008addb  lea     rax, WPP_GLOBAL_Control
0x14008ade2  cmp     rcx, rax
0x14008ade5  jz      short loc_14008AE60
0x14008ade7  test    dword ptr [rcx+1Ch], 1000h
0x14008adee  jz      short loc_14008AE60
0x14008adf0  cmp     [rcx+19h], sil
0x14008adf4  jb      short loc_14008AE60
0x14008adf6  call    cs:__imp_GetLastError
0x14008adfc  mov     edx, 87h
0x14008ae01  jmp     short loc_14008AE46
0x14008ae03  mov     rcx, [rbp+57h+var_78]; TokenHandle
0x14008ae07  lea     r8, [rbp+57h+IsMember]; IsMember
0x14008ae0b  lea     rdx, [rbp+57h+pSid]; SidToCheck
0x14008ae0f  call    cs:__imp_CheckTokenMembership
0x14008ae15  test    eax, eax
0x14008ae17  jnz     short loc_14008AE6E
0x14008ae19  mov     rcx, cs:WPP_GLOBAL_Control
0x14008ae20  lea     rax, WPP_GLOBAL_Control
0x14008ae27  cmp     rcx, rax
0x14008ae2a  jz      short loc_14008AE60
0x14008ae2c  test    dword ptr [rcx+1Ch], 1000h
0x14008ae33  jz      short loc_14008AE60
0x14008ae35  cmp     [rcx+19h], sil
0x14008ae39  jb      short loc_14008AE60
0x14008ae3b  call    cs:__imp_GetLastError
0x14008ae41  mov     edx, 88h
0x14008ae46  mov     rcx, cs:WPP_GLOBAL_Control
0x14008ae4d  lea     r8, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids
0x14008ae54  mov     r9d, eax
0x14008ae57  mov     rcx, [rcx+10h]
0x14008ae5b  call    WPP_SF_d
0x14008ae60  lea     rcx, [rbp+57h+var_78]
0x14008ae64  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x14008ae69  jmp     loc_14008AD8B
0x14008ae6e  cmp     [rbp+57h+IsMember], 0
0x14008ae72  lea     rcx, [rbp+57h+var_78]
0x14008ae76  setnz   bl
0x14008ae79  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x14008ae7e  lea     rcx, [rbp+57h+TokenInformation]
0x14008ae82  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x14008ae87  lea     rcx, [rbp+57h+TokenHandle]
0x14008ae8b  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x14008ae90  mov     al, bl
0x14008ae92  mov     rcx, [rbp+57h+var_10]
0x14008ae96  xor     rcx, rsp; StackCookie
0x14008ae99  call    __security_check_cookie
0x14008ae9e  lea     r11, [rsp+0C0h+var_s0]
0x14008aea6  mov     rbx, [r11+18h]
0x14008aeaa  mov     rsi, [r11+20h]
0x14008aeae  mov     rsp, r11
0x14008aeb1  pop     rbp
0x14008aeb2  retn
```
