# GetCurrentThreadTokenAndRevertToSelf

- ea: `0x18001b560`
- end: `0x18001b6f6`
- name: `GetCurrentThreadTokenAndRevertToSelf`
- size: `406`
- prototype: `void *()`
- caller_count: `4`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x18001b238`
- `0x18001b2ac`
- `0x18001b734`
- `0x18001bdac`

## callees

- `0x18000195c`
- `0x1800032dc`
- `0x18001b560`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b5c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b661`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b5c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b661`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b5ce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b5ce`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001b59b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001b59b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001b585`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001b585`
- `ADVAPI32!RevertToSelf` at `0x18001b5a9`
- `ADVAPI32!RevertToSelf` at `0x18001b5a9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void *GetCurrentThreadTokenAndRevertToSelf()
{
  HANDLE CurrentThread; // rax
  DWORD v2; // ebx
  DWORD LastError; // ebx
  void **pExceptionObject; // [rsp+20h] [rbp-40h] BYREF
  char v5; // [rsp+28h] [rbp-38h]
  const char *v6; // [rsp+30h] [rbp-30h]
  __int64 v7; // [rsp+38h] [rbp-28h]
  __int64 v8; // [rsp+40h] [rbp-20h]
  DWORD v9; // [rsp+48h] [rbp-18h]
  int v10; // [rsp+4Ch] [rbp-14h]
  int v11; // [rsp+50h] [rbp-10h]
  void *TokenHandle; // [rsp+70h] [rbp+10h] BYREF

  if ( !NtCurrentTeb()->IsImpersonating )
    return 0;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 4u, 1, &TokenHandle) )
  {
    LastError = GetLastError();
    if ( !LastError )
      LastError = 1287;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_3b54ed34bb4835de3895f7d36279b99a_Traceguids, LastError);
    }
    v5 = 0;
    v6 = "admin\\wmi\\events\\forwarding\\collector\\store\\credentialmanager.cpp";
    v7 = 0;
    pExceptionObject = &wmi::GenericException::`vftable';
    v8 = 0;
    v9 = LastError;
    v10 = -1;
    v11 = 34;
    throw (wmi::GenericException *)&pExceptionObject;
  }
  if ( !RevertToSelf() )
  {
    v2 = GetLastError();
    CloseHandle(TokenHandle);
    if ( !v2 )
      v2 = 1287;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_3b54ed34bb4835de3895f7d36279b99a_Traceguids, v2);
    }
    v5 = 0;
    v6 = "admin\\wmi\\events\\forwarding\\collector\\store\\credentialmanager.cpp";
    v7 = 0;
    pExceptionObject = &wmi::GenericException::`vftable';
    v8 = 0;
    v9 = v2;
    v10 = -1;
    v11 = 45;
    throw (wmi::GenericException *)&pExceptionObject;
  }
  return TokenHandle;
}

```

## disassembly

