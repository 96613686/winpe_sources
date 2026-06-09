# ATL::CAtlServiceModuleT<CBlbServiceModule,102>::Uninstall(void)

- ea: `0x140067bf8`
- end: `0x140067de7`
- name: `?Uninstall@?$CAtlServiceModuleT@VCBlbServiceModule@@$0GG@@ATL@@QEAAHXZ`
- size: `495`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, service_task, installer_update`

## callers

- `0x140067e60`

## callees

- `0x1400088f0`
- `0x1400606fc`
- `0x140063438`
- `0x140067bf8`
- `0x140134d20`
- `0x140134de0`

## import_xrefs

- `ADVAPI32!OpenSCManagerW` at `0x140067c3c`
- `ADVAPI32!OpenSCManagerW` at `0x140067c3c`
- `ADVAPI32!CloseServiceHandle` at `0x140067cba`
- `ADVAPI32!CloseServiceHandle` at `0x140067d71`
- `ADVAPI32!CloseServiceHandle` at `0x140067d7a`
- `ADVAPI32!CloseServiceHandle` at `0x140067cba`
- `ADVAPI32!CloseServiceHandle` at `0x140067d71`
- `ADVAPI32!CloseServiceHandle` at `0x140067d7a`
- `ADVAPI32!OpenServiceW` at `0x140067ca9`
- `ADVAPI32!OpenServiceW` at `0x140067ca9`
- `ADVAPI32!ControlService` at `0x140067cf6`
- `ADVAPI32!ControlService` at `0x140067cf6`
- `ADVAPI32!DeleteService` at `0x140067d66`
- `ADVAPI32!DeleteService` at `0x140067d66`
- `KERNEL32!GetLastError` at `0x140067d00`
- `KERNEL32!GetLastError` at `0x140067d00`
- `USER32!MessageBoxW` at `0x140067c8c`
- `USER32!MessageBoxW` at `0x140067d5d`
- `USER32!MessageBoxW` at `0x140067c8c`
- `USER32!MessageBoxW` at `0x140067d5d`
- `msvcrt!wcscpy_s` at `0x140067c6e`
- `msvcrt!wcscpy_s` at `0x140067d3f`
- `msvcrt!wcscpy_s` at `0x140067dac`
- `msvcrt!wcscpy_s` at `0x140067c6e`
- `msvcrt!wcscpy_s` at `0x140067d3f`
- `msvcrt!wcscpy_s` at `0x140067dac`

## string_xrefs

- `0x140067c5d`: `Could not open Service Manager`
- `0x140067cd3`: `Could not open service`
- `0x140067d2e`: `Could not stop service`
- `0x140067d99`: `Could not delete service`

## pseudocode

```c
__int64 ATL::CAtlServiceModuleT<CBlbServiceModule,102>::Uninstall()
{
  SC_HANDLE v0; // rax
  int v1; // r8d
  SC_HANDLE v2; // r14
  const wchar_t *v3; // r8
  errno_t v4; // eax
  wchar_t *v5; // rdx
  SC_HANDLE v7; // rax
  SC_HANDLE v8; // r15
  int v9; // r8d
  DWORD LastError; // eax
  int v11; // r8d
  errno_t v12; // eax
  BOOL v13; // ebx
  int v14; // r8d
  errno_t v15; // eax
  struct _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-E0h] BYREF
  wchar_t Destination[1024]; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t Buffer[1024]; // [rsp+840h] [rbp+740h] BYREF

  if ( (unsigned int)ATL::CAtlServiceModuleT<CBlbServiceModule,102>::IsInstalled() )
  {
    v0 = OpenSCManagerW(0, 0, 0xF003Fu);
    v2 = v0;
    if ( !v0 )
    {
      if ( (unsigned int)ATL::AtlLoadString(0xD80Au, Destination, v1) )
      {
LABEL_6:
        v5 = Destination;
LABEL_7:
        MessageBoxW(0, v5, &Caption, 0);
        return 0;
      }
      v3 = L"Could not open Service Manager";
LABEL_5:
      v4 = wcscpy_s(Destination, 0x400u, v3);
      ATL::AtlCrtErrorCheck(v4);
      goto LABEL_6;
    }
    v7 = OpenServiceW(v0, &Caption, 0x10020u);
    v8 = v7;
    if ( !v7 )
    {
      CloseServiceHandle(v2);
      if ( (unsigned int)ATL::AtlLoadString(0xD80Cu, Destination, v9) )
        goto LABEL_6;
      v3 = L"Could not open service";
      goto LABEL_5;
    }
    memset(&ServiceStatus, 0, sizeof(ServiceStatus));
    if ( !ControlService(v7, 1u, &ServiceStatus) )
    {
      LastError = GetLastError();
      if ( LastError != 1062 && (LastError != 1061 || ServiceStatus.dwCurrentState != 3) )
      {
        if ( !(unsigned int)ATL::AtlLoadString(0xD80Eu, Destination, v11) )
        {
          v12 = wcscpy_s(Destination, 0x400u, L"Could not stop service");
          ATL::AtlCrtErrorCheck(v12);
        }
        MessageBoxW(0, Destination, &Caption, 0);
      }
    }
    v13 = DeleteService(v8);
    CloseServiceHandle(v8);
    CloseServiceHandle(v2);
    if ( !v13 )
    {
      if ( !(unsigned int)ATL::AtlLoadString(0xD80Du, Buffer, v14) )
      {
        v15 = wcscpy_s(Buffer, 0x400u, L"Could not delete service");
        ATL::AtlCrtErrorCheck(v15);
      }
      v5 = Buffer;
      goto LABEL_7;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x140067bf8  push    rbp
0x140067bfa  push    rbx
0x140067bfb  push    r14
0x140067bfd  push    r15
0x140067bff  lea     rbp, [rsp-0F58h]
0x140067c07  mov     eax, 1058h
0x140067c0c  call    _alloca_probe
0x140067c11  sub     rsp, rax
0x140067c14  mov     rax, cs:__security_cookie
0x140067c1b  xor     rax, rsp
0x140067c1e  mov     [rbp+0F70h+var_30], rax
0x140067c25  call    ?IsInstalled@?$CAtlServiceModuleT@VCBlbServiceModule@@$0GG@@ATL@@QEAAHXZ; ATL::CAtlServiceModuleT<CBlbServiceModule,102>::IsInstalled(void)
0x140067c2a  test    eax, eax
0x140067c2c  jz      loc_140067DC5
0x140067c32  xor     edx, edx; lpDatabaseName
0x140067c34  xor     ecx, ecx; lpMachineName
0x140067c36  mov     r8d, 0F003Fh; dwDesiredAccess
0x140067c3c  call    cs:__imp_OpenSCManagerW
0x140067c42  mov     r14, rax
0x140067c45  test    rax, rax
0x140067c48  jnz     short loc_140067C99
0x140067c4a  lea     rdx, [rsp+1070h+Destination]; lpBuffer
0x140067c4f  mov     ecx, 0D80Ah; uID
0x140067c54  call    ?AtlLoadString@ATL@@YAHIPEAGH@Z; ATL::AtlLoadString(uint,ushort *,int)
0x140067c59  test    eax, eax
0x140067c5b  jnz     short loc_140067C7B
0x140067c5d  lea     r8, aCouldNotOpenSe; "Could not open Service Manager"
0x140067c64  mov     edx, 400h; SizeInWords
0x140067c69  lea     rcx, [rsp+1070h+Destination]; Destination
0x140067c6e  call    cs:__imp_wcscpy_s
0x140067c74  mov     ecx, eax; int
0x140067c76  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x140067c7b  lea     rdx, [rsp+1070h+Destination]; lpText
0x140067c80  lea     r8, Caption; lpCaption
0x140067c87  xor     r9d, r9d; uType
0x140067c8a  xor     ecx, ecx; hWnd
0x140067c8c  call    cs:__imp_MessageBoxW
0x140067c92  xor     eax, eax
0x140067c94  jmp     loc_140067DCA
0x140067c99  mov     r8d, 10020h; dwDesiredAccess
0x140067c9f  lea     rdx, Caption; lpServiceName
0x140067ca6  mov     rcx, r14; hSCManager
0x140067ca9  call    cs:__imp_OpenServiceW
0x140067caf  mov     r15, rax
0x140067cb2  test    rax, rax
0x140067cb5  jnz     short loc_140067CDC
0x140067cb7  mov     rcx, r14; hSCObject
0x140067cba  call    cs:__imp_CloseServiceHandle
0x140067cc0  lea     rdx, [rsp+1070h+Destination]; lpBuffer
0x140067cc5  mov     ecx, 0D80Ch; uID
0x140067cca  call    ?AtlLoadString@ATL@@YAHIPEAGH@Z; ATL::AtlLoadString(uint,ushort *,int)
0x140067ccf  test    eax, eax
0x140067cd1  jnz     short loc_140067C7B
0x140067cd3  lea     r8, aCouldNotOpenSe_0; "Could not open service"
0x140067cda  jmp     short loc_140067C64
0x140067cdc  xorps   xmm0, xmm0
0x140067cdf  lea     r8, [rsp+1070h+ServiceStatus]; lpServiceStatus
0x140067ce4  movups  xmmword ptr [rsp+1070h+ServiceStatus.dwServiceType], xmm0
0x140067ce9  mov     edx, 1; dwControl
0x140067cee  mov     rcx, r15; hService
0x140067cf1  movups  xmmword ptr [rsp+1070h+ServiceStatus.dwWin32ExitCode], xmm0
0x140067cf6  call    cs:__imp_ControlService
0x140067cfc  test    eax, eax
0x140067cfe  jnz     short loc_140067D63
0x140067d00  call    cs:__imp_GetLastError
0x140067d06  cmp     eax, 426h
0x140067d0b  jz      short loc_140067D63
0x140067d0d  cmp     eax, 425h
0x140067d12  jnz     short loc_140067D1B
0x140067d14  cmp     [rsp+1070h+ServiceStatus.dwCurrentState], 3
0x140067d19  jz      short loc_140067D63
0x140067d1b  lea     rdx, [rsp+1070h+Destination]; lpBuffer
0x140067d20  mov     ecx, 0D80Eh; uID
0x140067d25  call    ?AtlLoadString@ATL@@YAHIPEAGH@Z; ATL::AtlLoadString(uint,ushort *,int)
0x140067d2a  test    eax, eax
0x140067d2c  jnz     short loc_140067D4C
0x140067d2e  lea     r8, aCouldNotStopSe; "Could not stop service"
0x140067d35  mov     edx, 400h; SizeInWords
0x140067d3a  lea     rcx, [rsp+1070h+Destination]; Destination
0x140067d3f  call    cs:__imp_wcscpy_s
0x140067d45  mov     ecx, eax; int
0x140067d47  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x140067d4c  xor     r9d, r9d; uType
0x140067d4f  lea     r8, Caption; lpCaption
0x140067d56  lea     rdx, [rsp+1070h+Destination]; lpText
0x140067d5b  xor     ecx, ecx; hWnd
0x140067d5d  call    cs:__imp_MessageBoxW
0x140067d63  mov     rcx, r15; hService
0x140067d66  call    cs:__imp_DeleteService
0x140067d6c  mov     rcx, r15; hSCObject
0x140067d6f  mov     ebx, eax
0x140067d71  call    cs:__imp_CloseServiceHandle
0x140067d77  mov     rcx, r14; hSCObject
0x140067d7a  call    cs:__imp_CloseServiceHandle
0x140067d80  test    ebx, ebx
0x140067d82  jnz     short loc_140067DC5
0x140067d84  lea     rdx, [rbp+0F70h+Buffer]; lpBuffer
0x140067d8b  mov     ecx, 0D80Dh; uID
0x140067d90  call    ?AtlLoadString@ATL@@YAHIPEAGH@Z; ATL::AtlLoadString(uint,ushort *,int)
0x140067d95  test    eax, eax
0x140067d97  jnz     short loc_140067DB9
0x140067d99  lea     r8, aCouldNotDelete; "Could not delete service"
0x140067da0  mov     edx, 400h; SizeInWords
0x140067da5  lea     rcx, [rbp+0F70h+Buffer]; Destination
0x140067dac  call    cs:__imp_wcscpy_s
0x140067db2  mov     ecx, eax; int
0x140067db4  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x140067db9  lea     rdx, [rbp+0F70h+Buffer]
0x140067dc0  jmp     loc_140067C80
0x140067dc5  mov     eax, 1
0x140067dca  mov     rcx, [rbp+0F70h+var_30]
0x140067dd1  xor     rcx, rsp; StackCookie
0x140067dd4  call    __security_check_cookie
0x140067dd9  add     rsp, 1058h
0x140067de0  pop     r15
0x140067de2  pop     r14
0x140067de4  pop     rbx
0x140067de5  pop     rbp
0x140067de6  retn
```
