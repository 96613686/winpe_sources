# WdcStopService(ushort const *)

- ea: `0x18002f8cc`
- end: `0x18002faf5`
- name: `?WdcStopService@@YAJPEBG@Z`
- size: `553`
- prototype: `__int64 __fastcall(LPCWSTR lpServiceName)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18007b710`
- `0x18007c3f4`

## callees

- `0x18000b854`
- `0x18002f8cc`
- `0x18003a3c0`

## import_xrefs

- `ADVAPI32!OpenSCManagerW` at `0x18002f8fc`
- `ADVAPI32!OpenSCManagerW` at `0x18002f8fc`
- `ADVAPI32!OpenServiceW` at `0x18002f936`
- `ADVAPI32!OpenServiceW` at `0x18002f936`
- `ADVAPI32!CloseServiceHandle` at `0x18002fac9`
- `ADVAPI32!CloseServiceHandle` at `0x18002fad7`
- `ADVAPI32!CloseServiceHandle` at `0x18002fac9`
- `ADVAPI32!CloseServiceHandle` at `0x18002fad7`
- `ADVAPI32!ControlService` at `0x18002f974`
- `ADVAPI32!ControlService` at `0x18002f974`
- `KERNEL32!GetLastError` at `0x18002f913`
- `KERNEL32!GetLastError` at `0x18002f948`
- `KERNEL32!GetLastError` at `0x18002f9be`
- `KERNEL32!GetLastError` at `0x18002fa3b`
- `KERNEL32!GetLastError` at `0x18002fa80`
- `KERNEL32!GetLastError` at `0x18002f913`
- `KERNEL32!GetLastError` at `0x18002f948`
- `KERNEL32!GetLastError` at `0x18002f9be`
- `KERNEL32!GetLastError` at `0x18002fa3b`
- `KERNEL32!GetLastError` at `0x18002fa80`

## string_xrefs

- `0x18002f99c`: `WdcStopService`
- `0x18002f9ee`: `WdcStopService`
- `0x18002fa19`: `WdcStopService`
- `0x18002fa6b`: `WdcStopService`
- `0x18002faae`: `WdcStopService`

## pseudocode

