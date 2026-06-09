# IsUserAdmin(void *)

- ea: `0x18001562c`
- end: `0x1800156d7`
- name: `?IsUserAdmin@@YA_NPEAX@Z`
- size: `171`
- prototype: `bool __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180014ec0`

## callees

- `0x180014e04`
- `0x180015568`
- `0x18001562c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180015674`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800156aa`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180015674`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800156aa`

## pseudocode

```c
bool __fastcall IsUserAdmin(HANDLE TokenHandle)
{
  bool v2; // bl
  int TokenInformation; // [rsp+48h] [rbp+10h] BYREF
  DWORD ReturnLength; // [rsp+50h] [rbp+18h] BYREF
  HANDLE TokenHandlea; // [rsp+58h] [rbp+20h] BYREF

  v2 = IsTokenInAdminGroup(TokenHandle);
  if ( !v2 )
  {
    TokenInformation = 0;
    ReturnLength = 0;
    if ( GetTokenInformation(TokenHandle, TokenElevationType, &TokenInformation, 4u, &ReturnLength) )
    {
      if ( TokenInformation == 3 )
      {
        TokenHandlea = 0;
        if ( GetTokenInformation(TokenHandle, TokenLinkedToken, &TokenHandlea, 8u, &ReturnLength) )
          v2 = IsTokenInAdminGroup(TokenHandlea);
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandlea);
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x18001562c  mov     [rsp+arg_0], rbx
0x180015631  push    rdi
0x180015632  sub     rsp, 30h
0x180015636  mov     rdi, rcx
0x180015639  call    ?IsTokenInAdminGroup@@YA_NPEAX@Z; IsTokenInAdminGroup(void *)
0x18001563e  mov     bl, al
0x180015640  test    al, al
0x180015642  jnz     loc_1800156CA
0x180015648  mov     r9d, 4; TokenInformationLength
0x18001564e  mov     [rsp+38h+TokenInformation], 0
0x180015656  lea     rax, [rsp+38h+arg_10]
0x18001565b  mov     [rsp+38h+arg_10], 0
0x180015663  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x180015668  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18001566d  mov     rcx, rdi; TokenHandle
0x180015670  lea     edx, [r9+0Eh]; TokenInformationClass
0x180015674  call    cs:__imp_GetTokenInformation
0x18001567a  test    eax, eax
0x18001567c  jz      short loc_1800156CA
0x18001567e  cmp     [rsp+38h+TokenInformation], 3
0x180015683  jnz     short loc_1800156CA
0x180015685  mov     r9d, 8; TokenInformationLength
0x18001568b  mov     [rsp+38h+TokenHandle], 0
0x180015694  lea     rax, [rsp+38h+arg_10]
0x180015699  mov     rcx, rdi; TokenHandle
0x18001569c  lea     r8, [rsp+38h+TokenHandle]; TokenInformation
0x1800156a1  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x1800156a6  lea     edx, [r9+0Bh]; TokenInformationClass
0x1800156aa  call    cs:__imp_GetTokenInformation
0x1800156b0  test    eax, eax
0x1800156b2  jz      short loc_1800156C0
0x1800156b4  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x1800156b9  call    ?IsTokenInAdminGroup@@YA_NPEAX@Z; IsTokenInAdminGroup(void *)
0x1800156be  mov     bl, al
0x1800156c0  lea     rcx, [rsp+38h+TokenHandle]
0x1800156c5  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800156ca  mov     al, bl
0x1800156cc  mov     rbx, [rsp+38h+arg_0]
0x1800156d1  add     rsp, 30h
0x1800156d5  pop     rdi
0x1800156d6  retn
```
