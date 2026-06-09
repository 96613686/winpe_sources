# _LoadUnloadUserProfileClient(bool,void *,_PROFILEINFOW *)

- ea: `0x1800059a4`
- end: `0x180005b20`
- name: `?_LoadUnloadUserProfileClient@@YAJ_NPEAXPEAU_PROFILEINFOW@@@Z`
- size: `380`
- prototype: `__int64 __fastcall(char, void *, struct _PROFILEINFOW *)`
- caller_count: `4`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000246c`
- `0x18000429c`
- `0x1800065b0`
- `0x1800067b0`

## callees

- `0x180004f28`
- `0x180005320`
- `0x1800059a4`
- `0x180005b28`
- `0x180005de0`
- `0x18000cea0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800059f2`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180005a4f`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180005ab0`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800059f2`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180005a4f`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180005ab0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005ad6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005aed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005b03`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005ad6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005aed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005b03`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180005a73`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180005acc`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180005a73`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180005acc`
- `RPCRT4!RpcRevertToSelf` at `0x180005ae2`
- `RPCRT4!RpcRevertToSelf` at `0x180005b12`
- `RPCRT4!RpcRevertToSelf` at `0x180005ae2`
- `RPCRT4!RpcRevertToSelf` at `0x180005b12`

## string_xrefs

- `0x180005a8a`: `onecore\ds\security\gina\profile\userenv\dll\profrpc.cpp`

## pseudocode

```c
__int64 __fastcall _LoadUnloadUserProfileClient(char a1, void *a2, struct _PROFILEINFOW *a3)
{
  int v3; // eax
  int v4; // ebx
  _QWORD v6[4]; // [rsp+20h] [rbp-50h] BYREF
  int v7; // [rsp+40h] [rbp-30h] BYREF
  HANDLE Token; // [rsp+48h] [rbp-28h]
  __int64 v9; // [rsp+50h] [rbp-20h]
  int v10; // [rsp+58h] [rbp-18h]
  __int128 v11; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]
  char v13; // [rsp+90h] [rbp+20h] BYREF
  void *v14; // [rsp+98h] [rbp+28h] BYREF
  struct _PROFILEINFOW *v15; // [rsp+A0h] [rbp+30h] BYREF

  v15 = a3;
  v14 = a2;
  v13 = a1;
  v7 = 0;
  Token = 0;
  v9 = 0;
  v10 = 0;
  v11 = 0;
  v3 = CThreadContext::ImpersonateUser((CThreadContext *)&v7, a2);
  v4 = v3;
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCD,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\userenv\\dll\\profrpc.cpp",
      (const char *)(unsigned int)v3,
      v6[0]);
    CThreadContext::RevertPrivileges((CThreadContext *)&v7);
    if ( v7 )
    {
      SetThreadToken(0, Token);
      if ( Token )
      {
        CloseHandle(Token);
        Token = 0;
      }
      v7 = 0;
    }
    if ( HIDWORD(v9) )
    {
      RpcRevertToSelf();
      HIDWORD(v9) = 0;
    }
    if ( (_DWORD)v9 )
      RevertToSelf();
    return (unsigned int)v4;
  }
  if ( v7 )
  {
    SetThreadToken(0, Token);
    if ( Token )
    {
      CloseHandle(Token);
      Token = 0;
    }
    v7 = 0;
  }
  v6[0] = &v7;
  v6[1] = &v15;
  v6[2] = &v14;
  v6[3] = &v13;
  v4 = InvokeUserProfileRPC__lambda_7f94f01fc3cf1545aca7f938a37387d8_(v6);
  if ( v4 < 0 )
  {
    CThreadContext::~CThreadContext((CThreadContext *)&v7);
    return (unsigned int)v4;
  }
  CThreadContext::RevertPrivileges((CThreadContext *)&v7);
  if ( v7 )
  {
    SetThreadToken(0, Token);
    if ( Token )
    {
      CloseHandle(Token);
      Token = 0;
    }
    v7 = 0;
  }
  if ( HIDWORD(v9) )
  {
    RpcRevertToSelf();
    HIDWORD(v9) = 0;
  }
  if ( (_DWORD)v9 )
    RevertToSelf();
  return 0;
}

