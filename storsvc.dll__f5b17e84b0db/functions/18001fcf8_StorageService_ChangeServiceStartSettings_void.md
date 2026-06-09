# StorageService::ChangeServiceStartSettings(void)

- ea: `0x18001fcf8`
- end: `0x18001fdd1`
- name: `?ChangeServiceStartSettings@StorageService@@IEAAXXZ`
- size: `217`
- prototype: `void __fastcall(StorageService *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x180027858`
- `0x18002a3f8`

## callees

- `0x18001fcf8`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18001fd3a`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18001fd3a`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001fdb2`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001fdc0`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001fdb2`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001fdc0`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18001fd13`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18001fd13`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x18001fd96`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x18001fd96`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x18001fda9`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x18001fda9`

## pseudocode

```c
void __fastcall StorageService::ChangeServiceStartSettings(StorageService *this)
{
  SC_HANDLE v1; // rax
  SC_HANDLE v2; // rdi
  SC_HANDLE v3; // rax
  SC_HANDLE v4; // rbx
  StorageService *Info; // [rsp+70h] [rbp+8h] BYREF

  Info = this;
  v1 = OpenSCManagerW(0, 0, 0xF003Fu);
  LODWORD(Info) = 1;
  v2 = v1;
  if ( v1 )
  {
    v3 = OpenServiceW(v1, L"StorSvc", 0xF003Fu);
    v4 = v3;
    if ( v3 )
    {
      ChangeServiceConfigW(v3, 0xFFFFFFFF, 2u, 0xFFFFFFFF, 0, 0, 0, 0, 0, 0, 0);
      ChangeServiceConfig2W(v4, 3u, &Info);
    }
    CloseServiceHandle(v2);
    if ( v4 )
      CloseServiceHandle(v4);
  }
}

```

## disassembly

```asm
0x18001fcf8  mov     [rsp+arg_8], rbx
0x18001fcfd  mov     [rsp+Info], rcx
0x18001fd02  push    rdi
0x18001fd03  sub     rsp, 60h
0x18001fd07  mov     ebx, 0F003Fh
0x18001fd0c  xor     edx, edx; lpDatabaseName
0x18001fd0e  mov     r8d, ebx; dwDesiredAccess
0x18001fd11  xor     ecx, ecx; lpMachineName
0x18001fd13  call    cs:__imp_OpenSCManagerW
0x18001fd19  mov     dword ptr [rsp+68h+Info], 1
0x18001fd21  mov     rdi, rax
0x18001fd24  test    rax, rax
0x18001fd27  jz      loc_18001FDC6
0x18001fd2d  mov     r8d, ebx; dwDesiredAccess
0x18001fd30  lea     rdx, ServiceName; "StorSvc"
0x18001fd37  mov     rcx, rax; hSCManager
0x18001fd3a  call    cs:__imp_OpenServiceW
0x18001fd40  mov     rbx, rax
0x18001fd43  test    rax, rax
0x18001fd46  jz      short loc_18001FDAF
0x18001fd48  mov     [rsp+68h+lpDisplayName], 0; lpDisplayName
0x18001fd51  or      edx, 0FFFFFFFFh; dwServiceType
0x18001fd54  mov     [rsp+68h+lpPassword], 0; lpPassword
0x18001fd5d  mov     r9d, edx; dwErrorControl
0x18001fd60  mov     [rsp+68h+lpServiceStartName], 0; lpServiceStartName
0x18001fd69  mov     r8d, 2; dwStartType
0x18001fd6f  mov     [rsp+68h+lpDependencies], 0; lpDependencies
0x18001fd78  mov     rcx, rax; hService
0x18001fd7b  mov     [rsp+68h+lpdwTagId], 0; lpdwTagId
0x18001fd84  mov     [rsp+68h+lpLoadOrderGroup], 0; lpLoadOrderGroup
0x18001fd8d  mov     [rsp+68h+lpBinaryPathName], 0; lpBinaryPathName
0x18001fd96  call    cs:__imp_ChangeServiceConfigW
0x18001fd9c  lea     r8, [rsp+68h+Info]; lpInfo
0x18001fda1  mov     edx, 3; dwInfoLevel
0x18001fda6  mov     rcx, rbx; hService
0x18001fda9  call    cs:__imp_ChangeServiceConfig2W
0x18001fdaf  mov     rcx, rdi; hSCObject
0x18001fdb2  call    cs:__imp_CloseServiceHandle
0x18001fdb8  test    rbx, rbx
0x18001fdbb  jz      short loc_18001FDC6
0x18001fdbd  mov     rcx, rbx; hSCObject
0x18001fdc0  call    cs:__imp_CloseServiceHandle
0x18001fdc6  mov     rbx, [rsp+68h+arg_8]
0x18001fdcb  add     rsp, 60h
0x18001fdcf  pop     rdi
0x18001fdd0  retn
```
