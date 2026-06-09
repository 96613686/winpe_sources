# LoadProfileExtender

- ea: `0x1800067b0`
- end: `0x1800068fb`
- name: `LoadProfileExtender`
- size: `331`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180004f28`
- `0x180005320`
- `0x1800053f0`
- `0x1800059a4`
- `0x180005de0`
- `0x180005e20`
- `0x1800063d8`
- `0x1800067b0`
- `0x18000cea0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180006837`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180006837`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006846`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006846`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180006874`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180006874`
- `RPCRT4!RpcRevertToSelf` at `0x180006861`
- `RPCRT4!RpcRevertToSelf` at `0x180006861`

## string_xrefs

- `0x18000680e`: `onecore\ds\security\gina\profile\userenv\dll\profrpc.cpp`
- `0x180006896`: `onecore\ds\security\gina\profile\userenv\dll\profrpc.cpp`

## pseudocode

```c
__int64 __fastcall LoadProfileExtender(void *a1)
{
  int v2; // eax
  int v3; // ebx
  int UserNameAndDomain; // eax
  HANDLE v6; // [rsp+20h] [rbp-19h] BYREF
  HANDLE Token; // [rsp+28h] [rbp-11h]
  __int64 v8; // [rsp+30h] [rbp-9h]
  int v9; // [rsp+38h] [rbp-1h]
  __int128 v10; // [rsp+40h] [rbp+7h]
  _PROFILEINFOW v11; // [rsp+50h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+5Fh]

  v11.dwSize = 56;
  LODWORD(v6) = 0;
  Token = 0;
  v8 = 0;
  memset(&v11.dwFlags, 0, 52);
  v9 = 0;
  v10 = 0;
  v2 = CThreadContext::ImpersonateUser((CThreadContext *)&v6, a1);
  v3 = v2;
  if ( v2 >= 0 )
  {
    UserNameAndDomain = GetUserNameAndDomain(NameSamCompatible, &v11.lpUserName, 0);
    v3 = UserNameAndDomain;
    if ( UserNameAndDomain >= 0 )
    {
      CThreadContext::RevertToPreviousToken(&v6);
      v3 = _LoadUnloadUserProfileClient(0, a1, &v11);
      ResultFromHeapFree(v11.lpUserName);
      if ( v3 >= 0 )
        v3 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x231,
        (int)"onecore\\ds\\security\\gina\\profile\\userenv\\dll\\profrpc.cpp",
        (const char *)(unsigned int)UserNameAndDomain);
    }
    CThreadContext::~CThreadContext((CThreadContext *)&v6);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x22F,
      (int)"onecore\\ds\\security\\gina\\profile\\userenv\\dll\\profrpc.cpp",
      (const char *)(unsigned int)v2);
    CThreadContext::RevertPrivileges((CThreadContext *)&v6);
    if ( (_DWORD)v6 )
    {
      SetThreadToken(0, Token);
      if ( Token )
      {
        CloseHandle(Token);
        Token = 0;
      }
      LODWORD(v6) = 0;
    }
    if ( HIDWORD(v8) )
    {
      RpcRevertToSelf();
      HIDWORD(v8) = 0;
    }
    if ( (_DWORD)v8 )
      RevertToSelf();
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800067b0  mov     [rsp-8+arg_0], rbx
0x1800067b5  mov     [rsp-8+arg_8], rdi
0x1800067ba  push    rbp
0x1800067bb  lea     rbp, [rsp-57h]
0x1800067c0  sub     rsp, 90h
0x1800067c7  xor     eax, eax
0x1800067c9  mov     [rbp+57h+var_40.dwSize], 38h ; '8'
0x1800067d0  xorps   xmm0, xmm0
0x1800067d3  mov     dword ptr [rbp+57h+var_40.hProfile+4], eax
0x1800067d6  mov     rdi, rcx
0x1800067d9  mov     dword ptr [rbp+57h+var_70], eax
0x1800067dc  mov     rdx, rcx; void *
0x1800067df  mov     [rbp+57h+Token], rax
0x1800067e3  lea     rcx, [rbp+57h+var_70]; this
0x1800067e7  mov     [rbp+57h+var_60], rax
0x1800067eb  movups  xmmword ptr [rbp+57h+var_40.dwFlags], xmm0
0x1800067ef  mov     [rbp+57h+var_58], eax
0x1800067f2  movups  xmmword ptr [rbp+57h+var_40.lpProfilePath+4], xmm0
0x1800067f6  movups  xmmword ptr [rbp+57h+var_40.lpServerName+4], xmm0
0x1800067fa  movdqu  [rbp+57h+var_50], xmm0
0x1800067ff  call    ?ImpersonateUser@CThreadContext@@QEAAJPEAX@Z; CThreadContext::ImpersonateUser(void *)
0x180006804  mov     ebx, eax
0x180006806  test    eax, eax
0x180006808  jns     short loc_18000687C
0x18000680a  mov     rcx, [rbp+5Fh]; this
0x18000680e  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\gina\\profile\\u"...
0x180006815  mov     r9d, eax; char *
0x180006818  mov     edx, 22Fh; void *
0x18000681d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006822  lea     rcx, [rbp+57h+var_70]; this
0x180006826  call    ?RevertPrivileges@CThreadContext@@QEAAJXZ; CThreadContext::RevertPrivileges(void)
0x18000682b  cmp     dword ptr [rbp+57h+var_70], 0
0x18000682f  jz      short loc_18000685B
0x180006831  mov     rdx, [rbp+57h+Token]; Token
0x180006835  xor     ecx, ecx; Thread
0x180006837  call    cs:__imp_SetThreadToken
0x18000683d  mov     rcx, [rbp+57h+Token]; hObject
0x180006841  test    rcx, rcx
0x180006844  jz      short loc_180006854
0x180006846  call    cs:__imp_CloseHandle
0x18000684c  mov     [rbp+57h+Token], 0
0x180006854  mov     dword ptr [rbp+57h+var_70], 0
0x18000685b  cmp     dword ptr [rbp+57h+var_60+4], 0
0x18000685f  jz      short loc_18000686E
0x180006861  call    cs:__imp_RpcRevertToSelf
0x180006867  mov     dword ptr [rbp+57h+var_60+4], 0
0x18000686e  cmp     dword ptr [rbp+57h+var_60], 0
0x180006872  jz      short loc_1800068E4
0x180006874  call    cs:__imp_RevertToSelf
0x18000687a  jmp     short loc_1800068E4
0x18000687c  xor     r8d, r8d; unsigned __int16 **
0x18000687f  lea     rdx, [rbp+57h+var_40.lpUserName]; unsigned __int16 **
0x180006883  lea     ecx, [r8+2]; enum EXTENDED_NAME_FORMAT
0x180006887  call    ?GetUserNameAndDomain@@YAJW4EXTENDED_NAME_FORMAT@@PEAPEAG1@Z; GetUserNameAndDomain(EXTENDED_NAME_FORMAT,ushort * *,ushort * *)
0x18000688c  mov     ebx, eax
0x18000688e  test    eax, eax
0x180006890  jns     short loc_1800068AC
0x180006892  mov     rcx, [rbp+5Fh]; this
0x180006896  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\gina\\profile\\u"...
0x18000689d  mov     r9d, eax; char *
0x1800068a0  mov     edx, 231h; void *
0x1800068a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800068aa  jmp     short loc_1800068DB
0x1800068ac  lea     rcx, [rbp+57h+var_70]; this
0x1800068b0  call    ?RevertToPreviousToken@CThreadContext@@QEAAXXZ; CThreadContext::RevertToPreviousToken(void)
0x1800068b5  lea     r8, [rbp+57h+var_40]; struct _PROFILEINFOW *
0x1800068b9  mov     rdx, rdi; void *
0x1800068bc  xor     ecx, ecx; bool
0x1800068be  call    ?_LoadUnloadUserProfileClient@@YAJ_NPEAXPEAU_PROFILEINFOW@@@Z; _LoadUnloadUserProfileClient(bool,void *,_PROFILEINFOW *)
0x1800068c3  mov     rcx, [rbp+57h+var_40.lpUserName]; lpMem
0x1800068c7  mov     ebx, eax
0x1800068c9  test    eax, eax
0x1800068cb  jns     short loc_1800068D4
0x1800068cd  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x1800068d2  jmp     short loc_1800068DB
0x1800068d4  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x1800068d9  xor     ebx, ebx
0x1800068db  lea     rcx, [rbp+57h+var_70]; this
0x1800068df  call    ??1CThreadContext@@QEAA@XZ; CThreadContext::~CThreadContext(void)
0x1800068e4  lea     r11, [rsp+90h+var_s0]
0x1800068ec  mov     eax, ebx
0x1800068ee  mov     rbx, [r11+10h]
0x1800068f2  mov     rdi, [r11+18h]
0x1800068f6  mov     rsp, r11
0x1800068f9  pop     rbp
0x1800068fa  retn
```