```

## disassembly

```asm
0x1800059a4  mov     [rsp-18h+arg_10], r8
0x1800059a9  mov     [rsp-18h+arg_8], rdx
0x1800059ae  mov     [rsp-18h+arg_0], cl
0x1800059b2  push    rbp
0x1800059b3  push    rbx
0x1800059b4  push    rdi
0x1800059b5  mov     rbp, rsp
0x1800059b8  sub     rsp, 70h
0x1800059bc  xor     edi, edi
0x1800059be  mov     [rbp+var_30], edi
0x1800059c1  mov     [rbp+Token], rdi
0x1800059c5  mov     [rbp+var_20], rdi
0x1800059c9  mov     [rbp+var_18], edi
0x1800059cc  xorps   xmm0, xmm0
0x1800059cf  movdqu  [rbp+var_10], xmm0
0x1800059d4  lea     rcx, [rbp+var_30]; this
0x1800059d8  call    ?ImpersonateUser@CThreadContext@@QEAAJPEAX@Z; CThreadContext::ImpersonateUser(void *)
0x1800059dd  mov     ebx, eax
0x1800059df  test    eax, eax
0x1800059e1  js      loc_180005A83
0x1800059e7  cmp     [rbp+var_30], edi
0x1800059ea  jz      short loc_180005A08
0x1800059ec  mov     rdx, [rbp+Token]; Token
0x1800059f0  xor     ecx, ecx; Thread
0x1800059f2  call    cs:__imp_SetThreadToken
0x1800059f8  mov     rcx, [rbp+Token]; hObject
0x1800059fc  test    rcx, rcx
0x1800059ff  jnz     loc_180005AED
0x180005a05  mov     [rbp+var_30], edi
0x180005a08  lea     rax, [rbp+var_30]
0x180005a0c  mov     [rbp+var_50], rax
0x180005a10  lea     rax, [rbp+arg_10]
0x180005a14  mov     [rbp+var_48], rax
0x180005a18  lea     rax, [rbp+arg_8]
0x180005a1c  mov     [rbp+var_40], rax
0x180005a20  lea     rax, [rbp+arg_0]
0x180005a24  mov     [rbp+var_38], rax
0x180005a28  lea     rcx, [rbp+var_50]
0x180005a2c  call    InvokeUserProfileRPC__lambda_7f94f01fc3cf1545aca7f938a37387d8___; InvokeUserProfileRPC__lambda_7f94f01fc3cf1545aca7f938a37387d8_
0x180005a31  mov     ebx, eax
0x180005a33  lea     rcx, [rbp+var_30]; this
0x180005a37  test    eax, eax
0x180005a39  js      loc_180005AFC
0x180005a3f  call    ?RevertPrivileges@CThreadContext@@QEAAJXZ; CThreadContext::RevertPrivileges(void)
0x180005a44  cmp     [rbp+var_30], edi
0x180005a47  jz      short loc_180005A65
0x180005a49  mov     rdx, [rbp+Token]; Token
0x180005a4d  xor     ecx, ecx; Thread
0x180005a4f  call    cs:__imp_SetThreadToken
0x180005a55  mov     rcx, [rbp+Token]; hObject
0x180005a59  test    rcx, rcx
0x180005a5c  jnz     loc_180005B03
0x180005a62  mov     [rbp+var_30], edi
0x180005a65  cmp     dword ptr [rbp+var_20+4], edi
0x180005a68  jnz     loc_180005B12
0x180005a6e  cmp     dword ptr [rbp+var_20], edi
0x180005a71  jz      short loc_180005A79
0x180005a73  call    cs:__imp_RevertToSelf
0x180005a79  xor     eax, eax
0x180005a7b  add     rsp, 70h
0x180005a7f  pop     rdi
0x180005a80  pop     rbx
0x180005a81  pop     rbp
0x180005a82  retn
0x180005a83  mov     rcx, [rbp+18h]; this
0x180005a87  mov     r9d, ebx; char *
0x180005a8a  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\gina\\profile\\u"...
0x180005a91  mov     edx, 0CDh; void *
0x180005a96  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005a9b  nop
0x180005a9c  lea     rcx, [rbp+var_30]; this
0x180005aa0  call    ?RevertPrivileges@CThreadContext@@QEAAJXZ; CThreadContext::RevertPrivileges(void)
0x180005aa5  cmp     [rbp+var_30], edi
0x180005aa8  jz      short loc_180005AC2
0x180005aaa  mov     rdx, [rbp+Token]; Token
0x180005aae  xor     ecx, ecx; Thread
0x180005ab0  call    cs:__imp_SetThreadToken
0x180005ab6  mov     rcx, [rbp+Token]; hObject
0x180005aba  test    rcx, rcx
0x180005abd  jnz     short loc_180005AD6
0x180005abf  mov     [rbp+var_30], edi
0x180005ac2  cmp     dword ptr [rbp+var_20+4], edi
0x180005ac5  jnz     short loc_180005AE2
0x180005ac7  cmp     dword ptr [rbp+var_20], edi
0x180005aca  jz      short loc_180005AD2
0x180005acc  call    cs:__imp_RevertToSelf
0x180005ad2  mov     eax, ebx
0x180005ad4  jmp     short loc_180005A7B
0x180005ad6  call    cs:__imp_CloseHandle
0x180005adc  mov     [rbp+Token], rdi
0x180005ae0  jmp     short loc_180005ABF
0x180005ae2  call    cs:__imp_RpcRevertToSelf
0x180005ae8  mov     dword ptr [rbp+var_20+4], edi
0x180005aeb  jmp     short loc_180005AC7
0x180005aed  call    cs:__imp_CloseHandle
0x180005af3  mov     [rbp+Token], rdi
0x180005af7  jmp     loc_180005A05
0x180005afc  call    ??1CThreadContext@@QEAA@XZ; CThreadContext::~CThreadContext(void)
0x180005b01  jmp     short loc_180005AD2
0x180005b03  call    cs:__imp_CloseHandle
0x180005b09  mov     [rbp+Token], rdi
0x180005b0d  jmp     loc_180005A62
0x180005b12  call    cs:__imp_RpcRevertToSelf
0x180005b18  mov     dword ptr [rbp+var_20+4], edi
0x180005b1b  jmp     loc_180005A6E
```
