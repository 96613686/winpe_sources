# winmmWaitForService

- ea: `0x180006800`
- end: `0x180006b90`
- name: `winmmWaitForService`
- size: `912`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x1800065d0`
- `0x180006770`

## callees

- `0x180006800`
- `0x1800106c0`
- `0x180011d6c`
- `0x180012d08`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006b00`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006b00`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006a86`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006a86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006919`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800069c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006a40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006a4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006ab7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006b50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006919`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800069c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006a40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006a4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006ab7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006b50`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000695a`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000695a`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180006848`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180006848`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800068eb`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800068f9`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800068eb`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800068f9`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18000686f`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18000686f`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180006a36`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180006aa4`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180006a36`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180006aa4`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800068b1`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800068b1`

## pseudocode

```c
__int64 winmmWaitForService()
{
  SC_HANDLE v1; // rax
  SC_HANDLE v2; // rbx
  SC_HANDLE v3; // rdi
  int v4; // ebp
  DWORD v5; // eax
  PVOID *v6; // rcx
  DWORD LastError; // eax
  DWORD v8; // eax
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  struct _QUERY_SERVICE_CONFIGW *v11; // rax
  struct _QUERY_SERVICE_CONFIGW *v12; // r14
  DWORD v13; // eax
  DWORD pcbBytesNeeded; // [rsp+20h] [rbp-38h] BYREF
  _SERVICE_STATUS ServiceStatus; // [rsp+28h] [rbp-30h] BYREF

  if ( dword_18002D5C0 )
    return (unsigned int)dword_18002D5C8;
  v1 = OpenSCManagerW(0, 0, 1u);
  v2 = v1;
  if ( !v1 )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_d09965cb4e7936f4cd6f01087cde1378_Traceguids, LastError);
    return 0;
  }
  v3 = OpenServiceW(v1, L"AudioSrv", 5u);
  if ( !v3 )
  {
    v5 = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_d09965cb4e7936f4cd6f01087cde1378_Traceguids, v5);
    goto LABEL_11;
  }
  v4 = 0;
  if ( dword_18002D5C0 )
    goto LABEL_10;
  while ( 1 )
  {
    memset(&ServiceStatus, 0, sizeof(ServiceStatus));
    if ( !QueryServiceStatus(v3, &ServiceStatus) )
    {
      v8 = GetLastError();
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) == 0 )
        goto LABEL_9;
      v10 = 16;
LABEL_52:
      WPP_SF_d(v9[2], v10, WPP_d09965cb4e7936f4cd6f01087cde1378_Traceguids, v8);
      goto LABEL_9;
    }
    if ( ServiceStatus.dwCurrentState - 4 <= 3 )
    {
      dword_18002D5C8 = 1;
      goto LABEL_9;
    }
    if ( ServiceStatus.dwCurrentState != 1 )
    {
      if ( ServiceStatus.dwCurrentState != 2 )
        goto LABEL_9;
      goto LABEL_17;
    }
    if ( ServiceStatus.dwWin32ExitCode != 1077 )
      goto LABEL_9;
    if ( v4 )
      goto LABEL_17;
    pcbBytesNeeded = 0;
    if ( !QueryServiceConfigW(v3, 0, 0, &pcbBytesNeeded) && GetLastError() != 122 )
    {
      v8 = GetLastError();
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) == 0 )
        goto LABEL_9;
      v10 = 15;
      goto LABEL_52;
    }
    v11 = (struct _QUERY_SERVICE_CONFIGW *)HeapAlloc(hHeap, 0, pcbBytesNeeded);
    v12 = v11;
    if ( v11 )
    {
      if ( QueryServiceConfigW(v3, v11, pcbBytesNeeded, &pcbBytesNeeded) )
      {
        if ( v12->dwStartType != 2 )
          goto LABEL_42;
      }
      else
      {
        v13 = GetLastError();
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_d09965cb4e7936f4cd6f01087cde1378_Traceguids, v13);
LABEL_42:
        dword_18002D5C0 = 1;
      }
      HeapFree(hHeap, 0, v12);
