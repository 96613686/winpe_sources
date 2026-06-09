# HrSetAutoStart(void)

- ea: `0x18004f368`
- end: `0x18004f4cb`
- name: `?HrSetAutoStart@@YAJXZ`
- size: `355`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x18004f5b0`
- `0x18004fa60`
- `0x18004ff50`

## callees

- `0x1800074dc`
- `0x18003b1cc`
- `0x18004f368`
- `0x180050578`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18004f457`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18004f457`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18004f40c`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18004f40c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f3f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f3f7`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18004f46f`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18004f47e`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18004f46f`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18004f47e`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18004f3b8`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18004f3b8`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18004f380`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18004f380`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18004f3e7`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18004f430`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18004f3e7`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18004f430`

## string_xrefs

- `0x18004f377`: `ServicesActive`

## pseudocode

```c
__int64 HrSetAutoStart(void)
{
  SC_HANDLE v0; // rax
  SC_HANDLE v1; // rbp
  unsigned int Win32Error; // ebx
  SC_HANDLE v3; // rax
  SC_HANDLE v4; // rsi
  struct _QUERY_SERVICE_CONFIGW *v5; // rax
  struct _QUERY_SERVICE_CONFIGW *v6; // rdi
  DWORD pcbBytesNeeded; // [rsp+50h] [rbp+8h] BYREF

  v0 = OpenSCManagerW(0, L"ServicesActive", 1u);
  v1 = v0;
  if ( v0 )
  {
    pcbBytesNeeded = 0;
    v3 = OpenServiceW(v0, L"upnphost", 1u);
    v4 = v3;
    if ( v3 )
    {
      Win32Error = 0;
      if ( !QueryServiceConfigW(v3, 0, 0, &pcbBytesNeeded) )
      {
        if ( GetLastError() == 122 )
        {
          v5 = (struct _QUERY_SERVICE_CONFIGW *)malloc(pcbBytesNeeded);
          v6 = v5;
          if ( v5 )
          {
            if ( QueryServiceConfigW(v4, v5, pcbBytesNeeded, &pcbBytesNeeded) )
            {
              if ( v6->dwStartType == 3 )
                SetServiceStartTypeViaWMI();
            }
            else
            {
              Win32Error = HrFromLastWin32Error();
            }
            free(v6);
          }
        }
        else
        {
          Win32Error = HrFromLastWin32Error();
        }
      }
      CloseServiceHandle(v4);
    }
    else
    {
      Win32Error = HrFromLastWin32Error();
    }
    CloseServiceHandle(v1);
  }
  else
  {
    Win32Error = HrFromLastWin32Error();
  }
  if ( Win32Error && WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 76, WPP_0f8e6464007c3e0bdd6d585d5cfe4b6e_Traceguids, Win32Error);
  return Win32Error;
}

