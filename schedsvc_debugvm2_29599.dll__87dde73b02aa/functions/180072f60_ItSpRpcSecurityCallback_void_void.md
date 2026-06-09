# ItSpRpcSecurityCallback(void *,void *)

- ea: `0x180072f60`
- end: `0x180073111`
- name: `?ItSpRpcSecurityCallback@@YAJPEAX0@Z`
- size: `433`
- prototype: `RPC_IF_CALLBACK_FN`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180072f60`
- `0x18007e6d0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180072ff6`
- `msvcrt!_wcsicmp` at `0x180072ff6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073043`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073043`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800730cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800730cb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18007305e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18007305e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180073073`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180073073`
- `RPCRT4!RpcStringFreeW` at `0x1800730ac`
- `RPCRT4!RpcStringFreeW` at `0x1800730bc`
- `RPCRT4!RpcStringFreeW` at `0x1800730ac`
- `RPCRT4!RpcStringFreeW` at `0x1800730bc`
- `RPCRT4!RpcStringBindingParseW` at `0x180072fe1`
- `RPCRT4!RpcStringBindingParseW` at `0x180072fe1`
- `RPCRT4!RpcImpersonateClient` at `0x18007304f`
- `RPCRT4!RpcImpersonateClient` at `0x18007304f`
- `RPCRT4!RpcRevertToSelf` at `0x1800730e5`
- `RPCRT4!RpcRevertToSelf` at `0x1800730e5`
- `RPCRT4!RpcBindingToStringBindingW` at `0x180072fb6`
- `RPCRT4!RpcBindingToStringBindingW` at `0x180072fb6`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800730da`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800730da`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18007308c`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18007308c`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180073039`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180073039`

## pseudocode

```c
__int64 __fastcall ItSpRpcSecurityCallback(RPC_IF_HANDLE InterfaceUuid, void *Context)
{
  char v2; // di
  char v3; // si
  unsigned int LastError; // ebx
  HANDLE CurrentThread; // rax
  WINBOOL IsMember; // [rsp+60h] [rbp+7h] BYREF
  RPC_WSTR StringBinding; // [rsp+68h] [rbp+Fh] BYREF
  RPC_WSTR Protseq; // [rsp+70h] [rbp+17h] BYREF
  void *TokenHandle; // [rsp+78h] [rbp+1Fh] BYREF
  PSID SidToCheck; // [rsp+80h] [rbp+27h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+88h] [rbp+2Fh] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  IsMember = 0;
  StringBinding = 0;
  v2 = 0;
  Protseq = 0;
  v3 = 0;
  SidToCheck = 0;
  TokenHandle = 0;
  if ( RpcBindingToStringBindingW(Context, &StringBinding)
    || RpcStringBindingParseW(StringBinding, 0, &Protseq, 0, 0, 0)
    || _wcsicmp(Protseq, L"ncalrpc") )
  {
    LastError = 5;
    goto LABEL_11;
  }
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &SidToCheck) )
    goto LABEL_6;
  LastError = RpcImpersonateClient(0);
  if ( !LastError )
  {
    v2 = 1;
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 0x20008u, 0, &TokenHandle)
      || (v3 = 1, !CheckTokenMembership(TokenHandle, SidToCheck, &IsMember)) )
    {
LABEL_6:
      LastError = GetLastError();
      goto LABEL_11;
    }
    LastError = IsMember == 0 ? 5 : 0;
  }
LABEL_11:
  if ( StringBinding )
    RpcStringFreeW(&StringBinding);
  if ( Protseq )
    RpcStringFreeW(&Protseq);
  if ( v3 )
    CloseHandle(TokenHandle);
  if ( SidToCheck )
    FreeSid(SidToCheck);
  if ( v2 )
    RpcRevertToSelf();
  return LastError;
}

```

## disassembly