LABEL_17:
      v6 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_18;
    }
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_d09965cb4e7936f4cd6f01087cde1378_Traceguids);
      goto LABEL_17;
    }
LABEL_18:
    if ( dword_18002D5C0 )
      goto LABEL_10;
    if ( 2000 * v4 > 120000 )
      break;
    Sleep(0x7D0u);
    if ( dword_18002D5C0 )
      goto LABEL_10;
    ++v4;
  }
  if ( v6 != &WPP_GLOBAL_Control && (*((_DWORD *)v6 + 7) & 0x400000) != 0 )
    WPP_SF_(v6[2], 17, WPP_d09965cb4e7936f4cd6f01087cde1378_Traceguids);
LABEL_9:
  dword_18002D5C0 = 1;
LABEL_10:
  CloseServiceHandle(v3);
LABEL_11:
  CloseServiceHandle(v2);
  return (unsigned int)dword_18002D5C8;
}

```

## disassembly

```asm
0x180006800  sub     rsp, 58h
0x180006804  mov     rax, cs:__security_cookie
0x18000680b  xor     rax, rsp
0x18000680e  mov     [rsp+58h+var_10], rax
0x180006813  cmp     cs:dword_18002D5C0, 0
0x18000681a  jz      short loc_180006834
0x18000681c  mov     eax, cs:dword_18002D5C8
0x180006822  mov     rcx, [rsp+58h+var_10]
0x180006827  xor     rcx, rsp; StackCookie
0x18000682a  call    __security_check_cookie
0x18000682f  add     rsp, 58h
0x180006833  retn
0x180006834  mov     [rsp+58h+arg_0], rbx
0x180006839  xor     edx, edx; lpDatabaseName
0x18000683b  xor     ecx, ecx; lpMachineName
0x18000683d  mov     [rsp+58h+arg_10], rsi
0x180006842  mov     r8d, 1; dwDesiredAccess
0x180006848  call    cs:__imp_OpenSCManagerW
0x18000684e  mov     rbx, rax
0x180006851  test    rax, rax
0x180006854  jz      loc_1800069C5
0x18000685a  mov     r8d, 5; dwDesiredAccess
0x180006860  mov     [rsp+58h+arg_18], rdi
0x180006865  lea     rdx, ServiceName; "AudioSrv"
0x18000686c  mov     rcx, rax; hSCManager
0x18000686f  call    cs:__imp_OpenServiceW
0x180006875  mov     rdi, rax
0x180006878  test    rax, rax
0x18000687b  jz      loc_180006919
0x180006881  mov     [rsp+58h+arg_8], rbp
0x180006886  xor     ebp, ebp
0x180006888  cmp     cs:dword_18002D5C0, ebp
0x18000688e  jnz     short loc_1800068E8
0x180006890  lea     rsi, WPP_GLOBAL_Control
0x180006897  mov     [rsp+58h+var_8], r14
0x18000689c  xorps   xmm0, xmm0
0x18000689f  lea     rdx, [rsp+58h+ServiceStatus]; lpServiceStatus
0x1800068a4  movups  xmmword ptr [rsp+58h+ServiceStatus.dwServiceType], xmm0
0x1800068a9  mov     rcx, rdi; hService
0x1800068ac  movups  xmmword ptr [rsp+58h+ServiceStatus.dwWin32ExitCode], xmm0
0x1800068b1  call    cs:__imp_QueryServiceStatus
0x1800068b7  test    eax, eax
0x1800068b9  jz      loc_180006B50
0x1800068bf  mov     ecx, [rsp+58h+ServiceStatus.dwCurrentState]
0x1800068c3  lea     eax, [rcx-4]
0x1800068c6  cmp     eax, 3
0x1800068c9  ja      loc_180006A06
0x1800068cf  mov     cs:dword_18002D5C8, 1
0x1800068d9  mov     cs:dword_18002D5C0, 1
0x1800068e3  mov     r14, [rsp+58h+var_8]
0x1800068e8  mov     rcx, rdi; hSCObject
0x1800068eb  call    cs:__imp_CloseServiceHandle
0x1800068f1  mov     rbp, [rsp+58h+arg_8]
0x1800068f6  mov     rcx, rbx; hSCObject
0x1800068f9  call    cs:__imp_CloseServiceHandle
0x1800068ff  mov     eax, cs:dword_18002D5C8
0x180006905  mov     rdi, [rsp+58h+arg_18]
0x18000690a  mov     rbx, [rsp+58h+arg_0]
0x18000690f  mov     rsi, [rsp+58h+arg_10]
0x180006914  jmp     loc_180006822
0x180006919  call    cs:__imp_GetLastError
0x18000691f  mov     rcx, cs:WPP_GLOBAL_Control
0x180006926  lea     rsi, WPP_GLOBAL_Control
0x18000692d  cmp     rcx, rsi
0x180006930  jz      short loc_1800068F6
0x180006932  test    dword ptr [rcx+1Ch], 400000h
0x180006939  jz      short loc_1800068F6
0x18000693b  mov     rcx, [rcx+10h]
0x18000693f  lea     r8, WPP_d09965cb4e7936f4cd6f01087cde1378_Traceguids
0x180006946  mov     edx, 12h
0x18000694b  mov     r9d, eax
0x18000694e  call    WPP_SF_d
0x180006953  jmp     short loc_1800068F6
0x180006955  mov     ecx, 7D0h; dwMilliseconds
0x18000695a  call    cs:__imp_Sleep
0x180006960  cmp     cs:dword_18002D5C0, 0
0x180006967  jnz     loc_1800068E3
0x18000696d  inc     ebp
0x18000696f  jmp     loc_18000689C
0x180006974  mov     rcx, cs:WPP_GLOBAL_Control
0x18000697b  cmp     cs:dword_18002D5C0, 0
0x180006982  jnz     loc_1800068E3
0x180006988  imul    eax, ebp, 7D0h
0x18000698e  cmp     eax, 1D4C0h
0x180006993  jle     short loc_180006955
0x180006995  cmp     rcx, rsi
0x180006998  jz      loc_1800068D9
0x18000699e  test    dword ptr [rcx+1Ch], 400000h
0x1800069a5  jz      loc_1800068D9
0x1800069ab  mov     rcx, [rcx+10h]
0x1800069af  lea     r8, WPP_d09965cb4e7936f4cd6f01087cde1378_Traceguids
0x1800069b6  mov     edx, 11h
0x1800069bb  call    WPP_SF_
0x1800069c0  jmp     loc_1800068D9
0x1800069c5  call    cs:__imp_GetLastError
0x1800069cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800069d2  lea     rsi, WPP_GLOBAL_Control
0x1800069d9  cmp     rcx, rsi
0x1800069dc  jz      short loc_1800069FF
0x1800069de  test    dword ptr [rcx+1Ch], 400000h
0x1800069e5  jz      short loc_1800069FF
0x1800069e7  mov     rcx, [rcx+10h]
0x1800069eb  lea     r8, WPP_d09965cb4e7936f4cd6f01087cde1378_Traceguids
0x1800069f2  mov     edx, 0Ch
0x1800069f7  mov     r9d, eax
0x1800069fa  call    WPP_SF_d
0x1800069ff  xor     eax, eax
0x180006a01  jmp     loc_18000690A
0x180006a06  cmp     ecx, 1
0x180006a09  jnz     loc_180006B42
0x180006a0f  cmp     [rsp+58h+ServiceStatus.dwWin32ExitCode], 435h
0x180006a17  jnz     loc_1800068D9
0x180006a1d  test    ebp, ebp
0x180006a1f  jnz     loc_180006974
0x180006a25  lea     r9, [rsp+58h+pcbBytesNeeded]; pcbBytesNeeded
0x180006a2a  mov     [rsp+58h+pcbBytesNeeded], ebp
0x180006a2e  xor     r8d, r8d; cbBufSize
0x180006a31  xor     edx, edx; lpServiceConfig
0x180006a33  mov     rcx, rdi; hService
0x180006a36  call    cs:__imp_QueryServiceConfigW
0x180006a3c  test    eax, eax
0x180006a3e  jnz     short loc_180006A78
0x180006a40  call    cs:__imp_GetLastError
0x180006a46  cmp     eax, 7Ah ; 'z'
0x180006a49  jz      short loc_180006A78
0x180006a4b  call    cs:__imp_GetLastError
0x180006a51  mov     rcx, cs:WPP_GLOBAL_Control
0x180006a58  cmp     rcx, rsi
0x180006a5b  jz      loc_1800068D9
0x180006a61  test    dword ptr [rcx+1Ch], 400000h
0x180006a68  jz      loc_1800068D9
0x180006a6e  mov     edx, 0Fh
0x180006a73  jmp     loc_180006B78
0x180006a78  mov     r8d, [rsp+58h+pcbBytesNeeded]; dwBytes
0x180006a7d  xor     edx, edx; dwFlags
0x180006a7f  mov     rcx, cs:hHeap; hHeap
0x180006a86  call    cs:__imp_HeapAlloc
0x180006a8c  mov     r14, rax
0x180006a8f  test    rax, rax
0x180006a92  jz      short loc_180006B0B
0x180006a94  mov     r8d, [rsp+58h+pcbBytesNeeded]; cbBufSize
0x180006a99  lea     r9, [rsp+58h+pcbBytesNeeded]; pcbBytesNeeded
0x180006a9e  mov     rdx, rax; lpServiceConfig
0x180006aa1  mov     rcx, rdi; hService
0x180006aa4  call    cs:__imp_QueryServiceConfigW
0x180006aaa  test    eax, eax
0x180006aac  jz      short loc_180006AB7
0x180006aae  cmp     dword ptr [r14+4], 2
0x180006ab3  jz      short loc_180006AF4
0x180006ab5  jmp     short loc_180006AEA
0x180006ab7  call    cs:__imp_GetLastError
0x180006abd  mov     rcx, cs:WPP_GLOBAL_Control
0x180006ac4  cmp     rcx, rsi
0x180006ac7  jz      short loc_180006AEA
0x180006ac9  test    dword ptr [rcx+1Ch], 400000h
0x180006ad0  jz      short loc_180006AEA
0x180006ad2  mov     rcx, [rcx+10h]
0x180006ad6  lea     r8, WPP_d09965cb4e7936f4cd6f01087cde1378_Traceguids
0x180006add  mov     edx, 0Dh
0x180006ae2  mov     r9d, eax
0x180006ae5  call    WPP_SF_d
0x180006aea  mov     cs:dword_18002D5C0, 1
0x180006af4  mov     rcx, cs:hHeap; hHeap
0x180006afb  mov     r8, r14; lpMem
0x180006afe  xor     edx, edx; dwFlags
0x180006b00  call    cs:__imp_HeapFree
0x180006b06  jmp     loc_180006974
0x180006b0b  mov     rcx, cs:WPP_GLOBAL_Control
0x180006b12  cmp     rcx, rsi
0x180006b15  jz      loc_18000697B
0x180006b1b  test    dword ptr [rcx+1Ch], 400000h
0x180006b22  jz      loc_18000697B
0x180006b28  mov     rcx, [rcx+10h]
0x180006b2c  lea     r8, WPP_d09965cb4e7936f4cd6f01087cde1378_Traceguids
0x180006b33  mov     edx, 0Eh
0x180006b38  call    WPP_SF_
0x180006b3d  jmp     loc_180006974
0x180006b42  cmp     ecx, 2
0x180006b45  jnz     loc_1800068D9
0x180006b4b  jmp     loc_180006974
0x180006b50  call    cs:__imp_GetLastError
0x180006b56  mov     rcx, cs:WPP_GLOBAL_Control
0x180006b5d  cmp     rcx, rsi
0x180006b60  jz      loc_1800068D9
0x180006b66  test    dword ptr [rcx+1Ch], 400000h
0x180006b6d  jz      loc_1800068D9
0x180006b73  mov     edx, 10h
0x180006b78  mov     rcx, [rcx+10h]
0x180006b7c  lea     r8, WPP_d09965cb4e7936f4cd6f01087cde1378_Traceguids
0x180006b83  mov     r9d, eax
0x180006b86  call    WPP_SF_d
0x180006b8b  jmp     loc_1800068D9
```
