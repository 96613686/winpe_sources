# CWerService::QueryServiceStartType(ulong *)

- ea: `0x180016968`
- end: `0x180016aba`
- name: `?QueryServiceStartType@CWerService@@AEAAJPEAK@Z`
- size: `338`
- prototype: `__int64 __fastcall(CWerService *__hidden this, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config, service_task`

## callers

- `0x1800181f8`

## callees

- `0x180002a00`
- `0x180002ff0`
- `0x180016968`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800169ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800169e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016a1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016a27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016a56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800169ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800169e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016a1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016a27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016a56`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18001699d`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18001699d`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180016a93`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180016a9c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180016a93`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180016a9c`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800169d9`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800169d9`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180016a12`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180016a7f`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180016a12`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180016a7f`

## pseudocode

```c
__int64 __fastcall CWerService::QueryServiceStartType(CWerService *this, unsigned int *a2)
{
  unsigned int v3; // edi
  SC_HANDLE v4; // rax
  SC_HANDLE v5; // rbp
  signed int LastError; // eax
  struct _QUERY_SERVICE_CONFIGW *v7; // rbx
  SC_HANDLE v8; // rax
  SC_HANDLE v9; // rsi
  signed int v10; // eax
  signed int v11; // eax
  struct _QUERY_SERVICE_CONFIGW *v12; // rax
  signed int v13; // eax
  DWORD pcbBytesNeeded; // [rsp+50h] [rbp+8h] BYREF
  int v16; // [rsp+54h] [rbp+Ch]

  v16 = HIDWORD(this);
  pcbBytesNeeded = 0;
  if ( !a2 )
    return (unsigned int)-2147024809;
  *a2 = 0;
  v4 = OpenSCManagerW(0, 0, 4u);
  v5 = v4;
  if ( !v4 )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
    return v3;
  }
  v7 = 0;
  v8 = OpenServiceW(v4, L"WerSvc", 1u);
  v9 = v8;
  if ( !v8 )
  {
    v10 = GetLastError();
    v3 = v10;
    if ( v10 > 0 )
      v3 = (unsigned __int16)v10 | 0x80070000;
    goto LABEL_20;
  }
  if ( !QueryServiceConfigW(v8, 0, 0, &pcbBytesNeeded) && GetLastError() != 122 )
    goto LABEL_11;
  v12 = (struct _QUERY_SERVICE_CONFIGW *)operator new(pcbBytesNeeded, (const struct std::nothrow_t *)&std::nothrow);
  v7 = v12;
  if ( !v12 )
  {
    v13 = GetLastError();
    v3 = v13;
    if ( v13 > 0 )
      v3 = (unsigned __int16)v13 | 0x80070000;
    v7 = 0;
    goto LABEL_19;
  }
  if ( QueryServiceConfigW(v9, v12, pcbBytesNeeded, &pcbBytesNeeded) )
  {
    *a2 = v7->dwStartType;
    v3 = 0;
  }
  else
  {
LABEL_11:
    v11 = GetLastError();
    v3 = v11;
    if ( v11 > 0 )
      v3 = (unsigned __int16)v11 | 0x80070000;
  }
LABEL_19:
  CloseServiceHandle(v9);
LABEL_20:
  CloseServiceHandle(v5);
  if ( v7 )
    operator delete(v7);
  return v3;
}

```

## disassembly

