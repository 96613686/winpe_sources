# CRegRpcEndpoint::LocalAdminAccessCheck(void *)

- ea: `0x180015b70`
- end: `0x180015c4a`
- name: `?LocalAdminAccessCheck@CRegRpcEndpoint@@AEAAKPEAX@Z`
- size: `218`
- prototype: `__int64 __fastcall(CRegRpcEndpoint *this, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800157c0`

## callees

- `0x180001984`
- `0x180015b70`
- `0x180015e4c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180015bd0`
- `KERNEL32!GetLastError` at `0x180015c08`
- `KERNEL32!GetLastError` at `0x180015bd0`
- `KERNEL32!GetLastError` at `0x180015c08`
- `ADVAPI32!CreateWellKnownSid` at `0x180015bc0`
- `ADVAPI32!CreateWellKnownSid` at `0x180015bc0`
- `ADVAPI32!CheckTokenMembership` at `0x180015bf8`
- `ADVAPI32!CheckTokenMembership` at `0x180015bf8`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x180015c2b`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x180015c2b`

## pseudocode

```c
__int64 __fastcall CRegRpcEndpoint::LocalAdminAccessCheck(CRegRpcEndpoint *this, void *a2)
{
  unsigned int v2; // ebx
  void *v4; // rax
  void *v5; // rdi
  DWORD LastError; // eax
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // r9
  WINBOOL IsMember; // [rsp+30h] [rbp+8h] BYREF
  int v12; // [rsp+34h] [rbp+Ch]
  DWORD cbSid; // [rsp+40h] [rbp+18h] BYREF

  v12 = HIDWORD(this);
  v2 = 0;
  IsMember = 0;
  v4 = operator new[](0x44u, (const struct std::nothrow_t *)&std::nothrow);
  v5 = v4;
  if ( v4 )
  {
    cbSid = 68;
    if ( CreateWellKnownSid(WinBuiltinAdministratorsSid, 0, v4, &cbSid) )
    {
      if ( CheckTokenMembership(a2, v5, &IsMember) )
      {
        if ( !IsMember )
          v2 = 5;
        goto LABEL_10;
      }
      LastError = GetLastError();
      v9 = 438;
    }
    else
    {
      LastError = GetLastError();
      v9 = 430;
    }
    v2 = ElValidateWin32_7(LastError, v7, v8, v9);
LABEL_10:
    WdsPrivateHpFree(v5);
    return v2;
  }
  return 8;
}

```

## disassembly

```asm
0x180015b70  mov     rax, rsp
0x180015b73  mov     [rax+10h], rbx
0x180015b77  mov     [rax+20h], rsi
0x180015b7b  mov     [rax+8], rcx
0x180015b7f  push    rdi
0x180015b80  sub     rsp, 20h
0x180015b84  xor     ebx, ebx
0x180015b86  mov     rsi, rdx
0x180015b89  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180015b90  mov     [rax+8], ebx
0x180015b93  lea     ecx, [rbx+44h]; unsigned __int64
0x180015b96  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180015b9b  mov     rdi, rax
0x180015b9e  test    rax, rax
0x180015ba1  jnz     short loc_180015BAB
0x180015ba3  lea     ebx, [rax+8]
0x180015ba6  jmp     loc_180015C37
0x180015bab  xor     edx, edx; DomainSid
0x180015bad  mov     [rsp+28h+cbSid], 44h ; 'D'
0x180015bb5  lea     r9, [rsp+28h+cbSid]; cbSid
0x180015bba  mov     r8, rdi; pSid
0x180015bbd  lea     ecx, [rdx+1Ah]; WellKnownSidType
0x180015bc0  call    cs:__imp_CreateWellKnownSid
0x180015bc7  nop     dword ptr [rax+rax+00h]
0x180015bcc  test    eax, eax
0x180015bce  jnz     short loc_180015BED
0x180015bd0  call    cs:__imp_GetLastError
0x180015bd7  nop     dword ptr [rax+rax+00h]
0x180015bdc  mov     r9d, 1AEh
0x180015be2  mov     ecx, eax
0x180015be4  call    ElValidateWin32_7
0x180015be9  mov     ebx, eax
0x180015beb  jmp     short loc_180015C28
0x180015bed  lea     r8, [rsp+28h+IsMember]; IsMember
0x180015bf2  mov     rdx, rdi; SidToCheck
0x180015bf5  mov     rcx, rsi; TokenHandle
0x180015bf8  call    cs:__imp_CheckTokenMembership
0x180015bff  nop     dword ptr [rax+rax+00h]
0x180015c04  test    eax, eax
0x180015c06  jnz     short loc_180015C1C
0x180015c08  call    cs:__imp_GetLastError
0x180015c0f  nop     dword ptr [rax+rax+00h]
0x180015c14  mov     r9d, 1B6h
0x180015c1a  jmp     short loc_180015BE2
0x180015c1c  cmp     [rsp+28h+IsMember], ebx
0x180015c20  mov     eax, 5
0x180015c25  cmovz   ebx, eax
0x180015c28  mov     rcx, rdi
0x180015c2b  call    cs:__imp_?WdsPrivateHpFree@@YAKPEAX@Z; WdsPrivateHpFree(void *)
0x180015c32  nop     dword ptr [rax+rax+00h]
0x180015c37  mov     rsi, [rsp+28h+arg_18]
0x180015c3c  mov     eax, ebx
0x180015c3e  mov     rbx, [rsp+28h+arg_8]
0x180015c43  add     rsp, 20h
0x180015c47  pop     rdi
0x180015c48  retn
```
