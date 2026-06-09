# CGraphicsFactory__StartGraphicsServices(void)

- ea: `0x1800c410c`
- end: `0x1800c41d9`
- name: `?CGraphicsFactory__StartGraphicsServices@@YAJXZ`
- size: `205`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x18004aeb0`

## callees

- `0x1800c410c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c4167`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c4192`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c41b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c4167`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c4192`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c41b2`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800c418a`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800c41aa`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800c418a`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800c41aa`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800c4125`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800c4125`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x1800c4159`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x1800c4159`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800c4143`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800c4143`

## pseudocode

```c
__int64 CGraphicsFactory__StartGraphicsServices(void)
{
  SC_HANDLE v0; // rax
  SC_HANDLE v1; // rdi
  SC_HANDLE v2; // rax
  SC_HANDLE v3; // rsi
  unsigned int v4; // ebx
  signed int LastError; // eax
  signed int v6; // eax
  signed int v7; // eax

  v0 = OpenSCManagerW(0, 0, 0x80000000);
  v1 = v0;
  if ( v0 )
  {
    v2 = OpenServiceW(v0, L"RdpVideoMiniport", 0x10u);
    v3 = v2;
    if ( v2 )
    {
      if ( StartServiceW(v2, 0, 0) )
      {
        v4 = 0;
      }
      else
      {
        LastError = GetLastError();
        v4 = LastError;
        if ( LastError > 0 )
          v4 = (unsigned __int16)LastError | 0x80070000;
        if ( v4 == -2147023840 )
          v4 = 0;
      }
      CloseServiceHandle(v3);
    }
    else
    {
      v6 = GetLastError();
      v4 = v6;
      if ( v6 > 0 )
        v4 = (unsigned __int16)v6 | 0x80070000;
    }
    CloseServiceHandle(v1);
  }
  else
  {
    v7 = GetLastError();
    v4 = v7;
    if ( v7 > 0 )
      return (unsigned __int16)v7 | 0x80070000;
  }
  return v4;
}

```

## disassembly

```asm
0x1800c410c  mov     [rsp+arg_0], rbx
0x1800c4111  mov     [rsp+arg_8], rsi
0x1800c4116  push    rdi
0x1800c4117  sub     rsp, 20h
0x1800c411b  xor     edx, edx; lpDatabaseName
0x1800c411d  xor     ecx, ecx; lpMachineName
0x1800c411f  mov     r8d, 80000000h; dwDesiredAccess
0x1800c4125  call    cs:__imp_OpenSCManagerW
0x1800c412b  mov     rdi, rax
0x1800c412e  test    rax, rax
0x1800c4131  jz      short loc_1800C41B2
0x1800c4133  mov     r8d, 10h; dwDesiredAccess
0x1800c4139  lea     rdx, ServiceName; "RdpVideoMiniport"
0x1800c4140  mov     rcx, rax; hSCManager
0x1800c4143  call    cs:__imp_OpenServiceW
0x1800c4149  mov     rsi, rax
0x1800c414c  test    rax, rax
0x1800c414f  jz      short loc_1800C4192
0x1800c4151  xor     r8d, r8d; lpServiceArgVectors
0x1800c4154  xor     edx, edx; dwNumServiceArgs
0x1800c4156  mov     rcx, rax; hService
0x1800c4159  call    cs:__imp_StartServiceW
0x1800c415f  test    eax, eax
0x1800c4161  jz      short loc_1800C4167
0x1800c4163  xor     ebx, ebx
0x1800c4165  jmp     short loc_1800C4187
0x1800c4167  call    cs:__imp_GetLastError
0x1800c416d  mov     ebx, eax
0x1800c416f  test    eax, eax
0x1800c4171  jle     short loc_1800C417C
0x1800c4173  movzx   ebx, ax
0x1800c4176  or      ebx, 80070000h
0x1800c417c  xor     eax, eax
0x1800c417e  cmp     ebx, 80070420h
0x1800c4184  cmovz   ebx, eax
0x1800c4187  mov     rcx, rsi; hSCObject
0x1800c418a  call    cs:__imp_CloseServiceHandle
0x1800c4190  jmp     short loc_1800C41A7
0x1800c4192  call    cs:__imp_GetLastError
0x1800c4198  mov     ebx, eax
0x1800c419a  test    eax, eax
0x1800c419c  jle     short loc_1800C41A7
0x1800c419e  movzx   ebx, ax
0x1800c41a1  or      ebx, 80070000h
0x1800c41a7  mov     rcx, rdi; hSCObject
0x1800c41aa  call    cs:__imp_CloseServiceHandle
0x1800c41b0  jmp     short loc_1800C41C7
0x1800c41b2  call    cs:__imp_GetLastError
0x1800c41b8  mov     ebx, eax
0x1800c41ba  test    eax, eax
0x1800c41bc  jle     short loc_1800C41C7
0x1800c41be  movzx   ebx, ax
0x1800c41c1  or      ebx, 80070000h
0x1800c41c7  mov     rsi, [rsp+28h+arg_8]
0x1800c41cc  mov     eax, ebx
0x1800c41ce  mov     rbx, [rsp+28h+arg_0]
0x1800c41d3  add     rsp, 20h
0x1800c41d7  pop     rdi
0x1800c41d8  retn
```