```asm
0x18001b560  mov     [rsp-8+arg_8], rbx
0x18001b565  push    rbp
0x18001b566  mov     rbp, rsp
0x18001b569  sub     rsp, 60h
0x18001b56d  mov     eax, gs:179Ch
0x18001b575  test    eax, eax
0x18001b577  jnz     short loc_18001B57D
0x18001b579  xor     eax, eax
0x18001b57b  jmp     short loc_18001B5B7
0x18001b57d  mov     [rbp+TokenHandle], 0
0x18001b585  call    cs:__imp_GetCurrentThread
0x18001b58b  mov     edx, 4; DesiredAccess
0x18001b590  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18001b594  mov     rcx, rax; ThreadHandle
0x18001b597  lea     r8d, [rdx-3]; OpenAsSelf
0x18001b59b  call    cs:__imp_OpenThreadToken
0x18001b5a1  test    eax, eax
0x18001b5a3  jz      loc_18001B661
0x18001b5a9  call    cs:__imp_RevertToSelf
0x18001b5af  test    eax, eax
0x18001b5b1  jz      short loc_18001B5C2
0x18001b5b3  mov     rax, [rbp+TokenHandle]
0x18001b5b7  mov     rbx, [rsp+60h+arg_8]
0x18001b5bc  add     rsp, 60h
0x18001b5c0  pop     rbp
0x18001b5c1  retn
0x18001b5c2  call    cs:__imp_GetLastError
0x18001b5c8  mov     rcx, [rbp+TokenHandle]; hObject
0x18001b5cc  mov     ebx, eax
0x18001b5ce  call    cs:__imp_CloseHandle
0x18001b5d4  test    ebx, ebx
0x18001b5d6  mov     eax, 507h
0x18001b5db  cmovz   ebx, eax
0x18001b5de  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b5e5  lea     rax, WPP_GLOBAL_Control
0x18001b5ec  cmp     rcx, rax
0x18001b5ef  jz      short loc_18001B615
0x18001b5f1  test    byte ptr [rcx+1Ch], 40h
0x18001b5f5  jz      short loc_18001B615
0x18001b5f7  cmp     byte ptr [rcx+19h], 2
0x18001b5fb  jb      short loc_18001B615
0x18001b5fd  mov     rcx, [rcx+10h]
0x18001b601  lea     r8, WPP_3b54ed34bb4835de3895f7d36279b99a_Traceguids
0x18001b608  mov     edx, 0Bh
0x18001b60d  mov     r9d, ebx
0x18001b610  call    WPP_SF_D
0x18001b615  lea     rax, aAdminWmiEvents_9; "admin\\wmi\\events\\forwarding\\collect"...
0x18001b61c  mov     [rbp+var_38], 0
0x18001b620  mov     [rbp+var_30], rax
0x18001b624  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18001b62b  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18001b632  mov     [rbp+var_28], 0
0x18001b63a  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001b63e  mov     [rbp+pExceptionObject], rax
0x18001b642  mov     [rbp+var_20], 0
0x18001b64a  mov     [rbp+var_18], ebx
0x18001b64d  mov     [rbp+var_14], 0FFFFFFFFh
0x18001b654  mov     [rbp+var_10], 2Dh ; '-'
0x18001b65b  call    _CxxThrowException_0
0x18001b661  call    cs:__imp_GetLastError
0x18001b667  mov     ebx, eax
0x18001b669  mov     eax, 507h
0x18001b66e  test    ebx, ebx
0x18001b670  cmovz   ebx, eax
0x18001b673  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b67a  lea     rax, WPP_GLOBAL_Control
0x18001b681  cmp     rcx, rax
0x18001b684  jz      short loc_18001B6AA
0x18001b686  test    byte ptr [rcx+1Ch], 40h
0x18001b68a  jz      short loc_18001B6AA
0x18001b68c  cmp     byte ptr [rcx+19h], 2
0x18001b690  jb      short loc_18001B6AA
0x18001b692  mov     rcx, [rcx+10h]
0x18001b696  lea     r8, WPP_3b54ed34bb4835de3895f7d36279b99a_Traceguids
0x18001b69d  mov     edx, 0Ah
0x18001b6a2  mov     r9d, ebx
0x18001b6a5  call    WPP_SF_D
0x18001b6aa  lea     rax, aAdminWmiEvents_9; "admin\\wmi\\events\\forwarding\\collect"...
0x18001b6b1  mov     [rbp+var_38], 0
0x18001b6b5  mov     [rbp+var_30], rax
0x18001b6b9  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18001b6c0  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18001b6c7  mov     [rbp+var_28], 0
0x18001b6cf  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001b6d3  mov     [rbp+pExceptionObject], rax
0x18001b6d7  mov     [rbp+var_20], 0
0x18001b6df  mov     [rbp+var_18], ebx
0x18001b6e2  mov     [rbp+var_14], 0FFFFFFFFh
0x18001b6e9  mov     [rbp+var_10], 22h ; '"'
0x18001b6f0  call    _CxxThrowException_0
```
