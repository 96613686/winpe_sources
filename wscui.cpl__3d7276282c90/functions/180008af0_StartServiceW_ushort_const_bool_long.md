# StartServiceW(ushort const *,bool,long)

- ea: `0x180008af0`
- end: `0x180008d27`
- name: `?StartServiceW@@YAHPEBG_NJ@Z`
- size: `567`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180006520`

## callees

- `0x180008030`
- `0x180008058`
- `0x180008af0`
- `0x180008d30`
- `0x18000a640`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008bcb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008c77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008cb2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008bcb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008c77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008cb2`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180008c52`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180008c52`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180008b9f`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180008b9f`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180008bbf`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180008bbf`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180008b81`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180008b81`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180008c6f`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180008caa`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180008c6f`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180008caa`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180008c60`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180008c60`

## pseudocode

```c
__int64 __fastcall StartServiceW(const unsigned __int16 *a1, __int64 a2, __int64 a3)
{
  LPCWSTR v3; // rax
  _QWORD *v4; // rcx
  unsigned int started; // ebx
  SC_HANDLE v7; // rax
  SC_HANDLE v8; // rbp
  SC_HANDLE v9; // rax
  SC_HANDLE v10; // rsi
  DWORD LastError; // eax
  __int64 v12; // r8
  DWORD v13; // eax
  DWORD v14; // eax
  _QWORD *v15; // rcx
  LPCWSTR lpServiceName; // [rsp+20h] [rbp-58h] BYREF
  _SERVICE_STATUS ServiceStatus; // [rsp+28h] [rbp-50h] BYREF

  v3 = L"wscsvc";
  lpServiceName = L"wscsvc";
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, a3, L"wscsvc");
    v3 = lpServiceName;
    v4 = WPP_GLOBAL_Control;
  }
  if ( v3 )
  {
    started = 0;
    v7 = OpenSCManagerW(0, 0, 0x10u);
    v8 = v7;
    if ( v7 )
    {
      v9 = OpenServiceW(v7, lpServiceName, 0x10u);
      v10 = v9;
      if ( v9 )
      {
        started = StartServiceW(v9, 1u, &lpServiceName);
        if ( !started )
        {
          LastError = GetLastError();
          if ( LastError == 1056 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
              WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), started + 18, v12, lpServiceName);
            started = 1;
          }
          else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              19,
              &WPP_b298b2b0c5c43f867e700010dc436ffd_Traceguids,
              LastError);
          }
        }
        memset(&ServiceStatus, 0, sizeof(ServiceStatus));
        CloseServiceHandle(v10);
      }
      else
      {
        v13 = GetLastError();
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_b298b2b0c5c43f867e700010dc436ffd_Traceguids, v13);
      }
      CloseServiceHandle(v8);
    }
    else
    {
      v14 = GetLastError();
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return started;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
LABEL_29:
        if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 8) != 0 )
          WPP_SF_d(v15[2], 22, &WPP_b298b2b0c5c43f867e700010dc436ffd_Traceguids, started);
        return started;
      }
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_b298b2b0c5c43f867e700010dc436ffd_Traceguids, v14);
    }
    v15 = WPP_GLOBAL_Control;
    goto LABEL_29;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 1) != 0 )
    WPP_SF_(v4[2], 16, &WPP_b298b2b0c5c43f867e700010dc436ffd_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x180008af0  push    rbx
0x180008af2  push    rbp
0x180008af3  push    rsi
0x180008af4  push    r14
0x180008af6  push    r15
0x180008af8  sub     rsp, 50h
0x180008afc  mov     rax, cs:__security_cookie
0x180008b03  xor     rax, rsp
0x180008b06  mov     [rsp+78h+var_30], rax
0x180008b0b  lea     rax, aWscsvc; "wscsvc"
0x180008b12  mov     [rsp+78h+lpServiceName], rax
0x180008b17  mov     rcx, cs:WPP_GLOBAL_Control
0x180008b1e  lea     r15, WPP_GLOBAL_Control
0x180008b25  cmp     rcx, r15
0x180008b28  jz      short loc_180008B4D
0x180008b2a  test    byte ptr [rcx+1Ch], 8
0x180008b2e  jz      short loc_180008B4D
0x180008b30  mov     rcx, [rcx+10h]
0x180008b34  mov     edx, 0Fh
0x180008b39  mov     r9, rax
0x180008b3c  call    WPP_SF_S
0x180008b41  mov     rax, [rsp+78h+lpServiceName]
0x180008b46  mov     rcx, cs:WPP_GLOBAL_Control
0x180008b4d  test    rax, rax
0x180008b50  jnz     short loc_180008B77
0x180008b52  cmp     rcx, r15
0x180008b55  jz      short loc_180008B70
0x180008b57  test    byte ptr [rcx+1Ch], 1
0x180008b5b  jz      short loc_180008B70
0x180008b5d  mov     rcx, [rcx+10h]
0x180008b61  lea     edx, [rax+10h]
0x180008b64  lea     r8, WPP_b298b2b0c5c43f867e700010dc436ffd_Traceguids
0x180008b6b  call    WPP_SF_
0x180008b70  xor     eax, eax
0x180008b72  jmp     loc_180008D0E
0x180008b77  xor     ebx, ebx
0x180008b79  xor     edx, edx; lpDatabaseName
0x180008b7b  xor     ecx, ecx; lpMachineName
0x180008b7d  lea     r8d, [rbx+10h]; dwDesiredAccess
0x180008b81  call    cs:__imp_OpenSCManagerW
0x180008b87  mov     rbp, rax
0x180008b8a  test    rax, rax
0x180008b8d  jz      loc_180008CB2
0x180008b93  mov     rdx, [rsp+78h+lpServiceName]; lpServiceName
0x180008b98  lea     r8d, [rbx+10h]; dwDesiredAccess
0x180008b9c  mov     rcx, rax; hSCManager
0x180008b9f  call    cs:__imp_OpenServiceW
0x180008ba5  mov     rsi, rax
0x180008ba8  test    rax, rax
0x180008bab  jz      loc_180008C77
0x180008bb1  lea     r8, [rsp+78h+lpServiceName]; lpServiceArgVectors
0x180008bb6  mov     rcx, rax; hService
0x180008bb9  lea     edx, [rbx+1]; dwNumServiceArgs
0x180008bbc  xor     r14d, r14d
0x180008bbf  call    cs:__imp_StartServiceW
0x180008bc5  mov     ebx, eax
0x180008bc7  test    eax, eax
0x180008bc9  jnz     short loc_180008C2C
0x180008bcb  call    cs:__imp_GetLastError
0x180008bd1  cmp     eax, 420h
0x180008bd6  jnz     short loc_180008C02
0x180008bd8  mov     rcx, cs:WPP_GLOBAL_Control
0x180008bdf  cmp     rcx, r15
0x180008be2  jz      short loc_180008BFB
0x180008be4  test    byte ptr [rcx+1Ch], 4
0x180008be8  jz      short loc_180008BFB
0x180008bea  mov     r9, [rsp+78h+lpServiceName]
0x180008bef  lea     edx, [rbx+12h]
0x180008bf2  mov     rcx, [rcx+10h]
0x180008bf6  call    WPP_SF_S
0x180008bfb  mov     ebx, 1
0x180008c00  jmp     short loc_180008C2C
0x180008c02  mov     rcx, cs:WPP_GLOBAL_Control
0x180008c09  cmp     rcx, r15
0x180008c0c  jz      short loc_180008C2C
0x180008c0e  test    byte ptr [rcx+1Ch], 1
0x180008c12  jz      short loc_180008C2C
0x180008c14  mov     rcx, [rcx+10h]
0x180008c18  lea     r8, WPP_b298b2b0c5c43f867e700010dc436ffd_Traceguids
0x180008c1f  mov     edx, 13h
0x180008c24  mov     r9d, eax
0x180008c27  call    WPP_SF_d
0x180008c2c  xorps   xmm0, xmm0
0x180008c2f  movups  xmmword ptr [rsp+78h+ServiceStatus.dwServiceType], xmm0
0x180008c34  movups  xmmword ptr [rsp+78h+ServiceStatus.dwWin32ExitCode], xmm0
0x180008c39  test    ebx, ebx
0x180008c3b  jz      short loc_180008C6C
0x180008c3d  cmp     [rsp+78h+ServiceStatus.dwCurrentState], 4
0x180008c42  jz      short loc_180008C6C
0x180008c44  test    r14d, r14d
0x180008c47  jle     short loc_180008C6C
0x180008c49  mov     ecx, 64h ; 'd'; dwMilliseconds
0x180008c4e  sub     r14d, 64h ; 'd'
0x180008c52  call    cs:__imp_Sleep
0x180008c58  lea     rdx, [rsp+78h+ServiceStatus]; lpServiceStatus
0x180008c5d  mov     rcx, rsi; hService
0x180008c60  call    cs:__imp_QueryServiceStatus
0x180008c66  mov     ebx, eax
0x180008c68  test    eax, eax
0x180008c6a  jnz     short loc_180008C3D
0x180008c6c  mov     rcx, rsi; hSCObject
0x180008c6f  call    cs:__imp_CloseServiceHandle
0x180008c75  jmp     short loc_180008CA7
0x180008c77  call    cs:__imp_GetLastError
0x180008c7d  mov     rcx, cs:WPP_GLOBAL_Control
0x180008c84  cmp     rcx, r15
0x180008c87  jz      short loc_180008CA7
0x180008c89  test    byte ptr [rcx+1Ch], 1
0x180008c8d  jz      short loc_180008CA7
0x180008c8f  mov     rcx, [rcx+10h]
0x180008c93  lea     r8, WPP_b298b2b0c5c43f867e700010dc436ffd_Traceguids
0x180008c9a  mov     edx, 14h
0x180008c9f  mov     r9d, eax
0x180008ca2  call    WPP_SF_d
0x180008ca7  mov     rcx, rbp; hSCObject
0x180008caa  call    cs:__imp_CloseServiceHandle
0x180008cb0  jmp     short loc_180008CE2
0x180008cb2  call    cs:__imp_GetLastError
0x180008cb8  mov     rcx, cs:WPP_GLOBAL_Control
0x180008cbf  cmp     rcx, r15
0x180008cc2  jz      short loc_180008D0C
0x180008cc4  test    byte ptr [rcx+1Ch], 1
0x180008cc8  jz      short loc_180008CE9
0x180008cca  mov     rcx, [rcx+10h]
0x180008cce  lea     r8, WPP_b298b2b0c5c43f867e700010dc436ffd_Traceguids
0x180008cd5  mov     edx, 15h
0x180008cda  mov     r9d, eax
0x180008cdd  call    WPP_SF_d
0x180008ce2  mov     rcx, cs:WPP_GLOBAL_Control
0x180008ce9  cmp     rcx, r15
0x180008cec  jz      short loc_180008D0C
0x180008cee  test    byte ptr [rcx+1Ch], 8
0x180008cf2  jz      short loc_180008D0C
0x180008cf4  mov     rcx, [rcx+10h]
0x180008cf8  lea     r8, WPP_b298b2b0c5c43f867e700010dc436ffd_Traceguids
0x180008cff  mov     edx, 16h
0x180008d04  mov     r9d, ebx
0x180008d07  call    WPP_SF_d
0x180008d0c  mov     eax, ebx
0x180008d0e  mov     rcx, [rsp+78h+var_30]
0x180008d13  xor     rcx, rsp; StackCookie
0x180008d16  call    __security_check_cookie
0x180008d1b  add     rsp, 50h
0x180008d1f  pop     r15
0x180008d21  pop     r14
0x180008d23  pop     rsi
0x180008d24  pop     rbp
0x180008d25  pop     rbx
0x180008d26  retn
```
