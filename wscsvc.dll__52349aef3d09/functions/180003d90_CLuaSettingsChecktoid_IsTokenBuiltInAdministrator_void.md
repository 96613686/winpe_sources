# CLuaSettingsChecktoid::IsTokenBuiltInAdministrator(void *)

- ea: `0x180003d90`
- end: `0x180003e31`
- name: `?IsTokenBuiltInAdministrator@CLuaSettingsChecktoid@@CAHPEAX@Z`
- size: `161`
- prototype: `_BOOL8 __fastcall(void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180003cd8`

## callees

- `0x180003d90`
- `0x18003fc30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003e1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003e1f`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180003dda`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180003dda`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180003dea`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180003dea`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180003dcb`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180003dcb`

## pseudocode

```c
_BOOL8 __fastcall CLuaSettingsChecktoid::IsTokenBuiltInAdministrator(void *a1)
{
  PUCHAR SidSubAuthorityCount; // rax
  DWORD ReturnLength[4]; // [rsp+30h] [rbp-88h] BYREF
  PSID TokenInformation[12]; // [rsp+40h] [rbp-78h] BYREF

  ReturnLength[0] = 0;
  if ( GetTokenInformation(a1, TokenUser, TokenInformation, 0x58u, ReturnLength) )
  {
    SidSubAuthorityCount = GetSidSubAuthorityCount(TokenInformation[0]);
    return *GetSidSubAuthority(TokenInformation[0], (unsigned int)*SidSubAuthorityCount - 1) == 500;
  }
  else
  {
    GetLastError();
    return 0;
  }
}

```

## disassembly

```asm
0x180003d90  sub     rsp, 0B8h
0x180003d97  mov     rax, cs:__security_cookie
0x180003d9e  xor     rax, rsp
0x180003da1  mov     [rsp+0B8h+var_18], rax
0x180003da9  lea     rax, [rsp+0B8h+var_88]
0x180003dae  mov     [rsp+0B8h+var_88], 0
0x180003db6  mov     r9d, 58h ; 'X'; TokenInformationLength
0x180003dbc  mov     [rsp+0B8h+ReturnLength], rax; ReturnLength
0x180003dc1  lea     r8, [rsp+0B8h+TokenInformation]; TokenInformation
0x180003dc6  mov     edx, 1; TokenInformationClass
0x180003dcb  call    cs:__imp_GetTokenInformation
0x180003dd1  test    eax, eax
0x180003dd3  jz      short loc_180003E15
0x180003dd5  mov     rcx, [rsp+0B8h+TokenInformation]; pSid
0x180003dda  call    cs:__imp_GetSidSubAuthorityCount
0x180003de0  mov     rcx, [rsp+0B8h+TokenInformation]; pSid
0x180003de5  movzx   edx, byte ptr [rax]
0x180003de8  dec     edx; nSubAuthority
0x180003dea  call    cs:__imp_GetSidSubAuthority
0x180003df0  xor     ecx, ecx
0x180003df2  cmp     dword ptr [rax], 1F4h
0x180003df8  setz    cl
0x180003dfb  mov     eax, ecx
0x180003dfd  mov     rcx, [rsp+0B8h+var_18]
0x180003e05  xor     rcx, rsp; StackCookie
0x180003e08  call    __security_check_cookie
0x180003e0d  add     rsp, 0B8h
0x180003e14  retn
0x180003e15  mov     [rsp+0B8h+var_8], rbx
0x180003e1d  xor     ebx, ebx
0x180003e1f  call    cs:__imp_GetLastError
0x180003e25  mov     eax, ebx
0x180003e27  mov     rbx, [rsp+0B8h+var_8]
0x180003e2f  jmp     short loc_180003DFD
```
