# GetRedirectionPolicy(void)

- ea: `0x18003f804`
- end: `0x18003f8d8`
- name: `?GetRedirectionPolicy@@YA?AU_PROCESS_MITIGATION_REDIRECTION_TRUST_POLICY@@XZ`
- size: `212`
- prototype: `_BOOL8()`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x18003ecb0`

## callees

- `0x180038ce4`
- `0x18003f804`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003f887`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003f887`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003f84d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003f84d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003f87b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003f87b`

## string_xrefs

- `0x18003f837`: `System\CurrentControlSet\Services\UPnPHost`

## pseudocode

```c
_BOOL8 GetRedirectionPolicy()
{
  int v0; // edi
  LSTATUS v1; // ebx
  DWORD Type; // [rsp+50h] [rbp+20h] BYREF
  unsigned int Data; // [rsp+58h] [rbp+28h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+38h] BYREF

  Type = 4;
  v0 = 1;
  Data = 1;
  cbData = 4;
  hKey = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\UPnPHost", 0, 0x20019u, &hKey) )
  {
    v1 = RegQueryValueExW(hKey, L"RedirectionGuard", 0, &Type, (LPBYTE)&Data, &cbData);
    RegCloseKey(hKey);
    if ( !v1 && Type == 4 )
    {
      v0 = Data;
      if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 0x40) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_2670124a663039e2f0c82c5e619b77a4_Traceguids, Data);
    }
  }
  return v0 != 0;
}

```

## disassembly

```asm
0x18003f804  push    rbp
0x18003f806  push    rbx
0x18003f807  push    rdi
0x18003f808  mov     rbp, rsp
0x18003f80b  sub     rsp, 30h
0x18003f80f  lea     rax, [rbp+hKey]
0x18003f813  mov     [rbp+Type], 4
0x18003f81a  mov     edi, 1
0x18003f81f  mov     [rsp+30h+phkResult], rax; phkResult
0x18003f824  mov     r9d, 20019h; samDesired
0x18003f82a  mov     [rbp+Data], edi
0x18003f82d  xor     r8d, r8d; ulOptions
0x18003f830  mov     [rbp+cbData], 4
0x18003f837  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\UP"...
0x18003f83e  mov     [rbp+hKey], 0
0x18003f846  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003f84d  call    cs:__imp_RegOpenKeyExW
0x18003f853  test    eax, eax
0x18003f855  jnz     short loc_18003F8C9
0x18003f857  mov     rcx, [rbp+hKey]; hKey
0x18003f85b  lea     rax, [rbp+cbData]
0x18003f85f  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18003f864  lea     r9, [rbp+Type]; lpType
0x18003f868  lea     rax, [rbp+Data]
0x18003f86c  xor     r8d, r8d; lpReserved
0x18003f86f  lea     rdx, aRedirectiongua; "RedirectionGuard"
0x18003f876  mov     [rsp+30h+phkResult], rax; lpData
0x18003f87b  call    cs:__imp_RegQueryValueExW
0x18003f881  mov     rcx, [rbp+hKey]; hKey
0x18003f885  mov     ebx, eax
0x18003f887  call    cs:__imp_RegCloseKey
0x18003f88d  test    ebx, ebx
0x18003f88f  jnz     short loc_18003F8C9
0x18003f891  cmp     [rbp+Type], 4
0x18003f895  jnz     short loc_18003F8C9
0x18003f897  mov     edi, [rbp+Data]
0x18003f89a  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f8a1  lea     rax, WPP_GLOBAL_Control
0x18003f8a8  cmp     rcx, rax
0x18003f8ab  jz      short loc_18003F8C9
0x18003f8ad  test    byte ptr [rcx+1Ch], 40h
0x18003f8b1  jz      short loc_18003F8C9
0x18003f8b3  mov     rcx, [rcx+10h]
0x18003f8b7  lea     edx, [rbx+1Ch]
0x18003f8ba  mov     r9d, edi
0x18003f8bd  lea     r8, WPP_2670124a663039e2f0c82c5e619b77a4_Traceguids
0x18003f8c4  call    WPP_SF_d
0x18003f8c9  xor     eax, eax
0x18003f8cb  test    edi, edi
0x18003f8cd  setnz   al
0x18003f8d0  add     rsp, 30h
0x18003f8d4  pop     rdi
0x18003f8d5  pop     rbx
0x18003f8d6  pop     rbp
0x18003f8d7  retn
```
