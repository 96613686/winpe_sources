# LUAIsUserUACAdmin

- ea: `0x180026b58`
- end: `0x180026c61`
- name: `LUAIsUserUACAdmin`
- size: `265`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180018824`

## callees

- `0x1800269cc`
- `0x180026a70`
- `0x180026aac`
- `0x180026b58`
- `0x180026c68`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026c34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026c3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026c48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026c34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026c3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026c48`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180026b74`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180026b74`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180026b86`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180026b86`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026c19`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026c2c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026c19`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026c2c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180026bfb`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180026bfb`

## pseudocode

```c
__int64 __fastcall LUAIsUserUACAdmin(_DWORD *a1)
{
  HANDLE CurrentProcess; // rax
  NTSTATUS v3; // ebx
  int v4; // eax
  void *v5; // rcx
  DWORD ReturnLength; // [rsp+50h] [rbp+20h] BYREF
  void *TokenInformation; // [rsp+58h] [rbp+28h] BYREF
  void *TokenHandle; // [rsp+60h] [rbp+30h] BYREF

  *a1 = 0;
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0xAu, &TokenHandle) )
  {
    if ( (unsigned int)Feature_ShadowAdmin__private_IsEnabledDeviceUsageNoInline() )
    {
      v3 = LUAIsUserUACAdminEx(TokenHandle);
    }
    else
    {
      ReturnLength = 0;
      LODWORD(TokenInformation) = 0;
      v3 = LUAIsElevatedToken(TokenHandle, &ReturnLength, &TokenInformation);
      if ( v3 >= 0 )
      {
        if ( ReturnLength )
        {
          *a1 = _LUAIsTokenAdmin(TokenHandle);
        }
        else
        {
          TokenInformation = 0;
          ReturnLength = 8;
          if ( GetTokenInformation(TokenHandle, TokenLinkedToken, &TokenInformation, 8u, &ReturnLength)
            && TokenInformation )
          {
            v4 = _LUAIsTokenAdmin(TokenInformation);
            v5 = TokenInformation;
            *a1 = v4;
            CloseHandle(v5);
          }
        }
      }
    }
    CloseHandle(TokenHandle);
  }
  else if ( (int)GetLastError() > 0 )
  {
    return (unsigned __int16)GetLastError() | 0xC0070000;
  }
  else
  {
    return GetLastError();
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180026b58  push    rbp
0x180026b5a  push    rbx
0x180026b5b  push    rdi
0x180026b5c  mov     rbp, rsp
0x180026b5f  sub     rsp, 30h
0x180026b63  mov     rdi, rcx
0x180026b66  mov     dword ptr [rcx], 0
0x180026b6c  mov     [rbp+TokenHandle], 0
0x180026b74  call    cs:__imp_GetCurrentProcess
0x180026b7a  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180026b7e  mov     edx, 0Ah; DesiredAccess
0x180026b83  mov     rcx, rax; ProcessHandle
0x180026b86  call    cs:__imp_OpenProcessToken
0x180026b8c  test    eax, eax
0x180026b8e  jz      loc_180026C34
0x180026b94  call    Feature_ShadowAdmin__private_IsEnabledDeviceUsageNoInline
0x180026b99  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180026b9d  test    eax, eax
0x180026b9f  jz      short loc_180026BAD
0x180026ba1  mov     rdx, rdi
0x180026ba4  call    LUAIsUserUACAdminEx
0x180026ba9  mov     ebx, eax
0x180026bab  jmp     short loc_180026C28
0x180026bad  lea     r8, [rbp+TokenInformation]
0x180026bb1  mov     [rbp+arg_0], 0
0x180026bb8  lea     rdx, [rbp+arg_0]
0x180026bbc  mov     dword ptr [rbp+TokenInformation], 0
0x180026bc3  call    LUAIsElevatedToken
0x180026bc8  mov     ebx, eax
0x180026bca  test    eax, eax
0x180026bcc  js      short loc_180026C28
0x180026bce  cmp     [rbp+arg_0], 0
0x180026bd2  mov     rcx, [rbp+TokenHandle]; void *
0x180026bd6  jnz     short loc_180026C21
0x180026bd8  mov     r9d, 8; TokenInformationLength
0x180026bde  mov     [rbp+TokenInformation], 0
0x180026be6  lea     rax, [rbp+arg_0]
0x180026bea  mov     [rbp+arg_0], r9d
0x180026bee  lea     r8, [rbp+TokenInformation]; TokenInformation
0x180026bf2  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x180026bf7  lea     edx, [r9+0Bh]; TokenInformationClass
0x180026bfb  call    cs:__imp_GetTokenInformation
0x180026c01  test    eax, eax
0x180026c03  jz      short loc_180026C28
0x180026c05  mov     rcx, [rbp+TokenInformation]; void *
0x180026c09  test    rcx, rcx
0x180026c0c  jz      short loc_180026C28
0x180026c0e  call    ?_LUAIsTokenAdmin@@YAHPEAX@Z; _LUAIsTokenAdmin(void *)
0x180026c13  mov     rcx, [rbp+TokenInformation]; hObject
0x180026c17  mov     [rdi], eax
0x180026c19  call    cs:__imp_CloseHandle
0x180026c1f  jmp     short loc_180026C28
0x180026c21  call    ?_LUAIsTokenAdmin@@YAHPEAX@Z; _LUAIsTokenAdmin(void *)
0x180026c26  mov     [rdi], eax
0x180026c28  mov     rcx, [rbp+TokenHandle]; hObject
0x180026c2c  call    cs:__imp_CloseHandle
0x180026c32  jmp     short loc_180026C57
0x180026c34  call    cs:__imp_GetLastError
0x180026c3a  test    eax, eax
0x180026c3c  jg      short loc_180026C48
0x180026c3e  call    cs:__imp_GetLastError
0x180026c44  mov     ebx, eax
0x180026c46  jmp     short loc_180026C57
0x180026c48  call    cs:__imp_GetLastError
0x180026c4e  movzx   ebx, ax
0x180026c51  or      ebx, 0C0070000h
0x180026c57  mov     eax, ebx
0x180026c59  add     rsp, 30h
0x180026c5d  pop     rdi
0x180026c5e  pop     rbx
0x180026c5f  pop     rbp
0x180026c60  retn
```
