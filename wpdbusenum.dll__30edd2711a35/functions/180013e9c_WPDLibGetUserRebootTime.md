# WPDLibGetUserRebootTime

- ea: `0x180013e9c`
- end: `0x180014041`
- name: `WPDLibGetUserRebootTime`
- size: `421`
- prototype: `__int64 __fastcall(unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800069d0`

## callees

- `0x180006090`
- `0x180013e9c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014001`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014013`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014030`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014001`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014013`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014030`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001400b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001400b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013fd9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013feb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013fd9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013feb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013f81`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013f81`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180013fc0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180013fc0`
- `KERNEL32!RegOpenCurrentUser` at `0x180013f4e`
- `KERNEL32!RegOpenCurrentUser` at `0x180013f4e`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180013ff9`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180013ff9`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180013f37`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180013f37`
- `WTSAPI32!WTSEnumerateSessionsW` at `0x180013eea`
- `WTSAPI32!WTSEnumerateSessionsW` at `0x180013eea`
- `WTSAPI32!WTSQueryUserToken` at `0x180013f25`
- `WTSAPI32!WTSQueryUserToken` at `0x180013f25`
- `WTSAPI32!WTSFreeMemory` at `0x180014028`
- `WTSAPI32!WTSFreeMemory` at `0x180014028`

## pseudocode

```c
__int64 __fastcall WPDLibGetUserRebootTime(unsigned int *a1)
{
  unsigned int v2; // esi
  __int64 i; // rbx
  __int64 v4; // r8
  __int64 v5; // r9
  HKEY hKey; // [rsp+30h] [rbp-28h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-20h] BYREF
  void *phToken; // [rsp+40h] [rbp-18h] BYREF
  PWTS_SESSION_INFOW ppSessionInfo; // [rsp+48h] [rbp-10h] BYREF
  DWORD pCount; // [rsp+80h] [rbp+28h] BYREF
  unsigned int Data; // [rsp+88h] [rbp+30h] BYREF
  DWORD cbData; // [rsp+90h] [rbp+38h] BYREF
  DWORD Type; // [rsp+98h] [rbp+40h] BYREF

  *a1 = -1;
  phkResult = 0;
  v2 = 3;
  phToken = 0;
  ppSessionInfo = 0;
  pCount = 0;
  if ( WTSEnumerateSessionsW(0, 0, 1u, &ppSessionInfo, &pCount) )
  {
    for ( i = 0; (unsigned int)i < pCount; i = (unsigned int)(i + 1) )
    {
      if ( (unsigned int)SessionNotActive((unsigned int)ppSessionInfo[i].State) )
      {
        if ( WTSQueryUserToken(*(_DWORD *)(v5 + 8 * v4), &phToken) )
        {
          if ( ImpersonateLoggedOnUser(phToken) )
          {
            if ( !RegOpenCurrentUser(0x20019u, &phkResult) )
            {
              hKey = 0;
              if ( !RegOpenKeyExW(
                      phkResult,
                      L"SOFTWARE\\Policies\\Microsoft\\Windows\\RemovableStorageDevices",
                      0,
                      0x20019u,
                      &hKey) )
              {
                Data = 0;
                Type = 4;
                cbData = 4;
                if ( !RegQueryValueExW(hKey, L"RebootTimeinSeconds", 0, &Type, (LPBYTE)&Data, &cbData) )
                {
                  v2 = 0;
                  if ( Data < *a1 )
                    *a1 = Data;
                }
                RegCloseKey(hKey);
                hKey = 0;
              }
              RegCloseKey(phkResult);
              phkResult = 0;
            }
            RevertToSelf();
          }
          else
          {
            GetLastError();
          }
          CloseHandle(phToken);
        }
        else
        {
          GetLastError();
        }
      }
    }
    WTSFreeMemory(ppSessionInfo);
  }
  else
  {
    GetLastError();
  }
  return v2;
}

```

## disassembly

