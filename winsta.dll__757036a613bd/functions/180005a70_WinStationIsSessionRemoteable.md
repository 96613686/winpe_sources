# WinStationIsSessionRemoteable

- ea: `0x180005a70`
- end: `0x180005c28`
- name: `WinStationIsSessionRemoteable`
- size: `440`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002da60`

## callees

- `0x180005a70`
- `0x180005fcc`
- `0x180007890`
- `0x1800094f0`
- `0x18000b870`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005b66`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005b66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005acb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005b9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005bcc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005bfa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005acb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005b9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005bcc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005bfa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180005adc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180005adc`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180005ac1`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180005ac1`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180005aef`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180005aef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180005aa8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180005aa8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005b38`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005b38`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180005b1c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180005b1c`

## string_xrefs

- `0x180005bb6`: `GetTokenInformation failed: 0x%x`
- `0x180005be4`: `OpenProcessToken failed: 0x%x`
- `0x180005c12`: `OpenThreadToken failed: 0x%x`

## pseudocode

```c
char __fastcall WinStationIsSessionRemoteable(__int64 a1, unsigned int a2, __int64 a3)
{
  signed int v3; // edi
  int v7; // esi
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  DWORD v10; // eax
  signed int LastError; // eax
  signed int v13; // eax
  signed int v14; // eax
  DWORD ReturnLength; // [rsp+30h] [rbp-28h] BYREF
  void *TokenHandle[4]; // [rsp+38h] [rbp-20h] BYREF
  int TokenInformation; // [rsp+78h] [rbp+20h] BYREF

  v3 = 0;
  TokenInformation = -1;
  TokenHandle[0] = 0;
  ReturnLength = 0;
  if ( a2 == -1 )
    return WinStationIsCurrentSessionRemoteable(a3);
  v7 = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, TokenHandle) )
    goto LABEL_5;
  if ( GetLastError() == 1008 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 8u, TokenHandle) )
    {
LABEL_5:
      if ( GetTokenInformation(TokenHandle[0], TokenSessionId, &TokenInformation, 4u, &ReturnLength) )
      {
        LOBYTE(v7) = TokenInformation == a2;
      }
      else
      {
        LastError = GetLastError();
        v3 = LastError;
        if ( LastError > 0 )
          v3 = (unsigned __int16)LastError | 0x80070000;
        _DbgPrintMessage(8, "GetTokenInformation failed: 0x%x", v3);
      }
      goto LABEL_7;
    }
    v13 = GetLastError();
    v3 = v13;
    if ( v13 > 0 )
      v3 = (unsigned __int16)v13 | 0x80070000;
    _DbgPrintMessage(8, "OpenProcessToken failed: 0x%x", v3);
  }
  else
  {
    v14 = GetLastError();
    v3 = v14;
    if ( v14 > 0 )
      v3 = (unsigned __int16)v14 | 0x80070000;
    _DbgPrintMessage(8, "OpenThreadToken failed: 0x%x", v3);
  }
LABEL_7:
  if ( TokenHandle[0] )
    CloseHandle(TokenHandle[0]);
  if ( v3 < 0 )
  {
    _DbgPrintMessage(8, "CUtils::IsCurrentSession failed: 0x%x in %s", v3, "WinStationIsSessionRemoteable");
    v10 = ConvertHRESULT2WIN32(v3);
    SetLastError(v10);
    return 0;
  }
  if ( !v7 )
    return InternalIsSessionRemoteable(a1, a2, a3);
  return WinStationIsCurrentSessionRemoteable(a3);
}

