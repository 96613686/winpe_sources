# _StartAutoProxyService

- ea: `0x180014954`
- end: `0x180014c71`
- name: `_StartAutoProxyService`
- size: `797`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1800148a4`

## callees

- `0x180014954`
- `0x180015aa0`
- `0x18002a910`
- `0x1800838bc`
- `0x1800a1d10`
- `0x1800cf008`
- `0x1800db6b0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180014a92`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180014a92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014aa0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014b14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014b40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014b6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014bb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014aa0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014b14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014b40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014b6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014bb8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014a8a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014a8a`
- `api-ms-win-service-private-l1-1-0!WaitServiceState` at `0x180014c0a`
- `api-ms-win-service-private-l1-1-0!WaitServiceState` at `0x180014c0a`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800149c4`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800149c4`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180014a04`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180014a48`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180014a04`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180014a48`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800149ed`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800149ed`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180014b06`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180014b06`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180014a1a`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180014a1a`

## pseudocode

```c
__int64 __fastcall StartAutoProxyService(unsigned int a1)
{
  unsigned int v1; // ebx
  unsigned int LastError; // eax
  SC_HANDLE v4; // rbp
  SC_HANDLE v5; // rax
  SC_HANDLE v6; // r15
  SC_HANDLE v7; // rax
  __int64 v9; // rdx
  __int64 v10; // rdx
  __int64 v11; // r9
  DWORD v12; // eax
  DWORD v13; // eax
  DWORD v14; // eax
  DWORD v15; // eax
  unsigned int v16; // r15d
  char v17; // al
  HANDLE hObject; // [rsp+20h] [rbp-48h] BYREF
  _SERVICE_STATUS ServiceStatus; // [rsp+28h] [rbp-40h] BYREF

  v1 = 0;
  hObject = 0;
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  if ( g_fIsAPSvcAvailable )
    return v1;
  LastError = CaptureImpersonationToken(&hObject);
  v1 = LastError;
  if ( !LastError )
  {
    if ( hObject && !RevertToSelf() )
    {
      LastError = GetLastError();
      v1 = LastError;
      if ( (xmmword_180107A50 & 2) == 0 )
        goto LABEL_15;
      v9 = 16;
      goto LABEL_21;
    }
    v4 = 0;
    v5 = OpenSCManagerW(0, 0, 1u);
    v6 = v5;
    if ( v5 )
    {
      v7 = OpenServiceW(v5, L"WinHttpAutoProxySvc", 0x94u);
      if ( v7 )
      {
        v1 = 0;
        v4 = v7;
      }
      else
      {
        v14 = GetLastError();
        v1 = v14;
        if ( (xmmword_180107A50 & 2) != 0 )
          WPP_SF_d(513, 14, WPP_d20135cef7e33325d83cff35dd261285_Traceguids, v14, hObject);
      }
      CloseServiceHandle(v6);
    }
    else
    {
      v13 = GetLastError();
      v1 = v13;
      if ( (xmmword_180107A50 & 2) != 0 )
        WPP_SF_d(513, 13, WPP_d20135cef7e33325d83cff35dd261285_Traceguids, v13, hObject);
    }
    if ( v1 )
    {
      if ( (xmmword_180107A50 & 2) == 0 )
        goto LABEL_13;
      v10 = 17;
      v11 = v1;
    }
    else
    {
      if ( QueryServiceStatus(v4, &ServiceStatus) )
      {
        if ( ServiceStatus.dwCurrentState == 4 )
        {
          if ( (xmmword_180107A60 & 2) != 0 )
            WPP_SF_(1025, 19, WPP_d20135cef7e33325d83cff35dd261285_Traceguids);
        }
        else
        {
          if ( ServiceStatus.dwCurrentState == 2 )
            goto LABEL_40;
          if ( (xmmword_180107A60 & 2) != 0 )
            WPP_SF_(1025, 20, WPP_d20135cef7e33325d83cff35dd261285_Traceguids);
          if ( StartServiceW(v4, 0, 0) )
          {
LABEL_40:
            v16 = WaitServiceState(v4, 9, a1);
            v17 = xmmword_180107A50;
            if ( (xmmword_180107A50 & 2) != 0 )
            {
              WPP_SF_d(513, 21, WPP_d20135cef7e33325d83cff35dd261285_Traceguids, v16, hObject);
              v17 = xmmword_180107A50;
            }
            if ( v16 == 4 )
            {
              v1 = 0;
              UpdateAutoProxyServiceTimeStamp();
            }
            else
            {
              v1 = 12178;
              if ( (v17 & 2) != 0 )
                WPP_SF_d(513, 22, WPP_d20135cef7e33325d83cff35dd261285_Traceguids, v16, hObject);
            }
          }
          else
          {
            v12 = GetLastError();
            v1 = 0;
            if ( v12 != 1056 )
              v1 = v12;
          }
        }
        goto LABEL_13;
      }
      v15 = GetLastError();
      v1 = v15;
      if ( (xmmword_180107A50 & 2) == 0 )
      {
LABEL_13:
        if ( v4 )
          CloseServiceHandle(v4);
        goto LABEL_15;
      }
      v10 = 18;
      v11 = v15;
    }
    WPP_SF_d(513, v10, WPP_d20135cef7e33325d83cff35dd261285_Traceguids, v11, hObject);
    goto LABEL_13;
  }
  if ( (xmmword_180107A50 & 2) != 0 )
  {
    v9 = 15;
LABEL_21:
    WPP_SF_d(513, v9, WPP_d20135cef7e33325d83cff35dd261285_Traceguids, LastError, hObject);
  }
LABEL_15:
  if ( hObject )
  {
    Impersonate(hObject);
    CloseHandle(hObject);
  }
  return v1;
}

```

