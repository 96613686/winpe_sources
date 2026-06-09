# IsCurrentVersionServiceInstalled(SC_HANDLE__ *,ushort *,int *)

- ea: `0x18003a558`
- end: `0x18003a679`
- name: `?IsCurrentVersionServiceInstalled@@YAJPEAUSC_HANDLE__@@PEAGPEAH@Z`
- size: `289`
- prototype: `__int64 __fastcall(SC_HANDLE hSCManager, LPCWSTR lpServiceName, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18004086c`

## callees

- `0x18003a558`
- `0x18004d030`
- `0x18004d350`
- `0x18004d690`
- `0x18004d754`
- `0x18004f048`
- `0x18004f078`
- `0x18004f1a0`
- `0x180050a58`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18003a5cc`
- `KERNEL32!GetLastError` at `0x18003a5cc`
- `ADVAPI32!CloseServiceHandle` at `0x18003a650`
- `ADVAPI32!CloseServiceHandle` at `0x18003a650`
- `ADVAPI32!OpenServiceW` at `0x18003a59f`
- `ADVAPI32!OpenServiceW` at `0x18003a59f`
- `ADVAPI32!QueryServiceConfigW` at `0x18003a5c6`
- `ADVAPI32!QueryServiceConfigW` at `0x18003a5ff`
- `ADVAPI32!QueryServiceConfigW` at `0x18003a5c6`
- `ADVAPI32!QueryServiceConfigW` at `0x18003a5ff`

## pseudocode

```c
__int64 __fastcall IsCurrentVersionServiceInstalled(SC_HANDLE hSCManager, LPCWSTR lpServiceName, int *a3)
{
  LPCWSTR *v4; // rsi
  SC_HANDLE v7; // rax
  SC_HANDLE v8; // rdi
  unsigned int LastWin32Error; // ebx
  struct _QUERY_SERVICE_CONFIGW *v10; // rax
  DWORD pcbBytesNeeded; // [rsp+20h] [rbp-78h] BYREF
  _BYTE v13[24]; // [rsp+28h] [rbp-70h] BYREF
  struct tagVS_FIXEDFILEINFO v14; // [rsp+40h] [rbp-58h] BYREF

  v4 = 0;
  pcbBytesNeeded = 0;
  ASPNETVER::ASPNETVER((ASPNETVER *)v13);
  *a3 = 0;
  v7 = OpenServiceW(hSCManager, lpServiceName, 0x80000000);
  v8 = v7;
  if ( !v7 )
    goto LABEL_2;
  QueryServiceConfigW(v7, 0, 0, &pcbBytesNeeded);
  if ( GetLastError() != 122 )
    goto LABEL_2;
  v10 = (struct _QUERY_SERVICE_CONFIGW *)MemAlloc(pcbBytesNeeded);
  v4 = (LPCWSTR *)v10;
  if ( !v10 )
  {
    LastWin32Error = -2147024882;
    goto LABEL_9;
  }
  if ( !QueryServiceConfigW(v8, v10, pcbBytesNeeded, &pcbBytesNeeded) )
  {
LABEL_2:
    LastWin32Error = GetLastWin32Error();
    goto LABEL_9;
  }
  LastWin32Error = GetFileVersion(v4[2], &v14);
  if ( !LastWin32Error )
  {
    ASPNETVER::Init((ASPNETVER *)v13, &v14);
    *a3 = ASPNETVER::operator==(v13, &ASPNETVER::m_gThisVer);
  }
LABEL_9:
  MemFree(v4);
  if ( v8 )
    CloseServiceHandle(v8);
  return LastWin32Error;
}

