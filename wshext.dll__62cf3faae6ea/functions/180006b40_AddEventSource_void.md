# AddEventSource(void)

- ea: `0x180006b40`
- end: `0x180006cfd`
- name: `?AddEventSource@@YAXXZ`
- size: `445`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180006df0`

## callees

- `0x180006b40`
- `0x18000d1c0`

## import_xrefs

- `msvcrt!strcpy_s` at `0x180006b8c`
- `msvcrt!strcpy_s` at `0x180006b8c`
- `ADVAPI32!RegCreateKeyA` at `0x180006ba4`
- `ADVAPI32!RegCreateKeyA` at `0x180006c5a`
- `ADVAPI32!RegCreateKeyA` at `0x180006ba4`
- `ADVAPI32!RegCreateKeyA` at `0x180006c5a`
- `ADVAPI32!RegSetValueExA` at `0x180006be9`
- `ADVAPI32!RegSetValueExA` at `0x180006c23`
- `ADVAPI32!RegSetValueExA` at `0x180006c95`
- `ADVAPI32!RegSetValueExA` at `0x180006ccb`
- `ADVAPI32!RegSetValueExA` at `0x180006be9`
- `ADVAPI32!RegSetValueExA` at `0x180006c23`
- `ADVAPI32!RegSetValueExA` at `0x180006c95`
- `ADVAPI32!RegSetValueExA` at `0x180006ccb`
- `ADVAPI32!RegCloseKey` at `0x180006c3a`
- `ADVAPI32!RegCloseKey` at `0x180006cda`
- `ADVAPI32!RegCloseKey` at `0x180006c3a`
- `ADVAPI32!RegCloseKey` at `0x180006cda`

## string_xrefs

- `0x180006b6d`: `%SystemRoot%\System32\wshext.dll`
- `0x180006b9d`: `SYSTEM\CurrentControlSet\Services\EventLog\Application\WSH`
- `0x180006c53`: `SYSTEM\CurrentControlSet\Services\EventLog\System\Windows Script Host`

## pseudocode

```c
void AddEventSource(void)
{
  __int64 v0; // rbx
  __int64 v1; // rax
  BYTE Data[8]; // [rsp+30h] [rbp-19h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-11h] BYREF
  BYTE Destination[80]; // [rsp+40h] [rbp-9h] BYREF

  if ( Global::g_fWindowsNT )
  {
    phkResult = 0;
    *(_DWORD *)Data = 0;
    strcpy_s((char *)Destination, 0x50u, "%SystemRoot%\\System32\\wshext.dll");
    if ( !RegCreateKeyA(
            HKEY_LOCAL_MACHINE,
            "SYSTEM\\CurrentControlSet\\Services\\EventLog\\Application\\WSH",
            &phkResult) )
    {
      v0 = -1;
      v1 = -1;
      do
        ++v1;
      while ( Destination[v1] );
      if ( !RegSetValueExA(phkResult, "EventMessageFile", 0, 2u, Destination, v1 + 1) )
      {
        *(_DWORD *)Data = 31;
        if ( !RegSetValueExA(phkResult, "TypesSupported", 0, 4u, Data, 4u) )
        {
          if ( phkResult )
          {
            RegCloseKey(phkResult);
            phkResult = 0;
          }
          if ( !RegCreateKeyA(
                  HKEY_LOCAL_MACHINE,
                  "SYSTEM\\CurrentControlSet\\Services\\EventLog\\System\\Windows Script Host",
                  &phkResult) )
          {
            do
              ++v0;
            while ( Destination[v0] );
            if ( !RegSetValueExA(phkResult, "EventMessageFile", 0, 2u, Destination, v0 + 1) )
            {
              *(_DWORD *)Data = 24;
              RegSetValueExA(phkResult, "TypesSupported", 0, 4u, Data, 4u);
            }
          }
        }
      }
    }
    if ( phkResult )
      RegCloseKey(phkResult);
  }
}

