# CUtils::GetUserSessionId(void *,long *)

- ea: `0x18000a28c`
- end: `0x18000a3e0`
- name: `?GetUserSessionId@CUtils@@SAJPEAXPEAJ@Z`
- size: `340`
- prototype: `__int64 __fastcall(void *, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180008640`

## callees

- `0x180005b40`
- `0x18000a28c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a33a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a362`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a33a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a362`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000a3c2`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000a3c2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000a3a5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000a3a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a2fa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a2fa`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000a2da`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000a2da`

## string_xrefs

- `0x18000a359`: `OpenThreadToken failed: 0x%x in %s`
- `0x18000a385`: `GetTokenInformation failed: 0x%x in %s`

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
0x18000a28c  mov     rax, rsp
0x18000a28f  mov     [rax+8], rbx
0x18000a293  push    rsi
0x18000a294  sub     rsp, 30h
0x18000a298  mov     qword ptr [rax+20h], 0
0x18000a2a0  mov     rsi, rdx
0x18000a2a3  mov     dword ptr [rax+10h], 0
0x18000a2aa  mov     dword ptr [rax+18h], 0
0x18000a2b1  test    rdx, rdx
0x18000a2b4  jz      short loc_18000A314
0x18000a2b6  xor     ebx, ebx
0x18000a2b8  test    rcx, rcx
0x18000a2bb  jz      loc_18000A3A5
0x18000a2c1  mov     r9d, 4; TokenInformationLength
0x18000a2c7  lea     rax, [rsp+38h+arg_10]
0x18000a2cc  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x18000a2d1  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18000a2d6  lea     edx, [r9+8]; TokenInformationClass
0x18000a2da  call    cs:__imp_GetTokenInformation
0x18000a2e1  nop     dword ptr [rax+rax+00h]
0x18000a2e6  test    eax, eax
0x18000a2e8  jz      short loc_18000A362
0x18000a2ea  mov     ecx, [rsp+38h+TokenInformation]
0x18000a2ee  mov     [rsi], ecx
0x18000a2f0  mov     rcx, [rsp+38h+hObject]; hObject
0x18000a2f5  test    rcx, rcx
0x18000a2f8  jz      short loc_18000A306
0x18000a2fa  call    cs:__imp_CloseHandle
0x18000a301  nop     dword ptr [rax+rax+00h]
0x18000a306  mov     eax, ebx
0x18000a308  mov     rbx, [rsp+38h+arg_0]
0x18000a30d  add     rsp, 30h
0x18000a311  pop     rsi
0x18000a312  retn
0x18000a314  lea     r9, aCutilsGetusers_0; "CUtils::GetUserSessionId"
0x18000a31b  mov     ecx, 8; int
0x18000a320  lea     r8, aPsessionid; "pSessionId"
0x18000a327  lea     rdx, aMissingParamte; "Missing paramter %s in %s"
0x18000a32e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000a333  mov     ebx, 80070057h
0x18000a338  jmp     short loc_18000A2F0
0x18000a33a  call    cs:__imp_GetLastError
0x18000a341  nop     dword ptr [rax+rax+00h]
0x18000a346  mov     ebx, eax
0x18000a348  test    eax, eax
0x18000a34a  jle     short loc_18000A355
0x18000a34c  movzx   ebx, ax
0x18000a34f  or      ebx, 80070000h
0x18000a355  test    ebx, ebx
0x18000a357  jns     short loc_18000A3D6
0x18000a359  lea     rdx, aOpenthreadtoke_0; "OpenThreadToken failed: 0x%x in %s"
0x18000a360  jmp     short loc_18000A38C
0x18000a362  call    cs:__imp_GetLastError
0x18000a369  nop     dword ptr [rax+rax+00h]
0x18000a36e  mov     ebx, eax
0x18000a370  test    eax, eax
0x18000a372  jle     short loc_18000A37D
0x18000a374  movzx   ebx, ax
0x18000a377  or      ebx, 80070000h
0x18000a37d  test    ebx, ebx
0x18000a37f  jns     loc_18000A2EA
0x18000a385  lea     rdx, aGettokeninform_2; "GetTokenInformation failed: 0x%x in %s"
0x18000a38c  mov     r8d, ebx
0x18000a38f  lea     r9, aCutilsGetusers_0; "CUtils::GetUserSessionId"
0x18000a396  mov     ecx, 8; int
0x18000a39b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000a3a0  jmp     loc_18000A2F0
0x18000a3a5  call    cs:__imp_GetCurrentThread
0x18000a3ac  nop     dword ptr [rax+rax+00h]
0x18000a3b1  mov     edx, 8; DesiredAccess
0x18000a3b6  lea     r9, [rsp+38h+hObject]; TokenHandle
0x18000a3bb  mov     rcx, rax; ThreadHandle
0x18000a3be  lea     r8d, [rdx-7]; OpenAsSelf
0x18000a3c2  call    cs:__imp_OpenThreadToken
0x18000a3c9  nop     dword ptr [rax+rax+00h]
0x18000a3ce  test    eax, eax
0x18000a3d0  jz      loc_18000A33A
0x18000a3d6  mov     rcx, [rsp+38h+hObject]
0x18000a3db  jmp     loc_18000A2C1
```
