# CServerSet::CheckSecurity(void *)

- ea: `0x1800c1960`
- end: `0x1800c1b27`
- name: `?CheckSecurity@CServerSet@@QEAAHPEAX@Z`
- size: `455`
- prototype: `BOOL __fastcall(CServerSet *this, void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800c1b5c`

## callees

- `0x180018344`
- `0x180034540`
- `0x1800b27e0`
- `0x1800bb8f8`
- `0x1800c1960`
- `0x18010a000`

## import_xrefs

- `RPCRT4!RpcRevertToSelfEx` at `0x1800c19d1`
- `RPCRT4!RpcRevertToSelfEx` at `0x1800c19d1`
- `RPCRT4!RpcImpersonateClient` at `0x1800c199f`
- `RPCRT4!RpcImpersonateClient` at `0x1800c199f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c1a01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c1a9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c1a01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c1a9a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c1aaf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c1aaf`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800c19c6`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800c19c6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800c19b0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800c19b0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800c1a8e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800c1a8e`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800c1ac0`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800c1ac0`

## string_xrefs

- `0x1800c1a2c`: `onecore\com\combase\rpcss\objex\sset.hxx`
- `0x1800c1b03`: `onecore\com\combase\rpcss\objex\sset.hxx`
- `0x1800c1a16`: `CServerSet::CheckSecurity`
- `0x1800c1aeb`: `CServerSet::CheckSecurity`

## pseudocode

