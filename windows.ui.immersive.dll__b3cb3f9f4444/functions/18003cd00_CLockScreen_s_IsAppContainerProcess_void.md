# CLockScreen::_s_IsAppContainerProcess(void)

- ea: `0x18003cd00`
- end: `0x18003cdef`
- name: `?_s_IsAppContainerProcess@CLockScreen@@KA_NXZ`
- size: `239`
- prototype: `bool(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180009890`
- `0x1800422a0`

## callees

- `0x18003cd00`
- `0x18003d244`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003cd59`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003cd59`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003cd0c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003cd0c`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18003cd22`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18003cd22`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003cdc6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003cdd5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003cdc6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003cdd5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003cda0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003cda0`

## pseudocode

```c
bool CLockScreen::_s_IsAppContainerProcess(void)
{
  bool v0; // bl
  DWORD CurrentProcessId; // eax
  HANDLE v2; // rdi
  int TokenInformation; // [rsp+40h] [rbp+8h] BYREF
  DWORD ReturnLength; // [rsp+48h] [rbp+10h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp+18h] BYREF

  v0 = 0;
  CurrentProcessId = GetCurrentProcessId();
  v2 = OpenProcess(0x1000u, 0, CurrentProcessId);
  if ( v2 || (int)ResultFromKnownLastError() >= 0 )
  {
    TokenHandle = 0;
    if ( OpenProcessToken(v2, 8u, &TokenHandle) || (int)ResultFromKnownLastError() >= 0 )
    {
      ReturnLength = 0;
      TokenInformation = 0;
      if ( GetTokenInformation(TokenHandle, TokenIsAppContainer, &TokenInformation, 4u, &ReturnLength)
        || (int)ResultFromKnownLastError() >= 0 )
      {
        v0 = TokenInformation != 0;
      }
      CloseHandle(TokenHandle);
    }
    CloseHandle(v2);
  }
  return v0;
}

```

## disassembly

```asm
0x18003cd00  mov     [rsp+arg_18], rbx
0x18003cd05  push    rdi
0x18003cd06  sub     rsp, 30h
0x18003cd0a  xor     bl, bl
0x18003cd0c  call    cs:__imp_GetCurrentProcessId
0x18003cd13  nop     dword ptr [rax+rax+00h]
0x18003cd18  xor     edx, edx; bInheritHandle
0x18003cd1a  mov     ecx, 1000h; dwDesiredAccess
0x18003cd1f  mov     r8d, eax; dwProcessId
0x18003cd22  call    cs:__imp_OpenProcess
0x18003cd29  nop     dword ptr [rax+rax+00h]
0x18003cd2e  mov     rdi, rax
0x18003cd31  test    rax, rax
0x18003cd34  jnz     short loc_18003CD43
0x18003cd36  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18003cd3b  test    eax, eax
0x18003cd3d  js      loc_18003CDE1
0x18003cd43  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x18003cd48  mov     [rsp+38h+TokenHandle], 0
0x18003cd51  mov     edx, 8; DesiredAccess
0x18003cd56  mov     rcx, rdi; ProcessHandle
0x18003cd59  call    cs:__imp_OpenProcessToken
0x18003cd60  nop     dword ptr [rax+rax+00h]
0x18003cd65  test    eax, eax
0x18003cd67  jnz     short loc_18003CD72
0x18003cd69  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18003cd6e  test    eax, eax
0x18003cd70  js      short loc_18003CDD2
0x18003cd72  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x18003cd77  lea     rax, [rsp+38h+arg_8]
0x18003cd7c  mov     r9d, 4; TokenInformationLength
0x18003cd82  mov     [rsp+38h+arg_8], 0
0x18003cd8a  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x18003cd8f  mov     [rsp+38h+TokenInformation], 0
0x18003cd97  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18003cd9c  lea     edx, [r9+19h]; TokenInformationClass
0x18003cda0  call    cs:__imp_GetTokenInformation
0x18003cda7  nop     dword ptr [rax+rax+00h]
0x18003cdac  test    eax, eax
0x18003cdae  jnz     short loc_18003CDB9
0x18003cdb0  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18003cdb5  test    eax, eax
0x18003cdb7  js      short loc_18003CDC1
0x18003cdb9  cmp     [rsp+38h+TokenInformation], 0
0x18003cdbe  setnz   bl
0x18003cdc1  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x18003cdc6  call    cs:__imp_CloseHandle
0x18003cdcd  nop     dword ptr [rax+rax+00h]
0x18003cdd2  mov     rcx, rdi; hObject
0x18003cdd5  call    cs:__imp_CloseHandle
0x18003cddc  nop     dword ptr [rax+rax+00h]
0x18003cde1  mov     al, bl
0x18003cde3  mov     rbx, [rsp+38h+arg_18]
0x18003cde8  add     rsp, 30h
0x18003cdec  pop     rdi
0x18003cded  retn
```
