# InitClientUserString(ushort *)

- ea: `0x1800210c0`
- end: `0x18002130d`
- name: `?InitClientUserString@@YAKPEAG@Z`
- size: `589`
- prototype: `unsigned int __fastcall(unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001fb30`
- `0x18001fd20`

## callees

- `0x1800210c0`
- `0x1800a1d10`
- `0x1800d06a4`
- `0x1800db6b0`
- `0x1800db704`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180021155`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180021155`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180021224`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180021224`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180021128`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180021128`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002110f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002110f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180021237`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180021237`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021207`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021245`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002128b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021207`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021245`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002128b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800211ae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800211ae`
- `ntdll!RtlConvertSidToUnicodeString` at `0x18002117d`
- `ntdll!RtlConvertSidToUnicodeString` at `0x18002117d`
- `ntdll!RtlNtStatusToDosError` at `0x1800212e2`
- `ntdll!RtlNtStatusToDosError` at `0x1800212e2`

## pseudocode

```c
__int64 __fastcall InitClientUserString(unsigned __int16 *a1)
{
  HANDLE CurrentThread; // rax
  NTSTATUS v3; // eax
  NTSTATUS v4; // ebx
  ULONG v5; // ebx
  DWORD v7; // eax
  HANDLE CurrentProcess; // rax
  DWORD LastError; // eax
  PDWORD ReturnLength; // [rsp+20h] [rbp-A8h]
  void *TokenHandle; // [rsp+30h] [rbp-98h] BYREF
  _UNICODE_STRING UnicodeString; // [rsp+38h] [rbp-90h] BYREF
  DWORD v13; // [rsp+48h] [rbp-80h] BYREF
  PSID TokenInformation[12]; // [rsp+50h] [rbp-78h] BYREF

  TokenHandle = 0;
  v13 = 0;
  UnicodeString = 0;
  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_q(1029, 19, WPP_e24404dfc44e30604b090ca3bc8bd519_Traceguids);
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0x20008u, 1, &TokenHandle) )
  {
LABEL_4:
    if ( GetTokenInformation(TokenHandle, TokenUser, TokenInformation, 0x58u, &v13) )
    {
      *(_DWORD *)&UnicodeString.Length = 0x1000000;
      UnicodeString.Buffer = a1;
      v3 = RtlConvertSidToUnicodeString(&UnicodeString, TokenInformation[0], 0);
      v4 = v3;
      if ( v3 < 0 )
      {
        if ( (xmmword_180107A60 & 0x20) != 0 )
          WPP_SF_d(1029, 22, WPP_e24404dfc44e30604b090ca3bc8bd519_Traceguids, (unsigned int)v3, ReturnLength);
        v5 = RtlNtStatusToDosError(v4);
      }
      else
      {
        v5 = 0;
        if ( (xmmword_180107A60 & 0x20) != 0 )
          WPP_SF_S(1029, 23, WPP_e24404dfc44e30604b090ca3bc8bd519_Traceguids, a1);
      }
    }
    else
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( (xmmword_180107A60 & 0x20) != 0 )
        WPP_SF_d(1029, 21, WPP_e24404dfc44e30604b090ca3bc8bd519_Traceguids, LastError, ReturnLength);
    }
    goto LABEL_8;
  }
  v7 = GetLastError();
  v5 = v7;
  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_d(1029, 20, WPP_e24404dfc44e30604b090ca3bc8bd519_Traceguids, v7, ReturnLength);
  if ( v5 == 1008 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 0x20008u, &TokenHandle) )
    {
      v5 = GetLastError();
      goto LABEL_8;
    }
    goto LABEL_4;
  }
LABEL_8:
  if ( TokenHandle )
  {
    CloseHandle(TokenHandle);
    TokenHandle = 0;
  }
  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_d(1029, 24, WPP_e24404dfc44e30604b090ca3bc8bd519_Traceguids, v5, ReturnLength);
  return v5;
}