```

## disassembly

```asm
0x18003a558  mov     [rsp+arg_18], rbx
0x18003a55d  push    rsi
0x18003a55e  push    rdi
0x18003a55f  push    r14
0x18003a561  sub     rsp, 80h
0x18003a568  mov     rax, cs:__security_cookie
0x18003a56f  xor     rax, rsp
0x18003a572  mov     [rsp+98h+var_20], rax
0x18003a577  mov     rbx, rcx
0x18003a57a  xor     esi, esi
0x18003a57c  and     [rsp+98h+pcbBytesNeeded], esi
0x18003a580  lea     rcx, [rsp+98h+var_70]; this
0x18003a585  mov     r14, r8
0x18003a588  mov     rdi, rdx
0x18003a58b  call    ??0ASPNETVER@@QEAA@XZ; ASPNETVER::ASPNETVER(void)
0x18003a590  and     [r14], esi
0x18003a593  mov     r8d, 80000000h; dwDesiredAccess
0x18003a599  mov     rdx, rdi; lpServiceName
0x18003a59c  mov     rcx, rbx; hSCManager
0x18003a59f  call    cs:__imp_OpenServiceW
0x18003a5a5  mov     rdi, rax
0x18003a5a8  test    rax, rax
0x18003a5ab  jnz     short loc_18003A5B9
0x18003a5ad  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x18003a5b2  mov     ebx, eax
0x18003a5b4  jmp     loc_18003A640
0x18003a5b9  lea     r9, [rsp+98h+pcbBytesNeeded]; pcbBytesNeeded
0x18003a5be  xor     r8d, r8d; cbBufSize
0x18003a5c1  xor     edx, edx; lpServiceConfig
0x18003a5c3  mov     rcx, rdi; hService
0x18003a5c6  call    cs:__imp_QueryServiceConfigW
0x18003a5cc  call    cs:__imp_GetLastError
0x18003a5d2  cmp     eax, 7Ah ; 'z'
0x18003a5d5  jnz     short loc_18003A5AD
0x18003a5d7  mov     ecx, [rsp+98h+pcbBytesNeeded]; unsigned __int64
0x18003a5db  call    ?MemAlloc@@YAPEAX_K@Z; MemAlloc(unsigned __int64)
0x18003a5e0  mov     rsi, rax
0x18003a5e3  test    rax, rax
0x18003a5e6  jnz     short loc_18003A5EF
0x18003a5e8  mov     ebx, 8007000Eh
0x18003a5ed  jmp     short loc_18003A640
0x18003a5ef  mov     r8d, [rsp+98h+pcbBytesNeeded]; cbBufSize
0x18003a5f4  lea     r9, [rsp+98h+pcbBytesNeeded]; pcbBytesNeeded
0x18003a5f9  mov     rdx, rsi; lpServiceConfig
0x18003a5fc  mov     rcx, rdi; hService
0x18003a5ff  call    cs:__imp_QueryServiceConfigW
0x18003a605  test    eax, eax
0x18003a607  jz      short loc_18003A5AD
0x18003a609  mov     rcx, [rsi+10h]; lptstrFilename
0x18003a60d  lea     rdx, [rsp+98h+var_58]; struct tagVS_FIXEDFILEINFO *
0x18003a612  call    ?GetFileVersion@@YAJPEBGPEAUtagVS_FIXEDFILEINFO@@@Z; GetFileVersion(ushort const *,tagVS_FIXEDFILEINFO *)
0x18003a617  mov     ebx, eax
0x18003a619  test    eax, eax
0x18003a61b  jnz     short loc_18003A640
0x18003a61d  lea     rdx, [rsp+98h+var_58]; struct tagVS_FIXEDFILEINFO *
0x18003a622  lea     rcx, [rsp+98h+var_70]; this
0x18003a627  call    ?Init@ASPNETVER@@QEAAHPEAUtagVS_FIXEDFILEINFO@@@Z; ASPNETVER::Init(tagVS_FIXEDFILEINFO *)
0x18003a62c  lea     rdx, ?m_gThisVer@ASPNETVER@@0V1@A; ASPNETVER ASPNETVER::m_gThisVer
0x18003a633  lea     rcx, [rsp+98h+var_70]
0x18003a638  call    ??8ASPNETVER@@QEAAHAEAV0@@Z; ASPNETVER::operator==(ASPNETVER &)
0x18003a63d  mov     [r14], eax
0x18003a640  mov     rcx, rsi; lpMem
0x18003a643  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x18003a648  test    rdi, rdi
0x18003a64b  jz      short loc_18003A656
0x18003a64d  mov     rcx, rdi; hSCObject
0x18003a650  call    cs:__imp_CloseServiceHandle
0x18003a656  mov     eax, ebx
0x18003a658  mov     rcx, [rsp+98h+var_20]
0x18003a65d  xor     rcx, rsp; StackCookie
0x18003a660  call    __security_check_cookie
0x18003a665  mov     rbx, [rsp+98h+arg_18]
0x18003a66d  add     rsp, 80h
0x18003a674  pop     r14
0x18003a676  pop     rdi
0x18003a677  pop     rsi
0x18003a678  retn
```