```

## disassembly

```asm
0x180005a70  mov     [rsp+arg_0], rbx
0x180005a75  mov     [rsp+arg_8], rbp
0x180005a7a  push    rsi
0x180005a7b  push    rdi
0x180005a7c  push    r14
0x180005a7e  sub     rsp, 40h
0x180005a82  xor     edi, edi
0x180005a84  mov     [rsp+58h+TokenInformation], 0FFFFFFFFh
0x180005a8c  mov     [rsp+58h+TokenHandle], rdi
0x180005a91  mov     rbp, r8
0x180005a94  mov     [rsp+58h+var_28], edi
0x180005a98  mov     ebx, edx
0x180005a9a  mov     r14, rcx
0x180005a9d  cmp     edx, 0FFFFFFFFh
0x180005aa0  jz      loc_180005B94
0x180005aa6  mov     esi, edi
0x180005aa8  call    cs:__imp_GetCurrentThread
0x180005aae  lea     r9, [rsp+58h+TokenHandle]; TokenHandle
0x180005ab3  mov     edx, 8; DesiredAccess
0x180005ab8  mov     rcx, rax; ThreadHandle
0x180005abb  mov     r8d, 1; OpenAsSelf
0x180005ac1  call    cs:__imp_OpenThreadToken
0x180005ac7  test    eax, eax
0x180005ac9  jnz     short loc_180005AFD
0x180005acb  call    cs:__imp_GetLastError
0x180005ad1  cmp     eax, 3F0h
0x180005ad6  jnz     loc_180005BFA
0x180005adc  call    cs:__imp_GetCurrentProcess
0x180005ae2  lea     r8, [rsp+58h+TokenHandle]; TokenHandle
0x180005ae7  mov     edx, 8; DesiredAccess
0x180005aec  mov     rcx, rax; ProcessHandle
0x180005aef  call    cs:__imp_OpenProcessToken
0x180005af5  test    eax, eax
0x180005af7  jz      loc_180005BCC
0x180005afd  mov     rcx, [rsp+58h+TokenHandle]; TokenHandle
0x180005b02  lea     rax, [rsp+58h+var_28]
0x180005b07  mov     r9d, 4; TokenInformationLength
0x180005b0d  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x180005b12  lea     r8, [rsp+58h+TokenInformation]; TokenInformation
0x180005b17  mov     edx, 0Ch; TokenInformationClass
0x180005b1c  call    cs:__imp_GetTokenInformation
0x180005b22  test    eax, eax
0x180005b24  jz      short loc_180005B9E
0x180005b26  cmp     [rsp+58h+TokenInformation], ebx
0x180005b2a  setz    sil
0x180005b2e  mov     rcx, [rsp+58h+TokenHandle]; hObject
0x180005b33  test    rcx, rcx
0x180005b36  jz      short loc_180005B3E
0x180005b38  call    cs:__imp_CloseHandle
0x180005b3e  test    edi, edi
0x180005b40  jns     short loc_180005B81
0x180005b42  lea     r9, aWinstationisse_1; "WinStationIsSessionRemoteable"
0x180005b49  mov     r8d, edi
0x180005b4c  lea     rdx, aCutilsIscurren; "CUtils::IsCurrentSession failed: 0x%x i"...
0x180005b53  mov     ecx, 8; int
0x180005b58  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180005b5d  mov     ecx, edi; int
0x180005b5f  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x180005b64  mov     ecx, eax; dwErrCode
0x180005b66  call    cs:__imp_SetLastError
0x180005b6c  xor     al, al
0x180005b6e  mov     rbx, [rsp+58h+arg_0]
0x180005b73  mov     rbp, [rsp+58h+arg_8]
0x180005b78  add     rsp, 40h
0x180005b7c  pop     r14
0x180005b7e  pop     rdi
0x180005b7f  pop     rsi
0x180005b80  retn
0x180005b81  test    esi, esi
0x180005b83  jnz     short loc_180005B94
0x180005b85  mov     r8, rbp
0x180005b88  mov     edx, ebx
0x180005b8a  mov     rcx, r14
0x180005b8d  call    InternalIsSessionRemoteable
0x180005b92  jmp     short loc_180005B6E
0x180005b94  mov     rcx, rbp
0x180005b97  call    WinStationIsCurrentSessionRemoteable
0x180005b9c  jmp     short loc_180005B6E
0x180005b9e  call    cs:__imp_GetLastError
0x180005ba4  mov     edi, eax
0x180005ba6  test    eax, eax
0x180005ba8  jle     short loc_180005BB3
0x180005baa  movzx   edi, ax
0x180005bad  or      edi, 80070000h
0x180005bb3  mov     r8d, edi
0x180005bb6  lea     rdx, aGettokeninform_0; "GetTokenInformation failed: 0x%x"
0x180005bbd  mov     ecx, 8; int
0x180005bc2  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180005bc7  jmp     loc_180005B2E
0x180005bcc  call    cs:__imp_GetLastError
0x180005bd2  mov     edi, eax
0x180005bd4  test    eax, eax
0x180005bd6  jle     short loc_180005BE1
0x180005bd8  movzx   edi, ax
0x180005bdb  or      edi, 80070000h
0x180005be1  mov     r8d, edi
0x180005be4  lea     rdx, aOpenprocesstok_0; "OpenProcessToken failed: 0x%x"
0x180005beb  mov     ecx, 8; int
0x180005bf0  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180005bf5  jmp     loc_180005B2E
0x180005bfa  call    cs:__imp_GetLastError
0x180005c00  mov     edi, eax
0x180005c02  test    eax, eax
0x180005c04  jle     short loc_180005C0F
0x180005c06  movzx   edi, ax
0x180005c09  or      edi, 80070000h
0x180005c0f  mov     r8d, edi
0x180005c12  lea     rdx, aOpenthreadtoke; "OpenThreadToken failed: 0x%x"
0x180005c19  mov     ecx, 8; int
0x180005c1e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180005c23  jmp     loc_180005B2E
```
