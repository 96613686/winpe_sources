# GetCurrentUserSID

- ea: `0x18007e938`
- end: `0x18007eb09`
- name: `GetCurrentUserSID`
- size: `465`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004cd4c`

## callees

- `0x18007e938`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18007e983`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18007e983`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18007e993`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18007e993`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18007e954`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18007e954`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18007e96c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18007e96c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007e9ee`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007ea41`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007ea7b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007eaaf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007e9ee`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007ea41`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007ea7b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007eaaf`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007e9fd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007ea50`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007e9fd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007ea50`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007ea89`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007eabd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007ea89`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007eabd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007ea9e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007eaeb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007ea9e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007eaeb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e976`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e99d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e9db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ea73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007eaa7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007eacc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e976`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e99d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e9db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ea73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007eaa7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007eacc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007eae3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007eae3`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18007ea38`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18007ea38`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18007e9cd`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18007ea28`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18007e9cd`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18007ea28`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18007ea69`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18007ea69`

## pseudocode

```c
_BOOL8 __fastcall GetCurrentUserSID(_QWORD *a1)
{
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  DWORD LastError; // ebx
  DWORD v5; // ebx
  HANDLE ProcessHeap; // rax
  PSID *v7; // rsi
  PSID v8; // rbp
  DWORD LengthSid; // r14d
  HANDLE v10; // rax
  void *v11; // rax
  void *v12; // rdi
  DWORD v13; // ebx
  HANDLE v14; // rax
  HANDLE v15; // rax
  DWORD TokenInformationLength; // [rsp+68h] [rbp+10h] BYREF
  void *TokenHandle; // [rsp+70h] [rbp+18h] BYREF

  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0x20008u, 0, &TokenHandle)
    || GetLastError() == 1008
    && (CurrentProcess = GetCurrentProcess(), OpenProcessToken(CurrentProcess, 0x20008u, &TokenHandle)) )
  {
    TokenInformationLength = 0;
    if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) || GetLastError() != 122 )
    {
      LastError = GetLastError();
      if ( !LastError )
        LastError = 31;
    }
    else
    {
      v5 = TokenInformationLength;
      ProcessHeap = GetProcessHeap();
      v7 = (PSID *)HeapAlloc(ProcessHeap, 8u, v5);
      if ( v7 )
      {
        if ( GetTokenInformation(TokenHandle, TokenUser, v7, TokenInformationLength, &TokenInformationLength) )
        {
          v8 = *v7;
          LengthSid = GetLengthSid(*v7);
          v10 = GetProcessHeap();
          v11 = HeapAlloc(v10, 8u, LengthSid);
          v12 = v11;
          if ( v11 )
          {
            v13 = 0;
            if ( !CopySid(LengthSid, v11, v8) )
            {
              v13 = GetLastError();
              v14 = GetProcessHeap();
              if ( HeapFree(v14, 0, v12) )
                v12 = 0;
            }
          }
          else
          {
            v13 = 14;
          }
          SetLastError(v13);
          *a1 = v12;
        }
        LastError = GetLastError();
        v15 = GetProcessHeap();
        HeapFree(v15, 0, v7);
      }
      else
      {
        LastError = 14;
      }
    }
    CloseHandle(TokenHandle);
  }
  else
  {
    LastError = GetLastError();
  }
  SetLastError(LastError);
  return LastError == 0;
}

