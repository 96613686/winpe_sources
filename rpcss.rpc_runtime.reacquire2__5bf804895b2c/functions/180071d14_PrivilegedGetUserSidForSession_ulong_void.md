# PrivilegedGetUserSidForSession(ulong,void * *)

- ea: `0x180071d14`
- end: `0x180071ede`
- name: `?PrivilegedGetUserSidForSession@@YAJKPEAPEAX@Z`
- size: `458`
- prototype: `__int64 __fastcall(unsigned int, void **)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180053644`
- `0x18006e990`

## callees

- `0x1800158f8`
- `0x180034260`
- `0x180071d14`
- `0x1800a7388`
- `0x180112d90`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071d76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071e21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071d76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071e21`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180071ebf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180071ebf`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180071d6a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180071e11`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180071d6a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180071e11`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180071e9d`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180071e9d`
- `KERNELBASE!LocalAlloc` at `0x180071dd7`
- `KERNELBASE!LocalAlloc` at `0x180071dd7`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180071e43`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180071e43`

## string_xrefs

- `0x180071e76`: `GetTokenInformation failed: %!WINERROR!`
- `0x180071e8c`: `onecore\com\combase\rpcss\olescm\security.cxx`
- `0x180071e80`: `PrivilegedGetUserSidForSession`

## pseudocode

```c
__int64 __fastcall PrivilegedGetUserSidForSession(unsigned int a1, PSID **a2)
{
  unsigned int UserTokenForSession; // ebx
  signed int LastError; // eax
  signed int v5; // r8d
  int v6; // r8d
  PSID *v7; // rdi
  signed int v8; // eax
  signed int v9; // esi
  DWORD LengthSid; // eax
  signed int v12; // [rsp+28h] [rbp-10h]
  DWORD TokenInformationLength; // [rsp+48h] [rbp+10h] BYREF
  HANDLE TokenHandle; // [rsp+50h] [rbp+18h] BYREF

  *a2 = 0;
  TokenHandle = 0;
  UserTokenForSession = GetUserTokenForSession(a1, &TokenHandle);
  if ( (UserTokenForSession & 0x80000000) == 0 )
  {
    TokenInformationLength = 0;
    GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength);
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError == 122 )
    {
      v7 = (PSID *)LocalAlloc(0, TokenInformationLength);
      if ( !v7 )
      {
        UserTokenForSession = -2147024882;
LABEL_22:
        CloseHandle(TokenHandle);
        return UserTokenForSession;
      }
      if ( GetTokenInformation(TokenHandle, TokenUser, v7, TokenInformationLength, &TokenInformationLength) )
      {
        LengthSid = GetLengthSid(*v7);
        memmove_0(v7, *v7, LengthSid);
        *a2 = v7;
        goto LABEL_22;
      }
      v8 = GetLastError();
      v9 = v8;
      if ( v8 > 0 )
        UserTokenForSession = (unsigned __int16)v8 | 0x80070000;
      else
        UserTokenForSession = v8;
      LocalFree(v7);
      if ( !dword_1801574B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled(0)) )
        goto LABEL_22;
      v12 = v9;
      v6 = 1355;
    }
    else
    {
      if ( LastError > 0 )
        UserTokenForSession = (unsigned __int16)LastError | 0x80070000;
      else
        UserTokenForSession = LastError;
      if ( !dword_1801574B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled(0)) )
        goto LABEL_22;
      v12 = v5;
      v6 = 1338;
    }
    ComTraceMessageT<int>(
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\security.cxx",
      (unsigned int)"PrivilegedGetUserSidForSession",
      v6,
      0,
      (__int64)L"GetTokenInformation failed: %!WINERROR!",
      v12);
    goto LABEL_22;
  }
  return UserTokenForSession;
}

```

## disassembly

