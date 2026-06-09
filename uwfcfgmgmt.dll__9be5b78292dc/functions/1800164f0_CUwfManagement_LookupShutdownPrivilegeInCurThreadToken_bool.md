# CUwfManagement::LookupShutdownPrivilegeInCurThreadToken(bool &)

- ea: `0x1800164f0`
- end: `0x18001665b`
- name: `?LookupShutdownPrivilegeInCurThreadToken@CUwfManagement@@QEAAJAEA_N@Z`
- size: `363`
- prototype: `__int64 __fastcall(CUwfManagement *__hidden this, bool *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x180001384`
- `0x1800164f0`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180016636`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180016636`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016534`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016591`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800165ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016534`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016591`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800165ec`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180016566`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180016566`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180016552`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180016552`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016645`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016645`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180016587`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800165e2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180016587`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800165e2`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x18001652a`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x18001652a`

## string_xrefs

- `0x180016506`: `SeShutdownPrivilege`

## pseudocode

```c
__int64 __fastcall CUwfManagement::LookupShutdownPrivilegeInCurThreadToken(CUwfManagement *this, bool *a2)
{
  signed int v3; // eax
  unsigned int v4; // ebx
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  _DWORD *v7; // rsi
  signed int v8; // eax
  unsigned int v9; // edx
  __int64 v10; // r8
  DWORD TokenInformationLength; // [rsp+58h] [rbp+28h] BYREF
  void *TokenHandle; // [rsp+60h] [rbp+30h] BYREF
  _LUID Luid; // [rsp+68h] [rbp+38h] BYREF

  *a2 = 0;
  TokenHandle = 0;
  TokenInformationLength = 0;
  Luid = 0;
  if ( LookupPrivilegeValueW(0, L"SeShutdownPrivilege", &Luid)
    && (CurrentThread = GetCurrentThread(), OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle)) )
  {
    if ( GetTokenInformation(TokenHandle, TokenPrivileges, 0, 0, &TokenInformationLength) )
      goto LABEL_9;
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( v4 == -2147024774 )
    {
LABEL_9:
      v7 = operator new[](TokenInformationLength);
      if ( v7 )
      {
        if ( GetTokenInformation(TokenHandle, TokenPrivileges, v7, TokenInformationLength, &TokenInformationLength) )
        {
          v9 = 0;
          v4 = 0;
          if ( *v7 )
          {
            while ( 1 )
            {
              v10 = 7LL * v9;
              if ( v7[v10 + 1] == Luid.LowPart && v7[v10 + 2] == Luid.HighPart )
                break;
              if ( ++v9 >= *v7 )
                goto LABEL_20;
            }
            *a2 = 1;
          }
        }
        else
        {
          v8 = GetLastError();
          v4 = v8;
          if ( v8 > 0 )
            v4 = (unsigned __int16)v8 | 0x80070000;
        }
LABEL_20:
        operator delete[](v7);
      }
      else
      {
        v4 = -2147024882;
      }
    }
  }
  else
  {
    v3 = GetLastError();
    v4 = v3;
    if ( v3 > 0 )
      v4 = (unsigned __int16)v3 | 0x80070000;
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return v4;
}

```

## disassembly