## disassembly

```asm
0x180014954  mov     r11, rsp
0x180014957  mov     [r11+10h], rbx
0x18001495b  mov     [r11+18h], rbp
0x18001495f  push    rdi
0x180014960  push    r12
0x180014962  push    r15
0x180014964  sub     rsp, 50h
0x180014968  mov     rax, cs:__security_cookie
0x18001496f  xor     rax, rsp
0x180014972  mov     [rsp+68h+var_20], rax
0x180014977  xorps   xmm0, xmm0
0x18001497a  xor     eax, eax
0x18001497c  xor     ebx, ebx
0x18001497e  mov     [r11-48h], rax
0x180014982  cmp     cs:?g_fIsAPSvcAvailable@@3HA, eax; int g_fIsAPSvcAvailable
0x180014988  mov     r12d, ecx
0x18001498b  movups  xmmword ptr [rsp+68h+ServiceStatus.dwServiceType], xmm0
0x180014990  movups  xmmword ptr [rsp+68h+ServiceStatus.dwWin32ExitCode], xmm0
0x180014995  jnz     loc_180014A56
0x18001499b  lea     rcx, [r11-48h]; void **
0x18001499f  call    ?CaptureImpersonationToken@@YAKPEAPEAX@Z; CaptureImpersonationToken(void * *)
0x1800149a4  mov     ebx, eax
0x1800149a6  test    eax, eax
0x1800149a8  jnz     loc_180014B29
0x1800149ae  cmp     [rsp+68h+hObject], 0
0x1800149b4  jnz     loc_180014A92
0x1800149ba  xor     ebp, ebp
0x1800149bc  xor     edx, edx; lpDatabaseName
0x1800149be  xor     ecx, ecx; lpMachineName
0x1800149c0  lea     r8d, [rbp+1]; dwDesiredAccess
0x1800149c4  call    cs:__imp_OpenSCManagerW
0x1800149ca  lea     rdi, WPP_d20135cef7e33325d83cff35dd261285_Traceguids
0x1800149d1  mov     r15, rax
0x1800149d4  test    rax, rax
0x1800149d7  jz      loc_180014B40
0x1800149dd  mov     r8d, 94h; dwDesiredAccess
0x1800149e3  lea     rdx, ServiceName; "WinHttpAutoProxySvc"
0x1800149ea  mov     rcx, rax; hSCManager
0x1800149ed  call    cs:__imp_OpenServiceW
0x1800149f3  test    rax, rax
0x1800149f6  jz      loc_180014B6F
0x1800149fc  xor     ebx, ebx
0x1800149fe  mov     rbp, rax
0x180014a01  mov     rcx, r15; hSCObject
0x180014a04  call    cs:__imp_CloseServiceHandle
0x180014a0a  test    ebx, ebx
0x180014a0c  jnz     loc_180014ACC
0x180014a12  lea     rdx, [rsp+68h+ServiceStatus]; lpServiceStatus
0x180014a17  mov     rcx, rbp; hService
0x180014a1a  call    cs:__imp_QueryServiceStatus
0x180014a20  test    eax, eax
0x180014a22  jz      loc_180014BB8
0x180014a28  cmp     [rsp+68h+ServiceStatus.dwCurrentState], 4
0x180014a2d  jnz     loc_180014AE6
0x180014a33  test    byte ptr cs:xmmword_180107A60, 2
0x180014a3a  jnz     loc_180014BCF
0x180014a40  test    rbp, rbp
0x180014a43  jz      short loc_180014A4E
0x180014a45  mov     rcx, rbp; hSCObject
0x180014a48  call    cs:__imp_CloseServiceHandle
0x180014a4e  cmp     [rsp+68h+hObject], 0
0x180014a54  jnz     short loc_180014A7B
0x180014a56  mov     eax, ebx
0x180014a58  mov     rcx, [rsp+68h+var_20]
0x180014a5d  xor     rcx, rsp; StackCookie
0x180014a60  call    __security_check_cookie
0x180014a65  lea     r11, [rsp+68h+var_18]
0x180014a6a  mov     rbx, [r11+28h]
0x180014a6e  mov     rbp, [r11+30h]
0x180014a72  mov     rsp, r11
0x180014a75  pop     r15
0x180014a77  pop     r12
0x180014a79  pop     rdi
0x180014a7a  retn
0x180014a7b  mov     rcx, [rsp+68h+hObject]; Token
0x180014a80  call    ?Impersonate@@YAHPEAX@Z; Impersonate(void *)
0x180014a85  mov     rcx, [rsp+68h+hObject]; hObject
0x180014a8a  call    cs:__imp_CloseHandle
0x180014a90  jmp     short loc_180014A56
0x180014a92  call    cs:__imp_RevertToSelf
0x180014a98  test    eax, eax
0x180014a9a  jnz     loc_1800149BA
0x180014aa0  call    cs:__imp_GetLastError
0x180014aa6  mov     ebx, eax
0x180014aa8  test    byte ptr cs:xmmword_180107A50, 2
0x180014aaf  jz      short loc_180014A4E
0x180014ab1  mov     edx, 10h
0x180014ab6  mov     ecx, 201h
0x180014abb  lea     r8, WPP_d20135cef7e33325d83cff35dd261285_Traceguids
0x180014ac2  mov     r9d, eax
0x180014ac5  call    WPP_SF_d
0x180014aca  jmp     short loc_180014A4E
0x180014acc  test    byte ptr cs:xmmword_180107A50, 2
0x180014ad3  jz      loc_180014A40
0x180014ad9  mov     edx, 11h
0x180014ade  mov     r9d, ebx
0x180014ae1  jmp     loc_180014BA6
0x180014ae6  cmp     [rsp+68h+ServiceStatus.dwCurrentState], 2
0x180014aeb  jz      loc_180014BFD
0x180014af1  test    byte ptr cs:xmmword_180107A60, 2
0x180014af8  jnz     loc_180014BE6
0x180014afe  xor     r8d, r8d; lpServiceArgVectors
0x180014b01  xor     edx, edx; dwNumServiceArgs
0x180014b03  mov     rcx, rbp; hService
0x180014b06  call    cs:__imp_StartServiceW
0x180014b0c  test    eax, eax
0x180014b0e  jnz     loc_180014BFD
0x180014b14  call    cs:__imp_GetLastError
0x180014b1a  xor     ebx, ebx
0x180014b1c  cmp     eax, 420h
0x180014b21  cmovnz  ebx, eax
0x180014b24  jmp     loc_180014A40
0x180014b29  test    byte ptr cs:xmmword_180107A50, 2
0x180014b30  jz      loc_180014A4E
0x180014b36  mov     edx, 0Fh
0x180014b3b  jmp     loc_180014AB6
0x180014b40  call    cs:__imp_GetLastError
0x180014b46  mov     ebx, eax
0x180014b48  test    byte ptr cs:xmmword_180107A50, 2
0x180014b4f  jz      loc_180014A0A
0x180014b55  mov     edx, 0Dh
0x180014b5a  mov     ecx, 201h
0x180014b5f  mov     r9d, eax
0x180014b62  mov     r8, rdi
0x180014b65  call    WPP_SF_d
0x180014b6a  jmp     loc_180014A0A
0x180014b6f  call    cs:__imp_GetLastError
0x180014b75  mov     ebx, eax
0x180014b77  test    byte ptr cs:xmmword_180107A50, 2
0x180014b7e  jz      loc_180014A01
0x180014b84  mov     edx, 0Eh
0x180014b89  mov     ecx, 201h
0x180014b8e  mov     r9d, eax
0x180014b91  mov     r8, rdi
0x180014b94  call    WPP_SF_d
0x180014b99  jmp     loc_180014A01
0x180014b9e  mov     edx, 12h
0x180014ba3  mov     r9d, eax
0x180014ba6  mov     ecx, 201h
0x180014bab  mov     r8, rdi
0x180014bae  call    WPP_SF_d
0x180014bb3  jmp     loc_180014A40
0x180014bb8  call    cs:__imp_GetLastError
0x180014bbe  mov     ebx, eax
0x180014bc0  test    byte ptr cs:xmmword_180107A50, 2
0x180014bc7  jz      loc_180014A40
0x180014bcd  jmp     short loc_180014B9E
0x180014bcf  mov     edx, 13h
0x180014bd4  mov     ecx, 401h
0x180014bd9  mov     r8, rdi
0x180014bdc  call    WPP_SF_
0x180014be1  jmp     loc_180014A40
0x180014be6  mov     edx, 14h
0x180014beb  mov     ecx, 401h
0x180014bf0  mov     r8, rdi
0x180014bf3  call    WPP_SF_
0x180014bf8  jmp     loc_180014AFE
0x180014bfd  xor     r9d, r9d
0x180014c00  mov     r8d, r12d
0x180014c03  mov     rcx, rbp
0x180014c06  lea     edx, [r9+9]
0x180014c0a  call    cs:__imp_WaitServiceState
0x180014c10  mov     r15d, eax
0x180014c13  mov     al, byte ptr cs:xmmword_180107A50
0x180014c19  test    al, 2
0x180014c1b  jz      short loc_180014C38
0x180014c1d  mov     edx, 15h
0x180014c22  mov     ecx, 201h
0x180014c27  mov     r9d, r15d
0x180014c2a  mov     r8, rdi
0x180014c2d  call    WPP_SF_d
0x180014c32  mov     al, byte ptr cs:xmmword_180107A50
0x180014c38  cmp     r15d, 4
0x180014c3c  jnz     short loc_180014C4A
0x180014c3e  xor     ebx, ebx
0x180014c40  call    ?UpdateAutoProxyServiceTimeStamp@@YAXXZ; UpdateAutoProxyServiceTimeStamp(void)
0x180014c45  jmp     loc_180014A40
0x180014c4a  mov     ebx, 2F92h
0x180014c4f  test    al, 2
0x180014c51  jz      loc_180014A40
0x180014c57  mov     edx, 16h
0x180014c5c  mov     ecx, 201h
0x180014c61  mov     r9d, r15d
0x180014c64  mov     r8, rdi
0x180014c67  call    WPP_SF_d
0x180014c6c  jmp     loc_180014A40
```
