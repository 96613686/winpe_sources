# CheckProcessIsLowBox(void)

- ea: `0x1800734cc`
- end: `0x18007362d`
- name: `?CheckProcessIsLowBox@@YAKXZ`
- size: `353`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18007311c`

## callees

- `0x1800734cc`
- `0x1800a1d10`
- `0x1800db6b0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180073588`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180073588`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18007354d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18007354d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180073530`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180073530`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180073518`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180073518`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18007355f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18007355f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007353a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800735d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073615`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007353a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800735d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073615`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800735b3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800735ce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800735b3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800735ce`

## pseudocode

```c
__int64 CheckProcessIsLowBox(void)
{
  DWORD v0; // ebx
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  HANDLE CurrentProcess; // rax
  __int64 v5; // rdx
  PDWORD ReturnLength; // [rsp+20h] [rbp-30h]
  void *TokenHandle; // [rsp+30h] [rbp-20h] BYREF
  HANDLE hObject; // [rsp+38h] [rbp-18h] BYREF
  int TokenInformation; // [rsp+40h] [rbp-10h] BYREF
  DWORD v10; // [rsp+44h] [rbp-Ch] BYREF

  v0 = 0;
  TokenHandle = 0;
  hObject = 0;
  TokenInformation = 0;
  v10 = 0;
  if ( g_fLowBoxProcessDetermined )
    return v0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0x2000000u, 1, &TokenHandle) )
  {
    LastError = GetLastError();
    v0 = LastError;
    if ( LastError == 1008 )
    {
      CurrentProcess = GetCurrentProcess();
      if ( OpenProcessToken(CurrentProcess, 0x2000000u, &hObject) )
      {
        if ( GetTokenInformation(hObject, TokenIsAppContainer, &TokenInformation, 4u, &v10) )
        {
          g_fLowBoxProcessDetermined = 1;
          g_fLowBoxProcess = TokenInformation != 0;
          goto LABEL_8;
        }
        LastError = GetLastError();
        v0 = LastError;
        if ( (xmmword_180107A50 & 2) == 0 )
          goto LABEL_8;
        v5 = 25;
      }
      else
      {
        LastError = GetLastError();
        v0 = LastError;
        if ( (xmmword_180107A50 & 2) == 0 )
          goto LABEL_8;
        v5 = 24;
      }
    }
    else
    {
      if ( (xmmword_180107A50 & 2) == 0 )
        goto LABEL_8;
      v5 = 23;
    }
    WPP_SF_d(513, v5, WPP_d20135cef7e33325d83cff35dd261285_Traceguids, LastError, ReturnLength);
  }
LABEL_8:
  if ( TokenHandle )
  {
    CloseHandle(TokenHandle);
    TokenHandle = 0;
  }
  if ( hObject )
    CloseHandle(hObject);
  return v0;
}