```asm
0x180016968  mov     qword ptr [rsp+pcbBytesNeeded], rcx
0x18001696d  push    rbx
0x18001696e  push    rbp
0x18001696f  push    rsi
0x180016970  push    rdi
0x180016971  sub     rsp, 28h
0x180016975  mov     [rsp+48h+pcbBytesNeeded], 0
0x18001697d  mov     rdi, rdx
0x180016980  test    rdx, rdx
0x180016983  jnz     short loc_18001698F
0x180016985  mov     edi, 80070057h
0x18001698a  jmp     loc_180016AAF
0x18001698f  mov     dword ptr [rdx], 0
0x180016995  xor     ecx, ecx; lpMachineName
0x180016997  xor     edx, edx; lpDatabaseName
0x180016999  lea     r8d, [rdx+4]; dwDesiredAccess
0x18001699d  call    cs:__imp_OpenSCManagerW
0x1800169a3  mov     rbp, rax
0x1800169a6  test    rax, rax
0x1800169a9  jnz     short loc_1800169C9
0x1800169ab  call    cs:__imp_GetLastError
0x1800169b1  mov     edi, eax
0x1800169b3  test    eax, eax
0x1800169b5  jle     loc_180016AAF
0x1800169bb  movzx   edi, ax
0x1800169be  or      edi, 80070000h
0x1800169c4  jmp     loc_180016AAF
0x1800169c9  xor     ebx, ebx
0x1800169cb  lea     rdx, AliasPrefix; "WerSvc"
0x1800169d2  mov     rcx, rbp; hSCManager
0x1800169d5  lea     r8d, [rbx+1]; dwDesiredAccess
0x1800169d9  call    cs:__imp_OpenServiceW
0x1800169df  mov     rsi, rax
0x1800169e2  test    rax, rax
0x1800169e5  jnz     short loc_180016A05
0x1800169e7  call    cs:__imp_GetLastError
0x1800169ed  mov     edi, eax
0x1800169ef  test    eax, eax
0x1800169f1  jle     loc_180016A99
0x1800169f7  movzx   edi, ax
0x1800169fa  or      edi, 80070000h
0x180016a00  jmp     loc_180016A99
0x180016a05  lea     r9, [rsp+48h+pcbBytesNeeded]; pcbBytesNeeded
0x180016a0a  xor     r8d, r8d; cbBufSize
0x180016a0d  xor     edx, edx; lpServiceConfig
0x180016a0f  mov     rcx, rsi; hService
0x180016a12  call    cs:__imp_QueryServiceConfigW
0x180016a18  test    eax, eax
0x180016a1a  jnz     short loc_180016A3E
0x180016a1c  call    cs:__imp_GetLastError
0x180016a22  cmp     eax, 7Ah ; 'z'
0x180016a25  jz      short loc_180016A3E
0x180016a27  call    cs:__imp_GetLastError
0x180016a2d  mov     edi, eax
0x180016a2f  test    eax, eax
0x180016a31  jle     short loc_180016A90
0x180016a33  movzx   edi, ax
0x180016a36  or      edi, 80070000h
0x180016a3c  jmp     short loc_180016A90
0x180016a3e  mov     ecx, [rsp+48h+pcbBytesNeeded]; unsigned __int64
0x180016a42  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180016a49  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180016a4e  mov     rbx, rax
0x180016a51  test    rax, rax
0x180016a54  jnz     short loc_180016A6F
0x180016a56  call    cs:__imp_GetLastError
0x180016a5c  mov     edi, eax
0x180016a5e  test    eax, eax
0x180016a60  jle     short loc_180016A6B
0x180016a62  movzx   edi, ax
0x180016a65  or      edi, 80070000h
0x180016a6b  xor     ebx, ebx
0x180016a6d  jmp     short loc_180016A90
0x180016a6f  mov     r8d, [rsp+48h+pcbBytesNeeded]; cbBufSize
0x180016a74  lea     r9, [rsp+48h+pcbBytesNeeded]; pcbBytesNeeded
0x180016a79  mov     rdx, rbx; lpServiceConfig
0x180016a7c  mov     rcx, rsi; hService
0x180016a7f  call    cs:__imp_QueryServiceConfigW
0x180016a85  test    eax, eax
0x180016a87  jz      short loc_180016A27
0x180016a89  mov     eax, [rbx+4]
0x180016a8c  mov     [rdi], eax
0x180016a8e  xor     edi, edi
0x180016a90  mov     rcx, rsi; hSCObject
0x180016a93  call    cs:__imp_CloseServiceHandle
0x180016a99  mov     rcx, rbp; hSCObject
0x180016a9c  call    cs:__imp_CloseServiceHandle
0x180016aa2  test    rbx, rbx
0x180016aa5  jz      short loc_180016AAF
0x180016aa7  mov     rcx, rbx; Block
0x180016aaa  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180016aaf  mov     eax, edi
0x180016ab1  add     rsp, 28h
0x180016ab5  pop     rdi
0x180016ab6  pop     rsi
0x180016ab7  pop     rbp
0x180016ab8  pop     rbx
0x180016ab9  retn
```
