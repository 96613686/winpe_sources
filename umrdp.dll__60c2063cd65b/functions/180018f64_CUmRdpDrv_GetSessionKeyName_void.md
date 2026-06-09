# CUmRdpDrv::_GetSessionKeyName(void)

- ea: `0x180018f64`
- end: `0x180019105`
- name: `?_GetSessionKeyName@CUmRdpDrv@@AEAAJXZ`
- size: `417`
- prototype: `__int64 __fastcall(CUmRdpDrv *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001910c`

## callees

- `0x18000a01c`
- `0x180018f64`
- `0x180047ebe`
- `0x180047ef0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180018fb8`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180018fb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800190a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800190b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800190c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800190a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800190b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800190c3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800190af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800190af`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180019021`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180019021`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001900a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001900a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001906a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001906a`

## pseudocode

```c
__int64 __fastcall CUmRdpDrv::_GetSessionKeyName(CUmRdpDrv *this)
{
  int v2; // ebx
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  PDWORD ReturnLength; // [rsp+20h] [rbp-E0h]
  DWORD v7; // [rsp+30h] [rbp-D0h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-C8h] BYREF
  _OWORD TokenInformation[3]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v10; // [rsp+70h] [rbp-90h]
  struct _OSVERSIONINFOW VersionInformation; // [rsp+80h] [rbp-80h] BYREF

  if ( *((_DWORD *)this + 2) )
  {
    return 1;
  }
  else
  {
    memset_0(&VersionInformation.dwMajorVersion, 0, 0x110u);
    VersionInformation.dwOSVersionInfoSize = 276;
    if ( GetVersionExW(&VersionInformation) && VersionInformation.dwMajorVersion >= 6 )
    {
      v2 = StringCchPrintfW((unsigned __int16 *)this + 512, 0x1Eu, L"SessionInfo\\%d", **(unsigned int **)this);
      if ( v2 >= 0 )
        *((_DWORD *)this + 2) = 1;
    }
    else
    {
      v2 = -2147467259;
      TokenHandle = 0;
      CurrentThread = GetCurrentThread();
      if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
      {
        v10 = 0;
        v7 = 0;
        memset(TokenInformation, 0, sizeof(TokenInformation));
        if ( GetTokenInformation(TokenHandle, TokenStatistics, TokenInformation, 0x38u, &v7) )
        {
          LODWORD(ReturnLength) = DWORD2(TokenInformation[0]);
          StringCchPrintfW(
            (unsigned __int16 *)this + 512,
            0x1Eu,
            L"%08x%08x",
            HIDWORD(TokenInformation[0]),
            ReturnLength);
          v2 = 0;
          *((_DWORD *)this + 2) = 1;
        }
        else
        {
          GetLastError();
        }
        CloseHandle(TokenHandle);
      }
      else
      {
        GetLastError();
      }
    }
    if ( !*((_DWORD *)this + 2) )
    {
      LastError = GetLastError();
      v2 = LastError;
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180018f64  mov     [rsp-8+arg_8], rbx
0x180018f69  mov     [rsp-8+arg_10], rdi
0x180018f6e  push    rbp
0x180018f6f  lea     rbp, [rsp-0B0h]
0x180018f77  sub     rsp, 1B0h
0x180018f7e  mov     rax, cs:__security_cookie
0x180018f85  xor     rax, rsp
0x180018f88  mov     [rbp+0B0h+var_10], rax
0x180018f8f  cmp     dword ptr [rcx+8], 0
0x180018f93  mov     rdi, rcx
0x180018f96  jnz     loc_1800190DA
0x180018f9c  xor     edx, edx; Val
0x180018f9e  lea     rcx, [rbp+0B0h+VersionInformation.dwMajorVersion]; void *
0x180018fa2  mov     r8d, 110h; Size
0x180018fa8  call    memset_0
0x180018fad  lea     rcx, [rbp+0B0h+VersionInformation]; lpVersionInformation
0x180018fb1  mov     [rbp+0B0h+VersionInformation.dwOSVersionInfoSize], 114h
0x180018fb8  call    cs:__imp_GetVersionExW
0x180018fbe  test    eax, eax
0x180018fc0  jz      short loc_180018FFC
0x180018fc2  cmp     [rbp+0B0h+VersionInformation.dwMajorVersion], 6
0x180018fc6  jb      short loc_180018FFC
0x180018fc8  mov     r9, [rdi]
0x180018fcb  lea     rcx, [rdi+400h]; unsigned __int16 *
0x180018fd2  lea     r8, aSessioninfoD; "SessionInfo\\%d"
0x180018fd9  mov     edx, 1Eh; unsigned __int64
0x180018fde  mov     r9d, [r9]
0x180018fe1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180018fe6  mov     ebx, eax
0x180018fe8  test    eax, eax
0x180018fea  js      loc_1800190BD
0x180018ff0  mov     dword ptr [rdi+8], 1
0x180018ff7  jmp     loc_1800190BD
0x180018ffc  mov     ebx, 80004005h
0x180019001  mov     [rsp+1B0h+TokenHandle], 0
0x18001900a  call    cs:__imp_GetCurrentThread
0x180019010  mov     edx, 8; DesiredAccess
0x180019015  lea     r9, [rsp+1B0h+TokenHandle]; TokenHandle
0x18001901a  mov     rcx, rax; ThreadHandle
0x18001901d  lea     r8d, [rdx-7]; OpenAsSelf
0x180019021  call    cs:__imp_OpenThreadToken
0x180019027  test    eax, eax
0x180019029  jz      loc_1800190B7
0x18001902f  mov     rcx, [rsp+1B0h+TokenHandle]; TokenHandle
0x180019034  lea     r8, [rsp+1B0h+TokenInformation]; TokenInformation
0x180019039  xor     eax, eax
0x18001903b  xorps   xmm0, xmm0
0x18001903e  mov     r9d, 38h ; '8'; TokenInformationLength
0x180019044  mov     [rsp+1B0h+var_140], rax
0x180019049  mov     [rsp+1B0h+var_180], eax
0x18001904d  lea     rax, [rsp+1B0h+var_180]
0x180019052  movups  [rsp+1B0h+TokenInformation], xmm0
0x180019057  mov     [rsp+1B0h+ReturnLength], rax; ReturnLength
0x18001905c  lea     edx, [r9-2Eh]; TokenInformationClass
0x180019060  movups  [rsp+1B0h+var_160], xmm0
0x180019065  movups  [rsp+1B0h+var_150], xmm0
0x18001906a  call    cs:__imp_GetTokenInformation
0x180019070  test    eax, eax
0x180019072  jz      short loc_1800190A4
0x180019074  mov     eax, dword ptr [rsp+1B0h+TokenInformation+8]
0x180019078  lea     rcx, [rdi+400h]; unsigned __int16 *
0x18001907f  mov     r9d, dword ptr [rsp+1B0h+TokenInformation+0Ch]
0x180019084  lea     r8, a08x08x; "%08x%08x"
0x18001908b  mov     edx, 1Eh; unsigned __int64
0x180019090  mov     dword ptr [rsp+1B0h+ReturnLength], eax
0x180019094  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180019099  xor     ebx, ebx
0x18001909b  mov     dword ptr [rdi+8], 1
0x1800190a2  jmp     short loc_1800190AA
0x1800190a4  call    cs:__imp_GetLastError
0x1800190aa  mov     rcx, [rsp+1B0h+TokenHandle]; hObject
0x1800190af  call    cs:__imp_CloseHandle
0x1800190b5  jmp     short loc_1800190BD
0x1800190b7  call    cs:__imp_GetLastError
0x1800190bd  cmp     dword ptr [rdi+8], 0
0x1800190c1  jnz     short loc_1800190DF
0x1800190c3  call    cs:__imp_GetLastError
0x1800190c9  mov     ebx, eax
0x1800190cb  test    eax, eax
0x1800190cd  jle     short loc_1800190DF
0x1800190cf  movzx   ebx, ax
0x1800190d2  or      ebx, 80070000h
0x1800190d8  jmp     short loc_1800190DF
0x1800190da  mov     ebx, 1
0x1800190df  mov     eax, ebx
0x1800190e1  mov     rcx, [rbp+0B0h+var_10]
0x1800190e8  xor     rcx, rsp; StackCookie
0x1800190eb  call    __security_check_cookie
0x1800190f0  lea     r11, [rsp+1B0h+var_s0]
0x1800190f8  mov     rbx, [r11+18h]
0x1800190fc  mov     rdi, [r11+20h]
0x180019100  mov     rsp, r11
0x180019103  pop     rbp
0x180019104  retn
```