```

## disassembly

```asm
0x1800734cc  mov     [rsp-8+arg_0], rbx
0x1800734d1  push    rbp
0x1800734d2  mov     rbp, rsp
0x1800734d5  sub     rsp, 50h
0x1800734d9  mov     rax, cs:__security_cookie
0x1800734e0  xor     rax, rsp
0x1800734e3  mov     [rbp+var_8], rax
0x1800734e7  xor     ebx, ebx
0x1800734e9  cmp     cs:?g_fLowBoxProcessDetermined@@3HA, ebx; int g_fLowBoxProcessDetermined
0x1800734ef  mov     [rbp+TokenHandle], rbx
0x1800734f3  mov     [rbp+hObject], rbx
0x1800734f7  mov     [rbp+TokenInformation], ebx
0x1800734fa  mov     [rbp+var_C], ebx
0x1800734fd  jz      short loc_180073518
0x1800734ff  mov     eax, ebx
0x180073501  mov     rcx, [rbp+var_8]
0x180073505  xor     rcx, rsp; StackCookie
0x180073508  call    __security_check_cookie
0x18007350d  mov     rbx, [rsp+50h+arg_0]
0x180073512  add     rsp, 50h
0x180073516  pop     rbp
0x180073517  retn
0x180073518  call    cs:__imp_GetCurrentThread
0x18007351e  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180073522  mov     edx, 2000000h; DesiredAccess
0x180073527  mov     rcx, rax; ThreadHandle
0x18007352a  mov     r8d, 1; OpenAsSelf
0x180073530  call    cs:__imp_OpenThreadToken
0x180073536  test    eax, eax
0x180073538  jnz     short loc_1800735AA
0x18007353a  call    cs:__imp_GetLastError
0x180073540  mov     ebx, eax
0x180073542  cmp     eax, 3F0h
0x180073547  jnz     loc_180073605
0x18007354d  call    cs:__imp_GetCurrentProcess
0x180073553  lea     r8, [rbp+hObject]; TokenHandle
0x180073557  mov     edx, 2000000h; DesiredAccess
0x18007355c  mov     rcx, rax; ProcessHandle
0x18007355f  call    cs:__imp_OpenProcessToken
0x180073565  test    eax, eax
0x180073567  jz      loc_180073615
0x18007356d  mov     rcx, [rbp+hObject]; TokenHandle
0x180073571  lea     rax, [rbp+var_C]
0x180073575  mov     r9d, 4; TokenInformationLength
0x18007357b  mov     [rsp+50h+ReturnLength], rax; ReturnLength
0x180073580  lea     r8, [rbp+TokenInformation]; TokenInformation
0x180073584  lea     edx, [r9+19h]; TokenInformationClass
0x180073588  call    cs:__imp_GetTokenInformation
0x18007358e  test    eax, eax
0x180073590  jz      short loc_1800735D9
0x180073592  xor     eax, eax
0x180073594  mov     cs:?g_fLowBoxProcessDetermined@@3HA, 1; int g_fLowBoxProcessDetermined
0x18007359e  cmp     [rbp+TokenInformation], eax
0x1800735a1  setnz   al
0x1800735a4  mov     cs:?g_fLowBoxProcess@@3HA, eax; int g_fLowBoxProcess
0x1800735aa  mov     rcx, [rbp+TokenHandle]; hObject
0x1800735ae  test    rcx, rcx
0x1800735b1  jz      short loc_1800735C1
0x1800735b3  call    cs:__imp_CloseHandle
0x1800735b9  mov     [rbp+TokenHandle], 0
0x1800735c1  mov     rcx, [rbp+hObject]; hObject
0x1800735c5  test    rcx, rcx
0x1800735c8  jz      loc_1800734FF
0x1800735ce  call    cs:__imp_CloseHandle
0x1800735d4  jmp     loc_1800734FF
0x1800735d9  call    cs:__imp_GetLastError
0x1800735df  mov     ebx, eax
0x1800735e1  test    byte ptr cs:xmmword_180107A50, 2
0x1800735e8  jz      short loc_1800735AA
0x1800735ea  mov     edx, 19h
0x1800735ef  mov     ecx, 201h
0x1800735f4  lea     r8, WPP_d20135cef7e33325d83cff35dd261285_Traceguids
0x1800735fb  mov     r9d, eax
0x1800735fe  call    WPP_SF_d
0x180073603  jmp     short loc_1800735AA
0x180073605  test    byte ptr cs:xmmword_180107A50, 2
0x18007360c  jz      short loc_1800735AA
0x18007360e  mov     edx, 17h
0x180073613  jmp     short loc_1800735EF
0x180073615  call    cs:__imp_GetLastError
0x18007361b  mov     ebx, eax
0x18007361d  test    byte ptr cs:xmmword_180107A50, 2
0x180073624  jz      short loc_1800735AA
0x180073626  mov     edx, 18h
0x18007362b  jmp     short loc_1800735EF
```
