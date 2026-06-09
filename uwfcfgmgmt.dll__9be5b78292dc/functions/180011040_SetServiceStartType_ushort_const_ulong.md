# SetServiceStartType(ushort const *,ulong)

- ea: `0x180011040`
- end: `0x180011121`
- name: `?SetServiceStartType@@YAJPEBGK@Z`
- size: `225`
- prototype: `__int64 __fastcall(LPCWSTR lpServiceName, DWORD dwStartType)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x18000edc4`

## callees

- `0x180011040`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011068`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001109d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800110ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011068`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001109d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800110ef`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180011107`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180011110`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180011107`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180011110`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18001108f`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18001108f`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18001105a`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18001105a`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x1800110e5`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x1800110e5`

## pseudocode

```c
__int64 __fastcall SetServiceStartType(LPCWSTR lpServiceName, DWORD dwStartType)
{
  SC_HANDLE v4; // rax
  SC_HANDLE v5; // rsi
  signed int v6; // eax
  unsigned int v7; // ebx
  SC_HANDLE v8; // rax
  SC_HANDLE v9; // rdi
  signed int v10; // eax
  signed int LastError; // eax

  v4 = OpenSCManagerW(0, 0, 0x10000000u);
  v5 = v4;
  if ( v4 )
  {
    v8 = OpenServiceW(v4, lpServiceName, 0x10000000u);
    v9 = v8;
    if ( v8 )
    {
      v7 = 0;
      if ( !ChangeServiceConfigW(v8, 0xFFFFFFFF, dwStartType, 0xFFFFFFFF, 0, 0, 0, 0, 0, 0, 0) )
      {
        LastError = GetLastError();
        v7 = LastError;
        if ( LastError > 0 )
          v7 = (unsigned __int16)LastError | 0x80070000;
      }
      CloseServiceHandle(v9);
    }
    else
    {
      v10 = GetLastError();
      v7 = v10;
      if ( v10 > 0 )
        v7 = (unsigned __int16)v10 | 0x80070000;
    }
    CloseServiceHandle(v5);
  }
  else
  {
    v6 = GetLastError();
    v7 = v6;
    if ( v6 > 0 )
      return (unsigned __int16)v6 | 0x80070000;
  }
  return v7;
}

```

## disassembly

```asm
0x180011040  push    rbx
0x180011042  push    rbp
0x180011043  push    rsi
0x180011044  push    rdi
0x180011045  sub     rsp, 68h
0x180011049  mov     ebp, edx
0x18001104b  mov     rbx, rcx
0x18001104e  mov     edi, 10000000h
0x180011053  xor     edx, edx; lpDatabaseName
0x180011055  mov     r8d, edi; dwDesiredAccess
0x180011058  xor     ecx, ecx; lpMachineName
0x18001105a  call    cs:__imp_OpenSCManagerW
0x180011060  mov     rsi, rax
0x180011063  test    rax, rax
0x180011066  jnz     short loc_180011086
0x180011068  call    cs:__imp_GetLastError
0x18001106e  mov     ebx, eax
0x180011070  test    eax, eax
0x180011072  jle     loc_180011116
0x180011078  movzx   ebx, ax
0x18001107b  or      ebx, 80070000h
0x180011081  jmp     loc_180011116
0x180011086  mov     r8d, edi; dwDesiredAccess
0x180011089  mov     rdx, rbx; lpServiceName
0x18001108c  mov     rcx, rsi; hSCManager
0x18001108f  call    cs:__imp_OpenServiceW
0x180011095  mov     rdi, rax
0x180011098  test    rax, rax
0x18001109b  jnz     short loc_1800110B4
0x18001109d  call    cs:__imp_GetLastError
0x1800110a3  mov     ebx, eax
0x1800110a5  test    eax, eax
0x1800110a7  jle     short loc_18001110D
0x1800110a9  movzx   ebx, ax
0x1800110ac  or      ebx, 80070000h
0x1800110b2  jmp     short loc_18001110D
0x1800110b4  xor     ebx, ebx
0x1800110b6  or      edx, 0FFFFFFFFh; dwServiceType
0x1800110b9  mov     [rsp+88h+lpDisplayName], rbx; lpDisplayName
0x1800110be  mov     r9d, edx; dwErrorControl
0x1800110c1  mov     [rsp+88h+lpPassword], rbx; lpPassword
0x1800110c6  mov     r8d, ebp; dwStartType
0x1800110c9  mov     [rsp+88h+lpServiceStartName], rbx; lpServiceStartName
0x1800110ce  mov     rcx, rdi; hService
0x1800110d1  mov     [rsp+88h+lpDependencies], rbx; lpDependencies
0x1800110d6  mov     [rsp+88h+lpdwTagId], rbx; lpdwTagId
0x1800110db  mov     [rsp+88h+lpLoadOrderGroup], rbx; lpLoadOrderGroup
0x1800110e0  mov     [rsp+88h+lpBinaryPathName], rbx; lpBinaryPathName
0x1800110e5  call    cs:__imp_ChangeServiceConfigW
0x1800110eb  test    eax, eax
0x1800110ed  jnz     short loc_180011104
0x1800110ef  call    cs:__imp_GetLastError
0x1800110f5  mov     ebx, eax
0x1800110f7  test    eax, eax
0x1800110f9  jle     short loc_180011104
0x1800110fb  movzx   ebx, ax
0x1800110fe  or      ebx, 80070000h
0x180011104  mov     rcx, rdi; hSCObject
0x180011107  call    cs:__imp_CloseServiceHandle
0x18001110d  mov     rcx, rsi; hSCObject
0x180011110  call    cs:__imp_CloseServiceHandle
0x180011116  mov     eax, ebx
0x180011118  add     rsp, 68h
0x18001111c  pop     rdi
0x18001111d  pop     rsi
0x18001111e  pop     rbp
0x18001111f  pop     rbx
0x180011120  retn
```