```

## disassembly

```asm
0x18004f368  push    rbx
0x18004f36a  push    rbp
0x18004f36b  push    rsi
0x18004f36c  push    rdi
0x18004f36d  sub     rsp, 28h
0x18004f371  mov     r8d, 1; dwDesiredAccess
0x18004f377  lea     rdx, DatabaseName; "ServicesActive"
0x18004f37e  xor     ecx, ecx; lpMachineName
0x18004f380  call    cs:__imp_OpenSCManagerW
0x18004f387  nop     dword ptr [rax+rax+00h]
0x18004f38c  mov     rbp, rax
0x18004f38f  test    rax, rax
0x18004f392  jnz     short loc_18004F3A0
0x18004f394  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x18004f399  mov     ebx, eax
0x18004f39b  jmp     loc_18004F48A
0x18004f3a0  mov     r8d, 1; dwDesiredAccess
0x18004f3a6  mov     [rsp+48h+pcbBytesNeeded], 0
0x18004f3ae  lea     rdx, ServiceName; "upnphost"
0x18004f3b5  mov     rcx, rbp; hSCManager
0x18004f3b8  call    cs:__imp_OpenServiceW
0x18004f3bf  nop     dword ptr [rax+rax+00h]
0x18004f3c4  mov     rsi, rax
0x18004f3c7  test    rax, rax
0x18004f3ca  jnz     short loc_18004F3D8
0x18004f3cc  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x18004f3d1  mov     ebx, eax
0x18004f3d3  jmp     loc_18004F47B
0x18004f3d8  lea     r9, [rsp+48h+pcbBytesNeeded]; pcbBytesNeeded
0x18004f3dd  xor     r8d, r8d; cbBufSize
0x18004f3e0  xor     edx, edx; lpServiceConfig
0x18004f3e2  mov     rcx, rsi; hService
0x18004f3e5  xor     ebx, ebx
0x18004f3e7  call    cs:__imp_QueryServiceConfigW
0x18004f3ee  nop     dword ptr [rax+rax+00h]
0x18004f3f3  test    eax, eax
0x18004f3f5  jnz     short loc_18004F46C
0x18004f3f7  call    cs:__imp_GetLastError
0x18004f3fe  nop     dword ptr [rax+rax+00h]
0x18004f403  cmp     eax, 7Ah ; 'z'
0x18004f406  jnz     short loc_18004F465
0x18004f408  mov     ecx, [rsp+48h+pcbBytesNeeded]; Size
0x18004f40c  call    cs:__imp_malloc
0x18004f413  nop     dword ptr [rax+rax+00h]
0x18004f418  mov     rdi, rax
0x18004f41b  test    rax, rax
0x18004f41e  jz      short loc_18004F46C
0x18004f420  mov     r8d, [rsp+48h+pcbBytesNeeded]; cbBufSize
0x18004f425  lea     r9, [rsp+48h+pcbBytesNeeded]; pcbBytesNeeded
0x18004f42a  mov     rdx, rax; lpServiceConfig
0x18004f42d  mov     rcx, rsi; hService
0x18004f430  call    cs:__imp_QueryServiceConfigW
0x18004f437  nop     dword ptr [rax+rax+00h]
0x18004f43c  test    eax, eax
0x18004f43e  jnz     short loc_18004F449
0x18004f440  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x18004f445  mov     ebx, eax
0x18004f447  jmp     short loc_18004F454
0x18004f449  cmp     dword ptr [rdi+4], 3
0x18004f44d  jnz     short loc_18004F454
0x18004f44f  call    ?SetServiceStartTypeViaWMI@@YAXXZ; SetServiceStartTypeViaWMI(void)
0x18004f454  mov     rcx, rdi; Block
0x18004f457  call    cs:__imp_free
0x18004f45e  nop     dword ptr [rax+rax+00h]
0x18004f463  jmp     short loc_18004F46C
0x18004f465  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x18004f46a  mov     ebx, eax
0x18004f46c  mov     rcx, rsi; hSCObject
0x18004f46f  call    cs:__imp_CloseServiceHandle
0x18004f476  nop     dword ptr [rax+rax+00h]
0x18004f47b  mov     rcx, rbp; hSCObject
0x18004f47e  call    cs:__imp_CloseServiceHandle
0x18004f485  nop     dword ptr [rax+rax+00h]
0x18004f48a  test    ebx, ebx
0x18004f48c  jz      short loc_18004F4BF
0x18004f48e  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f495  lea     rax, WPP_GLOBAL_Control
0x18004f49c  cmp     rcx, rax
0x18004f49f  jz      short loc_18004F4BF
0x18004f4a1  test    byte ptr [rcx+1Ch], 1
0x18004f4a5  jz      short loc_18004F4BF
0x18004f4a7  mov     rcx, [rcx+10h]
0x18004f4ab  lea     r8, WPP_0f8e6464007c3e0bdd6d585d5cfe4b6e_Traceguids
0x18004f4b2  mov     edx, 4Ch ; 'L'
0x18004f4b7  mov     r9d, ebx
0x18004f4ba  call    WPP_SF_d
0x18004f4bf  mov     eax, ebx
0x18004f4c1  add     rsp, 28h
0x18004f4c5  pop     rdi
0x18004f4c6  pop     rsi
0x18004f4c7  pop     rbp
0x18004f4c8  pop     rbx
0x18004f4c9  retn
```
