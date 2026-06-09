# QuerySvcStatus(ushort const *,_SERVICE_STATUS_PROCESS *)

- ea: `0x18001ac48`
- end: `0x18001ad33`
- name: `?QuerySvcStatus@@YAJPEBGPEAU_SERVICE_STATUS_PROCESS@@@Z`
- size: `235`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct _SERVICE_STATUS_PROCESS *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180019a70`

## callees

- `0x1800050f0`
- `0x180019590`
- `0x18001ac48`

## import_xrefs

- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x18001acdd`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x18001acdd`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001ad0c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001ad15`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001ad0c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001ad15`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18001acac`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18001acac`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18001ac88`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18001ac88`

## pseudocode

```c
__int64 __fastcall QuerySvcStatus(const unsigned __int16 *a1, struct _SERVICE_STATUS_PROCESS *a2)
{
  unsigned int LastWin32Error; // ebx
  SC_HANDLE v4; // rax
  SC_HANDLE v5; // rsi
  SC_HANDLE v6; // rdi
  DWORD v7; // eax
  __int128 v8; // xmm1
  DWORD pcbBytesNeeded; // [rsp+30h] [rbp-68h] BYREF
  BYTE Buffer[16]; // [rsp+38h] [rbp-60h] BYREF
  __int128 v12; // [rsp+48h] [rbp-50h]
  DWORD v13; // [rsp+58h] [rbp-40h]

  LastWin32Error = 0;
  v13 = 0;
  pcbBytesNeeded = 0;
  *(_OWORD *)Buffer = 0;
  v12 = 0;
  v4 = OpenSCManagerW(0, 0, 0x80000000);
  v5 = v4;
  if ( v4 )
  {
    v6 = OpenServiceW(v4, L"StorSvc", 0x80000000);
    if ( v6 )
    {
      if ( QueryServiceStatusEx(v6, SC_STATUS_PROCESS_INFO, Buffer, 0x24u, &pcbBytesNeeded) )
      {
        v7 = v13;
        v8 = v12;
        *(_OWORD *)&a2->dwServiceType = *(_OWORD *)Buffer;
        *(_OWORD *)&a2->dwServiceSpecificExitCode = v8;
        a2->dwServiceFlags = v7;
      }
      else
      {
        LastWin32Error = GetLastWin32Error();
      }
      CloseServiceHandle(v6);
    }
    else
    {
      LastWin32Error = GetLastWin32Error();
    }
    CloseServiceHandle(v5);
  }
  else
  {
    return (unsigned int)GetLastWin32Error();
  }
  return LastWin32Error;
}

```

## disassembly

```asm
0x18001ac48  push    rbx
0x18001ac4a  push    rbp
0x18001ac4b  push    rsi
0x18001ac4c  push    rdi
0x18001ac4d  sub     rsp, 78h
0x18001ac51  mov     rax, cs:__security_cookie
0x18001ac58  xor     rax, rsp
0x18001ac5b  mov     [rsp+98h+var_38], rax
0x18001ac60  xorps   xmm0, xmm0
0x18001ac63  mov     rbp, rdx
0x18001ac66  xor     eax, eax
0x18001ac68  mov     edi, 80000000h
0x18001ac6d  xor     ebx, ebx
0x18001ac6f  mov     [rsp+98h+var_40], eax
0x18001ac73  mov     r8d, edi; dwDesiredAccess
0x18001ac76  mov     [rsp+98h+var_68], ebx
0x18001ac7a  xor     edx, edx; lpDatabaseName
0x18001ac7c  xor     ecx, ecx; lpMachineName
0x18001ac7e  movups  xmmword ptr [rsp+98h+Buffer], xmm0
0x18001ac83  movups  [rsp+98h+var_50], xmm0
0x18001ac88  call    cs:__imp_OpenSCManagerW
0x18001ac8e  mov     rsi, rax
0x18001ac91  test    rax, rax
0x18001ac94  jnz     short loc_18001AC9F
0x18001ac96  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x18001ac9b  mov     ebx, eax
0x18001ac9d  jmp     short loc_18001AD1B
0x18001ac9f  mov     r8d, edi; dwDesiredAccess
0x18001aca2  lea     rdx, ServiceName; "StorSvc"
0x18001aca9  mov     rcx, rsi; hSCManager
0x18001acac  call    cs:__imp_OpenServiceW
0x18001acb2  mov     rdi, rax
0x18001acb5  test    rax, rax
0x18001acb8  jnz     short loc_18001ACC3
0x18001acba  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x18001acbf  mov     ebx, eax
0x18001acc1  jmp     short loc_18001AD12
0x18001acc3  lea     rax, [rsp+98h+var_68]
0x18001acc8  mov     r9d, 24h ; '$'; cbBufSize
0x18001acce  lea     r8, [rsp+98h+Buffer]; lpBuffer
0x18001acd3  mov     [rsp+98h+pcbBytesNeeded], rax; pcbBytesNeeded
0x18001acd8  xor     edx, edx; InfoLevel
0x18001acda  mov     rcx, rdi; hService
0x18001acdd  call    cs:__imp_QueryServiceStatusEx
0x18001ace3  test    eax, eax
0x18001ace5  jnz     short loc_18001ACF0
0x18001ace7  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x18001acec  mov     ebx, eax
0x18001acee  jmp     short loc_18001AD09
0x18001acf0  movups  xmm0, xmmword ptr [rsp+98h+Buffer]
0x18001acf5  mov     eax, [rsp+98h+var_40]
0x18001acf9  movups  xmm1, [rsp+98h+var_50]
0x18001acfe  movups  xmmword ptr [rbp+0], xmm0
0x18001ad02  movups  xmmword ptr [rbp+10h], xmm1
0x18001ad06  mov     [rbp+20h], eax
0x18001ad09  mov     rcx, rdi; hSCObject
0x18001ad0c  call    cs:__imp_CloseServiceHandle
0x18001ad12  mov     rcx, rsi; hSCObject
0x18001ad15  call    cs:__imp_CloseServiceHandle
0x18001ad1b  mov     eax, ebx
0x18001ad1d  mov     rcx, [rsp+98h+var_38]
0x18001ad22  xor     rcx, rsp; StackCookie
0x18001ad25  call    __security_check_cookie
0x18001ad2a  add     rsp, 78h
0x18001ad2e  pop     rdi
0x18001ad2f  pop     rsi
0x18001ad30  pop     rbp
0x18001ad31  pop     rbx
0x18001ad32  retn
```
