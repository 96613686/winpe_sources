# GetServiceStartType(ushort const *,ulong *)

- ea: `0x18000fac0`
- end: `0x18000fbd3`
- name: `?GetServiceStartType@@YAJPEBGPEAK@Z`
- size: `275`
- prototype: `__int64 __fastcall(LPCWSTR lpServiceName, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x18000edc4`

## callees

- `0x18000fac0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000faf8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fb44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000faf8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fb44`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000fb59`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000fb59`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fb9c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fb9c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000fbaa`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000fbb8`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000fbaa`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000fbb8`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18000fb1f`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18000fb1f`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18000fae8`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18000fae8`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18000fb3a`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18000fb7c`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18000fb3a`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18000fb7c`

## pseudocode

```c
__int64 __fastcall GetServiceStartType(LPCWSTR lpServiceName, unsigned int *a2)
{
  struct _QUERY_SERVICE_CONFIGW *v2; // rsi
  SC_HANDLE v5; // rax
  SC_HANDLE v6; // rbp
  SC_HANDLE v7; // rdi
  signed int LastError; // eax
  unsigned int v9; // ebx
  SC_HANDLE v10; // rax
  DWORD v11; // ebx
  struct _QUERY_SERVICE_CONFIGW *v12; // rax
  DWORD pcbBytesNeeded; // [rsp+50h] [rbp+18h] BYREF

  v2 = 0;
  pcbBytesNeeded = 0;
  v5 = OpenSCManagerW(0, 0, 1u);
  v6 = v5;
  if ( !v5 )
  {
    v7 = 0;
LABEL_3:
    LastError = GetLastError();
    v9 = LastError;
    goto LABEL_4;
  }
  v10 = OpenServiceW(v5, lpServiceName, 1u);
  v7 = v10;
  if ( !v10 )
    goto LABEL_3;
  if ( QueryServiceConfigW(v10, 0, 0, &pcbBytesNeeded) )
  {
    v9 = -2147418113;
    goto LABEL_14;
  }
  LastError = GetLastError();
  v9 = LastError;
  if ( LastError == 122 )
  {
    v11 = pcbBytesNeeded;
    v12 = (struct _QUERY_SERVICE_CONFIGW *)LocalAlloc(0, pcbBytesNeeded);
    v2 = v12;
    if ( !v12 )
    {
      v9 = -2147024882;
      goto LABEL_14;
    }
    if ( QueryServiceConfigW(v7, v12, v11, &pcbBytesNeeded) )
    {
      v9 = 0;
      *a2 = v2->dwStartType;
      goto LABEL_14;
    }
    goto LABEL_3;
  }
LABEL_4:
  if ( LastError > 0 )
    v9 = (unsigned __int16)LastError | 0x80070000;
LABEL_14:
  LocalFree(v2);
  if ( v7 )
    CloseServiceHandle(v7);
  if ( v6 )
    CloseServiceHandle(v6);
  return v9;
}

```

## disassembly

```asm
0x18000fac0  mov     [rsp+arg_0], rbx
0x18000fac5  mov     [rsp+arg_8], rbp
0x18000faca  push    rsi
0x18000facb  push    rdi
0x18000facc  push    r14
0x18000face  sub     rsp, 20h
0x18000fad2  xor     esi, esi
0x18000fad4  mov     r14, rdx
0x18000fad7  mov     rbx, rcx
0x18000fada  mov     [rsp+38h+pcbBytesNeeded], esi
0x18000fade  xor     edx, edx; lpDatabaseName
0x18000fae0  xor     ecx, ecx; lpMachineName
0x18000fae2  lea     edi, [rsi+1]
0x18000fae5  mov     r8d, edi; dwDesiredAccess
0x18000fae8  call    cs:__imp_OpenSCManagerW
0x18000faee  mov     rbp, rax
0x18000faf1  test    rax, rax
0x18000faf4  jnz     short loc_18000FB16
0x18000faf6  xor     edi, edi
0x18000faf8  call    cs:__imp_GetLastError
0x18000fafe  mov     ebx, eax
0x18000fb00  test    eax, eax
0x18000fb02  jle     loc_18000FB99
0x18000fb08  movzx   ebx, ax
0x18000fb0b  or      ebx, 80070000h
0x18000fb11  jmp     loc_18000FB99
0x18000fb16  mov     r8d, edi; dwDesiredAccess
0x18000fb19  mov     rdx, rbx; lpServiceName
0x18000fb1c  mov     rcx, rbp; hSCManager
0x18000fb1f  call    cs:__imp_OpenServiceW
0x18000fb25  mov     rdi, rax
0x18000fb28  test    rax, rax
0x18000fb2b  jz      short loc_18000FAF8
0x18000fb2d  lea     r9, [rsp+38h+pcbBytesNeeded]; pcbBytesNeeded
0x18000fb32  xor     r8d, r8d; cbBufSize
0x18000fb35  xor     edx, edx; lpServiceConfig
0x18000fb37  mov     rcx, rax; hService
0x18000fb3a  call    cs:__imp_QueryServiceConfigW
0x18000fb40  test    eax, eax
0x18000fb42  jnz     short loc_18000FB94
0x18000fb44  call    cs:__imp_GetLastError
0x18000fb4a  mov     ebx, eax
0x18000fb4c  cmp     eax, 7Ah ; 'z'
0x18000fb4f  jnz     short loc_18000FB00
0x18000fb51  mov     ebx, [rsp+38h+pcbBytesNeeded]
0x18000fb55  xor     ecx, ecx; uFlags
0x18000fb57  mov     edx, ebx; uBytes
0x18000fb59  call    cs:__imp_LocalAlloc
0x18000fb5f  mov     rsi, rax
0x18000fb62  test    rax, rax
0x18000fb65  jnz     short loc_18000FB6E
0x18000fb67  mov     ebx, 8007000Eh
0x18000fb6c  jmp     short loc_18000FB99
0x18000fb6e  lea     r9, [rsp+38h+pcbBytesNeeded]; pcbBytesNeeded
0x18000fb73  mov     r8d, ebx; cbBufSize
0x18000fb76  mov     rdx, rsi; lpServiceConfig
0x18000fb79  mov     rcx, rdi; hService
0x18000fb7c  call    cs:__imp_QueryServiceConfigW
0x18000fb82  test    eax, eax
0x18000fb84  jz      loc_18000FAF8
0x18000fb8a  mov     eax, [rsi+4]
0x18000fb8d  xor     ebx, ebx
0x18000fb8f  mov     [r14], eax
0x18000fb92  jmp     short loc_18000FB99
0x18000fb94  mov     ebx, 8000FFFFh
0x18000fb99  mov     rcx, rsi; hMem
0x18000fb9c  call    cs:__imp_LocalFree
0x18000fba2  test    rdi, rdi
0x18000fba5  jz      short loc_18000FBB0
0x18000fba7  mov     rcx, rdi; hSCObject
0x18000fbaa  call    cs:__imp_CloseServiceHandle
0x18000fbb0  test    rbp, rbp
0x18000fbb3  jz      short loc_18000FBBE
0x18000fbb5  mov     rcx, rbp; hSCObject
0x18000fbb8  call    cs:__imp_CloseServiceHandle
0x18000fbbe  mov     rbp, [rsp+38h+arg_8]
0x18000fbc3  mov     eax, ebx
0x18000fbc5  mov     rbx, [rsp+38h+arg_0]
0x18000fbca  add     rsp, 20h
0x18000fbce  pop     r14
0x18000fbd0  pop     rdi
0x18000fbd1  pop     rsi
0x18000fbd2  retn
```
