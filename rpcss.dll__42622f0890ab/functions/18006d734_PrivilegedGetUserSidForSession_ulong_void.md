# PrivilegedGetUserSidForSession(ulong,void * *)

- ea: `0x18006d734`
- end: `0x18006d8cd`
- name: `?PrivilegedGetUserSidForSession@@YAJKPEAPEAX@Z`
- size: `409`
- prototype: `__int64 __fastcall(unsigned int, void **)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800665e4`
- `0x1800699a0`

## callees

- `0x180011954`
- `0x180034540`
- `0x18006d734`
- `0x1800a1e98`
- `0x18010a090`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d790`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d829`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d790`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d829`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006d8b5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006d8b5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18006d78a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18006d81f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18006d78a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18006d81f`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18006d899`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18006d899`
- `KERNELBASE!LocalAlloc` at `0x18006d7eb`
- `KERNELBASE!LocalAlloc` at `0x18006d7eb`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18006d845`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18006d845`

## string_xrefs

- `0x18006d872`: `GetTokenInformation failed: %!WINERROR!`
- `0x18006d888`: `onecore\com\combase\rpcss\olescm\security.cxx`
- `0x18006d87c`: `PrivilegedGetUserSidForSession`

## pseudocode

```c
__int64 __fastcall PrivilegedGetUserSidForSession(unsigned int a1, PSID **a2)
{
  unsigned int UserTokenForSession; // ebx
  signed int LastError; // eax
  signed int v5; // r8d
  unsigned int v6; // r8d
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
      if ( !dword_18014E4B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled(0)) )
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
      if ( !dword_18014E4B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled(0)) )
        goto LABEL_22;
      v12 = v5;
      v6 = 1338;
    }
    ComTraceMessageT<int>(
      (__int64)"onecore\\com\\combase\\rpcss\\olescm\\security.cxx",
      (__int64)"PrivilegedGetUserSidForSession",
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
0x18006d734  mov     rax, rsp
0x18006d737  mov     [rax+8], rbx
0x18006d73b  mov     [rax+20h], rsi
0x18006d73f  push    rdi
0x18006d740  sub     rsp, 30h
0x18006d744  mov     rsi, rdx
0x18006d747  mov     qword ptr [rdx], 0
0x18006d74e  lea     rdx, [rax+18h]; void **
0x18006d752  mov     qword ptr [rax+18h], 0
0x18006d75a  call    ?GetUserTokenForSession@@YAJKPEAPEAX@Z; GetUserTokenForSession(ulong,void * *)
0x18006d75f  mov     ebx, eax
0x18006d761  test    eax, eax
0x18006d763  js      loc_18006D8BB
0x18006d769  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x18006d76e  lea     rax, [rsp+38h+TokenInformationLength]
0x18006d773  xor     r9d, r9d; TokenInformationLength
0x18006d776  mov     [rsp+38h+TokenInformationLength], 0
0x18006d77e  xor     r8d, r8d; TokenInformation
0x18006d781  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18006d786  lea     edx, [r9+1]; TokenInformationClass
0x18006d78a  call    cs:__imp_GetTokenInformation
0x18006d790  call    cs:__imp_GetLastError
0x18006d796  mov     r8d, eax
0x18006d799  cmp     eax, 7Ah ; 'z'
0x18006d79c  jz      short loc_18006D7E5
0x18006d79e  test    eax, eax
0x18006d7a0  jg      short loc_18006D7A6
0x18006d7a2  mov     ebx, eax
0x18006d7a4  jmp     short loc_18006D7B0
0x18006d7a6  movzx   ebx, r8w
0x18006d7aa  or      ebx, 80070000h
0x18006d7b0  mov     eax, cs:dword_18014E4B8
0x18006d7b6  test    eax, eax
0x18006d7b8  jnz     short loc_18006D7D5
0x18006d7ba  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x18006d7c0  jz      loc_18006D8B0
0x18006d7c6  xor     ecx, ecx
0x18006d7c8  call    IsWppLevelEnabled
0x18006d7cd  test    al, al
0x18006d7cf  jz      loc_18006D8B0
0x18006d7d5  mov     [rsp+38h+var_10], r8d
0x18006d7da  mov     r8d, 53Ah
0x18006d7e0  jmp     loc_18006D872
0x18006d7e5  mov     edx, [rsp+38h+TokenInformationLength]; uBytes
0x18006d7e9  xor     ecx, ecx; uFlags
0x18006d7eb  call    cs:__imp_LocalAlloc
0x18006d7f1  mov     rdi, rax
0x18006d7f4  test    rax, rax
0x18006d7f7  jnz     short loc_18006D803
0x18006d7f9  mov     ebx, 8007000Eh
0x18006d7fe  jmp     loc_18006D8B0
0x18006d803  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x18006d808  lea     rax, [rsp+38h+TokenInformationLength]
0x18006d80d  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x18006d812  mov     r8, rdi; TokenInformation
0x18006d815  mov     edx, 1; TokenInformationClass
0x18006d81a  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18006d81f  call    cs:__imp_GetTokenInformation
0x18006d825  test    eax, eax
0x18006d827  jnz     short loc_18006D896
0x18006d829  call    cs:__imp_GetLastError
0x18006d82f  mov     esi, eax
0x18006d831  test    eax, eax
0x18006d833  jg      short loc_18006D839
0x18006d835  mov     ebx, eax
0x18006d837  jmp     short loc_18006D842
0x18006d839  movzx   ebx, si
0x18006d83c  or      ebx, 80070000h
0x18006d842  mov     rcx, rdi; hMem
0x18006d845  call    cs:__imp_LocalFree
0x18006d84b  mov     eax, cs:dword_18014E4B8
0x18006d851  test    eax, eax
0x18006d853  jnz     short loc_18006D868
0x18006d855  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x18006d85b  jz      short loc_18006D8B0
0x18006d85d  xor     ecx, ecx
0x18006d85f  call    IsWppLevelEnabled
0x18006d864  test    al, al
0x18006d866  jz      short loc_18006D8B0
0x18006d868  mov     [rsp+38h+var_10], esi
0x18006d86c  mov     r8d, 54Bh
0x18006d872  lea     rax, aGettokeninform; "GetTokenInformation failed: %!WINERROR!"
0x18006d879  xor     r9d, r9d
0x18006d87c  lea     rdx, aPrivilegedgetu; "PrivilegedGetUserSidForSession"
0x18006d883  mov     [rsp+38h+ReturnLength], rax
0x18006d888  lea     rcx, aOnecoreComComb_86; "onecore\\com\\combase\\rpcss\\olescm\\s"...
0x18006d88f  call    ??$ComTraceMessageT@H@@YAXPEBD0HW4TraceLevel@@PEBGH@Z; ComTraceMessageT<int>(char const *,char const *,int,TraceLevel,ushort const *,int)
0x18006d894  jmp     short loc_18006D8B0
0x18006d896  mov     rcx, [rdi]; pSid
0x18006d899  call    cs:__imp_GetLengthSid
0x18006d89f  mov     rdx, [rdi]; Src
0x18006d8a2  mov     rcx, rdi; void *
0x18006d8a5  mov     r8d, eax; Size
0x18006d8a8  call    memmove_0
0x18006d8ad  mov     [rsi], rdi
0x18006d8b0  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x18006d8b5  call    cs:__imp_CloseHandle
0x18006d8bb  mov     rsi, [rsp+38h+arg_18]
0x18006d8c0  mov     eax, ebx
0x18006d8c2  mov     rbx, [rsp+38h+arg_0]
0x18006d8c7  add     rsp, 30h
0x18006d8cb  pop     rdi
0x18006d8cc  retn
```
