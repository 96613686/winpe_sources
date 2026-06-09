# CContainerHelper::GetAllowListenersInsideArgonContainer(void)

- ea: `0x180042c18`
- end: `0x180042d97`
- name: `?GetAllowListenersInsideArgonContainer@CContainerHelper@@CAKXZ`
- size: `383`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180046ea0`

## callees

- `0x1800321f0`
- `0x180042c18`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180042d64`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180042d64`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x180042c7d`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x180042c7d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180042cb6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180042d45`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180042cb6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180042d45`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180042d79`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180042d79`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180042c61`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180042cff`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180042c61`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180042cff`

## string_xrefs

- `0x180042caf`: `AllowListenersInsideArgonContainer`

## pseudocode

```c
__int64 CContainerHelper::GetAllowListenersInsideArgonContainer(void)
{
  int v0; // eax
  BYTE Data[4]; // [rsp+30h] [rbp-50h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-4Ch] BYREF
  DWORD Type; // [rsp+38h] [rbp-48h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-40h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-38h] BYREF
  BYTE v7[16]; // [rsp+50h] [rbp-30h] BYREF
  __int128 v8; // [rsp+60h] [rbp-20h]
  __int16 v9; // [rsp+70h] [rbp-10h]

  hKey = 0;
  *(_DWORD *)Data = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\Terminal Server", 0, 0x20019u, &hKey) )
  {
    cbData = 0;
    Type = 0;
    phkResult = 0;
    if ( (unsigned int)RtlGetCurrentServiceSessionId() )
    {
      cbData = 4;
      if ( RegQueryValueExW(hKey, L"AllowListenersInsideArgonContainer", 0, &Type, Data, &cbData) || Type != 4 )
      {
        v0 = 0;
        *(_DWORD *)Data = 0;
      }
      else
      {
        v0 = *(_DWORD *)Data;
      }
      if ( v0 )
      {
        *(_DWORD *)Data = 0;
        if ( !RegOpenKeyExW(
                HKEY_LOCAL_MACHINE,
                L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion",
                0,
                0x20019u,
                &phkResult) )
        {
          cbData = 34;
          v9 = 0;
          *(_OWORD *)v7 = 0;
          v8 = 0;
          if ( !RegQueryValueExW(phkResult, L"EditionID", 0, &Type, v7, &cbData)
            && Type == 1
            && !(unsigned int)_o__wcsnicmp(v7, L"ContainerOSPlus", 15) )
          {
            *(_DWORD *)Data = 1;
          }
        }
      }
    }
    RegCloseKey(hKey);
  }
  return *(unsigned int *)Data;
}

```

## disassembly

```asm
0x180042c18  push    rbp
0x180042c1a  mov     rbp, rsp
0x180042c1d  sub     rsp, 80h
0x180042c24  mov     rax, cs:__security_cookie
0x180042c2b  xor     rax, rsp
0x180042c2e  mov     [rbp+var_8], rax
0x180042c32  lea     rax, [rbp+hKey]
0x180042c36  mov     [rbp+hKey], 0
0x180042c3e  mov     r9d, 20019h; samDesired
0x180042c44  mov     [rsp+80h+phkResult], rax; phkResult
0x180042c49  xor     r8d, r8d; ulOptions
0x180042c4c  mov     dword ptr [rbp+Data], 0
0x180042c53  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Control\\Ter"...
0x180042c5a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180042c61  call    cs:__imp_RegOpenKeyExW
0x180042c67  test    eax, eax
0x180042c69  jnz     loc_180042D7F
0x180042c6f  mov     [rbp+cbData], eax
0x180042c72  mov     [rbp+Type], eax
0x180042c75  mov     [rbp+var_38], 0
0x180042c7d  call    cs:__imp_RtlGetCurrentServiceSessionId
0x180042c83  test    eax, eax
0x180042c85  jz      loc_180042D75
0x180042c8b  mov     rcx, [rbp+hKey]; hKey
0x180042c8f  lea     rax, [rbp+cbData]
0x180042c93  mov     [rsp+80h+lpcbData], rax; lpcbData
0x180042c98  lea     r9, [rbp+Type]; lpType
0x180042c9c  lea     rax, [rbp+Data]
0x180042ca0  mov     [rbp+cbData], 4
0x180042ca7  xor     r8d, r8d; lpReserved
0x180042caa  mov     [rsp+80h+phkResult], rax; lpData
0x180042caf  lea     rdx, aAllowlisteners; "AllowListenersInsideArgonContainer"
0x180042cb6  call    cs:__imp_RegQueryValueExW
0x180042cbc  test    eax, eax
0x180042cbe  jnz     short loc_180042CCB
0x180042cc0  cmp     [rbp+Type], 4
0x180042cc4  jnz     short loc_180042CCB
0x180042cc6  mov     eax, dword ptr [rbp+Data]
0x180042cc9  jmp     short loc_180042CD0
0x180042ccb  xor     eax, eax
0x180042ccd  mov     dword ptr [rbp+Data], eax
0x180042cd0  test    eax, eax
0x180042cd2  jz      loc_180042D75
0x180042cd8  lea     rax, [rbp+var_38]
0x180042cdc  mov     dword ptr [rbp+Data], 0
0x180042ce3  mov     r9d, 20019h; samDesired
0x180042ce9  mov     [rsp+80h+phkResult], rax; phkResult
0x180042cee  xor     r8d, r8d; ulOptions
0x180042cf1  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180042cf8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180042cff  call    cs:__imp_RegOpenKeyExW
0x180042d05  test    eax, eax
0x180042d07  jnz     short loc_180042D75
0x180042d09  mov     rcx, [rbp+var_38]; hKey
0x180042d0d  lea     r9, [rbp+Type]; lpType
0x180042d11  xor     eax, eax
0x180042d13  mov     [rbp+cbData], 22h ; '"'
0x180042d1a  mov     [rbp+var_10], ax
0x180042d1e  lea     rdx, aEditionid; "EditionID"
0x180042d25  xorps   xmm0, xmm0
0x180042d28  lea     rax, [rbp+cbData]
0x180042d2c  mov     [rsp+80h+lpcbData], rax; lpcbData
0x180042d31  xor     r8d, r8d; lpReserved
0x180042d34  lea     rax, [rbp+var_30]
0x180042d38  mov     [rsp+80h+phkResult], rax; lpData
0x180042d3d  movups  xmmword ptr [rbp+var_30], xmm0
0x180042d41  movups  [rbp+var_20], xmm0
0x180042d45  call    cs:__imp_RegQueryValueExW
0x180042d4b  test    eax, eax
0x180042d4d  jnz     short loc_180042D75
0x180042d4f  cmp     [rbp+Type], 1
0x180042d53  jnz     short loc_180042D75
0x180042d55  lea     r8d, [rax+0Fh]
0x180042d59  lea     rdx, aContainerosplu; "ContainerOSPlus"
0x180042d60  lea     rcx, [rbp+var_30]
0x180042d64  call    cs:__imp__o__wcsnicmp
0x180042d6a  test    eax, eax
0x180042d6c  jnz     short loc_180042D75
0x180042d6e  mov     dword ptr [rbp+Data], 1
0x180042d75  mov     rcx, [rbp+hKey]; hKey
0x180042d79  call    cs:__imp_RegCloseKey
0x180042d7f  mov     eax, dword ptr [rbp+Data]
0x180042d82  mov     rcx, [rbp+var_8]
0x180042d86  xor     rcx, rsp; StackCookie
0x180042d89  call    __security_check_cookie
0x180042d8e  add     rsp, 80h
0x180042d95  pop     rbp
0x180042d96  retn
```
