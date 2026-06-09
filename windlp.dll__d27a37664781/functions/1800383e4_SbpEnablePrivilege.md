# SbpEnablePrivilege

- ea: `0x1800383e4`
- end: `0x18003859a`
- name: `SbpEnablePrivilege`
- size: `438`
- prototype: `__int64 __fastcall(LPCWSTR lpName)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800385a0`

## callees

- `0x1800383e4`
- `0x18007ed40`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18003850f`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18003853a`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18003850f`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18003853a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003848b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003848b`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003849d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003849d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180038460`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180038460`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180038474`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180038474`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003843b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003847e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003843b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003847e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180038552`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003856c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003857b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180038552`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003856c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003857b`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800384d6`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800384d6`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1800384fb`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1800384fb`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x180038431`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x180038431`

## pseudocode

```c
__int64 __fastcall SbpEnablePrivilege(LPCWSTR lpName)
{
  unsigned int v1; // ebx
  signed int LastError; // eax
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  void *v5; // rcx
  void *TokenHandle; // [rsp+30h] [rbp-30h] BYREF
  HANDLE Token; // [rsp+38h] [rbp-28h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+40h] [rbp-20h] BYREF

  v1 = 0;
  TokenHandle = 0;
  Token = 0;
  if ( lpName )
  {
    NewState = 0;
    NewState.PrivilegeCount = 1;
    if ( !LookupPrivilegeValueW(0, lpName, &NewState.Privileges[0].Luid) )
      goto LABEL_3;
    NewState.Privileges[0].Attributes = 2;
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 6u, 0, &TokenHandle) )
    {
      v5 = TokenHandle;
      hObject = TokenHandle;
    }
    else
    {
      if ( GetLastError() != 1008
        || (CurrentProcess = GetCurrentProcess(), !OpenProcessToken(CurrentProcess, 2u, &TokenHandle)) )
      {
LABEL_3:
        LastError = GetLastError();
        v1 = LastError;
        if ( LastError > 0 )
          v1 = (unsigned __int16)LastError | 0x80070000;
        goto LABEL_18;
      }
      v5 = TokenHandle;
    }
    if ( DuplicateTokenEx(v5, 0x2Cu, 0, SecurityImpersonation, TokenImpersonation, &Token)
      && AdjustTokenPrivileges(Token, 0, &NewState, 0, 0, 0)
      && SetThreadToken(0, Token) )
    {
      dword_1800AE780 = 1;
      goto LABEL_18;
    }
    goto LABEL_3;
  }
  if ( dword_1800AE780 )
  {
    SetThreadToken(0, hObject);
    dword_1800AE780 = 0;
  }
  if ( hObject )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
LABEL_18:
  if ( TokenHandle != hObject )
    CloseHandle(TokenHandle);
  if ( Token )
    CloseHandle(Token);
  return v1;
}

