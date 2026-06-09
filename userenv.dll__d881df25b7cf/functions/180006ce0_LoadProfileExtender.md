# LoadProfileExtender

- ea: `0x180006ce0`
- end: `0x180006e11`
- name: `LoadProfileExtender`
- size: `305`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800055d8`
- `0x180005a48`
- `0x180005b30`
- `0x180006160`
- `0x1800062ac`
- `0x1800065d8`
- `0x1800069c8`
- `0x180006ce0`
- `0x18000db08`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180006d83`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180006d83`
- `RPCRT4!RpcRevertToSelf` at `0x180006d6a`
- `RPCRT4!RpcRevertToSelf` at `0x180006d6a`

## string_xrefs

- `0x180006d3e`: `onecore\ds\security\gina\profile\userenv\dll\profrpc.cpp`
- `0x180006dab`: `onecore\ds\security\gina\profile\userenv\dll\profrpc.cpp`

## pseudocode

```c
__int64 __fastcall LoadProfileExtender(void *a1)
{
  int v2; // eax
  int v3; // ebx
  int UserNameAndDomain; // eax
  HANDLE v6[2]; // [rsp+20h] [rbp-19h] BYREF
  __int64 v7; // [rsp+30h] [rbp-9h]
  int v8; // [rsp+38h] [rbp-1h]
  __int128 v9; // [rsp+40h] [rbp+7h]
  _PROFILEINFOW v10; // [rsp+50h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+5Fh]

  v10.dwSize = 56;
  LODWORD(v6[0]) = 0;
  v6[1] = 0;
  v7 = 0;
  memset(&v10.dwFlags, 0, 52);
  v8 = 0;
  v9 = 0;
  v2 = CThreadContext::ImpersonateUser((CThreadContext *)v6, a1);
  v3 = v2;
  if ( v2 >= 0 )
  {
    UserNameAndDomain = GetUserNameAndDomain(NameSamCompatible, &v10.lpUserName, 0);
    v3 = UserNameAndDomain;
    if ( UserNameAndDomain >= 0 )
    {
      CThreadContext::RevertToPreviousToken(v6);
      v3 = _LoadUnloadUserProfileClient(0, a1, &v10);
      ResultFromHeapFree(v10.lpUserName);
      if ( v3 >= 0 )
        v3 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x231,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\userenv\\dll\\profrpc.cpp",
        (const char *)(unsigned int)UserNameAndDomain,
        (int)v6[0]);
    }
    CThreadContext::~CThreadContext((CThreadContext *)v6);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x22F,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\userenv\\dll\\profrpc.cpp",
      (const char *)(unsigned int)v2,
      (int)v6[0]);
    CThreadContext::RevertPrivileges((CThreadContext *)v6);
    CThreadContext::RevertToPreviousToken(v6);
    if ( HIDWORD(v7) )
    {
      RpcRevertToSelf();
      HIDWORD(v7) = 0;
    }
    if ( (_DWORD)v7 )
      RevertToSelf();
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180006ce0  mov     [rsp-8+arg_0], rbx
0x180006ce5  mov     [rsp-8+arg_8], rdi
0x180006cea  push    rbp
0x180006ceb  lea     rbp, [rsp-57h]
0x180006cf0  sub     rsp, 90h
0x180006cf7  xor     eax, eax
0x180006cf9  mov     [rbp+57h+var_40.dwSize], 38h ; '8'
0x180006d00  xorps   xmm0, xmm0
0x180006d03  mov     dword ptr [rbp+57h+var_40.hProfile+4], eax
0x180006d06  mov     rdi, rcx
0x180006d09  mov     [rbp+57h+var_70], eax
0x180006d0c  mov     rdx, rcx; void *
0x180006d0f  mov     [rbp+57h+var_68], rax
0x180006d13  lea     rcx, [rbp+57h+var_70]; this
0x180006d17  mov     [rbp+57h+var_60], rax
0x180006d1b  movups  xmmword ptr [rbp+57h+var_40.dwFlags], xmm0
0x180006d1f  mov     [rbp+57h+var_58], eax
0x180006d22  movups  xmmword ptr [rbp+57h+var_40.lpProfilePath+4], xmm0
0x180006d26  movups  xmmword ptr [rbp+57h+var_40.lpServerName+4], xmm0
0x180006d2a  movdqu  [rbp+57h+var_50], xmm0
0x180006d2f  call    ?ImpersonateUser@CThreadContext@@QEAAJPEAX@Z; CThreadContext::ImpersonateUser(void *)
0x180006d34  mov     ebx, eax
0x180006d36  test    eax, eax
0x180006d38  jns     short loc_180006D91
0x180006d3a  mov     rcx, [rbp+5Fh]; this
0x180006d3e  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\gina\\profile\\u"...
0x180006d45  mov     r9d, eax; char *
0x180006d48  mov     edx, 22Fh; void *
0x180006d4d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006d52  lea     rcx, [rbp+57h+var_70]; this
0x180006d56  call    ?RevertPrivileges@CThreadContext@@QEAAJXZ; CThreadContext::RevertPrivileges(void)
0x180006d5b  lea     rcx, [rbp+57h+var_70]; this
0x180006d5f  call    ?RevertToPreviousToken@CThreadContext@@QEAAXXZ; CThreadContext::RevertToPreviousToken(void)
0x180006d64  cmp     dword ptr [rbp+57h+var_60+4], 0
0x180006d68  jz      short loc_180006D7D
0x180006d6a  call    cs:__imp_RpcRevertToSelf
0x180006d71  nop     dword ptr [rax+rax+00h]
0x180006d76  mov     dword ptr [rbp+57h+var_60+4], 0
0x180006d7d  cmp     dword ptr [rbp+57h+var_60], 0
0x180006d81  jz      short loc_180006DF9
0x180006d83  call    cs:__imp_RevertToSelf
0x180006d8a  nop     dword ptr [rax+rax+00h]
0x180006d8f  jmp     short loc_180006DF9
0x180006d91  xor     r8d, r8d; unsigned __int16 **
0x180006d94  lea     rdx, [rbp+57h+var_40.lpUserName]; unsigned __int16 **
0x180006d98  lea     ecx, [r8+2]; enum EXTENDED_NAME_FORMAT
0x180006d9c  call    ?GetUserNameAndDomain@@YAJW4EXTENDED_NAME_FORMAT@@PEAPEAG1@Z; GetUserNameAndDomain(EXTENDED_NAME_FORMAT,ushort * *,ushort * *)
0x180006da1  mov     ebx, eax
0x180006da3  test    eax, eax
0x180006da5  jns     short loc_180006DC1
0x180006da7  mov     rcx, [rbp+5Fh]; this
0x180006dab  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\gina\\profile\\u"...
0x180006db2  mov     r9d, eax; char *
0x180006db5  mov     edx, 231h; void *
0x180006dba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006dbf  jmp     short loc_180006DF0
0x180006dc1  lea     rcx, [rbp+57h+var_70]; this
0x180006dc5  call    ?RevertToPreviousToken@CThreadContext@@QEAAXXZ; CThreadContext::RevertToPreviousToken(void)
0x180006dca  lea     r8, [rbp+57h+var_40]; struct _PROFILEINFOW *
0x180006dce  mov     rdx, rdi; void *
0x180006dd1  xor     ecx, ecx; bool
0x180006dd3  call    ?_LoadUnloadUserProfileClient@@YAJ_NPEAXPEAU_PROFILEINFOW@@@Z; _LoadUnloadUserProfileClient(bool,void *,_PROFILEINFOW *)
0x180006dd8  mov     rcx, [rbp+57h+var_40.lpUserName]; lpMem
0x180006ddc  mov     ebx, eax
0x180006dde  test    eax, eax
0x180006de0  jns     short loc_180006DE9
0x180006de2  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x180006de7  jmp     short loc_180006DF0
0x180006de9  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x180006dee  xor     ebx, ebx
0x180006df0  lea     rcx, [rbp+57h+var_70]; this
0x180006df4  call    ??1CThreadContext@@QEAA@XZ; CThreadContext::~CThreadContext(void)
0x180006df9  lea     r11, [rsp+90h+var_s0]
0x180006e01  mov     eax, ebx
0x180006e03  mov     rbx, [r11+10h]
0x180006e07  mov     rdi, [r11+18h]
0x180006e0b  mov     rsp, r11
0x180006e0e  pop     rbp
0x180006e0f  retn
```