```asm
0x180072f60  mov     [rsp-8+arg_0], rbx
0x180072f65  mov     [rsp-8+arg_10], rsi
0x180072f6a  push    rbp
0x180072f6b  push    rdi
0x180072f6c  push    r14
0x180072f6e  lea     rbp, [rsp-47h]
0x180072f73  sub     rsp, 0A0h
0x180072f7a  mov     rax, cs:__security_cookie
0x180072f81  xor     rax, rsp
0x180072f84  mov     [rbp+57h+var_20], rax
0x180072f88  xor     r14d, r14d
0x180072f8b  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x180072f91  mov     rcx, rdx; Binding
0x180072f94  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], r14d
0x180072f98  lea     rdx, [rbp+57h+StringBinding]; StringBinding
0x180072f9c  mov     [rbp+57h+IsMember], r14d
0x180072fa0  mov     [rbp+57h+StringBinding], r14
0x180072fa4  mov     dil, r14b
0x180072fa7  mov     [rbp+57h+Protseq], r14
0x180072fab  mov     sil, r14b
0x180072fae  mov     [rbp+57h+SidToCheck], r14
0x180072fb2  mov     [rbp+57h+TokenHandle], r14
0x180072fb6  call    cs:__imp_RpcBindingToStringBindingW
0x180072fbc  test    eax, eax
0x180072fbe  jz      short loc_180072FCA
0x180072fc0  mov     ebx, 5
0x180072fc5  jmp     loc_1800730A2
0x180072fca  mov     rcx, [rbp+57h+StringBinding]; StringBinding
0x180072fce  lea     r8, [rbp+57h+Protseq]; Protseq
0x180072fd2  mov     [rsp+0B0h+NetworkOptions], r14; NetworkOptions
0x180072fd7  xor     r9d, r9d; NetworkAddr
0x180072fda  xor     edx, edx; ObjUuid
0x180072fdc  mov     [rsp+0B0h+Endpoint], r14; Endpoint
0x180072fe1  call    cs:__imp_RpcStringBindingParseW
0x180072fe7  test    eax, eax
0x180072fe9  jnz     short loc_180072FC0
0x180072feb  mov     rcx, [rbp+57h+Protseq]; String1
0x180072fef  lea     rdx, aNcalrpc; "ncalrpc"
0x180072ff6  call    cs:__imp__wcsicmp
0x180072ffc  test    eax, eax
0x180072ffe  jnz     short loc_180072FC0
0x180073000  lea     rax, [rbp+57h+SidToCheck]
0x180073004  mov     r9d, 220h; nSubAuthority1
0x18007300a  mov     [rsp+0B0h+pSid], rax; pSid
0x18007300f  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x180073013  mov     [rsp+0B0h+nSubAuthority7], r14d; nSubAuthority7
0x180073018  mov     r8d, 20h ; ' '; nSubAuthority0
0x18007301e  mov     [rsp+0B0h+nSubAuthority6], r14d; nSubAuthority6
0x180073023  mov     dl, 2; nSubAuthorityCount
0x180073025  mov     [rsp+0B0h+nSubAuthority5], r14d; nSubAuthority5
0x18007302a  mov     [rsp+0B0h+nSubAuthority4], r14d; nSubAuthority4
0x18007302f  mov     dword ptr [rsp+0B0h+NetworkOptions], r14d; nSubAuthority3
0x180073034  mov     dword ptr [rsp+0B0h+Endpoint], r14d; nSubAuthority2
0x180073039  call    cs:__imp_AllocateAndInitializeSid
0x18007303f  test    eax, eax
0x180073041  jnz     short loc_18007304D
0x180073043  call    cs:__imp_GetLastError
0x180073049  mov     ebx, eax
0x18007304b  jmp     short loc_1800730A2
0x18007304d  xor     ecx, ecx; BindingHandle
0x18007304f  call    cs:__imp_RpcImpersonateClient
0x180073055  mov     ebx, eax
0x180073057  test    eax, eax
0x180073059  jnz     short loc_1800730A2
0x18007305b  mov     dil, 1
0x18007305e  call    cs:__imp_GetCurrentThread
0x180073064  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x180073068  xor     r8d, r8d; OpenAsSelf
0x18007306b  mov     rcx, rax; ThreadHandle
0x18007306e  mov     edx, 20008h; DesiredAccess
0x180073073  call    cs:__imp_OpenThreadToken
0x180073079  test    eax, eax
0x18007307b  jz      short loc_180073043
0x18007307d  mov     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x180073081  lea     r8, [rbp+57h+IsMember]; IsMember
0x180073085  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x180073089  mov     sil, dil
0x18007308c  call    cs:__imp_CheckTokenMembership
0x180073092  test    eax, eax
0x180073094  jz      short loc_180073043
0x180073096  mov     eax, [rbp+57h+IsMember]
0x180073099  neg     eax
0x18007309b  sbb     ebx, ebx
0x18007309d  not     ebx
0x18007309f  and     ebx, 5
0x1800730a2  cmp     [rbp+57h+StringBinding], r14
0x1800730a6  jz      short loc_1800730B2
0x1800730a8  lea     rcx, [rbp+57h+StringBinding]; String
0x1800730ac  call    cs:__imp_RpcStringFreeW
0x1800730b2  cmp     [rbp+57h+Protseq], r14
0x1800730b6  jz      short loc_1800730C2
0x1800730b8  lea     rcx, [rbp+57h+Protseq]; String
0x1800730bc  call    cs:__imp_RpcStringFreeW
0x1800730c2  test    sil, sil
0x1800730c5  jz      short loc_1800730D1
0x1800730c7  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x1800730cb  call    cs:__imp_CloseHandle
0x1800730d1  mov     rcx, [rbp+57h+SidToCheck]; pSid
0x1800730d5  test    rcx, rcx
0x1800730d8  jz      short loc_1800730E0
0x1800730da  call    cs:__imp_FreeSid
0x1800730e0  test    dil, dil
0x1800730e3  jz      short loc_1800730EB
0x1800730e5  call    cs:__imp_RpcRevertToSelf
0x1800730eb  mov     eax, ebx
0x1800730ed  mov     rcx, [rbp+57h+var_20]
0x1800730f1  xor     rcx, rsp; StackCookie
0x1800730f4  call    __security_check_cookie
0x1800730f9  lea     r11, [rsp+0B0h+var_10]
0x180073101  mov     rbx, [r11+20h]
0x180073105  mov     rsi, [r11+30h]
0x180073109  mov     rsp, r11
0x18007310c  pop     r14
0x18007310e  pop     rdi
0x18007310f  pop     rbp
0x180073110  retn
```
