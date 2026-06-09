# NotificationParser::WpnGetUserSid(ulong,void *)

- ea: `0x18002df8c`
- end: `0x18002e089`
- name: `?WpnGetUserSid@NotificationParser@@AEAAJKPEAX@Z`
- size: `253`
- prototype: `int(NotificationParser *__hidden this, unsigned int, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001d4cc`

## callees

- `0x1800070e8`
- `0x18001ff00`
- `0x18002cd98`
- `0x18002df8c`
- `0x1800307cc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002dfc9`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002dfc9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002dfb7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002dfb7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002dffc`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002dffc`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002e03e`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002e03e`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18002e011`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18002e011`

## pseudocode

```c
__int64 __fastcall NotificationParser::WpnGetUserSid(NotificationParser *this, __int64 a2, void *a3)
{
  HANDLE CurrentProcess; // rax
  __int64 v5; // rdx
  unsigned int v6; // ebx
  DWORD LengthSid; // eax
  int ReturnLength; // [rsp+20h] [rbp-39h]
  void *TokenHandle; // [rsp+30h] [rbp-29h] BYREF
  DWORD v11; // [rsp+38h] [rbp-21h] BYREF
  void *TokenInformation; // [rsp+40h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 0x20008u, &TokenHandle) )
  {
    v5 = 876;
LABEL_7:
    v6 = -2147467259;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)0x80004005LL,
      ReturnLength);
    goto LABEL_11;
  }
  v11 = 0;
  if ( !GetTokenInformation(TokenHandle, TokenUser, &TokenInformation, 0x54u, &v11) )
  {
    v5 = 884;
    goto LABEL_7;
  }
  if ( !IsValidSid(TokenInformation) )
  {
    v5 = 886;
    goto LABEL_7;
  }
  LengthSid = GetLengthSid(TokenInformation);
  if ( LengthSid <= 0x44 )
  {
    memcpy_0(a3, TokenInformation, LengthSid);
    v6 = 0;
  }
  else
  {
    v6 = -2147024774;
  }
LABEL_11:
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  return v6;
}

```

## disassembly

```asm
0x18002df8c  mov     [rsp-8+arg_0], rbx
0x18002df91  push    rbp
0x18002df92  lea     rbp, [rsp-57h]
0x18002df97  sub     rsp, 0B0h
0x18002df9e  mov     rax, cs:__security_cookie
0x18002dfa5  xor     rax, rsp
0x18002dfa8  mov     [rbp+57h+var_10], rax
0x18002dfac  mov     rbx, r8
0x18002dfaf  mov     [rbp+57h+TokenHandle], 0
0x18002dfb7  call    cs:__imp_GetCurrentProcess
0x18002dfbd  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x18002dfc1  mov     edx, 20008h; DesiredAccess
0x18002dfc6  mov     rcx, rax; ProcessHandle
0x18002dfc9  call    cs:__imp_OpenProcessToken
0x18002dfcf  test    eax, eax
0x18002dfd1  jnz     short loc_18002DFDA
0x18002dfd3  mov     edx, 36Ch
0x18002dfd8  jmp     short loc_18002E020
0x18002dfda  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x18002dfde  lea     rax, [rbp+57h+var_78]
0x18002dfe2  mov     r9d, 54h ; 'T'; TokenInformationLength
0x18002dfe8  mov     [rbp+57h+var_78], 0
0x18002dfef  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x18002dff3  mov     qword ptr [rsp+0B0h+ReturnLength], rax; int
0x18002dff8  lea     edx, [r9-53h]; TokenInformationClass
0x18002dffc  call    cs:__imp_GetTokenInformation
0x18002e002  test    eax, eax
0x18002e004  jnz     short loc_18002E00D
0x18002e006  mov     edx, 374h
0x18002e00b  jmp     short loc_18002E020
0x18002e00d  mov     rcx, [rbp+57h+TokenInformation]; pSid
0x18002e011  call    cs:__imp_IsValidSid
0x18002e017  test    eax, eax
0x18002e019  jnz     short loc_18002E03A
0x18002e01b  mov     edx, 376h; void *
0x18002e020  mov     rcx, [rbp+5Fh]; this
0x18002e024  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18002e02b  mov     ebx, 80004005h
0x18002e030  mov     r9d, ebx; char *
0x18002e033  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e038  jmp     short loc_18002E061
0x18002e03a  mov     rcx, [rbp+57h+TokenInformation]; pSid
0x18002e03e  call    cs:__imp_GetLengthSid
0x18002e044  cmp     eax, 44h ; 'D'
0x18002e047  jbe     short loc_18002E050
0x18002e049  mov     ebx, 8007007Ah
0x18002e04e  jmp     short loc_18002E061
0x18002e050  mov     rdx, [rbp+57h+TokenInformation]; Src
0x18002e054  mov     rcx, rbx; void *
0x18002e057  mov     r8d, eax; Size
0x18002e05a  call    memcpy_0
0x18002e05f  xor     ebx, ebx
0x18002e061  lea     rcx, [rbp+57h+TokenHandle]
0x18002e065  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002e06a  mov     eax, ebx
0x18002e06c  mov     rcx, [rbp+57h+var_10]
0x18002e070  xor     rcx, rsp; StackCookie
0x18002e073  call    __security_check_cookie
0x18002e078  mov     rbx, [rsp+0B0h+arg_0]
0x18002e080  add     rsp, 0B0h
0x18002e087  pop     rbp
0x18002e088  retn
```