```

## disassembly

```asm
0x1800383e4  mov     [rsp-8+arg_8], rbx
0x1800383e9  push    rbp
0x1800383ea  mov     rbp, rsp
0x1800383ed  sub     rsp, 60h
0x1800383f1  mov     rax, cs:__security_cookie
0x1800383f8  xor     rax, rsp
0x1800383fb  mov     [rbp+var_10], rax
0x1800383ff  xor     ebx, ebx
0x180038401  mov     [rbp+TokenHandle], 0
0x180038409  mov     [rbp+Token], 0
0x180038411  test    rcx, rcx
0x180038414  jz      loc_180038529
0x18003841a  xorps   xmm0, xmm0
0x18003841d  lea     r8, [rbp+NewState.Privileges]; lpLuid
0x180038421  mov     rdx, rcx; lpName
0x180038424  xor     ecx, ecx; lpSystemName
0x180038426  movups  xmmword ptr [rbp-20h], xmm0
0x18003842a  mov     [rbp+NewState.PrivilegeCount], 1
0x180038431  call    cs:__imp_LookupPrivilegeValueW
0x180038437  test    eax, eax
0x180038439  jnz     short loc_180038459
0x18003843b  call    cs:__imp_GetLastError
0x180038441  mov     ebx, eax
0x180038443  test    eax, eax
0x180038445  jle     loc_18003855F
0x18003844b  movzx   ebx, ax
0x18003844e  or      ebx, 80070000h
0x180038454  jmp     loc_18003855F
0x180038459  mov     [rbp+NewState.Privileges.Attributes], 2
0x180038460  call    cs:__imp_GetCurrentThread
0x180038466  xor     r8d, r8d; OpenAsSelf
0x180038469  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18003846d  mov     rcx, rax; ThreadHandle
0x180038470  lea     edx, [r8+6]; DesiredAccess
0x180038474  call    cs:__imp_OpenThreadToken
0x18003847a  test    eax, eax
0x18003847c  jnz     short loc_1800384AD
0x18003847e  call    cs:__imp_GetLastError
0x180038484  cmp     eax, 3F0h
0x180038489  jnz     short loc_18003843B
0x18003848b  call    cs:__imp_GetCurrentProcess
0x180038491  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180038495  mov     edx, 2; DesiredAccess
0x18003849a  mov     rcx, rax; ProcessHandle
0x18003849d  call    cs:__imp_OpenProcessToken
0x1800384a3  test    eax, eax
0x1800384a5  jz      short loc_18003843B
0x1800384a7  mov     rcx, [rbp+TokenHandle]
0x1800384ab  jmp     short loc_1800384B8
0x1800384ad  mov     rcx, [rbp+TokenHandle]; hExistingToken
0x1800384b1  mov     cs:hObject, rcx
0x1800384b8  mov     r9d, 2; ImpersonationLevel
0x1800384be  lea     rax, [rbp+Token]
0x1800384c2  mov     [rsp+60h+phNewToken], rax; phNewToken
0x1800384c7  xor     r8d, r8d; lpTokenAttributes
0x1800384ca  mov     [rsp+60h+TokenType], 2; TokenType
0x1800384d2  lea     edx, [r9+2Ah]; dwDesiredAccess
0x1800384d6  call    cs:__imp_DuplicateTokenEx
0x1800384dc  test    eax, eax
0x1800384de  jz      loc_18003843B
0x1800384e4  mov     rcx, [rbp+Token]; TokenHandle
0x1800384e8  lea     r8, [rbp+NewState]; NewState
0x1800384ec  mov     [rsp+60h+phNewToken], rbx; ReturnLength
0x1800384f1  xor     r9d, r9d; BufferLength
0x1800384f4  xor     edx, edx; DisableAllPrivileges
0x1800384f6  mov     qword ptr [rsp+60h+TokenType], rbx; PreviousState
0x1800384fb  call    cs:__imp_AdjustTokenPrivileges
0x180038501  test    eax, eax
0x180038503  jz      loc_18003843B
0x180038509  mov     rdx, [rbp+Token]; Token
0x18003850d  xor     ecx, ecx; Thread
0x18003850f  call    cs:__imp_SetThreadToken
0x180038515  test    eax, eax
0x180038517  jz      loc_18003843B
0x18003851d  mov     cs:dword_1800AE780, 1
0x180038527  jmp     short loc_18003855F
0x180038529  cmp     cs:dword_1800AE780, ebx
0x18003852f  jz      short loc_180038546
0x180038531  mov     rdx, cs:hObject; Token
0x180038538  xor     ecx, ecx; Thread
0x18003853a  call    cs:__imp_SetThreadToken
0x180038540  mov     cs:dword_1800AE780, ebx
0x180038546  mov     rcx, cs:hObject; hObject
0x18003854d  test    rcx, rcx
0x180038550  jz      short loc_18003855F
0x180038552  call    cs:__imp_CloseHandle
0x180038558  mov     cs:hObject, rbx
0x18003855f  mov     rcx, [rbp+TokenHandle]; hObject
0x180038563  cmp     rcx, cs:hObject
0x18003856a  jz      short loc_180038572
0x18003856c  call    cs:__imp_CloseHandle
0x180038572  mov     rcx, [rbp+Token]; hObject
0x180038576  test    rcx, rcx
0x180038579  jz      short loc_180038581
0x18003857b  call    cs:__imp_CloseHandle
0x180038581  mov     eax, ebx
0x180038583  mov     rcx, [rbp+var_10]
0x180038587  xor     rcx, rsp; StackCookie
0x18003858a  call    __security_check_cookie
0x18003858f  mov     rbx, [rsp+60h+arg_8]
0x180038594  add     rsp, 60h
0x180038598  pop     rbp
0x180038599  retn
```