```

## disassembly

```asm
0x18007e938  mov     [rsp+arg_0], rbx
0x18007e93d  push    rbp
0x18007e93e  push    rsi
0x18007e93f  push    rdi
0x18007e940  push    r14
0x18007e942  push    r15
0x18007e944  sub     rsp, 30h
0x18007e948  mov     r15, rcx
0x18007e94b  mov     [rsp+58h+TokenHandle], 0
0x18007e954  call    cs:__imp_GetCurrentThread
0x18007e95a  mov     ebx, 20008h
0x18007e95f  lea     r9, [rsp+58h+TokenHandle]; TokenHandle
0x18007e964  mov     rcx, rax; ThreadHandle
0x18007e967  mov     edx, ebx; DesiredAccess
0x18007e969  xor     r8d, r8d; OpenAsSelf
0x18007e96c  call    cs:__imp_OpenThreadToken
0x18007e972  test    eax, eax
0x18007e974  jnz     short loc_18007E9AA
0x18007e976  call    cs:__imp_GetLastError
0x18007e97c  cmp     eax, 3F0h
0x18007e981  jnz     short loc_18007E99D
0x18007e983  call    cs:__imp_GetCurrentProcess
0x18007e989  lea     r8, [rsp+58h+TokenHandle]; TokenHandle
0x18007e98e  mov     edx, ebx; DesiredAccess
0x18007e990  mov     rcx, rax; ProcessHandle
0x18007e993  call    cs:__imp_OpenProcessToken
0x18007e999  test    eax, eax
0x18007e99b  jnz     short loc_18007E9AA
0x18007e99d  call    cs:__imp_GetLastError
0x18007e9a3  mov     ebx, eax
0x18007e9a5  jmp     loc_18007EAE9
0x18007e9aa  mov     rcx, [rsp+58h+TokenHandle]; TokenHandle
0x18007e9af  lea     rax, [rsp+58h+TokenInformationLength]
0x18007e9b4  xor     r9d, r9d; TokenInformationLength
0x18007e9b7  mov     [rsp+58h+TokenInformationLength], 0
0x18007e9bf  xor     r8d, r8d; TokenInformation
0x18007e9c2  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x18007e9c7  lea     edi, [r9+1]
0x18007e9cb  mov     edx, edi; TokenInformationClass
0x18007e9cd  call    cs:__imp_GetTokenInformation
0x18007e9d3  test    eax, eax
0x18007e9d5  jnz     loc_18007EACC
0x18007e9db  call    cs:__imp_GetLastError
0x18007e9e1  cmp     eax, 7Ah ; 'z'
0x18007e9e4  jnz     loc_18007EACC
0x18007e9ea  mov     ebx, [rsp+58h+TokenInformationLength]
0x18007e9ee  call    cs:__imp_GetProcessHeap
0x18007e9f4  mov     r8d, ebx; dwBytes
0x18007e9f7  lea     edx, [rdi+7]; dwFlags
0x18007e9fa  mov     rcx, rax; hHeap
0x18007e9fd  call    cs:__imp_HeapAlloc
0x18007ea03  mov     rsi, rax
0x18007ea06  test    rax, rax
0x18007ea09  jz      loc_18007EAC5
0x18007ea0f  mov     r9d, [rsp+58h+TokenInformationLength]; TokenInformationLength
0x18007ea14  lea     rax, [rsp+58h+TokenInformationLength]
0x18007ea19  mov     rcx, [rsp+58h+TokenHandle]; TokenHandle
0x18007ea1e  mov     r8, rsi; TokenInformation
0x18007ea21  mov     edx, edi; TokenInformationClass
0x18007ea23  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x18007ea28  call    cs:__imp_GetTokenInformation
0x18007ea2e  test    eax, eax
0x18007ea30  jz      short loc_18007EAA7
0x18007ea32  mov     rbp, [rsi]
0x18007ea35  mov     rcx, rbp; pSid
0x18007ea38  call    cs:__imp_GetLengthSid
0x18007ea3e  mov     r14d, eax
0x18007ea41  call    cs:__imp_GetProcessHeap
0x18007ea47  mov     r8d, r14d; dwBytes
0x18007ea4a  lea     edx, [rdi+7]; dwFlags
0x18007ea4d  mov     rcx, rax; hHeap
0x18007ea50  call    cs:__imp_HeapAlloc
0x18007ea56  mov     rdi, rax
0x18007ea59  test    rax, rax
0x18007ea5c  jz      short loc_18007EA97
0x18007ea5e  mov     r8, rbp; pSourceSid
0x18007ea61  mov     rdx, rax; pDestinationSid
0x18007ea64  mov     ecx, r14d; nDestinationSidLength
0x18007ea67  xor     ebx, ebx
0x18007ea69  call    cs:__imp_CopySid
0x18007ea6f  test    eax, eax
0x18007ea71  jnz     short loc_18007EA9C
0x18007ea73  call    cs:__imp_GetLastError
0x18007ea79  mov     ebx, eax
0x18007ea7b  call    cs:__imp_GetProcessHeap
0x18007ea81  mov     r8, rdi; lpMem
0x18007ea84  xor     edx, edx; dwFlags
0x18007ea86  mov     rcx, rax; hHeap
0x18007ea89  call    cs:__imp_HeapFree
0x18007ea8f  test    eax, eax
0x18007ea91  jz      short loc_18007EA9C
0x18007ea93  xor     edi, edi
0x18007ea95  jmp     short loc_18007EA9C
0x18007ea97  mov     ebx, 0Eh
0x18007ea9c  mov     ecx, ebx; dwErrCode
0x18007ea9e  call    cs:__imp_SetLastError
0x18007eaa4  mov     [r15], rdi
0x18007eaa7  call    cs:__imp_GetLastError
0x18007eaad  mov     ebx, eax
0x18007eaaf  call    cs:__imp_GetProcessHeap
0x18007eab5  mov     r8, rsi; lpMem
0x18007eab8  xor     edx, edx; dwFlags
0x18007eaba  mov     rcx, rax; hHeap
0x18007eabd  call    cs:__imp_HeapFree
0x18007eac3  jmp     short loc_18007EADE
0x18007eac5  mov     ebx, 0Eh
0x18007eaca  jmp     short loc_18007EADE
0x18007eacc  call    cs:__imp_GetLastError
0x18007ead2  mov     ebx, eax
0x18007ead4  mov     eax, 1Fh
0x18007ead9  test    ebx, ebx
0x18007eadb  cmovz   ebx, eax
0x18007eade  mov     rcx, [rsp+58h+TokenHandle]; hObject
0x18007eae3  call    cs:__imp_CloseHandle
0x18007eae9  mov     ecx, ebx; dwErrCode
0x18007eaeb  call    cs:__imp_SetLastError
0x18007eaf1  xor     eax, eax
0x18007eaf3  test    ebx, ebx
0x18007eaf5  mov     rbx, [rsp+58h+arg_0]
0x18007eafa  setz    al
0x18007eafd  add     rsp, 30h
0x18007eb01  pop     r15
0x18007eb03  pop     r14
0x18007eb05  pop     rdi
0x18007eb06  pop     rsi
0x18007eb07  pop     rbp
0x18007eb08  retn
```
