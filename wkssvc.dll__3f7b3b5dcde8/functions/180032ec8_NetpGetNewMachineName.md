# NetpGetNewMachineName

- ea: `0x180032ec8`
- end: `0x180032f9c`
- name: `NetpGetNewMachineName`
- size: `212`
- prototype: `__int64 __fastcall(LPVOID *Buffer)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180028a80`
- `0x180028cb0`

## callees

- `0x180032ec8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180032f0c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180032f0c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180032f8c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180032f8c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180032f3f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180032f80`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180032f3f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180032f80`
- `netutils!NetApiBufferAllocate` at `0x180032f51`
- `netutils!NetApiBufferAllocate` at `0x180032f51`

## string_xrefs

- `0x180032f05`: `System\CurrentControlSet\Control\ComputerName\ComputerName`
- `0x180032f23`: `ComputerName`
- `0x180032f71`: `ComputerName`

## pseudocode

```c
__int64 __fastcall NetpGetNewMachineName(LPVOID *Buffer)
{
  DWORD v2; // ebx
  DWORD cbData; // [rsp+50h] [rbp+20h] BYREF
  DWORD Type; // [rsp+58h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+60h] [rbp+30h] BYREF

  *Buffer = 0;
  hKey = 0;
  cbData = 0;
  v2 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Control\\ComputerName\\ComputerName",
         0,
         0x20019u,
         &hKey);
  if ( !v2 )
  {
    Type = 0;
    v2 = RegQueryValueExW(hKey, L"ComputerName", 0, &Type, 0, &cbData);
    if ( !v2 )
    {
      v2 = NetApiBufferAllocate(cbData, Buffer);
      if ( !v2 )
        v2 = RegQueryValueExW(hKey, L"ComputerName", 0, &Type, (LPBYTE)*Buffer, &cbData);
    }
    RegCloseKey(hKey);
  }
  return v2;
}

```

## disassembly

```asm
0x180032ec8  push    rbp
0x180032eca  push    rbx
0x180032ecb  push    rdi
0x180032ecc  mov     rbp, rsp
0x180032ecf  sub     rsp, 30h
0x180032ed3  mov     rdi, rcx
0x180032ed6  mov     qword ptr [rcx], 0
0x180032edd  lea     rax, [rbp+hKey]
0x180032ee1  mov     [rbp+hKey], 0
0x180032ee9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180032ef0  mov     [rsp+30h+phkResult], rax; phkResult
0x180032ef5  mov     r9d, 20019h; samDesired
0x180032efb  mov     [rbp+cbData], 0
0x180032f02  xor     r8d, r8d; ulOptions
0x180032f05  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Control\\Com"...
0x180032f0c  call    cs:__imp_RegOpenKeyExW
0x180032f12  mov     ebx, eax
0x180032f14  test    eax, eax
0x180032f16  jnz     short loc_180032F92
0x180032f18  mov     rcx, [rbp+hKey]; hKey
0x180032f1c  lea     r9, [rbp+Type]; lpType
0x180032f20  mov     [rbp+Type], eax
0x180032f23  lea     rdx, aComputername; "ComputerName"
0x180032f2a  lea     rax, [rbp+cbData]
0x180032f2e  xor     r8d, r8d; lpReserved
0x180032f31  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180032f36  mov     [rsp+30h+phkResult], 0; lpData
0x180032f3f  call    cs:__imp_RegQueryValueExW
0x180032f45  mov     ebx, eax
0x180032f47  test    eax, eax
0x180032f49  jnz     short loc_180032F88
0x180032f4b  mov     ecx, [rbp+cbData]; ByteCount
0x180032f4e  mov     rdx, rdi; Buffer
0x180032f51  call    cs:__imp_NetApiBufferAllocate
0x180032f57  mov     ebx, eax
0x180032f59  test    eax, eax
0x180032f5b  jnz     short loc_180032F88
0x180032f5d  mov     rcx, [rbp+hKey]; hKey
0x180032f61  lea     rax, [rbp+cbData]
0x180032f65  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180032f6a  lea     r9, [rbp+Type]; lpType
0x180032f6e  mov     rax, [rdi]
0x180032f71  lea     rdx, aComputername; "ComputerName"
0x180032f78  xor     r8d, r8d; lpReserved
0x180032f7b  mov     [rsp+30h+phkResult], rax; lpData
0x180032f80  call    cs:__imp_RegQueryValueExW
0x180032f86  mov     ebx, eax
0x180032f88  mov     rcx, [rbp+hKey]; hKey
0x180032f8c  call    cs:__imp_RegCloseKey
0x180032f92  mov     eax, ebx
0x180032f94  add     rsp, 30h
0x180032f98  pop     rdi
0x180032f99  pop     rbx
0x180032f9a  pop     rbp
0x180032f9b  retn
```