```c
BOOL __fastcall CServerSet::CheckSecurity(CServerSet *this, void *a2)
{
  HANDLE CurrentThread; // rax
  BOOL v6; // ebx
  DWORD v7; // r9d
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // rcx
  void *v10; // rsp
  void *v11; // rsp
  BOOL v12; // ebx
  PSID TokenInformation; // [rsp+40h] [rbp+0h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp+8h] BYREF

  if ( !*((_QWORD *)this + 1) )
    return 1;
  TokenHandle = 0;
  if ( RpcImpersonateClient(a2) )
  {
    if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled((unsigned int)(dword_18014E4B8 + 1)) )
      ComTraceMessageT<CServerSet *,long>(
        (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\sset.hxx",
        (unsigned int)"CServerSet::CheckSecurity",
        168,
        1);
  }
  else
  {
    CurrentThread = GetCurrentThread();
    v6 = OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle);
    RpcRevertToSelfEx(a2);
    if ( v6 )
    {
      v7 = 24;
      LODWORD(TokenInformation) = 24;
      while ( 1 )
      {
        v8 = v7 + 15LL;
        if ( v8 <= v7 )
          v8 = 0xFFFFFFFFFFFFFF0LL;
        v9 = v8 & 0xFFFFFFFFFFFFFFF0uLL;
        v10 = alloca(v9);
        v11 = alloca(v9);
        v12 = GetTokenInformation(TokenHandle, TokenUser, &TokenInformation, v7, (PDWORD)&TokenInformation);
        if ( v12 || GetLastError() != 122 )
          break;
        v7 = (unsigned int)TokenInformation;
      }
      CloseHandle(TokenHandle);
      if ( v12 )
        return EqualSid(*((PSID *)this + 1), TokenInformation);
    }
    else if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(1) )
    {
      GetLastError();
      ComTraceMessage(0xFFFFFFFFLL, "onecore\\com\\combase\\rpcss\\objex\\sset.hxx", "CServerSet::CheckSecurity", 159);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800c1960  push    rbp
0x1800c1962  push    rbx
0x1800c1963  push    rsi
0x1800c1964  push    r14
0x1800c1966  sub     rsp, 68h
0x1800c196a  lea     rbp, [rsp+40h]
0x1800c196f  mov     rax, cs:__security_cookie
0x1800c1976  xor     rax, rbp
0x1800c1979  mov     [rbp+40h+var_30], rax
0x1800c197d  cmp     qword ptr [rcx+8], 0
0x1800c1982  mov     r14, rdx
0x1800c1985  mov     rsi, rcx
0x1800c1988  jnz     short loc_1800C1994
0x1800c198a  mov     eax, 1
0x1800c198f  jmp     loc_1800C1B11
0x1800c1994  mov     rcx, r14; BindingHandle
0x1800c1997  mov     [rbp+40h+TokenHandle], 0
0x1800c199f  call    cs:__imp_RpcImpersonateClient
0x1800c19a5  mov     r8d, eax
0x1800c19a8  test    eax, eax
0x1800c19aa  jnz     loc_1800C1AC8
0x1800c19b0  call    cs:__imp_GetCurrentThread
0x1800c19b6  mov     edx, 0Ch; DesiredAccess
0x1800c19bb  lea     r9, [rbp+40h+TokenHandle]; TokenHandle
0x1800c19bf  mov     rcx, rax; ThreadHandle
0x1800c19c2  lea     r8d, [rdx-0Bh]; OpenAsSelf
0x1800c19c6  call    cs:__imp_OpenThreadToken
0x1800c19cc  mov     rcx, r14; BindingHandle
0x1800c19cf  mov     ebx, eax
0x1800c19d1  call    cs:__imp_RpcRevertToSelfEx
0x1800c19d7  test    ebx, ebx
0x1800c19d9  jnz     short loc_1800C1A45
0x1800c19db  mov     eax, cs:dword_18014E4B8
0x1800c19e1  test    eax, eax
0x1800c19e3  jnz     short loc_1800C1A01
0x1800c19e5  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1800c19eb  jz      loc_1800C1B0F
0x1800c19f1  lea     ecx, [rbx+1]
0x1800c19f4  call    IsWppLevelEnabled
0x1800c19f9  test    al, al
0x1800c19fb  jz      loc_1800C1B0F
0x1800c1a01  call    cs:__imp_GetLastError
0x1800c1a07  mov     [rsp+80h+var_48], eax
0x1800c1a0b  mov     r9d, 9Fh
0x1800c1a11  mov     [rsp+80h+var_50], rsi
0x1800c1a16  lea     r8, aCserversetChec_0; "CServerSet::CheckSecurity"
0x1800c1a1d  lea     rax, aThisPWinerror; "this:%p %!WINERROR!"
0x1800c1a24  or      ecx, 0FFFFFFFFh
0x1800c1a27  mov     [rsp+80h+var_58], rax
0x1800c1a2c  lea     rdx, aOnecoreComComb_63; "onecore\\com\\combase\\rpcss\\objex\\ss"...
0x1800c1a33  mov     dword ptr [rsp+80h+ReturnLength], 1
0x1800c1a3b  call    ?ComTraceMessage@@YAXJPEBD0HW4TraceLevel@@PEBGZZ; ComTraceMessage(long,char const *,char const *,int,TraceLevel,ushort const *,...)
0x1800c1a40  jmp     loc_1800C1B0F
0x1800c1a45  mov     r9d, 18h
0x1800c1a4b  mov     dword ptr [rbp+40h+TokenInformation], r9d
0x1800c1a4f  mov     eax, r9d
0x1800c1a52  lea     rcx, [rax+0Fh]
0x1800c1a56  cmp     rcx, rax
0x1800c1a59  ja      short loc_1800C1A65
0x1800c1a5b  mov     rcx, 0FFFFFFFFFFFFFF0h
0x1800c1a65  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800c1a69  mov     rax, rcx
0x1800c1a6c  call    _alloca_probe
0x1800c1a71  sub     rsp, rcx
0x1800c1a74  lea     rax, [rbp+40h+TokenInformation]
0x1800c1a78  mov     rcx, [rbp+40h+TokenHandle]; TokenHandle
0x1800c1a7c  mov     edx, 1; TokenInformationClass
0x1800c1a81  lea     r14, [rsp+80h+TokenInformation]
0x1800c1a86  mov     [rsp+80h+ReturnLength], rax; ReturnLength
0x1800c1a8b  mov     r8, r14; TokenInformation
0x1800c1a8e  call    cs:__imp_GetTokenInformation
0x1800c1a94  mov     ebx, eax
0x1800c1a96  test    eax, eax
0x1800c1a98  jnz     short loc_1800C1AAB
0x1800c1a9a  call    cs:__imp_GetLastError
0x1800c1aa0  cmp     eax, 7Ah ; 'z'
0x1800c1aa3  jnz     short loc_1800C1AAB
0x1800c1aa5  mov     r9d, dword ptr [rbp+40h+TokenInformation]
0x1800c1aa9  jmp     short loc_1800C1A4F
0x1800c1aab  mov     rcx, [rbp+40h+TokenHandle]; hObject
0x1800c1aaf  call    cs:__imp_CloseHandle
0x1800c1ab5  test    ebx, ebx
0x1800c1ab7  jz      short loc_1800C1B0F
0x1800c1ab9  mov     rdx, [r14]; pSid2
0x1800c1abc  mov     rcx, [rsi+8]; pSid1
0x1800c1ac0  call    cs:__imp_EqualSid
0x1800c1ac6  jmp     short loc_1800C1B11
0x1800c1ac8  mov     eax, cs:dword_18014E4B8
0x1800c1ace  test    eax, eax
0x1800c1ad0  jnz     short loc_1800C1AE6
0x1800c1ad2  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1800c1ad8  jz      short loc_1800C1B0F
0x1800c1ada  lea     ecx, [rax+1]
0x1800c1add  call    IsWppLevelEnabled
0x1800c1ae2  test    al, al
0x1800c1ae4  jz      short loc_1800C1B0F
0x1800c1ae6  mov     dword ptr [rsp+80h+var_50], r8d
0x1800c1aeb  lea     rdx, aCserversetChec_0; "CServerSet::CheckSecurity"
0x1800c1af2  mov     r8d, 0A8h
0x1800c1af8  mov     [rsp+80h+var_58], rsi
0x1800c1afd  mov     r9d, 1
0x1800c1b03  lea     rcx, aOnecoreComComb_63; "onecore\\com\\combase\\rpcss\\objex\\ss"...
0x1800c1b0a  call    ??$ComTraceMessageT@PEAVCServerSet@@J@@YAXPEBD0HW4TraceLevel@@PEBGPEAVCServerSet@@J@Z; ComTraceMessageT<CServerSet *,long>(char const *,char const *,int,TraceLevel,ushort const *,CServerSet *,long)
0x1800c1b0f  xor     eax, eax
0x1800c1b11  mov     rcx, [rbp+40h+var_30]
0x1800c1b15  xor     rcx, rbp; StackCookie
0x1800c1b18  call    __security_check_cookie
0x1800c1b1d  lea     rsp, [rbp+28h]
0x1800c1b21  pop     r14
0x1800c1b23  pop     rsi
0x1800c1b24  pop     rbx
0x1800c1b25  pop     rbp
0x1800c1b26  retn
```