```c
__int64 __fastcall WdcStopService(LPCWSTR lpServiceName)
{
  SC_HANDLE v2; // rax
  SC_HANDLE v3; // rsi
  signed int LastError; // eax
  signed int v5; // ebx
  SC_HANDLE v6; // rax
  SC_HANDLE v7; // rdi
  signed int v8; // eax
  signed int v9; // eax
  signed int v10; // eax
  signed int v11; // eax
  _SERVICE_STATUS ServiceStatus; // [rsp+30h] [rbp-58h] BYREF

  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  v2 = OpenSCManagerW(0, 0, 1u);
  v3 = v2;
  if ( !v2 )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      if ( v5 >= 0 )
        goto LABEL_6;
    }
    else
    {
      v5 = -2147467259;
    }
    WdcDebugMessage("base\\diagnosis\\pdui\\perfmon\\mon\\listview.cpp", "WdcStopService", 0, L"FAILURE: 0x%08x", v5);
    return (unsigned int)v5;
  }
  if ( v2 != (SC_HANDLE)-1LL )
    goto LABEL_6;
  v9 = GetLastError();
  v5 = v9;
  if ( !v9 )
  {
    v5 = -2147467259;
LABEL_22:
    WdcDebugMessage("base\\diagnosis\\pdui\\perfmon\\mon\\listview.cpp", "WdcStopService", 0, L"FAILURE: 0x%08x", v5);
LABEL_43:
    CloseServiceHandle(v3);
    return (unsigned int)v5;
  }
  if ( v9 > 0 )
    v5 = (unsigned __int16)v9 | 0x80070000;
  if ( v5 < 0 )
    goto LABEL_22;
LABEL_6:
  v6 = OpenServiceW(v3, lpServiceName, 0x20u);
  v7 = v6;
  if ( !v6 )
  {
    v8 = GetLastError();
    v5 = v8;
    if ( v8 )
    {
      if ( v8 > 0 )
        v5 = (unsigned __int16)v8 | 0x80070000;
      if ( v5 >= 0 )
        goto LABEL_11;
    }
    else
    {
      v5 = -2147467259;
    }
    WdcDebugMessage("base\\diagnosis\\pdui\\perfmon\\mon\\listview.cpp", "WdcStopService", 0, L"FAILURE: 0x%08x", v5);
    goto LABEL_42;
  }
  if ( v6 != (SC_HANDLE)-1LL )
    goto LABEL_11;
  v10 = GetLastError();
  v5 = v10;
  if ( v10 )
  {
    if ( v10 > 0 )
      v5 = (unsigned __int16)v10 | 0x80070000;
    if ( v5 >= 0 )
    {
LABEL_11:
      if ( ControlService(v7, 1u, &ServiceStatus) )
      {
        v5 = 0;
        goto LABEL_40;
      }
      v11 = GetLastError();
      v5 = v11;
      if ( v11 )
      {
        if ( v11 > 0 )
          v5 = (unsigned __int16)v11 | 0x80070000;
        if ( v5 >= 0 )
        {
LABEL_40:
          if ( !v7 )
            goto LABEL_42;
          goto LABEL_41;
        }
      }
      else
      {
        v5 = -2147467259;
      }
      WdcDebugMessage("base\\diagnosis\\pdui\\perfmon\\mon\\listview.cpp", "WdcStopService", 0, L"FAILURE: 0x%08x", v5);
      goto LABEL_40;
    }
  }
  else
  {
    v5 = -2147467259;
  }
  WdcDebugMessage("base\\diagnosis\\pdui\\perfmon\\mon\\listview.cpp", "WdcStopService", 0, L"FAILURE: 0x%08x", v5);
LABEL_41:
  CloseServiceHandle(v7);
LABEL_42:
  if ( v3 )
    goto LABEL_43;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18002f8cc  push    rbx
0x18002f8ce  push    rbp
0x18002f8cf  push    rsi
0x18002f8d0  push    rdi
0x18002f8d1  sub     rsp, 68h
0x18002f8d5  mov     rax, cs:__security_cookie
0x18002f8dc  xor     rax, rsp
0x18002f8df  mov     [rsp+88h+var_38], rax
0x18002f8e4  xorps   xmm0, xmm0
0x18002f8e7  xor     edx, edx; lpDatabaseName
0x18002f8e9  mov     rdi, rcx
0x18002f8ec  xor     ecx, ecx; lpMachineName
0x18002f8ee  movups  xmmword ptr [rsp+88h+ServiceStatus.dwServiceType], xmm0
0x18002f8f3  lea     r8d, [rdx+1]; dwDesiredAccess
0x18002f8f7  movups  xmmword ptr [rsp+88h+ServiceStatus.dwWin32ExitCode], xmm0
0x18002f8fc  call    cs:__imp_OpenSCManagerW
0x18002f902  mov     rsi, rax
0x18002f905  mov     ebp, 80070000h
0x18002f90a  test    rax, rax
0x18002f90d  jnz     loc_18002F9B4
0x18002f913  call    cs:__imp_GetLastError
0x18002f919  mov     ebx, eax
0x18002f91b  test    eax, eax
0x18002f91d  jz      short loc_18002F989
0x18002f91f  jle     short loc_18002F926
0x18002f921  movzx   ebx, ax
0x18002f924  or      ebx, ebp
0x18002f926  test    ebx, ebx
0x18002f928  js      short loc_18002F98E
0x18002f92a  mov     r8d, 20h ; ' '; dwDesiredAccess
0x18002f930  mov     rdx, rdi; lpServiceName
0x18002f933  mov     rcx, rsi; hSCManager
0x18002f936  call    cs:__imp_OpenServiceW
0x18002f93c  mov     rdi, rax
0x18002f93f  test    rax, rax
0x18002f942  jnz     loc_18002FA31
0x18002f948  call    cs:__imp_GetLastError
0x18002f94e  mov     ebx, eax
0x18002f950  test    eax, eax
0x18002f952  jz      loc_18002FA06
0x18002f958  jle     short loc_18002F95F
0x18002f95a  movzx   ebx, ax
0x18002f95d  or      ebx, ebp
0x18002f95f  test    ebx, ebx
0x18002f961  js      loc_18002FA0B
0x18002f967  lea     r8, [rsp+88h+ServiceStatus]; lpServiceStatus
0x18002f96c  mov     edx, 1; dwControl
0x18002f971  mov     rcx, rdi; hService
0x18002f974  call    cs:__imp_ControlService
0x18002f97a  test    eax, eax
0x18002f97c  jz      loc_18002FA80
0x18002f982  xor     ebx, ebx
0x18002f984  jmp     loc_18002FAC1
0x18002f989  mov     ebx, 80004005h
0x18002f98e  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18002f995  mov     [rsp+88h+var_68], ebx
0x18002f999  xor     r8d, r8d; int
0x18002f99c  lea     rdx, aWdcstopservice; "WdcStopService"
0x18002f9a3  lea     rcx, aBaseDiagnosisP_29; "base\\diagnosis\\pdui\\perfmon\\mon\\li"...
0x18002f9aa  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18002f9af  jmp     loc_18002FADD
0x18002f9b4  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18002f9b8  jnz     loc_18002F92A
0x18002f9be  call    cs:__imp_GetLastError
0x18002f9c4  mov     ebx, eax
0x18002f9c6  test    eax, eax
0x18002f9c8  jz      short loc_18002F9DB
0x18002f9ca  jle     short loc_18002F9D1
0x18002f9cc  movzx   ebx, ax
0x18002f9cf  or      ebx, ebp
0x18002f9d1  test    ebx, ebx
0x18002f9d3  jns     loc_18002F92A
0x18002f9d9  jmp     short loc_18002F9E0
0x18002f9db  mov     ebx, 80004005h
0x18002f9e0  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18002f9e7  mov     [rsp+88h+var_68], ebx
0x18002f9eb  xor     r8d, r8d; int
0x18002f9ee  lea     rdx, aWdcstopservice; "WdcStopService"
0x18002f9f5  lea     rcx, aBaseDiagnosisP_29; "base\\diagnosis\\pdui\\perfmon\\mon\\li"...
0x18002f9fc  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18002fa01  jmp     loc_18002FAD4
0x18002fa06  mov     ebx, 80004005h
0x18002fa0b  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18002fa12  mov     [rsp+88h+var_68], ebx
0x18002fa16  xor     r8d, r8d; int
0x18002fa19  lea     rdx, aWdcstopservice; "WdcStopService"
0x18002fa20  lea     rcx, aBaseDiagnosisP_29; "base\\diagnosis\\pdui\\perfmon\\mon\\li"...
0x18002fa27  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18002fa2c  jmp     loc_18002FACF
0x18002fa31  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18002fa35  jnz     loc_18002F967
0x18002fa3b  call    cs:__imp_GetLastError
0x18002fa41  mov     ebx, eax
0x18002fa43  test    eax, eax
0x18002fa45  jz      short loc_18002FA58
0x18002fa47  jle     short loc_18002FA4E
0x18002fa49  movzx   ebx, ax
0x18002fa4c  or      ebx, ebp
0x18002fa4e  test    ebx, ebx
0x18002fa50  jns     loc_18002F967
0x18002fa56  jmp     short loc_18002FA5D
0x18002fa58  mov     ebx, 80004005h
0x18002fa5d  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18002fa64  mov     [rsp+88h+var_68], ebx
0x18002fa68  xor     r8d, r8d; int
0x18002fa6b  lea     rdx, aWdcstopservice; "WdcStopService"
0x18002fa72  lea     rcx, aBaseDiagnosisP_29; "base\\diagnosis\\pdui\\perfmon\\mon\\li"...
0x18002fa79  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18002fa7e  jmp     short loc_18002FAC6
0x18002fa80  call    cs:__imp_GetLastError
0x18002fa86  mov     ebx, eax
0x18002fa88  test    eax, eax
0x18002fa8a  jz      short loc_18002FA99
0x18002fa8c  jle     short loc_18002FA93
0x18002fa8e  movzx   ebx, ax
0x18002fa91  or      ebx, ebp
0x18002fa93  test    ebx, ebx
0x18002fa95  jns     short loc_18002FAC1
0x18002fa97  jmp     short loc_18002FA9E
0x18002fa99  mov     ebx, 80004005h
0x18002fa9e  mov     eax, ebx
0x18002faa0  mov     [rsp+88h+var_68], ebx
0x18002faa4  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18002faab  xor     r8d, r8d; int
0x18002faae  lea     rdx, aWdcstopservice; "WdcStopService"
0x18002fab5  lea     rcx, aBaseDiagnosisP_29; "base\\diagnosis\\pdui\\perfmon\\mon\\li"...
0x18002fabc  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18002fac1  test    rdi, rdi
0x18002fac4  jz      short loc_18002FACF
0x18002fac6  mov     rcx, rdi; hSCObject
0x18002fac9  call    cs:__imp_CloseServiceHandle
0x18002facf  test    rsi, rsi
0x18002fad2  jz      short loc_18002FADD
0x18002fad4  mov     rcx, rsi; hSCObject
0x18002fad7  call    cs:__imp_CloseServiceHandle
0x18002fadd  mov     eax, ebx
0x18002fadf  mov     rcx, [rsp+88h+var_38]
0x18002fae4  xor     rcx, rsp; StackCookie
0x18002fae7  call    __security_check_cookie
0x18002faec  add     rsp, 68h
0x18002faf0  pop     rdi
0x18002faf1  pop     rsi
0x18002faf2  pop     rbp
0x18002faf3  pop     rbx
0x18002faf4  retn
```