```asm
0x1800164f0  mov     [rsp-18h+arg_0], rbx
0x1800164f5  push    rbp
0x1800164f6  push    rsi
0x1800164f7  push    r14
0x1800164f9  mov     rbp, rsp
0x1800164fc  sub     rsp, 30h
0x180016500  mov     r14, rdx
0x180016503  mov     byte ptr [rdx], 0
0x180016506  lea     rdx, aSeshutdownpriv; "SeShutdownPrivilege"
0x18001650d  mov     [rbp+TokenHandle], 0
0x180016515  lea     r8, [rbp+Luid]; lpLuid
0x180016519  mov     [rbp+TokenInformationLength], 0
0x180016520  xor     ecx, ecx; lpSystemName
0x180016522  mov     qword ptr [rbp+Luid.LowPart], 0
0x18001652a  call    cs:__imp_LookupPrivilegeValueW
0x180016530  test    eax, eax
0x180016532  jnz     short loc_180016552
0x180016534  call    cs:__imp_GetLastError
0x18001653a  mov     ebx, eax
0x18001653c  test    eax, eax
0x18001653e  jle     loc_18001663C
0x180016544  movzx   ebx, ax
0x180016547  or      ebx, 80070000h
0x18001654d  jmp     loc_18001663C
0x180016552  call    cs:__imp_GetCurrentThread
0x180016558  xor     r8d, r8d; OpenAsSelf
0x18001655b  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18001655f  mov     rcx, rax; ThreadHandle
0x180016562  lea     edx, [r8+8]; DesiredAccess
0x180016566  call    cs:__imp_OpenThreadToken
0x18001656c  test    eax, eax
0x18001656e  jz      short loc_180016534
0x180016570  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180016574  lea     rax, [rbp+TokenInformationLength]
0x180016578  xor     r9d, r9d; TokenInformationLength
0x18001657b  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x180016580  xor     r8d, r8d; TokenInformation
0x180016583  lea     edx, [r9+3]; TokenInformationClass
0x180016587  call    cs:__imp_GetTokenInformation
0x18001658d  test    eax, eax
0x18001658f  jnz     short loc_1800165B2
0x180016591  call    cs:__imp_GetLastError
0x180016597  mov     ebx, eax
0x180016599  test    eax, eax
0x18001659b  jle     short loc_1800165A6
0x18001659d  movzx   ebx, ax
0x1800165a0  or      ebx, 80070000h
0x1800165a6  cmp     ebx, 8007007Ah
0x1800165ac  jnz     loc_18001663C
0x1800165b2  mov     ecx, [rbp+TokenInformationLength]; unsigned __int64
0x1800165b5  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800165ba  mov     rsi, rax
0x1800165bd  test    rax, rax
0x1800165c0  jnz     short loc_1800165C9
0x1800165c2  mov     ebx, 8007000Eh
0x1800165c7  jmp     short loc_18001663C
0x1800165c9  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x1800165cd  lea     rax, [rbp+TokenInformationLength]
0x1800165d1  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800165d5  mov     r8, rsi; TokenInformation
0x1800165d8  mov     edx, 3; TokenInformationClass
0x1800165dd  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x1800165e2  call    cs:__imp_GetTokenInformation
0x1800165e8  test    eax, eax
0x1800165ea  jnz     short loc_180016603
0x1800165ec  call    cs:__imp_GetLastError
0x1800165f2  mov     ebx, eax
0x1800165f4  test    eax, eax
0x1800165f6  jle     short loc_180016633
0x1800165f8  movzx   ebx, ax
0x1800165fb  or      ebx, 80070000h
0x180016601  jmp     short loc_180016633
0x180016603  xor     edx, edx
0x180016605  xor     ebx, ebx
0x180016607  cmp     [rsi], edx
0x180016609  jbe     short loc_180016633
0x18001660b  mov     rax, qword ptr [rbp+Luid.LowPart]
0x18001660f  mov     r9d, [rbp+Luid.HighPart]
0x180016613  mov     ecx, edx
0x180016615  imul    r8, rcx, 1Ch
0x180016619  cmp     [r8+rsi+4], eax
0x18001661e  jnz     short loc_180016627
0x180016620  cmp     [r8+rsi+8], r9d
0x180016625  jz      short loc_18001662F
0x180016627  inc     edx
0x180016629  cmp     edx, [rsi]
0x18001662b  jb      short loc_180016613
0x18001662d  jmp     short loc_180016633
0x18001662f  mov     byte ptr [r14], 1
0x180016633  mov     rcx, rsi
0x180016636  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18001663c  mov     rcx, [rbp+TokenHandle]; hObject
0x180016640  test    rcx, rcx
0x180016643  jz      short loc_18001664B
0x180016645  call    cs:__imp_CloseHandle
0x18001664b  mov     eax, ebx
0x18001664d  mov     rbx, [rsp+30h+arg_0]
0x180016652  add     rsp, 30h
0x180016656  pop     r14
0x180016658  pop     rsi
0x180016659  pop     rbp
0x18001665a  retn
```
