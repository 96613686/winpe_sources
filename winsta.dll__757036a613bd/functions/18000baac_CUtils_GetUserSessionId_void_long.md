# CUtils::GetUserSessionId(void *,long *)

- ea: `0x18000baac`
- end: `0x18000bbd7`
- name: `?GetUserSessionId@CUtils@@SAJPEAXPEAJ@Z`
- size: `299`
- prototype: `__int64 __fastcall(void *, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180009da0`

## callees

- `0x180007890`
- `0x18000baac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bb4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bb6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bb4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bb6f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000bbc3`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000bbc3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000bbac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000bbac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bb14`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bb14`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000bafa`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000bafa`

## string_xrefs

- `0x18000bb66`: `OpenThreadToken failed: 0x%x in %s`
- `0x18000bb8c`: `GetTokenInformation failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CUtils::GetUserSessionId(HANDLE a1, int *a2)
{
  signed int v3; // ebx
  signed int LastError; // eax
  signed int v6; // eax
  HANDLE CurrentThread; // rax
  int TokenInformation; // [rsp+48h] [rbp+10h] BYREF
  DWORD ReturnLength; // [rsp+50h] [rbp+18h] BYREF
  HANDLE hObject; // [rsp+58h] [rbp+20h] BYREF

  hObject = 0;
  TokenInformation = 0;
  ReturnLength = 0;
  if ( !a2 )
  {
    _DbgPrintMessage(8, "Missing paramter %s in %s", "pSessionId", "CUtils::GetUserSessionId");
    v3 = -2147024809;
    goto LABEL_5;
  }
  v3 = 0;
  if ( !a1 )
  {
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 8u, 1, &hObject) )
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
      if ( v3 < 0 )
      {
        _DbgPrintMessage(8, "OpenThreadToken failed: 0x%x in %s", (unsigned int)v3, "CUtils::GetUserSessionId");
        goto LABEL_5;
      }
    }
    a1 = hObject;
  }
  if ( GetTokenInformation(a1, TokenSessionId, &TokenInformation, 4u, &ReturnLength) )
    goto LABEL_4;
  v6 = GetLastError();
  v3 = v6;
  if ( v6 > 0 )
    v3 = (unsigned __int16)v6 | 0x80070000;
  if ( v3 >= 0 )
LABEL_4:
    *a2 = TokenInformation;
  else
    _DbgPrintMessage(8, "GetTokenInformation failed: 0x%x in %s", (unsigned int)v3, "CUtils::GetUserSessionId");
LABEL_5:
  if ( hObject )
    CloseHandle(hObject);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000baac  mov     rax, rsp
0x18000baaf  mov     [rax+8], rbx
0x18000bab3  push    rsi
0x18000bab4  sub     rsp, 30h
0x18000bab8  mov     qword ptr [rax+20h], 0
0x18000bac0  mov     rsi, rdx
0x18000bac3  mov     dword ptr [rax+10h], 0
0x18000baca  mov     dword ptr [rax+18h], 0
0x18000bad1  test    rdx, rdx
0x18000bad4  jz      short loc_18000BB27
0x18000bad6  xor     ebx, ebx
0x18000bad8  test    rcx, rcx
0x18000badb  jz      loc_18000BBAC
0x18000bae1  mov     r9d, 4; TokenInformationLength
0x18000bae7  lea     rax, [rsp+38h+arg_10]
0x18000baec  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x18000baf1  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18000baf6  lea     edx, [r9+8]; TokenInformationClass
0x18000bafa  call    cs:__imp_GetTokenInformation
0x18000bb00  test    eax, eax
0x18000bb02  jz      short loc_18000BB6F
0x18000bb04  mov     ecx, [rsp+38h+TokenInformation]
0x18000bb08  mov     [rsi], ecx
0x18000bb0a  mov     rcx, [rsp+38h+hObject]; hObject
0x18000bb0f  test    rcx, rcx
0x18000bb12  jz      short loc_18000BB1A
0x18000bb14  call    cs:__imp_CloseHandle
0x18000bb1a  mov     eax, ebx
0x18000bb1c  mov     rbx, [rsp+38h+arg_0]
0x18000bb21  add     rsp, 30h
0x18000bb25  pop     rsi
0x18000bb26  retn
0x18000bb27  lea     r9, aCutilsGetusers_0; "CUtils::GetUserSessionId"
0x18000bb2e  mov     ecx, 8; int
0x18000bb33  lea     r8, aPsessionid; "pSessionId"
0x18000bb3a  lea     rdx, aMissingParamte; "Missing paramter %s in %s"
0x18000bb41  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000bb46  mov     ebx, 80070057h
0x18000bb4b  jmp     short loc_18000BB0A
0x18000bb4d  call    cs:__imp_GetLastError
0x18000bb53  mov     ebx, eax
0x18000bb55  test    eax, eax
0x18000bb57  jle     short loc_18000BB62
0x18000bb59  movzx   ebx, ax
0x18000bb5c  or      ebx, 80070000h
0x18000bb62  test    ebx, ebx
0x18000bb64  jns     short loc_18000BBCD
0x18000bb66  lea     rdx, aOpenthreadtoke_0; "OpenThreadToken failed: 0x%x in %s"
0x18000bb6d  jmp     short loc_18000BB93
0x18000bb6f  call    cs:__imp_GetLastError
0x18000bb75  mov     ebx, eax
0x18000bb77  test    eax, eax
0x18000bb79  jle     short loc_18000BB84
0x18000bb7b  movzx   ebx, ax
0x18000bb7e  or      ebx, 80070000h
0x18000bb84  test    ebx, ebx
0x18000bb86  jns     loc_18000BB04
0x18000bb8c  lea     rdx, aGettokeninform_2; "GetTokenInformation failed: 0x%x in %s"
0x18000bb93  mov     r8d, ebx
0x18000bb96  lea     r9, aCutilsGetusers_0; "CUtils::GetUserSessionId"
0x18000bb9d  mov     ecx, 8; int
0x18000bba2  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000bba7  jmp     loc_18000BB0A
0x18000bbac  call    cs:__imp_GetCurrentThread
0x18000bbb2  mov     edx, 8; DesiredAccess
0x18000bbb7  lea     r9, [rsp+38h+hObject]; TokenHandle
0x18000bbbc  mov     rcx, rax; ThreadHandle
0x18000bbbf  lea     r8d, [rdx-7]; OpenAsSelf
0x18000bbc3  call    cs:__imp_OpenThreadToken
0x18000bbc9  test    eax, eax
0x18000bbcb  jz      short loc_18000BB4D
0x18000bbcd  mov     rcx, [rsp+38h+hObject]
0x18000bbd2  jmp     loc_18000BAE1
```
