# I_PinCacheGetLuid

- ea: `0x180039068`
- end: `0x180039163`
- name: `I_PinCacheGetLuid`
- size: `251`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003916c`
- `0x1800391c4`

## callees

- `0x180039068`
- `0x18003c240`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800390dd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800390dd`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800390c4`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800390c4`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800390ef`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800390ef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800390ae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800390ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800390ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800390f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800390ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800390f9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003913a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003913a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003911e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003911e`

## pseudocode

```c
__int64 __fastcall I_PinCacheGetLuid(_QWORD *a1)
{
  HANDLE CurrentThread; // rax
  DWORD LastError; // ebx
  HANDLE CurrentProcess; // rax
  void *TokenHandle; // [rsp+30h] [rbp-50h] BYREF
  DWORD ReturnLength; // [rsp+38h] [rbp-48h] BYREF
  _OWORD TokenInformation[3]; // [rsp+40h] [rbp-40h] BYREF
  __int64 v9; // [rsp+70h] [rbp-10h]

  TokenHandle = 0;
  memset(TokenInformation, 0, sizeof(TokenInformation));
  v9 = 0;
  ReturnLength = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    LastError = GetLastError();
    if ( LastError != 1008 )
      goto LABEL_7;
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
      goto LABEL_4;
  }
  if ( GetTokenInformation(TokenHandle, TokenStatistics, TokenInformation, 0x38u, &ReturnLength) )
  {
    LastError = 0;
    *a1 = *((_QWORD *)&TokenInformation[0] + 1);
  }
  else
  {
LABEL_4:
    LastError = GetLastError();
  }
LABEL_7:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return LastError;
}

```

## disassembly

```asm
0x180039068  mov     [rsp-8+arg_8], rbx
0x18003906d  mov     [rsp-8+arg_10], rdi
0x180039072  push    rbp
0x180039073  mov     rbp, rsp
0x180039076  sub     rsp, 80h
0x18003907d  mov     rax, cs:__security_cookie
0x180039084  xor     rax, rsp
0x180039087  mov     [rbp+var_8], rax
0x18003908b  xorps   xmm0, xmm0
0x18003908e  mov     [rbp+TokenHandle], 0
0x180039096  xor     eax, eax
0x180039098  mov     rdi, rcx
0x18003909b  movups  [rbp+TokenInformation], xmm0
0x18003909f  mov     [rbp+var_10], rax
0x1800390a3  movups  [rbp+var_30], xmm0
0x1800390a7  mov     [rbp+var_48], eax
0x1800390aa  movups  [rbp+var_20], xmm0
0x1800390ae  call    cs:__imp_GetCurrentThread
0x1800390b4  mov     edx, 8; DesiredAccess
0x1800390b9  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800390bd  mov     rcx, rax; ThreadHandle
0x1800390c0  lea     r8d, [rdx-7]; OpenAsSelf
0x1800390c4  call    cs:__imp_OpenThreadToken
0x1800390ca  test    eax, eax
0x1800390cc  jnz     short loc_180039103
0x1800390ce  call    cs:__imp_GetLastError
0x1800390d4  mov     ebx, eax
0x1800390d6  cmp     eax, 3F0h
0x1800390db  jnz     short loc_180039131
0x1800390dd  call    cs:__imp_GetCurrentProcess
0x1800390e3  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1800390e7  mov     edx, 8; DesiredAccess
0x1800390ec  mov     rcx, rax; ProcessHandle
0x1800390ef  call    cs:__imp_OpenProcessToken
0x1800390f5  test    eax, eax
0x1800390f7  jnz     short loc_180039103
0x1800390f9  call    cs:__imp_GetLastError
0x1800390ff  mov     ebx, eax
0x180039101  jmp     short loc_180039131
0x180039103  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180039107  lea     rax, [rbp+var_48]
0x18003910b  mov     r9d, 38h ; '8'; TokenInformationLength
0x180039111  mov     [rsp+80h+ReturnLength], rax; ReturnLength
0x180039116  lea     r8, [rbp+TokenInformation]; TokenInformation
0x18003911a  lea     edx, [r9-2Eh]; TokenInformationClass
0x18003911e  call    cs:__imp_GetTokenInformation
0x180039124  test    eax, eax
0x180039126  jz      short loc_1800390F9
0x180039128  mov     rax, qword ptr [rbp+TokenInformation+8]
0x18003912c  xor     ebx, ebx
0x18003912e  mov     [rdi], rax
0x180039131  mov     rcx, [rbp+TokenHandle]; hObject
0x180039135  test    rcx, rcx
0x180039138  jz      short loc_180039140
0x18003913a  call    cs:__imp_CloseHandle
0x180039140  mov     eax, ebx
0x180039142  mov     rcx, [rbp+var_8]
0x180039146  xor     rcx, rsp; StackCookie
0x180039149  call    __security_check_cookie
0x18003914e  lea     r11, [rsp+80h+var_s0]
0x180039156  mov     rbx, [r11+18h]
0x18003915a  mov     rdi, [r11+20h]
0x18003915e  mov     rsp, r11
0x180039161  pop     rbp
0x180039162  retn
```
