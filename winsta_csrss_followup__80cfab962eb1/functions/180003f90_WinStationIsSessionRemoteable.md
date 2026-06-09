# WinStationIsSessionRemoteable

- ea: `0x180003f90`
- end: `0x18000418f`
- name: `WinStationIsSessionRemoteable`
- size: `511`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002ff00`

## callees

- `0x180003f90`
- `0x180004558`
- `0x180005b40`
- `0x180007d20`
- `0x180009350`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800040b4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800040b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003ff7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800040f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004127`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000415b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003ff7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800040f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004127`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000415b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000400e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000400e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180003fe7`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180003fe7`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180004027`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180004027`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180003fc8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180003fc8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004080`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004080`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000405a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000405a`

## string_xrefs

- `0x180004111`: `GetTokenInformation failed: 0x%x`
- `0x180004145`: `OpenProcessToken failed: 0x%x`
- `0x180004179`: `OpenThreadToken failed: 0x%x`

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
0x180003f90  mov     [rsp+arg_0], rbx
0x180003f95  mov     [rsp+arg_8], rbp
0x180003f9a  push    rsi
0x180003f9b  push    rdi
0x180003f9c  push    r14
0x180003f9e  sub     rsp, 40h
0x180003fa2  xor     edi, edi
0x180003fa4  mov     [rsp+58h+TokenInformation], 0FFFFFFFFh
0x180003fac  mov     [rsp+58h+TokenHandle], rdi
0x180003fb1  mov     rbp, r8
0x180003fb4  mov     [rsp+58h+var_28], edi
0x180003fb8  mov     ebx, edx
0x180003fba  mov     r14, rcx
0x180003fbd  cmp     edx, 0FFFFFFFFh
0x180003fc0  jz      loc_1800040E9
0x180003fc6  mov     esi, edi
0x180003fc8  call    cs:__imp_GetCurrentThread
0x180003fcf  nop     dword ptr [rax+rax+00h]
0x180003fd4  lea     r9, [rsp+58h+TokenHandle]; TokenHandle
0x180003fd9  mov     edx, 8; DesiredAccess
0x180003fde  mov     rcx, rax; ThreadHandle
0x180003fe1  mov     r8d, 1; OpenAsSelf
0x180003fe7  call    cs:__imp_OpenThreadToken
0x180003fee  nop     dword ptr [rax+rax+00h]
0x180003ff3  test    eax, eax
0x180003ff5  jnz     short loc_18000403B
0x180003ff7  call    cs:__imp_GetLastError
0x180003ffe  nop     dword ptr [rax+rax+00h]
0x180004003  cmp     eax, 3F0h
0x180004008  jnz     loc_18000415B
0x18000400e  call    cs:__imp_GetCurrentProcess
0x180004015  nop     dword ptr [rax+rax+00h]
0x18000401a  lea     r8, [rsp+58h+TokenHandle]; TokenHandle
0x18000401f  mov     edx, 8; DesiredAccess
0x180004024  mov     rcx, rax; ProcessHandle
0x180004027  call    cs:__imp_OpenProcessToken
0x18000402e  nop     dword ptr [rax+rax+00h]
0x180004033  test    eax, eax
0x180004035  jz      loc_180004127
0x18000403b  mov     rcx, [rsp+58h+TokenHandle]; TokenHandle
0x180004040  lea     rax, [rsp+58h+var_28]
0x180004045  mov     r9d, 4; TokenInformationLength
0x18000404b  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x180004050  lea     r8, [rsp+58h+TokenInformation]; TokenInformation
0x180004055  mov     edx, 0Ch; TokenInformationClass
0x18000405a  call    cs:__imp_GetTokenInformation
0x180004061  nop     dword ptr [rax+rax+00h]
0x180004066  test    eax, eax
0x180004068  jz      loc_1800040F3
0x18000406e  cmp     [rsp+58h+TokenInformation], ebx
0x180004072  setz    sil
0x180004076  mov     rcx, [rsp+58h+TokenHandle]; hObject
0x18000407b  test    rcx, rcx
0x18000407e  jz      short loc_18000408C
0x180004080  call    cs:__imp_CloseHandle
0x180004087  nop     dword ptr [rax+rax+00h]
0x18000408c  test    edi, edi
0x18000408e  jns     short loc_1800040D6
0x180004090  lea     r9, aWinstationisse_1; "WinStationIsSessionRemoteable"
0x180004097  mov     r8d, edi
0x18000409a  lea     rdx, aCutilsIscurren; "CUtils::IsCurrentSession failed: 0x%x i"...
0x1800040a1  mov     ecx, 8; int
0x1800040a6  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800040ab  mov     ecx, edi; int
0x1800040ad  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x1800040b2  mov     ecx, eax; dwErrCode
0x1800040b4  call    cs:__imp_SetLastError
0x1800040bb  nop     dword ptr [rax+rax+00h]
0x1800040c0  xor     al, al
0x1800040c2  mov     rbx, [rsp+58h+arg_0]
0x1800040c7  mov     rbp, [rsp+58h+arg_8]
0x1800040cc  add     rsp, 40h
0x1800040d0  pop     r14
0x1800040d2  pop     rdi
0x1800040d3  pop     rsi
0x1800040d4  retn
0x1800040d6  test    esi, esi
0x1800040d8  jnz     short loc_1800040E9
0x1800040da  mov     r8, rbp
0x1800040dd  mov     edx, ebx
0x1800040df  mov     rcx, r14
0x1800040e2  call    InternalIsSessionRemoteable
0x1800040e7  jmp     short loc_1800040C2
0x1800040e9  mov     rcx, rbp
0x1800040ec  call    WinStationIsCurrentSessionRemoteable
0x1800040f1  jmp     short loc_1800040C2
0x1800040f3  call    cs:__imp_GetLastError
0x1800040fa  nop     dword ptr [rax+rax+00h]
0x1800040ff  mov     edi, eax
0x180004101  test    eax, eax
0x180004103  jle     short loc_18000410E
0x180004105  movzx   edi, ax
0x180004108  or      edi, 80070000h
0x18000410e  mov     r8d, edi
0x180004111  lea     rdx, aGettokeninform_0; "GetTokenInformation failed: 0x%x"
0x180004118  mov     ecx, 8; int
0x18000411d  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180004122  jmp     loc_180004076
0x180004127  call    cs:__imp_GetLastError
0x18000412e  nop     dword ptr [rax+rax+00h]
0x180004133  mov     edi, eax
0x180004135  test    eax, eax
0x180004137  jle     short loc_180004142
0x180004139  movzx   edi, ax
0x18000413c  or      edi, 80070000h
0x180004142  mov     r8d, edi
0x180004145  lea     rdx, aOpenprocesstok_0; "OpenProcessToken failed: 0x%x"
0x18000414c  mov     ecx, 8; int
0x180004151  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180004156  jmp     loc_180004076
0x18000415b  call    cs:__imp_GetLastError
0x180004162  nop     dword ptr [rax+rax+00h]
0x180004167  mov     edi, eax
0x180004169  test    eax, eax
0x18000416b  jle     short loc_180004176
0x18000416d  movzx   edi, ax
0x180004170  or      edi, 80070000h
0x180004176  mov     r8d, edi
0x180004179  lea     rdx, aOpenthreadtoke; "OpenThreadToken failed: 0x%x"
0x180004180  mov     ecx, 8; int
0x180004185  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000418a  jmp     loc_180004076
```