```

## disassembly

```asm
0x180006b40  mov     [rsp-8+arg_0], rbx
0x180006b45  push    rbp
0x180006b46  lea     rbp, [rsp-57h]
0x180006b4b  sub     rsp, 0A0h
0x180006b52  mov     rax, cs:__security_cookie
0x180006b59  xor     rax, rsp
0x180006b5c  mov     [rbp+57h+var_10], rax
0x180006b60  cmp     cs:?g_fWindowsNT@Global@@2_NA, 0; bool Global::g_fWindowsNT
0x180006b67  jz      loc_180006CE0
0x180006b6d  lea     r8, aSystemrootSyst; "%SystemRoot%\\System32\\wshext.dll"
0x180006b74  mov     [rbp+57h+phkResult], 0
0x180006b7c  mov     edx, 50h ; 'P'; SizeInBytes
0x180006b81  mov     dword ptr [rbp+57h+Data], 0
0x180006b88  lea     rcx, [rbp+57h+Destination]; Destination
0x180006b8c  call    cs:__imp_strcpy_s
0x180006b92  lea     r8, [rbp+57h+phkResult]; phkResult
0x180006b96  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180006b9d  lea     rdx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Services\\Ev"...
0x180006ba4  call    cs:__imp_RegCreateKeyA
0x180006baa  test    eax, eax
0x180006bac  jnz     loc_180006CD1
0x180006bb2  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180006bb6  lea     rcx, [rbp+57h+Destination]
0x180006bba  mov     rax, rbx
0x180006bbd  inc     rax
0x180006bc0  cmp     byte ptr [rcx+rax], 0
0x180006bc4  jnz     short loc_180006BBD
0x180006bc6  mov     rcx, [rbp+57h+phkResult]; hKey
0x180006bca  lea     rdx, aEventmessagefi; "EventMessageFile"
0x180006bd1  inc     eax
0x180006bd3  mov     r9d, 2; dwType
0x180006bd9  mov     [rsp+0A0h+cbData], eax; cbData
0x180006bdd  xor     r8d, r8d; Reserved
0x180006be0  lea     rax, [rbp+57h+Destination]
0x180006be4  mov     [rsp+0A0h+lpData], rax; lpData
0x180006be9  call    cs:__imp_RegSetValueExA
0x180006bef  test    eax, eax
0x180006bf1  jnz     loc_180006CD1
0x180006bf7  mov     rcx, [rbp+57h+phkResult]; hKey
0x180006bfb  lea     rax, [rbp+57h+Data]
0x180006bff  mov     [rsp+0A0h+cbData], 4; cbData
0x180006c07  lea     rdx, aTypessupported; "TypesSupported"
0x180006c0e  mov     r9d, 4; dwType
0x180006c14  mov     [rsp+0A0h+lpData], rax; lpData
0x180006c19  xor     r8d, r8d; Reserved
0x180006c1c  mov     dword ptr [rbp+57h+Data], 1Fh
0x180006c23  call    cs:__imp_RegSetValueExA
0x180006c29  test    eax, eax
0x180006c2b  jnz     loc_180006CD1
0x180006c31  mov     rcx, [rbp+57h+phkResult]; hKey
0x180006c35  test    rcx, rcx
0x180006c38  jz      short loc_180006C48
0x180006c3a  call    cs:__imp_RegCloseKey
0x180006c40  mov     [rbp+57h+phkResult], 0
0x180006c48  lea     r8, [rbp+57h+phkResult]; phkResult
0x180006c4c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180006c53  lea     rdx, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Services\\Ev"...
0x180006c5a  call    cs:__imp_RegCreateKeyA
0x180006c60  test    eax, eax
0x180006c62  jnz     short loc_180006CD1
0x180006c64  lea     rax, [rbp+57h+Destination]
0x180006c68  inc     rbx
0x180006c6b  cmp     byte ptr [rax+rbx], 0
0x180006c6f  jnz     short loc_180006C68
0x180006c71  mov     rcx, [rbp+57h+phkResult]; hKey
0x180006c75  lea     eax, [rbx+1]
0x180006c78  mov     [rsp+0A0h+cbData], eax; cbData
0x180006c7c  lea     rdx, aEventmessagefi; "EventMessageFile"
0x180006c83  lea     rax, [rbp+57h+Destination]
0x180006c87  mov     r9d, 2; dwType
0x180006c8d  xor     r8d, r8d; Reserved
0x180006c90  mov     [rsp+0A0h+lpData], rax; lpData
0x180006c95  call    cs:__imp_RegSetValueExA
0x180006c9b  test    eax, eax
0x180006c9d  jnz     short loc_180006CD1
0x180006c9f  mov     rcx, [rbp+57h+phkResult]; hKey
0x180006ca3  lea     rax, [rbp+57h+Data]
0x180006ca7  mov     [rsp+0A0h+cbData], 4; cbData
0x180006caf  lea     rdx, aTypessupported; "TypesSupported"
0x180006cb6  mov     r9d, 4; dwType
0x180006cbc  mov     [rsp+0A0h+lpData], rax; lpData
0x180006cc1  xor     r8d, r8d; Reserved
0x180006cc4  mov     dword ptr [rbp+57h+Data], 18h
0x180006ccb  call    cs:__imp_RegSetValueExA
0x180006cd1  mov     rcx, [rbp+57h+phkResult]; hKey
0x180006cd5  test    rcx, rcx
0x180006cd8  jz      short loc_180006CE0
0x180006cda  call    cs:__imp_RegCloseKey
0x180006ce0  mov     rcx, [rbp+57h+var_10]
0x180006ce4  xor     rcx, rsp; StackCookie
0x180006ce7  call    __security_check_cookie
0x180006cec  mov     rbx, [rsp+0A0h+arg_0]
0x180006cf4  add     rsp, 0A0h
0x180006cfb  pop     rbp
0x180006cfc  retn
```
