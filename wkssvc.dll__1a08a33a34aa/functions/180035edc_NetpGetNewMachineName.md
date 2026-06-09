# NetpGetNewMachineName

- ea: `0x180035edc`
- end: `0x180035fd3`
- name: `NetpGetNewMachineName`
- size: `247`
- prototype: `__int64 __fastcall(LPVOID *Buffer)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002ae70`
- `0x18002b0d0`

## callees

- `0x180035edc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180035f20`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180035f20`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035fbc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035fbc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180035f5d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180035faa`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180035f5d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180035faa`
- `netutils!NetApiBufferAllocate` at `0x180035f75`
- `netutils!NetApiBufferAllocate` at `0x180035f75`

## string_xrefs

- `0x180035f19`: `System\CurrentControlSet\Control\ComputerName\ComputerName`
- `0x180035f41`: `ComputerName`
- `0x180035f9b`: `ComputerName`

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
0x180035edc  push    rbp
0x180035ede  push    rbx
0x180035edf  push    rdi
0x180035ee0  mov     rbp, rsp
0x180035ee3  sub     rsp, 30h
0x180035ee7  mov     rdi, rcx
0x180035eea  mov     qword ptr [rcx], 0
0x180035ef1  lea     rax, [rbp+hKey]
0x180035ef5  mov     [rbp+hKey], 0
0x180035efd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180035f04  mov     [rsp+30h+phkResult], rax; phkResult
0x180035f09  mov     r9d, 20019h; samDesired
0x180035f0f  mov     [rbp+cbData], 0
0x180035f16  xor     r8d, r8d; ulOptions
0x180035f19  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Control\\Com"...
0x180035f20  call    cs:__imp_RegOpenKeyExW
0x180035f27  nop     dword ptr [rax+rax+00h]
0x180035f2c  mov     ebx, eax
0x180035f2e  test    eax, eax
0x180035f30  jnz     loc_180035FC8
0x180035f36  mov     rcx, [rbp+hKey]; hKey
0x180035f3a  lea     r9, [rbp+Type]; lpType
0x180035f3e  mov     [rbp+Type], eax
0x180035f41  lea     rdx, aComputername; "ComputerName"
0x180035f48  lea     rax, [rbp+cbData]
0x180035f4c  xor     r8d, r8d; lpReserved
0x180035f4f  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180035f54  mov     [rsp+30h+phkResult], 0; lpData
0x180035f5d  call    cs:__imp_RegQueryValueExW
0x180035f64  nop     dword ptr [rax+rax+00h]
0x180035f69  mov     ebx, eax
0x180035f6b  test    eax, eax
0x180035f6d  jnz     short loc_180035FB8
0x180035f6f  mov     ecx, [rbp+cbData]; ByteCount
0x180035f72  mov     rdx, rdi; Buffer
0x180035f75  call    cs:__imp_NetApiBufferAllocate
0x180035f7c  nop     dword ptr [rax+rax+00h]
0x180035f81  mov     ebx, eax
0x180035f83  test    eax, eax
0x180035f85  jnz     short loc_180035FB8
0x180035f87  mov     rcx, [rbp+hKey]; hKey
0x180035f8b  lea     rax, [rbp+cbData]
0x180035f8f  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180035f94  lea     r9, [rbp+Type]; lpType
0x180035f98  mov     rax, [rdi]
0x180035f9b  lea     rdx, aComputername; "ComputerName"
0x180035fa2  xor     r8d, r8d; lpReserved
0x180035fa5  mov     [rsp+30h+phkResult], rax; lpData
0x180035faa  call    cs:__imp_RegQueryValueExW
0x180035fb1  nop     dword ptr [rax+rax+00h]
0x180035fb6  mov     ebx, eax
0x180035fb8  mov     rcx, [rbp+hKey]; hKey
0x180035fbc  call    cs:__imp_RegCloseKey
0x180035fc3  nop     dword ptr [rax+rax+00h]
0x180035fc8  mov     eax, ebx
0x180035fca  add     rsp, 30h
0x180035fce  pop     rdi
0x180035fcf  pop     rbx
0x180035fd0  pop     rbp
0x180035fd1  retn
```