```asm
0x180013e9c  push    rbp
0x180013e9e  push    rbx
0x180013e9f  push    rsi
0x180013ea0  push    rdi
0x180013ea1  mov     rbp, rsp
0x180013ea4  sub     rsp, 58h
0x180013ea8  mov     rdi, rcx
0x180013eab  mov     dword ptr [rcx], 0FFFFFFFFh
0x180013eb1  lea     rax, [rbp+arg_0]
0x180013eb5  mov     [rbp+phkResult], 0
0x180013ebd  mov     esi, 3
0x180013ec2  mov     [rbp+phToken], 0
0x180013eca  lea     r9, [rbp+ppSessionInfo]; ppSessionInfo
0x180013ece  mov     [rbp+ppSessionInfo], 0
0x180013ed6  xor     edx, edx; Reserved
0x180013ed8  mov     [rbp+arg_0], 0
0x180013edf  xor     ecx, ecx; hServer
0x180013ee1  mov     [rsp+58h+pCount], rax; pCount
0x180013ee6  lea     r8d, [rsi-2]; Version
0x180013eea  call    cs:__imp_WTSEnumerateSessionsW
0x180013ef0  test    eax, eax
0x180013ef2  jz      loc_180014030
0x180013ef8  xor     ebx, ebx
0x180013efa  cmp     [rbp+arg_0], ebx
0x180013efd  jbe     loc_180014024
0x180013f03  mov     r9, [rbp+ppSessionInfo]
0x180013f07  lea     r8, [rbx+rbx*2]
0x180013f0b  mov     ecx, [r9+r8*8+10h]
0x180013f10  call    SessionNotActive
0x180013f15  test    eax, eax
0x180013f17  jz      loc_180014019
0x180013f1d  mov     ecx, [r9+r8*8]; SessionId
0x180013f21  lea     rdx, [rbp+phToken]; phToken
0x180013f25  call    cs:__imp_WTSQueryUserToken
0x180013f2b  test    eax, eax
0x180013f2d  jz      loc_180014013
0x180013f33  mov     rcx, [rbp+phToken]; hToken
0x180013f37  call    cs:__imp_ImpersonateLoggedOnUser
0x180013f3d  test    eax, eax
0x180013f3f  jz      loc_180014001
0x180013f45  lea     rdx, [rbp+phkResult]; phkResult
0x180013f49  mov     ecx, 20019h; samDesired
0x180013f4e  call    cs:__imp_RegOpenCurrentUser
0x180013f54  test    eax, eax
0x180013f56  jnz     loc_180013FF9
0x180013f5c  mov     rcx, [rbp+phkResult]; hKey
0x180013f60  lea     rax, [rbp+hKey]
0x180013f64  mov     r9d, 20019h; samDesired
0x180013f6a  mov     [rsp+58h+pCount], rax; phkResult
0x180013f6f  xor     r8d, r8d; ulOptions
0x180013f72  mov     [rbp+hKey], 0
0x180013f7a  lea     rdx, aSoftwarePolici_0; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x180013f81  call    cs:__imp_RegOpenKeyExW
0x180013f87  test    eax, eax
0x180013f89  jnz     short loc_180013FE7
0x180013f8b  mov     rcx, [rbp+hKey]; hKey
0x180013f8f  lea     r9, [rbp+Type]; lpType
0x180013f93  mov     [rbp+Data], eax
0x180013f96  lea     rdx, aReboottimeinse_0; "RebootTimeinSeconds"
0x180013f9d  lea     rax, [rbp+cbData]
0x180013fa1  mov     [rbp+Type], 4
0x180013fa8  mov     [rsp+58h+lpcbData], rax; lpcbData
0x180013fad  xor     r8d, r8d; lpReserved
0x180013fb0  lea     rax, [rbp+Data]
0x180013fb4  mov     [rbp+cbData], 4
0x180013fbb  mov     [rsp+58h+pCount], rax; lpData
0x180013fc0  call    cs:__imp_RegQueryValueExW
0x180013fc6  test    eax, eax
0x180013fc8  jnz     short loc_180013FD5
0x180013fca  mov     eax, [rbp+Data]
0x180013fcd  xor     esi, esi
0x180013fcf  cmp     eax, [rdi]
0x180013fd1  jnb     short loc_180013FD5
0x180013fd3  mov     [rdi], eax
0x180013fd5  mov     rcx, [rbp+hKey]; hKey
0x180013fd9  call    cs:__imp_RegCloseKey
0x180013fdf  mov     [rbp+hKey], 0
0x180013fe7  mov     rcx, [rbp+phkResult]; hKey
0x180013feb  call    cs:__imp_RegCloseKey
0x180013ff1  mov     [rbp+phkResult], 0
0x180013ff9  call    cs:__imp_RevertToSelf
0x180013fff  jmp     short loc_180014007
0x180014001  call    cs:__imp_GetLastError
0x180014007  mov     rcx, [rbp+phToken]; hObject
0x18001400b  call    cs:__imp_CloseHandle
0x180014011  jmp     short loc_180014019
0x180014013  call    cs:__imp_GetLastError
0x180014019  inc     ebx
0x18001401b  cmp     ebx, [rbp+arg_0]
0x18001401e  jb      loc_180013F03
0x180014024  mov     rcx, [rbp+ppSessionInfo]; pMemory
0x180014028  call    cs:__imp_WTSFreeMemory
0x18001402e  jmp     short loc_180014036
0x180014030  call    cs:__imp_GetLastError
0x180014036  mov     eax, esi
0x180014038  add     rsp, 58h
0x18001403c  pop     rdi
0x18001403d  pop     rsi
0x18001403e  pop     rbx
0x18001403f  pop     rbp
0x180014040  retn
```
