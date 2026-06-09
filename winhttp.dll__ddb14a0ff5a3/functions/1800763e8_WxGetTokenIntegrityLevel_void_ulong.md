# WxGetTokenIntegrityLevel(void *,ulong *)

- ea: `0x1800763e8`
- end: `0x1800764c8`
- name: `?WxGetTokenIntegrityLevel@@YAJPEAXPEAK@Z`
- size: `224`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800760f0`

## callees

- `0x1800763e8`
- `0x1800a1d10`
- `0x1800a2660`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18007644f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18007644f`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180076460`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180076460`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180076472`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180076472`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007649f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007649f`

## pseudocode

```c
__int64 __fastcall WxGetTokenIntegrityLevel(HANDLE TokenHandle, unsigned int *a2)
{
  signed int v4; // ebx
  PUCHAR SidSubAuthorityCount; // rax
  signed int LastError; // eax
  DWORD ReturnLength; // [rsp+30h] [rbp-98h] BYREF
  int v9; // [rsp+34h] [rbp-94h]
  PSID TokenInformation[14]; // [rsp+40h] [rbp-88h] BYREF

  v9 = 0;
  memset_0(TokenInformation, 0, 0x6Cu);
  ReturnLength = 108;
  *a2 = 4096;
  if ( GetTokenInformation(TokenHandle, TokenIntegrityLevel, TokenInformation, 0x6Cu, &ReturnLength) )
  {
    v4 = 0;
    SidSubAuthorityCount = GetSidSubAuthorityCount(TokenInformation[0]);
    *a2 = *GetSidSubAuthority(TokenInformation[0], (unsigned __int8)(*SidSubAuthorityCount - 1));
  }
  else
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    v9 = 307;
    if ( v4 >= 0 )
      return (unsigned int)-2147418113;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800763e8  mov     [rsp+arg_10], rbx
0x1800763ed  push    rdi
0x1800763ee  sub     rsp, 0C0h
0x1800763f5  mov     rax, cs:__security_cookie
0x1800763fc  xor     rax, rsp
0x1800763ff  mov     [rsp+0C8h+var_18], rax
0x180076407  mov     rdi, rdx
0x18007640a  mov     [rsp+0C8h+var_94], 0
0x180076412  xor     edx, edx; Val
0x180076414  mov     rbx, rcx
0x180076417  lea     rcx, [rsp+0C8h+TokenInformation]; void *
0x18007641c  lea     r8d, [rdx+6Ch]; Size
0x180076420  call    memset_0
0x180076425  mov     r9d, 6Ch ; 'l'; TokenInformationLength
0x18007642b  mov     [rsp+0C8h+var_98], 6Ch ; 'l'
0x180076433  lea     rax, [rsp+0C8h+var_98]
0x180076438  mov     dword ptr [rdi], 1000h
0x18007643e  lea     r8, [rsp+0C8h+TokenInformation]; TokenInformation
0x180076443  mov     [rsp+0C8h+ReturnLength], rax; ReturnLength
0x180076448  mov     rcx, rbx; TokenHandle
0x18007644b  lea     edx, [r9-53h]; TokenInformationClass
0x18007644f  call    cs:__imp_GetTokenInformation
0x180076455  test    eax, eax
0x180076457  jz      short loc_18007649F
0x180076459  mov     rcx, [rsp+0C8h+TokenInformation]; pSid
0x18007645e  xor     ebx, ebx
0x180076460  call    cs:__imp_GetSidSubAuthorityCount
0x180076466  mov     cl, [rax]
0x180076468  dec     cl
0x18007646a  movzx   edx, cl; nSubAuthority
0x18007646d  mov     rcx, [rsp+0C8h+TokenInformation]; pSid
0x180076472  call    cs:__imp_GetSidSubAuthority
0x180076478  mov     ecx, [rax]
0x18007647a  mov     [rdi], ecx
0x18007647c  mov     eax, ebx
0x18007647e  mov     rcx, [rsp+0C8h+var_18]
0x180076486  xor     rcx, rsp; StackCookie
0x180076489  call    __security_check_cookie
0x18007648e  mov     rbx, [rsp+0C8h+arg_10]
0x180076496  add     rsp, 0C0h
0x18007649d  pop     rdi
0x18007649e  retn
0x18007649f  call    cs:__imp_GetLastError
0x1800764a5  mov     ebx, eax
0x1800764a7  test    eax, eax
0x1800764a9  jle     short loc_1800764B4
0x1800764ab  movzx   ebx, ax
0x1800764ae  or      ebx, 80070000h
0x1800764b4  test    ebx, ebx
0x1800764b6  mov     [rsp+0C8h+var_94], 133h
0x1800764be  mov     eax, 8000FFFFh
0x1800764c3  cmovns  ebx, eax
0x1800764c6  jmp     short loc_18007647C
```
