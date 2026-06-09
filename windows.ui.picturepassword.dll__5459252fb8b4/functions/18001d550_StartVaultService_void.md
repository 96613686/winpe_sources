# StartVaultService(void *)

- ea: `0x18001d550`
- end: `0x18001d5e6`
- name: `?StartVaultService@@YAKPEAX@Z`
- size: `150`
- prototype: `unsigned int __fastcall(void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x1800092b8`
- `0x18001d550`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x18001d59b`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x18001d59b`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18001d585`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18001d585`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001d5b3`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001d5c5`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001d5b3`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001d5c5`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18001d567`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18001d567`

## pseudocode

```c
__int64 __fastcall StartVaultService(void *a1)
{
  SC_HANDLE v1; // rax
  SC_HANDLE v2; // rdi
  SC_HANDLE v3; // rax
  SC_HANDLE v4; // rsi
  unsigned int Error; // ebx

  v1 = OpenSCManagerW(0, 0, 1u);
  v2 = v1;
  if ( v1 )
  {
    v3 = OpenServiceW(v1, L"VaultSvc", 0x10u);
    v4 = v3;
    if ( v3 )
    {
      if ( StartServiceW(v3, 0, 0) )
        Error = 0;
      else
        Error = ResultFromKnownLastError();
      CloseServiceHandle(v4);
    }
    else
    {
      Error = ResultFromKnownLastError();
    }
    CloseServiceHandle(v2);
  }
  else
  {
    return (unsigned int)ResultFromKnownLastError();
  }
  return Error;
}

```

## disassembly

```asm
0x18001d550  mov     [rsp+arg_0], rbx
0x18001d555  mov     [rsp+arg_8], rsi
0x18001d55a  push    rdi
0x18001d55b  sub     rsp, 20h
0x18001d55f  xor     edx, edx; lpDatabaseName
0x18001d561  xor     ecx, ecx; lpMachineName
0x18001d563  lea     r8d, [rdx+1]; dwDesiredAccess
0x18001d567  call    cs:__imp_OpenSCManagerW
0x18001d56d  mov     rdi, rax
0x18001d570  test    rax, rax
0x18001d573  jz      short loc_18001D5CD
0x18001d575  mov     r8d, 10h; dwDesiredAccess
0x18001d57b  lea     rdx, ServiceName; "VaultSvc"
0x18001d582  mov     rcx, rax; hSCManager
0x18001d585  call    cs:__imp_OpenServiceW
0x18001d58b  mov     rsi, rax
0x18001d58e  test    rax, rax
0x18001d591  jz      short loc_18001D5BB
0x18001d593  xor     r8d, r8d; lpServiceArgVectors
0x18001d596  xor     edx, edx; dwNumServiceArgs
0x18001d598  mov     rcx, rax; hService
0x18001d59b  call    cs:__imp_StartServiceW
0x18001d5a1  test    eax, eax
0x18001d5a3  jz      short loc_18001D5A9
0x18001d5a5  xor     ebx, ebx
0x18001d5a7  jmp     short loc_18001D5B0
0x18001d5a9  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18001d5ae  mov     ebx, eax
0x18001d5b0  mov     rcx, rsi; hSCObject
0x18001d5b3  call    cs:__imp_CloseServiceHandle
0x18001d5b9  jmp     short loc_18001D5C2
0x18001d5bb  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18001d5c0  mov     ebx, eax
0x18001d5c2  mov     rcx, rdi; hSCObject
0x18001d5c5  call    cs:__imp_CloseServiceHandle
0x18001d5cb  jmp     short loc_18001D5D4
0x18001d5cd  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18001d5d2  mov     ebx, eax
0x18001d5d4  mov     rsi, [rsp+28h+arg_8]
0x18001d5d9  mov     eax, ebx
0x18001d5db  mov     rbx, [rsp+28h+arg_0]
0x18001d5e0  add     rsp, 20h
0x18001d5e4  pop     rdi
0x18001d5e5  retn
```
