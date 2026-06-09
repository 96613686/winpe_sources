# CRegRpcEndpoint::SecDescAccessCheck(void *)

- ea: `0x180015c50`
- end: `0x180015d57`
- name: `?SecDescAccessCheck@CRegRpcEndpoint@@AEAAKPEAX@Z`
- size: `263`
- prototype: `__int64 __fastcall(CRegRpcEndpoint *this, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800157c0`

## callees

- `0x180001984`
- `0x180015c50`
- `0x180015e4c`
- `0x18001c150`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180015cfc`
- `KERNEL32!GetLastError` at `0x180015cfc`
- `ADVAPI32!AccessCheck` at `0x180015cec`
- `ADVAPI32!AccessCheck` at `0x180015cec`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x180015d27`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x180015d27`

## pseudocode

```c
__int64 __fastcall CRegRpcEndpoint::SecDescAccessCheck(CRegRpcEndpoint *this, void *a2)
{
  unsigned int v4; // ebx
  struct _PRIVILEGE_SET *PrivilegeSet; // rdi
  DWORD LastError; // eax
  __int64 v7; // rdx
  __int64 v8; // r8
  WINBOOL AccessStatus; // [rsp+40h] [rbp-30h] BYREF
  DWORD GrantedAccess; // [rsp+44h] [rbp-2Ch] BYREF
  DWORD PrivilegeSetLength; // [rsp+48h] [rbp-28h] BYREF
  _GENERIC_MAPPING GenericMapping; // [rsp+50h] [rbp-20h] BYREF

  GenericMapping.GenericAll = 2031616;
  GenericMapping.GenericRead = 0x20000;
  GenericMapping.GenericWrite = 0x20000;
  PrivilegeSetLength = 212;
  v4 = 0;
  GenericMapping.GenericExecute = 0x20000;
  GrantedAccess = 0;
  AccessStatus = 0;
  PrivilegeSet = (struct _PRIVILEGE_SET *)operator new[](0xD4u, (const struct std::nothrow_t *)&std::nothrow);
  if ( PrivilegeSet )
  {
    if ( AccessCheck(
           *((PSECURITY_DESCRIPTOR *)this + 226),
           a2,
           *((_DWORD *)this + 454),
           &GenericMapping,
           PrivilegeSet,
           &PrivilegeSetLength,
           &GrantedAccess,
           &AccessStatus) )
    {
      if ( !AccessStatus )
        v4 = 5;
    }
    else
    {
      LastError = GetLastError();
      v4 = ElValidateWin32_7(LastError, v7, v8, 374);
    }
    WdsPrivateHpFree(PrivilegeSet);
  }
  else
  {
    return 8;
  }
  return v4;
}

```

## disassembly

```asm
0x180015c50  mov     [rsp-18h+arg_10], rbx
0x180015c55  mov     [rsp-18h+arg_18], rsi
0x180015c5a  push    rbp
0x180015c5b  push    rdi
0x180015c5c  push    r14
0x180015c5e  mov     rbp, rsp
0x180015c61  sub     rsp, 70h
0x180015c65  mov     rax, cs:__security_cookie
0x180015c6c  xor     rax, rsp
0x180015c6f  mov     [rbp+var_10], rax
0x180015c73  mov     eax, 20000h
0x180015c78  mov     [rbp+GenericMapping.GenericAll], 1F0000h
0x180015c7f  mov     rsi, rcx
0x180015c82  mov     [rbp+GenericMapping.GenericRead], eax
0x180015c85  mov     ecx, 0D4h; unsigned __int64
0x180015c8a  mov     [rbp+GenericMapping.GenericWrite], eax
0x180015c8d  mov     r14, rdx
0x180015c90  mov     [rbp+var_28], ecx
0x180015c93  xor     ebx, ebx
0x180015c95  mov     [rbp+GenericMapping.GenericExecute], eax
0x180015c98  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180015c9f  mov     [rbp+var_2C], ebx
0x180015ca2  mov     [rbp+var_30], ebx
0x180015ca5  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180015caa  mov     rdi, rax
0x180015cad  test    rax, rax
0x180015cb0  jnz     short loc_180015CB7
0x180015cb2  lea     ebx, [rax+8]
0x180015cb5  jmp     short loc_180015D33
0x180015cb7  mov     r8d, [rsi+718h]; DesiredAccess
0x180015cbe  lea     rax, [rbp+var_30]
0x180015cc2  mov     rcx, [rsi+710h]; pSecurityDescriptor
0x180015cc9  lea     r9, [rbp+GenericMapping]; GenericMapping
0x180015ccd  mov     [rsp+70h+AccessStatus], rax; AccessStatus
0x180015cd2  mov     rdx, r14; ClientToken
0x180015cd5  lea     rax, [rbp+var_2C]
0x180015cd9  mov     [rsp+70h+GrantedAccess], rax; GrantedAccess
0x180015cde  lea     rax, [rbp+var_28]
0x180015ce2  mov     [rsp+70h+PrivilegeSetLength], rax; PrivilegeSetLength
0x180015ce7  mov     [rsp+70h+PrivilegeSet], rdi; PrivilegeSet
0x180015cec  call    cs:__imp_AccessCheck
0x180015cf3  nop     dword ptr [rax+rax+00h]
0x180015cf8  test    eax, eax
0x180015cfa  jnz     short loc_180015D19
0x180015cfc  call    cs:__imp_GetLastError
0x180015d03  nop     dword ptr [rax+rax+00h]
0x180015d08  mov     ecx, eax
0x180015d0a  mov     r9d, 176h
0x180015d10  call    ElValidateWin32_7
0x180015d15  mov     ebx, eax
0x180015d17  jmp     short loc_180015D24
0x180015d19  cmp     [rbp+var_30], ebx
0x180015d1c  mov     eax, 5
0x180015d21  cmovz   ebx, eax
0x180015d24  mov     rcx, rdi
0x180015d27  call    cs:__imp_?WdsPrivateHpFree@@YAKPEAX@Z; WdsPrivateHpFree(void *)
0x180015d2e  nop     dword ptr [rax+rax+00h]
0x180015d33  mov     eax, ebx
0x180015d35  mov     rcx, [rbp+var_10]
0x180015d39  xor     rcx, rsp; StackCookie
0x180015d3c  call    __security_check_cookie
0x180015d41  lea     r11, [rsp+70h+var_s0]
0x180015d46  mov     rbx, [r11+30h]
0x180015d4a  mov     rsi, [r11+38h]
0x180015d4e  mov     rsp, r11
0x180015d51  pop     r14
0x180015d53  pop     rdi
0x180015d54  pop     rbp
0x180015d55  retn
```