```asm
0x180071d14  mov     rax, rsp
0x180071d17  mov     [rax+8], rbx
0x180071d1b  mov     [rax+20h], rsi
0x180071d1f  push    rdi
0x180071d20  sub     rsp, 30h
0x180071d24  mov     rsi, rdx
0x180071d27  mov     qword ptr [rdx], 0
0x180071d2e  lea     rdx, [rax+18h]; void **
0x180071d32  mov     qword ptr [rax+18h], 0
0x180071d3a  call    ?GetUserTokenForSession@@YAJKPEAPEAX@Z; GetUserTokenForSession(ulong,void * *)
0x180071d3f  mov     ebx, eax
0x180071d41  test    eax, eax
0x180071d43  js      loc_180071ECB
0x180071d49  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x180071d4e  lea     rax, [rsp+38h+TokenInformationLength]
0x180071d53  xor     r9d, r9d; TokenInformationLength
0x180071d56  mov     [rsp+38h+TokenInformationLength], 0
0x180071d5e  xor     r8d, r8d; TokenInformation
0x180071d61  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180071d66  lea     edx, [r9+1]; TokenInformationClass
0x180071d6a  call    cs:__imp_GetTokenInformation
0x180071d71  nop     dword ptr [rax+rax+00h]
0x180071d76  call    cs:__imp_GetLastError
0x180071d7d  nop     dword ptr [rax+rax+00h]
0x180071d82  mov     r8d, eax
0x180071d85  cmp     eax, 7Ah ; 'z'
0x180071d88  jz      short loc_180071DD1
0x180071d8a  test    eax, eax
0x180071d8c  jg      short loc_180071D92
0x180071d8e  mov     ebx, eax
0x180071d90  jmp     short loc_180071D9C
0x180071d92  movzx   ebx, r8w
0x180071d96  or      ebx, 80070000h
0x180071d9c  mov     eax, cs:dword_1801574B8
0x180071da2  test    eax, eax
0x180071da4  jnz     short loc_180071DC1
0x180071da6  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x180071dac  jz      loc_180071EBA
0x180071db2  xor     ecx, ecx
0x180071db4  call    IsWppLevelEnabled
0x180071db9  test    al, al
0x180071dbb  jz      loc_180071EBA
0x180071dc1  mov     [rsp+38h+var_10], r8d
0x180071dc6  mov     r8d, 53Ah
0x180071dcc  jmp     loc_180071E76
0x180071dd1  mov     edx, [rsp+38h+TokenInformationLength]; uBytes
0x180071dd5  xor     ecx, ecx; uFlags
0x180071dd7  call    cs:__imp_LocalAlloc
0x180071dde  nop     dword ptr [rax+rax+00h]
0x180071de3  mov     rdi, rax
0x180071de6  test    rax, rax
0x180071de9  jnz     short loc_180071DF5
0x180071deb  mov     ebx, 8007000Eh
0x180071df0  jmp     loc_180071EBA
0x180071df5  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x180071dfa  lea     rax, [rsp+38h+TokenInformationLength]
0x180071dff  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x180071e04  mov     r8, rdi; TokenInformation
0x180071e07  mov     edx, 1; TokenInformationClass
0x180071e0c  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180071e11  call    cs:__imp_GetTokenInformation
0x180071e18  nop     dword ptr [rax+rax+00h]
0x180071e1d  test    eax, eax
0x180071e1f  jnz     short loc_180071E9A
0x180071e21  call    cs:__imp_GetLastError
0x180071e28  nop     dword ptr [rax+rax+00h]
0x180071e2d  mov     esi, eax
0x180071e2f  test    eax, eax
0x180071e31  jg      short loc_180071E37
0x180071e33  mov     ebx, eax
0x180071e35  jmp     short loc_180071E40
0x180071e37  movzx   ebx, si
0x180071e3a  or      ebx, 80070000h
0x180071e40  mov     rcx, rdi; hMem
0x180071e43  call    cs:__imp_LocalFree
0x180071e4a  nop     dword ptr [rax+rax+00h]
0x180071e4f  mov     eax, cs:dword_1801574B8
0x180071e55  test    eax, eax
0x180071e57  jnz     short loc_180071E6C
0x180071e59  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x180071e5f  jz      short loc_180071EBA
0x180071e61  xor     ecx, ecx
0x180071e63  call    IsWppLevelEnabled
0x180071e68  test    al, al
0x180071e6a  jz      short loc_180071EBA
0x180071e6c  mov     [rsp+38h+var_10], esi
0x180071e70  mov     r8d, 54Bh
0x180071e76  lea     rax, aGettokeninform; "GetTokenInformation failed: %!WINERROR!"
0x180071e7d  xor     r9d, r9d
0x180071e80  lea     rdx, aPrivilegedgetu; "PrivilegedGetUserSidForSession"
0x180071e87  mov     [rsp+38h+ReturnLength], rax
0x180071e8c  lea     rcx, aOnecoreComComb_86; "onecore\\com\\combase\\rpcss\\olescm\\s"...
0x180071e93  call    ??$ComTraceMessageT@H@@YAXPEBD0HW4TraceLevel@@PEBGH@Z; ComTraceMessageT<int>(char const *,char const *,int,TraceLevel,ushort const *,int)
0x180071e98  jmp     short loc_180071EBA
0x180071e9a  mov     rcx, [rdi]; pSid
0x180071e9d  call    cs:__imp_GetLengthSid
0x180071ea4  nop     dword ptr [rax+rax+00h]
0x180071ea9  mov     rdx, [rdi]; Src
0x180071eac  mov     rcx, rdi; void *
0x180071eaf  mov     r8d, eax; Size
0x180071eb2  call    memmove_0
0x180071eb7  mov     [rsi], rdi
0x180071eba  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x180071ebf  call    cs:__imp_CloseHandle
0x180071ec6  nop     dword ptr [rax+rax+00h]
0x180071ecb  mov     rsi, [rsp+38h+arg_18]
0x180071ed0  mov     eax, ebx
0x180071ed2  mov     rbx, [rsp+38h+arg_0]
0x180071ed7  add     rsp, 30h
0x180071edb  pop     rdi
0x180071edc  retn
```
