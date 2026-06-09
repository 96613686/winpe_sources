# CGraphicsFactory__StartGraphicsServices(void)

- ea: `0x1800ca1b0`
- end: `0x1800ca2b2`
- name: `?CGraphicsFactory__StartGraphicsServices@@YAJXZ`
- size: `258`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x18004d4d0`

## callees

- `0x1800ca1b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ca221`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ca258`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ca284`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ca221`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ca258`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ca284`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800ca24a`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800ca276`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800ca24a`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800ca276`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800ca1c9`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800ca1c9`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x1800ca20d`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x1800ca20d`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800ca1f1`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800ca1f1`

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
0x1800ca1b0  mov     [rsp+arg_0], rbx
0x1800ca1b5  mov     [rsp+arg_8], rsi
0x1800ca1ba  push    rdi
0x1800ca1bb  sub     rsp, 20h
0x1800ca1bf  xor     edx, edx; lpDatabaseName
0x1800ca1c1  xor     ecx, ecx; lpMachineName
0x1800ca1c3  mov     r8d, 80000000h; dwDesiredAccess
0x1800ca1c9  call    cs:__imp_OpenSCManagerW
0x1800ca1d0  nop     dword ptr [rax+rax+00h]
0x1800ca1d5  mov     rdi, rax
0x1800ca1d8  test    rax, rax
0x1800ca1db  jz      loc_1800CA284
0x1800ca1e1  mov     r8d, 10h; dwDesiredAccess
0x1800ca1e7  lea     rdx, ServiceName; "RdpVideoMiniport"
0x1800ca1ee  mov     rcx, rax; hSCManager
0x1800ca1f1  call    cs:__imp_OpenServiceW
0x1800ca1f8  nop     dword ptr [rax+rax+00h]
0x1800ca1fd  mov     rsi, rax
0x1800ca200  test    rax, rax
0x1800ca203  jz      short loc_1800CA258
0x1800ca205  xor     r8d, r8d; lpServiceArgVectors
0x1800ca208  xor     edx, edx; dwNumServiceArgs
0x1800ca20a  mov     rcx, rax; hService
0x1800ca20d  call    cs:__imp_StartServiceW
0x1800ca214  nop     dword ptr [rax+rax+00h]
0x1800ca219  test    eax, eax
0x1800ca21b  jz      short loc_1800CA221
0x1800ca21d  xor     ebx, ebx
0x1800ca21f  jmp     short loc_1800CA247
0x1800ca221  call    cs:__imp_GetLastError
0x1800ca228  nop     dword ptr [rax+rax+00h]
0x1800ca22d  mov     ebx, eax
0x1800ca22f  test    eax, eax
0x1800ca231  jle     short loc_1800CA23C
0x1800ca233  movzx   ebx, ax
0x1800ca236  or      ebx, 80070000h
0x1800ca23c  xor     eax, eax
0x1800ca23e  cmp     ebx, 80070420h
0x1800ca244  cmovz   ebx, eax
0x1800ca247  mov     rcx, rsi; hSCObject
0x1800ca24a  call    cs:__imp_CloseServiceHandle
0x1800ca251  nop     dword ptr [rax+rax+00h]
0x1800ca256  jmp     short loc_1800CA273
0x1800ca258  call    cs:__imp_GetLastError
0x1800ca25f  nop     dword ptr [rax+rax+00h]
0x1800ca264  mov     ebx, eax
0x1800ca266  test    eax, eax
0x1800ca268  jle     short loc_1800CA273
0x1800ca26a  movzx   ebx, ax
0x1800ca26d  or      ebx, 80070000h
0x1800ca273  mov     rcx, rdi; hSCObject
0x1800ca276  call    cs:__imp_CloseServiceHandle
0x1800ca27d  nop     dword ptr [rax+rax+00h]
0x1800ca282  jmp     short loc_1800CA29F
0x1800ca284  call    cs:__imp_GetLastError
0x1800ca28b  nop     dword ptr [rax+rax+00h]
0x1800ca290  mov     ebx, eax
0x1800ca292  test    eax, eax
0x1800ca294  jle     short loc_1800CA29F
0x1800ca296  movzx   ebx, ax
0x1800ca299  or      ebx, 80070000h
0x1800ca29f  mov     rsi, [rsp+28h+arg_8]
0x1800ca2a4  mov     eax, ebx
0x1800ca2a6  mov     rbx, [rsp+28h+arg_0]
0x1800ca2ab  add     rsp, 20h
0x1800ca2af  pop     rdi
0x1800ca2b0  retn
```
