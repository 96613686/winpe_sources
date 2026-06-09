# CServerSet::CheckSecurity(void *)

- ea: `0x1800c7590`
- end: `0x1800c778e`
- name: `?CheckSecurity@CServerSet@@QEAAHPEAX@Z`
- size: `510`
- prototype: `int(CServerSet *__hidden this, void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800c77cc`

## callees

- `0x18001c624`
- `0x180034260`
- `0x1800b7ac0`
- `0x1800c11e4`
- `0x1800c7590`
- `0x180112d00`

## import_xrefs

- `RPCRT4!RpcRevertToSelfEx` at `0x1800c7613`
- `RPCRT4!RpcRevertToSelfEx` at `0x1800c7613`
- `RPCRT4!RpcImpersonateClient` at `0x1800c75cf`
- `RPCRT4!RpcImpersonateClient` at `0x1800c75cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c7649`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c76ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c7649`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c76ee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c7709`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c7709`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800c7602`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800c7602`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800c75e6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800c75e6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800c76dc`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800c76dc`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800c7720`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800c7720`

## string_xrefs

- `0x1800c767a`: `onecore\com\combase\rpcss\objex\sset.hxx`
- `0x1800c7769`: `onecore\com\combase\rpcss\objex\sset.hxx`
- `0x1800c7664`: `CServerSet::CheckSecurity`
- `0x1800c7751`: `CServerSet::CheckSecurity`

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
  PDWORD ReturnLength; // [rsp+20h] [rbp-20h]
  DWORD LastError; // [rsp+38h] [rbp-8h]
  PSID TokenInformation; // [rsp+40h] [rbp+0h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp+8h] BYREF

  if ( !*((_QWORD *)this + 1) )
    return 1;
  TokenHandle = 0;
  if ( RpcImpersonateClient(a2) )
  {
    if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled((unsigned int)(dword_1801574B8 + 1)) )
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
    else if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(1) )
    {
      LastError = GetLastError();
      LODWORD(ReturnLength) = 1;
      ComTraceMessage(
        0xFFFFFFFFLL,
        "onecore\\com\\combase\\rpcss\\objex\\sset.hxx",
        "CServerSet::CheckSecurity",
        159,
        ReturnLength,
        L"this:%p %!WINERROR!",
        this,
        LastError);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800c7590  push    rbp
0x1800c7592  push    rbx
0x1800c7593  push    rsi
0x1800c7594  push    r14
0x1800c7596  sub     rsp, 68h
0x1800c759a  lea     rbp, [rsp+40h]
0x1800c759f  mov     rax, cs:__security_cookie
0x1800c75a6  xor     rax, rbp
0x1800c75a9  mov     [rbp+40h+var_30], rax
0x1800c75ad  cmp     qword ptr [rcx+8], 0
0x1800c75b2  mov     r14, rdx
0x1800c75b5  mov     rsi, rcx
0x1800c75b8  jnz     short loc_1800C75C4
0x1800c75ba  mov     eax, 1
0x1800c75bf  jmp     loc_1800C7777
0x1800c75c4  mov     rcx, r14; BindingHandle
0x1800c75c7  mov     [rbp+40h+TokenHandle], 0
0x1800c75cf  call    cs:__imp_RpcImpersonateClient
0x1800c75d6  nop     dword ptr [rax+rax+00h]
0x1800c75db  mov     r8d, eax
0x1800c75de  test    eax, eax
0x1800c75e0  jnz     loc_1800C772E
0x1800c75e6  call    cs:__imp_GetCurrentThread
0x1800c75ed  nop     dword ptr [rax+rax+00h]
0x1800c75f2  mov     edx, 0Ch; DesiredAccess
0x1800c75f7  lea     r9, [rbp+40h+TokenHandle]; TokenHandle
0x1800c75fb  mov     rcx, rax; ThreadHandle
0x1800c75fe  lea     r8d, [rdx-0Bh]; OpenAsSelf
0x1800c7602  call    cs:__imp_OpenThreadToken
0x1800c7609  nop     dword ptr [rax+rax+00h]
0x1800c760e  mov     rcx, r14; BindingHandle
0x1800c7611  mov     ebx, eax
0x1800c7613  call    cs:__imp_RpcRevertToSelfEx
0x1800c761a  nop     dword ptr [rax+rax+00h]
0x1800c761f  test    ebx, ebx
0x1800c7621  jnz     short loc_1800C7693
0x1800c7623  mov     eax, cs:dword_1801574B8
0x1800c7629  test    eax, eax
0x1800c762b  jnz     short loc_1800C7649
0x1800c762d  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1800c7633  jz      loc_1800C7775
0x1800c7639  lea     ecx, [rbx+1]
0x1800c763c  call    IsWppLevelEnabled
0x1800c7641  test    al, al
0x1800c7643  jz      loc_1800C7775
0x1800c7649  call    cs:__imp_GetLastError
0x1800c7650  nop     dword ptr [rax+rax+00h]
0x1800c7655  mov     [rsp+80h+var_48], eax
0x1800c7659  mov     r9d, 9Fh
0x1800c765f  mov     [rsp+80h+var_50], rsi
0x1800c7664  lea     r8, aCserversetChec_0; "CServerSet::CheckSecurity"
0x1800c766b  lea     rax, aThisPWinerror; "this:%p %!WINERROR!"
0x1800c7672  or      ecx, 0FFFFFFFFh
0x1800c7675  mov     [rsp+80h+var_58], rax
0x1800c767a  lea     rdx, aOnecoreComComb_63; "onecore\\com\\combase\\rpcss\\objex\\ss"...
0x1800c7681  mov     dword ptr [rsp+80h+ReturnLength], 1
0x1800c7689  call    ?ComTraceMessage@@YAXJPEBD0HW4TraceLevel@@PEBGZZ; ComTraceMessage(long,char const *,char const *,int,TraceLevel,ushort const *,...)
0x1800c768e  jmp     loc_1800C7775
0x1800c7693  mov     r9d, 18h
0x1800c7699  mov     dword ptr [rbp+40h+TokenInformation], r9d
0x1800c769d  mov     eax, r9d
0x1800c76a0  lea     rcx, [rax+0Fh]
0x1800c76a4  cmp     rcx, rax
0x1800c76a7  ja      short loc_1800C76B3
0x1800c76a9  mov     rcx, 0FFFFFFFFFFFFFF0h
0x1800c76b3  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800c76b7  mov     rax, rcx
0x1800c76ba  call    _alloca_probe
0x1800c76bf  sub     rsp, rcx
0x1800c76c2  lea     rax, [rbp+40h+TokenInformation]
0x1800c76c6  mov     rcx, [rbp+40h+TokenHandle]; TokenHandle
0x1800c76ca  mov     edx, 1; TokenInformationClass
0x1800c76cf  lea     r14, [rsp+80h+TokenInformation]
0x1800c76d4  mov     [rsp+80h+ReturnLength], rax; ReturnLength
0x1800c76d9  mov     r8, r14; TokenInformation
0x1800c76dc  call    cs:__imp_GetTokenInformation
0x1800c76e3  nop     dword ptr [rax+rax+00h]
0x1800c76e8  mov     ebx, eax
0x1800c76ea  test    eax, eax
0x1800c76ec  jnz     short loc_1800C7705
0x1800c76ee  call    cs:__imp_GetLastError
0x1800c76f5  nop     dword ptr [rax+rax+00h]
0x1800c76fa  cmp     eax, 7Ah ; 'z'
0x1800c76fd  jnz     short loc_1800C7705
0x1800c76ff  mov     r9d, dword ptr [rbp+40h+TokenInformation]
0x1800c7703  jmp     short loc_1800C769D
0x1800c7705  mov     rcx, [rbp+40h+TokenHandle]; hObject
0x1800c7709  call    cs:__imp_CloseHandle
0x1800c7710  nop     dword ptr [rax+rax+00h]
0x1800c7715  test    ebx, ebx
0x1800c7717  jz      short loc_1800C7775
0x1800c7719  mov     rdx, [r14]; pSid2
0x1800c771c  mov     rcx, [rsi+8]; pSid1
0x1800c7720  call    cs:__imp_EqualSid
0x1800c7727  nop     dword ptr [rax+rax+00h]
0x1800c772c  jmp     short loc_1800C7777
0x1800c772e  mov     eax, cs:dword_1801574B8
0x1800c7734  test    eax, eax
0x1800c7736  jnz     short loc_1800C774C
0x1800c7738  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1800c773e  jz      short loc_1800C7775
0x1800c7740  lea     ecx, [rax+1]
0x1800c7743  call    IsWppLevelEnabled
0x1800c7748  test    al, al
0x1800c774a  jz      short loc_1800C7775
0x1800c774c  mov     dword ptr [rsp+80h+var_50], r8d
0x1800c7751  lea     rdx, aCserversetChec_0; "CServerSet::CheckSecurity"
0x1800c7758  mov     r8d, 0A8h
0x1800c775e  mov     [rsp+80h+var_58], rsi
0x1800c7763  mov     r9d, 1
0x1800c7769  lea     rcx, aOnecoreComComb_63; "onecore\\com\\combase\\rpcss\\objex\\ss"...
0x1800c7770  call    ??$ComTraceMessageT@PEAVCServerSet@@J@@YAXPEBD0HW4TraceLevel@@PEBGPEAVCServerSet@@J@Z; ComTraceMessageT<CServerSet *,long>(char const *,char const *,int,TraceLevel,ushort const *,CServerSet *,long)
0x1800c7775  xor     eax, eax
0x1800c7777  mov     rcx, [rbp+40h+var_30]
0x1800c777b  xor     rcx, rbp; StackCookie
0x1800c777e  call    __security_check_cookie
0x1800c7783  lea     rsp, [rbp+28h]
0x1800c7787  pop     r14
0x1800c7789  pop     rsi
0x1800c778a  pop     rbx
0x1800c778b  pop     rbp
0x1800c778c  retn
```
