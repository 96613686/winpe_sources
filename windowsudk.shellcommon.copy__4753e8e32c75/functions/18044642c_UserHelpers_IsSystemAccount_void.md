# UserHelpers::IsSystemAccount(void *)

- ea: `0x18044642c`
- end: `0x1804464bb`
- name: `?IsSystemAccount@UserHelpers@@YA_NPEAX@Z`
- size: `143`
- prototype: `bool __fastcall(UserHelpers *__hidden this, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800e48ac`

## callees

- `0x180033f28`
- `0x18015d524`
- `0x18044642c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18044644c`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x180446461`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x180446476`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18044648b`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18044644c`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x180446461`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x180446476`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18044648b`

## pseudocode

```c
bool __fastcall UserHelpers::IsSystemAccount(UserHelpers *this, void *a2)
{
  bool v2; // bl
  void *v3; // rcx
  void *Block; // [rsp+38h] [rbp+10h] BYREF

  wil::details::GetTokenInfoWrap<_TOKEN_USER,wil::err_exception_policy,0>(&Block, this);
  v2 = IsWellKnownSid(*(PSID *)Block, WinLocalSystemSid)
    || IsWellKnownSid(*(PSID *)Block, WinLocalServiceSid)
    || IsWellKnownSid(*(PSID *)Block, WinNetworkServiceSid)
    || IsWellKnownSid(*(PSID *)Block, WinLocalAccountAndAdministratorSid|WinCreatorGroupSid);
  v3 = Block;
  Block = 0;
  if ( v3 )
    operator delete(v3);
  return v2;
}

```

## disassembly

```asm
0x18044642c  push    rbx
0x18044642e  sub     rsp, 20h
0x180446432  mov     rdx, rcx
0x180446435  lea     rcx, [rsp+28h+Block]
0x18044643a  call    ??$GetTokenInfoWrap@U_TOKEN_USER@@Uerr_exception_policy@wil@@$0A@@details@wil@@YA?AV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::details::GetTokenInfoWrap<_TOKEN_USER,wil::err_exception_policy,0>(void *)
0x18044643f  mov     rcx, [rsp+28h+Block]
0x180446444  mov     edx, 16h; WellKnownSidType
0x180446449  mov     rcx, [rcx]; pSid
0x18044644c  call    cs:__imp_IsWellKnownSid
0x180446452  test    eax, eax
0x180446454  jnz     short loc_180446499
0x180446456  mov     rcx, [rsp+28h+Block]
0x18044645b  lea     edx, [rax+17h]; WellKnownSidType
0x18044645e  mov     rcx, [rcx]; pSid
0x180446461  call    cs:__imp_IsWellKnownSid
0x180446467  test    eax, eax
0x180446469  jnz     short loc_180446499
0x18044646b  mov     rcx, [rsp+28h+Block]
0x180446470  lea     edx, [rax+18h]; WellKnownSidType
0x180446473  mov     rcx, [rcx]; pSid
0x180446476  call    cs:__imp_IsWellKnownSid
0x18044647c  test    eax, eax
0x18044647e  jnz     short loc_180446499
0x180446480  mov     rcx, [rsp+28h+Block]
0x180446485  lea     edx, [rax+6Eh]; WellKnownSidType
0x180446488  mov     rcx, [rcx]; pSid
0x18044648b  call    cs:__imp_IsWellKnownSid
0x180446491  test    eax, eax
0x180446493  jnz     short loc_180446499
0x180446495  xor     bl, bl
0x180446497  jmp     short loc_18044649B
0x180446499  mov     bl, 1
0x18044649b  mov     rcx, [rsp+28h+Block]; Block
0x1804464a0  mov     [rsp+28h+Block], 0
0x1804464a9  test    rcx, rcx
0x1804464ac  jz      short loc_1804464B3
0x1804464ae  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1804464b3  mov     al, bl
0x1804464b5  add     rsp, 20h
0x1804464b9  pop     rbx
0x1804464ba  retn
```
