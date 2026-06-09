# HrSetAutoStart(void)

- ea: `0x18004c024`
- end: `0x18004c14d`
- name: `?HrSetAutoStart@@YAJXZ`
- size: `297`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x18004c230`
- `0x18004c6b0`
- `0x18004cb90`

## callees

- `0x18001347c`
- `0x180038ce4`
- `0x18004c024`
- `0x18004d178`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18004c0ec`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18004c0ec`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18004c0ad`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18004c0ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c09e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c09e`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18004c0fe`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18004c107`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18004c0fe`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18004c107`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18004c06e`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18004c06e`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18004c03c`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18004c03c`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18004c094`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18004c0cb`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18004c094`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18004c0cb`

## string_xrefs

- `0x18004c033`: `ServicesActive`

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
0x18004c024  push    rbx
0x18004c026  push    rbp
0x18004c027  push    rsi
0x18004c028  push    rdi
0x18004c029  sub     rsp, 28h
0x18004c02d  mov     r8d, 1; dwDesiredAccess
0x18004c033  lea     rdx, DatabaseName; "ServicesActive"
0x18004c03a  xor     ecx, ecx; lpMachineName
0x18004c03c  call    cs:__imp_OpenSCManagerW
0x18004c042  mov     rbp, rax
0x18004c045  test    rax, rax
0x18004c048  jnz     short loc_18004C056
0x18004c04a  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x18004c04f  mov     ebx, eax
0x18004c051  jmp     loc_18004C10D
0x18004c056  mov     r8d, 1; dwDesiredAccess
0x18004c05c  mov     [rsp+48h+pcbBytesNeeded], 0
0x18004c064  lea     rdx, ServiceName; "upnphost"
0x18004c06b  mov     rcx, rbp; hSCManager
0x18004c06e  call    cs:__imp_OpenServiceW
0x18004c074  mov     rsi, rax
0x18004c077  test    rax, rax
0x18004c07a  jnz     short loc_18004C085
0x18004c07c  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x18004c081  mov     ebx, eax
0x18004c083  jmp     short loc_18004C104
0x18004c085  lea     r9, [rsp+48h+pcbBytesNeeded]; pcbBytesNeeded
0x18004c08a  xor     r8d, r8d; cbBufSize
0x18004c08d  xor     edx, edx; lpServiceConfig
0x18004c08f  mov     rcx, rsi; hService
0x18004c092  xor     ebx, ebx
0x18004c094  call    cs:__imp_QueryServiceConfigW
0x18004c09a  test    eax, eax
0x18004c09c  jnz     short loc_18004C0FB
0x18004c09e  call    cs:__imp_GetLastError
0x18004c0a4  cmp     eax, 7Ah ; 'z'
0x18004c0a7  jnz     short loc_18004C0F4
0x18004c0a9  mov     ecx, [rsp+48h+pcbBytesNeeded]; Size
0x18004c0ad  call    cs:__imp_malloc
0x18004c0b3  mov     rdi, rax
0x18004c0b6  test    rax, rax
0x18004c0b9  jz      short loc_18004C0FB
0x18004c0bb  mov     r8d, [rsp+48h+pcbBytesNeeded]; cbBufSize
0x18004c0c0  lea     r9, [rsp+48h+pcbBytesNeeded]; pcbBytesNeeded
0x18004c0c5  mov     rdx, rax; lpServiceConfig
0x18004c0c8  mov     rcx, rsi; hService
0x18004c0cb  call    cs:__imp_QueryServiceConfigW
0x18004c0d1  test    eax, eax
0x18004c0d3  jnz     short loc_18004C0DE
0x18004c0d5  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x18004c0da  mov     ebx, eax
0x18004c0dc  jmp     short loc_18004C0E9
0x18004c0de  cmp     dword ptr [rdi+4], 3
0x18004c0e2  jnz     short loc_18004C0E9
0x18004c0e4  call    ?SetServiceStartTypeViaWMI@@YAXXZ; SetServiceStartTypeViaWMI(void)
0x18004c0e9  mov     rcx, rdi; Block
0x18004c0ec  call    cs:__imp_free
0x18004c0f2  jmp     short loc_18004C0FB
0x18004c0f4  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x18004c0f9  mov     ebx, eax
0x18004c0fb  mov     rcx, rsi; hSCObject
0x18004c0fe  call    cs:__imp_CloseServiceHandle
0x18004c104  mov     rcx, rbp; hSCObject
0x18004c107  call    cs:__imp_CloseServiceHandle
0x18004c10d  test    ebx, ebx
0x18004c10f  jz      short loc_18004C142
0x18004c111  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c118  lea     rax, WPP_GLOBAL_Control
0x18004c11f  cmp     rcx, rax
0x18004c122  jz      short loc_18004C142
0x18004c124  test    byte ptr [rcx+1Ch], 1
0x18004c128  jz      short loc_18004C142
0x18004c12a  mov     rcx, [rcx+10h]
0x18004c12e  lea     r8, WPP_0f8e6464007c3e0bdd6d585d5cfe4b6e_Traceguids
0x18004c135  mov     edx, 4Ch ; 'L'
0x18004c13a  mov     r9d, ebx
0x18004c13d  call    WPP_SF_d
0x18004c142  mov     eax, ebx
0x18004c144  add     rsp, 28h
0x18004c148  pop     rdi
0x18004c149  pop     rsi
0x18004c14a  pop     rbp
0x18004c14b  pop     rbx
0x18004c14c  retn
```