```

## disassembly

```asm
0x1800210c0  mov     r11, rsp
0x1800210c3  sub     rsp, 0C8h
0x1800210ca  mov     rax, cs:__security_cookie
0x1800210d1  xor     rax, rsp
0x1800210d4  mov     [rsp+0C8h+var_18], rax
0x1800210dc  mov     [r11+18h], rsi
0x1800210e0  xorps   xmm0, xmm0
0x1800210e3  xor     esi, esi
0x1800210e5  mov     [r11-8], rdi
0x1800210e9  mov     [rsp+0C8h+TokenHandle], rsi
0x1800210ee  mov     rdi, rcx
0x1800210f1  mov     [rsp+0C8h+var_80], esi
0x1800210f5  movups  xmmword ptr [rsp+0C8h+UnicodeString.Length], xmm0
0x1800210fa  test    byte ptr cs:xmmword_180107A60, 20h
0x180021101  jnz     loc_180021252
0x180021107  mov     [rsp+0C8h+arg_8], rbx
0x18002110f  call    cs:__imp_GetCurrentThread
0x180021115  lea     r9, [rsp+0C8h+TokenHandle]; TokenHandle
0x18002111a  mov     edx, 20008h; DesiredAccess
0x18002111f  mov     rcx, rax; ThreadHandle
0x180021122  mov     r8d, 1; OpenAsSelf
0x180021128  call    cs:__imp_OpenThreadToken
0x18002112e  test    eax, eax
0x180021130  jz      loc_180021207
0x180021136  mov     rcx, [rsp+0C8h+TokenHandle]; TokenHandle
0x18002113b  lea     rax, [rsp+0C8h+var_80]
0x180021140  mov     r9d, 58h ; 'X'; TokenInformationLength
0x180021146  mov     [rsp+0C8h+ReturnLength], rax; ReturnLength
0x18002114b  lea     r8, [rsp+0C8h+TokenInformation]; TokenInformation
0x180021150  mov     edx, 1; TokenInformationClass
0x180021155  call    cs:__imp_GetTokenInformation
0x18002115b  test    eax, eax
0x18002115d  jz      loc_18002128B
0x180021163  mov     rdx, [rsp+0C8h+TokenInformation]; Sid
0x180021168  lea     rcx, [rsp+0C8h+UnicodeString]; UnicodeString
0x18002116d  xor     r8d, r8d; AllocateDestinationString
0x180021170  mov     dword ptr [rsp+0C8h+UnicodeString.Length], 1000000h
0x180021178  mov     [rsp+0C8h+UnicodeString.Buffer], rdi
0x18002117d  call    cs:__imp_RtlConvertSidToUnicodeString
0x180021183  mov     ebx, eax
0x180021185  test    eax, eax
0x180021187  js      loc_1800212BE
0x18002118d  test    byte ptr cs:xmmword_180107A60, 20h
0x180021194  mov     ebx, esi
0x180021196  jnz     loc_1800212EF
0x18002119c  mov     rcx, [rsp+0C8h+TokenHandle]; hObject
0x1800211a1  mov     rdi, [rsp+0C8h+var_8]
0x1800211a9  test    rcx, rcx
0x1800211ac  jz      short loc_1800211B9
0x1800211ae  call    cs:__imp_CloseHandle
0x1800211b4  mov     [rsp+0C8h+TokenHandle], rsi
0x1800211b9  test    byte ptr cs:xmmword_180107A60, 20h
0x1800211c0  mov     rsi, [rsp+0C8h+arg_10]
0x1800211c8  jnz     short loc_1800211EC
0x1800211ca  mov     eax, ebx
0x1800211cc  mov     rbx, [rsp+0C8h+arg_8]
0x1800211d4  mov     rcx, [rsp+0C8h+var_18]
0x1800211dc  xor     rcx, rsp; StackCookie
0x1800211df  call    __security_check_cookie
0x1800211e4  add     rsp, 0C8h
0x1800211eb  retn
0x1800211ec  mov     edx, 18h
0x1800211f1  lea     r8, WPP_e24404dfc44e30604b090ca3bc8bd519_Traceguids
0x1800211f8  mov     ecx, 405h
0x1800211fd  mov     r9d, ebx
0x180021200  call    WPP_SF_d
0x180021205  jmp     short loc_1800211CA
0x180021207  call    cs:__imp_GetLastError
0x18002120d  mov     ebx, eax
0x18002120f  test    byte ptr cs:xmmword_180107A60, 20h
0x180021216  jnz     short loc_180021270
0x180021218  cmp     ebx, 3F0h
0x18002121e  jnz     loc_18002119C
0x180021224  call    cs:__imp_GetCurrentProcess
0x18002122a  lea     r8, [rsp+0C8h+TokenHandle]; TokenHandle
0x18002122f  mov     edx, 20008h; DesiredAccess
0x180021234  mov     rcx, rax; ProcessHandle
0x180021237  call    cs:__imp_OpenProcessToken
0x18002123d  test    eax, eax
0x18002123f  jnz     loc_180021136
0x180021245  call    cs:__imp_GetLastError
0x18002124b  mov     ebx, eax
0x18002124d  jmp     loc_18002119C
0x180021252  mov     edx, 13h
0x180021257  lea     r8, WPP_e24404dfc44e30604b090ca3bc8bd519_Traceguids
0x18002125e  mov     ecx, 405h
0x180021263  mov     r9, rdi
0x180021266  call    WPP_SF_q
0x18002126b  jmp     loc_180021107
0x180021270  mov     edx, 14h
0x180021275  lea     r8, WPP_e24404dfc44e30604b090ca3bc8bd519_Traceguids
0x18002127c  mov     ecx, 405h
0x180021281  mov     r9d, ebx
0x180021284  call    WPP_SF_d
0x180021289  jmp     short loc_180021218
0x18002128b  call    cs:__imp_GetLastError
0x180021291  mov     ebx, eax
0x180021293  test    byte ptr cs:xmmword_180107A60, 20h
0x18002129a  jz      loc_18002119C
0x1800212a0  mov     edx, 15h
0x1800212a5  lea     r8, WPP_e24404dfc44e30604b090ca3bc8bd519_Traceguids
0x1800212ac  mov     ecx, 405h
0x1800212b1  mov     r9d, eax
0x1800212b4  call    WPP_SF_d
0x1800212b9  jmp     loc_18002119C
0x1800212be  test    byte ptr cs:xmmword_180107A60, 20h
0x1800212c5  jz      short loc_1800212E0
0x1800212c7  mov     edx, 16h
0x1800212cc  lea     r8, WPP_e24404dfc44e30604b090ca3bc8bd519_Traceguids
0x1800212d3  mov     ecx, 405h
0x1800212d8  mov     r9d, ebx
0x1800212db  call    WPP_SF_d
0x1800212e0  mov     ecx, ebx; Status
0x1800212e2  call    cs:__imp_RtlNtStatusToDosError
0x1800212e8  mov     ebx, eax
0x1800212ea  jmp     loc_18002119C
0x1800212ef  mov     edx, 17h
0x1800212f4  lea     r8, WPP_e24404dfc44e30604b090ca3bc8bd519_Traceguids
0x1800212fb  mov     ecx, 405h
0x180021300  mov     r9, rdi
0x180021303  call    WPP_SF_S
0x180021308  jmp     loc_18002119C
```
